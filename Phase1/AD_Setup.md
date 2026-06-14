Active Directory and Routing Setup 
---
## Goal: Set-up Routing and Active Directory

![Project Screenshot](../images/Phase1networkimage.png)

In this one, the following VMs will be used
-	Server 2025 Standard – Active Directory  Server and Domain Controller(192.168.1.10)
    - Servers LAN Segment(192.168.1.0/28)

-	PfSense CE Firewall – Firewall and Router 
  EM0 -WAN (DYNAMIC - Internet)
  Em1 - LANMANAGEMENT(192.168.1.17)
  Em2(192.168.1.1)
  Opt1(192.168.1.33)
    - Internal Management Lan Segment (192.168.1.16/28)
    - Servers LAN Segment(192.168.1.0/28)
    - Office LAN Segment (192.168.1.32/28)



The goal of this lab is to setup and install Active directory Domain Services, set up the forrest, join the management pc to the domain and setup firewall and routing between the two networks.

## STEP1: STATIC IP CONFIGURATIONS

After installation, i assigned the interfaces to the correct networks and set up Static IP addresses for now..
-	Server Static IP
![](../images/phase1/serverstaticip.png)

-	Management PC Static IP

-	PfSense Firewall IPs

![](../images/phase1/pfsenseips.png)

-	Firewall Rules to permit traffic for now

![](../images/phase1/pfsenserules1.png)
![](../images/phase1/connectiontest.png)
 
 


Once that is completed, test connection from Server to Management PC


![PFSENSE IPs](../images/phase1/pfsenseips.png)


