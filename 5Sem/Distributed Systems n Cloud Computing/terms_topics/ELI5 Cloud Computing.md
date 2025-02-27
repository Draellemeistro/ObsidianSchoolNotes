


> [!NOTE] **Cloud Economics** For users
> **Pay-as-you-go** (usage-based) pricing:
> - Most services charge per minute, per byte, etc.
> - No minimum or up-front fee
> - helpful when apps have variable utilization
> 
> **Elasticity:**
> - Using 1000 servers for 1 hours costs the same as 1 server for 1000 hours.
> 	- **Same price to get a result faster**


> [!NOTE] **Cloud Economics** For Providers
> **Economies of scale:**
> - Purchasing, powering and managing machines at scale gives lower per-unit costs than customers'
> - to find tradeoff: fast growth vs efficiency
> - to find tradeoff: Flexibility vs cost
> 
> **Speed of iteration:**
> - SaaS means fast time-to-market, updates and detailed monitoring / feedback
> - compared to speed of iteration with ordinary software distribution

## Other interesting features
- Spot market for preemptible machines, the ability to purchase a productive old server
- Wide geographic access for disaster recovery and speed of access
- Ability to quickly try exotic hardware
- Ability to A/B test anything

# Compute Approaches
![[image_ELI5 Cloud Computing.png]]
See [[Virtualization]]

# Availability

| Technique                                                    | Performance | Availability |
| ------------------------------------------------------------ | ----------- | ------------ |
| [[Replication]]                                              | X           | X            |
| Partitioning (db tables sharding)                            | X           | X            |
| [[Load balancing]]                                               | X           |              |
| Watchdog timers (hang prevention)                            |             | X            |
| Integrity checks (checksum etc)                              |             | X            |
| Canaries (canary release)                                    |             | X            |
| [[Consistency Models\|Eventual consistency]] [[Consistency]] | X           | X            |
|                                                              |             |              |
## [[CAP Theorem]]