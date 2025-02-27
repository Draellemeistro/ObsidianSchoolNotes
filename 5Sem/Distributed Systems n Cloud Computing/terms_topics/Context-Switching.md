> [!FAIL] <mark class="hltr-red">AVOID PROCESS SWITCHING (Avoid expensive Context-Switching)</mark>

> [!NOTE] Main difference: **Generally faster to switch context between [[Threads]] than between [[Process|Processes]]** 
> Fewer states to track, and **more importantly**, since [[Threads]] share the same memory address, there's no need to switch out virtual memory spaces, which is **one of the more expensive** operations during a context switch.

**Processor Context:** The minimal collection of values stored in the registers of a processor used for the execution of a series of instructions (e.g., stack pointer, addressing registers, program counter)

**Thread Context:** The minimal collection of values stored in registers and memory, used for execution of a series of instructions (i.e., processor context, state)

**[[Process]] Context:** The minimal collection of values stored in registers and memory, used for the execution of a thread (i.e., thread context, but now also at least MMU register values)
![[image_Threads-1.png]]
## <mark class="hltr-red">AVOID PROCESS SWITCHING (Avoid expensive [[Context-Switching]])</mark>
![[image_Threads-2.png]]
### Observations
1. **[[Threads]]** share the same address space. **Thread** [[Context-Switching]] can be done entirely independent of the OS.
2. **[[Process]]** switching is generally (somewhat) more expensive as it involves getting the OS  in the loop, i.e., trapping to the kernel
3. Creating and destroying **[[Threads]]** is much cheaper than doing so for **[[Process|processes]]**
### Trade-offs
- [[Threads]] use the same address space: **More prone to errors**
- No support from OS/HW to protect [[Threads]] using each other's memory
- [[Threads|Thread]] [[Context-Switching]] **may be faster than** [[Process]] [[Context-Switching]]
