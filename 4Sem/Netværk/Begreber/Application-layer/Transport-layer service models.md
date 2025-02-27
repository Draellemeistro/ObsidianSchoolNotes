
> [!NOTE] Title #TODO 
> bla bla bla
> 
> [[TLS]] is implemented in the [[Application Layer]].
> Apps use TLS libraries that use [[TCP]] in turn



# See also


| [[UDP service]] | [[TCP service]] | [[TLS]]  |     |     |
| --------------- | --------------- | -------- | --- | --- |
|                 |                 |          |     |     |

# What transport service does an app need?
- **==Data integrity==**
	- Some apps (e.g file transfer, web transactions) require 100% reliable data transfer
	- Other apps (e.g audio) can tolerate some loss
- **==Timing==**
	- Some apps ( internet phoning, interactive games) require low delay to be "effective"
	- PING is shit, but so is packet loss
- **==Throughput==**
	- Some apps (multimedia) require min. amount of throughput to be "effective"
	- other apps ("elastic apps") make use of whatever throughput they get
- **==Security==**
	- Encryption, data integrity etc...

![[Pasted image 20240527053601.png]]

![[Pasted image 20240527053945.png]]![[Pasted image 20240527053957.png]]