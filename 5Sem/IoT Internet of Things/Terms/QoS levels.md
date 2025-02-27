# Nok ifht [[MQTT]] hvis ikke direkte nævnt sammen med noget andet.

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
	- When <span style="color:rgb(255, 0, 0)">reasonably stable TCP connection</span>
	- Example: connecting client to MQTT broker over wired network or good WiFi network
- **QoS 1**
	- When <span style="color:rgb(255, 0, 0)">every message is needed</span> and use case is **OK with duplicates**
- **QoS 2**
	- When it is **critical** to application to <span style="color:rgb(255, 0, 0)">get every message only once</span>
	- **Application must be tolerant to delay**

[[MQTT Topics]]
