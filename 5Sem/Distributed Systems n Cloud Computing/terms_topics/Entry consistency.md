related to [[Consistency]] and [[grouping operations]]
## Definition
- Accesses to locks are [[Sequential consistency|sequentially consistent]] 
- No access to a lock is allowed to be performed until all previous accesses to locks have been performed
**You dont care that reads and writes of a series of ops are immediately known to other processess. You just want the effect of the series itself to be known.**

### A valid event sequence for entry consistency
![[image_Entry consistency.png]]
#### Observation
Entry Consistency implies that we need to lock and unlock data (implicitly or not)

> [!question] **QUESTION**
> What Would be a convenient way of making this consistency more or less transparent to programmers?
