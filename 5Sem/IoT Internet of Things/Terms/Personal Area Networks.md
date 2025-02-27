# Module 4: [[Personal Area Networks]] – [[IEEE 802.15.4]]




### [[IEEE 802.15.4]] foresees that the [[Personal Area Networks|PAN]] is organized in clusters
- A cluster is formed around **coordinator**
- Two types of coordinators:
	- [[Personal Area Networks|PAN]] Coordinator (**always exists**)
	- Cluster coordinator (exists in [[Personal Area Networks|PANs]] with more than one cluster)
	  
	  ![[image_IEEE 802.15.4-MAC.png]]
#### There can be two types of devices in a [[Personal Area Networks|PAN]]:
- **FFD** - [[Full Function Device (FFD)]]
	- Acts as the [[Personal Area Networks|PAN]] coordinator, cluster coordinator or as an ordinary network node
- **RFD** - [[Reduced Function Device (RFD)]]
	- Just a network node, can **NOT** route data
## Cluster association / formation
A node that wants to join a cluster, or make its own cluster (as the _coordinator_) first has to perform scanning:
###### Active scanning
- A node selects a channel and sends a beacon request, waiting for the beacon
- Mandatory function for [[Full Function Device (FFD)|FFDs]], optional for [[Reduced Function Device (RFD)|RFDs]]
###### Passive scanning
- A node selects a channel and listens for the beacon
- Mandatory function for both [[Full Function Device (FFD)|FFDs]] and [[Reduced Function Device (RFD)|RFDs]] 
###### Energy Detection
- A node sweeps the available channels and performs energy detection, in order to determine the occupancy of the channel. Active and passive scanning are performed based on the output of the energy detection
- Mandatory function for [[Full Function Device (FFD)|FFDs]], optional for [[Reduced Function Device (RFD)|RFDs]]
###### Cluster formation
- if a channel is determined to be free, the node ([[Full Function Device (FFD)|FFD]]) that wants to form the cluster starts transmitting beacons
###### Cluster association
- the node sends the association request to the coordinator
	- sent in [[Contention-Access Period (CAP)|CAP]]
- The coordinator makes decision based on the number of the nodes in the cluster and their activity patterns
- the decision is sent in the standard way for downlink transmissions
	- The coordinator makes an announcement of the pending downlink transmission in the beacon $\to$ data request sent by node
## Multicluster [[Personal Area Networks|PANs]]
- [[IEEE 802.15.4]]-2003 allows only a single cluster per [[Personal Area Networks|PAN]]
- The standard from 2006 allows for having several clusters in a [[Personal Area Networks|PAN]]
- A node in a cluster can decide / be instructed from the coordinator to make a new cluster
	- Cluster forming stats
	- Beacons in the new cluster are shifted in time wrt the beacons in the original cluster
		- they are placed in the inactive period of the original cluster
	- The procedure can be repeated
- All the clusters in a [[Personal Area Networks|PAN]] use the same channel
- **multicluster [[Personal Area Networks|PAN]] = multihop network (routing has to be used)**
![[image_IEEE 802.15.4-3.png]]