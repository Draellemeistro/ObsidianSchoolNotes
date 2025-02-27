
> [!NOTE] TLDR
> **sender**: multiplexing, **receiver**: demultiplexing
> 
> ![[Pasted image 20240527084235.png]]
> 
> **Multiplexing**: handle data from multiple sockets, add transport header (later used for demultiplexing) **THINK: MERGING ONTO THE HIGHWAY**
> **Demultiplexing**: use header info to deliver received segments to correct socket **THINK: HIGHWAY EXITS AND GENERAL SIGN POSTING**

# See also

# Gist of it
![[Pasted image 20240527083314.png]]
## Think stuff
![[Pasted image 20240527083338.png]]

> [!question] ????
> **How did transport layer know to deliver message to Firefox browser process rather then Netflix process or Skype process?**
> 
> BECAUSE OF DEMULTIPLEXING

![[Pasted image 20240527083715.png]]
![[Pasted image 20240527083726.png]]

![[Pasted image 20240527083932.png]]
## Demultiplexing
### How it works
- host receives IP datagrams
	- each datagram has source IP address, destination IP address
	- each datagram carries one transport-layer segment
	- each segment has source, destination port number
- host uses **IP addresses & port numbers** to direct segment to appropriate socket
### Connectionless demultiplexing
![[Pasted image 20240527084006.png]]
#### EXAMPLE: Connectionless demultiplexing
![[Pasted image 20240527084043.png]]
### Connection-oriented demultiplexing
![[Pasted image 20240527084111.png]]
#### EXAMPLE: Connection-oriented demultiplexing
![[Pasted image 20240527084150.png]]
