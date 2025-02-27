# [[ZigBee]] application layer (see [[ZigBee-Application Layer|ZigAppLay]]) consists of:
- **[[Application Support Sublayer (APS)]]**
	- the interface between the application and network
- **[[ZigBee Device Object (ZDO)]]:** 
	- **offers functions common to all applications**
	- Configuration of a device to operate as:
		- [[ZC(ZigBee-Coordinator)]]
		- [[ZR(Zigbee-Router)]]
		- [[ZED(ZigBee-End-Device)]]
- **Application framework:** 
	- hosts application objects
![[image_ZigBee-Application Layer.png]]

## Application framework
Hosts **application objects**
#### Application Objects
- Application objects are defined by the manufacturer of the device. Every application object has its own address
	- Endpoint address
	- range 1-240
	- **255 - application level broadcast**
#### application profiles
- [[ZigBee]] standard offers application profiles in the application framework
	- **The purpose is to accelerate application development and ensure interoperability**
- <span style="font-weight:bold; color:rgb(255, 0, 0)">Application profile defines:</span> 
	- Messages and message formats
	- Message processing
- Application profile is characterized with 16-bit value assigned by [[ZigBee Alliance]]
	- e.g., home-automation application profile


## [[Application Support Sublayer (APS)]]
**performs two services:**
- Data service
- Management Service
### Data services
<span style="font-weight:bold; color:rgb(255, 0, 0)">reliable transfer of application layer PDU (i.e. packet)</span> (see [[ZigBee-Packet]])
- Reliability is achieved via ACKs
- May perform fragmentation of PDUs at the source and reassembly at the destination
> [!NOTE] <span style="color:rgb(21, 32, 9)">APS packet format</span>
> ![[image_ZigBee-Packet.png]]
#### Data services can be [[unicast]], [[Multicast]] and [[Broadcast]]
- **[[unicast]]:** there is a single endpoint to which the message is delivered
- **[[Multicast]]:** the message is delivered to all devices identified by the group address
- **[[Broadcast]]:** uses broadcast endpoint address (255)
- There is also an option of a data service with <span style="font-weight:bold; color:rgb(255, 0, 0)">indirect addressing</span> 
	- The message is transferred to [[ZC(ZigBee-Coordinator)]], which uses the info about the source network address and source endpoint to find the destination
		- **[[ZC(ZigBee-Coordinator)|ZC]] has to maintain the binding tables**
	- Used when the [[ZigBee]] devices are of limited capabilities
### Management Services
- **Security Services**
- **Binding**
- **Group formation / disbanding**

## [[ZigBee Device Object (ZDO)]]
Initializes **ASS** sublayer, security services and network layer
**Performs following procedures:**
- service discovery, device discovery
- Binding
- Maintains binding tables
- Network management
#### Device Discovery
- Devices from the same [[Personal Area Networks|PAN]]
	- <span style="font-weight:bold; color:rgb(255, 0, 0)">the goal</span> is to find out the network address of the device
#### Service Discovery
- Services that are performed by the endpoints on devices 
	- <span style="font-weight:bold; color:rgb(255, 0, 0)">the goal</span> is to find the endpoint address of the service on the devices

### [[ZigBee-Security]]
#### Security Services
> [!NOTE] [[ZigBee]] provides
> - encryption of data
> - Authentication of devices
> - Authentication of data
##### Encryption
- AES (Advanced Encryption Standard) with 128bit long keys
- Symmetric, block encryption
- <span style="color:rgb(255, 0, 0)">Key exchange can be done in two ways</span> 
	- **(1)** Pre-configured by the device manufacturer
	- **(2)** Key distribution is done by the device that has the role of the <span style="font-weight:bold; color:rgb(255, 0, 0)">trust center</span>:
		- Over insecure link
		- over secure link -- Requires an additional key to make the link secure
##### Authentication of Devices
- Done by <span style="font-weight:bold; color:rgb(255, 0, 0)">trust center</span>
##### Data authentication
- Using MIC (Message Integrity Code)
	- Can be 32, 64, or 128 bits long
		- _Larger size, better protection_
	- Made by CCM (Counter with Cipher Block Chaining Message Authentication Code) protocol
		- Uses the same key as AES
