
> [!NOTE] IN A NUTSHELL
> "*,**Monoliths** and **microservices** are not a simple binary choice. Both are fuzzy definitions that mean many systems would lie in a blurred boundary are among the two*" - **Martin Fowler**
> 
> ![[image_Monolithic vs Microservices.png]]

## [[Monolithic Architecture]]
#COMEBACK
## [[Microservice-based Architecture]]
- **its strength can also be a vulnerability**
	- Can have lots of overhead because its now also about networking.
	- Perspective, weighing needs
- Remove complex from source code onto architecture
	- From understanding code to managing architecture

[[decomposing applications into services]]
# Cases
## Amazon: Distributed [[Microservice-based Architecture]] to [[Monolithic Architecture]]
- Less expensive
- better scaling
- better resilience
Before, they encountered scaling bottlenecks ([[Orchestrators|orchestration]] management) and it was expensive (workflow & data management)

Storing data in bucket, moving cloud data around is networking -> temporary data storage.
### After / Conclusion
- Components into single process
	- To keep data transfer in process memory
- **Went vertical instead of horizontal**

## Real-time video streaming
#TODO 