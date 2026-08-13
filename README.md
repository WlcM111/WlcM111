# Mikhail Zorin — Go Backend Developer

Backend developer working in **Go** on **microservices, event-driven systems and payment flows**.
3rd-year Applied Informatics student at **SUAI** (GPA 4.89) with **1.5+ years** of backend development across production, contract and team projects. Main interests: backend architecture, distributed systems, storage-oriented services and infrastructure engineering.

---

## Tech Stack

### Languages
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

### Backend & Architecture
![REST API](https://img.shields.io/badge/REST_API-0A0A0A?style=for-the-badge)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=for-the-badge&logo=grpc&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=for-the-badge&logo=socketdotio&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Microservices](https://img.shields.io/badge/Microservices-4A5568?style=for-the-badge)
![Event-Driven](https://img.shields.io/badge/Event--Driven-6B46C1?style=for-the-badge)

### Databases & Messaging
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)

### Frameworks & Libraries
![Gin](https://img.shields.io/badge/Gin-008ECF?style=for-the-badge&logo=gin&logoColor=white)
![chi](https://img.shields.io/badge/chi-2F855A?style=for-the-badge)
![pgx](https://img.shields.io/badge/pgx-336791?style=for-the-badge)
![sqlc](https://img.shields.io/badge/sqlc-1A2C4B?style=for-the-badge)
![GORM](https://img.shields.io/badge/GORM-1A2C4B?style=for-the-badge)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Svelte](https://img.shields.io/badge/Svelte-FF3E00?style=for-the-badge&logo=svelte&logoColor=white)

### Tools & Observability
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger/OpenAPI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)

---

## Projects

### House VPN — subscription & payments platform
**Solo project, running in production.** Six Go microservices serving live users with card and cryptocurrency payments.

- Took the product from zero to production alone: Telegram gateway, subscriptions, card billing, crypto billing, node orchestrator and node agent — **100+ users, 150+ payments processed**
- Payment workflow orchestration: recurring charges, grace periods, automatic refunds and retry schedules as state machines driven by background workers using `FOR UPDATE SKIP LOCKED` — **no double charge in 3 months of operation**
- Two payment providers (YooKassa cards, CryptoBot USDT/TON/BTC/ETH) with **webhook deduplication by SHA-256 body fingerprint**, amount reconciliation and idempotent settlement
- **At-least-once delivery** across services over Kafka (8 topics + DLT): transactional **outbox/inbox** on PostgreSQL, exponential retry, per-command idempotency — zero lost or twice-applied events
- **Database per service**: the orchestrator rebuilds user access from events instead of reading other services' databases
- Node allocation with weighted least-load, sticky assignment and heartbeat health checks; **self-healing reconciler** on a Postgres advisory lock restores access within 10 minutes of a node failure
- Node agent driving **Xray over gRPC** (heartbeat, traffic reports, offline command buffer); found and fixed a production bug where the agent hung forever after losing Kafka connectivity
- **25+ Prometheus metrics** (consumer lag, outbox depth, light/heavy aggregates on separate intervals) and Grafana dashboards

**Stack:** `Go` `PostgreSQL` `Kafka` `Redis` `gRPC` `Docker` `Prometheus` `Grafana` `Xray/VLESS`

---

### LarHome — field report analytics service
**Contract work for Lartech.** Turns a noisy engineering chat into structured, deduplicated, actionable alerts.

- Ingests field-test reports from a Telegram channel across **9 cities**, filters noise, classifies issues into **11 categories**, deduplicates them, and sends critical alerts plus a daily digest
- **Two-stage classifier**: deterministic rules first, LLM fallback second — strict JSON Schema output, prompt caching and a backup model; invalid responses route to manual review instead of being dropped
- **Cost as a first-class metric**: tokens (including cached), USD spend and latency per call exported to Prometheus
- Event deduplication by composite SHA-256 key with 6–24h windows depending on severity; delivery through an outbox with exponential backoff
- **19-table PostgreSQL schema** with typed `sqlc` queries; 13-panel Grafana dashboard on a read-only Postgres role

**Stack:** `Go` `PostgreSQL` `sqlc` `chi` `LLM API` `Prometheus` `Grafana` `Docker`

---

### Unified AI Workspace — full-stack AI application
Multimodal workspace unifying eight scenarios in a single chat interface.

- Extended an open-source chat UI into one workspace: text chat, voice workflows, image generation, image understanding, file Q&A, web search, URL parsing and presentation generation
- **Automatic capability routing** picks the right model or tool per request, with manual override
- File ingestion, retrieval and **multimodal RAG** for document-based Q&A; long-term memory for consistent multi-turn conversations
- Integration layer split into **application / domain / infrastructure** tiers; one-command local deployment with Docker Compose

**Stack:** `Python` `FastAPI` `TypeScript` `Svelte` `Docker` `RAG` `VLM` `ASR`

---

### Amber Messenger — team backend project (5 people)
Backend for a messenger with phone-based authentication, personal and group chats, and real-time delivery.

- Designed API specifications for authentication, users, chats and messages; documented with **Swagger/OpenAPI**
- **REST + WebSocket** delivery with `message`, `typing`, `read_receipt` and `history` events
- 5-entity schema with **cursor-based pagination**, membership checks and read-status handling
- Redis for SMS codes, caching and presence tracking

**Stack:** `Go` `PostgreSQL` `Redis` `WebSocket` `Docker` `JWT` `Swagger`

---

<details>
<summary><b>Earlier projects</b></summary>

### Cloud Storage Service
Backend service for secure file storage and user access control — JWT auth, upload and storage logic, middleware-protected routes, PostgreSQL schema and indexes, HTTPS/TLS.
**Stack:** `Go` `PostgreSQL` `Gin` `pgx` `JWT` `bcrypt` `TLS`

### University Assistant Bot
Assistant for fast access to university schedules and reference data — external schedule API integration, role-based flows for students, teachers and applicants, subscription-based daily notifications, modular `handlers → services → repositories` structure.
**Stack:** `Go` `PostgreSQL` `Docker` `REST` `MAX API`

### Notification Service
Asynchronous notification processing — Kafka consumer, channel routing by event type and recipient, delivery history and statuses in PostgreSQL.
**Stack:** `Go` `Kafka` `PostgreSQL` `Gin`

</details>

---

## Competitive Programming

- **Finalist**, MTS True Tech Champ 2025 — national algorithmic programming championship
- **Top 100**, Yandex Algorithm Training 8.0
- **16th place**, Digital Marathon 2026
- Qualified at Yandex Cup
- Codeforces rating **1600**

---

## Education

**Saint Petersburg State University of Aerospace Instrumentation (SUAI)**
**Applied Informatics**, BSc — expected 2027
**GPA:** 4.89 / 5.0

---

## Focus Areas

Go backend development · API design and backend architecture · Microservices and event-driven systems · Distributed systems reliability (idempotency, exactly-once effects, transactional outbox) · Payment and subscription flows · Observability and production operations

---

## Contact

- **Email:** [zorinmick5@gmail.com](mailto:zorinmick5@gmail.com)
- **Telegram:** [@wlcm666z](https://t.me/wlcm666z)
- **GitHub:** [WlcM111](https://github.com/WlcM111)
- **Codeforces:** [Wlcm666](https://codeforces.com/profile/Wlcm666)
- **LeetCode:** [wlcm](https://leetcode.com/u/wlcm/)
