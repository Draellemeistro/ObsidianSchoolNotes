
##  [Python chat](https://github.com/ludvigknutsmark/python-chat)
#### Introduction
A basic example of a chat application which supports groups up to 10 people for each room. **==The goals of this project was to gain knowledge and experience in implementing encryption, diffie-hellman key exchange, digital signatures and SSL certificates into an Python application.==** This application is NOT(!!!!) meant for production or the sending of any sensitive data, therefore the GUI is ugly and very simplified and ==some huge security details are overlooked==, **see security issues for details.**

##### Some security features/measures is:
- End-to-end encrypted message between clients using **==Fernet==**, which is **a method that builds upon AES-128-CBC mode and a SHA256 hash authentication code (HMAC)**.
- **==[[Elliptic Curve Diffie-Hellman]] (ECDH) key exchange.==** I've implemented ECDH so that it works for more than two clients. Further explaination below.
- **SSL socket** between clients and server, where server acts as both server and CA.
- **Digital signatures using elliptical curves**.

# [Review of Algorithms for Securing Data Transmission in Mobile Banking](https://www.scirp.org/journal/paperinformation?paperid=127709)

**The study reviewed various encryption algorithms** such as Rivest-Shamir-Adleman Algorithm, Elliptic Curve Cryptography, Digital Signature Algorithm, Blowfish algorithm, Advanced Encryption Standard, Data Encryption Standard and Tripple Data Encryption Standard. In addition, the study reviewed steganography and hybrid algorithms.

## encryption algorithms reviewed
- RSA
- Elliptic Curve Cryptography
- Digital Signature Algorithm
- Blowfish
- Advanced Encryption Standard
- Data Encryption Standard and Tripple Data Encryption Standard
- steganography
- hybrid algorithms

# [Personal identification information](https://hypervault.com/data-templates/personal-identification-information/)

| **FULL NAME**                        | First, middle, and last name                                           |
| ------------------------------------ | ---------------------------------------------------------------------- |
| **DATE OF BIRTH**                    | Month, day, and year of an individual's birth                          |
| **PLACE OF BIRTH**                   | City, state, and country of an individual's birth                      |
| **GENDER**                           | Male, female, or other                                                 |
| **MARITAL STATUS**                   | Single, married, divorced, or widowed                                  |
| **PHONE NUMBER**                     | Home, cell, or work phone number                                       |
| **EMAIL ADDRESS**                    | Personal or professional email address                                 |
| **MAILING ADDRESS**                  | Home or work mailing address                                           |
| **GOVERNMENT-ISSUED IDENTIFICATION** | Social Security number, driver's license number, passport number, etc. |
| **FINGERPRINTS**                     | Digital or physical fingerprints                                       |
| **FACIAL RECOGNITION**               | Digital or physical facial features                                    |
| **SIGNATURE**                        | Digital or physical signature                                          |


# [FINANCIAL DATA SECURITY IN CLOUD COMPUTING](https://www.researchgate.net/publication/354340816_FINANCIAL_DATA_SECURITY_IN_CLOUD_COMPUTING)

- 

# [Securing Customer Data in the Financial Sector](https://www.flagright.com/post/securing-customer-data-in-the-financial-sector)
## Key principles in securing customer data
- Data encryption
- access control
	- Two types of access control are typically used:
	-  role-based access control (RBAC)
		- BAC assigns access rights based on predefined roles within the organization
	- attribute-based access control (ABAC).
		- while ABAC allows more granular control by considering additional attributes, like location, time, or the type of data being accessed.
- Multi-Factor Authentication (MFA)
- Secure storage and Data masking
- Compliance with data security regulations
## Tools & technologies for data security
- Firewalls
- Intrusion detection and prevention systems (IDPS)
- Data loss prevention (DLP) software
- Encryption tools
- Identity and access management (IAM)
- Security information and event management (SIEM) system

# [Encryption Algorithms Explained with Examples](https://www.freecodecamp.org/news/understanding-encryption-algorithms/)


# [5 Ways to Enhance Data Security in Banks](https://www.endpointprotector.com/blog/ways-banks-secure-data/)

LP solutions like [Endpoint Protector by CoSoSys](https://www.endpointprotector.com/solutions/finance) provide a comprehensive solution tailored to meet the unique challenges faced by the banking industry as well as the broader financial sector.
# [Protecting Sensitive Information](https://www.weber.edu/iso/protecting-sensitive-data.html)
**Data Disposal:** Computer hard disk drives containing electronic records with sensitive information that are no longer needed should be securely erased using an approved data erasure utility.
**Network Security Controls:** All transmission of Sensitive Information via the Internet must be through a properly secured connection point to ensure the network is protected.

# [Securing Data Transmission in Communication Networks](https://utilitiesone.com/securing-data-transmission-in-communication-networks)

## Effective Network Defense Strategies
Ensuring network security calls for a multi-layered and proactive approach. Here are some effective strategies to strengthen network defenses against data breaches:
### 1. Implement Strong Access Controls
- Enforce strong password policies and implement two-factor authentication to prevent unauthorized access.
- Regularly monitor and manage user access privileges to minimize the risk of insider threats.
### 2. Employ Next-Generation Firewalls
- Upgrade from traditional firewalls to modern next-generation firewalls that provide advanced threat detection and prevention capabilities.
- Utilize intrusion prevention systems (IPS) to detect and block malicious activities in real-time.
### 3. Conduct Vulnerability Assessments and Penetration Testing
- Regularly perform vulnerability assessments to identify and address potential weaknesses in the network infrastructure.
- Conduct penetration testing to simulate real-world attacks and evaluate the effectiveness of network defenses.
### 4. Implement Network Segmentation
- Divide the network into smaller, isolated segments that restrict unauthorized access and promote easier monitoring and control.
- Implement virtual local area networks (VLANs) to enhance security by separating traffic and isolating critical systems.
### 5. Utilize Encryption and Secure Communication Protocols
- Implement strong encryption protocols to protect sensitive data in transit.
- Use secure communication protocols, such as HTTPS, to establish secure connections between clients and servers.
### 6. Educate Employees on Cybersecurity Best Practices
- Train employees on identifying phishing attacks, using strong passwords, and practicing safe browsing habits.
- Create a culture of cybersecurity awareness to minimize human error as a potential entry point for cybercriminals.
# [Empowering and Securing Banking and Financial Organizations](https://live.paloaltonetworks.com/t5/general-articles/empowering-and-securing-banking-and-financial-organizations/ta-p/545427)

To safeguard inbound traffic, various security features can be enabled on the firewall. These include:
1. **Geo Location-Based Policy**: This helps prevent unauthorized access and reduces the risk of potential threats from specific regions
2. **Application Control (App-ID) :** NGFWs enable policy enforcement and control of inbound traffic based on specific applications. By identifying application characteristics, they can selectively allow or block traffic, ensuring that only authorized applications can access the network
3. **Decryption**: Implementing decryption mechanisms allows for inspecting and analyzing encrypted inbound traffic. By decrypting the traffic, organizations can identify and mitigate potential threats or malicious activities hidden within encrypted communications
4. **Data Loss Prevention (DLP):** Monitor inbound traffic for sensitive or confidential data entering the network. They can enforce policies to prevent the unauthorized transfer of sensitive information, such as credit card numbers, personal data, or intellectual property
5. **Advanced Threat Prevention**: Utilizing advanced threat prevention measures enhances the security posture against sophisticated attacks. These measures employ various techniques, such as behavioral analysis, machine learning, and threat intelligence, to detect and prevent known and unknown threats
6. **External Dynamic Lists (EDLs)**: EDLs enable the use of external threat intelligence sources to block traffic from known malicious IP addresses or domains. This helps proactively protect the network by preventing communication with known malicious entities

**In all these cases, banks need to ensure the security, integrity, and confidentiality of outbound traffic. Several security requirements should be considered to maintain a secure environment. Such as-**
- **Secure Connectivity:** Establish secure connections between the bank's on-premises infrastructure and the public cloud through encrypted communication channels, such as using VPN (Virtual Private Network) or dedicated private connections
- **Network Segmentation:** Implement network segmentation in the public cloud to separate services, applications, and data, limiting the impact of security breaches and improving control over outbound traffic flows
- **Intrusion Detection and Prevention**: To safeguard against security threats, such as unauthorized access attempts or malicious activities, deploy intrusion detection and prevention systems (IDPS). These systems actively monitor outbound network traffic, enabling the detection and prevention of potential security incidents
- **Data Loss Prevention (DLP):** Implement data loss prevention mechanisms to monitor and control outbound data flows. DLP solutions help identify and prevent the transmission of sensitive data that violates security policies, ensuring that confidential information is not leaked or exposed
- **Logging and Monitoring:** Implement a centralized logging system and SIEM solution to collect and analyze detailed logs of outbound traffic. This enables proactive detection of security incidents, identification of patterns, and timely response to potential threats. Monitor outbound traffic for suspicious activities, policy violations, or unauthorized access attempts, promptly investigating any anomalies
- **Compliance and Regulations:** Ensure compliance with relevant security standards, industry regulations, and data protection requirements, such as PCI DSS (Payment Card Industry Data Security Standard) or GDPR (General Data Protection Regulation). Implement necessary controls to protect customer data and maintain regulatory 
- **Network Traffic Monitoring:** Continuously monitor outbound network traffic for anomalies, unusual behavior, or signs of potential security breaches. Use network traffic monitoring tools to identify any suspicious outbound connections or abnormal data transfer patterns
- **Secure DNS:** Implement secure Domain Name System (DNS) services or DNS filtering solutions to protect against DNS-based attacks, such as DNS hijacking or domain spoofing. Secure DNS helps ensure that outbound traffic is directed to legitimate and trusted destinations
- **Web Proxy:** Deploying a web proxy server enables the implementation of web traffic filtering. Proxy servers serve as intermediaries between users and the internet, handling communications with websites on behalf of users, providing an additional layer of security and privacy
# [Best Practices To Secure Data Transmission](https://www.zippyops.com/best-practices-to-secure-data-transmission)
## **Role of Virtual Private Networks (VPNs)** 

Virtual Private Networks (VPNs) significantly ensure secure data transmission, particularly in a global marketplace where data often travels across different networks and authorities. A VPN establishes a secure tunnel for transmitting data over the internet, preventing unauthorized access or tampering. It encrypts your internet traffic, masking your IP address, and effectively shields your activities from prying eyes. For businesses, using a VPN adds an extra layer of security crucial for protecting sensitive information and complying with data protection laws. In an increasingly interconnected world, VPNs are vital to a robust data security strategy.
## **Importance of Secure Socket Layer (SSL) and Transport Layer Security (TLS)** 

TLS and SSL are cryptographic protocols that secure data transmission over the Internet. They are most recognized in the context of HTTPS websites, signified by a padlock symbol in the web address bar. SSL and TLS encrypt data packets between web browser and server, ensuring that any sensitive information — such as credit card details, personal identification, or proprietary business data — is secure from unauthorized access or tampering. For businesses operating in a global marketplace, employing SSL/TLS is not just best practice; it is essential for maintaining customer trust and regulatory compliance.
## **Multi-Factor Authentication (MFA)** 

This requires multiple forms of identification to access an account or system. In addition to something you know, such as a password, MFA often involves something you have, like a mobile device, for a verification code, or something you are, such as a fingerprint. Implementing MFA is crucial in securing data transmission in a global marketplace. Adding an extra layer of security significantly increases the difficulty for unauthorized users to access sensitive data. MFA is highly effective in thwarting cyberattacks like phishing and credential stuffing, making it a best practice for businesses prioritizing secure data transmission. 

## **Secure File Transfer Protocols (SFTP and FTPS)** 

Secure File Transfer Protocols like SFTP (Secure File Transfer Protocol) and FTPS (FTP Secure) are essential tools for transmitting data over a network safely. SFTP encrypts commands and data, effectively protecting against common cyber threats like data interception and unauthorized data access. FTPS, however, uses SSL (Secure Sockets Layer) encryption to secure the data channels. Both are significant upgrades over traditional FTP, which is not encrypted. Utilizing SFTP or FTPS is crucial for businesses operating in a global marketplace where data breaches can have severe repercussions. These protocols ensure that files containing sensitive information reach their intended destination securely. 

## **Legal Compliance and Global Regulations** 

Adhering to legal compliance and global regulations is a business imperative, not just a matter of good governance. Laws such as GDPR (General Data Protection Regulation) in Europe and CCPA in California set stringent standards for data protection. Non-compliance not only risks heavy fines but also damages a company's reputation. These laws often mandate Secure data transmission protocols, making them essential for global business operations.

## How to Choose a Data in Transit Encryption Solution:

When looking for a solution for securing data in transit, here are some items to add to your evaluation checklist:

**Encryption Standards:** Look for encrypted file sharing providers that employ robust encryption algorithms, such as AES (Advanced Encryption Standard) with a high encryption key length. Strong encryption ensures better protection against unauthorized access.

**Key Management:** Understand how the encryption keys are generated, stored, and managed by the provider. Ideally, encryption keys should be unique per user and stored securely. For even better security, look for a solution that enables you to manage your own keys. This way, the third party will not have access to your data and you can revoke access to your data at any time.

**Security Audits and Certifications:** Assess the provider’s adherence to security best practices and certifications. Depending on your industry’s requirements, look for certifications like SOC 2, ISO 27001, PIPEDA, and HIPAA compliance.
# [Securing Data in Transit With Encryption: The Ultimate Guide](https://www.titanfile.com/blog/data-in-transit-encryption/ "Permanent Link: Securing Data in Transit With Encryption: The Ultimate Guide")

## Protocols for Securing Data in Transit

Secure protocols are used to encrypt data transfer files securely over the internet. Always ensure these protocols to securely transfer your data without any risk. There are four common secure protocols for file transfer:

- Transport Layer Security (TLS)
- Secure File Transfer Protocol (SFTP)
- Secure Shell (SSH) File Transfer Protocol (SCP)
- Hypertext Transfer Protocol Secure (HTTPS)
# [Sentinel Banking: How Banks Secure Their Data](https://medium.com/@digicore/sentinel-banking-how-banks-secure-their-data-29c27f359bfa)
Cryptographic keys safeguard the world’s most sensitive data for the public, military, and private sectors. To adequately protect these assets, you need a **Hardware Security Module (HSM)**. However, HSMs are not created equal for a reason.


# [Securing the World’s Most Sensitive Data with FIPS and HSMs](https://www.linkedin.com/pulse/securing-worlds-most-sensitive-data-fips-hsms-michael-murray)

  

# [Encryption Requirements for Banks & Financial Services](https://info.townsendsecurity.com/encryption-requirements-for-banks-financial-services)
Examples of industry-tested and accepted standards and algorithms for encryption include AES (128 bits and higher), TDES (minimum double-length keys), RSA (2048 bits and higher), ECC (160 bits and higher), and ElGamal (1024 bits and higher). See [NIST Special Publication 800-57](http://csrc.nist.gov/publications/) for more information.
## **Encryption at the Database Level**
Almost all commercial databases now support some time of encryption in the database itself.  Encryption at the database layer provides some distinct advantages:
- Encryption is optimized for database performance
- Encryption services are better integrated with other database access control services resulting in fewer security gaps
- Encryption key management may be better integrated into the encryption implementation
## **Encryption at the Application Level**
It provides a very granular level of control of sensitive data and allows for the application of user access controls, program access controls, data masking, and other security controls.  Many feel that application layer encryption is the most secure way to protect data.
## **Encryption Key Management**
Encryption is only as secure as your encryption keys.  The essential functions of a key management solution include storing the encryption keys separate from the data that they protect, as well as managing the encryption keys through the entire lifecycle including:

- Generating keys for different cryptographic systems and different applications
- Generating and obtaining public keys
- Distributing keys to intended users, including how keys should be activated when received
- Storing keys, including how authorized users obtain access to keys
- Changing or updating keys, including rules on when and how keys should be changed
- Addressing compromised keys
- Archiving, revoking, and specifying how keys should be withdrawn or deactivated
- Recovering keys that are lost or corrupted as part of business continuity management
- Logging the auditing of key management-related activities
- Instituting defined activation and deactivation dates, and limiting the usage period of keys


# [How To Secure Data Transmission?](https://www.newsoftwares.net/blog/how-to-secure-data-transmission/)

1. **Use Encryption:** [Encrypt the data using mathematical algorithms](https://www.newsoftwares.net/blog/ensuring-data-security-does-data-encryption-occur-with-the-post-method/ "Ensuring Data Security: Does Data Encryption Occur with the POST Method?") and encoding methods before transmitting it. This ensures that the information is unreadable to unauthorized parties.
2. **Choose Secure Protocols:** Use secure communication [protocols like TLS/SSL for internet data transmission](https://www.newsoftwares.net/blog/ssl-tls-key-protocols-encrypting-data-across-the-internet/ "SSL & TLS: Key Protocols Encrypting Data Across the Internet") to establish encrypted connections.
3. **Implement Authentication:** Verify the identity of both sender and receiver to [prevent unauthorized access to data](https://www.newsoftwares.net/blog/usb-block-block-access-unauthorized-usb-drives-prevent-data-loss/ "USB Block – Block Access To Unauthorized USB Drives To Prevent Data Loss").
4. **Protect Encryption Keys:** [Safeguard encryption keys used to maintain data](https://www.newsoftwares.net/blog/windows-10-dell-data-protection-encryption-key-considerations/ "Windows 10 Dell Data Protection Encryption: Key Considerations") confidentiality.
5. **Use Secure** [**File Transfer Methods:** Employ protocols like SFTP](https://www.newsoftwares.net/blog/secure-methods-for-accessing-managing/ "Exploring Secure Methods for Accessing, Managing, and Transferring Data Files") for secure file transfers, especially for sensitive information.
## Secure File Transfer Protocol (SFTP)
builds File Transfer Protocol (FTP) by utilizing Secure Shell (SSH) components for secure file transfers.
1. **Preventing** Password Sniffing and Data Exposure SFTP prevents password sniffing and protects data from exposure during file transfers.
2. **Two-Factor Authentication for Added Security** SFTP supports two-factor authentication, adding an extra layer of security to the file transfer process.
###  SFTP vs. VPN: Different Tools, Common Goals
1. **The Purpose of SFTP and VPN**: SFTP is designed for secure file transfers, while Virtual Private Networks (VPNs) create encrypted data transmission tunnels. Both aim to enhance data security.
2. **Enhancing Security with SFTP over VPN** SFTP can be used through a VPN to enhance the security of file transfers further, providing an additional layer of protection.
## Ensuring Confidentiality and Authentication
- **Secret Key Encryption:** Secret key encryption, also known as symmetric encryption, involves using a single key to encrypt and decrypt data. Only the parties with access to the key can decipher the information.
- **Public Key Encryption**: Public key encryption, or asymmetric encryption, uses a public key for encryption and a private key for decryption. This method allows secure communication between parties without sharing the private key.
- **Digital Signatures for Data Integrity:** Digital signatures are used to verify the authenticity and integrity of data during transmission. They help identify any alterations or tampering with information.
## SSL – The Sentinel of Web Communication:
1. **Role of SSL in Web Security:** SSL (Secure Sockets Layer) is critical in securing web communication. It establishes an encrypted connection between a web server and a browser, protecting data during transmission.
2. **Securing Communication between Servers and Web Browsers** SSL ensures that sensitive data, such as login credentials and financial information, is encrypted and protected while being exchanged between servers and web browsers.
3. **SSL Certificates and Authentication** SSL certificates are used to authenticate the identity of websites. Users can trust that they interact with legitimate and secure websites when SSL certificates are present.
## Link Encryption: Building Secure Tunnels for Data Transmission:
1. **Understanding Link Encryption:** Link encryption creates secure tunnels between points in a network, ensuring confidentiality, integrity, and authentication during data transmission.
2. **Confidentiality, Integrity, and Authentication** Link encryption ensures that data remains confidential, unaltered, and secure while traveling through the network.
3. **Complementing Other Security Layers in Networking** Link encryption adds an additional layer of security to complement other security measures in a network, enhancing overall data protection.
# [MASTERCARD: Securing Sensitive Data Using Payload Encryption](https://developer.mastercard.com/platform/documentation/security-and-authentication/securing-sensitive-data-using-payload-encryption/)

![[Pasted image 20240228183133.png]]


**Here are the steps for sending an encrypted payload:**
1. An AES session key is generated along with some encryption parameters
2. Sensitive data are encrypted using the AES key
3. The AES key is encrypted using the recipient’s RSA public key
4. The payload is sent with the encrypted session key and parameters

**Here are the steps for decrypting a payload:**
1. The AES session key is decrypted using the recipient’s RSA private key
2. Sensitive data are decrypted using the AES key
# [Protecting Your System: Information Security](https://nces.ed.gov/pubs98/safetech/chapter6.asp)

GAD IKKE AT SKIMME IGENNEM DEN
 [5 Ways In Which Banks Secure Their Data](https://emtmeta.com/5-ways-in-which-banks-secure-their-data/)
[Security framework for mobile banking](https://dl.acm.org/doi/abs/10.1145/1971519.1971591)
banking service delivery platform must provide end-to-end security to safeguard the information exchange between the bank and the customer.

# [Information Security in Banking and Financial Industry](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=34758c819d3bb4d4e5e4b4d053db523684adac09)


# [Scale-based secured sensitive data storage for banking services in cloud](https://www.inderscienceonline.com/doi/abs/10.1504/IJEB.2018.094863)
GAD IKKE AT SKIMME IGENNEM DEN

# [QuickCash: Secure Transfer Payment Systems](https://www.mdpi.com/1424-8220/17/6/1376)
GAD IKKE AT SKIMME IGENNEM DEN
# [The application of multi-server authentication scheme in internet banking transaction environments](https://link.springer.com/article/10.1007/s10257-020-00481-5)


[Sensitive Data Transfer Security Model While Online Transaction Processing](https://www.researchgate.net/publication/295430766_Sensitive_Data_Transfer_Security_Model_While_Online_Transaction_Processing)


[FINANCIAL DATA SECURITY IN CLOUD COMPUTING](https://www.researchgate.net/publication/354340816_FINANCIAL_DATA_SECURITY_IN_CLOUD_COMPUTING)


[OMOS: A Framework for Secure Communication in Mashup Applications](https://ieeexplore.ieee.org/abstract/document/4721572)


# [Chapter Six - Protecting personal sensitive data security in the cloud with blockchain](https://www.sciencedirect.com/science/article/abs/pii/S006524582030084X)

The data owner does not want its personal sensitive data falling in the hand of any other entities. Meeting this security need is challenging when the data is outsourced in the cloud. We employ **Ethereum** **blockchain** and **smart contract**, which include a **blockchain-based access control mechanism** and a cloud data operation protocol fused with blockchain-based access policies, to construct a model that can protect personal sensitive data security in the cloud.
# [Survey on Sensitive Data Handling—Challenges and Solutions in Cloud Storage System](https://link.springer.com/chapter/10.1007/978-981-13-1882-5_17)

[Der er nogle gode ting, om opbevaring og transport af data, dog i kontekst af big data](https://link-springer-com.zorac.aub.aau.dk/chapter/10.1007/978-981-13-1882-5_17)
# [Homomorphic Encryption](https://link.springer.com/chapter/10.1007/978-3-319-12229-8_2)
