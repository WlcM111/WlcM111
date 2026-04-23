**Go Backend Developer**

Backend developer focused on **Go, APIs, microservices, and real-time systems**.
I am a **3rd-year Applied Informatics student at SUAI** with **1.5+ years of backend development experience** across educational, pet, and team projects. My core interests are **backend architecture, storage-related services, event-driven systems, and infrastructure-oriented development**.

---

## Tech Stack

### Languages
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)

### Backend & Architecture
![REST API](https://img.shields.io/badge/REST_API-0A0A0A?style=for-the-badge)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=for-the-badge&logo=grpc&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=for-the-badge&logo=socketdotio&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Microservices](https://img.shields.io/badge/Microservices-4A5568?style=for-the-badge)

### Databases & Messaging
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)

### Frameworks & Libraries
![Gin](https://img.shields.io/badge/Gin-008ECF?style=for-the-badge&logo=gin&logoColor=white)
![pgx](https://img.shields.io/badge/pgx-336791?style=for-the-badge)
![GORM](https://img.shields.io/badge/GORM-1A2C4B?style=for-the-badge)
![gorilla/mux](https://img.shields.io/badge/gorilla%2Fmux-2F855A?style=for-the-badge)
![gorilla/websocket](https://img.shields.io/badge/gorilla%2Fwebsocket-2D3748?style=for-the-badge)
![golang-jwt](https://img.shields.io/badge/golang--jwt-111827?style=for-the-badge)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

### Tools
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger/OpenAPI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)

---

## Projects:

### Amber Messenger
Full-featured backend for a messenger with phone-based authentication, personal and group chats, and real-time communication.

- Designed API specifications for authentication, users, chats, and messages
- Implemented backend logic in Go with **JWT authentication**
- Built **REST + WebSocket** communication for real-time messaging
- Added events such as `message`, `typing`, `read_receipt`, and `history`
- Implemented **cursor-based pagination**, membership checks, and read-status handling
- Used **Redis** for SMS codes, caching, and presence tracking
- Documented endpoints with **Swagger / OpenAPI**
- Configured the local environment with **Docker Compose**

**Stack:** `Go` `PostgreSQL` `Redis` `WebSocket` `Docker` `JWT` `Swagger`

### Cloud Storage Service
Backend service for secure file storage and user access control.

- Implemented user registration and authentication with **JWT**
- Built file upload and storage logic
- Added route protection via middleware
- Designed the **PostgreSQL schema and indexes**
- Configured **HTTPS / TLS** for secure access
- Used **pgx / pgxpool** for database access and **YAML** for configuration

**Stack:** `Go` `PostgreSQL` `Gin` `pgx` `JWT` `bcrypt` `YAML` `TLS`

### University Assistant Bot
Bot assistant for fast access to university information such as schedules, contacts, and reference data.

- Integrated an external schedule API
- Added role-based user flows for students, teachers, and applicants
- Implemented subscription-based daily schedule notifications
- Stored profiles, roles, selected groups, and subscriptions in the database
- Used a modular backend structure: `handlers -> services -> repositories`
- Containerized the project with Docker

**Stack:** `Go` `PostgreSQL` `Docker` `REST` `MAX API`

### Notification Service
Asynchronous service for processing and delivering notifications.

- Consumed events from **Kafka**
- Processed notifications asynchronously in Go
- Routed messages by channel depending on the event type and recipient
- Stored delivery history and statuses in **PostgreSQL**
- Built API endpoints with **Gin**

**Stack:** `Go` `Kafka` `PostgreSQL` `Gin`

# Unified AI Workspace

OpenWebUI-based multimodal AI workspace that unifies text chat, voice workflows, image generation, image understanding, file Q&A, web search, URL parsing, long-term memory, and presentation generation in a single chat interface.

- Implemented automatic capability routing to choose the right model or tool for each user request
- Added manual model selection so users can override routing when needed
- Built long-term memory and context reuse for more consistent multi-turn conversations
- Integrated file ingestion, retrieval, and multimodal RAG for document-based Q&A scenarios
- Added voice workflows with audio transcription and follow-up chat over transcribed content
- Implemented image understanding and image generation flows directly inside the chat UX
- Integrated web search and URL parsing so external information can be used without leaving the workspace
- Added artifact-based outputs for generated images, research results, and presentation workflows
- Extended OpenWebUI with a dedicated MWS layer using a cleaner application / domain / infrastructure structure
- Configured Docker and Docker Compose for one-command local deployment and easier demo setup

**Stack:** Python `FastAPI` `TypeScript` `Svelte` `OpenWebUI` `Docker` `Docker Compose` `SQLite` `MWS GPT API` `RAG` `VLM` `ASR`

---

## Education

**Saint Petersburg State University of Aerospace Instrumentation (SUAI)**  
**Applied Informatics**, 3rd year  
**GPA:** 4.89

---

## Professional Focus

- Go backend development
- API design and backend architecture
- Microservices and modular services
- Event-driven systems
- Real-time communication
- Storage-related backend systems
- Infrastructure-oriented engineering

---

## Contact

- **Email:** [zorinmick5@gmail.com](mailto:zorinmick5@gmail.com)
- **Telegram:** [@wlcm666z](https://t.me/wlcm666z)
- **GitHub:** [WlcM111](https://github.com/WlcM111)
- **LeetCode:** [wlcm](https://leetcode.com/u/wlcm/)
- **CodeForces:** [Wlcm666](https://codeforces.com/profile/Wlcm666)
