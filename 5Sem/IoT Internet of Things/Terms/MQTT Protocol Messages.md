![[image_MQTT Protocol Messages.png]]
# Connection Establishment
- [[MQTT]] based on TCP/IP—client and server need TCP/IP stack
- [[MQTT]] connection always initiated by client
- MQTT connection kept open until client disconnects (or connection breaks)
- simplified `CONNECT` message:
	- `CONNECT {ClientID, cleanSession, lastWill, keepAlive}`
	- `clientID`: unique per client (e.g. MAC address), to keep track of clients and their states
	- `cleanSession`: flag to tell server if client wants persistent connection (store subscriptions)
	- `lastWill`: tells broker if it should notify others that the client disconnected ungracefully
	- `keepAlive`: time interval in seconds between PING request/response
# Subscribe/Unsubscribe
- Clients subsribe to get messages on topics of interest, e.g., temperature
	- `SUBSCRIBE {PacketID, List of subscriptions}`
- Server confirms subscriptions
	- `SUBACK {PacketID, return code per subscription}`
- Client and server also agrees on a [[QoS levels]] (Quality of Service)
	- List of subscriptions is a list of topics/QoS pairs
# Publish
- Clients can publish as soon as connected to broker (publishers)
- Broker publishes to subscribing clients (subscribers)
- Each `PUBLISH` message must contain a topic, used by broker to forward message to interested clients
- Broker processes `PUBLISH` messages to determine which clients have subscribed to the message, and sends the message to them
- Publishing client unaware of subscribing clients—broker keeps track
### Publish message—details
- `PUBLISH {packetID, topicName, qos, retainFlag, payload, dupFlag}`
	- `packetID`: used to match responses
	- `topicName`: string definingn topic, e.g., ”myhome/kitchen/temperature”
	- `qos`: QoS level (Quality-of-Service), kind of delivery guarantee (more soon)
	- `retainFlag`: defines if message is OK as ”last known good value” for topic
	- `payload`: the actual data/content, MQTT is data agnostic (text, binary, ....)
	- `dupFlag`: indicates message is duplicate, relevant for certain QoS levels
# MQTT [[QoS levels|Quality-of-Service]]
- MQTT QoS is an agreement of delivery guarantees for specific messages
- <span style="font-weight:bold; color:rgb(255, 0, 0)">3 level of QoS in MQTT:</span> 
	- <span style="color:rgb(255, 0, 0)">QoS 0:</span> deliver message at most once, best-effort (**_shown in figure below_**)
	- <span style="color:rgb(255, 0, 0)">QoS 1:</span> deliver message at least once
	- <span style="color:rgb(255, 0, 0)">QoS 2:</span> deliver message exactly once
- **Two sides of this**
	- Publisher $\to$ broker, and
	- Broker $\to$ Subscriber
	- Publisher defines QoS for message delivery Publisher $\to$ broker
	- Subscriber defines QoS for message delivery Broker $\to$ Publisher
![[image_MQTT Protocol Messages-3.png]]
### [[MQTT]] QoS 1—deliver at least once
![[image_MQTT Protocol Messages-1.png]]
![[image_MQTT Protocol Messages-4.png]]
### [[MQTT]] QoS 2—deliver exactly once![[image_MQTT Protocol Messages-2.png]]
![[image_MQTT Protocol Messages-5.png]]
## Choosing [[MQTT]] QoS levels..... [[QoS levels]]
Some guidelines
- **QoS 0**
	- When reasonably stable TCP connection
	- Example: connecting client to MQTT broker over wired
	- network or good WiFi network
- **QoS 1**
	- When every message is needed and use case is OK with
	- duplicates
- **QoS 2**
	- When it is critical to application to get every message only
	- once
	- Application must be tolerant to delay

[[MQTT Topics]]
