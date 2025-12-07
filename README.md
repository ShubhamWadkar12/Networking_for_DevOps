# 🌐 Networking Commands & Concepts for DevOps Engineers 

---

## 🧠 Key Networking Concepts for DevOps

| Concept | Why DevOps uses it |
|---------|---------------------|
| **IP Address** | Identify servers and containers |
| **Ports** | Connect to services (e.g., 80,443,22,3306,8080) |
| **DNS** | Convert domain → IP during deployment |
| **Firewall / Security Groups** | Allow / block ports in cloud |
| **Routing** | Check network paths in cloud/VPC |
| **Load Balancer** | Distribute traffic between servers |
| **Reverse Proxy (Nginx/HAProxy)** | Manage routing/API access |
| **TCP vs UDP** | Debug connectivity & performance |
| **HTTP Status Codes** | Debug API, website issues |
| **SSH** | Remote server access |
| **Packets & Monitoring** | Check network flow & issues |

---

# 🛠 Networking Commands DevOps Uses Daily

---

## 1️⃣ Check Connectivity

```bash
ping google.com
ping 8.8.8.8
```

---

## 2️⃣ Check DNS & domain → IP

```bash
nslookup github.com
dig google.com +short

```
---

### 3️⃣ traceroute / tracert
Check the path your packets take to reach destination.

```bash
traceroute google.com         # Linux
tracert google.com            # Windows
```
---

### 4️⃣ Test HTTP / API Response

```
curl https://example.com
curl -I https://example.com
curl -v https://example.com

curl -X GET https://api.example.com/users

```
---

### 5️⃣ Test If Port Is Reachable (DB, App, Services)
```
nc -zv server-ip 80
nc -zv 192.168.1.10 8080

telnet server-ip 80      # old way
```
---

### 6️⃣ Check Open Ports & Running Services
```
ss -tulpn
ss -tulpn | grep 8080

netstat -tulpn         # older command
```

### 7️⃣ View Network Interfaces & IPs
```
ip a

ipconfig    #older way

```
---

### 8️⃣ View Routing Table (Gateway / VPC / Subnet Issues)

```
ip route
route -n
```
---

### 9️⃣ SSH to Remote Server
```
ssh user@server-ip
ssh -i key.pem ubuntu@54.xx.xx.xx

Copy files:

scp file.txt ubuntu@server:/home/ubuntu/
```
---

### 🔟 Capture & Inspect Network Traffic (Deep Debugging)

```
sudo tcpdump -i eth0
sudo tcpdump -i eth0 port 80
sudo tcpdump -i eth0 -w capture.pcap
```

| Code    | Meaning                |
| ------- | ---------------------- |
| 200     | OK                     |
| 301/302 | Redirect               |
| 400     | Client error           |
| 401     | Unauthorized           |
| 403     | Forbidden              |
| 404     | Not found              |
| 500     | Server error           |
| 502     | Bad gateway (LB issue) |
| 503     | Service unavailable    |

Check using:
```
curl -I https://google.com
```
---

Summary:

| Task            | Command           |
| --------------- | ----------------- |
| Host Reachable? | `ping`            |
| DNS working?    | `nslookup`, `dig` |
| Route path?     | `traceroute`      |
| Check site/API  | `curl`            |
| Download file   | `wget`            |
| IP addresses    | `ip a`            |
| Routing         | `ip route`        |
| Active services | `ss -tulpn`       |
| Port reachable? | `nc -zv`          |
| Connect server  | `ssh`             |
| Transfer files  | `scp`, `sftp`     |
| Capture packets | `tcpdump`         |

---
