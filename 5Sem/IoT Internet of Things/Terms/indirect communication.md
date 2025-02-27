**Space uncoupled, time uncoupled**
Some processes **WRITE** information into an **abstraction** and some other **READS** from that abstraction
## Good for
- Scenarios where **users connect and disconnect very often**
- **Event dissemination** where **receivers may be unknown and change often**
- scenarios with **very large number of participants**
### Basic Idea
- Some processes **WRITE** information into an **abstraction** and some other **READS** from that abstraction
- There are many examples (such as [[Message Queue Systems]], [[Tuple Space Systems]], [[Distributed Shared Memory Systems]])
- **The most popular example in [[IoT]]:**
	- [[Publish-Subscribe]] Systems (Distributed event-based systems)

- Communication through an **intermediary**
	- **no direct coupling between the sender and the receiver(s)**
- **Space uncoupling:** No need to know identity of receiver(s) and viceversa
	- participants can be replaced, updated, replicated, or migrated
- **time uncoupling:** independent lifetimes
	- requires persistence in the communication channel
#### [[Space Uncoupling]]
##### [[Time Uncoupling]]
###### Properties:
- Sender does not need to know the identity of receiver(s)
- sender(s) and receiver(s) can have independant lifetimes
- e.g., _[[indirect communication]] ([[Publish-Subscribe]])_