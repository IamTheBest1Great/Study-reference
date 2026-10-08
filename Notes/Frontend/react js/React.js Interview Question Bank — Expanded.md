# React.js — Complete Interview Question Bank with Answers (Expanded)

> 300+ numbered, section-wise questions covering every major React topic — from freshers to senior/staff level. Click any section below to jump straight to it.

---

**Table of Contents** — click a section to jump there; questions inside are numbered (e.g., Q4.12 = Section 4, question 12).

1. [Section 1 — React Core Fundamentals](#m2dhq6yp426.230) (Q1.1–Q1.22)
2. [Section 2 — JSX & Virtual DOM (Deep Dive)](#m2dhq6yp426.5416) (Q2.1–Q2.12)
3. [Section 3 — Components, Props & State](#m2dhq6yp426.7853) (Q3.1–Q3.16)
4. [Section 4 — Hooks](#m2dhq6yp426.11500) (Q4.1–Q4.30)
5. [Section 5 — Component Lifecycle & Rendering](#m2dhq6yp426.17371) (Q5.1–Q5.15)
6. [Section 6 — Context API & State Management](#m2dhq6yp426.20572) (Q6.1–Q6.20)
7. [Section 7 — React Router](#m2dhq6yp426.24935) (Q7.1–Q7.15)
8. [Section 8 — Forms & Controlled Components](#m2dhq6yp426.27747) (Q8.1–Q8.12)
9. [Section 9 — Performance Optimization](#m2dhq6yp426.30451) (Q9.1–Q9.18)
10. [Section 10 — Error Handling & Error Boundaries](#m2dhq6yp426.34618) (Q10.1–Q10.8)
11. [Section 11 — Data Fetching & React Query](#m2dhq6yp426.36709) (Q11.1–Q11.12)
12. [Section 12 — Styling in React](#m2dhq6yp426.39400) (Q12.1–Q12.8)
13. [Section 13 — Testing React Applications](#m2dhq6yp426.41228) (Q13.1–Q13.15)
14. [Section 14 — TypeScript with React](#m2dhq6yp426.44513) (Q14.1–Q14.15)
15. [Section 15 — Server-Side Rendering & Next.js](#m2dhq6yp426.47887) (Q15.1–Q15.18)
16. [Section 16 — React 18/19 Concurrent Features & Server Components](#m2dhq6yp426.52099) (Q16.1–Q16.12)
17. [Section 17 — Design Patterns in React](#m2dhq6yp426.55380) (Q17.1–Q17.15)
18. [Section 18 — Accessibility (a11y)](#m2dhq6yp426.59727) (Q18.1–Q18.12)
19. [Section 19 — Build Tools & Bundling](#m2dhq6yp426.62832) (Q19.1–Q19.10)
20. [Section 20 — Security](#m2dhq6yp426.66037) (Q20.1–Q20.12)
21. [Section 21 — Advanced / Senior-Level Questions](#m2dhq6yp426.69042) (Q21.1–Q21.15)
22. [Section 22 — Scenario-Based / System Design Questions](#m2dhq6yp426.73635) (Q22.1–Q22.20)

**Total: 330 numbered questions across 22 sections.**

---

## Section 1 — React Core Fundamentals

**Q1.1: What is React? What problem does it solve?** React is a JavaScript library for building user interfaces through reusable, composable components. It solves the problem of manually manipulating the DOM for dynamic UIs by introducing a declarative model: you describe what the UI should look like for a given state, and React handles updating the DOM efficiently.

**Q1.2: What is declarative vs imperative programming? How does React fit in?** Imperative code describes the exact steps to change the UI. Declarative code describes the desired end state, and the library figures out the steps. React is declarative: you write `<h1>{name}</h1>` and React reconciles the DOM to match.

**Q1.3: What is the Virtual DOM? Why does React use it?** The Virtual DOM is a lightweight, in-memory JS representation of the real DOM. When state changes, React builds a new Virtual DOM tree, diffs it against the previous one, and applies only the minimal set of real DOM mutations needed.

**Q1.4: How does React's reconciliation algorithm work?** It compares the new element tree with the previous one: elements of different types produce entirely new trees; elements of the same type keep the DOM node and only update changed attributes; for lists, `key` props let React match children across renders instead of diffing by position.

**Q1.5: What is the `key` prop? Why is it important in lists?** `key` gives React a stable identity for each list item across renders, enabling correct reordering/adding/removing of DOM nodes. Keys should be stable, unique IDs — never array index when the list can reorder or be filtered.

**Q1.6: What is the difference between the real DOM and the Virtual DOM?** The real DOM is the browser's actual node tree; mutating it is relatively expensive. The Virtual DOM is a plain JS object tree that's cheap to create and diff.

**Q1.7: What is Fiber? Why did React introduce it?** Fiber is React's reconciliation engine (React 16+), replacing the old synchronous stack reconciler. Each Fiber is a unit of work, making rendering interruptible/resumable and enabling concurrent features.

**Q1.8: What is the difference between class components and function components?** Class components use `this.state` and lifecycle methods. Function components use Hooks. Since Hooks (16.8), function components can do everything classes can and are now the default.

**Q1.9: What is JSX? How does it compile to JavaScript?** JSX is HTML-like syntax in JS. It compiles via Babel to `React.createElement(type, props, ...children)` or `jsx()` calls, returning plain JS objects describing the UI.

**Q1.10: Why can't browsers run JSX directly?** JSX isn't valid JS syntax. A build tool (Babel/SWC/esbuild) transpiles it to `createElement`/`jsx()` calls before reaching the browser.

**Q1.11: What is `React.createElement()`? What does it return?** The function JSX compiles to. It returns a plain JS object (a React element) describing type, props, and children — not an actual DOM node.

**Q1.12: What is the difference between an element and a component?** An element is a plain object describing what to render. A component is a function/class that *returns* elements.

**Q1.13: What is `ReactDOM.createRoot()`? How did rendering change in React 18?** `createRoot(container).render(<App/>)` is the React 18 mounting API, replacing legacy `ReactDOM.render()`, opting into the concurrent renderer.

**Q1.14: What is the difference between `props` and `state`?** `props` are read-only inputs from a parent. `state` is local, mutable data owned by the component; changing it triggers a re-render.

**Q1.15: Why are props read-only? What happens if you mutate them?** React's data flow is unidirectional; mutating props directly doesn't trigger a re-render and breaks the parent's ownership of that data.

**Q1.16: What is unidirectional data flow in React?** Data flows parent → child via props. A child requests a change via a callback passed down, and the parent updates its own state, flowing back down as new props.

**Q1.17: What is a controlled vs uncontrolled component?** Controlled: value driven entirely by React state (`value` + `onChange`). Uncontrolled: the DOM holds its own state, read via a `ref` when needed.

**Q1.18: What is `React.Fragment`? Why use it instead of a wrapping `<div>`?** `<>...</>` lets a component return multiple children without an extra DOM node, avoiding wrapper `div`s that could break CSS layout or semantics.

**Q1.19: What is `children` prop? How does composition work in React?** `props.children` holds nested content between a component's tags, enabling composition: a wrapper component lets the caller decide what content goes inside.

**Q1.20: What is prop drilling? How do you avoid it?** Passing props through intermediate components that don't need them. Avoid with Context, composition, or a state library.

**Q1.21: What are synthetic events in React?** SyntheticEvent wraps native DOM events for cross-browser consistency. Since React 17, events attach to the root container rather than `document`.

**Q1.22: What is the difference between `onClick={handleClick}` and `onClick={handleClick()}`?** The first passes a function reference React calls on click. The second invokes it immediately during render and passes its return value — almost always a bug.

---

## Section 2 — JSX & Virtual DOM (Deep Dive)

**Q2.1: How do you render a list of items in JSX?** Map the array to elements, each with a unique `key`: `items.map(item => <li key={item.id}>{item.name}</li>)`.

**Q2.2: How do you conditionally render content in JSX?** Ternary, logical AND (`cond && <A/>`, careful with falsy numbers), early return, or a variable computed before `return`.

**Q2.3: Why shouldn't you use array index as a `key` in dynamic lists?** If the list reorders/filters, the index no longer uniquely identifies an item, causing wrong state association or broken animations.

**Q2.4: What does React do differently when a `key` changes vs stays the same?** Same `key`+`type`: DOM node and instance reused (state preserved). Changed `key`: old instance unmounted, new one mounted fresh.

**Q2.5: What is `dangerouslySetInnerHTML`? When would you use it?** Sets raw HTML, bypassing escaping — an XSS risk with unsanitized input. Only use with trusted content or content sanitized via `DOMPurify`.

**Q2.6: What is JSX spread attributes (`{...props}`)? What's the risk?** Spreads an object's keys as individual props: `<Comp {...props} />`. Risk: passing unintended props through (e.g., leaking a prop the child doesn't expect, or overriding one accidentally depending on order).

**Q2.7: Can a component return multiple top-level elements without a Fragment?** Yes, as of React that supports returning arrays or using `<>...</>` — but each sibling in an array needs its own `key`.

**Q2.8: What happens if a component returns `null`?** React renders nothing for that component (no DOM node), which is valid and commonly used for conditionally hiding content.

**Q2.9: Why does `0 && <Component/>` render "0" instead of nothing?** Logical AND returns the first falsy operand if `cond` is falsy; `0` is falsy but is still a valid renderable value, so React renders the literal "0" text instead of nothing. Fix: use a boolean (`cond > 0 && ...`) or a ternary.

**Q2.10: How do style objects work in JSX (`style={{...}}`)?** The outer `{}` is JSX interpolation, the inner `{}` is a JS object with camelCased CSS properties and values as strings/numbers (unitless numbers default to `px` for most properties).

**Q2.11: What is the difference between `className` and `class` in JSX?** JSX uses `className` (matching the DOM property name) since `class` is a reserved word in JavaScript.

**Q2.12: How do comments work inside JSX?** `{/* comment */}` — regular `//` or `/* */` only work outside JSX expression blocks, not directly between JSX tags.

---

## Section 3 — Components, Props & State

**Q3.1: What is a pure component? What is `React.memo()`?** Renders the same output given the same props/state. `React.memo(Component)` skips re-rendering if props are shallowly equal to the previous render.

**Q3.2: What is `PureComponent` vs `Component` in class components?** `PureComponent` auto-implements a shallow `shouldComponentUpdate`. Plain `Component` always re-renders unless you implement that method yourself.

**Q3.3: What is `shouldComponentUpdate`? How does it relate to `React.memo`?** A class lifecycle method returning `false` to skip a re-render; `React.memo` is its function-component equivalent (shallow comparison, or a custom comparator).

**Q3.4: How do you lift state up? Why is it needed?** Move state to the closest common ancestor of components that need to share it, since siblings can't communicate directly in React's top-down data flow.

**Q3.5: What is a higher-order component (HOC)? Give an example.** A function taking a component and returning an enhanced one, e.g. `withAuth(Component)`. Largely superseded by custom Hooks.

**Q3.6: What is a render prop? How does it compare to Hooks?** A component that takes a function prop to determine what to render, sharing logic. Hooks avoid the "wrapper hell" render props create.

**Q3.7: What is composition vs inheritance in React?** React favors composition (props/children) over class inheritance hierarchies for building complex UIs.

**Q3.8: What are default props? How do you set them in function components?** Fallback values for unpassed props, set via default parameters: `function Button({ size = 'medium' }) {}`.

**Q3.9: What is `PropTypes`? How does it differ from TypeScript?** A runtime prop-validation library (dev-time console warnings). TypeScript validates at compile time, catching errors before the code runs, but not bad runtime data.

**Q3.10: What is the controlled component pattern for custom inputs?** The component accepts `value`/`onChange` like a native input, holding no internal source-of-truth state — the parent owns it.

**Q3.11: What is a "smart" vs "dumb" component?** Smart (container) components manage data/state/logic; dumb (presentational) components just render props. Largely replaced by custom Hooks + a single component today.

**Q3.12: How do you pass a component as a prop (not just data)?** Pass the element or component reference itself as a prop value: `<Layout icon={<HomeIcon/>} />` or `<Layout Icon={HomeIcon} />`, letting the parent customize rendered content.

**Q3.13: What is prop type narrowing with discriminated unions (conceptually, even pre-TS)?** Structuring props so only a valid, mutually exclusive combination can be passed (e.g., `variant: 'link'` requiring `href`, `variant: 'button'` requiring `onClick`), preventing invalid prop combinations at the API design level.

**Q3.14: What is the difference between `state` and `derived state`?** `state` is the authoritative, independently-set source of truth. Derived state is a value computed from existing state/props during render (should not be duplicated into its own `useState` — just compute it inline or with `useMemo`).

**Q3.15: Why is storing derived values in `useState` (and syncing via `useEffect`) usually an anti-pattern?** It creates two sources of truth that can get out of sync, adds an unnecessary extra render (state update → re-render), and is harder to reason about than just computing the value directly during render.

**Q3.16: What is the "key to reset a subtree" trick for resetting component state?** Changing an element's `key` forces React to unmount and remount the subtree, discarding all its internal state — a common technique to reset a form or widget to its initial state without manually clearing every field.

---

## Section 4 — Hooks

**Q4.1: What are Hooks? Why were they introduced?** Functions (`useState`, `useEffect`, etc.) letting function components use state/other React features. They solve: reusing stateful logic without wrapper hell, splitting components by concern, avoiding `this` confusion.

**Q4.2: What are the rules of Hooks? Why do they exist?** Only call at the top level (never in loops/conditions); only from components or custom Hooks. React relies on Hook call *order* being identical every render to associate state correctly.

**Q4.3: How does `useState` work internally?** React keeps a per-fiber linked list of Hook state, indexed by call order. Skipping a Hook call on some render shifts every subsequent Hook's slot.

**Q4.4: What is the difference between `useState` and `useReducer`?** `useState` for simple, independent state. `useReducer` centralizes complex transitions via `(state, action) => newState`, clearer for interdependent updates.

**Q4.5: Why does `setState` sometimes not update the value immediately?** Updates are async relative to triggering code; the new value is only visible on the next render (fresh closure).

**Q4.6: What is a stale closure? How do you avoid it?** A function capturing an outdated variable value from the render it was created in. Avoid via correct deps, the functional updater form, or `useRef`.

**Q4.7: `setCount(count + 1)` vs `setCount(prev => prev + 1)`?** First captures stale `count`; multiple calls in one handler still only increment once. Functional form queues correctly against the latest pending state.

**Q4.8: What does `useEffect` do? When does it run relative to render?** Runs a side effect *after* paint, asynchronously. Re-runs when a `deps` value changes (every render if omitted, once if `[]`).

**Q4.9: `useEffect` vs `useLayoutEffect`?** `useEffect` runs async after paint. `useLayoutEffect` runs sync after DOM mutation but before paint — for layout reads/adjustments avoiding flicker.

**Q4.10: What is the dependency array? What if you omit it?** Declares which values trigger a re-run. Omitted = runs every render. `[]` = run once on mount, cleanup on unmount.

**Q4.11: What is a cleanup function? When does it run?** The function an effect returns; runs before the effect re-runs and on unmount. Used for unsubscribing/clearing timers.

**Q4.12: What are common `useEffect` mistakes?** Missing deps (stale closures), unstable deps (infinite loops), using it for derivable values, missing cleanup.

**Q4.13: How do you fetch data with `useEffect`? What are the pitfalls?** Use a cancelled-flag or `AbortController` in the cleanup to avoid race conditions from fast-changing deps overwriting fresher data with stale responses.

**Q4.14: What is `useContext`? How does it avoid prop drilling?** Reads the nearest matching Provider's value, letting any descendant read it directly without threading through intermediate props.

**Q4.15: What is `useRef`? What are its two main use cases?** Returns a mutable `{ current }` persisting across renders without re-rendering. Uses: DOM node refs, and mutable "instance variables."

**Q4.16: `useRef` vs `useState`?** Ref updates don't trigger re-render and apply immediately; state updates do trigger re-render, visible next render.

**Q4.17: What is `useMemo`? When should you use it?** Memoizes a computation's result, recomputing only on dep change. Use for expensive computations or referential equality needs.

**Q4.18: What is `useCallback`? How does it differ from `useMemo`?** Memoizes a function reference (`useMemo(() => fn, deps)`). Prevents re-creating callbacks passed to memoized children.

**Q4.19: When is `useMemo`/`useCallback` actually worth it? Cost of overusing?** Worth it for expensive computations or memoized-child/dependency stability. Overuse adds comparison/storage overhead that can net lose for cheap computations.

**Q4.20: What is `useImperativeHandle`? When would you use it?** Customizes the instance exposed via `ref` (with `forwardRef`), exposing specific imperative methods instead of the raw DOM node.

**Q4.21: What is `forwardRef`? Why is it needed?** Function components don't accept `ref` by default; `forwardRef` lets a component receive and attach/expose a parent's ref. (React 19 allows `ref` as a plain prop.)

**Q4.22: What is a custom Hook? How do you build one?** A function starting with `use` that calls other Hooks, extracting reusable stateful logic (e.g., `useDebounce`).

**Q4.23: Do custom Hooks share state between components using them?** No — each call gets independent state tied to the calling component's fiber.

**Q4.24: What is `useTransition`? What problem does it solve?** Marks a state update as low-priority/interruptible, keeping the old UI visible while rendering the transition in the background.

**Q4.25: What is `useDeferredValue`? How does it differ from debouncing?** Returns a "lagging" version of a value during urgent updates, adapting automatically to rendering speed rather than a fixed timeout.

**Q4.26: What is `useId`? Why was it added?** Generates a stable unique ID for a11y attributes, guaranteeing matching IDs between server-rendered and hydrated markup.

**Q4.27: What is `useSyncExternalStore`? When is it needed?** Subscribes to an external store safely under concurrent rendering, avoiding "tearing." Used internally by state libraries.

**Q4.28: What is the `use` Hook (React 19)? How does it differ from other Hooks?** Can be called conditionally; reads a Promise's value directly in render, suspending via `Suspense` until resolved.

**Q4.29: What is an infinite `useEffect` loop and how does it happen?** Setting state inside an effect that's also a dependency of that same effect (without a stabilizing condition), causing effect → state update → re-render → effect again, forever.

**Q4.30: How do you share logic between a Hook and an effect cleanup safely (avoiding duplicated subscribe/unsubscribe code)?** Define the subscribe/unsubscribe logic as named functions inside the effect (or a stable custom Hook), ensuring the same reference is used to both subscribe and later unsubscribe correctly.

---

## Section 5 — Component Lifecycle & Rendering

**Q5.1: What are the three phases of a class component's lifecycle?** Mounting (`constructor`, `render`, `componentDidMount`), Updating (`render`, `componentDidUpdate`), Unmounting (`componentWillUnmount`).

**Q5.2: How do class lifecycle methods map to Hooks?** `componentDidMount` ≈ `useEffect(fn, [])`. `componentDidUpdate` ≈ `useEffect(fn, [deps])`. `componentWillUnmount` ≈ the cleanup function.

**Q5.3: What triggers a re-render in React?** Own state change, parent re-rendering, consumed context value changing, or a force update.

**Q5.4: Does a child always re-render when its parent re-renders?** Yes by default, unless wrapped in `React.memo` with shallowly-equal props.

**Q5.5: What is the difference between "rendering" and "committing"?** Rendering computes the new Virtual DOM (interruptible). Committing applies changes to the real DOM and runs effects (synchronous, not interruptible).

**Q5.6: What is batching? How did it change in React 18?** Grouping multiple updates into one re-render. React 18's automatic batching extends this to all updates, not just React event handlers.

**Q5.7: What is `flushSync`? When would you need it?** Forces a synchronous update/flush, opting out of batching — rarely needed, mainly for immediate DOM reads after a change.

**Q5.8: Difference between `key`-based remounting and conditional rendering?** Conditional rendering can preserve state if type/position match. Changing `key` forces unmount+remount, discarding state.

**Q5.9: Why is calling `setState` inside `render` dangerous?** Can trigger an infinite render loop; the update belongs in an event handler or effect instead.

**Q5.10: What are Strict Mode's dev-only behaviors?** Double-invokes component bodies, state initializers, and effect setup+cleanup to surface impure logic. No effect in production.

**Q5.11: What is the difference between a "key prop" warning and a "missing dependency" warning?** The key warning flags list items without stable identity (reconciliation risk); the missing-dependency warning (from the exhaustive-deps ESLint rule) flags a `useEffect`/`useMemo`/`useCallback` referencing a value not listed in its dependency array (stale-closure risk).

**Q5.12: What is the commit phase's "passive effects" vs "layout effects" ordering?** Layout effects (`useLayoutEffect`) run synchronously right after DOM mutation, before the browser paints. Passive effects (`useEffect`) run asynchronously after paint, so the user may briefly see the pre-effect UI.

**Q5.13: Can a re-render happen without a commit?** Yes — in concurrent mode, React can render (compute the new tree) and then discard/restart that work if interrupted by a higher-priority update, never reaching commit.

**Q5.14: Why do two sibling components with the same `key` cause a warning or misbehavior?** React uses `key` to uniquely identify items among siblings during reconciliation; duplicate keys make it ambiguous which DOM node/state belongs to which element, risking incorrect reuse.

**Q5.15: What is the difference between mounting and updating in terms of effect behavior?** On mount, every effect with satisfied conditions runs for the first time. On update, only effects whose dependency array changed re-run (compare each value against its previous render).

---

## Section 6 — Context API & State Management

**Q6.1: How do you create and consume Context?** `createContext(defaultValue)`, wrap in `<Context.Provider value={...}>`, read with `useContext(Context)`.

**Q6.2: What is the main performance pitfall of Context?** Any consumer re-renders whenever the Provider's `value` changes, even for unrelated fields, especially with a new object literal passed each render.

**Q6.3: How do you avoid unnecessary re-renders caused by Context?** Memoize the `value` (`useMemo`), split into smaller contexts, or move frequently-changing state into a selector-based library.

**Q6.4: When should you use Redux/Zustand instead of Context + `useState`?** For complex, frequently-updating shared state needing fine-grained subscriptions, time-travel debugging, or middleware.

**Q6.5: What is Redux? What are its three core principles?** Single store, read-only state (changed via dispatched actions), changes made by pure reducers.

**Q6.6: What is Redux Toolkit (RTK)? Why is it recommended?** The official package simplifying setup: `configureStore`, `createSlice` (Immer-powered), `createAsyncThunk` — drastically reducing boilerplate.

**Q6.7: What is a reducer? Why must reducers be pure functions?** Takes `(state, action)`, returns next state, no side effects — required for predictable replay/testing and reference-equality change detection.

**Q6.8: What is middleware in Redux? Example?** Intercepts dispatched actions before reducers; `redux-thunk` lets action creators return functions for async dispatch sequences.

**Q6.9: Redux vs Context API?** Context is a built-in value-passing mechanism, not a full state management solution (no actions/reducers/middleware). Redux provides all of that.

**Q6.10: What is Zustand? How does it differ from Redux?** A minimal hook-based store without action/reducer boilerplate; components subscribe via selectors.

**Q6.11: What is Recoil/Jotai? What problem do atom-based libraries solve?** Model state as small independent atoms, giving fine-grained reactivity without manually splitting Context.

**Q6.12: What is the `useSelector`/`useDispatch` pattern?** `useSelector` subscribes to a store slice, re-rendering on reference change; `useDispatch` returns `dispatch`.

**Q6.13: How do you avoid unnecessary re-renders with `useSelector`?** Select narrow slices, use memoized selectors (`reselect`), or a custom equality function (`shallowEqual`).

**Q6.14: What is the difference between normalized and nested state shape in a global store?** Normalized state stores entities by ID in flat lookup tables (like a database), avoiding duplication and making updates to a single entity cheap. Nested state embeds related data directly, which is simpler initially but causes duplication and update headaches as relationships grow.

**Q6.15: What is the Provider hell problem, and how do you avoid it?** Deeply nesting many separate Context Providers at the app root (`<A><B><C><D>`) becomes unreadable. Avoid by composing providers into a single wrapper component, or combining related, co-changing contexts into one.

**Q6.16: What is a selector function? Why is memoizing selectors (e.g., with `reselect`) important?** A function deriving a value from state. Memoizing avoids recomputing (and returning a new reference for) the same derived value on every call when inputs haven't changed, which would otherwise break consumer re-render optimizations.

**Q6.17: What is the difference between global state and server state (cache)?** Global state (UI preferences, auth) is owned entirely by the client. Server state (fetched API data) is actually owned by the server and the client just holds a cached, possibly-stale copy — better managed by a data-fetching library (React Query) than a generic state store.

**Q6.18: How do you persist Redux/Zustand state across page reloads?** `redux-persist` (Redux) or Zustand's built-in `persist` middleware serialize selected state to `localStorage`/`sessionStorage` and rehydrate on load.

**Q6.19: What is the "single source of truth" principle in state management?** Each piece of data should have exactly one authoritative place it lives; everything else derives from or references it, avoiding sync bugs from duplicated copies.

**Q6.20: How do you test components connected to Redux/Zustand?** Wrap the component in a test-specific store instance (seeded with known state) via the real `Provider`, rather than mocking the store entirely, so the real selector/dispatch wiring is exercised.

---

## Section 7 — React Router

**Q7.1: What is client-side routing? How does it differ from server routing?** Intercepts navigation via the History API, swapping components without a full reload/request per navigation.

**Q7.2: `BrowserRouter` vs `HashRouter`?** `BrowserRouter` uses clean URLs via History API (needs server config for refresh). `HashRouter` uses `#` fragments, never hitting the server, zero config but less clean.

**Q7.3: How do you define nested routes (v6+)?** Nest `<Route>` elements; render `<Outlet/>` in the parent for the matched child.

**Q7.4: `useParams`, `useNavigate`, `useSearchParams`?** `useParams` reads dynamic path segments. `useNavigate` programmatically navigates. `useSearchParams` reads/writes the query string.

**Q7.5: How do you implement protected/private routes?** Wrap the element in an auth check that renders children or `<Navigate to="/login"/>`.

**Q7.6: What is route-based code splitting?** Load each route's bundle on demand via `React.lazy` + `Suspense`, reducing initial bundle size.

**Q7.7: What are loaders and actions (v6.4+ data APIs)?** Loaders fetch data before a route renders (`useLoaderData`). Actions handle mutations from `<Form>` submissions (`useActionData`).

**Q7.8: How do you handle 404s in React Router?** A catch-all route with `path="*"` rendering a NotFound component, placed last in the route tree.

**Q7.9: What is the difference between `<Link>` and `<a>`?** `<Link>` intercepts the click and uses client-side navigation (History API) instead of a full page reload `<a>` would trigger.

**Q7.10: What is `<NavLink>`? How does it differ from `<Link>`?** Same as `<Link>` but automatically applies an "active" styling/class when its `to` matches the current URL, useful for nav menus.

**Q7.11: How do you pass state through navigation without putting it in the URL?** `navigate('/path', { state: { from: 'cart' } })`; read it on the destination with `useLocation().state`. Not persisted on refresh (unlike query params).

**Q7.12: How do you implement a layout route (shared header/sidebar across multiple pages)?** A parent `<Route element={<Layout/>}>` wrapping child routes, with `<Layout>` rendering shared chrome plus an `<Outlet/>` for the matched child.

**Q7.13: What is route matching precedence in React Router v6?** V6 uses a ranking algorithm based on specificity (static segments rank higher than dynamic `:param` segments, which rank higher than wildcards) rather than "first match wins" order.

**Q7.14: How do you redirect after a successful form submission/mutation?** Call `navigate('/success')` imperatively after the async action resolves, or return a `redirect()` response from a route action (data API), which React Router handles automatically.

**Q7.15: How do you prevent navigation away from a page with unsaved changes?** Use `useBlocker` (v6.4+ data router) to intercept navigation attempts and show a confirmation prompt before allowing the route change.

---

## Section 8 — Forms & Controlled Components

**Q8.1: How do you build a controlled form in React?** Each input's `value` is driven by state; `onChange` updates that state, making the state object the single source of truth.

**Q8.2: Downsides of fully controlled forms with many fields?** Every keystroke re-renders the owning component; mitigated by libraries keeping fields largely uncontrolled via refs.

**Q8.3: React Hook Form vs Formik?** RHF uses uncontrolled inputs via refs, minimizing re-renders. Formik is more fully controlled, more re-renders but more explicit data flow.

**Q8.4: How do you validate forms with Zod/Yup?** Define a schema; validate values against it on submit/per-field, surfacing field errors; integrates with RHF via resolvers.

**Q8.5: How do you handle file uploads in a form?** File inputs are inherently uncontrolled; read `e.target.files` directly and submit via `FormData`.

**Q8.6: What is debounced input? How do you implement it?** Delaying an expensive operation until typing pauses; implement with a `setTimeout`-based custom Hook reset on each keystroke.

**Q8.7: How do you handle multi-select and checkbox groups as controlled components?** Store selections as an array/Set in state; toggle membership on change rather than tracking each checkbox's own boolean independently, keeping one source of truth for the group.

**Q8.8: What is the difference between `onChange` and `onInput` in React forms?** React's `onChange` fires on every value change (behaving like the native `input` event), unlike the native DOM `change` event which only fires on blur/commit — React normalizes this for consistency.

**Q8.9: How do you reset a form to its initial values?** Either reset the controlling state object back to its initial shape, or (with RHF) call its built-in `reset()` method, or remount via a changed `key`.

**Q8.10: How do you implement field-level async validation (e.g., checking username availability)?** Debounce the field's value, trigger an API call on change (not on every keystroke), and show a pending/error/success state tied to that specific field, cancelling superseded in-flight checks.

**Q8.11: How do you handle a dynamic list of form fields (e.g., "add another email")?** Store the list as an array in state (or RHF's `useFieldArray`), rendering one input per item keyed by a stable ID (not index, since reordering/removal would otherwise misassociate values).

**Q8.12: What's the risk of validating only on submit vs validating as the user types?** Submit-only validation can feel abrupt (all errors appear at once) but avoids distracting/premature errors while typing. Live validation gives faster feedback but needs careful debouncing/timing to avoid flashing errors on a field the user hasn't finished typing into yet.

---

## Section 9 — Performance Optimization

**Q9.1: What causes unnecessary re-renders? How do you identify them?** Unstable prop references, Context changes, state living too high. Identify with the React DevTools Profiler.

**Q9.2: How does `React.memo` prevent re-renders? Limitations?** Shallow-compares props; skips re-render if equal. Doesn't help if props are new references every render (needs `useMemo`/`useCallback` upstream).

**Q9.3: How do you virtualize long lists? Why?** Only render visible DOM nodes (plus buffer) via `react-window`/`react-virtuoso`, reducing DOM node count for scroll performance.

**Q9.4: What is code splitting? How with `React.lazy`/`Suspense`?** Splitting the bundle into on-demand chunks; `React.lazy(() => import(...))` + `<Suspense fallback>`.

**Q9.5: What is the React DevTools Profiler used for?** Records renders, showing a flame graph of duration and "why did this render" causes.

**Q9.6: How do you avoid creating new object/array/function references every render?** Memoize with `useMemo`/`useCallback`, or move static values/handlers outside the component.

**Q9.7: What is windowing? Name a library.** List virtualization; `react-window` or `@tanstack/react-virtual`.

**Q9.8: How do you measure/optimize bundle size and Time to Interactive?** Lighthouse/`webpack-bundle-analyzer`; code split, tree-shake, replace heavy deps, defer non-critical scripts.

**Q9.9: Does the cost of inline arrow functions in JSX always matter?** No — harmless for plain DOM elements; matters mainly when breaking `React.memo` on a custom child component.

**Q9.10: What is the "render props waterfall" performance risk?** Deeply nested render-prop/HOC wrapping can cause every layer to re-render together even when only the innermost data changed, since each wrapper re-renders its children as part of its own render output.

**Q9.11: How do you profile and fix a slow initial page load vs a slow interaction?** Initial load: Lighthouse/bundle analysis, code-splitting, SSR/streaming. Interaction: DevTools Profiler during the specific interaction, looking for expensive re-renders or synchronous work blocking the main thread.

**Q9.12: What is the cost of excessive Context nesting on performance?** Each additional Context layer a component consumes adds another subscription that can trigger a re-render; deeply nested or frequently-changing contexts compound unnecessary renders across many consumers.

**Q9.13: How do you prevent an expensive component from blocking user input (e.g., a large table filtering as you type)?** `useTransition` to mark the expensive re-render as low priority, or `useDeferredValue` on the filter text, keeping the input responsive while the table catches up.

**Q9.14: What is the "double render" cost of Strict Mode in development? Does it affect production?** Strict Mode intentionally double-invokes render/effect logic in development to surface side effects, roughly doubling dev-time render cost — but it has zero effect on the production build's actual performance.

**Q9.15: How do you avoid re-rendering a large list when only one item's data changes?** Memoize list item components (`React.memo`) and ensure each item's props (including any callback) are referentially stable, so updating one row's data doesn't cascade a re-render through every row.

**Q9.16: What is image lazy-loading in React? How do you implement it?** Deferring offscreen image loads until they're near the viewport, via the native `loading="lazy"` attribute on `<img>` or an `IntersectionObserver`-based custom component for more control (placeholders, fade-in).

**Q9.17: How do you reduce the performance cost of a component that re-renders on every scroll event?** Throttle/debounce the scroll handler, or better, derive the needed value (e.g., scroll position bucket) and only call `setState` when that derived value actually changes, avoiding a state update (and render) on every pixel of scroll.

**Q9.18: What is "hydration cost" in SSR apps, and how do you reduce it?** The time/CPU spent re-running component JS to attach event listeners to server-rendered HTML. Reduce via selective/progressive hydration (Suspense boundaries), reducing the amount of interactive (Client Component) code shipped, and deferring non-critical component hydration.

---

## Section 10 — Error Handling & Error Boundaries

**Q10.1: What is an Error Boundary? What errors does it NOT catch?** A class component with `getDerivedStateFromError`/`componentDidCatch` catching render/lifecycle/constructor errors in its child tree. Does NOT catch event handler, async, or SSR errors.

**Q10.2: Why must Error Boundaries be class components?** No Hook equivalent of those lifecycle methods exists yet; teams write one reusable class-based boundary or use `react-error-boundary`.

**Q10.3: How do you handle errors from event handlers or async code?** `try/catch` inside the handler/async function, updating error state, or a global `window.addEventListener('error'/'unhandledrejection')`.

**Q10.4: How do you implement a global fallback UI?** Wrap the app root (or sections) in `<ErrorBoundary fallback={<ErrorPage/>}>`, nesting at different granularities.

**Q10.5: How do you log errors caught by an Error Boundary to a monitoring service (e.g., Sentry)?** Call the logging SDK inside `componentDidCatch(error, errorInfo)`, which receives both the error and the component stack trace, then report it before rendering the fallback UI.

**Q10.6: What is the difference between a recoverable and an unrecoverable error in a React app's error-handling strategy?** A recoverable error (e.g., a failed API call) can show an inline retry UI while the rest of the app keeps working. An unrecoverable error (e.g., corrupted app state) may require a full Error Boundary fallback or forced reload, since continuing to render could produce further incorrect behavior.

**Q10.7: How do you reset an Error Boundary after the user retries (e.g., clicking "Try again")?** Change the boundary's `key` prop to force a fresh mount, or use `react-error-boundary`'s `resetErrorBoundary`/`onReset` support to clear the caught error and re-render children.

**Q10.8: Why can't a single top-level Error Boundary be a complete error-handling strategy?** One crash anywhere takes down the entire app's UI behind a single fallback; nesting boundaries around independent sections (widgets, routes) isolates failures so one broken part doesn't block the rest.

---

## Section 11 — Data Fetching & React Query

**Q11.1: What problems does React Query solve vs raw `useEffect` fetching?** Caching, request dedup, background refetch, retries, stale-while-revalidate, and loading/error states out of the box.

**Q11.2: `staleTime` vs `cacheTime`/`gcTime`?** `staleTime`: how long data is "fresh." `gcTime`: how long unused cached data stays before garbage collection.

**Q11.3: What is query invalidation? How do you trigger a refetch after a mutation?** `queryClient.invalidateQueries({ queryKey })` marks queries stale, refetching on next use — typically called in a mutation's `onSuccess`.

**Q11.4: What is optimistic UI? How do you implement it?** Update the UI immediately before server confirmation, roll back on failure, via `onMutate`/`onError`/`onSettled`.

**Q11.5: SWR vs React Query?** SWR is lighter with similar stale-while-revalidate philosophy; React Query has richer built-ins (optimistic helpers, infinite queries, DevTools).

**Q11.6: What is `useInfiniteQuery`? When is it used?** Manages paginated data that loads incrementally (e.g., infinite scroll), tracking pages and providing a `fetchNextPage` function tied to a `getNextPageParam` cursor function.

**Q11.7: How do you deduplicate identical simultaneous requests?** React Query automatically dedupes identical in-flight queries (same query key) triggered by multiple components, serving them from one network request.

**Q11.8: What is the difference between `isLoading` and `isFetching` in React Query?** `isLoading` is true only during the very first fetch (no cached data yet). `isFetching` is true any time a request is in flight, including background refetches of already-cached data.

**Q11.9: How do you handle dependent/sequential queries (query B needs query A's result)?** Use the `enabled` option: `useQuery({ queryKey: ['b', aData?.id], queryFn: ..., enabled: !!aData })`, so query B only runs once `aData` is available.

**Q11.10: What is prefetching in React Query? When would you use it?** `queryClient.prefetchQuery(...)` loads data into the cache before it's needed (e.g., on hover over a link, or in a route loader), so the eventual component render finds data already cached.

**Q11.11: How do you cancel a query automatically when its component unmounts?** React Query handles this internally by default for the underlying fetch (via `AbortSignal` passed to the query function) when a query becomes unused and its `gcTime` conditions are met or when manually cancelled via `queryClient.cancelQueries`.

**Q11.12: What is the difference between a "query" and a "mutation" in React Query?** Queries are for reading/caching data (GET-like, retried automatically, cached). Mutations are for creating/updating/deleting data (side-effecting, not cached, triggered imperatively).

---

## Section 12 — Styling in React

**Q12.1: What are CSS Modules? How do they prevent collisions?** Locally-scoped class names via hashed generation at build time, imported as an object.

**Q12.2: What is CSS-in-JS? Trade-offs vs traditional CSS?** Writing CSS in JS (`styled-components`/Emotion), scoped per component, dynamic via props — at the cost of runtime overhead and bundle size.

**Q12.3: What is Tailwind CSS? How does it differ from CSS-in-JS?** Utility-first classes composed in markup, compiled/purged to plain CSS at build time, no runtime JS styling cost.

**Q12.4: How do you handle conditional class names?** `clsx`/`classnames`: `clsx('btn', { 'btn-active': isActive })`.

**Q12.5: What is a design system / component library pattern?** Shared, consistently-styled primitives and design tokens used across products for visual/behavioral consistency.

**Q12.6: What is a "zero-runtime" CSS-in-JS library (e.g., vanilla-extract, Panda CSS)? How does it differ from `styled-components`?** It extracts styles to static CSS files at build time rather than injecting `<style>` tags at runtime, giving CSS-in-JS's developer ergonomics (colocated, typed styles) without the runtime performance cost.

**Q12.7: What is the "FOUC" (flash of unstyled content) risk with runtime CSS-in-JS in SSR, and how is it mitigated?** If styles are injected client-side after hydration, the user may briefly see unstyled markup. Mitigated by extracting critical CSS server-side and inlining it in the initial HTML response (most CSS-in-JS libraries provide an SSR extraction API for this).

**Q12.8: How do you theme a React app (light/dark mode) cleanly?** Define theme values as CSS custom properties or a theme object, toggle a root-level class/attribute (`data-theme="dark"`) or Context provider, and have styled components/CSS reference the theme tokens rather than hardcoded values.

---

## Section 13 — Testing React Applications

**Q13.1: What is React Testing Library (RTL)? What is its core philosophy?** "Test your software the way users use it" — query by accessible roles/labels/text, not implementation details.

**Q13.2: `render`, `screen`, `fireEvent`/`userEvent`?** `render` mounts; `screen` provides queries; `userEvent` simulates realistic interactions (preferred over `fireEvent`).

**Q13.3: Why does RTL discourage test IDs/class names? When is `data-testid` appropriate?** Accessible queries keep tests resilient and verify actual accessibility. `data-testid` only as a fallback when no accessible query exists.

**Q13.4: How do you test a component that fetches data in `useEffect`?** Mock the request (`msw`/`jest.mock`), render, then `findByText`/`waitFor` for the resolved content.

**Q13.5: How do you test custom Hooks?** `renderHook` mounts the hook in a minimal test component, exposing `result.current`; wrap updates in `act()`.

**Q13.6: What is `act()`? Why does RTL warn about updates outside it?** Ensures updates/effects/re-renders are flushed before assertions; RTL wraps this internally, warning fires for manual async updates outside it.

**Q13.7: How do you mock API calls with `msw`?** Intercepts actual network requests at the network layer, returning fixture responses without the component knowing it's mocked.

**Q13.8: What is snapshot testing? When is it useful vs risky?** Serializes rendered output for comparison; useful for stable presentational components, risky as a primary strategy (hard to meaningfully review, easy to blindly update).

**Q13.9: How do you test components wrapped in Providers/Router?** A custom `render` wrapper that wraps the component in needed providers, reused across tests.

**Q13.10: How do you test that a component is accessible?** `jest-axe` runs axe-core against the rendered HTML, asserting no violations: `expect(await axe(container)).toHaveNoViolations()`.

**Q13.11: How do you test error states (e.g., a failed API call shows an error message)?** Mock the request to reject/return an error response via `msw`, render the component, and assert the error UI appears via `findByText`/`findByRole`.

**Q13.12: What is the difference between `getBy`, `queryBy`, and `findBy` in RTL?** `getBy*` throws immediately if not found (for elements expected to exist). `queryBy*` returns `null` instead of throwing (for asserting something is *absent*). `findBy*` is async, retrying until found or timing out (for elements that appear after an async update).

**Q13.13: How do you test a component with React Router routes?** Wrap it in `<MemoryRouter initialEntries={['/some/path']}>` to simulate a specific URL without a real browser, then assert on rendered route content or navigation behavior.

**Q13.14: What is test isolation, and why does it matter for React component tests?** Each test should run independently without leaking state (mocks, timers, DOM) into the next. RTL's `render` auto-cleans up the DOM after each test (via `afterEach(cleanup)`, often automatic), preventing one test's rendered output from bleeding into another's assertions.

**Q13.15: How do you test a component using fake timers (e.g., a debounce or a countdown)?** `jest.useFakeTimers()`, trigger the action, then `jest.advanceTimersByTime(ms)` or `jest.runAllTimers()` to fast-forward, asserting the expected state after the delay — avoiding real wall-clock waits in tests.

---

## Section 14 — TypeScript with React

**Q14.1: How do you type a function component's props?** `interface Props { label: string; onClick: () => void }` as the function's parameter type; `React.FC<Props>` is generally discouraged now.

**Q14.2: How do you type `useState` when the initial value doesn't convey the full type?** `useState<User | null>(null)` — supply an explicit generic.

**Q14.3: How do you type event handlers?** `React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`.

**Q14.4: How do you type `useRef` for a DOM node vs a mutable value?** `useRef<HTMLInputElement>(null)` for DOM; `useRef<number>(0)` for a freely mutable instance value.

**Q14.5: How do you type `children`?** `React.ReactNode` covers the broadest, most common case.

**Q14.6: How do you create a generic, reusable component?** `function List<T>({ items, renderItem }: { items: T[]; renderItem: (item: T) => React.ReactNode })`.

**Q14.7: How do you type a custom Hook's tuple return value?** Annotate the return type explicitly as a tuple, since TS otherwise infers an array literal as a union array.

**Q14.8: How do you discriminate prop variants (discriminated unions)?** A shared literal "kind" field narrows which other props are required for each variant.

**Q14.9: What is the difference between `interface` and `type` for defining props? When does it matter?** Both work for most prop definitions; `interface` supports declaration merging (useful for extending `Express.Request`-style ambient types) while `type` supports unions/intersections more directly. For simple component props, the choice is largely stylistic/team convention.

**Q14.10: How do you type a component that accepts all native `<button>` props plus custom ones?** `interface ButtonProps extends React.ButtonHTMLAttributes<HTMLButtonElement> { variant?: 'primary' | 'secondary' }`, then spread `{...rest}` onto the native `<button>`.

**Q14.11: How do you type a `forwardRef` component?** `forwardRef<HTMLInputElement, InputProps>((props, ref) => ...)` — the first generic is the ref's type, the second is the props type.

**Q14.12: How do you avoid `any` when typing a third-party library without TypeScript definitions?** Write a local `.d.ts` declaration file with minimal type definitions for the parts you use, or check if `@types/<package>` exists on DefinitelyTyped before falling back to `any`/`unknown` with manual runtime checks.

**Q14.13: How do you type a reducer function and its actions for `useReducer`?** Define a discriminated union for actions (`type Action = { type: 'increment' } | { type: 'set'; payload: number }`), then `function reducer(state: State, action: Action): State`, letting TypeScript narrow `action.payload` based on `action.type` inside each case.

**Q14.14: What is `satisfies` and how is it useful for typing component configuration objects?** `satisfies` checks a value against a type without widening/changing the value's inferred type, useful for config objects (e.g., a theme or route map) where you want both validation against a shape and precise literal-type inference preserved for later use.

**Q14.15: How do you type `useContext` so consumers get a properly-typed value (and a helpful error if used outside the Provider)?** Type the context as `createContext<ContextType | undefined>(undefined)`, then write a custom `useMyContext()` Hook that throws a clear error if the value is `undefined`, letting consumers use a properly-narrowed, non-nullable type.

---

## Section 15 — Server-Side Rendering & Next.js

**Q15.1: What is SSR? What problem does it solve vs a pure client-rendered SPA?** Generates initial HTML on the server with real content, improving perceived load and SEO vs an empty client-rendered shell.

**Q15.2: What is hydration? What can go wrong during it?** React attaches to server-rendered HTML, reusing nodes and wiring listeners. A "hydration mismatch" occurs if client and server output differ.

**Q15.3: SSR vs SSG vs ISR?** SSR: rendered per request. SSG: rendered once at build time. ISR: statically generated but regenerated in the background after an interval.

**Q15.4: What is the Next.js App Router vs Pages Router?** App Router (`app/`) uses Server Components, nested layouts, file conventions. Pages Router (`pages/`) is Client Components by default with `getServerSideProps`/`getStaticProps`.

**Q15.5: What are React Server Components (RSC)? How do they differ from SSR?** Run only on the server, never shipped to the client bundle, can access backend resources directly; SSR still ships and re-hydrates component JS client-side.

**Q15.6: What is the `'use client'` directive? When do you need it?** Marks a Client Component boundary for anything using Hooks, event handlers, or browser APIs.

**Q15.7: How do you fetch data in the App Router?** Server Components can be `async` and `await fetch(...)` directly — no `useEffect`/loading boilerplate.

**Q15.8: What is streaming SSR? How does `Suspense` enable it?** Sends the page shell immediately, streaming in slower parts wrapped in their own `Suspense` boundaries as they become ready.

**Q15.9: Server Action vs API route?** A Server Action is callable directly from components/forms with Next.js handling the network call. An API route is an explicit, stable HTTP endpoint.

**Q15.10: What is `getStaticPaths` (Pages Router)? When is it needed?** Defines which dynamic routes (`[slug].js`) to pre-render at build time for SSG, specifying a `fallback` strategy for paths not pre-rendered.

**Q15.11: What is Incremental Static Regeneration's `revalidate` option?** A time (in seconds) after which Next.js will regenerate a statically generated page in the background on the next request, serving the stale version until the new one is ready.

**Q15.12: How does Next.js handle image optimization?** The `next/image` component automatically resizes, optimizes format (WebP/AVIF), lazy-loads, and prevents layout shift via required width/height or `fill`.

**Q15.13: What is middleware in Next.js? Give a use case.** Code that runs before a request completes, at the edge, for tasks like auth redirects, A/B test routing, or geolocation-based rewrites, defined in a `middleware.ts` file.

**Q15.14: What is the difference between a dynamic and a static route segment caching behavior in the App Router?** Static segments (no dynamic data dependencies) are cached and reused across requests by default. Using dynamic functions (`cookies()`, `headers()`) or `cache: 'no-store'` on a fetch opts a route into fully dynamic, per-request rendering.

**Q15.15: What is parallel data fetching in Server Components, and why does it matter?** Starting multiple independent `fetch` calls without sequentially `await`-ing each one before the next starts, avoiding request waterfalls and reducing total time-to-render.

**Q15.16: What is the difference between `next/link` prefetching and a manual `router.prefetch()` call?** `<Link>` automatically prefetches linked pages' code/data when they enter the viewport (in production). `router.prefetch()` lets you trigger the same prefetching imperatively (e.g., on hover or a predicted next action) outside of a visible `<Link>`.

**Q15.17: How do environment variables work differently between server and client code in Next.js?** Only variables prefixed `NEXT_PUBLIC_` are inlined into the client bundle and accessible in browser code; unprefixed variables are only available in server-side code (Server Components, API routes, `getServerSideProps`), keeping secrets out of the client bundle.

**Q15.18: What is the risk of putting sensitive logic/secrets in a Client Component by mistake?** Anything in a `'use client'` module (and its non-server imports) ships to the browser bundle, so secrets or sensitive business logic placed there become visible/extractable by anyone inspecting the client JS.

---

## Section 16 — React 18/19 — Concurrent Features & Server Components

**Q16.1: What is concurrent rendering?** React can prepare multiple UI versions and interrupt/abandon in-progress work to prioritize urgent updates, rather than always running a render to completion.

**Q16.2: What is `Suspense`? How does it work for data fetching?** Shows a fallback while children aren't ready; extended via the `use` Hook/RSC to data fetching — a component "suspends" by throwing a promise.

**Q16.3: `useTransition` vs `Suspense`?** `Suspense` declares what fallback to show; `useTransition` declares how urgent an update is, keeping old UI visible while preparing the new one.

**Q16.4: What are React 19's main additions?** Actions (`<form action={...}>`), `useActionState`, `useOptimistic`, and the `use` Hook for reading promises/context in render.

**Q16.5: What is selective hydration? Why does it matter?** React hydrates parts of the page as their HTML/JS arrive and as the user interacts, rather than waiting for the whole page.

**Q16.6: What is the difference between `startTransition` and `useTransition`?** `startTransition` is the standalone function (usable outside components, e.g. in a vanilla event handler) for marking an update as a transition; `useTransition` is the Hook version that also gives you an `isPending` boolean for showing a pending UI state.

**Q16.7: What is automatic batching (React 18)? What changed from React 17?** React 18 batches state updates from *any* source (promises, timeouts, native event handlers), not just React's own event handlers as in React 17 and earlier, reducing unnecessary intermediate re-renders.

**Q16.8: What does it mean for a component to "suspend"? What triggers it?** A component suspends when it throws a Promise during render (directly, via `use()`, or via a Suspense-integrated data-fetching library), signaling to React "I'm not ready yet" so the nearest Suspense boundary shows its fallback until the promise resolves.

**Q16.9: What is the risk of using `key` to force-remount a component during a transition?** It discards all internal state of the remounted subtree immediately rather than smoothly transitioning, defeating the purpose of `useTransition`'s "keep old UI visible while preparing new" behavior — generally these two patterns solve different problems and shouldn't be combined carelessly.

**Q16.10: How does `useOptimistic` (React 19) differ from manually managing optimistic state with `useState`?** `useOptimistic` automatically reverts to the real state once the underlying async action settles (success or failure), removing the need to manually track and roll back a separate "pending" state variable yourself.

**Q16.11: What is the difference between a transition and a regular (synchronous) state update in terms of interruptibility?** A regular update renders to completion and commits as soon as possible (urgent). A transition's render work can be paused, abandoned, or restarted if a more urgent update comes in before it finishes, keeping the UI responsive.

**Q16.12: Why can Suspense boundaries be nested, and what determines which one catches a given suspension?** The nearest ancestor Suspense boundary to the component that suspended catches it and shows its fallback, letting different parts of a tree show independent loading states rather than one fallback blocking the entire page.

---

## Section 17 — Design Patterns in React

**Q17.1: What is the Compound Components pattern?** Components sharing implicit state via Context, giving flexible structure: `<Tabs><Tabs.List>...</Tabs.List></Tabs>`.

**Q17.2: What is the Container/Presentational pattern? Still relevant with Hooks?** Separating data-fetching "smart" containers from "dumb" rendering. With Hooks, the split often moves into a custom Hook instead of two files.

**Q17.3: What is the Provider pattern?** A component "providing" shared data/functions to descendants without prop drilling, implemented via Context's `Provider`.

**Q17.4: What is the Controlled/Uncontrolled hybrid pattern?** A component accepts optional `value`/`onChange` for controlled use, falling back to internal state via `defaultValue` otherwise.

**Q17.5: What is the Headless Component pattern?** Implements behavior/state logic with no markup/styling of its own, leaving visual output to the consumer (e.g., Radix primitives).

**Q17.6: What is the Slot pattern?** A component accepts other components as props for specific "slots" (`<Layout header={<Nav/>}>`), giving the caller control over region content.

**Q17.7: What is the "props getter" pattern used by headless libraries (e.g., downshift)?** Instead of exposing raw state, the Hook returns functions like `getInputProps()` / `getItemProps()` that spread the correct ARIA attributes and event handlers onto the consumer's own markup, bundling correct behavior without dictating the DOM structure.

**Q17.8: What is the "state reducer" pattern?** A component/Hook accepts an optional reducer function from the consumer to intercept and customize internal state transitions, giving advanced consumers control over behavior the component wouldn't otherwise expose via simple props.

**Q17.9: What is the difference between a Compound Component and a Slot-based component?** Compound Components implicitly share state via Context between a fixed set of sub-components (`<Tabs.Tab>` knows which `<Tabs>` it belongs to). Slot-based components explicitly receive arbitrary content/components as props without that implicit shared-state wiring.

**Q17.10: What is the "Portal" pattern, and when do you use it?** Rendering a component's output into a different part of the DOM tree (via `createPortal`) than its logical position in the React tree — typically for modals, tooltips, or dropdowns that need to escape a parent's `overflow: hidden` or `z-index` stacking context.

**Q17.11: What is the "render in a loop with composition" pattern vs a monolithic configurable component?** Instead of one component with many conditional props controlling every variant (`<Card showHeader showFooter variant=...>`), composing smaller pieces (`<Card><Card.Header/><Card.Body/></Card>`) that the consumer assembles as needed, improving flexibility without prop explosion.

**Q17.12: What is a factory/builder pattern for creating typed, reusable form field components?** A function that generates a pre-configured, typed field component bound to a specific form library/schema (e.g., `createFormField<FormValues>()`), reducing repetitive boilerplate across many similar fields while preserving type safety.

**Q17.13: How does the "Compound Components" pattern handle components that aren't direct children (e.g., nested in a wrapper div)?** Using `React.Children.map`/`cloneElement` (older approach, fragile with nesting) or, more robustly, Context — so sub-components can be nested arbitrarily deep and still read shared state/behavior without relying on direct parent-child positioning.

**Q17.14: What is the trade-off of the Compound Components pattern vs a single component with a declarative config object/array prop?** Compound Components give a more flexible, JSX-native, readable API (the consumer controls layout/order freely) but require more setup (Context plumbing) and are less convenient to generate dynamically from data; a config-array prop is easier to generate programmatically but less flexible for custom layout per-item.

**Q17.15: What is the Observer/Pub-Sub pattern's use in React outside of Context (e.g., a lightweight event bus for cross-cutting concerns)?** A module-level event emitter that components `subscribe`/`publish` to for concerns that don't fit cleanly into the component tree's data flow (e.g., a toast system triggered from non-component code, or a global "logout" event), avoiding the need to lift that state into React itself.

---

## Section 18 — Accessibility (a11y)

**Q18.1: Why does accessibility matter in a React app, differently from "regular" HTML?** React doesn't change DOM accessibility rules; the risk is component abstractions (custom dropdowns, `<div onClick>`) silently losing semantics native elements give for free.

**Q18.2: How do you manage focus during SPA route changes?** Move focus programmatically to the new page's main heading/content on route change, since there's no full reload to reset it naturally.

**Q18.3: How do you build an accessible modal?** Trap focus, `role="dialog"`/`aria-modal`, label it, return focus to the trigger on close, close on `Escape` — or use Radix UI/React Aria.

**Q18.4: What is `eslint-plugin-jsx-a11y`? What does it catch?** An ESLint plugin flagging common a11y mistakes in JSX statically (missing `alt`, missing keyboard handlers, invalid ARIA usage).

**Q18.5: How do you test accessibility in components (`jest-axe`)?** Runs axe-core against rendered HTML, asserting no violations automatically in CI.

**Q18.6: What is the difference between `aria-label` and `aria-labelledby`?** `aria-label` provides an inline accessible name string directly. `aria-labelledby` references the `id` of another element on the page whose text content becomes the accessible name — useful when the visible label already exists elsewhere in the DOM.

**Q18.7: How do you make a custom dropdown/combobox accessible (keyboard support)?** Support arrow keys to move selection, Enter/Space to select, Escape to close, Home/End to jump to first/last option, and set `role="listbox"`/`role="option"` with `aria-selected`/`aria-activedescendant` appropriately.

**Q18.8: What is a "skip to content" link, and why is it important?** A visually-hidden (until focused) link at the very top of the page that lets keyboard users jump directly past repeated navigation to the main content, avoiding having to Tab through the entire nav on every page.

**Q18.9: How do you announce dynamic content changes to screen reader users (e.g., a toast notification)?** Use an `aria-live="polite"` (or `"assertive"` for urgent messages) region; content inserted into it is automatically announced by screen readers without requiring focus to move there.

**Q18.10: What is the risk of using a non-semantic element (`<div>`/`<span>`) with an `onClick` handler for something interactive?** It's not focusable or keyboard-operable by default, isn't announced as a button/link by screen readers, and doesn't support Enter/Space activation — all of which a native `<button>`/`<a>` provides for free.

**Q18.11: How do you ensure form validation errors are accessible?** Associate the error message with its field via `aria-describedby`, and optionally set `aria-invalid="true"` on the field, so screen reader users hear the error when focusing or reviewing the field, not just see red text.

**Q18.12: What is color contrast, and how do you verify a React app meets WCAG requirements?** Sufficient contrast between text and background colors for readability, especially for low-vision users. Verify with tools like the axe DevTools extension, Lighthouse's accessibility audit, or a contrast-checker against WCAG AA/AAA thresholds.

---

## Section 19 — Build Tools & Bundling

**Q19.1: Webpack vs Vite vs esbuild/SWC for a React app?** Webpack: configurable, bundles everything (can be slow). Vite: native ESM in dev (fast start), Rollup for prod. esbuild/SWC: much faster Go/Rust-based compilers, often used underneath other tools.

**Q19.2: What is tree shaking? What's required for it to work?** Eliminating unused exports; requires ES Module syntax (statically analyzable) and side-effect-free library builds.

**Q19.3: What is `React.lazy()` plus dynamic `import()`? How does the bundler use it?** Tells the bundler to split that module and its deps into a separate chunk, loaded on demand when `import()` executes at runtime.

**Q19.4: Why did Create React App fall out of favor? What replaced it?** Slow Webpack-based tooling, limited configurability; superseded by Vite (SPAs) or meta-frameworks (Next.js/Remix) for SSR/routing conventions.

**Q19.5: What is the difference between a bundler and a compiler/transpiler in the React toolchain (e.g., Webpack vs Babel/SWC)?** A compiler/transpiler (Babel, SWC) transforms source syntax (JSX, newer JS, TypeScript) into code the target environment understands. A bundler (Webpack, Rollup, Vite's build step) combines many modules/files into optimized output bundles, handling code splitting, asset processing, and dependency graphs — they're complementary, often used together.

**Q19.6: What is Hot Module Replacement (HMR)? Why does it matter for React development?** HMR swaps updated modules in a running app without a full page reload, preserving component state during development (e.g., keeping a form's typed input while you tweak its styling), dramatically speeding up the dev feedback loop.

**Q19.7: What is the difference between a development build and a production build of a React app?** Development builds include extra warnings, Strict Mode double-invocation, unminified code with readable stack traces, and devtools hooks. Production builds strip these, minify/mangle code, and often run additional optimizations (dead code elimination), resulting in a smaller, faster bundle with less helpful error messages.

**Q19.8: What is a monorepo, and what tools help manage one for a React codebase (e.g., sharing a component library across apps)?** A single repository containing multiple packages/apps (e.g., a shared UI library plus several apps consuming it). Tools like Turborepo, Nx, or Yarn/pnpm workspaces manage shared dependencies, incremental builds, and task caching across the packages.

**Q19.9: What is source map generation, and why is it important in a production React deployment?** Source maps map minified/bundled production code back to original source lines, letting you read meaningful stack traces from production error reports (e.g., in Sentry) without shipping readable source code to end users (maps are uploaded separately, not served publicly).

**Q19.10: What is the purpose of a `postcss`/Tailwind build step in a React project, and how does it interact with the bundler?** PostCSS (often running Tailwind's engine) transforms authored CSS — expanding utility classes, adding vendor prefixes (autoprefixer), purging unused classes — before the bundler includes the resulting CSS in the final build output.

---

## Section 20 — Security

**Q20.1: Is React safe from XSS by default? When can it still occur?** React escapes interpolated values by default. XSS can still occur via `dangerouslySetInnerHTML` with unsanitized input, a user-controlled `javascript:` URL, or a DOM-manipulating third-party library.

**Q20.2: How do you safely render user-generated HTML?** Sanitize via `DOMPurify` before passing to `dangerouslySetInnerHTML`.

**Q20.3: What is a `javascript:` URL injection risk? How do you prevent it?** A user-controlled `href`/`src` could contain `javascript:alert(1)`. Prevent via scheme allow-listing before rendering.

**Q20.4: How do you securely store/use an auth token in a React SPA?** Prefer an HttpOnly, Secure, `SameSite` cookie over `localStorage` (readable by any injected script).

**Q20.5: What is a Content Security Policy (CSP)? How does it help?** Restricts allowed script/style/resource sources, mitigating XSS impact even if a vulnerability exists.

**Q20.6: What is the risk of exposing API keys/secrets in a client-side React bundle?** Anything bundled for the browser (including `NEXT_PUBLIC_`-prefixed or hardcoded values) is visible to anyone inspecting the JS; secrets must stay server-side, with the client calling a backend proxy instead.

**Q20.7: What is a Subresource Integrity (SRI) hash, and when would a React app use one?** A hash attribute on a `<script>`/`<link>` tag verifying a CDN-loaded file hasn't been tampered with; relevant when loading a library (e.g., via a CDN `<script>` tag in an HTML template) from a third-party host outside your build pipeline.

**Q20.8: How do you prevent clickjacking in a React app?** Set the `X-Frame-Options` header (or CSP's `frame-ancestors` directive) on the server/CDN response to prevent the app from being embedded in a malicious iframe on another site.

**Q20.9: What is the risk of trusting `window.postMessage` data without validation in a React component?** Any page can send a `postMessage` to your window; without checking `event.origin` against an allow-list and validating the message shape, a malicious page could inject fake data or trigger unintended state changes.

**Q20.10: How do you prevent a dependency supply-chain attack from affecting a React app?** Pin exact dependency versions (lockfile committed), run `npm audit`/Snyk in CI, review new dependencies before adding them, and consider a private registry proxy that vets packages.

**Q20.11: What is the security consideration around React Server Components and passing data from server to client?** Data passed as props from a Server Component into a Client Component is serialized and does ship to the browser; sensitive fields fetched server-side must be explicitly excluded from what's passed down, not just "kept on the server" by assumption.

**Q20.12: How do you prevent open redirect vulnerabilities in a React Router app (e.g., a `?redirect=` query param)?** Validate that the redirect target is a relative, same-origin path (not an arbitrary external URL) before calling `navigate()`/`window.location`, rejecting or ignoring untrusted absolute URLs.

---

## Section 21 — Advanced / Senior-Level Questions

**Q21.1: Walk through the complete lifecycle of a user interaction — from click to painted update.** Event fires → SyntheticEvent dispatched → handler runs, schedules update → React re-renders (interruptible) → reconciliation diff → commit (DOM mutation, synchronous) → layout effects run → paint → passive effects run.

**Q21.2: Why does React re-render the whole component function on every update rather than patching just changed JSX?** Re-running the function is what makes the model declarative; performance is recovered via cheap reconciliation and explicit `memo` rather than skipping the function call itself.

**Q21.3: What is referential equality, and why does it matter so much in React?** Same-object identity (`===`) vs structural equality. React's optimizations rely on cheap reference checks, so "new but equivalent" objects defeat them.

**Q21.4: How would you debug a component re-rendering far more than expected?** Profiler recording → check unstable prop references → check Context Provider value memoization → check effect/memo dependency arrays → consider state placement.

**Q21.5: How do you design a component library that's flexible and consistent org-wide?** Headless primitives for behavior/accessibility, shared design tokens, strict controlled/uncontrolled prop conventions, accessibility testing, Storybook for discoverability.

**Q21.6: How do you handle a memory leak from a subscription in a component?** Most commonly a missing `useEffect` cleanup; always return an unsubscribe/clear function, watch for "state update on unmounted component" warnings.

**Q21.7: How do you architect state for a large app with global and feature-local state?** Colocate state locally by default; Context for static global concerns; a dedicated library for complex/frequent updates, organized per-feature.

**Q21.8: Trade-offs of Server Components vs a traditional client-rendered SPA?** Smaller client bundles, direct backend access, better SEO/initial load — at the cost of a more complex mental model and framework lock-in; interactive-heavy apps still need substantial Client Component logic.

**Q21.9: How do you prevent waterfall requests in a component tree?** Start independent fetches in parallel (RSC siblings fetch concurrently by default; client-side use `Promise.all`/`useQueries`) rather than nested sequential `await`s.

**Q21.10: How do you handle feature flags cleanly in a React codebase?** Wrap checks in a Hook/component abstraction backed by a flag SDK, keeping logic swappable and dead flags easy to find and remove later.

**Q21.11: What is the "two render passes" behavior you might see in React 18 Strict Mode, and why doesn't it indicate a bug by itself?** Strict Mode intentionally renders twice in development to help surface components/effects that aren't pure or properly cleaned up; the second pass's output is discarded and this never happens in production, so by itself it's a detection tool, not a sign of broken app behavior.

**Q21.12: How would you design the data layer for an app that needs to work offline and sync later?** Use a local-first store (IndexedDB via a library, or a sync engine) as the source of truth for reads/writes while offline, queue mutations, and reconcile with the server (via timestamps, versioning, or CRDTs for conflict resolution) once connectivity returns.

**Q21.13: How do you decide between fetching data in a Server Component vs a Client Component with React Query?** Server Component fetching is simpler and ships no client JS for that data, ideal for content that doesn't need client-side caching/refetching/mutation UX. React Query fits when you need client-side cache invalidation, optimistic updates, polling, or the data is tied to client-only interaction (e.g., live search).

**Q21.14: What is the risk of relying on array order as an implicit key source when list items can be both reordered and have per-item local state (e.g., an expanded/collapsed toggle)?** Reordering without changing the index-derived key causes React to reuse DOM nodes/state for the wrong logical item — an expanded row's "expanded" state can appear to jump to a different item after reordering, since React thinks it's the same component instance.

**Q21.15: How do you approach migrating a large class-component codebase to Hooks incrementally without a risky big-bang rewrite?** Migrate leaf/simple components first (lowest risk, easiest to verify), convert shared logic into custom Hooks usable by both old and new components during the transition, and keep Error Boundaries (still class-only) as a stable exception rather than forcing their conversion.

---

## Section 22 — Scenario-Based / System Design Questions

**Q22.1: Design a typeahead/autocomplete search component.** Debounced controlled input; cancel in-flight requests with `AbortController`; cache recent results; keyboard navigation with `role="combobox"`; loading/no-results states.

**Q22.2: Design an infinite-scrolling feed.** `IntersectionObserver` sentinel; cursor-based pagination; virtualize once large; `useInfiniteQuery`; preserve scroll position on back-navigation.

**Q22.3: Design a real-time collaborative form/editor.** WebSocket sync with optimistic local updates; conflict resolution (last-write-wins or CRDT/OT); throttled outgoing changes; presence indicators; reconnection resync.

**Q22.4: Design a multi-step wizard with back-navigation that preserves data.** Lift all step data into one central state object; per-step validation before "Next"; persist progress to storage; reflect current step in the URL.

**Q22.5: Design a dashboard with many independent, simultaneously-loading widgets.** Each widget fetches independently and in parallel; its own Suspense/Error Boundary pair; skeleton loaders; coordinated polling to avoid redundant requests.

**Q22.6: Design a reusable, accessible `<Modal>`/`<Dialog>` component.** Headless core (focus trap, Escape, scroll lock, `role="dialog"`) separated from styling; render via portal; return focus on close; support nested modal stacking.

**Q22.7: Design the state management for a shopping cart shared across pages.** Dedicated store (Zustand/RTK) persisted to `localStorage`; optimistic add/remove synced to server; derived totals via memoized selectors; merge guest cart on login.

**Q22.8: Design a notification/toast system usable from anywhere, including outside components.** A `<ToastProvider>` rendering via portal; imperative API backed by a module-level emitter/store so non-component code (e.g., an API error handler) can trigger toasts; `aria-live` for a11y.

**Q22.9: Design a large, filterable/sortable data table (thousands of rows).** Virtualize rows (`react-window`/`@tanstack/react-virtual`); server-side or memoized client-side filtering/sorting to avoid recomputation on every render; column virtualization if very wide; debounce filter input.

**Q22.10: Design an app-wide undo/redo system for a drawing or document editor.** Maintain a history stack of immutable state snapshots (or inverse operations/commands); push a new entry on each committed change; undo/redo moves a pointer through the stack rather than mutating in place, keeping the UI in sync via a single source-of-truth state.

**Q22.11: Design a permission-aware UI that shows/hides features based on the logged-in user's role.** Fetch/derive a permissions object once (e.g., on login, cached), expose it via Context or a Hook (`useHasPermission('edit:posts')`), and gate both UI rendering and route access consistently from that single source — never trust client-side gating alone for actual security (the server must also enforce it).

**Q22.12: Design a file upload component with progress, retry, and cancel support.** Use `XMLHttpRequest` or `fetch` with a readable stream (for progress events, since plain `fetch` lacks upload progress natively), track per-file state (pending/uploading/done/error) in state, expose a cancel via `AbortController`, and support retry by re-triggering the same upload function for a failed file.

**Q22.13: Design a React app's error-reporting pipeline (client errors reaching an engineering dashboard).** Global Error Boundaries reporting to a monitoring SDK (e.g., Sentry) in `componentDidCatch`, a global `window.onerror`/`unhandledrejection` listener for errors outside React's tree, source maps uploaded for readable stack traces, and user/session context attached to each report for reproduction.

**Q22.14: Design a component that renders differently based on viewport size (responsive layout) without layout thrashing.** Prefer CSS media queries/container queries for purely visual changes (no JS needed, no re-render). Only use a `useMediaQuery`/`ResizeObserver`-based Hook when the *structure* of what renders must actually change (not just styling), and debounce/throttle resize-driven state updates.

### Scenario-Based Debugging

**Q22.15: A list re-renders every item on every keystroke in an unrelated search box. How do you fix it?** Check if the search state lives in a common ancestor causing the whole subtree to re-render; move it down/colocate; memo list items; debounce the value used for filtering.

**Q22.16: Users see stale data after a mutation. How do you debug?** Check query invalidation after the mutation; check for multiple differently-keyed queries reading the same data; check `staleTime`; consider optimistic updates.

**Q22.17: A React app's bundle size is unexpectedly large. How do you investigate?** Bundle analyzer; check for importing whole libraries instead of specific functions; check duplicate dependency versions; identify code-splittable components; check for server-only code leaking into the client bundle.

**Q22.18: The app passes Lighthouse locally but feels slow for real mobile users. What do you check?** Throttle CPU/network to simulate real devices; check third-party scripts blocking the main thread; profile actual interaction responsiveness, not just load metrics; check hydration cost.

**Q22.19: A Server Component page in Next.js is suddenly much slower after a change. How do you debug?** Check for an accidental request waterfall between components; verify fetch caching wasn't disabled; check if a new Client Component boundary pulled server-only code into the client bundle; profile with Next.js tracing/network waterfall.

**Q22.20: A form that worked fine suddenly loses user input on every keystroke after a refactor. What's the likely cause?** The input component is likely being recreated (remounted) each render rather than updated — commonly caused by defining the component function *inside* the parent's render body (a new component type every render, so React treats it as a brand-new element and discards the previous instance's state/focus).

---

## Quick Reference — Most Frequently Asked Topics

| Topic | Frequency in Interviews |
| --- | --- |
| Virtual DOM + reconciliation + `key` | 🔴 Always asked |
| Hooks rules + `useState`/`useEffect` internals | 🔴 Always asked |
| Controlled vs uncontrolled components | 🔴 Always asked |
| `useMemo` vs `useCallback` vs `React.memo` | 🔴 Always asked |
| Context API pitfalls + state management choice | 🔴 Always asked |
| `useEffect` dependency array + cleanup + stale closures | 🔴 Always asked |
| Error Boundaries — what they catch and don't | 🔠 Frequently asked |
| Performance: memoization, virtualization, code splitting | 🔠 Frequently asked |
| React Router nested routes + protected routes | 🔠 Frequently asked |
| Testing with React Testing Library philosophy | 🔠 Frequently asked |
| SSR vs SSG vs ISR vs RSC | 🟡 Senior rounds |
| Concurrent rendering, `useTransition`, `Suspense` for data | 🟡 Senior rounds |
| Designing component libraries / headless patterns | 🟡 Senior rounds |
| State architecture at scale (Redux/Zustand trade-offs) | 🟡 Senior rounds |
