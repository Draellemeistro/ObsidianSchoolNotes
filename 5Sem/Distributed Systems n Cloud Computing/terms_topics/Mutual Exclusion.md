- [[Centralized Mutex Algorithm]]
- [[Token-based Mutex Algorithm]]
#### Thought provokers
- How does the centralized mutual exclusion algorithm work?
- What is the main idea behind token-based mutual exclusion algorithms?

**Centralized vs Fully Distributed Mutex**
Centralized is simpler but single-point sensitive. Fully distributed increases resilience but is communication-intensive.
# Basic solutions
- **Permission-based:** A process wanting to enter its critical region or access a resource needs permission from other processes
- **Token-based:** A token is passed between processes. The one who has the token may proceed in its region or pass it on when not interested
## Permission based, centralized
[[Centralized Mutex Algorithm]]
![[image_Mutual Exclusion.png]]
- **(A)** Process $P_{1}$ asks the coordinator for permission to access a shared resource. Permission is granted
- **(b)** Process $P_{2}$ then asks permission to access the same resource. The coordinator does not reply.
- **(c)** When $P_{1}$ release the resource, it tells the coordinator, which then replies to $P_{2}$
![[image_Mutual Exclusion-1.png]]

## Token ring algorithm
[[Token-based Mutex Algorithm]]
**Essence:** Organize processes in a logical ring, and let a token be passed between them. The one that holds the token is allowed to etner the critical region (if it wants to)
