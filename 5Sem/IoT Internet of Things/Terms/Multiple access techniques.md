- The wireless channel in the [[IoT access networks]]  [[IoT device]]s  is **SHARED**
	- Multiple devices have the access to the channel resources -> multiple access channel
	- ![[image_Multiple access techniques.png]]
- **Channel resources:**
	- Channel tile and bandwidth (frequencies)
	- ![[image_Multiple access techniques-1.png]]

### How to share (partition) the channel resources among multiple devices?
> [!danger] [[channel partitioning]] is about how to separate resources and enable concurrent transmissions
> How to actually assign resources (subchannel, slot, and/or code) is the task of [[multiple-access protocols]]
> 
> ![[image_Multiple access techniques-2.png]]
##### Several approaches to [[channel partitioning]]:
- [[Frequency-division multiplexing]] (FDM)
- [[Time-division multiplexing]] (TDM)
- [[Code-division multiplex]] (CDM)
- combinations of the above
###### [[Frequency-division multiplexing]]
- Channel bandwidth is divided in subchannels (separate frequency bands)
	- A device is assigned a part of the bandwidth (subchannel) all the time
###### [[Time-division multiplexing]]
- Channel time gets divided into periodically recurring time slots
	- A device is assigned all the bandwidth for part of the time (time slot)
###### [[Code-division multiplex]]
- A device is assigned a special code enabling it to use all the bandwidth all the time
