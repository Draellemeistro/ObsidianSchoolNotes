- **[[Terms_L1-Intro_to_Cloud|Overview L1]]** ----- [[CLoud 1 introductions]]
- **[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch]]
- **[[Terms_L3-Cloud_Services|Overview L3]]** ----- [[Cloud 3 Cloud Computing Services]] & [[Cloud 3 Extra stuff]]
- **[[Terms_L4-Serverless_Computing|Overview L4]]** ----- [[Cloud 4 Serverless]]
- **[[Terms_L5-Kubernetes|Overview L5]]** ----- [[Cloud 5 Kubernetes]]
- **[[Terms_L6-Intro_DistrSys_Architectures|Overview L6]]** ----- [[Cloud 6 Intro to Distributed Systems]]
- **[[Terms_L7-CommProtocols_DistrSystems|Overview L7]]** ----- [[Cloud 7 Threads n Comm Models]]
- **[[Terms_L8-Coordination|Overview L8]]** ----- [[Cloud 8 Coordination]]
- **[[Terms_L9-Consistency_n_Replication|Overview L9]]** ----- [[Cloud 9 Consistency n Replication]]
- **[[Terms_L10-Fault_Tolerance|Overview L10]]** ----- [[Cloud 10 Fault Tolerance]]
# **Til Chat:**
 alright, great. Combine them all like a list (markdown format) with different things categorized under the relevant parent thing
# L1 - Introduction to [[cloud computing]]

## All L1 Terms

- [[ELI5 Cloud Computing]]
- [[Deployment Models]]
	- Public Cloud
	- Private Cloud
	- Hybrid Cloud
	- Multi-Cloud
- [[as-a-Service Models|service models]]
	- IaaS, PaaS, SaaS
## [[Virtualization]]
- Definition
- [[Hypervisor]] Types
    - [[Type-1-hypervisor]]
    - [[Type-2-Hypervisor]]
- [[Virtualization Types]]
    - [[Full-Virtualization]]
    - [[Para-Virtualization]]
    - [[Hardware-Assisted-Virtualization]]
    - [[OS-Level-Virtualization]] ([[Containers]])
- [[Virtual Machines|Virtual Machines]]
- [[Containers]]
- [[Containers]] vs [[Virtual Machines|Virtual Machines]]
- [[Kata-Containers]]
## Questions and Thoughts
- How does [[Virtualization]] enable [[cloud computing]]?
- What are the trade-offs between public and private clouds?
- How do [[Containers]] compare to [[Virtual Machines]] in terms of performance and isolation?
## Relevant Terms from Other Lectures
- [[Kubernetes]] (L5)
- [[Container Orchestration]] (L5)
---
# L2 - Monolithic and Microservices-Based Architectures
**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch]]
## All L2 Terms
- [[Monolithic Architecture]]
    - Single-process Monolith
    - Modular Monolith
    - Distributed Monolith
- [[Microservice-based Architecture]]
- Benefits and Challenges of Microservices
- [[Auto-scaling]]
- [[Load balancing]]
- Trade-offs in Microservices Adoption
- Service Decomposition
## Microservices and Container-Based Architectures
- Container Deployment
- Decentralized Governance
- Decentralized Data Management
- Service Meshes
## Questions and Thoughts
- What makes microservices scalable compared to monolithic architectures?
- What are some pitfalls in [[decomposing applications into services]]?
## Relevant Terms from Other Lectures
- [[Kubernetes]] Deployments (L5)
- [[RESTful Architectures]] (L6)

---
# L3 - [[Cloud Services]]
## All L3 Terms
- AWS Service Categories
    - Storage
    - Compute
    - Networking & Content Delivery
    - Database
    - Developer Tools
    - Machine Learning
    - Serverless
    - Security, Identity, & Compliance
    - Front-End Web & Mobile
    - Analytics
    - Business Applications
    - Management & Governance
    - Generative AI
## Tools
- [[AWS Lambda]] (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])
- Google Cloud Functions (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])
- Azure Tools
## Questions and Thoughts
- How do cloud providers differ in their service offerings?
- Why are serverless services particularly useful for event-driven architectures?
## Relevant Terms from Other Lectures
- Event-Driven Architectures (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])
- [[Auto-scaling]] (**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch|L2]]) 

---
# L4 - [[Serverless Computing]]
## All L4 Terms
- [[AWS Lambda]]
- Serverless Concepts
- Event-Driven Architectures
- Stateless Functions
- Function Triggers
- Monitoring Lambda Functions
## Tools
- Google Cloud Functions
- Document AI Pipeline
## Questions and Thoughts
- What are the key differences between serverless and traditional compute models?
- How can serverless architectures reduce operational overhead?
## Relevant Terms from Other Lectures
- Orchestration (**[[Terms_L5-Kubernetes|Overview L5]]** ----- [[Cloud 5 Kubernetes|L5]])
- [[Kubernetes]] (**[[Terms_L5-Kubernetes|Overview L5]]** ----- [[Cloud 5 Kubernetes|L5]])

---
# L5 - [[Kubernetes]]
## All L5 Terms
- [[Kubernetes]]
- [[Kubernetes]] Architecture
    - Control Plane
    - Worker Nodes
    - Pods
    - Deployments
    - Services
- Cluster Management
- Declarative Configuration
- Continuous Deployment
- Blue-Green Deployments
- Canary Deployments
## Tools
- Kubectl
- Minikube
## Questions and Thoughts
- How does [[Kubernetes]] enable scaling and failover?
- What challenges arise in multi-cloud Kubernetes deployments?
## Relevant Terms from Other Lectures
- [[Containers]] (L1)
- Microservices (**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch|L2]])
- Event-Driven Architectures (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])

---
# L6 - Introduction to [[Distributed Systems]]; Architectures
## All L6 Terms
- [[Distributed Systems]]
- [[System Topologies]]
	- [[client-server]] Architecture
	- [[Peer-to-Peer (P2P)]] Architecture
	- [[Hybrid Architectures]]
	    - [[cloud computing]]
	    - Edge Computing
	    - Blockchain Architecture
	- [[Layered Architectures]]
	- [[Service-Oriented Architecture (SOA)]]
	- [[Event-Driven Architecture]] (Publish-Subscribe)
	- [[RESTful Architectures]]
## Tools
- Python ([[client-server]] Implementation)
## Questions and Thoughts
- What advantages do [[Hybrid Architectures]] provide?
- How do publish-subscribe systems handle scalability?
## Relevant Terms from Other Lectures
- [[Load balancing]] (**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch|L2]])
- Messaging Protocols (L7: **[[Terms_L7-CommProtocols_DistrSystems|Overview L7]]** ----- [[Cloud 7 Threads n Comm Models]])

---
# L7 - [[Distributed-Communication]] Protocols for [[Distributed Systems]]
## All L7 Terms
### [[Distributed-Communication]]
- [[Remote Procedure Call (RPC)]]
	- gRPC (Google RPC)
- [[Message-Oriented Middleware]]
    - AMQP
    - [[MQTT]]
- [[MPI]]
- [[ZeroMQ]]
## Tools
- [[Sockets]]
- [[Protocol Buffers]] (ProtoBuf) (used in gRPC)
## Questions and Thoughts
- How does gRPC improve on traditional RPC?
- What are the trade-offs between transient and persistent messaging?
## Relevant Terms from Other Lectures
- Event-Driven Architectures (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])
- [[Coordination]] (L8)

	--- 
# L8 - [[Coordination]]
## All L8 Terms
- [[Clock Synchronization]]
    - [[Cristians Algorithm]]
    - [[Berkeley Algorithm]]
    - [[Network Time Protocol (NTP)]]
- [[Logical Clocks]]
    - [[Lamports Logical Clocks]]
    - [[Vector Clocks]]
- [[Mutual Exclusion]]
    - [[Centralized Mutex Algorithm]]
    - [[Token-based Mutex Algorithm]]
- [[Leader Election]]
    - [[Bully Algorithm]]
    - [[Ring Algorithm]]
## Questions and Thoughts
- How do [[Vector Clocks]] improve upon [[Lamports Logical Clocks]]?
- What are the advantages of decentralized [[Leader Election]] algorithms?
## Relevant Terms from Other Lectures
- Distributed Commit (L10)

---
# L9 - [[Consistency]] and [[Replication]]
## All L9 Terms
- [[Distributed Databases]]
	- [[ACID database]] vs. [[BASE database]] 
- [[CAP Theorem]]
- [[Consistency Models]]
    - [[Eventual Consistency]]
    - [[Sequential consistency]]
- [[Replica Management]]
    - Placement
    - Caching
## Questions and Thoughts
- How do [[Consistency Models]] affect performance in distributed databases?
- What trade-offs exist between strong and eventual consistency?
## Relevant Terms from Other Lectures
- [[Fault Tolerance]] (L10)

---
# L10 - [[Fault Tolerance]]
## All L10 Terms
- Partial Failures
- Resilience by Process Groups
- Failure Detection
- [[Consensus]]
    - Crash Failures
    - [[Byzantine failures]]
- Distributed Commit Protocols
## Questions and Thoughts
- Why is failure detection critical in [[Distributed Systems]]?
- How do [[Byzantine failures]] differ from crash failures in terms of complexity?
## Relevant Terms from Other Lectures
- [[Leader Election]] (L8)
- [[Replication]] (L9)