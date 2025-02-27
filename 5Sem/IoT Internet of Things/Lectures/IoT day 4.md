This lecture covers basics of low-power low-rate personal area networks, through discussion of the most popular networking solution - IEEE 802.15.4. This is complemented by an overview of ZigBee standard, which covers the higher layers of the protocol stack.
# Topics:
## IEEE 802.15.4


> [!NOTE] IEEE 802.15.4
> defines physical layer and MAC sublayer for low-rate wireless personal area networks (LR-WPANs)
> 
> **Encompasses physical and data link layers**
> - Short-range, low data-rates
> - Communication between devices, not people

Basis for ZigBee, 6LoWPAN, WirelesssHART and MiWi standards, which define higher layers of the protocol stack
![[Pasted image 20240925060150.png]]
#### Versions
- [[IEEE 802.15.4]]-2003 
	- the original standard 
- IEEE 802.15.4-2006 
	- increased data rates to 100 and 250 kbps in 868/915 MHz bands 
- IEEE 802.15.4c-2009 
	- incorporation of 314-316MHz, 430-434 MHz and 779-787 MHz bands (China) 
- IEEE 802.15.4d-2009 
	- incorporation of 3950-3956 MHz bands (Japan) 
- IEEE 802.15.4a-2007
	- Ultra Wide Band (UWB) 
- IEEE 802.15.4e-2012 
	- high-reliability industrial applications (time hopping)
-  …. 
- IEEE 802.15.4-2020
##### Physical layer

> [!NOTE] idk stuff?
> - Half-duplex mode of communication
> - turnaround time from reception to transmission mode (and vice versa) may last up to 12 symbol periods maximum (*denoted as aTurnaroundTime in the standard*)
> - Transmission power can be adusted
> 	- E.g., based on *Link Quality Indicator (**LQI**)* that is being monitored


> [!NOTE] **Clear Channel Assesment (CCA)**
> **Listening before talking**
> - Exploited by the MAC protocol
> - Lasts 8 symbol periods
> - **Three modes** of operations:
> 	- Energy received during CCA period is above some threshold
> 	- A carrier that uses the same band and the same transmission technique as the device is detected
> 	- Combination of the above (**Hybrid?**)

##### Defines/realizes: 
- Frequency bands 
- Signal bandwidth 
- Modulation 
- Data rate 
- Channel coding mechanism 
- Error detection mechanism 
- Frequency, phase and symbol synchronization 
- Physical procedures related to multiple access algorithms (clear channel assessment)

##### Frequency bands
- Transmissions in IEEE 802.15.4 are performed in ISM (Industrial, Scientific, Medical) bands
	- Open to use (limitations in terms of radiated power)
	- A lot of devices are using ISM bands (==I.e., a lot of interference==)
- IEEE 802.15.4 (original standards) uses bands in: 
	- 868/915 MHz 
	- 2.4 GHz
- **==In general: lower frequency -> larger distances + lower data-rates==**
- ![[Pasted image 20240925060651.png]]

##### Physical layer packet
![[Pasted image 20240925060838.png]]
- **Preamble**: synchronization sequence, 32 bits (10101010…)
- **SoP delimiter**: denotes the end of synchronization sequence, 8 bits (10101011)
- **PHY header**: denotes packet length (PHY SDU), 8 bits
- **PHY SDU:**
	- MAC packet-data unit (MAC PDU)
	- Maximum length of 127 bytes (1016 bits)

#### MEDIUM ACCESS CONTROL (Link layer??)
Combination of random-access (contention-based access) and contention-free access
![[Pasted image 20240925061819.png]]
- Link time is divided into slots
	- Some of the slots are reserved: **TDMA - contention free**
	- The devices contend for the rest of the slots: **Slotted CSMA/CA**
- IEEE 802.15.4 foresees that the PAN is organized in clusters
	- A cluster is formed around coordinator
	- two types of coordinators:
		- **PAN coordinator (always exists)**
		- **Cluster coordinator (exists in PANs with more than one cluster)**
- ==There can be two types of devices in a PAN:==
	- **FFD:** Full Function Device
		- Acts as the PAN coordinator, cluster cordinator os as an ordinary network node
		- Can route data
	- **RFD:** Reduced Function Device
		- Just a network node, can note route data
#### Network topologies

> [!NOTE] Network topologies
> There can be two types of topologies in IEEE 802.15.4:
> - **Star topology**
> 	- **FFD** can communicate with **FFD** and **RFD**
> 	- **RFD** can communicate only with **FFD**
> - **Peer-to-peer topology**
> 	- **RFD** can communicate with other **RFDs** directly ==(if ther are in reach of eachother)==
> 	- Coordinator still has to exist
> 
> ![[Pasted image 20240925063111.png]]
> - ![[Pasted image 20240925063336.png]] PAN coordinator
> - ![[Pasted image 20240925063401.png]] Cluster coordinator
> - ![[Pasted image 20240925063414.png]] Node

##### Star topology
In this topology, so-called **==beacon enabled==** mode of operation is used.
![[Pasted image 20240925063826.png]]
- Link time is divided in periods called beacon intervals
	- A beacon interval is divided into active an inactive period
	- Communication is performed during the active period.
	- **an active period is divided into:**
		- ***Contention-Access Period (CAP):*** Contention-based, exists always
		- ***Contention Free Period (CFP):*** Optional
	- During inactive period, the nodes in the cluster sleep / data can be exchanged among clusters (**THrough coordinators**)

- **Coordinator** is in charge of (*it coordinates*) cluster operation in star topology
	- Synchronizes nodes in  the cluster
	- Assigns slots in **CFP** to nodes
	- Transmits beacon packet at the beginning of the active period, notifying the nodes about the duration of the beacon interval and of the active period, slot assignments, etc....

> [!IMPORTANT] **All packet exchanges in star topology involve coordinator**
> **Downlink**: FFD (coordinator) $\rightarrow$ RFD (node)
> **Uplink**: FFD (coordinator) $\leftarrow$ RFD (node)


### stoppede her
#### Slotted CSMA/CA CAP
![[Pasted image 20240925064235.png]]s


## ZigBee
### Intro

> [!NOTE] **ZigBee,** quick and dirty version
> - **ELI5 dummy version:**
> 	- **ZigBee IS TOTALLY DEPENDENT ON IEEE 802.15.4**
> 	- **==IEEE 802.15.4 - networking *"hardware"*==**
> 	- **==ZigBee - application *,,software"*==**
> 
> ZigBee specifies **higher layer protocols for low-rate PANs**: *Network layer, Security layer and Application Programming interface*
> 
> Lower layers are based on **IEEE 802.15.4**
>-  ZigBee combined with IEEE 802.15.4 creates a full protocol stack required for networking and data exchange among the devices that run some IoT application

![[Pasted image 20240925065003.png]]
