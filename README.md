<div align="center">

# G M Mani

**Backend Engineer · Java · Spring Boot · Microservices**

*Building distributed systems that don't fall over.*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](http://www.linkedin.com/in/mani12)
[![GitHub](https://img.shields.io/badge/GitHub-gm--mani-181717?style=flat&logo=github)](https://github.com/gm-mani)

</div>

---

## About me

I'm a Software Engineer at Tata Consultancy Services, Bengaluru, focused on building scalable backend systems with Java and Spring Boot. I care about how services talk to each other, how they fail gracefully, and how they're wired together in production.

Most of my work lives in the microservices space — service discovery, async event streaming, API gateway patterns, and making sure the system keeps running when one piece breaks.

---

## Tech stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=spring-security&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

---

## GitHub stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=gm-mani&show_icons=true&theme=tokyonight&hide_border=true" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=gm-mani&layout=compact&theme=tokyonight&hide_border=true" height="165" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=gm-mani&theme=tokyonight&hide_border=true" />
</p>

---

## Featured project

### [Microservices — Banking Backend System](https://github.com/gm-mani/Microservices)

A fully wired, production-style microservices architecture built around a fictional banking domain. Not a tutorial clone — this is a system designed end-to-end with the patterns you'd expect in real distributed services work.

**What's inside:**

| Service | What it does |
|---|---|
| `accounts` | Core CRUD service — manages customers and bank accounts |
| `loans` | Loan lifecycle management |
| `cards` | Card issuance and details |
| `gatewayserver` | API gateway — routes, secures, rate-limits, and traces all traffic |
| `eurekaserver` | Service registry — all services register and discover each other here |
| `configserver` | Centralised config with environment-specific profiles (default / test / prod) |
| `message` | Async consumer — handles email and SMS notification events off the Kafka queue |

**How it's wired together:**

- Services communicate via **OpenFeign** with **Resilience4j circuit breakers** and **fallback handlers** — if a downstream service is down, requests degrade gracefully instead of cascading
- Account creation fires an event onto a **Kafka topic** (`send-communication`), the message service consumes it and processes email/SMS — fully async, fully decoupled
- The gateway enforces **OAuth2 / JWT auth via Keycloak**, performs **Redis-based rate limiting**, and propagates a **correlation ID** across the entire request chain for distributed tracing
- Retry policies, circuit breaker configs, and rate limiters are all tuned per-service in the centralised config server
- **Three Docker Compose environments** — `default`, `test`, `prod` — with shared base configs and service health checks

**Stack:** `Spring Boot 4` · `Java 21` · `Kafka` · `Resilience4j` · `Spring Cloud Gateway` · `Keycloak` · `Redis` · `Docker Compose` · `JIB`

---

## Contribution graph

![Snake](https://raw.githubusercontent.com/gm-mani/gm-mani/output/github-contribution-grid-snake-dark.svg)

---

<div align="center">
<sub>Based in Bengaluru, India · Open to opportunities</sub>
</div>
