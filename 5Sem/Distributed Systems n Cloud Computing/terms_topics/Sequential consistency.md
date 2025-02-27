> [!NOTE] See also **[[Consistency]]** and [[Causal consistency]]

## Definition
The result of any execution is the same as if the ops of all processes were executed in some sequential order, and the ops of each indiviudal process appear in this sequence on the order specified by its program.
**when processes run concurrently on (_possibly_) different machines, any valid interleaving of read and write ops is acceptable behavior, BUT ALL PROCESSES SEE THE SAME INTERLEAVING OF OPERATIONS**
![[image_Sequential consistency.png]]

p1 writes a to x, p2 then writes b to x, then p3 reads b from x, then p4 reads a from x...
**it doens't add up, because of how P3 and P4 muddy the sequence** 

## [[Primary-based protocols]]
#### [[remote-write protocols]]
Each data item $x$ in the data store has an associated primary, which is responsible for coordinating write ops on $x$.
A distinction can be made whether the primary is fixed at a remote server or if write ops can be carried out locally after moving the primary to the process where the write op is initiated.

###### **Example:** primary-backup protocol
Traditionally applied in distributed databases and file systems that require a high degree of [[Fault Tolerance]]. Replicas are often placed on the same LAN
![[image_Sequential consistency 1.png]]
###### **Example:** primary-backup protocol with local writes
Mobile computing in disconeected mode (ship all revelant files to user before disconnectiong, and update later on)
![[image_Sequential consistency-1.png]]
