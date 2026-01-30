# Essential networking tools for Security Engineers

# Networking Fundamentals – Tools & Components

This repository documents **core networking tools, devices, and technologies**, their roles, how they work together, and **why they matter in real-world IT, cloud, and SOC environments**. The goal is to demonstrate strong foundational knowledge that supports cybersecurity, cloud engineering, and threat detection projects.

---

## Table of Contents

1. Overview
2. Modem
3. Router
4. Switch
5. Hub
6. Wireless Access Point (WAP)
7. Wi‑Fi (Wireless Networking)
8. Firewall
9. DNS (Domain Name System)
10. DHCP (Dynamic Host Configuration Protocol)
11. VPN (Virtual Private Network)
12. Proxy Server
13. IDS / IPS
14. How These Components Work Together
15. Why This Matters for SOC & Cloud Security

---

## 1. Overview

Computer networks are built using multiple devices and technologies, each with a **specific responsibility**. Understanding these tools is critical for:

* Network troubleshooting
* Cloud architecture
* Security monitoring (SOC)
* Incident response

This documentation focuses on **what each tool does**, **where it operates (OSI layers)**, and **its security relevance**.

---

## 2. Modem (Modulator–Demodulator)

### What It Is

A modem connects a private network to an **Internet Service Provider (ISP)** by translating ISP signals into digital data.

### Key Functions

* Converts ISP signals (fiber, cable, DSL) into Ethernet data
* Assigns a public IP address (from ISP)
* Acts as the gateway to the internet

### OSI Layer

* Layer 1 (Physical)
* Layer 2 (Data Link)

### Security Relevance

* Limited visibility and control
* Often managed by ISP
* Rarely provides detailed logs

---

## 3. Router

### What It Is

A router connects **multiple networks** and directs traffic between them.

### Key Functions

* Routes traffic between LAN and WAN
* Performs NAT (Network Address Translation)
* Assigns private IPs using DHCP
* Provides basic firewall protection

### OSI Layer

* Layer 3 (Network)

### Security Relevance

* First line of network defense
* Controls inbound/outbound traffic
* Generates valuable logs for SOC analysis

---

## 4. Switch

### What It Is

A switch connects devices **within the same network** and forwards traffic intelligently using MAC addresses.

### Key Functions

* Reduces network collisions
* Improves performance
* Supports VLANs (advanced switches)

### OSI Layer

* Layer 2 (Data Link)
* Layer 3 (Layer‑3 switches)

### Security Relevance

* VLAN segmentation limits attack spread
* Used in enterprise network design

---

## 5. Hub

### What It Is

A hub is a basic networking device that broadcasts data to **all connected devices**.

### Key Functions

* Simple signal repeater
* No traffic intelligence

### OSI Layer

* Layer 1 (Physical)

### Security Relevance

* Highly insecure
* Susceptible to packet sniffing
* Largely obsolete

---

## 6. Wireless Access Point (WAP)

### What It Is

A WAP allows wireless devices to connect to a **wired network**.

### Key Functions

* Bridges wired and wireless networks
* Extends Wi‑Fi coverage
* Supports multiple SSIDs

### OSI Layer

* Layer 2 (Data Link)

### Security Relevance

* Common attack target
* Requires strong encryption (WPA2/WPA3)
* Rogue AP detection is important in SOCs

---

## 7. Wi‑Fi (Wireless Networking Technology)

### What It Is

Wi‑Fi is a **wireless communication standard** (IEEE 802.11).

### Key Characteristics

* Uses radio frequencies (2.4 GHz, 5 GHz, 6 GHz)
* Enables mobility and convenience

### Security Relevance

* Vulnerable to password attacks
* Evil Twin & MITM attacks
* Requires monitoring and strong authentication

---

## 8. Firewall

### What It Is

A firewall controls traffic based on **rules and policies**.

### Types

* Network firewall
* Host‑based firewall
* Next‑Generation Firewall (NGFW)

### OSI Layer

* Layers 3–7 (depending on type)

### Security Relevance

* Core SOC data source
* Enforces access control
* Detects suspicious behavior

---

## 9. DNS (Domain Name System)

### What It Is

DNS translates domain names into IP addresses.

### Security Relevance

* DNS logs reveal malware activity
* Common vector for phishing & C2 traffic

---

## 10. DHCP (Dynamic Host Configuration Protocol)

### What It Is

DHCP automatically assigns IP addresses to devices.

### Security Relevance

* Rogue DHCP servers can hijack traffic
* Logs help identify devices during incidents

---

## 11. VPN (Virtual Private Network)

### What It Is

A VPN encrypts traffic between a device and a network.




