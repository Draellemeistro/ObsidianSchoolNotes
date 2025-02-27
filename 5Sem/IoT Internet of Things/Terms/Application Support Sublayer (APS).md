
##### [[ZigBee]] application layer (see [[ZigBee-Application Layer|ZigAppLay]]) consists of:
- <span style="font-weight:bold; color:rgb(255, 0, 0)">Application Support Sublayer (APS)</span>
	- <span style="font-weight:bold; color:rgb(255, 0, 0)">the interface between the application and network</span>
	- ![[image_Application Support Sublayer (APS).png]]
- **[[ZigBee Device Object (ZDO)]]:** 
- **Application framework:** 

## APS performs two services:
- Data service
- Management Service
#### Data services
<span style="font-weight:bold; color:rgb(255, 0, 0)">reliable transfer of application layer PDU (i.e. packet)</span> (see [[ZigBee-Packet]])
- Reliability is achieved via ACKs
- May perform fragmentation of PDUs at the source and reassembly at the destination
> [!NOTE] <span style="color:rgb(21, 32, 9)">APS packet format</span>
> ![[image_ZigBee-Packet.png]]
##### Data services can be [[unicast]], [[Multicast]] and [[Broadcast]]
- **[[unicast]]:** there is a single endpoint to which the message is delivered
- **[[Multicast]]:** the message is delivered to all devices identified by the group address
- **[[Broadcast]]:** uses broadcast endpoint address (255)
- There is also an option of a data service with <span style="font-weight:bold; color:rgb(255, 0, 0)">indirect addressing</span> 
	- The message is transferred to [[ZC(ZigBee-Coordinator)]], which uses the info about the source network address and source endpoint to find the destination
		- **[[ZC(ZigBee-Coordinator)|ZC]] has to maintain the binding tables**
	- Used when the [[ZigBee]] devices are of limited capabilities
#### Management Services
- **Security Services**
- **Binding**
- **Group formation / disbanding**