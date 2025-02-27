Man kunne interviewe [bug bounty folk](https://www.yeswehack.com/) måske?
# Gode links:
- [Swiss Post Voting System - System specification](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/blob/master/System/System_Specification.pdf) 
	- HELE [GITLAB'EN](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation) ER EN GULDMINE: [TESTING](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/blob/master/Testing/Test%20Concept%20of%20the%20Swiss%20Post%20Voting%20System.md?ref_type=heads), [ARCHITECTURE & SPECIFICATION](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/tree/master/System?ref_type=heads),  [SECURITY ADVICES](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/tree/master/Security-advices?ref_type=heads), [SECURITY](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/blob/master/Product/Security%20Whitepaper%20of%20the%20Swiss%20Post%20Voting%20System.md), [AGIL UDVIKLINGSPROCESS](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/blob/master/Product/Software%20development%20process%20of%20the%20Swiss%20Post%20voting%20system.md) 
- [Til test af sikkerhed?](https://www.yeswehack.com/researchers/tools)
- [Mastercard developers](https://developer.mastercard.com/platform/documentation/security-and-authentication/securing-sensitive-data-using-payload-encryption/)
- [encryption algorithms reviewed](https://www.scirp.org/journal/paperinformation?paperid=127709)
- [A Comprehensive Review on Encryption based Open Source Cyber Security Tools](https://ieeexplore.ieee.org/abstract/document/9609369)
- **Måske de her tre:**
	- 2017: [Real-World Electronic Voting: Design, Analysis and Deployment](https://kbdk-aub.primo.exlibrisgroup.com/permalink/45KBDK_AUB/159qapk/cdi_proquest_miscellaneous_1878296184)
	- 2021: [E-Voting: Security, Threats and Prevention](https://ieeexplore.ieee.org/abstract/document/9768214)
	- dunno, bachelorprojekt: [Investigating the Security of End-to-End and Blockchain-based Electronic Voting Systems](https://www.diva-portal.org/smash/get/diva2:1683763/FULLTEXT01.pdf)
# ting
- 'stemmesedlen'/verifikation af faktisk gyldig vælger
- kryptering af valgsvar
- Vælger skal ikke kunne identificeres ud fra data de sender (eller rettere, skal ikke kunne kobles til den specifikke data dekrypteret)
- Hashing til at sløre krydset, ud over kryptering? (der er jo begrænsede valgmuligheder ifht til kandidat. Kan man stemme på nogen udover dem på blanketten?)
- Checksum inspireret løsning til at undgå tampering?
- [**Financial** information is extremely **sensitive**](https://www.researchgate.net/profile/Naveen-Kunnathuvalappil-Hariharan/publication/354340816_FINANCIAL_DATA_SECURITY_IN_CLOUD_COMPUTING/links/6132507538818c2eaf7e616f/FINANCIAL-DATA-SECURITY-IN-CLOUD-COMPUTING.pdf), … **The transmitted data is separated into several parts using encryption**..

## Mulige sikkerhedsting
**Primære problematikker:** ifølge [dem her](https://www.techpolicy.press/security-and-reliability-concerns-around-internet-voting-outweigh-benefits/)
1. Security Vulnerabilities
2. Reliability Concerns
3. Privacy Risks
4. Authentication Challenges


- Replace any cast ballot
- Drop any cast ballot
- Learn any target voter’s vote
### Attacking and Fixing Verifiability
#### Individual verifiability
- ==**allows the voter to check that the server correctly registered her vote and contains the voter’s choices.**== 
Faithfully executing the two-round return code scheme (see section 1.1) guarantees to the voter that the system’s trustworthy part registered the intended vote. Conversely, **this implies that even a powerful adversary, controlling the voting client and most of the server infrastructure, cannot alter or drop a vote without being detected by a diligent voter or auditor.**
#### Universal verifiability
- ==**allows voters or auditors to check that the system correctly counted all confirmed votes.** ==
Independent auditors verify every step in the counting process—from the registration of the encrypted voting options to the decryption and tallying process—without compromising vote secrecy. **Advanced cryptographic techniques such as non-interactive zero-knowledge proofs and verifiable mix-nets allow the Swiss Post Voting System to have the best of both worlds: the election result is correct beyond doubt, and every single vote remains secret.**

### Attacking and Fixing Ballot Privacy
#### Vote secrecy
- **==preserves the privacy of the voter.==** 
By extension, vote secrecy ensures that no component learns the election results before the final decryption step. The Swiss Post Voting System protects vote secrecy by encrypting votes end-to-end and splitting the decryption key among multiple entities.

### Electronic voting security: French legislative elections in June 2022
voters create their electronic ballot, their **device encrypts their vote** **with the election public key** and computes a **unique fingerprint** for the electronic ballot. The **ballot is sent to the server**, which in turn calculates a **receipt containing this fingerprint**, among other things:
- **If the server was compromised, it would be possible to modify the electronic ballot sent** and send voters a receipt that would lead them to believe that their ballot had been faithfully recorded according to their choice. [The verifiability, integrity and sincerity of the ballot are all undermined](https://www.inria.fr/en/security-electronic-voting-digital-security-confidentiality)
- **possible for an attacker to target a voter, divert their ballot** to a consular constituency where there were very few votes, or none at all, **and then find out who they voted for when the votes are counted** and the result revealed. This was made possible by a flaw in the design of the zero-knowledge proofs that accompany the ballots
**The vulnerabilities and attacks we have shown can be exploited** by an attacker who would **compromise either the voting server** or the **secure communication channel (TLS)**

# andre ting 



##### 4 steps to create an effective data encryption strategy
1. **Classify data.**
2. **Identify the right data encryption solution**
3. **Implement strong encryption key management practices.**
4. **Understand the limitations of encryption.**
### [Mastercard gennemgår meget fint programmeringen af security og authentication](https://developer.mastercard.com/platform/documentation/security-and-authentication/securing-sensitive-data-using-payload-encryption/)
**Here are the steps for sending an encrypted payload:**
1. An AES session key is generated along with some encryption parameters
2. Sensitive data are encrypted using the AES key
3. The AES key is encrypted using the recipient’s RSA public key
4. The payload is sent with the encrypted session key and parameters

**Here are the steps for decrypting a payload:**
1. The AES session key is decrypted using the recipient’s RSA private key
2. Sensitive data are decrypted using the AES key

![[Pasted image 20240222163627.png]]
#### Technology Stack (godt nok angående krypteret chat, men kan sætte gang i noget i guess)

**Client Application**
1. ReactJS for UI
2. Axios Library for handling AJAX calls
3. WebSocket library for real-time message exchange
4. Signal Protocol for end-to-end encryption
5. Tailwind CSS

**Server Application**
1. NodeJS
2. Express
3. Mongoose for MongoDB integration
4. TypeScript as the server-side language
5. REST APIs

## Tools & technologies for data security
- firewalls
- Intrusion detection and prevention systems (IDPS)
- Data loss prevention (DLP) software
- Encryption tools
- Identity and access management (IAM)
- Security information and event management (SIEM) system
- **Multi-Factor Authentication (MFA)**  Adding an extra layer of security significantly increases the difficulty for unauthorized users to access sensitive data. MFA is highly effective in thwarting cyberattacks like phishing and credential stuffing
- Secure storage and Data masking
- Compliance with data security regulations
- **Data Disposal:** Computer hard disk drives containing electronic records with sensitive information that are no longer needed should be securely erased using an approved data erasure utility.


-  **secure communication protocols**, such as HTTPS, to establish secure connections between clients and servers.
- **Network Security Controls:** All transmission of Sensitive Information via the Internet must be through a properly secured connection point to ensure the network is protected.
- **Network Segmentation:** isolated segments that restrict unauthorized access and promote easier monitoring and control. ... separate services, applications, and data, limiting the impact of security breaches and improving control over outbound traffic flows

- **Geo Location-Based Policy**: This helps prevent unauthorized access and reduces the risk of potential threats from specific regions.
- **External Dynamic Lists (EDLs)**: EDLs enable the use of external threat intelligence sources to block traffic from known malicious IP addresses or domains. This helps proactively protect the network by preventing communication with known malicious entities
- **Secure Connectivity:** Establish secure connections between the bank's on-premises infrastructure and the public cloud through encrypted communication channels, such as using VPN (Virtual Private Network) or dedicated private connections.
- **Secure DNS:** Implement secure Domain Name System (DNS) services or DNS filtering solutions to protect against DNS-based attacks, such as DNS hijacking or domain spoofing. Secure DNS helps ensure that outbound traffic is directed to legitimate and trusted destinations.
- **Web Proxy:** Deploying a web proxy server enables the implementation of web traffic filtering. Proxy servers serve as intermediaries between users and the internet, handling communications with websites on behalf of users, providing an additional layer of security and privacy.
- **Compliance and Regulations:** Ensure compliance with relevant security standards, industry regulations, and data protection requirements, such as PCI DSS (Payment Card Industry Data Security Standard) or GDPR (General Data Protection Regulation). Implement necessary controls to protect customer data and maintain regulatory 
- **Encryption Key Management?** 
- **security testing**: ex conducting penetration testing, code reviews, and security audits

## Protocols for Securing Data in Transit

Secure protocols are used to encrypt data transfer files securely over the internet. Always ensure these protocols to securely transfer your data without any risk. There are four common secure protocols for file transfer:
- **Secure Socket Layer (SSL) and Transport Layer Security (TLS)** are Cryptographic protocols that secure data transmission over the Internet. They are most recognized in the context of HTTPS websites, signified by a padlock symbol in the web address bar.
- Transport Layer Security (TLS)
- Secure File Transfer Protocol (SFTP)
- Secure Shell (SSH) File Transfer Protocol (SCP)
- Hypertext Transfer Protocol Secure (HTTPS)

**RELEVANT ELLER EJ?** PrimeRevenue realised that an **SSL** solution would not be secure enough and looked for a standards based solution using digital signature and encryption technology that would satisfy their demanding requirements. They identified the **==OpenPGP==** standard as being the most widely implemented technology for file encryption and digital signatures
### Ensuring Confidentiality and Authentication
- **Secret Key Encryption:** Secret key encryption, also known as symmetric encryption, involves using a single key to encrypt and decrypt data. Only the parties with access to the key can decipher the information.
- **Public Key Encryption**: Public key encryption, or asymmetric encryption, uses a public key for encryption and a private key for decryption. This method allows secure communication between parties without sharing the private key.
- **Digital Signatures for Data Integrity:** Digital signatures are used to verify the authenticity and integrity of data during transmission. They help identify any alterations or tampering with information.
### Link Encryption: Building Secure Tunnels for Data Transmission:
1. **Understanding Link Encryption:** Link encryption creates secure tunnels between points in a network, ensuring confidentiality, integrity, and authentication during data transmission.
2. **Confidentiality, Integrity, and Authentication** Link encryption ensures that data remains confidential, unaltered, and secure while traveling through the network.
3. **Complementing Other Security Layers in Networking** Link encryption adds an additional layer of security to complement other security measures in a network, enhancing overall data protection.

### in da cloud
[Meeting this security need is challenging when the data is outsourced in the cloud. We](https://www.sciencedirect.com/science/article/abs/pii/S006524582030084X) employ **Ethereum** **blockchain** and **smart contract**, which include a **blockchain-based access control mechanism** and a cloud data operation protocol fused with blockchain-based access policies, to construct a model that can protect personal sensitive data security in the cloud.


# [Fransk rapport om sikkerhed eller noget](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000038661239)
vurderinger:
- forseglingsprocessen forblev intakt under afstemningen;  
- krypterings-/dekrypteringsnøglerne er kun kendt af deres indehavere;  
- afstemning er anonym, når det kræves ved lov;  
- tilstedeværelseslisten omfatter kun listen over vælgere, der har stemt;  
- den strippede stemmeurn er faktisk den, der indeholder vælgernes stemmer, og at den kun indeholder disse stemmer;  
- der kunne ikke foretages en delvis optælling under afstemningen;  
- optællingen af ​​stemmeurnen kan efterprøves, og at den er gennemført korrekt.

# Lidt links og ekstra
## Videoer 
-  [Transport Layer Security (TLS) - Computerphile](https://www.youtube.com/watch?v=0TLDTodL7Lc)
- [TLS Handshake Explained - Computerphile](https://www.youtube.com/watch?v=86cQJ0MMses)
- [Secure Web Browsing - Computerphile](https://www.youtube.com/watch?v=E_wX40fQwEA)
- [HTTPS, SSL, TLS & Certificate Authority Explained](https://www.youtube.com/watch?v=EnY6fSng3Ew)
- [Security measures for i-voting](https://www.youtube.com/watch?v=uz9CUK0Ii6Q)
- [I-voting in Estonia 2021](https://www.youtube.com/watch?v=3OmNKhT9z_4)
- Daniels video: [Why Electronic Voting Is Still A Bad Idea](https://www.youtube.com/watch?v=LkH2r-sNjQs)
- [Electronic voting leaves a trail and may be audited at any time](https://www.youtube.com/watch?v=6ZWAbHu3LMQ)
- [David Bismark: E-voting without fraud](https://www.youtube.com/watch?v=izddjAp_N4I)
- Mere Tom Scott: [Why Electronic Voting is a BAD Idea - Computerphile](https://www.youtube.com/watch?v=w3_0x6oaDmI)
- EU parlamentets research service: [Blockchain voting](https://www.youtube.com/watch?v=2rgbOv_ab4c)

## apropos E-voting
- 2021/2022: Gitlab [E-voting documentation](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation)
- 2008: [On the notion of ‘software independence’ in voting systems](https://royalsocietypublishing.org/doi/10.1098/rsta.2008.0149)
- 2022: [Breaking and Fixing Vote Privacy of the Estonian E-Voting Protocol IVXV](https://orbilu.uni.lu/bitstream/10993/49442/1/main.pdf)  (springer: [link](https://link.springer.com/chapter/10.1007/978-3-031-32415-4_22))
- 2022: [How Efficient are Replay Attacks against Vote Privacy? A Formal Quantitative Analysis](https://eprint.iacr.org/2022/743)
- [Clash Attacks on the Verifiability of E-Voting Systems](https://eprint.iacr.org/2012/116)
- 2002: [Coercion-Resistant Electronic Elections](https://eprint.iacr.org/2002/165.pdf)
- 2016: [Improving the verifiability of the Estonian Internet Voting scheme](https://research.cyber.ee/~janwil/publ/ivxv-evoteid.pdf)
- 2020: [How not to prove your election outcome](https://ieeexplore.ieee.org/document/9152765)
- 2019: [Breaking the encryption scheme of the Moscow Internet voting system](https://arxiv.org/abs/1908.05127)
- 2010: [Attacking and fixing Helios: An analysis of ballot secrecy](https://eprint.iacr.org/2010/625)
- 2018: [Voting: You Can’t Have Privacy without Individual Verifiability](https://inria.hal.science/hal-01858034/document)
- 2020: [How to fake zero-knowledge proofs, again](https://inria.hal.science/hal-02928953/document)
- 2019: [Belenios: a simple private and verifiable electronic voting system](https://inria.hal.science/hal-02066930/document)
- 2022: [A privacy attack on the Swiss Post e-voting system](https://inria.hal.science/hal-03446801/file/rwc.pdf)
- 2007: [Civitas: Toward a Secure Voting System](https://www.cs.cornell.edu/andru/papers/civitas-tr.pdf)
- 2015: [A comprehensive analysis of game-based ballot privacy definitions](https://eprint.iacr.org/2015/255.pdf)
- 2008: [Helios: Web-based Open-Audit Voting](https://www.usenix.org/legacy/events/sec08/tech/full_papers/adida/adida.pdf)
- 2013: [STAR-Vote: A Secure, Transparent, Auditable, and Reliable Voting System](https://www.usenix.org/system/files/conference/evtwote13/jets-0101-bell.pdf)
- 2016: [Voting System Security and Reliability Risks](https://www.brennancenter.org/sites/default/files/analysis/Fact_Sheet_Voting_System_Security.pdf)
- 2015: [A Study of Vulnerabilities in E-Voting System](https://www.researchgate.net/publication/315040247_A_Study_of_Vulnerabilities_in_E-Voting_System)
- 2020: [MIT researchers identify security vulnerabilities in voting app](https://news.mit.edu/2020/voting-voatz-app-hack-issues-0213)
- 2022: [Vulnerabilities Affecting Dominion Voting Systems ImageCast X](https://www.cisa.gov/news-events/ics-advisories/icsa-22-154-01)
- 2021/2022: Gitlab [E-voting documentation](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation)
- 1987: [Verifiable Secret-Ballot Elections](https://cpsc.yale.edu/sites/default/files/files/tr561.pdf)
- 2018: [A Scheme for Three-way Secure and Verifiable E-Voting](https://www.computer.org/csdl/proceedings-article/aiccsa/2018/08612810/17D45WK5AmO)
- 2021: [Verifiable receipt-free electronic voting system based on mask ballot](https://www.computer.org/csdl/proceedings-article/isci/2021/004000a047/1Byed7IF4gU)
- 2020: [Ordinos: A Verifiable Tally-Hiding E-Voting System](https://www.computer.org/csdl/proceedings-article/euros&p/2020/508700a216/1oqKxJjEIUM)
- 2019/2023: [Towards End-to-End Verifiable Online Voting: Adding Verifiability to Established Voting Systems](https://www.computer.org/csdl/journal/tq/5555/01/10298802/1RADozid6p2)
- 2018: [SHARVOT: Secret SHARe-Based VOTing on the Blockchain](https://www.computer.org/csdl/proceedings-article/wetseb/2018/572601a030/13bd1fph1yP)
- 2018: [Alethea: A Provably Secure Random Sample Voting Protocol](https://www.computer.org/csdl/proceedings-article/csf/2018/668001a283/12OmNzZWbAn)
- 2022: [Efficient Homomorphic E-Voting Based On Batch Proof Techniques — An Improvement to Secure MPC Application](https://www.computer.org/csdl/proceedings-article/pst/2022/09851967/1FWmlodPyVO)
- 
## kryptering og netværkssikkerhed
### Almen forståelse
- https://en.wikipedia.org/wiki/Electronic_voting
-  [What is encryption?](https://cloud.google.com/learn/what-is-encryption)
- [WHY YOU SHOULDN'T WRITE YOUR OWN ENCRYPTION ALGORITHM](https://keasigmadelta.com/blog/why-you-shouldnt-write-your-own-encryption-algorithm/)
- [Why is writing your own encryption discouraged?](https://crypto.stackexchange.com/questions/43272/why-is-writing-your-own-encryption-discouraged)
- [7 Encryption Methods To Shield Sensitive Data from Prying Eyes](https://www.getapp.com/resources/common-encryption-methods/)
#### begreber 
- [Crypto and Number Theory](https://www-users.cse.umn.edu/~garrett/crypto/)
- [Cryptographic Primitives](https://www-users.cse.umn.edu/~garrett/crypto/overview.pdf)
-  [polyalphabetic cipher](https://en.wikipedia.org/wiki/Polyalphabetic_cipher)
-  [cryptanalysis](https://en.wikipedia.org/wiki/Cryptanalysis "Cryptanalysis") 
- [attack models](https://en.wikipedia.org/wiki/Attack_model)
- [penetration testing](https://www.synopsys.com/glossary/what-is-penetration-testing.html) (eller [her](https://www.hackerone.com/knowledge-center/what-penetration-testing-how-does-it-work-step-step), eller [IBM](https://www.ibm.com/topics/penetration-testing))
- [code reviews](https://www.synopsys.com/glossary/what-is-code-review.html#:~:text=Secure%20code%20review%20is%20a,style%20guidelines%2C%20among%20other%20activities.) (eller [her](https://www.cobalt.io/blog/introduction-to-secure-code-review),  [her](https://blog.codacy.com/security-code-review-best-practices), måske den her, dybdegående en: [her](https://owasp.org/www-pdf-archive/OWASP_Code_Review_Guide_v2.pdf))
- [security audits](https://www.auditboard.com/blog/what-is-security-audit/)
### Samlinger af gode og mindre artikler
- 2017: [Real-World Electronic Voting: Design, Analysis and Deployment](https://kbdk-aub.primo.exlibrisgroup.com/permalink/45KBDK_AUB/159qapk/cdi_proquest_miscellaneous_1878296184)
- 2021: [E-Voting: Security, Threats and Prevention](https://ieeexplore.ieee.org/abstract/document/9768214)
- [The recent trends in cyber security: A review](https://www.sciencedirect.com/science/article/pii/S1319157821000203)
- [A Comprehensive Review on Encryption based Open Source Cyber Security Tools](https://ieeexplore.ieee.org/abstract/document/9609369)
- [End-to-End Encrypted Messaging Protocols: An Overview](https://link.springer.com/chapter/10.1007/978-3-319-45982-0_22)
- [Advances in Cyber Security: Principles, Techniques, and Applications](https://link.springer.com/book/10.1007/978-981-13-1483-4)
- [Applied Cryptography for Cyber Security and Defense: Information Encryption and Cyphering](https://www.igi-global.com/gateway/book/41746)
- [Making, Breaking Codes: Introduction to Cryptology](https://dl.acm.org/doi/10.5555/517968)

- dunno, bachelorprojekt: [Investigating the Security of End-to-End and Blockchain-based Electronic Voting Systems](https://www.diva-portal.org/smash/get/diva2:1683763/FULLTEXT01.pdf)
### Security frameworks og reglementer
- [NIST: CYBERSECURITY FRAMEWORK](https://www.nist.gov/cyberframework?trk=article-ssr-frontend-pulse_little-text-block)
- 2016: [ICIT: Hacking Elections is Easy!](https://sanantonioreport.org/wp-content/uploads/2016/09/icit-analysis-hacking-elections-is-easy-part-one2.pdf)
- 2016-2017: [Making Democracy Harder to Hack](https://heinonline.org/HOL/LandingPage?handle=hein.journals/umijlr50&div=21&id=&page=)
- 2010: [electronic elections: The perils and Promises of Digital Democracy](https://books.google.dk/books?hl=en&lr=&id=OOhhIGSca7gC&oi=fnd&pg=PP1&dq=electronic+elections+security&ots=c7P-BSZgf4&sig=70lPhK7txTj4Ob0UEss9l032kRc&redir_esc=y#v=onepage&q=electronic%20elections%20security&f=false)
- 

### Angreb / sårbarheder / Security analysis
- [How Efficient are Replay Attacks against Vote Privacy? A Formal Quantitative Analysis](https://www.computer.org/csdl/proceedings-article/csf/2022/09979167/1J2YpxdOopO)
- [Injection Attacks Against End-to-End Encrypted Applications](https://www.computer.org/csdl/proceedings-article/sp/2024/313000a082/1RjEaQAIfkc)
- [Peek-a-boo, i still see you: Why efficient traffic analysis countermeasures fail](https://ieeexplore.ieee.org/abstract/document/6234422/)
- [Website fingerprinting: attacking popular privacy enhancing technologies with the multinomial naïve-bayes classifier](https://dl.acm.org/doi/abs/10.1145/1655008.1655013)
- [DTRAB: combating against attacks on encrypted protocols through traffic-feature analysis](https://www.computer.org/csdl/journal/nt/2010/04/05392994/13rRUwhpBAV)
- [Password-Based Authentication: Preventing Dictionary Attacks](https://www.computer.org/csdl/magazine/co/2007/06/r6068/13rRUy2YLOl)
- [Cryptographic vote-stealing attacks against a partially homomorphic e-voting architecture](https://www.computer.org/csdl/proceedings-article/iccd/2016/07753275/12OmNwCsdCm)
- [To Du or Not to Du: A Security Analysis of Du-Vote](https://www.computer.org/csdl/proceedings-article/eurosp/2016/07467372/12OmNyo1o37)
- [Exploiting the Client Vulnerabilities in Internet E-voting Systems: Hacking Helios 2.0 as an Example](https://www.usenix.org/legacy/event/evtwote10/tech/full_papers/Estehghari.pdf)
- [Security analysis of current voting systems](https://ieeexplore.ieee.org/abstract/document/8252006)
- 2012: [E-voting systems vulnerabilities](https://ieeexplore.ieee.org/abstract/document/6269229)

### Snak og/eller analyse af specifikke algoritmer
- [Cryptanalysis of the GPRS Encryption Algorithms GEA-1 and GEA-2](https://eprint.iacr.org/2021/819)
- [Study and Design of an Encryption Algorithm for Data Transmitted Over the Network by the IDEA and RSA](https://www.researchgate.net/profile/Ahmed-Nashaat-5/publication/348733134_Study_and_Design_of_an_Encryption_Algorithm_for_Data_Transmitted_Over_the_Network_by_the_IDEA_and_RSA/links/600d980545851553a06ae820/Study-and-Design-of-an-Encryption-Algorithm-for-Data-Transmitted-Over-the-Network-by-the-IDEA-and-RSA.pdf)
- Måske relevant? [End-to-End Encrypted Messaging Protocols: An Overview](https://link.springer.com/chapter/10.1007/978-3-319-45982-0_22)
- **[Review of Algorithms for Securing Data Transmission in Mobile Banking](https://www.scirp.org/journal/paperinformation?paperid=127709)**

### Implementation og how-to's
- [Generate keys for encryption and decryption](https://learn.microsoft.com/en-us/dotnet/standard/security/generating-keys-for-encryption-and-decryption)
- Mozilla: [Window: sessionStorage property](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

### Electronic voting manufacturers
- [AccuPoll](https://en.wikipedia.org/wiki/AccuPoll "AccuPoll")
- [Bharat Electronics Limited](https://en.wikipedia.org/wiki/Bharat_Electronics_Limited "Bharat Electronics Limited") (India)
- [Dominion Voting Systems](https://en.wikipedia.org/wiki/Dominion_Voting_Systems "Dominion Voting Systems") (Canada)
- [Electronics Corporation of India Ltd](https://en.wikipedia.org/wiki/Electronics_Corporation_of_India_Limited "Electronics Corporation of India Limited")
- [ES&S](https://en.wikipedia.org/wiki/ES%26S "ES&S") (United States)
- [Hart InterCivic](https://en.wikipedia.org/wiki/Hart_InterCivic "Hart InterCivic") (United States)
- [Nedap](https://en.wikipedia.org/wiki/Nedap "Nedap") ([Netherlands](https://en.wikipedia.org/wiki/Netherlands "Netherlands"))
- [Premier Election Solutions](https://en.wikipedia.org/wiki/Premier_Election_Solutions "Premier Election Solutions") (formerly Diebold Election Systems) (United States)
- [Safevote](https://en.wikipedia.org/wiki/Safevote "Safevote")
- [Sequoia Voting Systems](https://en.wikipedia.org/wiki/Sequoia_Voting_Systems "Sequoia Voting Systems") (United States)
- [Scytl](https://en.wikipedia.org/wiki/Scytl "Scytl") (Spain)
- [Smartmatic](https://en.wikipedia.org/wiki/Smartmatic "Smartmatic")
#### Academic efforts
- [Bingo Voting](https://en.wikipedia.org/wiki/Bingo_Voting "Bingo Voting")
- DRE-i and [DRE-ip](https://en.wikipedia.org/wiki/DRE-i_with_enhanced_privacy "DRE-i with enhanced privacy")
- [Prêt à Voter](https://en.wikipedia.org/wiki/Pr%C3%AAt_%C3%A0_Voter "Prêt à Voter")
- [Punchscan](https://en.wikipedia.org/wiki/Punchscan "Punchscan")

## Videnskabelige artikler
#### Om e-voting
* 2023: [The security of electronic voting: vulnerabilities and solutions](https://www.inria.fr/en/security-electronic-voting-digital-security-confidentiality)
- 2020: [A Survey on Feasibility and Suitability of Blockchain Techniques for the E-Voting Systems](https://arxiv.org/abs/2002.07175)
- 2012: [A conceptual approach to secure electronic elections based on patterns](https://www.sciencedirect.com/science/article/abs/pii/S0740624X12001360)
- 2004: [Building Secure Elections: E-Voting, Security, and Systems Theory](https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1540-6210.2004.00400.x)
- 2010: [Towards Trustworthy Elections](https://link.springer.com/book/10.1007/978-3-642-12980-3)
- 2004: [A secure electronic voting protocol for general elections](https://www.sciencedirect.com/science/article/abs/pii/S0167404804000276)
- 2005: [Coercion-resistant electronic elections](https://dl.acm.org/doi/abs/10.1145/1102199.1102213)
- 2010: [Security analysis of India's electronic voting machines](https://dl.acm.org/doi/abs/10.1145/1866307.1866309)
- 2009: [Security in Large-Scale Internet Elections: A Retrospective Analysis of Elections in Estonia, The Netherlands, and Switzerland](https://ieeexplore.ieee.org/abstract/document/5272405)
- 2012: [electronic elections security](https://books.google.dk/books?hl=en&lr=&id=d3bgBwAAQBAJ&oi=fnd&pg=PR7&dq=electronic+elections+security&ots=g7PRZEzHnx&sig=MR92_YGfO7gmJgL3R9advI3NiF8&redir_esc=y#v=onepage&q=electronic%20elections%20security&f=false) ([info](https://books.google.dk/books?id=d3bgBwAAQBAJ&dq=electronic+elections+security&lr=&source=gbs_navlinks_s))
- 2022: [Development of Electronic Elections Systems: A Review](https://pdfs.semanticscholar.org/7fe1/6ba303dcd6bf9c89fc0ebc3c19d15d7326ea.pdf)
- 2004: [A Security Analysis of the Secure Electronic Registration and Voting Experiment (SERVE)](https://www.cs.unibo.it/~babaoglu/courses/security11-12/resources/documents/serve.pdf)
- 2010: [Election Verifiability in Electronic Voting Protocols](https://link.springer.com/chapter/10.1007/978-3-642-15497-3_24)
- 2010: [electronic elections: The perils and Promises of Digital Democracy](https://books.google.dk/books?hl=en&lr=&id=OOhhIGSca7gC&oi=fnd&pg=PP1&dq=electronic+elections+security&ots=c7P-BSZgf4&sig=70lPhK7txTj4Ob0UEss9l032kRc&redir_esc=y#v=onepage&q=electronic%20elections%20security&f=false)
- 2010:  [Electronic Elections: A Balancing Act](https://link.springer.com/chapter/10.1007/978-3-642-12980-3_7)
- 2010: [Electronic Voting Security 10 Years after the Help America Vote Act](https://www.computer.org/csdl/magazine/sp/2012/05/msp2012050050/13rRUxNW1XL)
- 2007: [Towards secure online elections: models, primitives and open issues](https://www.inderscienceonline.com/doi/abs/10.1504/EG.2007.014161)
- 2004: [Electronic voting systems: security implications of the administrative workflow](https://ieeexplore.ieee.org/abstract/document/1232067)
- 2012: [Security and Elections](https://ieeexplore.ieee.org/abstract/document/6322973)
- 2023: [An Implementation and Analysis of Zero Knowledge Based E-Voting Solution With Proof of Vote on Public Ethereum Blockchain](https://www.computer.org/csdl/proceedings-article/metacom/2023/333300a423/1R1uwIFxK9i)
- 2023: [A Privacy-Preserving E-voting Scheme with Verifiable Format](https://www.computer.org/csdl/proceedings-article/dspp/2023/10404652/1TZNas84dsA)
- 2021: [Epoque: Practical End-to-End Verifiable Post-Quantum-Secure E-Voting](https://www.computer.org/csdl/proceedings-article/euros&p/2021/149100a272/1yg1eK2PSyA)
- 2023: [Election Verifiability with ProVerif](https://www.computer.org/csdl/proceedings-article/csf/2023/219200a488/1On91kycBXy)
- 2023: [Election Verifiability in Receipt-Free Voting Protocols](https://www.computer.org/csdl/proceedings-article/csf/2023/219200a063/1IUu2pu1iqQ)
- 2018: [Improving End-to-End Verifiable Voting Systems with Blockchain Technologies](https://www.computer.org/csdl/proceedings-article/ithings-greencom-cpscom-smartdata/2018/08726502/1axfgfdmNXO)
- 
#### assorterede
- [Domain-Specific Pseudonymous Signatures Revisited](https://eprint.iacr.org/2016/070.pdf)
- [Pseudonymous signatures for eID: efficient and strongly secure dynamic domain-specific pseudonymous signatures](https://eprint.iacr.org/2014/067.pdf)
- [In Encryption We Don’t Trust: The Effect of End-to-End Encryption to the Masses on User Perception](https://ieeexplore.ieee.org/abstract/document/8806742)
- [Why Johnny Can't Encrypt: A Usability Evaluation of PGP 5.0.](https://www.usenix.org/legacy/events/sec99/full_papers/whitten/whitten.pdf)
- [Injection Attacks Against End-to-End Encrypted Applications](https://www.computer.org/csdl/proceedings-article/sp/2024/313000a082/1RjEaQAIfkc)
-  [Text encryption: Character jumbling](https://ieeexplore.ieee.org/abstract/document/8068691)
- [Hiding the Lengths of Encrypted Messages via Gaussian Padding](https://dl.acm.org/doi/abs/10.1145/3460120.3484590)
- [Opportunistic Security: Some Protection Most of the Time](https://datatracker.ietf.org/doc/html/rfc7435)
- [Traffic Morphing: An Efficient Defense Against Statistical Traffic Analysis.](https://git.gnunet.org/bibliography.git/plain/docs/morphing09.pdf)
- [A Formal Analysis Method with Reasoning for Cryptographic Protocols](https://www.computer.org/csdl/proceedings-article/cis/2016/4840a566/12OmNwI8cbd)
- 2023: [WebEV: A Dataset on the Behavior of Testers for Web Application End to End Testing](https://www.computer.org/csdl/proceedings-article/icpc/2023/375000a079/1OKpzyFMBTa)
- 2023: [SEVerity: Code Injection Attacks against Encrypted Virtual Machines](https://www.computer.org/csdl/proceedings-article/spw/2021/373200a444/1v56mdvw5O0)

### Brugbart???
- https://github.com/axboe/fio: # Flexible IO Tester (FIO): [beskrivelse](https://microsoft.github.io/VirtualClient/docs/workloads/fio/)
- 
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
## Other types of sensitive data
**Herfra**: ([LINK](https://hypervault.com/exchange-of-sensitive-data-agencies-best-practices/)) 
1. Login credentials such as usernames and passwords for accessing various platforms, such as Hosting, CMS, ERP, CRM, FTP server, or email marketing tools.
2. API keys, access keys, and tokens required for integrating third-party services or applications.
3. Credit card details and payment information such as bank account numbers, and other payment-related data.
4. [Personally identifiable information](https://hypervault.com/data-templates/personal-identification-information/) (PII) of clients, customers, or employees, such as names, addresses, phone numbers, and email addresses.
5. Intellectual property in the form of design files, source code, proprietary algorithms, patents, or copyrighted material.
6. Confidential documents such as marketing plans, sales strategies, financial projections, and other confidential business information.
7. Contracts & legally binding documents.
8. IT and IT-security-related information such as network architecture diagrams, security policies, or vulnerability assessments.
9. Sensitive multimedia content. This can be unreleased photos, videos, or audio recordings related to a client's project or campaign.
10. Research and development (R&D) data: Information about ongoing or planned R&D projects, including prototypes, experimental data, or research findings
# sikkerheden af ​​elektroniske brevstemmesystemer
# Requirment BS
## Fra den [Franske rapport](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000038661239)sikkerhedsmål: 

### ==niveau 1==
- **mål** nr. 1-01: Implementere en teknisk og organisatorisk kvalitetsløsning, der ikke frembyder en større fejl (fejl offentliggjort af forlaget og/eller offentliggjort af tredjeparter).  
- **mål** nr. 1-02: Definer en vælgerstemme som en atomoperation, det vil sige som omfattende udeleligt valg, validering, registrering af stemmesedlen i stemmeurnen, underskrivelse og udlevering af kvittering.  
- **mål** nr. 1-03: Autentificere vælgere og samtidig sikre, at de store risici forbundet med identitetstyveri reduceres væsentligt.  
- **mål** nr. 1-04: Sikre streng fortrolighed af stemmesedlen fra dens oprettelse på vælgerens computer.  
- **mål** nr. 1-05: Sikre den strenge fortrolighed og integritet af bulletinen under transporten.  
- **mål** nr. 1-06: Sikre, organisatorisk og/eller teknisk, stemmesedlens strenge fortrolighed og integritet under dens behandling og opbevaring i stemmeboksen indtil optælling.  
- **mål** nr. 1-07: Sikre fuldstændig tætning mellem vælgerens identitet og stemmetilkendegivelsen i hele behandlingens varighed.  
- **mål** nr. 1-08: Styrke dataenes fortrolighed og integritet ved at distribuere hemmeligholdelsen, der tillader optælling udelukkende inden for valgkontoret og garanterer muligheden for at tælle fra en fastsat tavshedstærskel.  
- **mål** nr. 1-09: Definer tælling som en atomfunktion, der først kan bruges efter at valgstederne er lukket.  
- **mål** nr. 1-10: Sikre integriteten af ​​systemet, stemmeboksen og stemmelisten.  
- **mål** nr. 1-11: Sikre, at optællingen af ​​stemmeurnen kan verificeres efterfølgende.

### ==niveau 2==
- **mål** nr. 2-01: Sikre høj tilgængelighed af løsningen.  
- **mål** nr. 2-02: Sikre automatisk kontrol af systemets, stemmeboksens og stemmelistens integritet.  
- **mål** nr. 2-03: Tillad automatisk kontrol fra valgkontoret af stemmeplatformens integritet gennem hele valget.  
- **mål** nr. 2-04: Autentificere vælgere ved at sikre, at større og mindre risici i forbindelse med identitetstyveri reduceres væsentligt.  
- **mål** nr. 2-05: Sikre logisk opdeling mellem hver afstemningstjeneste, så det er muligt helt at stoppe en afstemning, uden at dette får den mindste betydning for andre igangværende afstemninger.  
- **mål** nr. 2-06: Brug et informationssystem, der implementerer de fysiske og logiske sikkerhedsforanstaltninger anbefalet af udgivere og ANSSI.  
- **mål** nr. 2-07: Sikre stemmeboksens gennemsigtighed for alle vælgere.

### ==niveau 3==
- **mål** nr. 3-01: Undersøg risici ved hjælp af en gennemprøvet metode for at definere de mest hensigtsmæssige tiltag for implementeringskonteksten.  
- **mål** nr. 3-02: Tillad gennemsigtighed i stemmeboksen for alle vælgere, der anvender tredjepartsværktøjer.  
- **mål** nr. 3-03: Sikre meget høj tilgængelighed af afstemningsløsningen under hensyntagen til risici for større skader.  
- **mål** nr. 3-04: Tillad automatisk og manuel kontrol fra valgkontoret af platformens integritet gennem hele valget.  
- **mål** nr. 3-05: Sikre fysisk opdeling mellem hver afstemningstjeneste, så det er muligt helt at stoppe en afstemning, uden at dette får den mindste indflydelse på andre igangværende afstemninger.