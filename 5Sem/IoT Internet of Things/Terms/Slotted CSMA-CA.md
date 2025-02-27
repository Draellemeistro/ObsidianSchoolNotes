Slotted [[CSMA-CA|CSMA/CA]]


## [[IEEE 802.15.4-MAC]]
### [[Slotted CSMA-CA|Slotted CSMA/CA]]  [[Contention-Access Period (CAP)|CAP]] in 
#### Uplink
![[image_Slotted CSMA-CA.png]]

#### Downlink
- Coordinator announces list of the nodes for which there are downlink packets in the beacon
	- Nodes that have received this announcement then send <span style="color:rgb(255, 0, 0)">data request</span> packet to coordinator using the [[Slotted CSMA-CA|Slotted CSMA/CA]]
		- The coordinator then ACKs the reception of the data request packet
	- In the next step, there are two ways for the coordinator to send the downlink packet:
		- **(1)** the packet is sent along with the ACK of the data request if there is enough time in the [[Contention-Access Period (CAP)|CAP]] period
		- **(2)** the packet is sent using the [[Slotted CSMA-CA|Slotted CSMA/CA]] --- **see the figure**
- The nodes that neither have uplink transmissions pending, nor have been announced for the downlink can go back to sleep until the next <span style="font-weight:bold; color:rgb(255, 0, 0)">beacon</span> interval
![[image_Slotted CSMA-CA-1.png]]