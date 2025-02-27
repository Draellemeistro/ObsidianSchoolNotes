### [[Network Topologies]]
**There can be two types of topologies in [[IEEE 802.15.4]]:**
- [[Star Topology]]
	- [[Full Function Device (FFD)|FFD]] can communicate with [[Full Function Device (FFD)|FFD]] and [[Reduced Function Device (RFD)|RFD]]
	- [[Reduced Function Device (RFD)|RDF]] can communicate only with [[Full Function Device (FFD)|FFD]]
- [[Peer-to-Peer Topology]]
	- [[Reduced Function Device (RFD)|RFD]] Can communicate with other [[Reduced Function Device (RFD)|RFDs]] (if they are in reach of each other)
	- Coordinator still has to exist ([[Full Function Device (FFD)|FFD]]s can only be this)
![[image_IEEE 802.15.4-MAC-1.png]]

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
