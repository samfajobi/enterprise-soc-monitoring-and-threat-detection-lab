# 🔥 Resetting and Configuring Static LAN IP in pfSense (Lab Documentation)

## Scenario
Reconfiguring the LAN interface on pfSense to use a **static IPv4 address** and enabling DHCP for client VMs.

---

# Step 1: Access pfSense Console

From the pfSense VM console menu:

```
2) Set interface IP address
```

Select the LAN interface when prompted.

---

# Step 2: Configure LAN IPv4 Address

You will see:

```
Configure IPv4 address LAN interface via DHCP?
```

### Answer:
```
n
```

Reason:  
LAN must use a **static IP address** because it acts as:
- Default gateway for clients
- DHCP server base address
- Internal network anchor

---

# Step 3: Enter Static IP Address

When prompted:

```
Enter the new LAN IPv4 address:
```

Example:
```
192.168.10.1
```

Then:

```
Enter subnet bit count:
```

For a /24 network:
```
24
```

When asked for upstream gateway:
```
Press Enter (leave blank)
```

LAN does NOT require an upstream gateway.

---

# Step 4: Enable DHCP Server on LAN

You will then see:

```
Enable DHCP server on LAN?
```

### Answer:
```
y
```

Configure DHCP range:

Start:
```
192.168.10.100
```

End:
```
192.168.10.200
```

This allows client VMs to automatically receive IP addresses.

---

# Step 5: Verify VM Network Adapter

Inside VirtualBox:

VM → Settings → Network

Ensure:







