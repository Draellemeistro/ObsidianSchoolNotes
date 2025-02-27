

> [!NOTE] **ELI5:** [[CAP Theorem]]
> **In distributed systems, choose 2 out of 3:**
> - **[[Consistency]]:** Every read returns data from most recent write.
> - **Availability:** Every request executes & receives a (non-error) response
> - **Partition-tolerance:** System continues to function when network partitions occur (messages dropped or delayed)

Distributed systems can't avoid the dangers of network failures. Venn diagrams, but they dont all overlap. You can choose 2, so: **CA**, **CP**, or **AP**

> [!NOTE] **CAP** (choose **2** drop **1**)
> - **C**onsistency: *every read receives the most recent write or an error. Note that [[Consistency]] as defined in the [[CAP Theorem]] is quite diffrent from the consistenc guaranteed in [[ACID database]] transactions.*
> - **A**vailability: *every reqyest received by a non-failing node in the system must result in response. different from high availability in SW architecture*
> - **P**artition tolerance: *System continues to operate despite an arbitrary number of messages being dropped or delayed by the network between nodes.*