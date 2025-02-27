![[image_IWSNs Standards-1.png]]
![[image_IoT-Protocol Stack.png]]
![[image_IoT-Protocol Stack 1.png]]
![[image_IoT-Protocol Stack-2.png]]



| Layer              | Protocol                       |
| ------------------ | ------------------------------ |
| Application        | [[HTTP]] , [[CoAP]] , [[MQTT]] |
| Transport          | TCP , UDP                      |
| Network, routing   | IPv6 , [[RPL]]                 |
| Adaption           | [[6LoWPAN]]                    |
| MAC                | [[CSMA-CA\|CSMA/CA]]           |
| Radio Duty Cycling | [[ContikiMAC]] , [[TSCH]]      |
| Radio              | [[IEEE 802.15.4]]              |
> [!NOTE] Traditional Client-Server in TCP/IP
>  **Server**
> - Always-on host
> - Permanent IP address
> 
> **Clients**
> - Communicate with server
> - May be intermittently connected
> - may have dynamic IP addresses


### Application Layer
- [[HTTP]] (and [[HTTPS]]????)
- [[MQTT]]
- [[CoAP]]
- [[AMQP]]
- [[XMPP]]
### Transport Layer
- TCP
- UDP
### Network Layer
- IPV4
- IPV6
- IPSec
- ICMP
- 6LowPAN
### Data link Layer
- [[ZigBee]]
- [[Bluetooth|Bluetooth (BLE)]]
- Wi-Fi
- [[LoRa]]
- [[NFC]]
- Cellular
- [[Zwave]]
### Physical Layer

#### Frequency bands of the Physical Layer in [[IEEE 802.15.4]]
![[image_IoT-Protocol Stack-1.png]]