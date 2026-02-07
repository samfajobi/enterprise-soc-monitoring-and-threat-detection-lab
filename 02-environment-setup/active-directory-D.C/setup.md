# Active Directory Domain Controller Setup (Enterprise SOC Lab)

## Overview
This document details the step-by-step setup of **Active Directory Domain Services (AD DS)** on **Windows Server 2019** to function as a **Domain Controller (DC)** in an enterprise-style SOC monitoring homelab.

Active Directory serves as the **central identity and authentication system**, enabling user, computer, and policy management while providing high-value security logs for SOC monitoring and SIEM ingestion.

---

## Lab Environment
- **Hypervisor:** VirtualBox
- **Firewall:** pfSense
- **Server OS:** Windows Server 2019
- **Client OS:** Windows Desktop (Domain-joined)
- **SIEM:** Splunk
- **Network Type:** Internal Network (LAN)

---

## Prerequisites
- Windows Server 2019 installed
- Static IP address configured
- Network connectivity to pfSense LAN
- Local Administrator access
- Virtual machine or physical server

---

## ⚙️ Step 1: Configure Static IP
- Open **Network Adapter Settings**
- Assign a **static IPv4 address**
- Set **Preferred DNS** to the server’s own IP

📷 *Screenshot: IPv4 configuration*

Note: Although some lab environments function without a static IP,
Microsoft best practice requires Domain Controllers to use a static IP
to ensure DNS and authentication reliability.


---

## 🏷️ Step 2: Rename the Server
- Open **Server Manager → Local Server**
- Rename the server (e.g., `DC01`)
- Restart the system

📷 *Screenshot: Server rename confirmation*

---