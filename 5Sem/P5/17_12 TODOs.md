EvolutionRaspRobin [link](https://www.huntress.com/blog/evolution-of-usb-borne-malware-raspberry-robin)
MicrosoftRaspRobin [link](https://www.microsoft.com/en-us/security/blog/2022/10/27/raspberry-robin-worm-part-of-larger-ecosystem-facilitating-pre-ransomware-activity/)
 ???????? [link](https://www.linkedin.com/video/live/urn:li:ugcPost:7099788852722077697/)

```javascript

console.log('Posting test files to:', featureExtractorAddress);
const testFilePath = fs.realpathSync('test/mspaint.exe');
const fileData = fs.readFileSync(testFilePath);
var fileStream = fs.createReadStream(testFilePath);

const testFilePathTwo = fs.realpathSync('test/SnippingTool.exe');
const fileDataTwo = fs.readFileSync(testFilePathTwo);
var fileStreamTwo = fs.createReadStream(testFilePathTwo);

  

const fileInput = {
            files: [
                {fileName: 'mspaint.exe', path: testFilePath, data: fileData, stream: fileStream },
                {fileName: 'SnippingTool.exe', path: testFilePathTwo, data: fileDataTwo, stream: fileStreamTwo }
            ],
        };

	var formData = new FormData();
    fileInput.files.forEach(file => {
        formData.append('file', file.stream, file.data, file.fileName);
    });
    
        
```
# MAIN LIST
- [ ] Gennemgå TensorFlow scriptet
- [ ] Lav Microservices
- [x] **Problemformulering Bullshit**
- [ ] **Design**
- [ ] **Kubernetes**
- [ ] Scriptshit
	- [ ] Nixos builder
	- [ ] Configger
- [ ] Disassembler

The USB protocol describes 18 different classes of standard devices, encompassing a wide range of functions and capabilities. To streamline the scope of analysis and testing, it was essential to focus on a narrower subset of devices that represent both the most prevalent usage scenarios and the most significant security risks. Mass Storage Devices (MSDs) and Human Interface Devices (HIDs) were selected for this project due to their ubiquity and their attractiveness as attack vectors.

Mass Storage Devices, such as USB flash drives and external hard drives, are among the most commonly used USB peripherals. They often carry sensitive data and are a frequent conduit for malware, as malicious code can be easily embedded in files or the device's firmware. Attackers frequently target MSDs for data exfiltration, system compromise, or even bootloader manipulation.

Similarly, Human Interface Devices, such as keyboards and mice, are integral to user interaction with computers and are nearly always connected in everyday usage. HIDs are particularly risky from a security perspective because they can be leveraged by attackers to execute unauthorized commands via techniques like keystroke injection or emulated device impersonation. These attacks exploit the trust systems inherently place in HIDs, making them a high-value target for malicious actors.

By narrowing the focus to MSDs and HIDs, the project concentrates on device classes that are both widely used and disproportionately targeted by attackers, ensuring the analysis has the greatest practical impact while maintaining manageable complexity.
## Priority
1. Microservices
2. A little scriptshit
3. problemformulering

As such, the initial focus was placed on \textbf{Mass Storage Devices} and \textbf{Human Interface Devices} due to their widespread use and the potential they offer attackers.
## Problemformulering
- How can different USB-borne attacks be defended against without rewriting the USB protocol?
	- Can some of the computation be offloaded to the cloud without too much overhead cost?
	- Can machine learning algorithms be leveraged to protect against such attacks, and, if so, which and how?


# Evolution of Malware
## [Statistics about Malware](https://www.av-test.org/en/statistics/malware/)
## [The MalSource Dataset: Quantifying Complexity and Code Reuse in Malware Development](https://ieeexplore.ieee.org/abstract/document/8568018)
we analyze the evolution of malware from 1975 to date from a software engineering perspective. We analyze the source code of 456 samples from 428 unique families and obtain measures of their size, code quality, and estimates of the development costs (effort, time, and number of people). Our results suggest an exponential increment of nearly one order of magnitude per decade in aspects such as size and estimated effort, with code quality metrics similar to those of benign software. We also study the extent to which code reuse is present in our dataset. We detect a significant number of code clones across malware families and report which features and functionalities are more commonly shared. Overall, our results support claims about the increasing complexity of malware and its production progressively becoming an industry.

# Ting at gøre rundt omkring

### **PLACER DEM HER:**
- [ ] [Cinch](https://www.usenix.org/sites/default/files/conference/protected-files/security16_slides_angel.pdf)
	- [ ] [endnu et link](https://www.usenix.org/conference/usenixsecurity16/technical-sessions/presentation/angel)
- [ ] [usbsas](https://github.com/cea-sec/usbsas?tab=readme-ov-file) 
#### HID section i State???
- [Dataset of human-written and synthesized samples of keystroke dynamics features for free-text inputs](https://www.sciencedirect.com/science/article/pii/S2352340923002445#bib0006)
- [Keystroke dynamics as a biometric for authentication](https://www.sciencedirect.com/science/article/pii/S0167739X9900059X)
- [Implementation and Analysis of Keyboard Injection Attack using USB Devices in Windows Operating System](https://www.semanticscholar.org/paper/Implementation-and-Analysis-of-Keyboard-Injection-Ramadhanty-Budiono/2754f26d0edc96147a343e8c7bad63fbfc8ee649)
- [Time-Print: Authenticating USB Flash Drives with Novel Timing Fingerprints](https://www.semanticscholar.org/paper/Time-Print%3A-Authenticating-USB-Flash-Drives-with-Cronin-Gao/6d9c41360a1b7843035e39806e6d9b4c15385bc7)
- 
## Problemanalysis
### State actors osv...
## Background
### Cloud shit

### Products for defense > hardware
#### USG
ss
#### eLock USB HID filter
s
## State
### Cloud Security
Se den [her](https://dl-acm-org.zorac.aub.aau.dk/doi/pdf/10.1145/2431211.2431216) plus de andre faner i cloud gruppen
## Design


# Write stuff
## VM shit
### \subsection{Virtual Machines}  
Virtual machines (VMs) provide much utility in modern computing environments by enabling the abstraction of physical hardware. They allow multiple operating systems to run on a single physical host, each isolated from the others. This isolation adds a layer of security, as processes running within one virtual machine are contained to it and cannot directly interact with the host system or other VMs.

Virtual machines can be used as simulated environments, where suspected files and code can be allowed to run and monitored. As such, processes can be put under closer scrutiny, analyzing their interactions with the environment and what network or API calls they make.

VMs can be used as simulated environments, allowing for analysis of potentially malicious files. By executing and monitoring these processes in an isolated virtual environment, their behavior can be scrutinized. Interactions with the operating system, as well as network activity, and API calls can observed without risking the integrity of the host machine.

**However, the use of virtual machines is not without risks. Advanced attackers can adapt their malicious code to detect when it is being executed in a virtualized environment. Upon detection, the malware may alter its behavior to evade analysis or even remain dormant until executed in a non-virtualized system. Additionally, vulnerabilities in hypervisors—the software managing virtual machines—can lead to a phenomenon known as "VM escape," where an attacker gains access to the host or other VMs running on the same physical hardware.**


Stripped down virtualizations of operating systems can be used to run several lightweight instances, such that computing power can be effectively delegated between different applications, and allow for scaling and balancing depending on resource use. Theses lightweight virtualizations, Containers, can ssssssssssssssssssssssssssssssssssss.

Containers represent a more stripped-down form of virtualization, utilizing lightweight bare-essentials instances of virtual machines. Unlike virtual machines, which emulate an entire operating system, containers share the host's kernel, making them more resource-efficient. This efficiency allows for rapid deployment, dynamic scaling, and effective resource utilization, enabling applications to run consistently across environments.

The ability to spin up multiple containers introduces challenges in management, particularly as containerized environments grow in size and complexity. Kubernetes, an open-source orchestration platform, addresses these challenges by automating the deployment, scaling, and management of containers. It can manage clusters of containers, controlling their creation and deletion, distributing resources like CPU and memory, and maintaining system reliability through duplication and failover mechanisms. Kubernetes also facilitates container networking, allowing seamless communication between services while maintaining isolation where needed.

By combining containers with Kubernetes, organizations can build scalable, resilient, and efficient cloud-based systems, meeting the demands of modern applications while maintaining control over complex infrastructures.
### LOOK AT THESE FIRST:
#### MORE SHIT
- [VM escape](https://www.techtarget.com/whatis/definition/virtual-machine-escape?utm_source=chatgpt.com)
- [Understanding VM Escape: Risks and Precautions](https://spyboy.blog/2024/09/17/understanding-vm-escape-risks-and-precautions/?utm_source=chatgpt.com)
- [Advantages of Kubernetes-native security](https://www.redhat.com/en/topics/containers/advantages-of-kubernetes-native-security?utm_source=chatgpt.com)
- [Kubernetes and Container Security](https://benpournader.medium.com/kubernetes-and-container-security-146b4dc7c742)
- [The good and the bad of kubernetes container orchestration](https://www.altexsoft.com/blog/kubernetes-pros-cons/?utm_source=chatgpt.com)
- [What is Orchestration Security?](https://www.paloaltonetworks.com/cyberpedia/what-is-orchestration-security?utm_source=chatgpt.com)
- 
---- 

- [Security in cloud computing: Opportunities and challenges](https://www.sciencedirect.com/science/article/abs/pii/S0020025515000638)
-  Crazy hvis du kan forstå den... [An Access Control Model for Preventing Virtual Machine Escape Attack](https://www.mdpi.com/1999-5903/9/2/20)
- 
### [Virtual Machine Security Best Practices](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.security.doc/GUID-14CCC8CD-D90D-4227-B2C3-0A93D3C023BA.html)
### Virtualization: Issues, Security Threats, and Solutions
### [Security in cloud computing: Opportunities and challenges](https://www.sciencedirect.com/science/article/abs/pii/S0020025515000638)

### [An Access Control Model for Preventing Virtual Machine Escape Attack](https://www.mdpi.com/1999-5903/9/2/20)

### [A Misuse Pattern for Compromising VMs via Virtual Machine Escape in NFG](https://dl-acm-org.zorac.aub.aau.dk/doi/abs/10.1145/3339252.3340530)
### [Elevated Penetration Attack Models of Virtual Machine Escape Based on FSM](https://publications.eai.eu/index.php/sesa/article/view/40)

### [A Survey on Virtual Machine Security](https://www.cs.umd.edu/class/fall2017/cmsc414/readings/vm-security.pdf)

### [A survey of security issues for cloud computing](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S1084804516301060)


## Cinch
### Dangers
- Peripherals' firmware can be modified with BadUSB (ref nohl and lell, black hat 2014)
- Government agenvies intercept and modify shipments (ref: Glenn Greenwald, The Guardian 2014)
#### Ways your system can be exploited
- Peripherals can exploit driver vulnerabilities.
	- 13 vuln in linuxs USB stack reported in 2016 alone
- Can leverage DMA to attack OSes
	- Inception (Maartmann-Moe 2014), Funderbolt (Black Hat 2013)
- Peripherals can lie about their identity
- **ANOTHER PROBLEM:** Hubs broadcast messages downstream (in usb 2.0 and below) compromised huns can eavesdrop and modify all traffic.

> [!NOTE] **Cinch:** brings network defenses to USB
> - Effective (but not perfect) against the threats described
> - Is portable and backwards-compatible
> 	- Works transparently accross OSes
> 	- Requires no driver or USB protocol modifications
> - Seperates the bus from your machine and create an enforcement point
### What to do?
- awareness doesnt work
- **we want to control interactions**
	- so take inspo from TCP/IP, and apply network security tools to peripheral buses

### How do we build Cinch?
 Easy idea: Attach devices to another machine
but this requires an additional machine....
**pragmatic choice:** leverage virtualization tech to instantiate the (sacrifical) **machine on the same hardware**


See click modular router (Kohler et al., ACM TOCS 2000)
### Whate defenses can be built on Cinch?
1. Enforcing allowed device behavior
	1. Constraints on: packet formats, individual fields, packet sequences.
	2. Used to built state machine
	3. allow / drop packet
2. Filtering known exploits
	1. Download / Populate DB with known malicious signatures
	2. Plus: quick response to an attack
		1. Deriving a signature is usually faster than understanding the explout and finding the root cause
	3. plus: useful for closed-source OSes
		1. no need to wait for OS vendor patch vulnerability
	4. minus: we need signature, so doesnt help against 0-day
	5. minus: tension between protection and compatibility
3. Authentication and encryption
	1. 

### How well do defenses work and what are their costs?
#### Implementation details
- Hypervisor is linux running qemu/kvm
- enforcer is linux userlevel proces written in rist
- USb transfers are encapsulated/decapsulated in TCP/IP
- We built the TLS adapter on a beaglebone Black (arm-based computer)
- we implement exploits using a facedancer21
#### effectiveness
- 3 ways 
####