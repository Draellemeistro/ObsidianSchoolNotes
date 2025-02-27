## See also [[Channel Access in IWSN Standards]]
## [[ZigBee]]
#### [[Network Topologies]]
Zigbee supports star, tree, and mesh topologies
- [[Star Topology]]: is efficient for low delay and small networks
- [[Tree Topology]]: (see example figure) is preferred in large scale networks
- [[Mesh Topology]]: Provides more reliable communication (**Redundant paths**)
![[image_ZigBee.png]]
#### Devices
Devices in Zigbee network are categorized into three types:
- **Coordinator:** control and maintain the Zigbee network
- **Router:** routing message from childes to parents
- **End devices:** collecting data, cannot route messages

## [[WirelessHART]]
#### [[Network Topologies]]
Supports [[Star Topology|star]] and [[Mesh Topology|mesh]] topologies 
![[image_IoT-network architectures.png]]
#### Devices
Devices in [[WirelessHART]] network are categorized into three types:
- **Network Manager:** responsible for configuring the network, scheduling and managing communications among devices
- **Access points:** connect field devices to the gateway
- **Field devices:** collecting data with routing capabilities

## [[ISA100.11a]]
#### [[Network Topologies]]
Supports [[Star Topology|star]] and [[Mesh Topology|mesh]] topologies 
![[image_IoT-network architectures-1.png]]
#### Devices
Devices in [[ISA100.11a]] network are categorized into two types:
- **Field devices**
	- Routers
	- I/O devices
	- Handheld devices
- **Infrastructure devices**
	- Backbone routers (high speed)
	- Gateway


## [[WIA-PA]]
#### [[Network Topologies]]
[[WIA-PA]] supports a hierarchical network topology that is basically [[Star Topology|star]] **PLUS** [[Mesh Topology|mesh]].
![[image_IoT-network architectures-2.png]]
#### Devices
Devices in [[WIA-PA]] network are categorized into four types:
- **Field/handheld devices (cluster members):** collecting data
- **Routers (cluster head):** managing the star network
- **Redundant cluster head**
- **Gateway**