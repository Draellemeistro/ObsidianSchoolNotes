# Basic Overview stuff
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

> [!NOTE] **Types of Communication**
> - **Transient Communication:** Comm. server discards messages when it cannot be delivered at the next server, or at the receiver.
> - **Persistent Communication:** A message is stored at a communication server as long as it takes to deliver.
> - [[Transient vs Persistent communication]]

![[image_Communication-1.png]]


# SDASDASDSADA
## asdasdasdasd
### Basic [[Remote Procedure Call (RPC)|RPC]] Idea
> [!NOTE]  [[Remote Procedure Call (RPC)|RPC]] Philosophy [billede2 ref](https://docs-multiplayer.unity3d.com/netcode/current/advanced-topics/messaging-system/)
> **Observations:**
> - Application developers are familiar with simple procedure model.
> - Well-engineered procedures operate in isolation (black box)
> - There is no fundamental reason not to execute procedures on separate machines.
> 
> **Conclusion:** Communication between caller & callee can be hidden by using procedure-call mechanism.


# [[Message-Oriented Communication]]
## Transient Messaging
### [[Sockets]]
[[Sockets]] are rather low level and programming mistakes are easily made. However, the way that they are used is often the same (such as in client-server setting).
### [[ZeroMQ]]
Provides a highler level of expression by pairing [[Sockets]]: one for sending messages at process P and a corresponding one at process Q for receiving messages. All communication is Asynchronous

## Message-Oriented Persistent communication
### Queue-based messaging
![[image_Communication-2.png]]

#### [[Message-Oriented Middleware]]

> [!NOTE] [[Message-Oriented Middleware]]
> **Essence:** Asynchronous persistent communication through support of middleware-level queues. Queues correspond to buffers at communication servers.

| Operation | Description                                                                    |
| --------- | ------------------------------------------------------------------------------ |
| PUT       | Append a message to a specified queue.                                         |
| GET       | Block until the specified queue is nonempty, and remove the first message.     |
| POLL      | Check a specified queue for messages, and remove the first. Never block        |
| NOTIFY    | Install a handler to be called when a message is put into the specified queue. |
![[image_Communication-3.png]]

##### Message Broker
Message queuing systems assume a **common messaging protocol**: all applications agree on message format (i.e., structure and data representation)
**Broker handles application heterogeneity in an MQ system:**
- Transforms incoming messages to target format
- Very often acts as an **application gateway**
- may provide **subject-based** routing capabilities (i.e., **publish-subscribe** capabilities)
### [[AMQP]]
> [!NOTE] Goal of **AMQP**(Advanced Message Queueing Protocol)
> Intended to play the same role as, ex, TCP in networks: a protocol for high-level messaging with different implementations (Because there was a lack of standardization(??))

Client sets up a (stable) connection, which is a container for several (possibly ephemeral) one-way channels. Two one-way channels can form a session. A link is akin to a socket, and maintains state about message transfers.

### [[MQTT]]
Lightweight. Used in IoT devices. Protocol of choice for pub-sub patterns![[image_Communication-5.png]]

# Extra shit
