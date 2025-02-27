part of [[Kubernetes Architecture]]
Wraps [[Pods]] in higher-level controllers. Used for stateless apps. Offer featues such as: self-healing, scaling, rolling updates, versioned rollbacks.

## [[Kube-controllers|Deployment Controllers]]
Run on the [[Control Plane]], Continuously reconciling observed and desired state.