# Load Balancing

Load balancing is the process of distributing incoming network traffic or user requests across multiple servers to ensure no single server is overwhelmed.

It improves system **availability**, **scalability**, and **fault tolerance**.

---

## Why Use Load Balancing?

- Handle more traffic without slowing down
- Prevent any single server from becoming a bottleneck
- Ensure high availability and uptime
- Allow horizontal scaling (adding/removing servers easily)

---

## Real-World Example

Imagine an e-commerce website during a sale:
- Millions of users send requests at the same time.
- A load balancer distributes these requests across 10 servers instead of just 1.
- If one server fails, traffic is redirected to the others.

---

## Types of Load Balancers

### 1. Hardware Load Balancer
- Physical device (e.g., F5, Citrix)
- Used in data centers or legacy setups
- Expensive but powerful

### 2. Software Load Balancer
- Installed on servers (e.g., NGINX, HAProxy)
- Flexible and widely used

### 3. Cloud Load Balancer
- Provided as a service (e.g., AWS ELB, Google Cloud Load Balancer)
- Scalable, pay-as-you-go

---

## Layer 4 vs Layer 7 Load Balancing

| Layer | Works At | Example |
|-------|----------|---------|
| Layer 4 | Transport (TCP/UDP) | Load balancing based on IP, port |
| Layer 7 | Application (HTTP/HTTPS) | Balancing based on URL path, headers, cookies |

---

## Common Load Balancing Algorithms

| Algorithm | Description |
|----------|-------------|
| Round Robin | Sends requests to servers in order, one by one |
| Least Connections | Sends new request to server with fewest active connections |
| IP Hashing | Chooses server based on hash of client IP (helps session stickiness) |
| Weighted Round Robin | Assigns weight to each server (powerful servers get more traffic) |

---

## Health Checks

A good load balancer performs health checks to monitor server status.

- If a server fails the check, it is removed from the rotation.
- Once it recovers, it is added back automatically.

---

## Load Balancer Placement

- **Client → DNS → Load Balancer → Web Servers**
- Load balancer sits between users and your backend servers.
- Can also be used between internal services (e.g., between web and DB layers).

---

## Horizontal Scaling with Load Balancer

- Add or remove servers without affecting clients
- Combine with **auto-scaling** to handle sudden traffic changes
- Makes system elastic and highly available

---

## Challenges

- Load balancer itself can be a single point of failure (SPOF)
  - Use multiple LBs in HA (high availability) setup
- Session stickiness (users always routed to same server) can be tricky
- Cost and configuration complexity (especially in hybrid or global setups)

---

## Summary

- Load balancing is essential for scaling, availability, and performance
- Choose the right algorithm based on traffic pattern and use case
- Use cloud-based or software-based load balancers for flexibility
- Ensure redundancy to avoid making your load balancer a failure point
