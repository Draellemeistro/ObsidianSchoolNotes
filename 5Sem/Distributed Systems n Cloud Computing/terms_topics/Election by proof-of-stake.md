for [[Leader Election]]
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