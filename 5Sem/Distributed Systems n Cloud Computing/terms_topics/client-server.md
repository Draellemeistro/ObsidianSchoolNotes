# Client-Server Architecture
#COMEBACK 
Traditional, centralized model; different components can be physically distributed across machines but maintain a client-server relationship. Clients send requests, Servers process them and return results.
## [[servers]]
#### Basic model
A process implementing a specific service on behalf of a collection of clients. It waits for an incoming request from a client and subsequently ensures that the request is taken care of, after which it waits for the next incoming request
### Two basic Types
##### Iterative Server:
- Server handles the request before attending a next request
##### Concurrent Server:
- Uses a **dispatcher**, which picks up an incoming request that is the passed on to a separate [[Threads]] / [[Process]].

> [!NOTE] **Observation:** Concurrent servers are the norm: They can easily handle multiple requests, notably in the presence of blocking operations (to disks or other servers)

### Stateless Servers
- Never keep **accurate** information about the status of a client after having handled a request:
### Stateful Servers
- Keeps track of the status of its clients:
> [!NOTE] **OBSERVATION:** The **performance of stateful servers can be extremely high**, provided clients are allowed to keep local copies. As it turn out, **reliability is often not a major problem.**

