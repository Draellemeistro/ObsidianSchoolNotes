[http://130.225.37.50:3000/](http://130.225.37.50:3000/ "http://130.225.37.50:3000/")
https://www.reddit.com/r/Malware/comments/tsv4il/dataset_with_labeled_benign_and_malicious_files/
# Malicious USB Devices
### The Typical Suspects​
- **Threats from USB Devices:**
    - USB-based attacks exploit user trust and curiosity. Examples include malware-infected flash drives and keystroke injection devices.
    - Nation-state actors and small hacking groups increasingly use USB devices for sophisticated attacks.
- **Examples of Malicious USB Tools:**
    - **BadUSB:** Reprogrammed USB devices that execute hidden malicious functions.
    - **Rubber Ducky:** Performs rapid keystroke injections to execute scripts.
    - **Bash Bunny:** Mimics multiple USB device types to execute tailored payloads.
- **Easy Access:**
    - Microcontrollers like Teensy and Arduino make creating malicious devices affordable and accessible
### BadUSB​
### Programmable Microcontrollers​

### Electrical​​
piss easy to get a hold of. easy to program(**Eller er det til programmable**)

# Malware Detection
- **Datasets:**
    - Numerous datasets like EMBER, Virus-MNIST, and BODMAS provide labeled malware and benign files, aiding in training models.
- **Data Preparation and Model Training:**
    - Data preprocessing (e.g., feature extraction, balancing datasets with SMOTE).
    - Use of supervised machine learning for malware classification, with metrics like ROC-AUC to evaluate performance.
- **Advanced Techniques:**
    - LSTMs for analyzing sequential data, particularly for detecting malicious patterns in keystroke sequences.
## Machine Learning for Malware Detection

### Many possible datasets available​

### Different ways of preparing the data.​
### Many ways of training the models
# ...

# Cloud implementation - Containers​
**Advantages of Containerization:**
- Lightweight and efficient virtualization compared to traditional VMs.
- Facilitates scaling and testing in different environments
**Kubernetes Cluster:**
- Deployed using **Minikube** for simplicity and low resource consumption.
- Single-node cluster adequate for project needs but scalable to more robust systems (e.g., Docker Swarm, production-level Kubernetes) for commercial deployment.

# Future Implementations
- **Enhanced Datasets:**
    - Incorporate more diverse benign and malicious samples to improve detection capabilities.
- **Remote NixOS Build:**
    - Explore secure and reproducible software builds for further protection.
- **Lightweight Checks:**
    - Implement faster and more efficient malware detection techniques suitable for real-time analysis.
- **Modular Components:**
    - Design modular and extensible systems for easier updates and feature enhancements.

### Dataset

### Remote NixOS build

### Lightweight checking

### Components 

