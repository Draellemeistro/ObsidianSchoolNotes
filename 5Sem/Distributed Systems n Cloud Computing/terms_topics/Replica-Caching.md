## Example: caching and [[Replication]] in the web
###### **Client-side caches**
- In the browser
- at a client's site, notably through a **web proxy.**
##### **Caches at ISPs**
Internet Service Providers also place caches to:
1. Reduce cross-ISP traffic and
2. Improve client-side performance
**may get nasty when a request needs to pass many ISPs**

### Web-cache [[Consistency]]
#### How to guarantee freshness?
To prevent that state information is returned to a client:
- **option 1:** Let the cache contact the original server to see if content is still up to date.
- **option 2:** Assign an expiration time $T_{\text{expire}}$ that depends on how long ago the document was last modified when it is cached. If $T_{\text{last modified}}$ is the last modification time of a document (as recorded by its owner), and $T_{\text{cached}}$ is the time it was cached, then:
	- $T_{\text{expire}}=\alpha(T_{\text{cached}}-T_{\text{last}})+T_{\text{cached}}$ 
	- with $\alpha=0.2$ until $T_{\text{expire}}$, the document is considered valid

## Alternatives for [[Replica-Caching|caching]] and [[Replication]] using [[edge servers]]
- **database copy:** the edge has the same as the origin
- **content-aware cache:** check if a (normal query) can be answered with cached data.
	- Requires that the server knows about which data is cached at the edge.
- **content-blind cache:** Store a query, and its result. WHen the exact same query is issued again, return the result from the cache.
![[image_Replica-Caching.png]]