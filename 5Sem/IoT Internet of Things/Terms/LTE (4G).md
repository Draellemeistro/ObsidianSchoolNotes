# LTE (4G) CELLULAR ACCESS

## LTE duplexing modes and [[Channel Access Protocol|channel access]]
![[image_LTE (4G).png]]
#### [[FDD]] LTE
#### [[TDD]] LTE
TDD is more popular due to more efficient transceivers

![[image_LTE (4G)-1.png]]
## LTE resource organization
![[image_LTE (4G)-2.png]]
![[image_LTE (4G)-3.png]]

> [!NOTE] **Subframes can be used either in the downlink or in the uplink**
> - Organization primarily depends on the duplexing method ([[FDD]] / [[TDD]])
> - there are many potential configurations

- Time organization requires that [[UE]] and [[BS]] are synchronized
	- Done in the [[initial access phase]]
- Once the device is synchronized, it can ask for the resources
- Assignments of resources is the task of the [[Radio Resource Control protocol]]


## LTE [[initial access phase|initial access]]
### Cell Search
- base station broadcasts synchronization signals and cell system information
	- Done through [[Primary Synchronization Signals|primary]] and [[Secondary Synchronization Signals|secondary]] [[Synchronization Signals]] which occur periodically, in slots 1 and 11 of the frame (i.e., every 5 ms)
- [[UE]] obtains physical layer information through system-information broadcasts
	- Master Information Block and System Information Block
	- UE acquires frequency and synchronizes to a cell
	- Determine the start of the downlink frame
		- **completes the downlink synchronization**
	- determines the cell identity
		- ![[image_LTE (4G)-4.png]]
## [[LTE Access Networking]]
**Resource-reservation based and connection-oriented**: A device establishes a connection before transmitting data

- Once connected, a device can stay in connected state only if it actively or periodically transmits (dormant state)
- The period that a device may spend in dormant state typically shorter than IoT reporting periods
- Connection establishment involves a sequence of signaling messages exchanged over uplink and downlink channel
- [[Radio Resource Control protocol]] states:
![[image_LTE (4G)-5.png]]
![[image_LTE (4G)-6.png]]
![[image_LTE (4G)-7.png]]
![[image_LTE (4G)-8.png]]
![[image_LTE (4G)-9.png]]
![[image_LTE (4G)-10.png]]
