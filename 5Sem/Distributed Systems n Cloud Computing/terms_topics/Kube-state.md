[[Kubernetes]] operates on a **declarative model**, built around three principles:

- **Desired State**(what you want),
- **Observed State**(what you have),
- **Reconciliation**: keeping the two states in sync.

Simply, it spins up new [[Pods]] if they die. Example: We have specified in a ReplicaSet, that we want 3 [[Pods]] of the app to run. One crashes, the [[Kube-controllers|controller]] notices this, and schedules one more replica to maintain the three we specified.

