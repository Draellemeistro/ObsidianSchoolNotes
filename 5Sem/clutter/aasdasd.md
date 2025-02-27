### Malicious USB Devices


1. **Threats from USB Devices:** 
    - USB devices exploit inherent trust in a widely used technology. Studies, like one from the University of Illinois, show that 45–98% of people plug in unknown USB drives, driven by curiosity or altruism. Attackers capitalize on this trust for phishing, malware injection, or data theft.
2. **Examples of Malicious USB Tools:**
    - **BadUSB:** Reprograms a USB device’s firmware to emulate a trusted peripheral, enabling covert control or data exfiltration without the user’s knowledge.
    - **Rubber Ducky:** A commercial tool that mimics a keyboard, executing a series of pre-programmed keystrokes at high speed, useful for tasks like opening backdoors or downloading malware.
    - **Bash Bunny:** A versatile tool that emulates devices such as flash drives or Ethernet adapters, supporting multiple payloads on different platforms.
3. **Accessibility of Malicious Tools:**
    - Microcontrollers such as Arduino or Teensy, priced as low as $5, can be programmed to simulate USB devices, including keyboards or mice, making them attractive for both ethical and malicious hackers. These programmable microcontrollers are simple to program yet powerful in their potential misuse.

---

### General Malware Detection and ML for Malware Detection

1. **Datasets:**
    
    - **EMBER Dataset:** Offers over 1.1 million samples for malware and benign software detection using static analysis.
    - **Virus-MNIST:** A specialized dataset converting malware code into image format for classification.
    - **MOTIF:** Focuses on maintaining clean family labels and metadata for malware samples, aiding precise evaluation
2. **Data Preparation and Model Training:**
    
    - Class imbalance is a challenge in malware datasets. Techniques like **SMOTE (Synthetic Minority Oversampling Technique)** are employed to generate synthetic examples of benign files, ensuring balanced training.
    - Feature selection, such as using Random Forest importance scores, reduces redundancy, optimizing model performance and preventing overfitting.
3. **Advanced Techniques:**
    
    - LSTMs (Long Short-Term Memory Networks) were utilized for keystroke injection detection. The model analyzes sequences of keystrokes (hold times, flight times, and key codes) to identify patterns typical of human typing versus injection attacks.

---

### Kubernetes Setup in the Cloud

1. **Minikube Implementation:**
    
    - Minikube was chosen for its simplicity in managing a Kubernetes cluster. While only supporting single-node clusters, it provided the necessary environment for container orchestration and testing.
    - Alternatives like Docker Compose were considered but found less adaptable for scaling to multi-node setups, which may become necessary for future commercial iterations.
2. **Containerization Benefits:**
    
    - Containers offer lightweight isolation of processes compared to virtual machines, sharing the host OS kernel but maintaining application-specific dependencies.
    - Kubernetes enables scaling, load balancing, and network management across containerized services, crucial for handling tasks like malware analysis in the cloud.

---

### Future Implementations

1. **Enhanced Datasets:**
    
    - Future work involves integrating datasets with broader coverage, such as obtaining additional benign software samples to complement the extensive malicious datasets, filling the gap identified during this project.
2. **Remote NixOS Build:**
    
    - Leveraging **NixOS** for building software in a secure, reproducible manner could simplify deploying updated models and backend services. This approach emphasizes immutability and consistency across environments.
3. **Lightweight Malware Detection:**
    
    - Proposals include optimizing real-time malware scanning with edge computing to minimize latency, allowing faster USB device validation at the point of use.
4. **Modular System Design:**
    
    - The project envisions modularizing components like the keystroke injection and malware classifiers. This would allow independent updates or upgrades without disrupting other system functionalities.

