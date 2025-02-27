> [!failure] [[ZigBee]] is **TOTALLY DEPENDENT**  on [[IEEE 802.15.4]]

> [!NOTE] **TLDR:** [[ZigBee]] introduction
>
> - **ZigBee specifies higher layer protocols for low-rate PANs:**
>  	- Network layer, Security layer and Application Programming Interface
> - **Lower layers are based on [[IEEE 802.15.4]]**
>  	- [[ZigBee]] combined with [[IEEE 802.15.4]] creates a full protocol stack required for networking and data exchange among the devices that run some IoT application
> - <span style="font-weight:bold; color:rgb(255, 0, 0)">ROUGHLY SPEAKING:</span>
>  	- [[IEEE 802.15.4]]: networking "_hardware_"
>  	- [[ZigBee]]: application "_software_"
>
> ![[image_ZigBee 1.png]]

[[ZigBee]] is standardized by the [[ZigBee Alliance]]

## [[ZigBee]] is totally dependent on [[IEEE 802.15.4]]

- Frequency bands used for communications
- Data rates
 	- maximum data rate on **physical layer** is 250 kbit/s
- [[IoT device-duty-cycle|Duty cycle]] (i.e sleeping periods)
- [[ZigBee]] network topologies are based on [[IEEE 802.15.4]] topologies
- [[ZigBee]] network formation is based on mechanisms for [[Personal Area Networks|PAN]] formation according to [[IEEE 802.15.4]] standard...

#### In comparison to similar [[Personal Area Networks|PAN]] standards that operate in the same bands ([[Bluetooth]], [[IEEE 802.11]]), [[ZigBee]] devices have

- lower complexity
- Lower energy consumption
- Lower data rates

### The focus of [[ZigBee Alliance]] is on

- Home Automation
- Building Automation
- Smart Energy
 	- Monitoring of consumption, accounting, reporting
- Health Care
- Remote Control

> [!danger] <span style="font-weight:bold; color:rgb(21, 32, 9)">In the core of [[ZigBee]] application is gathering of sensor readings and issuing commands to actuators</span>

# Zigbee [[Network Architectures in IWSN Standards]]

## [[ZigBee-Network Topologies]]

![[image_ZigBee-Network Topologies-3.png]]
([[Network Topologies|more general Topologies]])
Zigbee supports star, tree, and mesh topologies

- [[Star Topology]]: is efficient for low delay and small networks
- [[Tree Topology]]: (see example figure) is preferred in large scale networks
- [[Mesh Topology]]: Provides more reliable communication (**Redundant paths**)
![[image_ZigBee.png]]

#### [[ZigBee-Network Formation]]

#### [[ZigBee Network Devices]]

Devices in Zigbee network are categorized into three types:

- **Coordinator:** control and maintain the Zigbee network
- **Router:** routing message from childes to parents
- **End devices:** collecting data, cannot route messages

#### [[Channel Access in IWSN Standards]]

- Zigbee follows **Beacon-based superframe structure**
- Time is divided into superframes
- Each superframe starts with a beacon (control information)
- The superframe consists of **[[Contention-Access Period (CAP)]]** and **[[Contention Free Period (CFP)]]**
 	- **CAP:** nodes compete to get one Guaranteed Time Slot (GTS) in the CFP using CSMA/CA
 	- **CFP:** Succeeded nodes transmit data in the assigned (**[[TDMA]]**) **[[Guaranteed Transmission Slots (GTS)]]** (LIMITED TO 7 GTSs IN A SUPERFRAME)
- Finally, there is the **inactive period**, where nodes are set to sleeping mode to save power
![[image_Channel Access in IWSN Standards.png]]
