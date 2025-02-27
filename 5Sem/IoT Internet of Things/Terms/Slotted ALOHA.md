Most typically used protocol of the [[ALOHA]] family.
- Part of connection establishment in 2G, 3G, 4G, 5G.. **something [[LoRa]] (same as the G's??)**
	
- Access point sends feedback after every slot - ACK in case of successful decoding, NACK in case of failure
- Collided users observe NACK from the access point - this indicates collision
	- A very simple collision-resolution protocol: Collided users retry in next slots with a possibly changed $p_A$ 
- The standard goal of the access scheme is to maximize throughput, which is the fraction of useful slots
	- Throughput is the measure of efficiency
	- throughput maximization is achieved by optimizing $p_A$

![[image_Slotted ALOHA-2.png]]
### How to optimize $p_A$
###### Throughput can be computed as the probability that a slot is singleton:
- $T= {{N}\choose{1}}p_{A}(1-p)^{N-1}\approx Np_{A}e^{-Np_{a}}$
- $T_{\text{max}}=\frac{1}{e}\approx_{0}.37 \text{ (when )}Np_{A}=1$
###### The average channel laod is defined as $G=Np_{A}$
- makes sense to strive to acheive $G=1$

## Throughput curve
- [[Slotted ALOHA]] inherently tends to become unstable. **Stabilization is required**
	- Trying to get the channel load to 1 (_tuning the access probability_)
![[image_Slotted ALOHA-3.png]]
