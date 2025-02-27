


## [[Network Architectures in IWSN Standards]]
#### [[Network Topologies]]
[[WIA-PA]] supports a hierarchical network topology that is basically [[Star Topology|star]] **PLUS** [[Mesh Topology|mesh]].
![[image_IoT-network architectures-2.png]]
#### Devices
Devices in [[WIA-PA]] network are categorized into four types:
- **Field/handheld devices (cluster members):** collecting data
- **Routers (cluster head):** managing the star network
- **Redundant cluster head**
- **Gateway**

## [[Channel Access in IWSN Standards]]
- [[WIA-PA]] follows a similar superframe structure to [[ZigBee]]
- **CAP (CSMA/CA):** used for device joining and retransmissions
- CFP (TDMA): data transmissions to cluster head
- The inactive period is divided into: intra-cluster, inter-cluster and sleeping
- **Intra-cluster** and **inter-cluster** periods are used for exchanging control and management messages
![[image_Channel Access in IWSN Standards-1.png]]