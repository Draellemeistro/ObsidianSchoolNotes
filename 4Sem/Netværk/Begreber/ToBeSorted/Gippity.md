Sure, let's go through each topic one by one based on the structure provided by "Computer Networking: A Top-Down Approach".

### 1. Structure of Internet: Server-Client vs P2P Service Architecture

**Server-Client Architecture:**
- In the server-client model, there are dedicated servers that provide services, and clients that consume these services.
- Servers are always on and await requests from clients, which initiate communication.
- Examples include web servers and email servers.

**Peer-to-Peer (P2P) Architecture:**
- In P2P architecture, there is no central server. Instead, each node (peer) can act as both a client and a server.
- Peers directly interact and share resources with each other.
- Examples include file-sharing systems like BitTorrent.

**Comparison:**
- **Scalability:** P2P is more scalable since the addition of new peers increases both resources and service capacity, whereas client-server models may face bottlenecks at the server.
- **Management:** Client-server architectures are easier to manage due to centralized control, whereas P2P networks require decentralized management.
- **Reliability:** P2P can be more resilient as there is no single point of failure, unlike client-server models which rely on server availability.

### 2. H - FTP, FTP

**FTP (File Transfer Protocol):**
- FTP is used for transferring files between computers on a network.
- It operates on a client-server model using two connections: a control connection (port 21) and a data connection (port 20).
- Commands and responses are sent over the control connection, while file data is transferred over the data connection.

### 3. E-mail Related Protocols

**SMTP (Simple Mail Transfer Protocol):**
- Used for sending emails from a client to a server or between servers.
- Operates over TCP, typically on port 25.

**POP3 (Post Office Protocol version 3):**
- Used by clients to retrieve emails from a mail server.
- Downloads emails to the client’s device and deletes them from the server.
- Operates over TCP, typically on port 110.

**IMAP (Internet Message Access Protocol):**
- Also used for retrieving emails from a server.
- Unlike POP3, it allows multiple clients to access the same mailbox and keeps emails on the server.
- Operates over TCP, typically on port 143.

### 4. Connection-Oriented vs Connectionless Service, UDP, ICMP
[video om lige det](https://youtu.be/cA9ZJdqzOoU?si=jSZ4O_D4ZRjGyKNR)
![[Pasted image 20240528181151.png]]
- **==TCP vs UDP==**
- do i want reliable? TCP
- don't i care? maybe still TCP, but also maybe UDP
**Connection-Oriented (TCP):**
- Establishes a connection before data transfer.
- Provides reliable, ordered, and error-checked delivery of data.
- Example: TCP (Transmission Control Protocol).

**Connectionless (UDP):**
- Sends data without establishing a connection.
- No guarantee of delivery, ordering, or error-checking.
- Example: UDP (User Datagram Protocol).

**ICMP (Internet Control Message Protocol):**
- Used for error messages and operational information queries.
- Example: Ping uses ICMP to test reachability of hosts.

### 5. Principles of Reliable Data Transfer

**Reliable Data Transfer:**
- Ensures data is delivered accurately and in order.
- Techniques include:
  - Acknowledgments (ACKs)
  - Retransmissions on timeout or negative acknowledgment (NAK)
  - Sequence numbers to detect duplicates and reorder segments
  - Error detection mechanisms like checksums
[[Principles of reliable data transfer]]
### 6. TCP in General

**TCP (Transmission Control Protocol):**
- A connection-oriented protocol that provides reliable data transfer.
- Features include:
  - Three-way handshake for connection establishment.
  - Flow control using window size.
  - Congestion control mechanisms.
  - Error detection and correction.

### 7. TCP Flow and Congestion Control

**Flow Control:**
- Ensures a sender does not overwhelm a receiver by regulating the amount of data sent.
- Implemented using the sliding window mechanism.

**Congestion Control:**
- Aims to prevent network congestion by adjusting the rate of data transmission.
- Key algorithms include:
  - Slow Start
  - Congestion Avoidance
  - Fast Retransmit
  - Fast Recovery

### 8. IP Forwarding, Generalized Forwarding

**IP Forwarding:**
- The process of routing packets between different networks.
- Routers use routing tables to determine the best path for forwarding packets.

**Generalized Forwarding:**
- Refers to advanced techniques like software-defined networking (SDN) where forwarding rules can be dynamically updated.

### 9. IPv4 Addressing, IP Fragmentation, IPv4 vs IPv6

**IPv4 Addressing:**
- Uses a 32-bit address format, typically represented in decimal as four octets.
- Supports approximately 4.3 billion unique addresses.

**IP Fragmentation:**
- Necessary when packets are larger than the Maximum Transmission Unit (MTU) of a network segment.
- Packets are divided into smaller fragments, each containing part of the original payload and a header.

**IPv6:**
- Uses a 128-bit address format, allowing for a vastly larger address space.
- Simplifies address allocation and improves routing efficiency.

### 10. Link State vs Distance Vector Routing Algorithms

**Link State Routing:**
- Each router has knowledge of the entire network topology.
- Routers calculate the shortest path to each destination using algorithms like Dijkstra's.
- Example: OSPF (Open Shortest Path First).

**Distance Vector Routing:**
- Each router knows only the distance to its neighbors and periodically shares this information.
- Routes are calculated using algorithms like Bellman-Ford.
- Example: RIP (Routing Information Protocol).

### 11. Intra-AS vs Inter-AS Routing

**Intra-AS Routing:**
- Routing within a single Autonomous System (AS).
- Uses Interior Gateway Protocols (IGPs) like OSPF and RIP.

**Inter-AS Routing:**
- Routing between different Autonomous Systems.
- Uses Exterior Gateway Protocols (EGPs) like BGP (Border Gateway Protocol).

### 12. Reliability in Transport- and Link Layer (Wired and Wireless)

**Transport Layer (TCP):**
- Ensures end-to-end reliability through mechanisms like acknowledgments, retransmissions, and error checking.

**Link Layer (Wired):**
- Uses error detection (e.g., CRC) and correction techniques.
- Example: Ethernet uses CRC for error detection.

**Link Layer (Wireless):**
- Additional challenges due to higher error rates and interference.
- Uses techniques like ARQ (Automatic Repeat reQuest) and more robust error correction.

### 13. Variants of Multiple Access Protocols

**Multiple Access Protocols:**
- Mechanisms to control access to the shared medium.
- Examples include:
  - **TDMA (Time Division Multiple Access)**
  - **FDMA (Frequency Division Multiple Access)**
  - **CDMA (Code Division Multiple Access)**

### 14. ALOHA vs CSMA/CD

**ALOHA:**
- A simple, contention-based protocol for packet radio networks.
- Two versions: Pure ALOHA and Slotted ALOHA.
- Relies on random access and acknowledgments.

**CSMA/CD (Carrier Sense Multiple Access with Collision Detection):**
- Used in Ethernet networks.
- Nodes listen to the medium before transmitting.
- If a collision is detected, the transmission stops, and the node attempts to retransmit after a random backoff time.

### 15. 802.11 Association Procedure, CSMA/CA

**802.11 Association:**
- The process by which a wireless device connects to an Access Point (AP).
- Involves scanning for APs, authentication, and association.

**CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance):**
- Used in wireless networks to avoid collisions.
- Nodes listen before transmitting and use mechanisms like RTS/CTS (Request to Send/Clear to Send) to avoid collisions.

### 16. ARP, Switched Ethernet, VLANs

**ARP (Address Resolution Protocol):**
- Resolves IP addresses to MAC addresses within a local network.

**Switched Ethernet:**
- Uses switches to create separate collision domains, improving network efficiency and reducing collisions.

**VLANs (Virtual Local Area Networks):**
- Logical segmentation of a physical network into separate, isolated networks.
- Enhances security and performance.

### 17. A Day in the Life of a Web Request

**Web Request Process:**
1. **DNS Resolution:** Translate domain name to IP address.
2. **TCP Connection:** Establish a TCP connection using a three-way handshake.
3. **HTTP Request/Response:** Send an HTTP request and receive an HTTP response.
4. **Rendering:** Browser renders the received HTML content.

### 18. DNS, NAT, DHCP

**DNS (Domain Name System):**
- Translates human-readable domain names to IP addresses.

**NAT (Network Address Translation):**
- Allows multiple devices on a local network to share a single public IP address.

**DHCP (Dynamic Host Configuration Protocol):**
- Automatically assigns IP addresses to devices on a network.

### 19. Error Detection in Various Protocols

**Error Detection Techniques:**
- **Checksums:** Used in TCP/UDP headers to detect errors in transmitted data.
- **CRC (Cyclic Redundancy Check):** Used in Ethernet frames for error detection.
- **Parity Bits:** Simple error detection in memory and communication systems.

### 20. Addressing Between Two LANs Both Connected to the Internet

**Inter-LAN Communication:**
- Each LAN has its own private IP addresses.
- Routers use public IP addresses to communicate over the Internet.
- NAT translates private addresses to public addresses for outbound traffic and vice versa for inbound traffic.

These topics cover fundamental concepts in computer networking, providing a solid foundation for understanding how different components and protocols interact to form a cohesive network infrastructure.