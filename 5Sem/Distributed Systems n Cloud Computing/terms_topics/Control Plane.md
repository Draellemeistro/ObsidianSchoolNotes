part of [[Kubernetes Architecture]]
# Control Plane Nodes
Also called master noded
**no tasks!** there the swing the whip on the [[Worker Nodes]]
host the control plane services that implement the intelligence of [[Kubernetes]]. They can be physical servers, VMs, cloud instances, and more. Production clusters usually run three or five control plane nodes for high availability

Manages the cluster, runs control plane services like API server, scheduler, controllers. (Core Kubernetes Intelligence: **Manages cluster ops like self-healing, autoscaling, and rolling updates.**)
## [[Kube-scheduler]]

## [[KubeAPI]]

## [[Kube-controllers]]


# Best practices
They focus on cluster management, avoid running user applications here. 
### Simplest setup: 
1 control plane node (suitable for labs/testing). 
### In production: 
**High Availability(HA):** Use 3-5 control plane nodes for resilience, spread across availability zones

Run **3-5 control plane nodes** for HA in production. For large clusters, consider running a dedicated [[ETCD]] cluster for better performance. Ensure that the [[KubeAPI|API Server]] is configured correctly, as it handles all communication within the cluster.
