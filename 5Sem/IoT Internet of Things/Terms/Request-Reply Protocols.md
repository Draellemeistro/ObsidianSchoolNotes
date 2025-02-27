- **A direct coupling between a sender and a receiver**
	- _NOTE: direct communication does NOT mean one-hop communication_
- In the normal case, request-reply communication is **synchronous** because the client process **blocks** until the reply arrives from the server.
- It can also be reliable because the reply from the server is effectively an ACK to the client.
- **Asynchronous** [[Request-Reply]] communication is an alternative that may be useful in situations where clients can afford to retrieve replies **later.**
![[image_Request-Reply Protocols.png]]
## Examples
- [[REST HTTP]]
- [[CoAP]]