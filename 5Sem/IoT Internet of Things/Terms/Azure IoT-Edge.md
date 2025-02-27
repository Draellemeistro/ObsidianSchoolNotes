**moves cloud analytics and custom business logic to devices** so that your organization can focus on business insights **instead of data management**
[[IoT-Edge-Cloud]]
- Scale out your IoT solution by packaging your business logic into standard containers, then you can deploy those containers to any of your devices and monitor it all from the cloud.
- If you want to respond to emergencies as quickly as possible, you can run anomaly detection workloads at the edge
- If you want to reduce bandwidth costs and avoid transferring terabytes of raw data, you can clean and aggregate the data locally then only send the insights to the cloud for analysis.


## [[Azure IoT-Edge]] Components
(seems similar to [[Kubernetes]])
#### [[Azure IoT-Edge-Modules|Modules]]
- Are containers that run [[Microsoft Azure IoT|Azure]] services, third-party services, or your own code. 
- Modules are deployed to IoT Edge devices and execute locally on those devices.
- ###### [[Edge ML-AI|Artificial intelligence at the edge]] 
	- **Allows you to deploy complex event processing, machine learning, image recognition, and other high value AI without writing it in-house.**
	- Azure services like Azure Functions, Azure Stream Analytics, and Azure Machine Learning can all be run on-premises via Azure IoT Edge
	- You’re not limited to Azure services, though. Anyone is able to create AI modules and make them available to the community for use through the Azure Marketplace
#### [[Azure IoT-Edge-Runtime|Runtime]]
- Runs on each IoT Edge device and manages the modules deployed to each device.
- The Azure IoT Edge runtime enables custom and cloud logic on IoT Edge devices. The runtime **sits on the IoT Edge device and performs management and communication operations.**
#### [[Azure IoT-Edge-Cloud-Based Interface|Cloud-Based Interface]]
Enables you to remotely monitor and manage IoT Edge devices.
