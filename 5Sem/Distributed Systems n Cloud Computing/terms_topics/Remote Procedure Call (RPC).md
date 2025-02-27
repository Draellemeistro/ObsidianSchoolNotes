Se det her [link](https://dl.acm.org/doi/abs/10.1145/3600006.3613156) om [[EXTRA Cloud-Scale Characterization of RPCs]]
**YO, REMOTE... YOU INVOKE CODE ON OTHER MACHINE AS IF IT WAS A LOCAL FUNCTION**
## Questions and Thoughts
> [!NOTE] The **[[Remote Procedure Call (RPC)|RPC]] Latency Tax/RPC Tax**
> Ongoing advancements in the network stack have exposed the RPC layer itself as a **bottleneck**, that we show accounts for **40–90% of a microservice’s total execution cycles.**

#### How does gRPC improve on traditional RPC?
# General RPC
> [!NOTE] Basic Idea and goal of RPC [billede2 ref](https://docs-multiplayer.unity3d.com/netcode/current/advanced-topics/messaging-system/)
> ![[image_Remote Procedure Call (RPC).png]]
> ![[image_Remote Procedure Call (RPC)-1.png]]
> 
> **Observations:**
> - Application developers are familiar with simple procedure model.
> - Well-engineered procedures operate in isolation (black box)
> - There is no fundamental reason not to execute procedures on separate machines.
> 
> **Conclusion:** 
> [[Distributed-Communication]] between caller & callee can be hidden by using procedure-call mechanism.


## Basic RPC operation![[image_Remote Procedure Call (RPC)-2.png]]
1. Client procedure calls client stub.
2. Stub builds message; calls local OS
3. OS sends message to remote OS
4. Remote OS gives message to stub.
5. Stub unpacks parameters; calls server.
6. Server does local call; returns result to stub
7. Stub builds message; calls OS
8. Os sends message to client's OS
9. Client's OS gives message to stub
10. Client stub unpacks result; returns to client.

## RPC: Parameter Passing
- **There's more than just wrapping parameters into a message**
	- Clients and server machines may have **different data representations**(think of byte ordering)
	- Wrapping a parameter means **transforming a value into a sequence of bytes**
	- Client and server have to **agree on the same encoding:**
		- How are **basic data values** represented (integers, floats, chars)
		- How are **complex data values** represented (arrays, unions)
- **CONCLUSION:** 
	- Client and server need to **properly interpret messages**, transforming them into machine-dependent representations.

## Other types of RPCs
### Asynchronous RPCs
Try to get rid of the strict request-reply behavior, but let the client continue without waiting for an answer from the server.
![[image_Remote Procedure Call (RPC)-3.png]]
### Multicast RPCs
Sending an RPC request to a group of servers
![[image_Remote Procedure Call (RPC)-4.png]]

## [[Google RPC (gRPC)]]
### Overview
Modern open-source high performance RPC framework that can run in any environment.


Idiomatic client libraries in 11 languages. Highly efficient on wire and with a simple service definition framework. Bi-directional streaming with http/2 based transport. Pluggable auth, tracing, load balancing and health checking.
### Main usage scenarios of Google RPC
- Efficiently connecting polyglot services in microservice style architecture. 
- Connecting mobile devices, browser clients to backend services.
- Generating efficient client libraries.
### Core features
- Idiomatic client libraries in 11 languages. 
- Highly efficient on wire and with a simple service definition framework. 
- Bi-directional streaming with http/2 based transport. 
- Pluggable auth, tracing, [[Load balancing]] and health checking.
## sadasdasdasd
The data / messages need to be serialized in a common format (typical examples: XML, JSON) **Google's serialization format:** [[Protocol Buffers]]
### [[Protocol Buffers]] (ProtoBuf)
