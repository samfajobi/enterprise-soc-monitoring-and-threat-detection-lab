# pfSense Firewall Installation (VirtualBox)

## Overview
This document outlines the step-by-step process used to install and configure **pfSense Firewall** in **VirtualBox** as part of an enterprise SOC homelab.  
pfSense serves as the core network firewall, providing routing, traffic control, and network segmentation for other lab components such as Active Directory, Splunk, Security Onion, and Kali Linux.

---

## Prerequisites
- VirtualBox installed on host system
- pfSense ISO image downloaded
- Basic understanding of virtual networking (NAT & Internal Network)

---

## Step 1: Download pfSense ISO
1. Navigate to the official pfSense download page.
2. Download the **pfSense CE ISO Installer** (AMD64).
3. Save the ISO file locally.

![pfsense-setup](../screenshots/pfsense-download.png)

---

## Step 2: Create a New Virtual Machine
1. Open **VirtualBox**.
2. Click **New**.
3. Configure the VM:
   - **Name:** pfSense-Firewall
   - **Type:** BSD
   - **Version:** FreeBSD (64-bit)
4. Assign resources:
   - **Memory:** 1–2 GB (minimum)
   - **CPU:** 1–2 cores
5. Attach pfSense ISO   
   - **Go to **Settings → Storage**.
   - Under Controller IDE, **attach the pfSense ISO file**.
   - Confirm ISO is mounted.

![pfsense-setup](../screenshots/install-pfsense-vbox.png)

---

## Step 3: Configure Network Adapters
pfSense requires at least **two network interfaces** to function as a firewall.

### Adapter 1 – WAN (Internet)
- Enable Adapter
- Attached to: **NAT**
- Purpose: Provides internet access (WAN)

![pfsense-setup](../screenshots/pfsense-NAT.png)

### Adapter 2 – LAN (Internal Network)
- Enable Adapter
- Attached to: **Internal Network**
- Name: `intnet` (or any consistent name)
- Purpose: Internal LAN for SOC lab systems

![pfsense-setup](../screenshots/pfsense-LAN.png)


---

## Step 4: Start pfSense Installation
1. Start the pfSense VM.
2. Select **Install pfSense** when prompted.
3. Accept default options:
   - Keyboard layout
   - Partitioning (Auto / UFS)
4. Allow the installer to complete.

![pfsense-setup](../screenshots/pfsense-install-1.png)

![pfsense-setup](../screenshots/pfsense-install-2.png)

---

## Step 5: Reboot and Remove ISO
1. When installation completes, pfSense will prompt for a reboot.
2. **Before rebooting**:
   - Power off the VM (if required)
   - Go to **Settings → Storage**
   - Remove the pfSense ISO from the virtual optical drive

⚠️ This step prevents the installer from looping on reboot.

![pfsense-setup](../screenshots/pfsense-install-2.png)

---

## Step 6: Initial pfSense Boot
1. Start the VM again.
2. pfSense boots into the console menu.
3. Interfaces are automatically detected:
   - **WAN** → NAT adapter
   - **LAN** → Internal Network adapter
4. Default LAN IP is typically: 192.168.1.1/24

![pfsense-setup](../screenshots/pfsense-install-2.png)

---

## Step 7: Verify pfSense is Running
- pfSense console menu is accessible
- WAN interface has an IP address
- LAN interface is active
- Firewall is ready to route traffic

![pfsense-setup](../screenshots/pfsense-install-2.png)

---

## Next Steps
- Access pfSense Web GUI from a LAN-connected VM
- Configure DHCP for internal network
- Connect other lab systems (AD, Splunk, Kali, Security Onion)
- Begin SOC monitoring and attack simulations

![pfsense-setup](../screenshots/pfsense-install-2.png)

---

## Lab Purpose
This pfSense installation forms the foundation of an enterprise-style SOC lab, enabling:
- Network traffic inspection
- Attack surface simulation
- Firewall logging
- Integration with SIEM and NIDS tools

---

## Author
**Olusegun Fajobi**  
Cybersecurity Engineer | SOC & SIEM  
GitHub: https://github.com/samfajobi