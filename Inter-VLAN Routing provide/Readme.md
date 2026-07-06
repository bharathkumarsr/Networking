# Enterprise Inter-VLAN Routing using Router-on-a-Stick (Cisco Packet Tracer)

## 📌 Project Overview

This project demonstrates the implementation of **Inter-VLAN Routing** using the **Router-on-a-Stick (ROAS)** architecture in Cisco Packet Tracer.

In Project 1, multiple VLANs were created to logically separate departments within the organization. While devices inside the same VLAN could communicate successfully, communication between different VLANs was intentionally blocked.

This project extends the previous design by introducing a **Cisco 2911 Router** configured with **IEEE 802.1Q subinterfaces**, enabling secure communication between multiple VLANs over a single trunk link.

The implementation closely resembles how small and medium-sized enterprises perform inter-VLAN routing using Layer 2 switches and a centralized router.

---

# 🎯 Project Objectives

- Implement Router-on-a-Stick (ROAS)
- Configure IEEE 802.1Q trunking
- Configure router subinterfaces
- Enable communication between VLANs
- Configure default gateways
- Verify end-to-end connectivity
- Understand enterprise Layer 3 routing concepts

---

# 🏢 Business Scenario

An organization has multiple departments connected to the same access switch:

- Human Resources (HR)
- DevOps
- Server Team

Each department is placed into a separate VLAN for security and broadcast control.

Although VLANs improve security, departments occasionally need to communicate with shared resources such as:

- File Servers
- Internal Applications
- Authentication Servers
- Shared Databases

To enable secure communication between VLANs, an enterprise router is introduced using **Router-on-a-Stick**, allowing all VLANs to communicate through a single physical interface.

---

# 🛠 Technologies Used

| Technology | Purpose |
|------------|---------|
| Cisco Packet Tracer | Network Simulation |
| Cisco Catalyst 2960 Switch | Layer 2 Switching |
| Cisco 2911 Router | Inter-VLAN Routing |
| IEEE 802.1Q | VLAN Tagging |
| Router-on-a-Stick | Routing Multiple VLANs |
| IPv4 | Layer 3 Addressing |
| Cisco IOS CLI | Device Configuration |

---

# 🏗 Network Topology

```
                    Cisco 2911 Router
                    GigabitEthernet0/0
                            │
                     802.1Q Trunk Link
                            │
                    Cisco Catalyst 2960
                            │
       ┌────────────────────┼────────────────────┐
       │                    │                    │
    VLAN 10             VLAN 20             VLAN 30
      HR                 DevOps             Server

   PC0     PC1        PC2      PC3      PC4      PC5
```

---

# 🌐 VLAN Information

| VLAN | Department | Network | Gateway |
|------|------------|----------------|----------------|
| VLAN 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | DevOps | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Server | 192.168.30.0/24 | 192.168.30.1 |

---

# 💻 IP Addressing

| Device | IP Address | Default Gateway |
|---------|------------|----------------|
| PC0 | 192.168.10.10 | 192.168.10.1 |
| PC1 | 192.168.10.20 | 192.168.10.1 |
| PC2 | 192.168.20.10 | 192.168.20.1 |
| PC3 | 192.168.20.20 | 192.168.20.1 |
| PC4 | 192.168.30.10 | 192.168.30.1 |
| PC5 | 192.168.30.20 | 192.168.30.1 |

---

# ⚙ Project Implementation

## Step 1

Configured VLANs on the Cisco 2960 Switch.

- VLAN 10
- VLAN 20
- VLAN 30

---

## Step 2

Assigned switch access ports to each VLAN.

---

## Step 3

Configured GigabitEthernet0/1 on the switch as an IEEE 802.1Q trunk.

---

## Step 4

Connected Cisco 2911 Router to the switch using a single trunk link.

---

## Step 5

Configured Router-on-a-Stick.

Created subinterfaces:

- GigabitEthernet0/0.10
- GigabitEthernet0/0.20
- GigabitEthernet0/0.30

Each subinterface was configured with:

- 802.1Q encapsulation
- Default gateway IP address

---

## Step 6

Configured default gateways on all client devices.

---

## Step 7

Verified communication between all VLANs.

---

# 🔧 Router Configuration

Configured:

- Physical Interface
- Router Subinterfaces
- IEEE 802.1Q Encapsulation
- IP Addressing

Example:

```
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
```

---

# 🔧 Switch Configuration

Configured:

- Access Ports
- VLAN Membership
- Trunk Port
- Allowed VLANs

---

# ✅ Verification Commands

### Switch

```bash
show vlan brief

show interfaces trunk

show running-config
```

---

### Router

```bash
show ip interface brief

show running-config
```

---

### PC

```cmd
ipconfig

ping
```

---

# 🧪 Connectivity Testing

| Test | Expected Result | Status |
|------|-----------------|--------|
| HR → HR | Success | ✅ Pass |
| DevOps → DevOps | Success | ✅ Pass |
| Server → Server | Success | ✅ Pass |
| HR → DevOps | Success | ✅ Pass |
| HR → Server | Success | ✅ Pass |
| DevOps → Server | Success | ✅ Pass |

---

# 📖 How Router-on-a-Stick Works

The switch forwards VLAN-tagged traffic through a single trunk port.

The router receives the tagged frames, identifies the VLAN using IEEE 802.1Q encapsulation, routes the traffic to the destination network, and sends it back to the switch through the same physical interface.

This design allows one router interface to provide Layer 3 routing for multiple VLANs.

---

# 🌍 Real-World Use Cases

Router-on-a-Stick is commonly used in:

- Small Businesses
- Medium Enterprises
- Branch Offices
- Educational Institutions
- Retail Stores
- Healthcare Networks
- Testing & Lab Environments

Although large enterprises often use Layer 3 switches for higher performance, Router-on-a-Stick remains a valuable design for learning, branch deployments, and environments with limited hardware.

---

# 🚀 Benefits

- Enables communication between VLANs
- Cost-effective Layer 3 solution
- Uses a single physical router interface
- Supports multiple VLANs using subinterfaces
- Reduces hardware requirements
- Easy to implement and troubleshoot
- Industry-standard networking concept

---

# 📁 Project Structure

```
Project-02-InterVLAN-Routing
│
├── Project-02-InterVLAN-Routing.pkt
├── README.md
├── commands.txt
│
└── images
    ├── 01-network-topology.png
    ├── 02-switch-trunk-config.png
    ├── 03-router-subinterfaces.png
    ├── 04-switch-vlan-brief.png
    ├── 05-switch-running-config.png
    ├── 06-router-running-config.png
    ├── 07-same-vlan-ping.png
    ├── 08-inter-vlan-ping.png
    ├── 09-server-vlan-ping.png
    ├── 10-end-to-end-connectivity.png
    ├── 11-pc-ip-configuration.png
    └── 12-router-cli-verification.png
```

---

# 🎓 Skills Demonstrated

- Cisco IOS CLI
- VLAN Configuration
- Router-on-a-Stick
- IEEE 802.1Q Trunking
- Router Subinterfaces
- Layer 2 Switching
- Layer 3 Routing
- IPv4 Addressing
- Default Gateway Configuration
- Enterprise Network Design
- Network Verification
- Network Troubleshooting

---

# 📚 Key Learning Outcomes

After completing this project, I gained practical experience in:

- Configuring Router-on-a-Stick architecture
- Creating IEEE 802.1Q trunk links
- Configuring router subinterfaces
- Enabling communication between isolated VLANs
- Implementing default gateway configuration
- Verifying Layer 2 and Layer 3 connectivity
- Troubleshooting inter-VLAN routing issues
- Understanding enterprise routing architecture

---

# 🔜 Next Project

## Enterprise DHCP Server Configuration

In the next phase, the router will be configured as a DHCP Server to automatically assign:

- IP Addresses
- Subnet Masks
- Default Gateways
- DNS Server Information

This eliminates manual IP configuration and simulates how enterprise client devices are provisioned automatically.

---

## 👨‍💻 Author

**Bharath Kumar S R**

**Aspiring DevOps | AWS Cloud | Linux | Docker | Kubernetes | Terraform | Ansible | Cisco Networking**

> *Building enterprise-grade networking and cloud projects to strengthen practical infrastructure and DevOps skills.*
