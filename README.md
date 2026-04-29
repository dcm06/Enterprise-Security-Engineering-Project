# Enterprise-Security-Engineering-Project
By David Madubuko

As a Cybersecurity student at Fanshawe college, i have gained theoretical and hands on experience on cybersecurity concepts from Network Design and Security, Operating System Hardening and security, Penetration Testing, Cloud Design and Security Concepts. In this project, I will be demonstrating the core concepts in a complete mini-enterprise security lab setup, from network and perimete design to Penetration testing, to auditing and documentation.

## Description

The Lighthouse Superstores has 1 branch, which consists of 1 Domain Controller which is the DNS and DHCP server, will have a Web server, File Server and Database server, 1 management PC, 2 office PC, and 2 store devices.

In this project, the following Subnets have been configured as VLANS will be used:
* Servers LAN Segment(192.168.1.0/28)
* Internal Management Lan Segment (192.168.1.16/28)


The following VMs will be used

| VM                   | Description                                    | Subnet                          | IP Address                 |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Server 2025 Standard | Active Directory  Server and Domain Controller | Servers LAN Segment             | 192.168.1.10               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| Windows 11           | Management PC1                                 | Internal Management Lan Segment | 192.168.1.25               |
| -------------------  | ------------------------------------           | ------------------------------- | -------------------------- |
| PfSense CE Firewall  | Firewall and Router                            | WAN                             | WAN (DYNAMIC - Internet)   |
|                      |                                                | Internal Management Lan Segment | LANMANAGEMENT(192.168.1.17)|
|                      |                                                | Servers LAN Segment             | SERVERS(192.168.1.1)       |
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
        * Linux server (web/app)

Skills Proven:
•	Network design
•	Subnetting & VLANs
•	Basic enterprise architecture


```bash
./scriptname.sh -u username [OPTIONS]
```

> ⚠️ The `-u` option is **required**.
> All other options are optional.

---

## Required Option

| Option          | Description            |
| --------------- | ---------------------- |
| `-u <username>` | Username to be created |

---

## Optional Options

| Option           | Description                  | Default            |
| ---------------- | ---------------------------- | ------------------ |
| `-c <fullname>`  | Full name (comment field)    | Not set            |
| `-d <directory>` | Home directory path          | `/home/<username>` |
| `-s <shell>`     | Login shell                  | `/bin/bash`        |
| `-a`             | Add user to `sudo` group     | Disabled           |
| `-p <password>`  | Set a manual password        | Not set            |
| `-P`             | Generate a random password   | Disabled           |
| `-M <days>`      | Max password age             | `30`               |
| `-W <days>`      | Password expiry warning days | `10`               |
| `-I <days>`      | Inactive days after expiry   | `10`               |

---

## Rules & Validations

* `-u` **must** be provided
* Options requiring values **cannot accept another option as input**
* `-p` and `-P` **cannot be used together**
* No positional arguments are allowed
* Password expiry rules:

  * `-M` must be **≥ 20**
  * `-W` and `-I` must be **≥ 0**
* Script exits with meaningful error codes on failure

---

## Examples

### Create a basic user

```bash
./scriptname.sh -u john
```

### Create a user with full name and custom shell

```bash
./scriptname.sh -u john -c "John Doe" -s /bin/zsh
```

### Create a user with admin privileges

```bash
./scriptname.sh -u adminuser -a
```

### Create a user with a manual password

```bash
./scriptname.sh -u john -p mypassword123
```

### Create a user with a random password

```bash
./scriptname.sh -u john -P
```

*Output example:*

```
Username=john    Password=R@nd0mP@ss
```

### Set password expiry policies

```bash
./scriptname.sh -u john -M 45 -W 7 -I 14
```

---

## Exit Codes

| Code  | Meaning                              |
| ----- | ------------------------------------ |
| 11    | No arguments provided                |
| 2–9   | Invalid or missing option values     |
| 10    | Invalid option                       |
| 12    | Unexpected positional arguments      |
| 13    | Username not specified               |
| 14    | `-p` and `-P` used together          |
| 15–17 | Invalid password expiry values       |
| 18    | User creation failed                 |
| 19    | Password expiry configuration failed |
| 20    | Password setting failed              |
| 21    | Failed to add user to sudo group     |

---

## Requirements

* Linux system with:

  * `useradd`
  * `usermod`
  * `chage`
  * `chpasswd`
  * `apg` (required for `-P`)
* Script must be run by a user with **sudo privileges**

---

## Notes

* The script enforces **secure defaults**
* Designed to reject incorrect usage early
* Suitable for system administration labs and production-style scripting
