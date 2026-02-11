# 🔥 Firewall Overview

## 📌 Introduction

A firewall is a network security device or software that monitors, filters, and controls incoming and outgoing traffic based on defined security rules.

It acts as a security boundary between trusted and untrusted networks and is one of the most critical security controls in modern enterprise environments.

---

## 🎯 Purpose of a Firewall

A firewall exists to:

* Enforce trust boundaries
* Control network access
* Reduce attack surface
* Prevent unauthorized access
* Provide visibility into traffic flows
* Log and monitor suspicious activity

At its core, a firewall answers:

Who can talk to who?  
On which port?  
Using which protocol?  
Under what conditions?

---

## 🌍 Understanding Network Zones

Firewalls operate between security zones. A zone represents a group of systems with similar trust levels.

### Common Enterprise Zones

## WAN (Untrusted Network)
* The Internet
* External partner networks
* Third-party connections

This zone is considered hostile and untrusted.

## LAN (Trusted User Network)
* Employee workstations
* Corporate laptops
* Internal endpoints

This zone contains regular users and internal devices.

## Server Network
* Domain Controllers
* File servers
* Database servers
* Application servers

This zone contains critical infrastructure.

## DMZ (Demilitarized Zone)
* Public web servers
* Email gateways
* Reverse proxies

Systems exposed to the internet are placed here to isolate them from internal networks.

## Guest Network
* Visitor WiFi
* Unmanaged devices

This network is isolated from internal systems.

---

## 🛡 Types of Firewalls

## Packet Filtering Firewall
* Filters traffic based on IP address, port, and protocol
* Stateless
* Basic level of control

## Stateful Firewall
* Tracks active connections
* Makes decisions based on connection state
* Most common traditional firewall type

## Next-Generation Firewall (NGFW)
* Deep packet inspection
* Application awareness
* Intrusion prevention (IDS/IPS)
* Threat intelligence integration

## Host-Based Firewall
* Installed directly on endpoints
* Controls inbound/outbound traffic per device

---

## 🔎 How Firewalls Work

1. Traffic enters an interface
2. Firewall checks rules top-down
3. If rule matches:
   * Allow or deny
4. If no rule matches:
   * Default deny (best practice)
5. Allowed traffic is logged and optionally inspected

Firewalls evaluate traffic on ingress (when it enters an interface).

---




