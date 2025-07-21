Scalability : **Scalability** is a system's ability to handle increased load without performance degradation.
            : Ability of a system to handle more load— like more users, more data, or more requests—without slowing down or failing.

---

## Types of Scalability

### 1. Vertical Scaling (Scaling Up)
- Add more resources (CPU, RAM) to a single machine. (eg : upgrading 4GM RAM on server to 32GB RAM)
- Simpler to implement
- Has a hardware limit
- If server goes down the app also goes down(single point of failure)

### 2. Horizontal Scaling (Scaling Out)
- Add more machines or nodes to the system ( Instead of one powerful server, use 5 smaller servers )
- Virtually unlimited scalability
- Adds complexity (e.g., consistency, networking)
- More fault-tolerant—if one server crashes, others keep working.
- More complex to manage.

---

## Vertical vs Horizontal Scaling

| Feature         | Vertical Scaling   | Horizontal Scaling |
|----------------|--------------------|--------------------|
| Cost            | Lower initial cost | Higher long-term cost |
| Simplicity      | Easier             | More complex |
| Fault Tolerance | Low (single point of failure) | High |
| Scalability Limit | Hardware-dependent | Scales indefinitely |



## Why Systems Need to Scale

- Growing number of users ( Instagram grew from thousands to billions of users)
- Spikes in traffic (e.g. product launches, viral features, Flipkart’s Big Billion Days causes 10x traffic)
- Increasing data volume over time ( WhatsApp stores billions of messages per day )
- Better user experience and uptime
---

## How to Scale a System

### 1. Use Load Balancers  
Distribute user traffic across multiple servers to prevent overload.

**Example**:  
AWS Elastic Load Balancer or NGINX.

### 2. Replicate Services  
Run multiple instances of the same backend service.

**Example**:  
Deploying 10 stateless Node.js servers to handle login requests.

### 3. Add Read Replicas  
Create copies of databases to handle read traffic.

**Example**:  
A MySQL master handles writes; replicas handle all reads.

### 4. Shard the Database  
Split large datasets across multiple databases based on user ID or region.

**Example**:  
User IDs 1–1M go to DB1, 1M–2M to DB2.

### 5. Use Caching and CDN  
Store frequently accessed data close to users or in memory.

**Example**:  
Store profile pages in Redis cache or deliver images through Cloudflare CDN.

---
