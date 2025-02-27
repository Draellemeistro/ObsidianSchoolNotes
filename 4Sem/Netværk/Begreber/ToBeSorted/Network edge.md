## network edge:

- **hosts**: clients and servers
	  **servers**: often in data centers
	![[Pasted image 20240208133835.png]]
## Access networks, physical media:
- wired, wireless communication links
	![[Pasted image 20240208133906.png]]
## Network Core:
- interconnected routers
- network of networks
![[Pasted image 20240208134056.png]]
# Access networks and physical media
## How to connect end systems to edge router?
- residential access nets
- institutional access networks (school, company)
- mobile access networks (WiFi, 4G/5G)
![[Pasted image 20240208134221.png]]


## Access networks: cable-based access
- [[frequency division multiplexing (FDM)]]
- [[hybrid fiber coax (HFC)]]
	- network of cable, fiber attaches homes to ISP router 
## Access networks: digital subscriber line (DSL)
- use existing telephone line to central office DSLAM
	- data over DSL phone line goes to Internet
	- voice over DSL phone line goes to telephone net
- 24-52 Mbps dedicated downstream transmission rate
- 3.5-16 Mbps dedicated upstream transmission rate
![[Pasted image 20240208134827.png]]
## Access networks: home networks
![[Pasted image 20240208135114.png]]
## Wireless access networks
**Shared wireless access network connects end system to router**
- via base station aka “access point”
### Wireless local area networks (WLANs)
- typically within or around building (~100 ft)
- 802.11b/g/n (WiFi): 11, 54, 450 Mbps transmission rate
	![[Pasted image 20240208135215.png]]
### Wide-area cellular access networks
- provided by mobile, cellular network operator (10’s km)
- 10’s Mbps
- 4G/5G cellular networks
	![[Pasted image 20240208135302.png]]
## Access networks: enterprise networks

![[Pasted image 20240208135344.png]]
- companies, universities, etc.
- mix of wired, wireless link technologies, connecting a mix of switches and routers (we’ll cover differences shortly)
	- Ethernet: wired access at 100Mbps, 1Gbps, 10Gbps
	- WiFi: wireless access points at 11, 54, 450 Mbps

## Access networks: data center networks
![[Pasted image 20240208135519.png]]
- high-bandwidth links (10s to 100s Gbps) connect hundreds to thousands of servers together, and to Internet
## Host: sends packets of data
host sending function:
- takes application message
- breaks into smaller chunks, known as **packets**, of length **L** bits
- transmits packet into access network at **transmission rate R**
	- link transmission rate, aka link **capacity, aka link bandwidth**

![[Pasted image 20240208141131.png]]


> [!NOTE] Title
> packet transmission delay = time needed to transmit L-bit packet into link =  $$\frac{L_(bits)}{R_(bits/sec)}$$

## Links: physical media
- **bit**: propagates between transmitter/receiver pairs
- **physical link**: what lies between transmitter & receiver
- **guided media**:
	- signals propagate in solid media: copper, fiber, coax
- **unguided media**:
	- signals propagate freely, e.g., radio
### Twisted pair (TP)
- two insulated copper wires
	- Category 5: 100 Mbps, 1 Gbps Ethernet
	- Category 6: 10Gbps Ethernet
### Coaxial cable:
- two concentric copper conductors
- bidirectional
- broadband:
	- multiple frequency channels on cable
	- 100’s Mbps per channel
### Fiber optic cable
- glass fiber carrying light pulses, each pulse a bit
- high-speed operation:
	- high-speed point-to-point transmission (10’s-100’s Gbps)
- low error rate:
	- repeaters spaced far apart
	- immune to electromagnetic noise
### Wireless radio
- signal carried in various “bands” in electromagnetic spectrum
- no physical “wire”
- broadcast, “half-duplex” (sender to receiver)
- propagation environment effects:
	- reflection
	- obstruction by objects
	- Interference/noise
### Radio link types:
- **Wireless LAN** (WiFi)
	- 10-100’s Mbps; 10’s of meters
- **wide-area** (e.g., 4G/5G cellular)
	- 10’s Mbps (4G) over ~10 Km
- **Bluetooth**: cable replacement
	- short distances, limited rates
- **terrestrial microwave**
	- point-to-point; 45 Mbps channels
- **satellite**
	- up to < 100 Mbps (Starlink) downlink
	- 270 msec end-end delay (geostationary)
