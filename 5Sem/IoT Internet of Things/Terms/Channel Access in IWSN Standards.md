> [!NOTE] All the industrial standards utilize a combination of RDMA and CSMA/CA for channel access.

All the industrial standards utilize a combination of RDMA and CSMA/CA for channel access.

## [[ZigBee]]
- Zigbee follows **Beacon-based superframe structure**
- Time is divided into superframes
- Each superframe starts with a beacon (control information)
- The superframe consists of **Contention-Access Period (CAP)** and **Contention-Free Period (CFP)**
	- **CAP:** nodes compete to get one Guaranteed Time Slot (GTS) in the CFP using CSMA/CA
	- **CFP:** Succeeded nodes transmit data in the assigned (**TDMA**) **GTS** (LIMITED TO 7 GTSs IN A SUPERFRAME)
- Finally, there is the **inactive period**, where nodes are set to sleeping mode to save power
![[image_Channel Access in IWSN Standards.png]]
## [[WIA-PA]]
- [[WIA-PA]] follows a similar superframe structure to [[ZigBee]]
- **CAP (CSMA/CA):** used for device joining and retransmissions
- CFP (TDMA): data transmissions to cluster head
- The inactive period is divided into: intra-cluster, inter-cluster and sleeping
- **Intra-cluster** and **inter-cluster** periods are used for exchanging control and management messages
![[image_Channel Access in IWSN Standards-1.png]]
## [[WirelessHART]] / [[ISA100.11a]]
- [[WirelessHART]] and [[ISA100.11a]] follow **TDMA-based superframe structure**
- The superframe of WirelessHART consists of a set of timeslots with duration of 10 ms
- The superframe of ISA100.11a can be a hybrid of short and long timeslots
- TDMA provide deterministic communication; a network manager will assign a scheduled timeslot for transmitting a message from one node to another
- The superframe of [[WirelessHART]] / [[ISA100.11a]] includes a number of shared timeslots (CSMA/CA)
![[image_Channel Access in IWSN Standards-2.png]]

# Next, see [[Channel Hopping in IWSN Standards]]
