# React.js Interview Questions — Situational / Real-World Scenarios

A consolidated, deduplicated collection of **situational and real-time scenario-based React.js interview questions** — the kind asked to gauge how a candidate handles production issues, architecture trade-offs, and decisions on real projects — organized section-wise.

**Total unique questions: 69**

## Table of Contents

- [Components, Props & State](#components-props-state) (1)
  - [1. How would you design a controlled component pattern for a reusable component library?](#1-how-would-you-design-a-controlled-component-pattern-for-a-reusable-component-library)
- [Rendering, Reconciliation & Lifecycle](#rendering-reconciliation-lifecycle) (3)
  - [2. Design a simple virtual DOM diffing algorithm.](#2-design-a-simple-virtual-dom-diffing-algorithm)
  - [3. How does React Fiber architecture change rendering?](#3-how-does-react-fiber-architecture-change-rendering)
  - [4. React Fiber Architecture?](#4-react-fiber-architecture)
- [Hooks (Core & Advanced)](#hooks-core-advanced) (18)
  - [5. Design a real-time chat UI in React.](#5-design-a-real-time-chat-ui-in-react)
  - [6. How do you approach migrating a large class-component codebase to Hooks incrementally without a risky big-bang rewrite?](#6-how-do-you-approach-migrating-a-large-class-component-codebase-to-hooks-incrementally-without-a-risky-big-bang-rewrite)
  - [7. How do you handle a memory leak from a subscription in a component?](#7-how-do-you-handle-a-memory-leak-from-a-subscription-in-a-component)
  - [8. How do you handle cleanup in useEffect?](#8-how-do-you-handle-cleanup-in-useeffect)
  - [9. How do you handle feature flags cleanly in a React codebase?](#9-how-do-you-handle-feature-flags-cleanly-in-a-react-codebase)
  - [10. How do you pass parent data to a deeply nested child (e.g., 5th child)?](#10-how-do-you-pass-parent-data-to-a-deeply-nested-child-eg-5th-child)
  - [11. How do you structure a large-scale React application across multiple teams?](#11-how-do-you-structure-a-large-scale-react-application-across-multiple-teams)
  - [12. How would you architect a React app for a team of 20 developers?](#12-how-would-you-architect-a-react-app-for-a-team-of-20-developers)
  - [13. How would you build a custom hook library?](#13-how-would-you-build-a-custom-hook-library)
  - [14. How would you design component structure for scalability in a production-level app?](#14-how-would-you-design-component-structure-for-scalability-in-a-production-level-app)
  - [15. How would you implement internationalization (i18n) in React?](#15-how-would-you-implement-internationalization-i18n-in-react)
  - [16. How would you migrate a large class-based codebase to hooks?](#16-how-would-you-migrate-a-large-class-based-codebase-to-hooks)
  - [17. How would you structure a large-scale React application?](#17-how-would-you-structure-a-large-scale-react-application)
  - [18. Situation & Scenario?](#18-situation-scenario)
  - [19. Situation: `useEffect` runs infinitely – what's wrong?](#19-situation-useeffect-runs-infinitely-whats-wrong)
  - [20. Situation: A search input lags as user types -- how do you fix it?](#20-situation-a-search-input-lags-as-user-types-how-do-you-fix-it)
  - [21. Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?](#21-situation-you-need-to-keep-the-ui-responsive-during-a-heavy-filter-operation-on-10k-items-how)
  - [22. UseReducer vs useState for complex state?](#22-usereducer-vs-usestate-for-complex-state)
- [Performance Optimization](#performance-optimization) (8)
  - [23. A React app's bundle size is unexpectedly large. How do you investigate?](#23-a-react-apps-bundle-size-is-unexpectedly-large-how-do-you-investigate)
  - [24. How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)](#24-how-do-you-debug-a-performance-bottleneck-in-a-react-app-using-devtools-profiler-performance-tab)
  - [25. How do you detect and prevent memory leaks in long-running SPAs?](#25-how-do-you-detect-and-prevent-memory-leaks-in-long-running-spas)
  - [26. How would you debug a component re-rendering far more than expected?](#26-how-would-you-debug-a-component-re-rendering-far-more-than-expected)
  - [27. In a large-scale application, components are re-rendering unnecessarily — how would you identify and fix performance issues?](#27-in-a-large-scale-application-components-are-re-rendering-unnecessarily-how-would-you-identify-and-fix-performance-issues)
  - [28. Situation: Context is causing performance issues in a large app – what do you do?](#28-situation-context-is-causing-performance-issues-in-a-large-app-what-do-you-do)
  - [29. Situation: The app is slow on mobile – how do you diagnose and fix it?](#29-situation-the-app-is-slow-on-mobile-how-do-you-diagnose-and-fix-it)
  - [30. You are building a real-time dashboard --- how would you manage frequent state updates without affecting performance?](#30-you-are-building-a-real-time-dashboard-how-would-you-manage-frequent-state-updates-without-affecting-performance)
- [Context API & State Management (Redux/Zustand/MobX)](#context-api-state-management-reduxzustandmobx) (9)
  - [31. Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).](#31-compare-redux-mobx-and-recoil-for-enterprise-scale-state-management-pros-and-cons)
  - [32. Design a Posts with Comments system – how do you manage deeply nested data?](#32-design-a-posts-with-comments-system-how-do-you-manage-deeply-nested-data)
  - [33. How would you design a state management solution for a complex analytics/dashboard app?](#33-how-would-you-design-a-state-management-solution-for-a-complex-analyticsdashboard-app)
  - [34. How would you handle multiple dependent API calls using Redux Thunk or Saga in a real-world scenario?](#34-how-would-you-handle-multiple-dependent-api-calls-using-redux-thunk-or-saga-in-a-real-world-scenario)
  - [35. If Redux is causing too many re-renders, how would you optimize it?](#35-if-redux-is-causing-too-many-re-renders-how-would-you-optimize-it)
  - [36. In a complex application, state is becoming hard to manage — how would you restructure your Redux store?](#36-in-a-complex-application-state-is-becoming-hard-to-manage-how-would-you-restructure-your-redux-store)
  - [37. Redux vs Context API vs Zustand – how do you decide in a large-scale application?](#37-redux-vs-context-api-vs-zustand-how-do-you-decide-in-a-large-scale-application)
  - [38. Situation: Two components on different branches need the same data – what do you do?](#38-situation-two-components-on-different-branches-need-the-same-data-what-do-you-do)
  - [39. What is the difference between Redux, Context, and Zustand for large-scale apps?](#39-what-is-the-difference-between-redux-context-and-zustand-for-large-scale-apps)
- [Routing & Navigation](#routing-navigation) (1)
  - [40. How do you handle 404s in React Router?](#40-how-do-you-handle-404s-in-react-router)
- [Data Fetching & React Query/Suspense](#data-fetching-react-querysuspense) (5)
  - [41. Design an infinite scrolling feed.](#41-design-an-infinite-scrolling-feed)
  - [42. How do you decide between fetching data in a Server Component vs a Client Component with React Query?](#42-how-do-you-decide-between-fetching-data-in-a-server-component-vs-a-client-component-with-react-query)
  - [43. How do you ensure a React app performs well at 100k users?](#43-how-do-you-ensure-a-react-app-performs-well-at-100k-users)
  - [44. How would you implement infinite scroll?](#44-how-would-you-implement-infinite-scroll)
  - [45. Situation: API data is needed in multiple components – how do you avoid duplicate fetches?](#45-situation-api-data-is-needed-in-multiple-components-how-do-you-avoid-duplicate-fetches)
- [SSR, Next.js & Server Components](#ssr-nextjs-server-components) (5)
  - [46. A Server Component page in Next.js is suddenly much slower after a change. How do you debug?](#46-a-server-component-page-in-nextjs-is-suddenly-much-slower-after-a-change-how-do-you-debug)
  - [47. How would you design a migration strategy from a legacy jQuery app to modern React/Next.js?](#47-how-would-you-design-a-migration-strategy-from-a-legacy-jquery-app-to-modern-reactnextjs)
  - [48. How would you design SSR/SSG/hydration strategy for a React app?](#48-how-would-you-design-ssrssghydration-strategy-for-a-react-app)
  - [49. Poor SEO & Slow TTI: React app has poor SEO and slow TTI -- frontend-level solutions.](#49-poor-seo-slow-tti-react-app-has-poor-seo-and-slow-tti-frontend-level-solutions)
  - [50. What causes hydration mismatches and how do you fix them?](#50-what-causes-hydration-mismatches-and-how-do-you-fix-them)
- [Error Handling & Error Boundaries](#error-handling-error-boundaries) (3)
  - [51. A third-party component throws an error — how do you handle it?](#51-a-third-party-component-throws-an-error-how-do-you-handle-it)
  - [52. In which scenarios error boundaries do not catch errors?](#52-in-which-scenarios-error-boundaries-do-not-catch-errors)
  - [53. Situation: A third-party component throws -- how do you handle it?](#53-situation-a-third-party-component-throws-how-do-you-handle-it)
- [TypeScript with React](#typescript-with-react) (1)
  - [54. How would you design a design system in React?](#54-how-would-you-design-a-design-system-in-react)
- [Security & Accessibility](#security-accessibility) (1)
  - [55. How would you design a reusable component library for a large team?](#55-how-would-you-design-a-reusable-component-library-for-a-large-team)
- [React Ecosystem & Build Tools](#react-ecosystem-build-tools) (3)
  - [56. How do you debug a React Native app?](#56-how-do-you-debug-a-react-native-app)
  - [57. How to enable production mode in React?](#57-how-to-enable-production-mode-in-react)
  - [58. What is a CORS issue and how do you handle it?](#58-what-is-a-cors-issue-and-how-do-you-handle-it)
- [General / Miscellaneous React Concepts](#general-miscellaneous-react-concepts) (11)
  - [59. How do you handle conditional class names?](#59-how-do-you-handle-conditional-class-names)
  - [60. How do you handle dependent/sequential queries (query B needs query A's result)?](#60-how-do-you-handle-dependentsequential-queries-query-b-needs-query-as-result)
  - [61. How do you handle keyboard navigation in a custom component (e.g., a dropdown or menu)?](#61-how-do-you-handle-keyboard-navigation-in-a-custom-component-eg-a-dropdown-or-menu)
  - [62. How do you handle keyboard navigation in custom components?](#62-how-do-you-handle-keyboard-navigation-in-custom-components)
  - [63. How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue‑green deployments?](#63-how-would-you-design-a-cicd-pipeline-for-frontend-apps-with-staging-canary-and-bluegreen-deployments)
  - [64. How would you design a reusable, prop-explosion-resistant component (e.g., a Button or Modal)?](#64-how-would-you-design-a-reusable-prop-explosion-resistant-component-eg-a-button-or-modal)
  - [65. How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)](#65-how-would-you-handle-a-large-dataset-without-blocking-the-main-thread-web-workers-virtualization)
  - [66. How would you handle real-time updates in a React application efficiently?](#66-how-would-you-handle-real-time-updates-in-a-react-application-efficiently)
  - [67. Real-time Updates: How to handle real-time updates efficiently in React?](#67-real-time-updates-how-to-handle-real-time-updates-efficiently-in-react)
  - [68. Situation: A dropdown closes when you click inside it – what's likely wrong?](#68-situation-a-dropdown-closes-when-you-click-inside-it-whats-likely-wrong)
  - [69. What is source map generation, and why is it important in a production React deployment?](#69-what-is-source-map-generation-and-why-is-it-important-in-a-production-react-deployment)

---

## Components, Props & State

### 1. How would you design a controlled component pattern for a reusable component library?

Support *both* modes: the component manages its own internal state by default (uncontrolled/"autopilot"), but accepts optional `value`/`onChange` props to become fully parent-controlled when supplied — check `value !== undefined` to decide which mode is active.

[↑ Back to top](#table-of-contents)

## Rendering, Reconciliation & Lifecycle

### 2. Design a simple virtual DOM diffing algorithm.

Represent nodes as `{type, props, children}` objects. Diff function: if types differ, replace entirely. If same type, diff props — apply changed/removed/added props to the real DOM node. Recurse into children: use keys for stable matching; add/remove/patch as needed. Apply all changes in the commit phase after the full diff.

[↑ Back to top](#table-of-contents)

### 3. How does React Fiber architecture change rendering?

React Fiber (introduced in React 16) is a complete rewrite of the reconciliation engine. It enables **incremental rendering**, splitting work into chunks and prioritizing updates (e.g., user input over data fetching). Fiber makes React capable of:
- Pausing, aborting, or reusing work.
- Assigning priorities to different types of updates.
- Supporting concurrent rendering and Suspense.

[↑ Back to top](#table-of-contents)

### 4. React Fiber Architecture?

React’s core engine is called **Fiber**, introduced in React 16. Fiber is a reimplementation of the React reconciliation algorithm with the following capabilities:

*   Breaks rendering work into **units of work** (fiber nodes).
*   Enables **interruptible rendering** (important for responsiveness).
*   Supports **priority scheduling** and **concurrent rendering**.

Each Fiber node represents a component and stores:

*   The component type (function/class).
*   Props, state, and effects.
*   Links to parent, child, and sibling fibers.

[↑ Back to top](#table-of-contents)

## Hooks (Core & Advanced)

### 5. Design a real-time chat UI in React.

WebSocket for live messages. `useEffect` to subscribe/unsubscribe. Messages in `useState` or `useReducer`. Virtualized message list for performance. Optimistic updates when sending. Error boundary for connection failures. Reconnect logic in a custom hook.

[↑ Back to top](#table-of-contents)

### 6. How do you approach migrating a large class-component codebase to Hooks incrementally without a risky big-bang rewrite?

Migrate leaf/simple components first (lowest risk, easiest to verify), convert shared logic into custom Hooks usable by both old and new components during the transition, and keep Error Boundaries (still class-only) as a stable exception rather than forcing their conversion.

[↑ Back to top](#table-of-contents)

### 7. How do you handle a memory leak from a subscription in a component?

Most commonly a missing `useEffect` cleanup; always return an unsubscribe/clear function, watch for "state update on unmounted component" warnings.

[↑ Back to top](#table-of-contents)

### 8. How do you handle cleanup in useEffect?

The cleanup function in `useEffect` is used to **clean up side effects** before the component unmounts or before the effect runs again. This prevents memory leaks, stale data, and unexpected behavior.

##### Syntax

```js
useEffect(() => {
// Setup code

return () => {
// Cleanup code
};
}, [dependencies]);
```

##### Common Cleanup Scenarios

[↑ Back to top](#table-of-contents)

### 9. How do you handle feature flags cleanly in a React codebase?

Wrap checks in a Hook/component abstraction backed by a flag SDK, keeping logic swappable and dead flags easy to find and remove later.

[↑ Back to top](#table-of-contents)

### 10. How do you pass parent data to a deeply nested child (e.g., 5th child)?

Using **Context** is the most common approach. Create a context, wrap the parent tree with a `Provider`, and consume the context in the deeply nested child via `useContext` or `Context.Consumer`. Alternatively, use a state management library like Redux that provides global state.

[↑ Back to top](#table-of-contents)

### 11. How do you structure a large-scale React application across multiple teams?

**Structure**: - **Monorepo** (e.g., Nx, Turborepo) with packages for
shared UI, utils, hooks. - **Feature‑based folder structure** (e.g.,
`features/auth`, `features/dashboard`). Each feature contains its own
components, logic, tests. - **Shared libraries**: UI components, API
clients, types, constants. - **Routing**: Central routing with lazy
loading of features. - **State management**: Use a global store (Redux)
for shared state; feature‑local state where possible. - **Team
autonomy**: Teams own their features; they can release independently
with Module Federation or versioned packages. - **Code review and
standards**: ESLint, Prettier, TypeScript strict.

[↑ Back to top](#table-of-contents)

### 12. How would you architect a React app for a team of 20 developers?

Feature-based structure with enforced module boundaries (ESLint import rules or Nx); a shared, Storybook-documented component library; TypeScript everywhere; an agreed state strategy (React Query for server state, Zustand/RTK for client global state); ESLint + Prettier + pre-commit hooks (husky); CI running tests/type-checks/lint on every PR.

[↑ Back to top](#table-of-contents)

### 13. How would you build a custom hook library?

A custom hook library is a collection of reusable hooks. Steps: 1.
Design hooks with clear APIs, handling edge cases. 2. Write them as pure
functions that follow the Rules of Hooks. 3. Document with examples and
TypeScript types. 4. Publish to npm or a private registry. 5. Include
tests (React Testing Library) and ensure they work across versions.

[↑ Back to top](#table-of-contents)

### 14. How would you design component structure for scalability in a production-level app?

Scalable structure follows separation of concerns, reusability, and
clear boundaries.

-   **Folder by feature/module** (not by file type). Example:

src/
features/
dashboard/
components/
hooks/
api/
types/
profile/
...
shared/
ui/          # reusable presentational components
lib/         # utilities
hooks/       # shared hooks
app/           # routing, global providers

-   **Component design:**

-   **Presentational components:** Receive data via props, no
business logic. Easy to test and reuse.
-   **Container components / hooks:** Encapsulate logic, data
fetching, and state. Use custom hooks to share logic across
components.

-   **State management:** Use local state first, lift when needed. Use
context for themes/user, but avoid overusing it for high‑frequency
updates.

-   **Code splitting:** Use `React.lazy` for routes and large
components.

-   **Type safety:** TypeScript with strict mode catches many errors
early.

-   **Consistent naming and patterns:** Document and enforce (e.g.,
feature components export default, shared components named exports).

[↑ Back to top](#table-of-contents)

### 15. How would you implement internationalization (i18n) in React?

`react-intl` or `react-i18next`. Extract all strings to message
catalogs. `useIntl()` hook for formatting. Support RTL layouts
(`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies
via Intl API. Lazy load language bundles.

[↑ Back to top](#table-of-contents)

### 16. How would you migrate a large class-based codebase to hooks?

Incrementally – convert leaf components first, then move up. Map lifecycle methods to `useEffect` patterns. Extract shared logic to custom hooks. Maintain tests throughout. Use codemods for mechanical transforms. Don't big-bang rewrite.

[↑ Back to top](#table-of-contents)

### 17. How would you structure a large-scale React application?

Feature-based folder structure: src/features/auth/,
src/features/dashboard/ etc. Each feature contains: components/, hooks/,
slices/, api/, types/. Shared: src/components/ui/ (design system),
src/hooks/ (shared hooks), src/utils/, src/api/ (base client). Key
decisions: (1) Route-level code splitting for each feature. (2) Barrel
exports (index.ts) for clean imports. (3) Absolute imports configured
with path aliases. (4) Strict TypeScript throughout. (5) Global state
only for truly global data --- prefer local state + context for feature
state.

[↑ Back to top](#table-of-contents)

### 18. Situation & Scenario?

**Problem:** Implement compound component pattern for a flexible Accordion.

```jsx
const AccordionContext = React.createContext();

function Accordion({ children, defaultOpen = null }) {
const [openItem, setOpenItem] = React.useState(defaultOpen);
const toggle = React.useCallback((id) =>
setOpenItem(prev => prev === id ? null : id), []);
const value = React.useMemo(() => ({ openItem, toggle }), [openItem, toggle]);

return (
<AccordionContext.Provider value={value}>
<div className="accordion">{children}</div>
</AccordionContext.Provider>
);
}

Accordion.Item = function AccordionItem({ id, children }) {
return <div className="accordion-item">{children}</div>;
};

Accordion.Header = function AccordionHeader({ id, children }) {
const { openItem, toggle } = React.useContext(AccordionContext);
return (
<button
onClick={() => toggle(id)}
aria-expanded={openItem === id}
>
{children}
<span>{openItem === id ? '▲' : '▼'}</span>
</button>
);
};

Accordion.Panel = function AccordionPanel({ id, children }) {
const { openItem } = React.useContext(AccordionContext);
if (openItem !== id) return null;
return <div role="region">{children}</div>;
};

// Usage — consumer has full compositional control:
function App() {
return (
<Accordion defaultOpen="item1">
<Accordion.Item id="item1">
<Accordion.Header id="item1">Section 1</Accordion.Header>
<Accordion.Panel id="item1">Content 1</Accordion.Panel>
</Accordion.Item>
<Accordion.Item id="item2">
<Accordion.Header id="item2">Section 2</Accordion.Header>
<Accordion.Panel id="item2">Content 2</Accordion.Panel>
</Accordion.Item>
</Accordion>
);
}
```

*400+ questions covering every output, situation, and scenario pattern asked in JS and React interviews.*

*Master these and you will crack 95%+ of output-based interview questions. 🚀*

[↑ Back to top](#table-of-contents)

### 19. Situation: `useEffect` runs infinitely – what's wrong?

Most likely a dependency that changes on every render: an object/array created inline (`{} !== {}` every render), or a function without `useCallback`. Fix: memoize the dependency, move it outside the component, or restructure state.

[↑ Back to top](#table-of-contents)

### 20. Situation: A search input lags as user types -- how do you fix it?

Separate the input state (urgent) from the search results state
(deferred). Use `useDeferredValue` or `useTransition` on the results
update. This lets the input remain responsive while results compute
asynchronously.

[↑ Back to top](#table-of-contents)

### 21. Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?

Store the raw list. Put the filter input update in urgent state. Wrap the filtered results computation in `useTransition` or `useDeferredValue`. React renders the input update immediately; filter results follow when resources free up.

[↑ Back to top](#table-of-contents)

### 22. UseReducer vs useState for complex state?

```jsx
function reducer(state, action) {
switch(action.type) {
case 'increment': return { ...state, count: state.count + 1 };
case 'decrement': return { ...state, count: state.count - 1 };
case 'reset': return { count: 0, step: state.step };
default: return state;
}
}

function App() {
const [state, dispatch] = React.useReducer(reducer, { count: 0, step: 2 });

return (
<>
<p>{state.count}</p>
<button onClick={() => dispatch({ type: 'increment' })}>+</button>
<button onClick={() => dispatch({ type: 'decrement' })}>-</button>
<button onClick={() => dispatch({ type: 'reset' })}>reset</button>
</>
);
}
```

**Behavior:** Works as a predictable state machine. `reset` resets count to `0` but preserves `step`. Each action is declarative and traceable.

**Explanation:** `useReducer` is preferred over multiple `useState` when: state has multiple sub-values that update together, next state depends on action type, or you want predictable, testable state transitions.

[↑ Back to top](#table-of-contents)

## Performance Optimization

### 23. A React app's bundle size is unexpectedly large. How do you investigate?

Bundle analyzer; check for importing whole libraries instead of specific functions; check duplicate dependency versions; identify code-splittable components; check for server-only code leaking into the client bundle.

[↑ Back to top](#table-of-contents)

### 24. How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)

**React DevTools Profiler**\
- Record a profile while interacting with the app. - The "Flamegraph"
view shows which components rendered and why. - Look for components that
re‑render frequently or take a long time. - Use the "Why did this
render?" option (with a custom hook or the `why‑did‑you‑render` library)
to identify prop changes.

**Browser Performance Tab (Chrome DevTools)**\
- Record a performance trace during the problematic interaction. - Look
for long tasks (yellow/red bars) and inspect the call stack. - Identify
whether the bottleneck is JavaScript (React render) or layout/paint
(CSS). - Use "Timings" to see where time is spent: script, render,
paint.

**Lighthouse / Web Vitals**\
- Run Lighthouse to get a high‑level score and suggestions. - Use the
"Performance" panel to measure Core Web Vitals (LCP, CLS, INP).

**Memory Tab**\
- If performance degrades over time, take heap snapshots to find memory
leaks.

[↑ Back to top](#table-of-contents)

### 25. How do you detect and prevent memory leaks in long-running SPAs?

**Detection**:
- Chrome DevTools Memory tab: Take heap snapshots before and after actions; look for retained objects.
- Use `performance.memory` (Chrome) to monitor heap size over time.
- Check for detached DOM elements (elements removed from DOM but still referenced in JS).

**Prevention**:
- Cleanup `setInterval`/`setTimeout` in `useEffect` cleanup.
- Remove event listeners in cleanup.
- Cancel fetch requests with `AbortController` on unmount.
- Use `WeakMap`/`WeakSet` for caches.
- Avoid storing large objects in closures that outlive their purpose.
- Profile with React DevTools to see if components are being unmounted properly.

[↑ Back to top](#table-of-contents)

### 26. How would you debug a component re-rendering far more than expected?

Profiler recording → check unstable prop references → check Context Provider value memoization → check effect/memo dependency arrays → consider state placement.

[↑ Back to top](#table-of-contents)

### 27. In a large-scale application, components are re-rendering unnecessarily — how would you identify and fix performance issues?

**Identification:**
- Use React DevTools Profiler to record interactions and see which components re‑rendered and why.
- Enable “Highlight updates” in DevTools to visually see re‑renders.
- Add `console.log` or `why‑did‑you-render` library to log unnecessary updates.
- Check for common anti‑patterns: passing new object/array literals as props, inline functions in render, or missing keys in lists.

**Fixing:**
- **Memoisation:** Wrap components with `React.memo` if they receive the same props frequently. Use `useMemo` for expensive computations and `useCallback` for functions passed to memoized children.
- **State localisation:** Move state down to the component that actually needs it, or use context selectively.
- **Avoid spreading props** that contain large objects unless necessary.
- **Stable references:** Ensure that objects/arrays passed as props are created only when their contents change (e.g., `useMemo(() => ({...}), [deps])`).
- **Code splitting:** Use `React.lazy` and Suspense to reduce initial render cost.

[↑ Back to top](#table-of-contents)

### 28. Situation: Context is causing performance issues in a large app – what do you do?

Split into multiple smaller contexts by concern. Memoize provider values. Move high-frequency state to a store with selectors (Zustand, Jotai). Use context only for rarely-changing values.

[↑ Back to top](#table-of-contents)

### 29. Situation: The app is slow on mobile – how do you diagnose and fix it?

Throttle CPU in DevTools to simulate mobile. Use Lighthouse for performance audit. Check bundle size (code split aggressively). Profile renders with React DevTools. Remove render-blocking JS. Lazy load images and offscreen components. Reduce animation complexity.

[↑ Back to top](#table-of-contents)

### 30. You are building a real-time dashboard --- how would you manage frequent state updates without affecting performance?

Frequent state updates (e.g., WebSocket streams) can cause excessive
re‑renders.

-   **Throttle / debounce:** If the data arrives faster than the UI
needs to update, use `throttle` (e.g., Lodash) to limit render
frequency. For charts, consider down‑sampling.
-   **Selective subscriptions:** Instead of storing all data in a single
global state, use component‑specific subscriptions. Libraries like
`zustand` or `valtio` allow granular updates.
-   **Use `useReducer` or `useRef` for non‑render state:** If a value
changes but shouldn't trigger a render, store it in a ref.
-   **Virtualisation:** For tables or lists that update frequently, use
`react‑window` to render only visible rows.
-   **Web Workers:** Offload data processing (aggregation, filtering) to
a worker so the main thread only handles rendering.
-   **Batched updates:** In React 18, automatic batching groups state
updates from different sources. Ensure you're using concurrent
features if needed.
-   **Immutability:** Always update state immutably; libraries like
Immer help maintain predictable updates.

[↑ Back to top](#table-of-contents)

## Context API & State Management (Redux/Zustand/MobX)

### 31. Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).

| | Redux | MobX | Recoil |
|---|-------|------|--------|
| **Paradigm** | Functional, immutable | Observable, mutable | Atomic, graph‑based |
| **Boilerplate** | High (reducers, actions) | Low (decorators, observables) | Moderate (atoms, selectors) |
| **Learning curve** | Steep | Moderate | Moderate |
| **Performance** | Good with selectors | Excellent (fine‑grained) | Good with derived state |
| **Tooling** | Excellent DevTools | Good | Good (early) |
| **Scalability** | Proven in huge apps | Good, but mutable may cause unpredictability | Newer, but promising |

- **Redux** is battle‑tested, great for large teams due to strict patterns, but requires discipline.
- **MobX** allows more flexibility and less code, but mutable updates can be error‑prone in large teams.
- **Recoil** offers a more React‑centric approach with derived state and concurrent rendering support, but is newer.

[↑ Back to top](#table-of-contents)

### 32. Design a Posts with Comments system – how do you manage deeply nested data?

**Requirements**: Display posts, each with comments, comments may have nested replies.

**Design**:
- **Data structure**: Use normalized state (e.g., entities for posts, users, comments). Store comments as map with parent references. Build tree on demand.
- **State management**: Redux Toolkit with `createEntityAdapter` for normalized data. Or use React Query for server state and local state for UI.
- **Rendering**: Recursive component for comment tree. Use memoization to avoid re‑renders on deep trees.
- **Optimistic updates**: When adding comment, update local state immediately, then sync with server.
- **Performance**: Use virtual scrolling for long comment threads.

[↑ Back to top](#table-of-contents)

### 33. How would you design a state management solution for a complex analytics/dashboard app?

For a dashboard app with:
- Real‑time data (WebSockets)
- Multiple widgets that can be individually refreshed
- Filters that affect many widgets
- Large datasets (need virtualization)

Approach:
1. Use Redux Toolkit for global state (filters, user settings, notifications).
2. Use `createEntityAdapter` for normalized data (e.g., metrics, widgets).
3. Use `createAsyncThunk` for API calls with cancellation support (AbortController).
4. For real‑time updates, use a custom middleware to listen to WebSocket messages and dispatch actions.
5. Use `useSelector` with memoized selectors (Reselect) to avoid re‑renders.
6. For widget‑specific state (e.g., expanded/collapsed), keep it locally in the widget component to avoid global re‑renders.
7. Leverage React.memo for widget components that receive stable props.
8. Use Suspense and lazy loading for heavy dashboard sections.

This combines the predictability of Redux with localized state for performance.

[↑ Back to top](#table-of-contents)

### 34. How would you handle multiple dependent API calls using Redux Thunk or Saga in a real-world scenario?

**With Redux Thunk:**
- For sequential dependencies: `async`/`await` inside a thunk.

```javascript
export const fetchUserAndPosts = (userId) => async (dispatch) => {
dispatch(fetchUserRequest());
const user = await api.getUser(userId);
dispatch(fetchUserSuccess(user));
const posts = await api.getPosts(userId);
dispatch(fetchPostsSuccess(posts));
};
```

- For parallel calls that both must complete before next step: `Promise.all`.
- Use `dispatch` to trigger other thunks; thunks can wait for each other.

**With Redux Saga:**
- Sagas excel at complex flows. Use `takeEvery` or `takeLatest` with `call`, `put`, `select`, and `all`.

```javascript
function* fetchUserAndPosts(action) {
try {
const user = yield call(api.getUser, action.payload.userId);
yield put(fetchUserSuccess(user));
const posts = yield call(api.getPosts, action.payload.userId);
yield put(fetchPostsSuccess(posts));
} catch (err) {
yield put(fetchError(err));
}
}
```

- For parallel dependencies: `const [user, posts] = yield all([call(api.getUser), call(api.getPosts)])` if they can run simultaneously.
- Sagas also provide cancellation, debouncing, and race conditions, which are valuable in real‑world scenarios.

**Real‑world considerations:**
- Handle loading/error states for each independent call.
- Use selectors to avoid redundant calls when data already exists.
- Cache responses where appropriate.
- For complex orchestration, Saga is often more maintainable than nested thunks.

[↑ Back to top](#table-of-contents)

### 35. If Redux is causing too many re-renders, how would you optimize it?

Too many re‑renders usually mean components are subscribed to more state than they need, or selectors are not memoised.

- **Use memoised selectors:** `createSelector` from Reselect ensures that a component only re‑renders when the specific slice of state it uses changes.
- **Connect only what is needed:** When using `useSelector`, subscribe to individual pieces of state, not the whole state object.

```javascript
// Bad: re‑renders on any state change
const state = useSelector(state => state);

// Good: re‑renders only when user.name changes
const name = useSelector(state => state.user.name);
```

- **Shallow equality checks:** `useSelector` uses strict `===` by default; if returning a new object/array each time, it triggers re‑renders. Return primitives or use `shallowEqual` as a second argument.
- **Use `React.memo` on components** that receive props from Redux to prevent parent re‑renders from cascading.
- **Avoid dispatching actions that update large slices unnecessarily.** Split actions to target only what changed.
- **Consider using Redux Toolkit’s `createEntityAdapter`** which provides memoised selectors out of the box.
- **Profile with React DevTools** to confirm which components are re‑rendering and why.

[↑ Back to top](#table-of-contents)

### 36. In a complex application, state is becoming hard to manage — how would you restructure your Redux store?

Hard‑to‑manage state often results from a flat, overly nested, or “everything in one slice” structure.

- **Normalise the state:** Use a structure like `{ entities: { users: { byId: {}, allIds: [] } }, ui: {}, ... }`. This avoids deep nesting and simplifies updates. Libraries like `normalizr` help.
- **Split by domain / feature:** Combine related reducers with `combineReducers`. Each feature owns its slice of state and its own actions/reducers.
- **Use Redux Toolkit (RTK):** It enforces best practices: `createSlice` bundles reducers and actions, `createEntityAdapter` provides pre‑built normalisation logic.
- **Move derived data out of the store:** Use selectors (with `createSelector` from Reselect) to compute derived data on demand, preventing redundant storage.
- **Avoid deeply nested state:** If you have `state.a.b.c.d`, refactor so each slice is flatter. Consider if the nesting is necessary; often UI state can be local.
- **Separate UI state from domain state:** UI state (modal open, loading) can often be kept in local component state unless needed globally.

[↑ Back to top](#table-of-contents)

### 37. Redux vs Context API vs Zustand – how do you decide in a large-scale application?

| | Redux | Context API | Zustand |
|---|-------|-------------|---------|
| **Use case** | Large apps, complex state, frequent updates | Simple state, medium nesting, low update frequency | Small‑medium apps, simple API, minimal boilerplate |
| **Performance** | Optimized with selectors, middleware | Can cause re‑renders; requires careful splitting | Very performant, minimal re‑renders |
| **Boilerplate** | Higher (but RTK reduces it) | Low | Very low |
| **Tooling** | Excellent (DevTools) | Basic | Good |
| **Learning curve** | Steeper | Easy | Easy |

**Decision**: For large‑scale apps with many features, complex async logic, and need for time‑travel debugging, Redux (with RTK) is a solid choice. If you need a lighter alternative with good performance and less boilerplate, Zustand is popular. Context is best for static or low‑frequency updates (e.g., theme, localization) and not recommended for high‑frequency state.

[↑ Back to top](#table-of-contents)

### 38. Situation: Two components on different branches need the same data – what do you do?

Options: (1) Lift state to nearest common ancestor. (2) Put it in Context. (3) Use a global state store. (4) If server data, use React Query – both components call the same `useQuery` key and share a cache automatically.

[↑ Back to top](#table-of-contents)

### 39. What is the difference between Redux, Context, and Zustand for large-scale apps?

Redux Toolkit: most mature, excellent DevTools, enforces strict patterns, good for teams with complex state machines. Best when: large team, complex async flows, need for time-travel debugging. Context API: built-in, zero config, fine for infrequent updates. Problems with high-frequency updates (every consumer re-renders on any change). Zustand: minimal boilerplate, fast, component only re-renders on subscribed slice change, easy async. Best when: Redux feels too heavy but Context too limited. Decision matrix: Context for themes/auth, Zustand for medium complexity, RTK for enterprise.

[↑ Back to top](#table-of-contents)

## Routing & Navigation

### 40. How do you handle 404s in React Router?

A catch-all route with `path="*"` rendering a NotFound component, placed last in the route tree.

[↑ Back to top](#table-of-contents)

## Data Fetching & React Query/Suspense

### 41. Design an infinite scrolling feed.

Approach: (1) IntersectionObserver on a sentinel element at the bottom — fires when visible. (2) Maintain page/cursor state, append new items to existing array. (3) React Query or SWR for data fetching with built-in cursor-based pagination. (4) Virtualization (react-virtual) if list grows very large. (5) Loading skeleton for next batch. (6) Error state with retry. (7) Avoid re-fetching already loaded pages. Advanced: prefetch next page when user is 80% down current page for seamless experience.

[↑ Back to top](#table-of-contents)

### 42. How do you decide between fetching data in a Server Component vs a Client Component with React Query?

Server Component fetching is simpler and ships no client JS for that data, ideal for content that doesn't need client-side caching/refetching/mutation UX. React Query fits when you need client-side cache invalidation, optimistic updates, polling, or the data is tied to client-only interaction (e.g., live search).

[↑ Back to top](#table-of-contents)

### 43. How do you ensure a React app performs well at 100k users?

CDN for static assets. SSR/SSG for fast initial loads. Aggressive
caching (React Query, HTTP cache headers). Server-side pagination, never
load all data. Code splitting per route. Error boundaries everywhere.
Monitoring and alerting from day one.

[↑ Back to top](#table-of-contents)

### 44. How would you implement infinite scroll?

Use `IntersectionObserver` to detect when a sentinel element at the bottom is visible. Trigger the next page fetch. Append results to existing list. Use React Query's `useInfiniteQuery` for built-in pagination support. Virtualize for 1000+ items.

[↑ Back to top](#table-of-contents)

### 45. Situation: API data is needed in multiple components – how do you avoid duplicate fetches?

Use React Query – same query key deduplicates concurrent requests. Or fetch at a high level (loader, server component) and pass data down. Avoid fetching the same data in sibling components independently.

[↑ Back to top](#table-of-contents)

## SSR, Next.js & Server Components

### 46. A Server Component page in Next.js is suddenly much slower after a change. How do you debug?

Check for an accidental request waterfall between components; verify fetch caching wasn't disabled; check if a new Client Component boundary pulled server-only code into the client bundle; profile with Next.js tracing/network waterfall.

[↑ Back to top](#table-of-contents)

### 47. How would you design a migration strategy from a legacy jQuery app to modern React/Next.js?

**Goal**: Minimize risk, keep business running, and deliver incremental value.

**Strategy**:

[↑ Back to top](#table-of-contents)

### 48. How would you design SSR/SSG/hydration strategy for a React app?

**Strategy** depends on content type and performance needs.

-   **SSR for dynamic content** (e.g., user dashboard): Use Next.js
`getServerSideProps` or a custom Node server with `renderToString`.
Ensure hydration matches server HTML.
-   **SSG for marketing pages**: Use `getStaticProps` with `revalidate`
for ISR.
-   **Hybrid**: Use Next.js App Router with `use client` and server
components to mix server‑side and client‑side.
-   **Hydration**: Ensure that server and client render produce
identical HTML. Avoid using browser‑only APIs during server render.
Use `useEffect` for client‑only code.
-   **Performance**: Stream SSR (React 18 `renderToPipeableStream`) to
send HTML progressively.

[↑ Back to top](#table-of-contents)

### 49. Poor SEO & Slow TTI: React app has poor SEO and slow TTI -- frontend-level solutions.

**SEO issues**: - **Server‑Side Rendering (SSR)** or **Static Site
Generation (SSG)** with frameworks like Next.js. - Ensure meta tags
(title, description, Open Graph) are rendered on the server. - Use
semantic HTML.

**Slow TTI (Time to Interactive)**: - **Code splitting** -- lazy load
non‑critical components and routes. - **Bundle optimization** -- tree
shaking, minification, remove unused dependencies. - **Reduce
JavaScript** -- audit bundle size, use lightweight alternatives. -
**Prioritize critical CSS** -- inline above‑the‑fold styles, defer
non‑critical CSS. - **Use `preconnect` and `preload`** for important
resources. - **Optimize images** -- use modern formats, responsive
sizes. - **Lazy load off‑screen images**. - **Service Worker** for
caching assets.

[↑ Back to top](#table-of-contents)

### 50. What causes hydration mismatches and how do you fix them?

Think of a hydration mismatch like a blueprint mix-up between two different builders.

When using Server-Side Rendering (SSR), the Server builds the HTML webpage first and sends it to the browser. Then, React boots up in the browser, reads that HTML, and tries to "adopt" it (this adoption process is called hydration).

A hydration mismatch happens when the HTML that the server built does not exactly match what React expects to see in the browser. React gets confused and throws an error.

🚨 What Causes It? (The Differences)
Timestamps: The server creates the HTML at 10:00:00 AM. The browser downloads and reads it at 10:00:03 AM. Because the seconds don't match, React panics.

Browser-Only Secrets: The server doesn't have a screen or a hard drive, so it doesn't know what window.innerWidth or localStorage is. If your code uses these, the server will output a blank space, but the browser will try to fill it in with real data.

Random Numbers: If you use Math.random(), the server might roll a 4, but the browser rolls a 7.

🛠️ How to Fix It
The Best Way (useEffect): Keep the server text generic or empty at first. Use a useEffect hook to calculate the time, random numbers, or browser data after the page has fully loaded in the browser.

The "Ignore It" Way (suppressHydrationWarning): If you have a minor, harmless mismatch (like a text timestamp), you can add this attribute to your HTML tag to tell React: "I know they don't match, please don't yell at me."

The "Skip Server" Way: Turn off server-rendering for that specific component completely so it only ever builds on the browser.

[↑ Back to top](#table-of-contents)

## Error Handling & Error Boundaries

### 51. A third-party component throws an error — how do you handle it?

Wrap it in an Error Boundary, log to a monitoring service in `componentDidCatch`, and show a friendly fallback with a retry option.

[↑ Back to top](#table-of-contents)

### 52. In which scenarios error boundaries do not catch errors?

Below are the cases in which error boundaries doesn't work,

1. Inside Event handlers
2. Asynchronous code using **setTimeout or requestAnimationFrame** callbacks
3. During Server side rendering
4. When errors thrown in the error boundary code itself

[↑ Back to top](#table-of-contents)

### 53. Situation: A third-party component throws -- how do you handle it?

Wrap it in an error boundary. Log errors in `componentDidCatch` to a
monitoring service (Sentry, Datadog). Show a friendly fallback.
Optionally provide a 'Try Again' button that resets the boundary state.

[↑ Back to top](#table-of-contents)

## TypeScript with React

### 54. How would you design a design system in React?

Separate npm package. Primitive components (Button, Input, Text). Compound components for complex widgets. Design tokens (CSS variables). Storybook for documentation. Chromatic for visual regression. Semantic versioning with changelogs. TypeScript for consumer safety.

*225 questions across 18 sections. Happy studying! ⚛️*

[↑ Back to top](#table-of-contents)

## Security & Accessibility

### 55. How would you design a reusable component library for a large team?

(1) Storybook for component development and documentation. (2) Design
tokens (CSS variables or JS constants) for consistent colors,
spacing, typography. (3) Component API design:
controlled/uncontrolled variants, compound components, render props
for flexibility. (4) Accessibility: ARIA roles, keyboard navigation,
focus management by default. (5) TypeScript with comprehensive prop
types. (6) Versioned package (npm) with semantic versioning. (7)
Visual regression testing (Chromatic). (8) Atomic design
methodology: atoms → molecules → organisms. (9) Peer deps for React,
not bundled.

[↑ Back to top](#table-of-contents)

## React Ecosystem & Build Tools

### 56. How do you debug a React Native app?

Run in a simulator, open the in-app dev menu, use Chrome DevTools connected via the debugger, and enable "Pause on Caught Exceptions" for step-through debugging.

[↑ Back to top](#table-of-contents)

### 57. How to enable production mode in React?

You should use Webpack's `DefinePlugin` method to set `NODE_ENV` to `production`, by which it strip out things like propType validation and extra warnings. Apart from this, if you minify the code, for example, Uglify's dead-code elimination to strip out development only code and comments, it will drastically reduce the size of your bundle.

[↑ Back to top](#table-of-contents)

### 58. What is a CORS issue and how do you handle it?

Cross-Origin Resource Sharing: browsers block requests to different origins. Configure the server to send correct `Access-Control-Allow-Origin` headers. In development, use a proxy in `vite.config` or CRA's proxy setting.

[↑ Back to top](#table-of-contents)

## General / Miscellaneous React Concepts

### 59. How do you handle conditional class names?

`clsx`/`classnames`: `clsx('btn', { 'btn-active': isActive })`.

[↑ Back to top](#table-of-contents)

### 60. How do you handle dependent/sequential queries (query B needs query A's result)?

Use the `enabled` option: `useQuery({ queryKey: ['b', aData?.id], queryFn: ..., enabled: !!aData })`, so query B only runs once `aData` is available.

[↑ Back to top](#table-of-contents)

### 61. How do you handle keyboard navigation in a custom component (e.g., a dropdown or menu)?

Implement `onKeyDown` following WAI-ARIA authoring practices for that widget type: Enter/Space to activate, arrow keys to move between items, Escape to close.

[↑ Back to top](#table-of-contents)

### 62. How do you handle keyboard navigation in custom components?

Implement `onKeyDown` for keyboard interactions (Enter/Space for activation, arrow keys for navigation, Escape to close). Follow WAI-ARIA authoring practices for each widget type (menu, dialog, tabs, combobox).

[↑ Back to top](#table-of-contents)

### 63. How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue‑green deployments?

A robust pipeline enables safe, gradual rollouts.

[↑ Back to top](#table-of-contents)

### 64. How would you design a reusable, prop-explosion-resistant component (e.g., a Button or Modal)?

Use compound components or config objects instead of dozens of booleans; support both controlled and uncontrolled usage; forward refs for DOM access; separate variants into styling tokens rather than conditional logic.

[↑ Back to top](#table-of-contents)

### 65. How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)

**Web Workers** – offload data processing, sorting, filtering, or any CPU‑intensive task to a background thread.
- The worker processes the dataset and returns a result (e.g., filtered list) to the main thread.
- The main thread remains responsive for UI updates.

**Virtualization** – as described, reduces the number of DOM nodes, so the main thread has less work to do.

**Chunking / Time‑slicing** – break up heavy work into smaller chunks using `setTimeout` or `scheduler.postTask` to allow the browser to handle user interactions in between.

**Streaming / Pagination** – load data incrementally rather than all at once.

**WebAssembly** – if dataset processing is extremely heavy, consider using Wasm for performance (though overkill for most cases).

[↑ Back to top](#table-of-contents)

### 66. How would you handle real-time updates in a React application efficiently?

Options by use case: (1) WebSockets: bidirectional, persistent
connection --- best for chat, collaborative editing, live cursors. Use
socket.io or native WebSocket API. (2) Server-Sent Events (SSE): server
→ client only, uses HTTP --- best for live feeds, notifications, stock
prices. (3) Long polling: fallback for environments that block
WebSockets. React integration: connect in useEffect, cleanup on unmount,
update state with incoming data, use Redux or Zustand for normalization.
Optimization: batch rapid updates with throttle, use Immer for immutable
updates.

[↑ Back to top](#table-of-contents)

### 67. Real-time Updates: How to handle real-time updates efficiently in React?

**Approaches**: - **WebSockets** (or Socket.io) for low‑latency
bidirectional communication. - **Server‑Sent Events (SSE)** for
server‑to‑client streaming. - **Polling** as fallback (with exponential
backoff).

**Efficiency**: - **Throttle UI updates** -- use `requestAnimationFrame`
or `useDeferredValue` (React 18) to avoid blocking the main thread. -
**Batch updates** -- group multiple incoming messages into a single
state update. - **Use `useReducer`** with a reducer that merges data
intelligently. - **Memoize components** to avoid re‑rendering everything
on every update. - **Virtualization** for real‑time lists (e.g., live
feeds).

**Example WebSocket hook**:

``` javascript
const useWebSocket = (url) => {
const [data, setData] = useState(null);
useEffect(() => {
const ws = new WebSocket(url);
ws.onmessage = (event) => {
setData(JSON.parse(event.data));
};
return () => ws.close();
}, [url]);
return data;
};

```

[↑ Back to top](#table-of-contents)

### 68. Situation: A dropdown closes when you click inside it – what's likely wrong?

The click propagates to the document's mousedown handler which closes the dropdown before the button inside registers its click. Fix: call `e.stopPropagation()` on the dropdown container's mousedown, or check if click target is inside the ref.

[↑ Back to top](#table-of-contents)

### 69. What is source map generation, and why is it important in a production React deployment?

Source maps map minified/bundled production code back to original source lines, letting you read meaningful stack traces from production error reports (e.g., in Sentry) without shipping readable source code to end users (maps are uploaded separately, not served publicly).

[↑ Back to top](#table-of-contents)
