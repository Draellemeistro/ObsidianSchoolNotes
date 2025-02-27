[[Consistency Models]]
> [!NOTE] What is it? **ELI5**
> - Ensuring that all replicas reflect the same data state
> - When one replica is updated, changes must propagate to others to maintain uniformity.
> 
> (*Also, check out the sister term, [[Replication]]*) 
# Overview
WE CAN ACTUALLY TALK ABOUT A [[degree of consistency]] also **INCONSISTENCIES CAN BE HANDLED AT DIFFERENT LEVELS**
## Questions and Thoughts
- How do [[Consistency Models]] affect performance in distributed [[Distributed Databases]]?
- What trade-offs exist between strong and [[Eventual Consistency]]?
## Terms
- Strong Consistency [[Consistency Models]]
	- [[Sequential consistency]]
	- [[Causal consistency]]
	- [[grouping operations]] See git vs svn
		- [[Entry consistency]]
	- [[Eventual Consistency]]
also in relation to [[Distributed Databases]]

... [[Consistency Protocols]]
# Notes
## [[Consistency Models]]
### Data-centric [[Consistency Models]]
A Contract between a (distributed) data store and processes, in which the data store specifies precisely what the results of read and write ops are in the precense of concurrency

**Essential:** A data store is a distributed colleciton of storages.
#### Consistent ordering of operations

> [!NOTE] Some notations
> - $W_{i}(x)a$: process P_i writes value a to x
> - $R_{i}(x)b$: Process P_i reads value b from x
> - all data items initially have value **NIL** (nothing, brah)
> ![[image_Consistency.png]]

We omit the index when possible and draw according to time (x-axis)

# [[Sequential consistency]]


# [[Causal consistency]]


##### grouping ops

 