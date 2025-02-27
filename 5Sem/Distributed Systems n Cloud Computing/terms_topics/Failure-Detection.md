## Issue
> [!warning] How can we **reliably detect** that a process has **actually crashed**?
### General Model
- Each process is equipped with a failure detection module
- a process $P$ **probes** another process $Q$ for a reaction
- if $Q$ reacts: $Q$ is considered to be alive (by $P$)
- if $Q$ does not react with $t$ time units: $Q$ is **suspected** to have crashed

> [!tip] For a synchronous system, a suspected crash $\equiv$  a known crash (equivalent)

# Practical failure detection
### Implementation
- if $P$ did not receive **heartbeat** from $Q$ within time $t$: $P$ **suspects** $Q$
- if $Q$ later sends a message (which is received by $P$):
	- $P$ stops suspecting $Q$
	- $P$ increases the timeout value $t$
- **NOTE:** if $Q$ did crash, $P$ will keep suspecting $Q$

## Distributed Commit Protocols
##### Problem
Have an operation being performed by each member of a process group, or none at all.
- **Reliable Mutlicasting:** a message is to be delivered to all recipients.
- **Distributed transaction:** each local transaction must succeed.
### One phase commit (1PC)
> [!NOTE] One phase commit (1PC)
> Coordinator sends transaction to participants.
> 
> ![[image_Failure-Detection.png]]
> 
> **DRAWBACK:**
> without _ACK_: not sure whether transaction was performed.
> with _ACK_: what if _ACKs_ get lost? Not sure if transaction successful. 

### [[two-phase commit protocol]] (2PC)
> [!NOTE] [[two-phase commit protocol]] (2PC)
> In a two-phase commit protocol, a coordinator first checks whether all processes agree to perform the same operation (i.e., whether they all agree to commit), and in a second round, multicasts the outcome of that poll.


