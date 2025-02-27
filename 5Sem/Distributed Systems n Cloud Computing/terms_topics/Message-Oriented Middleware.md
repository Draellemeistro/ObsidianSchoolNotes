Asynchronous persistent communication through support of middleware-level queues. Queues correspond to buffers at communication servers.
- [[AMQP]]
- [[MQTT]]
> [!NOTE] Message-oriented Middleware
> **Essence:** Asynchronous persistent communication through support of middleware-level queues. Queues correspond to buffers at communication servers.
# Middleware-level Queues
- [[AMQP]], [[MQTT]]
> [!NOTE] Middleware-level Queue Operations
> PUT, GET, POLL, NOTIFY

**Queue OP: PUT**
Append a message to a specified queue.
**Queue OP: GET**
Block until the specified queue is nonempty, and remove the first message.
**Queue OP: POLL**
a specified queue for messages, and remove the first. Never block
**Queue OP: NOTIFY**
Install a handler to be called when a message is put into the specified queue.
### Message Broker
Broker handles application heterogeneity in an MQ system: Transforms incoming messages to target format. Very often acts as an application gateway. May provide subject-based routing capabilities (i.e., pub-sub...)



[Communication](app://obsidian.md/Communication)
- [Remote Procedure Call (RPC)](app://obsidian.md/Remote%20Procedure%20Call%20(RPC))
    - Basic RPC Operation
    - Parameter Parsing
    - Variations of RPC, Google RPC(gRPC)
- Message-Oriented [Communication](app://obsidian.md/Communication)
    - [Message-Oriented Middleware](app://obsidian.md/Message-Oriented%20Middleware)
    - Simple transient messaging with [[Sockets]]
    - Advanced transient messaging
    - message-oriented persistent [communication](app://obsidian.md/communication)
    - Advanced Message Queueing Protocol (AMQP)
    - Extra: [[MQTT]]

