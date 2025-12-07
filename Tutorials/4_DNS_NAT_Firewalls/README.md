# 🌍 DNS, NAT & Firewalls 

This README explains three very important networking concepts used daily by **DevOps engineers**:
- **DNS (Domain Name System)**
- **NAT (Network Address Translation)**
- **Firewalls**

---

# 🧠 1. DNS (Domain Name System)

DNS is like the **phonebook of the internet**.  
It converts **domain names** (easy for humans) into **IP addresses** (computers use IP to communicate).

### Example
```
You type: google.com
DNS translates to: 142.250.193.78
```

### Why DNS is needed?
Because we can’t remember thousands of IPs.

### ⚙ Real DevOps Uses of DNS
| Task | Tool |
|------|------|
| Debug domain issue | `nslookup google.com` |
| Get IP quickly | `dig google.com +short` |
| Check DNS records | `dig google.com` |
| Check DNS inside container | `cat /etc/resolv.conf` |

### 📌 Common DNS records
| Type | Meaning | Example |
|--------|--------|-----------|
| **A** | Domain → IPv4 | google.com → 142.250.x.x |
| **AAAA** | Domain → IPv6 | |
| **CNAME** | Alias name | www → google.com |
| **MX** | Mail server | gmail MX records |
| **TXT** | Verification | SPF, DKIM |
| **NS** | Who hosts DNS | Name servers |

---

# 🧠 2. NAT (Network Address Translation)

NAT allows many internal devices to share **one public IP**.  
It translates **private IP ↔ public IP** when accessing the internet.

### Simple example
```
Private home network:
Laptop: 192.168.1.10
Phone: 192.168.1.15
Smart TV: 192.168.1.30

All go to internet using public IP: 49.77.25.10
```
---

### Why NAT is used?
- IPv4 addresses are limited
- Provides security (internal IPs are hidden)
- Saves cost

### Types of NAT
| Type | Meaning |
|------|----------|
| **SNAT** | Source NAT (internal → public) |
| **DNAT** | Destination NAT (public → internal mapping) |
| **PAT** | Port-based NAT (router assigns ports) |

### Real DevOps Example
| Use case | Example |
|----------|---------|
| Access EC2 inside VPC | Public NAT Gateway |
| Kubernetes | NodePort / ClusterIP / LoadBalancer |
| Exposing internal server | DNAT: `203.x.x.x:5000 → 192.168.x.x:5000` |

---

# 🧠 3. Firewall

A firewall **controls what traffic is allowed or blocked** based on rules (ports, IP, protocol).

### Simple example
```
Allow: 22 (SSH), 80 (HTTP), 443 (HTTPS)
Block: 23, 21, 3389
```
---

### Firewall rules concept
```
ALLOW port 80 from anywhere
ALLOW port 22 only from 10.0.0.0/24
DENY all others
```
---

### Real DevOps Tools
| Platform | Command |
|-----------|---------------|
| Linux Firewall | `sudo ufw enable` `sudo ufw allow 22` |
| CentOS Firewall | `firewall-cmd --list-all` |
| AWS EC2 | Security Groups |
| Kubernetes | Network Policies |
| Cloudflare | Web firewall for websites |

### Example Commands
```bash
sudo ufw status
sudo ufw allow 22
sudo ufw deny 8080
sudo ufw disable
```
---
### Useful DevOps case
- Web app not loading → port 80 blocked
- SSH denied → security group rule missing
- DB unreachable → internal-only firewall
---
| Concept      | Simple meaning                 | Used for                           |
| ------------ | ------------------------------ | ---------------------------------- |
| **DNS**      | Domain name → IP translation   | Website & API resolution           |
| **NAT**      | Private ↔ public IP conversion | Internet access & cloud networking |
| **Firewall** | Allow / block network traffic  | Security & access control          |

---
### 🚀 Real DevOps Troubleshooting Example
Problem:

> Website not opening: app.example.com

| Step           | Command                    |
| -------------- | -------------------------- | 
| Check DNS      | `nslookup app.example.com` |         
| Ping IP        | `ping <resolved-ip>`       |          
| Check port     | `nc -zv <ip> 443`          |
| Check firewall | AWS SG / `ufw status`      |        
| Check route    | `traceroute <ip>`          |      
| Check service  | `ss -tulpn                 |

---
| Question            | Answer                                             |
| ------------------- | -------------------------------------------------- |
| What is DNS?        | Converts domain names to IP addresses              |
| What is NAT?        | Maps private IPs to public IPs                     |
| What is a Firewall? | Controls what traffic can enter or leave a network |
