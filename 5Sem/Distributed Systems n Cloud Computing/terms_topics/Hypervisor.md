**[[Hypervisor]]:** A piece of computer software, firmware or hardware that creates and runs [[Virtual Machines]].
## Hypervisor Types
![[image_Hypervisor.png]]
### Type 1: [[Type-1-hypervisor|Bare-Metal Hypervisors]]
> [!NOTE] **Type 1:** [[Type-1-hypervisor]]
> - Runs directly on the hosts hardware to control the hardware and to manage guest OSs. For this reason, they are sometimes called [[Type-1-hypervisor|Bare-Metal Hypervisors]]
> - **Examples:** Microsoft Hyper-V, VMware ESXi, Xen, ....
### Type 2: [[Type-2-Hypervisor|Hosted Architecture]]

> [!NOTE] **Type 2:** [[Type-2-Hypervisor]]
> - Runs on a conventional OS just as other computer programs do.
> - A guest OS runs as a [[Process]] on the host.
> - Type 2 hypervisors abstract guest OSs from the host OS
> - **Examples:** QEMU, VirtualBox, VMware Player, VMware Workstation,....