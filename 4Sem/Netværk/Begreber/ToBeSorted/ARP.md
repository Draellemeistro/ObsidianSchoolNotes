
> [!NOTE] Raison d'etre
> ==**How to determine interface's MAC address, knowing its IP address?**==
> **ARP table:** eACH ip NODE (HOST, ROUTER) on LAN has table
> - IP/MAC address mappings for some LAN nodes:
> 	- \<IP address; MAC address; TTL>
> 	- **TTL: Time To Live** 
> 		- time after which address mapping will be forgotten (typically 20 min)
> ![[Pasted image 20240529161224.png]]

# ARP in action
**==example==** A wants to send datagram to B
- B's MAC address not in A's ARP table, so A uses ARP to find B's MAC address
1. A broadcasts ARP query, containing B's IP address
	1. ==**(destination MAC address set to all F's: FF-FF-FF-FF-FF-FF)**==
	2. all nodes on LAN receive ARP query
2. B replies to A with ARP response, giving its MAC address
3. A receives B’s reply, adds B entry into its local ARP table
4. 
