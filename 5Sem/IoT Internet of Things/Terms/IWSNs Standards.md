- IoT protocols typically focus on optimizing data rate, range and battery life
- Different requirements for [[Industrial IoT|IIoT]] protocols, **different standards/technology**
- Several industrial standards have been developed for IIoT
- Industrial standards for [[Process Automation (PA) (batch processing)|PA]] (_seen below_) are based on the PHY layer of [[IEEE 802.15.4]]
	- [[WirelessHART]]
	- [[ISA100.11a]]
	- [[WIA-PA]]
	- [[IEEE 802.15.4e]]
![[image_IWSNs Standards.png]]
# Comparisons of the different Standards
## Protocol Stack of Industrial Standards
#### IoT/IIoT follows a 5-layer protocol stack (see this [[IoT-Protocol Stack|IoT Stack]])
## [[Network Architectures in IWSN Standards]]
## [[Channel Access in IWSN Standards]]
## [[Channel Hopping in IWSN Standards]]

# Which to choose???
> [!NOTE] Different applications, different requirements

Industrial facilities typically evaluate technologies based on primary factors:
- **Range:** How far does it need to send/receive data?
- **Data handling:** Does it send small data packets infrequently or large amounts of data on a near-continuous basis? Is communication bidirectional? How critical is it that every transmission gets through?
- **Power consumption:** Can it operate on batteries for an acceptable length of time, or does it require an external power source?
- **Reliability:** Do we require greater than 99.9% uptime, or are occasional brief outages tolerable
![[image_IWSNs Standards-2.png]]

# On to [[Industrial IoT Standard]] ((([[6TiSCH]])))