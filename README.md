# API Gateway - Pet Clinic Microservices

Unified Entry Point and Routing Engine for the Pet Clinic polyrepo microservices application, built with **Spring Boot 3.4.3**, **Spring Cloud Gateway (2024.0.0)**, and **Java 25**.

## Features

- **Centralized Routing Hub**: Single point of ingress (`:8080`) for all frontend and client API requests.
- **Eureka Load-Balanced Discovery**: Resolves downstream microservices dynamically (`lb://DOCTOR-SERVICE`, `lb://PET-SERVICE`, `lb://APPOINTMENT-SERVICE`).
- **Global CORS Configuration**: Configured to handle cross-origin requests seamlessly for the React frontend application.

## Port & Route Mappings

- **Port**: `8080`

| Route Predicate | Target Service | Load Balancer URI |
| :--- | :--- | :--- |
| `/api/doctors/**` | Doctor Service (`:8081`) | `lb://DOCTOR-SERVICE` |
| `/api/pets/**` | Pet Service (`:8082`) | `lb://PET-SERVICE` |
| `/api/appointments/**` | Appointment Service (`:8083`) | `lb://APPOINTMENT-SERVICE` |

## How to Run

```bash
mvn clean spring-boot:run
```
