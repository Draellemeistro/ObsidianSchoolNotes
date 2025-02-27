## Alternatives for [[Replica-Caching|caching]] and [[Replication]] using [[edge servers]]
- **database copy:** the edge has the same as the origin
- **content-aware cache:** check if a (normal query) can be answered with cached data.
	- Requires that the server knows about which data is cached at the edge.
- **content-blind cache:** Store a query, and its result. WHen the exact same query is issued again, return the result from the cache.
![[image_Replica-Caching.png]]