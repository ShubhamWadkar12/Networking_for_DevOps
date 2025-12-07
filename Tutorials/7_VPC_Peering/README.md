# 🌐 VPC & VPC Peering

## 🏗 What is VPC?
**VPC (Virtual Private Cloud)** is a **private network inside a cloud provider (AWS, GCP, Azure)** where you run servers, databases, and applications securely.

### 🧠 Simple Meaning
**Your own private network in the cloud.**

### 🔥 Why Use VPC?
- Secure private environment
- Full control over IPs, subnets, routing
- Separate Production / Testing / Dev networks
- Can connect to on-prem systems

### 🧱 Components of VPC
| Component | Meaning |
|-----------|----------|
| Subnet | Small network inside VPC |
| Route Table | Defines traffic direction |
| Internet Gateway | Allows internet access |
| NAT Gateway | Internet for private subnets |
| Security Group | Virtual Firewall |
| NACL | Subnet-level rules |

---

## 🔄 What is VPC Peering?
**VPC Peering connects two VPCs so they can communicate privately using private IPs.**

### 🧠 Simple Meaning
**Two separate private networks connected like a private bridge.**

Example:
VPC-A (App Servers) ↔ VPC-B (Databases)

---

### 🎯 Why Use VPC Peering?
- Allow services from different VPCs to talk
- No VPN or public internet needed
- Low-latency secure communication

---

## ⚙ Requirements for VPC Peering
| Requirement | Meaning |
|-------------|-----------|
| Different CIDR blocks | Example: `10.0.0.0/16` & `192.168.0.0/16` |
| Route tables updated | Add routes manually |
| Security groups allow traffic | Allow inbound rules |

---

## 🔧 Example Routing Table Entry
Destination: 192.168.0.0/16
Target: pcx-123456
---

---

## 🧪 Real DevOps Use Case
| Use Case | Example |
|-----------|----------|
| App servers in one VPC, DBs in another | `App → Peering → DB` |
| Multi-account cloud network | Shared Services VPC |
| Hybrid & microservices design | Secure internal comms |

---

## 🚫 Limitations of VPC Peering
| Limitation | Meaning |
|------------|----------|
| No transitive peering | A ↔ B ↔ C won’t route |
| Manual route updates | No automation |
| Cannot work across overlapping CIDRs | No same IP ranges |

---

## 🎯 Summary

| Term | Simple Meaning |
|-------|----------------|
| **VPC** | Private cloud network |
| **Subnet** | Smaller pieces inside VPC |
| **VPC Peering** | Connect two VPCs privately |

---

## 🧪 Quick Hands-On Practice (Try Yourself)
1. Create two VPCs in AWS (different CIDRs)
2. Add two subnets and EC2 in each
3. Create VPC peering connection
4. Update route tables
5. Ping internal private IP between EC2 machines

Expected result:
```text
Ping success = VPC peering working 🎉
```
