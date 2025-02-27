- In VMMs the atomic unit of scheduling is the VM, 
- Docker: the container, 
- Kubernetes: the [[Pods]](which wraps around VMs, containers etc.).

# Pods
Scaling up adds more Pods, Down deletes pods. Scaling isn't done by adding containers to existing Pods.