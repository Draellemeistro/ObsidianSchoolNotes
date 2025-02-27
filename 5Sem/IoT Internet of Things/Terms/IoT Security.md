### [[IoT device]]s prone to cyber attacks [[IoT Security]]
##### EASY TO EXPLOIT
- Resource-constrained devices with low-cost design
- Do not support complex security techniques
##### ATTRACTIVE TARGET
- Deployed in safe-critical domains
- Contain sensitive data & control physical environment
##### AMPLIFY THE ATTACK IMPACT
- Many interconnected devices
- Spread quickly the malware

# Security challenges of [[IoT]]
- Default, weak and hardcoded passwords
- Lack of security and privacy
- Vulnerable web interfaces
- Clear text protocols and uneccesary open ports
- Coding errors (e.g., buffer overflows)
- Storage issues
- Difficult to update firmware and OS
- Legal, regulatory, and rights issues
### Other IoT security challenges
##### **VOLUME** and **VARIETY** of [[IoT device]]s
- **complex [[Distributed Systems]]**
	- huge differences in resources across tiers
	- many languages, OS'es, and networks
	- Specialized hardware
- **LACK** of a **common [[IoT Security]] framework**
- **No uniform STANDARDS yet**
- **Security** is **NOT CORE COMPETENCY for device maufacturers**
	- .... and / or in many  cases of IT admins
- **Security** is **NOT CORE FOCUS of the IoT product development process**
	- **VERY FEW ORGANIZATIONS** focus on securing their IoT products from the **BEGINNING OF THE DEVELOPMENT PROCESS**
	- **RUSH-TO-MARKET** is prioritized over security
- Most organizations:
	- have **NOT** set up mechanism to **REMOTELY PATCH CONNECTED DEVICES.**
		- Connected products need to be updated regularly for their defences
	- are **NOT** focusing on **ACQUIRING SPECIALIZED SECURITY SKILLS** for their IoT products.
	- are **NOT** leveraging **THIRD-PARTY SUPPORT** to accelerate the process of strengthening security
- **LACK OF AWARENESS AMONG CONSUMERS** regarding **SECURITY BEST PRACTICES**

#### How is the attack happening in IoT?
#TODO se slides fra IoT  8
##### Adding Salt to Pepper…
> [!NOTE]  **EASY TO:**
> - intercept and discover **credentials**
> - gain **root access**
> - **steal data**
> - Use Pepper as a **Trojan horse** and **compromise other devices**
> - Use Pepper as a **spy tool** and **perform physical actions,** even without valid credentials

##### [[Shodan.io]]
![[image_IoT-Security.png]]

## [[IoT-Security-Adversary Types]]
##### [[Remote Software Adversary]]
is remotely and aims to infect the device with malware
- **the most common type of adversary**
- Adversary is located remotely
- Tries to gain remote access to the device
**Common attacks to performed by a remote software adversary**
##### [[Local Adversary]]
is sufficiently near the device to be capable of eavesdropping on, and interfering with, the device’s communication.
##### [[Physical Non-Intrusive Adversary]]
is physically even closer to the device, so as to be capable of mounting side-channel attacks.
##### [[Stealthy Physical Intrusive Adversary]]
can capture the device and attempt to physically extract any secret information
##### [[Physical Intrusive Adversary]]
besides being able to physically capture the device, can attempt to modify its state and/or hardware components (e.g., introduce additional memory).

### [[IoT-Security-Common Vulnerabilities]]
##### Examples of common attacks
- Brute force attacks or dictionary attacks
- Remote access using Backdoor attack
#### [[OWASP Top 10 IoT Vulnerabilities]]
![[image_IoT-Security-Common Vulnerabilities.png]]