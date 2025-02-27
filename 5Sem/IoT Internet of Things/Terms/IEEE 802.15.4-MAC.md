## [[Media Access Control (MAC)]]
> [!NOTE] [[Media Access Control (MAC)]]
> **Combination of [[Random-Access Protocols|Random-Access]] (contention-based access) and contention-free access**
- Link time is divided into slots
	- Some of the slots are reserved
		- **[[TDMA]]**: contention free
	- The devices contend for the rest of the slots
		- **Slotted** [[CSMA-CA]]

### [[IEEE 802.15.4]] foresees that the [[Personal Area Networks|PAN]] is organized in clusters
- A cluster is formed around **coordinator**
- Two types of coordinators:
	- [[Personal Area Networks|PAN]] Coordinator (**always exists**)
	- Cluster coordinator (exists in [[Personal Area Networks|PANs]] with more than one cluster)
	  
	  ![[image_IEEE 802.15.4-MAC.png]]
#### There can be two types of devices in a [[Personal Area Networks|PAN]]:
###### **FFD** - [[Full Function Device (FFD)]]
- Acts as the [[Personal Area Networks|PAN]] coordinator, cluster coordinator or as an ordinary network node
###### **RFD** - [[Reduced Function Device (RFD)]]
- Just a network node, can **NOT** route data

### [[Network Topologies]]
**There can be two types of topologies in [[IEEE 802.15.4]]:**
- [[Star Topology]]
	- [[Full Function Device (FFD)|FFD]] can communicate with [[Full Function Device (FFD)|FFD]] and [[Reduced Function Device (RFD)|RFD]]
	- [[Reduced Function Device (RFD)|RDF]] can communicate only with [[Full Function Device (FFD)|FFD]]
- [[Peer-to-Peer Topology]]
	- [[Reduced Function Device (RFD)|RFD]] Can communicate with other [[Reduced Function Device (RFD)|RFDs]] (if they are in reach of each other)
	- Coordinator still has to exist ([[Full Function Device (FFD)|FFD]]s can only be this)
![[image_IEEE 802.15.4-MAC-1.png]]
#### [[Star Topology]]
- In this topology, so-called <span style="font-weight:bold; color:rgb(255, 0, 0)">beacon enabled</span> mode of operation is used
- Link time is divided in periods called beacon intervals
	- A beacon interval is divided into active and inactive period
	- communication is performed during the **active period**.
	- an **Active period** is divided into:
		- [[Contention-Access Period (CAP)]] - contention-based, exists always
		- [[Contention Free Period (CFP)]] - optional
- During **inactive period**, the nodes in the cluster sleep / data can be exchanged among the clusters (Through **Coordinators**)
> [!NOTE] Coordinator is in charge of (coordinates) cluster operation in [[Star Topology]]:
> - Synchronizes nodes in the cluster
> - assigns slots in [[Contention Free Period (CFP)]] to nodes
> - Transmits beacon packet at the beginning of the **active period**, notifying the nodes about the duration of the beacon interval and of the active period, slot assignments, ......

> [!quote] <span style="color:rgb(255, 0, 0)">All packet exchanges in star topology involve coordinator</span>
> - **Downlink:** [[Full Function Device (FFD)|FFD]] (coordinator) $\to$ [[Reduced Function Device (RFD)|RFD]] (node)
> - **Uplink:** [[Full Function Device (FFD)|FFD]] (coordinator) $\gets$ [[Reduced Function Device (RFD)|RFD]] (node)
##### [[Slotted CSMA-CA|Slotted CSMA/CA]]   [[Contention-Access Period (CAP)|CAP]] **more info there**
##### [[Contention Free Period (CFP)]] - [[Guaranteed Transmission Slots (GTS)]]
- [[Contention Free Period (CFP)|CFP]] used for higher-priority data traffic
- If a node requires a more reliable (i.e., contention free) service, it may request af [[Guaranteed Transmission Slots (GTS)|GTS]] in [[Contention Free Period (CFP)|CFP]]
	- If the request is granted, the node gets a slot in the next beacon interval, which is advertised in the beacon.
	- The request is sent in [[Contention-Access Period (CAP)|CAP]]
	- A node may get a [[Guaranteed Transmission Slots (GTS)|GTS]] and still contend in [[Contention Free Period (CFP)|CFP]]
- When granting [[Guaranteed Transmission Slots (GTS)|GTSs]], the coordinator has to insure that [[Contention-Access Period (CAP)|CAP]] last at least 440 symbol periods
	- In other words, not all slots in a **superframe** can be allocated as [[Guaranteed Transmission Slots (GTS)|GTSs]]
- The allocation of a [[Guaranteed Transmission Slots (GTS)|GTS]] is repeated in 5 successive SFs #huhhh 
- [[Guaranteed Transmission Slots (GTS)|GTS]] can be used both for uplink and downlink
	- a node can request **two** [[Guaranteed Transmission Slots (GTS)|GTSs]] in this case (which is also the maximum what a node can request)
- The coordinator can deallocate a [[Guaranteed Transmission Slots (GTS)|GTS]:
	- When needed
	- if it is not used
#### [[Peer-to-Peer Topology]]
- non-beacon enabled mode of operation
	- $BO = SO = 15$
- the coordinator transmits a beacon only when requested
	- used to resynchronize the nodes
- There is no SF, [[Contention-Access Period (CAP)|CAP]], [[Contention Free Period (CFP)|CFP]]
- The nodes communicate directly with each other
- [[Media Access Control (MAC)]] is via [[Unslotted CSMA-CA]]
![[image_IEEE 802.15.4-MAC-2.png]]
###### [[Peer-to-Peer Topology]] Uplink & downlink
![[image_IEEE 802.15.4-MAC-3.png]]
