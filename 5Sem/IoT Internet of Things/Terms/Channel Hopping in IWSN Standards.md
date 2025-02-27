> [!NOTE] **[[Channel hopping]]:** changing transmission frequency per user
## [[WirelessHART]] / [[ISA100.11a]]
- WirelessHART and ISA100.11a use slotted hopping
- In slotted-hopping, frequency changes among time slots
- The actual channel is determined using the following formula:
	- $\text{ActualChannel}=(\text{ChannelOffset}+\text{ASN})\%\text{NumChannels}$ 
- Absolute Slot Number (**ASN**): The number of a time slots since the network was formed
![[image_Channel Hopping-2.png]]

## [[WIA-PA]]
WIA-PA uses three different channel hopping schemes:
1) **Adaptive frequency switching**
	1)  Used during CAP and CFP
	2) Channel is changed once the interference is above a certain level
2) **Adaptive frequency hopping**
	1) Used during the intra-cluster period
	2) Channel is changed once the quality of the current channel falls below a certain threshold
3) **Slotted hopping**
	1) Used during the inter-cluster period
	2) Channel changes following the sequence set by the network manager
