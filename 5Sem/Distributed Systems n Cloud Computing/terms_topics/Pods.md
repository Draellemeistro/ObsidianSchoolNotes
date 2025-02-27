part of [[Kubernetes Architecture]]
An abstraction layer, so [[Kubernetes]] can focus on deploying and managing Pods without having to care what's inside of them. 

Heterogenous workloads can run side-by-side on the same cluster. **Is the [[Atomic Unit of Scheduling]]**
Scaling up adds more Pods, Down deletes pods. Scaling isn't done by adding containers to existing Pods.
## Anatomy
A shared execution environment for 1 or more containers(Includes network stack, volumes, shared memory). Pod scheduling: All containers in a Pod are scheduled to the same node, pod startup is atomic(the Pod is marked running only when all containers have started.)
## Configuration
**Simplest configuration:** 
1 container per Pod. 
**Multi-container are used in specific cases**: Service Meshes, Helper services(init app envs), Tightly coupled helpers(e.g., log scrapers)

### Multicontainer pods
**Sidecar Container**. 
Sidecar: helper container running alongside the main app container. Ex: service mesh sidecar encrypts traffic, provides telemetry.
#### Multicontainer pod anatomy
Containers share the Pod's IP address. Communicate internally using localhost. When to use: For tightly coupled components(For loosely coupled apps, use single-container Pods and network communication).

## Life cycle
Pods are mortal: created, live, die. When it dies, Kubernetes replaces it with a new Pod (with a new ID and IP,PROBLEM: [[Pod-IP Churn]]). Applications must be designed to handle Pod failures.
## Immutability
You can't change them once they're running. To update, replace old Pod with new one. Fits with moderne tools and GitOps workflows.