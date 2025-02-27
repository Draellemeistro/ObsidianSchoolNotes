## Why do we need to [[Clock Synchronization|Synchronize Clocks]]?
- When each individual machine has its own clock, an event that occurred after another event may nevertheless be assigned an earlier time.
	- For example, imagine an “IoT dashboard” with data from unsynchronized sensors
- **This can be critical like power grids, industrial control processes**
### Challenges in [[Distributed-Synchronization]]
**there can be:** Different types of watches, Different hardware, Different software, Different temp ....
**All these generate:**
- **Clock skew:** Disagreement in the reading of two clocks
- **Clock drift:** Difference in the rate which two clocks count the time.
## Types of Clocks
- [[Physical Clocks]]
- [[Logical Clocks]] ([[Lamports Logical Clocks]])
- [[Vector Clocks]]
# Clock Sync Algorithms
Clocks synced by exchanging time values, accounting for message delay. Comm delay handling impacts sync accuracy.
- All devices get the time from GPs satellites 
- Some devices might not have a GPS receiver, they get the time from broadcasting stations 
- Some devices might also not be able to communicate with broadcasting stations 
- None of these devices can communicate with GPS satellites or broadcasting stations

### Requirements
- “Causlity”: real:time order timestamp order 
- Groups /replicates see the events in the same order 
- “Multiple- copy-updates” order of updates, consistency conflicts?
- Serializability of transactions: bases on aq common understanding of transaction order
### [[Happened before principle]]


- [[Cristians Algorithm]]
- [[Berkeley Algorithm]]
- [[Network Time Protocol (NTP)]] 
	- Multicast, Procedure-call, Symmetric

# Types of clocks
Physical Clocks, 
[[Logical Clocks]] ( [[Lamports Logical Clocks]], [[Vector Clocks]] )
