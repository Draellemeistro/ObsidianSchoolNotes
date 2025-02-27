

> [!NOTE] Definition
> **Serverless computing means you don't need to manage the infrastructure (like servers) explicitly**. Focus on building apps and services without thinking about the servers and software needed to run 
> 
> Instead, you focus only on writing and deploying code, while the cloud provider takes care of provisioning, scaling, and maintaining the servers.

### Key Benefits:
- **No server management**: The cloud provider handles it.
- **Scalability**: Automatically scales up or down depending on the demand.
- **Cost-efficient**: You only pay for what you use (e.g., function execution time).

**_ideal for short-lived tasks but not long-running processes._**
# Examples / Cases
## AWS Lambda
**_Serverless, event-driven_**
- Lambda takes care of server (Amazon does the admin shit)
	- They determine CPU etc for functions
	- Can be envoked by events & HTTPS API
- **Scale out, not up**
- **Cost = \# of calls $\times$ runtime** 

- [[Amazon X-ray]]
### The Code
- Runs you code (the lambda function)
	- **Can be envoke in 3 ways:**
		- Synchronous
		- Async
		- Polling
#### Code contains:
- Handler that will receive
- AIM (roles that can run function)
- Compute resources we want
- Delivery timeout
### Execution environment
**Three phases:**
1. init
2. invoke
3. shutdown

### IAM Resource Policy
#### Permissions
You must specify three settings:
1. memory
2. timeout
3. concurrency
**Adjust settings to optimize cost**