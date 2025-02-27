# System model
![[image_IoT access networks-2.png]]
- **Multiple access channel** (see [[multiple-access protocols]])
- [[Star Topology]]
	- single hop
	- common receiver
- Model of the received signal:
	- $y=\alpha *h*x+i+z+w$
	  
	- ![[image_IoT access networks-1.png]]
#### The full extent of the problem:
- No synchronization
- No channel-state information
- The base station does not know who is active
- Interference is uncontrolled
ss
s
- **Operation in licensed bands – interference from other networks is removed:**
	- $y=\alpha *h*x+i+z$
- **Use of signaling procedures to learn the channel state information (e.g., monitoring broadcasts in the downlink and relying on channel reciprocity):**
	- $y=\alpha *x+i+z$
- **Use of additional signaling procedures to learn who is active and RESERVE RESOURCES**
	- $y=x+z$
	- **THIS CREATES POINT-TO-POINT CHANNEL!**

> [!NOTE] Resource-reservation based access is standardly used in cellular networks!
> Also known as **grant-based access**












![[image_IoT access networks.png]]

- **Wired – dedicated cabling between sensor - gateway:**
	- **Technologies:** Cable, xDSL, Optical, etcll
	- **Pros:** very very reliable, very high rates, little delay, secure
	- **Cons:** Very expensive to roll out, vandalism, not scalable, no mobility
- **[[Short-range Networks]]**
	- **Technologies:** [[IEEE 802.11]] , [[IEEE 802.15.4]], Wireless M-BUS, etc...
	- **Pros:** Cheap to roll out, generally scalable, low power
	- **Cons:** short range, multi-hop not a solution, low rates, weaker security, interference, lack of universal infrastructure/coverage
- [[Cellular IoT]]
	- **Technologies:** GSM, GPRS, EDGE, 3G, LTE, LTE-A, [[LTE-M]], [[NB-IoT]], WiMAX, etc...
	- **Pros:** excellent coverage, mobility, roaming, generally secure, infrastructure
	- **Cons:** expensive to operate, not cheap to maintain, not power efficient, delays
- [[Long-range low-power IoT Networks]]
	- **AKA** Low-power WANs
	- **Technologies:** [[SigFox]] [[LoRa]]
	- **Pros:** Cheap to roll out, generally scalable, low power
	- **Cons:** short range, multi-hop not a solution, low rates, weaker security, interference, lack of universal infrastructure/coverage
- **Satellite** – the satellite serves as relay between device and gateway
	- **example:** only satellite [[machine-to-machine|M2M]] communication with the motors persisted after MH370 disappeared
	- Extremely high returns per device