# Day-7-100-Days-challenge-in-cybersecurity-
# 🛡️ Virtual Hacking Lab Setup (Day 7)

## 📖 Overview
This documentation covers the setup of a safe, isolated **Virtual Hacking Lab**. This environment serves as a "Sandbox" for practicing penetration testing, malware analysis, and network scanning without putting the host machine or external networks at risk.

> **Disclaimer:** This lab is built for educational purposes and ethical hacking practice only.

## 🏗️ Architecture

The lab consists of three main components hosted on a physical machine:
1.  **Hypervisor:** The foundation.
2.  **Attacker Machine:** The weaponized OS.
3.  **Victim Machine:** The vulnerable target.

## 🛠️ Tech Stack & Tools

| Component | Tool Used | Description |
| :--- | :--- | :--- |
| **Hypervisor** | VirtualBox | Open-source virtualization software to manage VMs. |
| **Attacker** | Kali Linux | Debian-based Linux distribution with pre-installed pen-testing tools. |
| **Target 1** | Metasploitable 2 | A test environment Linux server with intentional security vulnerabilities. |
| **Target 2** | DVWA | Damn Vulnerable Web App for practicing web exploitation (SQLi, XSS). |

## ⚙️ Installation & Configuration Steps

### Step 1: The Foundation (Virtualization)
- **Action:** Downloaded and installed VirtualBox.
- **Purpose:** Allows running "guest" operating systems inside the main computer without hardware conflicts.

### Step 2: The Attacker (Red Team)
- **OS:** Kali Linux.
- **Setup:** Imported the ISO into VirtualBox.
- **Tools Available:** Nmap, Wireshark, Metasploit, Burp Suite.

### Step 3: The Victim (Target)
- **OS:** Metasploitable / OWASP Juice Shop.
- **Purpose:** To serve as a legal target for exploits.

### Step 4: The Fence (Network Configuration) 🚧
*Critical Safety Step*
- **Configuration:** Set Network Adapter to **"NAT Network"** or **"Host-Only Adapter"**.
- **Result:** Creates a private internal network.
    - Kali can communicate with Metasploitable.
    - The Internet cannot access the Vulnerable Machine.
    - The Lab cannot accidentally attack the Home WiFi/Host LAN.

### Step 5: Snapshots (Recovery) ↩️
- **Best Practice:** Taken a snapshot of all VMs in a "Clean State" before launching any attacks.
- **Utility:** Allows instant reversion if the OS breaks or a critical file is deleted during exploitation.

## 📝 Future Labs
- [ ] Active Directory Lab
- [ ] Windows 10 Target Machine
- [ ] SIEM Integration (Splunk/Wazuh)

---
*Part of the 100 Days of Cybersecurity Challenge.*
