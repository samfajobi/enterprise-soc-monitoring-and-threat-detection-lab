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

# 2. Initial Setup Wizard

Configure:

- Hostname
- Domain
- DNS Servers (e.g. 8.8.8.8)
- Timezone
- WAN Configuration (DHCP)
- Admin Password

Finish setup.

---

# 3. Enable and Configure Additional Interfaces

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

# 4. Configure Firewall Rules

By default, new interfaces block all traffic.

For each VLAN:

Go to:

```
Firewall → Rules → [Interface]
```



---



---




---
