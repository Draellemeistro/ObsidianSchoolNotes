for [[Clock Synchronization]]
**Has several different modes**
- **Goals**
	- Externally synchronize clients via internet to UTC
	- Provide reliable service tolerating lengthy losses of connectivity 
	- Enable clients to resynchronize sufficiently frequently to offset typical HW drift rates
	- Provice protection against interference 
- NTP is based on a hierarchical organized synchronisations architecture, and is based on an UDP based protocol for distributing of time information at internet scale 
- **Each level synchronized to its super level which at top has a super steady clock**
![[image_Network Time Protocol (NTP).png]]

# NTP Modes
### Multicast
- One computer periodically multicasts time info to all other computers on network 
- These adjust clock assuming a very small transmission delay
- Only suitable for high speed lans; yields low but usually acceptable synchronization
### Procedure-call
#COMEBACK 
### Symmetric
#COMEBACK 