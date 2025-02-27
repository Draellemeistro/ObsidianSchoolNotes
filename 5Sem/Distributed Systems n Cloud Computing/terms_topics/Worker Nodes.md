part of [[Kubernetes Architecture]]
**Runs user apps... does the leg-work** Runs user applications(can be physical, VMs, or cloud instances)

Worker nodes handle task execution and network traffic, with the [[Kubelet]] managing communication with the [[KubeAPI|API server]], [[Runtime|Runtimes]] executing tasks, and [[kube-proxy]] balancing network traffic. As [[Kubernetes]] evolves, different runtimes may be used depending on the use case.
### [[Kubelet]]
Main [[Kubernetes]] agent on the [[Worker Nodes]]. Watches the [[KubeAPI|API server]] for new tasks; instructs the runtime to execute tasks; reports task status to the  [[KubeAPI|API server]]. If a task fails, the kubelet informs the [[KubeAPI|API server]], allowing the [[Control Plane]] to decide corrective actions.