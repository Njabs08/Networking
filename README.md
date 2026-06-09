#  Peer-to-Peer Office Network — Cisco Packet Tracer

A simulated inter-office network connecting two branch offices using a single router, built and tested in Cisco Packet Tracer.

---

##  Project Overview

This project demonstrates a basic peer-to-peer office network where two offices with different IP addressing schemes communicate through a centrally connected router. It covers core networking concepts including IP addressing, subnetting, inter-LAN routing, and end-to-end connectivity verification.

---

##  Network Topology

<img width="1136" height="393" alt="image" src="https://github.com/user-attachments/assets/3300cc9f-671e-4f82-a0d3-40b7a5883bf2" />


##  IP Addressing Table

| Device  | Interface | IP Address      | Subnet Mask     | Default Gateway |
|---------|-----------|-----------------|-----------------|-----------------|
| Router2 | Gi0/0     | 192.168.10.1    | 255.255.255.0   | —               |
| Router2 | Gi0/1     | 172.16.0.1      | 255.255.255.0   | —               |
| PC0     | Fa0       | 192.168.10.10   | 255.255.255.0   | 192.168.10.1    |
| PC1     | Fa0       | 192.168.10.20   | 255.255.255.0   | 192.168.10.1    |
| PC2     | Fa0       | 192.168.10.30   | 255.255.255.0   | 192.168.10.1    |
| PC3     | Fa0       | 172.16.0.10     | 255.255.255.0   | 172.16.0.1      |
| PC4     | Fa0       | 172.16.0.20     | 255.255.255.0   | 172.16.0.1      |

---

##  Router Configuration (Router2)

```bash
enable
configure terminal
hostname Router2

! Administrative Office - LAN Interface
interface GigabitEthernet0/0
 description Administrative-Office-LAN
 ip address 192.168.10.1 255.255.255.0
 no shutdown

! IT Office - LAN Interface
interface GigabitEthernet0/1
 description IT-Office-LAN
 ip address 172.16.0.1 255.255.255.0
 no shutdown

end
write memory
```

> **Note:** No static routes are needed. The router is directly connected to both networks and automatically knows how to route between them.

---

##  PC Configuration

### Administrative Office

| Device | IP Address    | Subnet Mask   | Default Gateway |
|--------|---------------|---------------|-----------------|
| PC0    | 192.168.10.10 | 255.255.255.0 | 192.168.10.1    |
| PC1    | 192.168.10.20 | 255.255.255.0 | 192.168.10.1    |
| PC2    | 192.168.10.30 | 255.255.255.0 | 192.168.10.1    |

### IT Office

| Device | IP Address  | Subnet Mask   | Default Gateway |
|--------|-------------|---------------|-----------------|
| PC3    | 172.16.0.10 | 255.255.255.0 | 172.16.0.1      |
| PC4    | 172.16.0.20 | 255.255.255.0 | 172.16.0.1      |

---

##  Connectivity Tests

Verified end-to-end connectivity using `ping` from the PC Command Prompt:

| Source | Destination   | Result     |
|--------|---------------|------------|
| PC0    | 192.168.10.20 |  Success |
| PC0    | 192.168.10.30 |  Success |
| PC0    | 172.16.0.10   |  Success |
| PC0    | 172.16.0.20   |  Success |
| PC3    | 192.168.10.10 |  Success |

---

##  Tools Used

- Cisco Packet Tracer
- Cisco 2911 Router
- Cisco 2960-24TT Switches

---

##  Concepts Demonstrated

- IPv4 addressing and subnetting (/24)
- Default gateway configuration
- Inter-LAN routing via a single router
- Layer 2 switching (no VLAN configuration required)
- End-to-end connectivity verification using ping

---

## 👤 Author

**Njabulo Prince Tshuma**  
