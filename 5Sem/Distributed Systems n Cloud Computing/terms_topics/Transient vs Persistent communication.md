> [!NOTE] **Types of Communication**
> - **Transient Communication:** Comm. server discards messages when it cannot be delivered at the next server, or at the receiver.
> - **Persistent Communication:** A message is stored at a communication server as long as it takes to deliver.
> - [[Transient vs Persistent communication]]



### **3. Transient Messaging vs Durable(Persistent) Messaging**

| Feature             | Transient Messaging                            | Persistent Messaging                              |
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |
| **Message Storage** | Messages stored temporarily (e.g., in memory). | Messages persist until delivered (e.g., on disk). |
| **Reliability**     | Messages may be lost if failures occur.        | Guarantees delivery even in case of failures.     |
| **Performance**     | Faster due to reduced I/O overhead.            | Slightly slower due to disk operations.           |
| **Use Case**        | Suitable for low-priority, ephemeral messages. | Critical messages requiring reliable delivery.    |
| **Examples**        | Stock price updates, sensor data streams.      | Order confirmations, payment transactions.        |
