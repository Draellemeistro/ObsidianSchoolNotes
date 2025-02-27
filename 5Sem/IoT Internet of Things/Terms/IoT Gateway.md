A **Gateway** enables devices that are not directly connected to the internet to reach cloud services.
- the term _gateway_ has a specific function in networking, but here it is also used to describe a class of device that processes data on behalf of a group or cluster of devices


## Fra [[Google Cloud IoT]] og også i [[IoT-Edge-Cloud]]
- A _Gateway_ manages traffic between networks that use different protocols.
	- A gateway is responsible for protocol translation and other interoperability tasks.
	- An [[IoT Gateway]] device is sometimes employed to provide the connection and translation between devices and the cloud
	- Because some devices don't contain the network stack required for internet connectivity, a gateway device acts as a proxy, receiving data from devices and packaging it for transmission over TCP/IP
- A dedicated gateway device might be requirement if devices in the deployment:
	- Don't have routable connectivity to the internet, for example [[Bluetooth]] devices
	- Don't have processing capability needed for [[transport-layer security (TLS)]], and as such can't communicate with Google APIs
	- Don't have the electrical power to perform required network transmissions.
