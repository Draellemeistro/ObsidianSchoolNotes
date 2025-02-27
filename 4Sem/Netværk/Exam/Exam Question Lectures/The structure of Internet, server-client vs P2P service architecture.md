# Structure of the internet
## Network Edge
#### Hosts: Clients and servers
- **==Host sending functions==**
	- Take app msg
	- break into to chunks (**PACKETS**) of **L** bits
	- transmit into access network at **transmission rate R**
		- link transmission rate, aka ==**link capacity, aka link bandwidth**== 
	- PacketTransmissionDelay = time to transmit L-bit packet into link = $$PacketTransmissionDelay=\frac{L_{(bits)}}{R_{(bits/sec)}}$$
- servers often in data centers

### Links
- Physical media
	- **bit** data being sent
	- **physical link**: what lies between transmitter & receiver
	- **Guided media**: 
		- signals propagate in solid media: copper, fiber, coax
		- **Twisted pair (TP)**
				- two insulated copper wires 
					- Category 5: 100 Mbps, 1 Gbps Ethernet 
					- Category 6: 10Gbps Ethernet
		- **Coaxial cable**
			- two concentric copper conductors
			- bidirectional 
			- broadband: 
				- multiple frequency channels on cable 
				- 100’s Mbps per channel
		- **Fiber optic cable:** 
			- glass fiber carrying light pulses, each pulse a bit
			- high-speed operation: 
			- high-speed point-to-point transmission (10’s-100’s Gbps) 
			- low error rate: 
				- repeaters spaced far apart 
				- immune to electromagnetic noise
	- **unguided media:**
		- signals propagate freely, e.g., radio
		- **wireless radio**
			- signal carried in various “bands” in electromagnetic spectrum
			- no physical “wire”
			- broadcast, “half-duplex” (sender to receiver)
			- propagation environment effects:
				- reflection 
				- obstruction by objects 
				- Interference/noise
	


> [!NOTE] Radio link types
>  - **Wireless LAN (WiFi)** 
> 	 - 10-100’s Mbps; 10’s of meters 
> - **wide-area (e.g., 4G/5G cellular)** 
> 	- 10’s Mbps (4G) over ~10 Km
> - **Bluetooth: cable replacement** 
> 	- short distances, limited rates 
> - **terrestrial microwave** 
> 	- point-to-point; 45 Mbps channels 
> - **satellite**
> 	- up to < 100 Mbps (Starlink) downlink 
> 	- 270 msec end-end delay (geostationary)

## Network Core

- interconnected routers
- Network of networks
- packet-switching
- 2 key functions
	- forwarding
	- routing


##### Key functionalities
- **==Forwarding==** aka **switching**
	- **local** action: move arriving packets from router's input link to appropriate router output link
- **==Routing==**
	- **global** action: determine source-destination paths taken by packets
	- routing algorithms


##### Packet-switching
**==Hosts break [[Application Layer]] messages into packets**==
Network Forwards packets from one router to the next, across links on path from source to destination
- **==Store-and-forward==**
	- packet transmission delay: takes L/R seconds to transmit (push out) L-bit packet into link at R bps
	- store and forward: entire packet must arrive at router before it can be transmitted on next link
- **==Queueing==**
	- packets arrive faster than they can be serviced
	- **Packet queuing and loss**: if arrival rate (in bps) to link exceeds transmission rate (bps) of link for some period of time
		- Packets will queue, waiting to be transmitted on putput link
		- packets can be dropped(lost) if memory(buffer) in router fills up
## Access networks, physical media
- wired, wireless communication links

> [!NOTE] How to connect end systems to edge router?
> - residential access nets
> - institutional access networks (school, company)
> - mobile access networks (WiFi, 4G/5G)
### cable-based access
- ==**frequency division multiplexing (FDM)**: ==
	- different channels transmitted in different frequency bands
- **==HFC: hybrid fiber coax==**
	- asymmetric: up to 40 Mbps – 1.2 Gbps downstream transmission rate, 30-100 Mbps upstream transmission rate
- **==network==** of cable, fiber attaches homes to ISP router
	- homes **share access network** to cable headend
##### digital subscriber line (DSL)
- use **existing** telephone line to central office DSLAM
	- data over DSL phone line goes to Internet
	- voice over DSL phone line goes to telephone net
- 24-52 Mbps dedicated downstream transmission rate
- 3.5-16 Mbps dedicated upstream transmission rate

### Wireless Access Networks
- **==Shared wireless access network connects end system to router==**
	- via base station aka “access point”
	- **==Wireless local area networks (WLANs)==**
		- Local radius, close to building
		- 802.11b/g/n (WiFi): 11, 54, 450 Mbps transmission rate
	- **==Wide-area cellular access networks==**
		- Wider area. through cellular network operatiors
		- 4g 5g

### data center networks
- high-bandwidth links (10s to 100s Gbps) connect hundreds to thousands of servers together, and to Internet
### enterprise networks
- COMPANIES, UNI etc.
- mix of wired, wireless link technologies, connecting a mix of switches and routers

### Noget andet noget
![[Pasted image 20240528161950.png]]

![[Pasted image 20240528162125.png]]
# Server-Client vs P2P Service Architecture

**Server-Client Architecture:**
- In the server-client model, there are dedicated servers that provide services, and clients that consume these services.
- Servers are always on and await requests from clients, which initiate communication.
- Examples include web servers and email servers.

**Peer-to-Peer (P2P) Architecture:**
- In P2P architecture, there is no central server. Instead, each node (peer) can act as both a client and a server.
- Peers directly interact and share resources with each other.
- Examples include file-sharing systems like BitTorrent.

**Comparison:**
- **Scalability:** P2P is more scalable since the addition of new peers increases both resources and service capacity, whereas client-server models may face bottlenecks at the server.
- **Management:** Client-server architectures are easier to manage due to centralized control, whereas P2P networks require decentralized management.
- **Reliability:** P2P can be more resilient as there is no single point of failure, unlike client-server models which rely on server availability.


![[Pasted image 20240528163230.png]]![[Pasted image 20240528172643.png]]![[Pasted image 20240528175920.png]]