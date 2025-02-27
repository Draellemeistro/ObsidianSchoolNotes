# Question 1
## Differences between typical IoT anmd Standard Wireless Devices
Typically, IoT devices differ from standard wireless devices in following ways:

##### Limited Functionality:
- Limited processing power, lack of software updates
- Driven by the target to achieve extremely low cost
##### Stringent Requirements on Energy Consumption
- Battery may not be rechargeable, while operational time should be more than 10 yrs (example)
##### Embedded Devices
- Often inaccessible and irreparable, such as in buildings or cars
- Should be deployed by projecting long-term future use.
###### **ALSO:** Power Consumption, Connectivity, Processing Power and Communication Patterns
- IoT devices are optimized for low power consumption,
  - whereas standard wireless devices (smartphones etc.) prioritize performance.
- IoT often use LPWAN (like LoRa, NB-IoT) or short-range protocols (ZigBee, Bluetooth, BLE).
  - Standard wireless devices rely more on high speed Wi-Fi or cellular networks.
- Limited computational capabilities as they are designed to perform specific tasks efficiently
- Often set to sleep, i.e., they only operate in intervals, periodically sending small(?) amounts of data.
  - Standard wireless devices generally support and are used for continuous streaming of data (YouTube, Scrolling TikTok etc.)

## What are the basic tasks that a typical IoT device performs and what are their relative power consumptions?
### Sensing, Processing(?), Actuation, Communication
- **Sensing:** Collect data from env using sensors
  - Low Power
- **Processing:** Perform local compute or preprocessing
  - Low(?)/Medium Power
- **Communication:** Transmit data to the cloud / other devices
  - High Power
- **Actuation:** Take action based on received data.
  - Medium / High Power
##### Sensing, Computing, Communication.
Sensing and computing generally don't get any where near as hungry as Communication.
Communication is the real 'killer' when it comes to power consumption and battery life in IoT devices.
## What is the basic strategy to reduce energy consumption of a typical IoT device?
### Sleep... Make em sleep to save power.
Lower the amount of communication needed,
make the device sleep between transmissions (wake it when scheduled communication approaches)

# Question 2
## Sketch a general structure of IoT network
### We have:
- **IoT Devices:** Sensors and Actuators
- **Edge layer:** Gateway or edge computing devices
- **Network Layer:** Communication Protocols (Wi-Fi, LPWAN, Cellular etc.)
- **Cloud/Server:** Data processing and storage
## Elaborate a general classification of IoT networks and provide examples of technologies
1. **Short-Range Solutions:**
  - ZigBee, Bluetooth, Wi-Fi
2. **Personal Area Networks:**
  - BLE, RFID, NFC
3. **Low Power Wide Area Networks:**
  - LoRa, NB-IoT, Sigfox(?)
4. **Cellular IoT:**
  - LTE-M, NB-IoT, 5G

# Question 3
## What are general characteristics of IoT traffic with respect to the standard types of IoT applications?
### Event-driven and Periodic traffic
- **Event-driven:** Devices send data only when event (a trigger of sorts) happens.
- **Periodic:** Devices send data at regular intervals (think of a monitor or heartbeat sensor)
#### Also, maybe... ?
- **Bulk Data Traffic:** Think Video Surveillance
- **Latency-Sensitive Traffic:** Real-time critical applications (some forms of industrial automation)
## Elaborate the differences between asynchronous and synchronous traffic generation
Maybe see asynchronous arrivals and real-time control ???
### synchronous traffic
Data is transmitted at regular time intervals (e.g., sensor networks with periodic updates).
### asynchronous traffic
Data is transmitted at regular time intervals (e.g., sensor networks with periodic updates).
# Question 4
## Exlpain the differences between the reservation (grant) based access and the reservation-free access
### Grant/Reservation-based
- Devices must request access from the network before transmitting data.
  - LTE, 5G scheduling
### Grant/Reservation-free
- Devices can transmit data without prior request
  - LoRa, ALOHA-based systems

# Question 5
## What are the basic 5G service categories? Which of those are relevant for IoT and  why?
#### See also [[5G-IoT service category]] and [[5G service categories]]
##### [[eMBB]]
Enhanced Mobile Broadband (from [[5G]])
- High data rates for data driven applications
- Wide spectrum range
- Wide area of application
##### [[mMTC]]
massive Machine-Type Communications (from [[5G]])
- Scalable connectivity
- Wide Area Coverage
- Deep indoor penetration
##### [[URLLC]]
Ultra-Reliable Low-Latency Communications (from [[5G]])
- Ultra-reliable for mission critical applications
- Low latency for real-time applications
- Suitable for [[Industrial IoT]]
## Provide examples of some IoT use cases relevant for 5G systems
- Smart Cities (mMTC): Large-scale sensor networks.
- Industrial Automation (URLLC): Precise, real-time control in factories.
- Autonomous Vehicles (URLLC): Communication between vehicles and infrastructure.
## Which 3GPP standards are directly related to IoT communications?
###### IoT services pose new challenges to mobile cellular networks
- High number of devices in a cell ([[mIoT]])
- Reliability and latency requirements ([[URLLC]])
##### together they form [[5G-IoT service category]]
- mIoT: 
  - NB-IoT, LTE-M
  - 5G ...?
- URLLC: Ultra-reliable Low Latency Communication
  - 5G IoT enhancements

# Question 6
## Which layers of the protocol stack are covered by IEEE 802.15.4 standard?
### (PHY)sical and (MAC) layer
(MAC, Medium Access Control) precides on the data link layer.
## In which bands this standard operates?
### Depends on locality!
- 2.4 GHz (Worldwide)
- 868 MHz (Europe)
- 915 MHz (US)
- (China etc also have specific operating bands reserved)
## What types of devices the standard foresees and what are the roles?
### FFD & RFD, Full-Function Devices and Reduced-Function Devices
- FFD can act as a coordinator (emphasis on CAN)
- RFD is pretty much just a basic end device with limited Functionality.
## What kind of network topologies are supported?
**There can be two types of topologies in [[IEEE 802.15.4]]:**
### [[Star Topology]]
- [[Full Function Device (FFD)|FFD]] can communicate with [[Full Function Device (FFD)|FFD]] and [[Reduced Function Device (RFD)|RFD]]
- [[Reduced Function Device (RFD)|RDF]] can communicate only with [[Full Function Device (FFD)|FFD]]
### [[Peer-to-Peer Topology]]
- [[Reduced Function Device (RFD)|RFD]] Can communicate with other [[Reduced Function Device (RFD)|RFDs]] (if they are in reach of each other)
- Coordinator still has to exist ([[Full Function Device (FFD)|FFD]]s can only be this)

# Question 7
## Elaborate operations IEEE 802.15.4 multiple access protocol in star topology
### Uses Carrier Sense Multiple Access([[CSMA]]) with Collision Avoidance (so.. [[CSMA-CA]])
- That's the medium access used. Devices check for an idle channel before transmission.
- OPTIONAL Time Division Multiple Access ([[TDMA]]) in beacon-enabled networks...
Fuck, go check out [[IEEE 802.15.4-Network Topologies]]

# Question 8
## Which layers of the protocol stack are covere by ZigBee specification?
It covers the network layer, application-layer. Implements its own ... sub-layers? 
## What is the relation between IEEE 802.15.4 and ZigBee?
zigbee builds on top of ieee standard
## What kind of devices and topologies are supported by ZigBee?
### DEVICES: ZigBee- Coordinator(ZC), Router(ZR), End Device(ZED)
- ZC (Coordinator): Manages the network
- ZR (Router): Forwards packets/traffic
- ZED (End Device) - Is some low-power thing (as in IoThings)
### TOPOLOGY: [[ZigBee]] supports **star**, tree, **and** **mesh** topologies
- [[Star Topology]]: is efficient for low delay and small networks
- [[Tree Topology]]:  is preferred in large scale networks
- [[Mesh Topology]]: Provides more reliable communication (**Redundant paths**)

# Question 9
## What are the basic components of an RFID system?
### Tag, Reader (Transponder, Interrogator) (+ stuff like antennas, processing chips, etc.)
- [[RFID-Reader|reader]] (aka interrogator)
- [[RFID-tags|tag]] (aka transponder)
- Link between the two:
	- Downlink (aka forward link)
	- Uplink (aka backward/reverse link)
- Reader is a (_more_) powerful device
	- The reader antenna may be physically separated from it
- [[RFID-tags|tag]] is simple device that has integrated antenna and an IC (chip) containing the operational logic
## What are the basic types of RFID systems?
### Different ways of classifying RFID systems
1. **Inductive vs. Radiative systems** (based on communication principle).
	1. [[RFID-Inductive Systems]]
	2. [[RFID-Radiative Systems]]
2. **LF, HF, UHF systems** (based on frequency bands).
	1. [[LF RFID]]
	2. [[HF RFID]]
	3. [[UHF RFID]]
3. **Passive, Semi-Passive, and Active tags** (based on the power source of the tags).
	1. [[Passive RFID tags]]
	2. [[Semipassive RFID tags]]
	3. [[Active RFID tags]]
## What kinds of RFID-tags exist?
- PASSIVE
  - No power source of their own
  - The reads powers through its transmission both the IC and the tag transmitter
- ACTIVE
  - Battery powers both the IC and the conventional transmitter
- SEMI-PASSIVE (AKA battery-assisted)
  - A (small, coin sized) battery is used to power the IC of the tag
  - The tag transmitter is powered by the transmission of the reader
## Give some example applications of different types of RFID systems

# Question 10
## Explain Constrained Application Protocol (CoAP)
### Lightweight, designed for IoT devices with limited resources
- Motivated by [[Internet of Things]] --- [[IoT]]
- [[machine-to-machine]] communication a driving force
- very small footprint, RAM, ROM
- URI (Uniform Resource Identifier)
- Reiable (Unicast)
- best effort (Multicast)
## What are the features
oej, det her gider jeg bare ikke mand #TODO
## What are CoAP message types and can you explain them?
- Confirmable message
- Non-confirmable message
- ACK message
- Reset message
- Responses
- Piggy-backed
- Separate
### EXPLANATIONS
sasdasdasdasdasdasdasdasdasdasasd

# Question 11
## Explain the Pub-Sub model
### THINK: RSS feed etc
- **Indirect communication - no direct coupling between the sender and the receiver(s)**
- Typically, theres an intermediary (a broker) between the two.
  - I.e., indirect comm. - no direct coupling between the sender and the receiver
#### PROTOCOLS for Pub-Sub
- MQTT - Message Queue(ing) Telemetry Transport see also [[MQTT-SN]]
- AMQP - Advanced Message Queueing Protocol
- DDS(??)

# Question 12
## Explain how MQTT works, e.g., what protocols it runs over.
- MQTT - Message Queue(ing) Telemetry Transport see also [[MQTT-SN]]
- Devices in two categories:
  - Publisher: send messages to broker
  - Subscriber: receive messages from broker
    - Publishers DO NOT NEED TO KNOW the number or identity of subscribers
    - and subscribers DO NOT NEED TO KNOW the number or identity of publishers
### Runs over TCP, and implements 'topics' (categories) and wildcards
## Explain the broker and topic Concepts
- Broker is just a central element that manages message delivery
- Topics can be visualized as a file tree (branching, and with possible sub trees)
## Explain the connection establishment procedure.
### Depends on whether any EXTRA security measures have been made
- connect. (TCP 3-way handshake, y'know)
- subscribe to topics
- (YOU SEE THE PROBLEM RIGHT?!)

# Question 13
## Explain QoS levels (Quality of Service)
## What are guidelines to choose MQTT QoS levels?

# Question 14
## Explain the main reasons why IoT devices are prone to cyber attacks
## Describe two examples of common attacks in IoT
## Mention two examples of how Fog Computing can be used to improve IoT Security

# Question 15
## Explain the main Security concerns in MQTT
## What are the types of wildcards in MQTT?
### two types of wildcards: single level(+), multi-level(#)
- You know these from navigationg & searching for files in the terminal (the * sign)
## How can the MQTT-wildcards be misused by attackers?
- Spam requests for /#
- Access things that maybe shouldn't be visible
# Question 16
## Explain two reasons why 5G is exposed to cyber attacks.
### HUGE ASS SURFACE TO APPLY ATTACKS. Unprecedented, really.

# Question 17
## What are the main components of an IoT-Edge-Cloud?
## What communication protocols do the major cloud providers support for IoT?

# Question 18
## What is device provisioning?
## How can that be done in Azure?
## What is the difference between Azure IoT-Hub and Central
## How can we provision thousands of IoT devices in azure?

# Question 19
## What are the benefits of doing computation at the edge bs on the cloud?
## What do the major cloud providers offer to support this?
## Describe the components of the Azure IoT-Edge
## How do modules run in an edge device with the Azure IoT-Edge

# Question 20
## State the difference between IoT and Industrial IoT (IIoT)
## State a couple of applications of each technology
## Define the six ISA traffic classes in Industrial automation according to ISA
## State an example of each class

# Question 21
## Explain what is a cyber-physical system

# Question 22
## Explain what is TSCH and RPL in 6TiSCH standard


# Sorted
## Sorted
### Sorted

## IoT Concepts of IoT Networking 
## Cellular IoT
## General IoT standards and technologies
## Industrial IoT
## Intro to IoT
## IoT Security - Attacks
## IoT Security - Defense, Practices, Protocols
## IoT and Cloud-Edge Computing
## Low Power Wide Area networks (LPWAN)
## MQTT
## Personal Area Networks (PANs)
## Short Range Solutions
### What is the difference between grant-based access and reservation-free access?
