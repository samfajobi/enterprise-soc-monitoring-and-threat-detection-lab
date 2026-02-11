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

![pfsense-setup](../../images/pfsense-download.png)

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

![pfsense-setup](../../images/install-pfsense-vbox.png)

---

## Step 3: Configure Network Adapters
pfSense requires at least **two network interfaces** to function as a firewall.

### Adapter 1 – WAN (Internet)
- Enable Adapter
- Attached to: **NAT**
- Purpose: Provides internet access (WAN)

![pfsense-setup](../../images/pfsense-NAT.png)

### Adapter 2 – LAN (Internal Network)
- Enable Adapter
- Attached to: **Internal Network**
- Name: `intnet` (or any consistent name)
- Purpose: Internal LAN for SOC lab systems

![pfsense-setup](../../images/pfsense-LAN.png)


---

## Step 4: Start pfSense Installation
1. Start the pfSense VM.
2. Select **Install pfSense** when prompted.
3. Accept default options:
   - Keyboard layout
   - Partitioning (Auto / UFS)
4. Allow the installer to complete.

![pfsense-setup](../../images/pfsense-install-1.png)

#### Click Accept
![pfsense-setup](../../images/pfsense-install-2.png)

#### Click **OK*
![pfsense-setup](../../images/pfsense-install-3.png)

#### Click **Install CE*
![pfsense-setup](../../images/pfsense-install-3a.png)

#### Click **OK*
![pfsense-setup](../../images/pfsense-install-3b.png)

#### Click **OK*
![pfsense-setup](../../images/pfsense-install-3c.png)

#### Click **Yes*
![pfsense-setup](../../images/pfsense-install-3d.png)

#### Click **OK*
![pfsense-setup](../../images/pfsense-install-3e.png)

#### Wait for a while, installation might take a while depending on your network speed.

![pfsense-setup](../../images/pfsense-install-3f.png)

### Perfect!!!! You are doing well!!!!! Let's proceed.

---

## Step 5: Reboot and Remove ISO
1. When installation completes, pfSense will prompt for a reboot.
2. **While rebooting**:
   - Power off the VM (if required)
   - Go to **Settings → Storage**
   - Remove the pfSense ISO from the virtual optical drive

⚠️ Why? This step prevents the installer from looping on reboot.

![pfsense-setup](../../images/pfsense-install-4.png)

Now Click **Remove**

![pfsense-setup](../../images/pfsense-install-4a.png)

### Note: **after deleting the ISO file, pfSense then boots from this below**

![pfsense-setup](../../images/pfsense-install-4b.png)


---

## Step 6: Initial pfSense Boot
1. Start the VM again.
2. pfSense boots into the console menu.
3. Interfaces are automatically detected:
   - **WAN** → NAT adapter
   - **LAN** → Internal Network adapter
4. Default LAN IP is typically: 192.168.1.1/24
   - **Ensure to write the IP address of the WAN and LAN somewheree, you'd need them as you proceed**

![pfsense-setup](../../images/pfsense-install-5.png)
   
### Note: **In some article, the steps might require you to setup the WAN and LAN ater starting the VM, but in this case, you've been prompted from the very start and you've selected the LAN and WAN if you could remember. **

---

## Step 7: Next, place the VMs you want to protect in the created LAN
- Click the VM and go to settings
- Go to network
- Change Adapter 1
- Attached to: **Internal Network**
- Now your VM is on same LAN interface with the pfSense firewall
- Firewall is ready to route traffic from the VM to the internet

![pfsense-setup](../../images/pfsense-install-6.png)

#### Why this step matters
- Reduces deployment risk
- Improves pipeline reliability
- Aligns with CI/CD best practices

---

## Step 8: Verify pfSense is Running
- pfSense console menu is accessible
- WAN interface has an IP address
- LAN interface is active
- Firewall is ready to route traffic

![pfsense-setup](../../images/pfsense-install-2.png)

---

## Next Steps
- Access pfSense Web GUI from a LAN-connected VM
- Configure DHCP for internal network
- Connect other lab systems (AD, Splunk, Kali, Security Onion)
- Begin SOC monitoring and attack simulations

![pfsense-setup](../../images/pfsense-install-2.png)

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