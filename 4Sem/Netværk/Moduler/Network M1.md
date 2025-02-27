## In this lecture, we will cover the basic aspects of computer networks and the Internet:
- What is the Internet and what are its building blocks?
- Network edge vs network core.
- Internet protocols and TCP/IP protocol stack.
[Hjemmeside til at øve wireshark](https://gaia.cs.umass.edu/kurose_ross/wireshark.php)
## Before the lecture:
**Reading:** 
	Kurose, Ross, "Computer Networking: A top down approach", 7th ed: 
	Chapters 1.1, 1.2.1, 1.3.3, 1.4, 15.
**Watch the video:**
	https://www.youtube.com/watch?v=Dxcc6ycZ73M
- [[Wireshark intro]]
# Chapters:
## Chapter 1: introduction
Get “feel,” “big picture,” introduction to terminology

![[Pasted image 20240527050044.png]]
### Overview/Roadmap
- [[Wireshark]]
- What is the Internet? What is a [[Protocol]]?
- [[Network edge]]: hosts, access network, physical media
- [[Network core]]: packet/circuit switching, internet structure
- [[Performance]]: loss, delay, throughput
- Protocol layers, service models
- Security
- [[Internet History]] 
#### the internet 
##### A nuts and bolts view
Billions of connected computing **devices**:
	- **hosts** = end systems
	- running network **apps** at Internet’s “edge”

**Packet switches**: forward packets (chunks of data)
	- *Routers*, *Switches*

**Communication links**
	- fiber, copper, radio, satellite
	- transmission rate: bandwidth

**Networks**
	- collection of devices, routers, links: managed by an organization

- **Internet: “network of networks”**
	- Interconnected ISPs
- **Protocols** are everywhere
	- control sending, receiving of messages
	- e.g., HTTP (Web), streaming video, Skype, TCP, IP, WiFi, 4/5G, Ethernet
- **Internet standards** 
	- **RFC**: Request for Comments
	- **IETF**: Internet Engineering Task Force
##### A "services" view
- **Infrastructure** that provides services to applications:
	- Web, streaming video, multimedia teleconferencing, email, games, ecommerce, social media, interconnected appliances, …
- provides **programming interface** to distributed applications:
	- “hooks” allowing sending/receiving apps to “connect” to, use Internet transport service
	- provides service options, analogous to postal service
#### What's a protocol?
**Human protocols:**
- “what’s the time?”
- “I have a question”
- introductions
**Network protocols:**
- computers (devices) rather than humans
- all communication activity in Internet governed by protocols

![[Pasted image 20240208112855.png]]
> [!NOTE] Protocols
> Protocols define the format, order of messages sent and received among network entities, and actions taken on message transmission, receipt

#### Network edge:
#TODO 

#### Network core:
#TODO 

#### Performance:
#TODO 

#### Protocol layers, service models
#TODO 

#### History
#TODO 