# The Physical Layer of [[IEEE 802.15.4]]
#### Defines / Realizes:
- [[Frequency bands]]
- [[Signal bandwidth]]
- Modulation
- Data rate
- Channel coding mechanism
- Error detection mechanism
- Frequency, phase and symbol synchronization
- Physical procedures related to [[multiple-access protocols]]/**protocols** ( [[Clear Channel Assessment (CCA)]])
### More general
- Half-duplex mode of communication
- Turnaround time from reception to transmission mode (and vice versa) may last up to 12 symbol periods maximum (denoted as _aTurnaroundTime_ in the standard)
- Transmission power CAN be adjusted
	- e.g., based on Link Quality Indicator (LQI) that is being monitored
- ##### [[Clear Channel Assessment (CCA)]] - Listening before talking

### [[IEEE 802.15.4]] Frequency bands
- Transmissions in [[IEEE 802.15.4]] are performed in [[ISM bands]] (Industrial, Scientific, Medical) bands
	- Open to use (limitations in terms of radiated power)
	- A lot of devices are using [[ISM bands]]
		- i.e., **a lot of interference**
#### IEEE 802.15.4 (original standards) uses bands in:
- 868/915 MHz
- 2.4 GHz
> [!NOTE] **In general:** lower frequency $\to$ larger distances + lower data-rates
![[image files etc/img5sem/IoT images/image_Frequency bands.png]]

####  [[IEEE 802.15.4]] Physical layer packet
> [!NOTE]  [[IEEE 802.15.4]] **Physical layer packet**
> ![[image_IEEE 802.15.4-2.png]]
> 
> - **preamble:** synchronization sequence, 32 bits (101010...)
> - **SoP delimiter:** Denotes the end of synchronization sequence, 8 bits (10101011)
> - **PHY header:** Denotes packet length (PHY SDU), 8 bits
> - **PHY SDU:**
> 	- MAC packet-data unit (MAC PDU)
> 	- Maximum length of 127 bytes (1016 bits)

#### [[Clear Channel Assessment (CCA)]] - Listening before talking
- Exploited by the [[Media Access Control (MAC)]] protocol
- lasts 8 [[symbol periods]]
- #### Three modes of operation:
	- Energy received during CCA period is above some threshold
	- A carrier that uses the same band and the same transmissions technique as the device is detected
	- Combination of the above