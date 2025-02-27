Thread: unit of execution within a process
> [!NOTE] Main difference: **Generally faster to switch context between [[Threads]] than between [[Process|Processes]]** 
> Fewer states to track, and **more importantly**, since [[Threads]] share the same memory address, there's no need to switch out virtual memory spaces, which is **one of the more expensive** operations during a context switch. (**a single thread can corrupt the entire process, though**)
> 
> **[[Threads|Thread]]**:
> s
> 
> **[[Process]]:**
> s
### **Key Comparisons**

| Feature               | Process                                 | Thread                                         |
| --------------------- | --------------------------------------- | ---------------------------------------------- |
| **Definition**        | Independent program in execution        | Lightweight unit of execution within a process |
| **Memory**            | Own memory space                        | Shares process memory                          |
| **Communication**     | Needs IPC mechanisms                    | Direct memory sharing                          |
| **Creation**          | Slower and resource-intensive           | Faster and less resource-intensive             |
| **Isolation**         | Processes are isolated                  | [[Threads]] are not isolated                       |
| **Crash Impact**      | One process crash doesn't affect others | Thread crash can affect the process            |
| **[[Context-Switching]]** | Slower (requires switching memory)      | Faster                                         |
| **Use Case**          | Independent programs/tasks              | Parallelism within a single program            |
### **Example**
- **Process**: Running a web browser (each tab may run as a separate process).
- **Thread**: A web browser's tab performing multiple tasks like rendering, downloading, and executing scripts, all within the same process.
## [[Context-Switching]]
### Observations
1. **[[Threads]]** share the same address space. **Thread** [[Context-Switching]] can be done entirely independent of the OS.
2. **[[Process]]** switching is generally (somewhat) more expensive as it involves getting the OS  in the loop, i.e., trapping to the kernel
3. Creating and destroying **[[Threads]]** is much cheaper than doing so for **[[Process|processes]]**
### Trade-offs
- [[Threads]] use the same address space: **More prone to errors**
- No support from OS/HW to protect [[Threads]] using each other's memory
- [[Threads|Thread]] [[Context-Switching]] **may be faster than** [[Process]] [[Context-Switching]]

# [[Process]] vs [[Threads|Thread]]
> [!tip] **Quick Definitions:** 
> - **Thread:** A minimal software **processor** in whose *context* a series of instructions can be executed. Saving a thread context implies stopping the current execution and saving all the data needed to continue the execution at a later stage.
> - **Processors:** Provides a set of instructions along with the capability of automatically executing a series of those instructions.
> - **Processes:** A software **processor** in whose context one or more **[[Threads]]** may be executed. Executing a **thread**, means executing a series of instructions in the context of that **thread**.
>
>**VIDEO:** [FANG Interview Question: Process vs Thread](https://www.youtube.com/watch?v=4rLW7zg21gI)
> ![[image_Threads.png]]