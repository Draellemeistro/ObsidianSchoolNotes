
> [!missing] Title
> - Once a USB device connects, it’s too late. So you have to isolate that device first, and in such a way that only a secure service can interact with it.
> - You need to interact with a USB device to determine what it is. You can’t rely on whatever the device tells you it is, because USB Device Types, Device IDs, Serial Numbers, and other identifiers can easily be spoofed or manipulated.
> - You have to be able to break any programmatic attempt for a smart, malicious USB device to circumvent #1 and #2. Requiring a conscious authorization from an Administrative user (a human, the H) is a sure-fire approach that has been proven extremely effective in other areas of privacy and security.

# All of them
## FirmUSB
### [FirmUSB: Vetting USB Device Firmware using Domain Informed Symbolic Execution](https://arxiv.org/abs/1708.09114)
> [!NOTE] **FirmUSB**
> **a USB-specific firmware analysis framework that uses domain knowledge of the USB protocol to examine firmware images and determine the activity that they can produce**
> - our work demonstrates how lifters into popular intermediate representations for analysis can be built, as well as the challenges of doing so.
> - We develop targeting algorithms and use domain knowledge to speed up these processes by a factor of 7 compared to unconstrained fully symbolic execution
> - We also successfully find malicious activity in embedded 8051 firmwares without the use of source cod

#### [SoK: "Plug & Play" Today - Understanding USB Insecurity in Versions 1 Through C](https://ieeexplore.ieee.org/document/8418652)
FirmUSB applies symbolic execution to find hidden and malicious functionalities inside the firmware
> [!NOTE] **TAKEAWAY:** Solution Integration
> ecause most existing USB defense solutions focus on a single layer, it is natural to investigate how to combine different solutions covering multiple layers. For instance, combining ProvUSB, GoodUSB, and FirmUSB provides a comprehensive defense from Human to Transport Layer, defeating most software-based attacks. Similarly, USBFirewall can act in combination with USB-FILTER to provide a powerful USB packet firewall for controlling USB device behavior while defending against exploits from malformed packets.

> [!NOTE] **TAKEAWAY:** Legacy Device Auth.
> To authenticate legacy devices, two techniques are promising, and solve the problem in different ways. USB host fingerprinting has shown the possibility of fingerprinting host machines via the USB interface using machine learning algorithms. The same idea could be applied to USB device fingerprinting, although with the pitfalls of building a robust machine learning system in an adversarial environment. FirmUSB is able to understand the USB device firmware behavior, and providing a stronger security guarantee than fingerprinting when the firmware is available. This combination of fingerprinting and firmware verification can potentially mitigate most attacks from legacy devices.

## b

## c

# **GODT [LINK](https://robbiedumitru.github.io/PDFs/DumitruBHW23.pdf)** (Samme som USB Proxy lidt længere nede)

# ML Malware
https://github.com/FA-PengFei/OOBAVD_Pub
Instead of relying on hand-crafted features which require manual analysis and updating to detect malware, OOBAVD leverages the generalization power of CNNs to detect visual similarities in the byteplot images of malware variants belonging to the same family. This allows for a high confidence in detecting novel malware, even when the model is encountering it for the first time.

To achieve this, we gathered a collection of malicious and non-malicious executables from various public datasets, converted them to byteplot images, and experimented with a variety of model architectures to find one that suits our requirements the best. Even without any significant changes to the architectures, we were able to achieve an accuracy of over 95% in the following models which were also chosen for their small sizes and low latency:

# USB/IP
## Links
- USB/IP - a Peripheral Bus Extension for Device Sharing over IP Network. Takahiro Hirofuchi, Eiji Kawai, Kazutoshi Fujikawa, and Hideki Sunahara. In the Proceedings of the FREENIX Track: USENIX Annual Technical Conference, pp. 47-60, April 2005. [**(Awarded FREENIX Track Best Paper!)**](http://www.usenix.org/events/usenix05/tech/freenix/hirofuchi.html)
- USB/IP: A Transparent Device Sharing Technology over IP Network. Takahiro Hirofuchi, Eiji Kawai, Kazutoshi Fujikawa, and Hideki Sunahara. IPSJ Transactions on Advanced Computing Systems, Vol. 46, No. SIG11(ACS11), pp. 349-361, August 2005. (Also appeared in [IPSJ Digital Courier](http://doi.org/10.2197/ipsjdc.1.394).)

## [USB Proxy](https://robbiedumitru.github.io/PDFs/DumitruBHW23.pdf)
USB can be leveraged to undermine the security of computer systems across different layers of its interface. **User-friendly, holistic security solutions have proven challenging to develop**, especially given they must be retrofitted to existing systems as add-on elements.
==**prototype USB Proxy device which brings together several protective functions for securing USB.**== The device serves as a lightweight mediator for USB connections.

**The Proxy can be configured to maintain a combination of explicitly trusted or non-trusted descriptor fields by which to filter devices that are enabled a connection toward the host, thereby implementing its own device authorisation policy**

it enforces **canonicalisation** of data transferred between a device and host, allowing only known-good behaviour. The connection **separation prevents malicious behaviour, such as bus-sniffing exploits**. It also **anonymises both ends of a connection**, providing confidentiality against profiling from either side

> [!NOTE] Useful til design?
> Virtual connection with the external device is facilitated by passing data between Proxy-host and Proxy-device. By emulating a generic device on the real device’s behalf, the Proxy canonicalises the data flows between external host and device because it strictly defines the interfaces established. Data in transit can be filtered or altered according to configured policy. Capture and storage of the data is also possible for post-use analysis.
> 
> ![[DumitruBHW23_4_Im2.png]]






## USB/IP Security(?)
### [USBIPS Framework](https://arxiv.org/abs/2409.12850)
**Regardless of the vector of a USB-based attack, the most important risks concerning most people and enterprises are service crashes and data loss**
==Although USB firewalls have been proposed to thwart malicious USB peripherals, such as USBFilter and USBGuard, they cannot prevent real-world intrusions.==

1. We first present a behavior-based detection mechanism focusing on attacks integrated into USB peripherals. 
2. We then introduce the novel idea of an allowlisting-based method for USB access control. 
3. We finally develop endpoint detection and response system to build the first generic security framework that thwarts USB-based intrusion.
**Within a centralized threat analysis framework, it provides persistent protection and may detect unknown malicious behavior. By addressing key security and performance challenges, these efforts help modern OSs against attacks from untrusted USB peripherals.**

#### Tabeller
##### Trusler
![[Pasted image 20241106160024.png]]

##### Forsvar
![[Pasted image 20241106155040.png]]
#### Intro
- Some researchers argue that software-based attacks from malicious peripherals that abuse protocol designs or exploit software stack vulnerabilities can be thwarted by building packet-layer firewalls, such as USBFilter and USBGuard, for I/O subsystte,s within OSs. However, although they can defend against attacks such as BadUSB, they can only work on Linux and need wee-trained computer engineers to input allowlisting and blocklisting policies using complex rule languages. Moreover, they do not have a central management mechanism that discourages their use in network-based environments.
- In light of the above, the central statement of this paper is that fragmented defenses cannot effectively stop attacks on any vulnerability vector.
- **This work aims to understand how to secure host machines with untrusted or even malicious modern peripherals plugged in. Specifically, this work explores how to build security solutions within OSs to thwart attacks from peripherals.** We take a step-by-step approach to verify and go beyond the paper statement by setting the following goals:
	- Understand attack vectors and methodologies
	- Find threats that pose significant risks
	- Study methods of thwarting such threats
	- **Our results include the follwing:**
		- A behaviour-based IPS named USBIPS is developed. it mainly protects against malicious USB peripherals.
		- By detecting and responding to clients persistently USBIPS can discover new threats and create releveant indicators of compromise
		- USBIPS can work practically on the wire while supporting various popular OSs
		- USBIPS clients can work online offline and the **USBIPS** server can be deployed on the same host or a remote computer.
#### Background and related works
- Given the large body of literature on this subject, we initially categorize existing attacks according to their targeted functionallity. We thus classify these functionalities into conceptual communication layers
	- By classifying functionalities into layers we can easily find similarities betwen approaches and derive primitives. Theses primitives cover both attack mechanisms (how attacks are accomplished) and attack outcomes (DoS forgery or eavesdropping). 
- A USB class is a group of one or more interfaces that merge to facilitate high-complexity functionality. Single-interface classes include the human interface device (HID) class, which enables the USB host controller to interact with mice and keyboards, and the USB mass storage class, which defines data transfer between the host and storage device

- A USB host controller detects the presence and speed of a device plugged into the host machine by checking for changes in voltage on data pins. The GetDeviceDescriptors command initiates enumeration
- where the host requests for the identifying information of the device, including its serial number, manufacturer, vendor ID (VID), and product ID [9]. The host controller resets the device and assigns an address to it for future communication. All device configurations are obtained using the GetConfigDescriptors request. A USB device has one configuration active at a time, although it can have more than one configuration. Each configuration can have one or more interfaces. These are acquired using the GetInterfaceDescriptors request and denote the vital functional entities served by various drivers in the OS. Then, GetInterfaceDescriptors finishes, drivers are loaded on behalf of the device, and class-specific subsets of the USB protocol (e.g., HID and storage) start operating.

##### Defensive measures
- USBFirewall \[86] protects the USB stack on the host by identifying malformed USB packets, such as those created using FaceDancer, using a formal protocol-syntax model.
- Cinch \[84], through virtualization, reduces the attack surface of the host; the host OS is isolated from the USB host controller by hoisting it into a VM
- **Then, USB traffic is entirely tunneled through a disposable gateway VM using an IOMMU. However, USBFirewall cannot thwart attacks such as BadUSB, and the overhead of Cinch limits its use in practice.**
#### System Design
- **==However, the recently proposed fragmented defenses cannot effectively thwart attacks on any vulnerability vector==**
##### Objectives
The services and data on the host are key assets so we pursue the following objectives:
- Establish a behaviour-based detection mechanism that focuses on abnormal intentions of the key assets
- Detect all USB devices plugged into a host, and at least recognize these devices as **HIDs**, **storage devices**, or **network adapters**
- Find IoCs and discover abnormal devices correctly by monitoring the behavior of the three types of devices individually
- Combine allowlisting- and behavior-based methods on different vectors for comprehensive protection.
- Develop a centralized management framework that can maintain the integrity of logs and support further threat analysis and persistent protection.
##### Design Principle
Based on the abovementioned objectives, our research is based on the following design principles:
- Detect and classify attached devices as HIDs, storage devices or network adapters
- use an allowlist to filter these devices by checking descriptor information
- perform behavior-based detection.
	- **HID:** ensure that the Captcha input from the detected device is correct.
	- **storage:** find illegal file access events relevant to specific paths.
	- **Network**: monitor configuration changes, and find abnormal DNS query results
##### Methodology
we explain the structure and components of the proposed framework. and illustrate how it can thwart USB-based attacks through behavior-based methods.
- When a device is plugged into a computers USB interface, an interrupt is triggered such that the processor responds to an event that needs attention from the software. The USB specification in the kernel space of an OS involves three layers of software abstraction
	- The host controller interface (**HCI**), the lowest level, configures and interacts with the host controller hardware through a local bus (e.g., PCIe) an HCI driver is specific to the hardware interface of the host controller but exposes hardware independtent abstraction to the following software layer (core). 
	- **The core** handles power management and device addressing and exposes an interface used by high-level drivers to communicate with devices. The core also enumereates a device that is plugged in, which requires identifying ut and activating its driver.
	- **Class drivers**, the upper most layer, are high-level drivers  that communicate with device functions. an interface is provided between USB devices and the rest of the OS by these drivers. For instance, the class driver of a keyboard communicates with the input subsystem of the kernel. A mass storage class driver, which communicates with the storage subsystem on the kernel, is another example.

==The USBIPS client collects and encodes the descriptor information of devices by interacting with kernel modules using the Win32 API on Windows. Therefore, behavior-based mechanisms can be used to thwart USB-based attacks.==
**We explain the system components in the following subsections:**
- a device classifier, an allowlisting-based access controller, 
- a behavior-based detector (
	- HID behavior observer, 
	- illegal storage access behavior detector, 
	- and illegal network usage detector, 
- and DAEMON and service observer
**Another critical component, the USBIPS server, is an EDR-based analysis center**. **==It is a collection of multiple functions divided into four components:==** 
- The server monitors the status and controls the versions of USB clients, collection logs, and analysis logs. It updates and distributes allowlists and behavior rules that provide all UPBIPS clients a central management mechanism.
	- the client status monitor, 
	- log analyzer, 
	- allowlist manager, 
	- and behavior rule manager. 
##### USBIPS Device Classifier


#### Conclusion

|                                    | USBIPS                | USBfilter/LBM      | FirmUSB                                 | Cinch                                       |
| ---------------------------------- | --------------------- | ------------------ | --------------------------------------- | ------------------------------------------- |
| **Defense Surface**                | Application/Transport | Transport          | Transport                               | Transport                                   |
| **Defense against BadUSB attacks** | All USB ports         | Specified USB port | Impractical, requiring extra facilities | Not real-time and requires extra facilities |
| **Behavior Detection**             | Yes                   | No                 | No                                      | Yes                                         |
| **Support OS**                     | Windows               | Linux              | Platform independent                    | Linux                                       |
| **Central Management**             | Yes                   | No                 | No                                      | No                                          |

##### Limitations
- A lack of defense surfaces
- Behavior rule update mechanism
- protection ranges
1. **Software layer depth:**
	1. As USBIPS was developed using the Windows API, a USBIPS client detects and controls a USB device after the driver is loaded. Thus, USBIPS may fail to block malicious behavior in an earlier stage. For example, by the time a USBIPS client detects illegal storage access behavior, the files will have almost finished read or write activities. USBIPS blocks these activities by deleting the copied files after the corresponding write activities are finished.
2. **Challenges in updating rules for new IoCs:**
	1. We did not create a detection method for storage and network devices as standardized rules; this makes it difficult for USBIPS clients to update behavior rules. Besides, an HID detection method that needs interactions with users is hard to regard as a standard rule and difficult to update. When a new IoC is found, the easiest way to update the behavior-based detection mechanism presently is to update the entire software of the USBIPS client. Moreover, these required interactions may cause some users to feel confused and helpless. When the HookingRawInput window pops up, the keystrokes of all keyboards are blocked. Even keystrokes from a newly detected true keyboard that does not match the Captcha will not return any response to any application in a host. A user may interpret this as a system/application error and may restart the host. Although this is an effective way to thwart USB keyboard spoofing attacks, it also disturbs users who are using true keyboards.
3. **Challenges in thwarting attacks via other devices:**
	1. The detection methods of the proposed system were developed individually according to different devices. It is not easy to find methods for all kinds of devices. Moreover, the detection method for HIDs only focuses on keyboard behavior when many other breaches may be generated for other HIDs. For example, an attacker may use a spoofed mouse to move a cursor to a specific application and implement double-click instructions to perform malicious behavior, such as stealing a file from a host to a flash drive or shutting down a DHCP service on a server. Another possible case is that an attacker can record a user’s voice or obtain pictures without alerting the user by using a spoofed webcam that resembles a USB flash drive. Effective solutions have yet to be developed to overcome such problems.
##### Future work
###### 1) Development of USBIPS client in driver layer
If developed using Windows Minifilter, USBIPS can control a device before its driver is loaded, thus improving the aforementioned file-blocking mechanism. Moreover, other features of abnormal behavior may be identified from unusual contents in USB packets.
###### 2) Standardization of rules
A method of converting the detection methods for storage and network devices to standardized rules, such as YARA rules, should be devised. This will help the USBIPS server update the behavior-based detection methods easily by only distributing new rules to clients. In addition, additional rule-based detection methods for HIDs that will not disturb users should be developed. In general, a user should have similar HID usage habits, such as the frequency of using a specific HID, and actions before and after a specific HID is plugged into a host. Therefore, developing a behavior-based detection mechanism using machine learning techniques may be a feasible way to enhance USBIPS.
###### 3) Grouping of devices and relevant detection methods
A short-term solution to breaches coming from different types of USB devices is to analyze similarities between various devices and identify general detection methods that suit these devices. In the long run, a machine learning–based mechanism may be developed.

##### Closing words / conclusion
- a framework that works on the defense surface of the application layer can protect a host from BadUSB attacks effectively
- Most existing solutions work in the transport layer, whereas USBIPS combines the defense surface of the transport and application layers while performing allowlisting-based access control before behavior-based detection
- A USBIPS client can work both online and offline, and a USBIPS server can be deployed on the same host or on a remote computer.
- the centralized management mechanism of USBIPS enables a system to manage clients easily and handle events instantly.
	- Furthermore, it provides persistent protection to a large number of hosts and may detect unknown malicious activity
### [Defending Against Malicious USB Firmware with GoodUSB](https://dl.acm.org/doi/abs/10.1145/2818000.2818040)
Rather than using USB devices solely as a delivery mechanism for host-side exploits, **attackers are targeting the USB stack itself, embedding malicious code in device firmware to covertly request additional USB interfaces**, providing unacknowledged and malicious functionality that lies outside the apparent purpose of the device.

**We observe that the root cause of such attacks is that the USB Stack exposes a set of unrestricted device privileges** and note that the most reliable information about a device's capabilities comes from the end user's expectation of the device's functionality.

### [USB-Watch: A Dynamic Hardware-Assisted USB Threat Detection Framework](https://link.springer.com/chapter/10.1007/978-3-030-37228-6_7)
SE også: **[Dynamically detecting USB attacks in hardware: poster](https://dl.acm.org/doi/abs/10.1145/3317549.3326315)**

The USB protocol is among the most widely adopted protocols today thanks to its plug-and-play capabilities and the vast number of devices which support the protocol. **To address these concerns, in this work, we introduce a novel hardware-assisted, dynamic USB-threat detection framework called USB-Watch.**

==**utilizes hardware placed between a USB device and the host machine to hook into the USB communication, collect USB data, and provides the capability to view unaltered USB protocol communications. This unfettered data is then fed into a machine learning-based classifier which dynamically determines the true nature of the USB device.**==



### [USBESAFE: An End-Point Solution to Protect Against USB-Based Attacks]
==the introduction of BadUSB attacks has shifted the attack paradigm tremendously. Such attacks embed malicious code in device firmware and exploit the lack of access control in the USB protocol==

USBESAFE works well in practice by achieving a true positive \[TP\] rate of 95.7% with 0.21% false positives \[FP\] with latency as low as three malicious USB packets on USB traffic

We tested USBESAFE by deploying the model at several end-points for 20 days and running multiple types of BadUSB-style attacks with different levels of sophistication. Our analysis shows that USBESAFE can detect a large number of mimicry attacks without introducing any significant changes to the standard USB protocol or the underlying systems. The performance evaluation also shows that USBESAFE is transparent to the operating system, and imposes no discernible performance overhead during the enumeration phase or USB communication compared to the unmodified Linux USB subsystem.



# Nogle ting

![[Pasted image 20241106154124.png]]

| Layer         | Defensive primitives          | Defense                                                                       |
| ------------- | ----------------------------- | ----------------------------------------------------------------------------- |
| ==Human==     | Security Education            | Government notices, Education materials                                       |
| ==Human==     | On-device data encryption     | IronKey, Kanguru                                                              |
| ==Human==     | On-device host auth           | Kells, ProvUSB                                                                |
| ==Human==     | Host or device-based auditing | System provenance, Transient provenance, ProvUSB                              |
| Application   | System Hardening              | AutoRun shutdown, Metascan, Olea, Windows CE, TMSUI, Smart Blocker, USBFilter |
| Application   | Device emulating honeypots    | Ghost                                                                         |
| Application   | Driver-based access controls  | GoodUSB                                                                       |
| ==Transport== | Firmware verification         | IronKey, FirmUSB, ProXray, Viper                                              |
| ==Transport== | USB stack fuzzing             | USB fuzzing, HW-based fuzzing, vUSBf, Syzkaller, POTUS, USBFuzz               |
| ==Transport== | USB packet firewall           | USBFilter, USBGuard, USBFirewall, Linux (e)BPF Modules (LBM)                  |
| ==Transport== | Host emulating honeypots      | GoodUSB, SandUSB, Cinch                                                       |
| Physical      | Antifingerprinting            | USB host fingerprinting                                                       |
| Physical      | Secure channel                | Cinch, UScramBle                                                              |


| Layer         | Offensive primitives  | Attack                                                                                                                 |
| ------------- | --------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| ==Human==     | Outsider threats      | Social Engineering, Planted USB drives, USB flas drives as social eng. attack vector                                   |
| ==Human==     | Insider threats       | Data breach via USB sticks, Theft of encrypted USB stick, Manning leak of classified records, Documnet smuggling       |
| Application   | Code injection        | BRAIN virus, Stuxnet, Conficker, Flame, Duqu virus                                                                     |
| Application   | Data extraction       | Webcam extraction, Audio extraction, USBee, TURNIPSCHOOL                                                               |
| ==Transport== | Protocol masquerading | USB rubber ducky, USBdriveby, TURNIPSCHOOL, USB bypassing tool, BadUSB, Hermes                                         |
| ==Transport== | Protocol corruption   | FaceDancer, UMAP2, Syzkaller                                                                                           |
| Physical      | Signal eavesdropping  | Smartphone USB exploits, Side-channel attacks, BadUSB hub, USB fingerprinting, USBSnoop, CottonMouth, USB GPS locator, |
| Physical      | Signal injection      | USBKill, Bad-quality USB cables, USBee, TURNIPSCHOOL                                                                   |
