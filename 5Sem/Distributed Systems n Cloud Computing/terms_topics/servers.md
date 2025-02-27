
> [!NOTE] **Servers:** Basic Model
> A process implementing a specific service on behalf of a collection of clients. It waits for an incoming request from a client and subsequently ensures that the request is taken care of, after which it waits for the next incoming request.
> 



> [!NOTE] **Servers: Two basic Types**
> - **Iterative Server:** Server handles the request before attending a next request
> - **Concurrent Server:** Uses a **dispatcher**, which picks up an incoming request that is the passed on to a separate [[Threads|thread/process]].
> 
> **Observation:** Concurrent servers are the norm: They can easily handle multiple requests, notably in the presence of blocking operations (to disks or other servers)

# Stateless Servers
Never keep **accurate** information about the status of a client after having handled a request:
- Don't record whether a file has been opened (simply close it again after access)
- Don't promise to invalidate the client's cache
- Don't Keep track of your clients.

**Consequences:**
- Clients and servers are **completely independent**.
- **State inconsistencies** due to client or server crashes **are reduced**.
- Possible **loss of performance** because, e.g., a server cannot anticipate client behavior (think of prefetching file blocks.)

#TODO Does connection-oriented [[Distributed-Communication]] fit into a stateless design?

# Stateful Servers
Keeps track of the status of its clients:
- Record that a file has been opened, so that prefetching can be done.
- Knows which data a client has cached, and allows clients to keep local copies of shared data.

> [!NOTE] **Observation:** Stateful Servers
> The **performance of stateful servers can be extremely high**, provided clients are allowed to keep local copies. As it turn out, **reliability is often not a major problem.**


# [[Threads|Multithreaded]] servers
- **Improve performance**
	- Starting a thread is cheaper than starting a new process. Having a single-threaded server prohibits simple scale-up to a **multiprocessor system**. As with clients: **hide network latency** by reacting to next request while previous one is being replied.
- **Better structure**
	- Most servers have high I/O demands. Using simple, **well-understood blocking calls** simplifies the structure. Multithreaded programs ted to be **smaller and easier to understand** due to **simplified flow of control**.