# Overview + Goals + Roadmap
![[Pasted image 20240529141650.png]]![[Pasted image 20240529141658.png]]

![[Pasted image 20240529170648.png]]

# Terms, topics and such
- hosts, routers: **nodes**
- communication channels that connect **adjacent** nodes alon communication path: **link**
	- wired, wireless
	- LANs
- layer-2 packet: **frame**,
	- encapsulates datagram
- error detection, correction 
- multiple access protocols 
	- addressing, ARP
	- Ethernet 
	- switches 
	- VLANs

# Link layer context

> [!NOTE] What does it do?
> **Link layer** has the responsibility of transferring datagram form one node to **physically adjacent** node over a link.

- datagram transferred by **different link protocols** over different links:
	- e.g. WiFi on first link, Ethernet on next link etc
- Each link protocol provides different services
	- **may or may not** provide reliable data transfer over link

# Services
+ **Framing, link access:**
	+ encapsulate datagram into frame, adding header and trailer
	+ channel access if shared medium
	+ "MAC" addresses in frame headers identify source, destination (different from IP address)
+ **reliable delivery between adjacent nodes**
	+ we already know how to do this
	+ seldom used on low bit-error links
	+ wireless links: high error rates
		+ **WHY BOTH LINK-LEVEL AND END-END RELIABILITY??**
+ **flow control**
	+ pacing between adjacent sending and receiving nodes
+ **error detection**
	+ errors caused by signal attenuation, noise.
	+ receiver detects errors, signals retransmission, or drops frame.
+ **error correction**
	+ receiver identifies **and corrects** bit error(s) without retransmission
+ **half-duplex and full-duplex**
	+ with half duplex, nodes at both ends of link can transmit, but not at same time

# Host link-layer implementation
- in each-and-every host
- link layer implemented on-chip or in network interface card (NIC)
	- implements link, physical layer
- Attaches into host's system buses
- combination of **hardware, software, firmware**

| in each-and-every host<br><br>--- link layer implemented on-chip<br> or in network interface card (NIC)<br><br>    --- implements link, physical layer<br><br>--- Attaches into host's system buses<br><br>--- combination of **hardware, software, firmware** | ![[Pasted image 20240529142751.png]] |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
|                                                                                                                                                                                                                                                                |                                      |

### Interfaces communicating
![[Pasted image 20240529142953.png]]


| **sending side**                                                     | **receiving side**                                           |
| -------------------------------------------------------------------- | ------------------------------------------------------------ |
| encapsulates datagram in frame                                       | Looks for errors, reliable data transfer, flow control, etc. |
| adds error checking bits, reliable data transfer, flow control, etc. | extracts datagram, passes to upper layer at receiving side   |


# Error detection, correction
- EDC: error detection and correction bits (e.g., redundancy)
- D: data protected by error checking, may include header fields
- ![[Pasted image 20240529143132.png]]
- **==Error detection not 100% reliable!==**
	- Protocols may miss some errors, but rarely (see **checksum**)
- Larger EDC field yields better detection and correction

### Parity checking
- **single bit parity**
	- detect single bit errors
	- **even/odd parity:** set parity bit so there is an even/odd number of 1's
- **Two-dimensional parity**: Detect **and correct** single bit errors
	- ![[Pasted image 20240529143855.png]]
- **At receiver:**
	- Compute parity of *d* received bits
	- Compare with received parity bit -if different than error detected.
- **==Internet checksum==**
	- **Goal:** detect errors (flipped bits etc.) in transmitted segment
	- **sender**
		- treat contents of UDP segment (including UDP header fields and IP addresses) as sequence of 16-bit integers
		- **checksum**: addition (one’s complement sum) of segment content
			- checksum value put into UDP checksum field
	- **receiver**
		- compute checksum of received segment
		- check if computed checksum equals checksum field value
			- not equal? **error detected**
			- equal? - **no error detected. ==But maybe errors nonetheless?==**
- **CRC: Cyclic Redundancy Check**
	- More powerful error-detection coding
	- **==D==** data bits (give, think of these as a binary number)
	- **==G==** bit pattern (generator), of r+1 bits (given, specified in **CRC standard**)
	- **sender:** compute r CRC bits, **==R==**, such that <D,R> exactly divisible by G (mod 2)
		- receiver knows **G**, divides by **G**. If non-zero remainder: error detected!
		- can detect all burst errors less than r+1 bits
		- widely used in practice (Ethernet, 802.11 WiFi)
	- ![[Pasted image 20240529144619.png]]

# Multiple Access Links, Protocols

> [!NOTE] Two types of links
> - **point-to-point**
> 	- point-to-point link between Ethernet switch, host
> 	- PPP for dial-up access
> - **Broadcast (shared wire or medium)**
> 	- old-school ethernet
> 	- upstream HFC in cable-based access network
> 	- 802.11 wireless LAN, 4g/4g. satellite
> ![[Pasted image 20240529144840.png]]

### Protocols
- Single shared broadcast channel
- two or more simultaneous transmissions by nodes: **==interference==**
	- **collision** if node receives two or more signals at the same time
- **==DEFINITION==**
	- distributed algorithm that determines how nodes share channel, i.e., determine when node can transmit
	- communication about channel sharing must use channel itself!
		- no out-of-band channel for coordination
- **An ==ideal== multiple access protocol**
	- **GIVEN:** multiple access channel (**==MAC==**) of rate R bps
	- **desiderata:**
		- 1. when one node wants to transmit, it can send at rate R
		- 2. when M nodes want to transmit, each can send at average rate R/M
		- 3. **fully decentralized:**
			- no special node to coordinate transmissions
			- no synchronization of clocks, slots
		- 4. simple

### MAC Protocols
> [!NOTE] Three broad classes
> - **Channel partitioning** *by time, frequency or code* 
> 	- divide channel into smaller "*pieces*" (time slots, frequency, code)
> 	- Allocate piece to node for exclusive use
> - **random access** (dynamic)
> 	- Channel not divided, allow collisions
> 	- "*recover*" from collisions
> - **"taking turns"**
> 	- Nodes take turns, but nodes with more to send can take longer turns


> [!important] Perspective on MAC protocols
> - **channel partitioning MAC protocols**
> 	- share channel **efficiently** and **fairly** at high load
> 	- inefficient at low load: delay in channel acces 1/N bandwidth allocated even if only 1 active node
> - **random acces MAC protocols**
> 	- efficient at low load: single node can fully utilize channel
> 	- high load: collision overhead
> - "**taking turns protocols**"
> 	- ==look for best of both worlds!==


> [!question] Summary of MAC protocols
> - **channel partioning** 
> 	- TIME DIVISION, FREQUENCY DIVISION
> - **random access** (dynamic)
> 	- ALOHA, S-ALOHA, CSMA, CSMA/CD
> 	- carrier sensing: **easy in some technologies (==wire==), hard in others (==wireless==)**
> 	- CSMA/CD used in **ethernet**
> 	- CSMA/CA USED IN 802.11
> - **Taking turns**
> 	- polling from central site, token passing
> 	- bluetooth, FDDI, token ring

#### Channel partitioning MAC protocols
##### TDMA: time division multiple access
- acces to channel in "*rounds*"
- each station gets fixed length slot (length = packet transmission time) in each round
- unused slots go idle
- **example**: 6-station LAN, 1,3,4 have packets to send, slots 2,5,6 idle
- ![[Pasted image 20240529145656.png]]

##### FDMA: Frequency Division Multiple Access
- Channel spectrum divided into frequency bands
- each station assigned fixed frequency band
- unused transmission time in frequency bands go idle
- **example** 6-station LAN, 1,3,4 have packet to send, frequency bands 2,5,6 idle
- ![[Pasted image 20240529145919.png]]
#### Random Access protocols
- when node has packet to send 
	- transmit at full channel data rate R 
	- no a priori coordination among nodes 
- two or more transmitting nodes: “**collision**”
- **==random access protocol specifies==**: 
	- how to detect collisions 
	- how to recover from collisions (e.g., via delayed retransmissions)
- **examples of random access MAC protocols:**
	-  ALOHA
		- slotted ALOHA
	- CSMA
		- CSMA/CD
		- CSMA/CA

##### Slotted ALOHA
- **==Assumptions:==**
	- All frames same size
	- time divided into equal size slots (time to transmit 1 frame)
	- nodes start to transmit only slot beginning
	- nodes are synchronized
	- if 2 or more nodes transmit in slot, all nodes detect collision
- **==operation: ==**
	- When node obtains fresh frame, transmits in next slot
		- **if no collision:** node can send new frame in next slot
		- **if collision:** node retransmits frame in each subsequent slot with probability ***p*** until success
			- **==RANDOMIZATION? WHY?==**
- ![[Pasted image 20240529150712.png]]

| **PROS**                                                             | **CONS**                                                                   |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| single active node can continuously transmit at full rate of channel | collisions, wasting slots                                                  |
| simple                                                               | idle slots                                                                 |
| highly decentralized: only slots in nodes need to be in sync         | nodes may be able to detect collision in less than time to transmit packet |
|                                                                      | clock synchronization                                                      |
- **==Efficiency:==** Long-run fraction of successful slots (many nodes, all with many frames to send)
	- **Suppose:** N nodes with many frames to send, each transmits in slot with probability *p*
		- prob that given node has success in a slot $=p(1-p)^{N-1}$
		- prob that any node has a success $=Np(1-p)^{N-1}$
		- **max efficiency:** find $p*t$ that maximizes $=Np(1-p)^{N-1}$
		- for many nodes, take limit of $Np*(1-p*)^{N-1}$ as N goes to infinity gives:
		- **==MAX EFFICIENCY = $\frac{1}{e}=.37$==**
	- **==at best: channel used for useful transmissions 37% of time!==**

##### CSMA: Carrier Sense Multiple Access
> [!NOTE] Overview
> - simple **==CSMA==** listen before transmit: (don't interrupt other while they speak)
> 	- **if channel sensed idle:** transmit entire frame
> 	- **if channel sensed busy:** defer transmission
> - **==CSMA/CD==:** CSMA with **collision detection**: (polite conversationalist)
> 	- collisions detected within short time
> 	- colliding transmissions aborted, reducing channel wastage
> 	- collision detection easy in wired, ==difficult with wireless==

- **==collisions==**
	- collisions can still occur with carrier sensing:
		- **propagation delay** means two nodes may not hear each other's just-started transmission
	- **collision:** enitre packet transmission time wasted
		- distance & propagation delay play role in determining collision probability
	- **CSMA/CD** reduces the amount of time wasted in collisions
		- Transmission aborted on collision detection
![[Pasted image 20240529151923.png]]

#### "*taking turns*" MAC protocols
##### polling
- ==centralized controller “invites” other nodes to transmit in turn==
- typically used with "*dumb*" devices
- **concerns:**
	- polling overhead
	- latency
	- single point of failure (the polling master)
- **bluetooth uses polling**
##### Token passing
- ==DET ER TALEPINDEN==
- control **token** message explicitly passed from one node to next, sequentially
	- transmit while holding token
- **concerns**
	- token overhead
	- latency
	- single point of failure (token)

# LANs
### MAC addresses

> [!NOTE] INFO
> - 32-bit IP address:
> 	- network-layer address for interface
> 	- used for layer 3 (**network layer**) forwarding
> 	- example: 128.119.40.136
> - MAC (or LAN or physical or Ethernet) address
> 	- **used “locally” to get frame from one interface to another physically-connected interface (same subnet, in IP-addressing sense)**
> 	- 48-bit(6 bytes) MAC address (for most LANs) burned in NIC ROM, also sometimes software settable
> 	- example: 1A-2F-BB-76-09-AD
> 		- ==different notations are used by different orgs==
> 		- hexadecimal(base16) notation
> 		- each char represents 4 bits
> 	- **each interface on LAN:**
> 		- has unique 48-bit MAC address
> 		- has a locally unique 32-bit IP address
> 
> 
> ==ANALOGY:==
> - ==MAC address: like Social Sec. Number==
> - ==IP address: loke postal address==
> 


> [!NOTE] Why though?
> MAC flat address: **portability**
> - can move interface from one LAN to another
> - recal IP address is not portable: depends on IP subnet to which node is attached

> [!NOTE] How are the distributed?
> - Allocation done by IEEE
> - manufacturer buys portions of MAC address space (to assure uniqueness)
> - 

### [[ARP]]

### Routing to another subnet: ADDRESSING
##### walkthrough: sending a datagram from A to B via R
- Focus on addressing - at IP (datagram) and MAC layer (frame) levels
- Assume that:
	- A knows B's IP address
	- A knows IP address of first hop router, R (==HOW?==)
	- A knows R's MAC address (==HOW?==)

![[Pasted image 20240529161735.png]]

1. A creates IP datagram with IP source A, destination B
2. A creates link-layer frame containing **A-to-B** IP datagram
	1. R's MAC address is frame's destination
	2. ![[Pasted image 20240529161842.png]]
3. frame sent from A to R
4. frame received at R, datagram removed, passed up to IP
	1. ![[Pasted image 20240529161858.png]]
5. R determines outgoing interface, passes datagram with IP source A, destination B to link layer
6. R creates link-layer frame containing A-to-B IP datagram. Frame destination address: B's MAC address
	1. ![[Pasted image 20240529161920.png]]
7. R determines outgoing interface, passes datagram with IP source A, destination B to link layer
8. R creates link-layer frame containing A-to-B IP datagram. Frame destination address: B's MAC address
9. transmits link-layer frame
	1. ![[Pasted image 20240529161959.png]]
10. B receives frame, extracts IP datagram destination B
11. B passes datagram up protocol stack to IP

### Ethernet


> [!NOTE] info: dominant wired LAN technology
> - first widely used LAN tech
> - simpler, cheap
> - kept up with speed race: 10 Mbps - 400 Gbps
> - Single chip, multiple speeds
> - **==topology==**
> 	- **bus**: popular through mid 90s
> 		- all nodes in same collision domain (can collide with each other)
> 	- **switched** prevails today
> 		- active link-layer 2 **switch** in center
> 		- each "*spoke*" runs a separate ethernet protocol (nodes do not collide with each other)


> [!NOTE] frame structure:
> Sending interface encapsulates IP datagram (or other **==network layer==** protocol) in **Ethernet frame**
![[Pasted image 20240529162534.png]]
>- **preamble:**
> 	- Used to synchronize receiver, sender clock rates
> 	- 7 bytes of 10101010 followed by one byte of 10101011
> - **Addresses:** 6 byte source, destination MAC address
> 	- if adapter receives frame with matching destination address, or with broadcast address (e.g., ARP packet), it passes data in frame to network layer protocol
> 	- otherwise, adapter discards frame
> - **type:** Indicates higher layer protocol
> 	- mostly IP but others possible
> 	- used to demultiplex up at receiver
> - **CRC:** Cyclic Redundancy Check at receiver
> 	- if error detected, frame is dropped

##### Ethernet: unreliable connectionless
- **connectionless:** No handshaking between sending and receiving NICs
- **unreliable:** receiving NIC doesn't send ACKs or NAKs to sending NIC
	- data in dropped frames recovered only if initial sender uses higher layer rdt (e.g. TCP), otherwise dropped data lost
- ethernet's MAC protocol: unslotted **CSMA/CD with binary backoff**

##### 802.3 Ethernet standards: link & physical layers
![[Pasted image 20240529163400.png]]
### Ethernet switch
switch is a **link-layer** device: takes an active role
- store, forward Ethernet (or other type of) frames
- examine incoming frame's MAC address, **selectively** forward frame to one-or-more outgoing links when frame is to be forwarded on segment, uses CSMA/CD to access segment
**==transparent==** hosts unaware of presence of switch
**==plug-n-play, self-learning==** switches do not need to be configured

![[Pasted image 20240529163757.png]]
![[Pasted image 20240529163824.png]]
![[Pasted image 20240529163830.png]]
![[Pasted image 20240529163836.png]]
![[Pasted image 20240529163847.png]]
![[Pasted image 20240529163855.png]]
![[Pasted image 20240529163904.png]]
![[Pasted image 20240529163912.png]]
### VLAN
- what happens as LAN sizes scale, users change point of attachment?
	- **single broadcast domain:**
		- **scaling:** all layer-2 broadcast traffic (**==ARP, DHCP, unknown MAC==**) must cross entire LAN
		- efficienct, security, privacy **==ISSUES==**
	- administrative issues:
		- CS user moves office to EE - **physically** attached to EE switch, but wants to remain logically **attached** to CS switch

==**switch(es) supporting VLAN capabilities can be configured to define multiple virtual LANS over single physical LAN infrastructure.**==

> [!NOTE] Port-based VLANs
> **switch ports grouped (by switch management software) so that single physical switch.**
> [[Pasted image 20240529165320.png]]

![[Pasted image 20240529165410.png]]
![[Pasted image 20240529165424.png]]
![[Pasted image 20240529165654.png]]
![[Pasted image 20240529165724.png]]
# Extra
## important terms??

## TODO
S