# JavaScript Interview Questions — Situational / Real-World Scenarios

A consolidated, deduplicated collection of **situational and real-time scenario-based JavaScript interview questions** — the kind asked to gauge how a candidate debugs issues, reasons about performance, and makes decisions on real projects — organized section-wise.

**Total unique questions: 78**

## Table of Contents

- [Closures, Scope & Hoisting](#closures-scope-hoisting) (2)
  - [1. Situation: Classic loop closure bug – `var` in a for loop.](#1-situation-classic-loop-closure-bug-var-in-a-for-loop)
  - [2. You have a feature using closures, but it's causing unexpected behavior in production — how would you debug and fix it?](#2-you-have-a-feature-using-closures-but-its-causing-unexpected-behavior-in-production-how-would-you-debug-and-fix-it)
- [`this`, call/apply/bind & Functions](#this-callapplybind-functions) (2)
  - [3. Implement `map`, `reduce`, `filter` from scratch.](#3-implement-map-reduce-filter-from-scratch)
  - [4. Implement a throttle function from scratch.](#4-implement-a-throttle-function-from-scratch)
- [Prototypes, Classes & OOP](#prototypes-classes-oop) (9)
  - [5. Explain how `Array.prototype.reduce` works from scratch.](#5-explain-how-arrayprototypereduce-works-from-scratch)
  - [6. How do you handle dark mode theming?](#6-how-do-you-handle-dark-mode-theming)
  - [7. How would you architect a state management system in vanilla JavaScript?](#7-how-would-you-architect-a-state-management-system-in-vanilla-javascript)
  - [8. How would you build a JavaScript SDK for a REST API?](#8-how-would-you-build-a-javascript-sdk-for-a-rest-api)
  - [9. How would you implement a simple dependency injection container?](#9-how-would-you-implement-a-simple-dependency-injection-container)
  - [10. Implement `Array.prototype.flat` from scratch.](#10-implement-arrayprototypeflat-from-scratch)
  - [11. Situation: `this` is `undefined` in a class method — what are the possible causes?](#11-situation-this-is-undefined-in-a-class-method-what-are-the-possible-causes)
  - [12. Situation: `this` is `undefined` inside a class method used as a callback — how do you fix it?](#12-situation-this-is-undefined-inside-a-class-method-used-as-a-callback-how-do-you-fix-it)
  - [13. What are mixins and how do you implement them in JavaScript?](#13-what-are-mixins-and-how-do-you-implement-them-in-javascript)
- [ES6+ Features (Destructuring, Spread/Rest, Modules)](#es6-features-destructuring-spreadrest-modules) (6)
  - [14. Design a rate limiter function in JavaScript.](#14-design-a-rate-limiter-function-in-javascript)
  - [15. How would you implement infinite scrolling with vanilla JS?](#15-how-would-you-implement-infinite-scrolling-with-vanilla-js)
  - [16. How would you implement server-sent events (SSE) on the client side?](#16-how-would-you-implement-server-sent-events-sse-on-the-client-side)
  - [17. How would you structure a micro‑frontend architecture enabling team autonomy and independent releases?](#17-how-would-you-structure-a-microfrontend-architecture-enabling-team-autonomy-and-independent-releases)
  - [18. How would you structure a micro‑frontend architecture for team autonomy?](#18-how-would-you-structure-a-microfrontend-architecture-for-team-autonomy)
  - [19. What is circular dependency and how do you handle it?](#19-what-is-circular-dependency-and-how-do-you-handle-it)
- [Arrays, Objects & Data Structures](#arrays-objects-data-structures) (5)
  - [20. Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.](#20-explain-call-apply-and-bind-with-use-cases-implement-polyfills)
  - [21. How would you handle large JSON files in Node.js?](#21-how-would-you-handle-large-json-files-in-nodejs)
  - [22. How would you implement memoization with a complex cache key?](#22-how-would-you-implement-memoization-with-a-complex-cache-key)
  - [23. Implement a deep clone function (deep copy).](#23-implement-a-deep-clone-function-deep-copy)
  - [24. Situation: `JSON.stringify` is dropping data — explain why and how to fix it.](#24-situation-jsonstringify-is-dropping-data-explain-why-and-how-to-fix-it)
- [Type Coercion, Equality & Data Types](#type-coercion-equality-data-types) (3)
  - [25. How would you architect a real-time collaborative editing feature?](#25-how-would-you-architect-a-real-time-collaborative-editing-feature)
  - [26. How would you implement a deep equality function?](#26-how-would-you-implement-a-deep-equality-function)
  - [27. How would you implement feature detection in JavaScript?](#27-how-would-you-implement-feature-detection-in-javascript)
- [Asynchronous JavaScript (Promises, async/await, Event Loop)](#asynchronous-javascript-promises-asyncawait-event-loop) (28)
  - [28. Design a JavaScript plugin system.](#28-design-a-javascript-plugin-system)
  - [29. Design a pipeline function (like `|>` operator) in JavaScript.](#29-design-a-pipeline-function-like-operator-in-javascript)
  - [30. Design a retry mechanism with exponential backoff for API calls.](#30-design-a-retry-mechanism-with-exponential-backoff-for-api-calls)
  - [31. How do you debug JavaScript effectively?](#31-how-do-you-debug-javascript-effectively)
  - [32. How do you handle errors in Promises vs async/await?](#32-how-do-you-handle-errors-in-promises-vs-asyncawait)
  - [33. How do you handle errors in Promises?](#33-how-do-you-handle-errors-in-promises)
  - [34. How do you handle errors with `async/await`?](#34-how-do-you-handle-errors-with-asyncawait)
  - [35. How would you handle multiple API calls efficiently without blocking the UI?](#35-how-would-you-handle-multiple-api-calls-efficiently-without-blocking-the-ui)
  - [36. How would you implement debounce and throttle from scratch?](#36-how-would-you-implement-debounce-and-throttle-from-scratch)
  - [37. How would you implement structured concurrency in JavaScript?](#37-how-would-you-implement-structured-concurrency-in-javascript)
  - [38. Implement `Promise.all` from scratch (already covered above).](#38-implement-promiseall-from-scratch-already-covered-above)
  - [39. Implement `Promise.all` from scratch.](#39-implement-promiseall-from-scratch)
  - [40. Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.](#40-implement-promiseall-promiserace-promiseallsettled-from-scratch)
  - [41. Implement a custom hook like `useDebounce` or `useFetch` (React).](#41-implement-a-custom-hook-like-usedebounce-or-usefetch-react)
  - [42. Implement a custom Promise (conceptually).](#42-implement-a-custom-promise-conceptually)
  - [43. Implement debounce and throttle functions.](#43-implement-debounce-and-throttle-functions)
  - [44. In a live application where users report slowness, how would you identify whether the issue is due to the event loop blocking or inefficient code?](#44-in-a-live-application-where-users-report-slowness-how-would-you-identify-whether-the-issue-is-due-to-the-event-loop-blocking-or-inefficient-code)
  - [45. Situation: `this` is `undefined` or `window` inside a callback – why?](#45-situation-this-is-undefined-or-window-inside-a-callback-why)
  - [46. Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.](#46-situation-a-for-loop-with-var-and-settimeout-doesnt-behave-as-expected-explain-and-fix)
  - [47. Situation: A Node.js server is leaking memory — how do you diagnose it?](#47-situation-a-nodejs-server-is-leaking-memory-how-do-you-diagnose-it)
  - [48. Situation: An async function is silently failing — how do you debug it?](#48-situation-an-async-function-is-silently-failing-how-do-you-debug-it)
  - [49. Situation: Design a retry mechanism for a failed API call.](#49-situation-design-a-retry-mechanism-for-a-failed-api-call)
  - [50. Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?](#50-situation-error-thrown-inside-settimeout-does-trycatch-catch-it)
  - [51. Situation: How do you cancel a fetch request?](#51-situation-how-do-you-cancel-a-fetch-request)
  - [52. Situation: Output the order of `setTimeout`, Promise, and synchronous code.](#52-situation-output-the-order-of-settimeout-promise-and-synchronous-code)
  - [53. Situation: Users report your web app crashes their browser tab — what do you investigate?](#53-situation-users-report-your-web-app-crashes-their-browser-tab-what-do-you-investigate)
  - [54. Situation: You need to run 100 API calls but limit concurrency to 5 — how?](#54-situation-you-need-to-run-100-api-calls-but-limit-concurrency-to-5-how)
  - [55. Situation: Your third-party script is blocking the main thread — how do you fix it?](#55-situation-your-third-party-script-is-blocking-the-main-thread-how-do-you-fix-it)
- [DOM, BOM & Events](#dom-bom-events) (2)
  - [56. Design a simple virtual DOM diffing algorithm.](#56-design-a-simple-virtual-dom-diffing-algorithm)
  - [57. Explain how you would implement virtual scrolling in vanilla JavaScript.](#57-explain-how-you-would-implement-virtual-scrolling-in-vanilla-javascript)
- [Error Handling & Debugging](#error-handling-debugging) (2)
  - [58. How do you handle JavaScript errors in a production application end-to-end?](#58-how-do-you-handle-javascript-errors-in-a-production-application-end-to-end)
  - [59. How would you design JavaScript error handling for a large team?](#59-how-would-you-design-javascript-error-handling-for-a-large-team)
- [Performance (Debounce, Throttle, Memoization)](#performance-debounce-throttle-memoization) (1)
  - [60. Memory Leak: You notice a memory leak in a production SPA – how do you identify and fix it?](#60-memory-leak-you-notice-a-memory-leak-in-a-production-spa-how-do-you-identify-and-fix-it)
- [Generators, Iterators & Symbols](#generators-iterators-symbols) (2)
  - [61. How do generators implement iterators?](#61-how-do-generators-implement-iterators)
  - [62. How would you implement a simple reactive system (like Vue's reactivity)?](#62-how-would-you-implement-a-simple-reactive-system-like-vues-reactivity)
- [Modules, Build Tools & Browser APIs](#modules-build-tools-browser-apis) (1)
  - [63. How would you build an offline-first JavaScript web app?](#63-how-would-you-build-an-offline-first-javascript-web-app)
- [General / Miscellaneous JavaScript Concepts](#general-miscellaneous-javascript-concepts) (15)
  - [64. A page is consuming too much memory over time — how would you detect and prevent memory leaks?](#64-a-page-is-consuming-too-much-memory-over-time-how-would-you-detect-and-prevent-memory-leaks)
  - [65. How do you approach writing JavaScript for low-powered devices?](#65-how-do-you-approach-writing-javascript-for-low-powered-devices)
  - [66. How do you ensure JavaScript is accessible?](#66-how-do-you-ensure-javascript-is-accessible)
  - [67. How do you handle breaking API changes safely on the frontend?](#67-how-do-you-handle-breaking-api-changes-safely-on-the-frontend)
  - [68. How do you handle disagreements in technical decisions?](#68-how-do-you-handle-disagreements-in-technical-decisions)
  - [69. How do you handle JavaScript in a security-sensitive context (e.g., fintech)?](#69-how-do-you-handle-javascript-in-a-security-sensitive-context-eg-fintech)
  - [70. How do you handle offline‑first apps with IndexedDB, background sync, and conflict resolution?](#70-how-do-you-handle-offlinefirst-apps-with-indexeddb-background-sync-and-conflict-resolution)
  - [71. How do you handle versioning of UI contracts?](#71-how-do-you-handle-versioning-of-ui-contracts)
  - [72. How would you build an undo/redo system?](#72-how-would-you-build-an-undoredo-system)
  - [73. How would you compile a simple expression language to JavaScript?](#73-how-would-you-compile-a-simple-expression-language-to-javascript)
  - [74. How would you design a client-side caching layer?](#74-how-would-you-design-a-client-side-caching-layer)
  - [75. How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)](#75-how-would-you-handle-a-large-dataset-without-blocking-the-main-thread-web-workers-virtualization)
  - [76. How would you implement a JavaScript interpreter in JavaScript?](#76-how-would-you-implement-a-javascript-interpreter-in-javascript)
  - [77. How would you implement a persistent undo history that survives page reload?](#77-how-would-you-implement-a-persistent-undo-history-that-survives-page-reload)
  - [78. How would you implement a simple template engine?](#78-how-would-you-implement-a-simple-template-engine)

---

## Closures, Scope & Hoisting

### 1. Situation: Classic loop closure bug – `var` in a for loop.

```javascript
for (var i = 0; i < 3; i++) {
setTimeout(() => console.log(i), 0);
}
// Logs: 3, 3, 3 — not 0, 1, 2
```

Because `var` is function-scoped, all callbacks share the same `i`. When they run, the loop has finished and `i` is `3`. Fix: use `let` (block-scoped, creates a new binding per iteration), use `setTimeout` with a closure factory, or use `forEach`.

[↑ Back to top](#table-of-contents)

### 2. You have a feature using closures, but it's causing unexpected behavior in production — how would you debug and fix it?

Closure issues often stem from variable capture inside loops, asynchronous callbacks, or stale state.

- **Reproduce locally:** Write a test that mimics production behavior. Use `console.log` or a debugger to inspect captured variables.
- **Check loop closures:** If the feature uses `var` inside a loop, the closure shares the same variable reference. Replace with `let` (block‑scoped) or use an IIFE to capture the current value.
- **Asynchronous closures:** When a callback accesses a variable that changes after the closure is created, the value may be outdated. Example:

```javascript
for (let i = 0; i < 3; i++) {
setTimeout(() => console.log(i), 100); // works with let
}
```

With `var`, all would log `3`. The fix is to use `let` or wrap in a function.
- **State in React hooks (if applicable):** Stale closures often appear with `useEffect` or `useCallback` when dependencies are missing. Use exhaustive‑deps rules and verify captured values.
- **Production debugging:** Add structured logging that includes the closure‑bound values at key points. Use remote debugging via `--inspect` if possible, or log snapshots.
- **Fix:** Once identified, refactor to avoid mutating captured variables or use explicit dependencies (e.g., `useCallback` with proper deps). Consider replacing closures with explicit parameters where appropriate.

[↑ Back to top](#table-of-contents)

## `this`, call/apply/bind & Functions

### 3. Implement `map`, `reduce`, `filter` from scratch.

**`map`**:

```javascript
Array.prototype.myMap = function(callback, thisArg) {
const result = [];
for (let i = 0; i < this.length; i++) {
if (i in this) { // skip empty slots (sparse arrays)
result.push(callback.call(thisArg, this[i], i, this));
}
}
return result;
};
```

**`filter`**:

```javascript
Array.prototype.myFilter = function(callback, thisArg) {
const result = [];
for (let i = 0; i < this.length; i++) {
if (i in this && callback.call(thisArg, this[i], i, this)) {
result.push(this[i]);
}
}
return result;
};
```

**`reduce`**:

```javascript
Array.prototype.myReduce = function(callback, initialValue) {
let accumulator = initialValue;
let startIndex = 0;
if (arguments.length < 2) {
if (this.length === 0) throw new TypeError('Reduce of empty array with no initial value');
accumulator = this[0];
startIndex = 1;
}
for (let i = startIndex; i < this.length; i++) {
if (i in this) {
accumulator = callback(accumulator, this[i], i, this);
}
}
return accumulator;
};

```

[↑ Back to top](#table-of-contents)

### 4. Implement a throttle function from scratch.

```javascript
function throttle(fn, limit) {
let lastCall = 0;
return function(...args) {
const now = Date.now();
if (now - lastCall >= limit) {
lastCall = now;
return fn.apply(this, args);
}
};
}

```

[↑ Back to top](#table-of-contents)

## Prototypes, Classes & OOP

### 5. Explain how `Array.prototype.reduce` works from scratch.

Takes a callback `(accumulator, currentValue, index, array) => newAccumulator` and an optional initial value. If no initial value, uses the first element. Iterates each element, passing the accumulator (starts as initial value or first element) to the callback, using the return value as the next accumulator. Returns the final accumulator.

[↑ Back to top](#table-of-contents)

### 6. How do you handle dark mode theming?

**Approaches**:
- **CSS custom properties**: Define light and dark color schemes in separate classes or via `prefers-color-scheme`.

```css
:root {
--bg: white;
--text: black;
}
@media (prefers-color-scheme: dark) {
:root {
--bg: black;
--text: white;
}
}
.dark {
--bg: black;
--text: white;
}
```

- **User toggle**: Add a class (e.g., `.dark`) to a parent element and define overrides.
- Use JavaScript to read user preference and apply the appropriate class.

[↑ Back to top](#table-of-contents)

### 7. How would you architect a state management system in vanilla JavaScript?

A central `Store` class holding state object. `dispatch(action)` runs the reducer to produce new state (immutably). `subscribe(listener)` adds observers; `unsubscribe` removes them. `getState()` returns current state. Middleware support: wrap `dispatch` with a chain of middleware functions. Notify subscribers after each dispatch.

**Q175. Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.**

`for (var i = 0; i < 5; i++) setTimeout(() => console.log(i), 0)` prints `5` five times. `var` is function-scoped — all callbacks close over the same `i`. Fix 1: `let` in the loop (block-scoped, new binding per iteration). Fix 2: IIFE `(function(i) { setTimeout(...) })(i)`. Fix 3: `setTimeout(console.log, 0, i)`.

[↑ Back to top](#table-of-contents)

### 8. How would you build a JavaScript SDK for a REST API?

A class or factory accepting `baseURL` and auth credentials. Each resource (users, posts) gets methods (`getAll`, `getById`, `create`, `update`, `delete`). Central `request` method handles: setting auth headers, base URL, error parsing, retry logic, and type coercion. Generate TypeScript types from OpenAPI spec. Version the SDK with semantic versioning.

[↑ Back to top](#table-of-contents)

### 9. How would you implement a simple dependency injection container?

A container maps tokens (strings, Symbols, or classes) to factories. `register(token, factory)`: store the factory. `resolve(token)`: call the factory, injecting dependencies by calling `resolve` for each declared dependency. Handle circular dependencies by detecting cycles. Supports singletons by caching resolved instances.

[↑ Back to top](#table-of-contents)

### 10. Implement `Array.prototype.flat` from scratch.

```javascript
function flat(arr, depth = 1) {
if (depth === 0) return arr.slice();
return arr.reduce((acc, item) => {
if (Array.isArray(item)) {
acc.push(...flat(item, depth - 1));
} else {
acc.push(item);
}
return acc;
}, []);
}

```

[↑ Back to top](#table-of-contents)

### 11. Situation: `this` is `undefined` in a class method — what are the possible causes?

The method was destructured from the instance (`const {method} = instance`). It was passed as a callback without binding. It's a static method being called on an instance. It's an async method and `this` was lost in a callback inside it. Fixes: bind in the constructor, use class field arrow functions, or use `fn.bind(instance)` at the call site.

[↑ Back to top](#table-of-contents)

### 12. Situation: `this` is `undefined` inside a class method used as a callback — how do you fix it?

Three options: (1) bind in the constructor: `this.method = this.method.bind(this)`. (2) Use a class field arrow function: `method = () => {}` (most common in React). (3) Use an arrow function at the call site: `element.addEventListener('click', () => this.method())`.

[↑ Back to top](#table-of-contents)

### 13. What are mixins and how do you implement them in JavaScript?

A mixin adds methods from one object to another without inheritance: `Object.assign(Target.prototype, MixinA, MixinB)`. Since JS only has single inheritance (via prototype chain), mixins allow composing multiple behaviors. Higher-order class mixins are more composable: `const Serializable = (Base) => class extends Base { serialize() {} }`.

[↑ Back to top](#table-of-contents)

## ES6+ Features (Destructuring, Spread/Rest, Modules)

### 14. Design a rate limiter function in JavaScript.

Track call timestamps in a sliding window or token bucket. `function rateLimit(fn, limit, window) { let calls = []; return (...args) => { const now = Date.now(); calls = calls.filter(t => now - t < window); if (calls.length >= limit) throw new Error('Rate limited'); calls.push(now); return fn(...args); }; }`. For async queuing instead of throwing, use a Promise queue with delay.

[↑ Back to top](#table-of-contents)

### 15. How would you implement infinite scrolling with vanilla JS?

```javascript
const sentinel = document.querySelector('#sentinel');
const observer = new IntersectionObserver(entries => {
if (entries[0].isIntersecting && !isLoading) {
isLoading = true;
fetchNextPage().then(items => {
renderItems(items);
isLoading = false;
if (hasMore) observer.observe(sentinel); // re-observe after render
});
}
}, { rootMargin: '200px' }); // load 200px before sentinel is visible
observer.observe(sentinel);
```

*300 questions across 20 sections. Master these and crack 95% of JavaScript interviews! 🟨*

[↑ Back to top](#table-of-contents)

### 16. How would you implement server-sent events (SSE) on the client side?

`const source = new EventSource('/events')`. `source.onmessage = e => handle(e.data)`. `source.addEventListener('customEvent', handler)`. `source.onerror` for reconnection logic. SSE auto-reconnects on disconnect. One-way server-to-client only. Use `source.close()` to stop. Better than polling; simpler than WebSockets for push-only scenarios.

[↑ Back to top](#table-of-contents)

### 17. How would you structure a micro‑frontend architecture enabling team autonomy and independent releases?

**Micro‑frontends** split the frontend into independently deployable modules, each owned by a team.

**Approaches**:
- **Build‑time integration**: Each micro‑frontend is a separate npm package, composed at build time (e.g., Webpack Module Federation). Teams release independently.
- **Runtime integration**: Use iframes, Web Components, or a container app that loads micro‑frontends at runtime via JavaScript.

**Structure**:
- **Container app**: Provides shell (layout, authentication, routing). Uses Module Federation to load remote modules.
- **Independent teams**: Own their codebase, build pipeline, and deployment. They expose entry points (e.g., a React component) via federation.
- **Shared libraries**: Manage via monorepo (e.g., Nx, Turborepo) with shared UI components, utilities, and types. Use semantic versioning and careful upgrades.
- **Routing**: Typically, the container handles top‑level routing; micro‑apps handle their own sub‑routing.
- **Communication**: Use custom events or a shared state library (e.g., Redux with a central store) but avoid tight coupling. Prefer event‑based communication.
- **Testing**: Each team tests its own app; integration tests ensure contracts.

[↑ Back to top](#table-of-contents)

### 18. How would you structure a micro‑frontend architecture for team autonomy?

**Goal**: Enable independent teams to develop, test, and deploy their parts of the frontend without coordination bottlenecks.

**Approaches**:
- **Build‑time integration (Module Federation)** – Each team builds a separate bundle; a host application loads them at runtime via Webpack 5 Module Federation. Teams release independently, and versioning is handled via semantic versioning or by exposing a manifest.
- **Runtime integration (iframes / Web Components)** – Iframes provide strong isolation but come with communication overhead. Web Components can be used to encapsulate frameworks; they can be loaded dynamically and work across frameworks.
- **Composition via API Gateway** – A backend‑for‑frontend (BFF) layer composes micro‑frontend fragments on the server and serves them as HTML.

**Key design decisions**:
- **Shared libraries** – Use a monorepo (e.g., Nx) to manage shared UI components, utilities, and types. Teams consume them as packages. Avoid global state between micro‑frontends; use custom events or a lightweight pub/sub for cross‑app communication.
- **Routing** – The host handles top‑level routing and passes control to the appropriate micro‑frontend for sub‑routes. This can be achieved by using a base path per team.
- **Team autonomy** – Each team owns its codebase, CI/CD pipeline, and deployment. The host application defines contracts (e.g., the shape of exported components, expected CSS namespacing) to ensure safe composition.
- **Testing** – Each micro‑frontend is tested in isolation. Integration tests verify that the host correctly loads them and that they work together.

**Challenges**:
- **Performance** – Loading multiple bundles can increase initial load time; use code splitting, preloading, and caching strategies.
- **Consistency** – Enforce design system adoption through shared components and linting.
- **Security** – Ensure iframes have proper sandboxing; avoid exposing sensitive data across boundaries.

**Example**:
> “We adopted Module Federation with a host app that provided the layout and authentication. Each team had a separate repo, built their app, and deployed it to a CDN. The host fetched a manifest listing available versions and loaded the required micro‑frontend on navigation. We used a shared UI library published to npm, and communication was done via custom events for cross‑app actions like logging out.”

[↑ Back to top](#table-of-contents)

### 19. What is circular dependency and how do you handle it?

Module A imports B, and B imports A. Both module systems handle it but the imported value may be `undefined` at evaluation time. Fix: restructure to extract shared code to a third module C, or use lazy imports (dynamic `import()`).

[↑ Back to top](#table-of-contents)

## Arrays, Objects & Data Structures

### 20. Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.

All three are used to control the `this` value in functions.

- **`call(thisArg, arg1, arg2, ...)`**: Invokes the function immediately with a given `this` and arguments passed individually.
- **`apply(thisArg, [argsArray])`**: Same as `call`, but arguments are passed as an array.
- **`bind(thisArg, ...args)`**: Returns a new function with the `this` bound permanently; can be called later.

**Use cases:**
- Borrowing methods: e.g., `Array.prototype.slice.call(arguments)`
- Function currying: `const multiply = (a,b) => a*b; const double = multiply.bind(null, 2);`
- Event handlers: ensure `this` refers to the class instance.

**Polyfills:**

```javascript
// call polyfill
Function.prototype.myCall = function(context, ...args) {
context = context || globalThis;
const uniqueId = Symbol(); // avoid property collision
context[uniqueId] = this;
const result = context[uniqueId](...args);
delete context[uniqueId];
return result;
};

// apply polyfill
Function.prototype.myApply = function(context, argsArray) {
context = context || globalThis;
const uniqueId = Symbol();
context[uniqueId] = this;
const result = context[uniqueId](...argsArray);
delete context[uniqueId];
return result;
};

// bind polyfill (simplified)
Function.prototype.myBind = function(context, ...boundArgs) {
const fn = this;
return function(...args) {
return fn.apply(context, boundArgs.concat(args));
};
};

```

[↑ Back to top](#table-of-contents)

### 21. How would you handle large JSON files in Node.js?

Don't load the entire file into memory with `JSON.parse`. Use streaming JSON parsers: `JSONStream`, `oboe`, or `stream-json`. Read the file as a Readable stream and pipe through the parser. Process records one at a time. For extremely large files, consider a line-delimited JSON format (NDJSON) which is easier to stream.

[↑ Back to top](#table-of-contents)

### 22. How would you implement memoization with a complex cache key?

For single-argument functions, a `Map` is sufficient. For multiple arguments, serialize args: `JSON.stringify(args)` (fast but fails for functions, undefined, circular refs). For robust solution: use a WeakMap for object args (prevents memory leaks) with a trie-like structure for multiple args (as in libraries like `memoize-one`).

[↑ Back to top](#table-of-contents)

### 23. Implement a deep clone function (deep copy).

**Using `structuredClone` (modern)**:

```javascript
const clone = structuredClone(original);
```

**Manual implementation** (handles objects, arrays, dates, maps, sets, and cyclic references):

```javascript
function deepClone(obj, map = new WeakMap()) {
if (obj === null || typeof obj !== 'object') return obj;
if (map.has(obj)) return map.get(obj);
let clone;
if (obj instanceof Date) clone = new Date(obj);
else if (obj instanceof Map) {
clone = new Map();
map.set(obj, clone);
obj.forEach((val, key) => clone.set(deepClone(key, map), deepClone(val, map)));
return clone;
} else if (obj instanceof Set) {
clone = new Set();
map.set(obj, clone);
obj.forEach(val => clone.add(deepClone(val, map)));
return clone;
} else if (obj instanceof Array) {
clone = [];
map.set(obj, clone);
obj.forEach((item, i) => clone[i] = deepClone(item, map));
} else {
clone = {};
map.set(obj, clone);
for (let key in obj) {
if (obj.hasOwnProperty(key)) clone[key] = deepClone(obj[key], map);
}
}
return clone;
}

```

[↑ Back to top](#table-of-contents)

### 24. Situation: `JSON.stringify` is dropping data — explain why and how to fix it.

`JSON.stringify` silently omits: `undefined` values in objects (and `undefined` itself), functions, `Symbol` keys and values, and `Infinity`/`NaN` (become `null`). Circular references throw. Fix: use a replacer function as the second argument to handle special values, or use a library like `flatted` for circular refs.

[↑ Back to top](#table-of-contents)

## Type Coercion, Equality & Data Types

### 25. How would you architect a real-time collaborative editing feature?

Operational Transformation (OT) or CRDT (Conflict-free Replicated Data Type) algorithms to handle concurrent edits. WebSocket for real-time transport. Server applies and broadcasts operations. Yjs and Automerge are production-ready CRDT libraries. Awareness protocol for cursor/presence sharing.

[↑ Back to top](#table-of-contents)

### 26. How would you implement a deep equality function?

Handle primitives with `===`. Handle `null` explicitly. Check same type and same constructor. For arrays, check length then recurse over indices. For objects, check same keys then recurse over values. Handle `Date`, `RegExp`, `Map`, `Set`, and circular references. `Object.is` for NaN/+0/-0 edge cases.

[↑ Back to top](#table-of-contents)

### 27. How would you implement feature detection in JavaScript?

Check for the feature's existence before using it: `if ('IntersectionObserver' in window)`. For methods: `if (typeof arr.flat === 'function')`. For CSS: `CSS.supports('display', 'grid')`. Prefer feature detection over user-agent sniffing (unreliable). Use polyfills for missing features rather than forking code.

[↑ Back to top](#table-of-contents)

## Asynchronous JavaScript (Promises, async/await, Event Loop)

### 28. Design a JavaScript plugin system.

A `PluginManager` class with `register(plugin)` and `run(hook, context)`. Plugins are objects with hook names as keys: `{beforeSave: async (ctx) => {...}}`. Manager maintains a `Map<hookName, Plugin[]>`. On `run`, iterate plugins for that hook in registration order. Support async hooks with sequential `await` or parallel `Promise.all`. Provide `context` object for plugins to share state.

[↑ Back to top](#table-of-contents)

### 29. Design a pipeline function (like `|>` operator) in JavaScript.

```javascript
const pipe = (...fns) => x => fns.reduce((acc, fn) => fn(acc), x);
const process = pipe(trim, toLowerCase, removeSpecialChars, truncate(50));
process(input);
```

For async pipelines: `const pipeAsync = (...fns) => x => fns.reduce(async (acc, fn) => fn(await acc), x)`.

[↑ Back to top](#table-of-contents)

### 30. Design a retry mechanism with exponential backoff for API calls.

```javascript
async function withRetry(fn, retries = 3, baseDelay = 100) {
for (let attempt = 0; attempt < retries; attempt++) {
try { return await fn(); }
catch (err) {
if (attempt === retries - 1) throw err;
const delay = baseDelay * 2 ** attempt + Math.random() * 100;
await new Promise(r => setTimeout(r, delay));
}
}
}
```

Jitter prevents thundering herd when many clients retry simultaneously.

[↑ Back to top](#table-of-contents)

### 31. How do you debug JavaScript effectively?

`debugger` statement (pauses in DevTools), `console.log/table/trace/time`, breakpoints in DevTools, conditional breakpoints, watch expressions, the Call Stack panel (for async), and network panel for API calls. For production: error monitoring (Sentry), structured logging.

[↑ Back to top](#table-of-contents)

### 32. How do you handle errors in Promises vs async/await?

Promises: `.catch(handler)` at the end of the chain. Async/await: `try/catch` block, or `.catch()` on the returned Promise. Unhandled rejections: listen to `process.on('unhandledRejection')` (Node) or `window.addEventListener('unhandledrejection')` (browser).

[↑ Back to top](#table-of-contents)

### 33. How do you handle errors in Promises?

`.catch(fn)` at the end of a chain handles any rejection in the chain. Can also pass a rejection handler as the second argument to `.then(null, onRejected)`. In `async/await`, use `try/catch`. Always handle promise rejections — unhandled rejections crash Node.js and cause console warnings in browsers.

[↑ Back to top](#table-of-contents)

### 34. How do you handle errors with `async/await`?

Wrap `await` calls in `try/catch` blocks. The `catch` block receives the rejection reason. You can also handle errors with `.catch()` on the async function call. For multiple operations, you can have one try/catch or separate ones depending on error handling needs.

```javascript
async function fetchData() {
try {
const res = await fetch(url);
const data = await res.json();
return data;
} catch (err) {
console.error('Failed:', err);
}
}
```

[↑ Back to top](#table-of-contents)

### 35. How would you handle multiple API calls efficiently without blocking the UI?

In a Node.js backend, “blocking the UI” usually refers to blocking the event loop. For frontend, it’s about keeping the UI responsive. I’ll cover both.

**Backend (Node.js):**
- Use `Promise.all` or `Promise.allSettled` to run independent API calls in parallel.
- Avoid sequential `await` calls unless there is a dependency.
- Offload CPU‑intensive tasks to worker threads (`worker_threads`) or a separate service so the main event loop remains free.
- Use streaming and back‑pressure when dealing with large payloads to avoid memory pressure.

**Frontend (Browser):**
- Use `Promise.all` for parallel requests, but be mindful of browser connection limits (usually 6 per origin). Group requests accordingly.
- Implement request caching (e.g., with React Query or SWR) to avoid duplicate calls.
- Show skeleton loaders or optimistic UI so the user perceives responsiveness.
- If calls are heavy, use Web Workers to process data without blocking the main thread.
- Debounce or throttle user‑triggered API calls (e.g., search inputs) to reduce unnecessary requests.

[↑ Back to top](#table-of-contents)

### 36. How would you implement debounce and throttle from scratch?

Debounce: `function debounce(fn, delay) { let timer; return (...args) => { clearTimeout(timer); timer = setTimeout(() => fn(...args), delay); }; }`. Throttle (leading): track `lastCall`. If `Date.now() - lastCall >= delay`, call `fn` and update `lastCall`. Trailing throttle: use `setTimeout` and cancel if called again within the window.

[↑ Back to top](#table-of-contents)

### 37. How would you implement structured concurrency in JavaScript?

Group async operations so all are cancelled/resolved together. Model with an `AbortController` shared among tasks. Pattern: `async function withTimeout(fn, ms) { const ac = new AbortController(); const timer = setTimeout(() => ac.abort(), ms); try { return await fn(ac.signal); } finally { clearTimeout(timer); } }`. The TC39 `Async Context` proposal and `AbortSignal.any()` improve this further. Libraries like `effect-ts` provide structured concurrency primitives.

[↑ Back to top](#table-of-contents)

### 38. Implement `Promise.all` from scratch (already covered above).

*(No answer text was present in the source.)*

[↑ Back to top](#table-of-contents)

### 39. Implement `Promise.all` from scratch.

```javascript
function promiseAll(promises) {
return new Promise((resolve, reject) => {
const results = [];
let pending = promises.length;
if (pending === 0) return resolve([]);
promises.forEach((promise, i) => {
Promise.resolve(promise).then(value => {
results[i] = value;
if (--pending === 0) resolve(results);
}).catch(reject);
});
});
}

```

[↑ Back to top](#table-of-contents)

### 40. Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.

**Promise.all**:

```javascript
Promise.myAll = function(promises) {
return new Promise((resolve, reject) => {
if (!Array.isArray(promises)) reject(new TypeError('Not an array'));
const results = new Array(promises.length);
let completed = 0;
if (promises.length === 0) resolve(results);
promises.forEach((p, i) => {
Promise.resolve(p).then(
val => {
results[i] = val;
completed++;
if (completed === promises.length) resolve(results);
},
err => reject(err)
);
});
});
};
```

**Promise.race**:

```javascript
Promise.myRace = function(promises) {
return new Promise((resolve, reject) => {
promises.forEach(p => {
Promise.resolve(p).then(resolve, reject);
});
});
};
```

**Promise.allSettled**:

```javascript
Promise.myAllSettled = function(promises) {
return new Promise(resolve => {
const results = [];
let remaining = promises.length;
if (remaining === 0) resolve(results);
promises.forEach((p, i) => {
Promise.resolve(p).then(
value => results[i] = { status: 'fulfilled', value },
reason => results[i] = { status: 'rejected', reason }
).finally(() => {
remaining--;
if (remaining === 0) resolve(results);
});
});
});
};

```

[↑ Back to top](#table-of-contents)

### 41. Implement a custom hook like `useDebounce` or `useFetch` (React).

**`useDebounce`**:

```javascript
import { useState, useEffect } from 'react';

function useDebounce(value, delay) {
const [debouncedValue, setDebouncedValue] = useState(value);
useEffect(() => {
const handler = setTimeout(() => setDebouncedValue(value), delay);
return () => clearTimeout(handler);
}, [value, delay]);
return debouncedValue;
}
```

**`useFetch`**:

```javascript
function useFetch(url, options = {}) {
const [data, setData] = useState(null);
const [loading, setLoading] = useState(true);
const [error, setError] = useState(null);

useEffect(() => {
const abortController = new AbortController();
const signal = abortController.signal;

fetch(url, { ...options, signal })
.then(res => {
if (!res.ok) throw new Error('Network response was not ok');
return res.json();
})
.then(data => {
setData(data);
setLoading(false);
})
.catch(err => {
if (err.name !== 'AbortError') {
setError(err);
setLoading(false);
}
});

return () => abortController.abort();
}, [url]);

return { data, loading, error };
}

```

[↑ Back to top](#table-of-contents)

### 42. Implement a custom Promise (conceptually).

A custom Promise implementation involves managing states (`pending`, `fulfilled`, `rejected`), handling `.then` callbacks (both onFulfilled and onRejected), and supporting chaining and async resolution.

```javascript
class MyPromise {
constructor(executor) {
this.state = 'pending';
this.value = undefined;
this.handlers = []; // stores { onFulfilled, onRejected }

const resolve = (value) => {
if (this.state !== 'pending') return;
this.state = 'fulfilled';
this.value = value;
this.handlers.forEach(h => this._runHandler(h));
};

const reject = (reason) => {
if (this.state !== 'pending') return;
this.state = 'rejected';
this.value = reason;
this.handlers.forEach(h => this._runHandler(h));
};

try {
executor(resolve, reject);
} catch (err) {
reject(err);
}
}

_runHandler(handler) {
if (this.state === 'pending') {
this.handlers.push(handler);
return;
}
const cb = this.state === 'fulfilled' ? handler.onFulfilled : handler.onRejected;
if (!cb) {
// propagate
const next = this.state === 'fulfilled' ? handler.resolve : handler.reject;
next(this.value);
return;
}
try {
const result = cb(this.value);
handler.resolve(result);
} catch (err) {
handler.reject(err);
}
}

then(onFulfilled, onRejected) {
return new MyPromise((resolve, reject) => {
this._runHandler({ onFulfilled, onRejected, resolve, reject });
});
}

catch(onRejected) {
return this.then(null, onRejected);
}

// static methods (all, race) would be added similarly
}

```

[↑ Back to top](#table-of-contents)

### 43. Implement debounce and throttle functions.

**Debounce**: Delays function execution until after a period of inactivity. Useful for search inputs, window resize.

```javascript
function debounce(fn, delay) {
let timer;
return function(...args) {
clearTimeout(timer);
timer = setTimeout(() => fn.apply(this, args), delay);
};
}
```

**Throttle**: Ensures a function is called at most once per interval. Useful for scroll events, button clicks.

```javascript
function throttle(fn, limit) {
let inThrottle;
return function(...args) {
if (!inThrottle) {
fn.apply(this, args);
inThrottle = true;
setTimeout(() => (inThrottle = false), limit);
}
};
}

```

[↑ Back to top](#table-of-contents)

### 44. In a live application where users report slowness, how would you identify whether the issue is due to the event loop blocking or inefficient code?

I would use a combination of monitoring, profiling, and diagnostic tools.

- **Monitor event loop lag:** Use the `perf_hooks` module or libraries like `event-loop-lag` to measure the delay between a scheduled task and its execution. High lag (>10‑20ms) indicates blocking.
- **Profiling:** Take CPU profiles using `node --inspect` and Chrome DevTools, or use `clinic` (Clinic.js) to visualise hotspots. A flat flame graph with long‑running synchronous functions points to blocking code.
- **Check for synchronous I/O:** Look for `fs.readFileSync`, heavy crypto, or JSON parsing of large objects in the main thread.
- **Use `process._getActiveHandles()` and `process._getActiveRequests()`** to see if too many pending operations are accumulating.
- **APM tools:** New Relic, Datadog, or Dynatrace can show event loop latency and transaction traces.
- **Inefficient code:** If the event loop is not blocked but operations are slow (e.g., slow database queries, N+1 problems), profiling will show time spent in callbacks or promises rather than a single synchronous block. In that case, the fix is optimising the async operations, not removing blocking code.

[↑ Back to top](#table-of-contents)

### 45. Situation: `this` is `undefined` or `window` inside a callback – why?

When a method is passed as a callback, it loses its implicit binding. `setTimeout(obj.method, 0)` — `method` is called without `obj` as context. Fix: use `.bind(obj)`, wrap in arrow function `() => obj.method()`, or use an arrow function class field for the method definition.
When you pass an object's method as a callback, the function is detached from its object and called without context. In non‑strict mode `this` becomes the global object (`window`), in strict mode it’s `undefined`.

```js
const obj = {
name: 'Alice',
greet() { console.log(this.name); }
};

setTimeout(obj.greet, 0); // `this` is window/undefined → error

```

[↑ Back to top](#table-of-contents)

### 46. Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.

`for (var i = 0; i < 5; i++) setTimeout(() => console.log(i), 0)` prints `5` five times. `var` is function-scoped — all callbacks close over the same `i`. Fix 1: `let` in the loop (block-scoped, new binding per iteration). Fix 2: IIFE `(function(i) { setTimeout(...) })(i)`. Fix 3: `setTimeout(console.log, 0, i)`.

[↑ Back to top](#table-of-contents)

### 47. Situation: A Node.js server is leaking memory — how do you diagnose it?

Take heap snapshots with `node --inspect` and Chrome DevTools. Use `clinic.js` or `0x`. Look for growing retained size in heap snapshots. Common culprits: global caches without eviction, event listeners not removed, closures capturing large objects, `setInterval` not cleared. Take multiple snapshots over time and diff them.

[↑ Back to top](#table-of-contents)

### 48. Situation: An async function is silently failing — how do you debug it?

Check for missing `await` (the Promise is returned but not awaited). Check for caught errors that are swallowed silently in `.catch(() => {})`. Add `process.on('unhandledRejection')`. Use `Promise.all` carefully — a rejection can be missed if the result isn't awaited. Enable the `no-floating-promises` ESLint rule.

[↑ Back to top](#table-of-contents)

### 49. Situation: Design a retry mechanism for a failed API call.

```javascript
async function fetchWithRetry(url, options = {}, retries = 3, delay = 1000) {
try {
const res = await fetch(url, options);
if (!res.ok) throw new Error(`HTTP ${res.status}`);
return await res.json();
} catch (err) {
if (retries === 0) throw err;
await new Promise(r => setTimeout(r, delay));
return fetchWithRetry(url, options, retries - 1, delay * 2); // exponential backoff
}
}

```

[↑ Back to top](#table-of-contents)

### 50. Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?

No. The `try/catch` has already exited by the time the `setTimeout` callback runs (it runs in a future event loop iteration). Handle errors inside the callback itself with an inner `try/catch`, or use `window.onerror` / `process.on('uncaughtException')` for a global handler.

[↑ Back to top](#table-of-contents)

### 51. Situation: How do you cancel a fetch request?

Use `AbortController`. Create a controller, pass its signal to `fetch`, and call `controller.abort()` to cancel. The fetch rejects with an `AbortError`.

```javascript
const controller = new AbortController();
const timeout = setTimeout(() => controller.abort(), 5000);
try {
const res = await fetch(url, { signal: controller.signal });
clearTimeout(timeout);
return await res.json();
} catch (err) {
if (err.name === 'AbortError') console.log('Request cancelled');
else throw err;
}
```

[↑ Back to top](#table-of-contents)

### 52. Situation: Output the order of `setTimeout`, Promise, and synchronous code.

```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// Output: 1, 4, 3, 2
```

Synchronous code runs first (1, 4). Microtasks (Promises) run before macrotasks (setTimeout). So 3 runs before 2.

[↑ Back to top](#table-of-contents)

### 53. Situation: Users report your web app crashes their browser tab — what do you investigate?

Check for infinite loops (missing loop exit condition, infinite recursion). Check memory usage in Task Manager / DevTools Memory tab — look for heap growth. Check for WebSocket or polling connections sending enormous payloads. Look for `setInterval` without `clearInterval`. Check for canvas or WebGL without proper cleanup. Use `performance.memory` API and heap snapshots to narrow down.

[↑ Back to top](#table-of-contents)

### 54. Situation: You need to run 100 API calls but limit concurrency to 5 — how?

Implement a concurrency limiter: maintain a running count and a queue. When running < limit, start a task. When a task completes, start the next queued one. Or use `p-limit` (npm). Alternatively, chunk the array into groups of 5 and `await Promise.all(chunk)` per group — less dynamic but simple for batch processing.

[↑ Back to top](#table-of-contents)

### 55. Situation: Your third-party script is blocking the main thread — how do you fix it?

Load with `defer` (executes after HTML parse, in order) or `async` (executes immediately when downloaded). Move to a Web Worker for CPU work. Use dynamic `import()` to load only when needed. Evaluate if the script is necessary at all — audit with Lighthouse third-party audit. Use `scheduler.postTask` (Chrome) to yield control.

[↑ Back to top](#table-of-contents)

## DOM, BOM & Events

### 56. Design a simple virtual DOM diffing algorithm.

Represent nodes as `{type, props, children}` objects. Diff function: if types differ, replace entirely. If same type, diff props — apply changed/removed/added props to the real DOM node. Recurse into children: use keys for stable matching; add/remove/patch as needed. Apply all changes in the commit phase after the full diff.

[↑ Back to top](#table-of-contents)

### 57. Explain how you would implement virtual scrolling in vanilla JavaScript.

Calculate item height. Determine total scroll height. Render only visible items + buffer. On scroll, update the range of visible indices. Translate the rendered container with `transform: translateY` instead of `top` (avoids reflow). Recycle DOM nodes instead of creating/destroying them.

[↑ Back to top](#table-of-contents)

## Error Handling & Debugging

### 58. How do you handle JavaScript errors in a production application end-to-end?

Error boundaries (React) for UI crashes. `window.onerror` and `window.onunhandledrejection` for unhandled errors. Integrate Sentry/Datadog with breadcrumbs and user context. Source maps for readable stack traces. Alert on error rate spikes. `try/catch` for expected failures with user-facing messages. Structured logging for server-side.

[↑ Back to top](#table-of-contents)

### 59. How would you design JavaScript error handling for a large team?

Establish error taxonomy — `ValidationError`, `NetworkError`, `NotFoundError` all extending `AppError` with codes. Central `handleError` function that: logs structured data, triggers monitoring, maps to user messages. Lint rules for no floating promises, no empty catch blocks. Document error contracts for every public function. Integration tests for error paths.

[↑ Back to top](#table-of-contents)

## Performance (Debounce, Throttle, Memoization)

### 60. Memory Leak: You notice a memory leak in a production SPA – how do you identify and fix it?

**Identify**:
- Use Chrome DevTools **Memory** tab: take heap snapshots before and after the suspected user actions (e.g., opening/closing a modal, navigating between pages). Compare snapshots to see which objects are retained.
- Look for **detached DOM nodes** – elements removed from the DOM but still referenced in JavaScript (e.g., event listeners not cleaned, closures holding references).
- Monitor `performance.memory` in real time to see JS heap growth.
- Use the **Performance** tab with “Memory” checkbox to correlate memory usage with actions.

**Common causes**:
- Event listeners not removed on component unmount.
- `setInterval` / `setTimeout` not cleared.
- WebSocket connections not closed.
- Large data structures kept in global state or closures.
- Forgotten subscriptions (e.g., to observables).

**Fix**:
- Add cleanup functions in `useEffect` (return function).
- Use `AbortController` for fetch requests.
- Use `WeakMap` / `WeakSet` for caches.
- Ensure global event listeners are removed.
- Use React DevTools profiler to detect unmounted components that are still referenced.
- Consider using a tool like `why-did-you-render` to spot accidental retention.

[↑ Back to top](#table-of-contents)

## Generators, Iterators & Symbols

### 61. How do generators implement iterators?

`function*` creates a generator function returning a generator object that is both an iterable and an iterator. `yield` pauses execution and provides the next value. `yield*` delegates to another iterable. Generator's `next()` resumes from the last `yield`.

[↑ Back to top](#table-of-contents)

### 62. How would you implement a simple reactive system (like Vue's reactivity)?

Track the currently executing effect in a global variable. `reactive(obj)`: wrap with `Proxy`. On `get`, if an effect is running, add it to that property's subscriber Set (track). On `set`, call all subscribers (trigger). Effects run their function, which accesses reactive properties, automatically subscribing. This is Vue 3's reactivity core.

[↑ Back to top](#table-of-contents)

## Modules, Build Tools & Browser APIs

### 63. How would you build an offline-first JavaScript web app?

Service Worker for caching assets and API responses (Cache API). Background sync for deferring requests when offline. IndexedDB for structured client-side storage. Optimistic UI updates that sync when connection restores. Conflict resolution strategy (last-write-wins or CRDT). Workbox simplifies service worker caching strategies.

[↑ Back to top](#table-of-contents)

## General / Miscellaneous JavaScript Concepts

### 64. A page is consuming too much memory over time — how would you detect and prevent memory leaks?

Memory leaks in Node.js usually come from global caches, event listeners not removed, or lingering references.

- **Detection:**
- Monitor heap size using `process.memoryUsage()` and look for steady growth.
- Take heap snapshots (Chrome DevTools or `node --inspect`) and compare before/after operations to find objects that should have been garbage collected but persist.
- Use `--trace-gc` to see GC activity; if GC runs frequently but heap grows, there’s a leak.
- **Common culprits:**
- **Event listeners:** Forgetting `removeListener` on `EventEmitter` or `process.on`. Use tools like `why-is-node-running` to see pending listeners.
- **Caches:** Unbounded caches (e.g., `Map` or object) that never expire. Implement TTL or size limits (use `lru-cache`).
- **Closures:** Accidentally retaining large objects in closure scopes referenced by long‑living callbacks.
- **Global variables:** Attaching large data to `global` or `module.exports` unintentionally.
- **Prevention:**
- Use weak references (`WeakMap`, `WeakSet`) for caching when appropriate.
- Always remove listeners in cleanup functions (e.g., `on('data', handler)` paired with `off('data', handler)`).
- For HTTP servers, ensure responses are ended and streams are destroyed.
- Use tools like `memwatch-next` or `node-memwatch` to detect leaks in tests.

[↑ Back to top](#table-of-contents)

### 65. How do you approach writing JavaScript for low-powered devices?

Minimize main thread work — offload to Workers. Avoid long tasks (> 50ms). Use passive event listeners. Reduce layout thrash — batch reads and writes. Minimize repaints. Prefer CSS animations over JS animations. Code split aggressively. Avoid large dependency bundles. Test on real low-end devices with CPU throttling in DevTools. Use the `scheduler` API (when available) to yield to the browser.

[↑ Back to top](#table-of-contents)

### 66. How do you ensure JavaScript is accessible?

Manage focus after dynamic content changes. Announce dynamic updates via `aria-live` regions. Don't rely solely on color or hover states. Ensure all interactive elements are keyboard operable (Enter/Space, arrow keys per ARIA patterns). Test with screen readers (NVDA, VoiceOver). Use eslint-plugin-jsx-a11y for automated linting.

[↑ Back to top](#table-of-contents)

### 67. How do you handle breaking API changes safely on the frontend?

**Strategies**:
- **Versioned API**: Include API version in URL (e.g., `/v1/users`). Deprecate old versions gradually.
- **Adapters**: Write adapters that transform new API responses to the old shape, so frontend can upgrade later.
- **Feature flags**: Roll out new API calls behind a flag; enable gradually.
- **Backward compatibility**: Backend can support both old and new response shapes for a period.
- **Contract testing**: Use tools like Pact to verify consumer‑provider compatibility.

[↑ Back to top](#table-of-contents)

### 68. How do you handle disagreements in technical decisions?

**Approach**: Emphasize collaboration, data‑driven reasoning, and maintaining positive relationships. Show that you can advocate for your view while being open to alternatives.

**Example**:
> “I believe healthy disagreements lead to better solutions. I handle them by:
> - **Understanding the other person’s perspective** – I ask questions to uncover their concerns and constraints.
> - **Gathering evidence** – I prototype both approaches, run benchmarks, or present data (e.g., bundle size, render performance) to support my case.
> - **Focusing on the problem, not the person** – I frame the discussion around technical trade‑offs, not ego.
> - **Escalating when necessary** – if we cannot agree, I propose a quick spike or bring in a third team member. Ultimately, I respect the decision of the team lead or architect.
>
> For example, we debated whether to use Redux or Context for a new feature. I preferred Redux for predictability and DevTools, while another developer wanted Context to reduce boilerplate. I built a small prototype showing that Context caused unnecessary re‑renders because the state changed frequently. After seeing the data, we agreed on Redux Toolkit, which satisfied both concerns.”

[↑ Back to top](#table-of-contents)

### 69. How do you handle JavaScript in a security-sensitive context (e.g., fintech)?

Subresource Integrity (SRI) on external scripts. Strict CSP. No `eval`, `new Function`, `innerHTML` with user data. Sanitize all inputs. HTTPS everywhere. `HttpOnly`/`Secure` cookies. Dependency auditing (`npm audit`). Regular penetration testing. Runtime Application Self-Protection (RASP). Code review for timing attacks and prototype pollution.

[↑ Back to top](#table-of-contents)

### 70. How do you handle offline‑first apps with IndexedDB, background sync, and conflict resolution?

**Offline‑first architecture**:

[↑ Back to top](#table-of-contents)

### 71. How do you handle versioning of UI contracts?

**Context**: When frontend and backend are developed independently, or when multiple frontend teams share a common component API.

**Strategies**:

[↑ Back to top](#table-of-contents)

### 72. How would you build an undo/redo system?

Maintain two stacks: undo stack and redo stack. On action: push current state to undo, clear redo. On undo: pop from undo → apply → push to redo. On redo: pop from redo → apply → push to undo. For commands (not full state snapshots), store `do`/`undo` function pairs to avoid cloning large state objects.

[↑ Back to top](#table-of-contents)

### 73. How would you compile a simple expression language to JavaScript?

Lexer: tokenize the input string into tokens (numbers, operators, identifiers, parentheses). Parser: build an Abstract Syntax Tree (AST) using recursive descent. Code generator: walk the AST and emit JavaScript (or evaluate directly from the AST). Libraries: Acorn (JS parser), Chevrotain (parser toolkit).

[↑ Back to top](#table-of-contents)

### 74. How would you design a client-side caching layer?

LRU (Least Recently Used) cache: doubly linked list + Map for O(1) get/set. `get(key)`: move node to front. `set(key, val)`: add to front, evict tail if over capacity. Add TTL: store expiry timestamp, check on `get`. Add stale-while-revalidate: return stale value while background-fetching fresh data.

[↑ Back to top](#table-of-contents)

### 75. How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)

**Web Workers** – offload data processing, sorting, filtering, or any CPU‑intensive task to a background thread.
- The worker processes the dataset and returns a result (e.g., filtered list) to the main thread.
- The main thread remains responsive for UI updates.

**Virtualization** – as described, reduces the number of DOM nodes, so the main thread has less work to do.

**Chunking / Time‑slicing** – break up heavy work into smaller chunks using `setTimeout` or `scheduler.postTask` to allow the browser to handle user interactions in between.

**Streaming / Pagination** – load data incrementally rather than all at once.

**WebAssembly** – if dataset processing is extremely heavy, consider using Wasm for performance (though overkill for most cases).

[↑ Back to top](#table-of-contents)

### 76. How would you implement a JavaScript interpreter in JavaScript?

Tokenize input into a stream of tokens (lexer). Parse tokens into an AST (parser — use recursive descent for simplicity). Evaluate the AST recursively (interpreter): for literals, return the value; for binary expressions, evaluate both sides; for identifiers, look up in an environment object; for function calls, evaluate the function and arguments then apply. This is the basis of js-interpreter and Babel plugins.

[↑ Back to top](#table-of-contents)

### 77. How would you implement a persistent undo history that survives page reload?

Store the action history (not full state snapshots) in `localStorage` or `IndexedDB`. On load, replay the action log to reconstruct state. For large histories, use snapshots at intervals: store the base snapshot plus a delta log since the last snapshot. Limit history length to control storage size.

[↑ Back to top](#table-of-contents)

### 78. How would you implement a simple template engine?

Replace `{{variable}}` placeholders with values from a context object: `str.replace(/\{\{(\w+)\}\}/g, (_, key) => context[key] ?? '')`. For loops and conditionals, parse into an AST and evaluate. For production use: Handlebars, Mustache, or Nunjucks. For type safety: tagged template literals with TypeScript.

[↑ Back to top](#table-of-contents)
