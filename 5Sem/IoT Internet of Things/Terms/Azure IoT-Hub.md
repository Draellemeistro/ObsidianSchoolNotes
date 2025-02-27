> [!NOTE] Managed service to enable bi-directional communication between [[IoT device|IoT devices]] and Azure

![[image_Azure IoT-Hub.png]]
### Features / selling points
- **Connect your devices:** Use the [[Azure IoT Device SDK]] libraries to build applications  that run on your devices and interact with [[Azure IoT-Hub]]
	- **supported platforms:** Multiple linux distributions, Windows, and real-time OSs
	- **Supported languages:** C, C#, Java, Python, Node.js
	- **[[Communication Protocols]]:** [[HTTPS]], [[AMQP]], [[MQTT]] and [[AMQP]]/[[MQTT]] over [[Websockets]]
- **Scalability**: [[Azure IoT-Hub|IoT Hub]] scales to millions of simultaneously connected devices and millions of events per second to support your IoT workloads.
- **Security**: [[Azure IoT-Hub|IoT Hub]] gives you a secure communication channel for your devices to send data.
	- Per-device authentication enables each device to connect securely to IoT Hub and for each device to be managed securely.
	- You have complete control over device access and can control connections at the per-device level.
	- The **[[Azure IoT-Hub|IoT Hub]] Device Provisioning Service** automatically provisions devices to the right IoT hub when the device first boots up.
	- Multiple authentication types support a variety of device capabilities
- **Route device data:** Built-in message routing functionality gives you flexibility to set up automatic rules-based message fan-out:
	- Use message routing to control where your hub sends device telemetry ([MS link om message routing](https://learn.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-messages-d2c))
- **integrate with other services:** Integrate [[Azure IoT-Hub|IoT Hub]] with other [[Microsoft Azure IoT|Azure]] services to build complete, end-to-end solutions.
	- **Azure Event Grid** to enable your business to react quickly to critical events in a reliable, scalable, and secure manner.
	- **Azure Logic Apps** to automate business processes
	- **Azure Machine Learning** to add machine learning and AI models to your solution
	- **Azure Stream Analytics** to run real-time analytic computations on the data streaming from your device.
- **Configure and control your devices**
	- Store, synchronize, and query device metadata and state information for all your devices.
	- Set device state either per-device or based on common characteristics of devices
	- Automatically respond to a device-reported state change with message routing integration
- **Make your solution highly available**
	- There's a 99.9% Service Level Agreement for [[Azure IoT-Hub|IoT Hub]]

## [[Azure IoT-Central]] vs [[Azure IoT-Hub]]

| [[Azure IoT-Central]]                                                                                     | [[Azure IoT-Hub]]                                                                                                                            |
| --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| A [[SaaS]] solution that makes it easy to get started and pull data into your existing business processes | managed [[PaaS]], acts as a central message hub for bi-directional communication between IoT app and the device                              |
| Provides App Templates                                                                                    | Anyone can use [[Azure IoT-Hub\|IoT Hub]] to build IoT solutions with reliable and secure communications between millions of [[IoT device]]s |
| Provides seamless device connectivity and management                                                      | Supports multi-language and open-source SDKs                                                                                                 |
| Connects millions of devices and manages input/output of data                                             | [[device provisioning\|provision devices]] at scale with IoT device provisioning service.                                                    |

### [[Azure Device-Provisioning-Service]]
- is a helper service for [[Azure IoT-Hub| IoT Hub]] that enables zero-touch, just-in-time provisioning to the right IoT hub without requiring human intervention
- enables the provisioning of millions of devices in a secure and scalable manner


## Questions from exam
#### What is the difference between [[Azure IoT-Hub]] and Central?
- What is [[device provisioning|IoT device provisioning]]?
- How can that be done in Azure?
- What is the difference between [[Azure IoT-Hub]] and [[Azure IoT-Central]]?
