
> [!NOTE] TLDR
> Contents

# See also

# Info
## Some quick points


> [!tip] Some preliminary thoughts
> Complexity of reliable data transfer protocol will depend (strongly) on characteristics of unreliable channel (lose, corrupt, reorder data?)
> 
> Sender, receiver **do not** know the “state” of each other, e.g., was a message received? **NOT UNLESS COMMUNICATED VIA CHANNEL**
## Reliable data transfer protocol (rdt):
### Reliable data transfer protocol (rdt): Interfaces
![[Pasted image 20240527090327.png]]
### getting started
- incrementally develop sender, receiver sides of reliable data transfer protocol (rdt)
- consider only unidirectional data transfer
	- **but control info will flow in both directions!**
- use [[finite state machines (FSM)]] to specify sender, receiver
### rdt1.0: 
**==reliable transfer over a reliable channel==**
- assumes underlying channel perfectly reliable
	- no bit errors
	- no loss of packets
- **seperate** FSMs for sender, receiver:
	- **sender** sends data into underlying channel
		- ![[Pasted image 20240527090649.png]]
	- **receiver** reads data from underlying channel
		- ![[Pasted image 20240527090702.png]]


### rdt2.0: 
**==channel with bit errors==**

- underlying channel may flip bits in packet
	- checksum (e.g., Internet checksum) to detect bit errors

**the question: how to recover from errors?**
- How do humans do it? they communicate! "sorry, I didn't quite catch that last part."
- **acknowledgements (==ACKs==)**: receiver explicitly tells sender that pkt received OK
- **negative acknowledgements (==NAKs==):** receiver explicitly tells sender that pkt had errors
- sender **retransmits** pkt on receipt of NAK
- [[Network Terms|stop and wait]]

#### rdt2.0 FSM
![[Pasted image 20240527091244.png]]

> [!important] NOTE
> “state” of receiver (did the receiver get my message correctly?) isn’t known to sender unless somehow communicated from receiver to sender. **THAT'S WHY WE NEED A PROTOCOL!**
##### rdt2.0 FSM operation with no errors
![[Pasted image 20240527091457.png]]

##### rdt2.0 FSM corrupted packet scenario
![[Pasted image 20240527091507.png]]

#### rdt2.0 FATAL FLAW

> [!warning] what happens if ACK/NAK corrupted?
> sender doesn’t know what happened at receiver! can’t just retransmit: possible **==duplicate==**.

> [!NOTE] rdt2.1: Handling duplicates
> - sender retransmits current pkt if ACK/NAK corrupted
> - sender adds **sequence** **number** to each pkt
> - receiver discards (doesn't deliver up) duplicate pkt
### rdt2.1
![[Pasted image 20240527092047.png]]


#### rdt2.1: sender, handling garbled ACK/NAKs
![[Pasted image 20240527092009.png]]


#### rdt2.1: receiver, handling garbled ACK/NAKs
![[Pasted image 20240527092019.png]]




### rdt2.2: NAK-free
- same functionality as rdt2.1, using ACKs only
- instead of NAK, receiver sends ACK for last pkt received OK
	- receiver must explicitly include seq # of pkt being ACKed
- duplicate ACK at sender results in same action as NAK: retransmit current pkt
==- As we will see==, [[TCP]] ==uses this approach to be NAK-free==
![[Pasted image 20240527092258.png]]
## rdt3.0: channels with errors and loss

> [!NOTE] New channel assumption
> **underlying channel can also lose packets (data, ACKs)**. checksum, sequence # 's, ACKs, retransmissions will be of help … but not quite enough.
> 
> **How do humans handle lost sender-toreceiver words in conversation?**
> THEY WAIT A BIT

**==sender waits “reasonable” amount of time for ACK==**
- retransmits if no ACK received in this time
- if pkt (or ACK) just delayed (not lost):
	- retransmission will be duplicate, but seq # s already handles this!
	- receiver must specify seq # of packet being ACKed
- use countdown timer to interrupt after “reasonable” amount of time


### rdt3.0 performance (stop-and-wait)
$U_{sender}$ : **utilization** - fraction of time sender busy sender

**==EXAMPLE==** 1gbps link, 15ms prop. delay, 8000 bit packet
	Time to transmit packet into channel:
$$
D_{trans} = \frac{L}{R} = \frac{8000bits}{10^{9}bits/\sec} = 8microsecs
$$

### rdt3.0 illustrations etc.
#### rdt3.0 FSM
##### idk why there are two with same title
![[Pasted image 20240527092820.png]]
##### 22idk why there are two with same title
![[Pasted image 20240527092842.png]]

#### rdt3.0 in action
![[Pasted image 20240527092939.png]]![[Pasted image 20240527092951.png]]

#### rdt3.0 stop-and-wait
![[Pasted image 20240527093559.png]]
![[Pasted image 20240527093610.png]]

## rdt3.0: pipelined protocols operation

> [!success] Pipelining
> Sender allows multiple, 'in-flight', yet-to-be-acknowledged packets
> - range of sequence numbers must be increased
> - buffering at sender and/or receiver

![[Pasted image 20240527093948.png]]

### Go-Back-N
#### Go-Back-N: sender
- window of up to N, consecutive transmitted but unACKed pkts
	- k-bit seq # in pkt header
- **cumulative ACK**: ACK(n): ACKS all packets up to, including seq # n
	- on receving ACK(n): move window forward to begin at n+1
- timer for oldest in-flight packet
- timeout(n): retransmit packet n and all higher seq # packets in window

> [!NOTE] Go-Back-N: sender
> ![[Pasted image 20240527094448.png]]

#### Go-Back-N: receiver
- ACK-only: always send ACK for correctly-received packet so far, with highest **in-order** seq #
	- may generate duplicate ACKs
	- need only remember *rcv_base*
- on receipt of out-of-order packet
	- can discard (don't buffer) or buffer: **an implementation decision**
	- re-ACK pkt with highest in-order seq


> [!NOTE] Go-Back-N receiver
> ![[Pasted image 20240527094725.png]]

#### Go-Back-N in action
![[Pasted image 20240527094807.png]]



### Selective Repeat

#### Approach
- **Pipelining**: multiple packets in flight
 - **Receiver individually ACKs** all correctly received packets
	- buffers packets, as needed, for in-order delivery to upper layer
 - **sender maintains (conceptually):**
	- a timer for each unACKed pkt  (**timeout: retransmits single unACKed packet associated with timeout**) 
	- a 'window' over **N** consecutive seq # s (**limits pipelined, 'in flight' packets to be within this window**)

![[Pasted image 20240527100012.png]]

> [!example] Sender
> - **Data from above** - if next available seq # in window, send packet
> - **Timeout(n):** - resend packet n, restart timer
> - **ACK(n)** in \[sendbase,sendbase+N-1]:
> 	- mark packet n as received
> 	- if n smallest unACKed packet, advance window base to next unACKed seq \# 

> [!tip] Receiver
> - **Packet n in \[rcvbase, rcvbase+N-1]**
> 	- send ACK(n)
> 	- **out-of-order:** buffer
> 	- **in-order:** deliver (also deliver buffered, in order packets), advance window to next **not-yet-received** paket
> - **packet n in \[rcvbase-N,rcvbase-1]:** ACK(n)
> - **otherwise:** ignore


#### Selective repeat in action
![[Pasted image 20240527100616.png]]

#### Selective repeat: DILEMMA!
- example:
	- seq \#s: 0, 1, 2, 3 (base 4 counting)
	- window size=3
![[Pasted image 20240527100718.png]]![[Pasted image 20240527100724.png]]

> [!warning] The problem
> **what relationship is needed between sequence # size and window size to avoid problem in scenario (b)?**
> 
> - receiver can’t see sender side
> - receeiver behavior identical in both cases
> - **something's very wrong!**
