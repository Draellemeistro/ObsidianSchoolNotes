

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