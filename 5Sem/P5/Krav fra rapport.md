# Fundet
- System Must be able to roll the Hardwall device back to a known clean state
- System Must roll the Hardwall device back to a known clean state after each ended session of use
- The backend component must not directly interact with any files on the USB if it is a drive.
## State
- (grundet BadUSB etc.) System must block the USB device, if it changes descriptors/device class
- 
- System must extract at least XXXX features from any executable file, DLL +++ ?????
- **bg** et eller andet sikkerhed og hypervisor
# Kommer ikke med
-  Sanitizing and normalizing of packets sent to the host have been used in several projects\cite{USBProxyPaper, Cinch}.
- Must have functionality of white- and black-listing, providing robust rulesystems to discern intentions as well as handling anomalies.
- presents to the host a generic HID descriptor set. Packets transmitted to the host contain only input packets, and the proxy performs a size check on this data.


1. **System Rollback**
    
    - The system must be able to restore the Hardwall device to a known clean state.
    - The system must automatically roll the Hardwall device back to a clean state after the end of each session.
2. **Backend File Interaction**
    
    - The backend component must not directly interact with any files on the USB device if it is a mass storage device.
3. **Device Descriptor Integrity**
    
    - The system must block a USB device if it changes its descriptors or device class during a session, as this may indicate malicious behavior (e.g., BadUSB attacks).
4. **Executable File Analysis**
    
    - The system must extract at least XX number features from executable files, DLLs, and other similar file types to support detailed analysis.
5. **Hypervisor Security**
    
    - The system must include robust security measures, such as hypervisor-based isolation, to ensure safe handling of USB traffic.
6. **Packet Sanitization and Normalization**
    
    - Sanitizing and normalizing packets sent to the host is a critical feature and has been demonstrated in several projects \cite{USBProxyPaper, Cinch}.
7. **Whitelist/Blacklist Functionality**
    
    - The system must include functionality for whitelisting and blacklisting devices, offering a robust rule-based system to manage device intentions and handle anomalies effectively.
8. **HID Descriptor Presentation**
    
    - The system must present a generic HID descriptor set to the host.
    - Packets transmitted to the host must contain only input packets, and the proxy must perform a size check on all transmitted data.

---

### Notes:

- For **feature extraction** (point 4), specify the exact number of features and the type of analysis (static/dynamic) you plan to implement.
- The **hypervisor security** point could be expanded by referencing specific techniques (e.g., hardware-assisted virtualization, micro-hypervisors) for added clarity.
- Consider adding a performance benchmark for the **rollback functionality** (e.g., "rollback must complete within X seconds").
- In **packet sanitization**, clarify what "sanitizing and normalizing" entails (e.g., removing unnecessary data, ensuring compliance with USB protocols).