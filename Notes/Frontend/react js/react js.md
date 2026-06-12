# React.js – Comprehensive Interview Question Bank

**225+ Questions across 18 sections**

*Fundamentals · Hooks · Patterns · Performance · TypeScript · Testing · RSC · Senior Scenarios*

---

## Section 1: Fundamentals & JSX

*Core concepts every React developer must know cold.*

**Q1. What is React and what problem does it solve?**

React is a JavaScript library by Meta for building UIs using a declarative, component-based model. It solves the complexity of keeping the UI in sync with application state by reacting to state changes automatically and efficiently updating the DOM.

**Q2. How is React different from Angular or Vue?**

React is a view library (handles only UI); Angular is a full framework with DI, routing, forms built-in; Vue sits in between. React uses JSX + JS composition, Angular uses TypeScript + decorators + templates, Vue uses SFC (Single File Components).

**Q3. What is JSX and why does React use it?**

JSX is a syntax extension allowing HTML-like markup inside JS. At build time it compiles to `React.createElement()` calls. It improves readability, catches errors earlier via the compiler, and makes component trees visually clear.

**Q4. What does JSX compile to?**

JSX compiles to `React.createElement(type, props, ...children)` in React <17, and to the automatic `jsx()` runtime in React 17+. Both produce plain JavaScript objects (React elements) describing the UI.

**Q5. Can you use React without JSX?**

Yes. `React.createElement('div', {className:'box'}, 'Hello')` is valid but verbose. JSX is purely syntactic sugar; the output is identical JS objects.

**Q6. What is the Virtual DOM?**

An in-memory lightweight JS tree that mirrors the real DOM. React renders to the virtual DOM first, diffs two versions (reconciliation), and applies only the minimal set of real DOM mutations needed.

**Q7. How does the Virtual DOM improve performance?**

Real DOM mutations are expensive (layout, paint, composite). React batches changes and applies minimal updates. The diffing algorithm is O(n) using heuristics (same type → update; different type → destroy and replace).

**Q8. What are React elements vs React components?**

An element is a plain JS object describing what to render: `{type:'div', props:{...}}`. A component is a function or class that accepts props and returns elements. `createElement()` creates elements; components are called/constructed to produce them.

**Q9. What is `createRoot()` and why was it introduced in React 18?**

`createRoot()` replaces `ReactDOM.render()`. It opts the app into React 18's concurrent features (automatic batching, `startTransition`, Suspense improvements). `ReactDOM.render()` runs in legacy mode without those features.

**Q10. What are pure components?**

Components that produce the same output for the same props/state. `React.PureComponent` (class) and `React.memo` (function) implement shallow-equality checks to skip redundant renders.

**Q11. What is the difference between an element and a component instance?**

An element is a description object (`{type, props}`). An instance is the internal object React creates for class components to hold state and lifecycle. Functional components have no instance; hooks store state in React's fiber node instead.

**Q12. What does 'declarative' mean in React?**

You describe what the UI should look like for a given state. React figures out how to make the DOM match. Imperative code would manually manipulate the DOM step by step; declarative code just re-renders with new state.

**Q13. What is the React DevTools and what can you do with it?**

A browser extension that lets you inspect the component tree, view props/state/context, highlight re-renders, and use the Profiler to record timing and flame graphs of render performance.

**Q14. What are the rules of JSX?**

Must return a single root element (or Fragment); all tags must be closed; attributes use camelCase (`className`, `onClick`, `htmlFor`); JS expressions go inside `{}`; cannot use reserved words like 'class' or 'for'.

**Q15. What is a React SPA and what are its trade-offs?**

A Single Page App loads once and swaps content client-side. Pros: fast subsequent navigation, rich interactions, offline potential. Cons: slower initial load, SEO challenges without SSR/prerendering, requires client-side routing.

---

## Section 2: Components, Props & State

*The building blocks of every React application.*

**Q16. What is a React component?**

A reusable, self-contained piece of UI. It's a function (or class) that accepts props and returns React elements. Components can be composed together to build complex UIs.

**Q17. Functional vs class components – key differences?**

Functional: plain JS functions, use hooks for state/lifecycle, simpler, preferred since React 16.8. Class: extend `React.Component`, use `this.state` and lifecycle methods, support error boundaries natively. New code should use functional components.

**Q18. What are props?**

Read-only inputs passed from parent to child. Props flow downward (one-way data flow). Mutating props directly is forbidden; instead lift state or use callbacks.

**Q19. How do you pass data child → parent?**

Pass a callback function as a prop. The child calls it with data, the parent receives it in the handler and updates its state. This maintains one-way data flow while still communicating upward.

**Q20. What is prop drilling and why is it a problem?**

Passing props through many intermediate components that don't use them just to reach a deep child. It creates tight coupling and makes refactoring hard. Solved by Context, state management libraries, or component composition.

**Q21. What is state in React?**

Mutable data owned by a component. When state changes, React schedules a re-render. State is private to the component unless shared via props or context. `useState` / `useReducer` manage it in functional components.

**Q22. What is the difference between props and state?**

Props are external, immutable (from parent). State is internal, mutable (managed by the component). Props configure a component; state tracks what changes over time inside it.

**Q23. Why is state update asynchronous?**

React batches state updates for performance. `setState()` / the setter from `useState()` schedules a re-render rather than immediately mutating state. Reading state right after calling the setter still returns the old value within the same event handler.

**Q24. What is lifting state up?**

Moving shared state to the nearest common ancestor of components that need it, then passing it down via props and up via callbacks. This keeps state as the single source of truth.

**Q25. What is the `key` prop and why is it important?**

A special string or number that uniquely identifies a list item. React uses keys to match items between renders for efficient reconciliation. Wrong or missing keys cause incorrect DOM reuse and subtle bugs.

**Q26. Why avoid array index as key?**

When items are reordered, inserted, or deleted, index-based keys cause React to reuse DOM nodes incorrectly. Use stable unique IDs (DB id, UUID) instead.

**Q27. Controlled vs uncontrolled components?**

Controlled: form value stored in React state, updated via `onChange` → single source of truth, enables validation. Uncontrolled: value lives in DOM, read via ref → less code for simple forms, harder to validate or manipulate programmatically.

**Q28. What are fragments?**

Syntax for returning multiple elements without an extra DOM node: `<> </>` or `<React.Fragment>`. Keyed fragments use the long form: `<React.Fragment key={id}>`.

**Q29. What are portals?**

`ReactDOM.createPortal(child, domNode)` renders child outside the parent component's DOM hierarchy while keeping it in React's component tree (events still bubble through). Used for modals, tooltips, dropdowns.

**Q30. What are default props and PropTypes?**

`defaultProps` sets fallback values for missing props. `PropTypes` (from 'prop-types' package) validates prop types at runtime in development. TypeScript interfaces are the modern alternative.

**Q31. What is the children prop?**

A special prop containing everything between a component's opening and closing tags. Accessed as `props.children`. Can be any renderable value: string, element, array, or a function (render prop pattern).

**Q32. When should a component be split into smaller components?**

When it exceeds ~150 lines, has distinct logical sections, when part of it needs to be reused, or when different parts change at different frequencies. Each component should have a single clear responsibility.

**Q33. What is the difference between element and component re-render?**

Elements are plain objects; React creates/updates them every render cheaply. A component re-renders when its state or props change, executing the function body again. Only DOM nodes actually affected get updated in the real DOM.

**Q34. What are presentational vs container components?**

Presentational: concern is how things look, receive data via props, rarely have own state. Container: concern is how things work, handle data fetching and state, pass data to presentational children. The pattern is less strict now that hooks exist.

**Q35. What happens if you mutate state directly?**

React does not detect the change and won't re-render. Always return new references: `setState([...arr])` or `setState({...obj})`. Direct mutation causes stale UI and hard-to-debug bugs.

---

## Section 3: Rendering, Reconciliation & Lifecycle

*Understanding how React decides what to render and when.*

**Q36. What is reconciliation?**

The process of diffing the new React element tree against the previous one to compute minimal DOM mutations. React uses two heuristics: same type → update props; different type → unmount old, mount new. Keys help reconcile lists.

**Q37. How does React's diffing algorithm work (O(n))?**

React compares trees level by level. If root elements differ in type, it destroys the old tree. For same-type DOM elements it updates only changed attributes. For same-type components it updates props and re-renders. Keys enable efficient list diffing.

**Q38. What is React Fiber?**

Fiber is React's reimplemented reconciler (React 16+). It represents each component as a 'fiber' node in a linked list. Work is split into units that can be paused, prioritized, aborted, or resumed – enabling concurrent features.

**Q39. What are the three main lifecycle phases?**

Mounting (component added to DOM), Updating (props/state change → re-render), Unmounting (component removed from DOM). Class components have explicit methods; hooks model these via `useEffect`.

**Q40. Map class lifecycle methods to hooks.**

- `componentDidMount` → `useEffect(() => {...}, [])`
- `componentDidUpdate` → `useEffect(() => {...}, [dep])`
- `componentWillUnmount` → cleanup function returned from `useEffect`
- `getDerivedStateFromProps` → compute derived state inline or in `useMemo`

**Q41. What is the order of hook execution in a component?**

Hooks run top-to-bottom on every render in the same order. React relies on call order to associate hook state with the correct hook – this is why hooks cannot be inside conditionals or loops.

**Q42. What causes unnecessary re-renders?**

New object/array/function references created inline in JSX; context value changing; parent re-rendering; global state updates. Fix: memoize with `React.memo`, `useMemo`, `useCallback`, or restructure state.

**Q43. What is hydration?**

Attaching React's event handlers and internal state to server-rendered HTML without re-rendering it. React expects the client-side output to exactly match server HTML; mismatches cause warnings or errors.

**Q44. What causes hydration mismatches and how do you fix them?**

Random values, timestamps, browser-only APIs (`window`, `localStorage`), or different data between server and client. Fix: move non-deterministic code to `useEffect`, use `suppressHydrationWarning` for unavoidable differences, or avoid SSR for that component.

**Q45. What is Strict Mode?**

A development-only wrapper (`<React.StrictMode>`) that double-invokes renders, effects, and reducers to surface non-idempotent side effects. Also warns about deprecated APIs. Has no production effect.

**Q46. What is `getDerivedStateFromProps` and when would you use it?**

A static class lifecycle that returns new state derived from props before every render. Rarely needed; usually derived state should be computed during render or via `useMemo`. Overuse leads to confusing state synchronization bugs.

**Q47. What is `getSnapshotBeforeUpdate`?**

A class lifecycle called right before the DOM is updated. Its return value is passed as 'snapshot' to `componentDidUpdate`. Used for reading scroll position or other DOM measurements before a commit.

**Q48. Explain the commit phase vs render phase.**

Render phase: React calls component functions, runs reconciliation – pure, may be paused/aborted. Commit phase: React applies DOM mutations, runs layout effects (`useLayoutEffect`), then passive effects (`useEffect`) – cannot be interrupted.

**Q49. What happens when a parent re-renders?**

All child components re-render by default unless wrapped in `React.memo` or the subtree is stable. Re-rendering means the function runs again; it does not mean the DOM changes – React still diffs before touching the DOM.

**Q50. What is `shouldComponentUpdate` and its functional equivalent?**

`shouldComponentUpdate` returns boolean to control re-rendering in class components. The functional equivalent is `React.memo` (shallow comparison) or a custom comparator passed as its second argument.

---

## Section 4: Core Hooks

*Mastering the hooks that power modern React.*

**Q51. What is `useState`?**

Declares state in a functional component. Returns `[value, setter]`. The setter schedules a re-render with the new value. Multiple `useState` calls are independent.

**Q52. Why use functional updates with `useState`?**

`setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

**Q53. What is lazy initialization in `useState`?**

`useState(() => expensiveCalc())` passes a function so the initial value is computed only once (on mount), not on every render. Useful for reading from `localStorage` or parsing data.

**Q54. What is `useEffect`?**

Runs side effects after render (data fetching, subscriptions, DOM manipulation). Dependency array controls when it runs: `[]` → once on mount; `[a,b]` → when a or b changes; omitted → every render.

**Q55. What is the `useEffect` cleanup function?**

Return a function from `useEffect` to run cleanup before the next effect or on unmount. Used to clear timers, cancel fetch, unsubscribe from observables, or remove event listeners.

**Q56. What are stale closures in `useEffect`?**

When an effect captures a variable from a previous render. If the dependency array is incomplete, the effect uses the old value. Fix: add the variable to deps, or use a ref to always access the latest value.

**Q57. What is `useRef`?**

Returns a mutable `{current}` object that persists across renders without triggering re-renders. Two main uses: (1) accessing DOM nodes directly, (2) storing instance variables like timers or previous values.

**Q58. How does `useRef` differ from a regular variable?**

Regular variables reset on every render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for functional components.

**Q59. What is `useContext`?**

Subscribes to a React context. Receives the current context value and re-renders whenever it changes. Eliminates prop drilling for shared data like theme, locale, auth, or feature flags.

**Q60. What is `useReducer`?**

Like `useState` but manages state via a `reducer(state, action) => newState` function. Better for complex state with multiple sub-values, or when next state depends on action type. Pairs well with `useContext` for mini-Redux patterns.

**Q61. What is `useMemo`?**

Memoizes the result of an expensive computation. Re-computes only when dependencies change. Use for: heavy calculations, creating stable object/array references, derived data from props.

**Q62. What is `useCallback`?**

Memoizes a function reference. Prevents child components that receive the function as prop from re-rendering unnecessarily, and prevents effects from re-running when a callback is a dependency.

**Q63. `useMemo` vs `useCallback` – what's the difference?**

`useMemo(() => fn(), deps)` memoizes the return value of `fn`. `useCallback(fn, deps)` memoizes `fn` itself. `useCallback(fn, deps) === useMemo(() => fn, deps)`. Choose `useMemo` for values, `useCallback` for functions.

**Q64. What is `useLayoutEffect`?**

Same signature as `useEffect` but fires synchronously after DOM mutations and before browser paint. Use for: reading layout (scroll position, dimensions) and synchronously updating the DOM to avoid flicker.

**Q65. What is `useImperativeHandle`?**

Customizes the ref value exposed when `forwardRef` is used. Lets a parent call specific methods on a child (e.g., `child.focus()`) without exposing the entire DOM node or component internals.

**Q66. What are the Rules of Hooks?**

1. Only call hooks at the top level – not inside conditions, loops, or nested functions.
2. Only call hooks from React function components or custom hooks.

These rules ensure hooks are called in the same order every render.

**Q67. How do you create a custom hook?**

A function whose name starts with 'use' that calls other hooks. It extracts and reuses stateful logic without changing component hierarchy. E.g., `useWindowSize()`, `useFetch()`, `useDebounce()`.

**Q68. What is `useId`?**

Generates a stable, unique ID that is consistent between server and client renders. Use for accessibility attributes like `aria-labelledby` or `htmlFor` where IDs must match across SSR and hydration.

**Q69. What is `useDebugValue`?**

Used inside custom hooks to display a label in React DevTools. Helps identify what a custom hook is doing when inspecting components. The second argument is a formatting function called only in DevTools.

**Q70. Situation: `useEffect` runs infinitely – what's wrong?**

Most likely a dependency that changes on every render: an object/array created inline (`{} !== {}` every render), or a function without `useCallback`. Fix: memoize the dependency, move it outside the component, or restructure state.

---

## Section 5: Advanced Hooks & Performance

*Optimizing React apps for real-world scale.*

**Q71. What is `React.memo`?**

A HOC that wraps a functional component. On re-render of the parent, React shallowly compares old and new props; if equal, it skips re-rendering the child. Accepts a custom comparator as second argument.

**Q72. When does `React.memo` NOT help?**

When props include new object/function references on every parent render (must pair with `useMemo`/`useCallback`). When the component is cheap to render (overhead of comparison > render cost). When props always change.

**Q73. How do you avoid unnecessary object/function recreation?**

Declare stable values outside the component when possible, use `useMemo` for objects/arrays, `useCallback` for functions, and avoid inline object literals as prop values in JSX.

**Q74. What is windowing/virtualization and when do you need it?**

Rendering only visible list items in a large dataset instead of all of them. Libraries: `react-window`, `react-virtual`, `TanStack Virtual`. Use when rendering 1000+ items causes frame drops or memory pressure.

**Q75. What is code splitting?**

Splitting the JS bundle into smaller chunks loaded on demand. `React.lazy` + `Suspense` enable component-level splitting. Route-level splitting is most impactful (each route loads only its JS).

**Q76. What is `React.lazy` and how does it work?**

`React.lazy(() => import('./Comp'))` creates a lazy-loaded component. React suspends rendering until the chunk loads, showing the nearest `Suspense` fallback. Only works with default exports.

**Q77. What is the Profiler API?**

`React.Profiler` wraps a tree and calls `onRender(id, phase, actualDuration, ...)` after each commit. Used to programmatically measure render performance in development. React DevTools Profiler wraps this in a UI.

**Q78. How do you measure and fix excessive re-renders?**

Use React DevTools 'Highlight Updates' to spot components re-rendering. Record a Profiler session to see flame charts. Then: add `React.memo`, split context, move state closer to usage, or batch updates.

**Q79. What is the `useTransition` hook for performance?**

Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator.

**Q80. What is `useDeferredValue`?**

Accepts a value and returns a deferred copy that trails behind during heavy renders. UI stays responsive with the current value while React concurrently renders the expensive output with the new value.

**Q81. Situation: A search input lags as user types – how do you fix it?**

Separate the input state (urgent) from the search results state (deferred). Use `useDeferredValue` or `useTransition` on the results update. This lets the input remain responsive while results compute asynchronously.

**Q82. What is tree shaking?**

Bundlers (webpack, Rollup, Vite) remove unused exports from the final bundle using static analysis of import/export. Use named exports and avoid side-effectful imports to enable effective tree shaking.

**Q83. What are common React performance pitfalls?**

Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading.

**Q84. What is the 'why did you render' library?**

A development utility that patches React to notify you when a component re-renders due to reference-equal props/state. Helps find components where `React.memo` or `useMemo` would be beneficial.

**Q85. What is the difference between optimistic and pessimistic updates?**

Optimistic: update UI immediately assuming success, roll back on error (fast UX). Pessimistic: wait for server confirmation before updating UI (safe, may feel slow). React 19 has `useOptimistic` for the optimistic pattern.

---

## Section 6: Context & State Management

*Managing state at every scale.*

**Q86. What is the Context API?**

A built-in React mechanism for sharing values across the component tree without prop drilling. Three parts: `React.createContext()` (creates context), `Provider` (supplies value), `useContext()` (consumes value).

**Q87. Context re-render behavior – what should you know?**

Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`.

**Q88. When should you NOT use Context for state?**

For frequently changing data (e.g., mouse position, animation frames), because every consumer re-renders. Use a dedicated state library with selectors (Zustand, Jotai, Redux) for fine-grained subscriptions.

**Q89. Context vs Redux – when to choose which?**

Context: simple, low-frequency shared state (theme, auth, locale). Redux: complex update logic, middleware (logging, side effects), time-travel debugging, large team codebases, or when you need strict action-based mutations.

**Q90. What is Zustand and how does it differ from Redux?**

Zustand is a minimal state library using hooks. No boilerplate, no reducers/actions required. Stores are plain JS objects with setter functions. Components subscribe to specific slices to avoid unnecessary re-renders.

**Q91. What is Jotai and how does the atomic model work?**

Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

**Q92. What is server state vs client state?**

Server state: data from APIs (users, posts) – needs caching, refetching, synchronization, background updates. Client state: local UI state (modal open, form values) – synchronous, lives only in the browser.

**Q93. What is React Query (TanStack Query)?**

A library for fetching, caching, synchronizing, and updating server state. Provides `useQuery` (fetch), `useMutation` (create/update/delete), automatic background refetching, cache invalidation, and stale-while-revalidate.

**Q94. Situation: Two components on different branches need the same data – what do you do?**

Options: (1) Lift state to nearest common ancestor. (2) Put it in Context. (3) Use a global state store. (4) If server data, use React Query – both components call the same `useQuery` key and share a cache automatically.

**Q95. What is the Redux Toolkit (RTK)?**

The official, recommended way to write Redux. Reduces boilerplate with `createSlice` (combines actions + reducers), `configureStore`, and RTK Query (built-in data fetching/caching layer).

**Q96. What is the `useSelector` / `useDispatch` pattern in Redux?**

`useSelector(state => state.slice.value)` subscribes a component to a slice of Redux state and re-renders only when that value changes. `useDispatch()` returns the dispatch function to send actions.

**Q97. Situation: Context is causing performance issues in a large app – what do you do?**

Split into multiple smaller contexts by concern. Memoize provider values. Move high-frequency state to a store with selectors (Zustand, Jotai). Use context only for rarely-changing values.

**Q98. What is the flux architecture pattern?**

Unidirectional data flow: Action → Dispatcher → Store → View → (user interaction) → Action. Redux is inspired by Flux. Data always flows one way, making state changes predictable and traceable.

---

## Section 7: Component Patterns & Architecture

*Patterns that make React code reusable, scalable, and maintainable.*

**Q99. What are Higher-Order Components (HOCs)?**

Functions that take a component and return a new component with enhanced behavior. E.g., `withAuth(Component)` wraps it to redirect if unauthenticated. HOCs are less common now that custom hooks exist.

**Q100. What is the render props pattern?**

A component accepts a function prop (`render` or `children`) and calls it with shared data. `<Mouse render={({x,y}) => <Cursor x={x} y={y}/>}/>`. Flexible but can lead to callback hell; custom hooks are usually cleaner.

**Q101. What are compound components?**

A set of components that share implicit state through context. E.g., `<Select>`, `<Select.Option>`, `<Select.Trigger>`. The parent manages state; children are compositionally flexible. Used in UI libraries (Headless UI, Radix).

**Q102. What is the provider pattern?**

A component that wraps part of the tree and supplies shared state/functionality via context. Used extensively: `ThemeProvider`, `AuthProvider`, `QueryClientProvider`. Stacking providers is common.

**Q103. What is the state reducer pattern?**

A component exposes a `stateReducer` prop. Consumers can override state transitions for customization, giving them control without losing default behavior. Used in libraries like Downshift.

**Q104. What is the controlled component pattern for reusable components?**

A reusable component can work in two modes: uncontrolled (manages own state) or controlled (parent provides `value` + `onChange`). Example: an `<Accordion>` that works out of the box but can also be fully controlled.

**Q105. Custom hooks vs HOCs vs render props – when to use each?**

Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when you need to wrap a component (e.g., code splitting, legacy compatibility). Render props: when JSX composition is specifically needed.

**Q106. How should you structure a large React application?**

Feature-based folder structure (`features/auth`, `features/dashboard`). Shared UI components in `components/`. Keep business logic in hooks/services. Clear separation between UI, state, and data layers. TypeScript for safety.

**Q107. What is colocation in React?**

Keeping related code together – state close to where it's used, styles next to components, tests next to source. Avoid premature abstraction. Move state up only when shared, not just to 'be organized'.

**Q108. What is the container/presenter pattern and is it still relevant?**

Separating data logic (container) from UI (presenter). Less strictly followed now – hooks handle data logic inside any component. But the concept of separating concerns is still valuable, enforced by custom hooks.

**Q109. How do you design a reusable button component?**

Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type` props. Use TypeScript to type them. Forward refs for DOM access. Avoid hardcoding styles – use class variants or a styling system. Compose with an icon slot.

**Q110. How do you build a reusable modal?**

Use a portal to render outside the app root. Manage open state via controlled pattern. Trap focus inside for accessibility. Close on Escape key and overlay click. Accept children for flexible content.

**Q111. What is prop inversion of control?**

Giving the consumer control over behavior by accepting render functions, state reducers, or slot components instead of hardcoding behavior. Makes components flexible without bloating their props API.

**Q112. What are headless components?**

Components that provide behavior, accessibility, and state management with no UI – consumers apply their own styles. Examples: Radix UI, Headless UI, React Aria. Powerful for design systems needing full styling control.

**Q113. How do you prevent prop explosion in complex components?**

Use compound components instead of many boolean props. Accept a config object. Use context for deeply shared state. Separate components for different variants rather than one component with 20 props.

---

## Section 8: Error Handling & Boundaries

*Making React apps resilient to failures.*

**Q114. What is an error boundary?**

A class component that implements `getDerivedStateFromError()` and/or `componentDidCatch()`. It catches rendering errors in its subtree and renders a fallback UI instead of crashing the whole app.

**Q115. How do you create an error boundary?**

Class component with `static getDerivedStateFromError(error) { return {hasError:true} }` to render fallback, and `componentDidCatch(error, info)` for logging. Render fallback UI when `hasError` is true.

**Q116. What errors can't error boundaries catch?**

Event handler errors, async code (`setTimeout`, promises), server-side rendering errors, and errors in the error boundary itself. Handle async errors with `try/catch` or `window.onerror`.

**Q117. Is there a functional equivalent of error boundaries?**

Not built-in to React as of React 18. `react-error-boundary` library provides a functional wrapper. React 19 is expected to improve this. You must use a class component or a wrapper library.

**Q118. What is the `react-error-boundary` library?**

Provides `<ErrorBoundary fallback={...}>` and `<ErrorBoundary FallbackComponent={...}>`. Also provides `useErrorBoundary()` hook to imperatively throw errors into the nearest boundary and reset it.

**Q119. Situation: A third-party component throws – how do you handle it?**

Wrap it in an error boundary. Log errors in `componentDidCatch` to a monitoring service (Sentry, Datadog). Show a friendly fallback. Optionally provide a 'Try Again' button that resets the boundary state.

**Q120. How do you handle errors in `useEffect`?**

Wrap async calls in `try/catch` inside the effect. Update an error state and render error UI. For network errors, consider retry logic (react-query handles this automatically with its error/retry API).

**Q121. What is global error monitoring in React apps?**

Pair error boundaries with a monitoring SDK (Sentry, LogRocket). Use `window.onerror` and `window.onunhandledrejection` for uncaught async errors. Error boundaries call `componentDidCatch` which logs to the service.

---

## Section 9: React 18, 19 & Concurrency

*The cutting edge of React's capabilities.*

**Q122. What is concurrent rendering?**

React can work on multiple UI versions simultaneously, pausing, aborting, or resuming renders based on priority. Urgent updates (typing) interrupt non-urgent ones (data rendering). Enabled by `createRoot()`.

**Q123. What is automatic batching in React 18?**

React 18 batches multiple `setState` calls in async contexts (`setTimeout`, Promises, native event handlers) into one re-render. Previously, only synchronous event handlers were batched. Reduces render count.

**Q124. What is `startTransition`?**

Marks a state update as non-urgent. React processes urgent updates first and defers the transition. If a newer transition comes in, the in-progress one is aborted. Used for navigation, search, filtering.

**Q125. What is `useTransition`?**

Hook version of `startTransition`. Returns `[isPending, startTransition]`. `isPending` is true while the transition is rendering. Use it to show loading spinners without setting separate loading state.

**Q126. What is `useDeferredValue`?**

Defers updating a value until after more urgent renders complete. Useful when you receive a value you can't control (e.g., from a prop) but want to defer expensive computation based on it.

**Q127. What is Suspense?**

A component that shows a fallback while children are 'suspended'. Components suspend by throwing a Promise. React catches it, shows the fallback, and retries when the Promise resolves. Used with `lazy()` and data-fetching libraries.

**Q128. What is streaming SSR?**

Sending HTML to the browser in chunks as components finish rendering on the server. Parts of the page become interactive progressively. React 18's `renderToPipeableStream` / `renderToReadableStream` enable this.

**Q129. What are React Server Components (RSC)?**

Components that run only on the server. They can directly access databases, file systems, and APIs. Their code never ships to the client. They cannot use hooks or browser APIs. They interleave with Client Components.

**Q130. RSC vs SSR – what's the difference?**

SSR renders components on the server to HTML and then hydrates on the client (components run on both). RSC components run ONLY on the server, never hydrate, and can be async. They reduce client bundle size significantly.

**Q131. What is the 'use client' directive?**

Placed at the top of a file to mark it and its imports as Client Components in the RSC architecture. Required for any component using hooks, event handlers, or browser APIs when using Next.js App Router.

**Q132. What are React 19 Actions?**

Functions that handle async mutations (form submissions, data updates). They can be synchronous or async. React 19 provides `useActionState`, `useFormStatus`, and `useOptimistic` to manage their state automatically.

**Q133. What is `useActionState` (React 19)?**

Manages state for an async action. Returns `[state, dispatch, isPending]`. On form submission, calls the action with form data, updates state with the result, and tracks pending status automatically.

**Q134. What is `useOptimistic` (React 19)?**

Shows an optimistic state update immediately while an async action is pending. When the action completes (or fails), React reverts to the actual state. Provides smooth UX without complex manual state management.

**Q135. What is `useFormStatus`?**

A hook available inside a form child component. Returns `{pending, data, method, action}` of the parent form's submission. Lets you disable inputs or show spinners without prop drilling from the form.

**Q136. Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?**

Store the raw list. Put the filter input update in urgent state. Wrap the filtered results computation in `useTransition` or `useDeferredValue`. React renders the input update immediately; filter results follow when resources free up.

---

## Section 10: Routing & Navigation

*Building navigable, URL-driven React applications.*

**Q137. How does client-side routing work?**

A router library (React Router, TanStack Router) listens to the browser history API (`pushState`, `popstate`) and renders different components based on the current URL – without full page reloads.

**Q138. What is React Router and what are its main components?**

`<BrowserRouter>` or `<RouterProvider>`: wraps the app. `<Routes>`/`<Route>`: declare URL → component mappings. `<Link>`: navigation without reload. `useNavigate()`, `useParams()`, `useSearchParams()`, `useLocation()`: hooks for router state.

**Q139. What are nested routes in React Router v6?**

Child `<Route>` elements inside a parent `<Route>`. The parent renders an `<Outlet/>` where child content appears. Enables layouts where outer shell (nav, sidebar) persists and inner content changes with URL.

**Q140. What is the `Outlet` component?**

A placeholder rendered by a parent route where its matching child route's element is shown. Enables nested layouts. Multiple outlets can be named for parallel rendering in advanced scenarios.

**Q141. What are route loaders in React Router v6.4+?**

Functions defined on routes that fetch data before the component renders. The component receives data via `useLoaderData()`. Eliminates loading spinners inside components – data is ready before render.

**Q142. What are route actions in React Router?**

Functions that handle form submissions and mutations on a route. Called when a Form is submitted to that route. Work with React Router's data APIs for full progressive enhancement.

**Q143. What is code splitting at the route level?**

Use `React.lazy()` for each route's component wrapped in `Suspense`. Only the JS for the current route loads initially. Subsequent routes load their chunk on demand – dramatically reduces initial bundle size.

**Q144. How do you protect routes (auth guards)?**

In the loader, check auth status and redirect if not authenticated. Or create a `RequireAuth` wrapper component that checks auth state and renders `<Navigate to='/login'/>` if not authenticated.

**Q145. What is the difference between `useNavigate` and `<Navigate>`?**

`useNavigate()` returns an imperative function for programmatic navigation (after form submit, in event handlers). `<Navigate>` is a component that redirects declaratively as part of JSX render output.

**Q146. What are search params and how do you use them?**

URL query string parameters (`?tab=settings&page=2`). `useSearchParams()` returns `[searchParams, setSearchParams]`. Use as UI state (tab, filter, page) so users can share/bookmark specific views.

---

## Section 11: Data Fetching & SSR / Next.js

*Getting data into React apps efficiently.*

**Q147. What are the patterns for data fetching in React?**

1. `useEffect` + fetch (basic)
2. Custom `useFetch` hook
3. React Query / SWR (recommended for server state)
4. Route loaders (React Router v6.4+)
5. Server Components with async/await (Next.js App Router)

**Q148. What is SWR?**

Stale-While-Revalidate: a data fetching hook from Vercel. Returns cached data immediately (stale), then revalidates in the background. Simple API: `const {data, error, isLoading} = useSWR(key, fetcher)`.

**Q149. What is React Query's caching model?**

Data is cached by query key. `staleTime` controls how long data is considered fresh (no background refetch). `cacheTime` controls how long unused data stays in cache. Queries refetch on window focus, reconnect, or stale threshold.

**Q150. What is optimistic mutation in React Query?**

In `useMutation`'s `onMutate`, update the cache optimistically. In `onError`, roll back via context passed from `onMutate`. In `onSettled`, invalidate/refetch to sync with server. Provides instant UI feedback.

**Q151. What is SSR with React?**

Rendering React components on the server to HTML strings. Improves FCP (First Contentful Paint) and SEO. Client then hydrates the HTML. Next.js handles SSR automatically with `getServerSideProps` or Server Components.

**Q152. What is SSG (Static Site Generation)?**

Pre-rendering pages to HTML at build time. Fastest delivery via CDN. Used for content that doesn't change per request (blogs, docs, marketing). Next.js uses `getStaticProps` and `generateStaticParams`.

**Q153. What is ISR (Incremental Static Regeneration)?**

SSG with time-based revalidation. Pages are statically generated but regenerated in the background after a specified interval. Serves stale page while regenerating fresh version. Set with `revalidate` in Next.js.

**Q154. What is the Next.js App Router?**

File-system based routing using `app/` directory with `layout.js`, `page.js`, `loading.js`, `error.js` conventions. Pages are Server Components by default. Client Components use `'use client'` directive.

**Q155. What are Next.js `loading.js` and `error.js`?**

`loading.js`: automatically wraps the page in Suspense – shown while the page is loading. `error.js`: an error boundary for the route – shown when the page throws. They are React components with special Next.js behavior.

**Q156. Situation: API data is needed in multiple components – how do you avoid duplicate fetches?**

Use React Query – same query key deduplicates concurrent requests. Or fetch at a high level (loader, server component) and pass data down. Avoid fetching the same data in sibling components independently.

**Q157. What is parallel vs sequential data fetching?**

Sequential: `await A`, then `await B` – total time = A + B. Parallel: `await Promise.all([A,B])` – total time = max(A,B). In Server Components, initiate fetches without awaiting them first, then await together.

---

## Section 12: Forms, Events & DOM Integration

*Handling user input and DOM interactions correctly.*

**Q158. Controlled vs uncontrolled forms – trade-offs in practice?**

Controlled: every keystroke updates state → always have current value for validation, but can cause re-renders. Uncontrolled with ref: only read on submit → fewer renders, but can't do real-time validation easily.

**Q159. What is React Hook Form and why is it popular?**

Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood – minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms.

**Q160. What is Formik?**

A form library providing values, errors, touched state, and handlers. Uses controlled components. Simpler API for moderate forms. Yup integration for schema validation. Slower than React Hook Form for large forms.

**Q161. How do you do form validation in React without a library?**

Track values and errors in state. Validate in `onChange` (real-time) or `onBlur` (on leave) or `onSubmit`. Set error messages in state and display them. For complex forms, a library is usually worth the dependency.

**Q162. What are synthetic events?**

React wraps native browser events in `SyntheticEvent`, providing a consistent cross-browser API. Event properties (`target`, `value`, `preventDefault`, `stopPropagation`) work identically across browsers.

**Q163. What is event delegation in React?**

React attaches a single event listener at the root DOM node and routes events to the correct handler using its internal fiber tree. Efficient: one listener handles all events instead of per-element listeners.

**Q164. What happened to event pooling?**

In React 16 and earlier, `SyntheticEvent` objects were pooled and reused – accessing event properties asynchronously returned null. React 17 removed pooling. `event.persist()` is no longer needed.

**Q165. How do you integrate a non-React library (e.g., D3, Leaflet)?**

Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it.

**Q166. What is `forwardRef`?**

`React.forwardRef((props, ref) => ...)` passes a ref from a parent through a functional component to a DOM node or child component. Required because refs are not regular props and cannot be passed through as-is.

**Q167. What is focus management and why does it matter?**

After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes.

**Q168. Situation: A dropdown closes when you click inside it – what's likely wrong?**

The click propagates to the document's mousedown handler which closes the dropdown before the button inside registers its click. Fix: call `e.stopPropagation()` on the dropdown container's mousedown, or check if click target is inside the ref.

---

## Section 13: TypeScript with React

*Writing type-safe React applications.*

**Q169. Why use TypeScript with React?**

Catches type errors at compile time (wrong prop types, missing required props). Enables autocomplete, refactoring safety, and self-documenting component APIs. Reduces runtime bugs significantly in large codebases.

**Q170. How do you type component props with TypeScript?**

Define an interface or type alias: `interface Props {name: string; onClick: () => void}`. Pass as generic to FC: `const Comp: React.FC<Props> = ({name, onClick}) => ...` or just define props inline: `function Comp({name}: Props)`.

**Q171. `React.FC` vs explicit return type – which is better?**

Explicit: `function Comp({name}: Props): JSX.Element` is more explicit about what's returned. `React.FC<Props>` implicitly types children and return. The React team no longer recommends `React.FC` – prefer explicit typing.

**Q172. How do you type `useState` with TypeScript?**

`useState<Type>(initialValue)`. For nullable: `useState<User | null>(null)`. TypeScript infers the type from initial value in simple cases; be explicit when the initial value doesn't reveal the full type.

**Q173. How do you type `useRef`?**

For DOM nodes: `useRef<HTMLInputElement>(null)` – `ref.current` can be null. For mutable values: `useRef<number>(0)` – not null. Use the appropriate overload based on usage.

**Q174. How do you type event handlers?**

`React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`. Or use inline type: `(e: React.ChangeEvent<HTMLInputElement>) => void`.

**Q175. How do you type `useReducer`?**

Define State and Action types (often a discriminated union for Action). `useReducer<Reducer<State, Action>>(reducer, initial)`. TypeScript infers dispatch type automatically.

**Q176. How do you type context?**

`createContext<ContextType | undefined>(undefined)`. In `useContext` wrapper hook, assert non-null or throw if context is undefined. This avoids the need to check for undefined in every consumer.

**Q177. What is a discriminated union and when is it useful in React?**

A union type with a common literal property ('type' or 'status') that narrows the type: `type Action = {type:'increment'} | {type:'setValue', payload:number}`. TypeScript can infer the correct shape in switch/case.

**Q178. How do you type children in React with TypeScript?**

`React.ReactNode`: anything renderable (most flexible). `React.ReactElement`: a React element only. `React.PropsWithChildren<Props>`: adds optional children to any props type. Prefer `ReactNode` for general children.

---

## Section 14: Testing React

*Writing confident tests for React components.*

**Q179. What is the testing pyramid for React?**

Unit tests (fast, many): individual functions/hooks. Integration tests (medium): component interactions, user flows. E2E tests (slow, few): full browser flows via Playwright or Cypress. Focus effort on the middle layer.

**Q180. What is React Testing Library?**

A testing library that renders components to a DOM (via jsdom) and provides user-centric queries (`getByRole`, `getByText`, `getByLabelText`). Encourages testing behavior, not implementation details.

**Q181. What are the RTL query priorities?**

Priority order: `getByRole` (most like how screen readers work) > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByDisplayValue` > `getByAltText` > `getByTitle` > `getByTestId` (last resort).

**Q182. `getBy` vs `queryBy` vs `findBy` – when do you use each?**

- `getBy`: throws if not found (use when element should exist)
- `queryBy`: returns null if not found (use for asserting absence)
- `findBy`: async, returns Promise – use when element appears after async operation

**Q183. How do you test user interactions?**

Use `userEvent` from `@testing-library/user-event` (more realistic than `fireEvent` – triggers all real browser events). `userEvent.click()`, `userEvent.type()`, `userEvent.selectOptions()`.

**Q184. How do you test async behavior (e.g., API calls)?**

Mock fetch or use MSW (Mock Service Worker). Use `findBy*` or `waitFor(() => expect(...))` to wait for async DOM updates. Never use arbitrary `setTimeout` in tests.

**Q185. What is Mock Service Worker (MSW)?**

Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly.

**Q186. How do you test custom hooks?**

Use `renderHook` from `@testing-library/react`. `act()` wraps state updates. `const {result} = renderHook(() => useCounter(0)); act(() => result.current.increment()); expect(result.current.count).toBe(1)`.

**Q187. How do you test components with context?**

Wrap with the real Provider (or a test Provider with controlled values) in the render call. RTL's `render` accepts a wrapper option: `render(<Comp/>, {wrapper: TestProviders})`.

**Q188. How do you test error boundaries?**

Suppress `console.error` in the test. Render a component that throws inside an error boundary. Assert the fallback UI renders. Use `jest.spyOn(console, 'error').mockImplementation(() => {})` to silence expected errors.

**Q189. What is the difference between shallow and deep rendering?**

Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees.

**Q190. What is Vitest and how does it differ from Jest?**

Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects.

---

## Section 15: Accessibility (a11y) in React

*Building React apps usable by everyone.*

**Q191. Why does accessibility matter in React apps?**

SPAs often break native browser accessibility (focus management, history, page titles). React renders JS-controlled UI that screen readers may not handle correctly without explicit a11y handling.

**Q192. What are ARIA roles and attributes?**

ARIA (Accessible Rich Internet Applications) attributes like `role`, `aria-label`, `aria-describedby`, `aria-expanded`, `aria-hidden` provide semantic meaning to custom components for screen readers.

**Q193. How do you manage focus after navigation in a SPA?**

After route change, programmatically move focus to the new page's heading or a skip-link target. Use a ref and `ref.current.focus()` in `useEffect` when the route changes.

**Q194. What is a focus trap?**

Confines keyboard focus within a modal/dialog so Tab doesn't reach content behind it. Required for accessible modals. Libraries: `focus-trap-react`, `@radix-ui/react-dialog` handle this automatically.

**Q195. How do you handle keyboard navigation in custom components?**

Implement `onKeyDown` for keyboard interactions (Enter/Space for activation, arrow keys for navigation, Escape to close). Follow WAI-ARIA authoring practices for each widget type (menu, dialog, tabs, combobox).

**Q196. What tools help check React app accessibility?**

- `eslint-plugin-jsx-a11y` (static analysis)
- `@axe-core/react` (runtime checks in development)
- Browser extensions: Axe DevTools, WAVE
- Lighthouse a11y audit
- Manual screen reader testing (NVDA, VoiceOver)

**Q197. What is a skip link?**

A visually hidden link at the top of the page that becomes visible on focus and links to the main content area. Allows keyboard users to skip repetitive navigation. Required for WCAG 2.1 AA compliance.

---

## Section 16: Security in React

*Common vulnerabilities and how React handles them.*

**Q198. How does React prevent XSS by default?**

React escapes all values rendered in JSX. Strings are HTML-encoded before being inserted into the DOM. You cannot accidentally inject script tags through regular JSX expressions.

**Q199. What is `dangerouslySetInnerHTML` and why is it dangerous?**

Sets raw HTML on a DOM node, bypassing React's XSS protection. If the HTML contains user input, it can execute arbitrary scripts. Always sanitize with DOMPurify before using it.

**Q200. What is a CSRF attack and how do you prevent it in React apps?**

Cross-Site Request Forgery tricks a user's browser into making authenticated requests to your API. Prevent with CSRF tokens in headers, `SameSite` cookie attribute, and not relying solely on cookies for auth.

**Q201. What is a CORS issue and how do you handle it?**

Cross-Origin Resource Sharing: browsers block requests to different origins. Configure the server to send correct `Access-Control-Allow-Origin` headers. In development, use a proxy in `vite.config` or CRA's proxy setting.

**Q202. How do you securely store auth tokens in a React app?**

HttpOnly cookies: cannot be accessed by JS, protected from XSS (but vulnerable to CSRF). `localStorage`: accessible to JS, vulnerable to XSS. Best practice: HttpOnly cookies + CSRF tokens, not `localStorage` for sensitive tokens.

**Q203. What environment variables are safe to expose in a React app?**

Only non-secret config: API base URLs, feature flags, analytics IDs. Never: API secret keys, database credentials, private keys. Vite exposes `VITE_` prefixed vars; CRA exposes `REACT_APP_` prefixed vars – all are visible in the bundle.

---

## Section 17: Build, Tooling & Ecosystem

*The infrastructure around a React application.*

**Q204. What is Vite and why is it preferred over CRA?**

Vite uses native ES modules for dev server (near-instant startup) and Rollup for production builds. Much faster than CRA's webpack-based dev server. CRA is no longer maintained.

**Q205. What is the role of Babel in a React project?**

Transpiles modern JS and JSX to browser-compatible JS. Plugins transform JSX to `createElement` calls. In Vite projects, esbuild handles transpilation faster; Babel is less common in new setups.

**Q206. What is HMR (Hot Module Replacement)?**

Replaces changed modules in the browser without full page reload. React's Fast Refresh preserves component state during HMR. Dramatically speeds up development iteration.

**Q207. What is the purpose of ESLint and Prettier in a React project?**

ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other – ESLint for rules, Prettier for style.

**Q208. What is the `eslint-plugin-react-hooks` plugin?**

Enforces Rules of Hooks: 'rules-of-hooks' (hooks only in function components/custom hooks) and 'exhaustive-deps' (all effect dependencies declared). Install in every React project.

**Q209. What is Storybook?**

A development environment for building, documenting, and testing UI components in isolation. Write stories for different component states. Used for design systems, component libraries, and visual regression testing.

**Q210. What is a monorepo and how does it relate to React projects?**

A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps.

**Q211. What is bundle analysis and how do you do it?**

Inspect what's in your production bundle to find large dependencies. Vite: `rollup-plugin-visualizer`. Webpack: `webpack-bundle-analyzer`. Look for: duplicate libraries, large unused imports, unnecessarily large dependencies.

---

## Section 18: Senior-Level Scenario Questions

*Open-ended design and debugging scenarios for experienced developers.*

**Q212. Design a real-time chat UI in React.**

WebSocket for live messages. `useEffect` to subscribe/unsubscribe. Messages in `useState` or `useReducer`. Virtualized message list for performance. Optimistic updates when sending. Error boundary for connection failures. Reconnect logic in a custom hook.

**Q213. How would you migrate a large class-based codebase to hooks?**

Incrementally – convert leaf components first, then move up. Map lifecycle methods to `useEffect` patterns. Extract shared logic to custom hooks. Maintain tests throughout. Use codemods for mechanical transforms. Don't big-bang rewrite.

**Q214. Design a form wizard with multiple steps in React.**

Store step index in state. Store all step data in a reducer or React Hook Form with a persistent form context. Each step validates before proceeding. Preserve data when navigating back. Consider URL-based step state for shareable links.

**Q215. How would you implement infinite scroll?**

Use `IntersectionObserver` to detect when a sentinel element at the bottom is visible. Trigger the next page fetch. Append results to existing list. Use React Query's `useInfiniteQuery` for built-in pagination support. Virtualize for 1000+ items.

**Q216. How would you build a drag-and-drop kanban board?**

Use `dnd-kit` or `@hello-pangea/dnd`. Model board state as `{columns: {id: {cards: []}}}`. On drag end, update state with new column/position. Optimistic updates. Sync to backend with debounce or on drop. Accessibility: keyboard drag support via dnd-kit.

**Q217. How would you architect a React app for a team of 20 developers?**

Feature-based folder structure. Shared component library (with Storybook). TypeScript throughout. Agreed state management strategy (React Query for server, Zustand for client global). ESLint + Prettier + husky pre-commit hooks. Module boundaries enforced by Nx or ESLint import rules.

**Q218. Situation: The app is slow on mobile – how do you diagnose and fix it?**

Throttle CPU in DevTools to simulate mobile. Use Lighthouse for performance audit. Check bundle size (code split aggressively). Profile renders with React DevTools. Remove render-blocking JS. Lazy load images and offscreen components. Reduce animation complexity.

**Q219. How would you implement role-based access control (RBAC) in React?**

Store user roles in auth context. Create a `usePermissions` hook that checks roles. Wrap protected components with a `Can` component or conditional rendering. Protect routes in the router (loader-level redirect). Never trust client-side checks alone – enforce on the server.

**Q220. How would you handle real-time data updates (live prices, scores)?**

WebSockets or SSE (Server-Sent Events). Custom `useWebSocket` hook managing connection lifecycle. Update local cache (`queryClient.setQueryData`) on incoming messages. Show live indicator. Handle reconnection with exponential backoff.

**Q221. How do you implement a feature flag system?**

Feature flag service (LaunchDarkly, Unleash, homegrown). Fetch flags at app init, store in context. `useFeatureFlag('feature-name')` hook returns boolean. Guard components with conditional rendering. Allow runtime flag changes without redeploy.

**Q222. Situation: A critical bug is in production – what's your process?**

Check monitoring (Sentry) for error details, affected users, first occurrence. Reproduce locally. Deploy a hotfix or feature-flag it off. Post-mortem: add a test to prevent regression. Update error boundary to catch similar errors more gracefully.

**Q223. How would you implement internationalization (i18n) in React?**

`react-intl` or `react-i18next`. Extract all strings to message catalogs. `useIntl()` hook for formatting. Support RTL layouts (`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies via Intl API. Lazy load language bundles.

**Q224. How do you ensure a React app performs well at 100k users?**

CDN for static assets. SSR/SSG for fast initial loads. Aggressive caching (React Query, HTTP cache headers). Server-side pagination, never load all data. Code splitting per route. Error boundaries everywhere. Monitoring and alerting from day one.

**Q225. How would you design a design system in React?**

Separate npm package. Primitive components (Button, Input, Text). Compound components for complex widgets. Design tokens (CSS variables). Storybook for documentation. Chromatic for visual regression. Semantic versioning with changelogs. TypeScript for consumer safety.
