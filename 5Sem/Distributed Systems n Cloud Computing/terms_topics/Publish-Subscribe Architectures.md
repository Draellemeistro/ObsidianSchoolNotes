(Assume events are described by (Attribute,value) pairs) A system that acts as a clolection of autno operat processes. Coordination is the act of managing communication between processes.
**Content-based subscriptions may easily have serious scalability problems**
- A system that acts as a collection of autonomously operating processes 
- Coordination is the act of managing the communication between processes

![[image_Publish-Subscribe Architectures.png]]
# Csoordination Types
Direct, Mailbox, Event-based, Shared Data space
**Temporally Coupled:** B is typically online when A sends a message
**Temporally decoupled:** A and B do not have to be online at the same time

**Referentially Coupled:** A will communicate with B explicitly
**Referentially Decoupled:** A will send a message to B indirectly

|                             | Temporally Coupled | Temporally decoupled |
| --------------------------- | ------------------ | -------------------- |
| **Referentially Coupled**   | Direct             | Mailbox              |
| **Referentially Decoupled** | Event-based        | Shared Data space    |
**Direct Coordination Type:** 
(Referentially and Temporally coupled) A sends message direct to B, and both are online simultaneously
**Event-based Coordination type:** 
(Referentially Decoupled, Temporally Coupled) A sends message through something(indirectly). Both online simultaneously
**Mailbox Coordination type:** 
(Referentially Coupled, Temporally Decoupled) Direct communication. Not online simultaneously
**Shared data space Coordination type:** 
(Referentially Decoupled. Temporally Decoupled) A sends message indirectly to B. Both don't have to be online simultaneously.
# Pub-Sub / Publish-Subscrube
(Assume events are described by (Attribute,value) pairs) A system that acts as a clolection of autno operat processes. Coordination is the act of managing communication between processes.

**topic-based subscription:** specify a “attribute = value” series
**content-based subscription:** specify a “attribute ∈ range” series
![[image_Event-Driven Architecture.png]]