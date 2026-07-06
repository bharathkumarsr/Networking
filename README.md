# Enterprise Network Implementation using Cisco Packet Tracer

## 📌 Project Overview

This repository showcases the implementation of a multi-phase enterprise network using Cisco Packet Tracer. Starting with VLAN segmentation, the project gradually evolves into a fully functional enterprise network by introducing Inter-VLAN Routing and DHCP services.

Each phase builds upon the previous one, following a real-world enterprise deployment approach rather than creating isolated networking labs.

---

# 🎯 Project Objectives

- Design an enterprise Layer 2 network
- Implement VLAN Segmentation
- Configure Inter-VLAN Routing
- Configure DHCP Server
- Simulate enterprise network architecture
- Verify end-to-end connectivity
- Practice Cisco IOS CLI configuration and troubleshooting

---

# 🏢 Business Scenario

A growing organization has three departments:

- Human Resources (HR)
- DevOps
- Server Team

Initially, all departments were connected to a single switch. As the company expanded, the network required better security, scalability, and centralized management.

To meet these requirements:

- Departments were separated using VLANs.
- A Cisco router was introduced for Inter-VLAN Routing.
- DHCP was implemented to automate IP address allocation.

This project demonstrates how enterprise networks are commonly deployed in real-world environments.

---

# 🛠 Technologies Used

- Cisco Packet Tracer
- Cisco Catalyst 2960 Switch
- Cisco 2911 Router
- VLAN
- IEEE 802.1Q Trunking
- Router-on-a-Stick (ROAS)
- DHCP
- IPv4
- Cisco IOS CLI

---

# 🏗 Network Architecture

```

Internet (Future)
│
Cisco Router 2911
│
802.1Q Trunk
│
Cisco Catalyst 2960
├───────────────┬───────────────┬───────────────┐
│               │               │
VLAN 10      VLAN 20        VLAN 30
HR           DevOps          Server
│               │               │
PC0 PC1      PC2 PC3        PC4 PC5

```

---

# 📁 Project Phases

## ✅ Phase 1 – Enterprise VLAN Segmentation

### Description

Configured multiple VLANs to logically separate departments and reduce broadcast traffic.

### Features

- VLAN Creation
- Port Assignment
- Static IP Addressing
- Layer 2 Communication
- VLAN Isolation

### Verification

```bash
show vlan brief

show running-config

show mac address-table
```

---

## ✅ Phase 2 – Enterprise Inter-VLAN Routing

### Description

Configured Router-on-a-Stick to enable communication between different VLANs through a Cisco 2911 Router.

### Features

- Router Subinterfaces
- IEEE 802.1Q Trunk
- Default Gateways
- Layer 3 Routing

### Verification

```bash
show interfaces trunk

show ip interface brief

show running-config
```

---

## ✅ Phase 3 – Enterprise DHCP Server

### Description

Configured the Cisco Router as a DHCP Server to automatically assign IP addresses to client devices across all VLANs.

### Features

- DHCP Pools
- Excluded Addresses
- Automatic IP Allocation
- DNS Configuration

### Verification

```bash
show ip dhcp binding

show ip dhcp pool

show running-config
```

---

# 🌐 Network Information

| VLAN | Department | Network | Gateway |
|------|------------|----------------|----------------|
| 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| 20 | DevOps | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Server | 192.168.30.0/24 | 192.168.30.1 |

---

# 📂 Repository Structure

```

Enterprise-Network-Implementation/

│
├── README.md
├── Enterprise-Network.pkt
├── commands.txt
│
├── Project-01-VLAN-Segmentation/
│   ├── README.md
│   └── images/
│
├── Project-02-InterVLAN-Routing/
│   ├── README.md
│   └── images/
│
└── Project-03-DHCP-Server/
├── README.md
└── images/

```

---

# 📸 Screenshots

## Project 1

- Network Topology
- VLAN Configuration
- Running Configuration
- MAC Address Table
- VLAN Isolation

## Project 2

- Updated Topology
- Trunk Configuration
- Router Subinterfaces
- Inter-VLAN Routing
- Connectivity Test

## Project 3

- DHCP Pool Configuration
- DHCP Binding
- DHCP Pool Details
- Automatic IP Assignment
- End-to-End Connectivity

---

# ✅ Skills Demonstrated

- Enterprise Network Design
- Cisco IOS CLI
- VLAN Configuration
- Layer 2 Switching
- Router-on-a-Stick
- IEEE 802.1Q Trunking
- Inter-VLAN Routing
- DHCP Server Configuration
- IPv4 Addressing
- Network Verification
- Network Troubleshooting

---

# 🌍 Real-World Applications

The technologies implemented in this project are widely used in:

- Enterprise Corporate Networks
- Banks
- Hospitals
- Educational Institutions
- Manufacturing Companies
- Retail Organizations
- Branch Offices
- IT Companies
- Data Centers

---


# 📚 Learning Outcomes

After completing this project, I gained practical experience in:

- Designing enterprise network topology
- Configuring VLANs
- Implementing Router-on-a-Stick
- Configuring IEEE 802.1Q trunk links
- Enabling Inter-VLAN communication
- Deploying DHCP services
- Automating IP address allocation
- Verifying and troubleshooting enterprise networks using Cisco IOS CLI

---

# 👨‍💻 Author

## Bharath Kumar S R

**Aspiring DevOps Engineer | AWS | Linux | Docker | Kubernetes | Terraform | Ansible | Cisco Networking**

---
