- Communication between processes in a distributed system can have unpredictable delays, processes can fail, messages can be lost.
- Synchronization in distributed systems is harder than in centralized systems because the need for distributed algorithms

## Why do we need to [[Clock Synchronization|Synchronize Clocks]]?
- When each individual machine has its own clock, an event that occurred after another event may nevertheless be assigned an earlier time.
	- For example, imagine an “IoT dashboard” with data from unsynchronized sensors
- **This can be critical like power grids, industrial control processes**
## Challenges in distributed synchronization
- Different types of watches
- Different hardware
- Different software
- Different temp
- ...... **LOTS OF FACTORS AFFECT THIS SHIT**
All these generate:
**Clock skew:** Disagreement in the reading of two clocks
**Clock drift:** Difference in the rate which two clocks count the time.
![[image_Distributed-Synchronization.png]]

### [[Happened before principle]]
> [!NOTE] **a -> b**
> - "a happens first, afterwards b happens"
> - "a happens before b"
> - "a might cause b"

- If a and b are events in the same process, and a occurs before b, then a->b is true.
- If a is te event of a message being sent by one process, and b is the event of a message received by another process, then a->b is also true
- **if a->b and b->c, then a->c _(transitive)_**
- If a does not happen before b and b does not happen before a, then a and b are _"concurrent"_ $( a\vert\vert b)$
![[image_Consistency Models.png]]
