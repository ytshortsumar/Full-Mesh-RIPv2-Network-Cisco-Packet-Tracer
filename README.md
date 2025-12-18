# Full Mesh RIPv2 Network Implementation Using Cisco Packet Tracer

## 📘 Project Overview
This project demonstrates the design and configuration of a **Full Mesh network topology** using **four Cisco 2811 routers** in Cisco Packet Tracer.  
Each router is directly connected to every other router using serial links, ensuring **maximum redundancy and fault tolerance**.

Dynamic routing is implemented using **RIP Version 2 (RIPv2)**, allowing all routers to automatically learn routes to remote networks.

---

## 🎯 Project Objectives
- Design a full mesh WAN topology
- Configure serial and LAN interfaces on multiple routers
- Implement **RIPv2 dynamic routing**
- Ensure full end-to-end connectivity
- Understand redundancy and alternate path routing

---

## 🧱 Network Topology

### Devices Used
- **4 × Cisco 2811 Routers**
- **4 × PCs**
- **Serial DCE/DTE links (Full Mesh)**

Each router is connected to:
- **1 LAN**
- **3 Serial WAN links** (to other routers)

---

## 🌐 IP Addressing Scheme

### LAN Networks
| Router | LAN Network | Gateway |
|------|-------------|---------|
| Router 0 | 192.168.10.0/24 | 192.168.10.1 |
| Router 1 | 192.168.20.0/24 | 192.168.20.1 |
| Router 2 | 192.168.30.0/24 | 192.168.30.1 |
| Router 3 | 192.168.40.0/24 | 192.168.40.1 |

### WAN Networks
| Network | Purpose |
|-------|--------|
| 192.168.50.0 | R0 ↔ R1 |
| 192.168.60.0 | R2 ↔ R3 |
| 192.168.70.0 | R0 ↔ R2 |
| 192.168.80.0 | R1 ↔ R3 |
| 192.168.90.0 | R0 ↔ R3 |
| 192.168.100.0 | R1 ↔ R2 |

> `.1` and `.2` IPs are used on serial links.

---

## ⚙️ Router Configuration Summary

### Hardware Setup
- Each router is equipped with **two WIC-2T modules**
- Provides sufficient serial interfaces for full mesh connectivity

---

### Routing Protocol
- **Routing Protocol**: RIP Version 2
- **Auto-summary**: Disabled
- **Dynamic route learning enabled on all routers**

Example configuration:

router rip
version 2
no auto-summary
network 192.168.X.0


---

## 🖥️ PC Configuration

| PC | IP Address | Subnet Mask | Default Gateway |
|----|------------|-------------|-----------------|
| PC0 | 192.168.10.2 | 255.255.255.0 | 192.168.10.1 |
| PC2 | 192.168.20.2 | 255.255.255.0 | 192.168.20.1 |
| PC1 | 192.168.30.2 | 255.255.255.0 | 192.168.30.1 |
| PC3 | 192.168.40.2 | 255.255.255.0 | 192.168.40.1 |

---

## ✅ Verification & Testing

### Routing Verification
- RIP routes automatically populated routing tables
- All networks visible using:

show ip route


---

### Connectivity Tests
- Ping between **any PC to any other PC** ✔
- Full reachability confirmed across all LANs
- Redundant paths available if a serial link fails

---

## 📂 Files Included
- `Full Mesh RIP Network Implementation with 4 routers.pkt`
- `README.md`

---

## 🧠 Key Learning Outcomes
- Full mesh topology design
- Serial WAN configuration
- Dynamic routing with RIPv2
- Redundancy and fault tolerance
- Enterprise-level routing concepts

---

## 🛠 Tools Used
- Cisco Packet Tracer
- Cisco 2811 Routers
- RIP Version 2

---

## 👤 Author
**Umar Farooq**  
Networking Lab Assignment
