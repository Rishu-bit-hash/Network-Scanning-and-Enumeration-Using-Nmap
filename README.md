# Network-Scanning-and-Enumeration-Using-Nmap
Performed Nmap-based network scanning and enumeration on a Metasploitable 2 target using Kali Linux. Identified active hosts, open ports, running services, service versions, and OS details to demonstrate reconnaissance techniques in a controlled penetration testing environment.
## Project Overview

This project demonstrates the use of Nmap (Network Mapper) for host discovery, port scanning, and service enumeration within a controlled penetration testing laboratory environment. The objective was to identify active services, open ports, and system information on the Metasploitable 2 target machine from the Kali Linux attacker machine.

The activity was performed in the isolated VirtualBox NAT Network created in Project 1, ensuring that all scanning activities remained within the secure lab environment.

---

## Lab Environment

### Attacker Machine
- Kali Linux

### Target Machine
- Metasploitable 2

### Network Configuration
- Oracle VirtualBox NAT Network
- Subnet: 10.0.2.0/24

### IP Addresses
- Kali Linux: 10.0.2.8
- Metasploitable 2: 10.0.2.7

---

## Objectives

The primary objectives of this project were:

- Verify target host availability.
- Discover open ports on the target machine.
- Identify running services.
- Enumerate service versions.
- Gather operating system and network information.

---

## Tools Used

- Kali Linux
- Nmap 7.99
- Metasploitable 2
- Oracle VirtualBox

---

## Scanning Methodology

### Step 1 – Host Discovery

**Command:**

```bash
nmap -sn 10.0.2.7
```

**Result:**

- Host detected as active.
- IP Address: 10.0.2.7
- MAC Address identified as Oracle VirtualBox Virtual NIC.

---

### Step 2 – Basic Port Scan

**Command:**

```bash
nmap 10.0.2.7
```

**Result:**

Several ports were discovered in the open state, including:

| Port | Service |
|------|----------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 111 | RPCBind |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900 | VNC |
| 6000 | X11 |
| 8009 | AJP13 |
| 8180 | HTTP Service |

---

### Step 3 – Service Version Enumeration

**Command:**

```bash
sudo nmap -sV 10.0.2.7
```

**Results Obtained:**

| Port | Service Version |
|------|----------------|
| 21 | vsftpd 2.3.4 |
| 22 | OpenSSH 4.7p1 |
| 23 | Linux Telnetd |
| 25 | Postfix SMTP |
| 53 | ISC BIND 9.4.2 |
| 80 | Apache HTTPD 2.2.8 |
| 139/445 | Samba SMB 3.x–4.x |
| 2049 | NFS |
| 2121 | ProFTPD 1.3.1 |
| 3306 | MySQL 5.0.51a |
| 5432 | PostgreSQL 8.3.x |
| 5900 | VNC Protocol 3.3 |
| 8009 | Apache JServ Protocol |

**Additional Information:**

- Hostname: metasploitable.localdomain
- Operating System: Linux/Unix

---

### Step 4 – Full Port Scan

**Command:**

```bash
nmap -p- 10.0.2.7
```

**Result:**

Additional open ports were discovered beyond the default top 1000 ports, including:

- 1524
- 3632
- 6667
- 6697
- 8787
- 40775
- 44210
- 47470
- 53079

These services increase the attack surface and provide valuable information during penetration testing.

---

## Enumeration Findings

The target system exposed multiple network services commonly found on Linux servers. Enumeration revealed:

- Web services running on Apache.
- Remote administration services such as SSH, Telnet, and VNC.
- Database services including MySQL and PostgreSQL.
- File-sharing services through Samba and NFS.
- FTP services available on multiple ports.

The large number of exposed services indicates a deliberately vulnerable environment designed for security testing and learning purposes.

---
## Screenshots

1. Host Discovery Scan
   
   <img width="1917" height="637" alt="Host Discovery Proj2" src="https://github.com/user-attachments/assets/167e8703-a0dc-4dfd-b878-2ebf439c171a" />

2. Basic Port Scan
   
   <img width="1917" height="717" alt="Basic Port Scan" src="https://github.com/user-attachments/assets/dbcf5e36-0ca2-4f61-84ae-1932161f5748" />

3. Service Version Enumeration
   
   <img width="1917" height="982" alt="basic_version_scan" src="https://github.com/user-attachments/assets/5b061320-12de-40b5-ac12-63480945b72a" />

4. Full Port Scan
   
   <img width="1917" height="981" alt="all_ports_scan" src="https://github.com/user-attachments/assets/3127d53f-29dc-4c72-8be8-88fd4b8fe5a2" />

## Key Learnings and Outcomes

- Learned how to use Nmap for network reconnaissance.
- Performed host discovery and connectivity verification.
- Identified open ports and associated services.
- Enumerated service versions running on the target machine.
- Gathered information useful for vulnerability assessment.
- Understood the importance of enumeration in penetration testing.

---

## Conclusion

The Nmap scanning and enumeration exercise successfully identified active services, open ports, service versions, and operating system information on the Metasploitable 2 target machine. The results demonstrate how reconnaissance and enumeration provide critical information that helps security professionals understand a system's attack surface and prepare for vulnerability assessment activities.











