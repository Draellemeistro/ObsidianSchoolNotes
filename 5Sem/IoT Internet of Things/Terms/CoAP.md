> [!NOTE] [[CoAP]] overview
> - Motivated by [[Internet of Things]] --- [[IoT]]
> - CoAP (Constrained Application Protocol)
> 	- Application protocol for constrained devices
> - IETF standard RFC 7252
> - [[machine-to-machine]] communication a driving force
> - very small footprint, RAM, ROM
> - URI (Uniform Resource Identifier)
> - [[CoAP]] implementation
> 	- Operating system Contiki-2.6, ETH Zurich
> 		- 8.5 kB ROM  --  1.5 kB RAM
> - Resource discovery
> 	- new feature to find resources (URIs) on a server
> - observe
> 	- new feature, report without `WGET`
> - <span style="color:rgb(255, 0, 0)">UDP port 5683</span> <span style="font-weight:bold; color:rgb(255, 0, 0)">(mandatory)</span>
> - reliable [[unicast]]
> - best effort [[Multicast]]

### CoAP Message Types
- Confirmable message
- Non-confirmable message
- ACK message
- Reset message
- Responses
- Piggy-backed
- Separate

> [!NOTE] CoAP Protocol Header (from RFC)
> ![[image_CoAP.png]]
> 
> **EXAMPLE::**
> ![[image_CoAP-1.png]]



# Constrained Application Protocol 
> [!FAIL] **PARADIGM:** [[Request-Reply]]
> _**If you take away one thing from this post it is that you can consider CoAP a lighter version of HTTP designed for IoT.**_ ([link](https://jonathanberi.medium.com/a-field-guide-to-coap-part-1-75576d3c768b))
- [[CoAP]] is a lightweight protocol designed for IoT devices with limited resources.
- [[CoAP]] is used for [[machine-to-machine]] communication and is designed to be used over [[constrained networks]], such as low-power wireless networks.
- Is widely used in use cases such as:
- **[[Industrial automation]]:** The Industrial Internet Consortium (IIC) has adopted CoAP as the preferred protocol for [[IIoT]] ([[Industrial IoT]]) applications
- **Smart Grid:** The OpenADR Alliance, an industry group focused on demand response programs for smart grid applications, has chosen CoAP as the protocol for its latest OpenADR 2.0 specification
- **healthcare:** The Continua Health Alliance, an organization focused on developing interoperable healthcare solutions, has adopted CoAP as part of its suite of communication protocols
- **Smart Cities:** The IPSO Alliance, a group focused on promoting the use of IP in smart objects, has developed a Smart Objects Framework that includes CoAP as the communication protocol
#### defines “_constrained_” so:
- Limited memory, storage and compute (100s of KBs & 10s of MHz)
- battery power
- low bandwidth (Kbps - kilo _bits_ per second)
- Security, but specialized for, well, constrained devices
## Pros & Cons
#### Pros
- **lightweight:** CoAP is designed to be used on devices with limited resources, making it a good choice for IoT devices.
- **multicast support:** CoAP supports multicast communication, which is useful for broadcasting information to multiple devices
- **Security:** CoAP has built in security features, such as encryption and authentication
#### Cons
- **Limited adoption:** CoAP is not as widely used as other protocols, such as [[MQTT]]
- **UDP protocol:** CoAP uses the UDP protocol, which can be less reliable than TCP for data transmission.
# [[CoAP-Security]]
## Security issues in CoAP
#### DDoS Attacks:
IoT devices using CoAP can be vulnerable to distributed denial of service (DDoS) attacks, where a large number of malicious requests are sent to the device or network, overwhelming its resources and causing it to crash or malfunction.
#### Insecure Object Model:
CoAP's object model, which defines how devices are represented and accessed, can be insecure if not implemented properly. Attackers can exploit vulnerabilities in the object model to gain unauthorized access to devices or data
#### Lack of Standardization:
CoAP is a relatively new protocol, and there is still a lack of standardization and best practices for implementing it securely. This can lead to inconsistencies in security across different IoT devices and networks.
### [[Mirai botnet]] incident
- In 2018, a large-scale botnet attack was carried out on IoT devices that used the Constrained Application Protocol ([[CoAP]]) for communication
- This attack targeted devices that had CoAP implemented in an unsecured manner, allowing them to be easily compromised and turned into bots
- The attack involved sending a large number of malicious CoAP packets to vulnerable devices, overwhelming them and causing them to crash or become unresponsive
- These devices were then added to the botnet, which could be used for a variety of malicious purposes, such as carrying out DDoS attacks or stealing sensitive data