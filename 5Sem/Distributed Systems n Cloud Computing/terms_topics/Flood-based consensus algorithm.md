A talks to neighbors, who in turn talk to their neighbors, eventually flooding the network in order to reach consensus on a common value or state,.
## System Model
- A [[Process-groups|process-group]] $P=\{P_{1},\dots,P_{n}\}$
- **[[Halting Failures|Fail-stop]]** failure semantics, ... with **reliable failure detection** (see [[Failure Terminology]]) 
- A client contacts a $P_{i}$ requesting it to execute a command.
- every $P_{i}$ maintains a list of proposed commands
### Basic algorithm (based on rounds)
1. in **round** $r$, $P_{i}$ multicasts its known set of commands $C_{i}^{r}$ to all others
2. at the end of $r$ each $P_{i}$ merges all received commands itno a new $C_{i}^{r+1}$
3. Next command $\text{cmd}_{i}$ selected through a **globally shared, deterministic function:** $\text{cmd}_{i}← \text{select}(C_{i}^{r+1})$.
# Exercise
Draw the sequance of messages exchanged in the case when the arbitrary node P3 crashes after sending R to P1 (so P2 doesn't receive the message from P3)
#COMEBACK 
# Examples
## No crashes
![[image_Flood-based consensus algorithm.png]]
![[image_Flood-based consensus algorithm-1.png]]

## With crashes
![[image_Flood-based consensus algorithm-2.png]]
![[image_Flood-based consensus algorithm-3.png]]

## With [[arbitrary failure]]
![[image_Flood-based consensus algorithm-4.png]]
![[image_Flood-based consensus algorithm-5.png]]

# Example from book

![[image_Flood-based consensus algorithm-6.png]]
