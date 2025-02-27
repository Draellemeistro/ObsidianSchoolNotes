## General structure of IoT network:
- [[IoT device]] (sensor/actuator) which sends measurements (in the uplink) and gets actuated (in the downlink)
- [[IoT access networks]]
	- Provides access to the gateways and [[IoT device]]s
- [[IoT Gateway]]
	- Provides (when necessary) the protocol translation between the access networks and core network
- **Edge server**
- **Backhaul, Core, Internet**
	- Provides the device connectivity to the IoT service / application
- **cloud**
![[image_IoT network.png]]
# IoT networking
![[image_IoT network-2.png]]
#### IoT services are very heterogenous
- **Ex:** Connected vehicles vs agricultural monitoring
- This reflects in the IoT networking domain – there is a multitude of [[IoT Networking technologies]]
#### Basic categories
- [[Long-range low-power IoT Networks]]
	- [[LoRa]], [[SigFox]]
- [[Cellular IoT]]
	- [[LTE-M]], [[NB-IoT]], [[RedCap]]
- [[Short-range Networks]]
	- [[Personal Area Networks]] (PAN)
		- [[ZigBee]], [[BLE]]
		- [[Body Area Networks]] (BAN)
### Standardization Bodies
![[image_IoT network-1.png]]

## [[IoT access networks]]
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
