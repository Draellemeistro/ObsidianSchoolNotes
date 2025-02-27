
## [[CLoud 1 introductions]]
#### Deployment Models
- **Public:**
- **Private:**
- **Hybrid:**
- **Multi/community:**
#### as a Service
- **IaaS:** (infrastructure)
- **PaaS:** (platform)
- **SaaS:** (software)
#### Hypervisor
- **type 1:** (bare-metal)
- **type 2:** (Hosted)
#### Virtualization
- **full virtualization**
- **para-virtualization**
- **HW-assisted virtualization**
- **OS-lvl virtualization**
##### Virtual Machines
##### Containers
###### Kata Containers
## [[Cloud 2 Monolithic and microservice Arch]]
#### Monolithic
#### Microservices

#### Micro vs Mono
#### Service Decomposition
##### Decomposing Monolith to Microservices
## [[Cloud 3 Cloud Computing Services]]

### [[Cloud 3 Extra stuff]]

## [[Cloud 4 Serverless]]
#### Serverless Computing
#### Event-driven Architecture
##### AWS Lambda
##### Statelesss Functions
###### Function triggers

## [[Cloud 5 Kubernetes]]
#### Kubernetes Architecture
##### Control Plane
- Kube API server
- Cloud control manager
- Scheduler
- controllers & controller managers
- cluster store (ETCD)
##### Worker node
- Kubelet
- Runtime
- Kube-proxy
- pods (and containers)
##### Structure tings
###### Pods
- Pod IP-churn (leads to services)
###### Deployments
###### Services
## [[Cloud 6 Intro to Distributed Systems]]
#### System topologies
- Centralized
- Decentralized
- Distributed
#### Distributed Architectures
##### Client-Server Architecture
Traditional, centralized model; different components can be physically distributed across machines but maintain a client-server relationship.
##### Peer-to-Peer P2P
- Structured
- unstructered 
	- **searching in unstructured:** flooding, random walk
##### Hybrid Architectures
###### Cloud Computing
###### Edge Computing
##### Blockchain Architecture
#### Architectural Styles
##### Layered Architectures
##### Service-Oriented Architecture (SOA)
##### Event-Driven Architecture
###### Publish-Subscribe Arch
###### RESTful Architecture
## [[Cloud 7 Threads n Comm Models]]
#### Threads & Processes
##### Threads
##### Processes
##### Context-Switching
#### Communication
##### Remote Procedure Call (RPC)
###### Parameter Parsing
###### gRPC
###### Protobuff (gRPC)
##### Message-Oriented Communication #COMEBACK 
###### Message-oriented middleware
##### Transient messaging with sockets
##### Persistent message-oriented
##### AMQP
##### ZeroMQ
##### MQTT
## [[Cloud 8 Coordination]]
#### Distributed Sync
#### Clock Sync
##### Regular Clocks
###### Cristians Algorithm
request based.... CENTRALIZED. external sync. time server s uses RTT (small RTT best)
###### Berkeley Algorithm
Broadcast based.... CENTRALIZED. internal. master-slave. server main driver (contrary to cristian)
###### Network Time Protocol (NTP)
DISTRIBUTED
##### Logical clocks
###### Lamports Scalar-based Logical Clocks
###### Vector Clocks
#### Mutual Exclusion
##### Centralized Mutex Algorithm
##### Token-based Mutex algorithm
#### Leader Election
###### Bully Algorithm
##### Ring
##### RAFT

## [[Cloud 9 Consistency n Replication]]
#### Distributed Databases
##### ACID
##### BASE
#### CAP Theorem
Choose max 2:
- **[Consistency](app://obsidian.md/Consistency):** Every read returns data from most recent write.
- **Availability:** Every request executes & receives a (non-error) response
- **Partition-tolerance:** System continues to function when network partitions occur (messages dropped or delayed)
#### Consistency Models
##### Sequential Consistency
##### Causal Consistency
##### Entry Consistency
##### Eventual Consistency
#### Consistency Protocols
##### [[Sequential consistency|sequentially consistent]]
###### [[Primary-based protocols]]
###### [[Replicated-write protocols]]
##### ?????
###### [[Cache-coherence protocols]]
###### [[remote-write protocols]]
## [[Cloud 10 Fault Tolerance]]
#### Failure Terminology
##### Dependability
##### Partial Failures
##### Halting Failures
##### Arbitrary Failures
###### Byzantine Failures
#### Failure Masking
##### Redundancy
###### Information-redundancy
###### Time-redundancy
###### Physical Redundancy
##### Process groups and process resilience
#### Failure Detection
##### 1 & 2 phase commit
#### Consensus Mechanisms
##### [[Flood-based consensus algorithm]]
##### k-fault tolerance and degree of fault tolerance
- **halting failures:** k+1 (no member produce incorrect result)
- **arbitrary failures:** 2k+1
- **byzantine failures:** 3k+1

