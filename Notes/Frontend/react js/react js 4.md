# React.js Interview Questions — Organized by Section & Difficulty

*Deduplicated and reorganized from the original 758-question collection. Each section is split into Junior, Mid-Level, Senior, Output-Based, Scenario-Based, and Coding questions (only where applicable to that section).*

---

## Table of Contents

1. [React Fundamentals & JSX](#1-react-fundamentals--jsx)
2. [Components, Props & State](#2-components-props--state)
3. [Hooks](#3-hooks)
4. [Rendering, Virtual DOM & Reconciliation](#4-rendering-virtual-dom--reconciliation)
5. [Lists, Keys & Conditional Rendering](#5-lists-keys--conditional-rendering)
6. [Forms & Controlled Components](#6-forms--controlled-components)
7. [Context API & Prop Drilling](#7-context-api--prop-drilling)
8. [State Management (Redux, Zustand, MobX, Query)](#8-state-management-redux-zustand-mobx-query)
9. [React Router & Navigation](#9-react-router--navigation)
10. [React 18/19, Concurrency & Suspense](#10-react-1819-concurrency--suspense)
11. [SSR, Next.js & Server Components](#11-ssr-nextjs--server-components)
12. [Error Handling & Error Boundaries](#12-error-handling--error-boundaries)
13. [Performance Optimization](#13-performance-optimization)
14. [Component Design Patterns](#14-component-design-patterns)
15. [Testing React Applications](#15-testing-react-applications)
16. [TypeScript with React](#16-typescript-with-react)
17. [Accessibility (a11y)](#17-accessibility-a11y)
18. [Security](#18-security)
19. [React Native](#19-react-native)
20. [Ecosystem, Libraries & i18n](#20-ecosystem-libraries--i18n)
21. [Build Tools & Developer Experience](#21-build-tools--developer-experience)
22. [Architecture & System Design](#22-architecture--system-design)
23. [Coding Exercises (Build-From-Scratch)](#23-coding-exercises-build-from-scratch)

---

## 1. React Fundamentals & JSX

### Junior
1. **What is React?** A declarative, component-based JavaScript library (by Meta) for building UIs. It uses a virtual DOM, unidirectional data flow, and JSX.
2. **What is JSX?** A syntax extension that lets you write HTML-like markup in JS. It compiles (via Babel) to `React.createElement()` calls (or the automatic `jsx()` runtime in React 17+), producing plain JS objects.
3. **Do browsers understand JSX?** No — a transpiler like Babel is required to convert JSX to plain JavaScript.
4. **What is the Virtual DOM?** An in-memory, lightweight copy of the real DOM. React diffs the new virtual DOM against the previous one and applies only the minimal necessary changes to the real DOM, which is expensive to manipulate directly.
5. **What are the rules of JSX?** Return a single root element (or Fragment), close every tag explicitly, and use camelCase for attribute names (`className`, `tabIndex`) except `aria-*`/`data-*`.
6. **Why does React use `className` instead of `class`?** `class` is a reserved JS keyword; since JSX compiles to JS object literals, `class` would conflict, so React uses `className` (mirroring the DOM API `element.className`).
7. **Can you use React without JSX?** Yes — JSX is sugar for `React.createElement(type, props, ...children)`.
8. **How do you write comments in JSX?** Wrap standard JS comments in curly braces: `{/* comment */}`.
9. **What are React Fragments and why use them?** `<Fragment>` / `<>...</>` group multiple children without adding an extra DOM node — useful to avoid breaking CSS layouts (flex/grid) or creating invalid HTML.
10. **Why must component names start with a capital letter?** JSX treats lowercase tag names as native HTML/SVG elements; a capitalized name tells JSX to treat it as a custom component.
11. **What is the difference between an Element and a Component?** An element is a plain, immutable JS object describing what to render (`{type, props}`). A component is a function/class that returns elements.
12. **What are the major features of React?** Component-based architecture, Virtual DOM, JSX, unidirectional data flow, Hooks, Context API, Suspense/concurrent rendering, and support for SSR/Server Components.

### Mid-Level
13. **What does JSX compile to?** `React.createElement(type, props, ...children)` pre-React 17, or the automatic `jsx()`/`jsxs()` runtime import from `react/jsx-runtime` in React 17+ (no need to import React just for JSX).
14. **How does the new JSX transform differ from the old one?** The new transform auto-imports `jsx` from `react/jsx-runtime`, so you no longer need `import React from 'react'` purely to use JSX (you still need it for Hooks).
15. **How does JSX prevent injection (XSS) attacks?** React DOM escapes any value embedded in JSX (`{}`) before rendering, converting it to a string — you can't inject raw HTML/scripts through normal interpolation.
16. **How do you conditionally apply class names?** Move the ternary outside the string: `className={'btn ' + (visible ? 'show' : 'hidden')}` or a template literal.
17. **What is `React.Fragment` with a key used for?** Rendering a keyed list of grouped elements without a wrapper `div` — only `<React.Fragment key={}>` supports the `key` prop, not the `<>` shorthand.
18. **What's the difference between imperative and declarative UI code?** Imperative code manually walks through steps to mutate the DOM based on current state; declarative code (React) just describes the desired UI for a given state and lets React compute the diff.
19. **What is `dangerouslySetInnerHTML`?** React's replacement for `innerHTML`; it accepts `{ __html: string }` and bypasses XSS protection — sanitize any HTML before use.

### Senior
20. **How does ReactJS work behind the scenes (render → reconciliation → commit)?** Components execute to build a virtual DOM tree; React's Fiber architecture reconciles (diffs) the new tree against the previous one in an interruptible render phase; then applies minimal DOM mutations in an uninterruptible commit phase and runs effects.
21. **What is the reason multiple JSX elements must be wrapped in one parent?** JSX transpiles to function calls; a function/component can't return multiple sibling objects without wrapping them in an array or single parent (or Fragment).
22. **Why is `react-dom` a separate package from `react`?** To decouple the core reconciliation/component model from any specific rendering target, enabling `react-native`, `react-art`, SSR (`react-dom/server`), etc., to share the same core.

### Output-Based
23. **What happens with `<div mycustomattribute="x" />` in modern React?** Since React 16, unknown DOM attributes pass through to the rendered DOM instead of being stripped.
24. **What does `<label for="user">` render/warn as?** A console warning and the `for` attribute is dropped — use `htmlFor` instead, since `for` is a reserved JS word.

---

## 2. Components, Props & State

### Junior
25. **What is state in React?** A component-owned, mutable-via-setter object that persists across renders; changing it triggers a re-render. Managed via `useState`/`useReducer` (function components) or `this.state` (class components).
26. **What are props?** Read-only inputs passed from parent to child, similar to HTML attributes, used to configure and customize child components.
27. **Difference between props and state:** Props are immutable and passed down from a parent; state is local, mutable (via setter), and owned by the component itself.
28. **How do you create components?** Function components (plain JS functions returning JSX, the modern default) or class components (`extends React.Component` with a `render()` method).
29. **What is the `children` prop?** A special prop containing whatever is nested between a component's opening and closing tags — used for layout/wrapper components.
30. **What are default props?** A `defaultProps` static property (or default parameter values in function components) used when a prop is `undefined`. Note: `null`/`0` are NOT replaced by defaults.
31. **Why can't you mutate props?** React enforces a "pure function" contract — components must never modify their own props; data flows one-way from parent to child.
32. **What are controlled vs. presentational (stateless) components?** Presentational components render UI based purely on props with no internal state; container/stateful components manage state and pass data down.

### Mid-Level
33. **What is "lifting state up"?** Moving shared state to the closest common ancestor of the components that need it, instead of duplicating local state in siblings.
34. **What are Higher-Order Components (HOCs)?** Functions that take a component and return a new, enhanced component — used to share cross-cutting logic (e.g., data fetching, auth checks) between components.
35. **What is prop drilling and how do you avoid it?** Passing props through many intermediate components that don't need them, just to reach a deeply nested child. Fixes: Context API, state management libraries, or restructuring via component composition.
36. **How do you update objects/arrays in state immutably?** Spread syntax (`{...obj, key: val}`, `[...arr, item]`) or `Array.prototype.map/filter/slice` instead of mutating methods like `push`/`splice`; libraries like Immer simplify this with mutable-looking syntax.
37. **What are React Portals and when do you use them?** `ReactDOM.createPortal(child, domNode)` renders children into a DOM node outside the parent hierarchy while keeping them in the React tree (context, event bubbling still work) — used for modals, tooltips, and dropdowns to escape `overflow:hidden`/`z-index` issues.
38. **What is `React.memo`?** A HOC that memoizes a function component, skipping re-render if props are shallow-equal to the previous render — the functional equivalent of `PureComponent`.
39. **What are Pure Components?** Components (`React.PureComponent` for classes, `React.memo` for functions) that automatically skip re-rendering when props/state are shallow-equal to the previous render.
40. **What is the `key` prop's purpose beyond lists?** It also forces React to treat two renders as different component instances (unmount/remount) if the key changes — useful for intentionally resetting internal state.

### Senior
41. **How would you design a reusable, prop-explosion-resistant component (e.g., a Button or Modal)?** Use compound components or config objects instead of dozens of booleans; support both controlled and uncontrolled usage; forward refs for DOM access; separate variants into styling tokens rather than conditional logic.
42. **How do you prevent prop explosion in complex components?** Compound components, context for deeply shared state, accepting a single config object, or splitting into distinct components per variant instead of one component with 20 props.
43. **What are the limitations of HOCs?** Don't create them inside `render()` (causes remount every render); static methods aren't copied automatically; refs don't pass through without `forwardRef`.

### Output-Based
44. **State mutation directly:**
```jsx
function App() {
  const [items, setItems] = useState([1, 2, 3]);
  function addItem() {
    items.push(4);       // direct mutation
    setItems(items);     // same reference!
  }
  // clicking "Add" may not re-render — React's shallow check sees the same array reference.
  // Fix: setItems([...items, 4])
}
```
45. **Object state partial update:**
```jsx
setCount(5); setCount(5); setCount(5);
// Re-renders ONCE — React batches updates, and since the value is unchanged (Object.is), it may bail out entirely.
```
46. **Nested function components defined inside a parent's render:**
```jsx
function Parent() {
  const Child = () => <div>child</div>; // defined INSIDE render — new type every render!
  return <Child />;
  // Every re-render creates a new component type → React unmounts/remounts Child each time. Move Child outside Parent.
}
```
47. **Event bubbling through a Portal:** A `stopPropagation()` call inside a portal-rendered modal still stops the click from reaching a React-tree ancestor's `onClick`, even though the portal's DOM node lives outside that ancestor — because React bubbles events along the **React tree**, not the DOM tree.

### Scenario-Based
48. **API data is needed in multiple sibling components — how do you avoid duplicate fetches?** Fetch once at a common ancestor and pass down, or use a caching data-fetching library (React Query/SWR) where the same query key deduplicates concurrent requests automatically.
49. **A third-party component throws an error — how do you handle it?** Wrap it in an Error Boundary, log to a monitoring service in `componentDidCatch`, and show a friendly fallback with a retry option.
50. **Two components on different branches of the tree need the same data.** Lift state to the nearest common ancestor, use Context, a global store, or a shared React Query cache key.

---

## 3. Hooks

### Junior
51. **What is a Hook?** A function that lets you "hook into" React state/lifecycle features from function components (e.g., `useState`, `useEffect`). Introduced in React 16.8 to avoid needing classes for state.
52. **What are the Rules of Hooks?** (1) Only call Hooks at the top level — never inside loops, conditions, or nested functions. (2) Only call Hooks from React function components or custom Hooks.
53. **What is `useState`?** Returns `[value, setter]`; calling the setter schedules a re-render with the new value. Can accept a function for lazy initialization (runs once, on mount).
54. **What is `useEffect`?** Runs side effects (data fetching, subscriptions, DOM manipulation) after render. Dependency array controls timing: `[]` = once on mount, `[a,b]` = when `a`/`b` change, omitted = every render.
55. **What is the `useEffect` cleanup function?** A function returned from the effect, run before the next effect execution or on unmount — used to clear timers, unsubscribe, cancel fetches, or remove listeners.
56. **What is `useRef`?** Returns a mutable `{current}` object that persists across renders without causing re-renders when changed. Used for DOM node access or storing instance-like values (timers, previous values).
57. **What is `useContext`?** Subscribes a component to a Context value, re-rendering when it changes — eliminates prop drilling.
58. **Can Hooks be used in class components?** No — Hooks only work in function components (or other Hooks), since they rely on stable call order across renders, which classes don't guarantee the same way.
59. **What is a custom Hook?** A function starting with `use` that calls other Hooks internally, extracting and sharing reusable stateful logic (e.g., `useFetch`, `useDebounce`) without changing the component tree.

### Mid-Level
60. **`useMemo` vs `useCallback` — what's the difference?** `useMemo(() => computeValue(), deps)` memoizes a **computed value**; `useCallback(fn, deps)` memoizes a **function reference** itself. `useCallback(fn, deps)` is equivalent to `useMemo(() => fn, deps)`.
61. **What is `useReducer` and when do you prefer it over `useState`?** `const [state, dispatch] = useReducer(reducer, initialState)` — better for complex state with multiple sub-values, when next state depends on the action type, or when you want predictable, testable transitions (Redux-like pattern locally).
62. **What is `useLayoutEffect` and how does it differ from `useEffect`?** Same API, but fires synchronously after DOM mutations and *before* the browser paints — used for reading layout (measurements) and making synchronous DOM adjustments to avoid visual flicker. `useEffect` is non-blocking and runs after paint.
63. **What is `forwardRef`?** `React.forwardRef((props, ref) => ...)` lets a function component accept and forward a `ref` to an inner DOM node or child, since `ref` isn't a normal prop.
64. **What is `useImperativeHandle`?** Used with `forwardRef` to customize what a parent's ref exposes on a child (e.g., only `open()`/`close()` methods) rather than the raw DOM node.
65. **What are stale closures and how do they happen in `useEffect`?** An effect captures variables from the render it was created in; if the dependency array is incomplete, subsequent updates to those variables aren't seen inside the effect. Fix: add to deps or use a ref for "latest value" access.
66. **What is `useId`?** Generates a stable, unique ID consistent between server and client renders — for accessibility attributes (`htmlFor`, `aria-labelledby`) needing to match across hydration.
67. **What is lazy initialization in `useState`?** Passing a function (`useState(() => expensiveCalc())`) so the initial value is computed only once on mount, not on every render.
68. **Why use functional updates (`setState(prev => ...)`)?** Ensures you're operating on the latest state rather than a value captured in a stale closure — critical when calling the setter multiple times in one handler or inside async code.
69. **What is `useDeferredValue`?** Returns a deferred copy of a value that lags behind during expensive re-renders, keeping the UI (e.g., an input) responsive while an expensive computation catches up.
70. **What is `useTransition`?** Returns `[isPending, startTransition]`; marks a state update as non-urgent so React prioritizes urgent updates (like typing) and shows `isPending` while the transition renders.

### Senior
71. **How does `useState` work internally?** React keeps a per-component list ("hook list") of slots indexed by call order; each `useState` call reads/writes its slot. This is why hook order must stay identical across renders — React has no other way to match calls to state.
72. **How would you build a custom hook library for a team?** Design small, composable hooks with clear return shapes, document with TypeScript types, keep pure functions honoring the Rules of Hooks, unit test with React Testing Library, and version/publish via an internal npm registry.
73. **How would you migrate a large class-based codebase to hooks?** Incrementally, starting from leaf components upward; map lifecycle methods to `useEffect` equivalents; extract shared logic into custom hooks; keep tests green throughout; consider codemods for mechanical parts.
74. **What are the differences between `useEffect` and the experimental `useEvent`/Effect Event pattern?** `useEvent`-style patterns create a stable function reference that always reads the latest props/state without needing to be listed as a dependency — solving the "stable callback with fresh closure" problem that plain `useCallback` can't.
75. **When does `useLayoutEffect` cause layout thrashing?** When you repeatedly read then write layout properties (e.g., `offsetHeight` then setting `style.height` then reading `offsetHeight` again) inside it — each read after a write forces a synchronous reflow, blocking the main thread.

### Output-Based
76. **Calling a hook conditionally:**
```jsx
if (flag) {
  const [extra, setExtra] = useState(0); // Rules of Hooks violation!
}
// React throws: "Rendered more hooks than during the previous render."
```
77. **Multiple `setState` calls with functional updates in one handler:**
```jsx
function handleClick() {
  setCount(prev => prev + 1);
  setCount(prev => prev + 1);
  setCount(prev => prev + 1);
}
// Count increments by 3 — each functional updater receives the latest queued value (0→1→2→3).
```
78. **State update is asynchronous / stale closure:**
```jsx
function handleClick() {
  setCount(count + 1);
  setCount(count + 1);
  setCount(count + 1);
  console.log(count); // logs the OLD value (e.g. 0)
}
// All three calls read the same stale `count` from the closure — count ends up +1, not +3.
```
79. **`useEffect` infinite loop:**
```jsx
useEffect(() => {
  setCount(count + 1); // updates a dependency of itself
}, [count]);
// Infinite re-render loop. Fix: functional update + [] deps, or restructure logic.
```
80. **Stale closure in a `setInterval` inside `useEffect`:**
```jsx
useEffect(() => {
  const id = setInterval(() => console.log('count is', count), 1000);
  return () => clearInterval(id);
}, []); // missing `count` dependency
// Always logs the count from mount time (e.g. 0), never updates.
```
81. **Two components using the same custom hook — do they share state?** No. Each call to a custom hook creates its own independent `useState`/`useEffect` instances. Custom hooks share *logic*, never *state*.
82. **`useEffect` vs `useLayoutEffect` paint timing:** `useLayoutEffect` runs and can update the DOM *before* the browser paints (no flicker, but blocks rendering); `useEffect` runs *after* paint (non-blocking, possible one-frame flicker if it mutates the DOM).
83. **Returning a Promise from `useEffect`:**
```jsx
useEffect(async () => { await fetchData(); }, []); // anti-pattern
// React expects undefined or a cleanup function, not a Promise — warns in console. Wrap the async logic in an inner function instead.
```

### Coding
84. **Implement `useDebounce`:**
```jsx
function useDebounce(value, delay = 300) {
  const [debounced, setDebounced] = useState(value);
  useEffect(() => {
    const t = setTimeout(() => setDebounced(value), delay);
    return () => clearTimeout(t);
  }, [value, delay]);
  return debounced;
}
```
85. **Implement `useFetch` (loading/error/data):**
```jsx
function useFetch(url) {
  const [state, setState] = useState({ data: null, loading: true, error: null });
  useEffect(() => {
    const controller = new AbortController();
    setState({ data: null, loading: true, error: null });
    fetch(url, { signal: controller.signal })
      .then(r => r.json())
      .then(data => setState({ data, loading: false, error: null }))
      .catch(err => { if (err.name !== 'AbortError') setState({ data: null, loading: false, error: err }); });
    return () => controller.abort();
  }, [url]);
  return state;
}
```
86. **Implement `usePrevious`:**
```jsx
function usePrevious(value) {
  const ref = useRef();
  useEffect(() => { ref.current = value; }, [value]);
  return ref.current; // holds value from the PREVIOUS render, since effects run after commit
}
```
87. **Implement `useClickOutside`:**
```jsx
function useClickOutside(callback) {
  const ref = useRef(null);
  useEffect(() => {
    function handler(e) {
      if (ref.current && !ref.current.contains(e.target)) callback(e);
    }
    document.addEventListener('mousedown', handler);
    return () => document.removeEventListener('mousedown', handler);
  }, [callback]);
  return ref;
}
```
88. **Implement `useLocalStorage`:**
```jsx
function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    try { const item = localStorage.getItem(key); return item ? JSON.parse(item) : initialValue; }
    catch { return initialValue; }
  });
  const setStoredValue = useCallback((newValue) => {
    setValue(prev => {
      const resolved = newValue instanceof Function ? newValue(prev) : newValue;
      localStorage.setItem(key, JSON.stringify(resolved));
      return resolved;
    });
  }, [key]);
  return [value, setStoredValue];
}
```

---

## 4. Rendering, Virtual DOM & Reconciliation

### Junior
89. **What is reconciliation?** React's process of comparing the new virtual DOM tree with the previous one (diffing) and computing the minimal set of real-DOM updates needed.
90. **What is the diffing algorithm's complexity and why?** Heuristic O(n) instead of the theoretically optimal O(n³), based on two assumptions: elements of different types produce different trees, and `key` gives stable identity to list children.
91. **What are synthetic events?** `SyntheticEvent` is React's cross-browser wrapper around native events, with the same API (`stopPropagation`, `preventDefault`) working identically across browsers. `nativeEvent` gives access to the underlying browser event.
92. **How is React different from HTML in event handling?** camelCase names (`onClick` not `onclick`), pass a function reference (not a string), and must call `event.preventDefault()` explicitly instead of `return false`.

### Mid-Level
93. **What is React Fiber?** A reimplementation of React's reconciliation algorithm (since React 16) that breaks rendering work into small interruptible units, enabling pausing, prioritization, and concurrent rendering.
94. **What is the difference between the render phase and commit phase?** Render phase: React calls component functions and reconciles — pure, interruptible, may be paused/aborted. Commit phase: DOM mutations are applied and `useLayoutEffect`/`useEffect` run — synchronous, non-interruptible.
95. **What is event delegation in React?** React attaches a single listener at the root and routes events internally via the fiber tree, instead of one listener per DOM element — more efficient than native per-node listeners.
96. **What happened to event pooling?** Removed in React 17+; `SyntheticEvent` objects are no longer reused/nullified after the handler, so `event.persist()` is no longer necessary.

### Senior
97. **Explain React Fiber's architecture in detail.** Each component maps to a Fiber node (type, props, state, effect tags, parent/child/sibling links) forming a Fiber tree. React maintains a "current" tree (on screen) and a "work-in-progress" tree (being built) — double buffering. Work is split into units scheduled by priority; low-priority work can be paused to handle urgent updates (e.g., user input), then resumed.
98. **What is the main goal of Fiber?** Incremental, interruptible, and prioritizable rendering — enabling concurrent features, Suspense, and smoother animations/gestures by not blocking the main thread on large renders.

### Output-Based
99. **Nested render order:**
```jsx
function Parent() { console.log('Parent'); return <Child />; }
function Child() { console.log('Child'); return <GrandChild />; }
function GrandChild() { console.log('GrandChild'); return <div/>; }
// Logs top-down: Parent, Child, GrandChild — React renders parents before children, then commits the whole tree at once.
```

---

## 5. Lists, Keys & Conditional Rendering

### Junior
100. **What is the `key` prop and why does it matter?** A unique string/number identifying list items across renders — lets React correctly match, reorder, insert, or remove DOM nodes and state instead of guessing by position.
101. **What are the conditions to safely use array index as a key?** Only when the list is static (never reordered/filtered/inserted), items have no stable ID, and the list order never changes.
102. **How do you conditionally render in JSX?** Short-circuit with `&&` for if-only cases, a ternary for if/else, or early `return null` to render nothing.

### Mid-Level
103. **Why avoid array index as a key when the list can reorder?** Index keys are tied to *position*, not *identity* — on reorder/insert/delete, React may reuse the wrong DOM node (and its internal state, like uncontrolled input values) for a different item.
104. **Should keys be globally unique?** No — only unique among siblings in the same array. The same key can safely reuse across different arrays/components.
105. **What is the diffing algorithm's rule set?** (1) Different element types → tear down and rebuild the subtree. (2) Same DOM type → keep the node, patch changed attributes. (3) Same component type → keep the instance, update props, re-render. (4) Children are diffed via `key` matching, falling back to index if no key.

### Output-Based
106. **Index-as-key with items prepended to the front:**
```jsx
// key={index}: prepending an item shifts all indices — React reuses old DOM nodes for the WRONG items,
//   e.g. an uncontrolled <input defaultValue> ends up showing stale text tied to the wrong item.
// key={item.id}: correctly mounts a new node for the new item; other items' input state stays put.
```
107. **Missing `key` prop:** React logs a console warning and falls back to index-based reconciliation, risking incorrect state reuse if the list changes shape.

---

## 6. Forms & Controlled Components

### Junior
108. **Controlled vs. uncontrolled components?** Controlled: the input's value is driven by React state (`value` + `onChange`) — React is the single source of truth. Uncontrolled: the DOM holds the value itself; React reads it via a `ref` only when needed (e.g., on submit).
109. **How do you set a default/initial value for an uncontrolled input?** Use `defaultValue` (or `defaultChecked` for checkboxes/radios) instead of `value`, so React only sets it on the initial render.

### Mid-Level
110. **What are the trade-offs between controlled and uncontrolled forms?** Controlled: real-time validation, conditional disabling of submit, enforced input formatting — but more re-renders (one per keystroke). Uncontrolled: fewer re-renders and simpler for "read-once-on-submit" cases, but no live validation without refs/extra listeners.
111. **How do you implement form validation without a library?** Track `values` and `errors` in state; validate in `onChange` (real-time), `onBlur` (on leave), or `onSubmit`; display error messages conditionally from the `errors` object.

### Senior
112. **How would you design a controlled component pattern for a reusable component library?** Support *both* modes: the component manages its own internal state by default (uncontrolled/"autopilot"), but accepts optional `value`/`onChange` props to become fully parent-controlled when supplied — check `value !== undefined` to decide which mode is active.

---

## 7. Context API & Prop Drilling

### Junior
113. **What is the Context API?** A built-in mechanism (`createContext`, `Provider`, `useContext`) for sharing values (theme, auth, locale) across the tree without manually passing props at every level.
114. **What is prop drilling?** Passing props through intermediate components that don't need them, purely to reach a deeply nested descendant.

### Mid-Level
115. **When should you use Context vs. Redux/Zustand?** Context: simple, low-frequency shared values (theme, auth user, locale). Redux/Zustand: complex update logic, frequent updates, middleware needs, or when many unrelated consumers must avoid re-rendering on unrelated state changes.
116. **How does Context cause performance issues, and how do you fix it?** Any Provider value change re-renders **all** consumers, even ones using only part of the object; a new object literal (`value={{...}}`) is created on every render, breaking reference equality. Fixes: `useMemo` the value, split into multiple smaller contexts by concern, or move high-frequency state to a selector-based store.
117. **What's a common pitfall with `useContext` and objects?** Bundling unrelated state (`user`, `theme`) into one context object — updating either causes every consumer to re-render regardless of which piece they actually use. Split contexts by concern instead.
118. **When should you NOT use Context for state?** For rapidly changing values (mouse position, animation frames, form inputs) — every keystroke re-renders every consumer. Use a dedicated store with fine-grained subscriptions instead (Zustand, Jotai).

### Senior
119. **How do you keep a user authenticated across page refreshes using Context?** Wrap the app with the auth Provider at the top level (e.g., in `index.js`, outside `App`), and dispatch a `loadUser()` action inside a `useEffect` in `App` so it runs on every mount/reload regardless of route.

### Output-Based
120. **Context value re-renders all consumers even for the same conceptual value:**
```jsx
<ThemeContext.Provider value={{ color: 'blue' }}> {/* new object every render */}
// Every setTheme({color:'blue'}) call — even with unchanged data — creates a NEW object reference,
// so ALL consumers re-render. Fix: useMemo(() => ({color}), [color]).
```
121. **No matching Provider in the tree:** `useContext(SomeContext)` returns the `defaultValue` passed to `createContext(defaultValue)` — or `undefined` if no default was given.

---

## 8. State Management (Redux, Zustand, MobX, Query)

### Junior
122. **What is Redux?** A predictable state container: a single global store (source of truth), read-only state changed only via dispatched actions, and pure reducer functions that compute the next state.
123. **What is an action in Redux?** A plain JS object with a required `type` field describing what happened, optionally carrying a payload.
124. **What is a reducer?** A pure function `(state, action) => newState` that computes the next state without mutating the previous one or performing side effects.
125. **What is Redux Toolkit (RTK) and why is it recommended?** The official, opinionated Redux toolset: `configureStore` (sensible defaults + DevTools), `createSlice` (auto-generates actions/reducers, uses Immer for mutable-looking immutable updates), and `createAsyncThunk` for async logic — drastically reduces boilerplate versus plain Redux.

### Mid-Level
126. **What is `useReducer` vs `useState`?** `useReducer` centralizes complex state transitions in one function via dispatched actions — better when state has multiple sub-values or next state depends on the action type; `useState` is simpler for independent, unrelated values.
127. **What are Redux selectors, and why use Reselect?** Selectors compute derived data from state; Reselect memoizes them so they only recompute when their specific input arguments change, keeping the store minimal and avoiding unnecessary re-renders.
128. **What is Redux Thunk vs Redux Saga?** Thunk: action creators return functions (`dispatch`, `getState` access) for simple async logic using Promises — simple, minimal API. Saga: generator-based middleware for complex async flows (cancellation, race conditions, sequencing) — more powerful, steeper learning curve.
129. **What is React Query (TanStack Query) / SWR, and why use them over manual `useEffect` fetching?** Purpose-built server-state libraries providing caching, deduplication of concurrent requests, background refetching, and stale-while-revalidate semantics — solving problems manual `fetch`-in-`useEffect` doesn't (race conditions, cache invalidation, refetch-on-focus).
130. **Server state vs. client state — what's the difference?** Server state (API-fetched data) needs caching, refetching, and synchronization across components — best handled by React Query/SWR. Client state (UI toggles, form values) is synchronous and local — `useState`/Context/Zustand suffice.
131. **What is Zustand and how does it differ from Redux?** A minimal hook-based store with no reducers/actions boilerplate — plain objects with setter functions; components subscribe to specific slices, avoiding unnecessary re-renders, with a much smaller API surface than Redux.

### Senior
132. **Compare Redux, MobX, Recoil/Jotai, Zustand, and Context for a large-scale app.** Redux (RTK): battle-tested, best DevTools/time-travel debugging, most boilerplate (mitigated by RTK), best for large teams needing strict patterns. MobX: less boilerplate via mutable observables, can be less predictable at scale. Recoil/Jotai: atomic, fine-grained, React-native mental model, newer ecosystem. Zustand: minimal API, great performance, good for medium complexity. Context: built-in, fine for infrequent/low-fanout updates only.
133. **How does Redux Toolkit work internally?** `createSlice` composes `createReducer`+`createAction`, using Immer under the hood so "mutating" `state.x = y` inside a reducer is actually translated into an immutable update via a Proxy-based draft state. `createAsyncThunk` auto-dispatches `pending`/`fulfilled`/`rejected` actions for a Promise-returning function.
134. **What is optimistic mutation, and how would you implement it with React Query?** Update the UI/cache immediately assuming success (`onMutate`), roll back via a snapshot if the request fails (`onError`), and reconcile with the server response (`onSettled`) — improves perceived responsiveness for common CRUD actions.
135. **How would you design state management for a complex analytics dashboard (real-time data, many independently-refreshable widgets, large datasets)?** RTK with `createEntityAdapter` for normalized data; `createAsyncThunk` with `AbortController` for cancellable fetches; a WebSocket middleware dispatching real-time updates; memoized Reselect selectors; local component state for widget-only UI (expanded/collapsed); virtualization for large lists; `React.memo` for widgets receiving stable props.

### Scenario-Based
136. **Redux vs. Context vs. Zustand — how do you decide for a large-scale app?** Context for rarely-changing app-wide values (theme, auth); Zustand when Redux feels heavy but Context too limited (medium complexity, need for selectors); Redux Toolkit for enterprise apps with complex async flows, multiple teams, and a need for time-travel debugging.

---

## 9. React Router & Navigation

### Junior
137. **What is React Router?** The standard client-side routing library for React SPAs — maps URL paths to components without full page reloads, using the browser History API.
138. **What are the core components/hooks of React Router v6?** `<BrowserRouter>` (wraps the app), `<Routes>`/`<Route>` (URL → component mapping), `<Link>`/`<NavLink>` (navigation), and hooks `useNavigate`, `useParams`, `useSearchParams`, `useLocation`.
139. **How do you implement a 404/NotFound page?** Add a catch-all `<Route path="*" element={<NotFound />} />` at the end of your route list.

### Mid-Level
140. **What are nested routes and the `<Outlet>` component?** Child `<Route>` elements inside a parent route; the parent renders `<Outlet/>` as a placeholder where the matched child's content appears — enables persistent layouts (nav/sidebar) with swappable inner content.
141. **`useNavigate` vs `<Navigate>` — when to use each?** `useNavigate()` is imperative (call it in event handlers/effects, e.g. after a form submits); `<Navigate>` is declarative (render it conditionally in JSX to redirect during render).
142. **What are route loaders (React Router 6.4+)?** Functions attached to routes that fetch data *before* the route's component renders; the component reads it via `useLoaderData()` — removes in-component loading spinners for initial data.
143. **How do you protect routes (auth guards)?** Wrap protected routes in a component that checks auth state and renders `<Navigate to="/login" />` if unauthenticated, or check auth inside a route loader and redirect there.
144. **How do you read query/search params?** `useSearchParams()` returns `[searchParams, setSearchParams]`, an interface over `URLSearchParams` — useful as UI state that's shareable/bookmarkable (tabs, filters, pagination).

### Senior
145. **How does client-side routing work under the hood?** The router intercepts navigation, updates the URL via the History API (`pushState`/`replaceState`) without a full reload, listens for `popstate`, and re-renders the component tree matching the new path.

---

## 10. React 18/19, Concurrency & Suspense

### Junior
146. **What is `createRoot()` and why replace `ReactDOM.render()`?** `createRoot()` (React 18+) opts an app into concurrent features (automatic batching, transitions, improved Suspense). `ReactDOM.render()` runs in legacy mode without them.
147. **What is Suspense?** A component that shows a fallback UI while its children are "suspended" (e.g., loading code via `React.lazy` or async data) — the child "throws" a Promise, React catches it, shows the fallback, and retries on resolution.
148. **What is `React.lazy`?** `React.lazy(() => import('./Comp'))` lazily loads a component's code on first render, suspending until the chunk downloads — must be wrapped in `<Suspense fallback={...}>`.

### Mid-Level
149. **What is automatic batching in React 18, and how does it differ from React 17?** React 18 batches all `setState` calls within the same tick — even inside `setTimeout`, Promises, or native event handlers — into a single re-render. React 17 only batched inside React's own synthetic event handlers.
150. **How do you opt out of automatic batching when needed?** `flushSync(() => setState(...))` from `react-dom` forces an immediate, synchronous DOM flush for that specific update.
151. **What is `useTransition` used for?** Marking a state update as non-urgent so React can interrupt it in favor of higher-priority updates (like typing); `isPending` lets you show a loading indicator without manual loading state.
152. **What is `useDeferredValue` and how does it differ from `useTransition`?** `useDeferredValue` wraps a *value* you don't control the update of (e.g., a prop); `useTransition` wraps a *state update* you do control (via `startTransition`). Both let urgent UI stay responsive while expensive work is deferred.

### Senior
153. **What are React 19's key additions?** The React Compiler (automatic memoization, reducing manual `useMemo`/`useCallback`/`React.memo`), Server Actions (`'use server'` functions callable from Client Components), `useActionState`/`useFormStatus`/`useOptimistic` for form/action UX, the `use()` hook for reading Promises/Context during render (can be called conditionally, unlike other hooks), and built-in document metadata support (`<title>`, `<meta>` inside components).
154. **What is `useOptimistic`?** Shows an optimistic UI update immediately while an async action is pending, automatically reverting to actual state if the action fails — removes manual "pending item" state management.
155. **What is streaming SSR and how does React 18+ improve it?** HTML is streamed to the client in chunks as it becomes ready, instead of waiting for the whole page; `<Suspense>` boundaries let slow parts stream in later with a fallback shown first, and hydration can happen progressively/selectively per boundary rather than all at once.

### Output-Based
156. **Automatic batching inside a native event handler (React 18):**
```jsx
<button onClick={() => { setA(1); setB(2); }}>Click</button>
// Logs ONE render, not two — React 18 batches automatically everywhere, including native handlers.
```
157. **`useDeferredValue` keeping an input responsive:** The input updates immediately on every keystroke (urgent); the deferred value (and anything computed from it, like search results) lags behind and updates once React has spare capacity — so typing never feels sluggish even with expensive downstream rendering.

---

## 11. SSR, Next.js & Server Components

### Junior
158. **What is server-side rendering (SSR)?** Generating the initial HTML on the server per request and sending it to the browser, so content is visible before JS loads/executes — improves perceived performance and SEO versus a blank-shell client-side render.
159. **What is hydration?** The process where React attaches event listeners and reconciles server-rendered static HTML with the client-side virtual DOM, making it interactive.
160. **CSR vs. SSR vs. SSG vs. ISR — what's the difference?** CSR: all rendering happens in the browser (fast interactions after load, poor initial SEO/TTI). SSR: server renders per request (good SEO, slower TTFB under load). SSG: HTML pre-built at build time (fastest delivery, best for rarely-changing content). ISR: SSG pages regenerated in the background after a revalidation interval — combines SSG speed with SSR-like freshness.

### Mid-Level
161. **What causes hydration mismatches, and how do you fix them?** The server-rendered HTML differs from what the client initially computes — common causes: timestamps/`Date.now()`, `Math.random()`, browser-only APIs (`window`, `localStorage`) used during initial render. Fixes: move such logic into `useEffect` (client-only), or use `suppressHydrationWarning` for known-harmless mismatches.
162. **What is the Next.js App Router, and how does it differ from the Page Router?** File-system routing via `app/` (vs. `pages/`); components are Server Components by default (vs. all Client Components); native nested layouts (`layout.js`) and built-in `loading.js`/`error.js` for Suspense/error boundaries per route; native async data fetching with `fetch`; native Server Actions support.

### Senior
163. **Explain React Server Components vs. Client Components.** Server Components run only on the server, never ship JS to the client, never hydrate, and can be `async` (direct DB/file-system access) — reducing client bundle size. Client Components (`'use client'`) run in the browser, support state/effects/event handlers. Server Components can import Client Components; the reverse is not allowed.
164. **RSC vs. traditional SSR — what's the real difference?** SSR renders components to HTML on the server *and* the same component code re-runs (hydrates) on the client. RSC components run *exclusively* on the server and are never re-executed or shipped to the client at all — a fundamentally different, more bundle-size-efficient model.
165. **What are Server Actions (React 19 / Next.js)?** Functions marked `'use server'` that can be called directly from Client Components (e.g., as a `<form action={fn}>`) without hand-writing an API route; React serializes arguments, executes on the server, and streams the result back — includes automatic CSRF protection and progressive enhancement (forms work without JS).

---

## 12. Error Handling & Error Boundaries

### Junior
166. **What are error boundaries?** Class components implementing `static getDerivedStateFromError()` (to render fallback UI) and/or `componentDidCatch(error, info)` (to log) that catch JS errors in their child tree during rendering and lifecycle methods, showing a fallback instead of crashing.
167. **What's the required signature for `componentDidCatch`?** `componentDidCatch(error, info)` — `error` is the thrown error object, `info.componentStack` describes which component threw it.

### Mid-Level
168. **In which scenarios do error boundaries NOT catch errors?** Event handlers, asynchronous code (`setTimeout`, Promises), server-side rendering, and errors thrown inside the error boundary itself.
169. **Why don't event handlers need error boundaries?** Event handlers don't happen during rendering, so an error there doesn't leave React unsure what to display — use a regular `try/catch` inside the handler instead.
170. **Is there a functional-component equivalent of error boundaries?** Not natively as of React 18 — you must use a class component, or the `react-error-boundary` library which wraps one for you.
171. **What is the difference between `try/catch` and error boundaries?** `try/catch` is for imperative code; error boundaries wrap *declarative* JSX trees and catch errors thrown during React's render/lifecycle process, even from deep descendants (e.g., triggered by a distant `setState`).

### Senior
172. **What is the behavior of an uncaught error with no error boundary present (React 16+)?** The entire component tree unmounts — React's philosophy is that leaving corrupted UI on screen (e.g., a payments app showing a wrong amount) is worse than showing nothing. Always wrap critical sections in boundaries to avoid full-app blank-outs.
173. **Where should you place error boundaries in a large app?** Granularity is a judgment call: wrap top-level route components for a generic app-wide fallback, and additionally wrap individual risky/third-party components so a local failure doesn't crash the whole page.

---

## 13. Performance Optimization

### Junior
174. **What causes unnecessary re-renders?** Parent re-renders cascading to all children by default; inline object/array/function props creating new references every render; Context value changes; missing `React.memo` on stable pure components.
175. **What is `React.memo`?** Wraps a component to skip re-rendering when its props are shallow-equal to the previous render — the function-component equivalent of `PureComponent`.
176. **What is code-splitting?** Breaking the JS bundle into smaller chunks loaded on demand (via dynamic `import()`/`React.lazy`) instead of one large upfront bundle — reduces initial load time.
177. **What is windowing/virtualization?** Rendering only the currently-visible rows of a large list (via `react-window`/`react-virtual`) instead of all items — dramatically reduces DOM node count and improves scroll performance.

### Mid-Level
178. **`useMemo` vs `React.memo` — how are they different?** `React.memo` prevents an entire *component* from re-rendering based on props; `useMemo` memoizes a *computed value* inside a component. They're often used together: `React.memo` on the child, `useMemo`/`useCallback` in the parent to keep the props it receives referentially stable.
179. **When does `React.memo` NOT help?** When props include a new object/function reference every render (must pair with `useMemo`/`useCallback`), when the component is cheap to render (comparison overhead > render cost), or when props genuinely change every time anyway.
180. **How do you measure and fix excessive re-renders?** Use React DevTools "Highlight updates" and the Profiler's flame chart to spot the offending components, then apply `React.memo`, split Context, colocate state closer to where it's used, or memoize props.
181. **What is the Profiler API?** `React.Profiler` wraps a subtree and calls `onRender(id, phase, actualDuration, ...)` after each commit — used to programmatically measure render cost; DevTools Profiler is a UI on top of the same mechanism.
182. **What problems does `useMemo` actually solve, and when should you NOT use it?** Solves recomputation of expensive calculations and preserves referential equality for downstream dependencies. Skip it for trivial calculations, where memoization overhead exceeds the savings, or values that change on virtually every render anyway.

### Senior
183. **How would you optimize a React app rendering 100,000+ list items?** Virtualize (react-window/react-virtual) to render only visible rows; paginate or infinite-scroll instead of loading everything; memoize row components; use stable keys; debounce filter/search; offload heavy sorting/filtering to a Web Worker; code-split the list component if not immediately needed.
184. **How would you ensure a React app performs well at 100k concurrent users?** CDN for static assets, SSR/SSG for fast first paint, aggressive HTTP/query caching (React Query), server-side pagination (never load full datasets), route-level code splitting, error boundaries everywhere, and production monitoring/alerting from day one.
185. **How do you implement a runtime feature-flag system?** A flag service (LaunchDarkly/Unleash/homegrown) fetched at app init and stored in Context; a `useFeatureFlag(name)` hook returns a boolean; guard components/branches with conditional rendering; support runtime updates without redeploys.
186. **How does `useLayoutEffect` cause layout thrashing, and how do you avoid it?** Alternating reads (`offsetHeight`) and writes (`style.height = ...`) forces synchronous reflow on every read-after-write cycle. Batch all reads first, then all writes, to avoid interleaved forced reflows.

### Output-Based
187. **`React.memo` with an inline function prop still re-renders:**
```jsx
const MemoChild = React.memo(Child);
function Parent() {
  const [count, setCount] = useState(0);
  return <MemoChild onClick={() => setCount(c => c+1)} />;
  // New function reference every render → React.memo's shallow comparison fails → Child re-renders every time.
  // Fix: wrap the handler in useCallback.
}
```
188. **`React.memo` + stable `useMemo` array — correctly skips re-render:**
```jsx
const items = useMemo(() => [1, 2, 3], []); // same reference every render
<MemoChild items={items} /> // Child renders ONCE regardless of parent re-renders — correct pairing.
```
189. **`useMemo` recomputing despite unrelated state changes:**
```jsx
const result = useMemo(() => count * multiplier, [count, multiplier]);
// Only recomputes when count OR multiplier change — clicking an unrelated button does NOT trigger recomputation.
```
190. **`useMemo` still recomputing due to a fresh dependency array reference:**
```jsx
function App() {
  const data = [1, 2, 3]; // new array every render!
  return <Expensive data={data} />; // useMemo inside Expensive keyed on `data` recomputes every render
  // Fix: const data = useMemo(() => [1,2,3], []) in App.
}
```
191. **`useRef` never triggers a re-render:** Incrementing `ref.current` doesn't cause the component to re-render — the updated value only becomes visible on screen the next time something *else* triggers a render.

### Scenario-Based
192. **A search input lags as the user types — how do you fix it?** Separate the input's own state (urgent, updates instantly) from the derived search-results computation (deferred via `useDeferredValue` or `useTransition`) — the input stays responsive while results compute in the background.
193. **The app is slow on mobile — how do you diagnose and fix it?** Throttle CPU in DevTools to simulate mobile, run a Lighthouse audit, check bundle size and code-split aggressively, profile renders in React DevTools, remove render-blocking JS, lazy-load offscreen images/components, and simplify animations.
194. **Context is causing performance problems in a large app — what do you do?** Split into multiple smaller, purpose-specific contexts; memoize the Provider's `value`; move high-frequency state out of Context into a selector-based store (Zustand/Jotai).
195. **You need the UI to stay responsive during a heavy filter operation on 10k items.** Keep the raw list in state; put the filter *input* update in urgent state; wrap the *filtered results* computation in `useTransition`/`useDeferredValue` so React renders the input change immediately and the results once resources are free.

---

## 14. Component Design Patterns

### Junior
196. **What are render props?** A prop whose value is a function that a component calls to determine what to render — a technique for sharing code/behavior between components (e.g., `<DataProvider render={data => <View data={data}/>} />`).
197. **What are compound components?** A group of components designed to work together, sharing implicit state (e.g., `<Select>` + `<Select.Option>`), giving consumers flexible composition while the parent manages shared logic.
198. **What is the provider pattern?** A component that wraps part of the tree and supplies shared state/functionality via Context — `ThemeProvider`, `AuthProvider`, `QueryClientProvider` are common examples.

### Mid-Level
199. **Custom hooks vs. HOCs vs. render props — when do you use each today?** Custom hooks are the modern default for sharing stateful logic without extra JSX nesting. HOCs remain useful when you need to *wrap* a component itself (e.g., legacy code-splitting boundaries). Render props matter when the sharing genuinely needs to happen through JSX composition/context.
200. **What are headless components?** Components providing behavior, state, and accessibility with zero built-in UI/styling — consumers supply their own markup/CSS (e.g., Radix UI, Headless UI, React Aria) — maximizes design flexibility while keeping complex a11y/interaction logic centralized.
201. **What is prop inversion of control?** A component stops hardcoding every rendering decision internally and instead exposes a render-prop/children-function so the *consumer* decides how a piece should look, e.g. `<List items={data} renderItem={item => <Custom {...item}/>} />`.

### Senior
202. **What is the container/presenter pattern, and is it still relevant?** Separating data-fetching/logic (container) from pure rendering (presenter). Less strictly enforced today since hooks let any component embed data logic — but the underlying separation-of-concerns principle remains valuable, often expressed instead via custom hooks.
203. **How would you design a design system in React?** Publish as a separate versioned package; build primitive components (Button, Input, Text) plus compound components for complex widgets; define design tokens as CSS variables; document/visually test with Storybook + Chromatic; use TypeScript for consumer safety.
204. **What is the state reducer pattern?** Gives consumers a "veto" over a component's internal state transitions — the component computes proposed next state, but passes it through a caller-supplied reducer function first, letting consumers intercept/override specific transitions without forking the component.

### Coding
205. **HOC that logs props on every render:**
```jsx
const withLogger = (Wrapped) => (props) => {
  console.log(`${Wrapped.name} rendered with:`, props);
  return <Wrapped {...props} />;
};
// Always define HOCs OUTSIDE component render — defining inline creates a new type every render, forcing remounts.
```

---

## 15. Testing React Applications

### Junior
206. **What is Jest?** A JS unit testing framework (originally by Facebook) providing test running, assertions, mocking, and a jsdom-based DOM environment for testing components without a real browser.
207. **What is React Testing Library (RTL)?** A testing library that renders components into jsdom and provides user-centric queries (`getByRole`, `getByText`, `getByLabelText`) — encourages testing observable behavior over implementation details.
208. **`getBy` vs `queryBy` vs `findBy` — when do you use each?** `getBy*` throws if not found (assert existence); `queryBy*` returns `null` if not found (assert *absence*); `findBy*` is async/returns a Promise (wait for an element that appears after an async operation).

### Mid-Level
209. **How do you test user interactions?** Use `userEvent` from `@testing-library/user-event` (more realistic than `fireEvent` — fires the full sequence of real browser events) for clicks, typing, and selecting options.
210. **How do you test async behavior (API calls)?** Mock `fetch`/use Mock Service Worker (MSW) to intercept network requests; assert with `findBy*` or `waitFor(() => expect(...))` rather than arbitrary `setTimeout`s.
211. **What are the RTL query priorities?** Preferred order (most to least accessible/robust): `getByRole` > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByDisplayValue` > `getByAltText` > `getByTitle` > `getByTestId` (last resort).
212. **What is Mock Service Worker (MSW)?** Intercepts network requests at the Service Worker (browser) or interceptor (Node/test) level — the same mock handlers work in both tests and local development, more realistic than mocking `fetch` directly.

### Senior
213. **What is the testing pyramid for a React app?** Many fast unit tests (functions/hooks), a solid middle layer of integration tests (component interactions, user flows via RTL), and few slow E2E tests (full browser flows via Playwright/Cypress) — most effort belongs in the middle layer.
214. **Shallow vs. deep/full rendering — which do modern tools favor?** Shallow rendering (older Enzyme approach) renders one level deep without mounting children; RTL favors full/deep rendering to jsdom, testing what a real user would actually see and interact with.
215. **What is Vitest and how does it differ from Jest?** A Vite-native test runner with a Jest-compatible API — faster (reuses Vite's module graph, no separate transform step), native ESM support, drop-in replacement for Jest in Vite-based projects.

---

## 16. TypeScript with React

### Junior
216. **How do you type component props?** Define an `interface`/`type`: `interface Props { name: string; onClick: () => void }`, then `function Comp({name, onClick}: Props)`.
217. **How do you type `useState`?** `useState<Type>(initial)` — TypeScript infers the type from the initial value in simple cases; be explicit (`useState<User | null>(null)`) when the initial value doesn't reveal the full type.

### Mid-Level
218. **`React.FC` vs. an explicit return type — which is preferred?** Modern guidance favors explicit typing (`function Comp(props: Props): JSX.Element`) over `React.FC<Props>`, since `React.FC` implicitly (and often incorrectly) types `children` and complicates generics.
219. **How do you type event handlers?** Use the specific synthetic event generic, e.g. `(e: React.ChangeEvent<HTMLInputElement>) => void` or `React.MouseEvent<HTMLButtonElement>`.
220. **How do you type `children`?** `React.ReactNode` (most flexible — covers anything renderable) is generally preferred over `React.ReactElement` (element only); `React.PropsWithChildren<Props>` adds an optional `children` field to any props type.
221. **How do you type `useRef`?** For DOM nodes: `useRef<HTMLInputElement>(null)` (nullable, since it starts as `null`); for mutable non-DOM values: `useRef<number>(0)` (non-null).
222. **How do you type Context?** `createContext<ContextType | undefined>(undefined)`, then assert non-null (or throw) inside a wrapper `useMyContext()` hook so every consumer doesn't need to null-check.

### Senior
223. **What is a discriminated union and when is it useful in React?** A union type sharing a common literal field (e.g., `type Action = {type:'increment'} | {type:'setValue', payload:number}`) — lets TypeScript narrow the exact shape inside a `switch`/`if` on that field, ideal for typing reducer actions.
224. **How do you type `useReducer`?** Define `State` and `Action` (often a discriminated union) types, then `useReducer<Reducer<State, Action>>(reducer, initialState)` — TypeScript then infers a correctly-typed `dispatch`.

---

## 17. Accessibility (a11y)

### Junior
225. **Why does accessibility matter in React SPAs specifically?** SPAs bypass native browser navigation behaviors (focus reset, page titles, history announcements) that screen readers rely on by default — these must be manually re-implemented.
226. **What are ARIA roles/attributes for?** Attributes like `role`, `aria-label`, `aria-expanded`, `aria-hidden` provide semantic meaning to custom (non-native) components for assistive technology.

### Mid-Level
227. **What is a focus trap, and when do you need one?** Confines keyboard `Tab` focus within a modal/dialog so it can't escape to background content — required for any accessible modal implementation; handled automatically by libraries like Radix UI Dialog.
228. **How do you manage focus after client-side navigation?** Programmatically move focus (via `ref.current.focus()` in a `useEffect` triggered on route change) to the new page's heading or a "skip to content" landmark, since the browser won't do this automatically in an SPA.
229. **How do you handle keyboard navigation in a custom component (e.g., a dropdown or menu)?** Implement `onKeyDown` following WAI-ARIA authoring practices for that widget type: Enter/Space to activate, arrow keys to move between items, Escape to close.
230. **What tools help audit React app accessibility?** `eslint-plugin-jsx-a11y` (static analysis), `@axe-core/react` (runtime checks in dev), browser extensions (Axe DevTools, WAVE), Lighthouse a11y audits, and manual screen-reader testing (NVDA, VoiceOver).

---

## 18. Security

### Junior
231. **How does React prevent XSS by default?** All values interpolated via `{}` in JSX are HTML-escaped before insertion into the DOM — you cannot accidentally inject executable script tags through normal text/attribute interpolation.
232. **Why is `dangerouslySetInnerHTML` dangerous?** It bypasses React's automatic escaping entirely; if the HTML string contains untrusted user input, it can execute arbitrary scripts (XSS). Always sanitize (e.g., with DOMPurify) before use.

### Mid-Level
233. **How do you securely store auth tokens?** Prefer HttpOnly cookies (inaccessible to JS, so immune to XSS token theft, but need CSRF protection) over `localStorage` (accessible to any injected script, so a single XSS hole leaks the token).
234. **What is a CSRF attack and how do you prevent it?** Tricks a logged-in user's browser into making an unwanted authenticated request. Prevent with CSRF tokens in headers, the `SameSite` cookie attribute, and never relying on cookies alone for authorization.
235. **What is a CORS issue and how do you handle it?** The browser blocks cross-origin requests unless the server responds with appropriate `Access-Control-Allow-Origin` headers; configure the server accordingly, or proxy requests during local development.

### Senior
236. **How would you implement role-based access control (RBAC) in React?** Store roles in an auth Context; a `usePermissions`/`useCan` hook checks role against required permissions; wrap protected UI or routes with conditional rendering/loader-level redirects — but always enforce authorization server-side too, since client checks are only a UX convenience.

---

## 19. React Native

### Junior
237. **What is the difference between React and React Native?** React is a JS library for web UIs (and SSR); React Native is a framework that compiles React components to native mobile UI elements (iOS/Android/Windows) instead of DOM nodes.
238. **How do you debug a React Native app?** Run in a simulator, open the in-app dev menu, use Chrome DevTools connected via the debugger, and enable "Pause on Caught Exceptions" for step-through debugging.

### Mid-Level
239. **Does `React.lazy` support named exports?** No, only default exports. For a named export, create an intermediate module that re-exports it as default: `export { Named as default } from './Module'`.

---

## 20. Ecosystem, Libraries & i18n

### Junior
240. **What is Formik / React Hook Form used for?** Form state libraries handling values, validation, touched/error tracking, and submission. React Hook Form is uncontrolled-by-default (fewer re-renders, better performance for large forms); Formik uses controlled inputs (simpler mental model, more re-renders).
241. **What is Storybook?** A development environment for building, documenting, and visually testing UI components in isolation from the full app — commonly used for design systems and component libraries.

### Mid-Level
242. **How do you integrate a non-React library (e.g., D3, Leaflet, a jQuery plugin)?** Create a ref for the container DOM node; in a `useEffect` with `[]` deps, initialize the library against `ref.current`; return a cleanup function to destroy the instance on unmount — let the library fully own that DOM subtree rather than letting React re-render inside it.
243. **How would you implement internationalization (i18n)?** `react-intl` or `react-i18next`: extract all UI strings into message catalogs, use a hook (`useIntl`/`useTranslation`) for formatting, support RTL layouts where needed, format dates/numbers/currencies via the `Intl` API, and lazy-load language bundles per locale.

---

## 21. Build Tools & Developer Experience

### Junior
244. **What is the role of Babel in a React project?** Transpiles modern JS and JSX into browser-compatible JavaScript (e.g., JSX → `createElement`/`jsx()` calls). Some modern toolchains (esbuild in Vite) handle this faster without full Babel.
245. **What is HMR (Hot Module Replacement)?** Replaces changed modules in the running browser app without a full page reload; React's Fast Refresh additionally preserves component state across HMR updates, speeding up the dev feedback loop.

### Mid-Level
246. **What is tree shaking and how does it work?** Dead-code elimination that removes unused exports from the final bundle by statically analyzing the import/export graph — relies on ES module syntax being statically analyzable (not `require`/dynamic requires).
247. **What is Vite, and why is it preferred over Create React App today?** Vite uses native ES modules for near-instant dev-server startup and Rollup for optimized production builds; CRA (webpack-based, no longer actively maintained) is significantly slower in dev and is no longer recommended for new projects — Vite (SPAs) or Next.js (SSR/full-stack) are the modern defaults.
248. **What is the purpose of ESLint + Prettier together?** ESLint performs static analysis to catch bugs and enforce coding rules (with `eslint-plugin-react-hooks` enforcing the Rules of Hooks, `jsx-a11y` for accessibility); Prettier handles opinionated code formatting — complementary, not overlapping, concerns.

### Senior
249. **What is a monorepo, and how does it relate to React projects?** A single repository containing multiple packages/apps (tools: Nx, Turborepo, pnpm workspaces) — useful for sharing a component library, hooks, or design system consistently across multiple React apps.
250. **What is bundle analysis, and how do you perform it?** Inspecting what's actually inside your production bundle to spot bloat — via `rollup-plugin-visualizer` (Vite) or `webpack-bundle-analyzer` — looking for duplicate dependencies, oversized unused imports, or libraries that should be lazy-loaded.

---

## 22. Architecture & System Design

### Mid-Level
251. **How should you structure a large React application?** Feature-based folders (`features/auth`, `features/dashboard`) rather than type-based (`components/`, `containers/`) once the app grows; shared UI primitives in a common folder; business logic pushed into hooks/services; clear separation between UI, state, and data layers; TypeScript for safety at scale.
252. **What are common folder structure conventions?** Group-by-feature (colocate CSS/JS/tests per feature/route) vs. group-by-file-type (`api/`, `components/`) — feature-based generally scales better for large apps.

### Senior
253. **How would you architect a React app for a team of 20 developers?** Feature-based structure with enforced module boundaries (ESLint import rules or Nx); a shared, Storybook-documented component library; TypeScript everywhere; an agreed state strategy (React Query for server state, Zustand/RTK for client global state); ESLint + Prettier + pre-commit hooks (husky); CI running tests/type-checks/lint on every PR.
254. **How would you design a real-time chat UI?** WebSocket connection managed in a custom hook (connect on mount, reconnect with backoff, disconnect on unmount); messages held in `useReducer`/state; virtualized message list for performance; optimistic UI on send; error boundary around the connection; reconnection/offline handling surfaced to the user.
255. **How would you build a drag-and-drop Kanban board?** A library like `dnd-kit` or `@hello-pangea/dnd`; model state as `{ columns: { id: { cards: [] } } }`; update state on drag-end with the new column/position; optimistic local update with debounced/on-drop sync to the backend; ensure keyboard-accessible dragging (dnd-kit supports this natively).
256. **Walk through your process when a critical bug is discovered in production.** Check monitoring (Sentry/logs) for scope, affected users, and first occurrence; reproduce locally; ship a hotfix or disable via a feature flag; write a regression test; do a brief post-mortem and consider whether an error boundary or additional monitoring would have caught it sooner.
257. **How does the React Fiber architecture change how rendering fundamentally works?** It replaces the old synchronous, recursive stack-based reconciler with an incremental one built on linked Fiber nodes — enabling pausable/resumable/abortable/prioritizable rendering work, which is the foundation for concurrent rendering, transitions, and Suspense.

---

## 23. Coding Exercises (Build-From-Scratch)

*A representative, deduplicated set — the originals included ~30 near-identical prompts across debounced search, infinite scroll, virtualization, autocomplete, etc. Grouped here by pattern rather than repeated per variant.*

### Mid-Level Coding
258. **Build a counter with increment/decrement/reset (functional updates):**
```jsx
function Counter({ step = 1 }) {
  const [count, setCount] = useState(0);
  return (
    <div>
      <button onClick={() => setCount(c => c - step)}>-</button>
      <span>{count}</span>
      <button onClick={() => setCount(c => c + step)}>+</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
```
259. **Build a Todo app (CRUD + filter + localStorage persistence):** Isolate CRUD logic into a `useTodos()` custom hook (backed by `useLocalStorage`); component only handles rendering + filtering by `all/active/done`.
260. **Build an Accordion (single vs. multi-open):** Track open item IDs in a `Set`; `allowMultiple` prop decides whether opening a new item clears the set first (single-open/accordion behavior) or just adds to it (multi-open).
261. **Build Tabs with lazy-loaded content that persists state when switching away:** Track which tab IDs have ever been `loaded` in a `Set`; render all loaded tabs but `hidden={id !== activeId}` rather than unmounting — preserves scroll/form state on switch-back.
262. **Build a Star Rating component:** Track `hovered` (transient preview) separately from the committed `value`/`onChange` (controlled by parent) — classic controlled-component + local preview-state pattern.

### Senior Coding
263. **Build a debounced search input that fetches from an API:**
```jsx
function SearchBox() {
  const [query, setQuery] = useState('');
  const debouncedQuery = useDebounce(query, 400);
  const [results, setResults] = useState([]);
  useEffect(() => {
    if (!debouncedQuery) return setResults([]);
    const controller = new AbortController();
    fetch(`/api/search?q=${debouncedQuery}`, { signal: controller.signal })
      .then(r => r.json()).then(setResults).catch(() => {});
    return () => controller.abort();
  }, [debouncedQuery]);
  return (/* input + results list */ null);
}
```
264. **Build a typeahead/autocomplete with keyboard navigation:** Debounce the query; track `activeIndex` for arrow-key highlighting; use `onMouseDown` (not `onClick`) for selecting a suggestion, since `onClick` fires *after* `onBlur` would have already closed the list.
265. **Build a virtualized list (render only visible rows):**
```jsx
function VirtualList({ items, itemHeight = 40, containerHeight = 400 }) {
  const [scrollTop, setScrollTop] = useState(0);
  const startIndex = Math.floor(scrollTop / itemHeight);
  const visibleCount = Math.ceil(containerHeight / itemHeight);
  const endIndex = Math.min(items.length, startIndex + visibleCount + 1);
  const visibleItems = items.slice(startIndex, endIndex);
  return (
    <div onScroll={e => setScrollTop(e.target.scrollTop)} style={{ height: containerHeight, overflowY: 'auto' }}>
      <div style={{ height: items.length * itemHeight, position: 'relative' }}>
        {visibleItems.map((item, i) => (
          <div key={startIndex + i} style={{ position: 'absolute', top: (startIndex + i) * itemHeight, height: itemHeight }}>
            {item.label}
          </div>
        ))}
      </div>
    </div>
  );
  // For production, prefer react-window / @tanstack/react-virtual (handles variable heights, horizontal scroll, etc.)
}
```
266. **Build a Modal with a focus trap and Escape-to-close:** Render via `ReactDOM.createPortal` (escapes parent `overflow`/`z-index` constraints); trap `Tab` focus by finding all focusable descendants and wrapping focus at the first/last; listen for `Escape` to call `onClose`; restore `document.body` scroll on unmount.
267. **Build a multi-step form wizard with validation:** Lift `formData` and `errors` to the wizard container so data survives moving back/forward; each step validates its own slice and reports errors up via an `onNext(values, errors)` callback before the wizard advances the step index.
268. **Build a drag-and-drop list without a library (native HTML5 DnD):** Use refs (not state) to track the dragged/target index during `dragstart`/`dragenter` (avoids re-renders on every intermediate drag event); reorder the array only once, in `dragend`.
269. **Build a recursive nested comment thread with reply:** The `Comment` component renders itself for `comment.children` — recursion terminates naturally when there are no children; pass `onReply` down unchanged so any depth level can add a new child to the tree.
270. **What is `flushSync` and when would you use it?** Forces a state update to apply synchronously (immediate DOM flush) rather than being batched — a rare escape hatch for cases like measuring the DOM immediately after a state change, or integrating with a non-React library needing a synchronously up-to-date DOM. Overuse defeats React 18's automatic batching and hurts performance.

---

*Original collection: 758 questions. This reorganized version consolidates duplicate/near-duplicate entries (multiple "What is React?", "What is JSX?", deprecated-API questions like `componentWillMount`/React 15 error boundaries/CRA-as-the-default-tool, and dozens of near-identical coding exercises) into ~270 unique, leveled questions across 23 sections.*
