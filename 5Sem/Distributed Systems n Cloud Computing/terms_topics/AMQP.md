> [!NOTE] Goal of **AMQP**(Advanced Message Queueing Protocol)
> Intended to play the same role as, ex, TCP in networks: a protocol for high-level messaging with different implementations (Because there was a lack of standardization(??))

Client sets up a (stable) connection, which is a container for several (possibly ephemeral) one-way channels. Two one-way channels can form a session. A link is akin to a socket, and maintains state about message transfers.

> [!FAIL] **PARADIGM:** [[Publish-Subscribe]], 
> - **Direct communication between entities is possible.** Different topologies:
> 	- Client-to-Client
> 	- Client-to-Broker
> 	- Broker-to-Broker
> - Runs over TCP and provides different [[QoS levels]]
> - More features than [[MQTT]] (therefore)
> 	- heavier, more power, processing, and memory demands
> - Preferred for communication in devices that are not constrained
> - [[transport-layer security (TLS)]] for security

![[image_AMQP.png]]
## INFO
Advanced Message-Queuing Protocol Intended to play the same role as, ex, TCP in networks: a protocol for high-level messaging with different implementations.
#### Basic Model
![[image_Communication-4.png]]
Client sets up a (stable) **connection**, which is a container for several (possibly ephemeral) **one-way channels**. Two one-way channels can form a **session**. A **link** is akin to a socket, and maintains state about message transfers.