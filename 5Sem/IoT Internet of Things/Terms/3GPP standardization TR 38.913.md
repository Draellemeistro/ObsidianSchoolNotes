# [[5G-Service Requirements]] (????????)
## [[mIoT]]
- battery life for [[IoT device]] (UE - User Equipment)
	- 200 bytes in the uplink per day
	- 20 bytes in the downlink per day
	- 5 Wh battery capacity
	- 10-20 years of unattended operation (15 years is desirable)
- target connectivity density
	- 1.000.000 connections / km^2 in urban environment
	- under [[QoS levels]] of 1% packet drop rate
## [[URLLC]]
- **user plane latency**
	- "_The time it takes to successfully deliver an application layer packet/message from the radio protocol layer **2/3 SDU ingress point** to the radio protocol layer **2/3 SDU egress point** via the radio interface in both uplink and downlink directions…._"
	- "_For [[URLLC]], the target for user plane latency should be **0.5ms** for UL, and **0.5ms** for DL. …. The value above should be considered an average value and does not have an associated high reliability requirement_"
- **Reliability**
	- A success probability of transmitting certain amount of bytes within a certain delay
	- "_A general [[URLLC]] reliability requirement for one transmission of a packet is $1-10^{-5}$ for **32 bytes** with a user plane latency of **1ms**_"

