# Overview + Goals + Roadmap

![[Pasted image 20240527105701.png]]
![[Pasted image 20240527105839.png]]
# Terms, topics and such
- [[IP Internet Protocol]]
	- [[Datagram Format]]
	- [[Network-Layer Addressing]]
	- [[Network Address Translation]]
	- [[IPv6]]
	- [[Routing Algorithms]]
		- CIDR
	- [[DHCP]]: Dynamic Host Configuration Protocol
	- [[subnets]]
- [[Routers]]
## network-layer functions (Forwarding, Routing)


> [!NOTE] Forwarding
> move packets from a router’s input link to appropriate router output link
> (process of getting through single interchange)
>


> [!NOTE] Routing
> determine route taken from source to destination by packets from source to destination
> (process of planning trip from source to destination)



## Data Plane
- **==local==**, per-router function
- determines how datagram arriving on router input port is forwarded to router output port
## Control Plane
- **==Network-wide==** logic
- determines how datagram is routed among routers along endend path from source host to destination host
- two control-plane approaches:
	- traditional routing algorithms: implemented in routers
	- software-defined networking (SDN): implemented in (remote) servers
# Extra
## important terms??

## TODO
