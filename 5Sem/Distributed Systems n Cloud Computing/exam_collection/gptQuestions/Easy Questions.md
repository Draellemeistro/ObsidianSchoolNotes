# 1
## What are the three primary cloud [[as-a-Service Models|service models]]?
Platform as a Service, Infrastructure as a Service, and ???????????
PaaS, IaaS, software?
## Define [[Virtualization]] in the context of cloud computing.

## What is a public cloud?
The overall data center is shared amongst many users. Individual virtual environments are still exclusive to the intended users, but the instances run on shared hardware with other [[Virtual Machines]] and containers for other users
# 2
## What is a monolithic architecture?
Its a monolith (think of the word, MONO-lith) the applications services and functions are all consolidated in one place. 

Can run into problems of sprawling code and spaghetti
## Define a microservices architecture.
Contrary to the monolithic setup, microservices splits the applications services / functions apart, so it becomes a collection of multiple services. It simplifies the corresponding codebases of each of these services, since they can be understood in isolation, and adjusted without the chance that some sneaky snippet of code in another part is the glue that holds it together.
**The main philosphy is:** Move complexity from the source code onto to architecture / infrastructure. Individual functions/ services are simplified, with the trade-off of adding networking to the mix.
## What is auto-scaling?
The simplest example is a 

A real world example could be painted with the self-order stands in McDonalds. If every single one is in use and a new user steps into the restaurant, then a new stand pops up. Once all those people are done, and only a couple are being used, then the free ones pops back down.
# 3
## Name three categories of AWS services.
## What is the role of compute services in cloud platforms?
## Define [[Serverless Computing]].
It ain't without a server, thats for sure. It's more Managed, than serverless. [[Serverless Computing]] removes the task of managing the server, and all that it entails (CPU, memory, etc.), by handing that responsibility over to the cloud providers.

This can allow developers to focus on the service they're trying to create, and less on the logistics of managing the required architecture and 
# 4
## What triggers can invoke an AWS Lambda function?
## Define event-driven architectures.
## What does “stateless” mean in serverless functions?
# 5
## What is Kubernetes?
## Define the term “Pod” in Kubernetes.
Container wraps around the application, pod wraps around that (possibly multiple containers) in order to make everything adhere to and work with the way kubernetes clusters are setup.

## What is the role of the kubelet?
# 6
## Define a distributed system.
## What is the difference between a client-server and a peer-to-peer architecture?
## Name one example of a hybrid architecture.
# 7
## What is a Remote Procedure Call (RPC)?
## Define gRPC.
## What is the role of a message broker?
# 8
## What is the purpose of clock synchronization?
## Define [[Lamports Logical Clocks]].
## What is the bully algorithm used for?
# 9
## What does ACID stand for?
## Define eventual consistency.
## What is the CAP theorem?
# 10
## What is fault tolerance?
## Define Byzantine failures.
## What is a distributed commit protocol?