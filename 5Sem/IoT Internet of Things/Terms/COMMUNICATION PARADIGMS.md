Two popular communication models for IoT-Cloud environments:
- [[Request-Reply]]: is designed to support the message exchanges in typical c**lient-server interactions** (see [[Request-Reply Protocols]])
- [[Publish-Subscribe]]: disseminating events to multiple recipients with the sender unaware of the identity of the recipients. Typically, senders and receivers communicate through an intermediary (i.e., [[broker]])
### Choosing the right communication paradigm
The choice of communication paradigm **DEPENDS ON VARIOUS FACTORS,** including:
- The nature of the system
- The performance requirements
- The reliability requirements
- The scalability requirements
- The security requirements
#### Importance in [[IoT-Fog-Cloud]] 
- Communication patterns play a crucial role in the design, development, and deployment of IoT-Fog-Cloud systems
- By using the right communication pattern, we can ensure that the system performs optimally in terms of speed, scalability, reliability, and security.
- For example, in IoT system, 
	- using a **[[Publish-Subscribe]] pattern** can help **REDUCE NETWORK TRAFFIC** and **IMPROVE SCALABILITY**, 
	- while using a **[[Request-Reply]]** pattern can help ensure **RELIABILITY AND CONSISTENCY**
####  [[Request-Reply]] (or **Point-to-Point** communication in general)
- Participants need to exist at the same time
- Participants need to know address of each other and identities
- Not a good way to communicate with several participants
### [[indirect communication]]
- Communication through an **intermediary**
	- **no direct coupling between the sender and the receiver(s)**
- **Space uncoupling:** No need to know identity of receiver(s) and viceversa
	- participants can be replaced, updated, replicated, or migrated
- **time uncoupling:** independent lifetimes
	- requires persistence in the communication channel

### [[Space and Time Coupling]]
see also [[coupling]]
#### [[Space Coupling]]
##### [[Time Coupling]]
###### Properties:
- Communication directed towards a given receiver or receivers
- Receiver(s) must exist at that moment in time
- e.g., _synchronous communication ([[Request-Reply]], [[remote invocation]]_)
##### [[Time Uncoupling]]
###### Properties:
- Communication directed towards a given receiver(s)
- sender(s) and receiver(s) can have independant lifetimes
- e.g., _[[asynchronous communication]] (email, text messaging)_
#### [[Space Uncoupling]]
##### [[Time Coupling]]
###### Properties:
- Sender does not need to know the identity of receiver(s)
- Receiver(s) must exist at that moment in time
- e.g., _[[IP Multicast]]_ 
##### [[Time Uncoupling]]
###### Properties:
- Sender does not need to know the identity of receiver(s)
- sender(s) and receiver(s) can have independant lifetimes
- e.g., _[[indirect communication]] ([[Publish-Subscribe]])_
