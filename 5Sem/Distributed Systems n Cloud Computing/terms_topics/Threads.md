> [!NOTE] **Thought Provokers**
> - What is the benefit of using [[Threads]] instead of processes in a distributed system?
> - How do [[Threads]] help hide network latency in distributed clients and servers?
> - How can shared memory between [[Threads]] lead to potential errors, and what approach might help prevent these issues?


> [!warning] **[[Threads]]:** definition
> **Thread:** A minimal software **processor** in whose *context* a series of instructions can be executed. Saving a thread context implies stopping the current execution and saving all the data needed to continue the execution at a later stage.

# **Thread**
- **Definition**: A thread is a lightweight execution unit within a process. A process can have multiple threads sharing the same memory space.
- **Memory**: Threads share the same memory (heap and data) of the process but have their own stack and registers.
- **Communication**: Threads within the same process can communicate easily as they share memory.
- **Overhead**: Threads are lighter and faster. [[Context-Switching]] between threads is quicker compared to processes.
- **Crash Impact**: A crash in one thread can affect the entire process and its threads.
- **Use Case**: Suitable for tasks requiring shared data or parallel execution within a single application.
## Multithreaded Web Client
- **Hiding network latencies**
	- Web browser scans an incoming HTML page, and finds that **more files need to be fetched.** 
		- **Each file is fetched by a separate thread**, each doing a (blocking) [[HTTP]] request. As files come in, the browser displays them
- **Multiple request-response calls to other machines ([[Remote Procedure Call (RPC)|RPC]])**
	- A client does several calls at the same time. each one by a different thread. I then waits until all results have been returned. (Note: if calls are to different servers, we may have a **linear speed-up**)
## Multithreaded [[servers]]
- **Improve performance**
	- Starting a thread is cheaper than starting a new process. Having a single-threaded server prohibits simple scale-up to a **multiprocessor system**. As with clients: **hide network latency** by reacting to next request while previous one is being replied.
- **Better structure**
	- Most servers have high I/O demands. Using simple, **well-understood blocking calls** simplifies the structure. Multithreaded programs ted to be **smaller and easier to understand** due to **simplified flow of control**.
# [[Process vs Thread]]
> [!tip] [[Process]] vs [[Threads]] **VIDEO:** [FANG Interview Question: Process vs Thread](https://www.youtube.com/watch?v=4rLW7zg21gI)
# Why use Threads?
1. **Avoid Needless Blocking:** A single-threaded process will block when doing I/O; in a multithreaded process, the OS can switch the CPU to another thread in that process.
2. **Exploit Parallelism:** TH threads in a multithreaded process can be scheduled to run in parallel on a multiprocessor or multicore processor.
3. **Avoid Process Switching:** Structure large applications not as a collection of process, but through multiple threads.
![[image_Threads-3.png]]
# [[Context-Switching]]
![[image_Threads-1.png]]

**Processor Context:** The minimal collection of values stored in the registers of a processor used for the execution of a series of instructions (e.g., stack pointer, addressing registers, program counter)

**Thread Context:** The minimal collection of values stored in registers and memory, used for execution of a series of instructions (i.e., processor context, state)

**[[Process]] Context:** The minimal collection of values stored in registers and memory, used for the execution of a thread (i.e., thread context, but now also at least MMU register values)

## <mark class="hltr-red">AVOID PROCESS SWITCHING (Avoid expensive [[Context-Switching]])</mark>
![[image_Threads-2.png]]
### Observations
1. **[[Threads]]** share the same address space. **Thread** [[Context-Switching]] can be done entirely independent of the OS.
2. **[[Process]]** switching is generally (somewhat) more expensive as it involves getting the OS  in the loop, i.e., trapping to the kernel
3. Creating and destroying **[[Threads]]** is much cheaper than doing so for **[[Process|processes]]**
### Trade-offs
- [[Threads]] use the same address space: **More prone to errors**
- No support from OS/HW to protect threads using each other's memory
- [[Threads|Thread]] [[Context-Switching]] **may be faster than** [[Process]] [[Context-Switching]]
