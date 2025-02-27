https://dl.acm.org/doi/abs/10.1145/3600006.3613156

The global scale and challenging requirements of modern cloud applications have led to the development of complex, widely distributed, service-oriented applications.

One being the [[Remote Procedure Call (RPC)]], which provides location-independent communication and hides the myriad of cloud communication complexities and requirements within the RPC stack. 

**Understanding RPCs is thus one key to understanding the behavior of cloud applications.** While there have been numerous studies of RPCs in distributed systems, as well as attempts to optimize RPC overheads with both software and hardware, there is still a lack of knowledge about the characteristics of RPCs "in the wild" in the modern cloud environment.

mong other things, we consider the volume, throughput and growth rate of RPCs in the datacenter, the latency of RPCs and their components **==(the "RPC latency tax")==**, and the structure of RPC call chains. Our analysis shows that the characteristics, scope and complexity of RPCs at hyperscale differ significantly from the assumptions made in prior research.