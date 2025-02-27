![[image_Azure IoT-Edge.png]]

## [[Communication Protocols]] in [[IoT-Edge-Cloud]]



# Fra [[Google Cloud IoT]]
### Device 
(_see [[IoT device]]_)
A **device** includes hardware and software that directly interact with the world.
- Devices connect to a network to communicate with each other, or to centralized applications
- Devices might be directly or indirectly connected to the internet
### Gateway
A **Gateway** enables devices that are not directly connected to the internet to reach cloud services.
- the term _gateway_ has a specific function in networking, but here it is also used to describe a class of device that processes data on behalf of a group or cluster of devices
### Cloud Platform
The data from each device is sent to the **Cloud Platform**, where it is processed and combined with data from other devices, and potentially with other business-transactional data,

## Device
### [[IoT device-Heterogeneity]]
- Its not always clear what constitutes a device
	- Many physical things are modular, which means it can be hard to decide whether the whole machine is the device, or each module is a discrete device.
	- There's no single, right answer to this question
- Different types of hardware & platforms
	- Beaglebone
	- Raspberry Pi
	- Arduino
	- Adafruit Feather
- Different Operating Systems
	- Android Things
	- Linux versions
### Device Metadata
- Identifer (ID) an identifier that uniquely identifies a device
- Class or type
- model
- revision
- date manufactured
- Hardware serial number
### Device State Information & Telemetry
- #### **State information** describes the current status of the device, not of the environment
	- it is updated, but usually not frequently
- #### **telemetry:** data collected by the device.
	- This is the eyes-and-ears data that IoT devices provide to applications. Telemetry is read-only data about the environment, usually collected through sensors
	- each source of telemetry results in a **channel.** Telemetry data might be preserved as a stateful variable on the device or in the cloud.
	- Although each device might sen only a single data point every minute, when you multiply that data by a large number of devices, you quickly need to apply vig data strategies and patterns.

### Device Commands
##### _Commands_ are actions performed by a device.
- Not easily represented as state data.
- Are often not idempotent, which means each duplicate message usually results in a different outcome.
- The command mechanism can include a return value or might rely on the confirmation being made through a separate return message or by reflecting the expected change in the state data.
- Commands might be of limited temporal relevance, so they should include a time-to-live (TTL) or other expiration value.
##### Examples
- Spin 360 degrees to the right
- run self cleaning cycle
- increase the rate by ten percent
### [[On-device Processing]]
- After data is collected from a sensor, the device can provide data processing functionality before sending the data to the cloud.
- Multiple devices might handle the data before it gets to the cloud, and each might perform some amount of processing.

- **converting** data to another format
- **packaging** data in a way that's secure and combines the data into a practical batch
- **validating** data to ensure it meets a set of rules
- **sorting** data to create a preferred sequence
- **enhancing** data to decorate the core value with additional related information
- **summarizing** data to reduce the volume and eliminate unneeded or unwanted detail
- **combining** data into aggregate values

### [[device provisioning]]
![[image_device provisioning.png]]

- **bootstrapping with basic device information.**
	- At a minimum, a device needs an ID and basic metadata
- **Credentials and authentication required for secure communications**
	- For example, the device can be provided a token or key that can be used for ongoing communications.
	- Such credentials might have an expiration time.
- **Authorizing the device**
	- Authorization establishes the permissions of the device to interact with the application or other services, relying on the authentication credentials above
	- Authorization in the specific permission of the device ID and credential with a specific resource it can use
- **Setting up the network connection**
	- A device needs a network connection to be able to communicate with other services and to transmit data.
- **Registering the device**
	- Applications need to know which devices are available
	- A device registry keeps track of which devices are in use, manages the cloud side of authentication, and associates devices with specific data and resources (such as telemetry topics and state storage).

## [[IoT Gateway|gateway]]
- A _Gateway_ manages traffic between networks that use different protocols.
	- A gateway is responsible for protocol translation and other interoperability tasks.
	- An [[IoT Gateway]] device is sometimes employed to provide the connection and translation between devices and the cloud
	- Because some devices don't contain the network stack required for internet connectivity, a gateway device acts as a proxy, receiving data from devices and packaging it for transmission over TCP/IP
- A dedicated gateway device might be requirement if devices in the deployment:
	- Don't have routable connectivity to the internet, for example [[Bluetooth]] devices
	- Don't have processing capability needed for [[transport-layer security (TLS)]], and as such can't communicate with Google APIs
	- Don't have the electrical power to perform required network transmissions.
