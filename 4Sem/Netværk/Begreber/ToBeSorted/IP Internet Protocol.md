![[Pasted image 20240527140107.png]]
![[Pasted image 20240529112200.png]]
![[Pasted image 20240529112241.png]]

|Field|Description|
|---|---|
|**Version number**|Specifies the IP protocol version of the datagram (IPv4 or IPv6).|
|**Header length**|Determines the start of the payload in the IP datagram; typically 20 bytes for most datagrams.|
|**Type of service**|Bits used to distinguish different types of IP datagrams based on the required level of service.|
|**Datagram length**|Total length of the IP datagram (header plus data) in bytes; maximum theoretical size is 65,535 bytes.|
|**Identifier, flags, fragmentation offset**|Fields related to IP fragmentation, where large datagrams are broken into smaller fragments for transmission.|
|**Time-to-live**|Ensures datagrams do not circulate indefinitely; decremented by routers, and dropped if it reaches 0.|
|**Protocol**|Indicates the specific transport-layer protocol for the data portion of the IP datagram (e.g., TCP, UDP).|
|**Header checksum**|Aids in detecting bit errors in the received IP datagram; computed using 1s complement arithmetic.|
|**Source and destination IP addresses**|Source inserts its IP address, and destination's address is determined, usually via DNS lookup.|
|**Options**|Allow IP header extension for rare use cases, but omitted in IPv6 for simplicity.|
|**Data (payload)**|Contains the transport-layer segment (e.g., TCP or UDP) or other data, such as ICMP messages.|
==_Note: An IP datagram typically has a 20-byte header (excluding options). If carrying a TCP segment, each datagram includes a total of 40 bytes of header (20 bytes of IP header plus 20 bytes of TCP header) along with the application-layer message._==
