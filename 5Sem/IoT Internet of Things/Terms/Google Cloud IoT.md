Google Cloud IoT is a complete set of tools to connect, process, store, and analyze data both at the edge and in the cloud.

**The platform consists of** 
- scalable, fully-managed cloud services
- an integrated software stack for [[Edge Computing|edge]]/on-premises computing with machine learning capabilities for all you IoT needs.

**For use cases, see [[Cloud IoT Use Cases]], under Google**
![[image_Google Cloud IoT-1.png]]
## Google IoT Components
- look at this [link](https://cloud.google.com/architecture/connected-devices)
> [!NOTE] #TODO Sæt nedestående in i [[IoT-Edge-Cloud]] måske?
### Device 
A **device** includes hardware and software that directly interact with the world.
- Devices connect to a network to communicate with each other, or to centralized applications
- Devices might be directly or indirectly connected to the internet
### Gateway
A **Gateway** enables devices that are not directly connected to the internet to reach cloud services.
- the term _gateway_ has a specific function in networking, but here it is also used to describe a class of device that processes data on behalf of a group or cluster of devices
### Cloud Platform
The data from each device is sent to the **Cloud Platform**, where it is processed and combined with data from other devices, and potentially with other business-transactional data,

## Reference Architecture
- Device data captured by [[Cloud IoT Core]] gets published to [[Google Cloud-PubSub]]  for [[downstream analytics]].
- Easy to do ad hoc analysis using [[Google BigQuery]]
- Run advanced analytics and apply machine learning with [[Cloud Machine Learning Engine]]
- Visualize results with rich reports and dashboards in [[Google Data Studio]]
![[image_Google Cloud IoT.png]]

# Google IoT Edge 
### AI at the Edge - [[Project Coral]]
- The Edge TPU allows you to deploy high-quality ML inferencing at the edge, using various prototyping and production products from [Coral](https://coral.ai/).
- Edge TPU complements CPUs, GPUs, FPGAs, and other ASIC solutions  for running AI at the edge.
- The Coral platform for ML at the edge augments Google's Cloud TPU and [[Google Cloud IoT]] to provide an end-to-end (cloud-to-edge, hardware + software) infrastructure to facilitate the deployment of customers' AI-based solutions.
- The Coral platform provides a complete developer toolkit so you can compile your own models or retrain several Google AI models for the Edge TPU, combining Google's expertise in both AI and hardware
# From slides
## Use Cases

## Components description
### Devices
### Gateway
### Cloud
## How to work with google cloud iot
### TPU
### AI at the edge -- [[Project Coral]]