**Message Queue(ing) Telemetry Transport**  see also [[MQTT-SN]]

a **lightweight protocol** designed for IoT devices that have limited processing power, memory and bandwidth
- Open source publish/subscribe protocol
	- Runs over TCP
- Data is relayed by a broker
- Devices can publish and subscribe to different "_topics_"
	- Wildcard \# can be used to subscribe to all
- Once a topic is updated, subscribers get notified and get data via the broker
> [!NOTE] The protocol of choice for **pub-sub** patterns
> ![[5Sem/Distributed Systems n Cloud Computing/terms_topics/image_MQTT.png]]

![[image_Communication-5.png]]
- In [[MQTT]], the devices are divided into TWO categories: **publishers and subscribers**
	- **publishers send messages** to a **[[broker]]**, which acts as a central hub
	- While **subscribers receive messages** from the [[broker]].
	- Publishers DO NOT NEED TO KNOW the number or identity of subscribers
	- and subscribers DO NOT NEED TO KNOW the number or identity of publishers
#### Pros & Cons
- $++$ **lightweight:** MQTT is designed to be lightweight and efficient, making it ideal for IoT devices that have limited processing power, memory, and bandwidth.
- $++$ **Scalable:** : MQTT can handle large-scale IoT deployments with millions of devices and subscribers.
- $++$ **Flexible:** MQTT supports **multiple quality of service levels**, which allows developers to choose the level of reliability that meets their requirements
- $--$ **Message size:** MQTT is designed for small messages, which limits its use cases for applications that require large data transfers.
- $--$ **Complexity:** MQTT requires developers to have a good understanding of the protocol and its implementation.
- $--$ **Security:** MQTT does not provide built-in security features, such as encryption and authentication. These features must be implemented separately
### Subscriptions in [[MQTT]]
- [[MQTT]] uses a **topic-based [[Publish-Subscribe]]** model, where each message has ta topic associated with it.
- The job of an [[broker|MQTT broker]] is **to filter messages based on topic, and then distribute them to subscribers.**
- Subscribers can SUBSCRIBE TO TOPICS USING [[MQTT-wildcards|WILDCARDS]] to receive messages that match a specific pattern.
### [[MQTT-wildcards]]
In [[MQTT]], wildcards provide a powerful mechanism for subscribing to multiple topics simultaneously.
#### There are two types of wildcards:
- **single level:** it is represented by **THE SYMBOL PLUS (+)**. It allows the replacement of a single topic level. By subscribing to a topic with a single-level wildcard, any topic that contains an arbitrary string in place of the wildcard will be matched
	- _FOR EXAMPLE,_ a subscription to **myhome/groundfloor/+/temperature** can produce the following results:
		- _myhome/groundfloor/**livingroom**/temperature_
		- _myhome/groundfloor/**kitchen**/temperature_
- **Multi-level:** the multi-level wildcard covers multiple topic levels. It is represented by **THE HASH SYMBOL (\#)** and must be placed as the last character in the topic, preceded by a forward-slash.
	- When a client subscribes to **a topic with a multi-level wildcard**, it receives all messages of a topic that **begins with the pattern before the wildcard character**, **regardless of the length or depth of the topic.**
	- if the topic specified as **"\#" alone,**  the client receives **all messages** sent to the [[MQTT]] broker [[broker]]
## [[MQTT Protocol Messages]]
![[5Sem/Distributed Systems n Cloud Computing/terms_topics/image_MQTT-1.png]]


# [[MQTT-Security]]
## Security Concerns in [[MQTT]]
Some of the common security concerns in [[MQTT]] are:
- **lack of authentication:**
	- By default, [[MQTT]] does not provide any auth. mechanism for clients or [[broker|brokers]]. 
	- This means that any client can connect to the broker and subscribe or publish to any topic
	- **This can be a serious security concern if sensitive data is being transmitted.**
- **Unencrypted communication:**
	- [[MQTT]] does not provide encryption for communication between clients and [[broker|brokers]].
	- **this means that if a client is transmitting sensitive data, it an easily be intercepted by an attacker**
#### [[VERKADA incident]]
- One example of a real-life cyber attack that impacted **[[MQTT]]** was the 2021 [[VERKADA incident|VERKADA hack]]
- Verkada is a security camera company that uses [[MQTT]] to communicate between devices and its cloud-based management platform.
- In this attack, hackers gained access to Verkada's super-admin account and were able to access live video feeds from thousands of cameras in various locations including prisons, hospitals, and schools.
- affected over 150,000 security cameras, including those used by hospitals, schools, prisons, and companies. The hackers gained access to live camera feeds and archived video footage, raising serious concerns about privacy and security.

### Common [[MQTT]] Attacks
##### Brute-Force Attacks:
When the MQTT broker is configured to accept only authenticated users, attackers can perform brute-force attacks and obtain valid credentials that would allow them to successfully authenticate on the vulnerable server.
##### Denial of Service (DoS) Attacks:
MQTT is vulnerable to DoS attacks, where an attacker can flood the broker with a large number of requests, causing it to crash or become unresponsive.
##### Man-in-the-Middle (MitM) Attacks:
MQTT does not provide any encryption to protect against MitM attacks, where an attacker can intercept the communication between the client and the broker, and modify or eavesdrop on the data being transmitted

### Countermeasures for [[MQTT]]
##### Enabling authentication:
MQTT provides the option to use authentication mechanisms such as username/password or certificates. By enabling authentication, clients will have to provide valid credentials before they can connect to the broker, which helps to prevent unauthorized access
##### Using encryption:
MQTT can be used with TLS (Transport Layer Security) to provide encryption for communication between clients and brokers. This helps to prevent eavesdropping and unauthorized access to sensitive data
##### Implementing access control:
MQTT brokers can be configured to allow or deny access to specific topics based on the client's credentials. This helps to prevent unauthorized access to sensitive topics
##### Limiting network access:
MQTT brokers should be placed behind a firewall and only accessible from trusted networks or clients. This helps to prevent DoS attacks and unauthorized access to the broker
##### Implementing message integrity checks:
MQTT messages can be digitally signed or encrypted to ensure that they have not been tampered with during transmission. This helps to prevent MitM attacks and ensure message authenticity.