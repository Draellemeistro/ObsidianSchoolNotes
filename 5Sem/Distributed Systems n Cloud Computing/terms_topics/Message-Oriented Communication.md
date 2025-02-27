Great! it can allow us to loosely couple subsystems. messages consumed by subscribers. 
(**Think:** we need [[Microservice-based Architecture|Microservices]] to talk)
# Transient Messaging
> [!NOTE] **Transient Messaging:** Comm. server discards messages when it cannot be delivered
### [[Sockets]]
[[Sockets]] are rather low level and programming mistakes are easily made. However, the way that they are used is often the same (such as in client-server setting).
### [[ZeroMQ]]
Provides a highler level of expression by pairing [[Sockets]]: one for sending messages at process P and a corresponding one at process Q for receiving messages. All communication is Asynchronous

# Persistent communication
> [!NOTE] **Persistent Communication:** A message is stored at a communication server as long as it takes to deliver.

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
