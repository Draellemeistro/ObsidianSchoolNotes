Devices in Zigbee network are categorized into three types:
- **Coordinator:** control and maintain the Zigbee network
- **Router:** routing message from childes to parents
- **End devices:** collecting data, cannot route messages

# More depth
### [[ZigBee]] Coordinator - **ZC** 
[[ZC(ZigBee-Coordinator)]]
- There can be only one ZigBee coordinator in the network
- Functions of **ZC** ([[ZigBee]] cordinator)
	- Initiates [[Network Formation]]
	- Acts as [[Personal Area Networks|PAN]] coordinator ([[IEEE 802.15.4]]) - [[Full Function Device (FFD)|FFD]]
	- **Performs routing in the [[ZigBee]] network**
### [[ZigBee]] router - **ZR** 
[[ZR(Zigbee-Router)]]
- an **optional device**
- Functions:
	- Enables network extension
	- Associates with **ZC** or other **ZRs**
	- Acts as a cluster coordinator [[IEEE 802.15.4]] - [[Full Function Device (FFD)|FFD]]
	- **Performs routing in the network**
### [[ZigBee]] End Device - **ZED** 
[[ZED(ZigBee-End-Device)]])
- an **optional device**
	- but should exist in order to actually do something
- [[Reduced Function Device (RFD)]] ([[IEEE 802.15.4]])
- can **NOT** route packets
- <span style="color:rgb(255, 0, 0)">sensor / actuator</span> 
### [[ZigBee]] gateway
- Interface to other (non-[[ZigBee]]) networks
- e.g., [[ZigBee]]-TCP/IP gateway