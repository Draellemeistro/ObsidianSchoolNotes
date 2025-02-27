**What are the advantages of decentralized leader election algorithms?**
- [[Bully Algorithm]]
- [[Ring Algorithm]]
see also [[Raft Consensus Algorithm]], where leader election................. 

## [[Elections by proof of work]]
### Basics (_think [[Blockchain Architecture|Blockchain]]_)
- Consider a potentially large group of processes
- Each process is required to solve a computational puzzle 
- When a process solves the puzzle, it broadcasts its victory to the group
- We assume there is a conflict resolution procedure when more than one process claims victory
### Solving a computational puzzle
![[image_Leader Election.png]]
##### Controlled race
![[image_Leader Election-1.png]]
#### Observation
![[image_Leader Election-2.png]]
## [[Election by proof-of-stake]]
### Basics
We assume a [[Blockchain Architecture|blockchain]] system in which $N$ **secure tokens** are used:
- each token has a unique **owner**
- each token has a uniquely associated **index** $1\leq k\leq N$
- A token cannot be modified or copied without this going unnoticed.
#### Principle
- Draw a random number $k \in \{1,\dots ,N\}$ 
- Look up the process $P$ that owns the token with index $k$. $P$ is the next leader.
### Observation
The more tokens a process owns, the higher probability it will be selected as leader.