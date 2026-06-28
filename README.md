<div align="center">

# G M Mani

**Backend Engineer · Java · Spring Boot · Microservices · Event-Driven Systems**

*Designing distributed backends for reliability at scale.*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](http://www.linkedin.com/in/mani12)
[![GitHub](https://img.shields.io/badge/gm--mani-181717?logo=github&logoColor=white&style=flat)](https://github.com/gm-mani)

</div>

---

## About me

Software Engineer at Tata Consultancy Services, Bengaluru, specialising in backend systems — Java, Spring Boot, and distributed microservices architecture.

I focus on event-driven design, async messaging with Kafka, API security (OAuth2/JWT, Keycloak), and resilience patterns like circuit breakers, retry chains, and dead-letter handling. The projects here demonstrate production-grade patterns: outbox pattern for guaranteed delivery, idempotent consumers, schema-enforced Kafka contracts, and multi-environment Docker deployments.

---

## Tech stack

**Core**
`Java 21` · `Spring Boot 3` · `Spring Cloud` · `Spring Security 6`

**Microservices & Messaging**
`Eureka` · `Spring Cloud Config` · `OpenFeign` · `Apache Kafka` · `Spring Cloud Stream` · `Avro` · `Schema Registry`

**Resilience**
`Resilience4j` · `Circuit Breaker` · `Retry` · `Rate Limiter` · `DLT` · `Idempotent Consumer`

**API & Security**
`Spring Cloud Gateway` · `OAuth2 / JWT` · `Keycloak` · `RBAC` · `REST APIs`

**Data & Persistence**
`Spring Data JPA` · `Hibernate` · `PostgreSQL` · `H2` · `Redis`

**DevOps & Tooling**
`Docker` · `Docker Compose` · `JIB` · `Maven` · `Git`

---

## Projects

### [Microservices — Banking Backend System](https://github.com/gm-mani/Microservices)

A production-style banking backend built with 7 Spring Boot microservices, demonstrating service-to-service communication, async event processing, and layered security in a reliability-critical domain.

![Architecture](./microservices-architecture.png)

**Services:** `accounts` · `loans` · `cards` · `API gateway` · `Eureka` · `Config Server` · `Message Service`

**Key patterns implemented:**
- Gateway handles OAuth2/JWT (Keycloak), Redis rate limiting, correlation ID propagation, and circuit breaker fallbacks — per route
- Services communicate via OpenFeign with Resilience4j circuit breakers and fallback handlers
- Account creation publishes to Kafka (`send-communication`); message service consumes asynchronously for email/SMS — zero coupling between services
- Config Server manages environment-specific profiles (default / test / prod) across all services
- Full Docker Compose setup across three environments; JIB for containerisation

`Spring Boot 3` · `Java 21` · `Kafka` · `Resilience4j` · `Spring Cloud Gateway` · `Keycloak` · `Redis` · `Docker Compose` · `JIB`

---

### [Kafka Order Processing System](https://github.com/gm-mani/kafka-order-processing-system)

A producer/consumer system built around the Kafka patterns that matter in production — guaranteed delivery, schema contracts, and safe duplicate handling.

**What's implemented:**
- **Outbox Pattern** — order and outbox event written in a single `@Transactional` block; a `@Scheduled` publisher polls and sends to Kafka, guaranteeing no lost events even if Kafka is temporarily down
- **Avro + Confluent Schema Registry** — strongly typed event contracts enforced between producer and consumer
- **Retry topics + Dead Letter Topic** — failed messages flow through `retry-1 (1s)` → `retry-2 (2s)` → `DLT`; poison messages parked for investigation
- **Idempotent consumer** — deduplication via `processed_orders` table; duplicate deliveries safely ignored
- **Manual offset acknowledgment** — offsets committed only after successful processing
- Consumer group rebalancing, message keys for ordering guarantees, Kafka UI for monitoring

`Spring Boot 3` · `Apache Kafka` · `Avro` · `Schema Registry` · `Outbox Pattern` · `DLT` · `PostgreSQL` · `Docker Compose`

---

## Currently working on

- Kubernetes — migrating the microservices system from Docker Compose to K8s (ConfigMaps, health probes, resource limits)
- Distributed tracing with Micrometer + Zipkin
- Refresh token rotation and method-level security in Spring Security

---

## Get in touch

**LinkedIn:** [linkedin.com/in/mani12](http://www.linkedin.com/in/mani12)
**GitHub:** [github.com/gm-mani](https://github.com/gm-mani)

---

<div align="center">
<sub>Based in Bengaluru, India · Open to opportunities</sub>
</div>
