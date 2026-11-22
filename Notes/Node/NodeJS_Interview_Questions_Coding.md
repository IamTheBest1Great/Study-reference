# Node.js Backend Interview Questions — Coding / Implementation

A consolidated, deduplicated collection of **hands-on coding and implementation-focused Node.js interview questions** — build/implement tasks for streams, middleware, rate limiters, custom utilities, and more — organized section-wise.

**Total unique questions: 59**

## Table of Contents

- [Core Fundamentals & Runtime (V8, libuv, process, modules)](#core-fundamentals-runtime-v8-libuv-process-modules) (4)
  - [1. How can you create a CLI tool using Node.js?](#1-how-can-you-create-a-cli-tool-using-nodejs)
  - [2. How do you create and use custom modules in Node.js?](#2-how-do-you-create-and-use-custom-modules-in-nodejs)
  - [3. How do you implement a webhook receiver in Node.js?](#3-how-do-you-implement-a-webhook-receiver-in-nodejs)
  - [4. How do you write a `Dockerfile` for a Node.js application?](#4-how-do-you-write-a-dockerfile-for-a-nodejs-application)
- [Event Loop, Concurrency & Async Patterns](#event-loop-concurrency-async-patterns) (4)
  - [5. How do you implement a timeout for an asynchronous operation?](#5-how-do-you-implement-a-timeout-for-an-asynchronous-operation)
  - [6. How do you implement structured concurrency in Node.js?](#6-how-do-you-implement-structured-concurrency-in-nodejs)
  - [7. What happens when you `await` a non-Promise value?](#7-what-happens-when-you-await-a-non-promise-value)
  - [8. What is `promisify()`? How would you implement it from scratch?](#8-what-is-promisify-how-would-you-implement-it-from-scratch)
- [Streams & Buffers](#streams-buffers) (3)
  - [9. How do you create a Buffer? What is the difference between `Buffer.alloc()` and `Buffer.allocUnsafe()`?](#9-how-do-you-create-a-buffer-what-is-the-difference-between-bufferalloc-and-bufferallocunsafe)
  - [10. How do you implement a custom Transform stream?](#10-how-do-you-implement-a-custom-transform-stream)
  - [11. What are WebSockets and how can you implement them in Node.js?](#11-what-are-websockets-and-how-can-you-implement-them-in-nodejs)
- [Express.js, Middleware & REST API Design](#expressjs-middleware-rest-api-design) (16)
  - [12. How can you create a RESTful API using Node.js?](#12-how-can-you-create-a-restful-api-using-nodejs)
  - [13. How can you implement rate limiting in a Node.js application?](#13-how-can-you-implement-rate-limiting-in-a-nodejs-application)
  - [14. How do you create a router in Express? Why would you use `express.Router()`?](#14-how-do-you-create-a-router-in-express-why-would-you-use-expressrouter)
  - [15. How do you implement API rate limiting? What headers do you return?](#15-how-do-you-implement-api-rate-limiting-what-headers-do-you-return)
  - [16. How do you implement error-handling middleware in Express?](#16-how-do-you-implement-error-handling-middleware-in-express)
  - [17. How do you implement graceful error responses (not leaking stack traces in production)?](#17-how-do-you-implement-graceful-error-responses-not-leaking-stack-traces-in-production)
  - [18. How do you implement input validation and sanitization?](#18-how-do-you-implement-input-validation-and-sanitization)
  - [19. How do you implement rate limiting in Express?](#19-how-do-you-implement-rate-limiting-in-express)
  - [20. How do you implement request timeout middleware?](#20-how-do-you-implement-request-timeout-middleware)
  - [21. How do you implement SSE in Express?](#21-how-do-you-implement-sse-in-express)
  - [22. What is `supertest`? How do you test Express routes with it?](#22-what-is-supertest-how-do-you-test-express-routes-with-it)
  - [23. What is centralized error handling in Express? How do you implement it?](#23-what-is-centralized-error-handling-in-express-how-do-you-implement-it)
  - [24. What is graceful shutdown in an Express application? How do you implement it?](#24-what-is-graceful-shutdown-in-an-express-application-how-do-you-implement-it)
  - [25. What is rate limiting? How do you implement it? What is distributed rate limiting?](#25-what-is-rate-limiting-how-do-you-implement-it-what-is-distributed-rate-limiting)
  - [26. What is RBAC (Role-Based Access Control)? How do you implement it in Express?](#26-what-is-rbac-role-based-access-control-how-do-you-implement-it-in-express)
  - [27. What is the Chain of Responsibility pattern? How does Express middleware implement it?](#27-what-is-the-chain-of-responsibility-pattern-how-does-express-middleware-implement-it)
- [Authentication & Authorization](#authentication-authorization) (8)
  - [28. How do you implement API key authentication securely?](#28-how-do-you-implement-api-key-authentication-securely)
  - [29. How do you implement authentication in a Node.js application?](#29-how-do-you-implement-authentication-in-a-nodejs-application)
  - [30. How do you implement authentication/authorization in GraphQL resolvers?](#30-how-do-you-implement-authenticationauthorization-in-graphql-resolvers)
  - [31. How do you implement JWT refresh tokens? What is the refresh token rotation pattern?](#31-how-do-you-implement-jwt-refresh-tokens-what-is-the-refresh-token-rotation-pattern)
  - [32. How do you implement magic link (passwordless) authentication?](#32-how-do-you-implement-magic-link-passwordless-authentication)
  - [33. How do you implement session storage in Redis?](#33-how-do-you-implement-session-storage-in-redis)
  - [34. What is MFA (Multi-Factor Authentication)? How do you implement TOTP?](#34-what-is-mfa-multi-factor-authentication-how-do-you-implement-totp)
  - [35. What is Passport.js? How do you implement a `passport-jwt` strategy?](#35-what-is-passportjs-how-do-you-implement-a-passport-jwt-strategy)
- [Databases — MongoDB & Mongoose](#databases-mongodb-mongoose) (2)
  - [36. How do you connect to a MongoDB database from a Node.js application?](#36-how-do-you-connect-to-a-mongodb-database-from-a-nodejs-application)
  - [37. How do you implement soft deletes in Mongoose?](#37-how-do-you-implement-soft-deletes-in-mongoose)
- [Databases — SQL, PostgreSQL & ORMs](#databases-sql-postgresql-orms) (1)
  - [38. How do you implement distributed locking in Node.js?](#38-how-do-you-implement-distributed-locking-in-nodejs)
- [Caching & Redis](#caching-redis) (6)
  - [39. How do you implement a rate limiter using Redis?](#39-how-do-you-implement-a-rate-limiter-using-redis)
  - [40. How do you implement caching at the application layer?](#40-how-do-you-implement-caching-at-the-application-layer)
  - [41. How do you implement distributed locking with Redis? (Redlock algorithm)](#41-how-do-you-implement-distributed-locking-with-redis-redlock-algorithm)
  - [42. How do you implement feature flags in a Node.js service?](#42-how-do-you-implement-feature-flags-in-a-nodejs-service)
  - [43. What is graceful shutdown? How do you implement it? (drain existing connections, stop accepting new ones)](#43-what-is-graceful-shutdown-how-do-you-implement-it-drain-existing-connections-stop-accepting-new-ones)
  - [44. What is the module cache in Node.js? What happens when you require the same module twice?](#44-what-is-the-module-cache-in-nodejs-what-happens-when-you-require-the-same-module-twice)
- [Error Handling & Logging](#error-handling-logging) (2)
  - [45. How do you implement audit logging in a Node.js app?](#45-how-do-you-implement-audit-logging-in-a-nodejs-app)
  - [46. How do you implement centralized logging in a distributed Node.js system? (ELK, Datadog, Loki)](#46-how-do-you-implement-centralized-logging-in-a-distributed-nodejs-system-elk-datadog-loki)
- [Security](#security) (1)
  - [47. How do you implement security headers? (HSTS, X-Frame-Options, X-Content-Type-Options)](#47-how-do-you-implement-security-headers-hsts-x-frame-options-x-content-type-options)
- [File System & Built-in Modules](#file-system-built-in-modules) (2)
  - [48. How do you implement atomic file writes?](#48-how-do-you-implement-atomic-file-writes)
  - [49. How does Node.js perform I/O? Walk through what happens when `fs.readFile()` is called.](#49-how-does-nodejs-perform-io-walk-through-what-happens-when-fsreadfile-is-called)
- [Microservices Architecture](#microservices-architecture) (1)
  - [50. What is circuit breaker pattern? How do you implement it in Node.js?](#50-what-is-circuit-breaker-pattern-how-do-you-implement-it-in-nodejs)
- [Message Queues (RabbitMQ, Kafka, Bull)](#message-queues-rabbitmq-kafka-bull) (1)
  - [51. How do you implement job queues with BullMQ? What are job priorities and retries?](#51-how-do-you-implement-job-queues-with-bullmq-what-are-job-priorities-and-retries)
- [Testing in Node.js](#testing-in-nodejs) (1)
  - [52. How do you use the `mocha` and `chai` libraries for testing in Node.js?](#52-how-do-you-use-the-mocha-and-chai-libraries-for-testing-in-nodejs)
- [DevOps — Docker, CI/CD & Deployment](#devops-docker-cicd-deployment) (1)
  - [53. How do you implement zero-downtime deployment with Node.js?](#53-how-do-you-implement-zero-downtime-deployment-with-nodejs)
- [Design Patterns in Node.js](#design-patterns-in-nodejs) (2)
  - [54. What is Dependency Injection? How do you implement it without a framework?](#54-what-is-dependency-injection-how-do-you-implement-it-without-a-framework)
  - [55. What is the Observer pattern? How does `EventEmitter` implement it?](#55-what-is-the-observer-pattern-how-does-eventemitter-implement-it)
- [General / Miscellaneous Node.js Concepts](#general-miscellaneous-nodejs-concepts) (4)
  - [56. How can you create an HTTP server using Node.js?](#56-how-can-you-create-an-http-server-using-nodejs)
  - [57. How do you implement a retry mechanism with exponential backoff?](#57-how-do-you-implement-a-retry-mechanism-with-exponential-backoff)
  - [58. How do you implement distributed tracing? (OpenTelemetry, Jaeger)](#58-how-do-you-implement-distributed-tracing-opentelemetry-jaeger)
  - [59. What is a custom error class in Node.js? Implement `AppError` with a status code.](#59-what-is-a-custom-error-class-in-nodejs-implement-apperror-with-a-status-code)

---

## Core Fundamentals & Runtime (V8, libuv, process, modules)

### 1. How can you create a CLI tool using Node.js?

Create a Node.js script with a shebang (`#!/usr/bin/env node`). Use `process.argv` to parse arguments, or use libraries like `commander` or `yargs` for robust CLI parsing. Publish to npm to make it globally installable.

[↑ Back to top](#table-of-contents)

### 2. How do you create and use custom modules in Node.js?

Create a file (e.g., `math.js`) and export functionality using `module.exports`. In another file, import it with `require('./math')`. This keeps code organized, reusable, and encapsulated.

[↑ Back to top](#table-of-contents)

### 3. How do you implement a webhook receiver in Node.js?

Expose an endpoint that accepts POST requests. Validate payload (e.g., HMAC signature). Acknowledge immediately with 200 (or queued). Process asynchronously (queue) to avoid timeouts. Ensure idempotency (deduplicate events). Use a queue for reliability.

[↑ Back to top](#table-of-contents)

### 4. How do you write a `Dockerfile` for a Node.js application?

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]
```

Multi-stage builds separate build and runtime.

[↑ Back to top](#table-of-contents)

## Event Loop, Concurrency & Async Patterns

### 5. How do you implement a timeout for an asynchronous operation?

Expected interview answer:

“One way to implement a timeout is to use `Promise.race()` between the actual operation and a Promise that rejects after a specified delay.

Whichever Promise settles first determines the result returned by `Promise.race()`.

For example, if I want an operation to finish within three seconds, I can race it against a three-second timeout Promise.

However, there is an important distinction: `Promise.race()` does not automatically cancel the underlying operation. It only determines which result the caller receives first. If the operation supports cancellation, I would cancel it separately when the timeout occurs.”

Example:
```

function withTimeout(promise, ms) {
let timer;

const timeout = new Promise((_, reject) => {
timer = setTimeout(() => {
reject(new Error("Operation timed out"));
}, ms);
});

return Promise.race([promise, timeout])
.finally(() => clearTimeout(timer));
}
```

Usage:
```

try {
const result = await withTimeout(fetchData(), 3000);
console.log(result);
} catch (error) {
console.error(error.message);
}
```

Remember: A timeout limits how long the caller waits; it does not necessarily stop the underlying operation.

[↑ Back to top](#table-of-contents)

### 6. How do you implement structured concurrency in Node.js?

Structured concurrency ensures that concurrent tasks are properly scoped and cancelled together. Implement using `Promise.allSettled` with `AbortController`, or use libraries like `p-queue`. Cancel all child tasks when parent is cancelled. The pattern prevents orphan promises and resource leaks.

[↑ Back to top](#table-of-contents)

### 7. What happens when you `await` a non-Promise value?

Expected interview answer:

“When we use `await` with a non-Promise value, JavaScript evaluates that value and uses it as the result of the `await` expression.

For example, if we write `await 10`, the expression evaluates to `10`.

However, the execution of the surrounding async function is still suspended and resumed asynchronously. So even though the value is not a Promise, `await` still affects the execution order.

This is useful to remember when reasoning about asynchronous code and microtask scheduling.”

Example:
```

async function main() {
console.log("Start");

const value = await 10;

console.log(value);
console.log("End");
}

main();

console.log("Outside");
```

Output:
```

Start
Outside
10
End
```

Remember: `await` works with ordinary values too, but the continuation of the async function resumes asynchronously.

[↑ Back to top](#table-of-contents)

### 8. What is `promisify()`? How would you implement it from scratch?

Expected interview answer:

“`promisify()` converts a callback-based function into a function that returns a Promise.

In Node.js, we can use the built-in `util.promisify()` utility for compatible error-first callback APIs.

The basic idea is to create a Promise, invoke the original function, and pass it a callback. If the callback receives an error, we reject the Promise. Otherwise, we resolve it with the result.

This allows us to use older callback-based APIs with `async/await`.”

Example implementation for a simple function that returns one result:
```

function promisify(fn) {
return (...args) =>
new Promise((resolve, reject) => {
fn(...args, (err, result) => {
if (err) {
reject(err);
} else {
resolve(result);
}
});
});
}
```

Using Node.js's built-in utility:
```

const { promisify } = require("node:util");
const fs = require("node:fs");

const readFile = promisify(fs.readFile);

async function main() {
const data = await readFile("data.txt", "utf8");
console.log(data);
}

main().catch(console.error);
```

Remember: `promisify()` converts a compatible callback API into a Promise-returning function.

[↑ Back to top](#table-of-contents)

## Streams & Buffers

### 9. How do you create a Buffer? What is the difference between `Buffer.alloc()` and `Buffer.allocUnsafe()`?

Expected interview answer:

“We can create Buffers using methods such as `Buffer.from()`, `Buffer.alloc()`, and `Buffer.allocUnsafe()`.

`Buffer.from()` creates a Buffer from existing data, such as a string or an array of byte values.

`Buffer.alloc()` creates a Buffer of a specified size and initializes all its bytes to zero.

`Buffer.allocUnsafe()` allocates a Buffer without first initializing its contents, which can be faster in some situations. However, the Buffer may contain old memory contents, so I must overwrite the relevant bytes before reading or exposing them.

For most normal application code, I would prefer `Buffer.alloc()` when allocating an empty buffer because it is safer.”

Example:
```

const safeBuffer = Buffer.alloc(5);

const bufferFromString = Buffer.from("Hello", "utf8");

const unsafeBuffer = Buffer.allocUnsafe(5);

// Initialize every byte before using it.
unsafeBuffer.fill(0);

console.log(safeBuffer);
console.log(bufferFromString.toString("utf8"));
console.log(unsafeBuffer);
```

Remember: `Buffer.alloc()` initializes memory; `Buffer.allocUnsafe()` requires care because its initial contents are not guaranteed to be zero.

[↑ Back to top](#table-of-contents)

### 10. How do you implement a custom Transform stream?

Expected interview answer:

“A Transform stream is a type of Duplex stream that allows us to modify data as it passes from the readable side to the writable side.

To create one, I can use the `Transform` class from Node.js's stream module and implement the `transform()` method.

This method receives a chunk of data, processes it, and passes the resulting data forward.

For example, if I want to convert incoming text to uppercase, I can create a custom Transform stream that processes each chunk and outputs the uppercase version.”

Example:
```

const { Transform } = require("node:stream");

const upperCaseTransform = new Transform({
transform(chunk, encoding, callback) {
callback(null, chunk.toString().toUpperCase());
}
});

upperCaseTransform.on("data", chunk => {
console.log(chunk.toString());
});

upperCaseTransform.write("hello node.js");
upperCaseTransform.end();
```

Output:
```

HELLO NODE.JS
```

Remember: Implement `transform()` to process each incoming chunk and pass the result through the callback or stream.

[↑ Back to top](#table-of-contents)

### 11. What are WebSockets and how can you implement them in Node.js?

WebSockets provide full‑duplex communication over a single TCP connection. In Node.js, use the `ws` library or integrate with frameworks like `socket.io`. Example with `ws`:

```js
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });
wss.on('connection', ws => { ws.on('message', message => { ... }); });

```

[↑ Back to top](#table-of-contents)

## Express.js, Middleware & REST API Design

### 12. How can you create a RESTful API using Node.js?

Use Express.js. Define routes for each resource with appropriate HTTP methods. Use middleware for parsing bodies, authentication, etc. Return JSON responses. Example:

```js
app.get('/api/users', (req, res) => res.json(users));
app.post('/api/users', (req, res) => { /* create user */ });

```

[↑ Back to top](#table-of-contents)

### 13. How can you implement rate limiting in a Node.js application?

Use the `express-rate-limit` middleware. Configure the window and maximum number of requests per IP. Example:

```js
const rateLimit = require('express-rate-limit');
const limiter = rateLimit({ windowMs: 15*60*1000, max: 100 });
app.use('/api', limiter);

```

[↑ Back to top](#table-of-contents)

### 14. How do you create a router in Express? Why would you use `express.Router()`?

Expected interview answer:

“`express.Router()` allows us to create a modular routing system within an Express application.

Instead of defining every route in a single file, we can group related routes into separate router files.

For example, I can create a user router containing endpoints for retrieving users, creating users, and updating user details.

Then I can mount that router in the main application using `app.use('/users', userRouter)`.

This improves separation of concerns and makes a large backend easier to maintain.”

Example:
```

// routes/userRoutes.js
const express = require("express");

const router = express.Router();

router.get("/", (req, res) => {
res.json({ message: "Get users" });
});

router.post("/", (req, res) => {
res.status(201).json({ message: "Create user" });
});

module.exports = router;
```

```
// app.js
const userRoutes = require("./routes/userRoutes");

app.use("/users", userRoutes);
```

Remember: `express.Router()` lets us organize related routes into reusable modules.

[↑ Back to top](#table-of-contents)

### 15. How do you implement API rate limiting? What headers do you return?

Expected interview answer:

“API rate limiting restricts the number of requests a client can make during a defined time window.

I would normally implement it using middleware that tracks requests by an appropriate key, such as an authenticated API key or client IP address.

If the client exceeds the configured limit, the API returns `429 Too Many Requests`.

The response can include headers that communicate the limit, the remaining quota, and when the limit resets. Examples of commonly used header names are `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and `X-RateLimit-Reset`.

For a distributed system, I would use a shared store such as Redis when rate-limit state needs to be consistent across application instances.”

Remember: Return `429` when a client exceeds the allowed request rate, and communicate the applicable limit where appropriate.

[↑ Back to top](#table-of-contents)

### 16. How do you implement error-handling middleware in Express?

Expected interview answer:

“Express uses a special error-handling middleware signature containing four parameters: `err`, `req`, `res`, and `next`.

When a route or middleware forwards an error using `next(err)`, Express skips normal middleware and passes control to an applicable error handler.

I normally use centralized error handling so that errors are logged and returned using a consistent response format.

I also avoid exposing stack traces or internal details to clients in production.”

Example:
```

function errorHandler(err, req, res, next) {
console.error(err);

if (res.headersSent) {
return next(err);
}

const status = err.status || 500;

res.status(status).json({
error: status === 500
? "Internal server error"
: err.message
});
}

app.use(errorHandler);
```

Remember: Error-handling middleware has four parameters and should generally be registered after routes.

[↑ Back to top](#table-of-contents)

### 17. How do you implement graceful error responses (not leaking stack traces in production)?

In error-handling middleware, check `NODE_ENV`. In production, send a generic message; in development, include the error stack. Always use custom error classes to control what is sent.

[↑ Back to top](#table-of-contents)

### 18. How do you implement input validation and sanitization?

Use validation libraries (Joi, Zod, express-validator) to define expected schemas and reject invalid input. Sanitize data by escaping, trimming, or type coercion. Validate at the boundary (API middleware).

[↑ Back to top](#table-of-contents)

### 19. How do you implement rate limiting in Express?

Expected interview answer:

“Rate limiting restricts how many requests a client can make within a specific period.

It helps protect an API from excessive traffic, accidental request loops, and certain forms of abuse.

In Express, I can use middleware such as `express-rate-limit` to define a time window and a maximum request count.

When the client exceeds the limit, the middleware can return HTTP `429 Too Many Requests`.

For a distributed deployment with multiple application instances, I would use a shared store such as Redis so that the rate limit is coordinated across instances.”

Example:
```

const rateLimit = require("express-rate-limit");

const limiter = rateLimit({
windowMs: 15 * 60 * 1000,
limit: 100
});

app.use("/api", limiter);
```

Remember: Rate limiting controls request frequency; distributed deployments often need shared rate-limit state.

[↑ Back to top](#table-of-contents)

### 20. How do you implement request timeout middleware?

Expected interview answer:

“A request timeout defines how long the application is willing to wait for a request or operation to complete.

In Express, I would distinguish between an incoming request timeout, an outgoing response timeout, and a timeout for a downstream operation such as a database or external API call.

For downstream operations, I would set an appropriate deadline and cancel the operation if the underlying API supports cancellation.

If the server needs to send a timeout response, I would first ensure that the response has not already been sent or ended. I would avoid indiscriminately destroying the request because that can prevent the client from receiving a useful response.”

Example of a simple response deadline:
```

function timeoutMiddleware(req, res, next) {
const timer = setTimeout(() => {
if (!res.headersSent && !res.writableEnded) {
res.status(503).json({
error: "Request processing timed out"
});
}
}, 10000);

res.on("finish", () => clearTimeout(timer));
res.on("close", () => clearTimeout(timer));

next();
}
```

This is a simplified example; production implementations should also cancel the underlying operation and ensure timed-out work cannot continue unnecessarily.

Remember: A timeout policy should define the deadline, stop unnecessary work when possible, and avoid sending duplicate responses.

[↑ Back to top](#table-of-contents)

### 21. How do you implement SSE in Express?

Set headers: `Content-Type: text/event-stream`, `Cache-Control: no-cache`, `Connection: keep-alive`. Then write events: `res.write('data: message\n\n');`.

[↑ Back to top](#table-of-contents)

### 22. What is `supertest`? How do you test Express routes with it?

`supertest` allows testing HTTP servers by making requests and asserting responses. Example:

```javascript
const request = require('supertest');
const app = require('../app');
await request(app).get('/users').expect(200);

```

[↑ Back to top](#table-of-contents)

### 23. What is centralized error handling in Express? How do you implement it?

Create an error-handling middleware (four arguments) at the end. All errors passed via `next(err)` will end up there. This middleware can log the error and send a consistent JSON response.

[↑ Back to top](#table-of-contents)

### 24. What is graceful shutdown in an Express application? How do you implement it?

Expected interview answer:

“Graceful shutdown means stopping an application without unnecessarily interrupting requests that are already being processed.

When a deployment platform sends a signal such as `SIGTERM`, I would stop accepting new connections, allow active requests to finish within a defined period, and close resources such as database connections.

I would also implement a timeout so that the application does not wait forever for a connection or request to finish.

This is important in production deployments because it helps reduce failed requests and ensures that resources are released correctly.”

Example:
```

const http = require("node:http");
const app = require("./app");

const server = http.createServer(app);

server.listen(3000);

process.on("SIGTERM", () => {
server.close(async () => {
// Close the database pool and other resources here.
process.exit(0);
});
});
```

This is a simplified illustration. A production implementation should also handle shutdown timeouts and cleanup failures.

Remember: Stop new connections, drain active work, release resources, and then terminate.

[↑ Back to top](#table-of-contents)

### 25. What is rate limiting? How do you implement it? What is distributed rate limiting?

Rate limiting restricts the number of requests per client/IP in a time window to prevent abuse. Implement with `express-rate-limit`. For distributed systems, store counters in Redis (`rate-limit-redis`). This coordinates limits across multiple server instances.

[↑ Back to top](#table-of-contents)

### 26. What is RBAC (Role-Based Access Control)? How do you implement it in Express?

RBAC assigns permissions to roles, and users are assigned roles. In Express, create middleware that checks `req.user.role` against required roles for the route. e.g., `authorize('admin', 'editor')` middleware.

[↑ Back to top](#table-of-contents)

### 27. What is the Chain of Responsibility pattern? How does Express middleware implement it?

Chain of Responsibility passes a request along a chain of handlers. Express middleware chain does exactly this: each middleware decides to handle or pass to the next by calling `next()`.

[↑ Back to top](#table-of-contents)

## Authentication & Authorization

### 28. How do you implement API key authentication securely?

Client sends API key in header or query param. Server validates against a store (DB, Redis). Use constant-time comparison. Never log the key. Enforce HTTPS. Consider rate limiting and key rotation.

[↑ Back to top](#table-of-contents)

### 29. How do you implement authentication in a Node.js application?

Common approaches: session‑based (using cookies and `express-session`), token‑based (JWT), or OAuth. JWTs are often used with Bearer tokens. Passport.js is a popular authentication middleware that supports many strategies (local, OAuth, JWT).

[↑ Back to top](#table-of-contents)

### 30. How do you implement authentication/authorization in GraphQL resolvers?

Pass context (e.g., `{ user }`) to resolvers via Apollo context function, which extracts user from request headers (JWT). In resolvers, check context.user and throw `AuthenticationError` or `ForbiddenError`. Use custom directives for declarative auth.

[↑ Back to top](#table-of-contents)

### 31. How do you implement JWT refresh tokens? What is the refresh token rotation pattern?

Access token short-lived (e.g., 15 min), refresh token long-lived (e.g., 7 days). On access token expiry, client sends refresh token to get a new access token. Refresh token rotation: each refresh issues a new refresh token and invalidates the old one. This limits the window of token reuse.

[↑ Back to top](#table-of-contents)

### 32. How do you implement magic link (passwordless) authentication?

User enters email; server generates a signed, time-limited token, sends an email with a link containing the token. User clicks link; server verifies token, creates session/JWT. Eliminates password storage.

[↑ Back to top](#table-of-contents)

### 33. How do you implement session storage in Redis?

Use `connect-redis` as session store for Express-session: `app.use(session({ store: new RedisStore({ client: redisClient }), secret, ... }))`. Sessions stored as key-value, with automatic expiration.

[↑ Back to top](#table-of-contents)

### 34. What is MFA (Multi-Factor Authentication)? How do you implement TOTP?

MFA requires two or more verification factors. TOTP (Time-based One-Time Password) uses a shared secret and the current time to generate a 6-digit code. Use `speakeasy` library to generate secret, verify token. Show QR code for Google Authenticator.

[↑ Back to top](#table-of-contents)

### 35. What is Passport.js? How do you implement a `passport-jwt` strategy?

Passport.js is authentication middleware for Node.js. To use JWT: configure `JwtStrategy` from `passport-jwt` with `secretOrKey` and a JWT extractor (from header). In route, use `passport.authenticate('jwt', { session: false })`. The strategy verifies token, attaches user to `req.user`.

[↑ Back to top](#table-of-contents)

## Databases — MongoDB & Mongoose

### 36. How do you connect to a MongoDB database from a Node.js application?

Use the official MongoDB driver (`mongodb`) or an ODM like Mongoose. Example with Mongoose:

```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/mydb');

```

[↑ Back to top](#table-of-contents)

### 37. How do you implement soft deletes in Mongoose?

Add a `deleted: Boolean` or `deletedAt: Date` field. Override query helpers or use a plugin to automatically filter `deleted: false`. On delete, update the field instead of removing.

[↑ Back to top](#table-of-contents)

## Databases — SQL, PostgreSQL & ORMs

### 38. How do you implement distributed locking in Node.js?

Use Redis with Redlock algorithm or a single instance with `SETNX` and TTL. Ensure lock is released only by owner. Handle lock expiry and contention. Use `redlock` library. Alternative: use PostgreSQL advisory locks for simple cases.

[↑ Back to top](#table-of-contents)

## Caching & Redis

### 39. How do you implement a rate limiter using Redis?

Use sorted sets for sliding window: for each request, add timestamp to a sorted set with key per user/IP, remove outdated entries, count remaining. Or use token bucket algorithm with INCR and EXPIRE. Libraries like `rate-limiter-flexible` use Redis backend.

[↑ Back to top](#table-of-contents)

### 40. How do you implement caching at the application layer?

Implement a cache-aside pattern: check cache first, on miss query DB and store in cache (Redis/Memory). Use TTLs, invalidate on writes. Cache frequently read, rarely changed data.

[↑ Back to top](#table-of-contents)

### 41. How do you implement distributed locking with Redis? (Redlock algorithm)

Redlock uses multiple independent Redis instances. To acquire lock, set a unique key with NX and PX (TTL) on a majority of instances within a timeout. To release, check value and delete if still owner. Libraries like `redlock` implement this. More reliable than single instance.

[↑ Back to top](#table-of-contents)

### 42. How do you implement feature flags in a Node.js service?

Use a feature flag service (LaunchDarkly, or custom config in DB). Wrap new code paths with a check: `if (await isEnabled('new-feature', user)) { ... }`. Allow gradual rollout via percentage or targeted users. Invalidate cache on flag change.

[↑ Back to top](#table-of-contents)

### 43. What is graceful shutdown? How do you implement it? (drain existing connections, stop accepting new ones)

1. Catch SIGTERM.
2. Stop accepting new connections (`server.close()`).
3. Allow current requests to finish (track active connections, use `http-terminator` or `stoppable`).
4. Clean up resources (close DB pools, disconnect Redis).
5. Exit.

[↑ Back to top](#table-of-contents)

### 44. What is the module cache in Node.js? What happens when you require the same module twice?

Expected interview answer:

“Node.js maintains a module cache for CommonJS modules. Once a module has been loaded and evaluated, its exports are cached using its resolved filename as the cache key.

When we require the same module again and it resolves to the same cached entry, Node.js returns the cached exports instead of executing the module code again.

This improves performance and means that modules can maintain shared state within the same process.

For example, if a module exports an object, different files requiring that module can receive the same object reference.

We can inspect the cache using `require.cache` and, when necessary, remove an entry to make Node.js load that module again on the next `require()`.”

Example:
```

// counter.js
console.log("Module executed");

module.exports = { count: 0 };
```

```
// app.js
const first = require("./counter");
const second = require("./counter");

first.count++;

console.log(second.count); // 1
```

The message `"Module executed"` prints only once in this example.

Remember: CommonJS caches modules, so repeated `require()` calls usually reuse the same exports.

[↑ Back to top](#table-of-contents)

## Error Handling & Logging

### 45. How do you implement audit logging in a Node.js app?

Create a dedicated audit log middleware or service that records who did what, when, and the relevant data. Write audit events to a secure, append-only storage (database, separate log file). Use correlation IDs and ensure immutability.

[↑ Back to top](#table-of-contents)

### 46. How do you implement centralized logging in a distributed Node.js system? (ELK, Datadog, Loki)

Send logs to a central system using agents (Filebeat -> Elasticsearch), direct API calls (Datadog, Loki), or syslog. Use structured logging with correlation IDs. Avoid writing logs to local files in containers.

[↑ Back to top](#table-of-contents)

## Security

### 47. How do you implement security headers? (HSTS, X-Frame-Options, X-Content-Type-Options)

Set them via middleware (helmet sets most). HSTS: `Strict-Transport-Security` header with max-age; X-Frame-Options: `DENY` or `SAMEORIGIN`; X-Content-Type-Options: `nosniff`. These prevent clickjacking, MIME sniffing, and enforce HTTPS.

[↑ Back to top](#table-of-contents)

## File System & Built-in Modules

### 48. How do you implement atomic file writes?

Write to a temporary file, then atomically rename it to the target filename using `fs.rename`. This ensures the file is either fully written or not at all (no partial data).

[↑ Back to top](#table-of-contents)

### 49. How does Node.js perform I/O? Walk through what happens when `fs.readFile()` is called.

1. `fs.readFile` delegates to libuv.
2. libuv allocates a thread from the thread pool if the operation is blocking (file I/O).
3. The JS thread continues executing the next line (non-blocking).
4. When the thread completes reading, it places a completion event in the event loop's pending I/O queue.
5. The event loop, during the poll phase, picks up the event and invokes the callback provided to `readFile`.
6. The callback is executed on the main thread.

[↑ Back to top](#table-of-contents)

## Microservices Architecture

### 50. What is circuit breaker pattern? How do you implement it in Node.js?

Circuit breaker detects failures and prevents cascading failures by "opening" the circuit after a threshold, failing fast until a timeout. In Node.js, use `opossum` library to wrap calls to external services. It provides fallback and auto-recovery.

[↑ Back to top](#table-of-contents)

## Message Queues (RabbitMQ, Kafka, Bull)

### 51. How do you implement job queues with BullMQ? What are job priorities and retries?

Define a Queue, add jobs with options `{ priority, attempts, backoff }`. Workers process jobs. Priority determines order; retries automatically re-attempt on failure with exponential backoff.

[↑ Back to top](#table-of-contents)

## Testing in Node.js

### 52. How do you use the `mocha` and `chai` libraries for testing in Node.js?

Install mocha and chai, then write tests in a `test/` folder. Example:

```js
const { expect } = require('chai');
describe('Math', () => {
it('should add numbers', () => {
expect(1+1).to.equal(2);
});
});
```

Run with `mocha`.

[↑ Back to top](#table-of-contents)

## DevOps — Docker, CI/CD & Deployment

### 53. How do you implement zero-downtime deployment with Node.js?

Using PM2: `pm2 reload` or `pm2 startOrGracefulReload` sends SIGUSR2 to start new workers and gracefully shut down old ones. With a load balancer, drain connections from old instance before stopping. In Kubernetes, rolling updates achieve similar.

[↑ Back to top](#table-of-contents)

## Design Patterns in Node.js

### 54. What is Dependency Injection? How do you implement it without a framework?

DI passes dependencies into a component rather than having it create them. In Node.js, you can pass DB instance, logger, etc., as constructor arguments or via function parameters. For simplicity, use a DI container like `awilix` for automatic injection.

[↑ Back to top](#table-of-contents)

### 55. What is the Observer pattern? How does `EventEmitter` implement it?

Observer pattern defines a one-to-many dependency between objects. `EventEmitter` maintains a list of listeners; when an event is emitted, all listeners are notified. Used throughout Node.js (streams, process events).

[↑ Back to top](#table-of-contents)

## General / Miscellaneous Node.js Concepts

### 56. How can you create an HTTP server using Node.js?

Use `http.createServer((req, res) => { ... })` which returns a server instance. Then call `server.listen(port)` to start listening. The callback receives request and response objects. For example:

```js
const http = require('http');
http.createServer((req, res) => {
res.writeHead(200, { 'Content-Type': 'text/plain' });
res.end('Hello World');
}).listen(3000);

```

[↑ Back to top](#table-of-contents)

### 57. How do you implement a retry mechanism with exponential backoff?

Expected interview answer:

“Exponential backoff is a retry strategy in which the waiting time increases after each failed attempt.

For example, if the initial delay is 100 milliseconds, the next delays could be 100, 200, and 400 milliseconds.

This is useful when an operation fails temporarily because of network issues, rate limiting, or a remote service being overloaded.

I would limit the number of attempts and retry only errors that are appropriate to retry. I would also consider adding random jitter to prevent many clients from retrying simultaneously.

For operations that change data, I would verify that retrying cannot accidentally perform the same action twice.”

Example implementation:
```

async function retry(fn, maxAttempts = 3, initialDelay = 100) {
for (let attempt = 0; attempt < maxAttempts; attempt++) {
try {
return await fn();
} catch (error) {
const isLastAttempt = attempt === maxAttempts - 1;

if (isLastAttempt) {
throw error;
}

const delay = initialDelay * 2 ** attempt;

await new Promise(resolve => setTimeout(resolve, delay));
}
}
}
```

Usage:
```

const result = await retry(() => fetchData(), 3, 100);
```

In this example, there are at most three total attempts, with waits of 100 ms and 200 ms before the second and third attempts.

Remember: Exponential backoff increases the delay after each failure; always limit retries and consider idempotency.

[↑ Back to top](#table-of-contents)

### 58. How do you implement distributed tracing? (OpenTelemetry, Jaeger)

Instrument services with OpenTelemetry SDK to generate spans and propagate context via headers (W3C TraceContext). Export to Jaeger, Zipkin, or other backends to trace requests across microservices.

[↑ Back to top](#table-of-contents)

### 59. What is a custom error class in Node.js? Implement `AppError` with a status code.

```javascript
class AppError extends Error {
constructor(message, statusCode) {
super(message);
this.statusCode = statusCode;
this.isOperational = true; // distinguish from programmer errors
Error.captureStackTrace(this, this.constructor);
}
}

```

[↑ Back to top](#table-of-contents)
