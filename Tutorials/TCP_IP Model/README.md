
# 🌐 TCP/IP Model

The **TCP/IP Model** is a simplified version of the OSI Model and is used in real-life networking and the Internet.  
It has **4 layers** instead of 7.

---

## 📚 TCP/IP Model Layers

| Layer No. | Name | Simple Meaning | Examples |
|----------|-------|----------------|-----------|
| **4** | Application | Apps and protocols for users & software | HTTP, HTTPS, DNS, SSH, FTP, SMTP |
| **3** | Transport | Breaks data into packets and ensures safe delivery | TCP, UDP, Ports |
| **2** | Internet | Chooses best route to destination using IP | IP Addressing, Routing |
| **1** | Network Access (Link) | Physical transmission and hardware | Ethernet, Wi-Fi, MAC, NIC |

---

## 💡 Easy Trick to Remember
**A T I N**
- **A**pplication  
- **T**ransport  
- **I**nternet  
- **N**etwork Access  

---

## 📦 Real-Life Example: Opening Google in Browser

| Step | TCP/IP Layer |
|------|--------------|
| You type google.com | Application |
| Browser uses HTTP & DNS | Application |
| Data converted to packets using TCP | Transport |
| Route selected to Google server | Internet |
| Data sent via Wi-Fi or Ethernet | Network Access |

---

## 🛠 Why TCP/IP Is Important for DevOps

| Layer | DevOps Use |
|--------|-----------|
| Application | Debug APIs & websites using `curl`, DNS, HTTPS |
| Transport | Check ports, firewalls using `nc`, `ss`, TCP vs UDP |
| Internet | Check routing using `ping`, `traceroute`, `ip route` |
| Network Access | Fix Wi-Fi/cable issues, switches, NIC problems |

---

## 🧠 TCP vs UDP

| Feature | TCP | UDP |
|---------|------|------|
| Reliability | Guaranteed & safe delivery | Fast but no guarantee |
| Use case | Web, SSH, File transfer | Games, video calls, streaming |
| Example Ports | 80, 443, 22 | 53 (DNS), 161 (SNMP) |

---

## 🔥 Key Commands Mapped to TCP/IP Layers

| Task | Tool | Layer |
|-------|-------|---------|
| Check connectivity | `ping` | Internet |
| Check route | `traceroute` / `tracert` | Internet |
| Test ports | `nc -zv`, `ss -tulpn` | Transport |
| Test website | `curl -v` | Application |
| DNS Query | `nslookup`, `dig` | Application |
| Show IP | `ip a` | Network Access |
| Show route | `ip route` | Internet |
| Packet capture | `tcpdump` | Network Debugging (All) |

---

## 🧾 OSI vs TCP/IP Model Comparison (Simple Table)

| OSI Model | TCP/IP Model |
|------------|----------------|
| 7 Layers | 4 Layers |
| More theoretical | Practical & used on Internet |
| Clear separation | Combined layers |
| Used for teaching | Used in real networking |

Mapping:
| OSI Layer | TCP/IP Layer |
|-----------|--------------|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

---

## 🎯 Summary
> **TCP/IP is the model used in real networks and Internet communication.  
> It has 4 layers that help send data from one device to another safely and efficiently.**

---

