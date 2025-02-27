## [[ZigBee]] network layer performs two functions:
##### Message exchange
- Route creation and maintainance
- Routing of messages
##### Network management
- Network initialization
- network address assignment
- [[ZigBee-Network Topologies|Topology]] control
#### Uses network addresses
- 16 bits (2 bytes)
- address assignment is done by the [[ZigBee]] coordinator (see [[ZigBee Network Devices]])
- Network address **is the same as the short** [[IEEE 802.15.4]] MAC address (see [[Media Access Control (MAC)]])
#### [[ZigBee-Packet]] Format
![[image_ZigBee-Network Layer.png]]

# Communication Modes
> [!warning] <span style="font-weight:bold; color:rgb(21, 32, 9)">Three modes of communication:</span>
> - **Broadcast**
> - **Multicast**
> - **Unicast** (the default mode of communication is _Unicast_)
### [[Broadcast]]
- Limited to a [[Personal Area Networks|PAN]]
- **Broadcast** network addres is `0xffff`
- No explicit ACK
	- There is so-called passive ACK mechanism
	- after performing broadcast, **[[ZC(ZigBee-Coordinator)]]** and **[[ZR(Zigbee-Router)]]** switch to reception mode 
	  _(see [[ZigBee Network Devices]])_
		- By listening(i.e., _receiving_) to the transmissions from their neighbors, they verify that the packet is being  (_re_)broadcasted

Upon receiving broadcast transmission, a [[ZigBee]] node waits for a random amount of time (broadcast jitter), before it broadcasts the packet further

If an already broadcasted message is received, the message is not broadcasted again (i.e., it is ignored)

If the passive acknowledgement fails (the related timer expires, [[ZC(ZigBee-Coordinator)]] **/** [[ZR(Zigbee-Router)]] performs another broadcast)
![[image_ZigBee-Network Layer-1.png]]
### [[Multicast]] 
- The message (packet) is meant for a group (a subset) of nodes in [[Personal Area Networks|PAN]]
- Every **multicast** group has a 16-bit ID
	- a node (device) can be a member of several groups
- ##### <span style="font-weight:bold; color:rgb(255, 192, 0)">TWO TYPES OF MULTICAST</span> 
	- Multicast initiated by a group member (**member mode multicasting**)
	- Multicast initiated by a non-member (**non-member mode multicasting**)
###### Non-member mode multicasting
- Source device sends the message to the device that is on the route to some member-device:
	- It is assumed that the routing has taken place
	- The transmission mode is **unicast**
- This is repeated until the message arrives to a group member
	- Then the transmission mode becomes the same as the case of **member mode multicast**
###### Member mode multicasting
- The actual transmission mode is broadcast
- All devices that receive such message (both members and non-members) perform its further broadcast (in the standard way)
	- Number of broadcasts by non-members may be limited by the field non-member radius in network layer header (in the multicast control field)
- ![[image_ZigBee-Network Layer-2.png]]
### [[Convergecast]]
- A very typical [[Transmission Mode]] for sensor networks
	- <span style="font-weight:bold; color:rgb(255, 10, 222)">Many-to-one communication</span>
- All messages are directed towards the **sink node**
	- all [[ZC(ZigBee-Coordinator)]]s and [[ZR(Zigbee-Router)]]s create routes to the sink within the given radius
- ![[image_ZigBee-Network Layer-3.png]]

# More looking at [[Network Topologies]], more specifically [[ZigBee-Network Topologies]]
> [!NOTE] <span style="font-weight:bold; color:rgb(255, 10, 222)">Two (main??) variants:</span> Tree & Mesh 
> - [[Tree Topology]] - **hierarchical topology**
> 	- Combined with hierarchical addressing and simple routing
> 	- [[ZC(ZigBee-Coordinator)]] is in the root of the tree
> 	- ![[image_ZigBee-Network Topologies-4.png]]
> .
> .
> - [[Mesh Topology]] - **non-hierarchical topology**
> 	- Combined with [[AODV routing protocol]]

# Now on to [[ZigBee-Application Layer]]