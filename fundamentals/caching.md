# Caching

Caching is the process of storing frequently accessed data in a fast storage layer (usually in-memory) so future requests can be served faster. It helps reduce load on databases and improves response time.

---

## Why Use Caching?

- Reduce database load
- Improve latency (faster responses)
- Handle high traffic more efficiently
- Save cost on expensive computations or API calls

**Example**:  
Instead of hitting the database every time a user loads the home page, store the homepage data in cache and serve it directly.

---

## Common Use Cases

- User session data
- Product catalog pages
- User profile details
- Popular blog posts or videos
- API responses (e.g., weather, currency rates)

---

## How Caching Works

1. Client sends a request.
2. Server checks the cache:
   - If data is found (cache hit), return it.
   - If data is not found (cache miss), fetch it from the database, store it in cache, and return it.

---

## Types of Caching

### 1. In-Memory Caching

- Fastest type of cache
- Data stored in RAM
- Common tools: **Redis**, **Memcached**

### 2. CDN Caching

- Used for static files (images, JS, CSS)
- Cached at global edge locations
- Tools: Cloudflare, Akamai

### 3. Browser Cache

- Client-side cache
- Stores static assets using HTTP headers (`Cache-Control`, `Expires`)

---

## Caching Strategies

### 1. Write-Through Cache

- Data is written to both the cache and the database simultaneously.
- Ensures consistency but slower for writes.

### 2. Write-Back (Write-Behind) Cache

- Write happens to the cache first.
- Database is updated asynchronously.
- Faster writes but risk of data loss if cache fails.

### 3. Cache-Aside (Lazy Loading)

- Application reads from cache first.
- On cache miss, it reads from the database and stores it in cache.
