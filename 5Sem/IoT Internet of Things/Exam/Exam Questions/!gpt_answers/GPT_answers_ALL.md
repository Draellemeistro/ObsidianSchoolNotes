### **1. IoT-Exam question 1**

#### **Difference between typical IoT and standard wireless devices**:
- **IoT Devices**: Designed for low-power, low-bandwidth applications, constrained resources, and intermittent connectivity. Focuses on machine-to-machine (M2M) communication.
- **Standard Wireless Devices**: Typically have higher power, bandwidth, and resource availability. Focus on human-to-human or human-to-machine communication.

#### **Basic tasks of a typical IoT device and power consumption**:

1. **Sensing** (Low Power): Collects data using sensors.
2. **Processing** (Moderate Power): Analyzes or preprocesses data locally.
3. **Communication** (High Power): Sends/receives data to/from a network or cloud.

#### **Strategies to reduce energy consumption**:

1. Use low-power communication protocols (e.g., Bluetooth Low Energy, ZigBee).
2. Implement duty cycling (devices sleep when not in use).
3. Offload processing to the edge or cloud.

---

### **2. IoT-Exam question 2**

#### **General structure of IoT network**:

1. Sensing Layer (IoT devices/sensors).
2. Network Layer (Gateways, communication protocols).
3. Processing Layer (Edge devices, cloud servers).
4. Application Layer (User interfaces, analytics).

#### **Classification of IoT networks**:

1. **Personal Area Networks (PANs)**: Bluetooth, ZigBee.
2. **Local Area Networks (LANs)**: Wi-Fi.
3. **Wide Area Networks (WANs)**: Cellular (e.g., LTE-M, NB-IoT).
4. **Low Power Wide Area Networks (LPWANs)**: LoRaWAN, Sigfox.

---

### **3. IoT-Exam question 3**

#### **Characteristics of IoT traffic**:

- **Periodic**: Regular updates (e.g., environmental monitoring).
- **Event-driven**: Alerts for specific triggers (e.g., motion detection).
- **Asynchronous**: Varies with no fixed timing (e.g., emergency data).
- **Low throughput**: Minimal data size for most applications.

#### **Asynchronous vs. Synchronous traffic**:

- **Synchronous**: Predictable and occurs at fixed intervals (e.g., periodic sensor readings).
- **Asynchronous**: Irregular and triggered by events (e.g., alarm notifications).

---

### **4. IoT-Exam question 4**

#### **Reservation-based vs. Reservation-free access**:

- **Reservation-based (Grant)**: Devices request access, and the network allocates resources. Efficient for predictable traffic but adds latency.
- **Reservation-free (Grant-free)**: Devices transmit without prior requests. Reduces latency but risks collisions.

---

### **5. IoT-Exam question 5**

#### **5G service categories**:

1. **Enhanced Mobile Broadband (eMBB)**: High-speed data (less relevant for IoT).
2. **Massive Machine-Type Communications (mMTC)**: Scales IoT device connectivity.
3. **Ultra-Reliable Low-Latency Communications (URLLC)**: Supports critical IoT applications (e.g., autonomous vehicles, healthcare).

#### **Examples of IoT use cases**:

- **mMTC**: Smart cities, smart agriculture.
- **URLLC**: Industrial automation, remote surgery.

#### **3GPP standards for IoT**:

- LTE-M (Cat-M1), NB-IoT, and 5G NR (New Radio).

---

### **6. IoT-Exam question 6**

#### **IEEE 802.15.4 Layers**:

- Covers Physical (PHY) and Medium Access Control (MAC) layers.

#### **Operating bands**:

- 2.4 GHz ISM band and regional sub-GHz bands.

#### **Device types**:

- **Full-Function Devices (FFDs)**: Act as coordinators or routers.
- **Reduced-Function Devices (RFDs)**: Limited roles as end devices.

#### **Supported topologies**:

- Star, peer-to-peer, and cluster-tree.

---

### **7. IoT-Exam question 7**

#### **IEEE 802.15.4 multiple access in star topology**:

- Uses CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance).
- Devices communicate with a central coordinator.

---

### **8. IoT-Exam question 8**

#### **ZigBee specification layers**:

- Covers Application and Network layers.

#### **Relation to IEEE 802.15.4**:

- ZigBee uses IEEE 802.15.4 PHY and MAC layers.

#### **Devices and topologies**:

- Devices: Coordinators, routers, end devices.
- Topologies: Star, tree, and mesh.

---

### **9. IoT-Exam question 9**

#### **RFID components**:

- Tags, Readers, Antenna, Middleware.

#### **Types of RFID systems**:

- Inductive, Radiative (LF, HF, UHF systems).

#### **Types of RFID tags**:

- Passive, Semi-passive, Active.

#### **Example applications**:

- LF: Animal tracking.
- HF: Smart cards.
- UHF: Inventory management.

---

### **10. IoT-Exam question 10**

#### **Constrained Application Protocol (CoAP)**:

- Lightweight protocol for IoT devices over UDP.
- Features: RESTful interaction, low overhead.

#### **CoAP message types**:

1. Confirmable (CON): Requires acknowledgment.
2. Non-Confirmable (NON): Does not require acknowledgment.
3. Acknowledgment (ACK).
4. Reset (RST).

---

### **11. IoT-Exam question 11**

#### **Pub-Sub model**:

- Publishers send messages to topics; subscribers receive them via a broker.

---

### **12. IoT-Exam question 12**

#### **MQTT basics**:

- Runs over TCP/IP.
- Broker: Manages message routing.
- Topics: Hierarchical message categories.

#### **Connection establishment**:

1. Client connects to the broker.
2. Authentication (if required).
3. Subscription to topics.

---

### **13. IoT-Exam question 13**

#### **MQTT QoS levels**:

- 0: At most once.
- 1: At least once.
- 2: Exactly once.

#### **Choosing guidelines**:

- Use QoS 1 or 2 for critical data.

---

### **14. IoT-Exam question 14**

#### **IoT device vulnerabilities**:

- Limited security features, poor patch management.

#### **Common attacks**:

1. DDoS.
2. Man-in-the-middle (MITM).

#### **Fog computing for security**:

1. Local anomaly detection.
2. Data encryption offloading.

---

### **15. IoT-Exam question 15**

#### **MQTT security concerns**:

- Lack of encryption and authentication.

#### **MQTT wildcards**:

- Single level (`+`), Multi-level (`#`).

#### **Misuse by attackers**:

- Wildcards used to intercept unintended topics.

---

### **16. IoT-Exam question 16**

#### **5G vulnerabilities**:

1. Increased attack surface from massive device connections.
2. Complex architecture.

---

### **17. IoT-Exam question 17**

#### **IoT-Edge-Cloud components**:

- Edge devices, gateways, cloud servers.

#### **Supported protocols**:

- MQTT, CoAP, HTTP.

---

### **18. IoT-Exam question 18**

#### **IoT device provisioning**:

- Configuring devices for secure cloud connection.

#### **Azure IoT-Hub vs. Central**:

- **Hub**: Developer-centric.
- **Central**: Simplified, managed solution.

---

### **19. IoT-Exam question 19**

#### **Benefits of edge over cloud**:

- Low latency, reduced bandwidth.

#### **Azure IoT Edge**:

- Runs modules on edge devices for local computation.

---

### **20. IoT-Exam question 20**

#### **IoT vs. IIoT**:

- IoT: Consumer-focused.
- IIoT: Industry-focused (e.g., predictive maintenance).

#### **ISA traffic classes**:

1. Safety-critical, 2. Control, 3. Monitoring, etc.

---

### **21. IoT-Exam question 21**

#### **Cyber-physical systems**:

- Integration of physical processes with computation/control.

---

### **22. IoT-Exam question 22**

#### **TSCH and RPL in 6TiSCH**:

- **TSCH**: Time-synchronized channel hopping.
- **RPL**: IPv6 routing protocol for low-power networks.