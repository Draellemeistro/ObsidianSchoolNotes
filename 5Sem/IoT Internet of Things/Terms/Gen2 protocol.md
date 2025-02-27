also known as **Q protocol**
> [!NOTE] ISO 1800-6c, EPC global Class 1 Generation 2
- [[Electronic Product Code (EPC)]]
	- A universal identifier that provides a unique identity for every **physical object** anywhere in the world
	- does not necessarily have to involve [[RFID]]
- The protocol is based on **dynamic frame [[Slotted ALOHA]]**
- Gen2 operates in inventory rounds, initiated by the reader

## Simple, simple overview

> [!NOTE] Title
> ![[image_Gen2 protocol-1.png]]
> 
> **Notes:**
> - CRC-16 is not shown in transition
> - See command reply tables for command tables
### A little more
- If two or more tags reply, a collision occurs
	- The collision may not be detected in RN16 responses
		- One tag can be “_stronger_” than the others (good), or
		- Decoded RN16 is wrong, so the ACK sent by the reader is wrong (bad)
- After a round has been finished, the reader has the following options:
	- Increase the value of Q by 1 and do another round
	- Do not change Q and do another round
	- Decrease the value of Q by 1 and do another round
	- Issue a new Query command with an arbitrary value of Q
	- stop
- The value of Q (i.e., $L=2^Q$) should be optimized according to the number of [[RFID-tags|tags]] $N$
- The observations from the previous round can be used to tune $Q$
- Gen2 $Q$ selection algorithm
	- ![[image_Gen2 protocol-2.png]]

> [!NOTE] Performance of Gen2 $Q$ selection algorithm
> ![[image_Gen2 protocol-3.png]]


> [!NOTE] Optimal round (_frame_) size (Optimal $Q$ (i.e., $L$))
> - The idea is to minimize the throughput:
> 	- Probability that a slot is a singleton:
> 	  $$T={N\choose1}\left( \frac{1}{L} \right)\left(1-\frac{1}{L}\right)^{N-1} \approx \frac{N}{L}e^{- \frac{N}{L}}$$
> - $T_{\text{max}}=\frac{1}{e}\approx 0.37$ (when $\frac{N}{L}=1$)
> - There are many algorithms published in the literature that try to estimate $N$ precisely and set $Q$ correspondingly

### The basic scheme:
- The reader specifies the number of slots in the inventory round
- Each tag randomly chooses a location to reply within the round
- The reader issues short commands to mark the beginning of each slot within the round
- If a tag has chosen that slot, it replies with a random number
- If the reader can decipher the number and acknowledge it, the tag sends its [[Electronic Product Code (EPC)]]
- The random number exchanged between tag and reader also allows the reader to maintain a unique logical session with that tag, independently of the tag’s [[Electronic Product Code (EPC)|EPC]], or even whether it has a unique [[Electronic Product Code (EPC)]]
	- With the aid of this number (the handle) the reader can read from and write to the tag’s memory and perform other operations unique to that tag
### More shit

- **The round is started by a Query command that carries information that controls the round**
	- Parameter $Q$ determines how many slots $L$ will be in round (frame)
		- $Q \in [0, 15]$
		- $L=2^{Q}\in[1,32768]$
	- The [[RFID-tags|tags]] roll a dice and determine independently in which slots they will be active
		- i.e., the tags choose a random number in $[0,L-1]$
- ![[image_Gen2 protocol.png]]
- If tags random number is $0$, the tag  responds in the first slot
	- Otherwise, the tag records the number and waits
- A tag that responds sends a 16-bit random number RN16
- If the receiver hears the response (during a period after **_Query_** command) and is able to decode it, it sends the ACK which includes the received RN16
	- There is no error checking, the received RN16 may be wrong (_at both sides_)
- If the tag hears the ACK, it replies with, among other info, its [[Electronic Product Code (EPC)]]
	- **CRC** is included now
- At this point, the reader can choose to access the specific tag and `read`/`write` to its memory
- in most cases, the reader just wanted the [[Electronic Product Code (EPC)]], so the round continues with a new command: `QueryRep`:
	- Signals the end of the slot and that new slot starts
	- the tags decrement their random numbers by 1, and if some tags end up having 0, it replies etc.
- the reader may also choose to start a new round, by sending new **Query**
- The tags may be programmed to change the state after hearing the ACK
	- so they become "_interrogated_" and stay silent in the enxt round