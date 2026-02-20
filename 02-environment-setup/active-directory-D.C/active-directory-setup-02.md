# Windows 10 Domain Join Guide (Enterprise SOC Lab)

## Overview
This document provides a step-by-step procedure for **joining a Windows 10 endpoint to an Active Directory domain**.

Domain-joining a workstation allows:
- Centralized authentication
- Group Policy enforcement
- Realistic enterprise identity telemetry
- High-value security events for SOC monitoring and SIEM ingestion

---

## Lab Context

- **Domain Controller:** Windows Server (AD DS + DNS)
- **Client OS:** Windows 10
- **Network:** LAN behind pfSense
- **IP Assignment:** DHCP (client), Static (DC)
- **DNS:** Active Directory DNS on DC

---

## Prerequisites

Before attempting to join the domain, confirm:

- Domain Controller is online and promoted
- DNS is functioning on the DC
- Client has network connectivity to the DC
- Client is using the **DC as its DNS server**
- Domain Administrator credentials are available

---

## Step 1: Verify Network Configuration on Windows 10 Client

On the Windows 10 endpoint, open **Command Prompt** and run: ipconfig/all


Confirm:
- DHCP Enabled: Yes
- IPv4 Address: Within LAN subnet
- Default Gateway: pfSense LAN IP (e.g. 192.168.1.1)
- DNS Server: Domain Controller IP (e.g. 192.168.1.10)

⚠️ If DNS does not point to the Domain Controller, the domain join will fail.

---

## Step 2: Verify DNS Resolution to the Domain

Run: nslookup corp.local

Expected result:
- DNS server = Domain Controller IP
- Domain name resolves successfully

If this fails:
- Stop
- Fix DNS before proceeding

---

## Step 3: Rename the Windows 10 Computer (Recommended)

To follow enterprise naming standards:

1. Open **Settings**
2. Navigate to **System → About**
3. Click **Rename this PC**
4. Enter a hostname such as: Windows-Workstation
5. Restart the system

---

## Step 4: Join the Domain

1. Open **Settings**
2. Navigate to: Accounts → Access work or school
3. Click **Connect**
4. Select:
   - Join this device to a local Active Directory domain
5. Enter the domain name:
   - corp.local
6. Click **Next**

---

## Step 5: Authenticate with Domain Credentials

When prompted, enter domain administrator credentials:
 - Username: CORP\Administrator
 - Password: ********


If authentication is successful:
- You will see a welcome message
- You will be prompted to restart

---

## Step 6: Restart the Endpoint

Click **Restart now** to complete the domain join process.

---

## Step 7: Log In Using Domain Credentials

After reboot:

1. At the login screen, select **Other user**
2. Log in with:
   - CORP\username





