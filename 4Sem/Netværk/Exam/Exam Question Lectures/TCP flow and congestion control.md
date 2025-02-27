# TCP flow control

> [!NOTE] Question
> **What happens if network layer delivers data faster than application layer removes data from socket buffers?**
> 
> ![[Pasted image 20240527101241.png]]
> 
> ==INDSÆT VIDEO AF DAME MED CHAMPAGNEFLASKE DER SPRØJTER==


> [!NOTE] Flow control
> receiver controls sender, so sender won’t overflow receiver’s buffer by transmitting too much, too fast
> **receive window (header field):** flow control: # bytes receiver willing to accept
> 
> **TCP receiver “advertises” free buffer space in rwnd field in TCP header**
> - **RcvBuffer:** size set via socket options (typical ddefault is 4096 bytes)
> - many operating systems auto-adjust **RcvBuffer**
> Sender limits amount of unACKed data to the received **rwnd**
> **guarantees receive buffer will not overflow**
> 
> ![[Pasted image 20240527101802.png]]



# TCP congestion control:
## [[AIMD]]

![[Pasted image 20240527102709.png]]
![[Pasted image 20240527102717.png]]
### Details
![[Pasted image 20240527102732.png]]
### TCP slow start
![[Pasted image 20240527102749.png]]
![[Pasted image 20240527102757.png]]
![[Pasted image 20240527102818.png]]
## [[TCP CUBIC]]
![[Pasted image 20240527102908.png]]
![[Pasted image 20240527102916.png]]
![[Pasted image 20240527102931.png]]
![[Pasted image 20240527102939.png]]


## Delay-based TCP congestion control
![[Pasted image 20240527103005.png]]
![[Pasted image 20240527103017.png]]


### Explicit congestion notification (ECN)
![[Pasted image 20240527103054.png]]
![[Pasted image 20240527103103.png]]
![[Pasted image 20240527103113.png]]
![[Pasted image 20240527103121.png]]




