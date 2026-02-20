# pfSense Firewall Setup Guide (From Scratch)

This document outlines a complete step-by-step pfSense firewall rules setup in a virtualized lab environment for a segmented SOC architecture.


# 1. Access Web Interface

From a client VM inside LAN:

```
https://192.168.1.1
```

Login:

- Username: admin
- Password: pfsense

![pfsense-setup](../../images/pfsense-install-7.png)

![pfsense-setup](../../images/pfsense-install-7a.png)

![pfsense-setup](../../images/pfsense-install-7b.png)

Run initial setup wizard.

---

# 6. Initial Setup Wizard

Configure:

- Hostname
- Domain
- DNS Servers (e.g. 8.8.8.8)
- Timezone
- WAN Configuration (DHCP)
- Admin Password

Finish setup.

---

# 7. Enable and Configure Additional Interfaces

Go to:

```
Interfaces → Assignments
```

Enable each OPT interface:

- Check "Enable Interface"
- Rename (e.g., SERVERS, REDTEAM)
- Set Static IPv4
- Assign correct subnet

Save and Apply.

---

# 8. Configure Firewall Rules

By default, new interfaces block all traffic.

For each VLAN:

Go to:

```
Firewall → Rules → [Interface]
```

Add rule:

| Field | Value |
|--------|--------|
| Action | Pass |
| Protocol | Any |
| Source | [Interface] net |
| Destination | Any |

Save → Apply Changes.

Important:  
Rules apply where traffic enters.

---

# 9. Configure Outbound NAT

Go to:

```
Firewall → NAT → Outbound
```

Select:

```
Automatic outbound NAT rule generation
```

Save → Apply.

This ensures:

- All internal subnets are translated to WAN IP.

---

# 10. Verify Connectivity

From client VM:

```
ping <gateway>
ping 8.8.8.8
ping google.com
```

From pfSense:

```
Diagnostics → Ping → 8.8.8.8
```

All should succeed.

---

# 11. Enable DNS Resolver

Go to:

```
Services → DNS Resolver
```

Ensure:

- Enabled
- Listen on all interfaces
- Outgoing interface: WAN

Clients can now use:

```
DNS: 192.168.x.1
```

---

# 12. Configure Inter-VLAN Routing (Optional Hardening Later)

Currently:

All VLANs can talk to each other.

Later for segmentation:

- Create specific allow rules
- Block lateral movement
- Restrict Red Team access

---

# 13. Enable Logging

Ensure logging is enabled under:

```
Status → System Logs
```

For future SIEM integration:

```
Status → System Logs → Settings
```

Enable:

- Remote logging (Syslog)
- Select Firewall Events
- Select System Events
- Enter SIEM IP address

---

# 14. Validation Checklist

- [ ] WAN receives IP
- [ ] LAN interfaces enabled
- [ ] DHCP working on each VLAN
- [ ] Firewall rules created per interface
- [ ] Outbound NAT set to Automatic
- [ ] Clients can reach internet
- [ ] DNS resolving
- [ ] Logs visible in System Logs

---

# 15. Final Architecture Flow

Traffic Path:

```
Client (VLAN)
    ↓
Interface Rule (Ingress)
    ↓
Routing Engine
    ↓
Outbound NAT
    ↓
WAN
    ↓
Internet
```

---

# Conclusion

This pfSense deployment provides:

- Segmented VLAN architecture
- Inter-VLAN routing
- Controlled egress
- NAT translation
- DNS resolution
- Foundation for SIEM log ingestion

This firewall now serves as the core infrastructure component for SOC simulation, attack testing, and log correlation exercises.

---
