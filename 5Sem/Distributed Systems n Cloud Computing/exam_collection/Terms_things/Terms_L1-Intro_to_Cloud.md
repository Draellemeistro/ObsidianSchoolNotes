# 1222

# ExamShit
## sdasasd

> [!NOTE] grey
> IaaS, PaaS, Private/Public/Hybrid/Multi Cloud; [[Virtualization]], [[Virtual Machines]], Containers

### 1. What are the main differences between a [[Type-1-hypervisor|type 1]] and [[Type-2-Hypervisor|type 2]] [[Hypervisor]]?
**Type 1** Runs directly on the hosts hardware to control the hardware and to manage guest OSs.

**Type 2** Runs on a conventional OS just as other computer programs do, and the guest OS runs as a process. 

**Type 2 hypervisors abstract guest OSs from the host OS**
### 2. Why is [[Virtualization]] considered key to cloud computing?
Well, it is rather essential, for all the ways  we use the cloud. A bunch of machines, with more "machines" running inside. a customer can have acces to a virtual machine, and when it's no longer needed, shut it down and boot a new one.
### 3. What are the main cloud [[Deployment Models]]?
**Public**: the classic, we all think of
**Private** Running your own cloud setup (client = provider)
**Hybrid** a mix of both, split between private and public (for security, privacy reason or otherwise)
**Community / multi** oof, i guess you share this cloud with some other orgs? maybe like expanded private??? #COMEBACK
### 4. How do containers differ from traditional [[Virtual Machines]]?
Traditional [[Virtual Machines]] virtualize an entire OS, whereas containers are more stripped-down, only having what is necessary to running the application. Theres also the whole [[Hypervisor]] situation. VMs use a [[Hypervisor]] whereas containers are hoisted on ssssss #COMEBACK
### 5. What is the difference between IaaS, PaaS, and SaaS? [[as-a-Service Models]]
![[Comparison_of_on-premise,_IaaS,_PaaS,_and_SaaS 1.png]]
Essentially, how much management you want to outsource. 
**IaaS**, you 'rent' the infrastructure (server compute), and manage the networking, services etc yourself. in essence, you just want access to extra hardware(in the cloud) computing resources such as storage, network, servers, and [[Virtualization]]. dont have to maintain their own datacenter
**but you yourself have to do all the specific setup.**

**PaaS**, you get access to the platform, 
_a complete cloud environment that includes everything developers need to build, run, and manage applications—from servers and operating systems to all the networking, storage, middleware, tools, and more._
**Client has no control over OS and networking**

**Saas** separates "the possession and ownership of software from its use"
**Client just an app user. No control over application development and deployment**

### 6. Why might a business choose a hybrid cloud model?
They have some things that they want to manage themselves (perhaps relating to security), while other services and data could viably be put in the cloud.
also maybe avoiding vendor-lockin? and service downtime
### 7. How do modern processors support [[Virtualization]]?
#COMEBACK 
### 8. How does full [[Virtualization]] differ from paravirtualization and hardware-assisted [[Virtualization]]?
#COMEBACK 
### 9. What are the advantages and disadvantages of using containers compared to running applications on bare metal or within [[Virtual Machines]]?
Efficiency, and why give the application capabilities that it doesn't need? Better memory usage, more efficient containers (as they can be cut down to as close to just running the application as possible.)
### 10. Why might an organization choose a private cloud despite potentially higher costs?
simple