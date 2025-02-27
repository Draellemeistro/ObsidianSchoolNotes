> [!info] **Definition**
> In an event-driven architecture, code execution is triggered by events. An **event** can be anything, such as:
> - A file upload to an S3 bucket.
> - A new record being added to a database.
> - An HTTP request via an API Gateway.
> - A timer (e.g., run every hour).
## Quick overview
### Key Benefits
- **Flexibility**: Code runs only when an event occurs, making it resource-efficient.
- **Loose Coupling**: Components don’t need to be tightly integrated, as they communicate through events.
### Common Use Cases
- Real-time data processing (e.g., streaming analytics).
- Automation workflows (e.g., resizing images after upload).
- API backends and webhooks.
### AWS Lambda Example
- Lambda functions are inherently event-driven. For instance:
- If a file is uploaded to an S3 bucket, an event is generated, and Lambda can execute code in response.
- If there’s an HTTP request to an API Gateway, Lambda can run code to process it.
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

## How to match Events?
## potential issue
Content-based subscriptions may easily have serious scalability problems