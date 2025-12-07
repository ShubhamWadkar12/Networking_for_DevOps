# 🌐 Ping / Traceroute / Nslookup

This document explains the **3 most important network troubleshooting commands** used daily by **DevOps engineers** to check connectivity, routing path, and DNS issues.

---

## 1️⃣ Ping

### 📌 What Ping Does
`ping` checks if a server or device is reachable and measures response time.

### 🧠 Simple Meaning
**"Are you alive?" check for a server**

### 💻 Example Command
```bash
ping google.com
ping 8.8.8.8
```
---
## 2️⃣ Traceroute / Tracert
### 📌 What Traceroute Does
Shows the path (hops) that data travels to reach the destination and where delays happen.

### 🧠 Simple Meaning
"How do I reach the target and where is the problem?"
```
traceroute google.com      #linux
tracert google.com         #windows
```
---
## 3️⃣ Nslookup
### 📌 What Nslookup Does
Resolves a domain name to an IP address (DNS lookup).

### 🧠 Simple Meaning
"What is the IP of this website/server?"
```
nslookup github.com
nslookup google.com

```
---
| Command      | Purpose                  | Used For                 |
| ------------ | ------------------------ | ------------------------ |
| `ping`       | Check reachability       | Connectivity testing     |
| `traceroute` | Show route & hop delays  | Troubleshooting slowness |
| `nslookup`   | DNS name → IP resolution | Domain issues            |

---
| Tool           | Simple Meaning                       |
| -------------- | ------------------------------------ |
| **Ping**       | Is server alive & how fast?          |
| **Traceroute** | How do we reach the server?          |
| **Nslookup**   | What IP does this domain resolve to? |
