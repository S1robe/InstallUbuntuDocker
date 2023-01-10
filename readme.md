
---

<h3 align=center><p> This is set of guides that walk you through how to install Docker to an Ubuntu (Linux) machine, and Microsoft Windows WSL2 platform.

Scroll to the bottom for a TLDR</p> </h3>

---

<br>
 
 <h1 align=center> -: What is a Virtual Machine? :-</h1>

<p>

Simply, it is a "virtualized" computer, this can be any combination of hardware (cpu, ram, storage, etc...), that is organzed together by a host machine (the one running the VM). 

We typically refer to the virtualized machine as the guest, and the physical machine, host.

- <b>REMEMBER! "Physical" does not always imply that it is physically present.
- Think "available".

<br>

A guest (VM) works off of the host's provided resources (virtual and physical). In some cases the resources can be allocated and deallocated (also called provisioning) while both machines are running simultaneously. 

When we actually create a VM it is called provisioning.
</p>
<br>

<h1 align=center> <b><- Hypervisors -></b></h2>

<p>
You may at some point hear the term "hypervisor".

I prefer to think of it as a "wrapper" for an operating system or hardware because of its function.


[<img src="S1robe/InstallUbuntuDocker/img/hypervisor.webp" width="190"/>](/img/hypervisor.webp)


- Type 1: "Bare Metal" or "Process VMs"
    
    - <h4>Linux "KVM" (Kernel Virtual Machine)</h4>
    - <h4>Windows Hyper-V </h4>
    - <h4>VMware "Vsphere" </h4>

- Type 2: "Hosted" or "System VMs"
    
    - <h4>VMWare (Workstation/Fusion) </h4>
    - <h4>VirtualBox </h4>
    - <h4>Parallels </h4>
    - <h4>QEMU & UTM </h4>
</p>