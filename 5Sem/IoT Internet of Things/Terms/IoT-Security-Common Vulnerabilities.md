
## Examples of common attacks
- Brute force attacks or dictionary attacks
- Remote access using Backdoor attack
**to play around with this, look at [[IoTGoat]]** 
#### Brute force attacks or dictionary attacks
- automated tools: **Hydra, Medusa**
- Primarily targets **online services** like SSH, FTP, [[HTTP]] and more
- But we need to know the username (or try to guess it)
- And then we have to choose a password list - and we choose the **John The Ripper** list

> [!NOTE] Do you know the difference: **_/etc/passwd_** vs **_/etc/shadow_**
> - **_/etc/passwd:_** all valid user accounts
> - **_/etc/shadow:_** requires root privileges to read and write the file
> 
> Both Can be used to crack the password.
###### Cracking Passwords Countermeasures
- Use **strong passwords** that consist of at least 12 random characters including both lower and uppercase letters, digits and special characters
- **Do not use dictionary words** including combinations of these words no matter the language
- **Do not store passwords unencrypted** like for example in word files. Do not write those fuckers down!!!
- **Do not reuse your passwords!** Use a unique password for each website or service
- **SET UP 2-WAY AUTHENTICATION**
#### Firmware analysis
- The attacker can analyze the firmware the extract passwords
	- e.g., `binwalk -e`
	- IoTGoat example: https://github.com/OWASP/IoTGoat/releases
##### Where to get the firmware?
- Directly from the dev team, manufacturer / vendor or client
- Buidl from scratch using walkthroughs provided by the manufacturer
- From the vendor's support site
- Extract directly from hardware via UART, JTAG, PICit, etc
- Sniff serial communication within hardware components for update server requests
- via a hardcoded endpoint within the mobile or thick applications
- Dumping firmware from the bootloader (e.g., U-boot) to flash storage or over the network via `tftp`
##### Firmware: Manufacturer Recommendations
- Ensure **supported and up-to-date software** is used by devs
- Ensure that **robust update mechanisms** are in place for devices
- Develop a mechanism to ensure a **new certificate is installed when old ones expire**
- Ensure that devs **do not code in easy-to-guess or common admin passwords**
- Develop a mechanism that **requires the user to create a secure admin password** during initial device setup
- Ensure developers **do not hard code passwords or hashes**
- Have **source code reviewed by a third-party** before releasing device to production
- Ensure **industry standard encryption or strong hashing** is used
#### Remote access using Backdoor attack
- **Search for open ports:** `nmap -nv -p- <IP>`
- **Try to connect:** `nc -v IP PORT`
##### Backdoor Countermeasures
- **Regular Updates:**
	- Keep device firmware and software up-to-date to address known vulnerabilities and security flaws.
- **Secure Coding Practices:**
	- Adhere to secure coding standards to minimize the introduction of vulnerabilities during development.
- **Static and Dynamic Analysis:**
	- Use automated tools to identify potential vulnerabilities in the codebase.
- **Network Segmentation:**
	- Isolate IoT devices from critical networks to limit the potential damage of a successful attack.
- **Intrusion Detection Systems (IDS):**
	- Monitor network traffic for suspicious activity that may indicate a backdoor attempt.
- **Behavioral Analysis:**
	- Analyze the device's behavior for anomalies that could signal a compromise.

# sadasd

![[image_IoT-Security-Common Vulnerabilities.png]]
## [[OWASP Top 10 IoT Vulnerabilities]]
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