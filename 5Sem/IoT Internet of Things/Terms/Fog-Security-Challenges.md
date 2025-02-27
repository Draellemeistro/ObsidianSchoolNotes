## Open Security challenges in Fog computing
#### Trust and Privacy
- The fog allows applications to process user’s data in third-party’ s hardware/software. This introduces strong concerns about data privacy and its visibility to those third-parties
- **Isolation and sandboxing mechanisms must be in place to ensure bidirectional trust among cooperating parties**
Source: L.M. Vaquero, L.Rodero-Merino, “Finding your Way in the Fog: Towards a Comprehensive Definition of Fog Computing”, ACM SIGCOMM Computer Comm. Review, Vol. 44, No 5, October 2014
#### Authentication
- Designing and implementing authentication and authorization techniques that can work with multiple fog nodes that have different computing capacities is difficult.
- **Public-key infrastructures and trusted execution environments are potential solutions**
Source: I. Stojmenovic and S. Wen, “The Fog Computing Paradigm: Scenarios and Security Issues,” Proc. 2014 Federated Conf. Comp. Sci. and Info. Sys.(FedCSIS14), 2014, pp. 1–8
#### Enabling real-time analytics
- In fog environments, resource management systems should be able to dynamically determine which analytics tasks are being pushed to which cloud or edge-based resource. These systems also must consider other criteria such as various countries’ data privacy laws involving, for example, medical and financial information
Source: Amir Vahid Dastjerdi, Rajkumar Buyya, "Fog Computing: Helping the Internet of Things Realize Its Potential", Computer, vol. 49, no. , pp. 112-116, Aug. 2016, doi:10.1109/MC.2016.245
#### Access Control
- Data ownership will be a very important cornerstone of the fog, where some applications will be able to use the network to run applications and manage data without relying on centralised services. In fog computing, we can also raise questions like how to design access control spanning client-fog-cloud, to meet the goals and resource constraints at different levels.
Source: Yi, S., Li, C. & Li, Q. (2015). A Survey of Fog Computing: Concepts, Applications and Issues.. In Q. Li & D. Xuan (eds.),Mobidata@MobiHoc (p./pp. 37-42), : ACM. ISBN: 978-1-4503-3524-9

#### Data Leakage
- Fog nodes may be more vulnerable to physical attacks, increasing the risk of data leakage
#### Data Tampering
- Ensuring the integrity of data at the edge is a concern, especially when data is collected from untrusted sources.



# The gist of it

In general, the [[Fog computing]] paradigm consists of **a highly dynamic and decentralized environment** where devices MOVE, JOIN and LEAVE the network. In such a setting, it is challenging to manage secure **access control, determine the trustworthiness of devices**, manage the security of edge devices **throughout their entire lifecycle**, including updates and patch management, etc.