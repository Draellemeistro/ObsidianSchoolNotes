### Key Concepts of Replicated-Write Protocols

1. **Replication:**
    - Data is duplicated across multiple nodes to provide fault tolerance, improve availability, and enhance performance.
2. **Consistency:**
    - Ensures that all replicas reflect the same state after a write operation is completed.
3. **Concurrency Control:**
    - Manages simultaneous write operations to prevent conflicts and inconsistencies.
4. **Fault Tolerance:**
    - The system continues to operate even if some replicas fail, as long as a majority or quorum of replicas are functional.
### Types of Replicated-Write Protocols

1. **Active Replication (Write-All Protocols):**
    - Every write operation is sent to all replicas simultaneously.
    - Each replica processes the write request independently, applying the same operation in the same order.
    **Advantages:**
    - Strong consistency is maintained across replicas.
    - Fault tolerance is high as every replica has an up-to-date copy of the data.
    **Challenges:**
    - High communication overhead due to broadcasting to all replicas.
    - Requires mechanisms to ensure operations are applied in the same order (e.g., consensus protocols like Paxos or Raft).
1. - .g., consensus protocols like Paxos or Raft).

---
2. **Primary-Backup Protocols (Primary-Replica Protocols):**
    - A designated **primary node** processes all write requests and propagates the updates to **backup replicas**.
    - Backup replicas only accept updates from the primary node.
    **Advantages:**
    - Simplifies coordination, as the primary ensures order and consistency.
    - Reduced overhead compared to active replication.
    **Challenges:**
    - Single point of failure if the primary node goes down (mitigated using leader election mechanisms).
    - Latency increases as writes depend on the primary node's responsiveness.
---
3. **Consensus-Based Protocols:**
    - Protocols like **Paxos** or **Raft** ensure agreement among replicas before committing a write.
    - Each write operation goes through a consensus process to determine whether it should be applied.
    **Advantages:**
    - Ensures strong consistency and fault tolerance.
    - Suitable for distributed databases and systems requiring high reliability.
    **Challenges:**
    - High latency due to the need for consensus.
    - Complex implementation and operational overhead.

