# USB Shit
## ADD THESE!!!
- [ ] FirmUSB (øverst i [[P5 USB defense stuff]])
It’s another framework with its own syntax to add on to all the others, so it’s another thing to learn and keep track of, even if it is rather simple to understand once getting into it. Also, we’re generating more files in addition to all the other ones; files that, although not necessary to understand, are still a bit obtuse.

The feature of strictness, also means a hissy fit unless you make sure to follow its principles, like strict contracts between services and clear boundaries.

It’s not quick and easy to change things around and experiment in the code, needing to recompile the .proto file each time there’s a change. Also, I could only get the protoc compiler to work through the python-specific sadasdasdasdadasdadasdadasds. 

It must be said, however, that having a single place to look for an idea of how communication should be structured is quite nice. It’s confusing that the two services both need access to the same proto files. Yeah, you can just copy the files, but it’s still awkward from ther perspective of structuring repositories.
# Discussion

**Title:** Between Innovation and Adoption: Bridging Academia and Industry in USB Security

 Innovation and Adoption: 
**Subtitle:** Addressing Misaligned Goals and Practical Barriers to Implementing Research-Driven Defenses

**Title**: Bridging the Gap: Hardware Solutions for Malicious USB Threats

**Subtitle**: Examining the Challenges and Isolation Benefits of Hardware-Centric Approaches in USB Security

**Title:** Closing the Gap: Bridging Academic Insights and Industry Needs in USB Security

**Subtitle:** Addressing Misaligned Goals and the Challenges of Implementing Research-Driven Hardware Solutions

why haven't there been any proper implementations of systems seen in the research?

, mitigation strategies should focus on containing these risks at the earliest point of interaction.

The capabilities of the actual device acting as the intermediary is still an open issue. More powerful processors could allow more of the analysis to be done locally on the device, in the hopes of reducing overhead and latency. However, a slimmed down and focused device, would be less susceptible to common malware.


The trade-offs between local and external handling of data also include considerations like latency, privacy, and bandwidth. For instance, local processing may prioritize speed and security but could be limited by the device’s hardware capabilities. On the other hand, cloud-based analysis offers advanced processing capabilities but introduces risks related to data exposure during transmission and reliance on remote systems.

Ultimately, addressing the risks associated with untrusted USB mass storage devices requires a multi-faceted strategy that incorporates both local isolation and networked resources while accounting for the trustworthiness of each component involved.

This nicely leads to the next part, where'd it like to make some concise conclusions regarding: 
- How the introduction of an intermediary device affects convenience
- balancing usability with strong security measures



**How can an intermediary hardware device leveraging cloud components and machine learning be used to effectively protect systems against malicious USB devices?**

1. What are the most common USB-borne attack vectors (e.g., malware, HID attacks) and how can they be mitigated using an external device without altering the USB protocol?  
 
2. How can computation-heavy tasks such as malware analysis be securely offloaded to the cloud while maintaining acceptable levels of latency and overhead?  

3. What types of machine learning algorithms are most effective for detecting malicious USB device behavior, and how can they be implemented in this architecture?  

4. How does the choice of hardware device versus software implementation affect the system's performance, power consumption, and scalability?