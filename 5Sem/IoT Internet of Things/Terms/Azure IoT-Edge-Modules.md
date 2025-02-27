> [!NOTE] The [[Containers|Container]] in Azure IoT.
- Are containers that run [[Microsoft Azure IoT|Azure]] services, third-party services, or your own code. 
- Modules are deployed to IoT Edge devices and execute locally on those devices.
- Units of execution, implemented as Docker compatible [[Containers]], that run your business logic at the edge
- Multiple modules can be configured to communicate with each other, creating a pipeline of data processing.
- You can develop custom modules or package certain Azure services into modules that provide insights offline and at the edge.

##### [[Edge ML-AI|Artificial intelligence at the edge]]
- [[Azure IoT-Edge]] allows you to deploy complex event processing, machine learning, image recognition, and other high value AI without writing it in-house.
- Azure services like Azure Functions, Azure Stream Analytics, and Azure Machine Learning can all be run on-premises via Azure IoT Edge
- You’re not limited to Azure services, though. Anyone is able to create AI modules and make them available to the community for use through the Azure Marketplace
#### Build your own code
- You can deploy your own code to your devices via [[Azure IoT-Edge]]
- [[Azure IoT-Edge]] holds to the same programming model as the other [[Microsoft Azure IoT]] services. You can run the same code on a device or in the cloud.
	- [[Azure IoT-Central]] and [[Azure IoT-Hub]] etc....
- Supports both Linux and Windows, so you can code to the platform of your choice.
- Supports Java, .NET Core 2.0, Node.js, C, and Python. So developers can code in a language they already know and use existing business logic
