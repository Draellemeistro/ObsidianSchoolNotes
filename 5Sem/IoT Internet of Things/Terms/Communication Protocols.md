**[[Azure IoT-Hub]]** supports these: 
- [[HTTPS]], 
- [[AMQP]], 
- [[MQTT]]
- and [[AMQP]]/[[MQTT]] over [[Websockets]]

(i guess these) [[HTTP]], [[MQTT]] and [[AMQP]]

![[image_Communication Protocols.png]]
## Communication vs Connectivity
- **[[Communication Protocols]]** are about how data is exchanged.
- **[[Connectivity Protocols]]** are about where and how devices connect.

## [[Communication Protocols]] in [[IoT-Edge-Cloud]]
### Message Queuing Telemetry Transport ([[MQTT]])
> [!FAIL] **PARADIGM:** [[Publish-Subscribe]], **runs over TCP**

- [[MQTT]] is a **lightweight protocol** designed for IoT devices that have limited processing power, memory and bandwidth
- In [[MQTT]], the devices are divided into TWO categories: **publishers and subscribers**
	- **publishers send messages** to a **[[broker]]**, which acts as a central hub
	- While **subscribers receive messages** from the [[broker]].
	- Publishers DO NOT NEED TO KNOW the number or identity of subscribers
	- and subscribers DO NOT NEED TO KNOW the number or identity of publishers
### Data Distribution Service for Real-Time Systems ([[DDS]])
> [!FAIL] **PARADIGM:** [[Publish-Subscribe]], decentralized with no [[broker]]. **Runs over UDP, but also supports TCP**

- [[DDS]] is particularly useful in domains that require **high-performance** and **low-latency** data exchange, such as [[Industrial IoT]].
- [[transport-layer security (TLS)]] for security
- **Provides:** Authentication, Access Control, Data Tagging, etc...
### Advanced Message Queuing Protocol ([[AMQP]])
> [!FAIL] **PARADIGM:** [[Publish-Subscribe]], 
> - **Direct communication between entities is possible.** Different topologies:
> 	- Client-to-Client
> 	- Client-to-Broker
> 	- Broker-to-Broker
> - Runs over TCP and provides different [[QoS levels]]
> - More features than [[MQTT]] (therefore)
> 	- heavier, more power, processing, and memory demands
> - Preferred for communication in devices that are not constrained
> - [[transport-layer security (TLS)]] for security
### Constrained Application Protocol ([[CoAP]])
> [!FAIL] **PARADIGM:** [[Request-Reply]]
- [[CoAP]] is a lightweight protocol designed for IoT devices with limited resources.
- [[CoAP]] is used for [[machine-to-machine]] communication and is designed to be used over [[constrained networks]], such as low-power wireless networks.
- Is widely used in use cases such as:
- **[[Industrial automation]]:** The Industrial Internet Consortium (IIC) has adopted CoAP as the preferred protocol for [[IIoT]] ([[Industrial IoT]]) applications
- **Smart Grid:** The OpenADR Alliance, an industry group focused on demand response programs for smart grid applications, has chosen CoAP as the protocol for its latest OpenADR 2.0 specification
- **healthcare:** The Continua Health Alliance, an organization focused on developing interoperable healthcare solutions, has adopted CoAP as part of its suite of communication protocols
- **Smart Cities:** The IPSO Alliance, a group focused on promoting the use of IP in smart objects, has developed a Smart Objects Framework that includes CoAP as the communication protocol
### [[HTTP]]
> [!FAIL] **PARADIGM:** [[Request-Reply]]

1. A client sends an HTTP request message to a server, which responds with an HTTP response message.
2. The client can send different types of requests such as below, and the server responds accordingly.
	**a. GET** to to retrieve information,
	**b. POST** to submit data,
	**c. PUT** to update or replace existing data,
	**d. DELETE** to remove data,
#### IoT Use Case
In IoT, a sensor can send a request to a cloud server for processing and storing data. The server responds with a message confirming the successful processing and storage of the data.
#### Pros & Cons
##### Pros
- **Reliability:** The client is guaranteed to receive a response from the server, ensuring that the request is fulfilled.
- **flexibility:** The client can make different types of requests, and the server can respond with different types of responses.
- **Control:** The client has control over the request, and the server has control over the response.
##### Cons
- **Performance:** The client has to wait for the response from the server, which can affect performance, especially in a high-traffic environment.
- **Scalability:** The request-response pattern can become difficult to scale in a large distributed system with many clients and servers.
