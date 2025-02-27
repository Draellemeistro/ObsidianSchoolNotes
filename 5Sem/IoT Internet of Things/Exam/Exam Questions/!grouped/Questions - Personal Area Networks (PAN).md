[[Questions - MQTT]] -- [[Questions - Short Range Solutions]]
## **(1)** Which layers of the protocol stack are covered by the [[IEEE 802.15.4]] standard? 
**[[IEEE 802.15.4-PHY|PHY]]sical** and **[[IEEE 802.15.4-MAC|MAC]]** (datalink)
- **defines physical layer and MAC sublayer for low-rate wireless**
- ![[image_IEEE 802.15.4 1.png]]

### In which bands does this standard operate?
[[Frequency bands]] [[ISM bands]]
- <span style="font-weight:bold; color:rgb(255, 20, 0)">Depends on region</span>
- **worldwide:** 2.4 gHZ (_you've seen this number plenty_)
- **US:** 915 MHz (Up to 10 channels (channels 1–10).)
- **EU** 868 MHz (1 channel (channel 0).)
	- ![[image_Frequency bands-1.png]]
	- The IEEE 802.15.4 standard provides flexibility in frequency band selection, enabling diverse IoT applications. The **868/915 MHz bands** are ideal for long-range, low-power, and interference-resilient applications, while the **2.4 GHz band** excels in scenarios requiring global compatibility and higher data rates. The choice of band depends on the specific use case, regional regulations, and environmental conditions.
### What types of devices does the standard foresee and what are the roles? [[Personal Area Networks|PANs and shit? eller phones]] 
In regards to the [[Personal Area Networks]]:
- **FFD** - [[Full Function Device (FFD)]]
	- Acts as the [[Personal Area Networks|PAN]] coordinator, cluster coordinator or as an ordinary network node
- **RFD** - [[Reduced Function Device (RFD)]]
	- Just a network node, can **NOT** route data
- ![[image_IEEE 802.15.4-MAC.png]]
### What kind of [[Network Topologies]] are supported?
[[IEEE 802.15.4-Network Topologies]]
![[image_IEEE 802.15.4-MAC-1.png]]
## **(2)** Elaborate on the operation of the [[IEEE 802.15.4]] [[multiple-access protocols|multiple access protocol]] in a [[Star Topology]].
- Link time is divided into slots
	- Some of the slots are reserved
		- **[[TDMA]]**: contention free
	- The devices contend for the rest of the slots
		- **Slotted** [[CSMA-CA]]
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
## **(3)** Which layers of the [[ZigBee-Protocol Stack|protocol stack(ZigBee)]] are covered by the [[ZigBee]] specification?

- **ZigBee specifies higher layer protocols for low-rate PANs:**
    - **application layer**
    - **Network layer**, 
    - Security layer 
    - and Application Programming Interface
- [[ZigBee]] specifies a comprehensive **security framework** that spans across the <span style="color:rgb(255, 0, 0)">application and network layers</span>
### What is the relationship between [[IEEE 802.15.4]] and [[ZigBee]]? 
> [!failure] [[ZigBee]] is **TOTALLY DEPENDENT**  on [[IEEE 802.15.4]]
- Frequency bands used for communications
- Data rates
	- maximum data rate on **physical layer** is 250 kbit/s
- [[IoT device-duty-cycle|Duty cycle]] (i.e sleeping periods)
- [[ZigBee]] network topologies are based on [[IEEE 802.15.4]] topologies
- [[ZigBee]] network formation is based on mechanisms for [[Personal Area Networks|PAN]] formation according to [[IEEE 802.15.4]] standard...
### What kinds of devices and topologies are supported by ZigBee?
> [!NOTE] Based on [[IEEE 802.15.4]]s (network) [[IEEE 802.15.4-Network Topologies|IEEE Topologies]]
> - [[Mesh Topology]] (based on [[Peer-to-Peer Topology]] of [[IEEE 802.15.4]])
> - [[Tree Topology]] (based on [[Star Topology]] of [[IEEE 802.15.4]])

Devices in Zigbee network are categorized into three types:
- **Coordinator:** control and maintain the Zigbee network
- **Router:** routing message from childes to parents
- **End devices:** collecting data, cannot route messages

**[[ZigBee]] devices have:**
- lower complexity
- Lower energy consumption
- Lower data rates
> [!danger] <span style="font-weight:bold; color:rgb(21, 32, 9)">In the core of [[ZigBee]] application is gathering of sensor readings and issuing commands to actuators</span>

[[ZigBee-Network Topologies]]
[[ZigBee Network Devices]]


## **(4)** What are the basic components of an [[RFID]] system? 
- [[RFID-Reader|reader]] (aka interrogator)
- [[RFID-tags|tag]] (aka transponder)
	- **Can be of different types**
	

### What are the basic types of RFID systems? 
[[RFID-Inductive Systems]]
[[RFID-Radiative Systems]]
### What kinds of [[RFID-tags|RFID tags]] exist? 
-  [[Passive RFID tags]]
	- No power source of their own
	- The reads powers through its transmission both the IC and the tag transmitter
- [[Semipassive RFID tags]] (_aka battery-assisted_)
	- A (small, coin sized) battery is used to power the IC of the tag
	- The tag transmitter is powered by the transmission of the reader
- [[Active RFID tags]]
	- Battery powers both the IC and the conventional transmitter
### Give some example applications of different types of RFID systems.
[[RFID Protocols]]
[[RFID-Components]]
