# Interview Prep – Concise Answer Templates

> **Note:** These are templates. Replace the sample technologies, years, metrics, and stories with your actual experience before using them.

---

## 1. Day-to-Day Tech Stack

**Question:**  
Walk me through the tech stack you work with day-to-day. What languages, frameworks, and databases do you use — and for what purpose? How long have you worked with each, and where would you rate your depth? Have you migrated from one stack to another? What drove that decision?

**Short Answer:**

**Day-to-Day Stack:**  
TypeScript, React (Frontend), Node.js/Express (Backend), PostgreSQL (Database).

| Technology | Purpose | Experience | Depth |
|---|---|---|---|
| TypeScript / JavaScript | Core language for all development | 3 years | Expert |
| React | Building interactive user interfaces | 3 years | Proficient |
| Node.js / Express | Building scalable REST APIs | 3 years | Proficient |
| PostgreSQL & Redis | Relational data storage and caching | 2.5 years | Proficient |

**Stack Migration:**  
Migrated a major legacy service from plain JavaScript (Node.js) to TypeScript.

**Driver for Decision:**  
Better type safety, fewer runtime errors, and improved code maintainability as the engineering team scaled.

> **Note:** Update the technologies, years of experience, and migration story to reflect your actual background.

---

## 2. Most Complex Backend or Frontend Problem Solved

**Question:**  
Describe the most complex backend or frontend problem you’ve solved — walk me through it. What was the business context and why did it matter?

**Short Answer:**

**Problem & Business Context:**  
A critical real-time reporting API was timing out during peak end-of-month usage. Enterprise clients relied on these reports for billing, and failures flooded support with tickets and risked customer churn.

**The Solution:**  
Decoupled heavy data aggregation from the main request thread. First, optimized slow PostgreSQL queries by adding composite indexes. Then introduced Redis to cache frequently accessed data and moved heavy report generation to an asynchronous background worker queue.

**The Result:**  
Reduced p99 latency from 15 seconds to under 200 ms, completely eliminated API timeouts, and stabilized the system for future scaling.

> **Note:** Adjust the problem, technologies, and metrics to reflect a real project.

---

## 3. Largest Scale System Worked On

**Question:**  
Tell me about the largest scale system you’ve worked on — give me the actual numbers. What was the peak load — RPS, DAUs, data volume, message throughput? What was your role — did you design it, inherit it, or scale it up? Where did the system start breaking as load grew, and what were the early warning signs? How did the architecture evolve — what did v1 look like vs. where it is now? What was the most surprising thing that failed at scale that you didn’t anticipate?

**Short Answer:**

**Scale & Numbers:**  
The largest system I scaled handled peak loads of ~5,000 RPS and 150,000 DAUs. We processed around 10k messages/second, with a primary database volume of roughly 2 TB.

**My Role:**  
I inherited the v1 system and was responsible for designing and executing the scale-up strategy to handle a 3x increase in traffic over six months.

**Breaking Points & Early Warnings:**  
The system first started breaking at the database layer. Early warning signs were database CPU utilization frequently spiking over 90% during peak hours and application-side connection pool exhaustion, which led to intermittent 502 errors.

**Architecture Evolution:**

- **v1:** A monolithic Node.js application directly querying a single primary PostgreSQL instance.
- **v2 (Scaled):** Routed read-heavy queries to dedicated read replicas, introduced Redis to cache session and hot-path configuration data, and decoupled heavy write operations by pushing them to an asynchronous background worker queue (RabbitMQ/Kafka).

**Surprising Failure:**  
The most unanticipated failure at scale was our logging infrastructure. As traffic surged, the massive volume of raw application logs choked our sidecar logging agent. It consumed all available node memory, causing the application containers to OOM (Out of Memory) crash before the core application itself actually reached its performance limits.

> **Note:** Adjust the RPS, DAU numbers, stack details, and surprising failure to accurately reflect your actual background.

---

## 4. Most Impactful Performance Optimisation Shipped

**Question:**  
Walk me through the most impactful performance optimisation you’ve shipped. How did you first identify the problem — was it user-reported, alerting, or proactive profiling? What tools did you use to diagnose — flamegraphs, query plans, distributed traces? What did you try that didn’t work, and why did it fail? What was the measurable before/after — latency p50/p99, throughput, infra cost?

**Short Answer:**

**Identification & Tools:**  
Automated alerting flagged high p99 latency on a critical data-export API. I diagnosed the bottleneck using Datadog distributed traces to pinpoint the slow service, followed by PostgreSQL `EXPLAIN ANALYZE` (query plans) to isolate the specific inefficient queries.

**Failed Attempt:**  
I initially tried implementing application-level Redis caching. This failed because the data was highly user-specific and dynamic, resulting in a low cache hit rate and unnecessary memory bloat without solving the underlying database strain.

**Solution & Measurable Impact:**  
The root cause was a severe N+1 query issue in the ORM. I rewrote the data fetching logic to use optimized SQL JOINs and batching. As a result:

- p99 latency dropped from **3.5 seconds to 150 ms**
- throughput increased by **4x**
- database CPU load decreased by **40%**
- allowed us to downscale our RDS instance and save on infrastructure costs

> **Note:** Adjust the monitoring tools, failed attempt, and metrics to match a real optimization you shipped.

---

## 5. Services or Components Personally Owned

**Question:**  
What services or components do you personally own — describe your domain. What does each service do, what are its SLAs, and who are its consumers? How do your services communicate — REST, gRPC, event-driven, message queues? Why that choice?

**Short Answer:**

**Domain & Ownership:**  
I own the **Reporting & Notification Domain**, managing two core services:

1. **Reporting Service** — aggregates and exports analytics/billing data.
2. **Notification Dispatcher** — handles email, webhook, and in-app alerts.

**Services, Consumers & SLAs:**

| Service | Consumers | SLA |
|---|---|---|
| **Reporting Service** | Web/mobile frontend clients and internal billing/finance systems | 99.9% availability; p95 latency < 300 ms for dashboard queries; asynchronous jobs under 3 minutes |
| **Notification Dispatcher** | Upstream business services (Auth, Billing, Order Management) | 99.95% delivery guarantee within 5 seconds for critical alerts (OTP, billing triggers) |

**Communication Architecture & Rationale:**

- **REST APIs:** Used for synchronous client-to-service communication (e.g., frontend fetching reporting dashboards) due to universal tooling and easy HTTP caching.
- **Message Queues / Event-Driven (Kafka / RabbitMQ):** Used for inter-service communication and trigger handling (e.g., billing event triggers a report, or an alert triggers the notification dispatcher).

**Why this choice:**  
Asynchronous event queues decouple producer services from downstream processing spikes, guarantee delivery via retries/dead-letter queues (DLQs), and prevent slow external dependencies (like third-party email/SMS gateways) from blocking critical user-facing requests.

---

## Final Reminder

Customize every section with **your real experience**:

- Actual languages, frameworks, databases
- Real years and depth ratings
- Real migration story
- Real problem, scale numbers, metrics, and failures
- Real services, SLAs, consumers, and communication patterns
