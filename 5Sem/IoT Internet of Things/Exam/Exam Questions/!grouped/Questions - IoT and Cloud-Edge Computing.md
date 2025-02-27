[[Questions - Introduction to IoT]] -- next [[Questions - IoT Security (attacks)]]
## **(1)** What are the main components of an [[IoT-Edge-Cloud]] system? 
### What [[Communication Protocols]] do the major cloud providers support for IoT?
- [[HTTP]]
- [[MQTT]]
- [[AMQP]]
- ALSO
	- [[CoAP]]
	- [[DDS]] 
## **(2)** What is IoT [[device provisioning]]? 
> [!NOTE] **TLDR:** [[device provisioning]]
> **preparing and configuring IoT devices so they can securely connect** to a network or cloud service, **communicate** with other devices, and **perform** their intended **functions**.
> <span style="color:rgb(255, 0, 0)">ensures that devices are correctly registered, authenticated, and configured for secure operation.</span>
### How can that be done in [[Microsoft Azure IoT]]? 
### What is the difference between [[Azure IoT-Hub]] and [[Azure IoT-Central]]? 

| **[[Azure IoT-Central]]**                                                                                 | **[[Azure IoT-Hub]]**                                                                                                                        |
| --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| A [[SaaS]] solution that makes it easy to get started and pull data into your existing business processes | managed [[PaaS]], acts as a central message hub for bi-directional communication between IoT app and the device                              |
| Provides App Templates                                                                                    | Anyone can use [[Azure IoT-Hub\|IoT Hub]] to build IoT solutions with reliable and secure communications between millions of [[IoT device]]s |
| Provides seamless device connectivity and management                                                      | Supports multi-language and open-source SDKs                                                                                                 |
| Connects millions of devices and manages input/output of data                                             | [[device provisioning\|provision devices]] at scale with IoT device provisioning service.                                                    |

### How can we provision thousands of IoT devices in Azure?
see also [[Azure Device-Provisioning-Service]]
- Enables zero-touch, just-in-time [[device provisioning|provisioning]] to the right IoT hub without requiring human intervention
- enables the provisioning of millions of devices in a secure and scalable manner
- <span style="font-weight:bold; color:rgb(255, 0, 0)">Kubernetes-esque? load-balancing etc</span>
## **(3)** What are the benefits of doing computation at the edge vs. on the cloud? 
uuhhhh, if possible and viable, then less data has to be transmitted. Which we saw was quite costly in terms of power consumption.
[[IoT-Edge-Cloud]] 
[[Cloud IoT]]
[[Fog vs Edge Computing]]
### What do the major cloud providers offer to support this? 
### Describe the components of the [[Azure IoT-Edge]].

### How do modules run on an edge device with the Azure IoT-Edge?
[[Azure IoT-Edge-Modules]]