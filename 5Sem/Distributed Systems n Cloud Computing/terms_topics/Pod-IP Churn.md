**Pods are mortal: created, live, die. When it dies, Kubernetes replaces it with a new Pod**  Applications must be designed to handle Pod failures.

A new [[Pods|Pod]] will have a new ID and IP. Pods are dynamic: pod deaths, rollouts, scaling up and down. Because of this, clients can't reliably connect to individual pods as their IPs change frequently. (Solution: --[[Services]]--)

