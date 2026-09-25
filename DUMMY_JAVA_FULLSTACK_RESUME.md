# Rohan Sharma
**Senior Java Full Stack Developer**  
Bengaluru, India | +91 98765 43210 | rohan.sharma.dev@example.com  
[LinkedIn: linkedin.com/in/rohan-sharma-dummy](https://linkedin.com/in/rohan-sharma-dummy) | [GitHub: github.com/rohansharma-dev](https://github.com/rohansharma-dev) | [Portfolio: rohansharma.dev](https://rohansharma.dev)

---

## Professional Summary
Results-driven **Java Full Stack Developer** with **5+ years of experience** designing, developing, and deploying enterprise-grade distributed web applications and cloud-native microservices. Proficient in **Java 17/21, Spring Boot 3, Hibernate/JPA, React.js, TypeScript, PostgreSQL, Docker, and Kubernetes**. Proven expertise in workflow orchestration systems, Directed Acyclic Graph (DAG) dependency engines, real-time Kanban platforms, and event-driven architectures. Adept at building high-throughput RESTful APIs, enforcing strict transactional integrity, and implementing responsive, accessible web frontends.

---

## Technical Skills

| Domain | Technologies & Tools |
| :--- | :--- |
| **Languages** | Java (8/11/17/21), JavaScript (ES6+), TypeScript, SQL, HTML5, CSS3/Tailwind |
| **Backend Frameworks** | Spring Boot 3.x, Spring MVC, Spring Data JPA, Hibernate ORM, Spring Security (OAuth2, JWT) |
| **Frontend Technologies** | React.js (18+), Next.js, Redux Toolkit, Zustand, Axios, Vite, HTML5 Drag & Drop API |
| **Databases & Caching** | PostgreSQL, MySQL, Redis (Caching & Pub/Sub), Flyway DB Migrations, H2 Database |
| **Architecture & Patterns** | Microservices, RESTful APIs, WebSocket (STOMP), DAG Workflow Engines, Event-Driven Architecture, CQRS |
| **Cloud & DevOps** | Docker, Docker Compose, Kubernetes, AWS (EC2, S3, RDS), GitHub Actions, CI/CD Pipelines |
| **Testing & Quality** | JUnit 5, Mockito, AssertJ, Testcontainers, Postman, Jest, React Testing Library, SonarQube |
| **Tools & Methodologies** | Git, Maven, Gradle, Agile/Scrum, JIRA, OpenAPI/Swagger |

---

## Professional Experience

### Senior Full Stack Developer | ApexCloud Software Solutions, Bengaluru
*June 2022 – Present*
* Architected and implemented scalable microservices using **Java 17**, **Spring Boot 3**, and **PostgreSQL**, serving over 250,000 active daily users with 99.95% uptime.
* Spearheaded the development of **TaskFlow Pro**, a dependency-aware workflow management system featuring an interactive React/TypeScript Kanban board backed by a custom Java DAG scheduling engine.
* Designed and optimized graph traversal algorithms (Kahn’s algorithm & DFS reachability) to detect circular dependencies and compute dynamic Blocked/Ready task states in sub-10ms latency.
* Engineered bidirectional real-time board updates using **WebSocket (STOMP)** and **Redis Pub/Sub**, cutting client polling overhead by 75%.
* Implemented strict database concurrency controls utilizing JPA `@Version` optimistic locking to eliminate race conditions during simultaneous drag-and-drop operations.
* Authored end-to-end integration test suites utilizing **JUnit 5**, **Mockito**, and **Testcontainers**, elevating test coverage from 62% to 88%.

### Full Stack Java Developer | InnoTech Global Systems, Pune
*July 2020 – May 2022*
* Developed core RESTful backend APIs using Spring Boot, Spring Security, and JPA, interfacing with PostgreSQL and Redis.
* Built responsive, mobile-first frontend dashboards using **React.js**, **Redux Toolkit**, and **Tailwind CSS**.
* Automated database schema versioning and zero-downtime database migrations with **Flyway**.
* Configured automated CI/CD pipelines via **GitHub Actions** for containerized builds, static code analysis (SonarQube), and staging deployments on AWS ECS.
* Reduced critical API response latency by 35% through query optimization, index tuning, and Redis caching.

---

## Key Projects

### 1. TaskFlow Pro — Dependency-Aware Workflow & DAG Scheduling Kanban Engine
*Tech Stack: Java 21, Spring Boot 3, React 18, TypeScript, PostgreSQL, Tailwind CSS, Docker*
* Built an advanced project management board with 4 workflow stages (Backlog, In Progress, Review, Done) and strict prerequisite enforcement.
* Implemented graph-based dependency resolution preventing circular references (e.g., A → B → C → A) and handling complex diamond dependencies (A → B, A → C → D).
* Integrated automatic schedule propagation: shifting upstream milestone dates automatically cascades downstream without compounding delay errors.
* Developed full test coverage including unit tests, graph cycle validation, rollback regression testing, and concurrency integration tests.

### 2. Enterprise Role-Based Access Control (RBAC) & Multi-Tenant Service
*Tech Stack: Java 17, Spring Boot, Spring Security, JWT, Redis, PostgreSQL*
* Designed a multi-tenant authentication and authorization microservice using stateless JWT tokens and Redis session revocation.
* Implemented method-level security (`@PreAuthorize`) and tenant-isolated database schemas with automated Flyway migration scripts.

---

## Education
**Bachelor of Technology (B.Tech) in Computer Science & Engineering**  
*National Institute of Technology (NIT)* | 2016 – 2020  
* CGPA: 8.7 / 10.0

---

## Certifications & Achievements
* **Oracle Certified Professional**: Java SE 17 Developer (1Z0-829)
* **AWS Certified Developer – Associate** (Amazon Web Services)
* **Hackathon Finalist**: Contata Systems Cloud Innovation Sprint 2024
