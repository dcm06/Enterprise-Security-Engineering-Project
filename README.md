# Enterprise-Security-Engineering-Project
By David Madubuko

As a Cybersecurity student at Fanshawe college, i have gained theoretical and hands on experience on cybersecurity concepts from Network Design and Security, Operating System Hardening and security, Penetration Testing, Cloud Design and Security Concepts. In this project, I will be demonstrating the core concepts in a complete mini-enterprise security lab setup, from network and perimete design to Penetration testing, to auditing and documentation.

## Description

The Lighthouse Superstores has 1 branch, which consists of 1 Domain Controller which is the DNS and DHCP server, will have a Web server, File Server and Database server, 1 management PC, 2 office PC, and 2 store devices.

In this project, the following Subnets have been configured as VLANS will be used:
* Servers LAN Segment(192.168.1.0/28)
* Internal Management Lan Segment (192.168.1.16/28)
* Office Lan Segment (192.168.1.32/28)
* Store Lan Segment (192.168.1.48/28)


The following VMs will be used

| VM                   | Description                                    | Subnet                          | IP Address                 |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Server 2025 Standard | Active Directory  Server and Domain Controller | Servers LAN Segment             | 192.168.1.10               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Windows 11           | Management PAW (L-PAW)                         | Internal Management Lan Segment | 192.168.1.25               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Windows 11           | L-PC1                                          | Office Lan Segment              | 192.168.1.35               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Windows 11           | L-PC2                                          | Store Lan Segment               | 192.168.1.50               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| PfSense CE Firewall  | Firewall and Router                            | WAN                             | WAN (DYNAMIC - Internet)   |
|                      |                                                | Internal Management Lan Segment | LANMANAGEMENT(192.168.1.17)|
|                      |                                                | Servers LAN Segment             | SERVERS(192.168.1.1)       |
|                      |                                                | Office LAN Segment              | OFFICE(192.168.1.33)       |
|                      |                                                | Store LAN Segment               | STORE(192.168.1.49)        |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |




---

## PHASE 1 — Foundation (Build the Enterprise Lab)
Goal: Design Lighthouse Stores Network from scratch

What to Build:
*	Network Design and configuration (Packet Tracer)
* Network segmentation:
   * WAN / Internet
   * Internal network (AD, users)

* Routing
  * VLAN Configuration
  * Wireless Configuration

* Virtual Lab Configuration ( VMWare )
    * OS:
        *	Windows Server (Domain Controller)
        * Windows 10/11 clients
     
* Active Directory Domain Installation
    * Create Admin Account
    * Join the management PC to the Domain 

Skills Proven:
*	Network design
*	Subnetting & VLANs
*	Basic enterprise architecture
* Windows Active Directory
* Powershell


---

