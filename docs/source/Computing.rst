Scientific Computing
====================
.. contents:: Table of Contents
   :depth: 2
Operating Systems, Networking and Virtualization
------------------------------------------------

The Linux Operating System (OS)
...............................

**Operating Systems:** is a software program that manages and controls the hardware and software resources of a computer system. It acts as an intermediary between the user, applications, and the computer hardware, providing an environment in which programs can run and interact with the underlying hardware components. The primary functions  of an operating system are to manage processes, memory, file systems, the device and the user interfaces.

*Processes vs Services:* 
**Process:** A process is an executing instance of a program. It represents a running program and includes the program's code, data, and resources. Each process has its own unique process identifier (PID).
**Services:** A service, in the context of Linux, generally refers to a program or a process that runs in the background (seamlessly) and provides specific functionality or performs certain tasks. Services are typically designed to start automatically when the system boots up and continue running in the background, even when no user is logged in.

**Daemon Services**: Daemon services are background processes that run continuously on a computer system, providing system-related services without requiring direct user interaction, such as network services or log management. They are managed by the system-init systems and operate independently of user sessions.

**Server-Client Architecture:** is a computing model where a central server provides services or resources to multiple client devices over a network. The server acts as a powerful host, managing data, applications, or services, while clients are devices that request and consume those services. This architecture enables efficient distribution of resources, with the server handling client requests and delivering the requested information or services. It allows for centralized management, scalability, and flexibility, making it widely used in various applications, such as web services, email systems, and file sharing networks.

**The** ``root`` **user on linux**: has the highest degree of control and has permission to execute any type of command.

Linux Directories
.................

- ``/bin`` (Binaries): Contains essential binary executables (programs) that are available to all users and are required for basic system functionality.
- ``/etc`` (Etcetera): Stores system configuration files, including network settings, user account information, software configurations, and various system-wide configuration files.
- ``/home`` (Home directories): Each user on the system has their own subdirectory in /home, where their personal files and settings are stored.
- ``/lib`` (Libraries): Houses shared libraries needed by the system and various programs. 
- ``/root`` (Root Home): Home directory for the root user (superuser/administrator).
- ``/tmp`` (Temporary): Provides a location for temporary files that can be used by programs or users. The contents of this directory are typically cleared on system reboot.
- ``/usr`` (Unix System Resources): Contains a wide range of user-related programs, libraries, documentation, and other resources.
- ``/var`` (Variable): Holds variable data files, such as log files, spool directories (for print queues and mail), temporary files used by programs, and more.
- ``/dev`` (Devices): Represents device files that correspond to physical and virtual devices on the system, allowing programs to interact with them.
- ``/proc`` (Process Information): Provides a virtual file system that contains information about running processes and system configuration, which can be accessed by programs.
- ``/mnt`` (Mount): Serves as a temporary mount point for mounting external or remote file systems.
- ``/boot`` (Bootloader): Contains files necessary for system booting, including the bootloader configuration, kernel images, and initial RAM disk (initrd).

Networking
..........

*Global IP* addresses are unique addresses assigned to devices on the internet, allowing them to communicate with other devices across the world, while *local IP* addresses are used within a private network to identify devices and facilitate communication within the local network but are not directly accessible from the internet.

*Global (Public) IP range:* 0.0.0.0 - 255.255.255.255

*Local IP ranges:* 
10.0.0.0 - 10.255.255.255  |  172.16.0.0 - 172.31.255.255



Rocky Linux Basics and Virtual Access
-------------------------------------

Rocky Virtual Machine
.....................

Since the Linux environment is open-sourced, it is configured by many different distributors, some of the most famous ones are Ubuntu, Redhat, Centos, ... etc. The one we will be using is called Rocky, which is configured by Redhat Enterprise. We use Rocky specifically since the majority of the servers at SESAME are configured using Rocky. So, as a first step to take is to have **Rocky version 8** installed. 
In order to start working with a Linux environment, one must have access to the Operating System. However, as most people who possess personal computers usually use Windows and MacOS, we have to establish an alternate environment to install the Linux OS. 

**Virtual Machines**  are computer systems created using software on one physical computer in order to emulate the functionality of another separate physical computer. Therefore, we can take advantage of the hardware on the PC that we have to operate a LinuxOS through a virtualized environment. 

In order to do that we have to intall a popular virtual machine system called **VMware Workstation 17 Player** that allows us to handpick the specs of the virtual machine to our liking. 

After we have installed Rocky 8, we must configure our VM using VMware:

- Open VMware and press "Create a New Virtual Machine".
  
- A new window will pop up, choose the option "Installer Disc Image File", and choose the Rocky 8 file you have downloaded previously.
  
- Choose Linux as your OS and choose "Red Hat Enterprise Linux 8 64-bit". 

- Choose an appropriate name for your VM.

- For the disk size, 15-20 GB should be more than enough. Also choose "Store virtual disk as a single file" as it is a better practice to have all the environment installed in one place.

- Now, we must customize our hardware. The following image shows what you should be seeing on the window:

- We need at least 3 GB for the memory of the VM, in order for it to work smoothly, and please make sure that the "Network Adapter" is set for NAT, as it should extend its network locally from your machine.
 

Now you should be good with setting up your personal virtual machine. You just have to access your VM and make sure it is conifgured properly and connected to the network. Also, make sure to install the LinuxOS environment with a *GUI* in order to have easier access to different packages and facilities later on.

Create a new user with a password and you should be set!

**Basic Linux Commands on Rocky 8:** 

- ``ifconfig`` or ``ip a``: Display or configure network interface information.
- ``cd``: Change the current directory.
- ``cp``: Copy files or directories.
- ``ls``: List directory contents.
- ``useradd``: Create a new user.
- ``passwd``: Set or change a user's password.
- ``su``: Switch to a different user.
- ``whoami``: Display the current user's username.
- ``awk``: A text processing tool used to extract and manipulate data.
- ``ll``: List files and directories in a long format.
- ``mv``: Move or rename files and directories.
- ``rm``: Remove files or directories.
- ``du``: Display disk usage of files and directories.
- ``df -h``: Display disk space usage in a human-readable format.
- ``cat``: Concatenate and display file contents.
- ``uname -r``: Show the kernel version.
- ``tail -n``: Display the last n lines of a file.
- ``head -n``: Display the first n lines of a file.
- ``vim``: A text editor for creating and modifying files.
- ``yum``: Package manager for CentOS and RHEL-based distributions.
- ``dnf``: Package manager for Fedora and newer RHEL-based distributions.
- ``top``: Monitor system processes and resource usage.
- ``scp``: Securely copy files between local and remote systems.
- ``xkill``: Forcefully terminate a graphical application.
- ``ps aux``: Display information about running processes.
- ``grep``: Search for specific patterns in files or output.



Remote Network Protocols
........................

**Data Transfer Protocols (FTP, SFTP):** FTP (File Transfer Protocol) and SFTP (Secure File Transfer Protocol) are methods used to transfer files between systems over a network, with SFTP providing an additional layer of security by encrypting the data being transferred.

**Internet Protocols (HTTP, HTTPS):** HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are communication protocols used for transmitting data over the internet, with HTTPS providing encryption and authentication to secure the data exchanged between a web server and a client, ensuring a safer browsing experience.

At SESAME, the Scientific Computing Department uses a very big cluster of servers that all run hundreds of virtual machines. Therefore, having a remote access method to these virtual machines is necissary and very needed to have control over the servers over the local SESAME network without having to physically plug in your laptop and make changes to each server.

Some of the Remote Access Protocol methods used at SESAME include:
* SSH
* VNC
* NoMachine

Ports for servers: 

- SSH: 22
- HTTP: 80
- HTTPS: 443
- NoMachine: 5000

*Firewall Management:* Ports in the device allow for data transfer, managing the data going in and out. 


**SSH (Secure Shell):** is a network protocol that provides a secure and encrypted method for remote access to and management of systems over an unsecured network.

**VNC (Virtual Network Computing):** is a graphical desktop-sharing system that allows remote control of a computer desktop, enabling users to access and interact with a remote system as if they were physically present.

We can utilize SSH or VNC protocols to access our VM from our Windows or MacOS environments with **MobaXterm**: 

MobaXterm: is a comprehensive remote desktop and networking tool that combines various utilities and protocols into a single platform, facilitating efficient remote access and system administration.
Therefore, we need to install MobaXterm as it has a better GUI to accessing and controlling the command line in our VM.

Steps to connect via SSH:

* Note that we can establish a SSH connection between two VM's as long as they share the same local network. 

- we can do that by writing ``ssh user@IPaddress``, to access a specific user or the root by just writing "root" instead of "user" and the IPadress which we can get from writing ``ifconfig`` or ``ip a``.

Steps to connect via VNC: 

Establishing a VNC network is a quite long and specific process, I recommend the looking up how to install a VNC viewer on Linux and access it through you own OS (Windows or MacOS). 
Here are some links that should be helpful:

- https://cat.pdx.edu/platforms/windows/remote-access/vnc-to-linux/
  
- https://linuxhint.com/install-realvnc-vnc-viewer-linux/#:~:text=8%20Linux%20distribution.-,First%2C%20visit%20the%20official%20download%20page%20of%20RealVNC%20VNC%20Viewer,the%20VNC%20Viewer%20installation%20file.
  
- https://techviewleo.com/install-and-configure-vnc-server-on-rocky-linux/?expand_article=1

**SSH Public/Private key:** is a secure method for accessing remote systems. The public key is stored on the server, while the private key remains with the user. When connecting, the client uses their private key to authenticate with the server by proving they possess the corresponding public key, ensuring secure and encrypted communication.

In order to establish a SSH network without asking for a password or verification, establishing a private/public key would ensure that the client accessing the server is secure for any later attempts to access the server.

A very helpful link to build a SSH Public/Private key on Rocky Linux 8: 

- https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-rocky-linux-8

File Sharing Protocols
----------------------

**File Sharing Protocols:** are standardized methods for transferring files over a network. They define rules and formats for efficient and secure transmission, enabling users to share files across different devices and systems seamlessly.

**Network File System (NFS):** is a distributed file system protocol that allows remote access to files over a network. It enables a client system to mount and access directories located on a remote server as if they were local. By using NFS, multiple clients can simultaneously access and share files, facilitating seamless collaboration and centralized storage in networked environments.

- Linux uses NFS
- Windows uses Samba
- FTP is cross platform

In order to set up an NFS Mount on LinuxOS (Rocky), please use this link as a guide:

- https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-rocky-linux-8


Using the ``systemctl`` Command: A system management tool to get access and control over different systems in the OS. (could give firewall as example) (when you enable, it's only doing so when booting so usually you have to reboot, you can put --now so it would enable instantly)

- Start and stop, i.e. ``systemctl stop firwalld.service``
  
- Enable and disable, i.e. ``systemctl enable firwalld.service``

- Status: things to look for enabled and active, i.e. ``systemctl status firwalld.service``



Process of verification of network:

- Ping the IP address
- Ping the local host
- Browse http://localhost

**iptables:** is a powerful firewall utility in Linux used for configuring and managing network traffic rules. It allows system administrators to define and enforce rules to filter and manipulate network packets, providing security and control over network connections. By leveraging iptables, administrators can control access to services, block malicious traffic, and set up port forwarding or network address translation (NAT) rules.

iptables Commands: 

``iptables -L``: manages rules in the firewall. 

``iptables -F``: (DO NOT RUN THIS COMMAND) F is for flush, flushes all the implemented rules (deletes them), then you would have to re-build all the rules again one by one. 

**Permissions in Linux:** define the level of access and control users and groups have over files and directories. They are set using three categories: owner, group, and others. Each category can have three types of permissions: read, write, and execute, determining whether users can view, modify, or execute a file or directory.

*The Form of Permission Information:* Permissions are stored in 3 fields, each represented by 3 bits, meaning that each field has a range of values from 0-7. Since the maximum value of 3 bits is 7. 

The fields: 

- User Permission (3-bits) (000-111)

- Group Permission (3-bits) (000-111)

- Other Permission (3-bits) (000-111)

As each permission field has a binary representation, the first binary bit in the 3-bits is for reading, second is for writing, and third is for execution.

Example: 111 110 100

Value: 	 7   6   4

Full access: 7 7 7 

``cat/etc/shadow``: contains passwords but encrypted and unreadable. 

``cat/etc/password``: all details about the user.

**User groups (grouping techniques):** adding users to certain groups, each group would require a different level of permission, and accordingly would be granted access to certain facilities. 
User id’s and groups id’s: stored to separate people, since two users could have the same name but not the same id.

**Normal and Superusers:** Superusers have the same privileges as the root user. You have to use the ``sudo`` command if user belongs to super-user group. The superuser group is called ``wheel`` group on Linux.

``etc/sudoers`` contains superusers and their privileges.


High-End Computing Services and infastructure
---------------------------------------------

**High-End Computing Services and Infrastructure:** refer to advanced computing resources and facilities designed to handle large-scale and computationally intensive workloads. These services often involve high-performance computing (HPC) clusters, supercomputers, or cloud-based infrastructures that provide exceptional processing power, storage capacity, and network capabilities. They are utilized by researchers, scientists, and organizations to tackle complex problems that require significant computational resources.

**High-performance computing (HPC):** refers to the practice of using advanced computing systems and techniques to solve problems that demand substantial computational power and efficiency. HPC systems are specifically designed to deliver exceptional performance, enabling the execution of complex simulations, data analysis, and modeling tasks. They leverage parallel processing, utilizing multiple processors or cores to divide and conquer tasks, allowing for faster and more efficient execution.

These technologies play a crucial role in various fields such as scientific research, engineering, weather forecasting, molecular modeling, and financial analysis, where massive amounts of data processing, simulations, or computations are required. High-End Computing Services and Infrastructure, along with high-performance computing, provide the foundation for accelerating research, innovation, and data-driven decision making by offering immense computational capabilities and scalability to meet the evolving needs of modern computing.

Computing Project
-----------------

- Build new VM on your computer with Rocky Linux 8.7: 
    Follow the instructions in the Rocky Virtual Machines section. 
- Add user: sesame, make it a sudoer:
    Follow the instructions in the File Sharing Protocols section. 
- Install VNC server, enable sesame user to access the VM via VNC:
    Follow the steps in the Remote Network Protocols section.
- Install MediaWiki and publish it on LAN:
    The following link is very helpful to establish a local web-based server through MediaWiki:
    https://techviewleo.com/install-mediawiki-on-rocky-almalinux-with-lets-encrypt/?expand_article=1
