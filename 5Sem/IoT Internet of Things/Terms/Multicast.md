
## In regards to [[ZigBee]] as seen in [[ZigBee-Network Layer]]
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