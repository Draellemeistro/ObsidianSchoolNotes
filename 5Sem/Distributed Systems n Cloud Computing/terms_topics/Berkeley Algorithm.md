for [[Clock Synchronization]]
- The nodes elect a master 
- The master polls all nodes to give their times by the clock
- The master estimates the local times of all nodes regarding the involved message transfer time
- The master uses the estimated local times for building the arithmetic mean 
- The deviations from the mean are sent to the nodes so they can adjust their clock.

- **Suitable for distributed systems** 
	- If elected master crashes a new master can be appointed by  a [[Leader Election|master election]] algorithm