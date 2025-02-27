> [!NOTE] [[Kata-Containers]] designed to provide stronger isolation than traditional containers while maintaining container-like performance
> Each container runs inside a lightweight  [[Virtual Machines|Virtual Machine]] providing hardware-based isolation.
> **Pros:** security & isolation similar to VMs while preserving container workflows
> **Cons:** slightly more resource overhead, slower startup compared to traditional [[Containers]]


![[image_Kata-Containers.png]]
The greatest advantage of Kata containers is the **combination of simplicity and performance**. Nesting containers in full-fledged [[Virtual Machines]] is no longer necessary. The community has instead opted for standard interfaces that simplify entry and connection enormously. Performance remains **consistent** with a standard Linux container, but does not have the normal performance control of a virtual standard machine thanks to the increased isolation. The following graphic illustrates this beneficial structure