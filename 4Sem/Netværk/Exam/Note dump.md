
# Network \# 4
- "*Move complexity to edge. Keep core simple fast*"
- Local dns: when host makes DNS query it is sent to local DNS
	- each ISP has local DNS name server
-  **DNS NAME RESOLUTION**
	- **ITERATED QUERY**: Server sender videre til den næste (respond and forget)
		- "IDK but ask this guy"
	- **RECURSIVE QUERY** Burden is on the contacted server, ==burden of name resolution== 
		- (*Potential for a lot of steps her*)
	- **DNS RECORDS**
		- RR : (Name, Value, Type, TTL)
		- Types:
			- A
			- NS
			- CNAME (Canonical?)
			- MX
	- **DNS PROT(?) MESSAGES** Query and reply have same format
		- EXAMPLE: register name at DNS Registrar
			- Insert NS, A, RR into .com TLD server
- **L2 OVERVIEW**
	- **P2P APPS** Clients are servers
		- ==DRAWBACKS==
			- Can be slow
			- Not enough IP-addresses in the world (at least for IPv4. IPv6 solves it)
			- DNS works on static fixed IP
			- host machine can have diff IPs depending on network
			- IP 32 bits, so $2^{32}$ (roughly 10 billion) different addresses (==why everyone can't have static addresses==)
			- Servers have to havbe static IP, so P2P complex management
			- no always on server
		- self-scalable: more people, more capacity (and other way around)
		- EXAMPLE: bittorrent etc
	- **FILES: P2P vs CLIENT-SERVER**
		- **server** client time grows linearly with N (amount of downloads from client server)
		- **P2P** do N times, but size of peer network helps
		- ==ESSENTIALLY SERVER=LINEAR, WHILE P2P LOGARITHM WITH SIZE OF N (more people are participating in P2P network)==

# Ch3 Transport Layer
## Keywords
- Multiplexing
	- "*coming onto the freeway*"
- demultiplexing (**DEMUX**)
	- "*people take train together. 'OK, i get off here.' something like that *"
	- "*signs that show you where to get off*"
- reliable data transfer
- flow control
- congestion control
- Service access points
	- Services to application layer go through here
- sockets
	- "*bridge connecting the layers App-layer & transport-layer*"
## Transport Layer Protocols
- TCP 
	- Tries to make enhancements (potentially) to IP-layer(**==?==**)
	- **CONNECTION ORIENTED PROTOCOL** ==REMEMBER FOR EXAM==
- UDP 
	- (**==both or just this one?==**) doesn't care what's going on below (layers below it)
	- CONNECTIONLESS, '*DOESN'T CARE*'
	- Especially good for smaller messages. TCP needs to use data on establishing connections
	- DOES ONLY DE- & MULTIPLEXING
	- DOESN'T CARE ABOUT PROBLEMS
		- DATAGRAMS CAN BE LOST. WHO CARES
		- CAN BE OUT OF ORDER. WHO CARES
	- **==BCUZ CONNECTIONLESS!!!!!==**
- 
- There are others but meeeh
- **IP DATAGRAM** has source IP addy, and dest IP addy
	- in ==transport, segment has source & dest port==
- **UDP DATAGRAMS**
	- Datagrams with same dest port, go in same socket, ==whether the source is the same==. (**IS NOT THE CASE FOR TCP**)
		- ifht multiplexing & demultiplexing
- TCP
	- SOCKET IS DECIDED BY THESE FOUR:
		- SOURCE IP
		- SOURCE PORT
		- DEST IP
		- DEST PORT
- **LISTENING SOCKETS**
- **SESSION SOCKETS**
- HTTP SERVER PORT \#: 80
- "*error checking: checksum is hold-over from past, where necessary. We now have more sophisticated and useful solutions, but it is still there below the hood. **cuz why not***"
- **UDP STRENGTHS**
	- It's fast.... SAHNIC
	- little overhead
	- doesn't care about congestion (won't try to help solve congestion problems)
	- **GOOD FOR:**
		- Media streaming
		- DNS
		- SNMP
		- HTTP/3

## Principles of reliable data transfer

- **==STEPS==**
	- Setup & maintain connection: **HANDSHAKE**
	- Dealing with packet corruption: **CHECKSUM**
	- dealing with packet loss: **SEQUENCING OR, Y'KNOW THE \# THING**
	- Making sure packet ordering is ketp: **PACKET ID**
- **RELIABLE SERVICE -**
	- **ABSTRACTION** 
		- "*we assume that it works by letting it do it's thing*"
	- **IMPLEMENTATION**
		- "*forebyg problemer*"
	- BY USING(?) **==AUTOMATA==**
	- **==TCP: BIDIRECTIONAL==**
		- One side doesnt KNOW state / what's up on the other end, so they have to guess from:
			- what they receive
			- assumptions
			- ==THINK EXTRAPOLATE FROM INFORMATION. HAS TO BE DONE SOMETIMES==
## rdt Reliable Data Transfer protocol
-  **rdt (Reliable Data Transfer protocol)**
	- **==basic==**
		- Consider only unidirectional transfer
		- use FSM (Finite State Machine)
	- **==2.0==**
		- recover from errors
			- ACK : *received*
			- NACK: *didnt get it*
		- **==stop-and-wait==**
		- fatal flaw: what do if ack/nack is corrupted?
	- **==2.1==**
		- solves 2.0 problem
			- add sequence \#'s to packets
			- receiver will know to discard duplicates
			- sender handles garbled ack/nacks(??)
		- WALKTHROUGH
			- **SENDER**
				- seq \# adeed to pkt
				- (2 seq \#'s will why)
				- must check if received ack/nack is corrupted
				- **==twice amount of states==**
			- **RECEIVER**
				- must check if received pkt is duplicate
				- state remember if expected 0 or 1 pkt seq \#
	- **==2.2==**
		- **NAK-FREE PROTOCOL** 
			- '*Just ACk the earlier pkt.*'
			- same functionality as rdt2.1, using only ACKs
			- instead of NAK, receiver sends ACK for last pkt received OK
		- **TCP USES THIS**
	- **==3.0==**
		- **SENDER SHOULD WAIT REASONABLE AMOUNT OF TIME**
		- pipelining
		- Go-Back-N
			- window of up to N consecutive transmitted but unACKed pkts
			- **cumulative ACK:** ACK(n)
			- **timer** for oldest in-flight pkt
				- timeout(n):
			- **receiver:** ACK-only: always send ACK for correctly received pkts so far with highest **==in-order==** seq \#
			- May generate duplicate ACKs
			- need only to know **rcv_base**
			- on receipt of out-of-order pkt:
		- Selective Repeat
			- like pipelining, but no go back
			- **receiver individually ACKs all correctly received pkts**
			- **==buffers==** packets for in-order delivery to upper layer
			- **sender maintains:**


- **==TCP receiver==**
	- Event at receiver
		- everything smooth - delay ACK, wait uto 0.5 send ACK if no new
			- we confirm every other segment
		- out-of-order segment, higher than expected seq \#
			- duplicate ACK indicating \# of nexte expected seq. \#
- **==FLOW CONTROL==**
	- der er noget med en buffer
	- (bcuz receive window)
	- "*TCPrcvr advertises free bandwith*" or some shit
	- **==BUFFER SPACE IN RW==**
- **==TCP CONNECTION MANAGEMENT**
	- **3-way handshake**
		- I WANT CONNECT
		- AIIGHT, BET
		- COOL, IM COMMING ONLINE
	- **both sides can close connection**
		- SEND ==FIN-bit== set to 1
- **==PRINCIPLES OF CONGESTION CONTROL==**
	- "*Too many sources sending too much data for the network to handle.*"
		- "*Too many cooks in the kitchen spoil the food*"
	- **long delays** queuing in router buffer
	- **packet loss** buffer overflow in routers
	- **==2 approaches==**
		- E2E congestion control
			- additive increase, multiplicatively decrease 
			- Cautiously increase transmission rate, Quickly course-correct if problem
			- (**slow ramp-up. Slam the brakes if problem**)
		- network assisted
			- router gives direct feedback to sender. **not really the case with public internet**
	- **TCP AIMD**
		- Distributed, async
		- '*everyone does it*'
		- stable 
		- TCP rate
	- **SOME SHIT ABOUT:**
		- RENO
		- TAHOU
	- **IDK CONTEXT:** What to do start:
		- TCP slow start (so after recover??)
			- start very slow, increase rate exponentially , but then slow down to linear
				- when go slow and linear? **when CWND gets to 1/2 of its value before timeout**
			- **implementation:** variable ==ssthresh==
	- **==TCP QUBIC==** better than AIMD to '*probe*' for ??????
		- bcuz something with cubic function
		- **K** point in time when window size will reach $W_{{max}}$ (==is tunable==)
		- **W**
	- **==ECN: EXPLICIT CONGESTION CONTROL==**
		- Router sees problem, tells to receiver that it's a problem. receiver sets ECE bit = ___ to tell sender .......
	- ==**TCP FAIRNESS**==
		- figure out what kind of goal
		- **GENERAL FAIRNESS**
			- UDP
		- **PARALLEL CONNECTIONS**
			- TCP
	- **==QUIC==** Quick UDP
		- *==mix of UDP and TCP==*
		- App-layer protocol on top of UDP
		- Kernel space (TCP, UDP) optimized, simple
		- error & congestion control
		- connect establish
			- 2-way handshake
		- NEW!
			- streams, multiple: multiplexed over single quic connection
				- seperate reliable data transfer, security
				- common congestion cxontrol
			- **avoids end-of-line blocking** one co-stream won't fuck it up for everyone else

## Sokol TCP UDP cameo
- TCP UDP in practice
	- client server example
- **why use threads?**
	- very slow and confusing to do all the work for all the clients
	- ==ALWAYS FLUSH AFTER OUTPUT!!==
- **streams**
	- one stream on the socket houses input stream & output. We need threads to handle multiple clients. **one for each**
	- **Serializable interface**

## Ch4 Data Plane in Network Layer
- network layer service models
- forwarding vs routing
- **Network Layer**
	- PURPOSE: transport packet
		- how to create the path between end points actual transmission is handed over to link layer
- **ROUTERS**
	- Checks header-fields in all IP datagrams
	- **FORWARDING:** moves datagrams from input ports to output ports (==SO DOES ROUTING????==)
	- **ROUTING** creates routing / forwarding table that dictates forwarding.
		- '*planning the trip. more of a background task*'
- **DATA PLANE**
	- Functions are local-logic
- **CONTROL PLANE**
	- network-wide logic (**2 SUB-APPROACHES**)
		- Pre-router control plane
			- **individual routing algos in each and every router exchange info and....**
- **SDN** There is remote controller telling other routers which forwarding  table to use.
- ==**NETWORK LAYER SERVICE MODELS**==
	- best-effort
	- constant bit-rate
	- best-effort succeeded because it is simple and sufficient.
- **INPUT PORT QUEUING:** if datagram arrive faster than forwarding rate into switch
- **BITS -> FRAMES -> DATAGRAMS**
	- Physical layer: **bits**
	- Link layer: **ethernet etc**
	- software layer (network?) look-up, forwarding
		- decentralizewd switching
- **destination-based forwarding** based on any set of header fields
- **table**
	- dest addy range  |  Link interface
	- **think** '*ups says to PostNord: "You know this area, i'll let you handle it"*'
	- best match is longest match
		- longest matching bits gets us closest / farthest
			- matching to destination address
	- longest prefix match
- switching fabrics
	- switching rate
- queuing
	- input port Q: if switch fabric, slower than input ports combined
		- loss due to input buffer overflow
		- **HOL: Head Of Line**
- output port Q
	- all packets want to go same out. **buffering required** but after certain point have to decide how datagrams should bee dropped: **==drop policy==**
		- also **==scheduling discipline==**
- **buffering** when arrival rate exceeds output line speed
	- **drop policy:** Datagrams can be lost due to congestion, lack of buffers
	- **scheduling discipline:** priority scheduling - who gets best performance, network neutrality.
	- **==buffer management==**
		- packet scheduling:
			- first come first served
			- RR(??)
		- Priority: diff Qs for different classes. traffic is divided into classes (classified)
			- some get VIP treatment, some dont
		- Round Robin
			- Q1, then Q2, then Q3
			- add weights: 30% time spent on this Q 
				- **==weighted fair==**
- **some weird shit......**
- **==IP addressing==**
	- 32-bit identifier associated with each host or Router Interface
	- **interface**
		- Connection between router/host & physical layer
	- **dotted decimal IP-address notation/representation**
	- **==subnets==**
		- devices in network that can reac eachother without passing through intervening route
	- IP-ADDY STRUCTURE
		- Devices in same subnet have incommon the high order bits (den første del af IP addressen)
		- **HOST PART** the remaining low order bits
		- **subnet mask** IP addy tal -> tal "first bits = subnet"
			- relevant for prefix matching
- **==CIDR==**
	- Classless InterDomain Routing
		- subnet portion of add can be of arbitrary length
	- addy format: A.b.c.d/x
	- **HOW TO GET ONE?**
		- ==DHCP== Dynamic Host Configuration Protocol
			- Plug-N-play, essentially leasing it (in car terms)
			- You're not always using ip-addy, ex turned off laptop, on the way home
			- goal: ...............
			- **host broadcasts ==DHCP discover== msg \[optional]**
			- **DHCP server responds with ==DHCP offer== msg \[optional]**
			- Typically DHCP server is co-located in router, serving all subnets to which router is attached
		- 
- ==HIERARCHICAL AGGREGATION==
	- Easier routing

## links
- two types
	- Point-to-point
	- broadcast(shared wire / medium)
		- think ...cocktail party?
- multiple acces protocols
	- An ideal multiple acces protocol:
		- something about interference
- three broad classes
	- taking turns
		- hard for wireless (more for ethernet)
		- **polling** used in Bluetooth
		- **Token passing** talepinden sendes på tur
	- Random acces
		- good for if you don't know the \# of people or their use patterns
		- How to: detect collisions & recover from
		- **ALOHA (& slotted ALOHA)**
		- **CSMA**
	- Channel Partitioning
		- simple, ineffective, static
		- **TDMA** (think private parking)
		- **FDMA**
- **==SLOTTED ALOHA==**
	- assumptions
		- all frames are same size
		- time divided into equal slots
		- nodes start transmit only at beginning of slot
	- Decentralized, simple, ineffective(==er det til ALOHA ???==)
- **==CSMA==**: *' Listen before talk'*
	- if channel is sensed idle: **transmit entire frame**
	- if sensed busy (==chance of collision==): **defer/wait**
	- **==CSMA/CD==** *with **C**ollision **D**etection*
		- collision possible even with carrier-sensing
- **==ISOMORPHIC vs SPA==**
- 
