# Kanban Board (TaskFlow Pro) — Setup Guide

This guide provides instructions to build, configure, and launch the **TaskFlow Pro Kanban Board** application (Java Spring Boot Backend + React Frontend + PostgreSQL Database) for testing and evaluation.

For the in-depth system architecture, database schema, and DAG mechanics, see [KANBAN_SETUP_AND_DESIGN.md](file:///c:/Users/utkarshg/CS-Hackathon/KANBAN_SETUP_AND_DESIGN.md).  
For the complete test suite and failure cases, see [KANBAN_TEST_SUITE_AND_FAILURE_CASES.md](file:///c:/Users/utkarshg/CS-Hackathon/KANBAN_TEST_SUITE_AND_FAILURE_CASES.md).

---

## 1. Quick Start via Docker Compose (Recommended)

The fastest way to spin up the entire environment (PostgreSQL, Spring Boot backend, and React frontend):

```bash
cd Hackthaon_BE
docker compose up -d --build
```

Services will be accessible at:
* **Frontend Kanban UI:** `http://localhost:5173`
* **Backend REST API:** `http://localhost:8080`
* **Swagger API Docs:** `http://localhost:8080/swagger-ui.html`
* **Health Check:** `http://localhost:8080/actuator/health`

To stop all containers:
```bash
docker compose down
```

---

## 2. Local Manual Setup

### 2.1 Prerequisites
* **JDK 17 or 21+** (`java -version`)
* **Maven 3.8+** (`mvn -version`)
* **Node.js 18+ & npm 9+** (`node -version`, `npm -version`)
* **PostgreSQL 14+** (running on port 5432)

---

### 2.2 Database Initialization
```bash
psql -U postgres -c "CREATE DATABASE taskflow_db;"
psql -U postgres -c "CREATE USER taskflow_user WITH PASSWORD 'taskflow_pass';"
psql -U postgres -c "GRANT ALL PRIVILEGES ON DATABASE taskflow_db TO taskflow_user;"
```

Flyway will automatically execute database migrations on backend startup.

---

### 2.3 Backend Setup (Spring Boot)

1. Navigate to the backend directory:
   ```bash
   cd Hackthaon_BE
   ```

2. Configure environment variables in `.env` (or pass via terminal):
   ```env
   SERVER_PORT=8080
   SPRING_DATASOURCE_URL=jdbc:postgresql://localhost:5432/taskflow_db
   SPRING_DATASOURCE_USERNAME=taskflow_user
   SPRING_DATASOURCE_PASSWORD=taskflow_pass
   ```

3. Build and launch:
   ```bash
   # Windows PowerShell / CMD
   .\mvnw.cmd spring-boot:run

   # Linux / macOS
   ./mvnw spring-boot:run
   ```

---

### 2.4 Frontend Setup (React + Vite)

1. Navigate to the frontend directory:
   ```bash
   cd hackathon_Frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start development server:
   ```bash
   npm run dev
   ```
4. Access the web app at `http://localhost:5173`.

---

## 3. Seeded Sample Tasks (Ready for Testing)

Upon launch, 10 sample tasks are available to test the board:
* **TASK-01: Database Schema & Migrations** (`DONE`)
* **TASK-02: Authentication & JWT** (`DONE`, depends on 01)
* **TASK-03: Cloud Infrastructure** (`DONE`, depends on 01)
* **TASK-04: Task Engine API** (`IN_PROGRESS`, depends on 02)
* **TASK-05: GraphQL & Cache** (`IN_PROGRESS`, depends on 03)
* **TASK-06: E2E Integration Suite** (`BACKLOG` - **BLOCKED**, depends on 04 & 05)
* **TASK-07: Production Deployment** (`BACKLOG` - **BLOCKED**, depends on 06)
* **TASK-08: UI Design System** (`DONE`)
* **TASK-09: React Kanban Board UI** (`IN_PROGRESS`, depends on 08)
* **TASK-10: User Documentation** (`BACKLOG` - **READY**, independent)

---

## 4. Quick API Smoke Test Commands

```bash
# 1. Check health
curl http://localhost:8080/actuator/health

# 2. Get all boards & tasks
curl http://localhost:8080/api/boards

# 3. Test cycle detection (attempting invalid reverse edge)
curl -X POST http://localhost:8080/api/tasks/dependencies \
  -H "Content-Type: application/json" \
  -d '{"prerequisiteTaskId":"TASK_02_ID","dependentTaskId":"TASK_01_ID"}'
# Response: HTTP 400 Bad Request ("Circular dependency detected: TASK-01 -> TASK-02 -> TASK-01")
```
