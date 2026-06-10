# VLAN Configuration Lab

## Objective
To configure VLANs on a switch and establish communication between devices belonging to the same VLAN while isolating devices in different VLANs.

---

## Devices Used
- 1 Switch (2960)
- 4 PCs
- Copper Straight-through Cables

---

## VLAN Configuration

| VLAN ID | VLAN Name |
|----------|----------|
| 10 | HR |
| 20 | FINANCE |

---

## IP Addressing

| Device | IP Address | Subnet Mask |
|----------|----------|----------|
| PC0 | 192.168.10.2 | 255.255.255.0 |
| PC1 | 192.168.10.3 | 255.255.255.0 |
| PC2 | 192.168.20.2 | 255.255.255.0 |
| PC3 | 192.168.20.3 | 255.255.255.0 |

---

## Switch Configuration

### Create VLANs

```bash
enable
configure terminal

vlan 10
name HR
exit

vlan 20
name FINANCE
exit
```

### Assign Ports to VLAN 10

```bash
interface range fa0/1 - 2
switchport mode access
switchport access vlan 10
exit
```

### Assign Ports to VLAN 20

```bash
interface range fa0/3 - 4
switchport mode access
switchport access vlan 20
exit
```

### Verify VLAN Configuration

```bash
show vlan brief
```

---

## Connectivity Testing

### Same VLAN Communication

```bash
ping 192.168.10.3
```

Result: Successful

```bash
ping 192.168.20.3
```

Result: Successful

---

### Different VLAN Communication

```bash
ping 192.168.20.2
```

Result: Request Timed Out

---

## Result

VLANs were successfully configured. Devices within the same VLAN communicated successfully, while communication between different VLANs was restricted.

---

## Concepts Learned

- VLAN Creation
- VLAN Port Assignment
- Network Segmentation
- Broadcast Domain Separation
- VLAN Isolation
- Basic Network Security

---

## Cybersecurity Relevance

VLANs help improve network security by separating departments and users into different logical networks. This reduces unauthorized access, limits attack spread, and improves network management.
