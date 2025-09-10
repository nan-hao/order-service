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
---

## Getting Started

### Prerequisites
- Java 24  
- Maven 3.9+  
- Docker & Docker Compose  

### Run Locally
```bash
mvn spring-boot:run
```

### Swagger UI
http://localhost:8080/swagger-ui.html

### Example API Calls
1. Get order by ID 
```bash
curl http://localhost:8080/orders/ORD-98765
```
2. Create order
```bash
curl -X POST http://localhost:8080/orders \
  -H "Content-Type: application/json" \
  -H "orderId: ORD-98765" \
  -d '{
        "customerId": "C-123",
        "items": [
          { "productCode": "PROD-001", "qty": 1 },
          { "productCode": "PROD-002", "qty": 2 }
        ]
      }'
```

### Notes
In production, schema management would be handled by Liquibase. For demo purposes, Hibernate auto-ddl is used.
