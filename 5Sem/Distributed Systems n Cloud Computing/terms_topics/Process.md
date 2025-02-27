> [!NOTE] **[[Process]]** Definition
> **Processes:** A software **processor** in whose context one or more **[[Threads]]** may be executed. Executing a **thread**, means executing a series of instructions in the context of that **thread**.
> 
> **Processors:** Provides a set of instructions along with the capability of automatically executing a series of those instructions.

# sdasdasd
## Context
**[[Process]] Context:** The minimal collection of values stored in registers and memory, used for the execution of a thread (i.e., thread context, but now also at least MMU register values)
**Processor Context:** The minimal collection of values stored in the registers of a processor used for the execution of a series of instructions (e.g., stack pointer, addressing registers, program counter)
> [!warning] <mark class="hltr-red">AVOID PROCESS SWITCHING (Avoid expensive [[Context-Switching]])</mark>
![[image_Threads-2.png]]

### **Process**
- **Definition**: A process is an independent program in execution with its own memory space.
- **Memory**: Each process has its own memory (heap, stack, data, and code segments). Processes are isolated from each other.
- **Communication**: Inter-process communication (IPC) is needed to share data between processes (e.g., pipes, message queues, shared memory).
- **Overhead**: Processes are heavier and require more resources. Switching between processes ([[Context-Switching]]) is slower due to memory and state separation.
- **Crash Impact**: A crash in one process does not affect other processes.
- **Use Case**: Useful for running independent tasks that do not need to share memory.