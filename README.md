# E-Commerce Microservices

A Spring Boot-based e-commerce application built using a microservices architecture. The project consists of independent services for order management, inventory management, service discovery, and API gateway routing.

## 🏗️ Architecture

```text
                    Client
                       |
                       v
                +-------------+
                | API Gateway |
                |    :8080    |
                +-------------+
                       |
                       v
                +-------------+
                |    Eureka   |
                |    :8761    |
                |  Discovery  |
                +-------------+
                    /       \
                   /         \
                  v           v
        +---------------+  +------------------+
        | Order Service |  | Inventory Service|
        |     :9020     |  |      :9010       |
        +---------------+  +------------------+
                 \              /
                  \            /
                   +----------+
                    PostgreSQL
🧩 Microservices
1. API Gateway
- Central entry point for client requests
- Routes requests to appropriate microservices
- Uses Spring Cloud Gateway
- Supports service discovery through Eureka
2. Discovery Service
- Provides service registration and discovery
- Built using Netflix Eureka
- Allows microservices to locate each other dynamically
3. Order Service
- Handles order-related operations
- Communicates with the Inventory Service
- Uses PostgreSQL for data persistence
- Implements resilience patterns using Resilience4j
4. Inventory Service
- Manages product and inventory information
- Uses PostgreSQL for persistence
- Provides APIs for inventory-related operations
🛠️ Technologies Used
- Java
- Spring Boot
- Spring Cloud
- Spring Cloud Gateway
- Netflix Eureka
- Spring Data JPA
- Hibernate
- PostgreSQL
- Resilience4j
- Maven
- REST APIs
- Git & GitHub
✨ Key Features
- Microservices-based architecture
- API Gateway routing
- Service discovery with Eureka
- Inter-service communication
- PostgreSQL database integration
- JPA/Hibernate based persistence
- Retry mechanism using Resilience4j
- Circuit breaker using Resilience4j
- Rate limiting using Resilience4j
- Actuator-based application monitoring
🛡️ Resilience
The Order Service uses Resilience4j to improve reliability when communicating with other services.
Implemented patterns include:
- Retry — retries failed requests
- Circuit Breaker — prevents repeated calls to an unavailable service
- Rate Limiter — controls the number of requests within a time period
🚀 How to Run
Prerequisites
Make sure the following are installed:
- Java 17+
- Maven
- PostgreSQL
- IntelliJ IDEA (recommended)
1. Clone the repository
git clone https://github.com/Harsh-singh002/ecommerce-microservices.git
cd ecommerce-microservices
2. Configure PostgreSQL
Create the required databases:
orderDB
inventoryDB
Configure your database username and password using environment variables rather than committing credentials to the repository.
Example:
DB_USERNAME=your_username
DB_PASSWORD=your_password
3. Start the services
Start the services in this order:
1. Discovery Service
2. Inventory Service
3. Order Service
4. API Gateway
4. Access the services
Eureka Dashboard:
http://localhost:8761

API Gateway:
http://localhost:8080
## 📁 Project Structure
ecommerce-microservices/
│
├── api-gateway/
│
├── discovery-service/
│
├── inventory-service/
│
├── order-service/
│
├── .gitignore
└── README.md
📌 Future Improvements
- Add Swagger / OpenAPI documentation
- Add JUnit and Mockito tests
- Containerize services using Docker
- Add centralized configuration
- Add distributed tracing
- Add CI/CD pipeline
👨‍💻 Author
Harsh Singh
B.E. Computer Science and Engineering