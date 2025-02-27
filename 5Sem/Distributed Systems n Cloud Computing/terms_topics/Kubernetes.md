**An open-source system (and the de-facto standard) for orchestrating container [[Deployments]]. Supports multiple app types([[Containers]], VMs, Wasm apps, etc.). Features include Automatic Deployment, Scaling & [[Load balancing]], Management**

**spin up and manage [[Containers]]**
do  scaling, [[Load balancing]], health checks.
**IS AN [[Orchestrators|ORCHESTRATOR]]**
## [[Kube-state]]
## Packaging apps for K8s
Multiple app types are supported, B**UT THEY MUST ALL BE WRAPPED IN** --[[Pods]]-- to run on [[Kubernetes]].

Write app -> containerize it -> push to registry -> wrap in a Pod(Most commonly the pod is further wrapped in a --Deploymeent-- for added management features like autoscaling and health checks) -> Post the Deployment YAML file to the API server- Kubernetes handles running the app based on the desired state.
## The [[Cloud-OS]]
[[Cloud-native]]
it abstracts differences between cloud platforms, similar to how traditional OSs abstract server resources.
#### Key functions
Resource Abstraction. Enabler for [[Hybrid Cloud]], [[Multi-Cloud]], Cloud Migrations

Kubernetes schedules application microservices regardless of the underlying cloud provider (AWS, Azure, GCP, etc.)

Abstracts away cloud and datacenter complexities, allowing developers to focus on apps without worrying about specific resources (compute nodes, failure zines, storage volumes). Kubernetes optimally manages resources, making development and deployment easier.
- Cluster Management
- Declarative Configuration
- Continuous Deployment
- Blue-Green [[Deployments]]
- Canary [[Deployments]]
## Tools
- Kubectl
- Minikube
## Questions and Thoughts
- How does Kubernetes enable scaling and failover?
- What challenges arise in [[Multi-Cloud]] Kubernetes [[Deployments]]?
### [[Kubernetes Architecture]]

## Why kubernetes
**[[Containers]] might crash/go down and need to be replaced(Container health checks + Automatic re-deployment). We might need more container instances upon traffic spikes(Autoscaling). Incoming traffic should be distributed equally(Load balancer).**





## Relevant Terms from Other Lectures
- [[Containers]] (L1)
- Microservices (**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch|L2]])
- Event-Driven Architectures (**[[Terms_L4-Serverless_Computing|L4Over]]** ----- [[Cloud 4 Serverless|L4]])