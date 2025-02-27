## Security Concerns in [[MQTT]]
Some of the common security concerns in [[MQTT]] are:
- **lack of authentication:**
	- By default, [[MQTT]] does not provide any auth. mechanism for clients or [[broker|brokers]]. 
	- This means that any client can connect to the [[broker]] and subscribe or publish to any topic
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
[[MQTT-More Attacks]]
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