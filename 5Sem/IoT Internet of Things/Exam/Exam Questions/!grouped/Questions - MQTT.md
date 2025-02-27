[[Questions - Low Power Wide Area Networks (LPWAN)]] --- [[Questions - Personal Area Networks (PAN)]]
## **(1)** Explain the [[Publish-Subscribe]] model.
## **(2)** Explain how [[MQTT]] works, e.g., what protocol it runs over, 
[[MQTT Protocol Messages]] 
and [[Publish-Subscribe Protocols]]
### explain the [[broker]] and [[MQTT Topics|topic]] concepts. 
- **[[broker]]:** to filter messages based on topic, and then distribute them to subscribers.
- **[[MQTT Topics|topics]]:** See it as file directory, with subfolders: C/andreas/myhome/myroom/lights **THINK TREES**
	- Subscribers can use [[MQTT-wildcards|wildcards]] to get multiple topics at same time (<span style="color:rgb(255, 0, 0)">think of the \* in terminal</span>)
		- **single level: (+)** C/andreas/myhome/+/lights gets lights in all rooms of home C/andreas/+/myroom/lights gets lights in every home with myroom
		- **Multi-level: (\#)**  get everything in sub-topics. C/andreas/myhome/# gets every topic below this point

### Explain the connection establishment procedure.
[[MQTT Protocol Messages]]
- based on TCP/IP—client and server need TCP/IP stack
- initiated by client
	- kept open until client disconnects (or connection breaks)
- 
## **(3)** Explain MQTT [[QoS levels|Quality of Service (QoS) levels]] and the guidelines for choosing them.
[[MQTT Protocol Messages]]
###### <span style="font-weight:bold; color:rgb(255, 192, 0)">MQTT QoS is an agreement of delivery guarantees for specific messages</span>
- <span style="font-weight:bold; color:rgb(255, 0, 0)">3 level of QoS in MQTT:</span> 
	- <span style="color:rgb(255, 0, 0)">QoS 0:</span> deliver message at most once, best-effort (**_shown in figure below_**)
	- <span style="color:rgb(255, 0, 0)">QoS 1:</span> deliver message at least once
	- <span style="color:rgb(255, 0, 0)">QoS 2:</span> deliver message exactly once
- **QoS 0**
	- When <span style="color:rgb(255, 0, 0)">reasonably stable TCP connection</span>
	- Example: connecting client to MQTT broker over wired network or good WiFi network
- **QoS 1**
	- When <span style="color:rgb(255, 0, 0)">every message is needed</span> and use case is **OK with duplicates**
- **QoS 2**
	- When it is **critical** to application to <span style="color:rgb(255, 0, 0)">get every message only once</span>
	- **Application must be tolerant to delay**
## **(4)** What are the main security concerns in MQTT? 
- **lack of authentication:** and **Unencrypted communication:**
- - **lack of authentication:**
	- By default, [[MQTT]] does not provide any auth. mechanism for clients or [[broker|brokers]]. 
	- This means that any client can connect to the [[broker]] and subscribe or publish to any topic
	- **This can be a serious security concern if sensitive data is being transmitted.**
- **Unencrypted communication:**
	- [[MQTT]] does not provide encryption for communication between clients and [[broker|brokers]].
	- **this means that if a client is transmitting sensitive data, it an easily be intercepted by an attacker**
### What are the types of [[MQTT-wildcards|wildcards]] in MQTT? 
 Subscribers can use [[MQTT-wildcards|wildcards]] to get multiple topics at same time (<span style="color:rgb(255, 0, 0)">think of the \* in terminal</span>)
- **single level: (+)** 
	- C/andreas/myhome/+/lights gets lights in all rooms of home C/andreas/+/myroom/lights gets lights in every home with myroom
- **Multi-level: (\#)**  get everything in sub-topics. 
	- C/andreas/myhome/# gets every topic below this po
### How can wildcards be misused by attackers?
[[MQTT-Security]]
**Attackers** subscribe to unauthorized topics or overload brokers with excessive subscriptions.
- **Solution**: Restrict wildcard usage and monitor for unusual subscription patterns.