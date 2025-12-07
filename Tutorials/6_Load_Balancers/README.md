# ⚖️ Load Balancers 

A **Load Balancer** is a networking component that **distributes incoming traffic across multiple servers** so that no single server gets overloaded.  
It helps improve **performance, reliability, and availability** of applications.

---

## 💡 Simple Example

Imagine a restaurant with 4 counters.  
Customers enter → Load Balancer → decide which counter is free → send them there.

Without load balancer = big queue at one counter  
With load balancer = customers split and served faster

Same for websites and servers.

---

## 🧠 Why Load Balancer is used?

| Benefit | Meaning |
|---------|---------|
| High availability | If one server fails, traffic goes to another |
| Better performance | Multiple servers handle more users |
| Zero downtime deployment | Shift traffic during updates |
| Scalability | Add or remove servers easily |
| Security | Hide internal server IPs |

---

## 🏗 Types of Load Balancers

### 1. **Layer 4 Load Balancer (Transport Layer)**
Works based on **IP + Port + TCP/UDP**.

| Example | |
|---------|--|
| Load balancer checks request on port 80 | Sends to one backend server |

➡ Fast but no content intelligence.

**Examples**
- AWS NLB (Network Load Balancer)
- Kubernetes Service NodePort / LoadBalancer
- HAProxy (L4 mode)
- Nginx (L4 mode)

---

### 2. **Layer 7 Load Balancer (Application Layer)**
Understands **HTTP, HTTPS, URLs, Cookies, Headers**, etc.

| Example | |
|---------|--|
| /login → server A | /images → server B |

➡ Smart routing & content rules.

**Examples**
- AWS ALB (Application Load Balancer)
- NGINX
- Traefik
- Envoy / Istio (Service Mesh)
- Google Cloud LB

---

## 🔀 Load Balancing Algorithms

| Algorithm | Meaning |
|-----------|----------|
| **Round Robin** | Requests go one-by-one per server |
| **Least Connections** | Send to server with least active users |
| **IP Hash** | Same client always goes to same server |
| **Weighted Round Robin** | Powerful servers get more requests |
| **Random** | Random distribution |

---

## 🧪 Real DevOps Example
```
User → Load Balancer → 3 backend servers

Server-1 ✓ running
Server-2 ✓ running
Server-3 ✖ down

Load balancer sends traffic only to Server-1 & Server-2
```
---

This is called **Health Check**.

---

## 🔥 Where DevOps Uses Load Balancers

| Platform | Example |
|---------|---------|
| AWS | ALB, NLB, ELB |
| Kubernetes | Service type LoadBalancer / Ingress |
| Docker Swarm | Routing mesh |
| Reverse Proxy | NGINX, HAProxy |
| Cloudflare | Web load balancing |

---

## 🧠 Health Checks

A load balancer continuously tests servers.

Example:
```text
http://server1:8080/health
Response: 200 OK → send traffic
If 500, timeout, or no response → mark unhealthy
```
---
| Load Balancer                   | Reverse Proxy                                       |
| ------------------------------- | --------------------------------------------------- |
| Distributes load across servers | Handles requests for backend but may not split load |
| In front of multiple servers    | In front of one or many servers                     |
| Improves availability           | Improves security & caching                         |

---
| Feature              | Load Balancer Purpose |
| -------------------- | --------------------- |
| Traffic Distribution | Prevent overload      |
| High Availability    | Failover              |
| Scalability          | Add more servers      |
| Health Checks        | Test server status    |
| Security             | Hide private IPs      |

---
