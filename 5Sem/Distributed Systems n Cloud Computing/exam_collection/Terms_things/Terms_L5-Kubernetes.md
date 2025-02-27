# Some Shit
ssssss


# Exam Questions
## Architecture, components, orchestration
- What is Kubernetes; 
- Kubernetes Architecture and Components: Control plane, Worker nodes, Pods, Deployments, Services; 
- Hands-on examples; 
- Kubernetes on the cloud
### 1. What is Kubernetes and why is it important?

### 2. What is the fundamental unit of deployment in Kubernetes?
the pod, it wraps around the container(s), and is the mechanic for interfacing with the containers, from the cluster. Want to scale? adjust the number of pods relating to service 
### 3. How does Kubernetes handle application scaling?
Replicasets. Services work as an API gateway to the deployment and its pods.  This allows pods to be spun up and brought down, while kubernetes takes care of IP and routing.
### 4. How does Kubernetes ensure high availability and self-healing?
Monitors pod stderror (?) if it crashes, it spins up a new one. This also applies to when updating pods, allowing for rolling updates while maintaining availability.
### 5. What is container orchestration?
#COMEBACK 
### 6. What does it mean that Kubernetes is "cloud-native"?
#COMEBACK 
### 7. Why do we often use Deployments instead of just Pods?
#COMEBACK 
### 8. Why is Kubernetes considered an "operating system for the cloud"?
#COMEBACK 
### 9. How does the Kubernetes control plane maintain the desired state of the cluster?
#COMEBACK 
### 10. What is etcd and why is it critical to Kubernetes?

### 11. How does the scheduler decide where to run a new Pod?

### 12. What is the difference between a Pod and a multi-container Pod?

### 13. Why are Pods considered ephemeral and immutable?

### 14. What problem does a Service solve in a dynamic Kubernetes environment?
The issue of ip churn with pods, and generally just routing and networking the pods correctly. They're constantly being spun up and taken down based on demand etc, so there needs to be some abstraction and automation of how to access them.
### 15. How do Deployments manage updates and rollbacks of applications?

### 16. What is the role of kubelet and kube-proxy on worker nodes?

### 17. Why might you choose a managed Kubernetes service like GKE, EKS, or AKS over a self-hosted cluster?