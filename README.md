# 🌐 Networking Basics

---

## 📌 Why Networking Matters in DevOps
DevOps engineers work with:
- Cloud platforms (AWS / Azure / GCP)
- Containers & orchestration (Docker & Kubernetes)
- CI/CD systems
- Distributed applications & microservices
- Security, firewalls & load balancing

Without networking knowledge, it's impossible to debug issues like:
- Application not reachable
- DNS failure
- Port blocked / service down
- Routing or latency issues
- Load balancer failures
- Cross-VPC / microservice communication issues

---

# 🧠 Core Networking Concepts for DevOps

### **IP Address**
A unique identification given to a device inside a network.
- **Private IP:** Used inside internal networks (e.g., 192.168.x.x)
- **Public IP:** Used on the internet
- **IPv4 / IPv6:** Different addressing versions

### **Subnet**
Divides a large network into smaller networks for better performance and security.
- Example: `/24`, `/16`, `/30` etc.

### **CIDR**
Short notation representing subnet size.
- Example: `10.0.0.0/16` = large network

### **Gateway**
The device that connects local network to another network (like the internet).

### **DNS (Domain Name System)**
Converts human-readable names into IP addresses.
- Example: `google.com → 142.xx.xx.xx`

### **NAT (Network Address Translation)**
Converts private IP ↔ public IP to allow devices inside a private network to access external networks.

### **Firewall**
Security layer that allows or blocks specific network traffic based on rules.

### **Ports**
Different entry points for different application services.
- Example: 80 (HTTP), 443 (HTTPS), 22 (SSH)

### **Protocols**
Rules that define data communication.
- **TCP** → reliable
- **UDP** → fast but not guaranteed
- **HTTP/HTTPS** → web communication
- **FTP / SSH / SMTP** → various services

---

# 📦 Real DevOps Use Case Example (High-Level)
