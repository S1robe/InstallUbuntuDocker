
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


![](/img/hypervisor.webp)


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

<h1 align=center> <b> -> Containers <- </b></h1>
<p>
Containers however, are not the same as hypervisors. They are similar as they are able to hide resources from other containers. Container run on roughly the same level as the host's kernel, and from this, provision resources to different instances, and only explicitly what is required for these provisions. 

- Pros: 
    - Consume exactly what is necessary.
    - Containers are hidden from each other (Could go either way)
    - Typically faster than VM's 
    - No need to emulate hardware like VM's

- Cons: 
    - Dont run at bare metal speeds (Theyre virtualized)
    - Not everything runs well on a container
    - Having a backing storage is tricky.


> How do Containers and Virtual Machines differ?

Containers like mentioned before typically run apps or binaries. These are sometimes large programs or server type architecture. 

Virtual machines are standalone Operating systems. This means the entire Operating system, with all its drivers, bits and pieces.

![](/img/conVvm.webp)

However, it should be remembered that they serve different purposes.

Typically Containers are better in the following categories:
 
 - Speed
    
    - They run single applications that are loaded into memory, the OS is already running and read to accept applications

    - Virtual Machines require the OS to be loaded and maintained with a full extra kernel loaded.

- Resources

    - Again since they tend to run only one or a few applications, they only add the memory requried by those applications. Containers dont run applications through a virtualzation layer which saves memory and dont require a hyper visor.

    - This extends into resource allocation; when the Container is shutdown, all of its resources are cleanly returned back to the host.
    If a VM is to be used like a container it must be running at all times which consumes resouces regardless of user interaction.

- Portability
    
    - Because of their small factor image size, containers dont require a full OS every time you run them, just one already running beforehand. 

    - VM's require the full OS, kernel, system libraries, files, directorys, etc...


Again I stress that these are used in different instances, as if you need an entirely isolated workstation, then a Virtual Machine is right for you. 

For example, and editor studio or team of software developers/designers might want thier own workspace. VM's can achieve isolated environments whereas containers might not.
</p>

<h1 align=center> TLDR </h1>

- Containers and Virtual Machines serve different purposes.

- Containers are better if you need rapid deployment and destruction of a particular app or resource, like a web server application. 

- Virtual Machines are better if you need an entirely isolated Operating system, like personal workstation for employees.

- Hypervisors are deployed before virtual machines are created to isolate system resources between the Host and Guest Operating systems. Containers do not have nor need this to function.

- Virtual Machines can:

    - Isolate system resources
    - provide encapsulted environment for testing of entire OS's, Applications, networks, ideas etc
    - Uses Hypervisors
    - Emulates hardware
    - Has a minimum operating requirement
<h2></h2>

- Containers can:
    - Isolate system resources TO APPs
    - provide encapuslated enviroment for testing of single applications
    - No overhead for hardware, virtualization.
    - Operating requirement typically much lower than VM's.
        - requests or is given explicitly what is necessary by Sys Admin or Container Engine to run the Application