

> [!NOTE] TLDR
> **Why?** Map names and IP-addresses together
> 
![[Pasted image 20240527075216.png]]
# See also


## Terms for this shit
- name servers
- Distributed database
- iterated query, recursive query
- DNS registrar
- networks edge
- local DNS name server
- Root name server
- Top Level Domain (TLD) server
- Authoritative DNS server

==authoritative name server (primary and secondary)==
# More info
## Context
- **People**: many identifiers
	- SSN, name, passport # etc
- **internet hosts, routers**:
	- IP address (32bit) - used for addressing datagrams
	- "*name*" e.g. cs/umass.edu - used by humans
- **==HOW TO MAP BETWEEN IP ADDRESS AND NAME OR THE OTHER WAY==**

## How it works
- Host makes DNS query
- it is sent to its local DNS server
- Local DNS server returns reply answering:
	- from its local cache of recent name-to-address translation pairs (possibly out of date!)
	- forwarding request into DNS hierarchy for resolution
- each ISP has local DNS name server
- local DNS server doesn’t strictly belong to hierarchy
### Something about queries
#### Iterated Query
![[Pasted image 20240527074257.png]]

#### Recursive Query
![[Pasted image 20240527074535.png]]
## Domain Name System (DNS)
- **Distributed Database** implemented in hierarchy of many **name servers**
- **Application-layer protocol**: hosts, DNS servers communicate to **resolve** names (address/name translation)
	- **Note**: core Internet function, ==**implemented as application-layer protocol**==
	- **Complexity at network's "edge"** #DAFUQ
### DNS Services
- hostname-to-IP-address translation
- Host aliasing
	- canonical, alias names
- mail server aliasing
- load distribution
	- replicated Web servers: many IP addresses correspond to one name

> [!warning] Why not centralize DNS??
> **Seems logical**: one point of failure, traffic volume, distant centralized database, maintenance
> 
> **ANSWER!** It doesn't scale to the needs
> Comcast DNS servers alone: 600B DNS queries per day
> Akamai DNS servers alone: 2.2T DNS queries per day

## Thinking about the DNS
- **freaking big ass motherfucking database** (thank god it's distributed)
	- approx 1 billion records, though each of them is simple
- **Handles many trillions of queries per day**
	- many more reads than writes
	- PERFORMANCE MATTERS: almost every internet transaction interacts with DNS - msecs count!!
- **Organizationally, physically decentralized**
	- millions of different organizations responsible for their records
- **"bulletproof": reliability, security**

## Hierarchy
### What does hierarchy mean in this context?
![[Pasted image 20240527073152.png]]
![[Pasted image 20240527073204.png]]
#### Root name servers
- **==VERY FUCKING IMPORTANT==** Internet function
	- Internet can't function without them
	- **DNSSEC - provides security: Authentication, message integrity**
- official, contact-of-last-resort by name servers that can not resolve name. 
	- **If no one else can figure it out or has the information, then it goes to these guys**
- **==13 logical root name “servers” worldwide==** 
	- though each “server” replicated many times (~200 servers in US)

#### Top level Domain (TLD) servers
- **==Responsible for==**
	- com, org, net, edu, aero, jobs, museums, and **all top-level country domains like .dk .kr . fr etc**
- Network Solutions: authoritative registry for .com, .net TLD
- Educause: .edu TLD

#### Authoritative DNS servers
- Organization's own DNS server(s), providing authoritative hostname to IP mappings for organization's named hosts
- can by maintained by organization or a service provider.

## Caching DNS Information
- once (any) name server learns mapping, it **caches** mapping, and **immediately** returns a cached mapping in response to a query
	- caching improves response time
	- cache entries timeout (disappear) after some time [[Network Terms|TTL]]
- Cached entries may be **out-of-date**
	- if named host changes IP address, may not be known Internet-wide until all TTLs expire!
	- ==best-effort name-to-address translation!==
## DNS records (Resource Records)
![[Pasted image 20240527074952.png]]
### Getting info into the DNS
- Register name bububibo.com at **DNS registrar** (there are several)
	- Provide names, IP addresses of authoritative name server (primary and secondary)
	- Registra inserts NS, A RRs into .com TLD server:
		- ( bububibo.com, dns1. bububibo.com, NS)
		- (dns1. bububibo.com, 212.212.212.1, A)
- Create authoritative server locally with IP address *212.212.212.1*
	- type A record for www. bububibo.com 
	- type MX record for bububibo.com
