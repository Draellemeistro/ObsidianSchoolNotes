# VMs & Containers
## Kubernetes
### Kubevirt ([LINK](https://www.getambassador.io/blog/how-to-run-virtual-machine-vm-local-kubernetes-cluster-guide))
Create, control and use [[Virtual Machines]] inside Kubernetes
# Articles

## PRIME TIME
- [virtualization: issues, security threats and solutions](https://dl.acm.org/doi/abs/10.1145/2431211.2431216?casa_token=r2UbqO1QoaYAAAAA:gL_H3i72COhY3ixniCOQS5ONZGXPnn4EXWi3qF3LcAyMSgN5Kb_B3_Htf558xBWMyp5Qyx4DhiQKwA)
- [VM escape in cloud computing services 2020](https://d1wqtxts1xzle7.cloudfront.net/101585126/Paper_43-Virtual_Machine_Escape_in_Cloud_Computing_Services-libre.pdf?1682667817=&response-content-disposition=inline%3B+filename%3DVirtual_Machine_Escape_in_Cloud_Computin.pdf&Expires=1733930108&Signature=Ap6ICcIt0v-IQ6hAvEi76OdsUXBnSguO4nPoLHItj3JWmKBEwsDxGRwiM9IROWrkJ8nk77Lgc3s1n~U7Fw6KL-hStZwI4T9~lyq1bTdw2Q04-pkZtNEo4LaoW2AeaRJlPHFdvRASQDbbofqRXWv29LXawos4xGcJqYOeh0itAKqVf4eoXduZulhIPKwB4m4d-~tverrHwBC5UnuUsVmuTSw8ZCNI2Fisq6MJqIsYQluO5hmMycl-eikUkhKLGgrCdYguPhj5zgYE9hoV5gJCpXEiKO5ibdDaKTOp0QgpRe3DNIO4CYYBUmFXb2ung7Tw9YYATjlp-5LunlhKLmw7NQ__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)
- [NIST virt guidelines](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-125.pdf)
- [A survey of security issues for cloud computing](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S1084804516301060)
- 
## [A survey of security issues for cloud computing](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S1084804516301060)
we present a survey of security issues in terms of security threats and their remediations. The contribution aims at the analysis and categorization of working mechanisms of the main security issues and the possible solutions that exist in the literature. We perform a parametric comparison of the threats being faced by cloud platforms. Moreover, we compare various [intrusion detection and prevention](https://www-sciencedirect-com.zorac.aub.aau.dk/topics/computer-science/intrusion-detection-and-prevention "Learn more about intrusion detection and prevention from ScienceDirect's AI-generated Topic Pages") frameworks being used to address security issues.

**application-level sandboxing** attempts to address malware threats by containing their malicious behavior. High-profile applications that now employ sandboxing include the Google Chrome browser, Internet Explorer Protect Mode, and Adobe Reader X.

there are in fact several techniques to encapsulate and contain bad behavior from exploited Internet-based applications and mal-ware. These techniques range from restricting account privileges to defining a separate file system for an application to running an application in its own full virtual machine. **Separating untrusted code from the rest of the system using some form of a sandbox can significantly mitigate the malware threat by preventing malicious actions from compromising the desktop.**

#### SANDBOXING
**Sandboxes are typically applied to the components of the application with the highest vulnerability.** The sandboxed process runs with restricted privileges and will em-ploy DLL hooking and memory trampolines as needed to certain APIs. This means that the sandbox can examine certain system calls for malicious behavior, then rewrite or block them as appropriate.

Internet Explorer's Protect Mode can be bypassed by exploiting the fact that it's disabled for local or intranet zone sites. **This type of kernel exploitation has become a favorite target of hackers, partially due to the emergence of application sandboxes.**

B**esides kernel vulnerabilities, sandboxing still leaves the desktop open to attacks that involve asking the user's permission**. Attacks that lure users into installing software, such as a codec multimedia plug-in, will effectively bypass the sandbox. These so-called trust-exploitation attacks convince users to install software unwittingly by sending links to malicious sites from users in the victim's social network or as tweets from people the user follows on Twitter. Rogue antivirus sites often bait users to install malicious software by scaring them into clicking on dialog boxes that supposedly clean up infections. **If a user can be lured or scared into clicking through dialog boxes that install software, then application sandboxes aren't going to provide much protection, even if they ask users if they want to install the software twice.**

#### PARTIAL VIRTUALIZATION
usually involve a combination of privilege restrictions by user accounts and a virtual file system.

The “virtualization” typically refers to providing the target application the appearance of its own virtual file system, of-ten including a system registry on Windows, so that file writes are to this virtualized resource rather than the file system of the underlying host.

**What distinguishes partial virtualization techniques from [[Full-Virtualization]] is that partial virtualization approaches share the same OS kernel as the host. Consequently, an exploit of the kernel will defeat a partial virtualization approach.**
#### [[Full-Virtualization]]
[[Full-Virtualization]] provides a high degree of containment, in terms of the vulnerable application’ without requiring changes to the application. If any piece of the application is exploited, the attacker only succeeds in gaining access to the guest environment's data, applications, resources, and OS, not the underlying host's.
**The isolation afforded by [[Full-Virtualization]] can present significant usability challenges.**

==**Users have low tolerance for security mechanisms that introduce friction into the experience.**==

While hardware virtualization approaches provide kernel confinement from the host OS, it does not, by default, provide network confinement, which prevents an infected process from causing damage on the network.

**Real-time detection of unknown threats coupled with automated recovery to a known pristine image is necessary to prevent an infected virtual machine from compromising user sessions and credentials or attacking other machines on the network.**

Finally, the virtualization layer itself might be attacked by malicious code through vulnerabilities in its interface with software running in the virtual machine. Advanced inspection techniques can be employed to vouch for the virtualization layer's integrity to ensure it isn't compromised by malicious software.