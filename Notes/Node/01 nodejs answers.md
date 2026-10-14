# Node.js Backend — Complete Interview Question Bank with Answers

> Comprehensive, section-wise question bank covering every topic asked in Node.js backend interviews — from freshers to senior/staff level. All questions are linked from the Table of Contents and answered in detail.

---

## Table of Contents

1. [Node.js Core Fundamentals](#1-nodejs-core-fundamentals)
2. [Event Loop & Async Model](#2-event-loop--async-model)
3. [Streams & Buffers](#3-streams--buffers)
4. [Modules System](#4-modules-system)
5. [Express.js & Middleware](#5-expressjs--middleware)
6. [REST API Design](#6-rest-api-design)
7. [Authentication & Authorization](#7-authentication--authorization)
8. [Databases — MongoDB & Mongoose](#8-databases--mongodb--mongoose)
9. [Databases — PostgreSQL / SQL & ORMs](#9-databases--postgresql--sql--orms)
10. [Caching — Redis & Strategies](#10-caching--redis--strategies)
11. [Error Handling & Logging](#11-error-handling--logging)
12. [Security](#12-security)
13. [Performance, Scaling & Clustering](#13-performance-scaling--clustering)
14. [Worker Threads & Child Processes](#14-worker-threads--child-processes)
15. [File System & Built-in Modules](#15-file-system--built-in-modules)
16. [WebSockets & Real-Time Communication](#16-websockets--real-time-communication)
17. [Microservices & Architecture](#17-microservices--architecture)
18. [Message Queues — RabbitMQ / Kafka / Bull](#18-message-queues--rabbitmq--kafka--bull)
19. [Testing in Node.js](#19-testing-in-nodejs)
20. [DevOps — Docker, CI/CD & Deployment](#20-devops--docker-cicd--deployment)
21. [TypeScript with Node.js](#21-typescript-with-nodejs)
22. [Design Patterns in Node.js](#22-design-patterns-in-nodejs)
23. [GraphQL with Node.js](#23-graphql-with-nodejs)
24. [Advanced / Senior-Level Questions](#24-advanced--senior-level-questions)
25. [Scenario-Based / System Design Questions](#25-scenario-based--system-design-questions)

---

## 1. Node.js Core Fundamentals

### Architecture & Runtime

# Node.js Backend Interview Questions — Interview-Ready Answers

These are the answers to all 30 questions in your attached document, “Node.js Core Fundamentals — Architecture & Runtime.” I’ve rewritten them in natural spoken English, as I would expect you to explain them in a technical interview.

The goal is to help you understand and explain each answer confidently, rather than memorize textbook definitions.

# Section 1: Node.js Core Fundamentals

## Q1. What is Node.js? How is it different from a browser's JavaScript environment?

Expected interview answer:

“Node.js is an open-source, cross-platform JavaScript runtime environment that allows us to execute JavaScript outside the browser.

It uses Google's V8 engine to execute JavaScript and provides additional features to interact with the operating system, such as file handling, networking, and database connectivity.

The main difference is that browsers provide objects like `window` and the DOM for interacting with web pages, whereas Node.js provides objects like `process`, `global`, and built-in modules such as `fs`, `http`, and `path`.

Node.js is mainly used for backend development, REST APIs, real-time applications, and other server-side applications.”

Remember: Node.js = JavaScript runtime + V8 + server-side APIs.

## Q2. Explain the Node.js architecture. What are its key components?

Expected interview answer:

“Node.js architecture consists of several important components.

First, V8 is the JavaScript engine that compiles and executes JavaScript code. Second, libuv provides the event loop, asynchronous I/O support, and a thread pool for certain operations.

The event loop coordinates the execution of callbacks and asynchronous operations. The libuv thread pool handles operations such as many file-system tasks, certain DNS lookups, and some cryptographic operations.

Node.js also uses C++ bindings to connect JavaScript with lower-level system functionality.

Together, these components allow Node.js to handle many concurrent I/O operations efficiently without requiring a separate JavaScript thread for every request.”

Remember: V8 executes JavaScript; libuv helps manage asynchronous operations and the event loop.

## Q3. What is the V8 engine? What does it do in Node.js?

Expected interview answer:

“V8 is Google's open-source JavaScript engine, written in C++. It is used by Chrome and Node.js to execute JavaScript code.

V8 compiles and optimizes JavaScript, including using Just-In-Time compilation to improve execution performance. It also manages JavaScript memory and garbage collection.

However, V8 itself does not provide all the server-side functionality. Node.js adds APIs and bindings that allow JavaScript to interact with the file system, network, processes, and other operating-system resources.”

Remember: V8 executes JavaScript; Node.js adds the runtime capabilities needed for backend development.

## Q4. What is libuv? What role does it play in Node.js?

Expected interview answer:

“libuv is a cross-platform C library that provides the event loop and asynchronous I/O capabilities used by Node.js.

For example, when our application needs to read a file or perform another asynchronous operation, Node.js can delegate the work to the operating system or the libuv thread pool, depending on the operation.

While the operation is in progress, JavaScript can continue processing other work. When the result becomes available, the associated callback or continuation can execute through the event loop.

So, libuv is one of the main components that enables Node.js to handle concurrent operations efficiently.”

Remember: libuv manages the event loop and coordinates many asynchronous operations.

## Q5. Why is Node.js single-threaded? What does that mean practically?

Expected interview answer:

“Node.js normally executes our JavaScript application code on a single main thread, which is coordinated by the event loop.

This does not mean that the entire Node.js runtime uses only one thread. The operating system and libuv's thread pool can perform certain operations separately.

The advantage is that Node.js can handle many I/O operations without creating a separate application thread for every request.

However, CPU-intensive JavaScript can block the event loop and delay other requests. For such workloads, we can consider worker threads, multiple processes, or an external processing service.”

Remember: Single-threaded JavaScript execution does not mean the entire Node.js runtime is single-threaded.

## Q6. If Node.js is single-threaded, how does it handle thousands of concurrent requests?

Expected interview answer:

“Node.js achieves high concurrency through asynchronous, non-blocking I/O.

Suppose an Express API receives a request that needs data from PostgreSQL. Node.js starts the database operation asynchronously instead of blocking the main JavaScript thread while waiting for the result.

During that time, the event loop can process other requests. Once the database operation completes, the application continues processing the result and sends the response.

This allows one Node.js process to manage many concurrent requests efficiently, especially when the application spends much of its time waiting for I/O.

However, actual capacity depends on workload, available resources, database capacity, and how efficiently the application is implemented.”

Remember: Node.js doesn't wait idly for I/O; it can process other work while the operation is pending.

## Q7. What is non-blocking I/O? Give a concrete example.

Expected interview answer:

“Non-blocking I/O means that our application does not have to stop executing JavaScript while waiting for an I/O operation to finish.

For example, when we use `fs.readFile()` to read a file asynchronously, Node.js can continue executing other code while the file is being read.

When the operation completes, the callback receives the result or error.

This approach improves concurrency because the main JavaScript thread does not remain occupied simply waiting for an I/O operation.”

Example:

```
const fs = require("node:fs");

fs.readFile("data.txt", "utf8", (err, data) => {
  if (err) {
    console.error(err);
    return;
  }

  console.log(data);
});

console.log("Reading file...");
```

Here, `"Reading file..."` can print before the file contents are available.

## Q8. What is the difference between blocking and non-blocking code?

Expected interview answer:

“The main difference is whether the operation prevents further JavaScript execution while it is running.

Blocking code makes the current JavaScript execution wait until the operation completes. For example, `fs.readFileSync()` blocks the thread while reading a file.

Non-blocking code allows the application to continue executing other JavaScript while an asynchronous operation is pending. For example, `fs.readFile()` can read a file asynchronously.

In a backend server, excessive blocking operations can increase response times and reduce the number of requests the server can handle efficiently.”

| Blocking                          | Non-blocking                           |
| --------------------------------- | -------------------------------------- |
| Waits for the operation to finish | Allows other work while I/O is pending |
| Can delay other requests          | Supports higher I/O concurrency        |
| Example: `fs.readFileSync()`      | Example: `fs.readFile()`               |

## Q9. What are the advantages and disadvantages of Node.js over Java or PHP for backend development?

Expected interview answer:

“One major advantage of Node.js is its ability to handle a large number of concurrent I/O operations using asynchronous, non-blocking programming.

It also allows teams to use JavaScript on both the frontend and backend, and its npm ecosystem provides many packages for application development.

Another advantage is that Node.js is well suited for APIs, real-time applications, and services that frequently interact with databases or external APIs.

However, CPU-intensive JavaScript can block the event loop if it is not handled appropriately. Asynchronous code can also become difficult to manage if it is poorly structured, although Promises and `async/await` help with this.

Compared with Java, the best choice depends on the workload, language ecosystem, concurrency requirements, and the team's expertise. Node.js is not automatically better or worse than Java or PHP for every application.”

Remember: Node.js is especially useful for I/O-heavy applications; CPU-heavy workloads require more careful design.

## Q10. When should you NOT use Node.js? What workloads is it poor for?

Expected interview answer:

“I would be careful about choosing Node.js for workloads that require heavy CPU computation on the main JavaScript thread.

For example, complex mathematical calculations, intensive image processing, or video processing could block the event loop and delay other requests.

However, this does not mean Node.js cannot be used for these applications. We can offload CPU-intensive tasks to worker threads, child processes, or separate processing services.

The decision depends on the workload, performance requirements, and the additional complexity introduced by that architecture.”

Remember: The main concern is running heavy CPU-bound work directly on the event-loop thread.

## Q11. What is the Node.js thread pool? What operations use it? What is its default size?

Expected interview answer:

“The Node.js thread pool is managed by libuv and allows certain operations to execute on worker threads instead of blocking the main JavaScript thread.

Operations that commonly use it include many file-system operations, `crypto` operations such as `pbkdf2`, `zlib` compression, and certain DNS operations.

The default thread-pool size is four threads. We can configure it using the `UV_THREADPOOL_SIZE` environment variable.

It is important to understand that not every asynchronous operation uses this thread pool. For example, much network I/O is handled using operating-system facilities rather than a thread from the libuv pool.”

Remember: Default pool size = 4. The thread pool is separate from the main JavaScript thread.

## Q12. How do you change the thread pool size in Node.js?

Expected interview answer:

“We can configure the libuv thread-pool size using the `UV_THREADPOOL_SIZE` environment variable.

For example, on a Unix-like system, we can start our application like this:

```
UV_THREADPOOL_SIZE=8 node app.js
```

This configures the pool to use eight threads instead of the default four.

We should set the variable before Node.js initializes the thread pool. Increasing the pool size is not automatically beneficial because it can increase resource usage and thread contention. I would tune it only after identifying that thread-pool saturation is a real bottleneck.”

Remember: Configure `UV_THREADPOOL_SIZE` before startup, and measure performance before increasing it.

## Q13. What is `process` in Node.js? What are its key properties and methods?

Expected interview answer:

“`process` is a global object that provides information about the currently running Node.js process and allows us to interact with it.

For example, `process.env` lets us access environment variables, `process.argv` provides command-line arguments, and `process.pid` gives us the process ID.

We can also use `process.cwd()` to get the current working directory, `process.memoryUsage()` to inspect memory usage, and `process.uptime()` to check how long the process has been running.

These properties and methods are useful for application configuration, debugging, monitoring, and process management.”

Remember: `process` gives us information about and control over the running Node.js process.

## Q14. What is `global` in Node.js? How does it differ from `window` in the browser?

Expected interview answer:

“`global` is the global object in Node.js, whereas `window` is commonly associated with the browser's window environment.

In a browser, JavaScript can use browser APIs such as the DOM to interact with web pages. Node.js does not provide the browser DOM by default; instead, it provides server-side APIs, such as file-system and process APIs.

Node.js also supports `globalThis`, which is the standard cross-environment reference to the global object.

One important point is that variables declared inside a Node.js module using `const`, `let`, or `var` do not automatically become properties of `global`.”

Example:

```
console.log(globalThis === global); // true in Node.js
console.log(typeof window);         // "undefined" by default in Node.js
```

Remember: Browser → `window` and DOM APIs. Node.js → `global`, `process`, and server-side APIs.

## Q15. What is the difference between `process.exit()` and throwing an uncaught error?

Expected interview answer:

“`process.exit()` explicitly terminates the Node.js process with a specified exit code. For example, `process.exit(1)` indicates that the process is exiting because of an error.

An uncaught exception occurs when an error is thrown and is not handled by the application. Depending on the runtime behavior and any installed handlers, it can result in the process terminating.

The important difference is that calling `process.exit()` directly can terminate the process before pending asynchronous operations have completed.

In production, I would prefer proper error handling and graceful shutdown where possible. If an uncaught exception leaves the application in an unsafe state, I would log the error, perform appropriate cleanup, and allow the process to restart through the process manager.”

Remember: Avoid using `process.exit()` as a routine error-handling mechanism because it can interrupt pending work.

## Q16. What is `process.nextTick()`? How does it compare to `setImmediate()`?

Expected interview answer:

“Both `process.nextTick()` and `setImmediate()` allow us to schedule a callback to run later, but they run at different points in Node.js execution.

`process.nextTick()` schedules a callback to run after the current operation finishes, before Node.js continues to the next event-loop phase.

`setImmediate()` schedules a callback to run in the check phase of the event loop, which follows the poll phase.

One important difference is that repeatedly scheduling `process.nextTick()` callbacks can starve the event loop and delay I/O processing.

I would use these methods only when I need their specific scheduling behavior rather than treating them as interchangeable.”

Example:

```
process.nextTick(() => {
  console.log("nextTick");
});

setImmediate(() => {
  console.log("setImmediate");
});

console.log("sync");
```

The synchronous message prints first, followed by the `nextTick` callback and then the `setImmediate` callback in this example.

Remember: `nextTick` runs before the next event-loop phase; `setImmediate` runs in the check phase.

## Q17. What is `NODE_ENV`? Why is it important?

Expected interview answer:

“`NODE_ENV` is an environment variable commonly used to identify the application's environment, such as development, production, or testing.

For example, when deploying an Express application, we can set `NODE_ENV=production` so that Express and other libraries can use their production-specific behavior.

It can also help us configure logging, debugging, and other environment-dependent settings.

I would normally configure it through the deployment environment rather than hardcoding it in the source code.”

Example:

```
NODE_ENV=production node app.js
```

Remember: `NODE_ENV` helps distinguish development, testing, and production configurations.

## Q18. How do you read environment variables in Node.js? What is `dotenv`?

Expected interview answer:

“In Node.js, we can access environment variables using `process.env`.

For example, if our application needs a database URL or API key, we can read it using `process.env.DATABASE_URL` or `process.env.API_KEY`.

The `dotenv` package is commonly used during local development to load variables from a `.env` file into `process.env`.

This helps us keep configuration separate from application code. In production, environment variables are commonly provided by the deployment platform or a secrets-management system.

Sensitive `.env` files should not be committed to source control.”

Example:

```
require("dotenv").config();

const port = process.env.PORT || 3000;
```

Remember: `process.env` reads configuration; `dotenv` loads local `.env` configuration.

## Q19. What is REPL in Node.js? What is it useful for?

Expected interview answer:

“REPL stands for Read-Eval-Print Loop. It is an interactive environment that allows us to execute JavaScript statements directly from the terminal.

We can start it by running the `node` command without specifying a file.

It reads our input, evaluates the code, displays the result, and waits for the next input.

REPL is useful for quickly testing JavaScript expressions, checking how built-in modules work, trying small pieces of code, and debugging simple problems without creating a separate file.”

Example:

```
node
```

Then enter:

```
2 + 3
```

The output will be:

```
5
```

Remember: REPL is useful for quickly experimenting with JavaScript in the terminal.

## Q20. What is the purpose of `package.json`? What are its key fields?

Expected interview answer:

“`package.json` is the main configuration and manifest file for a Node.js project.

It contains project information such as the name and version, scripts for running commands, dependencies, development dependencies, and other configuration.

For example, we can define a `start` script to run our application or a `dev` script to start the development server.

It also specifies package-related settings, including the module system through fields such as `type`.

Overall, `package.json` helps manage dependencies, scripts, and project configuration in a consistent way.”

Example:

```
{
  "name": "my-backend",
  "version": "1.0.0",
  "type": "commonjs",
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js"
  },
  "dependencies": {
    "express": "^5.0.0"
  }
}
```

Remember: `package.json` defines project metadata, scripts, dependencies, and configuration.

## Q21. What is `package-lock.json`? Why should it be committed to source control?

Expected interview answer:

“`package-lock.json` records the resolved dependency tree, including the specific versions of installed packages and their dependencies.

Even if `package.json` permits a range of versions, the lock file records the versions selected for that installation.

Committing the lock file helps developers and CI/CD pipelines install a consistent dependency tree, reducing differences between local and production environments.

This is especially useful when deploying applications because it makes dependency installation more reproducible.”

Remember: `package.json` describes dependency requirements; `package-lock.json` records the resolved dependency tree.

## Q22. What is the difference between `dependencies` and `devDependencies`?

Expected interview answer:

“The main difference is the purpose of the packages.

`dependencies` contains packages required by the application at runtime. For example, Express and a PostgreSQL driver are typically production dependencies.

`devDependencies` contains packages used mainly during development, testing, linting, or building. Examples include Jest, ESLint, and development tools.

When deploying an application, we can configure the installation process to omit development dependencies if they are not needed at runtime.

Separating these dependencies makes the project's requirements clearer and can reduce the installed production package set.”

Example:

```
npm install express
npm install --save-dev jest
```

Remember: Production runtime packages go in `dependencies`; development and testing tools generally go in `devDependencies`.

## Q23. What is semantic versioning? What is the difference between `^1.2.3` and `~1.2.3`?

Expected interview answer:

“Semantic versioning uses three main numbers: MAJOR, MINOR, and PATCH.

The major version represents incompatible changes, the minor version represents backward-compatible functionality, and the patch version represents backward-compatible bug fixes.

In `package.json`, the caret and tilde symbols specify which versions npm is allowed to select within a version range.

For example, `^1.2.3` allows compatible updates below version `2.0.0`, while `~1.2.3` allows patch updates below version `1.3.0`.

These ranges help us manage dependency updates without automatically accepting every new major version.”

| Version  | Meaning                                         |
| -------- | ----------------------------------------------- |
| `1.2.3`  | Exact version when no range operator is present |
| `^1.2.3` | `>=1.2.3` and `<2.0.0`                          |
| `~1.2.3` | `>=1.2.3` and `<1.3.0`                          |

Remember: Caret generally permits minor and patch updates for a non-zero major version; tilde permits patch updates.

## Q24. What is `npm audit`? When should you run it?

Expected interview answer:

“`npm audit` checks the project's installed dependency tree against known security vulnerability information.

It identifies vulnerable packages and reports details about the issues, including available remediation options when applicable.

I would run it after adding or updating dependencies and include dependency security checks in the CI/CD process.

However, I would review the suggested fixes before applying them because an automatic fix can sometimes introduce breaking changes or require dependency upgrades.”

Example:

```
npm audit
```

To attempt applicable fixes:

```
npm audit fix
```

Remember: `npm audit` identifies known dependency vulnerabilities; fixes should be reviewed and tested.

## Q25. What is the difference between `npm install` and `npm ci`? When do you use `npm ci`?

Expected interview answer:

“Both commands install Node.js dependencies, but they serve slightly different purposes.

`npm install` installs dependencies based on `package.json` and can update the lock file when necessary.

`npm ci` is intended for clean, reproducible installations. It requires a compatible lock file, removes the existing `node_modules` directory, and installs the dependency versions recorded in the lock file.

I would generally use `npm install` during normal development and `npm ci` in CI/CD pipelines, where I want dependency installation to be consistent with the committed lock file.”

Remember: `npm install` is convenient for development; `npm ci` is generally preferred for reproducible automated builds.

## Q26. How does Node.js handle uncaught exceptions? What is `process.on('uncaughtException')`?

Expected interview answer:

“An uncaught exception occurs when JavaScript throws an error that is not handled by an appropriate `try/catch` block or other error-handling mechanism.

Node.js provides the `uncaughtException` process event, which can be used as a last-resort mechanism to record the error and begin shutdown procedures.

However, continuing to run an application after an unexpected uncaught exception may be unsafe because its state could be inconsistent.

In production, I would log the error, perform the necessary cleanup, and allow the process to exit so that a process manager or orchestration platform can restart it.

I would not use this handler as a replacement for normal application-level error handling.”

Remember: Catch expected errors normally; use `uncaughtException` only for last-resort handling and shutdown.

## Q27. What is `process.on('unhandledRejection')`? When is it triggered?

Expected interview answer:

“An unhandled promise rejection happens when a Promise is rejected and the application does not attach appropriate rejection handling.

For example, if an asynchronous database operation fails and I neither await it inside suitable error handling nor attach a `.catch()` handler, it may result in an unhandled rejection.

Node.js provides the `unhandledRejection` process event to help applications detect and log these situations. The process behavior also depends on the Node.js version and runtime configuration; in modern Node.js, an unhandled rejection can cause the process to terminate.

In production code, I would handle expected asynchronous errors using `try/catch` with `async/await` or Promise rejection handlers rather than relying on this event.”

Example:

```
async function getData() {
  try {
    const result = await fetchData();
    return result;
  } catch (error) {
    console.error("Failed to fetch data:", error);
    throw error;
  }
}
```

Remember: Handle Promise rejections at the appropriate point in the application; do not rely on a global event to replace proper error handling.

## Q28. What is the difference between `__dirname` and `__filename`?

Expected interview answer:

“Both `__dirname` and `__filename` are available in CommonJS modules and provide absolute path information about the current module.

`__dirname` gives the absolute path of the directory containing the current file, whereas `__filename` gives the absolute path of the current file itself, including its filename.

For example, if my file is located at `/app/routes/user.js`, `__dirname` would be `/app/routes` and `__filename` would be `/app/routes/user.js`.

In ES modules, these CommonJS variables are not available by default. We can use `import.meta.url` and Node.js URL and path utilities to achieve equivalent results.”

Example:

```
console.log(__dirname);
console.log(__filename);
```

Remember: `__dirname` = containing directory; `__filename` = complete file path.

## Q29. What is `process.argv`? How do you parse command-line arguments?

Expected interview answer:

“`process.argv` is an array containing the command-line arguments passed to the running Node.js process.

The first element is normally the Node.js executable path, and the second element is the script path. Any additional arguments appear after those two elements.

We can use these arguments to customize application behavior without modifying the source code. For more complex command-line interfaces, we can use libraries such as Commander or Yargs.”

Example:

```
console.log(process.argv);
```

Run:

```
node app.js development
```

We can access the custom argument with:

```
const environment = process.argv[2];

console.log(environment);
```

Output:

```
development
```

Remember: `process.argv[2]` is commonly the first custom argument supplied to a script.

## Q30. How do you gracefully shut down a Node.js server?

Expected interview answer:

“Graceful shutdown means stopping a server safely without unnecessarily interrupting requests that are already being processed.

For example, when a deployment platform sends a `SIGTERM` signal, I would first stop accepting new connections. I would then allow ongoing requests to finish within an appropriate shutdown period.

After that, I would close resources such as database connections and other application resources.

Once cleanup is complete, the process can exit. I would also implement a timeout so that the application does not remain stuck indefinitely if some requests or connections fail to close.

This is important during production deployments and restarts because it helps reduce failed requests and resource leaks.”

A simplified example using Node.js HTTP server:

```
const http = require("node:http");

const server = http.createServer((req, res) => {
  res.end("Hello World");
});

server.listen(3000, () => {
  console.log("Server running on port 3000");
});

process.on("SIGTERM", () => {
  console.log("Shutting down...");

  server.close(() => {
    console.log("Server closed");
    process.exit(0);
  });
});
```


---

## 2. Event Loop & Async Model

### Event Loop Phases

# Node.js Backend Interview Questions — Interview-Ready Answers

## Section 2: Event Loop & Async Model

This section covers 27 questions from your attached document. The answers follow the original question order and are written in the style you should use when answering an interviewer: explain the concept, describe how it works, and give a practical example when appropriate.

# Part A: Event Loop Phases

## Q1. Explain the Node.js event loop in detail. What are its phases?

Expected interview answer:

“The event loop is a mechanism that allows Node.js to handle asynchronous operations without blocking the main JavaScript thread while waiting for I/O.

When an asynchronous operation, such as reading a file or receiving a network response, is initiated, Node.js can continue executing other code instead of waiting for that operation to finish.

The event loop coordinates when callbacks associated with completed operations can execute. It has several phases, including timers, pending callbacks, poll, check, and close callbacks.

After JavaScript finishes the current operation, Node.js processes its scheduled microtasks and continues through the event-loop phases.

This architecture allows Node.js to handle many concurrent I/O operations efficiently. However, long-running synchronous JavaScript can block the event loop and delay other requests.”

Remember: The event loop coordinates asynchronous work; it does not make CPU-intensive JavaScript run in parallel.

## Q2. What are the six phases of the Node.js event loop? Describe each.

Expected interview answer:

“The Node.js event loop has six main phases, and each phase handles a particular category of callbacks.

1. Timers: Executes callbacks whose `setTimeout()` or `setInterval()` thresholds have been reached.
2. Pending callbacks: Executes certain I/O callbacks deferred to a later loop iteration, such as some TCP-related error callbacks.
3. Idle and prepare: Used internally by libuv for event-loop preparation.
4. Poll: Processes I/O-related events and callbacks. It can also wait for new I/O events when appropriate.
5. Check: Executes callbacks scheduled using `setImmediate()`.
6. Close callbacks: Executes certain close-event callbacks, such as a socket's `close` event.

The loop moves between these phases as the application runs. Promise callbacks and `process.nextTick()` callbacks are handled through separate scheduling queues rather than being additional event-loop phases.”

Remember this order:

`Timers → Pending callbacks → Idle/Prepare → Poll → Check → Close callbacks`

## Q3. What is the difference between the microtask queue and the macrotask queue?

Expected interview answer:

“The main difference is their scheduling behavior and when their callbacks get a chance to execute.

In Node.js, Promise callbacks, such as those registered with `.then()`, and callbacks scheduled using `queueMicrotask()` are processed through the microtask queue.

Node.js also has a separate `process.nextTick()` queue, which is generally processed before the Promise microtask queue after the current JavaScript operation.

What developers commonly call macrotasks are scheduled operations such as timers, I/O callbacks, and `setImmediate()`. These are associated with different event-loop phases.

Microtasks generally run before Node.js proceeds to the next event-loop phase. However, repeatedly scheduling microtasks or `nextTick` callbacks can delay other work, including I/O.”

Remember: `process.nextTick()` has its own queue; Promise callbacks use the microtask queue; timers and I/O callbacks are handled through event-loop phases.

## Q4. What runs first: `Promise.then()` or `setTimeout(fn, 0)`? Why?

Expected interview answer:

“Normally, a Promise's `.then()` callback runs before a `setTimeout(fn, 0)` callback when both are scheduled during the same synchronous execution.

The reason is that Promise callbacks are microtasks, whereas `setTimeout()` schedules a timer callback.

After the synchronous JavaScript finishes, Node.js processes the relevant microtask queues before moving on to the timer callback.

So, under these conditions, the Promise callback executes first.”

Example:

```
console.log("Start");

setTimeout(() => console.log("Timer"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");
```

Output:

```
Start
End
Promise
Timer
```

Remember: Synchronous code runs first, followed by the Promise callback, then the timer callback in this example.

## Q5. What is the order of execution of `process.nextTick`, `Promise.then`, `setImmediate`, and `setTimeout(0)`?

Expected interview answer:

“First, synchronous JavaScript executes. After the current operation finishes, Node.js processes `process.nextTick()` callbacks before Promise microtasks in the normal case.

After those queues are processed, execution continues through the event loop, where timer callbacks and `setImmediate()` callbacks can execute.

An important point is that I would not claim that `setTimeout(fn, 0)` always runs before `setImmediate()`. Their relative order can depend on the execution context and timing.

For example, inside an I/O callback, `setImmediate()` normally executes before a zero-delay timer scheduled in that callback.

Therefore, I would distinguish the reliable ordering of synchronous code and microtasks from the context-dependent ordering of timers and `setImmediate()`.”

Example:

```
process.nextTick(() => console.log("nextTick"));

Promise.resolve().then(() => console.log("Promise"));

setTimeout(() => console.log("Timeout"), 0);

setImmediate(() => console.log("Immediate"));

console.log("Sync");
```

The beginning of the output is:

```
Sync
nextTick
Promise
```

The relative order of `Timeout` and `Immediate` is not guaranteed for this top-level example.

Remember: Do not memorize a universal execution order for `setTimeout(0)` and `setImmediate()`.

## Q6. What is `process.nextTick()`? Give a practical use case.

Expected interview answer:

“`process.nextTick()` schedules a callback to run after the current JavaScript operation completes, before Node.js continues to the next event-loop phase.

It can be useful when an API needs to defer a callback until the current call stack has finished, while still executing it before normal event-loop callbacks.

For example, it can help an API invoke a callback asynchronously and maintain consistent behavior when the result is immediately available.

However, I would use it carefully because recursively scheduling `process.nextTick()` can prevent the event loop from progressing and delay I/O operations.”

Example:

```
console.log("Start");

process.nextTick(() => {
  console.log("Next tick");
});

console.log("End");
```

Output:

```
Start
End
Next tick
```

Remember: `process.nextTick()` defers execution until the current operation finishes; it does not mean the callback executes immediately in the current call stack.

## Q7. What is `setImmediate()`? How is it different from `setTimeout(fn, 0)`?

Expected interview answer:

“Both methods schedule callbacks for later execution, but they are associated with different parts of the event loop.

`setImmediate()` schedules a callback for the check phase, which follows the poll phase.

`setTimeout(fn, 0)` schedules a timer callback after a minimum delay threshold. It does not mean the callback runs immediately.

When both are scheduled inside an I/O callback, `setImmediate()` normally executes first because the check phase follows the poll phase.

At the top level of a script, however, their relative execution order is not guaranteed.”

Example:

```
const fs = require("node:fs");

fs.readFile(__filename, () => {
  setTimeout(() => console.log("Timeout"), 0);

  setImmediate(() => console.log("Immediate"));
});
```

Here, `Immediate` normally prints before `Timeout`.

Remember: `setImmediate()` is tied to the check phase; `setTimeout()` is tied to the timers phase.

## Q8. Can you starve the event loop using `process.nextTick()`? How?

Expected interview answer:

“Yes. Event-loop starvation can happen if we continuously schedule callbacks using `process.nextTick()`.

For example, if a callback schedules itself again using `process.nextTick()`, Node.js keeps processing the next-tick queue instead of progressing normally through the event-loop phases.

As a result, timers and I/O callbacks can be delayed for a very long time or indefinitely.

This is dangerous in a backend application because incoming requests may not receive timely responses.

To prevent this, I would avoid unbounded recursive scheduling with `process.nextTick()`. For repeated work, I would consider chunking it and yielding through mechanisms such as `setImmediate()`.”

Example of a problematic pattern:

```
function repeat() {
  process.nextTick(repeat);
}

repeat();
```

Remember: An endlessly replenished `nextTick` queue can starve the event loop.

## Q9. What is event-loop blocking? How do you detect and fix it?

Expected interview answer:

“Event-loop blocking happens when JavaScript runs an operation that occupies the main thread for too long, preventing the application from processing other callbacks and requests promptly.

For example, a large synchronous computation or parsing an extremely large JSON payload can increase API response times even when other requests are performing simple operations.

To investigate this, I would monitor event-loop delay and CPU usage, review application logs, and use diagnostic tools such as Node.js `perf_hooks` or Clinic.js.

Once the cause is identified, I would optimize the algorithm, break work into smaller chunks where appropriate, or offload CPU-intensive work to worker threads or child processes.

I would then measure event-loop delay and request latency again to confirm that the fix improves performance.”

Remember: Detect the bottleneck first; then optimize, split, or offload the blocking work.

## Q10. What is the difference between CPU-bound and I/O-bound operations? How does Node.js handle each?

Expected interview answer:

“CPU-bound operations are limited mainly by processing power. Examples include complex mathematical computations, large data transformations, and intensive image processing.

I/O-bound operations spend much of their time waiting for external resources, such as a database, file system, or remote API.

Node.js handles I/O-bound workloads well because asynchronous I/O allows the main JavaScript thread to process other work while an operation is pending.

CPU-intensive JavaScript running on the main thread is different because it can block the event loop.

For CPU-heavy tasks, I would consider worker threads, child processes, or a separate processing service, depending on the workload and architecture.”

| CPU-bound                         | I/O-bound                                       |
| --------------------------------- | ----------------------------------------------- |
| Limited by computation            | Often limited by waiting for external resources |
| Can block the main thread         | Asynchronous I/O allows other work to proceed   |
| Example: complex calculations     | Example: asynchronous database query            |
| Possible solution: worker threads | Possible solution: non-blocking I/O             |

Remember: Node.js is especially effective when operations involve waiting rather than prolonged computation on the main thread.

## Q11. Why is synchronous code like `JSON.parse()` of a huge payload dangerous?

Expected interview answer:

“`JSON.parse()` is synchronous, meaning the JavaScript thread must finish parsing the JSON before it can execute other JavaScript.

If a server receives an extremely large JSON payload, parsing it can consume considerable CPU time and block the event loop.

During that period, other requests, timers, and callbacks may be delayed, which can increase latency and even cause request timeouts.

To address this, I would limit request-body sizes, validate input, avoid unnecessarily large payloads, and consider worker threads or streaming parsers when the workload justifies them.”

Remember: A synchronous operation does not become non-blocking simply because the application uses Node.js.

## Q12. What are common causes of event-loop lag in production?

Expected interview answer:

“Event-loop lag means callbacks are being executed later than expected because the event loop cannot make progress quickly enough.

Common causes include CPU-intensive synchronous operations, large JSON parsing tasks, long-running loops, large object or array transformations, excessive `process.nextTick()` scheduling, and garbage-collection pauses caused by memory pressure.

Excessive synchronous logging can also contribute to the problem.

To troubleshoot it, I would examine event-loop delay metrics, CPU and memory usage, request latency, and profiling data.

After identifying the cause, I would optimize the work, reduce unnecessary memory allocation, or offload CPU-intensive processing where appropriate.”

Remember: Event-loop lag can come from CPU use, memory pressure, or scheduling patterns—not only from database queries.

## Q13. What is the `--max-old-space-size` flag? What does it control?

Expected interview answer:

“The `--max-old-space-size` flag configures the maximum size of V8's old-generation heap, measured in megabytes.

For example, we can start a Node.js application with a larger heap limit using this command:

```
node --max-old-space-size=4096 app.js
```

This sets the old-generation heap limit to approximately 4 GB.

It can help an application that legitimately needs to keep a large amount of data in memory. However, increasing the limit does not fix a memory leak or guarantee better performance.

I would first investigate memory usage and garbage collection, then increase the heap limit only if the application's workload requires it and the host has sufficient memory.”

Remember: This flag controls a V8 heap limit; it does not set the total memory limit for the entire process.

# Part B: Callbacks, Promises & Async/Await

## Q14. What is callback hell? How do you avoid it?

Expected interview answer:

“Callback hell happens when multiple asynchronous operations are nested inside one another, making the code difficult to read, understand, and maintain.

For example, an application might need to fetch a user, retrieve that user's orders, and then fetch payment details for those orders. If each operation uses a nested callback, the code can become deeply indented.

We can avoid callback hell by breaking the logic into smaller functions, using Promises, or using `async/await`.

In modern Node.js applications, I generally prefer `async/await` for sequential asynchronous workflows because it makes the code easier to read and allows us to handle errors using `try/catch`.”

Example:

```
async function getUserDetails(userId) {
  try {
    const user = await getUser(userId);
    const orders = await getOrders(user.id);
    const payments = await getPayments(orders);

    return payments;
  } catch (error) {
    console.error("Failed to fetch user details:", error);
    throw error;
  }
}
```

Remember: Promises and `async/await` help avoid deeply nested callbacks and improve error handling.

## Q15. What are the three ways to handle asynchronous code in Node.js?

Expected interview answer:

“There are three common approaches to handling asynchronous code in Node.js: callbacks, Promises, and `async/await`.

First, callbacks pass a function to be executed when an operation completes. Traditional Node.js APIs often use error-first callbacks.

Second, Promises represent the eventual success or failure of an asynchronous operation. We can handle the result using `.then()` and errors using `.catch()`.

Third, `async/await` provides a more readable syntax for working with Promises. It allows us to write asynchronous workflows in a style similar to synchronous code.

Although all three approaches are useful, I generally prefer `async/await` for most modern application code.”

Example:

```
// Callback
fs.readFile("data.txt", "utf8", (err, data) => {
  if (err) return console.error(err);
  console.log(data);
});

// Promise
fetchData()
  .then(data => console.log(data))
  .catch(error => console.error(error));

// Async/await
async function main() {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

Remember: Callback → function; Promise → `.then()` and `.catch()`; `async/await` → readable Promise-based code.

## Q16. What is the difference between error-first callbacks and Promises?

Expected interview answer:

“Error-first callbacks and Promises are two different ways of handling asynchronous results.

With an error-first callback, the first argument represents the error, and the second argument represents the successful result. If the operation succeeds, the error is generally `null`.

With Promises, a successful operation fulfills the Promise, while a failure rejects it. We can handle fulfillment using `.then()` and rejection using `.catch()`.

Promises are easier to compose across multiple asynchronous operations and provide a more structured way to propagate errors. They also work naturally with `async/await`.”

Example of an error-first callback:

```
fs.readFile("data.txt", "utf8", (err, data) => {
  if (err) {
    return console.error(err);
  }

  console.log(data);
});
```

Example using a Promise:

```
fetchData()
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

Remember: Callbacks pass errors as arguments; Promises represent success or failure through their state.

## Q17. What is `promisify()`? How would you implement it from scratch?

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

## Q18. What is the difference between `async/await` and `.then()` chaining?

Expected interview answer:

“Both `async/await` and `.then()` are ways of working with Promises. The main difference is how the code is written and organized.

With `.then()` chaining, we attach callbacks to handle the result of each Promise. With `async/await`, we can write the same workflow in a more sequential and readable style.

For error handling, `.then()` chains can use `.catch()`, whereas `async/await` commonly uses `try/catch`.

Importantly, `await` does not block the entire Node.js thread. It suspends the execution of the current async function while the awaited Promise settles, allowing other work to proceed.”

Example using `.then()`:

```
getUser()
  .then(user => getOrders(user.id))
  .then(orders => console.log(orders))
  .catch(error => console.error(error));
```

Equivalent approach using `async/await`:

```
async function main() {
  try {
    const user = await getUser();
    const orders = await getOrders(user.id);

    console.log(orders);
  } catch (error) {
    console.error(error);
  }
}
```

Remember: Both use Promises; `async/await` often makes sequential workflows easier to read.

## Q19. What happens when you `await` a non-Promise value?

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

## Q20. How do you run multiple asynchronous operations in parallel in Node.js?

Expected interview answer:

“When multiple independent asynchronous operations do not depend on one another, I can run them concurrently using `Promise.all()`.

For example, an API dashboard might need user details, notifications, and activity information. Instead of awaiting each request sequentially, I can start the operations together and await the resulting Promises.

`Promise.all()` resolves when all its input Promises fulfill. If one rejects, the combined Promise rejects.

If I need the outcome of every operation, including failures, I would consider `Promise.allSettled()` instead.”

Example:

```
async function getDashboard() {
  const [user, notifications, activity] = await Promise.all([
    getUser(),
    getNotifications(),
    getActivity()
  ]);

  return { user, notifications, activity };
}
```

Remember: Use `Promise.all()` for independent operations that can run concurrently.

## Q21. What is the difference between `await Promise.all()` and sequential `await` in a loop?

Expected interview answer:

“The main difference is whether independent operations run concurrently or one after another.

With `Promise.all()`, we start the independent operations and wait for all of them to finish. This can reduce total execution time.

With sequential `await` in a loop, each operation must complete before the next one starts.

For example, if I need to fetch information for ten independent users, running the requests concurrently can be faster than awaiting each request one by one.

However, for large workloads, I would use controlled concurrency instead of launching an unlimited number of operations at once.”

Sequential execution:

```
for (const id of userIds) {
  await getUser(id);
}
```

Concurrent execution:

```
const users = await Promise.all(
  userIds.map(id => getUser(id))
);
```

Remember: Sequential `await` is appropriate when operations depend on one another; concurrent execution is useful when they are independent.

## Q22. What does `Promise.allSettled()` do that `Promise.all()` does not?

Expected interview answer:

“Both methods work with multiple Promises, but they handle failures differently.

`Promise.all()` fulfills when all input Promises fulfill. If any input Promise rejects, the returned Promise rejects without waiting for all the remaining operations to settle.

`Promise.allSettled()` waits until every input Promise has either fulfilled or rejected. It then returns an array describing the result of each operation.

I would use `Promise.all()` when all results are required for success. I would use `Promise.allSettled()` when I need to collect every outcome, such as generating a report about several independent API calls.”

Example:

```
const results = await Promise.allSettled([
  fetchUser(),
  fetchOrders(),
  fetchNotifications()
]);

results.forEach(result => {
  if (result.status === "fulfilled") {
    console.log("Success:", result.value);
  } else {
    console.log("Failure:", result.reason);
  }
});
```

Remember: `Promise.all()` is useful for all-or-fail workflows; `Promise.allSettled()` is useful when every operation's result matters.

## Q23. How do you implement a timeout for an asynchronous operation?

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

## Q24. How do you cancel an in-flight asynchronous operation using `AbortController` and `AbortSignal`?

Expected interview answer:

“`AbortController` provides a way to request cancellation of an asynchronous operation, while its `signal` communicates that cancellation request to an API that supports it.

I create an `AbortController`, pass its signal to the operation, and call `controller.abort()` when I need to cancel it.

For example, in a backend service making an HTTP request to an external API, I could abort the request if it exceeds a timeout or is no longer needed.

The important point is that cancellation depends on the operation supporting the signal. `AbortController` cannot automatically cancel arbitrary JavaScript code or every asynchronous operation.”

Example:

```
const controller = new AbortController();

async function fetchData() {
  try {
    const response = await fetch("https://example.com/api", {
      signal: controller.signal
    });

    return await response.json();
  } catch (error) {
    if (error.name === "AbortError") {
      console.log("Request cancelled");
    } else {
      throw error;
    }
  }
}

fetchData();

// Cancel when needed:
controller.abort();
```

Remember: Create a controller, pass its signal to a compatible API, and call `abort()` to request cancellation.

## Q25. What is `async_hooks`? What is it used for?

Expected interview answer:

“`async_hooks` is a Node.js module that provides hooks for observing the lifecycle of asynchronous resources.

It can help developers understand how asynchronous operations are created and managed, and it has been used to implement request tracing and context propagation.

For example, in a backend application, we might want to associate a request ID with every log entry produced while handling a particular HTTP request, including logs from asynchronous database operations.

Rather than manually passing the request ID through every function, we can use context-propagation mechanisms. For many application-level use cases, Node.js's `AsyncLocalStorage` is a more convenient high-level solution than directly implementing context management with low-level hooks.”

Remember: `async_hooks` helps observe asynchronous resource lifecycles; `AsyncLocalStorage` is commonly useful for carrying context across asynchronous operations.

## Q26. How do you implement a retry mechanism with exponential backoff?

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

## Q27. What is a race condition in asynchronous Node.js code? Give an example.

Expected interview answer:

“A race condition occurs when the result of an operation depends on the timing or ordering of concurrent activities.

Even though JavaScript in a typical Node.js process executes on one main thread, asynchronous operations can still create race conditions when their execution overlaps.

For example, suppose two requests update the same user's account balance. Both requests read the same balance, calculate a new value, and then write their results. One update may overwrite the other, causing a lost update.

To prevent this, I would use an appropriate database-level solution, such as an atomic update, transaction, optimistic concurrency control, or locking, depending on the requirement.”

Consider this conceptual example:

```
async function incrementBalance(userId) {
  const user = await getUser(userId);

  const newBalance = user.balance + 1;

  await updateBalance(userId, newBalance);
}
```

If two requests execute this function concurrently, both could read the same original balance and then write the same incremented balance.

For a database that supports atomic updates, the operation should instead be performed atomically, conceptually like this:

```
UPDATE users
SET balance = balance + 1
WHERE user_id = $1;
```

Remember: Race conditions can occur in asynchronous Node.js applications; protecting shared state often requires atomic operations or database concurrency controls.

# Final Revision Sheet

Here are the key distinctions from this section that you should be able to explain quickly in an interview.

| Concept                | Main point                                                                      |
| ---------------------- | ------------------------------------------------------------------------------- |
| Event loop             | Coordinates callback execution and asynchronous work                            |
| Microtasks             | Promise callbacks and `queueMicrotask()`                                        |
| `process.nextTick()`   | Separate queue processed before Promise microtasks in normal Node.js scheduling |
| `setImmediate()`       | Callback in the check phase                                                     |
| `setTimeout(fn, 0)`    | Timer callback; not guaranteed to precede `setImmediate()`                      |
| Event-loop blocking    | Long-running synchronous work delays callbacks                                  |
| CPU-bound vs I/O-bound | Computation versus waiting for external operations                              |
| Callback vs Promise    | Callback convention versus composable Promise state                             |
| `async/await`          | Syntax for working with Promises                                                |
| `Promise.all()`        | Fails fast when an input rejects                                                |
| `Promise.allSettled()` | Collects all fulfillment and rejection outcomes                                 |
| `Promise.race()`       | Returns the first settled result; does not automatically cancel other work      |
| `AbortController`      | Requests cancellation from APIs that support its signal                         |
| Exponential backoff    | Increases delay between retries                                                 |
| Race condition         | Outcome depends on overlapping operations and their ordering                    |

## What you should focus on first

The most important concepts to practise explaining aloud are the event-loop scheduling order, why CPU-heavy work blocks Node.js, `Promise.all()` versus `Promise.allSettled()`, timeout versus cancellation, and race conditions in database updates.

These are particularly useful because they test not just your knowledge of definitions, but also whether you understand how to apply Node.js in real backend applications.

---

## 3. Streams & Buffers

### Streams

**Q: What are streams in Node.js? Why are they important?**  
Streams are objects that let you read data from a source or write data to a destination continuously. They process data piece by piece (chunks), keeping memory usage low and enabling backpressure handling. Important for I/O operations with large amounts of data (files, network).

**Q: What are the 4 types of streams? Give an example of each.**  
1. **Readable**: `fs.createReadStream()` — data can be read from it.  
2. **Writable**: `fs.createWriteStream()` — data can be written to it.  
3. **Duplex**: `net.Socket` — both readable and writable.  
4. **Transform**: `zlib.createGzip()` — a Duplex stream that modifies or transforms data as it passes through.

**Q: How do you read a large file in Node.js without running out of memory?**  
Use `fs.createReadStream()` with an appropriate `highWaterMark` and pipe it to a writable stream or process chunks via the `'data'` event, without loading the entire file into memory.

**Q: What is `pipe()`? How does it work internally?**  
`pipe()` connects a readable stream to a writable stream, automatically managing the flow and backpressure. It reads from the readable, writes to the writable, and pauses/resumes the readable when the writable's buffer is full, preventing memory bloat. It returns the destination stream to enable chaining.

**Q: What is backpressure in Node.js streams? How do you handle it?**  
Backpressure occurs when a writable stream cannot process data as fast as it is being provided, causing a buildup. `pipe()` handles it by pausing the readable. Manually, listen for the `'drain'` event on the writable and call `readable.resume()` or use `readable.pipe(writable)`. When implementing custom streams, respect the return value of `write()` (false indicates backpressure) and wait for `'drain'`.

**Q: What is the difference between flowing mode and paused mode in readable streams?**  
- **Flowing mode**: data is automatically pushed to the consumer via the `'data'` event. You attach a `'data'` listener or call `resume()`.  
- **Paused mode**: you must call `read()` explicitly to read chunks. A readable starts in paused mode; adding a `'data'` listener switches to flowing.

**Q: What is `pipeline()` and how does it differ from `pipe()`? Why is `pipeline()` preferred?**  
`stream.pipeline(source, ...transforms, destination, callback)` pipes streams together and properly handles errors and cleanup. Unlike `pipe()`, it automatically destroys all streams if one errors, preventing resource leaks. `pipeline` is the modern, safer alternative.

**Q: How do you implement a custom Transform stream?**  
Extend `Transform` and implement `_transform(chunk, encoding, callback)`.
```javascript
const { Transform } = require('stream');
const upperCaseTransform = new Transform({
  transform(chunk, encoding, callback) {
    this.push(chunk.toString().toUpperCase());
    callback();
  }
});
```

**Q: What is the `highWaterMark` option in streams?**  
`highWaterMark` sets the internal buffer size limit (in bytes for binary streams, object count for object mode). When the buffer reaches this threshold, the stream signals backpressure (writable returns false, readable pauses).

**Q: How do you handle errors in a piped stream chain?**  
Attach an `'error'` listener to each stream in the chain, or use `pipeline()` which propagates errors to its callback. Without this, errors can silently crash the process.

**Q: What are object mode streams?**  
Streams in object mode handle JavaScript objects instead of Buffers/strings. Activated by `{ objectMode: true }`. Each chunk is a discrete object. Used for streaming database records or structured data.

**Q: What is the difference between `stream.Readable.from()` and creating a custom readable?**  
`stream.Readable.from(iterable)` creates a readable from an iterable (array, generator) simply. A custom readable requires extending `Readable` and implementing `_read()`. The former is convenient for wrapping existing data sources.

**Q: When would you use streams vs loading a file entirely into memory?**  
Use streams when the file is larger than the available memory, or when you want to process data incrementally (e.g., transformation, compression, network transfer). Loading into memory is simpler for small files.

**Q: What is `zlib`? How do you compress/decompress data using streams?**  
`zlib` provides compression/decompression functionality (gzip, deflate, brotli). Use `zlib.createGzip()` as a transform stream:
```javascript
const gzip = zlib.createGzip();
fs.createReadStream('input.txt').pipe(gzip).pipe(fs.createWriteStream('output.txt.gz'));
```

### Buffers

**Q: What is a Buffer in Node.js? How does it differ from an array?**  
Buffer is a class that provides a way to work with raw binary data directly. It is a fixed-size chunk of memory allocated outside the V8 heap. Unlike JavaScript arrays, Buffer stores bytes (0-255), is not resizable, and has methods to read/write integers, floats, etc. It is the foundation of I/O data handling.

**Q: Why does Node.js need Buffers? What is binary data?**  
Buffers are needed because JavaScript originally did not handle binary data efficiently. Node.js deals with TCP streams, file system, etc., which involve raw bytes. Buffers provide a fast, native way to manipulate these bytes.

**Q: How do you create a Buffer? What is the difference between `Buffer.alloc()` and `Buffer.allocUnsafe()`?**  
- `Buffer.alloc(size)`: creates a buffer of given size filled with zeros (safe, initialised).  
- `Buffer.allocUnsafe(size)`: allocates memory without initialization, may contain old sensitive data, but is faster. Use only when you will immediately overwrite the buffer.

**Q: How do you convert between a Buffer and a string?**  
- Buffer to string: `buf.toString('utf8')`  
- String to Buffer: `Buffer.from('hello', 'utf8')`

**Q: What is encoding? What are the common encodings in Node.js? (`utf8`, `base64`, `hex`, `binary`)**  
Encoding specifies the character encoding used to interpret binary data into strings. Common: `utf8` (default), `base64`, `hex`, `latin1` (binary). Different encodings represent bytes differently.

**Q: How do you convert a file to base64 using Buffers?**  
Read file into a Buffer, then convert to base64: `const base64 = fs.readFileSync(file).toString('base64');`  
For large files, use streams: read chunk, convert, and concatenate base64 strings (careful with newlines).

---

## 4. Modules System

### CommonJS vs ES Modules

**Q: What is the CommonJS module system? How does `require()` work internally?**  
CommonJS defines a module format used by Node.js by default (`require`, `module.exports`). `require()` resolves the file path, checks cache, reads the file, wraps it in a function `(function(exports, require, module, __filename, __dirname) { ... })`, executes it, and returns `module.exports`. Modules are cached.

**Q: What is the module cache in Node.js? What happens when you `require` the same module twice?**  
Node caches the result of `require()` in `require.cache`. Subsequent requires return the same cached exports, meaning the module code executes only once. This ensures singletons and performance. Use `delete require.cache[key]` to force reload.

**Q: What is the difference between CommonJS (`require/module.exports`) and ES Modules (`import/export`)?**  
- CJS: synchronous, dynamic, can be called conditionally; exports are copies of values.  
- ESM: static, asynchronous, `import` statements are hoisted; exports are live bindings; better tree-shaking; `import()` dynamic expression supported.  
CJS is default, ESM requires `"type": "module"` or `.mjs` extension.

**Q: How do you use ES Modules in Node.js? What is the `"type": "module"` field in `package.json`?**  
Set `"type": "module"` in `package.json` to treat `.js` files as ES modules. Alternatively, use `.mjs` extension. Without this, `.js` is CJS. Use `import`/`export` syntax.

**Q: What is the difference between `module.exports` and `exports`?**  
`exports` is a shorthand reference to `module.exports`. If you assign a new value to `exports`, it breaks the reference, and only `module.exports` is returned. So `exports = function(){}` will not work; always use `module.exports` to export a constructor or function directly. `exports.prop = ...` works because it mutates the object.

**Q: Can you use `require` inside a conditional statement? Can you use `import` conditionally?**  
`require()` can be used conditionally because it's a function. Static `import` declarations cannot be conditional (must be at top level), but dynamic `import()` can be used anywhere.

**Q: What is dynamic `import()`? When would you use it?**  
`import()` is a function-like expression that returns a promise for the module. It allows on-demand lazy loading, code-splitting, or conditional imports. Use when loading heavy modules only when needed.

**Q: What is circular dependency in Node.js modules? How does Node handle it?**  
Circular dependency: Module A requires B, and B requires A. Node handles it by returning an incomplete exports object for the module that is still being executed, avoiding infinite recursion, but this can lead to unexpected `undefined` values. Avoid circular dependencies.

**Q: What is the difference between a built-in module, an npm package, and a local module?**  
- Built-in: shipped with Node.js (e.g., `fs`, `http`).  
- npm package: installed from npm registry into `node_modules`.  
- Local module: your own files referenced by relative or absolute path.

**Q: How does Node.js resolve module paths? (the module resolution algorithm)**  
When `require(x)` is called:
1. If x is a core module, return it.
2. If x starts with `./`, `../`, or `/`, resolve as file (add extensions `.js`, `.json`, `.node`) or directory (look for `index.js` or `package.json` `main` field).
3. Otherwise, look in `node_modules` directories moving up the directory tree.
ESM has similar algorithm but with different extension resolution.

**Q: What is `__esModule` interop?**  
`__esModule` is a flag used by transpilers (like Babel) to mark an object as an ES module default export when importing into CommonJS. It helps with interop between CJS and ESM, ensuring the default import works as expected.

**Q: What is tree shaking? Why does it only work with ES Modules?**  
Tree shaking removes dead code from bundles. ESM `import`/`export` are static (determined at parse time), allowing bundlers to analyze which exports are unused. CJS `require()` is dynamic, making static analysis impossible, so tree shaking cannot be reliably applied.

---

## 5. Express.js & Middleware

### Core Express

**Q: What is Express.js? Why is it used with Node.js?**  
Express.js is a minimal, flexible web application framework for Node.js, providing a robust set of features for building web and mobile APIs. It simplifies routing, middleware integration, request/response handling, and templating.

**Q: What is the request-response lifecycle in Express?**  
A request enters Express, goes through a series of middleware functions and route handlers (in the order they are defined), and eventually sends a response. Middleware can modify `req` and `res`, end the cycle, or call `next()` to pass control to the next middleware.

**Q: What is middleware in Express? How does the middleware chain work?**  
Middleware functions have access to `req`, `res`, and `next`. They execute sequentially; each middleware can end the request or call `next()`. This chaining allows modular handling (logging, auth, body parsing, routing).

**Q: What does `next()` do in middleware? What happens if you don't call it?**  
`next()` passes control to the next middleware in the stack. If not called, the request hangs (unless a response is sent). In error-handling middleware, `next(err)` sends the error to the error handler.

**Q: What is the difference between `app.use()` and `app.get()` / `app.post()`?**  
`app.use()` mounts middleware for all HTTP methods at a specified path (or globally). `app.get()`, `app.post()` handle specific HTTP methods on a path.

**Q: What is the difference between application-level, router-level, and error-handling middleware?**  
- Application-level: bound to `app` instance (e.g., `app.use`).  
- Router-level: bound to `express.Router()`.  
- Error-handling: takes four arguments `(err, req, res, next)`, defined after other middleware.

**Q: How do you create a router in Express? Why would you use `express.Router()`?**  
```javascript
const router = express.Router();
router.get('/users', ...);
module.exports = router;
```
Router enables modular route definitions, keeping code organized. Use it to mount sub-applications.

**Q: What is the difference between `req.params`, `req.query`, and `req.body`?**  
- `req.params`: route parameters (e.g., `/users/:id` → `req.params.id`).  
- `req.query`: query string parameters (e.g., `?name=foo` → `req.query.name`).  
- `req.body`: parsed request body (requires body-parser middleware, e.g., `express.json()`).

**Q: How do you serve static files in Express?**  
`app.use(express.static('public'))` serves files from the `public` directory. Options can set cache control, etc.

**Q: What is `express.json()` middleware? What did `body-parser` used to do?**  
`express.json()` parses incoming requests with JSON payloads, populating `req.body`. It's built-in since Express 4.16+, replacing the separate `body-parser` package.

**Q: What is the order of middleware execution? Does order matter?**  
Yes, the order in which middleware is defined determines the execution order. General pattern: global middleware (logging, parsing), then route-specific middleware, then error-handling middleware last.

**Q: How do you implement error-handling middleware in Express? (4-argument signature)**  
Define a middleware with `(err, req, res, next)`. Express recognizes error handlers by the four arguments. Inside, send appropriate status code and error message. Ensure it's placed after all other routes.
```javascript
app.use((err, req, res, next) => {
  res.status(err.status || 500).json({ error: err.message });
});
```

**Q: How do you handle 404 errors in Express?**  
Add a catch-all middleware at the end of your routes: `app.use((req, res, next) => { res.status(404).send('Not Found'); });`

**Q: What is `res.json()` vs `res.send()` vs `res.end()`?**  
- `res.json(obj)`: sends JSON response, sets Content-Type to application/json.  
- `res.send(body)`: automatically sets Content-Type based on body type (string, Buffer, object).  
- `res.end()`: ends the response without sending data (or after raw writing with `res.write()`).

**Q: What is `res.locals`? What is it used for?**  
`res.locals` is an object that holds response-local variables scoped to the request, accessible only to the view(s) rendered during that request/response cycle. Useful for passing data to templates.

**Q: How do you implement request timeout middleware?**  
Create middleware that sets a timer; if the response isn't finished after a certain time, call `req.destroy()` or `res.status(408).send('Request Timeout')`. You can use `req.setTimeout` or a library like `express-timeout`.

**Q: What is `express-async-errors` / `express-async-handler`? Why is it needed?**  
Express does not catch errors thrown inside async route handlers automatically. If an async function throws, the error is lost. `express-async-handler` wraps an async function to catch rejections and pass them to `next`. `express-async-errors` monkey-patches Express to propagate unhandled rejections, but explicit wrapping is safer.

**Q: What is `helmet`? What HTTP headers does it set?**  
Helmet helps secure Express apps by setting various HTTP headers: `Content-Security-Policy`, `X-Content-Type-Options: nosniff`, `X-Frame-Options`, `Strict-Transport-Security`, `X-DNS-Prefetch-Control`, etc.

**Q: What is `morgan`? What does request logging look like in production?**  
Morgan is an HTTP request logger middleware. In production, use combined format or custom JSON logs. It outputs request method, URL, status, response time, etc.

**Q: What is `compression` middleware? What does it do?**  
`compression` gzip/deflates response bodies to reduce network payload size, improving performance. It adds a `Content-Encoding` header. Trade-off: CPU overhead.

**Q: What is `cors` middleware? When and how do you configure it?**  
`cors` middleware enables Cross-Origin Resource Sharing. Configure it with allowed origins, methods, headers, credentials. Use restrictive policies, not `*` for production.

**Q: How do you implement rate limiting in Express? (e.g., `express-rate-limit`)**  
Use `express-rate-limit`: `app.use(rateLimit({ windowMs: 15*60*1000, max: 100 }));` This returns 429 when exceeded. For distributed systems, use a store like `rate-limit-redis`.

**Q: How do you validate request bodies in Express? (`Joi`, `zod`, `express-validator`)**  
Create a validation middleware that checks `req.body` against a schema, and if invalid, returns 400 with error details. Example with Joi: `const { error } = schema.validate(req.body); if (error) return res.status(400).json(...);`

**Q: What is graceful shutdown in an Express app? How do you implement it?**  
Graceful shutdown stops accepting new connections, allows ongoing requests to finish, then closes. Implementation: listen for SIGTERM, call `server.close()`, wait for active connections to drain (using `stoppable` or manual tracking), then exit.

**Q: What is the difference between `app.listen()` and `http.createServer(app).listen()`?**  
`app.listen()` is a convenience wrapper that creates an `http.Server`, calls `listen` on it, and returns the server. Using `http.createServer(app).listen()` allows you more control (e.g., attaching WebSocket server to the same HTTP server). Both are equivalent.

**Q: How do you structure a large Express application? (folder structure, separation of concerns)**  
Common structure:  
- `routes/` — route definitions  
- `controllers/` — request handlers  
- `services/` — business logic  
- `models/` — data access  
- `middleware/` — custom middleware  
- `config/` — environment configuration  
- `utils/` — utilities  
- `app.js` — Express setup, `server.js` — entry point.

**Q: What is `res.cookie()` vs setting the `Set-Cookie` header manually?**  
`res.cookie()` sets a cookie with options (domain, path, maxAge, httpOnly, secure, sameSite) and automatically creates the `Set-Cookie` header. Manually you'd craft the header string, but `res.cookie()` is safer and simpler.

**Q: How do you handle file uploads in Express? (`multer`)**  
Multer is middleware for handling `multipart/form-data`. Configure storage (disk or memory), limits. Add to route: `upload.single('avatar')`. Access file via `req.file`.

**Q: What is `express-session`? How does it work?**  
`express-session` creates a session middleware that stores session data server-side, identified by a cookie (session ID). It populates `req.session`. Use a store (e.g., Redis) for production. It keeps state between HTTP requests.

---

## 6. REST API Design

### Principles & Best Practices

**Q: What is REST? What are the 6 constraints of REST architecture?**  
REST (Representational State Transfer) is an architectural style. Constraints:
1. Client-server separation.
2. Statelessness: each request must contain all necessary information.
3. Cacheability: responses must indicate whether they are cacheable.
4. Uniform interface (resource identification, manipulation through representations, self-descriptive messages, HATEOAS).
5. Layered system.
6. (Optional) Code on demand.

**Q: What is the difference between REST and RPC?**  
REST is resource-oriented, using standard HTTP methods and URLs to represent resources. RPC (Remote Procedure Call) is action-oriented, invoking specific functions with parameters. REST leverages HTTP semantics; RPC often uses custom methods (like `/getUser`). gRPC is a modern RPC framework.

**Q: What is statelessness in REST? Why is it important?**  
Statelessness means the server does not store client context between requests. Each request must be self-contained (authentication, state). This simplifies scaling and reliability, as any server can handle any request without session affinity.

**Q: What does idempotency mean? Which HTTP methods are idempotent?**  
An idempotent operation produces the same result even if called multiple times. Idempotent HTTP methods: GET, HEAD, PUT, DELETE, OPTIONS, TRACE. POST is not idempotent.

**Q: What is the difference between `PUT` and `PATCH`?**  
PUT replaces the entire resource (or creates if absent) with the request payload; it is idempotent. PATCH applies partial modifications; it is not necessarily idempotent (depends on instructions).

**Q: When do you use `POST` vs `PUT`?**  
POST is used to create a new resource when the server determines the URI (or for non-idempotent actions). PUT is used to create or replace a resource at a specific URI known by the client. PUT requires the full resource representation.

**Q: What are the correct HTTP status codes to use? Give examples for 2xx, 3xx, 4xx, 5xx.**  
- 200 OK: success
- 201 Created: resource created
- 204 No Content: success with no body
- 301 Moved Permanently, 302 Found
- 304 Not Modified (caching)
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 409 Conflict
- 422 Unprocessable Entity
- 429 Too Many Requests
- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable

**Q: When do you return `200` vs `201` vs `204`?**  
- 200: standard success with response body.
- 201: after successful creation, often with a Location header.
- 204: success but no content to return (e.g., DELETE, successful update without body).

**Q: When do you return `400` vs `401` vs `403` vs `404` vs `422` vs `409`?**  
- 400: malformed request syntax (invalid JSON, missing required field).
- 401: authentication required or failed.
- 403: authenticated but not allowed (forbidden).
- 404: resource not found.
- 422: semantic validation errors (well-formed but invalid data).
- 409: conflict with current state (duplicate, stale version).

**Q: What is HATEOAS?**  
Hypermedia as the Engine of Application State. Responses include links to related resources/actions, allowing clients to navigate the API dynamically. Rarely fully implemented in practice but a principle of REST.

**Q: How do you version an API? What are the different strategies? (URI versioning, header versioning)**  
- URI versioning: `/api/v1/users`, `/api/v2/users`. Simple, explicit.
- Header versioning: `Accept: application/vnd.company.v2+json`. Cleaner URLs, but harder to browse.
- Query parameter: `?version=2`.  
Choose based on client needs.

**Q: How do you design pagination for a REST API? (offset-based vs cursor-based)**  
- Offset-based: `?offset=0&limit=20`. Simple but inefficient with large offsets, susceptible to drift.
- Cursor-based: `?cursor=abc123&limit=20`. Encodes position, more stable for large, real-time datasets. Often implemented with an opaque cursor (e.g., base64 encoded timestamp or ID).

**Q: What is cursor-based pagination? When is it better than offset-based?**  
Cursor-based pagination returns a cursor pointing to the next item, avoiding the performance penalty of counting rows for offsets. Better for large, constantly updated datasets (e.g., social media feeds), as it maintains consistency despite insertions/deletions.

**Q: How do you design filtering, sorting, and searching for a REST API?**  
- Filtering: query parameters `?status=active&role=admin`. Use bracket notation for range `?price[lte]=100`.  
- Sorting: `?sort=-created_at,+name` (desc, asc).  
- Searching: `?q=keyword` for full-text, or field-specific `?name=John`.  
Validate and sanitize parameters.

**Q: What is the difference between `/users/:id/posts` and `/posts?userId=:id`?**  
Both return posts belonging to a user. `/users/:id/posts` emphasizes the relationship as a nested resource, typically cleaner for parent-child relations. `/posts?userId=:id` is a filtered collection. Nested can become deeply nested and less flexible; filtering is simpler for complex queries.

**Q: What is request/response envelope vs plain JSON body? When do you use each?**  
Envelope wraps data in a consistent structure (e.g., `{ success: true, data: {...}, meta: {...}, errors: null }`). Plain JSON returns only the resource. Envelope is useful for metadata (pagination, error details), but increases payload. Many APIs use plain JSON for success and envelope for errors.

**Q: How do you handle partial responses (field selection) in a REST API?**  
Allow clients to request specific fields via query parameter: `?fields=id,name,email`. In the response, include only those fields. This reduces payload size.

**Q: How do you design a batch API endpoint?**  
POST `/batch` with a body containing an array of operations, each with method, path, body. Execute in order (or parallel) and return an array of responses. Example: `{ ops: [ { method: 'POST', path: '/users', body: {...} }, ... ] }`. Consider partial failures.

**Q: How do you implement API rate limiting? What headers do you return?**  
Use middleware to track request count per API key/IP. Return `429 Too Many Requests`. Include headers: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` (Unix timestamp when quota resets).

**Q: What is API idempotency key? When is it used?**  
An idempotency key is a unique value sent by the client to make POST/PATCH requests idempotent. The server stores the key and the response; if the same key is received again, the same response is returned without re-executing the operation. Essential for payments and safe retries.

**Q: How do you document a REST API? (Swagger/OpenAPI, Postman)**  
Use OpenAPI specification (formerly Swagger) to describe endpoints, request/response schemas. Tools like `swagger-jsdoc` + `swagger-ui-express` can generate interactive docs from JSDoc comments. Postman collections can also document APIs.

**Q: What is OpenAPI/Swagger? How do you generate docs from code?**  
OpenAPI is a specification for describing REST APIs. You can write the spec manually (YAML/JSON) or generate it from code annotations (JSDoc with `swagger-jsdoc`, or using TypeScript decorators with `tsoa`). Then serve via `swagger-ui`.

**Q: How do you handle CORS in a REST API?**  
Set appropriate `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers` headers. For preflight (OPTIONS), respond with `204`. Use `cors` middleware to configure.

**Q: What is the difference between a monolithic API and a BFF (Backend for Frontend)?**  
Monolithic API serves all clients equally. BFF creates separate backend services tailored to specific frontend experiences (mobile, web), aggregating data and reducing over-fetching. BFF is a pattern in microservices to avoid chatty APIs.

---

## 7. Authentication & Authorization

### Authentication

**Q: What is the difference between authentication and authorization?**  
Authentication verifies who you are (credentials). Authorization determines what you are allowed to do (permissions).

**Q: What is session-based authentication vs token-based authentication?**  
Session-based: server stores session data, client holds session ID in cookie. Server looks up session each request.  
Token-based: client holds a token (JWT), server verifies token without storing session state; stateless.

**Q: What is JWT (JSON Web Token)? What are its three parts?**  
JWT is a compact, URL-safe token for claims. It consists of: Header (algorithm & type), Payload (claims), Signature (signed with secret or private key). Format: `header.payload.signature`, base64url encoded.

**Q: How does JWT authentication work end-to-end? (sign, send, verify)**  
1. Client sends credentials.  
2. Server validates, creates JWT with user info and expiry, signs it, sends back.  
3. Client stores token, sends it in `Authorization: Bearer <token>` header.  
4. Server verifies signature, decodes claims, and authorizes request.

**Q: What is the difference between `HS256` and `RS256` signing algorithms in JWT?**  
- HS256: HMAC with SHA-256, symmetric secret key (same key signs and verifies). Simpler but requires sharing secret between parties.  
- RS256: RSA with SHA-256, asymmetric (private key signs, public key verifies). Better for distributed systems, allows key rotation without exposing private key.

**Q: What are the security risks of JWT? How do you mitigate them?**  
- Token theft: use short expiration, HTTPS, store securely (HttpOnly, Secure cookie).  
- Sensitive data in payload: payload is only base64 encoded, not encrypted; never put secrets.  
- No built-in revocation: implement a blacklist or use short-lived tokens with refresh.  
- Weak signing key: use strong keys, rotate regularly.

**Q: Where should you store JWT on the client? (localStorage vs HttpOnly cookie — trade-offs)**  
- localStorage: vulnerable to XSS; JavaScript can access it.  
- HttpOnly cookie: not accessible via JS, mitigates XSS, but susceptible to CSRF (if not `SameSite`). Use `SameSite=Strict/Lax` and CSRF tokens. Preferred for security.

**Q: How do you implement JWT refresh tokens? What is the refresh token rotation pattern?**  
Access token short-lived (e.g., 15 min), refresh token long-lived (e.g., 7 days). On access token expiry, client sends refresh token to get a new access token. Refresh token rotation: each refresh issues a new refresh token and invalidates the old one. This limits the window of token reuse.

**Q: What is the difference between access token and refresh token?**  
Access token: used to access resources, short lifespan. Refresh token: used to obtain new access tokens, longer lifespan, stored securely. The server can revoke refresh tokens.

**Q: How do you invalidate/revoke a JWT before it expires?**  
JWT is stateless; to revoke, maintain a blacklist (in Redis or DB) of tokens (by `jti` claim) until they expire. Check the blacklist on each request. Alternatively, use short-lived tokens and rely on token expiration.

**Q: What is OAuth 2.0? What are the 4 grant types?**  
OAuth 2.0 is an authorization framework for delegated access. Grant types:
1. Authorization Code (most secure, with server-side app).
2. Implicit (deprecated).
3. Resource Owner Password Credentials (deprecated).
4. Client Credentials (machine-to-machine).
Plus Device Code, Refresh Token.

**Q: What is the Authorization Code flow with PKCE? When is it used?**  
PKCE (Proof Key for Code Exchange) enhances the Authorization Code flow for mobile/SPA clients that cannot securely store a client secret. It uses a code verifier and challenge to prevent authorization code interception.

**Q: What is OpenID Connect (OIDC)? How does it extend OAuth 2.0?**  
OIDC is an identity layer on top of OAuth 2.0. It adds an ID token (JWT) with user identity claims, standardizing authentication. OAuth 2.0 alone is for authorization; OIDC enables single sign-on (SSO).

**Q: What is Passport.js? How do you implement a `passport-jwt` strategy?**  
Passport.js is authentication middleware for Node.js. To use JWT: configure `JwtStrategy` from `passport-jwt` with `secretOrKey` and a JWT extractor (from header). In route, use `passport.authenticate('jwt', { session: false })`. The strategy verifies token, attaches user to `req.user`.

**Q: How do you implement Google OAuth login in a Node.js app?**  
Use `passport-google-oauth20`. Register app in Google Cloud Console to get client ID/secret. Passport handles redirect and callback; exchange code for tokens, fetch user profile, create/find user in DB, issue session or JWT.

**Q: What is bcrypt? How do you hash and compare passwords with it?**  
bcrypt is a password hashing function with salt and cost factor. Hash: `const hash = await bcrypt.hash(password, saltRounds);`. Compare: `const match = await bcrypt.compare(password, hash);`. bcrypt is slow by design to resist brute-force.

**Q: What is the difference between encryption and hashing?**  
- Encryption is reversible with a key; transforms data into ciphertext.  
- Hashing is one-way, irreversible; produces fixed-size digest. Used for integrity and password storage.

**Q: What is salting a password? Why is it necessary?**  
A salt is a random value added to a password before hashing. It ensures that identical passwords produce different hashes, preventing rainbow table attacks and revealing duplicate passwords. bcrypt handles salting automatically.

**Q: What is `crypto.timingSafeEqual()`? Why is it important for authentication?**  
It compares two buffers in constant time, preventing timing attacks where an attacker can guess secrets by measuring response time differences. Essential for comparing tokens, API keys, or passwords.

**Q: How do you implement magic link (passwordless) authentication?**  
User enters email; server generates a signed, time-limited token, sends an email with a link containing the token. User clicks link; server verifies token, creates session/JWT. Eliminates password storage.

**Q: What is MFA (Multi-Factor Authentication)? How do you implement TOTP?**  
MFA requires two or more verification factors. TOTP (Time-based One-Time Password) uses a shared secret and the current time to generate a 6-digit code. Use `speakeasy` library to generate secret, verify token. Show QR code for Google Authenticator.

### Authorization

**Q: What is RBAC (Role-Based Access Control)? How do you implement it in Express?**  
RBAC assigns permissions to roles, and users are assigned roles. In Express, create middleware that checks `req.user.role` against required roles for the route. e.g., `authorize('admin', 'editor')` middleware.

**Q: What is ABAC (Attribute-Based Access Control)?**  
ABAC evaluates attributes of the user, resource, and environment against policies. More fine-grained than RBAC. Example: "User can edit document if userId matches document.owner and time is within business hours."

**Q: How do you implement permission-based middleware in Express?**  
Define a middleware that checks specific permissions from `req.user.permissions`. For example, `checkPermission('write:article')`. Permissions can be stored in JWT or DB.

**Q: What is the principle of least privilege? How do you apply it in API design?**  
Grant only the minimum necessary permissions to perform a task. In APIs: restrict endpoints to specific roles, limit data returned, validate permissions per operation, avoid exposing admin endpoints publicly.

---

## 8. Databases — MongoDB & Mongoose

### MongoDB

**Q: What is MongoDB? How does it differ from relational databases?**  
MongoDB is a document-oriented NoSQL database that stores data in flexible, JSON-like BSON documents. Differences: schema-less/ flexible schema, denormalization common, horizontal scaling via sharding, no joins in the traditional sense (use `$lookup`), ACID transactions available for replica sets.

**Q: What are documents and collections in MongoDB?**  
A document is a record (analogous to a row) stored as BSON. A collection is a grouping of documents (analogous to a table) with no enforced schema.

**Q: What is a BSON document? How does it differ from JSON?**  
BSON (Binary JSON) extends JSON with additional data types (Date, ObjectId, binary) and is efficient for encoding and decoding. It is used internally by MongoDB.

**Q: What are the common MongoDB data types?**  
String, Number (Int, Long, Double), Boolean, Date, ObjectId, Array, Object, Binary data, Timestamp, Regular Expression, Null.

**Q: What is the `_id` field? How is an ObjectId generated?**  
Every document must have an `_id` field as primary key. If not provided, MongoDB generates a unique ObjectId (12 bytes: timestamp, machine id, process id, counter), ensuring global uniqueness and sortability.

**Q: What is an index in MongoDB? Why are indexes important?**  
Indexes support efficient query execution by allowing MongoDB to find data without scanning the entire collection. Without indexes, MongoDB performs a collection scan. They dramatically improve read performance but add write overhead.

**Q: What types of indexes does MongoDB support?**  
Single field, compound (multiple fields), multikey (for arrays), text (for full-text search), geospatial (2d, 2dsphere), hashed (for sharding), TTL (auto-delete after time), sparse, partial, unique.

**Q: What is the explain() method? How do you use it to diagnose slow queries?**  
`collection.find().explain('executionStats')` returns query plan details: which index used (or COLLSCAN), execution time, documents examined vs returned. Helps identify missing indexes or inefficient queries.

**Q: What is a covered query in MongoDB?**  
A query fully satisfied by an index without reading documents. All queried fields and conditions are part of the index. This results in high performance as only the index is scanned.

**Q: What is the aggregation pipeline? Name 5 common stages and what they do.**  
Aggregation pipeline processes data in stages, where each stage transforms documents. Common stages:
- `$match`: filters documents.
- `$group`: groups by a key, calculates aggregations.
- `$project`: reshapes documents (include/exclude fields, computed fields).
- `$sort`: sorts documents.
- `$limit` / `$skip`: pagination.

**Q: What is `$lookup`? How does it perform a join?**  
`$lookup` performs a left outer join with another collection. It adds an array field containing matching documents from the joined collection. Example: join orders with users.

**Q: What is `$facet`? When would you use it?**  
`$facet` processes multiple aggregation pipelines within a single stage, enabling multi-faceted computations (e.g., count by category and top products) and returning separate result arrays in one pass.

**Q: What is the difference between `find()` and `aggregate()`?**  
`find()` returns documents matching a query, with optional projection and sort, but no complex transformations. `aggregate()` provides a pipeline for advanced data processing, grouping, joining, reshaping.

**Q: What are MongoDB transactions? When are they used?**  
Transactions provide ACID guarantees across multiple documents/collections within a replica set. Use when you need atomicity for writes that must all succeed or fail together (e.g., transfer money between accounts). Not needed for single-document operations (which are already atomic).

**Q: What is the difference between `updateOne`, `updateMany`, `replaceOne`, `findOneAndUpdate`?**  
- `updateOne`: updates the first matching document.
- `updateMany`: updates all matching documents.
- `replaceOne`: replaces an entire document (except `_id`).
- `findOneAndUpdate`: updates a document and returns the original or updated document.

**Q: What is an upsert?**  
Option `upsert: true` in update operations creates a new document if no document matches the filter. Insert if not exist, update if exists.

**Q: What are MongoDB write concerns and read concerns?**  
- Write concern: level of acknowledgment requested for write operations (e.g., `{ w: "majority" }` waits for majority of replica set members).
- Read concern: level of isolation for read operations (e.g., `"majority"` returns data that has been acknowledged by a majority, providing consistency).

**Q: What is sharding in MongoDB? What problem does it solve?**  
Sharding distributes data across multiple servers (shards) to handle large datasets and high throughput operations. Each shard holds a subset of data based on a shard key. Enables horizontal scaling.

**Q: What is a replica set? How does failover work?**  
A replica set is a group of MongoDB processes maintaining the same data set, providing redundancy and high availability. One primary receives writes; secondaries replicate data. If primary fails, an election promotes a secondary to primary automatically.

**Q: What is the oplog?**  
The oplog (operations log) is a capped collection that records all modifications in the primary, enabling secondaries to replicate changes.

**Q: What is MongoDB Atlas? How does it differ from self-hosted MongoDB?**  
Atlas is MongoDB's managed cloud database service (DBaaS). It handles deployment, scaling, backups, monitoring, and security. Self-hosted requires manual setup, maintenance, and scaling.

### Mongoose

**Q: What is Mongoose? Why use it instead of the native MongoDB driver?**  
Mongoose is an ODM (Object Data Modeling) library for MongoDB and Node.js. It provides schema validation, model creation, middleware, and query building, enforcing a structure on otherwise schemaless collections. Useful for data consistency and relationship handling.

**Q: What is a Mongoose schema? What is a model?**  
Schema defines the structure, data types, validators, and default values for documents. A model is a compiled constructor created from the schema, providing an interface to interact with the database collection.

**Q: How do you define validation in a Mongoose schema?**  
Within schema definition, use built-in validators (required, min, max, enum, match) or custom validators via `validate` function. Example: `name: { type: String, required: true, minlength: 3 }`.

**Q: What are Mongoose virtuals?**  
Virtuals are document properties that are not persisted to MongoDB but computed on the fly. They can be getters/setters. Example: `fullName` computed from `firstName` and `lastName`.

**Q: What are Mongoose middleware (pre/post hooks)? Give 3 use cases.**  
Middleware (hooks) execute functions before/after certain events (save, validate, remove, updateOne). Use cases: hashing password before save (`pre('save')`), removing dependent documents after delete (`post('remove')`), logging changes, or updating timestamps.

**Q: What is `populate()` in Mongoose? How does it work? What are its limitations?**  
`populate()` replaces referenced ObjectIds with actual documents from another collection, similar to a join. It issues additional queries. Limitations: can lead to N+1 queries, not SQL joins; for large references, performance degrades. Use `lean()` for plain objects.

**Q: How do you implement soft deletes in Mongoose?**  
Add a `deleted: Boolean` or `deletedAt: Date` field. Override query helpers or use a plugin to automatically filter `deleted: false`. On delete, update the field instead of removing.

**Q: What is the difference between `save()` and `updateOne()` in Mongoose?**  
- `save()`: validates the full document against schema, runs middleware, works on a document instance.
- `updateOne()`: sends an update operation to MongoDB, bypasses schema validation and middleware (by default). Faster for bulk updates.

**Q: What is `lean()` in Mongoose? When should you use it?**  
`lean()` returns plain JavaScript objects instead of Mongoose documents, skipping hydration, getters/setters, and virtuals. Use when you only need data, for performance gains (e.g., read-only queries).

**Q: How do you handle connection pooling in Mongoose?**  
Mongoose manages connection pooling via the MongoDB driver's `poolSize` option (e.g., `mongoose.connect(uri, { maxPoolSize: 10 })`). Adjust based on expected concurrency.

**Q: What is the Mongoose `session` and how do you use it for transactions?**  
To use MongoDB transactions, start a session: `const session = await mongoose.startSession(); session.startTransaction();`. Pass `{ session }` to all operations within the transaction. Commit or abort.

**Q: What is discriminator in Mongoose?**  
Discriminators enable schema inheritance within a single collection. You define a base schema and then derived schemas that inherit and add fields, sharing the same collection but with a `__t` discriminator key.

**Q: How do you paginate results in Mongoose efficiently?**  
Use `skip()` and `limit()` for offset pagination, or cursor-based using `find({ _id: { $gt: lastId } }).limit(n)`. For large collections, cursor-based is more efficient. `mongoose-paginate-v2` plugin simplifies.

---

## 9. Databases — PostgreSQL / SQL & ORMs

### SQL Fundamentals

**Q: What is the difference between SQL and NoSQL databases?**  
SQL databases (relational): structured schema, tables, rows, SQL queries, ACID compliance (e.g., PostgreSQL). NoSQL: flexible schema (documents, key-value, graph), designed for horizontal scaling, eventual consistency often used (e.g., MongoDB). Different use cases.

**Q: When would you choose PostgreSQL over MongoDB?**  
When data is relational, requires complex joins, transactions across multiple entities, strict data integrity constraints, or reporting queries. PostgreSQL excels at structured, consistent data; MongoDB at rapidly evolving schemas, high write throughput, and hierarchical data.

**Q: What are ACID properties? Explain each.**  
- Atomicity: all operations in a transaction succeed or all fail.  
- Consistency: a transaction brings the database from one valid state to another.  
- Isolation: concurrent transactions do not interfere.  
- Durability: committed transactions persist even after a crash.

**Q: What is a transaction? How do you use one in Node.js?**  
A transaction groups multiple SQL statements into a single unit of work. In Node.js with `pg` (or ORM), use `BEGIN`, `COMMIT`, `ROLLBACK`. With an ORM like Sequelize, you can use managed transactions:
```javascript
await sequelize.transaction(async (t) => {
  // operations passing { transaction: t }
});
```

**Q: What is the difference between `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`?**  
- INNER: returns rows with matching values in both tables.
- LEFT: all rows from left table, plus matched rows from right; NULLs if no match.
- RIGHT: all rows from right, matched from left.
- FULL OUTER: all rows when there is a match in either table; NULLs where no match.

**Q: What is a subquery? What is a CTE (Common Table Expression)?**  
Subquery: a query nested inside another query (e.g., in `SELECT`, `FROM`, `WHERE`).  
CTE: a named temporary result set defined using `WITH` clause, reusable within the main query, improving readability and recursion (recursive CTE).

**Q: What is an index in PostgreSQL? What is the trade-off of over-indexing?**  
Index speeds up data retrieval but slows down write operations (INSERT, UPDATE, DELETE) because the index must be updated. Over-indexing consumes disk and increases maintenance overhead, with diminishing returns.

**Q: What is the difference between B-tree, Hash, GIN, and BRIN indexes?**  
- B-tree: default, good for equality and range queries, sorting.
- Hash: only equality comparisons, no range.
- GIN (Generalized Inverted Index): for full-text search, arrays, JSONB.
- BRIN (Block Range Index): for very large tables with natural correlation (e.g., timestamp), lightweight.

**Q: What is EXPLAIN ANALYZE in PostgreSQL?**  
`EXPLAIN ANALYZE` executes the query and shows the actual execution plan and timing, including row counts and loops. Vital for performance tuning.

**Q: What is N+1 query problem? How do you fix it?**  
The N+1 problem occurs when you fetch a list of entities and then for each entity run a separate query to fetch related data. Fix: use eager loading (JOINs or `include` in ORM) to fetch all needed data in one or few queries.

**Q: What are database migrations? How do you manage schema migrations in a Node.js app?**  
Migrations are version-controlled scripts that alter database schema. Tools like Knex.js, Sequelize, Prisma Migrate, `node-pg-migrate` apply changes incrementally and allow rollback.

**Q: What is optimistic locking vs pessimistic locking?**  
- Pessimistic locking: locks the row when reading, preventing others from updating until lock released (SELECT ... FOR UPDATE).  
- Optimistic locking: adds a version column; update checks version has not changed, else fails and retry. Suitable for low contention.

**Q: What is a deadlock? How do you prevent it?**  
Deadlock occurs when two transactions hold locks and each waits for the other. Prevent by accessing resources in the same order, using timeouts, and keeping transactions short.

**Q: What is connection pooling? Why is it critical in a Node.js app?**  
Connection pooling maintains a set of database connections that can be reused, avoiding the overhead of establishing a new connection per request. In Node.js, `pg-pool` is essential for performance under load.

**Q: What is `pg` vs `pg-pool` vs Knex.js vs Sequelize vs Prisma? When to use each?**  
- `pg`: low-level PostgreSQL client, callback/promise API.
- `pg-pool`: connection pooling for `pg`.
- Knex.js: SQL query builder with migrations and pooling, more control than ORM.
- Sequelize: full ORM with model definitions, associations, validation.
- Prisma: modern ORM with type-safe client, declarative schema, auto-generated migrations.
Use `pg` for simple scripts; Knex for SQL lovers; ORM for complex domain models and rapid development.

### ORMs

**Q: What is an ORM? What are its advantages and disadvantages?**  
ORM maps database tables to objects. Advantages: reduces boilerplate SQL, automates migrations, provides relations, type safety. Disadvantages: can generate inefficient queries, learning curve, hides complexity, less control over advanced SQL.

**Q: What is Sequelize? How do you define a model and associations?**  
Sequelize is a promise-based ORM for Node.js. Define model: `sequelize.define('User', { name: DataTypes.STRING })`. Associations: `User.hasMany(Post)`, `Post.belongsTo(User)`.

**Q: What is Prisma? How does it differ from Sequelize?**  
Prisma is a next-gen ORM with a declarative schema file, auto-generated type-safe client, and migration system. It provides better TypeScript support, less boilerplate, and more predictable queries. Sequelize is more traditional, JavaScript-first.

**Q: What is the Prisma schema? What is the Prisma client?**  
Prisma schema (in `schema.prisma`) defines the data model, database connection, and generator. Prisma client is an auto-generated, type-safe query builder used in application code to interact with the database.

**Q: How do you handle database migrations in Prisma vs Sequelize?**  
- Prisma Migrate: `npx prisma migrate dev` creates SQL migration files from schema changes.  
- Sequelize: use `sequelize-cli` to create migration files manually or auto-generate.

**Q: What is a repository pattern? How do you implement it in Node.js?**  
Repository pattern abstracts data access logic, providing a collection-like interface. Implement a class that encapsulates ORM/query calls, e.g., `UserRepository.findAll()`. This decouples business logic from data source details.

**Q: What is the active record pattern vs the data mapper pattern?**  
- Active Record: model object contains data and behavior (like Sequelize models).  
- Data Mapper: separates in-memory objects from database, using a mapper to translate (like Doctrine). Sequelize leans toward active record; Prisma is more data mapper (client generates queries).

**Q: What is Knex.js? When would you use it over an ORM?**  
Knex.js is a SQL query builder. Use when you need full control over SQL but want to avoid raw strings, migrations, and connection pooling. It's lighter than a full ORM and suitable for complex queries.

**Q: How do you prevent SQL injection using a query builder?**  
Query builders like Knex parameterize queries automatically, separating SQL code from values. They escape input, eliminating injection. Avoid raw interpolated strings; use parameterized queries (`?` placeholders) or builder methods.

---

## 10. Caching — Redis & Strategies

### Redis

**Q: What is Redis? What data structures does it support?**  
Redis is an in-memory data structure store used as cache, database, message broker. Supports strings, hashes, lists, sets, sorted sets, streams, HyperLogLog, bitmaps, geospatial indexes.

**Q: What is the difference between Redis as a cache vs as a database vs as a message broker?**  
- Cache: volatile data, often with TTL, eviction policies.  
- Database: data persisted, used as primary store (less common).  
- Message broker: Pub/Sub or streams for real-time messaging.

**Q: How do you connect to Redis from Node.js? (`ioredis` vs `node-redis`)**  
`ioredis` and `redis` (npm `redis`) are popular clients. Example with ioredis: `const Redis = require('ioredis'); const redis = new Redis();`. Both support promises; ioredis has better cluster/sentinel support.

**Q: How do you set a key with a TTL (expiration) in Redis?**  
`redis.set('key', 'value', 'EX', 3600);` (expires in 3600 seconds). Or `setex key 3600 value`. The client libraries provide the same.

**Q: What are Redis data types? When would you use each?**  
- Strings: simple key-value, counters, caching.  
- Hashes: object storage (user profile fields).  
- Lists: queues (LPUSH/RPOP), recent items.  
- Sets: unique collections, tags, friend lists.  
- Sorted Sets: leaderboards, priority queues.  
- Streams: log data, event sourcing.  
- HyperLogLog: approximate unique counting.  
- Bitmaps: feature flags, online status.

**Q: How do you implement session storage in Redis?**  
Use `connect-redis` as session store for Express-session: `app.use(session({ store: new RedisStore({ client: redisClient }), secret, ... }))`. Sessions stored as key-value, with automatic expiration.

**Q: How do you implement a rate limiter using Redis?**  
Use sorted sets for sliding window: for each request, add timestamp to a sorted set with key per user/IP, remove outdated entries, count remaining. Or use token bucket algorithm with INCR and EXPIRE. Libraries like `rate-limiter-flexible` use Redis backend.

**Q: What is Redis Pub/Sub? How does it differ from a message queue?**  
Pub/Sub allows publishers to send messages to channels; subscribers receive them in real-time. It's fire-and-forget; messages are not persisted or queued if no subscriber. Message queues (like RabbitMQ) persist messages and ensure delivery.

**Q: What is a Redis pipeline? What problem does it solve?**  
Pipelining sends multiple commands without waiting for replies, reducing network round-trips. Useful for batch operations. In Node.js, `redis.pipeline().set('a', 1).incr('a').exec()`.

**Q: What is Redis Lua scripting? When is it useful?**  
Lua scripts run atomically inside Redis, combining multiple commands into one execution. Useful for complex operations that require atomicity (e.g., rate limiting, compare-and-set). Use `EVAL` command.

**Q: What is the difference between Redis `WATCH/MULTI/EXEC` and a transaction?**  
`WATCH` marks keys for optimistic locking; `MULTI/EXEC` queues commands. If watched keys change before EXEC, the transaction fails. This provides atomicity and isolation but not full ACID. Redis transactions don't support rollback (commands are just not executed if EXEC fails).

**Q: What is Redis persistence? What is the difference between RDB and AOF?**  
- RDB (snapshotting): periodic point-in-time snapshots of dataset. Fast recovery, but can lose recent data.  
- AOF (Append Only File): logs every write operation; more durable, but slower. Can be used together.

**Q: What is Redis Cluster? What is Redis Sentinel?**  
- Redis Cluster: horizontal scaling with automatic sharding and failover.  
- Redis Sentinel: monitors master/slave instances, performs automatic failover for high availability without sharding.

**Q: What is cache invalidation? What are the common strategies?**  
Cache invalidation removes or updates stale cache entries. Strategies: TTL-based (expire after time), write-through (update cache and DB together), write-behind (update cache then async to DB), cache-aside (read cache, miss->DB, store in cache; manual invalidation on write). There's no universal solution; it's a hard problem.

**Q: What is the cache-aside pattern? How does it differ from write-through and write-behind?**  
- Cache-aside: application checks cache first; on miss, loads from DB and stores in cache. Writes go directly to DB, then invalidate cache.  
- Write-through: application writes to cache, cache synchronously writes to DB.  
- Write-behind: application writes to cache, cache asynchronously writes to DB later.

**Q: What is a cache stampede (thundering herd)? How do you prevent it?**  
When many concurrent requests try to rebuild the same expired cache entry simultaneously, overwhelming the database. Prevent with: staggered TTLs, mutex/lock on cache rebuild (only one fetches, others wait), pre-warming cache, or using `SETNX` to acquire a lock in Redis.

**Q: How do you implement distributed locking with Redis? (Redlock algorithm)**  
Redlock uses multiple independent Redis instances. To acquire lock, set a unique key with NX and PX (TTL) on a majority of instances within a timeout. To release, check value and delete if still owner. Libraries like `redlock` implement this. More reliable than single instance.

**Q: What is the difference between `DEL` and `UNLINK` in Redis?**  
`DEL` synchronously deletes a key and blocks Redis while freeing memory (for large values). `UNLINK` non-blocking; it marks the key for deletion and reclaims memory in the background, reducing latency spikes.

**Q: What are common Redis anti-patterns to avoid?**  
- Using `KEYS *` in production (blocking) → use `SCAN`.  
- Storing very large keys/values (bandwidth, memory).  
- Not setting TTLs, causing memory bloat.  
- Using single instance without persistence for critical data.  
- Overusing Pub/Sub for reliable messaging.

---

## 11. Error Handling & Logging

### Error Handling

**Q: What is the difference between operational errors and programmer errors in Node.js?**  
- Operational errors: expected runtime problems (e.g., failed network connection, invalid user input, database timeout). These should be handled gracefully.  
- Programmer errors: bugs in code (e.g., undefined variable, wrong type). These should be fixed. Handling them as operational errors can hide bugs.

**Q: How do you handle errors in synchronous vs asynchronous code?**  
- Synchronous: try/catch blocks.  
- Asynchronous callbacks: error-first callbacks; pass error as first arg.  
- Promises: `.catch()` or try/catch with async/await.  
- Express: pass to `next(err)`.

**Q: What is the error-first callback convention?**  
Callbacks should have the signature `(err, result)`. If error, `err` is non-null; else `result` is provided. This standardizes error handling.

**Q: How do you propagate errors through a Promise chain?**  
Using `reject` in a then callback or throwing an error inside a `.then()` passes it to the next `.catch()`. Unhandled rejections bubble up.

**Q: How do you handle errors in `async/await`? What is the try/catch pattern?**  
Wrap await in try/catch:
```javascript
try {
  const data = await fetchData();
} catch (err) {
  // handle error
}
```
Alternatively, use `.catch()` on the promise or a wrapper function.

**Q: What is centralized error handling in Express? How do you implement it?**  
Create an error-handling middleware (four arguments) at the end. All errors passed via `next(err)` will end up there. This middleware can log the error and send a consistent JSON response.

**Q: What is a custom error class in Node.js? Implement `AppError` with a status code.**  
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

**Q: When should you use `process.on('uncaughtException')`? What are the risks?**  
Use it as a last-resort handler to log fatal errors and perform a graceful shutdown. Risks: the process might be in an inconsistent state; continuing after uncaught exception is dangerous. Always exit after logging.

**Q: When should you use `process.on('unhandledRejection')`?**  
To catch promise rejections that were not handled. In Node.js, unhandled rejections will eventually terminate the process. Use this to log and alert, then gracefully shut down.

**Q: How do you implement graceful error responses (not leaking stack traces in production)?**  
In error-handling middleware, check `NODE_ENV`. In production, send a generic message; in development, include the error stack. Always use custom error classes to control what is sent.

**Q: What is the difference between `throw` and `next(err)` in Express?**  
`throw` inside synchronous code or async without catch will crash the process (unless caught by global handlers). `next(err)` passes the error to the Express error-handling middleware chain safely.

**Q: How do you handle async errors in Express without try/catch on every route?**  
Use a wrapper function like `express-async-handler` or `asyncWrap`:
```javascript
const asyncHandler = (fn) => (req, res, next) => Promise.resolve(fn(req, res, next)).catch(next);
```
Then wrap route handlers: `app.get('/', asyncHandler(async (req, res) => { ... }))`.

**Q: What is domain error handling in Node.js? (deprecated, but may be asked)**  
Domain module was a way to handle multiple I/O operations as a group, catching errors. Deprecated due to performance and reliability issues. Replaced by `async_hooks` and better patterns.

**Q: How do you distinguish between a 4xx error (client) and 5xx error (server) in your error handler?**  
Use the status code attached to the error object. Custom error classes can have `statusCode` property. If `statusCode` >= 400 and < 500, it's client error; >= 500 is server. Default to 500 if unknown.

### Logging

**Q: What is structured logging? Why is it better than `console.log` in production?**  
Structured logging outputs log entries as key-value pairs (JSON), enabling parsing and searching by log aggregators (ELK, Datadog). `console.log` outputs unstructured strings, harder to query at scale.

**Q: What is Winston? How do you configure transports, log levels, and formatters?**  
Winston is a logging library. Transports define output destinations (console, file, HTTP). Levels: `error: 0, warn: 1, info: 2, http: 3, verbose: 4, debug: 5, silly: 6`. Formatters customize the log structure (e.g., `winston.format.json()`). Configure via `winston.createLogger`.

**Q: What is Pino? Why is it faster than Winston?**  
Pino is a very fast JSON logger for Node.js. It achieves speed by minimizing overhead, using native JSON stringification, and avoiding complex features. Often used in high-throughput production services.

**Q: What are log levels? (`error`, `warn`, `info`, `http`, `verbose`, `debug`, `silly`)**  
Log levels indicate severity; they allow filtering logs based on importance. Higher severity numbers mean less verbosity.

**Q: What is correlation ID / request ID? How do you propagate it across async calls?**  
A correlation ID is a unique identifier attached to a request, passed across services and logged with each entry, enabling tracing of a transaction. In Node.js, use `AsyncLocalStorage` or `cls-hooked` to maintain the ID through asynchronous operations without explicit parameter passing.

**Q: How do you implement centralized logging in a distributed Node.js system? (ELK, Datadog, Loki)**  
Send logs to a central system using agents (Filebeat -> Elasticsearch), direct API calls (Datadog, Loki), or syslog. Use structured logging with correlation IDs. Avoid writing logs to local files in containers.

**Q: What is `morgan`? What log format would you use in production?**  
Morgan is an HTTP request logger middleware. In production, use the `combined` format (standard Apache combined log) or a custom JSON format that includes request ID, method, URL, status, response time.

**Q: How do you redact sensitive fields (passwords, tokens) from logs?**  
Use a formatter that replaces or removes sensitive keys from the log object before output. Winston/Pino have redact options or you can write a custom serializer.

**Q: What is `cls-hooked` or `AsyncLocalStorage` for log context propagation?**  
`AsyncLocalStorage` (built into Node.js) allows associating state (like request ID) with the current asynchronous execution context, ensuring it's available in all subsequent async operations without passing it manually. It replaces the deprecated `cls-hooked` with a better API.

**Q: How do you implement audit logging in a Node.js app?**  
Create a dedicated audit log middleware or service that records who did what, when, and the relevant data. Write audit events to a secure, append-only storage (database, separate log file). Use correlation IDs and ensure immutability.

---

## 12. Security

### Common Vulnerabilities

**Q: What is SQL injection? How do you prevent it in Node.js?**  
SQL injection occurs when untrusted input is concatenated into SQL queries. Prevention: use parameterized queries or ORM/query builders that escape inputs. Never use string interpolation for values.

**Q: What is NoSQL injection (MongoDB injection)? How do you prevent it?**  
By passing objects with operators like `{ $gt: '' }` in query parameters, attackers can bypass logic. Prevent: use `mongoose` schema validation, sanitize input, use `express-mongo-sanitize` to remove `$` and `.` from keys.

**Q: What is XSS (Cross-Site Scripting)? How do you prevent it in a Node.js API?**  
XSS injects malicious scripts into web pages. In APIs, prevent by escaping output, setting Content-Type headers appropriately (not `text/html` when serving JSON), and using `helmet` with CSP. Validate and sanitize input.

**Q: What is CSRF (Cross-Site Request Forgery)? How do you prevent it?**  
CSRF tricks a user into making unwanted requests to a site where they're authenticated. Prevention: use CSRF tokens (sync token pattern), `SameSite=Strict` cookies, and check origin/referer headers. `csurf` middleware (though deprecated, alternatives exist).

**Q: What is prototype pollution? How can it affect a Node.js app?**  
Prototype pollution allows an attacker to add or modify properties of `Object.prototype` by abusing deep merge or assignment operations. This can lead to denial of service, or even remote code execution in some cases. Prevent: use `Object.create(null)`, validate object keys, use libraries like `lodash` with safe defaults, or `Object.freeze(Object.prototype)`.

**Q: What is a mass assignment vulnerability? How do you prevent it?**  
Mass assignment occurs when an API blindly assigns client-provided properties to a database model, allowing unauthorized fields to be set. Prevent: explicitly define which fields can be updated (whitelist approach). In Mongoose, use `strict` schema; in Sequelize/Prisma, specify allowed fields.

**Q: What is SSRF (Server-Side Request Forgery)?**  
SSRF allows an attacker to induce the server to make HTTP requests to internal resources. Prevent: validate and sanitize user-supplied URLs, restrict allowed hosts/protocols, use allowlists, and avoid making requests to user-provided URLs.

**Q: What is a timing attack? How does `crypto.timingSafeEqual()` help?**  
Timing attacks infer secrets by measuring response time differences. `crypto.timingSafeEqual()` compares two buffers in constant time, preventing leakage of how many characters matched.

**Q: What is a ReDoS (Regular Expression Denial of Service)?**  
A ReDoS exploits catastrophic backtracking in poorly crafted regex patterns, causing extreme CPU usage and event loop block. Prevent: use safe regex patterns (avoid nested quantifiers), use tools like `safe-regex`, set timeouts for regex matching.

**Q: What is directory traversal? How do you prevent it?**  
Directory traversal uses `../` sequences to access files outside intended directory. Prevent: resolve the path using `path.resolve` and verify it starts with the allowed base path. Never directly pass user input to `fs.readFile`.

### Hardening & Best Practices

**Q: What does `helmet.js` do? Which headers does it set?**  
Helmet sets various security-related HTTP headers: `X-DNS-Prefetch-Control`, `X-Frame-Options`, `X-Content-Type-Options: nosniff`, `Strict-Transport-Security`, `X-Permitted-Cross-Domain-Policies`, `Referrer-Policy`, `Content-Security-Policy` (disabled by default), etc.

**Q: What is CORS? How do you configure it securely?**  
CORS (Cross-Origin Resource Sharing) controls which origins can access resources. Use `cors` middleware, specify allowed origins (never `*` with credentials), methods, headers. For sensitive data, restrict origins explicitly.

**Q: What is the principle of least privilege in APIs?**  
Grant users and services only the minimum access necessary. Apply fine-grained permissions, separate admin from user routes, and never expose admin functionality to all clients.

**Q: How do you implement input validation and sanitization?**  
Use validation libraries (Joi, Zod, express-validator) to define expected schemas and reject invalid input. Sanitize data by escaping, trimming, or type coercion. Validate at the boundary (API middleware).

**Q: What is rate limiting? How do you implement it? What is distributed rate limiting?**  
Rate limiting restricts the number of requests per client/IP in a time window to prevent abuse. Implement with `express-rate-limit`. For distributed systems, store counters in Redis (`rate-limit-redis`). This coordinates limits across multiple server instances.

**Q: What is `hpp` (HTTP Parameter Pollution)? How do you protect against it?**  
HPP exploits passing multiple parameters with the same name to bypass validation or cause unexpected behavior. Use `hpp` middleware to handle duplicate parameters (e.g., pick last, first, or reject).

**Q: How do you securely store secrets in a Node.js application?**  
Use environment variables (not hardcoded) and tools like `dotenv` only for development. In production, use secret managers (AWS Secrets Manager, HashiCorp Vault), CI/CD secrets injection, or Kubernetes secrets. Never commit secrets to source control.

**Q: What is a Content Security Policy (CSP)?**  
CSP is a security header that controls which resources the browser is allowed to load for a page. Mitigates XSS and data injection attacks. Defined via `Content-Security-Policy` header, often configured with helmet.

**Q: What is HTTPS? How do you force HTTPS in Express?**  
HTTPS encrypts HTTP traffic. Force HTTPS by detecting `req.protocol` or `X-Forwarded-Proto` header (when behind a proxy) and redirecting HTTP to HTTPS. Use `express-sslify` or manual middleware. In production, terminate SSL at load balancer, but still enforce.

**Q: How do you prevent brute-force login attacks?**  
Implement rate limiting on login endpoints, account lockout after consecutive failures, CAPTCHA after threshold, and use bcrypt/argon2 for password hashing (slow by design).

**Q: What is `npm audit`? How do you handle vulnerable dependencies?**  
`npm audit` checks for known vulnerabilities. Handle by updating the dependency if a fix is available, or applying patches/alternatives. Use `npm audit fix`. Integrate into CI to catch issues early.

**Q: What is OWASP Top 10? Which items are most relevant to Node.js APIs?**  
OWASP Top 10 lists critical web application security risks. Relevant ones: Injection (NoSQL, SQL), Broken Authentication (JWT misuse), Sensitive Data Exposure (leaking stack traces), XXE, Broken Access Control, Security Misconfiguration (CORS, headers), XSS, Insecure Deserialization, Using Components with Known Vulnerabilities, Insufficient Logging & Monitoring.

**Q: How do you implement security headers? (HSTS, X-Frame-Options, X-Content-Type-Options)**  
Set them via middleware (helmet sets most). HSTS: `Strict-Transport-Security` header with max-age; X-Frame-Options: `DENY` or `SAMEORIGIN`; X-Content-Type-Options: `nosniff`. These prevent clickjacking, MIME sniffing, and enforce HTTPS.

**Q: What is a JWT secret? How long should it be? How do you rotate it?**  
The secret is used to sign and verify JWT. For HS256, it should be a long, random string (at least 256 bits). Rotation involves using a key ID (`kid`) in the header, supporting multiple keys simultaneously, and deprecating old keys after a period. Store secrets securely.

**Q: How do you implement API key authentication securely?**  
Client sends API key in header or query param. Server validates against a store (DB, Redis). Use constant-time comparison. Never log the key. Enforce HTTPS. Consider rate limiting and key rotation.

---

## 13. Performance, Scaling & Clustering

### Performance Optimization

**Q: How do you profile a Node.js application? What tools do you use?**  
- CPU profiling: Node.js built-in `--inspect` + Chrome DevTools, or `clinic doctor`, `v8-profiler-next`.  
- Memory profiling: heap snapshots with Chrome DevTools, `memwatch-next`, `heapdump`.  
- Event loop lag: `clinic doctor`, `blocked` module, `perf_hooks.monitorEventLoopDelay`.  
- Flamegraphs: `0x` or `clinic flame`.

**Q: What is the `clinic` tool suite? (clinic doctor, clinic flame, clinic bubbleprof)**  
Clinic.js is a set of tools to diagnose performance issues in Node.js:  
- `clinic doctor`: overall health, event loop delay, GC activity.  
- `clinic flame`: generates flamegraphs to visualize CPU usage.  
- `clinic bubbleprof`: visualises async operations and their latencies.

**Q: How do you detect event loop lag in production?**  
Use `perf_hooks.monitorEventLoopDelay()` and expose a metric. Compare lag threshold; if consistently high, the loop is blocked. Also implement a "busy" middleware using `toobusy-js`.

**Q: What is `--inspect` flag? How do you use Chrome DevTools to profile Node.js?**  
`node --inspect app.js` starts the debugger. Open `chrome://inspect` in Chrome, connect to the Node instance. Use the Profiler tab to record CPU profiles, heap snapshots, etc.

**Q: What is V8 heap snapshot? How do you use it to debug memory leaks?**  
A heap snapshot captures the state of memory. Take two snapshots with a time gap; compare them to see which objects increased. Chrome DevTools can compare snapshots and show retained size. Objects still referenced unintentionally indicate a leak.

**Q: How do you detect and fix memory leaks in Node.js?**  
Detect by monitoring heap usage over time, taking snapshots, using `memwatch-next` for leak events, or APM tools. Common fixes: clear intervals/timeouts, remove event listeners, avoid global variables and closures holding references, nullify references when done.

**Q: What are the common causes of memory leaks in Node.js?**  
- Unremoved event listeners.  
- Closures retaining large objects.  
- Global variables or module-level caches that never get cleaned.  
- Unintentional reference from timers.  
- Streams not properly destroyed.

**Q: What is garbage collection in Node.js? How does V8's GC work?**  
GC reclaims memory occupied by objects no longer in use. V8 uses generational GC: New space (Scavenge) for short-lived objects, Old space (Mark-Sweep & Mark-Compact) for long-lived. It stops the world briefly (minor GCs are fast) but major GCs can cause pauses.

**Q: What is the old space vs new space in V8 memory?**  
New space is where new, short-lived objects are allocated; it's collected quickly (Scavenge). Objects that survive two minor GCs are promoted to old space, which is collected less frequently and more thoroughly (Mark-Sweep). Old space holds long-lived data.

**Q: How do you tune V8 garbage collection? (`--max-old-space-size`, `--expose-gc`)**  
- `--max-old-space-size=4096`: increases max heap memory.  
- `--expose-gc`: enables `global.gc()` for manual triggering (only in dev).  
- `--optimize-for-size` reduces memory. Tune as needed based on monitoring.

**Q: What is `process.memoryUsage()`? What do `heapUsed`, `heapTotal`, `rss`, `external` mean?**  
- `rss`: Resident Set Size, total memory allocated in RAM.  
- `heapTotal`: total size of V8 heap (including free).  
- `heapUsed`: actual memory used by JS objects on the heap.  
- `external`: memory used by C++ objects bound to JS (buffers, etc.). Monitor for leaks.

**Q: What is the `perf_hooks` module? How do you measure execution time with `performance.now()`?**  
`perf_hooks` provides high-resolution timing and performance measurement. `performance.now()` returns a high-resolution timestamp in milliseconds. Use to measure code execution: `const start = performance.now(); ... const duration = performance.now() - start;`.

**Q: How do you optimize database queries in a Node.js app?**  
- Use proper indexing.  
- Avoid N+1 by eager loading.  
- Use connection pooling.  
- Select only needed fields.  
- Batch operations.  
- Use query analysis (explain).  
- Paginate results efficiently.

**Q: When should you use streaming vs buffering for large responses?**  
Stream when the response is large (file downloads, large dataset), to keep memory low and start sending data early. Buffer small responses (e.g., JSON payloads) that fit in memory.

**Q: What is connection pooling? Why is it critical for performance under load?**  
Connection pooling maintains a pool of reusable database connections, avoiding the overhead of establishing new ones per request. Critical for Node.js because a single-threaded event loop benefits from fast, reusable connections.

**Q: How do you implement caching at the application layer?**  
Implement a cache-aside pattern: check cache first, on miss query DB and store in cache (Redis/Memory). Use TTLs, invalidate on writes. Cache frequently read, rarely changed data.

**Q: What is `compression` middleware? What is the trade-off of enabling it?**  
`compression` gzips responses, reducing bandwidth. Trade-off: it consumes CPU cycles. For high traffic, it's usually worth it. Can be offloaded to a reverse proxy.

### Scaling

**Q: How do you scale a Node.js application to handle high traffic?**  
- Horizontally: run multiple instances behind a load balancer (cluster module or separate processes).  
- Use a reverse proxy (Nginx).  
- Design stateless services.  
- Use caching, CDN.  
- Offload CPU-intensive tasks to worker threads.  
- Scale database (sharding, read replicas).

**Q: What is the Node.js Cluster module? How does it work?**  
The `cluster` module allows creating child processes (workers) that share the same server port. The master process manages workers; incoming connections are distributed among workers (round-robin by default). Each worker runs its own event loop, utilizing multiple CPU cores.

**Q: What is the difference between clustering and worker threads?**  
Clustering spawns separate Node.js processes, each with its own V8 instance, memory, and event loop. Worker threads share the same process memory and can efficiently communicate via `SharedArrayBuffer`. Clustering is for CPU-bound parallelization across cores; worker threads are for parallelizing within a single process, lighter but still separate event loops.

**Q: How does the master process distribute connections to workers in Cluster mode? (round-robin)**  
On most platforms, the master listens on the port and distributes incoming connections to workers in a round-robin fashion (except Windows where workers listen directly). This balances load.

**Q: What is PM2? What are its key features? How is it different from raw `node`?**  
PM2 is a process manager for Node.js applications. Features: cluster mode, auto-restart on crash, load balancing, log management, monitoring, zero-downtime reload, and deployment. Unlike raw `node`, it keeps the app alive and manages multiple instances.

**Q: How do you use PM2 in cluster mode?**  
`pm2 start app.js -i max` (or number of instances). `-i max` spawns as many workers as CPU cores. PM2 automatically load balances.

**Q: What is horizontal vs vertical scaling? Which does Node.js lean toward?**  
- Vertical: add more resources (CPU, RAM) to a single machine.  
- Horizontal: add more machines/instances. Node.js naturally leans toward horizontal scaling due to its single-threaded nature; running multiple instances across machines/cores works well.

**Q: What is stateless architecture? Why is it necessary for horizontal scaling?**  
Stateless means any server instance can handle any request; no session stored locally. Necessary for horizontal scaling so that a load balancer can distribute requests to any instance without sticky sessions. Use external stores (Redis) for session data.

**Q: How do you share state across multiple Node.js instances? (Redis, sticky sessions)**  
Use a centralized store like Redis for sessions, cache, and real-time data. For WebSockets, use a Redis adapter with `socket.io` to broadcast across instances. Sticky sessions (ip hash) tie a client to a specific instance, but this breaks true statelessness; prefer external state.

**Q: What is a load balancer? How does Nginx act as a reverse proxy/load balancer for Node.js?**  
A load balancer distributes incoming traffic across multiple backend servers. Nginx can be configured as a reverse proxy, forwarding requests to multiple Node.js instances defined in an upstream block, with load balancing algorithms (round-robin, least_conn, ip_hash).

**Q: What is sticky session? When do you need it?**  
Sticky session routes a client to the same backend instance for the duration of a session. Needed when the application stores session state locally (not externalized). Otherwise, avoid it for better scalability and resilience.

**Q: How do you implement zero-downtime deployment with Node.js?**  
Using PM2: `pm2 reload` or `pm2 startOrGracefulReload` sends SIGUSR2 to start new workers and gracefully shut down old ones. With a load balancer, drain connections from old instance before stopping. In Kubernetes, rolling updates achieve similar.

**Q: What is graceful shutdown? How do you implement it? (drain existing connections, stop accepting new ones)**  
1. Catch SIGTERM.  
2. Stop accepting new connections (`server.close()`).  
3. Allow current requests to finish (track active connections, use `http-terminator` or `stoppable`).  
4. Clean up resources (close DB pools, disconnect Redis).  
5. Exit.

**Q: What is circuit breaker pattern? How do you implement it in Node.js?**  
Circuit breaker detects failures and prevents cascading failures by "opening" the circuit after a threshold, failing fast until a timeout. In Node.js, use `opossum` library to wrap calls to external services. It provides fallback and auto-recovery.

**Q: What is the `--max-semi-space-size` flag?**  
It sets the maximum size of V8's semi-spaces (used in new space for Scavenge). Increasing can reduce GC frequency but increases memory footprint. Rarely tuned manually.

---

## 14. Worker Threads & Child Processes

### Worker Threads

**Q: What is the `worker_threads` module? What problem does it solve?**  
`worker_threads` enables running JavaScript in separate threads within the same process, sharing memory. It solves CPU-intensive tasks blocking the event loop by offloading them to parallel threads with their own event loop.

**Q: When should you use worker threads vs clustering?**  
Worker threads: for CPU-bound tasks that need parallel execution within the same application, sharing memory and resources efficiently.  
Clustering: for scaling an entire web server process across multiple CPU cores, each with isolated memory.

**Q: How do worker threads share memory? What is `SharedArrayBuffer`?**  
Worker threads can share memory via `SharedArrayBuffer`, a buffer that can be accessed by multiple workers simultaneously. Synchronization is done using `Atomics`. Additionally, they communicate via `postMessage`.

**Q: What is `Atomics`? When is it needed with `SharedArrayBuffer`?**  
`Atomics` provides atomic operations (add, sub, load, store, wait, notify) on `SharedArrayBuffer`, ensuring thread-safe access without race conditions. It's needed to coordinate between workers sharing memory.

**Q: How do worker threads communicate? (`MessageChannel`, `postMessage`, `workerData`)**  
- `workerData`: initial data passed to worker at creation.  
- `postMessage`: send messages; worker listens with `parentPort.on('message')`.  
- `MessageChannel`: creates a two-way communication channel between two workers.

**Q: How do you terminate a worker thread gracefully?**  
Call `worker.terminate()` which sends a termination signal, or within the worker listen for exit signals. Clean up resources in the worker's exit handler. Avoid abrupt termination if the worker is in the middle of a task.

**Q: What is `isMainThread`? How do you use it to write a single-file worker?**  
`isMainThread` is a boolean from `worker_threads` that indicates if the code is running in the main thread. Use `if (isMainThread) { ... } else { ... }` to have both the main and worker code in the same file.

**Q: What are the limitations of worker threads?**  
- Each worker has its own V8 instance and event loop, so they still have some overhead.  
- Cannot share functions or closures; communication is via serializable objects and buffers.  
- Not available on some environments; disabled by default before Node 12 LTS.  
- Not suitable for I/O-bound tasks (event loop handles I/O better).

**Q: What is a thread pool pattern using worker threads?**  
Create a pool of worker threads that can process tasks. Maintain a queue of jobs; a manager assigns work to an available worker. This avoids spawning workers per task. Use `piscina` library which provides an efficient pool.

### Child Processes

**Q: What are child processes in Node.js? What are the 4 methods to create them?**  
Child processes allow spawning new OS processes. Methods: `spawn()`, `exec()`, `execFile()`, `fork()`. They are separate processes with their own memory, communicating via IPC.

**Q: What is the difference between `spawn()` and `exec()`?**  
- `spawn()`: streams the output, efficient for large data, returns a ChildProcess instance with `stdout`/`stderr` streams.  
- `exec()`: buffers the entire output in memory, calls callback with complete output. Good for small outputs.

**Q: What is the difference between `fork()` and `spawn()`?**  
`fork()` is a special case of `spawn()` for spawning new Node.js processes. It automatically sets up an IPC channel, allowing message passing. Used for parallelizing Node tasks without manual IPC setup.

**Q: What is IPC (Inter-Process Communication) in Node.js?**  
IPC allows parent and child processes to communicate asynchronously via messages. `fork()` enables IPC by default; use `child.on('message')` and `child.send()`.

**Q: How do you communicate between a parent and child process?**  
Using `child.send(message)` and the child listens with `process.on('message', ...)`. Messages are serialized using structured clone. For `spawn`, you may use stdio pipes.

**Q: What are the security risks of using `exec()` with user input?**  
`exec()` runs a command in a shell, which is susceptible to command injection if user input is not sanitized. Never pass unsanitized user input to `exec()`. Use `execFile()` with safe arguments.

**Q: When would you use `execFile()` instead of `exec()`?**  
`execFile()` runs an executable file directly without invoking a shell, which is safer and more efficient. Use it when you don't need shell features and want to avoid injection risks.

**Q: How do you handle a child process crash in the parent?**  
Listen for the `'exit'` event on the child process; check the exit code and signal. You may decide to restart the child or log the error. If the child is critical, implement a respawn logic.

**Q: What is `detached: true` option in `spawn()`?**  
When `detached` is true, the child process becomes the leader of a new process group and will not be terminated when the parent exits. Useful for long-running background tasks that should survive parent shutdown.

---

## 15. File System & Built-in Modules

### File System (`fs`)

**Q: What is the `fs` module? What are the key methods?**  
`fs` module provides API for interacting with the file system. Key methods: `readFile`, `writeFile`, `appendFile`, `mkdir`, `readdir`, `stat`, `unlink`, `rename`, `createReadStream`, `createWriteStream`, `watch`. Both synchronous and asynchronous (callback/Promise) variants.

**Q: What is the difference between `fs.readFile()` and `fs.createReadStream()`? When to use each?**  
- `readFile`: reads entire file into memory, simple for small files.  
- `createReadStream`: reads chunk by chunk, memory efficient for large files. Use streaming for large or unbounded data.

**Q: What is `fs.promises`? How does it differ from callback-based `fs`?**  
`fs.promises` provides the same file system methods but returns Promises instead of using callbacks, enabling async/await and better error handling.

**Q: What is `fs.watch()` vs `fs.watchFile()`? What are their limitations?**  
- `fs.watchFile`: polls file stats periodically; higher CPU usage, works on all platforms.  
- `fs.watch`: uses OS events (more efficient), but behavior differs across platforms and may not detect all changes (e.g., some editors). Both have reliability issues; for robust watching, use `chokidar`.

**Q: How do you recursively read a directory in Node.js?**  
Use `fs.readdir` with `{ recursive: true }` (Node 20+), or use a recursive function that iterates through subdirectories, or `fs.promises.readdir` with the option.

**Q: What is `fs.stat()` vs `fs.lstat()`?**  
- `stat`: follows symbolic links and returns info about the target.  
- `lstat`: returns info about the link itself if it's a symlink.

**Q: How do you implement atomic file writes?**  
Write to a temporary file, then atomically rename it to the target filename using `fs.rename`. This ensures the file is either fully written or not at all (no partial data).

**Q: What is the `path` module? What is `path.join()` vs `path.resolve()`?**  
`path` module provides utilities for working with file and directory paths.  
- `join`: concatenates path segments using the correct separator, normalizing.  
- `resolve`: resolves an absolute path from segments, treating the rightmost parameter as relative to preceding ones or cwd.

**Q: What is `os` module? Give 3 use cases.**  
Provides operating system-related utility methods. Use cases: get CPU info (`os.cpus()`), free memory (`os.freemem()`), hostname, platform, network interfaces, uptime.

**Q: What is the `url` module? How do you parse a URL?**  
`url` module parses and formats URL strings. `url.parse('http://example.com/path?query=1')` returns object with `protocol`, `host`, `pathname`, `query`, etc. In modern Node, use `URL` class globally.

**Q: What is `crypto` module? How do you generate a random token? How do you create an HMAC?**  
`crypto` provides cryptographic functionality. Random token: `crypto.randomBytes(32).toString('hex')`. HMAC: `crypto.createHmac('sha256', secret).update(data).digest('hex')`.

**Q: What is `zlib` module? How do you gzip a response in Express?**  
`zlib` provides compression. In Express, use `compression` middleware that uses zlib behind the scenes. For manual streaming: `zlib.createGzip()` as transform.

**Q: What is `net` module? What can you build with it?**  
`net` module provides an asynchronous network API for creating TCP or IPC servers and clients. You can build chat servers, custom protocols, proxies.

**Q: What is `dns` module? What are `dns.lookup()` vs `dns.resolve()`?**  
- `dns.lookup()`: uses OS DNS resolver (libuv thread pool), returns IP address.  
- `dns.resolve()`: performs DNS resolution using the network, returns an array of records (A, AAAA, MX, etc.), more detailed.

---

## 16. WebSockets & Real-Time Communication

### WebSockets

**Q: What is a WebSocket? How does the WebSocket handshake work?**  
WebSocket provides full-duplex, persistent communication over a single TCP connection. Handshake: client sends an HTTP Upgrade request with headers `Upgrade: websocket` and `Connection: Upgrade`. Server responds with `101 Switching Protocols`, and the connection is upgraded to WebSocket.

**Q: What is the difference between WebSockets, HTTP long polling, and Server-Sent Events (SSE)?**  
- WebSockets: full-duplex, real-time, low overhead.  
- Long polling: client makes HTTP request, server holds until data available, then client immediately reconnects. Higher overhead.  
- SSE: server pushes events to client via HTTP; unidirectional, simpler, auto-reconnect.

**Q: When would you use WebSockets vs SSE vs polling?**  
WebSockets for bidirectional, low-latency (chat, gaming). SSE for server-to-client streaming (notifications, live feeds) where client only reads. Polling for simple, infrequent updates where real-time isn't critical.

**Q: What is `socket.io`? How does it differ from raw WebSockets?**  
`socket.io` is a library that provides an abstraction over WebSockets with automatic reconnection, rooms, namespaces, fallback to HTTP long polling, and broadcast. Raw `ws` package gives low-level WebSocket control.

**Q: What is `socket.io` room? How does it enable group messaging?**  
A room is a channel that sockets can join/leave. Send to a room broadcasts to all members except the sender. Useful for chat groups, collaborative editing.

**Q: How do you scale `socket.io` across multiple servers? (Redis adapter)**  
Use `socket.io-redis-adapter` (or the newer `@socket.io/redis-adapter`). It uses Redis Pub/Sub to relay events between nodes, so a message emitted on one server reaches all servers and their connected clients.

**Q: What is `socket.io` namespace?**  
Namespaces allow splitting the server into separate communication channels sharing the same underlying WebSocket connection. They help organize endpoints (e.g., `/admin`, `/chat`).

**Q: What is a heartbeat/ping-pong in WebSockets? Why is it needed?**  
A heartbeat sends periodic ping frames to keep the connection alive and detect disconnections. If no pong is received, the connection is considered lost. `socket.io` handles this automatically.

**Q: How do you authenticate a WebSocket connection?**  
Pass a token as query parameter or in the first message, verify it upon connection, then associate user with the socket. `socket.io` middleware can be used to reject unauthorized connections.

**Q: How do you handle reconnection logic in WebSocket clients?**  
`socket.io` has built-in reconnection with exponential backoff. For raw `ws`, implement a reconnection function that attempts to reconnect after a delay. Handle `close` event.

**Q: How do you broadcast to all connected clients vs a subset?**  
- All: `io.emit('message', data)` (all namespaces).  
- Subset: use rooms: `socket.to('room').emit(...)`, or filter by connected sockets manually.

**Q: What is the `ws` package? When would you use it over `socket.io`?**  
`ws` is a simple, fast WebSocket implementation for Node.js. Use it when you need lightweight, low-level control without the overhead of `socket.io` features (rooms, fallback), e.g., for high-throughput custom protocols.

### SSE (Server-Sent Events)

**Q: What is SSE? How does it work?**  
SSE is a standard allowing servers to push data to clients over HTTP. Client uses `EventSource` to open a connection; server keeps it open and sends `data:` lines. It's one-way and auto-reconnects.

**Q: How do you implement SSE in Express?**  
Set headers: `Content-Type: text/event-stream`, `Cache-Control: no-cache`, `Connection: keep-alive`. Then write events: `res.write('data: message\n\n');`.

**Q: What are the limitations of SSE vs WebSockets?**  
SSE is unidirectional (server to client), limited to text (UTF-8), and max connections per browser domain (~6) can be limited. WebSockets are full-duplex, binary capable.

**Q: How do you handle client disconnection in SSE?**  
Listen for the `'close'` event on the request object to detect when the client disconnects, and clean up resources.

---

## 17. Microservices & Architecture

### Microservices

**Q: What is a microservices architecture? What are its advantages and disadvantages?**  
Microservices break an application into small, independent services, each with its own database and business logic. Advantages: scalability, independent deployment, technology diversity. Disadvantages: complexity, network latency, data consistency challenges, operational overhead.

**Q: What is the difference between a monolith and microservices?**  
Monolith: single codebase and deployment; simpler initially but can become unwieldy. Microservices: multiple small services; more complex but enables better scaling and agility for large teams.

**Q: How do microservices communicate? (REST/HTTP, gRPC, message queues)**  
- Synchronous: REST/HTTP (simplest), gRPC (high-performance, binary).  
- Asynchronous: message queues (RabbitMQ, Kafka) for decoupling and resiliency.

**Q: What is gRPC? How does it compare to REST?**  
gRPC is a high-performance RPC framework using Protocol Buffers for serialization, HTTP/2 for transport. Benefits: strong typing, code generation, bidirectional streaming, smaller payloads. REST is text-based (JSON), simpler but less efficient. Use gRPC for internal service communication.

**Q: What is a service mesh? What problems does it solve?**  
Service mesh (e.g., Istio) manages service-to-service communication via sidecar proxies, handling load balancing, service discovery, retries, circuit breaking, and observability without code changes.

**Q: What is an API Gateway? What are its responsibilities?**  
An API Gateway is the single entry point for clients, routing requests to appropriate microservices, handling cross-cutting concerns: authentication, rate limiting, request aggregation, and protocol translation.

**Q: What is service discovery? How does it work in a Node.js microservices setup?**  
Service discovery enables services to locate each other dynamically. Client-side discovery uses a registry (Consul, etcd) queried by the client. Server-side discovery uses a load balancer. In Node.js, libraries like `consul` can be used.

**Q: What is the circuit breaker pattern? How do you implement it in Node.js?**  
(Already answered) Use `opossum` to wrap external calls; it monitors failures and opens the circuit to fail fast.

**Q: What is the bulkhead pattern?**  
Bulkhead isolates elements of an application into pools so that if one fails, others remain functional. In Node.js, you can limit concurrent connections to a service (e.g., using a connection pool or semaphore) to prevent resource exhaustion.

**Q: What is the saga pattern? What is the difference between choreography and orchestration?**  
Saga manages distributed transactions by splitting into local transactions with compensating actions. Choreography: services react to events, publish events themselves. Orchestration: a central coordinator tells services what to do.

**Q: What is CQRS (Command Query Responsibility Segregation)?**  
CQRS separates read and write operations into different models, potentially using different databases. Useful for complex domains with different read/write performance needs.

**Q: What is event sourcing?**  
Event sourcing stores state as a sequence of events rather than current state. The current state is derived by replaying events. Good for audit trails and temporal queries. Combined with CQRS.

**Q: How do you handle distributed transactions in microservices?**  
Use saga patterns (choreography or orchestration) to maintain eventual consistency across services. Avoid 2PC due to performance.

**Q: How do you implement health checks in a Node.js service?**  
Expose a `/health` endpoint that reports the status of dependencies (DB, Redis). Use `terminus` library that integrates with Express to provide liveness/readiness checks.

**Q: How do you implement distributed tracing? (OpenTelemetry, Jaeger)**  
Instrument services with OpenTelemetry SDK to generate spans and propagate context via headers (W3C TraceContext). Export to Jaeger, Zipkin, or other backends to trace requests across microservices.

**Q: What is a sidecar pattern?**  
A sidecar is a helper container deployed alongside the main application container, providing support functionalities (e.g., proxy, logging agent, service mesh proxy). They share the same lifecycle.

**Q: What is the strangler fig pattern for migrating a monolith to microservices?**  
Incrementally replace specific functionality of the monolith with new microservices, routing traffic to the new service gradually. Over time the monolith is "strangled" and eventually retired.

**Q: How do you handle inter-service authentication?**  
Use JWT tokens issued by a central identity service. Services validate tokens using shared public key (asymmetric). Alternatively, use mutual TLS (mTLS) or API keys with service mesh.

**Q: What is a BFF (Backend for Frontend)?**  
A BFF is a dedicated backend service tailored to a specific frontend client (mobile, web), aggregating data and reducing over-fetching, as opposed to a single general-purpose API.

**Q: How do you handle versioning in a microservices setup?**  
- API versioning: URI or header versioning for external endpoints.  
- Internal service versioning: contract testing, backward-compatible changes, or version in message schema. Use semantic versioning and feature toggles.

---

## 18. Message Queues — RabbitMQ / Kafka / Bull

### Message Queues

**Q: What is a message queue? Why would you use one?**  
A message queue is a durable buffer that decouples producers and consumers. Use for asynchronous processing, load leveling, reliability (guaranteed delivery), and microservice communication.

**Q: What is the difference between a message queue and a pub/sub system?**  
- Message queue: typically point-to-point, messages consumed by one consumer from a queue (work queue).  
- Pub/sub: broadcasts to multiple subscribers based on topics; each subscriber gets a copy.

**Q: What is RabbitMQ? What are exchanges, queues, and bindings?**  
RabbitMQ is a message broker implementing AMQP.  
- Exchanges receive messages and route them to queues based on bindings.  
- Queues store messages until consumed.  
- Bindings define the relationship between exchange and queue (routing key patterns).

**Q: What are the RabbitMQ exchange types? (direct, fanout, topic, headers)**  
- Direct: routing key exact match.  
- Fanout: broadcasts to all bound queues.  
- Topic: routing key pattern match with wildcards.  
- Headers: routing based on header attributes.

**Q: What is message acknowledgment in RabbitMQ? What happens if a consumer crashes?**  
Consumer sends ack after processing. If consumer crashes before ack, the message is re-queued and delivered to another consumer, ensuring at-least-once delivery.

**Q: What is a dead letter queue? When is it used?**  
Dead letter queue stores messages that could not be delivered or processed (expired, rejected, max retries exceeded). Used for failure analysis and manual intervention.

**Q: What is message durability vs persistence in RabbitMQ?**  
- Durable queues survive broker restart.  
- Persistent messages are written to disk. Both are needed to ensure messages survive a restart.

**Q: What is Apache Kafka? How is it different from RabbitMQ?**  
Kafka is a distributed streaming platform designed for high-throughput, persisted logs. Messages are stored in topics partitioned and replicated. Unlike RabbitMQ, Kafka retains messages for a configurable time, allowing replay, and uses consumer groups and offsets. Kafka is better for large-scale event streaming; RabbitMQ for traditional messaging with complex routing.

**Q: What is a Kafka topic, partition, consumer group, and offset?**  
- Topic: category of messages.  
- Partition: ordered, immutable log; topics split into partitions for parallelism.  
- Consumer group: set of consumers that share work (each partition consumed by one member).  
- Offset: position of a consumer in a partition.

**Q: What is Kafka's message retention policy?**  
Kafka retains messages based on time or size (e.g., 7 days or 1TB), regardless of consumption. It can also compact logs to keep latest value per key.

**Q: When would you choose Kafka over RabbitMQ?**  
When you need high throughput, event sourcing, replay capability, very large scale, and durable log semantics. RabbitMQ for low-latency, complex routing, priority queues, and where brokered delivery is simpler.

**Q: What is Bull/BullMQ? How does it use Redis as a backend?**  
Bull is a Node.js job queue library using Redis for persistence. It supports job priorities, delays, retries, and concurrency. BullMQ is the modern rewrite. Redis stores job data and uses pub/sub for real-time events.

**Q: How do you implement job queues with BullMQ? What are job priorities and retries?**  
Define a Queue, add jobs with options `{ priority, attempts, backoff }`. Workers process jobs. Priority determines order; retries automatically re-attempt on failure with exponential backoff.

**Q: How do you handle failed jobs in BullMQ?**  
Jobs that exceed retries are moved to the failed set. Monitor failed jobs via events, dashboard (Bull Board). You can manually retry or remove.

**Q: What is the competing consumers pattern?**  
Multiple consumer instances listen to the same queue; each message is delivered to only one consumer, distributing workload. Achieved with RabbitMQ queues or Kafka consumer groups.

**Q: What is at-least-once vs at-most-once vs exactly-once delivery?**  
- At-most-once: message may be lost but not duplicated.  
- At-least-once: message never lost, but may be delivered multiple times (requires idempotent processing).  
- Exactly-once: message processed exactly once, very hard to achieve end-to-end; Kafka provides some transactional support.

---

## 19. Testing in Node.js

### Testing Fundamentals

**Q: What is the testing pyramid in Node.js context? (unit, integration, e2e)**  
The testing pyramid suggests many fast unit tests (isolated functions), fewer integration tests (modules working together, DB), and few end-to-end tests (full system). In Node.js, unit tests with Jest, integration with supertest + test DB, e2e with Cypress/Playwright.

**Q: What is Jest? What is Mocha + Chai? How do they compare?**  
Jest: full-featured testing framework with built-in assertion library, mocking, coverage, snapshot testing. Mocha is a test runner, often paired with Chai (assertion) and Sinon (mocks). Jest offers a cohesive out-of-the-box experience; Mocha is more flexible.

**Q: What is `supertest`? How do you test Express routes with it?**  
`supertest` allows testing HTTP servers by making requests and asserting responses. Example:
```javascript
const request = require('supertest');
const app = require('../app');
await request(app).get('/users').expect(200);
```

**Q: What is the difference between a mock, stub, and spy?**  
- Mock: object with pre-programmed expectations (e.g., `jest.fn()` with expected calls).  
- Stub: replaces a function to return fixed values, without verifying interactions.  
- Spy: wraps a real function to record calls but still executes original logic.

**Q: How do you mock modules in Jest? (`jest.mock()`, `jest.spyOn()`)**  
`jest.mock('module')` auto-mocks all exports. `jest.spyOn(object, 'method')` spies on an existing method. Both can override implementations.

**Q: How do you mock external API calls in tests? (nock, msw, jest.fn)**  
- `nock`: intercepts HTTP requests at the Node.js level, returning mock responses.  
- `msw`: intercepts at the service worker level, works in Node and browser.  
- `jest.fn` can mock functions that make API calls, replacing them with stubs.

**Q: How do you test a function that uses `setTimeout`? (fake timers: `jest.useFakeTimers()`)**  
Use `jest.useFakeTimers()` to control time. Then `jest.advanceTimersByTime()` or `jest.runAllTimers()` to trigger callbacks. Restore with `jest.useRealTimers()`.

**Q: How do you test async code in Jest?**  
Return a promise from the test; Jest waits. Or use `async/await`. Use `expect.assertions()` to verify callbacks were called. Or `done` callback (deprecated for promises).

**Q: What is `beforeAll`, `beforeEach`, `afterAll`, `afterEach`?**  
Setup/teardown hooks in test suites. `beforeAll` runs once before all tests, `beforeEach` before each test, `afterEach` after each, `afterAll` once after all.

**Q: What is code coverage? What does 100% coverage guarantee?**  
Code coverage measures which lines/branches/functions are executed during tests. 100% coverage does not guarantee correctness, only that all code was touched; it does not catch missing requirements or edge cases.

**Q: How do you test database interactions? (in-memory DB, test containers, mocking)**  
- Use an in-memory database (e.g., sqlite in-memory, mongodb-memory-server) for fast, isolated tests.  
- Test containers: real database in Docker for integration tests.  
- Mock the database layer entirely for unit tests.

**Q: What are snapshot tests? When are they useful in a backend context?**  
Snapshot tests record a serialized value and compare subsequent runs. In backend, they can validate API response structures, complex objects. Useful to catch unintended changes, but can be brittle.

**Q: What is `testcontainers`? How does it help with integration tests?**  
Testcontainers is a library that starts real databases/message queues in Docker containers for integration tests, providing a consistent, disposable environment without manual setup.

**Q: How do you test error handling middleware?**  
Use supertest to trigger a route that throws or calls `next(error)`, then assert the response status and body matches the error handler's output.

**Q: How do you test WebSocket handlers?**  
Create a WebSocket client (e.g., `ws`) in the test, connect to the server, send messages, and assert received responses. Use `socket.io-client` for socket.io.

**Q: What is contract testing? What is Pact?**  
Contract testing ensures that services (provider and consumer) adhere to a shared contract. Pact is a framework for contract testing; consumer defines expectations, provider verifies them, preventing integration issues.

**Q: What is TDD (Test-Driven Development)? How do you apply it in Node.js?**  
TDD cycle: write a failing test, write minimal code to pass, refactor. In Node.js, use Jest to write tests first for a function/API, then implement. Enforces design and test coverage.

**Q: What is mutation testing?**  
Mutation testing introduces small bugs (mutations) into code and checks if tests catch them. It measures test suite quality beyond coverage. Tools: Stryker.

---

## 20. DevOps — Docker, CI/CD & Deployment

### Docker & Containers

**Q: What is Docker? What is a container vs a virtual machine?**  
Docker is a platform for developing, shipping, and running applications inside lightweight containers. Containers share the host OS kernel and isolate processes; VMs virtualize entire hardware with full OS, heavier.

**Q: How do you write a `Dockerfile` for a Node.js application?**  
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

**Q: What is a multi-stage build in Docker? Why is it important for Node.js?**  
Multi-stage builds use multiple `FROM` statements; you can compile/build in one stage and copy only artifacts to the final image, reducing image size and removing build-time dependencies.

**Q: What is `.dockerignore`? What should you include in it?**  
Similar to `.gitignore`, it excludes files from the build context. Include `node_modules`, `npm-debug.log`, `.git`, `Dockerfile`, `.env`, `coverage`, etc., to speed up builds and avoid leaking secrets.

**Q: What is the difference between `COPY` and `ADD` in a Dockerfile?**  
- `COPY`: copies local files into the image.  
- `ADD`: also supports tar extraction and URL downloading; use `COPY` unless you need those features, for clarity.

**Q: What is `CMD` vs `ENTRYPOINT` in a Dockerfile?**  
- `CMD`: provides default command and arguments that can be overridden.  
- `ENTRYPOINT`: sets the executable; `CMD` then becomes default arguments to entrypoint. `ENTRYPOINT` is harder to override.

**Q: How do you optimize Docker image size for a Node.js app?**  
- Use small base (alpine).  
- Multi-stage builds.  
- `npm ci --only=production` to avoid devDependencies.  
- Remove unnecessary files.  
- Use `.dockerignore`.

**Q: What is Docker Compose? How do you use it for a Node.js + MongoDB + Redis stack?**  
Docker Compose defines multi-container applications in a YAML file. Define services: `web` (Node.js), `mongo`, `redis`. Link them via network. Start with `docker-compose up`.

**Q: How do you handle environment variables in Docker containers?**  
Pass with `-e` flag, or use `env_file`, or in Docker Compose `environment` section. For secrets, use Docker secrets or external vaults, not hardcoded.

**Q: What is a health check in Docker?**  
A health check command tests container's health; if it fails, container can be restarted. Example: `HEALTHCHECK CMD curl --fail http://localhost:3000/health || exit 1`.

**Q: What is Kubernetes? What are pods, services, deployments, and ingress?**  
Kubernetes orchestrates containers. Pod: smallest deployable unit (one or more containers). Service: stable network endpoint for pods. Deployment: manages replicas and updates. Ingress: external HTTP access routing.

**Q: What is a rolling deployment vs blue-green deployment vs canary deployment?**  
- Rolling: gradually replaces old instances with new.  
- Blue-green: two environments, swap traffic from old (blue) to new (green) instantly.  
- Canary: small percentage of traffic to new version, gradually increase.

### CI/CD & Deployment

**Q: What is a CI/CD pipeline? What does a typical Node.js CI pipeline look like?**  
CI/CD automates code integration, testing, and deployment. A Node.js pipeline: lint, test (unit, integration), build, push Docker image, deploy to staging, run e2e, deploy to production.

**Q: What is GitHub Actions? How do you set up a basic CI pipeline for a Node.js app?**  
GitHub Actions runs workflows. Create `.github/workflows/ci.yml`: on push, use `actions/checkout`, setup Node, `npm ci`, `npm test`, etc. Add secrets for env vars.

**Q: What is the difference between `npm start` and using PM2 in production?**  
`npm start` runs the application as a single process. PM2 provides process management, clustering, auto-restart, log management, and daemonization, making it suitable for production.

**Q: What is PM2? What are its key features?**  
(Already covered) Process manager with clustering, monitoring, log management, and deployment.

**Q: What is a reverse proxy? How do you configure Nginx in front of a Node.js app?**  
A reverse proxy accepts requests from clients and forwards to backend servers. Nginx config: `location / { proxy_pass http://localhost:3000; proxy_set_header ... }`. It handles SSL, static files, load balancing.

**Q: What is SSL termination at the load balancer level?**  
SSL termination means the load balancer decrypts HTTPS traffic and forwards plain HTTP to backend services, offloading encryption overhead from Node.js.

**Q: What is a 12-factor app? Which factors are most relevant to Node.js?**  
12-factor app methodology for building scalable SaaS. Relevant factors: codebase in version control, dependencies explicitly declared, config in environment, backing services as attached resources, build/release/run separation, stateless processes, port binding, concurrency via process model, disposability (fast startup/graceful shutdown), dev/prod parity, logs as event streams, admin processes.

**Q: How do you manage secrets in production? (env vars, Vault, AWS Secrets Manager)**  
Inject secrets at runtime via environment variables from a secret manager (HashiCorp Vault, AWS Secrets Manager, Kubernetes secrets). Avoid storing in config files. Rotate regularly.

**Q: What is infrastructure as code? What is Terraform?**  
IaC manages infrastructure through code instead of manual processes. Terraform is a tool to define and provision infrastructure across cloud providers declaratively.

**Q: How do you implement zero-downtime deployment for a Node.js app?**  
(Already answered) Use PM2 graceful reload or Kubernetes rolling updates, with health checks and readiness probes.

---

## 21. TypeScript with Node.js

**Q: How do you set up a TypeScript Node.js project from scratch?**  
1. `npm init -y`  
2. Install `typescript`, `@types/node`, `ts-node`, `nodemon` as devDependencies.  
3. Create `tsconfig.json` (using `npx tsc --init`).  
4. Configure `outDir`, `rootDir`, `strict`.  
5. Write code in `src/`.  
6. Add scripts: `"dev": "ts-node src/index.ts"`, `"build": "tsc"`, `"start": "node dist/index.js"`.

**Q: What is `tsconfig.json`? What are the key compiler options? (`strict`, `target`, `module`, `outDir`, `paths`)**  
`tsconfig.json` configures TypeScript compiler. Key options: `strict` enables all strict checks; `target` sets ECMAScript version; `module` (commonjs, esnext); `outDir` output directory; `rootDir` source; `paths` for module aliasing.

**Q: What is the difference between `CommonJS` and `ESNext` as `module` target?**  
- `CommonJS` outputs `require`/`exports`.  
- `ESNext` outputs ES module `import`/`export` (if `type: "module"`). Choose based on Node.js support.

**Q: How do you type `req`, `res`, `next` in an Express route with TypeScript?**  
Install `@types/express`. Route handler: `(req: Request, res: Response, next: NextFunction) => void`. For custom properties, augment `Request`.

**Q: How do you type environment variables in TypeScript?**  
Declare a module augmentation for `process.env` or use a library like `env-var` with types. Or create a config module that reads and casts values.

**Q: What is declaration merging? How do you extend `Request` type in Express?**  
Declaration merging allows combining multiple declarations of the same interface. Extend `Express.Request` by adding a `.d.ts` file:
```typescript
declare namespace Express {
  interface Request {
    user?: UserPayload;
  }
}
```

**Q: How do you use generics in service classes and repositories?**  
Define a generic base repository class: `class Repository<T> { findAll(): Promise<T[]> {} }`. Then extend with specific type: `class UserRepository extends Repository<User> {}`. Increases reusability.

**Q: What is `ts-node`? What is `ts-node-dev`?**  
`ts-node` executes TypeScript files directly without pre-compilation, useful for development. `ts-node-dev` restarts on file changes (similar to nodemon) with faster compilation.

**Q: How do you handle JSON imports in TypeScript?**  
Enable `resolveJsonModule` in `tsconfig.json`. Then `import data from './data.json'` works, with types inferred.

**Q: What are path aliases in TypeScript? How do you configure them for Node.js?**  
Define `paths` in `tsconfig.json` (e.g., `"@services/*": ["src/services/*"]`). To work at runtime, use `module-alias` package or `tsconfig-paths` with `ts-node`. For compiled output, use `tsc-alias` or similar.

**Q: What is `zod`? How does it combine runtime validation with TypeScript types?**  
`zod` is a schema validation library. Define a schema, infer the TypeScript type: `const UserSchema = z.object({ name: z.string() }); type User = z.infer<typeof UserSchema>;`. It validates at runtime and provides static typing.

**Q: How do you type a MongoDB document with Mongoose + TypeScript?**  
Define an interface extending `mongoose.Document`, or use `mongoose.Schema` with type inference. E.g., `interface IUser extends Document { name: string; }`. Or use `@typegoose/typegoose` for decorator-based typing.

---

## 22. Design Patterns in Node.js

### Creational Patterns

**Q: What is the Singleton pattern? When is it used in Node.js? (DB connection, config)**  
Singleton ensures only one instance of a class exists. In Node.js, module caching already provides singletons; exporting an instance of a DB connection (e.g., `mongoose.connect()`) or a config object works as a singleton.

**Q: What is the Factory pattern? Give a Node.js example.**  
Factory pattern centralizes object creation. Example: a logger factory that returns the appropriate logger (console, file) based on environment.

**Q: What is Dependency Injection? How do you implement it without a framework?**  
DI passes dependencies into a component rather than having it create them. In Node.js, you can pass DB instance, logger, etc., as constructor arguments or via function parameters. For simplicity, use a DI container like `awilix` for automatic injection.

**Q: What is IoC (Inversion of Control)?**  
IoC inverts the flow of control; the framework calls your code. DI is a form of IoC. In Node.js, Express middleware chain is an example: you define middleware, Express controls when they are called.

### Structural Patterns

**Q: What is the Repository pattern? Why is it used in Node.js backends?**  
Repository pattern abstracts data access, providing collection-like methods. It decouples business logic from ORM/database details, making it easier to swap data sources and test.

**Q: What is the Service layer pattern? How does it separate concerns from controllers?**  
Service layer contains business logic; controllers handle HTTP request/response. This separates concerns, allowing reuse of logic across different transports (HTTP, WebSocket, CLI).

**Q: What is the Adapter pattern? Give a Node.js use case.**  
Adapter converts one interface to another. Example: adapting a third-party payment gateway API into a common interface that your application expects, so switching providers requires only a new adapter.

**Q: What is the Decorator pattern? How does it relate to Express middleware?**  
Decorator adds behavior to an object dynamically. Express middleware decorates the request handling by adding functionality (logging, auth) before/after route handler, like wrapping.

**Q: What is the Proxy pattern? When is it used in Node.js? (caching, rate limiting)**  
Proxy controls access to an object. In Node.js, a proxy can add caching, logging, or rate limiting to an API client. Example: a redis-cached proxy for database queries.

### Behavioral Patterns

**Q: What is the Observer pattern? How does `EventEmitter` implement it?**  
Observer pattern defines a one-to-many dependency between objects. `EventEmitter` maintains a list of listeners; when an event is emitted, all listeners are notified. Used throughout Node.js (streams, process events).

**Q: What is the Pub/Sub pattern? How is it different from Observer?**  
Pub/Sub uses a message broker/topic to decouple publishers and subscribers, often across distributed systems. Observer is a direct relationship within the same process. Pub/Sub is more loosely coupled and scalable.

**Q: What is the Strategy pattern? Give a Node.js example.**  
Strategy pattern defines a family of algorithms and makes them interchangeable. Example: different authentication strategies in Passport.js — you can swap local strategy with OAuth strategy without changing the authentication flow.

**Q: What is the Chain of Responsibility pattern? How does Express middleware implement it?**  
Chain of Responsibility passes a request along a chain of handlers. Express middleware chain does exactly this: each middleware decides to handle or pass to the next by calling `next()`.

**Q: What is the Command pattern?**  
Command pattern encapsulates a request as an object, allowing parameterization, queuing, logging. In Node.js, job queues (Bull) where each job is a command with parameters.

### Node.js Specific Patterns

**Q: What is the Middleware pattern? How is it different from traditional OOP patterns?**  
Middleware pattern uses a pipeline of functions to process a request/response. It’s functional, composable, and avoids complex inheritance hierarchies. Express popularized it.

**Q: What is the callback pattern? What problems does it cause at scale?**  
The callback pattern uses functions passed as arguments to handle async results. Problems: callback hell, difficult error handling, lack of composability. Mitigated by Promises and async/await.

**Q: What is the Reactor pattern? How does it relate to the event loop?**  
Reactor pattern is the design behind the event loop: it demultiplexes I/O events and dispatches them to registered handlers. The event loop acts as the synchronous event demultiplexer.

**Q: What is the pipeline pattern in Node.js streams?**  
Streams can be connected using `.pipe()` or `pipeline()`, where data flows through a series of transforms. Each step is a processing unit, forming a pipeline.

**Q: What is module-level singleton pattern (leveraging module cache)?**  
Node.js caches modules after first `require`. By exporting an instance of a class or object, you effectively create a singleton because subsequent requires return the same object. This is a common way to share DB connections.

---

## 23. GraphQL with Node.js

**Q: What is GraphQL? How does it differ from REST?**  
GraphQL is a query language for APIs, allowing clients to request exactly the data they need. REST exposes fixed endpoints returning fixed structures; GraphQL has a single endpoint, and the client shapes the response, reducing over/under-fetching.

**Q: What are the three GraphQL operation types: query, mutation, and subscription?**  
- Query: read data (like GET).  
- Mutation: modify data (like POST/PUT/DELETE).  
- Subscription: real-time updates via WebSocket.

**Q: What is a GraphQL schema? What is SDL (Schema Definition Language)?**  
Schema defines the types, queries, mutations, and subscriptions available. SDL is the syntax to define the schema using `type` and `input` keywords. Example:
```graphql
type User { id: ID!, name: String }
type Query { users: [User] }
```

**Q: What is a resolver in GraphQL?**  
Resolvers are functions that resolve the value for a type's field. They define how to fetch data for each field. You provide a resolver map: `{ Query: { users: () => db.getUsers() } }`.

**Q: What is `Apollo Server`? How do you set it up with Express?**  
Apollo Server is a community-driven GraphQL server. Integrate with Express: `const server = new ApolloServer({ typeDefs, resolvers }); await server.start(); server.applyMiddleware({ app });`. It serves the GraphQL endpoint and optional playground.

**Q: What is `graphql-yoga`?**  
`graphql-yoga` is a fully-featured GraphQL server built on top of Express/Apollo, with defaults for CORS, subscriptions, file uploads, etc. It’s a simpler alternative.

**Q: What is the N+1 problem in GraphQL? What is DataLoader?**  
N+1 problem occurs when resolvers make separate DB queries for each related item. DataLoader batches and caches requests, turning N+1 into a few batched queries. Example: `dataLoader.load(userId)` collects keys and dispatches a single query.

**Q: How do you implement authentication/authorization in GraphQL resolvers?**  
Pass context (e.g., `{ user }`) to resolvers via Apollo context function, which extracts user from request headers (JWT). In resolvers, check context.user and throw `AuthenticationError` or `ForbiddenError`. Use custom directives for declarative auth.

**Q: What is schema stitching vs federation?**  
- Schema stitching combines multiple GraphQL schemas into one, but can be brittle.  
- Federation (Apollo Federation) enables composing a unified graph from multiple services, with a gateway that distributes queries. More scalable for microservices.

**Q: What is a GraphQL directive? Give an example.**  
Directives provide instructions to the schema or query. Example: `@deprecated(reason: "Use newField")` marks a field deprecated. Custom directives can implement authentication (`@auth(requires: ADMIN)`).

**Q: What is persisted queries?**  
A technique where the client sends a hash of the query instead of the full query string. The server stores the mapping, reducing request size and preventing arbitrary queries (security). Apollo supports automatic persisted queries (APQ).

**Q: What is introspection? Should you disable it in production?**  
Introspection allows querying the schema itself. Disable in production to hide the schema from attackers and prevent automated attacks, unless you need it for client tools. Apollo can disable via `introspection: false`.

**Q: What is the difference between GraphQL subscription and polling?**  
Subscription uses WebSocket to push real-time updates to clients efficiently. Polling repeatedly queries the server at intervals, wasting resources. Subscriptions are event-driven.

**Q: How do you handle file uploads in GraphQL?**  
Use the GraphQL multipart request spec. Apollo Server supports file uploads via `graphql-upload` (or built-in in older versions). Define a scalar `Upload`, and handle the file stream in the resolver.

**Q: What is code-first vs schema-first GraphQL?**  
- Schema-first: write SDL schema first, then implement resolvers.  
- Code-first: define the schema programmatically using decorators or builders (e.g., TypeGraphQL, Nexus). The schema is generated from code, ensuring type consistency.

---

## 24. Advanced / Senior-Level Questions

### Deep Internals

**Q: Explain the complete lifecycle of an HTTP request in a Node.js + Express application.**  
1. TCP connection established, HTTP request parsed by Node.js `http` module.  
2. Event loop picks up the request, creates `req` and `res` objects.  
3. Express runs the request through its middleware stack in order.  
4. Each middleware can modify `req`/`res`, end the response, or call `next()`.  
5. Route matching directs to appropriate route handler.  
6. Handler processes request, may query DB, call external services.  
7. Response sent via `res.send()` etc., underlying socket writes data.  
8. Response finishes; if `Connection: close`, socket closes; else reused.  
9. Middleware after sending may run (error if headers sent).  
10. Resources cleaned up.

**Q: How does Node.js perform I/O? Walk through what happens when `fs.readFile()` is called.**  
1. `fs.readFile` delegates to libuv.  
2. libuv allocates a thread from the thread pool if the operation is blocking (file I/O).  
3. The JS thread continues executing the next line (non-blocking).  
4. When the thread completes reading, it places a completion event in the event loop's pending I/O queue.  
5. The event loop, during the poll phase, picks up the event and invokes the callback provided to `readFile`.  
6. The callback is executed on the main thread.

**Q: What is V8's JIT (Just-In-Time) compilation? What is hidden class optimization?**  
V8 compiles JavaScript to machine code at runtime using two compilers: Ignition (interpreter) and TurboFan (optimizing compiler). Hidden classes (or map) speed up property access; V8 creates a hidden class for each object shape. Objects with same property order share the same hidden class, enabling fast access. Dynamically adding properties creates new hidden classes, degrading performance.

**Q: What is inline caching in V8? How does it affect performance?**  
Inline caching is an optimization where V8 caches the location of a property access after the first lookup, assuming the object shape (hidden class) remains the same. Subsequent accesses become direct memory reads. When the shape changes, the cache misses, causing deoptimization.

**Q: What is deoptimization in V8? What causes it?**  
When V8's optimizing compiler makes assumptions (like a function is always called with integers) and those assumptions are violated (e.g., passing a string), it deoptimizes, reverting to the generic bytecode. Causes: changing object shapes (adding/deleting properties), passing unexpected types, using `eval` or `arguments`, try/catch in hot functions.

**Q: What is the heap vs the stack in Node.js memory?**  
- Stack: stores local variables and function call frames; fast, small, LIFO.  
- Heap: dynamic memory for objects, strings, closures; managed by GC. Larger but slower allocation.

**Q: How does the garbage collector decide what to collect? What are generations?**  
V8's GC is generational: it separates objects into young (new space) and old (old space). Young generation is collected frequently via Scavenge (copying survivors). If objects survive enough scavenges, they're promoted to old generation. Old generation uses Mark-Sweep and Mark-Compact. GC starts from roots (global, stack) and marks reachable objects; unreachable are collected.

**Q: What is `--heap-prof` and `--cpu-prof` in Node.js?**  
- `--heap-prof`: generates heap profiling snapshots for memory analysis.  
- `--cpu-prof`: records CPU profile output (similar to Chrome DevTools profiler). Both produce files that can be loaded in Chrome DevTools.

**Q: What is `AsyncLocalStorage`? How do you use it for request context propagation?**  
`AsyncLocalStorage` creates a storage context that is maintained across asynchronous operations without explicitly passing data. Usage: `const als = new AsyncLocalStorage(); als.run({ requestId }, () => { ... })`. Inside the callback, `als.getStore()` returns the context. Perfect for logging, request tracing.

**Q: What is `async_hooks`? How is `AsyncLocalStorage` built on top of it?**  
`async_hooks` provides low-level hooks to track the lifecycle of async resources (promises, timers, etc.). `AsyncLocalStorage` uses `async_hooks` internally to propagate context, but presents a simpler API. Prior to `AsyncLocalStorage`, libraries like `cls-hooked` used `async_hooks`.

**Q: How do you implement structured concurrency in Node.js?**  
Structured concurrency ensures that concurrent tasks are properly scoped and cancelled together. Implement using `Promise.allSettled` with `AbortController`, or use libraries like `p-queue`. Cancel all child tasks when parent is cancelled. The pattern prevents orphan promises and resource leaks.

**Q: What is `AbortController` and `AbortSignal` used for in Node.js?**  
`AbortController` is a standard mechanism to abort one or more asynchronous operations. Create `const ac = new AbortController();`, pass `signal` to fetch, streams, or custom code that listens for `abort` event. Call `ac.abort()` to cancel.

**Q: How does `require()` differ from `import()` in terms of blocking vs non-blocking?**  
`require()` is synchronous; it blocks the event loop while loading a module. `import()` is asynchronous and returns a Promise, non-blocking. In modern Node.js, `import()` is used for dynamic loading; static `import` is also compiled synchronously but handled at parse time.

**Q: What is the `vm` module in Node.js? What are its security implications?**  
`vm` allows executing JavaScript code in a sandboxed V8 context. It can provide isolation but is not a security sandbox; untrusted code can escape and access the host. Use `vm2` (now deprecated) or `isolated-vm` for stronger sandboxing. Avoid running arbitrary untrusted code.

**Q: What is NAPI / Node Addons? When would you write a native Node.js addon?**  
N-API (Node-API) is a stable ABI for building native addons in C/C++. Write an addon when you need to call existing C++ libraries, perform CPU-intensive computations with native speed, or interface with OS-specific APIs. Modern addons use `node-addon-api`.

### Architecture & Design Decisions

**Q: How do you design a Node.js service for 10,000 requests per second?**  
- Use clustering (multiple workers) or run multiple instances behind a load balancer.  
- Optimize I/O: connection pooling, caching (Redis).  
- Avoid blocking the event loop: offload CPU tasks.  
- Use fast web framework (Fastify instead of Express for marginal gains).  
- Ensure stateless design.  
- Use a reverse proxy (Nginx) for connection management.  
- Profile and monitor continuously.

**Q: You notice your Node.js service's memory is growing unboundedly in production. How do you investigate?**  
1. Monitor memory usage over time (process.memoryUsage).  
2. Take heap snapshots using `--inspect` or `heapdump`, compare to see which objects are retained.  
3. Look for common causes: event listener leaks, large caches, unclosed streams, closures.  
4. Use `clinic doctor` or APM tools.  
5. Reproduce in staging, isolate recent changes.

**Q: Your event loop is showing high lag (200ms+). Walk through your debugging process.**  
1. Confirm lag using `perf_hooks.monitorEventLoopDelay`.  
2. Profile CPU: `clinic doctor` or Chrome DevTools recording during high lag.  
3. Identify synchronous operations (e.g., large `JSON.parse`, regex, synchronous loop).  
4. Check for blocking DB queries, synchronous `fs` calls.  
5. Review recent code changes.  
6. Offload CPU work or break into chunks.

**Q: How would you migrate a monolith Node.js app to microservices?**  
Use the Strangler Fig pattern: identify bounded contexts, extract one service at a time. Route traffic through an API gateway to redirect specific endpoints to the new service. Keep the monolith working until fully replaced. Ensure data is migrated/separated gradually.

**Q: How do you ensure data consistency across multiple microservices?**  
Employ eventual consistency using sagas (orchestration or choreography). Each service maintains its own data; events are published after local transactions. Compensating actions handle failures. Avoid distributed transactions.

**Q: How do you design an idempotent API?**  
1. Use idempotency keys: client sends a unique key, server stores key and response, returns cached response on subsequent requests.  
2. Implement POST as idempotent by checking for existing resource or using PUT for full replacement.  
3. Design operations naturally idempotent (e.g., setting a value, not incrementing blindly).

**Q: How do you implement distributed locking in Node.js?**  
Use Redis with Redlock algorithm or a single instance with `SETNX` and TTL. Ensure lock is released only by owner. Handle lock expiry and contention. Use `redlock` library. Alternative: use PostgreSQL advisory locks for simple cases.

**Q: How do you handle long-running background jobs in a Node.js API?**  
Use job queues (BullMQ) to enqueue jobs. The API responds with a job ID and status endpoint. Workers process jobs asynchronously. Store job state in DB/Redis.

**Q: How do you implement feature flags in a Node.js service?**  
Use a feature flag service (LaunchDarkly, or custom config in DB). Wrap new code paths with a check: `if (await isEnabled('new-feature', user)) { ... }`. Allow gradual rollout via percentage or targeted users. Invalidate cache on flag change.

**Q: How do you design an API that handles both synchronous and asynchronous workflows?**  
For long-running operations, return `202 Accepted` with a `Location` header pointing to a status resource. Provide webhook or polling endpoint to retrieve result. Synchronous responses for immediate processing.

**Q: What are the trade-offs between using an ORM vs raw SQL in a high-performance Node.js app?**  
ORM: faster development, type safety, migrations, but can generate suboptimal queries, overhead. Raw SQL: precise control, better performance for complex queries, but more boilerplate and prone to injection without care. For high performance, a query builder like Knex offers a middle ground.

**Q: How do you design a multi-tenant Node.js SaaS application?**  
Strategies:  
- Database per tenant (strong isolation, harder to manage).  
- Shared database with tenant ID column (simpler, risk of data leaks).  
- Shared schema, separate schemas.  
Implement tenant context middleware that sets the tenant ID for every request, used in queries automatically. Use connection pools scoped to tenant if needed.

**Q: How do you implement a webhook receiver in Node.js?**  
Expose an endpoint that accepts POST requests. Validate payload (e.g., HMAC signature). Acknowledge immediately with 200 (or queued). Process asynchronously (queue) to avoid timeouts. Ensure idempotency (deduplicate events). Use a queue for reliability.

**Q: How would you design a file processing service (e.g., image resizing)?**  
Users upload file -> store in temporary location (S3) -> API enqueues a job (file path, desired operations) -> Worker pool picks up job, processes (using sharp for images), uploads result, updates status. Webhook/notification on completion. Use streams for large files.

---

## 25. Scenario-Based / System Design Questions

### Design Problems

**Design a URL shortener service:**  
- API: POST `/shorten` with long URL, returns short code.  
- Short code: base62 encoded auto-incrementing ID or random string (6-8 chars).  
- Storage: relational DB (URLs table with short_code, long_url, created_at, clicks).  
- Redirect: GET `/:code` -> 302 redirect, increment counter.  
- Rate limiting per IP/user.  
- Caching: Redis for hot codes.  
- Analytics: record clicks separately.  
- Collision handling: unique index on code; retry on conflict.

**Design a real-time chat application:**  
- WebSocket (socket.io) for real-time messaging.  
- Store messages in DB (MongoDB or PostgreSQL) with chat room, sender, timestamp.  
- Online status: via presence (socket.io rooms, heartbeat).  
- Read receipts: acknowledge message ID from client.  
- Offline messages: push notification or store and deliver on reconnect.  
- Scaling: Redis adapter for multi-instance, use a message queue for reliable persistence.  
- Authentication: JWT validated on connection.

**Design a job queue system:**  
- Use BullMQ backed by Redis.  
- Support delayed jobs, priorities, retries with backoff, dead letter queue.  
- API to add jobs, workers to process.  
- Monitoring dashboard (Bull Board).  
- Persist job state, handle worker crashes with timeouts.  
- Concurrency control per worker.

**Design a notification service:**  
- API to send notification (email, SMS, push) with recipient, template, data.  
- Queue jobs per channel (BullMQ).  
- Template engine for rendering content.  
- User preferences: which channels, opt-out.  
- Rate limiting per channel.  
- Idempotency keys to prevent duplicate sends.  
- Asynchronous processing; webhook for delivery status updates.

**Design a file upload and processing service:**  
- Upload endpoint with multipart (multer), store in temporary S3.  
- Return immediate response with file ID.  
- Enqueue processing job (image resize, video transcode).  
- Workers process files, store output in S3.  
- Progress tracking via WebSocket or polling.  
- Signed URLs for secure downloads.  
- Security: validate file type, size limit, virus scan.

**Design an authentication service:**  
- Central auth service issuing JWTs (access + refresh).  
- User management: register, login, logout (blacklist tokens).  
- OAuth2 integration for social login.  
- MFA (TOTP).  
- Rate limiting, brute-force protection.  
- Token revocation via blacklist in Redis.  
- Microservices validate tokens using public key (RS256).  
- Refresh token rotation.

**Design a rate limiting service:**  
- Middleware that tracks requests per key (API key, IP).  
- Use sliding window algorithm with Redis sorted sets for accuracy.  
- Return `429` and headers.  
- Distributed: shared Redis, but can be approximate with local counters + eventual sync.  
- Support burst limits.  
- Admin endpoint to set limits dynamically.

**Design an audit log system:**  
- Capture events: middleware to log actions (user, action, resource, timestamp, changes).  
- Store in an append-only database (time-series DB or separate table).  
- Ensure immutability (no update/delete allowed).  
- Search and filter capability (Elasticsearch).  
- Retention policy.  
- Asynchronous logging to avoid affecting primary API.

**Design a payment processing service:**  
- Accept payment requests; generate idempotency key.  
- Integrate with payment gateway (Stripe, PayPal).  
- Handle webhooks for asynchronous confirmation.  
- Retry with exponential backoff.  
- Reconciliation jobs comparing internal records with gateway.  
- Idempotency to prevent duplicate charges.  
- Secure storage of payment tokens.

**Design a search service using Elasticsearch:**  
- Index data from primary DB (sync via CDC or change streams).  
- API accepts search queries, translates to Elasticsearch DSL.  
- Use analyzers, tokenizers for full-text.  
- Pagination with search_after.  
- Reindexing scripts.  
- Caching frequent queries.

**Design a caching layer for a high-traffic Node.js API:**  
- Cache-aside pattern with Redis.  
- Key generation based on request parameters.  
- TTL per endpoint.  
- Invalidation: delete on data mutation (write-through or publish event).  
- Stale-while-revalidate to reduce latency.  
- Cache stampede protection using distributed lock.  
- Monitor hit ratio.

**Design a multi-tenant API with data isolation at the database level:**  
- Separate database per tenant (strong isolation).  
- Connection pool per tenant or dynamically switch database based on tenant context.  
- Tenant identification via subdomain or JWT claim.  
- Middleware resolves tenant and sets DB connection.  
- Backup and restore per tenant.  
- Migrations must apply to all tenant databases.

**Design a webhook delivery system:**  
- Accept subscription (URL, events).  
- When event occurs, enqueue delivery job.  
- Retry with exponential backoff on failure.  
- Store delivery attempts.  
- At-least-once delivery; idempotency key in payload.  
- Monitor failures, dead letter queue after max retries.  
- Signature (HMAC) to verify sender.

**Design a distributed task scheduler:**  
- Multiple scheduler instances with leader election (Redis lock) to avoid duplicate execution.  
- Cron-like expressions parsed.  
- When due, enqueue job to a queue.  
- Workers process jobs.  
- Ensure exactly-once execution per schedule.  
- Store schedules and last run times in DB.

### Scenario-Based Debugging

**Your Node.js API's response times are spiking to 5 seconds under moderate load. How do you diagnose?**  
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

**After deploying a new version, one of your services is causing cascading failures. What do you do?**  
1. Immediately rollback the deployment if possible.  
2. If not, scale up healthy instances, apply circuit breakers.  
3. Check logs for errors (connection refused, timeouts).  
4. Verify dependencies (DB, Redis) not overloaded.  
5. Check if the new version introduced a bug causing excessive retries or blocked event loop.  
6. Implement health checks to prevent spreading.  
7. Post-incident: improve testing, canary releases.

**Your PostgreSQL queries that used to be fast are now taking 3 seconds. How do you debug?**  
1. Check query plan with `EXPLAIN ANALYZE`.  
2. Look for missing indexes, sequential scans.  
3. Check for table bloat, outdated statistics (`VACUUM ANALYZE`).  
4. Verify hardware resource contention.  
5. See if data volume has grown significantly.  
6. Look for lock contention.  
7. Enable slow query logging.

**A Redis `KEYS *` command is running in production and causing latency spikes. How do you fix it and prevent recurrence?**  
- Immediately kill the session running it if possible.  
- Replace `KEYS` with `SCAN` in application code.  
- Implement code reviews to catch dangerous commands.  
- Rename dangerous commands in Redis config (`rename-command KEYS ""`).  
- Monitor with Redis slowlog.

**Your JWT tokens are somehow being forged in production. What is your incident response process?**  
1. Rotate the signing secret/key immediately.  
2. Invalidate all existing tokens if possible (blacklist).  
3. Investigate if the secret was leaked (logs, source code).  
4. Check if algorithm was set to `none` or weak key.  
5. Review access logs for unauthorized access.  
6. Force all users to re-authenticate.  
7. Implement stronger key management (Vault, rotation).

**Your message queue is growing without consumers processing messages. What are the possible causes?**  
- Consumers crashed or not running.  
- Consumers stuck in a deadlock or slow processing loop.  
- Message format changed and consumers are failing to parse, causing retries and redeliveries.  
- Network issues between consumers and queue.  
- Queue bound to wrong exchange/routing.  
Check consumer logs, queue state, and restart consumers.

**A deployment caused one pod to restart in a loop (CrashLoopBackOff). How do you debug?**  
1. Get pod logs: `kubectl logs <pod> --previous`.  
2. Check exit code.  
3. Look for uncaught exceptions, missing environment variables, configuration errors.  
4. Verify health check probes (liveness/readiness) are correctly configured; maybe app isn't starting fast enough.  
5. Check resource limits (OOMKilled).  
6. Investigate if dependencies are reachable.  
7. Rollback to previous version, then fix.

---

## Quick Reference — Most Frequently Asked Topics

| Topic | Frequency in Interviews |
|---|---|
| Event loop phases + execution order | 🔴 Always asked |
| Streams + backpressure | 🔴 Always asked |
| JWT + refresh token flow | 🔴 Always asked |
| Express middleware chain + error handling | 🔴 Always asked |
| Clustering vs Worker Threads | 🔴 Always asked |
| MongoDB aggregation pipeline | 🔴 Always asked |
| Redis caching strategies | 🔴 Always asked |
| `process.nextTick` vs `setImmediate` vs `setTimeout` order | 🔴 Always asked |
| Memory leak detection and debugging | 🟠 Frequently asked |
| Graceful shutdown implementation | 🟠 Frequently asked |
| REST API design principles + versioning | 🟠 Frequently asked |
| Circuit breaker pattern | 🟠 Frequently asked |
| `async_hooks` / `AsyncLocalStorage` | 🟡 Senior rounds |
| CQRS / Event sourcing | 🟡 Senior rounds |
| gRPC vs REST | 🟡 Senior rounds |
| Kafka vs RabbitMQ trade-offs | 🟡 Senior rounds |
