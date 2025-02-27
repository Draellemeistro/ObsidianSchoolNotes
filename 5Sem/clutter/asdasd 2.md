# Malicious USB Devices

### 1. **Threats from USB Devices:** 

> [!NOTE] **Threats from USB Devices:**
> <span style="color:rgb(255, 0, 0)">USB-based attacks exploit user trust and curiosity. Examples include malware-infected flash drives and keystroke injection devices.</span>
> 
> <span style="color:rgb(255, 0, 0)">Nation-state actors and small hacking groups increasingly use USB devices for sophisticated attacks.</span>

USB devices exploit inherent trust in a widely used technology. Studies, like one from the University of Illinois, show that 45–98% of people plug in unknown USB drives, driven by curiosity or altruism. Attackers capitalize on this trust for phishing, malware injection, or data theft.
### 2. **Examples of Malicious USB Tools:**

> [!NOTE] **Examples of Malicious USB Tools:**
> - **BadUSB:** <span style="color:rgb(255, 0, 0)">Reprogrammed USB devices that execute hidden malicious functions.</span>
> - **Rubber Ducky:** <span style="color:rgb(255, 0, 0)">Performs rapid keystroke injections to execute scripts.</span>
> - **Bash Bunny:** <span style="color:rgb(255, 0, 0)">Mimics multiple USB device types to execute tailored payloads.</span>

###### **BadUSB:** 
Reprograms a USB device’s firmware to emulate a trusted peripheral, enabling covert control or data exfiltration without the user’s knowledge.
###### **Rubber Ducky:** 
A commercial tool that mimics a keyboard, executing a series of pre-programmed keystrokes at high speed, useful for tasks like opening backdoors or downloading malware.
###### **Bash Bunny:** 
A versatile tool that emulates devices such as flash drives or Ethernet adapters, supporting multiple payloads on different platforms.
### 3. **Accessibility of Malicious Tools:** 
Microcontrollers such as Arduino or Teensy, priced as low as $5, can be programmed to simulate USB devices, including keyboards or mice, making them attractive for both ethical and malicious hackers. These programmable microcontrollers are simple to program yet powerful in their potential misuse.

---

# General Malware Detection and ML for Malware Detection
### 1. **Datasets:**
> [!NOTE] **Datasets**
> <span style="color:rgb(255, 0, 0)">Numerous datasets like EMBER, Virus-MNIST, and BODMAS provide labeled malware and benign files, aiding in training models.</span>
###### **EMBER Dataset:** 
Offers over 1.1 million samples for malware and benign software detection using static analysis.
###### **Virus-MNIST:** 
A specialized dataset converting malware code into image format for classification.
###### **MOTIF:** 
Focuses on maintaining clean family labels and metadata for malware samples, aiding precise evaluation
### 2. **Data Preparation and Model Training:**
> [!NOTE] **Data Preparation and Model Training**
> - <span style="color:rgb(255, 0, 0)">Data preprocessing (e.g., feature extraction, balancing datasets with SMOTE).</span>
> - <span style="color:rgb(255, 0, 0)">Use of supervised machine learning for malware classification, with metrics like ROC-AUC to evaluate performance.</span>

2. **Advanced Techniques:**
    - **Image-based Malware Classification:** Image datasets like Virus-MNIST allow for CNN-based detection.
    - **Sequential Analysis with LSTMs:** Useful for analyzing patterns in keystrokes or other time-series data.
3. **Applications of Preprocessing:**
    - Transformations like static feature extraction enable scalable and efficient model training, even on limited dataset
- Class imbalance is a challenge in malware datasets. Techniques like **SMOTE (Synthetic Minority Oversampling Technique)** are employed to generate synthetic examples of benign files, ensuring balanced training.
- Feature selection, such as using Random Forest importance scores, reduces redundancy, optimizing model performance and preventing overfitting.
### 3. **Advanced Techniques:**
LSTMs (Long Short-Term Memory Networks) were utilized for keystroke injection detection. The model analyzes sequences of keystrokes (hold times, flight times, and key codes) to identify patterns typical of human typing versus injection attacks.

---
# Kubernetes Setup in the Cloud
### 1. **Containerization Benefits:**
> [!NOTE] **Advantages of Containerization:**
> - <span style="color:rgb(255, 0, 0)">Lightweight and efficient virtualization compared to traditional VMs.</span>
> - <span style="color:rgb(255, 0, 0)">Facilitates scaling and testing in different environments</span>

- Containers offer lightweight isolation of processes compared to virtual machines, sharing the host OS kernel but maintaining application-specific dependencies.
- Kubernetes enables scaling, load balancing, and network management across containerized services, crucial for handling tasks like malware analysis in the cloud.
### 2. **Minikube Implementation:**
> [!NOTE] **Kubernetes Cluster**
> - <span style="color:rgb(255, 0, 0)">Deployed using **Minikube** for simplicity and low resource consumption.</span>
> - <span style="color:rgb(255, 0, 0)">Single-node cluster adequate for project needs but scalable to more robust systems (e.g., Docker Swarm, production-level Kubernetes) for commercial deployment.</span>

- Minikube was chosen for its simplicity in managing a Kubernetes cluster. While only supporting single-node clusters, it provided the necessary environment for container orchestration and testing.
- Alternatives like Docker Compose were considered but found less adaptable for scaling to multi-node setups, which may become necessary for future commercial iterations.

---
# Future Implementations
> [!NOTE] **Future Implementations**
> 1. **Enhanced Datasets:** <span style="color:rgb(255, 0, 0)">Incorporate more diverse benign and malicious samples to improve detection capabilities.</span>
> 2. **Remote NixOS Build:** <span style="color:rgb(255, 0, 0)">Explore secure and reproducible software builds for further protection.</span>
> 3. **Lightweight Checks:** <span style="color:rgb(255, 0, 0)">Implement faster and more efficient malware detection techniques suitable for real-time analysis.</span>
> 4. **Modular Components:** <span style="color:rgb(255, 0, 0)">Design modular and extensible systems for easier updates and feature enhancements.</span>

### 1. **Enhanced Datasets:**
Future work involves integrating datasets with broader coverage, such as obtaining additional benign software samples to complement the extensive malicious datasets, filling the gap identified during this project.
### 2. **Remote NixOS Build:**
Leveraging **NixOS** for building software in a secure, reproducible manner could simplify deploying updated models and backend services. This approach emphasizes immutability and consistency across environments.
### 3. **Lightweight Malware Detection:**
Proposals include optimizing real-time malware scanning with edge computing to minimize latency, allowing faster USB device validation at the point of use.
### 4. **Modular System Design:**
The project envisions modularizing components like the keystroke injection and malware classifiers. This would allow independent updates or upgrades without disrupting other system functionalities.




----
# The shabang
### Malicious USB Devices
Andreas

**Malicious USBs on the rise**: Nation-state actors and small hacking groups increasingly use USB devices for sophisticated attacks

**Reason for effectiveness:** USB-based attacks exploit user trust and curiosity.

**Usual suspects:** Examples include malware-infected flash drives, Autorun exploits keystroke injection devices.

**BadUSB**: Reprogrammed  firmware to emulate a trusted peripheral, while secretly executing malicious actions

**Programmable MCs:** 
**--- Easy/cheap Access:** Arduino etc. are priced very low and can be programmed to simulate various USB devices. They can be simple to program while being quite capable for misuse.

**Electrical:** Damage the system with high-voltage electrical current.

Pictured are:
### General Malware Detection and ML for Malware Detection
**The Typical Approach:** Most often using signatures of known malicious patterns. Identify suspicious behavior or characteristics in code that might indicate malware.

**VirusTotal**: Compare results from multiple antivirus services. Good for malware checks, not designed for real-time protection or new / advanced ssssssss

**MLAI**
May possibly become able to recognize patterns and similarities, which otherwise wouldn’t be detected by typical rules or signature matches.  
Can be implemented in different ways and areas.
**Standard / static**: Headers, patterns in bytes ………….
**Dynamic:** Anomaly detection, like odd API calls or network connections
**datasets**
Many datasets with varying compositions of data. Easily highlighted by the amount of malware-families, and choice of benign inclusion.
**Also** goes beyond, to how features are extracted from files and which features are available.

**Example**: Virus-MNIST takes inspiration from the classic MNIST dataset, and formats the binaries into images for use in computer vision
### Kubernetes Setup in the Cloud
Offload to minikube cluser for scalability

Essentially, as is, it is the simplest most straight-forward implementation, but kubernetes allows for the potential to scale
also, some hypothetical / **theoretical isolation security features**

**We wanted to try at setting up virtual machines** in the cluster, which could also be leveraged for the possible implementation of dynamic testing. Also better isolation in theory.

**Persistent Volumes** could have been leveraged to store  potentially malicious files
### Future Implementations
Andreas  
**Datasets**: Explore ways to improve detection capabilities. Choices in Feature selection depend alot on what kind of dataset is provided. through use of more diverse benign and malicious samples. Expanding the datasets to include more real world benign data and a broader range

of real-world malicious files could enhance the classification accuracy  

**NixOS**: Since the nix device will interact with many potentially malicious devices, implementing the capability of automatic rebuilds after or before use could automate cleaning, and allow for the ability to configure how it should function. With remote building that process can be removed from the device

**Checks**: Light and efficient detection processes on-device would be suitable for real-time analysis, but could also help to filter out clear malignance without communication with the cloud.

**Håndter infected USB (format osv.)**  
**Implementer mus**
