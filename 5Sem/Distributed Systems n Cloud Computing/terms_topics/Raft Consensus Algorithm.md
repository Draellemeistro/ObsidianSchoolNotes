## Basics
- we have a (relatively small) group of servers
- A server is in one of three states: follower, candidate, leader
- protocol works in **terms**, starting with term 0
- Each server starts in the follower state.
- A leader is to regularly broadcast messages (perhaps just a simple **heartbeat**)
### Selecting a new leader
When follower $s*$ hasn't received anything from the alleged leader $s$ for some time, $s*$ broadcasts that it volunteers to be the next leader, increasing the term by 1. $s*$ enters the **candidate** state. Then:
- if leader $s$ receives the message, it responds by ACK that it is still the leader. $s*$ returns to the **follower** state
- if another follower $s**$ gets the election message from $s*$ and it is the first election message during the current term, $s**$ votes for $s*$. Otherwise, it simply ignores the election message from $s*$. when $s*$ has collected a majority of votes, a new term starts with a new leader

> [!done] **What is [[Raft Consensus Algorithm|Raft]]?**
> **Raft is a consensus algorithm that is designed to be easy to understand.** 
> It's equivalent to [[Paxos|Paxos]] in [[Fault Tolerance|fault-tolerance]] and performance. The difference is that it's decomposed into relatively independent subproblems, and it cleanly addresses all major pieces needed for practical systems. We hope Raft will make [[Consensus]] available to a wider audience, and that this wider audience will be able to develop a variety of higher quality consensus-based systems than are available today.
> 
> **[See Raft Visualization](https://raft.github.io/)** (Also just contains a lot of good links to info on raft, also [this](https://web.stanford.edu/~ouster/cgi-bin/cs190-winter20/lecture.php?topic=raft))

> [!quote] Regarding [[Consensus]] in [[Cloud 10 Fault Tolerance|Lecture 10]]
> **Other relevant topics:**
> - [[Fault Tolerance]]
> - **[[Cloud 8 Coordination]]:** 
> 	- [[Leader Election]]
> - [[Replication]]

#TODO se [liink](https://thesquareplanet.com/blog/students-guide-to-raft/)  oooog [link](https://www.scs.stanford.edu/20sp-cs244b/notes/raft.pdf) 
# The Basics
## Core Concepts
Below is from [here](https://medium.com/@jitenderkmr/understanding-raft-algorithm-consensus-and-leader-election-explained-faadf28fd047)
1. **Nodes (servers):** In Raft, the network is composed of several nodes or dervers
2. **Leader:** One of the nodes in the raft cluster is elected as the leader. The leader is responsible for managing the replication of logs across the cluster
3. **Follower:** All other nodes in the cluster are followers. They respond to requests from the leader and forward client requests to the leader.
4. **Candidate:** When a leader fails, a new leader needs to be elected. Nodes transition to the candidate State and initiate an election
5. **Term:** Raft operates in terms, where each term begins with an election and ends with a new leader being elected or re-elected.
6. **Log Replication:** Raft ensures that all logs across the cluster are replicated and maintained in the same order.
## Info
> [!NOTE] **Motivation:** Replicated State Machines
> Service that is replicated on multiple machines:
> - All instances produce same behavior
> - **Fault Tolerant**: Available for service as long as a majority of the servers are up.
- **Leader Based:**
	- Pick one server to be leader
	- It accepts client requests, manages replication
	- Pick a new leader if the current fails
- **Server States:**
	- Leader
	- Follower: totally passive
	- Candidate: Used for electing new leaders
- **Time divided into _terms_:**
	- Terms have numbers that increase monotonically
	- Each term starts with an election
		- one or more candidates attempting to become leader
	- Winning candidate (if any) serves as leader for the rest of the term
	- Terms allow detection of stale information
		- Each server stores current term
		- Checked on every request
		- Term numbers increase monotonically
	- Different servers observe term transitions differently.
- Request-response protocol between servers ( [[Remote Procedure Call (RPC)]])2 request types:
	- RequestVote
	- AppendEntries (also serves as heartbeat)

# Visuals
![[image_Raft Consensus Algorithm.png]]
![[image_Raft Consensus Algorithm-1.png]]
# Expanded Info
## [[Leader Election]]
#### All servers start as followers
- **No heartbeat (AppendEntries)? Start election:**
    - Increment current term
    - Vote for self
    - Send RequestVote requests to all other servers
- **Election outcomes**:
    - Receive votes from majority of cluster: become leader, start sending heartbeats to prevent additional elections
    - Receive AppendEntries from some other server in the new term: revert back to follower
    - Timeout: start a new election
- Each server votes for at most one candidate in a given term
- **Election Safety**: only one server can be elected leader in a given term
- **Availability**: randomized election timeouts reduce split votes


## Log Replication
- Handled by leader
- When client request arrives:
    - Append to local log
    - Replicate to other servers using AppendEntries requests
    - _Committed_: entry replicated by leader to majority of servers
    - Once committed, apply to local state machine
    - Return result to client
    - Notify other servers of committed entries in future AppendEntries requests
- Log entries: index, term, command
- Logs can become inconsistent after leader crashes
- Raft maintains a high level of coherency between logs (Log Matching Property):
    - If entries in different logs have same term and index, then
        - They also have the same command
        - The two logs are identical up through that entry
- AppendEntries consistency check preserves above properties.
- Leader forces other logs to match its own:
    - `nextIndex` for each follower (initialized to leader's log length)
    - If AppendEntries fails, reduce `nextIndex` for that follower and retry.
    - If follower receives conflicting entries but consistency check passes, removes all conflicting entries

## Safety
- Must ensure that the leader for new term always holds all of the log entries committed in previous terms (Leader Completeness Property).
- Step 1: restriction on elections: don't vote for a candidate unless candidate's log is at least as up-to-date as yours.
- Compare indexes and terms from last log entries.
- Step 2: be _very_ careful about when an entry is considered committed
    - As soon as replicated on majority? Unsafe!
    - Committed => entry in _current term_ replicated on majority
        - All preceding entries also committed because of Log Matching Property

## Persistent Storage
- Each server stores the following in persistent storage (e.g. disk or flash):
    - Current term
    - Most recent vote granted
    - Log
- These must be recovered from persistent storage after a crash
- If a server loses its persistent storage, it cannot participate in the cluster anymore
## Client Interactions
- Clients interact only with the leader
- Initially, a client can send a request to any server
    - If not leader, it rejects request, returns info about most recent leader
    - Client retries until it reaches leader
- If leader crashes while executing a client request, the client retries (with a new randomly-chosen server) until the request succeeds
- This can result in multiple executions of a command: not consistent!
- Goal: _linearizability_: System behaves as if each operation is executed exactly once, atomically, sometime between sending of the request and receipt of the response.
- Solution:
    - Client generates unique serial number for each request (client id, request number)
    - When retrying, client reuses the original serial number
    - Servers track latest serial number processed for each client, plus associated response (must be stored persistently)
    - When leader detects duplicate, it sends old response without reexecuting request

