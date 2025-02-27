Most typically used protocol from this family is [[Slotted ALOHA]]
- **[[Slotted ALOHA]]:** Part of connection establishment in 2G, 3G, 4G, 5G.
	- [[LoRa]]
- **[[Pure (unslotted) ALOHA]]:** No synchronization at all
	- Users transmit when they want
	- Without synchronization, the chances of colliding with other users’ transmissions increase
		- The max throughput becomes 0.18


**A very simple channel [[Channel Access Protocol]]:** Users that experience packet arrivals start transmitting at the beginning of the next slot with some probability $𝑝_{𝐴}$ (i.e., access probability)
- $N$ active users, single access point (AP)
	- homogenous population
	- equal length packets
- [[Random-Access Protocols|Random-Access]]
	- distributed, decentralized
	- User behave in the same way
- Link time is divided in slots of equal duration
	- A slot can accommodate single packet transmission
	- Slot-synchronization of the users is assumed

### Slots can be
- **idle/empty (no user transmitted)** - this is a waste of resources
- **Singleton (a single user transmitted)** - This is a useful slot
- **Collision (two or more users transmitted)** - This is a waste of resources
![[image_ALOHA.png]]