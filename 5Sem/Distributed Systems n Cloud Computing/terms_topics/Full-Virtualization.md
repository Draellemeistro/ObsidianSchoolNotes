
> [!NOTE] [[Full-Virtualization]] (emulation)
> - The [[Hypervisor]] emulates some hardware for the guest OS
> - Not necessary to perform any modification on the guest OS
> - **The [[Hypervisor]] dynamically translates the instructions received.**
> 
> ![[image_Full-Virtualization-2.png]]
# Extra
[[Full-Virtualization]] provides a high degree of containment, in terms of the vulnerable application’ without requiring changes to the application. If any piece of the application is exploited, the attacker only succeeds in gaining access to the guest environment's data, applications, resources, and OS, not the underlying host's.
**The isolation afforded by [[Full-Virtualization]] can present significant usability challenges.**