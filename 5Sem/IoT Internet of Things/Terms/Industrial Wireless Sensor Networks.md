> [!NOTE] IWSN is a distributed systems of interconnected sensors and actuators
- **Main components:** 
	- sensors
	- actuators
	- sink (gateway, network manager, ….)


### Why?
**Adopting of wireless technology offer competitive advantages over wired solutions**
- Flexibility and cost (reducing cost of cables)
- Easier maintenance
- Mobility (rotating equipment)
- Positioning - advanced use-cases
### [[ISA traffic classes]]
> [!warning] **IMPORTANT:** Different traffic exist in [[Industrial Wireless Sensor Networks|IWSNs]]

| CATEGORY       | CLASS | APPLICATION                                        | LATENCY     | CRITICAL LEVEL       |
| -------------- | ----- | -------------------------------------------------- | ----------- | -------------------- |
| **safety**     | 0     | -  Emergency shutdowm<br>-  Automatic fire control | 10-250 _ms_ | Always Critical      |
| **control**    | 1     | Closed loop regularity                             | 10-500 _ms_ | often critical       |
| **control**    | 2     | Closed loop supervisory                            | 10-500 _ms_ | usually non-critical |
| **control**    | 3     | Open loop control                                  | 10-500 _ms_ | non-critical         |
| **monitoring** | 4     | Alerting                                           | sec-days    | non-critical         |
| **monitoring** | 5     | Logging and downloading / uploading                | sec-days    | non-critical         |
## [[IWSNs Standards]]
- IoT protocols typically focus on optimizing data rate, range and battery life
- Different requirements for IIoT protocols, **different standards/technology**
- Several industrial standards have been developed for IIoT
# WSN [[Network Topologies|Topologies]] 
![[image_Industrial Wireless Sensor Networks.png]]
![[image_Network Topologies.png]]
- [[Tree Topology]]
- [[Star Topology]]
- [[Mesh Topology]]


