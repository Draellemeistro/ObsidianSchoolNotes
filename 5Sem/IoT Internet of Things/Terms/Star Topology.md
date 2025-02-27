is efficient for low delay and small networks

![[image_Star Topology.png]]

## Used by
- [[IEEE 802.15.4-MAC]] (or just [[IEEE 802.15.4]] in general???)




## In regards to [[IEEE 802.15.4-MAC]]
In this topology, so-called <span style="font-weight:bold; color:rgb(255, 0, 0)">beacon enabled</span> mode of operation is used
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
