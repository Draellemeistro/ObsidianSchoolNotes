# Border Gateway Protocol
### the de facto inter-domain routing protocol

- allows subnet to advertise its existence, and the destinations it can reach, to rest of Internet: “**I am here, here is who I can reach, and how**”
- provides each AS a means to:
	- Obtain destination network reachability info from neighboring ASes (**==eBGP==**)
	- determine routes to other networks based on reachability information and **policy**
	- propagate reachability information to all AS-internal router (**==iBGP==**)
	- **advertise** (to neighboring networks) destination reachability info
### eBGP, iBGP connection
![[Pasted image 20240529123938.png]]
## BGP basics
- **BGP session**: two BGP routers ('*peers*') exchange BGP messages over semi-permanent TCP connection:
	- advertising *paths* to different destination network prefixes (BGP is a "path vector" protocol)
- when AS3 gateway 3a advertises **path AS3,X** to AS2 gateway 2c:
	- AS3 **promises** to AS2 it will forward datagrams towards X
	- ![[Pasted image 20240529124348.png]]

### BGP protocol messages
- BGP messages exchanged between peers over [[TCP]] connection
- BGP messages:
	- **OPEN:** opens TCP connection to remote BGP peer and authenticates sending BGP peer
	- **UPDATE**: advertises new path (or withdraws old)
	- **KEEPALIVE:** keeps connection alive in absence of UPDATEs; also ACKs OPEN request
	- **NOTIFICATION:** reports errors in previous msg; also used to close connection
### Path attributes and BGP routes
- BGP advertised route: prefix + attributes
	- prefix: destination being advertised
	- two important attributes:
		- **AS-PATH**: list of ASes through which prefix advertisement has passed
		- **NEXT-HOP:** indicates specific internal-AS router to next-hop AS
- **==policy-based routing:==**
	- gateway receiving route advertisement uses **import policy** to accept/decline path (e.g., never route through AS Y).
	- AS policy also determines whether to **advertise** path to other other neighboring ASes
## BGP path advertisement

![[Pasted image 20240529125549.png]]
![[Pasted image 20240529125607.png]]
![[Pasted image 20240529125615.png]]
![[Pasted image 20240529125623.png]]
![[Pasted image 20240529125643.png]]
![[Pasted image 20240529125715.png]]
![[Pasted image 20240529125721.png]]
![[Pasted image 20240529125729.png]]
