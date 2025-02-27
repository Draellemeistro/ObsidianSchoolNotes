![[image_IoT-Security-Common Vulnerabilities.png]]
##### 1. Weak, Guessable, or Hardcoded Passwords
Use of:
- Easily bruteforced
- Publicly available
- Unchangeable credentials

Including backdoors in firmware or client software that grants unauthorized access.
##### 2. Insecure Network Services
Unneeded or insecure network services running on the device itself, especially:
- Those exposed to the Internet
- Any that compromise the confidentiality, integrity/authenticity, or availability of information
- Any service that allows unauthorized remote control
##### 3. Insecure Ecosystem Interfaces
Insecure interfaces in the ecosystem outside the device:
- Web
- Backend API
- Cloud
- Mobile
**Common Issues:**
- Lack of authentication
- Lack of authorization
- Lacking or weak encryption
- Lack of input and output filtering
##### 4. Lack of Secure Update Mechanism
Lack of ability to securely update the device.
- Lack of firmware validation on device
- Lack of secure delivery (un-encrypted in transit)
- Lack of anti-rollback mechanisms
- Lack of notifications of security changes due to updates
##### 5. Use of Insecure or Outdated Components
Use of deprecated or insecure software components/libraries that could allow the device to be compromised. (see also **heartbleed**)
- Insecure customization of operating system platforms
- Third-party software libraries from a compromised supply chain
- Third-party hardware components from a compromised supply chain