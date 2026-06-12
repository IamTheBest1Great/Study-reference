# Frontend Interview — High Frequency Questions

> Distilled from real interview reports (Glassdoor, Blind, LeetCode discuss, GitHub repos, GreatFrontEnd, NamasteDev, Leetcode), FAANG/MAANG experiences, and what shows up repeatedly across companies at all levels.

**Legend:**
- 🔴 **MUST KNOW** — Asked in almost every frontend interview across all companies & levels. If you miss these, you likely fail.
- 🟠 **VERY LIKELY** — Asked at mid-level+ and at most product companies (Flipkart, Swiggy, Atlassian, Microsoft, Amazon, etc.)
- 🟡 **LIKELY** — Comes up at senior levels or at companies like Google, Meta, Uber, Stripe.

---

## JAVASCRIPT CONCEPTUAL

| # | Question | Frequency |
|---|---|---|
| 1 | Explain **closures** with a real-world use case | 🔴 |
| 2 | **Event loop** — call stack, task queue, microtask queue, execution order | 🔴 |
| 3 | `var` vs `let` vs `const` — scope, hoisting, TDZ | 🔴 |
| 4 | `this` keyword — what does it refer to in arrow fn vs regular fn vs class method vs event handler | 🔴 |
| 5 | `call`, `apply`, `bind` — difference with examples | 🔴 |
| 6 | Hoisting — how does it work for `var`, `let/const`, and function declarations | 🔴 |
| 7 | Prototypal inheritance and prototype chain | 🔴 |
| 8 | What is a **Promise**? Explain the 3 states. | 🔴 |
| 9 | `==` vs `===` — type coercion examples | 🔴 |
| 10 | Deep copy vs shallow copy — how to implement each | 🔴 |
| 11 | Explain `async/await` — how it works under the hood | 🔴 |
| 12 | `Promise.all` vs `Promise.allSettled` vs `Promise.race` vs `Promise.any` | 🔴 |
| 13 | What is **currying**? Implement `curry(fn)` | 🔴 |
| 14 | What is **memoization**? Implement `memoize(fn)` | 🔴 |
| 15 | Explain the difference between `null` and `undefined` | 🔴 |
| 16 | What is the **temporal dead zone**? | 🔴 |
| 17 | What are **higher-order functions**? Give 3 examples. | 🔴 |
| 18 | What is **event delegation**? Why use it? | 🔴 |
| 19 | What is **debounce**? What is **throttle**? When to use each? | 🔴 |
| 20 | What are **generators** (`function*`)? What is `yield`? | 🟠 |
| 21 | What is `typeof null`? Why? | 🟠 |
| 22 | `Map` vs `Object` — when to use which? | 🟠 |
| 23 | `WeakMap` vs `Map` — garbage collection difference | 🟠 |
| 24 | What is the module system? CommonJS vs ES Modules | 🟠 |
| 25 | What is **tree shaking**? How does it work? | 🟠 |
| 26 | What is **function composition**? Implement `compose` and `pipe` | 🟠 |
| 27 | What causes **memory leaks** in JavaScript? List common causes. | 🟠 |
| 28 | What is `Object.freeze` vs `Object.seal`? | 🟠 |
| 29 | What are **symbols**? What are they used for? | 🟡 |
| 30 | What is `structuredClone()`? | 🟡 |

---

## JAVASCRIPT — OUTPUT-BASED (Almost always asked)

| # | Snippet | What They're Testing | Frequency |
|---|---|---|---|
| 1 | `for (var i=0; i<3; i++) { setTimeout(() => console.log(i), 0) }` | Closure + var scope + event loop | 🔴 |
| 2 | `console.log(1); setTimeout(()=>log(2),0); Promise.resolve().then(()=>log(3)); console.log(4)` | Event loop microtask vs macrotask order | 🔴 |
| 3 | `'5' + 3`, `'5' - 3`, `'5' * '3'`, `true + true` | Type coercion | 🔴 |
| 4 | `typeof typeof 1` | `typeof` of a string → `"string"` | 🟠 |
| 5 | `console.log(0.1 + 0.2 === 0.3)` | Floating point precision | 🟠 |
| 6 | `[1,2,3].map(parseInt)` → `[1, NaN, NaN]` | `parseInt` radix + `map` index arg | 🔴 |
| 7 | Hoisting quiz with `var foo = fn` and `function foo(){}` | Hoisting priority | 🟠 |
| 8 | `null == undefined` vs `null === undefined` | Loose vs strict equality | 🟠 |
| 9 | `[] + []`, `[] + {}`, `{} + []` | Coercion with arrays/objects | 🟠 |
| 10 | async/await execution order with multiple awaits and `console.log` | async/await + event loop | 🔴 |
| 11 | Stale closure in `useEffect` (React context) | Closure capture in async | 🔴 |
| 12 | `!!'false'`, `!!null`, `!!0`, `!!''`, `!!-1` | Truthiness/falsy values | 🟠 |

---

## JAVASCRIPT — POLYFILLS / IMPLEMENTATIONS

These are the most frequently asked "code it from scratch" questions. Sorted by frequency:

| # | Question | Frequency |
|---|---|---|
| 1 | Implement **`debounce`** | 🔴 |
| 2 | Implement **`throttle`** | 🔴 |
| 3 | Implement **`Function.prototype.bind`** | 🔴 |
| 4 | Implement **`Promise.all`** | 🔴 |
| 5 | Implement **`Array.prototype.map`** | 🔴 |
| 6 | Implement **`Array.prototype.filter`** | 🔴 |
| 7 | Implement **`Array.prototype.reduce`** | 🔴 |
| 8 | Implement **`deep clone`** (handle nested objects, arrays, no circular refs first) | 🔴 |
| 9 | Implement **`curry`** | 🔴 |
| 10 | Implement **`memoize`** | 🔴 |
| 11 | Implement **`EventEmitter`** (on, off, emit, once) | 🔴 |
| 12 | Implement **`Promise`** from scratch (basic) | 🟠 |
| 13 | Implement **`Promise.allSettled`** | 🟠 |
| 14 | Implement **`Promise.race`** | 🟠 |
| 15 | Implement **`Function.prototype.call`** and **`apply`** | 🟠 |
| 16 | Implement **`flatten`** array to depth n | 🟠 |
| 17 | Implement **`deep equal`** (compare two objects) | 🟠 |
| 18 | Implement **`once`** (function executes only once) | 🟠 |
| 19 | Implement **`pipe`** / **`compose`** | 🟠 |
| 20 | Implement **`LRU Cache`** | 🟠 |
| 21 | Implement **`Object.assign`** | 🟠 |
| 22 | Implement **`setInterval`** using `setTimeout` | 🟠 |
| 23 | Implement **`Array.prototype.flat`** | 🟠 |
| 24 | Implement **`Promise.any`** | 🟡 |
| 25 | Implement **`JSON.stringify`** (basic) | 🟡 |
| 26 | Implement **`getElementsByClassName`** (DOM traversal) | 🟡 |
| 27 | Implement **`classNames`** utility | 🟡 |
| 28 | Implement **async retry with exponential backoff** | 🟡 |
| 29 | Implement **`get`** (lodash-style `_.get` with dot-notation path) | 🟡 |
| 30 | Implement **`chunk`** (split array into groups of n) | 🟡 |

---

## ASYNC JAVASCRIPT

| # | Question | Frequency |
|---|---|---|
| 1 | What is the event loop? Explain microtasks vs macrotasks. | 🔴 |
| 2 | Difference between `Promise.all`, `allSettled`, `race`, `any` | 🔴 |
| 3 | How does `async/await` work internally? | 🔴 |
| 4 | How do you run N async tasks in **parallel** vs **sequentially**? | 🔴 |
| 5 | How do you limit **concurrent requests** to N at a time? | 🟠 |
| 6 | How do you **cancel a fetch** request? (`AbortController`) | 🟠 |
| 7 | What happens if you `await` a non-Promise value? | 🟠 |
| 8 | Implement async retry with backoff | 🟡 |
| 9 | What is top-level `await`? | 🟡 |

---

## CSS

| # | Question | Frequency |
|---|---|---|
| 1 | Explain the **CSS box model**. `content-box` vs `border-box`. | 🔴 |
| 2 | **Flexbox** — all properties, main axis vs cross axis | 🔴 |
| 3 | **CSS Grid** — difference from Flexbox, when to use each | 🔴 |
| 4 | How to center a div **5 different ways** | 🔴 |
| 5 | **CSS specificity** — how is it calculated? | 🔴 |
| 6 | `position: relative` vs `absolute` vs `fixed` vs `sticky` | 🔴 |
| 7 | What is a **stacking context**? What creates one? | 🔴 |
| 8 | `display: none` vs `visibility: hidden` vs `opacity: 0` | 🔴 |
| 9 | What is **margin collapsing**? | 🟠 |
| 10 | `em` vs `rem` vs `px` vs `vw/vh` vs `%` | 🟠 |
| 11 | How do you implement **dark mode** with CSS variables? | 🟠 |
| 12 | What is **CSS custom properties** (variables)? How do they cascade? | 🟠 |
| 13 | What is `will-change`? When should you use it? | 🟠 |
| 14 | What is the difference between `transition` and `animation`? | 🟠 |
| 15 | How do CSS `transform` and `opacity` differ from other animated properties (compositor layer)? | 🟠 |
| 16 | What is `z-index` and why doesn't it work on `position: static`? | 🟠 |
| 17 | Responsive design — mobile-first with `min-width` media queries | 🟠 |
| 18 | `clamp()` for fluid typography | 🟡 |
| 19 | CSS `@layer` — what problem does it solve? | 🟡 |
| 20 | Container queries vs media queries | 🟡 |

---

## HTML

| # | Question | Frequency |
|---|---|---|
| 1 | `<script>` vs `<script async>` vs `<script defer>` | 🔴 |
| 2 | Semantic HTML — `<section>` vs `<article>` vs `<div>` | 🔴 |
| 3 | Accessible form labels and error messages | 🔴 |
| 4 | `<button>` vs `<a>` — when to use each | 🔴 |
| 5 | ARIA roles — what are they and when to use? | 🟠 |
| 6 | `alt` attribute — when should it be empty? | 🟠 |
| 7 | `srcset` and `sizes` on `<img>` | 🟠 |
| 8 | What is the shadow DOM? | 🟡 |
| 9 | What are Web Components? | 🟡 |

---

## REACT — CONCEPTUAL

| # | Question | Frequency |
|---|---|---|
| 1 | What is the **Virtual DOM**? How does reconciliation work? | 🔴 |
| 2 | `useState` — batching, functional updates, lazy initialization | 🔴 |
| 3 | `useEffect` — dependency array rules, cleanup, when it runs | 🔴 |
| 4 | `useMemo` vs `useCallback` — difference and when to actually use them | 🔴 |
| 5 | `useRef` — 3+ use cases beyond just DOM access | 🔴 |
| 6 | Controlled vs uncontrolled components | 🔴 |
| 7 | When does a React component re-render? How do you prevent unnecessary renders? | 🔴 |
| 8 | `React.memo` — when does it help, when does it not? | 🔴 |
| 9 | What is **prop drilling** and how do you avoid it? | 🔴 |
| 10 | `useReducer` vs `useState` — when to switch? | 🔴 |
| 11 | What is `useLayoutEffect`? How does it differ from `useEffect`? | 🟠 |
| 12 | What is React **Fiber**? What problem does it solve? | 🟠 |
| 13 | What are the **rules of hooks**? Why do they exist? | 🔴 |
| 14 | What is **React.lazy** and **Suspense**? | 🟠 |
| 15 | What is an **Error Boundary**? How do you implement one? | 🟠 |
| 16 | HOC vs Render Props vs Custom Hooks — compare | 🟠 |
| 17 | What is **Context API**? Performance implications? | 🟠 |
| 18 | Context API vs Redux vs Zustand — when to use which? | 🟠 |
| 19 | What are compound components? | 🟡 |
| 20 | `key` prop — why is it important? The "reset trick" with `key`. | 🔴 |
| 21 | What is React 18 **automatic batching**? | 🟠 |
| 22 | `useTransition` vs `useDeferredValue` — when to use each | 🟠 |
| 23 | What are **React Server Components**? | 🟡 |
| 24 | Stale closure in `useEffect` — what causes it and how to fix | 🔴 |
| 25 | How does `useEffect` cleanup work? Common mistakes. | 🔴 |

---

## REACT — CODING (Live Coding / Machine Coding)

| # | Question | Frequency |
|---|---|---|
| 1 | Build a **Todo App** (CRUD + filter + localStorage) | 🔴 |
| 2 | Build a **Search with Debouncing** + API fetch | 🔴 |
| 3 | Implement **`useFetch`** custom hook (loading/error/data) | 🔴 |
| 4 | Implement **`useDebounce`** hook | 🔴 |
| 5 | Fix a component with a **stale closure** inside `useEffect` | 🔴 |
| 6 | Fix a component that **infinite re-renders** | 🔴 |
| 7 | Build a **controlled form** with validation | 🟠 |
| 8 | Build an **Accordion** (single/multi open) | 🟠 |
| 9 | Build a **Modal** with focus trap + close on Escape | 🟠 |
| 10 | Implement **Infinite Scroll** with IntersectionObserver | 🟠 |
| 11 | Build a **Star Rating** component | 🟠 |
| 12 | Build **Tabs** with lazy content | 🟠 |
| 13 | Build a **Shopping Cart** with quantity/total | 🟠 |
| 14 | Build a **multi-step form wizard** | 🟠 |
| 15 | Build a **Typeahead/Autocomplete** with keyboard nav | 🟠 |
| 16 | Implement **`useLocalStorage`** hook | 🟡 |
| 17 | Implement **`usePrevious`** hook | 🟡 |
| 18 | Implement **`useClickOutside`** hook | 🟡 |
| 19 | Build a **recursive comment tree** | 🟡 |
| 20 | Build a **drag-and-drop list** (without libraries) | 🟡 |

---

## MACHINE CODING ROUND — Most Frequently Asked

| # | Component | Frequency | Notes |
|---|---|---|---|
| 1 | **Todo App** | 🔴 | Absolute classic. CRUD, filter, persist. |
| 2 | **Search with debounce + API** | 🔴 | Tests debounce, fetch, loading state |
| 3 | **Infinite Scroll** | 🔴 | IntersectionObserver, pagination logic |
| 4 | **Modal / Dialog** | 🔴 | Focus trap, backdrop, keyboard close |
| 5 | **Accordion / FAQ** | 🔴 | Smooth toggle, single vs multi open |
| 6 | **Tabs** | 🔴 | Active state, lazy load, accessibility |
| 7 | **Carousel / Image Slider** | 🔴 | Prev/next, dots, autoplay, pause on hover |
| 8 | **Form with Validation** | 🔴 | Controlled, error messages, submit |
| 9 | **Star Rating** | 🟠 | Hover preview, fractional stars |
| 10 | **Toast Notification** | 🟠 | Queue, auto-dismiss, types |
| 11 | **Typeahead / Autocomplete** | 🟠 | Debounce, keyboard nav, highlight |
| 12 | **Stopwatch / Timer** | 🟠 | Start/stop/reset, lap times |
| 13 | **Progress Bar** | 🟠 | Animated, determinate/indeterminate |
| 14 | **OTP Input** | 🟠 | Auto-advance, paste, backspace nav |
| 15 | **Tag Input** | 🟠 | Add/remove chips, no duplicates |
| 16 | **Shopping Cart** | 🟠 | Quantity, remove, total calculation |
| 17 | **File Upload** | 🟡 | Drag-and-drop, progress, cancel |
| 18 | **Virtual Scroll / List** | 🟡 | Render only visible rows — 10k items |
| 19 | **Kanban Board** | 🟡 | Columns + drag cards between columns |
| 20 | **C-shape Box Clicker** | 🟡 | Grid, click → green, auto-revert in order |
| 21 | **Tree View** | 🟡 | Expand/collapse nested nodes |
| 22 | **Data Table** | 🟡 | Sort, filter, pagination, row select |

---

## BROWSER INTERNALS & WEB APIs

| # | Question | Frequency |
|---|---|---|
| 1 | What is the **Critical Rendering Path**? | 🔴 |
| 2 | What causes **reflow** vs **repaint**? | 🔴 |
| 3 | What is **CORS**? How does the preflight work? | 🔴 |
| 4 | `localStorage` vs `sessionStorage` vs `cookies` | 🔴 |
| 5 | What is a **Service Worker**? Its lifecycle? | 🟠 |
| 6 | `http/1.1` vs `http/2` vs `http/3` — key differences | 🟠 |
| 7 | What is **WebSocket** vs HTTP polling vs SSE? | 🟠 |
| 8 | What is `AbortController`? How do you cancel a fetch? | 🟠 |
| 9 | What is the `IntersectionObserver` API? | 🟠 |
| 10 | What are `HttpOnly` and `Secure` cookie flags? | 🟠 |
| 11 | What is `SameSite` cookie attribute? | 🟡 |

---

## PERFORMANCE & WEB VITALS

| # | Question | Frequency |
|---|---|---|
| 1 | What are **Core Web Vitals**? (LCP, CLS, INP, FCP, TTFB) | 🔴 |
| 2 | How do you optimize **LCP**? | 🔴 |
| 3 | How do you fix **CLS**? | 🔴 |
| 4 | What is **code splitting**? How to implement in React? | 🔴 |
| 5 | What is **lazy loading**? (`loading="lazy"`, `React.lazy`) | 🔴 |
| 6 | `<link rel="preload">` vs `prefetch` vs `preconnect` | 🟠 |
| 7 | What is **tree shaking** and when does it fail? | 🟠 |
| 8 | How do you reduce **bundle size**? | 🟠 |
| 9 | What is `font-display: swap`? | 🟠 |
| 10 | What is a **CDN** and how does edge caching work? | 🟠 |

---

## SECURITY

| # | Question | Frequency |
|---|---|---|
| 1 | What is **XSS**? How does React protect against it? | 🔴 |
| 2 | What is **CSRF**? How do you prevent it? | 🔴 |
| 3 | What is **CSP**? What does a basic header look like? | 🟠 |
| 4 | `localStorage` vs `HttpOnly cookie` for token storage — trade-offs | 🔴 |
| 5 | What is **JWT**? How does it work? What are its risks? | 🟠 |
| 6 | What is **Clickjacking**? How do you prevent it? | 🟡 |

---

## TYPESCRIPT

| # | Question | Frequency |
|---|---|---|
| 1 | `any` vs `unknown` vs `never` | 🔴 |
| 2 | `interface` vs `type` — when to use each | 🔴 |
| 3 | **Generics** — write a generic function | 🔴 |
| 4 | Union types (`A \| B`) vs intersection types (`A & B`) | 🔴 |
| 5 | Utility types: `Partial`, `Pick`, `Omit`, `Record`, `ReturnType` | 🔴 |
| 6 | What is **type narrowing**? | 🟠 |
| 7 | What is a **discriminated union**? | 🟠 |
| 8 | What is `keyof` and `typeof`? | 🟠 |
| 9 | What is a **mapped type**? | 🟡 |
| 10 | What is `infer` in TypeScript? | 🟡 |

---

## FRONTEND SYSTEM DESIGN — Most Asked Topics

| # | Design Question | Frequency |
|---|---|---|
| 1 | Design an **Autocomplete Search** component | 🔴 |
| 2 | Design a **News Feed** (like Facebook/Twitter) | 🔴 |
| 3 | Design a **Chat Application** (WhatsApp Web) | 🔴 |
| 4 | Design an **E-commerce Product Listing Page** | 🟠 |
| 5 | Design a **Notification System** | 🟠 |
| 6 | Design a **Design System / Component Library** | 🟠 |
| 7 | Design a **Video Player** (YouTube) | 🟠 |
| 8 | Design a **Google Docs** collaborative editor | 🟡 |
| 9 | Design a **Dashboard with real-time data** | 🟡 |
| 10 | Design a **Micro-frontend architecture** | 🟡 |

**System design concepts almost always probed:**
- State management architecture for large apps
- Client-side caching strategies
- Real-time (WebSocket vs SSE vs polling)
- Rendering strategy choice (SSR/CSR/SSG/ISR)
- Error handling, loading states, skeleton screens
- Offline support (PWA / service workers)
- Authentication flows

---

## TESTING

| # | Question | Frequency |
|---|---|---|
| 1 | Unit vs Integration vs E2E tests — when to use each | 🟠 |
| 2 | What is React Testing Library's philosophy? | 🟠 |
| 3 | `getBy` vs `queryBy` vs `findBy` | 🟠 |
| 4 | How do you test a component that fetches data? (MSW) | 🟠 |
| 5 | What is Cypress / Playwright? | 🟡 |

---

## ACCESSIBILITY

| # | Question | Frequency |
|---|---|---|
| 1 | What is WCAG? POUR principles. | 🟠 |
| 2 | How do you implement keyboard navigation in a custom dropdown? | 🟠 |
| 3 | What is a **focus trap** and when do you need one? | 🟠 |
| 4 | `aria-live` regions — `polite` vs `assertive` | 🟡 |
| 5 | `aria-hidden="true"` vs `display: none` for screen readers | 🟡 |

---

## BUILD TOOLS

| # | Question | Frequency |
|---|---|---|
| 1 | What is **Webpack**? Loader vs Plugin? | 🟠 |
| 2 | Why is **Vite** faster than Webpack in dev? | 🟠 |
| 3 | What is **Babel** and what does it do? | 🟠 |
| 4 | What is **HMR** (Hot Module Replacement)? | 🟠 |
| 5 | What is **source maps**? | 🟡 |

---

## THE ABSOLUTE MUST-KNOW LIST (Prepare These First)

If you only had 2 weeks to prepare, these are the highest-ROI topics:

### Week 1 — Core JS + Output + Polyfills
1. Closures (concept + output + loop trap)
2. Event loop (concept + output question)
3. `var/let/const` + hoisting + TDZ
4. `this` in all contexts + `call/apply/bind`
5. Promises + async/await + event loop order
6. `Promise.all/allSettled/race/any`
7. Implement: `debounce`, `throttle`, `bind`, `Promise.all`, `map`, `filter`, `reduce`, `curry`, `memoize`, `EventEmitter`, `deep clone`
8. Type coercion output questions
9. `[1,2,3].map(parseInt)` classic trap
10. Prototypal inheritance

### Week 2 — React + CSS + Machine Coding
1. Virtual DOM + reconciliation
2. All hooks — `useState`, `useEffect`, `useMemo`, `useCallback`, `useRef`, `useReducer`, `useContext`, `useLayoutEffect`
3. Stale closure + infinite re-render bugs
4. `React.memo` — real conditions for it to work
5. CSS Flexbox + Grid (center a div 5 ways)
6. Specificity + stacking context + `position`
7. Machine code: TodoApp, Search with debounce, Modal, Accordion, Infinite Scroll
8. Custom hooks: `useFetch`, `useDebounce`
9. CORS + XSS + CSRF (security basics)
10. Core Web Vitals + `preload/prefetch/lazy`
