Provides more reliable communication (**Redundant paths**)
![[image_Mesh Topology.png]]

-  A **physical or logical network topology** in which every node (device) is interconnected with multiple other nodes. Data can travel along multiple paths to reach its destination.
- **Key Characteristics**:
    
    - **Full Mesh**: Every node is connected to every other node.
    - **Partial Mesh**: Nodes are connected to only some other nodes, but still have multiple paths to communicate.
    - Uses **routing** to determine the best path for data.
- **Connectivity**:
    
    - Redundant paths between nodes ensure robustness and fault tolerance.
    - If one connection fails, data can take an alternative route.
- **Examples**:
    
    - IoT networks like Zigbee or Thread.
    - Wireless mesh networks (used in smart cities, industrial IoT).
- **Advantages**:
    
    - High fault tolerance.
    - Scalable for large networks.
    - Reliable communication due to multiple data paths.
- **Disadvantages**:
    
    - More complex to set up and manage.
    - Requires more power and processing resources for routing.