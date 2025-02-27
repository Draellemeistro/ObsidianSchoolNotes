**figure out what the best K places are out of N possible locations.**
- Select best location out of $N-K$ for which the **average distance to clients is minimal**. Then choose the necxt best server (**Note:** the first chosen location minimizes the average distance to all clients.) **computationally expensive.**
- Select the $K$-th largest **autonomous system** and place a server at the best-connected host. **computationally expensive.**

### [[Content Replication]]
Distinguish different processes. A process is capable of hosting a replica of an object or data:
- **[[Permanent replicas]]:** Process/machine always having a replica
- **[[Server-initiated replica]]:** Process that can dynamically host a replica on request of another server in the data store.
- **[[Client-initiated replica]]:** Process that can dynamically host a replica on request of a client.

### Dynamic web-content placement
- keep track of access counts per file, aggregated by considering server closest to requesting clients
- Number of accesses drops below threshold $D\to$ **drop file**
- Number of accesses exceeds threshold $R\to$ **replicate file**
- Number of access between $D$ and $R\to$ **migrate file**

![[image_Replica Placement.png]]