# Access Control List (ACL) Configuration Lab

## Objective

To configure a Standard Access Control List (ACL) on a router and control communication between different networks.

---

## Devices Used

- 1 Router (2911)
- 2 Switches (2960)
- 2 PCs
- Copper Straight-through Cables

---

## Network Topology

PC0 ---- Switch0 ---- Router0 ---- Switch1 ---- PC1

---

## IP Addressing

### HR Network

| Device | IP Address |
|----------|----------|
| PC0 | 192.168.10.2 |
| Router G0/0 | 192.168.10.1 |

### Finance Network

| Device | IP Address |
|----------|----------|
| PC1 | 192.168.20.2 |
| Router G0/1 | 192.168.20.1 |

---

## Router Configuration

### Configure Interfaces

```bash
enable
configure terminal

interface g0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit

interface g0/1
ip address 192.168.20.1 255.255.255.0
no shutdown
exit
```

### Configure ACL

```bash
access-list 10 deny 192.168.10.0 0.0.0.255
access-list 10 permit any
```

### Apply ACL

```bash
interface g0/0
ip access-group 10 in
```

---

## Verification Commands

```bash
show access-lists
show ip interface brief
show running-config
```

---

## Connectivity Test

### Before ACL

```bash
ping 192.168.20.2
```

Result: Successful

### After ACL

```bash
ping 192.168.20.2
```

Result: Blocked by ACL

---

## Concepts Learned

- Access Control Lists (ACL)
- Traffic Filtering
- Network Security
- Packet Filtering
- Router Security
- Access Restrictions

---

## Cybersecurity Relevance

ACLs are used to control network traffic by allowing or denying packets based on defined rules. They help protect sensitive resources, enforce security policies, and reduce unauthorized access within enterprise networks.

---

## Result

Successfully configured a Standard ACL on the router to control network traffic and restrict access between networks according to security requirements.
