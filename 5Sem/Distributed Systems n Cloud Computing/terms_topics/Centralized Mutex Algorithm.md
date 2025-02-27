A process wanting to enter its critical region or access a resource needs permission from other processes
## Permission based, centralized
![[image_Mutual Exclusion.png]]
- **(A)** Process $P_{1}$ asks the coordinator for permission to access a shared resource. Permission is granted
- **(b)** Process $P_{2}$ then asks permission to access the same resource. The coordinator does not reply.
- **(c)** When $P_{1}$ release the resource, it tells the coordinator, which then replies to $P_{2}$
![[image_Mutual Exclusion-1.png]]