# IoT traffic Characteristics
### IoT packets
##### The ratio of control information and data in human-oriented communications:
![[image_IoT traffic.png]]
##### For short packets typically used in IoT:
![[image_IoT traffic-1.png]]
### Almost 50/50 ratio (**actually, could be much worse**):
- Do we need to reconsider the fundamental ways of communication?

## IoT [[traffic generation patterns]]
- Depend on the application
- IoT traffic is predominantly uplink oriented
	- Sending of sensor readings
	- Downlink is mainly used for signaling and network-control functions
		- may also carry data in scenarios with actuation
	- ![[image_IoT traffic-3.png]]
- It is standardly assumed that reporting is push-based [[Push-based reporting]]
	- i.e., the devices themselves initiate reporting
- However, it may also happen that the devices are queried for the readings
	- Pull-based (on-demand) reporting [[Pull-based reporting]]
##### General classes:
1. [[Full-buffer reporting]]
	1. Devices always have something to send
		1. **Happens rarely in IoT (video surveillance)**
2. [[Intermittent reporting]]
	1. **Typical for IoT**
	2. Different types
		1. [[Real-time control]] ([[Industrial IoT]])
		2. [[Periodic Monitoring]]
		3. [[Event Detection]]

### [[IoT traffic generation models]]
- **there are two basic models:**
	- Asynchronous and synchronous reporting (arrivals)
![[image_IoT traffic 1.png]]
##### [[Asynchronous Arrivals]]
- Aka **uncorrelated traffic generations** 
- Models periodic reporting
- no synchronism between the reporting devices
- aggregated over devices shows stable (stationary behavior)
	- **Makes it easier to dimension the network**
- Deterministic periodic arrivals
	- [[Real-time control]]
- Uniform, Bernoulli, Poisson arrivals

##### [[Synchronous Arrivals]]
- Users’ traffic arrivals are independent of each other and independent of their previous traffic arrivals

ONN to [[Multiple access techniques]]
