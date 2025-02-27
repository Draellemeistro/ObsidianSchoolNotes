part of [[Kubernetes Architecture]]
Adds stable networking for dynamic pod groups, to maintain a reliable DNS name, IP address, and port. Also [[Load balancing|Load balances]] traffic to healthy [[Pods]] behind the service.

**Frontend**: has a DNS name, IP address and port. **Backend**: Uses labels to distribute traffic across a dynamic set of Pods.

## Main Role
Provide stable networking for dynamic pod groups and reliability. Maintains a list of healthy pods during scaling, rollouts, failures to guarantee that the name, IP, and port on the frontend will never change(Reliability)