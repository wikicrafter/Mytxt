
Hypervisors 
Type 1 <br>
#### Runs natively on host hardware. Some examples:
* Proxmox - It's free 
* ESXi
* Xen 
* Nutanix AHV 

Type 2 runs on top of OS. Examples:
* VirtuaBox 
* VMWare Workstation
* Hyper-V


Tupe 1 hypervisors guarantee that your guest virtual machines have access to more host system resources 

![image](https://user-images.githubusercontent.com/22988682/202482833-fcd81072-898c-4b23-b9c5-ecbb44260efe.png)

#### Containers
* Lightweight, isolated environments 
* Quick to start
* Examples Docker 
* Good choice for small services and quick scalling 
* Create manual or orchestrate with software like Kubernets 

## Planning LAB resources 
* Don't under or overprovision your lab
* Look for clever tricks to conserve resources 

## VM Host resources 
* Many VMs don't use all the resources allocated to them all the time 

My recoomendention is: build your lab according your needs 

#### KVM Switches
What is a KVM Switch? A Keyboard-Video-Mouse (KVM) switch allows a user to control more than one computer with a single keyboard, mouse, and monitor user station (often referred to as a "console"). Users can manage and access thousands of computers or servers from a single "console".


## QEMU  & KVM
* KVM is a linux kernel virtual machine
* QEMU provides emulation tools and standard virtual hardware for VM


### Use FreeNAS 
The FreeNAS Project is an open source storage operating system (OS) that allows the sharing of storage over a network. It was created in 2005 and is based on the open source FreeBSD OS and the OpenZFS OS. FreeNAS software can be downloaded at no cost from freenas.org, and runs on most x86-64 commodity hardware.
##### Note it's called now a TrueNAS
It designed as a Network Attached Storage - NAS

#### Steps u need: 
* Networking 
* Sysadmin 
* Windows and Linux server
* DevOps, orchestration and more
