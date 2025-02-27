
> [!NOTE] **ELI5:** What is [[Consensus]]?
> Consensus is a fundamental problem in fault-tolerant distributed systems. Consensus involves multiple servers agreeing on values. **Once they reach a decision on a value, that decision is final.** Typical consensus algorithms make progress when any majority of their servers is available; 
> 
> **for example,** a cluster of 5 servers can continue to operate even if 2 servers fail. If more servers fail, they stop making progress (but will never return an incorrect result). 
> 
> **(See also: [[Fault Tolerance]],  )**



# Consensus in faulty systems with crash failures
**Prerequisite:** In a [[Fault Tolerance|Fault Tolerant]] [[Process-groups|process-group]], each nonfaulty [[Process]] executes the same commands, and in the same order, as every other nonfaulty process.
### Reformulation
**nonfaulty group members need to reach [[Consensus|CONSENSUS]] on which command to execute next** 
## [[Flood-based consensus algorithm]]
A talks to neighbors, who in turn talk to their neighbors, eventually flooding the network in order to reach consensus on a common value or state,.

## [[Consensus]] under [[arbitrary failure]]
**essence:** we consider process groups in which communication between process is **inconsistent.** 
![[image_Consensus.png]]
#### **Observation:** 
This is a different behaviour from what we saw before. In the previous examples, the arbitrary node was simply voting differntly than the others, it was not behaving **_"maliciously"_** 
### System model
- we consider a **primary** $P$ and $n-1$ **backups:** $B_{1},\dots,B_{n-1}$
- A client sends $v\in \{T,F\}$ to $P$ 
- messages may be **lost**, but this can be detected
- messages **cannot be corrupted** beyond detection
- A receiver of a message can **reliably detect its sender.**
#### **Byzantine agreement:** requirements
- **BA1:** Every nonfaulty backup process stores the same value.
- **BA2:** If the primary is nonfaulty then every nonfaulty backup process stores exactly what the primary had sent
#### Observation
- **Primary faulty** $\to$ BA1 says that backups may store the same, but different (and thus wrong) value than originally sent by the client.
- **Primary not faulty** $\to$ satisfying BA2 implies that BA1 is satisfied.


# **Related topics**
## From [[Cloud 10 Fault Tolerance|lecture 10]]

