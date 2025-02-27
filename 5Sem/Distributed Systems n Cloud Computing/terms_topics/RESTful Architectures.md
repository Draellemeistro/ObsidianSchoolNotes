View a distributed system as a collection of resources, individually managed by components. Resources may be added, removed, retrieved, and modified by (remote) applications.... (PUT, GET, DELETE, POST)

## Handling Resources
1: Resources are identified through a single naming scheme. 
2: All services offer the same interface. 
3: Messages sent to or form a service are fully self-described. 
4: After executing an operation at a service, that component forgets everything about the caller.

## [[Service-Oriented Architecture (SOA)|SOA]] or RESTful(?????????????) example
Amazon's Simple Storage Service. Objects are placed into buckets (i.e., directorues). Buckets cannot be palced into buckets. Ops on 'ObjectName' in bucker 'BucketName' require identifier. All ops are carried out by sending [[HTTP]] requests.