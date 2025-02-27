# Some Shit
ssssss


# Exam Questions
## RPC, RMI, gRPC, Message-oriented (AMQP, [[MQTT]],...), MPI

### 1. What is the benefit of using [[Threads]] instead of processes in a distributed system?
Context-switching, since they share memory. It can allow for more performant context-switching... with the caveat of possibly screwing everything op if handled incorrectly (they could corrupt the entire process' memory...)
### 2. Why might a server be designed as a multithreaded application rather than a single-threaded one?
Simple, but lets refresh it
### 3. What problem does Remote Procedure Call (RPC) aim to solve? How does gRPC differ from a traditional RPC approach?
I think it has to do both with providing a unified framework / contract for how communication should be done between services..(services???) And also, at least for gRPC achieving more lightweight communication. done by using protocol buffers to serialize the data being send (and thereby making it smaller... somehow)
### 4. What are the key differences between transient and persistent message-oriented [[Distributed-Communication]]?
transient.. oh i couldn't deliver it? aiight, bye-bye!
persistent, the comm server keeps the message until it can deliver... y'know the persistent mailman!
### 5. How do publish-subscribe systems work in distributed [[Distributed-Communication]]?
Think of an RRS feed. Say you want a service to modify or do computations on some sensor readings coming from some thing (or maybe a collection of things).... well, just subscribe to that specific newsletter, and you can (event-based????) enjoy the content every time something is posted.
### 6. Why are asynchronous message-oriented models often preferred in large distributed systems?
Not as strict constraints, easier to develop for most likely. I mean, if they have to communicate synchronously, then both machines have to be on and connected. Seams quite a hassle if messages are not critically urgent. why not just send it off and let bruv handle it, when he has the time for it?
### 7. What is the main advantage of using a standardized messaging protocol like [[AMQP]] or [[MQTT]]?

### 8. How do [[Threads]] help hide network latency in distributed clients and servers? 
instead of iteration through a list (set list, we know, we'll need to do x things), why not just start banging out the next one without waiting for an answer? This applies to both server and client

### 9. How can shared memory between [[Threads]] lead to potential errors, and what approach might help prevent these issues?
oooohhhh... race conditions... not nice. think of the iterating number example.
thread a reads x=1
thread b reads x=1
thread a writes x=x+2
thread b writes x=x+1
what is x????? its fucked, i tell you.
### 10. Why is a message broker beneficial in a [[Message-Oriented Middleware]] system?

