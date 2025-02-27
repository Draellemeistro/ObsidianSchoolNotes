**from [[Publish-Subscribe]]**
See also [[Publish-Subscribe Architectures]]

- **Indirect communication - no direct coupling** between the sender and the receiver(s)
- De-facto present in real-life [[IoT]] applications: Adopted by major cloud providers
	- [[AWS IoT-Greengrass]], [[Microsoft Azure IoT]]
- **PROTOCOL EXAMPLES:**
	- [[MQTT]]
	- [[AMQP]]
	- [[DDS]]

## Idea
A large number of **publishers** (producers) **PUBLISH** structured events to an **event service** and a large number of **subscribers** (consumers) **EXPRESS INTEREST** in particular events through subscriptions which can be arbitrary patterns over the structured events.
#### (Distributed event-based systems)
disseminating events to multiple recipients with the sender unaware of the identity of the recipients. Typically, senders and receivers communicate through an intermediary (i.e., [[broker]])
