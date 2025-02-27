




# From slides
![[image_Microsoft Azure IoT.png]]
### Reference Architecture
![[image_Microsoft Azure IoT-1.png]]
### Azure IoT Data Processing
##### Hot Path
Analyzes data in near-real-time, as it arrives. In the hot path, telemetry must be processed with very low latency.
##### Cold Path
Performs batch processing at longer intervals (hourly or daily). The cold path typically operates over large volumes of data, but the results don't need to be as timely as the hot path
##### Warm Path
Analyzes data that can accommodate longer delays for more detailed processing. Consider **Azure Data Explorer** for storing and analyzing large volumes of data.

## Technologies, Services, Solutions

| If you want to                                                   | Use this                  |
| ---------------------------------------------------------------- | ------------------------- |
| Accelerate the creation of IoT solutions                         | [[Azure IoT-Central]]     |
| Extend intelligence from the cloud to your edge devices          | [[Azure IoT-Edge]]        |
| connect, monitor, and control billions of IoT assets             | [[Azure IoT-Hub]]         |
| Create a digital model of your physical space or assets          | Azure Digital Twins       |
| Explore and gain insights from time-series IoT data in real time | Azure Time Series Insight |
| Build and connect highly secure MCU-powered devices              | Azure Sphere              |
| Making embedded IoT development and connectivity easy            | Azure RTOS                |
| Consume Services privately on Azure Platform                     | Azure SQL Edge            |
#### [[Azure IoT-Central]] vs [[Azure IoT-Hub]]

| [[Azure IoT-Central]]                                                                                     | [[Azure IoT-Hub]]                                                                                                                            |
| --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| A [[SaaS]] solution that makes it easy to get started and pull data into your existing business processes | managed [[PaaS]], acts as a central message hub for bi-directional communication between IoT app and the device                              |
| Provides App Templates                                                                                    | Anyone can use [[Azure IoT-Hub\|IoT Hub]] to build IoT solutions with reliable and secure communications between millions of [[IoT device]]s |
| Provides seamless device connectivity and management                                                      | Supports multi-language and open-source SDKs                                                                                                 |
| Connects millions of devices and manages input/output of data                                             | [[device provisioning\|provision devices]] at scale with IoT device provisioning service.                                                    |


### Fundamentals
#### [[IoT device|IoT devices]]
An [[IoT device]] is typically made up of a circuit board with sensors attached that use WiFi to connect to the internet. 
**For example:**
- pressure sensor on a remote oil pump; 
- Temperature and humidity sensors in an air-conditioning unit; 
- An accelerometer in an elevator; 
- Presence sensors in a room
#### Cloud Services
In an IoT solution, the back-end service provides functionality such as:
- Receiving telemetry at scale from your devices, and determining how to process and store that data.
- Analyzing the telemetry to provide insights, either in real time or after the fact.
- sending commands from the cloud to a specific device
- [[device provisioning|provisioning devices]] and controlling which devices can connect to your infrastructure.
- controlling the state of your devices and monitoring their activities.
- Managing the firmware installed on your devices
#### Communication
Typically, IoT devices send telemetry from the sensors to back-end services in the cloud.
However, other types of communication are possible such as a back-end service sending commands to your device:
- A mobile refrigeration truck sends temperature every 5 minutes to an IoT Hub
- The back-end service sends a command to a device to change the frequency at which it sends telemetry to help diagnose a problem
- A device sends alerts based on the values read from its sensors. For example, a device monitoring a batch reactor in a chemical plant, sends an alert when the temperature exceeds a certain value
- Your devices send information to display on a dashboard for viewing by human operators. For example, a control room in a refinery may show the temperature, pressure, and flow volumes in each pipe, enabling operators to monitor the facility.
- The IoT Device SDKs and [[Azure IoT-Hub]] support common [[Communication Protocols]] such as [[HTTP]], [[MQTT]] and [[AMQP]]

## [[Azure IoT-Central]]
## [[Azure IoT-Hub]]
## [[Azure IoT-Edge]]
## [[Azure Device-Provisioning-Service]]

> [!NOTE] **Opgave:** [[Tasks-11]] om [[Azure IoT-Hub|IoT Hub]]