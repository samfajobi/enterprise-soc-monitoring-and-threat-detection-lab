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
- Administrator privileges

---