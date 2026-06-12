# Frontend Coding Interview — Complete Question Bank

> Every question that has appeared, is likely to appear, or is considered "must-know" for frontend coding interviews — across all formats (conceptual, output-based, polyfill/implementation, machine coding, system design).

---

## Table of Contents

1. [HTML — Semantics, Accessibility, Structure](#1-html)
2. [CSS — Layout, Specificity, Animation, Performance](#2-css)
3. [JavaScript — Conceptual / Oral Round](#3-javascript-conceptual)
4. [JavaScript — Output-Based Questions](#4-javascript-output-based)
5. [JavaScript — Polyfills & Implementations (Implementation Round)](#5-javascript-polyfills--implementations)
6. [Browser Internals & Web APIs](#6-browser-internals--web-apis)
7. [Async JavaScript](#7-async-javascript)
8. [TypeScript](#8-typescript)
9. [React — Conceptual](#9-react-conceptual)
10. [React — Coding / Implementation](#10-react-coding--implementation)
11. [Machine Coding Round — Component Build Questions](#11-machine-coding-round)
12. [Frontend System Design](#12-frontend-system-design)
13. [Performance & Web Vitals](#13-performance--web-vitals)
14. [Accessibility (a11y)](#14-accessibility-a11y)
15. [Security (XSS, CSRF, CSP)](#15-security)
16. [Testing](#16-testing)
17. [Build Tools, Bundlers & DevOps](#17-build-tools-bundlers--devops)
18. [DSA for Frontend (Commonly Asked)](#18-dsa-for-frontend)
19. [Miscellaneous / Advanced Topics](#19-miscellaneous--advanced)

---

## 1. HTML

### Semantics & Structure

- What is the purpose of the `DOCTYPE` declaration? What happens if you omit it?
- What is the difference between `<section>`, `<article>`, `<aside>`, `<main>`, `<nav>`, and `<div>`?
- When should you use `<button>` vs `<a>`? What are the accessibility implications?
- What is the difference between inline, inline-block, and block elements? Give examples.
- Explain the difference between `<strong>`, `<b>`, `<em>`, and `<i>`.
- What are void elements in HTML? Give 5 examples.
- What is the difference between `<script>`, `<script async>`, and `<script defer>`? Draw the parsing timeline.
- What are Web Components? When would you use them over a framework component?
- What is the shadow DOM? How does it relate to encapsulation?
- What are custom HTML elements? How do you register one?
- What is the difference between `<link>` and `@import` for stylesheets?
- What are data attributes (`data-*`)? When should you use them?
- What is the difference between `<input type="submit">` and `<button type="submit">`?
- Explain how the `<template>` element works.
- What is the difference between `<picture>`, `<figure>`, and `<img>`? When do you use `srcset`?
- How does the `<details>` and `<summary>` element work natively?
- What are the differences between HTML4 and HTML5? Name 5 new semantic elements.
- What is the purpose of the `<meta charset="UTF-8">` tag?
- What is the `viewport` meta tag and why is it important for responsive design?
- How does the `<canvas>` element work vs `<svg>`? When would you choose one over the other?

### Forms & Accessibility

- How do you implement accessible form labels and error messaging?
- What is the difference between `placeholder` and `label`? Why is `placeholder` not a substitute?
- What are ARIA roles? Give 5 examples with their use cases.
- What are ARIA landmark regions?
- What is the `tabindex` attribute? What does `tabindex="0"`, `tabindex="-1"`, and `tabindex="5"` do?
- What is `aria-label` vs `aria-labelledby` vs `aria-describedby`?
- How does a screen reader interpret your markup? Walk through an example form.
- What are the HTML5 form validation attributes? (`required`, `pattern`, `min`, `max`, etc.)
- How do you make an image accessible? When should `alt` be empty?

---

## 2. CSS

### Box Model & Layout

- Explain the CSS box model. What is the difference between `content-box` and `border-box`?
- What is the difference between `margin` and `padding`? Can `margin` be negative?
- What is margin collapsing? When does it happen and when does it not?
- Explain Flexbox. What are the main axis and cross axis?
- What is the difference between `justify-content` and `align-items`?
- Explain CSS Grid. What is the difference between `grid-template-columns` and `grid-auto-columns`?
- When would you use Flexbox vs CSS Grid? Give real-world examples.
- What is the difference between `fr` unit and `%` in CSS Grid?
- What are named grid areas? How do you implement a holy grail layout with CSS Grid?
- How does `position: relative`, `absolute`, `fixed`, `sticky` work? What is each relative to?
- What is the containing block concept in CSS?
- What is `z-index`? Why doesn't it work on a `position: static` element?
- What are stacking contexts? How are they created?
- How does `float` work? Why is it mostly replaced by Flexbox/Grid today?
- What are the different CSS display values? (`block`, `inline`, `inline-block`, `flex`, `grid`, `none`, `contents`, `table`)
- How do you center a div both horizontally and vertically — name 5 different ways.
- What is `overflow: hidden`, `scroll`, `auto`, `clip`? How does `overflow: hidden` affect stacking?
- What is the difference between `visibility: hidden` and `display: none` and `opacity: 0`?

### Specificity, Cascade & Selectors

- Explain CSS specificity. How is it calculated? What beats what?
- What is the difference between `!important` and inline styles in the specificity hierarchy?
- What is the CSS cascade? In what order are styles applied?
- What is the difference between `:is()`, `:where()`, and `:not()`?
- What are CSS custom properties (variables)? How do they cascade and inherit?
- What is the `@layer` rule? How does it change cascade order?
- What is the difference between `:nth-child()` and `:nth-of-type()`?
- What are pseudo-elements (`::before`, `::after`, `::placeholder`, etc.) and how do they work?
- What is the `:root` selector? Why is it used over `html` for custom properties?

### Responsive Design & Media Queries

- What is the difference between `em`, `rem`, `px`, `vw`, `vh`, `%`?
- What is the difference between `min-width` and `max-width` in media queries? Which is mobile-first?
- What are container queries? How are they different from media queries?
- How does `clamp()` work? Write a fluid font-size using `clamp`.
- What is the difference between `min()`, `max()`, and `clamp()` CSS functions?
- What is responsive typography? How do you implement it without media queries?

### Animations & Transitions

- What is the difference between CSS `transition` and `animation`?
- What properties can be animated efficiently (compositor-only)? Why are `transform` and `opacity` preferred?
- What is `will-change`? When should and shouldn't you use it?
- What is `requestAnimationFrame`? Why is it better than `setInterval` for animation?
- What is the difference between `animation-fill-mode: forwards`, `backwards`, `both`?
- How do you implement a keyframe animation that pauses on hover?
- What is the `prefers-reduced-motion` media query? Why is it important?

### CSS Architecture & Advanced

- What are BEM, SMACSS, OOCSS? When would you use each?
- What is CSS-in-JS? What are the trade-offs vs CSS Modules vs utility-first (Tailwind)?
- How does CSS containment work (`contain: layout paint style`)?
- What is the difference between `Sass` and `Less`? What features do they provide over plain CSS?
- What is CSS Houdini? What problems does it solve?
- What are logical properties in CSS? (`margin-inline-start`, `padding-block-end`, etc.)
- How would you implement a dark mode using CSS custom properties?
- What is `aspect-ratio`? How does it prevent Cumulative Layout Shift?

---

## 3. JavaScript — Conceptual

### Core Language

- What is the difference between `var`, `let`, and `const`? Explain scope, hoisting, and TDZ.
- What is hoisting? How does it differ for `var`, `let/const`, and function declarations?
- What is the Temporal Dead Zone (TDZ)?
- Explain closures. Give a real-world use case.
- What is a closure trap in loops? How do you fix it?
- What is lexical scoping vs dynamic scoping?
- Explain the `this` keyword. What does `this` refer to in: arrow function, regular function, class method, event handler, `call/apply/bind`?
- What is the difference between `call`, `apply`, and `bind`?
- What is the prototype chain? How does prototypal inheritance work?
- What is the difference between `Object.create()` and the `new` keyword?
- What are getters and setters in JavaScript?
- What is the difference between `==` and `===`? Give examples of type coercion.
- What is `typeof null`? Why is it `"object"`? (Historical quirk)
- What is the difference between `undefined` and `null`?
- What is `NaN`? How do you check for it?
- What is the difference between `Object.freeze()`, `Object.seal()`, and `Object.preventExtensions()`?
- What is the difference between shallow copy and deep copy? How do you implement each?
- What are symbols in JavaScript? What are they used for?
- What are `WeakMap` and `WeakSet`? How do they differ from `Map` and `Set`?
- What are generators (`function*`)? What is `yield`?
- What are iterators and iterables? What is the iterator protocol?
- What is the difference between `for...in` and `for...of`?
- What are tagged template literals?
- What is destructuring? Explain object and array destructuring with defaults.
- What is the rest operator vs the spread operator? Give examples.
- What are optional chaining (`?.`) and nullish coalescing (`??`)?
- What is `Object.assign()` vs spread operator for objects? What are the differences?
- What is `Array.from()` vs `Array.of()`?
- What is `structuredClone()`?
- What is the difference between a pure function and an impure function?
- What is function currying? Implement a curried `add` function.
- What is memoization? Implement a generic `memoize` function.
- What is function composition?
- What is the module system? Difference between CommonJS (`require`) and ES Modules (`import/export`)?
- What is tree shaking? How does it work with ES Modules?
- What is a higher-order function? Give 3 examples.
- What is the difference between `Array.prototype.map`, `filter`, `reduce`, `forEach`, `find`, `findIndex`, `some`, `every`, `flat`, `flatMap`?
- What is `Array.prototype.sort()`'s default behavior? Why can it be dangerous?

### Memory & Garbage Collection

- How does JavaScript garbage collection work? What is mark-and-sweep?
- What causes memory leaks in JavaScript? List 5 common causes.
- What are detached DOM nodes? Why do they cause memory leaks?

---

## 4. JavaScript — Output-Based

These are questions where you are given a code snippet and asked what the output is:

- What is the output of `typeof typeof 1`?
- What logs from:
  ```js
  console.log(1);
  setTimeout(() => console.log(2), 0);
  Promise.resolve().then(() => console.log(3));
  console.log(4);
  ```
- What is the output of using `var` in a `for` loop with `setTimeout`:
  ```js
  for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 0);
  }
  ```
  And why? How do you fix it with `let` or an IIFE?
- What does the following output and why?
  ```js
  console.log(0.1 + 0.2 === 0.3);
  ```
- What is the result of `[] + []`, `[] + {}`, `{} + []`?
- What does `[1, 2, 3].map(parseInt)` return?
- What is the output of:
  ```js
  const obj = { a: 1 };
  const obj2 = obj;
  obj2.a = 2;
  console.log(obj.a);
  ```
- What logs in this `this` context question:
  ```js
  const obj = {
    name: 'test',
    getName: function() { return this.name; },
    getNameArrow: () => this.name
  };
  console.log(obj.getName());
  console.log(obj.getNameArrow());
  ```
- What does `'5' - 3`, `'5' + 3`, `'5' * '3'`, `true + true` evaluate to?
- What is the output of:
  ```js
  console.log(typeof undefined === typeof NULL);
  ```
- What is the output of the following closure?
  ```js
  function outer() {
    let x = 10;
    function inner() { console.log(x); }
    x = 20;
    return inner;
  }
  outer()();
  ```
- What does this Promise chain output?
  ```js
  Promise.resolve(1)
    .then(x => x + 1)
    .then(x => { throw x })
    .catch(x => console.log(x))
    .then(() => console.log('done'));
  ```
- What is the output of `null == undefined` vs `null === undefined`?
- Hoisting with `var` and `function`:
  ```js
  foo();
  var foo = function() { console.log('var'); };
  function foo() { console.log('function'); }
  foo();
  ```
- What does this event loop output?
  ```js
  async function foo() {
    console.log('A');
    await Promise.resolve();
    console.log('B');
  }
  console.log('C');
  foo();
  console.log('D');
  ```
- What is the output of `!!'false'`, `!!null`, `!!0`, `!!''`, `!!-1`?
- What does `new Array(3)` vs `Array.of(3)` create?

---

## 5. JavaScript — Polyfills & Implementations

These are the most common "implement from scratch" questions. These test deep understanding of how things work internally.

### Array Methods

- Implement `Array.prototype.map`
- Implement `Array.prototype.filter`
- Implement `Array.prototype.reduce`
- Implement `Array.prototype.forEach`
- Implement `Array.prototype.find` and `findIndex`
- Implement `Array.prototype.some` and `every`
- Implement `Array.prototype.flat` and `flatMap`
- Implement `Array.prototype.includes`
- Implement `Array.prototype.indexOf`
- Implement `Array.from()`
- Implement `Array.prototype.at()`
- Implement `Array.prototype.fill`

### Function Methods

- Implement `Function.prototype.bind`
- Implement `Function.prototype.call`
- Implement `Function.prototype.apply`
- Implement `new` keyword behavior (simulate `new`)

### Object Methods

- Implement `Object.assign`
- Implement `Object.create`
- Implement `Object.keys`, `Object.values`, `Object.entries`
- Implement `Object.freeze`
- Implement deep clone (handle circular references)
- Implement deep equal (deeply compare two objects)
- Implement `Object.groupBy` (newer)

### Promise

- Implement `Promise` from scratch (basic)
- Implement `Promise.all`
- Implement `Promise.allSettled`
- Implement `Promise.race`
- Implement `Promise.any`
- Implement `Promise.resolve` and `Promise.reject`
- Implement a retry mechanism with exponential backoff
- Implement a `promisify` function

### Utility Functions

- Implement `debounce`
- Implement `throttle`
- Implement `memoize` (with and without cache size limit)
- Implement `curry` (with arity awareness)
- Implement `compose` and `pipe`
- Implement `once` (function that runs only once)
- Implement `partial` application
- Implement `flatten` a nested array to a given depth
- Implement `chunk` (split array into chunks of size n)
- Implement `groupBy`
- Implement `pick` and `omit` (like lodash)
- Implement `get` (like lodash `_.get` with dot-notation path)
- Implement `cloneDeep`
- Implement `isEqual` (deep equality)
- Implement `sleep` / `delay` using Promises
- Implement `EventEmitter` (on, off, emit, once)
- Implement `pub/sub` pattern
- Implement `LRU Cache`
- Implement `classNames` utility (like the `classnames` npm package)

### DOM / Browser APIs

- Implement `getElementsByClassName` from scratch
- Implement `getElementsByTagName` from scratch
- Implement `querySelectorAll` for simple selectors
- Implement `addEventListener` with event delegation
- Implement `innerHTML` setter (safely)
- Implement `closest()` polyfill
- Implement `fetch` using `XMLHttpRequest`

### String Methods

- Implement `String.prototype.trim`
- Implement `String.prototype.trimStart` / `trimEnd`
- Implement `String.prototype.repeat`
- Implement `String.prototype.padStart` / `padEnd`
- Implement `String.prototype.startsWith` / `endsWith` / `includes`
- Implement `String.prototype.replaceAll`

### Miscellaneous Implementations

- Implement `setInterval` using `setTimeout`
- Implement `clearInterval` for the above
- Implement `JSON.stringify` (basic version)
- Implement `JSON.parse` (basic version)
- Implement a `deepFreeze` utility
- Implement an observable (basic reactive pattern)
- Implement `localStorage` with expiry

---

## 6. Browser Internals & Web APIs

### Rendering Pipeline

- What is the Critical Rendering Path? Describe all steps (DOM → CSSOM → Render Tree → Layout → Paint → Composite).
- What is the difference between layout, paint, and composite layers?
- What causes reflow? What causes repaint? How are they different?
- What is layout thrashing? How do you avoid it?
- What is `will-change`? Which CSS properties promote elements to their own compositor layer?
- How does the browser handle `requestAnimationFrame`?
- What is the difference between hardware-accelerated and non-accelerated CSS properties?
- What is FOUC (Flash Of Unstyled Content)? How do you prevent it?

### Event Loop & Execution Model

- Explain the JavaScript event loop in detail.
- What is the call stack? What is heap memory?
- What is the difference between the task queue (macrotask queue) and the microtask queue?
- What runs first — `Promise.then()` or `setTimeout(fn, 0)`? Why?
- What are macrotasks vs microtasks? Give examples of each.
- What does `queueMicrotask()` do?
- What is the difference between `process.nextTick` (Node.js) and `Promise.then`?
- What happens when the call stack overflows?

### Storage

- What is the difference between `localStorage`, `sessionStorage`, and `cookies`?
- What is IndexedDB? When would you use it over localStorage?
- What is the difference between session cookies and persistent cookies?
- What are `HttpOnly` and `Secure` cookie flags?
- What is the `SameSite` cookie attribute?
- What is the `Cache-Control` header? What are `no-store`, `no-cache`, `max-age`, `s-maxage`?

### Networking & HTTP

- What is the difference between HTTP/1.1, HTTP/2, and HTTP/3?
- What is multiplexing in HTTP/2?
- What is CORS? How does preflight work?
- What is the difference between a simple CORS request and a preflighted request?
- How do you send credentials (cookies) with a `fetch` request?
- What is the difference between `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, `OPTIONS`?
- What is idempotency in HTTP?
- What is a WebSocket? How is it different from HTTP long polling and SSE?
- What is Server-Sent Events (SSE)?
- What are Service Workers? What is their lifecycle?
- What is the Intersection Observer API? Give a use case.
- What is the MutationObserver API?
- What is the ResizeObserver API?
- What is the `Performance` API? How do you measure FCP, LCP, TTI?
- What is the `navigator.sendBeacon()` API? When would you use it?
- What is `AbortController`? How do you cancel a fetch request?

---

## 7. Async JavaScript

- What is the difference between synchronous and asynchronous code?
- What is a callback? What is callback hell?
- What are Promises? Explain the three states.
- What is the difference between `.then()` chaining and `async/await`?
- What is `async/await`? How does it handle errors?
- What is the difference between `await Promise.all([])` and `await` in a `for` loop (sequential vs parallel)?
- What does `Promise.all` do when one promise rejects?
- How does `Promise.allSettled` differ from `Promise.all`?
- What is `Promise.race`? Give a real-world use case (e.g., timeout).
- What is `Promise.any`? How is it different from `Promise.race`?
- How do you implement a request queue that limits concurrent requests to N?
- How do you implement an async retry with backoff?
- How do you implement cancellation of an async operation?
- What is the difference between `try/catch` in async functions and `.catch()` on promises?
- What happens if you `await` a non-Promise value?
- Can you use `await` at the top level in a module? (Top-level await)
- How do you handle multiple independent async calls that should all complete before proceeding?
- What is an async generator? When would you use one?

---

## 8. TypeScript

- What is the difference between `any`, `unknown`, and `never`?
- What is `void` vs `undefined` as a return type?
- What is the difference between `interface` and `type`?
- When would you use `type` over `interface`?
- What are generics? Write a generic identity function and a generic array wrapper.
- What is a union type (`A | B`) vs an intersection type (`A & B`)?
- What are utility types? Explain `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`, `Exclude`, `Extract`, `NonNullable`, `ReturnType`, `Parameters`.
- What is type narrowing? How does TypeScript narrow types from `unknown`?
- What are type guards? How do you implement a custom type guard?
- What is the `satisfies` operator (TS 4.9)?
- What is a discriminated union? Give an example.
- What is a mapped type? Write an example.
- What are template literal types?
- What is `keyof` and `typeof` in TypeScript?
- What is a conditional type in TypeScript? Give an example.
- What are declaration files (`.d.ts`)? When do you need them?
- What is `as const`? How does it affect type inference?
- What is strict mode in TypeScript? What does `strictNullChecks` enable?
- How do you type a React component's props? What is `React.FC` vs manually typing props?
- What is `infer` in TypeScript?

---

## 9. React — Conceptual

### Core

- What is the Virtual DOM? How does reconciliation work?
- What is the diffing algorithm React uses? What are its heuristics?
- What is JSX? How does it compile down?
- What is the difference between a controlled and an uncontrolled component?
- What is the difference between `props` and `state`?
- What is prop drilling? How do you avoid it?
- When does a React component re-render?
- What is React.memo? When does it help and when does it not?
- What is the difference between `useMemo` and `useCallback`?
- What is `useRef`? List 3 use cases that aren't just DOM access.
- What is `useReducer`? When would you use it over `useState`?
- What is `useContext`? What are its performance implications?
- What is `useLayoutEffect`? How and when does it differ from `useEffect`?
- What is `useImperativeHandle`? When would you use `forwardRef`?
- What is `useDeferredValue`? What is `useTransition`? When do you use each?
- What are the rules of hooks? Why do they exist?
- What is React Fiber? What problem did it solve over the old reconciler?
- What is concurrent mode in React?
- What is `Suspense`? How does it work?
- What is `React.lazy()`? How does it differ from dynamic `import()`?
- What is `Error Boundary`? How do you implement one?
- What is `StrictMode`? What does it double-invoke?
- What are compound components? Give an example.
- What are render props? Give an example.
- What are Higher-Order Components (HOCs)?
- What is the difference between `children` and render props?
- What is the Context API vs Redux? When would you choose each?
- What is Zustand? How does it compare to Redux Toolkit?
- What is React Query (TanStack Query)? What problem does it solve?
- What is SWR? How does it handle caching and revalidation?
- What is the difference between `key` prop for reconciliation and `key` as a reset trick?
- What is `flushSync`? When would you use it?

### React 18+ / Modern React

- What are the new features in React 18? (automatic batching, `useTransition`, `useDeferredValue`, concurrent features)
- What is automatic batching in React 18?
- What is the `use()` hook in React 19?
- What are React Server Components (RSC)? How do they differ from SSR?
- What is the difference between a Server Component and a Client Component in Next.js App Router?
- What is `use client` and `use server` directive in Next.js 13+?
- What is the `useOptimistic` hook (React 19)?

---

## 10. React — Coding / Implementation

These are live coding questions in React:

- Implement a custom `useFetch` hook that handles loading, error, and data states.
- Implement a custom `useDebounce` hook.
- Implement a custom `useThrottle` hook.
- Implement a custom `useLocalStorage` hook.
- Implement a custom `useIntersectionObserver` hook.
- Implement a custom `usePrevious` hook (returns previous state value).
- Implement a custom `useMediaQuery` hook.
- Implement a custom `useEventListener` hook.
- Implement a custom `useClickOutside` hook.
- Implement a custom `useWindowSize` hook.
- Implement a custom `useAsync` hook (manage async function states).
- Build a counter that increments and decrements.
- Build a controlled form with validation (email, password strength).
- Build a search input with debouncing that fetches from an API.
- Build a list that renders only visible items (virtualization, manual).
- Implement a todo list with CRUD and localStorage persistence.
- Build a shopping cart with add, remove, update quantity, and total calculation.
- Build a multi-step form wizard with Next/Back navigation and validation.
- Build an accordion with multiple or single open behavior.
- Build a modal / dialog with focus trap and escape key to close.
- Implement pagination (client-side and server-side).
- Implement infinite scroll using Intersection Observer.
- Build a drag-and-drop list (without libraries).
- Build a star rating component.
- Build a file upload component with drag-and-drop, progress, and preview.
- Implement a recursive comment thread (nested comments with reply).
- Fix a component that has a stale closure problem in `useEffect`.
- Fix a component where `useEffect` has missing dependencies (ESLint warning trap).
- Fix a React component that causes infinite re-renders.
- Given a slow React tree, identify and fix the performance bottleneck (profile, add `memo`, `useMemo`, `useCallback`).
- Implement `useReducer` for a complex form state.
- Implement context + reducer for a mini global state.
- Build a real-time search/filter over a large list with debouncing.
- Build a typeahead / autocomplete component.
- Build tabs component with lazy-loaded content.
- Implement a carousel/image slider.
- Build a tree view (expandable/collapsible nodes).
- Implement a virtualized list (render only visible rows).
- Build a Kanban board with columns and drag-and-drop cards.
- Build a data grid/table with sort, filter, and pagination.

---

## 11. Machine Coding Round

These are "build this from scratch" questions given as a 45–90 min challenge:

### Classic Component Builds (Vanilla JS or React)

- Build a `TodoApp` — add, edit, delete, filter (active/completed/all), persistence.
- Build a `Calculator` — basic arithmetic with operator precedence.
- Build a `Stopwatch` — start, stop, reset, lap.
- Build a `Digital Clock` — live updating, AM/PM toggle.
- Build a `Countdown Timer` — user-defined duration, pause/resume.
- Build an `Image Carousel` — auto-play, prev/next, dot indicators, pause on hover.
- Build a `Modal / Dialog` — open/close animation, focus trap, backdrop click to close.
- Build a `Toast Notification System` — multiple toasts, auto-dismiss, types (success/error/info).
- Build a `Accordion / FAQ` — single or multi-open, smooth animation.
- Build `Tabs` — active tab highlight, lazy content, URL sync.
- Build a `Progress Bar` — animated, determinate and indeterminate.
- Build a `Rating Component (Stars)` — hover preview, half-star support.
- Build a `Typeahead / Autocomplete` — debounced API call, keyboard navigation, highlight match.
- Build a `Tag Input` — add/remove tags, no duplicates, comma/enter to add.
- Build a `Color Picker` — hex/rgb/hsl, alpha, preview swatch.
- Build a `Date Picker` — month navigation, date selection, range support.
- Build a `Drag & Drop List` — reorderable items, visual feedback.
- Build a `File Upload` — multi-file, drag-and-drop zone, progress per file, cancel.
- Build a `Infinite Scroll` — fetch next page on scroll end, loading skeleton.
- Build a `Virtual Scroll / List` — render only visible rows (e.g., 10,000 items, only show 20).
- Build a `Tree View` — expandable/collapsible nodes, multi-level.
- Build a `Breadcrumb` component with dynamic segments.
- Build a `Stepper / Wizard Form` — multi-step, validation, back/next.
- Build a `Data Table` — sort, filter, pagination, row selection.
- Build a `Kanban Board` — multiple columns, drag cards between columns.
- Build a `Comment Thread` — nested replies, collapse/expand, recursive rendering.
- Build a `Responsive Navigation Bar` — hamburger menu on mobile, dropdown on desktop.
- Build a `Sticky Header` — hides on scroll down, shows on scroll up.
- Build a `Scroll-to-Top Button` — appears after scrolling down a certain amount.
- Build a `Read More / Truncate` component — expand inline.
- Build a `Code Editor` (textarea with syntax highlight using a `pre` overlay approach).

### Logic-Heavy / Tricky Builds

- Build a grid of boxes in a "C" shape; clicking turns them green. When all are green, they revert back to yellow one by one in the order they were clicked (1-second delay each).
- Build a `Snake Game` using JS and Canvas.
- Build a `Minesweeper` game.
- Build a `Tic-Tac-Toe` with win detection and reset.
- Build a `Sudoku Validator`.
- Build a `Memory Card Game` — flip two cards, match pairs.
- Build a `Connect Four` — gravity-based piece drop, win detection.
- Build a `Traffic Light` that cycles through states automatically.
- Build a `Poll/Vote System` — vote and see live % bar update.
- Build an `Expense Tracker` — add/delete, category filter, total.
- Build a `Multi-Select` dropdown with search and chips.
- Build an `OTP Input` — 6 boxes, auto-advance, backspace to go back, paste support.

---

## 12. Frontend System Design

These are open-ended design questions asked at senior levels. You are expected to walk through requirements, architecture, component design, data flow, API design, performance, and edge cases.

### Applications to Design

- Design a **News Feed** (like Facebook/Twitter) — infinite scroll, real-time updates, optimistic likes.
- Design a **YouTube / Video Streaming** frontend — adaptive bitrate, buffering, controls, recommendation sidebar.
- Design a **Google Docs** collaborative editor — real-time sync, conflict resolution (OT/CRDT), offline mode.
- Design an **E-commerce Product Listing Page** — filters, sort, pagination, search, cart management.
- Design a **Chat Application** (like WhatsApp Web) — WebSocket, message status, typing indicators, media.
- Design a **Notification System** — polling vs WebSocket vs SSE, badge count, read/unread.
- Design an **Autocomplete Search** — debounce, caching results, handling stale results, keyboard nav.
- Design a **Form Builder** — drag-and-drop fields, dynamic validation, schema-based rendering.
- Design an **Image Gallery** — lazy loading, masonry layout, lightbox, virtual scroll.
- Design a **Calendar / Scheduling App** — recurring events, timezone support, drag-to-reschedule.
- Design a **Design System / Component Library** — tokens, theming, accessibility, docs, versioning.
- Design a **Dashboard / Analytics UI** — charts, real-time data, resizable widgets, filter persistence.
- Design a **Code Editor** (like CodeSandbox) — syntax highlighting, file tree, live preview, hot reload.
- Design a **Maps Application** — tile rendering, markers, clustering, real-time updates.
- Design a **Pinterest-style Masonry Feed** — variable height cards, virtual scroll.
- Design a **Ride Hailing App UI** — real-time driver tracking, map, WebSocket, fare estimation.

### System Design Concepts (Frontend-Specific)

- How would you implement **client-side caching**? What strategies would you use?
- How would you handle **pagination vs infinite scroll** at scale? Trade-offs?
- How would you design a **state management architecture** for a large React app?
- How would you implement **offline support** (PWA, Service Workers, sync queue)?
- How would you design a **micro-frontend architecture**?
- How would you implement **real-time collaboration** on the frontend?
- How would you architect a **multi-tenant SaaS frontend**?
- How would you handle **error boundaries and fallback UI** at a product level?
- How would you design a **feature flag system** on the frontend?
- How would you implement **A/B testing** on the client?
- How would you implement **i18n (internationalization) and l10n (localization)**?
- How would you design a **frontend monitoring and observability** system? (error tracking, performance monitoring)
- How would you implement **authentication flows** (OAuth2, token refresh, logout everywhere)?
- How would you design a **URL routing architecture** for a large SPA?
- How would you design a **server-side rendering architecture** for an e-commerce app?

---

## 13. Performance & Web Vitals

- What are Core Web Vitals? Define LCP, FID, CLS, INP, TTFB, FCP.
- What are the "Good" thresholds for LCP, CLS, and INP?
- How do you measure LCP in production? What are common causes of poor LCP?
- How do you measure and fix CLS? What are the most common CLS causes?
- What is INP and how does it replace FID?
- How do you analyze performance in Chrome DevTools? What is the Performance panel?
- What is the Network waterfall? How do you diagnose render-blocking resources?
- What is `<link rel="preload">` vs `<link rel="prefetch">` vs `<link rel="preconnect">`?
- What is `<link rel="dns-prefetch">`?
- How does `loading="lazy"` on images and iframes work?
- What is code splitting? How do you implement route-based splitting in React?
- What is tree shaking? What are conditions for tree shaking to work?
- What is a bundle analyzer? How do you use `webpack-bundle-analyzer`?
- What is the difference between critical CSS and non-critical CSS? How do you inline critical CSS?
- What is font subsetting? What is `font-display: swap`?
- What is an image sprite? When is it still relevant?
- What are modern image formats? (`WebP`, `AVIF`) When do you use `srcset` and `sizes`?
- What is a CDN? How does edge caching work?
- What is HTTP/2 server push? Why is it mostly deprecated now?
- What is Lighthouse? How do you interpret its audit results?
- What is the difference between `DOMContentLoaded` and `load` events?
- What is TTFB (Time to First Byte) and how do you reduce it?
- What is `navigation.sendBeacon`? What is it better than XHR for analytics?
- How do you implement skeleton screens vs spinners? Which is better for perceived performance?
- What is `content-visibility: auto` CSS property? How does it help rendering performance?
- How do you reduce JavaScript parse and execution time?
- What is the `PerformanceObserver` API?

---

## 14. Accessibility (a11y)

- What is WCAG? What are the levels (A, AA, AAA)?
- What are the 4 WCAG principles? (POUR — Perceivable, Operable, Understandable, Robust)
- What are ARIA roles and attributes? When should you use them vs native HTML?
- What is the rule "No ARIA is better than bad ARIA"?
- How do you implement keyboard navigation in a custom dropdown?
- What is a focus trap and when do you need one?
- How do you implement skip links?
- What is the minimum color contrast ratio for AA compliance?
- How do you make an icon button accessible?
- What is `role="status"` and `aria-live`? What are the `polite` and `assertive` values?
- How do you make a custom `<div>` checkbox accessible?
- What is `aria-expanded`, `aria-controls`, `aria-haspopup`?
- How do you test accessibility? What tools do you use? (axe DevTools, Lighthouse, screen readers)
- What is the difference between `aria-hidden="true"` and `display: none` for assistive tech?
- What is ARIA `role="alert"`? When do you use it vs `role="status"`?
- How do you handle focus management when a modal opens and closes?
- What is `prefers-reduced-motion` and how do you respect it in CSS and JS animations?
- What is `prefers-color-scheme`?
- What is the difference between `role="button"` on a `<div>` and a native `<button>`? (Also handle Enter/Space key)

---

## 15. Security

- What is XSS (Cross-Site Scripting)? What are the 3 types?
- How do you prevent XSS in React? (React escapes by default; `dangerouslySetInnerHTML`)
- What is CSRF (Cross-Site Request Forgery)? How do you prevent it?
- What is CSP (Content Security Policy)? What does a basic CSP header look like?
- What is `Subresource Integrity (SRI)`?
- What is Clickjacking? How do you prevent it? (`X-Frame-Options`, `frame-ancestors`)
- What is the `Referrer-Policy` header?
- What is `HTTPS`? Why is mixed content a security issue?
- What are `HttpOnly` and `Secure` cookie flags?
- What is the `SameSite` cookie attribute and how does it prevent CSRF?
- What is the difference between authentication and authorization?
- What is JWT? How does it work? What are its security risks?
- What is OAuth2? What is the implicit flow vs authorization code flow (PKCE)?
- What is a Content Security Policy nonce?
- How do you securely store tokens on the client? (HttpOnly cookie vs localStorage — trade-offs)
- What is prototype pollution? How does it affect JavaScript security?
- What is OWASP Top 10? Which ones are directly relevant to frontend?

---

## 16. Testing

- What is the difference between unit tests, integration tests, and end-to-end (E2E) tests?
- What is the testing pyramid vs the testing trophy (Kent C. Dodds)?
- What is Jest? What is Vitest?
- What is React Testing Library? What is its philosophy? ("Test behavior, not implementation")
- What is the difference between `getBy`, `queryBy`, and `findBy` queries in RTL?
- What is `userEvent` vs `fireEvent` in RTL?
- How do you test a component that fetches data? (Mock `fetch` or use MSW)
- What is MSW (Mock Service Worker)?
- How do you test custom hooks?
- What is snapshot testing? What are its pros and cons?
- What is Cypress? What is Playwright? When would you use E2E tests?
- What is code coverage? What is the difference between line, statement, branch, and function coverage?
- What is test-driven development (TDD)?
- How do you test accessibility in automated tests? (`jest-axe`)
- What is a test double? What is the difference between a mock, stub, and spy?
- How do you test that a component doesn't re-render unnecessarily?
- How do you test error boundaries?

---

## 17. Build Tools, Bundlers & DevOps

- What is Webpack? What is its role?
- What is the difference between Webpack, Vite, Parcel, Rollup, and esbuild?
- Why is Vite faster than Webpack in development? (ES modules, HMR via native ESM)
- What is a loader in Webpack? What is a plugin?
- What is `babel`? What does it transform?
- What is `babel-preset-env`? What is `@babel/polyfill` vs core-js?
- What is source maps? How do they work?
- What is Hot Module Replacement (HMR)?
- What is tree shaking? What conditions prevent it?
- What is code splitting? How do you configure it in Webpack?
- What is the difference between `devDependencies` and `dependencies` in `package.json`?
- What is `package-lock.json` vs `yarn.lock`? Why is locking versions important?
- What is semantic versioning (`^`, `~`, exact)?
- What is `npx`? How is it different from `npm`?
- What is a monorepo? What tools manage them? (Turborepo, Nx, Lerna)
- What is CI/CD? What does a basic frontend CI pipeline look like?
- What is Docker? How would you containerize a frontend app?
- What is the difference between SSR, CSR, SSG, and ISR? (Next.js context)
- What is edge rendering?

---

## 18. DSA for Frontend

These are LeetCode-style problems frequently asked in frontend coding rounds:

### Arrays & Strings

- Two Sum (hash map approach)
- Three Sum
- Maximum Subarray (Kadane's algorithm)
- Product of Array Except Self
- Find all anagrams in a string
- Longest substring without repeating characters
- Group anagrams
- Valid parentheses
- Rotate an array
- Flatten a nested array (without `.flat()`)
- Find the first non-repeating character
- Count occurrences of a character in a string

### Objects & Hashmaps

- Implement a frequency counter
- Implement LRU Cache (Map-based in JS)
- Implement a phone book / contact search
- Deep merge two objects
- Find the difference between two objects

### DOM / Frontend-Specific DSA

- Implement `getElementsByClassName` (BFS/DFS on DOM tree)
- Implement `querySelectorAll` for a CSS selector
- Render a JSON tree as an HTML nested list
- Flatten a nested comment structure
- Implement a virtual DOM diff (simplified)
- Sort a table by column values
- Implement infinite scroll with a FIFO queue
- Build a task scheduler with priorities

### Sorting & Searching

- Implement binary search
- Sort an array of objects by a key
- Find the kth largest element
- Merge sorted arrays
- Count inversions in an array

### Trees & Graphs

- BFS and DFS on a tree of DOM nodes
- Render a tree structure from a flat array with `parentId`
- Find all paths in a file system tree
- Implement a trie (for autocomplete)

### Recursion & Dynamic Programming

- Fibonacci (memoized)
- Flatten nested object with dot-notation keys
- Implement `JSON.stringify`
- Implement a template string parser

---

## 19. Miscellaneous / Advanced Topics

### Progressive Web Apps (PWA)

- What is a PWA? What are the requirements? (Service Worker, Web App Manifest, HTTPS)
- What is a Service Worker? What is its lifecycle?
- What caching strategies does Workbox support? (Cache First, Network First, Stale While Revalidate)
- How do you implement background sync in a PWA?
- What is the Web App Manifest?
- What is the `install` and `activate` lifecycle in a Service Worker?

### Web Workers

- What is a Web Worker? How is it different from a service worker?
- How do you communicate between the main thread and a Web Worker?
- What is `SharedArrayBuffer` and `Atomics`? When would you use them?
- When would you use a Web Worker in a real app?

### Microfrontends

- What is a microfrontend architecture?
- What are the different integration approaches? (build-time, run-time via Module Federation, iframes)
- What is Webpack Module Federation?
- What are the challenges of microfrontend? (shared state, CSS isolation, routing)

### Observability & Monitoring

- What is Sentry? How do you integrate it in a React app?
- What is Real User Monitoring (RUM)?
- What is the `Performance` API? What metrics can you capture?
- How do you track custom events for analytics?
- What is a `Content Security Policy` violation report?

### Rendering Patterns

- Explain SSR, CSR, SSG, ISR, ESR (Edge Side Rendering).
- What is hydration? What is selective hydration?
- What is resumability? How does Qwik differ from React?
- What are React Server Components and how do they eliminate client bundle size?
- What is streaming SSR? How does React 18 support it with `Suspense`?
- What is island architecture? (Astro)
- What is partial hydration?

### Miscellaneous

- What is the difference between GraphQL and REST? When would you use GraphQL on the frontend?
- What is `tRPC`?
- What is OpenAPI / Swagger? How does it help frontend development?
- What is WebAssembly (WASM)? What are its use cases in the frontend?
- What is the `IntersectionObserver` API? Implement lazy image loading with it.
- What is the `ResizeObserver`? What problem does it solve over `window.resize`?
- What are CSS Grid subgrid and CSS `@container` queries?
- What is the difference between a rehydration bug and a hydration mismatch?
- What is the "stale-while-revalidate" caching strategy?
- What is "optimistic UI"? Implement an optimistic like button.
- What are the trade-offs between client-side routing and server-side routing?
- What is the difference between a cookie-based session and a token-based session?
- What is the role of a reverse proxy (Nginx) in serving a frontend app?
- What is the difference between `npm`, `yarn`, `pnpm`?
- What are monorepos and why are they useful for frontend teams?
- What is Storybook and how is it used in component development?

---

## Interview Round Reference

| Round Type | What to Expect |
|---|---|
| **JS Conceptual** | Closures, hoisting, `this`, event loop, prototypes, coercion — oral Q&A |
| **JS Output-Based** | Given code snippet → predict console output |
| **Polyfill / Implement** | Implement `bind`, `debounce`, `Promise.all`, etc. from scratch |
| **React Conceptual** | Hooks, reconciliation, rendering, patterns — oral Q&A |
| **Machine Coding** | Build a UI component in 45–90 min (todo, carousel, modal, etc.) |
| **Frontend System Design** | Design a large frontend system (feed, chat app, etc.) |
| **HTML/CSS Coding** | Build a layout, fix a specificity bug, implement responsive design |
| **DSA (Frontend)** | LeetCode-style problems in JavaScript, often DOM-related |
| **Performance/Accessibility** | Diagnose and fix performance/a11y issues |
