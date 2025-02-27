![[5Sem/IoT Internet of Things/Terms/image_CSMA-CA.png]]
# CSMA/CA: **[[Carrier-sense Multiple Access|CSMA]] with collision avoidance**
- is used in local wireless networks
	- [[IEEE 802.11]]([[Wi-Fi]]), [[IEEE 802.15.4]] ([[ZigBee]])
- In wireless, it is hard to for devices to detect collisions themselves
	- hidden terminal problem
		- ![[image files etc/img5sem/IoT images/image_CSMA-CA.png]]
		- **A and C are hidden terminals to each other.**
- Detecting collisions - absence of ACK
- How the collision avoidance works:
	- If the channel is sensed busy, start random backoff timer
		- timer counts down while channel idle
		- transmit when timer expires
	- If there is no ACK, increase

## An enhancement:
### request to send (RTS) - clear to send (CTS) mechanism
#### IDEA:
**Allow sender to “reserve” channel rather than random access of data frames: avoid collisions of long data frames**
1. Sender first transmits small request-to-send (RTS) packets to BS using [[Carrier-sense Multiple Access|CSMA]]
	1. RTSs may still collide with each other (but they're short)
2. BS broadcasts clear-to-send CTS in response to RTS
	1. CTS heard by all nodes
3. Sender transmits data frame
	1. other stations defer transmissions
#### A can not hear C and vice versa
- However, both A and C can hear B
- **If A requests to send and B says clear to send, then C will hear it and avoid collision.**
- ![[image_CSMA-CA-1.png]]
