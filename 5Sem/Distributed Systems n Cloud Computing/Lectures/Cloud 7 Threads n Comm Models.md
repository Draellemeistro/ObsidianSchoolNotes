

> [!NOTE] Overview
> - Processes
> 	- [[Threads]]
> 	- Servers
> - [[Distributed-Communication]]
> 	- [[Remote Procedure Call (RPC)]]
> 		- Basic RPC Operation
> 		- Parameter Parsing
> 		- Variations of RPC, Google RPC(gRPC)
> 	- Message-Oriented [[Distributed-Communication]]
> 		- [[Message-Oriented Middleware]]
> 		- Simple transient messaging with [[Sockets]]
> 		- Advanced transient messaging
> 		- message-oriented persistent [[Distributed-Communication]]
> 		- [[AMQP|Advanced Message Queueing Protocol (AMQP)]]
> 		- Extra: [[MQTT]]

> [!NOTE] **[[ZeroMQ]]:** Goal
> Provides a highler level of expression by pairing [[Sockets]]: one for sending messages at process P and a corresponding one at process Q for receiving messages. All communication is Asynchronous

## [[Threads]]

## [[Distributed-Communication]] Models

# Overview
## **[[Terms_L7-CommProtocols_DistrSystems|Overview L7]]** ----- [[Cloud 7 Threads n Comm Models]]
## All L7 Terms
- RPC (Remote Procedure Call)
- gRPC (Google RPC)
- [[Message-Oriented Middleware]]
    - [[AMQP]]
    - [[MQTT]]
- MPI
- [[ZeroMQ]]
## Tools
- [[Sockets]]
- [[Protocol Buffers]] (ProtoBuf)
## Questions and Thoughts
- How does gRPC improve on traditional RPC?
- What are the trade-offs between transient and persistent messaging?
## Relevant Terms from Other Lectures
- Event-Driven Architectures (L4: **[[Terms_L4-Serverless_Computing|Overview L4]]** ----- [[Cloud 4 Serverless]])
- Coordination (L8: **[[Terms_L8-Coordination|Overview L8]]** ----- [[Cloud 8 Coordination]])
