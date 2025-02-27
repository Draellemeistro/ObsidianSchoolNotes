- is a helper service for [[Azure IoT-Hub| IoT Hub]] that enables zero-touch, just-in-time [[device provisioning|provisioning]] to the right IoT hub without requiring human intervention
- enables the provisioning of millions of devices in a secure and scalable manner


- Zero-touch provisioning to a single IoT solution without hardcoding IoT Hub connection information at the factory (initial setup)
- [[Load balancing]] devices across multiple hubs
- Connecting devices to their owner's IoT solution based on sales transaction data (**Multitenancy**)
- Connecting devices to a particular IoT solution depending on use-case (**Solution isolation**)
- Connecting a device to the [[Azure IoT-Hub| IoT Hub]] with the lowest latency (**Geo-sharding**)
- reprovisioning based on a change in the device
![[image_Azure Device-Provisioning-Service.png]]