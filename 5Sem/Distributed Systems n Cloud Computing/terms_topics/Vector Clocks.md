for [[Clock Synchronization]]
> [!NOTE] The problem with [[Lamports Logical Clocks]] is that they dont capture causality. [[Vector Clocks]] do!
> **Goal:** reflect causality, e.g., 
> if $C(a) <C(b)$ then $a\to b$

Vector clocks are constructed by letting each process Pi maintain a vector $VC_{i}$ with the following **two properties**:
1. $VC_{i}[i]$ is the number of events that have occured so far at $P_{i}$ (ie its the local logical clock at process P_i)
2. if $VC_{i}[j]=k$ then Pi knows that k events have occurred at Pj (it is thus Pi's knowledge of the local time at Pj)

![[image_Vector Clocks 1.png]]
> [!NOTE] **Vector Clocks:** example
> ![[image_Vector Clocks.png]]


[[Lamports Logical Clocks]] and this leads into talks of [[Replication]] and [[Consistency]] ([[Mutual Exclusion]] also seems relevant)

