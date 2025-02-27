
> [!NOTE] GOAL
> Determine “good” paths (equivalently, routes), from sending hosts to receiving host, through network of routers
> 
> **Path:** Sequence of routers packets travers from given initial source host to final destination
> 
> **"Good":** Least 'cost', 'fastest', 'least congested'
> 
> Routing: A 'top-10' networking challenge!



![[Pasted image 20240529113250.png]]

## Graph abstraction: link costs
![[Pasted image 20240527152726.png]]

## Routing algorithm classification
[[Link state vs distance vector routing algorithms]]
![[Pasted image 20240527152813.png]]


# Intra-AS routing
### [[RIP]]: 
- Classic DV: DVs exchanged every 30 secs
- no longer widely use
### [[EIGRP]]: 
- DV based
- Formerly Cisco-proprietary for decades (open in 2013)
### [[OSPF]]: 
- Link-state routing
- IS-IS protocol (ISO std, not RFC std) essentially same as OSPF