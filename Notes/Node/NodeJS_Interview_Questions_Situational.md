# Node.js Backend Interview Questions — Situational / Real-World Scenarios

A consolidated, deduplicated collection of **situational and real-time scenario-based Node.js interview questions** — production incidents, scaling decisions, debugging, and architecture trade-offs — organized section-wise.

**Total unique questions: 37**

## Table of Contents

- [Core Fundamentals & Runtime (V8, libuv, process, modules)](#core-fundamentals-runtime-v8-libuv-process-modules) (7)
  - [1. After deploying a new version, one of your services is causing cascading failures. What do you do?](#1-after-deploying-a-new-version-one-of-your-services-is-causing-cascading-failures-what-do-you-do)
  - [2. How do you handle a child process crash in the parent?](#2-how-do-you-handle-a-child-process-crash-in-the-parent)
  - [3. How do you handle large amounts of data in Node.js?](#3-how-do-you-handle-large-amounts-of-data-in-nodejs)
  - [4. How do you handle long-running background jobs in a Node.js API?](#4-how-do-you-handle-long-running-background-jobs-in-a-nodejs-api)
  - [5. How do you handle versioning in a microservices setup?](#5-how-do-you-handle-versioning-in-a-microservices-setup)
  - [6. What is `npm audit`? How do you handle vulnerable dependencies?](#6-what-is-npm-audit-how-do-you-handle-vulnerable-dependencies)
  - [7. Your JWT tokens are somehow being forged in production. What is your incident response process?](#7-your-jwt-tokens-are-somehow-being-forged-in-production-what-is-your-incident-response-process)
- [Event Loop, Concurrency & Async Patterns](#event-loop-concurrency-async-patterns) (3)
  - [8. How do you handle errors in `async/await`? What is the try/catch pattern?](#8-how-do-you-handle-errors-in-asyncawait-what-is-the-trycatch-pattern)
  - [9. How do you handle errors in synchronous vs asynchronous code?](#9-how-do-you-handle-errors-in-synchronous-vs-asynchronous-code)
  - [10. Your Node.js API's response times are spiking to 5 seconds under moderate load. How do you diagnose?](#10-your-nodejs-apis-response-times-are-spiking-to-5-seconds-under-moderate-load-how-do-you-diagnose)
- [Streams & Buffers](#streams-buffers) (2)
  - [11. How do you handle errors in a piped stream chain?](#11-how-do-you-handle-errors-in-a-piped-stream-chain)
  - [12. What is backpressure in Node.js streams? How do you handle it?](#12-what-is-backpressure-in-nodejs-streams-how-do-you-handle-it)
- [Express.js, Middleware & REST API Design](#expressjs-middleware-rest-api-design) (7)
  - [13. How do you handle 404 errors in Express?](#13-how-do-you-handle-404-errors-in-express)
  - [14. How do you handle async errors in Express without try/catch on every route?](#14-how-do-you-handle-async-errors-in-express-without-trycatch-on-every-route)
  - [15. How do you handle CORS in a REST API?](#15-how-do-you-handle-cors-in-a-rest-api)
  - [16. How do you handle file uploads in Express using Multer?](#16-how-do-you-handle-file-uploads-in-express-using-multer)
  - [17. How do you handle partial responses or field selection in a REST API?](#17-how-do-you-handle-partial-responses-or-field-selection-in-a-rest-api)
  - [18. How do you handle routing in Express.js?](#18-how-do-you-handle-routing-in-expressjs)
  - [19. How would you structure a large Express application?](#19-how-would-you-structure-a-large-express-application)
- [Authentication & Authorization](#authentication-authorization) (1)
  - [20. How do you handle inter-service authentication?](#20-how-do-you-handle-inter-service-authentication)
- [Databases — MongoDB & Mongoose](#databases-mongodb-mongoose) (1)
  - [21. How do you handle connection pooling in Mongoose?](#21-how-do-you-handle-connection-pooling-in-mongoose)
- [Databases — SQL, PostgreSQL & ORMs](#databases-sql-postgresql-orms) (3)
  - [22. How do you handle database migrations in Prisma vs Sequelize?](#22-how-do-you-handle-database-migrations-in-prisma-vs-sequelize)
  - [23. What is N+1 query problem? How do you fix it?](#23-what-is-n1-query-problem-how-do-you-fix-it)
  - [24. Your PostgreSQL queries that used to be fast are now taking 3 seconds. How do you debug?](#24-your-postgresql-queries-that-used-to-be-fast-are-now-taking-3-seconds-how-do-you-debug)
- [Caching & Redis](#caching-redis) (1)
  - [25. A Redis `KEYS *` command is running in production and causing latency spikes. How do you fix it and prevent recurrence?](#25-a-redis-keys-command-is-running-in-production-and-causing-latency-spikes-how-do-you-fix-it-and-prevent-recurrence)
- [Error Handling & Logging](#error-handling-logging) (1)
  - [26. How do you handle different environments (development, staging, production) in Node.js applications?](#26-how-do-you-handle-different-environments-development-staging-production-in-nodejs-applications)
- [WebSockets & Real-Time Communication](#websockets-real-time-communication) (2)
  - [27. How do you handle client disconnection in SSE?](#27-how-do-you-handle-client-disconnection-in-sse)
  - [28. How do you handle reconnection logic in WebSocket clients?](#28-how-do-you-handle-reconnection-logic-in-websocket-clients)
- [Message Queues (RabbitMQ, Kafka, Bull)](#message-queues-rabbitmq-kafka-bull) (2)
  - [29. How do you handle failed jobs in BullMQ?](#29-how-do-you-handle-failed-jobs-in-bullmq)
  - [30. Your message queue is growing without consumers processing messages. What are the possible causes?](#30-your-message-queue-is-growing-without-consumers-processing-messages-what-are-the-possible-causes)
- [DevOps — Docker, CI/CD & Deployment](#devops-docker-cicd-deployment) (2)
  - [31. A deployment caused one pod to restart in a loop (CrashLoopBackOff). How do you debug?](#31-a-deployment-caused-one-pod-to-restart-in-a-loop-crashloopbackoff-how-do-you-debug)
  - [32. How do you handle environment variables in Docker containers?](#32-how-do-you-handle-environment-variables-in-docker-containers)
- [TypeScript with Node.js](#typescript-with-nodejs) (1)
  - [33. How do you handle JSON imports in TypeScript?](#33-how-do-you-handle-json-imports-in-typescript)
- [GraphQL with Node.js](#graphql-with-nodejs) (1)
  - [34. How do you handle file uploads in GraphQL?](#34-how-do-you-handle-file-uploads-in-graphql)
- [General / Miscellaneous Node.js Concepts](#general-miscellaneous-nodejs-concepts) (3)
  - [35. How do you handle cross-platform issues in Node.js?](#35-how-do-you-handle-cross-platform-issues-in-nodejs)
  - [36. How do you handle distributed transactions in microservices?](#36-how-do-you-handle-distributed-transactions-in-microservices)
  - [37. How would you design a file processing service (e.g., image resizing)?](#37-how-would-you-design-a-file-processing-service-eg-image-resizing)

---

## Core Fundamentals & Runtime (V8, libuv, process, modules)

### 1. After deploying a new version, one of your services is causing cascading failures. What do you do?

1. Immediately rollback the deployment if possible.
2. If not, scale up healthy instances, apply circuit breakers.
3. Check logs for errors (connection refused, timeouts).
4. Verify dependencies (DB, Redis) not overloaded.
5. Check if the new version introduced a bug causing excessive retries or blocked event loop.
6. Implement health checks to prevent spreading.
7. Post-incident: improve testing, canary releases.

[↑ Back to top](#table-of-contents)

### 2. How do you handle a child process crash in the parent?

Listen for the `'exit'` event on the child process; check the exit code and signal. You may decide to restart the child or log the error. If the child is critical, implement a respawn logic.

[↑ Back to top](#table-of-contents)

### 3. How do you handle large amounts of data in Node.js?

Use streams to process data in chunks, preventing memory overload. For databases, use cursors or pagination. For file uploads, use `multer` with streaming. Avoid loading everything into memory; instead, pipeline data through transforms.

[↑ Back to top](#table-of-contents)

### 4. How do you handle long-running background jobs in a Node.js API?

Use job queues (BullMQ) to enqueue jobs. The API responds with a job ID and status endpoint. Workers process jobs asynchronously. Store job state in DB/Redis.

[↑ Back to top](#table-of-contents)

### 5. How do you handle versioning in a microservices setup?

- API versioning: URI or header versioning for external endpoints.
- Internal service versioning: contract testing, backward-compatible changes, or version in message schema. Use semantic versioning and feature toggles.

[↑ Back to top](#table-of-contents)

### 6. What is `npm audit`? How do you handle vulnerable dependencies?

`npm audit` checks for known vulnerabilities. Handle by updating the dependency if a fix is available, or applying patches/alternatives. Use `npm audit fix`. Integrate into CI to catch issues early.

[↑ Back to top](#table-of-contents)

### 7. Your JWT tokens are somehow being forged in production. What is your incident response process?

1. Rotate the signing secret/key immediately.
2. Invalidate all existing tokens if possible (blacklist).
3. Investigate if the secret was leaked (logs, source code).
4. Check if algorithm was set to `none` or weak key.
5. Review access logs for unauthorized access.
6. Force all users to re-authenticate.
7. Implement stronger key management (Vault, rotation).

[↑ Back to top](#table-of-contents)

## Event Loop, Concurrency & Async Patterns

### 8. How do you handle errors in `async/await`? What is the try/catch pattern?

Wrap await in try/catch:

```javascript
try {
const data = await fetchData();
} catch (err) {
// handle error
}
```

Alternatively, use `.catch()` on the promise or a wrapper function.

[↑ Back to top](#table-of-contents)

### 9. How do you handle errors in synchronous vs asynchronous code?

- Synchronous: try/catch blocks.
- Asynchronous callbacks: error-first callbacks; pass error as first arg.
- Promises: `.catch()` or try/catch with async/await.
- Express: pass to `next(err)`.

[↑ Back to top](#table-of-contents)

### 10. Your Node.js API's response times are spiking to 5 seconds under moderate load. How do you diagnose?

1. Check CPU/memory usage.
2. Profile the event loop lag.
3. Look for slow database queries (APM, DB logs).
4. Check external service latencies (circuit breaker).
5. Examine recent deployments.
6. Use `clinic doctor` or flamegraph to find blocking code.
7. Possibly connection pool exhaustion or GC pauses.
8. Scale horizontally while debugging.

**A Node.js service is consuming 4GB of RAM and growing. Walk through your memory leak investigation.**
1. Monitor heap usage over time.
2. Take heap snapshots at intervals and compare.
3. Identify objects with increasing counts (e.g., strings, buffers).
4. Look at retainers: find what references are keeping them alive.
5. Check for global caches without eviction, unclosed streams, event listeners.
6. Use `--inspect` and Chrome DevTools.
7. Simulate load in a controlled environment.

[↑ Back to top](#table-of-contents)

## Streams & Buffers

### 11. How do you handle errors in a piped stream chain?

Expected interview answer:

“Errors need to be handled carefully when working with streams because a failure in one stream can affect the entire data-processing operation.

When using `pipe()`, I can attach error listeners to the relevant streams and implement appropriate cleanup.

However, for a chain involving multiple streams, I generally prefer `pipeline()` because it propagates errors through a single callback or Promise and performs coordinated cleanup.

For example, if a file-reading stream fails while compressing a file, I want the application to report the error rather than incorrectly treating the operation as successful.”

Example:
```

const fs = require("node:fs");
const zlib = require("node:zlib");
const { pipeline } = require("node:stream");

pipeline(
fs.createReadStream("input.txt"),
zlib.createGzip(),
fs.createWriteStream("output.txt.gz"),
error => {
if (error) {
console.error("Stream error:", error);
return;
}

console.log("Operation completed successfully");
}
);
```

Remember: Prefer `pipeline()` for stream chains when you need coordinated error handling and cleanup.

[↑ Back to top](#table-of-contents)

### 12. What is backpressure in Node.js streams? How do you handle it?

Expected interview answer:

“Backpressure occurs when a data consumer cannot process incoming data as quickly as the producer generates it.

For example, a file-reading stream might produce data faster than a network connection can send it. If the application continues accumulating data without controlling the flow, memory usage can increase significantly.

Node.js streams handle this through buffering and backpressure mechanisms. When using `pipe()`, the readable stream is automatically paused and resumed as necessary.

When writing data manually, I check the return value of `writable.write()`. If it returns `false`, I wait for the writable stream's `drain` event before writing more data.

This allows the producer to respect the consumer's capacity.”

Example:
```

const canContinue = writable.write(chunk);

if (!canContinue) {
writable.once("drain", () => {
// Continue writing more data
});
}
```

Remember: When `write()` returns `false`, stop writing temporarily and wait for `drain`.

[↑ Back to top](#table-of-contents)

## Express.js, Middleware & REST API Design

### 13. How do you handle 404 errors in Express?

Expected interview answer:

“A 404 error means that the server could not find a matching resource or route for the request.

In Express, I handle unmatched requests by registering a catch-all middleware after the application's routes.

If none of the preceding routes sends a response, this middleware returns a 404 status code.

I would keep this separate from the general error handler because an unmatched route is not necessarily an application exception.”

Example:
```

app.use((req, res) => {
res.status(404).json({
error: "Route not found"
});
});
```

Remember: The 404 handler should come after all routes but before the final error handler.

[↑ Back to top](#table-of-contents)

### 14. How do you handle async errors in Express without try/catch on every route?

Use a wrapper function like `express-async-handler` or `asyncWrap`:

```javascript
const asyncHandler = (fn) => (req, res, next) => Promise.resolve(fn(req, res, next)).catch(next);
```

Then wrap route handlers: `app.get('/', asyncHandler(async (req, res) => { ... }))`.

[↑ Back to top](#table-of-contents)

### 15. How do you handle CORS in a REST API?

Expected interview answer:

“CORS controls whether browser-based applications from one origin are permitted to access resources from another origin.

In a REST API, I configure the appropriate allowed origins, HTTP methods, headers, and credential behavior.

For requests that require a preflight check, the browser sends an OPTIONS request to determine whether the actual request is permitted. The API must return suitable CORS headers in response.

In Express, I would commonly configure the `cors` middleware instead of manually managing every header.

I would make the policy restrictive enough for the application's requirements and remember that CORS does not replace authentication or authorization.”

Example:
```

const cors = require("cors");

app.use(cors({
origin: ["https://app.example.com"],
methods: ["GET", "POST", "PATCH", "DELETE"]
}));
```

Remember: Configure CORS deliberately and ensure browser requests receive the appropriate headers.

[↑ Back to top](#table-of-contents)

### 16. How do you handle file uploads in Express using Multer?

Expected interview answer:

“Multer is middleware that handles `multipart/form-data` requests, which are commonly used for file uploads.

It allows us to configure whether uploaded files are stored in memory or on disk and provides access to uploaded-file information through properties such as `req.file` or `req.files`.

For example, if a user uploads a profile image, I can configure a Multer middleware and attach it to the relevant upload route.

In production, I would also enforce file-size limits, validate allowed file types, generate safe filenames, and consider storing larger files in object storage rather than the application server's local disk.”

Example:
```

const multer = require("multer");

const upload = multer({
dest: "uploads/",
limits: {
fileSize: 5 * 1024 * 1024
}
});

app.post("/upload", upload.single("avatar"), (req, res) => {
res.json({
filename: req.file.filename
});
});
```

Remember: Multer parses multipart uploads; file-size limits and file validation are important security controls.

[↑ Back to top](#table-of-contents)

### 17. How do you handle partial responses or field selection in a REST API?

Expected interview answer:

“Partial responses allow clients to request only the fields they need, which can reduce response size and unnecessary data transfer.

For example, a client might request `/users?fields=id,name,email` instead of receiving every field associated with the user.

The API validates the requested fields and returns only the allowed fields.

I would implement field selection using an explicit allowlist so that clients cannot request sensitive internal fields.

This can improve efficiency, especially when resources contain large nested structures.”

Example:
```

GET /users?fields=id,name,email
```

Remember: Field selection reduces payload size, but the API must enforce which fields clients are allowed to access.

[↑ Back to top](#table-of-contents)

### 18. How do you handle routing in Express.js?

Define routes using methods like `app.get()`, `app.post()`, etc., with a path and a handler function. Example:

```js
app.get('/users/:id', (req, res) => {
const userId = req.params.id;
res.send(`User ${userId}`);
});

```

[↑ Back to top](#table-of-contents)

### 19. How would you structure a large Express application?

Expected interview answer:

“For a large Express application, I would separate the code into layers based on their responsibilities.

The routes directory would define API endpoints, controllers would handle HTTP request and response logic, services would contain business logic, and models or repositories would handle database access.

I would keep reusable middleware, configuration, and utility functions in separate directories.

For example, when creating a user, the route would call the controller, the controller would invoke the service, and the service would interact with the repository or database layer.

This structure improves maintainability, testing, and separation of concerns.”

Example structure:
```

src/
├── routes/
├── controllers/
├── services/
├── models/
├── repositories/
├── middleware/
├── config/
├── utils/
├── app.js
└── server.js
```

Remember: Separate routing, HTTP handling, business logic, and data access.

[↑ Back to top](#table-of-contents)

## Authentication & Authorization

### 20. How do you handle inter-service authentication?

Use JWT tokens issued by a central identity service. Services validate tokens using shared public key (asymmetric). Alternatively, use mutual TLS (mTLS) or API keys with service mesh.

[↑ Back to top](#table-of-contents)

## Databases — MongoDB & Mongoose

### 21. How do you handle connection pooling in Mongoose?

Mongoose manages connection pooling via the MongoDB driver's `poolSize` option (e.g., `mongoose.connect(uri, { maxPoolSize: 10 })`). Adjust based on expected concurrency.

[↑ Back to top](#table-of-contents)

## Databases — SQL, PostgreSQL & ORMs

### 22. How do you handle database migrations in Prisma vs Sequelize?

- Prisma Migrate: `npx prisma migrate dev` creates SQL migration files from schema changes.
- Sequelize: use `sequelize-cli` to create migration files manually or auto-generate.

[↑ Back to top](#table-of-contents)

### 23. What is N+1 query problem? How do you fix it?

The N+1 problem occurs when you fetch a list of entities and then for each entity run a separate query to fetch related data. Fix: use eager loading (JOINs or `include` in ORM) to fetch all needed data in one or few queries.

[↑ Back to top](#table-of-contents)

### 24. Your PostgreSQL queries that used to be fast are now taking 3 seconds. How do you debug?

1. Check query plan with `EXPLAIN ANALYZE`.
2. Look for missing indexes, sequential scans.
3. Check for table bloat, outdated statistics (`VACUUM ANALYZE`).
4. Verify hardware resource contention.
5. See if data volume has grown significantly.
6. Look for lock contention.
7. Enable slow query logging.

[↑ Back to top](#table-of-contents)

## Caching & Redis

### 25. A Redis `KEYS *` command is running in production and causing latency spikes. How do you fix it and prevent recurrence?

- Immediately kill the session running it if possible.
- Replace `KEYS` with `SCAN` in application code.
- Implement code reviews to catch dangerous commands.
- Rename dangerous commands in Redis config (`rename-command KEYS ""`).
- Monitor with Redis slowlog.

[↑ Back to top](#table-of-contents)

## Error Handling & Logging

### 26. How do you handle different environments (development, staging, production) in Node.js applications?

Use environment variables (e.g., `NODE_ENV`) to switch configurations. Set different database URLs, logging levels, and API endpoints based on the environment. Use configuration files (e.g., `config/development.json`) and load them conditionally. Tools like `dotenv` help manage local settings.

[↑ Back to top](#table-of-contents)

## WebSockets & Real-Time Communication

### 27. How do you handle client disconnection in SSE?

Listen for the `'close'` event on the request object to detect when the client disconnects, and clean up resources.

[↑ Back to top](#table-of-contents)

### 28. How do you handle reconnection logic in WebSocket clients?

`socket.io` has built-in reconnection with exponential backoff. For raw `ws`, implement a reconnection function that attempts to reconnect after a delay. Handle `close` event.

[↑ Back to top](#table-of-contents)

## Message Queues (RabbitMQ, Kafka, Bull)

### 29. How do you handle failed jobs in BullMQ?

Jobs that exceed retries are moved to the failed set. Monitor failed jobs via events, dashboard (Bull Board). You can manually retry or remove.

[↑ Back to top](#table-of-contents)

### 30. Your message queue is growing without consumers processing messages. What are the possible causes?

- Consumers crashed or not running.
- Consumers stuck in a deadlock or slow processing loop.
- Message format changed and consumers are failing to parse, causing retries and redeliveries.
- Network issues between consumers and queue.
- Queue bound to wrong exchange/routing.
Check consumer logs, queue state, and restart consumers.

[↑ Back to top](#table-of-contents)

## DevOps — Docker, CI/CD & Deployment

### 31. A deployment caused one pod to restart in a loop (CrashLoopBackOff). How do you debug?

1. Get pod logs: `kubectl logs <pod> --previous`.
2. Check exit code.
3. Look for uncaught exceptions, missing environment variables, configuration errors.
4. Verify health check probes (liveness/readiness) are correctly configured; maybe app isn't starting fast enough.
5. Check resource limits (OOMKilled).
6. Investigate if dependencies are reachable.
7. Rollback to previous version, then fix.

[↑ Back to top](#table-of-contents)

### 32. How do you handle environment variables in Docker containers?

Pass with `-e` flag, or use `env_file`, or in Docker Compose `environment` section. For secrets, use Docker secrets or external vaults, not hardcoded.

[↑ Back to top](#table-of-contents)

## TypeScript with Node.js

### 33. How do you handle JSON imports in TypeScript?

Enable `resolveJsonModule` in `tsconfig.json`. Then `import data from './data.json'` works, with types inferred.

[↑ Back to top](#table-of-contents)

## GraphQL with Node.js

### 34. How do you handle file uploads in GraphQL?

Use the GraphQL multipart request spec. Apollo Server supports file uploads via `graphql-upload` (or built-in in older versions). Define a scalar `Upload`, and handle the file stream in the resolver.

[↑ Back to top](#table-of-contents)

## General / Miscellaneous Node.js Concepts

### 35. How do you handle cross-platform issues in Node.js?

Use the `path` module for file paths. For line endings, be aware of differences (CRLF vs LF). Avoid shell commands that are OS‑specific; use Node.js APIs or libraries. For spawning processes, use cross‑platform command wrappers like `cross-env`.

[↑ Back to top](#table-of-contents)

### 36. How do you handle distributed transactions in microservices?

Use saga patterns (choreography or orchestration) to maintain eventual consistency across services. Avoid 2PC due to performance.

[↑ Back to top](#table-of-contents)

### 37. How would you design a file processing service (e.g., image resizing)?

Users upload file -> store in temporary location (S3) -> API enqueues a job (file path, desired operations) -> Worker pool picks up job, processes (using sharp for images), uploads result, updates status. Webhook/notification on completion. Use streams for large files.

[↑ Back to top](#table-of-contents)
