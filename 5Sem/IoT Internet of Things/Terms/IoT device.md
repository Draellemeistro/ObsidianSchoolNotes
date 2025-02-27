**The key element of an [[IoT network]]. Performs  three basic tasks:**
- Observes its surroundings (**sensing**) [[IoT-Sensors]]
- Processes the sensed data (**Computation**) [[IoT-Computation]]
- Communicates the data (**Communication**) [[IoT-Communication]]

(see also [[IoT device-Power Consumption]])
Some IoT devices may also perform (**typically simple**) commands (**Actuation**)
## Typical architecture of IoT device
![[image_IoT device.png]]

### Most [[IoT device|IoT devices]] have very different features compared to the usual wireless devices
- **limited functionality:** 
	- Limited processing power, lack of software updates
	- Driven by the target to achieve extremely low cost
- **Stringent requirements on energy consumption**
	- Battery may not be rechargeable, while operational time should be more than 10 yrs (example)
- **Embedded devices**
	- Often inaccessible and irreparable, such as in buildings or cars
	- Should be deployed by projecting long-term future use

### From [[IoT-Edge-Cloud]]
A **device** includes hardware and software that directly interact with the world.
- Devices connect to a network to communicate with each other, or to centralized applications
- Devices might be directly or indirectly connected to the internet
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