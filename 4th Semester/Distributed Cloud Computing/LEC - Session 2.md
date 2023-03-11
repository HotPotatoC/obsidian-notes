# LEC - Session 2
Class: [[COMP6710001 - Distributed Cloud Computing]]
Session: 2
Topics: Distributed system Models
Date: 2023-02-22
Lecturer: [[D6667 - SAID ACHMAD, S.Kom., M.Kom]]

# Technologies for Network-Based Systems

## Multi-core CPUs and Multithreading Technologies

CPU's today assume a multi-core architecture with dual, quad, six, or more processing cores. The clock rate increased from 10 MHz for Intel 286 to 4 GHz for Pentium 4 in 30 years. However, the clock rate reached its limit on CMOS chips due to power limitations. Clock speeds cannot continue to increase due to excessive heat generation and current leakage.

![[Pasted image 20230222133215.png|center]]

![[Pasted image 20230222133320.png]]

L1 cache is private to each core, L2 cache is shared and L3 cache or DRAM is off the chip. Examples of multi-core CPUs include Intel i7, Xeon, AMD Opteron. Each core can also be multithreaded. E.g. the Niagara II has 8 cores with each core handling 8 threads for a total of 64 threads maximum.

## Memory, Storage and WAN

DRAM chip capacity increased from 16 KB in 1976 to 64 GB in 2011 for a 4x increase in capacity every 3 years. Memory access time did not improve as much.

For hard drives, capacity increased from 260 MB in 1981 to 20 TB for the Seagate IronWolfhard drive in 2020

Faster processor speed and larger memory capacity result in a wider performance gap between processors and memory. The memory wall may become an even worse problem limiting CPU performance.

## System-Area Interconnects

A LAN is typically used to connect clients to big servers. A Storage Area Network (SAN) connects servers to network storage such as disk arrays. Network attached storage (NAS) connects servers directly to disk arrays. All 3 types of networks often appear in a large cluster built with commercial network components.

### 1. NAS (Network Attached Storage)

A NAS is fundamentally a bunch of disks, usually arranged in a disk array. Users and servers attach to the NAS primarily using TCP/IP over Ethernet, and the NAS has its own IP address. The primary job of a NAS is to serve files, so most NAS systems offer support for Windows networking, HTTP, plus file systems and protocols such as NFS.

![[Pasted image 20230222133647.png]]

### 2. SAN (Storage Area Network)

SANs allow multiple servers to share a RAID, making it appear to the server as if it were local or directly attached storage, and it cannot be accessed by individual users. A dedicated networking standard, Fiber Channel, allow blocks to be moved between servers and storage at high speed.

![[Pasted image 20230222133608.png]]

## Virtual Machines and Virtualization Middleware

To build clouds we need to aggregate large amounts of computing, storage, and networking resources in a virtualized manner. Specifically, clouds rely on the dynamic virtualization of CPU, memory, and I/O.

**Virtual Machines**

The VM is built with virtual resources managed by a guest OS to run a specific application.

![[Pasted image 20230222134322.png]]
![[Pasted image 20230222134327.png]]

