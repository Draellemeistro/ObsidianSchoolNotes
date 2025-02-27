# Threats / Attacks
## Application Layer
## Transport Layer
## Physical Layer

# Defense
Many propositions have been made to combat the vulnerabilities of the USB protocol. Prototypes and commercial solutions, both software based and as external hardware, have been shown to achieve varying degrees of effectiveness. However, the differing scopes and objectives showcase the perplexing landscape of USB-oriented defense.

> [!NOTE] Skal slettes, men er i rapporten
> **Products available:**
> - [ ] USG Hardware Firewall
> - [ ] Armadillo Hardware Firewall
> - [ ] eLock USB HID Filter
> **Not available?**
> - [ ] USB Sentry
> - [x] USBESAFE
> - [ ] USB-Watch ([link1](https://csl.fiu.edu/wp-content/uploads/2023/05/usb_watch_kyle.pdf), [link2](https://www.researchgate.net/publication/337952507_USB-Watch_A_Dynamic_Hardware-Assisted_USB_Threat_Detection_Framework))

While defensive tools can, in essence, be boiled all the way down to the categories of internal software and external hardware, it also obfuscates a lot of important detail. Viewing them through the lens of the network stack\cite{SoKHistUSB}, same as the attack-vectors, allows for more direct comparisons between the two.


> [!NOTE] New text
> ==The creators behind **USBFilter** plainly describes the problems with the USB protocol  as allowing unlimited capabilities with no authentication, exacerbated by the emergence of BadUSB==
link [powerpoint](https://www.usenix.org/sites/default/files/conference/protected-files/security16_slides_tian.pdf)

econd, further
static analysis methods can be introduced to the USB-Watch
framework, as dynamic methods cannot cover all potential
threats. Merging both dynamic and static analyses into the
USB-Watch framework would create a truly smart USB host
controller that can prevent malicious USB behavio
## Physical Layer
## Transport Layer
USBESAFE, USB-Watch, 
### OOBAVD: Out-Of-Band Anti-Virus Dock
OOBAVD stands for "Out-Of-Band Anti-Virus Dock". It is as a proof-of-concept and work-in-progress solution designed to protect air-gapped systems from USB-based attacks. It protects the host by acting as an intermediary middleman between the air-gapped system and USB-devices. It works by scanning USB devices for malicious files using Convolutional Neural Network (CNN) machine learning model to detect malware by analyzing byteplot images of files. The developers of OOBAVD made use of a Raspberry Pi 4B to act as the proxy intercepting the data from the USB-drive. The developers prioritised ease of use and simplicity to avoid complicating the act of using the solution, to a point where it would hinder the work of the operators. 
### USB Proxy
https://robbiedumitru.github.io/PDFs/DumitruBHW23.pdf
In USB Proxy\cite{USBProxyPaper}, a prototype is built with the primary focus on HID-devices, such as keyboard and mouse. It can be configured to black- or white-list a combination of specific descriptor fields, and presents to the host a generic HID descriptor set. Packets transmitted to the host contain only input packets, and the proxy performs a size check on this data. As thus, they argue that it delivers device and data filtering, interface normalization, a level of anonymization between host and HID-device as well physical separation to prevent bus sniffing.
## Application Layer
### Expanding the Operating Systems Defensive Capabilities
**USBGuard**: white/blacklisting, **USBFilter**: USB layer firewall for Linux kernel
### USBIPS Framework
An argument is made, that data loss and service crashes are the risks of most importance to most people and businesses. Noting that management of USB peripherals is relegated to the hosts operating system, BadUSB is mentioned as a malicious peripheral that can pose those risks.

Since physical USB-focused firewalls can't necessarily prevent physical intrusions, USBIPS proposes a security framework for the OS to defend against malicious USBs and intrusions
### GoodUSB