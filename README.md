# Order Service

Order Service handling order creation with idempotency, calls the inventory service for reserving items and persistent orders in PG. 
Implements global error handling, Logging with AOP and leverages virtual threads for scalability.

---

## Tech Stack
- Java 24 
- Spring Boot 3.5.x
- Spring Cloud 2025.0.x aka Northfields (OpenFeign) 
- Springdoc OpenAPI (Swagger UI)
- Testcontainers (Postgres for integration tests)
- Docker
- 
---

## Getting Started

### Prerequisites
- Java 24  
- Maven 3.9+  
- Docker & Docker Compose  

### Run Locally
```bash
mvn spring-boot:run
