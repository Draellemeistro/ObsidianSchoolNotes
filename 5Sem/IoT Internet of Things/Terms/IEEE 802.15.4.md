> [!NOTE] [[IEEE 802.15.4]] defines physical layer and MAC sublayer for low-rate wireless [[Personal Area Networks]] (**LR-WPANs**)
> Basis for [[ZigBee]], [[6LoWPAN]], [[WirelessHART]], and [[MiWi]] standards, **which define higher layers of the protocol stack**
> 
> ![[image_IEEE 802.15.4 1.png]]

> [!NOTE] Frequency bands it operates
> - WOrldwide 2.4 gHZ
> - EU 868 mHZ
> - NA 915 mHZ

![[image_IEEE 802.15.4-1.png]]

![[image_IEEE 802.15.4.png]]
# [[IEEE 802.15.4-PHY]]

#### Defines / Realizes:
- [[Frequency bands]]
- [[Signal bandwidth]]
- Modulation
- Data rate
- Channel coding mechanism
- Error detection mechanism
- Frequency, phase and symbol synchronization
- Physical procedures related to [[multiple-access protocols]]/**protocols** ( [[Clear Channel Assessment (CCA)]])
### More general
- Half-duplex mode of communication
- Turnaround time from reception to transmission mode (and vice versa) may last up to 12 symbol periods maximum (denoted as _aTurnaroundTime_ in the standard)
- Transmission power CAN be adjusted
	- e.g., based on Link Quality Indicator (LQI) that is being monitored
- ##### [[Clear Channel Assessment (CCA)]] - Listening before talking
- ##### [[IEEE 802.15.4]] Frequency bands
	- Transmissions in [[IEEE 802.15.4]] are performed in [[ISM bands]] (Industrial, Scientific, Medical) bands
		- Open to use (limitations in terms of radiated power)
		- A lot of devices are using [[ISM bands]]
			- i.e., **a lot of interference**
			  
	- ###### <span style="font-weight:bold; color:rgb(255, 10, 222)">IEEE 802.15.4 (original standards) uses bands in:</span>
		- 868/915 MHz
		- 2.4 GHz
> [!NOTE] **In general:** lower frequency $\to$ larger distances + lower data-rates
# [[IEEE 802.15.4-MAC]]
## [[Media Access Control (MAC)]]
> [!NOTE] [[Media Access Control (MAC)]]
> **Combination of [[Random-Access Protocols|Random-Access]] (contention-based access) and contention-free access** see also [[MAC packet]]
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
#### There can be two types of devices in a [[Personal Area Networks|PAN]]: [[IEEE 802.15.4-Devices]]
- **FFD** - [[Full Function Device (FFD)]]
	- Acts as the [[Personal Area Networks|PAN]] coordinator, cluster coordinator or as an ordinary network node
- **RFD** - [[Reduced Function Device (RFD)]]
	- Just a network node, can **NOT** route data

# [[Personal Area Networks|PAN]] information
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
### Multicluster [[Personal Area Networks|PANs]]
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
# Different Versions / Iterations
- ### [[IEEE 802.15.4]]-2003 
	- the original standard 
- ### IEEE 802.15.4-2006 
	- increased data rates to 100 and 250 kbps in 868/915 MHz bands 
- ### IEEE 802.15.4c-2009 
	- incorporation of 314-316MHz, 430-434 MHz and 779-787 MHz bands (China) 
- ### IEEE 802.15.4d-2009 
	- incorporation of 3950-3956 MHz bands (Japan) 
- ### IEEE 802.15.4a-2007
	- [[Ultra Wide Band (UWB)]] 
- ### IEEE 802.15.4e-2012 
	- high-reliability industrial applications (time hopping)
- ###  …. 
- ### IEEE 802.15.4-2020
