# Enterprise VLAN Segmentation using Cisco Packet Tracer

## 📌 Project Overview

This project demonstrates the implementation of **Enterprise VLAN Segmentation** using a Cisco Catalyst 2960 Switch in Cisco Packet Tracer.

The objective is to divide a single physical network into multiple logical networks (VLANs) to improve security, reduce broadcast traffic, and simplify network management. Devices within the same VLAN can communicate with each other, while communication between different VLANs is restricted until a Layer 3 device (Router or Layer 3 Switch) is introduced.

This project simulates a small enterprise environment with three departments:
- Human Resources (HR)
- DevOps
- Server Network

---

# 🎯 Project Objectives

- Build a basic enterprise LAN
- Create multiple VLANs
- Assign switch ports to VLANs
- Configure IP addressing
- Verify intra-VLAN communication
- Demonstrate VLAN isolation
- Understand enterprise network segmentation

---

# 🏢 Business Scenario

A company has multiple departments working on the same office floor.

Instead of allowing every department to communicate on one large network, the organization separates departments into different VLANs.

This approach provides:

- Better security
- Improved performance
- Easier management
- Reduced broadcast traffic

---

# 🛠 Technologies Used

| Technology | Purpose |
|------------|---------|
| Cisco Packet Tracer | Network Simulation |
| Cisco Catalyst 2960 Switch | Layer 2 Switching |
| VLAN | Logical Network Segmentation |
| IPv4 Addressing | Host Communication |
| Cisco IOS CLI | Device Configuration |

---

# 📦 Network Topology

```
                     Cisco 2960 Switch
                           │
      ┌────────────────────┼────────────────────┐
      │                    │                    │
   VLAN 10              VLAN 20             VLAN 30
     (HR)              (DevOps)            (Server)

  PC0     PC1        PC2     PC3        PC4     PC5
```

---

# 🗂 VLAN Configuration

| VLAN ID | Department | Network |
|----------|------------|----------------|
| 10 | HR | 192.168.10.0/24 |
| 20 | DevOps | 192.168.20.0/24 |
| 30 | Server | 192.168.30.0/24 |

---

# 💻 IP Addressing

| Device | IP Address | VLAN |
|---------|------------|------|
| PC0 | 192.168.10.10 | VLAN 10 |
| PC1 | 192.168.10.20 | VLAN 10 |
| PC2 | 192.168.20.10 | VLAN 20 |
| PC3 | 192.168.20.20 | VLAN 20 |
| PC4 | 192.168.30.10 | VLAN 30 |
| PC5 | 192.168.30.20 | VLAN 30 |

---

# ⚙️ Configuration Steps

### Step 1
Build the network topology using one Cisco 2960 Switch and six PCs.

### Step 2
Create VLANs:

- VLAN 10 (HR)
- VLAN 20 (DevOps)
- VLAN 30 (Server)

### Step 3
Assign switch ports to the appropriate VLANs.

### Step 4
Configure static IP addresses on all PCs.

### Step 5
Verify VLAN membership.

### Step 6
Test connectivity within the same VLAN.

### Step 7
Verify that communication between different VLANs is blocked.

---

# ✅ Verification

### Verify VLANs

```bash
show vlan brief
```

### Verify Running Configuration

```bash
show running-config
```

### Verify MAC Address Learning

```bash
show mac address-table
```

### Verify PC IP Configuration

```cmd
ipconfig
```

---

# 🧪 Test Results

| Test | Expected Result | Status |
|------|-----------------|--------|
| HR → HR | Success | ✅ Pass |
| DevOps → DevOps | Success | ✅ Pass |
| Server → Server | Success | ✅ Pass |
| HR → DevOps | Blocked | ✅ Pass |
| HR → Server | Blocked | ✅ Pass |
| DevOps → Server | Blocked | ✅ Pass |

---

# 📈 Why VLAN Segmentation?

Without VLANs, every device belongs to the same broadcast domain.

Problems include:

- Large broadcast traffic
- Lower network performance
- Poor security
- Difficult management

VLANs divide the network into smaller logical segments, allowing administrators to isolate departments and control communication.

---

# 🌍 Real-World Use Cases

VLANs are widely used in enterprise environments such as:

- IT Companies
- Banks
- Hospitals
- Universities
- Government Organizations
- Manufacturing Industries
- Data Centers
- Corporate Offices

Common examples include separating:

- HR
- Finance
- Development
- Servers
- Voice (IP Phones)
- Guest Wi-Fi
- CCTV Networks

---

# 🚀 Benefits

- Improved Security
- Better Network Performance
- Reduced Broadcast Domains
- Simplified Network Management
- Logical Department Separation
- Easy Scalability
- Industry Standard Enterprise Design

---

# 📁 Project Structure

```
Enterprise-VLAN-Segmentation/
│
├── Enterprise-VLAN-Segmentation.pkt
├── README.md
├── commands.txt
│
└── images
    ├── 01-network-topology.png
    ├── 02-show-vlan-brief.png
    ├── 03-running-config.png
    ├── 04-show-mac-address-table.png
    ├── 05-ping-success.png
    ├── 06-vlan-isolation.png
    ├── 07-ipconfig.png
    └── 08-device-layout.png
```

---

# 🎓 Skills Demonstrated

- Cisco IOS CLI
- VLAN Configuration
- Layer 2 Switching
- Port Assignment
- IPv4 Addressing
- Network Verification
- Basic Network Troubleshooting
- Enterprise Network Segmentation

---

# 📚 Key Learning Outcomes

After completing this project, I gained hands-on experience in:

- Designing an enterprise Layer 2 network
- Creating and managing VLANs
- Assigning switch ports to VLANs
- Configuring static IP addressing
- Verifying VLAN configurations using Cisco CLI
- Testing network connectivity
- Understanding VLAN isolation and broadcast domains
- Troubleshooting Layer 2 connectivity issues

---

# 🔜 Next Project

**Enterprise Inter-VLAN Routing (Router-on-a-Stick)**

In the next phase, a Cisco 2911 Router will be integrated to enable communication between VLANs using IEEE 802.1Q trunking and router subinterfaces, simulating a real-world enterprise network architecture.

---

## 👨‍💻 Author

**Bharath Kumar S R**

Aspiring DevOps & Cloud Engineer | AWS | Linux | Docker | Kubernetes | Terraform | Ansible | Cisco Networking
