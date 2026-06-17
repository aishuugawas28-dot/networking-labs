# Inter-VLAN Routing Lab

## Objective
To configure Inter-VLAN Routing using Router-on-a-Stick and enable communication between devices in different VLANs.

---

## Devices Used
- 1 Router (2911)
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

### VLAN 10

| Device | IP Address |
|----------|----------|
| PC0 | 192.168.10.2 |
| PC1 | 192.168.10.3 |
| Gateway | 192.168.10.1 |

### VLAN 20

| Device | IP Address |
|----------|----------|
| PC2 | 192.168.20.2 |
| PC3 | 192.168.20.3 |
| Gateway | 192.168.20.1 |

---

## Switch Configuration

### Create VLANs

```bash
vlan 10
name HR

vlan 20
name FINANCE
```

### Configure Trunk Port

```bash
interface fa0/24
switchport mode trunk
```

---

## Router Configuration

### VLAN 10

```bash
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
```

### VLAN 20

```bash
interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
```

---

## Verification Commands

```bash
show vlan brief
show interfaces trunk
show ip interface brief
```

---

## Connectivity Test

```bash
ping 192.168.20.2
```

Result: Successful

---

## Concepts Learned

- VLAN Configuration
- Trunk Port Configuration
- Router-on-a-Stick
- Subinterfaces
- 802.1Q Encapsulation
- Inter-VLAN Communication

---

## Cybersecurity Relevance

Inter-VLAN Routing allows controlled communication between different network segments. It is commonly used in enterprise networks for security, network segmentation, and access control.

---

## Result

Successfully configured Inter-VLAN Routing using Router-on-a-Stick. Devices in different VLANs were able to communicate through the router.
