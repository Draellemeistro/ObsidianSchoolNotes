fra [[CLoud 1 introductions]] (se også [[Terms_L1-Intro_to_Cloud]])

> [!NOTE] **Definition:** [[Virtualization]], the key to the cloud
> **[[Virtualization]]:** Creating a virtual (_rather than an actual_) version of something, including but not limited to a virtual computer hardware platform, OS, storage device, or computer network resources.
> 
> **[[Hypervisor]]:** A piece of computer software, firmware or hardware that creates and runs [[Virtual Machines]].
> 
> **[[Virtual Machines|Virtual Machine (VM)]]:** A software based, fictive computer
# Thought starters
- How does virtualization enable [[cloud computing]]?
# [[Virtualization]]
## Virtualization Types
![[virtualization-types.png]]
### [[Full-Virtualization]] (emulation)
> [!NOTE] [[Full-Virtualization]] (emulation)
> - The [[Hypervisor]] emulates some hardware for the guest OS
> - Not necessary to perform any modification on the guest OS
> - **The [[Hypervisor]] dynamically translates the instructions received.**
> 
### [[Para-Virtualization]]
> [!NOTE] [[Para-Virtualization]]
> - No hardware emulation
> - The [[Hypervisor]] provides a special API different from the one provided by the hardware.
> - The guest OS needs certain modifications to interact with the [[Hypervisor]]
### [[Hardware-Assisted-Virtualization]]
> [!NOTE] [[Hardware-Assisted-Virtualization]]
> - Full [[Virtualization]], that takes advantage of the hardware instructions implemented in current processors.
> - efficiency of emulation increases, while reducing the overhead of instruction translation.
### [[OS-Level-Virtualization]] ([[Containers]])
> [!NOTE] [[OS-Level-Virtualization]] ([[Containers]])
> - It is a quite new way of [[Virtualization]] in which the guest OS shares the same running instance of the host OS
> - They share the kernel of the OS, although each OS works as if it was running in an isolated environment.
> - this is the tech used by [[Containers]], which would be the equivalent to typical [[Virtual Machines]]
## Virtualized Systems
> [!NOTE] **Comparison:** [[Virtualization]] of [[Virtual Machines|Virtual Machines]] and [[Containers]] (_note the [[Hypervisor]]_)
> ![[image_Virtualization-1.png]]
### [[Virtual Machines]]
#### Se den her fra P5: [[State Cloud og VM-Containers]]
### [[Containers]]
### [[Kata-Containers]]
### [[Containers]] vs. [[Virtual Machines]]

# [[Hypervisor]]
ssssss
## Hypervisor Types
### [[Type-1-hypervisor]]
> [!NOTE] **Type 1:** [[Type-1-hypervisor]]
> - Runs directly on the hosts hardware to control the hardware and to manage guest OSs. For this reason, they are sometimes called [[Type-1-hypervisor|Bare-Metal Hypervisors]]
> - **Examples:** Microsoft Hyper-V, VMware ESXi, Xen, ....
> 
### [[Type-2-Hypervisor]]
> [!NOTE] **Type 2:** [[Type-2-Hypervisor]]
> - Runs on a conventional OS just as other computer programs do.
> - A guest OS runs as a [[Process]] on the host.
> - Type 2 hypervisors abstract guest OSs from the host OS
> - **Examples:** QEMU, VirtualBox, VMware Player, VMware Workstation,....

