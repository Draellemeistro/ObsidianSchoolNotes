# Directly Mentioned
![[image_as-a-Service Models.png]]
![[Comparison_of_on-premise,_IaaS,_PaaS,_and_SaaS.png]]
## [[IaaS]] (Infrastructure)
- Provides clients with computational, networking and storage resources
- Client no need to invest in hardware
- Client can scale the infrastructure on demand based on workload
## [[PaaS]] (Platform)
- **main difference with [[IaaS]]:**
	- Client has no control over OS and networking
- Cloud-based environment for building and delivering web-based and mobile apps.
- Deploy apps and get to market faster
- Only minutes to deploy app on cloud
## [[SaaS]] (Software)
- **Main difference with [[PaaS]]:**
	- Client just an app user
	- No control over application development and deployment
- Apps and data accessible from any internet-enabled device
- No data is lost if device breaks, since data is on the cloud
# May be interesting
## [[FaaS]] (Function)
**develop, run, and manage application functionalities without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app.**

allows customers to run code in response to events, without managing the complex infrastructure typically associated with building and launching microservices applications. [[AWS Lambda]], Google Cloud Functions, Azure Functions, IBM/Apache's OpenWhisk and Oracle Cloud Fn

> [!NOTE] FaaS (Function-as-a-Service)
> an emerging cloud computing paradigm that disaggregates a large monolithic application into many small standalone components called functions. Each function typically has a single, independent functionality, separate from the others. To perform the task of the original monolithic application, these functions collaborate and communicate with each other over the network. Consequently, functions are usually implemented as web services that can be invoked through various means, such as HTTP requests, WebSockets, or remote procedure calls


### FaaS vs PaaS
**PaaS** application hosting services is similar to FaaS in that they also hide "servers" from developers. However, such hosting services typically always have at least one server process running that receives external requests. Scaling is achieved by booting up more server processes, which the developer is typically charged directly for. Consequently, scalability remains visible to the developer.

By contrast, **FaaS** does not require any server process constantly being run. While an initial request may take longer to be handled than an application hosting platform (up to several seconds), caching may enable subsequent requests to be handled within milliseconds. As developers only pay for function execution time (and no process idle time), lower costs at higher scalability can be achieved (at the cost of latency).

