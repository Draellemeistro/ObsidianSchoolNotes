### [[remote-write protocols]]
Each data item $x$ in the data store has an associated primary, which is responsible for coordinating write ops on $x$.
A distinction can be made whether the primary is fixed at a remote server or if write ops can be carried out locally after moving the primary to the process where the write op is initiated.

###### **Example:** primary-backup protocol
Traditionally applied in distributed databases and file systems that require a high degree of [[Fault Tolerance]]. Replicas are often placed on the same LAN
![[image_Sequential consistency 1.png]]
###### **Example:** primary-backup protocol with local writes
Mobile computing in disconeected mode (ship all revelant files to user before disconnectiong, and update later on)
![[image_Sequential consistency-1.png]]
