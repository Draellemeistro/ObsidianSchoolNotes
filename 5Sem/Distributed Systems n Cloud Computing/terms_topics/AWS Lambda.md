> [!NOTE] [[Serverless Computing|Serverless]] AND [[Event-Driven Architecture|Event-Driven]] ... **cost = \# calls * runtime**


> [!NOTE] **ELI5:** [[AWS Lambda]]
> ssssssssssssssssssssssssssssssssssssssss #TODO
> 
> **Corresponding services from other providers:**
> Google Cloud Functions, Azure Functions, IBM/Apache's OpenWhisk and Oracle Cloud Fn

#TODO see this [link](https://www.usenix.org/conference/atc23/presentation/brooker) 

# How **[[Serverless Computing|Serverless]]** and **[[Event-Driven Architecture|Event-Driven]]** Work Together
AWS Lambda combines both ideas:
1. **Serverless**: You don’t manage the underlying [[servers]]; AWS provisions resources dynamically for you.
2. **Event-driven**: Lambda is triggered only when a specific event occurs, so you're only paying for execution time during those events.

This combination is powerful for creating highly scalable, cost-efficient, and loosely coupled systems.
## [[Serverless Computing|Serverless]]
When you deploy a function in [[AWS Lambda]], you don’t need to worry about setting up or maintaining a server. AWS manages everything. You only pay for the actual time your code runs, rather than for a continuously running server.
## Event-Driven
Lambda functions are inherently event-driven. For instance:
- If a file is uploaded to an S3 bucket, an event is generated, and Lambda can execute code in response.
- If there’s an HTTP request to an API Gateway, Lambda can run code to process it.


## **_Serverless, event-driven_**
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
- [[Lambda-AIM]] (roles that can run function)
- Compute resources we want
- Delivery timeout
### [[Lambda-Execution environment]]
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