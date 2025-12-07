
# 🌍 IP Address & Subnetting (Simple Words – DevOps Friendly)

This guide explains **IP addresses, subnet masks, networks, hosts, and CIDR**  
in the simplest possible way — useful for DevOps, cloud, networking & interviews.

---

## 🔹 What is an IP Address?

An **IP address** is like the **home address of a device on a network**.  
It helps devices identify each other and send data.

### Example:
```
192.168.1.10
```


- `192.168.1` = Network part
- `.10` = Host (device) part

---

## 🔹 Types of IP

| Type | Meaning | Example |
|------|----------|----------|
| **Public IP** | Used on internet | 8.8.8.8 |
| **Private IP** | Used in local network | 192.168.x.x, 10.x.x.x |
| **Static IP** | Fixed | Servers, DB |
| **Dynamic IP** | Changes automatically | Home Wi-Fi devices |

Common private IP ranges:
```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```


---

# 🟧 What is Subnetting?

**Subnetting = dividing a large network into smaller networks.**  
It improves performance, security, and IP management.

### Why subnet?
- Reduce network traffic
- Separate departments (HR, Finance, DevOps, etc.)
- Better security control

---

# 🔢 IP + Subnet Mask Example
```
192.168.1.10 /24
```

| Part | Meaning |
|--------|------------|
| `192.168.1` | Network |
| `.10` | host |
| `/24` | 24 bits for network (subnet mask) |

### `/24` in decimal subnet mask:
```
255.255.255.0
```


---

# 📍 CIDR (Classless Inter-Domain Routing)

CIDR = `/` notation used to show subnet size.

| CIDR | Hosts available | Subnet Mask |
|-------|-----------------|----------------|
| **/30** | 2 usable hosts | 255.255.255.252 |
| **/29** | 6 hosts | 255.255.255.248 |
| **/28** | 14 hosts | 255.255.255.240 |
| **/27** | 30 hosts | 255.255.255.224 |
| **/26** | 62 hosts | 255.255.255.192 |
| **/24** | 254 hosts | 255.255.255.0 |
| **/16** | 65,534 hosts | 255.255.0.0 |
| **/8** | 16M+ | 255.0.0.0 |

💡 **Reminder:**  
Network address = first IP  
Broadcast address = last IP

---

# ✨ Example Subnetting Breakdown
```
Network:
192.168.1.0 /24
```
---

| Type | Value |
|-------|--------|
| Network Address | 192.168.1.0 |
| Usable Host Range | 192.168.1.1 – 192.168.1.254 |
| Broadcast Address | 192.168.1.255 |
| Total Hosts | 256 |
| Usable Hosts | 254 |

---

# 🧠 Real Example for DevOps

Company wants to split network by teams:

| Team | Network |
|---------|-----------|
| Dev Team | 192.168.1.0 /26 (62 hosts) |
| QA Team | 192.168.1.64 /26 |
| Security | 192.168.1.128 /26 |
| Production | 192.168.1.192 /26 |

---

# 🛠 Useful Commands for IP + Subnet

| Purpose | Command |
|---------|----------|
| Show IP | `ip a` |
| Show routing | `ip route` |
| Check subnet | `ipcalc 192.168.1.0/24` *(install: `sudo apt install ipcalc`)* |
| Network scan | `nmap -sn 192.168.1.0/24` |

Example:
```bash
ipcalc 192.168.10.0/28
```
---

| Concept     | Meaning                            |
| ----------- | ---------------------------------- |
| IP Address  | Identity of device                 |
| Subnet Mask | Defines network & host area        |
| CIDR        | `/` notation for subnet            |
| Subnetting  | Breaking large network into small  |
| /24         | Most common LAN subnet (254 hosts) |
