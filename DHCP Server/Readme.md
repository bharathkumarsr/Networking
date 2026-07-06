# Enterprise DHCP Server Configuration using Cisco Router (Cisco Packet Tracer)

## 📌 Project Overview

This project demonstrates the implementation of an **Enterprise Dynamic Host Configuration Protocol (DHCP) Server** using a Cisco 2911 Router in Cisco Packet Tracer.

In the previous project, IP addresses were manually assigned to every client device. While manual addressing works in small environments, it becomes difficult to manage in enterprise networks with hundreds or thousands of devices.

To solve this challenge, the Cisco Router is configured as a **DHCP Server**, automatically assigning IP addresses, subnet masks, default gateways, and DNS server information to devices in multiple VLANs.

This project simulates how enterprise organizations automate IP address management, reducing manual configuration and minimizing network administration effort.

---

# 🎯 Project Objectives

- Configure Cisco Router as a DHCP Server
- Create DHCP Pools for multiple VLANs
- Configure Excluded Addresses
- Automatically assign IP addresses
- Configure Default Gateway
- Configure DNS Server
- Verify DHCP Lease Allocation
- Test End-to-End Network Connectivity

---

# 🏢 Business Scenario

A company has multiple departments connected across different VLANs:

- Human Resources (HR)
- DevOps
- Server Network

As the company grows, manually assigning IP addresses to every employee's computer becomes inefficient and error-prone.

To simplify network management, the organization deploys a centralized DHCP service on the router that automatically provides:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

This approach reduces administrative overhead and ensures consistent network configuration across all client devices.

---

# 🛠 Technologies Used

| Technology | Purpose |
|------------|---------|
| Cisco Packet Tracer | Network Simulation |
| Cisco 2911 Router | DHCP Server & Inter-VLAN Routing |
| Cisco Catalyst 2960 | Layer 2 Switching |
| DHCP | Automatic IP Address Assignment |
| IEEE 802.1Q | VLAN Trunking |
| IPv4 | Network Addressing |
| Cisco IOS CLI | Device Configuration |

---

# 🏗 Network Topology

```
                    Cisco 2911 Router
             (DHCP Server + Inter-VLAN Router)
                         │
                  802.1Q Trunk Link
                         │
                 Cisco Catalyst 2960
                         │
      ┌──────────────────┼──────────────────┐
      │                  │                  │
   VLAN 10           VLAN 20           VLAN 30
      HR             DevOps             Server

  PC0    PC1      PC2     PC3      PC4     PC5
```

---

# 🌐 VLAN Information

| VLAN | Department | Network | Gateway |
|------|------------|----------------|----------------|
| VLAN 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | DevOps | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Server | 192.168.30.0/24 | 192.168.30.1 |

---

# ⚙ Project Implementation

## Step 1

Configured DHCP Excluded Addresses.

Reserved IP addresses for:

- Default Gateway
- Future Static Devices
- Network Infrastructure

Example:

```
ip dhcp excluded-address 192.168.10.1 192.168.10.20
```

---

## Step 2

Created DHCP Pool for HR VLAN.

Configured:

- Network Address
- Default Gateway
- DNS Server

---

## Step 3

Created DHCP Pool for DevOps VLAN.

---

## Step 4

Created DHCP Pool for Server VLAN.

---

## Step 5

Configured all client devices to obtain IP addresses automatically using DHCP.

---

## Step 6

Verified DHCP lease allocation.

---

## Step 7

Tested end-to-end communication between all VLANs.

---

# 🔧 DHCP Configuration

Each DHCP Pool includes:

- Network Address
- Subnet Mask
- Default Router
- DNS Server

Example:

```
ip dhcp pool HR

network 192.168.10.0 255.255.255.0

default-router 192.168.10.1

dns-server 8.8.8.8
```

---

# 🔧 DHCP Excluded Addresses

Reserved addresses prevent DHCP from assigning IPs already used by infrastructure devices.

Example:

```
ip dhcp excluded-address 192.168.10.1 192.168.10.20
```

This ensures:

- Router IP remains fixed
- Future Servers use static IPs
- Network devices remain reachable

---

# 🔍 Verification Commands

## Router

```bash
show ip dhcp binding

show ip dhcp pool

show running-config
```

---

## PC

```cmd
ipconfig

ipconfig /renew

ping
```

---

# 🧪 Connectivity Testing

| Test | Expected Result | Status |
|------|-----------------|--------|
| PC receives IP automatically | Success | ✅ Pass |
| Default Gateway assigned | Success | ✅ Pass |
| DNS Server assigned | Success | ✅ Pass |
| HR → DevOps | Success | ✅ Pass |
| HR → Server | Success | ✅ Pass |
| DevOps → Server | Success | ✅ Pass |

---

# 📖 How DHCP Works

When a client device is configured for automatic addressing, it sends a DHCP Discover message to the network.

The DHCP Server responds by offering an available IP address.

The client requests the offered address, and the server acknowledges the request.

This process is commonly known as the **DORA Process**:

- Discover
- Offer
- Request
- Acknowledge

Once completed, the client receives:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

without requiring any manual configuration.

---

# 🌍 Real-World Use Cases

DHCP is widely used in:

- Enterprise Offices
- Banks
- Universities
- Hospitals
- Government Organizations
- IT Companies
- Data Centers
- Manufacturing Industries
- Retail Chains
- Branch Offices

Almost every modern enterprise network relies on DHCP for client IP address management.

---

# 🚀 Benefits

- Eliminates Manual IP Configuration
- Reduces Configuration Errors
- Simplifies Network Administration
- Improves Scalability
- Centralized IP Management
- Faster Device Deployment
- Supports Large Enterprise Networks
- Industry Standard Network Service

---

# 📁 Project Structure

```
Project-03-Enterprise-DHCP
│
├── Project-03-Enterprise-DHCP.pkt
├── README.md
├── commands.txt
│
└── images
    ├── 01-network-topology.png
    ├── 02-dhcp-pool-config.png
    ├── 03-show-ip-dhcp-binding.png
    ├── 04-show-ip-dhcp-pool.png
    ├── 05-pc-dhcp-ipconfig.png
    ├── 06-inter-vlan-ping.png
    ├── 07-router-running-config-1.png
    ├── 07-router-running-config-2.png
    ├── 07-router-running-config-3.png
    └── 08-final-topology.png
```

---

# 🎓 Skills Demonstrated

- Cisco IOS CLI
- DHCP Server Configuration
- DHCP Pool Management
- Excluded Address Configuration
- IPv4 Address Management
- Router Administration
- Layer 3 Networking
- Inter-VLAN Routing
- Network Verification
- Enterprise Network Troubleshooting

---

# 📚 Key Learning Outcomes

After completing this project, I gained hands-on experience in:

- Configuring a Cisco Router as a DHCP Server
- Creating DHCP pools for multiple VLANs
- Reserving IP addresses using excluded ranges
- Automatically assigning network settings to clients
- Verifying DHCP leases and pool utilization
- Troubleshooting DHCP-related issues
- Managing IP addressing in an enterprise network
- Understanding automated network provisioning

---

# 🔜 Next Project

## Enterprise Access Control Lists (ACL)

In the next phase, Access Control Lists (ACLs) will be implemented to control communication between departments.

Examples include:

- HR can access the Server VLAN
- DevOps can access all VLANs
- Server VLAN blocks direct access to HR
- Restrict unauthorized traffic between departments

This introduces enterprise-level security policies and traffic filtering.

---

## 👨‍💻 Author

**Bharath Kumar S R**

**Aspiring DevOps | AWS Cloud | Linux | Docker | Kubernetes | Terraform | Ansible | Cisco Networking**

> *Building enterprise-grade networking and cloud infrastructure projects to strengthen practical networking and DevOps skills.*
