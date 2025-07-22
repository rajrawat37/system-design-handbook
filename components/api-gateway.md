# API Gateway

An API Gateway is a **single entry point** for all client requests in a microservices architecture. It sits between the client and backend services, handling request routing, authentication, rate limiting, response aggregation, and other cross-cutting concerns.
API Gateway gives the frontend a single source of truth for multiple backend services. It abstracts away the complexity of the microservices and allows the frontend to work with unified, simplified APIs.

---

## 🧾 Example: Why Use an API Gateway?

### Without API Gateway

The frontend must:

- Know the URLs of all 3 services:
  - `/users` (Node.js)
  - `/orders` (Java)
  - `/payments` (Python)
- Make 3 separate HTTP requests
- Handle failure or timeout of any one service
- Combine the results manually in frontend logic

---

### With API Gateway

The frontend calls **one unified API**:

GET /api/user/123


Behind the scenes, the **API Gateway**:

- Makes internal calls to:
  - `http://user-service/users/123` (Node.js)
  - `http://order-service/orders/123` (Java)
  - `http://payment-service/payments/order123` (Python)
- Aggregates the responses
- Sends back a **single, merged JSON** response to the frontend

---

### Benefits of API Gateway

- Reduces the number of HTTP calls made by the client
- Hides microservice details and tech stack from the frontend
- Centralizes failure handling, retries, and logging
- Simplifies frontend logic with a unified API structure

---

## Responsibilities of an API Gateway

| Functionality        | Description |
|----------------------|-------------|
| **Request Routing**  | Forwards incoming requests to appropriate microservice |
| **Authentication**   | Validates JWTs, API keys, or session tokens |
| **Rate Limiting**    | Restricts request rate per client or IP |
| **Caching**          | Stores responses for frequent requests |
| **Request Aggregation** | Combines responses from multiple services into one |
| **Load Balancing**   | Distributes load across service instances |
| **Logging & Monitoring** | Centralized logging and metric collection |

---

##  Why Use an API Gateway?

- Provide a **single endpoint** to access multiple microservices
- Hide backend service complexity and internal architecture
- Handle common logic like **authentication**, **logging**, **monitoring**
- Reduce the number of calls the frontend has to make
- Enable features like **caching**, **rate limiting**, and **load balancing**



