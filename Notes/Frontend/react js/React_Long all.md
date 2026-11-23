# React Interview — Complete Master Guide

**830 questions · 19 topical sections · updated November 2026**

Use the Core guide for daily practice. Read each question, answer aloud in about 30–60 seconds, then compare with the concise answer. The Master guide includes advanced and legacy topics. Code examples are illustrations, not scripts to memorize; type them out and explain the trade-offs.

Version notes cross-checked against React documentation and React Router documentation in November 2026; implementation details are version-specific.

## Answering in a technical interview

1. **Answer directly** with a definition or decision.
2. **Explain why** or how it works.
3. **Give an example or trade-off** when asked for depth.

<a id="contents"></a>
## Complete linked table of contents

- **[1. Fundamentals, JSX & Virtual DOM](#section-01)** (57)
  - [1.1. Can React be used without JSX? How?](#qa-01-001)
  - [1.2. How would you add a page title and meta tags in a React application?](#qa-01-002)
  - [1.3. Does the cost of inline arrow functions in JSX always matter?](#qa-01-003)
  - [1.4. How does React keep DOM updates efficient?](#qa-01-004)
  - [1.5. How can we find the version of React at runtime in the browser?](#qa-01-005)
  - [1.6. How do you write comments in JSX?](#qa-01-006)
  - [1.7. How do style objects work in JSX (`style={{...}}`)?](#qa-01-007)
  - [1.8. How do you print falsy values in JSX?](#qa-01-008)
  - [1.9. How would you loop inside JSX?](#qa-01-009)
  - [1.10. What is the Virtual DOM, and how does React update the UI?](#qa-01-010)
  - [1.11. How is event handling in React different from plain HTML?](#qa-01-011)
  - [1.12. How does JSX help prevent injection attacks?](#qa-01-012)
  - [1.13. How do you pass an event handler or arguments to a JSX event?](#qa-01-013)
  - [1.14. How do you associate a label with an input in JSX?](#qa-01-014)
  - [1.15. What is React, and why would you use it?](#qa-01-015)
  - [1.16. Why do React component names begin with a capital letter?](#qa-01-016)
  - [1.17. What are the rules of JSX?](#qa-01-017)
  - [1.18. What is JSX, and how does it become browser-readable JavaScript?](#qa-01-018)
  - [1.19. What is React Dev Tools?](#qa-01-019)
  - [1.20. What is React Intl?](#qa-01-020)
  - [1.21. What is React proptype array with shape?](#qa-01-021)
  - [1.22. What is React scripts?](#qa-01-022)
  - [1.23. How are the render phase and commit phase different in React?](#qa-01-023)
  - [1.24. How is the Virtual DOM different from the real DOM?](#qa-01-024)
  - [1.25. How are error boundaries different from JavaScript try/catch?](#qa-01-025)
  - [1.26. How should React components be named for readability and debugging?](#qa-01-026)
  - [1.27. Can you import an SVG file and use it as a React component?](#qa-01-027)
  - [1.28. Can I use web components in React application?](#qa-01-028)
  - [1.29. Can you list down top websites or applications using React as front end framework?](#qa-01-029)
  - [1.30. What happens during the initial render of a React component?](#qa-01-030)
  - [1.31. Can a React component render nothing? How would you do that?](#qa-01-031)
  - [1.32. Render order of nested Parent → Child → GrandChild components?](#qa-01-032)
  - [1.33. Why does a React component need to return one root element?](#qa-01-033)
  - [1.34. What are inline conditional expressions?](#qa-01-034)
  - [1.35. What is the difference between declarative and imperative programming in React?](#qa-01-035)
  - [1.36. What is `createRoot()` and why replace `ReactDOM.render()`?](#qa-01-036)
  - [1.37. What is `React.createElement()`? What does it return?](#qa-01-037)
  - [1.38. What is a switching component, and when would you use one?](#qa-01-038)
  - [1.39. What does React.lazy do, and when would you use it?](#qa-01-039)
  - [1.40. Why React uses `className` over `class` attribute?](#qa-01-040)
  - [1.41. Why is `React-dom` a separate package from `React`?](#qa-01-041)
  - [1.42. What would be the common mistake of function being called every time the component renders?](#qa-01-042)
  - [1.43. Does React support all HTML attributes?](#qa-01-043)
  - [1.44. How do you update a previously rendered React element?](#qa-01-044)
  - [1.45. What types of values can a React component return?](#qa-01-045)
  - [1.46. Should I learn ES6 before learning React?](#qa-01-046)
  - [1.47. What are synthetic events in React?](#qa-01-047)
  - [1.48. What are the limitations of React?](#qa-01-048)
  - [1.49. What are the Pointer Events supported in React?](#qa-01-049)
  - [1.50. How can you format strings, numbers, and dates in a React app?](#qa-01-050)
  - [1.51. Does modern React support Internet Explorer?](#qa-01-051)
  - [1.52. What are the main differences between React and Angular?](#qa-01-052)
  - [1.53. What is the history behind React evolution?](#qa-01-053)
  - [1.54. What is the purpose of displayName class property?](#qa-01-054)
  - [1.55. Why does `0 && <Component/>` render "0" instead of nothing?](#qa-01-055)
  - [1.56. How does the newer JSX transform differ from the older transform?](#qa-01-056)
  - [1.57. What are decorators in React, and when might you encounter them?](#qa-01-057)
- **[2. Components, Props & State](#section-02)** (120)
  - [2.1. What is lifting state up?](#qa-02-001)
  - [2.2. What is prop drilling and why is it a problem?](#qa-02-002)
  - [2.3. What is React.Fragment and why is it useful?](#qa-02-003)
  - [2.4. What is state in React?](#qa-02-004)
  - [2.5. What is state mutation and how to prevent it?](#qa-02-005)
  - [2.6. What is the difference between props and state in React?](#qa-02-006)
  - [2.7. What are React Portals, and when would you use them?](#qa-02-007)
  - [2.8. What is the difference between controlled and uncontrolled components?](#qa-02-008)
  - [2.9. Can you explain event bubbling through a React portal rendered outside the DOM parent?](#qa-02-009)
  - [2.10. How do you pass dynamic values to JSX attributes?](#qa-02-010)
  - [2.11. Do React state updates merge objects automatically?](#qa-02-011)
  - [2.12. How do you set default value for uncontrolled component?](#qa-02-012)
  - [2.13. How does Immer help with immutable state updates?](#qa-02-013)
  - [2.14. How does React batch multiple state updates?](#qa-02-014)
  - [2.15. How do React components communicate with each other?](#qa-02-015)
  - [2.16. How do you read updated state immediately after dispatching an action?](#qa-02-016)
  - [2.17. If we have var, let, and const, why do we need state variables?](#qa-02-017)
  - [2.18. How do class components consume Context with contextType?](#qa-02-018)
  - [2.19. What happens if you forget the key prop when rendering a list?](#qa-02-019)
  - [2.20. Render props pattern — headless component sharing fetch logic?](#qa-02-020)
  - [2.21. When and why should you split React Context providers?](#qa-02-021)
  - [2.22. What are Keyed Fragments?](#qa-02-022)
  - [2.23. What are props?](#qa-02-023)
  - [2.24. What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)?](#qa-02-024)
  - [2.25. What does React do differently when a `key` changes vs stays the same?](#qa-02-025)
  - [2.26. What is a reducer? Why must reducers be pure functions?](#qa-02-026)
  - [2.27. What is JSX spread attributes (`{...props}`)? What's the risk?](#qa-02-027)
  - [2.28. What is the controlled component pattern for reusable components?](#qa-02-028)
  - [2.29. What is the Controlled/Uncontrolled hybrid pattern?](#qa-02-029)
  - [2.30. What is the difference between a "key prop" warning and a "missing dependency" warning?](#qa-02-030)
  - [2.31. What is the difference between a transition and a regular (synchronous) state update in terms of interruptibility?](#qa-02-031)
  - [2.32. What is the Observer/Pub-Sub pattern's use in React outside of Context (e.g., a lightweight event bus for cross-cutting concerns)?](#qa-02-032)
  - [2.33. What is the purpose of default value in context?](#qa-02-033)
  - [2.34. What happens if you write a boolean prop without a value in JSX?](#qa-02-034)
  - [2.35. When should you NOT use Context for state?](#qa-02-035)
  - [2.36. Why is state update asynchronous?](#qa-02-036)
  - [2.37. When should you split a React component into smaller components?](#qa-02-037)
  - [2.38. Why are inline ref callbacks or functions not recommended?](#qa-02-038)
  - [2.39. What is a wrapper component?](#qa-02-039)
  - [2.40. What is the children prop in React, and why is it useful?](#qa-02-040)
  - [2.41. What is forwardRef, and when do you need it?](#qa-02-041)
  - [2.42. What is the difference between an Element and a Component?](#qa-02-042)
  - [2.43. What goes wrong when you use an array index as a key and reorder the list?](#qa-02-043)
  - [2.44. What is the `key` prop and why is it important?](#qa-02-044)
  - [2.45. What will happen if you use props in initial state?](#qa-02-045)
  - [2.46. Should you dispatch another action inside a reducer?](#qa-02-046)
  - [2.47. What can cause a React component to re-render unexpectedly?](#qa-02-047)
  - [2.48. Can you explain difference between `key`-based remounting and conditional rendering?](#qa-02-048)
  - [2.49. Can you explain conditional rendering in React?](#qa-02-049)
  - [2.50. What is a function component in React?](#qa-02-050)
  - [2.51. Given users = \\[{id:1, active:true}, {id:2, active:false}\\], find all active user IDs?](#qa-02-051)
  - [2.52. How do you pass data child → parent?](#qa-02-052)
  - [2.53. How do you prevent prop explosion in complex components?](#qa-02-053)
  - [2.54. How do you update arrays inside state?](#qa-02-054)
  - [2.55. How do you update nested objects inside state?](#qa-02-055)
  - [2.56. How would you create React class components without ES6?](#qa-02-056)
  - [2.57. How would you use and update the state object?](#qa-02-057)
  - [2.58. Is it ref argument available for all functions or class components?](#qa-02-058)
  - [2.59. Must prop be named as render for render props?](#qa-02-059)
  - [2.60. What is a reducer, and how does it manage state?](#qa-02-060)
  - [2.61. How would you manage the visibility of a modal or sidebar shared between components?](#qa-02-061)
  - [2.62. Do React list keys need to be unique across the entire application?](#qa-02-062)
  - [2.63. What causes re-renders in React, and how can you reduce unnecessary ones?](#qa-02-063)
  - [2.64. Where is state stored in a React application?](#qa-02-064)
  - [2.65. What are default props and PropTypes?](#qa-02-065)
  - [2.66. What are React elements vs React components?](#qa-02-066)
  - [2.67. What are stateful components?](#qa-02-067)
  - [2.68. What are presentational vs container components?](#qa-02-068)
  - [2.69. What are render props?](#qa-02-069)
  - [2.70. What are the guidelines to be followed for writing reducers?](#qa-02-070)
  - [2.71. What are the problems of using render props with pure components?](#qa-02-071)
  - [2.72. What happens if a component wrapped in `memo()` has its own state changes?](#qa-02-072)
  - [2.73. Why should we not update the state directly?](#qa-02-073)
  - [2.74. What is `createSlice()` and what does it contain? (name, initialState, reducers)?](#qa-02-074)
  - [2.75. What is an updater function? Should an updater function be used in all cases?](#qa-02-075)
  - [2.76. What is colocation in React?](#qa-02-076)
  - [2.77. What is composition vs inheritance in React?](#qa-02-077)
  - [2.78. What is flux?](#qa-02-078)
  - [2.79. What is Hot Module Replacement (HMR)? Why does it matter for React development?](#qa-02-079)
  - [2.80. What is prop inversion of control?](#qa-02-080)
  - [2.81. What is prop type narrowing with discriminated unions (conceptually, even pre-TS)?](#qa-02-081)
  - [2.82. What is server state vs client state?](#qa-02-082)
  - [2.83. What is a consumer?](#qa-02-083)
  - [2.84. What is test isolation, and why does it matter for React component tests?](#qa-02-084)
  - [2.85. What is the "render in a loop with composition" pattern vs a monolithic configurable component?](#qa-02-085)
  - [2.86. What are the advantages and trade-offs of a React SPA?](#qa-02-086)
  - [2.87. What is the difference between `interface` and `type` for defining props? When does it matter?](#qa-02-087)
  - [2.88. What is the difference between `setState()` and `replaceState()` methods?](#qa-02-088)
  - [2.89. What is the difference between normalized and nested state shape in a global store?](#qa-02-089)
  - [2.90. What are headless components?](#qa-02-090)
  - [2.91. What is the provider pattern?](#qa-02-091)
  - [2.92. What is the purpose of callback function as an argument of `setState()`?](#qa-02-092)
  - [2.93. What is the recommended approach of removing an array element in React state?](#qa-02-093)
  - [2.94. What is the render props pattern?](#qa-02-094)
  - [2.95. What is the risk of trusting `window.postMessage` data without validation in a React component?](#qa-02-095)
  - [2.96. What is the Slot pattern?](#qa-02-096)
  - [2.97. What is the state reducer pattern?](#qa-02-097)
  - [2.98. When did you get stuck while using React, and how did you fix it?](#qa-02-098)
  - [2.99. Why can't you update props in React?](#qa-02-099)
  - [2.100. Why do you not required to use inheritance?](#qa-02-100)
  - [2.101. Why we need to be careful when spreading props on DOM elements?](#qa-02-101)
  - [2.102. When do you need to use refs?](#qa-02-102)
  - [2.103. Why do you need additional care for component libraries while using forward refs?](#qa-02-103)
  - [2.104. Why is `isMounted()` an anti-pattern and what is the proper solution?](#qa-02-104)
  - [2.105. Why is calling `setState` inside `render` dangerous?](#qa-02-105)
  - [2.106. What is the difference between `super()` and `super(props)` in React using ES6 classes?](#qa-02-106)
  - [2.107. Which method must a class component implement?](#qa-02-107)
  - [2.108. What is a class component in React?](#qa-02-108)
  - [2.109. Can you explain data flow in React?](#qa-02-109)
  - [2.110. Does the statics object work with ES6 classes in React?](#qa-02-110)
  - [2.111. Is it mandatory to define constructor for React component?](#qa-02-111)
  - [2.112. How can a class component subscribe to one Context using contextType?](#qa-02-112)
  - [2.113. How was state initialized in older React.createClass components compared with ES6 classes?](#qa-02-113)
  - [2.114. What is the difference between Flow and PropTypes?](#qa-02-114)
  - [2.115. What is the constructor used for in a React class component?](#qa-02-115)
  - [2.116. What did unmountComponentAtNode do in older React versions?](#qa-02-116)
  - [2.117. Why do class components sometimes call super(props) in the constructor?](#qa-02-117)
  - [2.118. What is unidirectional data flow in React?](#qa-02-118)
  - [2.119. What will happen if you use `setState()` in constructor?](#qa-02-119)
  - [2.120. Why are String Refs legacy?](#qa-02-120)
- **[3. Rendering, Reconciliation & Lifecycle](#section-03)** (35)
  - [3.1. What happens in React’s commit phase?](#qa-03-001)
  - [3.2. What is React Fiber, and why was it introduced?](#qa-03-002)
  - [3.3. What is reconciliation, and how does React’s diffing algorithm work?](#qa-03-003)
  - [3.4. How does React work behind the scenes (render → reconciliation → commit)?](#qa-03-004)
  - [3.5. How is JavaScript strict mode different from React Strict Mode?](#qa-03-005)
  - [3.6. How does the React Fiber architecture change how rendering fundamentally works?](#qa-03-006)
  - [3.7. In what order do class mounting, state updates, and componentDidUpdate run?](#qa-03-007)
  - [3.8. What happens before React commits DOM updates?](#qa-03-008)
  - [3.9. What are Strict Mode's dev-only behaviors?](#qa-03-009)
  - [3.10. What is `getDerivedStateFromProps` and when would you use it?](#qa-03-010)
  - [3.11. What is `PureComponent` vs `Component` in class components?](#qa-03-011)
  - [3.12. Can you explain different trees are produced because of different elements?](#qa-03-012)
  - [3.13. What is the commit phase's "passive effects" vs "layout effects" ordering?](#qa-03-013)
  - [3.14. What is the methods order when component re-rendered?](#qa-03-014)
  - [3.15. Can you explain elements of the same type are compared attribute-wise?](#qa-03-015)
  - [3.16. Can you explain Strict Mode in React?](#qa-03-016)
  - [3.17. What is the structure of a React Fiber tree?](#qa-03-017)
  - [3.18. Is it possible to access a ref in the render method?](#qa-03-018)
  - [3.19. What are the different phases of component lifecycle?](#qa-03-019)
  - [3.20. What is `getSnapshotBeforeUpdate`?](#qa-03-020)
  - [3.21. What is `shouldComponentUpdate` and its functional equivalent?](#qa-03-021)
  - [3.22. What is event delegation in React?](#qa-03-022)
  - [3.23. What is the lifecycle methods order in mounting?](#qa-03-023)
  - [3.24. What is double buffering in React Fiber?](#qa-03-024)
  - [3.25. What is the recommended ordering of methods in component class?](#qa-03-025)
  - [3.26. Why do two sibling components with the same `key` cause a warning or misbehavior?](#qa-03-026)
  - [3.27. Why do you not need error boundaries for event handlers?](#qa-03-027)
  - [3.28. Why should not call setState in componentWillUnmount?](#qa-03-028)
  - [3.29. What are the three main steps React follows to update the screen?](#qa-03-029)
  - [3.30. How does React work behind the scenes?](#qa-03-030)
  - [3.31. What is the difference between mounting and updating in terms of effect behavior?](#qa-03-031)
  - [3.32. Should you use componentWillMount in a modern React application?](#qa-03-032)
  - [3.33. What are the lifecycle methods going to be deprecated in React v16?](#qa-03-033)
  - [3.34. Which is preferred option with in callback refs and findDOMNode()?](#qa-03-034)
  - [3.35. Why is a component constructor called only once?](#qa-03-035)
- **[4. Hooks (Core & Advanced)](#section-04)** (177)
  - [4.1. Can you explain `useMemo` vs `React.memo` — how are they different?](#qa-04-001)
  - [4.2. How does useRef differ from useState?](#qa-04-002)
  - [4.3. How is useTransition different from Suspense?](#qa-04-003)
  - [4.4. How can you avoid unstable dependencies in useEffect?](#qa-04-004)
  - [4.5. How does useEffect behave with a dependency array?](#qa-04-005)
  - [4.6. Can you combine **useReducer** with **useContext**?](#qa-04-006)
  - [4.7. Can you have multiple useEffect hooks in a single component?](#qa-04-007)
  - [4.8. How are useEffect, useLayoutEffect, and useInsertionEffect different?](#qa-04-008)
  - [4.9. Can you explain useEffect, including its cleanup and dependency array?](#qa-04-009)
  - [4.10. When does the cleanup function returned by useEffect run?](#qa-04-010)
  - [4.11. How can Context and custom Hooks work together for feature flags?](#qa-04-011)
  - [4.12. How would you manage event listeners with useEffect?](#qa-04-012)
  - [4.13. Can you explain fix a `useEffect` that has missing dependencies (the ESLint exhaustive-deps warning)?](#qa-04-013)
  - [4.14. How do reactive dependencies in the useEffect dependency array affect its execution behavior?](#qa-04-014)
  - [4.15. How do you fetch data with `useEffect`? What are the pitfalls?](#qa-04-015)
  - [4.16. How does `useOptimistic` (React 19) differ from manually managing optimistic state with `useState`?](#qa-04-016)
  - [4.17. How does `useRef` differ from a regular variable?](#qa-04-017)
  - [4.18. How does useLayoutEffect work during server-side rendering (SSR)?](#qa-04-018)
  - [4.19. When would you use useReducer instead of useState?](#qa-04-019)
  - [4.20. What can cause an infinite loop in useEffect?](#qa-04-020)
  - [4.21. Does useImperativeHandle require forwardRef in React 19?](#qa-04-021)
  - [4.22. In what order do multiple useEffect Hooks execute?](#qa-04-022)
  - [4.23. What happens when you omit the useEffect dependency array?](#qa-04-023)
  - [4.24. How do you manage useEffect dependencies correctly?](#qa-04-024)
  - [4.25. Can you explain react.useMemo() memoizing a JSX element to skip a child's re-render?](#qa-04-025)
  - [4.26. When does the setup function inside useEffect run?](#qa-04-026)
  - [4.27. What is a stale closure in useEffect, and how do you fix it?](#qa-04-027)
  - [4.28. How do you handle subscriptions safely in useEffect?](#qa-04-028)
  - [4.29. When does useEffect cleanup run before the next effect?](#qa-04-029)
  - [4.30. Can you explain useEffect mount/unmount order when toggling between two sibling components?](#qa-04-030)
  - [4.31. When do useEffect and useLayoutEffect run relative to browser paint?](#qa-04-031)
  - [4.32. Why should you not make the useEffect callback itself async?](#qa-04-032)
  - [4.33. What happens when useEffect has an empty dependency array?](#qa-04-033)
  - [4.34. Can you explain useMemo recomputing when a dependency array value is a new array reference each render?](#qa-04-034)
  - [4.35. Can you explain useTransition marking a state update as non-urgent?](#qa-04-035)
  - [4.36. What are common `useEffect` mistakes?](#qa-04-036)
  - [4.37. What are the differences between `useEffect` and the experimental `useEvent`/Effect Event pattern?](#qa-04-037)
  - [4.38. How do Effect Events compare with ordinary useEffect callbacks?](#qa-04-038)
  - [4.39. What are the use cases of useContext hook?](#qa-04-039)
  - [4.40. What is the use of useEffect React Hooks?](#qa-04-040)
  - [4.41. What happens if you return a Promise from useEffect?](#qa-04-041)
  - [4.42. What is useContext? What are the steps to follow for useContext?](#qa-04-042)
  - [4.43. What is `useLayoutEffect` and how does it differ from `useEffect`?](#qa-04-043)
  - [4.44. What is `useReducer` vs `useState`?](#qa-04-044)
  - [4.45. What is an infinite `useEffect` loop and how does it happen?](#qa-04-045)
  - [4.46. What is Formik / React Hook Form used for?](#qa-04-046)
  - [4.47. What is React Hook Form and why is it popular?](#qa-04-047)
  - [4.48. What is React Query (TanStack Query) / SWR, and why use them over manual `useEffect` fetching?](#qa-04-048)
  - [4.49. What is React.memo? How is it different from useMemo and useCallback?](#qa-04-049)
  - [4.50. What is React’s use() API and how does it differ from regular Hooks?](#qa-04-050)
  - [4.51. What is the `useEffect` cleanup function?](#qa-04-051)
  - [4.52. What is the difference between useMemo and useCallback?](#qa-04-052)
  - [4.53. What is the difference between useState and useRef hook?](#qa-04-053)
  - [4.54. What problems does React Query solve vs raw `useEffect` fetching?](#qa-04-054)
  - [4.55. How does React Context help you avoid prop drilling?](#qa-04-055)
  - [4.56. What's a common pitfall when using useContext with objects?](#qa-04-056)
  - [4.57. When does a child's useEffect cleanup run vs the parent's cleanup?](#qa-04-057)
  - [4.58. When is `useMemo`/`useCallback` actually worth it? Cost of overusing?](#qa-04-058)
  - [4.59. When should you use Redux/Zustand instead of Context + `useState`?](#qa-04-059)
  - [4.60. Why is storing derived values in `useState` (and syncing via `useEffect`) usually an anti-pattern?](#qa-04-060)
  - [4.61. How do you cancel a fetch request when a React component unmounts?](#qa-04-061)
  - [4.62. What are Actions and form Actions in modern React?](#qa-04-062)
  - [4.63. Can you explain calling a hook conditionally inside an if block?](#qa-04-063)
  - [4.64. Can Hooks be used in class components?](#qa-04-064)
  - [4.65. Can React Hooks replace Redux?](#qa-04-065)
  - [4.66. Can useRef be used to store previous values?](#qa-04-066)
  - [4.67. Can useState take a function as an initial value?](#qa-04-067)
  - [4.68. Can you describe the useMemo() Hook?](#qa-04-068)
  - [4.69. Can you dispatch multiple actions in a row with useReducer?](#qa-04-069)
  - [4.70. Can you explain how useState works internally?](#qa-04-070)
  - [4.71. When would you use a custom Hook instead of a higher-order component or render prop?](#qa-04-071)
  - [4.72. How do you clean up side effects in a React component?](#qa-04-072)
  - [4.73. How do React Hooks differ from class components?](#qa-04-073)
  - [4.74. Do Hooks cover all the functionalities provided by the classes?](#qa-04-074)
  - [4.75. Do Hooks replace render props and higher order components?](#qa-04-075)
  - [4.76. Does React Hook work with static typing?](#qa-04-076)
  - [4.77. What types of Hooks are available in React?](#qa-04-077)
  - [4.78. How would you build a simple component using React Hooks?](#qa-04-078)
  - [4.79. Can you explain React Hooks and why they were introduced?](#qa-04-079)
  - [4.80. What are Custom Hooks?](#qa-04-080)
  - [4.81. How do you share state logic between components using custom hooks?](#qa-04-081)
  - [4.82. Can You Use Multiple Contexts in One Component?](#qa-04-082)
  - [4.83. Can you use useRef to persist values across renders?](#qa-04-083)
  - [4.84. How can you combine React Hooks to share stateful logic?](#qa-04-084)
  - [4.85. Can you explain defining a child component inside a parent's render function?](#qa-04-085)
  - [4.86. Do I need to rewrite all my class components with hooks?](#qa-04-086)
  - [4.87. Does useMemo prevent re-rendering of child components?](#qa-04-087)
  - [4.88. Types of side effects in React component?](#qa-04-088)
  - [4.89. Can you explain how to create a simple React Hooks example program?](#qa-04-089)
  - [4.90. What are the Rules of Hooks, and why must you follow them?](#qa-04-090)
  - [4.91. Can you explain force-updating a component after mutating a ref directly?](#qa-04-091)
  - [4.92. Can you explain functional update vs direct update?](#qa-04-092)
  - [4.93. How does React track Hooks internally?](#qa-04-093)
  - [4.94. How do Hooks help manage component state?](#qa-04-094)
  - [4.95. How do you avoid unnecessary object/function recreation?](#qa-04-095)
  - [4.96. How do you avoid unnecessary re-renders caused by Context?](#qa-04-096)
  - [4.97. How do you create and consume Context?](#qa-04-097)
  - [4.98. How do you integrate a non-React library (e.g., D3, Leaflet)?](#qa-04-098)
  - [4.99. How do you manage focus after navigation in a SPA?](#qa-04-099)
  - [4.100. How do you pass parent data to the 5th child component?](#qa-04-100)
  - [4.101. How do you prevent an expensive component from blocking user input (e.g., a large table filtering as you type)?](#qa-04-101)
  - [4.102. How do you share logic between a Hook and an effect cleanup safely (avoiding duplicated subscribe/unsubscribe code)?](#qa-04-102)
  - [4.103. How do you use useRef to focus an input in React?](#qa-04-103)
  - [4.104. How does useLayoutEffect cause layout thrashing?](#qa-04-104)
  - [4.105. How does `useReducer` works? Explain with an example?](#qa-04-105)
  - [4.106. How does the performance of using Hooks will differ in comparison with the classes?](#qa-04-106)
  - [4.107. How should you structure a large React application?](#qa-04-107)
  - [4.108. How can you avoid unnecessary re-renders in a React application?](#qa-04-108)
  - [4.109. How would you ensure hooks followed the rules in your project?](#qa-04-109)
  - [4.110. How would you optimize a slow React application?](#qa-04-110)
  - [4.111. Is dispatch from useReducer asynchronous and does it update state immediately?](#qa-04-111)
  - [4.112. Is Hooks cover all use cases for classes?](#qa-04-112)
  - [4.113. Does a React state setter update the state variable immediately?](#qa-04-113)
  - [4.114. What makes a custom Hook easy to maintain?](#qa-04-114)
  - [4.115. Map class lifecycle methods to hooks?](#qa-04-115)
  - [4.116. Why might you memoize a Context provider value?](#qa-04-116)
  - [4.117. What does React Compiler optimize automatically?](#qa-04-117)
  - [4.118. How do you safely manage timers and intervals in React?](#qa-04-118)
  - [4.119. What is the React use() API, and when is it useful?](#qa-04-119)
  - [4.120. Can you explain useCallback returning a stable function reference across re-renders?](#qa-04-120)
  - [4.121. What happens when a useCallback dependency stays unchanged?](#qa-04-121)
  - [4.122. Can you explain useDeferredValue keeping input responsive during an expensive re-render?](#qa-04-122)
  - [4.123. What is referential equality, and why does it matter so much in React?](#qa-04-123)
  - [4.124. When does useMemo recalculate a value?](#qa-04-124)
  - [4.125. Can you explain useRef does not cause re-render?](#qa-04-125)
  - [4.126. How would you track the previous value of a prop or state with useRef?](#qa-04-126)
  - [4.127. Can you explain useTransition keeps UI responsive?](#qa-04-127)
  - [4.128. What are Custom React Hooks, and How Can You Develop One?](#qa-04-128)
  - [4.129. What are the best practices for using React Hooks?](#qa-04-129)
  - [4.130. What are Higher-Order Components (HOCs)?](#qa-04-130)
  - [4.131. What are stateless components?](#qa-04-131)
  - [4.132. What are the common usecases of useRef hook?](#qa-04-132)
  - [4.133. What are the rules needs to follow for hooks?](#qa-04-133)
  - [4.134. What are the rules that must be followed while using React Hooks?](#qa-04-134)
  - [4.135. What are the sources used for introducing hooks?](#qa-04-135)
  - [4.136. What are the usecases of useLayoutEffect?](#qa-04-136)
  - [4.137. What do useActionState and useFormStatus do for React forms?](#qa-04-137)
  - [4.138. What happens if you call `useState` conditionally?](#qa-04-138)
  - [4.139. What happens if you use useLayoutEffect for non-layout logic?](#qa-04-139)
  - [4.140. What is `useActionState` (React 19)?](#qa-04-140)
  - [4.141. What is `useCallback` and why is it used?](#qa-04-141)
  - [4.142. What does useDebugValue do?](#qa-04-142)
  - [4.143. How do useDeferredValue and useTransition differ?](#qa-04-143)
  - [4.144. What is `useId`? Why was it added?](#qa-04-144)
  - [4.145. When would you use useImperativeHandle in React?](#qa-04-145)
  - [4.146. What is `useReducer`? Why do you use useReducer?](#qa-04-146)
  - [4.147. What is `useRef`? What are its two main use cases?](#qa-04-147)
  - [4.148. What is useState() in React?](#qa-04-148)
  - [4.149. What is useSyncExternalStore, and when would you use it?](#qa-04-149)
  - [4.150. What is a "smart" vs "dumb" component?](#qa-04-150)
  - [4.151. What is a monorepo and how does it relate to React projects?](#qa-04-151)
  - [4.152. What is a render prop? How does it compare to Hooks?](#qa-04-152)
  - [4.153. What is focus management and why does it matter?](#qa-04-153)
  - [4.154. What is lazy initialization in `useState`?](#qa-04-154)
  - [4.155. What is the purpose of eslint plugin for hooks?](#qa-04-155)
  - [4.156. What is the `React-error-boundary` library?](#qa-04-156)
  - [4.157. What is the `useTransition` hook for performance?](#qa-04-157)
  - [4.158. What is the container/presenter pattern and is it still relevant?](#qa-04-158)
  - [4.159. What is the difference between `startTransition` and `useTransition`?](#qa-04-159)
  - [4.160. What is the difference between a development build and a production build of a React app?](#qa-04-160)
  - [4.161. What is the difference between optimistic and pessimistic updates?](#qa-04-161)
  - [4.162. What is the order of hook execution in a component?](#qa-04-162)
  - [4.163. What is the risk of using `key` to force-remount a component during a transition?](#qa-04-163)
  - [4.164. What is the stable release for hooks support?](#qa-04-164)
  - [4.165. What is the testing pyramid for a React app?](#qa-04-165)
  - [4.166. What is the use() hook in React 19?](#qa-04-166)
  - [4.167. What is the useId hook and when should you use it?](#qa-04-167)
  - [4.168. What is useInsertionEffect and who should use it?](#qa-04-168)
  - [4.169. What are the two important Rules of Hooks?](#qa-04-169)
  - [4.170. What types of values can `useState` hold?](#qa-04-170)
  - [4.171. When should you avoid using React’s useId?](#qa-04-171)
  - [4.172. When should you still apply manual performance optimizations in React?](#qa-04-172)
  - [4.173. Why do React Hooks make use of refs?](#qa-04-173)
  - [4.174. Why do we use array destructuring (square brackets notation) in `useState`?](#qa-04-174)
  - [4.175. Why React tab is not showing up in DevTools?](#qa-04-175)
  - [4.176. Why use functional updates with `useState`?](#qa-04-176)
  - [4.177. When to use a Class Component over a Function Component?](#qa-04-177)
- **[5. Performance Optimization](#section-05)** (69)
  - [5.1. Can you explain a React component re-renders again and again but you never called setState. Why?](#qa-05-001)
  - [5.2. When is component memoization worth using?](#qa-05-002)
  - [5.3. Can you explain techniques for dynamic code splitting and lazy loading in multi-route SPAs?](#qa-05-003)
  - [5.4. Given a slow React tree, how do you identify and fix the performance bottleneck?](#qa-05-004)
  - [5.5. How do you reduce the performance cost of a component that re-renders on every scroll event?](#qa-05-005)
  - [5.6. How does `React.memo` prevent re-renders? Limitations?](#qa-05-006)
  - [5.7. How does React Context work? When can it hurt performance?](#qa-05-007)
  - [5.8. How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)?](#qa-05-008)
  - [5.9. How does React apply queued state updates on the next render?](#qa-05-009)
  - [5.10. How does React.memo behave when a child receives an object prop?](#qa-05-010)
  - [5.11. What happens when you call a state updater function in React?](#qa-05-011)
  - [5.12. What are React Suspense and React.lazy? How do they enable code splitting?](#qa-05-012)
  - [5.13. When would you use `React.memo`?](#qa-05-013)
  - [5.14. What is `shouldComponentUpdate`? How does it relate to `React.memo`?](#qa-05-014)
  - [5.15. What is code splitting and how does React.lazy work internally?](#qa-05-015)
  - [5.16. What is code splitting? How with `React.lazy`/`Suspense`?](#qa-05-016)
  - [5.17. What is route based code splitting?](#qa-05-017)
  - [5.18. What is the main performance pitfall of Context?](#qa-05-018)
  - [5.19. What is the purpose of Suspense beyond lazy loading?](#qa-05-019)
  - [5.20. What is the React DevTools Profiler used for?](#qa-05-020)
  - [5.21. When does `React.memo` NOT help?](#qa-05-021)
  - [5.22. When is useCallback useful?](#qa-05-022)
  - [5.23. Why does React re-render the whole component function on every update rather than patching just changed JSX?](#qa-05-023)
  - [5.24. What is the difference between virtualization and windowing? Trade-offs?](#qa-05-024)
  - [5.25. What is the Profiler API?](#qa-05-025)
  - [5.26. What are loadable components?](#qa-05-026)
  - [5.27. Can you explain a user complains about slow UI after data load --- how would you optimize rendering and improve UX?](#qa-05-027)
  - [5.28. What are React’s resource preloading APIs used for?](#qa-05-028)
  - [5.29. Can a re-render happen without a commit?](#qa-05-029)
  - [5.30. Can you force a component to re-render without calling setState?](#qa-05-030)
  - [5.31. What is canary deployment, and why is it useful for React apps?](#qa-05-031)
  - [5.32. Can you explain context re-render behavior – what should you know?](#qa-05-032)
  - [5.33. Can you explain cSS Animation Jank: A CSS animation is janky on mobile – how to identify and fix?](#qa-05-033)
  - [5.34. What does React Compiler do at build time?](#qa-05-034)
  - [5.35. How would you deploy a React application to staging and validate it?](#qa-05-035)
  - [5.36. Does the lazy function support named exports?](#qa-05-036)
  - [5.37. Does a child always re-render when its parent re-renders?](#qa-05-037)
  - [5.38. Can you explain the concept of "controlled re‑render boundaries"?](#qa-05-038)
  - [5.39. Can you explain follow-up: What if we set the SAME value?](#qa-05-039)
  - [5.40. How would you prevent re-renders in React?](#qa-05-040)
  - [5.41. How would you re-render the view when the browser is resized?](#qa-05-041)
  - [5.42. How would you implement a robust frontend monitoring and logging system?](#qa-05-042)
  - [5.43. How would you improve Web Vitals (LCP, CLS, INP)?](#qa-05-043)
  - [5.44. How would you optimize a React list with 100,000 items?](#qa-05-044)
  - [5.45. Is it good to use arrow functions in render methods?](#qa-05-045)
  - [5.46. Name a few techniques to optimize React app performance?](#qa-05-046)
  - [5.47. How do you avoid a poor user experience while feature flags are loading?](#qa-05-047)
  - [5.48. What are common React performance optimization techniques? (practical guide)?](#qa-05-048)
  - [5.49. What are common React performance pitfalls?](#qa-05-049)
  - [5.50. What happens if a child uses React.memo() and parent props don't change?](#qa-05-050)
  - [5.51. What is a selector function? Why is memoizing selectors (e.g., with `reselect`) important?](#qa-05-051)
  - [5.52. What is the "render props waterfall" performance risk?](#qa-05-052)
  - [5.53. What will happen by defining nested function components?](#qa-05-053)
  - [5.54. Why are keys important in lists? What happens if keys are unstable?](#qa-05-054)
  - [5.55. Why function is preferred over object for `setState()`?](#qa-05-055)
  - [5.56. Why we need to pass a function to setState()?](#qa-05-056)
  - [5.57. How would you improve a React application with poor SEO and slow time to interactive (TTI)?](#qa-05-057)
  - [5.58. What is the 'why did you render' library?](#qa-05-058)
  - [5.59. How does the browser rendering pipeline work?](#qa-05-059)
  - [5.60. What is windowing technique?](#qa-05-060)
  - [5.61. What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)?](#qa-05-061)
  - [5.62. When would you still manually optimize components instead of relying on React Compiler?](#qa-05-062)
  - [5.63. How does React identify expensive calculations and renders?](#qa-05-063)
  - [5.64. How would you investigate a React performance bottleneck using DevTools?](#qa-05-064)
  - [5.65. What would you check first when improving an existing website’s performance?](#qa-05-065)
  - [5.66. What are Web Vitals and why do they matter?](#qa-05-066)
  - [5.67. How would you identify and fix a memory leak in a production React SPA?](#qa-05-067)
  - [5.68. What is `flushSync`? When would you need it?](#qa-05-068)
  - [5.69. What is image lazy-loading in React? How do you implement it?](#qa-05-069)
- **[6. Context API & State Management (Redux/Zustand/MobX)](#section-06)** (77)
  - [6.1. Why would you use Redux instead of local component state?](#qa-06-001)
  - [6.2. Compare Redux, MobX, Recoil/Jotai, Zustand, and Context for a large-scale app?](#qa-06-002)
  - [6.3. What is a container component in Redux?](#qa-06-003)
  - [6.4. Can you explain context vs Redux – when to choose which?](#qa-06-004)
  - [6.5. How do you handle async logic with Redux Toolkit?](#qa-06-005)
  - [6.6. How do you get redux scaffolding using create-React-app?](#qa-06-006)
  - [6.7. How do you manage global state? Compare Context, Redux, and modern alternatives?](#qa-06-007)
  - [6.8. How do you persist Redux/Zustand state across page reloads?](#qa-06-008)
  - [6.9. How do you test components connected to Redux/Zustand?](#qa-06-009)
  - [6.10. How does Redux Toolkit work internally?](#qa-06-010)
  - [6.11. How Redux Form `initialValues` get updated from state?](#qa-06-011)
  - [6.12. How Relay is different from Redux?](#qa-06-012)
  - [6.13. How do you configure a Redux Toolkit store?](#qa-06-013)
  - [6.14. How would you reset state in Redux?](#qa-06-014)
  - [6.15. How should you organize a Redux application?](#qa-06-015)
  - [6.16. How does connect() work in React Redux, and what is the modern alternative?](#qa-06-016)
  - [6.17. How do you define a Redux Toolkit slice?](#qa-06-017)
  - [6.18. Why is immutability important in Redux state updates?](#qa-06-018)
  - [6.19. How do you dispatch an action created by Redux Toolkit?](#qa-06-019)
  - [6.20. How is Redux different from the React Context API?](#qa-06-020)
  - [6.21. Should I keep all component's state in Redux store?](#qa-06-021)
  - [6.22. What are Redux selectors and why use them?](#qa-06-022)
  - [6.23. What are the advantages of formik over redux form library?](#qa-06-023)
  - [6.24. What are the three main principles of Redux?](#qa-06-024)
  - [6.25. What are the differences between `call()` and `put()` in redux-saga?](#qa-06-025)
  - [6.26. How are Redux and MobX different as state-management approaches?](#qa-06-026)
  - [6.27. What is middleware in Redux? Example?](#qa-06-027)
  - [6.28. What is Redux and why is it used?](#qa-06-028)
  - [6.29. What is Redux Toolkit, and why is it recommended?](#qa-06-029)
  - [6.30. What is the Context API? When should you use it instead of prop drilling?](#qa-06-030)
  - [6.31. What is the difference between Context API and Redux Toolkit?](#qa-06-031)
  - [6.32. What is Zustand and how does it differ from Redux?](#qa-06-032)
  - [6.33. When should you use Context vs. Redux/Zustand?](#qa-06-033)
  - [6.34. Where and why have you used Redux Toolkit in your projects?](#qa-06-034)
  - [6.35. Can Redux only be used with React?](#qa-06-035)
  - [6.36. Can you explain careful selection of complementary packages?](#qa-06-036)
  - [6.37. What is a presentational component in Redux?](#qa-06-037)
  - [6.38. Do I need to keep all my state into Redux? Should I ever use React internal state?](#qa-06-038)
  - [6.39. Do you need to have a particular build tool to use Redux?](#qa-06-039)
  - [6.40. How would you access Redux store outside a component?](#qa-06-040)
  - [6.41. What are the trade-offs of static typing in Flux-style and Redux applications?](#qa-06-041)
  - [6.42. Give an example of Reselect usage?](#qa-06-042)
  - [6.43. Explain reducers and extraReducers – when to use each?](#qa-06-043)
  - [6.44. What are the downsides of Redux compared to Flux?](#qa-06-044)
  - [6.45. What are the features of Redux DevTools?](#qa-06-045)
  - [6.46. What are the main features of Redux Form?](#qa-06-046)
  - [6.47. How do you avoid unnecessary re-renders with `useSelector`?](#qa-06-047)
  - [6.48. What are the main features of Reselect library?](#qa-06-048)
  - [6.49. What are typical middleware choices for handling asynchronous calls in Redux?](#qa-06-049)
  - [6.50. What is an action in Redux?](#qa-06-050)
  - [6.51. What is createAsyncThunk() and why is it used?](#qa-06-051)
  - [6.52. What is Jotai and how does the atomic model work?](#qa-06-052)
  - [6.53. What is MobX?](#qa-06-053)
  - [6.54. What is Recoil/Jotai? What problem do atom-based libraries solve?](#qa-06-054)
  - [6.55. What is Redux Form?](#qa-06-055)
  - [6.56. What is Redux Thunk vs Redux Saga?](#qa-06-056)
  - [6.57. What is Redux Thunk?](#qa-06-057)
  - [6.58. What is redux-saga?](#qa-06-058)
  - [6.59. What is Redux?](#qa-06-059)
  - [6.60. What is the "single source of truth" principle in state management?](#qa-06-060)
  - [6.61. What is the `useSelector` / `useDispatch` pattern in Redux?](#qa-06-061)
  - [6.62. What is the difference between global state and server state (cache)?](#qa-06-062)
  - [6.63. What is the flux architecture pattern?](#qa-06-063)
  - [6.64. What is the mental model of redux-saga?](#qa-06-064)
  - [6.65. What is the proper way to access Redux store?](#qa-06-065)
  - [6.66. What is the purpose of the constants in Redux?](#qa-06-066)
  - [6.67. What is the use of the `ownProps` parameter in `mapStateToProps()` and `mapDispatchToProps()`?](#qa-06-067)
  - [6.68. What problems does Redux solve in large React applications?](#qa-06-068)
  - [6.69. Whats the purpose of `at` symbol in the Redux connect decorator?](#qa-06-069)
  - [6.70. How would you provide feature flags throughout a React application?](#qa-06-070)
  - [6.71. When would you decide NOT to use Redux and choose a simpler solution?](#qa-06-071)
  - [6.72. Why are Redux state functions called reducers?](#qa-06-072)
  - [6.73. What is reselect and how it works?](#qa-06-073)
  - [6.74. What is createSlice() and what does it contain?](#qa-06-074)
  - [6.75. What is the Provider hell problem, and how do you avoid it?](#qa-06-075)
  - [6.76. Can you explain the Redux Toolkit flow?](#qa-06-076)
  - [6.77. How does async flow work in Redux Toolkit?](#qa-06-077)
- **[7. Routing & Navigation](#section-07)** (32)
  - [7.1. What do useParams, useNavigate and useSearchParams do in React Router?](#qa-07-001)
  - [7.2. How do you prevent open redirect vulnerabilities in a React Router app (e.g., a `?redirect=` query param)?](#qa-07-002)
  - [7.3. How do you test a component with React Router routes?](#qa-07-003)
  - [7.4. How React Router is different from history library?](#qa-07-004)
  - [7.5. How can data be passed between routes in React Router?](#qa-07-005)
  - [7.6. What are nested routes in React Router v6?](#qa-07-006)
  - [7.7. What are route actions in React Router?](#qa-07-007)
  - [7.8. What are route loaders in React Router v6.4+?](#qa-07-008)
  - [7.9. What are the `<Router>` components of React Router v6?](#qa-07-009)
  - [7.10. What is client-side routing? How does it differ from server routing?](#qa-07-010)
  - [7.11. What is React Router and what are its main components?](#qa-07-011)
  - [7.12. What is route matching precedence in React Router v6?](#qa-07-012)
  - [7.13. What is the difference between `Router` and `Link` in React Router?](#qa-07-013)
  - [7.14. How do you define nested routes (v6+)?](#qa-07-014)
  - [7.15. How do you implement a layout route (shared header/sidebar across multiple pages)?](#qa-07-015)
  - [7.16. How do you implement protected/private routes?](#qa-07-016)
  - [7.17. What is the difference between BrowserRouter and HashRouter?](#qa-07-017)
  - [7.18. How do you redirect after a successful form submission/mutation?](#qa-07-018)
  - [7.19. How does client-side routing work?](#qa-07-019)
  - [7.20. How is React different from Angular or Vue?](#qa-07-020)
  - [7.21. What is the difference between `useNavigate` and `<Navigate>`?](#qa-07-021)
  - [7.22. How do you pass state through navigation without putting it in the URL?](#qa-07-022)
  - [7.23. How do you protect routes (auth guards)?](#qa-07-023)
  - [7.24. How do you prevent navigation away from a page with unsaved changes?](#qa-07-024)
  - [7.25. What are search params and how do you use them?](#qa-07-025)
  - [7.26. What are loaders and actions (v6.4+ data APIs)?](#qa-07-026)
  - [7.27. What is `<NavLink>`? How does it differ from `<Link>`?](#qa-07-027)
  - [7.28. What is the purpose of `push()` and `replace()` methods of `history`?](#qa-07-028)
  - [7.29. How do you programmatically navigate using React Router v4?](#qa-07-029)
  - [7.30. How would you get query parameters in React Router v4?](#qa-07-030)
  - [7.31. What are the benefits of React Router V4?](#qa-07-031)
  - [7.32. How did routing syntax change from React Router v5 to v6?](#qa-07-032)
- **[8. Forms & Controlled Components](#section-08)** (14)
  - [8.1. How do you do form validation in React without a library?](#qa-08-001)
  - [8.2. What is Formik?](#qa-08-002)
  - [8.3. What is the popular choice for form handling?](#qa-08-003)
  - [8.4. How do you build a controlled form in React?](#qa-08-004)
  - [8.5. How would you prevent a function from being called multiple times?](#qa-08-005)
  - [8.6. What is a factory/builder pattern for creating typed, reusable form field components?](#qa-08-006)
  - [8.7. What is the difference between `onChange` and `onInput` in React forms?](#qa-08-007)
  - [8.8. How do you handle a form submit without refreshing the page?](#qa-08-008)
  - [8.9. How do you prevent a user from submitting the same form twice?](#qa-08-009)
  - [8.10. How do you show validation errors accessibly?](#qa-08-010)
  - [8.11. How do you upload a file from a React form?](#qa-08-011)
  - [8.12. How do you handle checkbox and select values in a controlled form?](#qa-08-012)
  - [8.13. How would you handle dependent fields in a large form?](#qa-08-013)
  - [8.14. How do you decide between a form library and ordinary React state?](#qa-08-014)
- **[9. Data Fetching & React Query/Suspense](#section-09)** (22)
  - [9.1. How do you deduplicate identical simultaneous requests?](#qa-09-001)
  - [9.2. How does the data-fetching process work with Suspense?](#qa-09-002)
  - [9.3. How do staleTime and gcTime affect TanStack Query caching?](#qa-09-003)
  - [9.4. How do SWR and TanStack Query compare for data fetching?](#qa-09-004)
  - [9.5. What are the patterns for data fetching in React?](#qa-09-005)
  - [9.6. What is `Suspense`? How does it work for data fetching?](#qa-09-006)
  - [9.7. What is an optimistic update in TanStack Query, and how would you implement it?](#qa-09-007)
  - [9.8. What is parallel data fetching in Server Components, and why does it matter?](#qa-09-008)
  - [9.9. What is parallel vs sequential data fetching?](#qa-09-009)
  - [9.10. What is prefetching in React Query? When would you use it?](#qa-09-010)
  - [9.11. What is React Query (TanStack Query)?](#qa-09-011)
  - [9.12. What is React Query's caching model?](#qa-09-012)
  - [9.13. What is the difference between `isLoading` and `isFetching` in React Query?](#qa-09-013)
  - [9.14. What is the difference between a "query" and a "mutation" in React Query?](#qa-09-014)
  - [9.15. Why can Suspense boundaries be nested, and what determines which one catches a given suspension?](#qa-09-015)
  - [9.16. What is `useInfiniteQuery`? When is it used?](#qa-09-016)
  - [9.17. What is optimistic UI? How do you implement it?](#qa-09-017)
  - [9.18. What is query invalidation? How do you trigger a refetch after a mutation?](#qa-09-018)
  - [9.19. How do you cancel a query automatically when its component unmounts?](#qa-09-019)
  - [9.20. How does React prioritize work with its Scheduler?](#qa-09-020)
  - [9.21. What does it mean for a component to "suspend"? What triggers it?](#qa-09-021)
  - [9.22. What is SWR?](#qa-09-022)
- **[10. React 18/19, Concurrent Features](#section-10)** (22)
  - [10.1. How would you ensure a React app performs well at 100k concurrent users?](#qa-10-001)
  - [10.2. Is it possible to prevent automatic batching?](#qa-10-002)
  - [10.3. What are React 19 Actions?](#qa-10-003)
  - [10.4. What are Server Actions (React 19 / Next.js)?](#qa-10-004)
  - [10.5. What are the most important React 19 features?](#qa-10-005)
  - [10.6. What is Concurrent Rendering?](#qa-10-006)
  - [10.7. What is concurrent rendering? When does it help vs hurt?](#qa-10-007)
  - [10.8. What is streaming SSR and how does React 18+ improve it?](#qa-10-008)
  - [10.9. How does concurrent rendering help React prioritize updates?](#qa-10-009)
  - [10.10. What is the "two render passes" behavior you might see in React 18 Strict Mode, and why doesn't it indicate a bug by itself?](#qa-10-010)
  - [10.11. What are Server Actions, and when would you use them?](#qa-10-011)
  - [10.12. What is the difference between async mode and concurrent mode?](#qa-10-012)
  - [10.13. What are the key features introduced in React 18?](#qa-10-013)
  - [10.14. How does React Compiler preserve the behavior of components?](#qa-10-014)
  - [10.15. When can concurrent rendering add complexity instead of improving performance?](#qa-10-015)
  - [10.16. Can I use JavaScript urls in react16.9?](#qa-10-016)
  - [10.17. Is there a functional-component equivalent of error boundaries?](#qa-10-017)
  - [10.18. What is `startTransition`?](#qa-10-018)
  - [10.19. How does React break rendering into work units and schedule them?](#qa-10-019)
  - [10.20. Are custom DOM attributes supported in React v16?](#qa-10-020)
  - [10.21. Can you explain batching in React 18 vs React 17?](#qa-10-021)
  - [10.22. What is the behavior of uncaught errors in React 16?](#qa-10-022)
- **[11. SSR, Next.js & Server Components](#section-11)** (39)
  - [11.1. Can you explain browser downloads the JS bundle (hydration)?](#qa-11-001)
  - [11.2. How do environment variables work differently between server and client code in Next.js?](#qa-11-002)
  - [11.3. How do you fetch data in the App Router?](#qa-11-003)
  - [11.4. How does Next.js handle image optimization?](#qa-11-004)
  - [11.5. How would you implement Server-Side Rendering (SSR) for a React application? When to use SSR, SSG, ISR?](#qa-11-005)
  - [11.6. Can you explain server Action vs API route?](#qa-11-006)
  - [11.7. Can you explain rSC vs SSR – what's the difference?](#qa-11-007)
  - [11.8. How would you load feature flags on the server in a Next.js app?](#qa-11-008)
  - [11.9. Can you explain sSR vs SSG vs ISR?](#qa-11-009)
  - [11.10. What is streaming SSR? How does `Suspense` enable it?](#qa-11-010)
  - [11.11. What are the differences between page router and app router in nextjs?](#qa-11-011)
  - [11.12. What is "hydration cost" in SSR apps, and how do you reduce it?](#qa-11-012)
  - [11.13. What is hydration?](#qa-11-013)
  - [11.14. What is hydration? How do hydration mismatches occur?](#qa-11-014)
  - [11.15. What is request middleware in Next.js, and when would you use it?](#qa-11-015)
  - [11.16. What is ReactDOMServer?](#qa-11-016)
  - [11.17. What is server-side rendering (SSR), and how does it differ from client-side rendering?](#qa-11-017)
  - [11.18. What is the "FOUC" (flash of unstyled content) risk with runtime CSS-in-JS in SSR, and how is it mitigated?](#qa-11-018)
  - [11.19. What is the difference between a dynamic and a static route segment caching behavior in the App Router?](#qa-11-019)
  - [11.20. What is the Next.js App Router, and how does it differ from the Page Router?](#qa-11-020)
  - [11.21. What is the security consideration around React Server Components and passing data from server to client?](#qa-11-021)
  - [11.22. When to use client and server components?](#qa-11-022)
  - [11.23. How are React Server Components different from Client Components?](#qa-11-023)
  - [11.24. What is the difference between `next/link` prefetching and a manual `router.prefetch()` call?](#qa-11-024)
  - [11.25. How do you prevent waterfall requests in a component tree?](#qa-11-025)
  - [11.26. Is it possible to use async/await in plain React?](#qa-11-026)
  - [11.27. What are Next.js `loading.js` and `error.js`?](#qa-11-027)
  - [11.28. What are React Server Components (RSC)?](#qa-11-028)
  - [11.29. What is `getStaticPaths` (Pages Router)? When is it needed?](#qa-11-029)
  - [11.30. What is ISR (Incremental Static Regeneration)?](#qa-11-030)
  - [11.31. What is NextJS and major features of it?](#qa-11-031)
  - [11.32. What is selective hydration? Why does it matter?](#qa-11-032)
  - [11.33. What is SSG (Static Site Generation)?](#qa-11-033)
  - [11.34. What is streaming SSR?](#qa-11-034)
  - [11.35. What does the "use client" directive mean in Next.js?](#qa-11-035)
  - [11.36. What is the `use server` directive (Next.js Server Actions)?](#qa-11-036)
  - [11.37. What is the risk of putting sensitive logic/secrets in a Client Component by mistake?](#qa-11-037)
  - [11.38. How would you implement server-side rendering for a React application?](#qa-11-038)
  - [11.39. What replaced ReactDOMServer.renderToNodeStream for streaming SSR?](#qa-11-039)
- **[12. Error Handling & Error Boundaries](#section-12)** (16)
  - [12.1. Which types of errors are caught by a React error boundary?](#qa-12-001)
  - [12.2. How do you create an error boundary?](#qa-12-002)
  - [12.3. How do you log errors caught by an Error Boundary to a monitoring service (e.g., Sentry)?](#qa-12-003)
  - [12.4. How do you reset an Error Boundary after the user retries (e.g., clicking "Try again")?](#qa-12-004)
  - [12.5. How do you test error boundaries?](#qa-12-005)
  - [12.6. What are the methods invoked during error handling?](#qa-12-006)
  - [12.7. What is an Error Boundary? What errors does it NOT catch?](#qa-12-007)
  - [12.8. What is the benefit of component stack trace from error boundary?](#qa-12-008)
  - [12.9. What is the difference between a recoverable and an unrecoverable error in a React app's error-handling strategy?](#qa-12-009)
  - [12.10. Why can't a single top-level Error Boundary be a complete error-handling strategy?](#qa-12-010)
  - [12.11. Can you describe about componentDidCatch lifecycle method signature?](#qa-12-011)
  - [12.12. What is global error monitoring in React apps?](#qa-12-012)
  - [12.13. What is the purpose of getDerivedStateFromError?](#qa-12-013)
  - [12.14. What is the proper placement for error boundaries?](#qa-12-014)
  - [12.15. What is the behavior of an uncaught error with no error boundary present (React 16+)?](#qa-12-015)
  - [12.16. How are error boundaries handled in React v15?](#qa-12-016)
- **[13. Design Patterns (HOC, Render Props, Compound Components)](#section-13)** (25)
  - [13.1. How would you define a clean API for a reusable React component?](#qa-13-001)
  - [13.2. How do you create HOC using render props?](#qa-13-002)
  - [13.3. How do you build a reusable modal?](#qa-13-003)
  - [13.4. What is a higher-order component (HOC)? Give an example?](#qa-13-004)
  - [13.5. How do you design a component library that's flexible and consistent org-wide?](#qa-13-005)
  - [13.6. What is the difference between a Compound Component and a Slot-based component?](#qa-13-006)
  - [13.7. How would you develop a React component in isolation?](#qa-13-007)
  - [13.8. How would you version the API of a shared React component library?](#qa-13-008)
  - [13.9. How would you build a reusable React component library?](#qa-13-009)
  - [13.10. How would you document reusable React components for a team?](#qa-13-010)
  - [13.11. How do you create a generic, reusable component?](#qa-13-011)
  - [13.12. What is the purpose of forward ref in HOCs?](#qa-13-012)
  - [13.13. What are HOC factory implementations?](#qa-13-013)
  - [13.14. Can you explain higher-Order Component (HOC) that logs props on every render?](#qa-13-014)
  - [13.15. What is render hijacking in React?](#qa-13-015)
  - [13.16. How do you pass a component as a prop (not just data)?](#qa-13-016)
  - [13.17. What is the trade-off of the Compound Components pattern vs a single component with a declarative config object/array prop?](#qa-13-017)
  - [13.18. How does the "Compound Components" pattern handle components that aren't direct children (e.g., nested in a wrapper div)?](#qa-13-018)
  - [13.19. What do you analyze before designing a reusable React component?](#qa-13-019)
  - [13.20. How would you organize folders in a large React codebase?](#qa-13-020)
  - [13.21. What are the limitations of higher-order components (HOCs)?](#qa-13-021)
  - [13.22. What is a design system / component library pattern?](#qa-13-022)
  - [13.23. What is the "props getter" pattern used by headless libraries (e.g., downshift)?](#qa-13-023)
  - [13.24. What is the Compound Components pattern?](#qa-13-024)
  - [13.25. What is a monorepo, and what tools help manage one for a React codebase (e.g., sharing a component library across apps)?](#qa-13-025)
- **[14. Testing React Applications](#section-14)** (26)
  - [14.1. Give a simple example of Jest test case?](#qa-14-001)
  - [14.2. Can you explain `getBy` vs `queryBy` vs `findBy` – when do you use each?](#qa-14-002)
  - [14.3. How do you test that a component is accessible?](#qa-14-003)
  - [14.4. What roles do render, screen and userEvent play in React Testing Library?](#qa-14-004)
  - [14.5. What is React Testing Library (RTL)?](#qa-14-005)
  - [14.6. What is visual regression testing, and how would you implement it?](#qa-14-006)
  - [14.7. What is Vitest and how does it differ from Jest?](#qa-14-007)
  - [14.8. Why does RTL discourage test IDs/class names? When is `data-testid` appropriate?](#qa-14-008)
  - [14.9. How do you mock API calls with `msw`?](#qa-14-009)
  - [14.10. How do you test async behavior (e.g., API calls)?](#qa-14-010)
  - [14.11. How do you test components with context?](#qa-14-011)
  - [14.12. How do you test components wrapped in Providers/Router?](#qa-14-012)
  - [14.13. How do you test error states (e.g., a failed API call shows an error message)?](#qa-14-013)
  - [14.14. How do you test user interactions?](#qa-14-014)
  - [14.15. How do you test a component that fetches data in `useEffect`?](#qa-14-015)
  - [14.16. How do you test custom hooks?](#qa-14-016)
  - [14.17. What is `act()`? Why does RTL warn about updates outside it?](#qa-14-017)
  - [14.18. What is Mock Service Worker (MSW)?](#qa-14-018)
  - [14.19. How do you test a component using fake timers (e.g., a debounce or a countdown)?](#qa-14-019)
  - [14.20. What is Shallow Renderer in React testing?](#qa-14-020)
  - [14.21. What is the difference between visual regression testing and contract testing?](#qa-14-021)
  - [14.22. What is the difference between shallow and deep rendering?](#qa-14-022)
  - [14.23. What are the RTL query priorities?](#qa-14-023)
  - [14.24. What is snapshot testing? When is it useful vs risky?](#qa-14-024)
  - [14.25. How would you test a React application at different levels?](#qa-14-025)
  - [14.26. Is ReactTestUtils still recommended for testing React?](#qa-14-026)
- **[15. TypeScript with React](#section-15)** (21)
  - [15.1. Why use TypeScript with React?](#qa-15-001)
  - [15.2. How do you avoid `any` when typing a third-party library without TypeScript definitions?](#qa-15-002)
  - [15.3. How do you design a reusable button component?](#qa-15-003)
  - [15.4. How do you type children in React with TypeScript?](#qa-15-004)
  - [15.5. How would you use TypeScript in `create-React-app` application?](#qa-15-005)
  - [15.6. What is `PropTypes`? How does it differ from TypeScript?](#qa-15-006)
  - [15.7. Can you explain `React.FC` vs explicit return type – which is better?](#qa-15-007)
  - [15.8. What is a discriminated union and when is it useful in React?](#qa-15-008)
  - [15.9. How do you say that props are readonly?](#qa-15-009)
  - [15.10. How do you type a component that accepts all native `<button>` props plus custom ones?](#qa-15-010)
  - [15.11. How do you type a React function component’s props in TypeScript?](#qa-15-011)
  - [15.12. How do you type event handlers?](#qa-15-012)
  - [15.13. How do you type `useContext` so consumers get a properly-typed value (and a helpful error if used outside the Provider)?](#qa-15-013)
  - [15.14. How do you type `useRef` for a DOM node vs a mutable value?](#qa-15-014)
  - [15.15. How do you type `useState` when the initial value doesn't convey the full type?](#qa-15-015)
  - [15.16. How do you type a custom Hook's tuple return value?](#qa-15-016)
  - [15.17. How do you type a reducer function and its actions for `useReducer`?](#qa-15-017)
  - [15.18. How do you type a `forwardRef` component?](#qa-15-018)
  - [15.19. How React PropTypes allow different types for one prop?](#qa-15-019)
  - [15.20. What is `satisfies` and how is it useful for typing component configuration objects?](#qa-15-020)
  - [15.21. What is Flow?](#qa-15-021)
- **[16. Styling in React](#section-16)** (15)
  - [16.1. How would you use Font Awesome icons in React?](#qa-16-001)
  - [16.2. Is it recommended to use CSS In JS technique in React?](#qa-16-002)
  - [16.3. What is a "zero-runtime" CSS-in-JS library (e.g., vanilla-extract, Panda CSS)? How does it differ from `styled-components`?](#qa-16-003)
  - [16.4. What is CSS-in-JS? Trade-offs vs traditional CSS?](#qa-16-004)
  - [16.5. What is Tailwind CSS? How does it differ from CSS-in-JS?](#qa-16-005)
  - [16.6. What is the purpose of a `postcss`/Tailwind build step in a React project, and how does it interact with the bundler?](#qa-16-006)
  - [16.7. How would you use styles in React?](#qa-16-007)
  - [16.8. How do you keep component styling encapsulated and themeable?](#qa-16-008)
  - [16.9. What are CSS Modules? How do they prevent collisions?](#qa-16-009)
  - [16.10. How would you add Bootstrap to a React application?](#qa-16-010)
  - [16.11. Give an example of Styled Components?](#qa-16-011)
  - [16.12. What are the different ways to style a React component?](#qa-16-012)
  - [16.13. What is the benefit of styles modules?](#qa-16-013)
  - [16.14. How do you theme a React app (light/dark mode) cleanly?](#qa-16-014)
  - [16.15. How would you implement theme customization in React?](#qa-16-015)
- **[17. Security & Accessibility](#section-17)** (19)
  - [17.1. What tools help check React app accessibility?](#qa-17-001)
  - [17.2. Why does accessibility matter in React apps?](#qa-17-002)
  - [17.3. How do you securely store auth tokens in a React app?](#qa-17-003)
  - [17.4. How would you use innerHTML in React?](#qa-17-004)
  - [17.5. How does React help prevent XSS, and what risks remain?](#qa-17-005)
  - [17.6. What are ARIA roles and attributes?](#qa-17-006)
  - [17.7. What is dangerouslySetInnerHTML, and what are its security risks?](#qa-17-007)
  - [17.8. What is `eslint-plugin-jsx-a11y`? What does it catch?](#qa-17-008)
  - [17.9. What is a CSRF attack and how do you prevent it in React apps?](#qa-17-009)
  - [17.10. What is color contrast, and how do you verify a React app meets WCAG requirements?](#qa-17-010)
  - [17.11. Why does accessibility matter in React SPAs specifically?](#qa-17-011)
  - [17.12. How do you prevent a dependency supply-chain attack from affecting a React app?](#qa-17-012)
  - [17.13. How do you prevent clickjacking in a React app?](#qa-17-013)
  - [17.14. How would you implement role-based access control (RBAC) in React?](#qa-17-014)
  - [17.15. What is a Subresource Integrity (SRI) hash, and when would a React app use one?](#qa-17-015)
  - [17.16. What is the risk of exposing API keys/secrets in a client-side React bundle?](#qa-17-016)
  - [17.17. What is a focus trap?](#qa-17-017)
  - [17.18. What is a skip link?](#qa-17-018)
  - [17.19. Can you explain user Authentication and Session Management?](#qa-17-019)
- **[18. React Ecosystem & Build Tools](#section-18)** (35)
  - [18.1. How would you access current locale with React Intl?](#qa-18-001)
  - [18.2. How would you format a date using React Intl?](#qa-18-002)
  - [18.3. How would you use FormattedMessage as a placeholder with React Intl?](#qa-18-003)
  - [18.4. How can Polymer web components be used in a React app?](#qa-18-004)
  - [18.5. How would you implement internationalization (i18n) in React?](#qa-18-005)
  - [18.6. Can you explain a/B Testing: How to implement A/B testing without affecting current users?](#qa-18-006)
  - [18.7. How does tree shaking work in modern bundlers?](#qa-18-007)
  - [18.8. How would you avoid using relative path imports in create-React-app?](#qa-18-008)
  - [18.9. Can you explain webpack vs Vite vs esbuild/SWC for a React app?](#qa-18-009)
  - [18.10. What environment variables are safe to expose in a React app?](#qa-18-010)
  - [18.11. What is the difference between a bundler and a compiler/transpiler in the React toolchain (e.g., Webpack vs Babel/SWC)?](#qa-18-011)
  - [18.12. How do you implement feature flags in a React application?](#qa-18-012)
  - [18.13. What are the main features of React Intl?](#qa-18-013)
  - [18.14. What is the purpose of registerServiceWorker in React?](#qa-18-014)
  - [18.15. How would you debug your React Native?](#qa-18-015)
  - [18.16. How would you do logging in React Native?](#qa-18-016)
  - [18.17. What is blue-green deployment, and how would you use it for a frontend?](#qa-18-017)
  - [18.18. What compatibility issues should you consider when using React in different environments?](#qa-18-018)
  - [18.19. What checks should run in a React application’s build and test pipeline?](#qa-18-019)
  - [18.20. How does the React Hooks ESLint plugin help prevent Hook mistakes?](#qa-18-020)
  - [18.21. What are the popular React-specific linters?](#qa-18-021)
  - [18.22. What is `TestRenderer` package in React?](#qa-18-022)
  - [18.23. What is code-splitting?](#qa-18-023)
  - [18.24. What is the purpose of ESLint and Prettier in a React project?](#qa-18-024)
  - [18.25. What is the difference between React Native and React?](#qa-18-025)
  - [18.26. What is the role of Babel in a React project?](#qa-18-026)
  - [18.27. How would you roll out a new frontend release to production safely?](#qa-18-027)
  - [18.28. Can you explain library Upgrade: A component breaks when upgrading a library version -- how do you manage dependencies?](#qa-18-028)
  - [18.29. How do you handle localization and internationalization in React?](#qa-18-029)
  - [18.30. What should you expect in a React machine-coding interview round?](#qa-18-030)
  - [18.31. How would you roll back a faulty frontend release?](#qa-18-031)
  - [18.32. What is chaos engineering for frontend?](#qa-18-032)
  - [18.33. What are the features of create React app?](#qa-18-033)
  - [18.34. Why is Create React App deprecated, and what should new projects use?](#qa-18-034)
  - [18.35. What is Vite, and why is it preferred over Create React App today?](#qa-18-035)
- **[19. Legacy, Ecosystem & Additional Concepts](#section-19)** (9)
  - [19.1. How do you access imperative API of web components?](#qa-19-001)
  - [19.2. How would you programmatically trigger click event in React?](#qa-19-002)
  - [19.3. What are capture phase events?](#qa-19-003)
  - [19.4. What are the advantages of React over Vue.js?](#qa-19-004)
  - [19.5. What does MVW mean, and is it useful for modern React interviews?](#qa-19-005)
  - [19.6. What happened to event pooling?](#qa-19-006)
  - [19.7. When do we need a Higher Order Component?](#qa-19-007)
  - [19.8. What are React Mixins?](#qa-19-008)
  - [19.9. Why is ReactDOM.render considered a legacy API?](#qa-19-009)

---

<a id="section-01"></a>
## 1. Fundamentals, JSX & Virtual DOM

*57 questions — [Back to contents](#contents)*

<a id="qa-01-001"></a>
### 1.1. Can React be used without JSX? How?

**Interview answer:** Yes. JSX is optional. I can write React elements using `React.createElement`, but JSX is shorter and easier to read, so I normally use JSX in real projects.

<a id="qa-01-002"></a>
### 1.2. How would you add a page title and meta tags in a React application?

**Interview answer:** In modern React versions that support document metadata, I can render `<title>` and `<meta>` elements in a component and React places them in the document head. In older setups, I would use a library such as React Helmet or a framework metadata API.

<a id="qa-01-003"></a>
### 1.3. Does the cost of inline arrow functions in JSX always matter?

**Interview answer:** Not usually. An inline arrow function creates a new function on each render, but that is normally inexpensive. It becomes relevant when I pass it to a memoized child, because the changed function reference can defeat `React.memo`. I would profile first, then use `useCallback` only where stable identity actually helps.

<a id="qa-01-004"></a>
### 1.4. How does React keep DOM updates efficient?

**Interview answer:** React creates a description of the next UI, compares it with the previous one, and commits only the necessary DOM changes. This avoids manually updating every DOM element, although the Virtual DOM is not automatically faster than every alternative.

<a id="qa-01-005"></a>
### 1.5. How can we find the version of React at runtime in the browser?

**Interview answer:** I can check the runtime package version using `React.version`. This is useful when debugging a mismatch between the version I expect and the version actually loaded.

<a id="qa-01-006"></a>
### 1.6. How do you write comments in JSX?

**Interview answer:** I put JavaScript-style comments inside JSX expressions, for example `{/* Comment */}`. Outside the JSX markup, I can use normal JavaScript `//` or `/* ... */` comments.

<a id="qa-01-007"></a>
### 1.7. How do style objects work in JSX (`style={{...}}`)?

**Interview answer:** The outer `{}` is JSX interpolation, the inner `{}` is a JS object with camelCased CSS properties and values as strings/numbers (unitless numbers default to `px` for most properties).

<a id="qa-01-008"></a>
### 1.8. How do you print falsy values in JSX?

**Interview answer:** React does not display `true`, `false`, `null`, or `undefined` directly inside JSX. If I need to show one of them, I convert it with `String(value)`. The number `0` and an empty string behave differently: `0` can appear, while an empty string displays nothing.

<a id="qa-01-009"></a>
### 1.9. How would you loop inside JSX?

**Interview answer:** I normally use `array.map()` to turn data into JSX elements, for example `users.map(user => <li key={user.id}>{user.name}</li>)`. I give each item a stable key so React can track it correctly.

**Optional coding illustration:**
```jsx
const items = [{ id: 1, name: 'Asha' }];
return <ul>{items.map(item => <li key={item.id}>{item.name}</li>)}</ul>;
```

<a id="qa-01-010"></a>
### 1.10. What is the Virtual DOM, and how does React update the UI?

**Interview answer:** The Virtual DOM is a common name for React's in-memory representation of the UI. When props or state change, React renders a new description, reconciles it with the previous tree, and commits the needed DOM changes. React does not simply repaint the whole page. This approach makes UI updates predictable, although the Virtual DOM is not automatically faster for every case.

<a id="qa-01-011"></a>
### 1.11. How is event handling in React different from plain HTML?

**Interview answer:** In HTML, handlers are often written as strings in markup. In React, I pass JavaScript functions, such as `onClick={handleClick}`. React uses camelCase event names, and I can manage event behavior through its event system.

<a id="qa-01-012"></a>
### 1.12. How does JSX help prevent injection attacks?

**Interview answer:** React escapes text values inserted into JSX by default, so a string is displayed as text rather than executed as HTML. I still validate untrusted input and avoid `dangerouslySetInnerHTML` unless the HTML has been safely sanitized.

<a id="qa-01-013"></a>
### 1.13. How do you pass an event handler or arguments to a JSX event?

**Interview answer:** I pass the function reference, such as `onClick={handleSave}`, instead of calling it during rendering. If I need an argument, I use `onClick={() => handleSave(id)}`. This ensures the function runs when the event occurs.

**Optional coding illustration:**
```jsx
<button onClick={handleSave}>Save</button>
<button onClick={() => deleteUser(user.id)}>Delete</button>
```

<a id="qa-01-014"></a>
### 1.14. How do you associate a label with an input in JSX?

**Interview answer:** In JSX, I use `htmlFor` on a `<label>` instead of the HTML `for` attribute. For example, `<label htmlFor="email">Email</label>` connects to `<input id="email" />`.

<a id="qa-01-015"></a>
### 1.15. What is React, and why would you use it?

**Interview answer:** React is a JavaScript library for building user interfaces using reusable components. Instead of manually updating DOM elements, I describe how the UI should look based on props and state, and React updates it when those values change. I use it because it makes complex, interactive applications easier to organize and maintain.

<a id="qa-01-016"></a>
### 1.16. Why do React component names begin with a capital letter?

**Interview answer:** React treats lowercase JSX tags, such as `<div>`, as built-in HTML or SVG elements. Capitalized tags, such as `<ProfileCard>`, are treated as custom components. That is why I use PascalCase for component names.

<a id="qa-01-017"></a>
### 1.17. What are the rules of JSX?

**Interview answer:** JSX must return one top-level value, so I wrap sibling elements in a parent or Fragment. I close every tag, use `className` instead of `class` for HTML elements, and put JavaScript expressions inside curly braces.

<a id="qa-01-018"></a>
### 1.18. What is JSX, and how does it become browser-readable JavaScript?

**Interview answer:** JSX is a syntax extension that lets me write UI markup inside JavaScript. A build tool converts JSX into JavaScript that creates React elements. React then uses those elements to render and update the UI.

<a id="qa-01-019"></a>
### 1.19. What is React Dev Tools?

**Interview answer:** React DevTools is a browser extension that helps me inspect the component tree, props, state, and Hooks. Its Profiler is useful for finding slow renders and checking performance improvements.

<a id="qa-01-020"></a>
### 1.20. What is React Intl?

**Interview answer:** React Intl is an internationalization library. It helps format translated messages, dates, numbers, and plural forms using the user's locale, so I do not need to hard-code formatting for every language.

<a id="qa-01-021"></a>
### 1.21. What is React proptype array with shape?

**Interview answer:** To validate an array containing objects in a JavaScript project, I can use `PropTypes.arrayOf(PropTypes.shape({ id: PropTypes.number.isRequired, name: PropTypes.string }))`. `PropTypes` comes from the separate `prop-types` package, not `React.PropTypes`. In new TypeScript projects I usually describe this shape with an interface, while still validating untrusted API data at runtime.

<a id="qa-01-022"></a>
### 1.22. What is React scripts?

**Interview answer:** `react-scripts` was the collection of commands used by Create React App for development, testing, and production builds. It hides most build configuration. For new apps, I usually use Vite or a maintained framework instead of Create React App.

<a id="qa-01-023"></a>
### 1.23. How are the render phase and commit phase different in React?

**Interview answer:** Rendering is when React calls components to calculate what the UI should look like. Committing is when React applies the required changes to the actual DOM. React may render and discard work without committing it. Layout effects run around the commit before the browser paints; passive effects usually run later. This separation helps React schedule UI updates efficiently.

<a id="qa-01-024"></a>
### 1.24. How is the Virtual DOM different from the real DOM?

**Interview answer:** The real DOM is the browser’s actual document structure. The Virtual DOM is React’s in-memory representation of the UI. React compares rendered descriptions and updates the real DOM where changes are needed; the Virtual DOM is an implementation strategy, not a replacement for the browser DOM.

<a id="qa-01-025"></a>
### 1.25. How are error boundaries different from JavaScript try/catch?

**Interview answer:** A JavaScript `try/catch` handles exceptions thrown in the code it directly executes, such as an awaited request inside an event handler. An error boundary catches rendering and lifecycle errors in its descendant React tree and shows fallback UI instead of losing the whole screen. Error boundaries do not replace `try/catch` for asynchronous operations or click handlers.

<a id="qa-01-026"></a>
### 1.26. How should React components be named for readability and debugging?

**Interview answer:** I name components with descriptive PascalCase identifiers such as `UserProfile` or `IncidentTable` so React treats them as components and DevTools displays useful names. I generally rely on normal function or class names. `displayName` is useful for anonymous wrappers or higher-order components when the automatic name is unclear.

<a id="qa-01-027"></a>
### 1.27. Can you import an SVG file and use it as a React component?

**Interview answer:** Yes, if the build setup supports SVG-as-component imports. For example, Create React App supports an SVG component import, while Vite usually needs an SVG plugin such as SVGR. Otherwise, I can use an SVG as an image file or write the SVG markup directly in JSX.

<a id="qa-01-028"></a>
### 1.28. Can I use web components in React application?

**Interview answer:** Yes. React can render Web Components as custom elements. I can pass attributes and work with their custom events, although integration details depend on the React version and the Web Component API.

<a id="qa-01-029"></a>
### 1.29. Can you list down top websites or applications using React as front end framework?

**Interview answer:** React has been used by many major web applications and organizations. In an interview, I would focus on why React is suitable for interactive, component-based interfaces rather than memorizing a company list that may change over time.

<a id="qa-01-030"></a>
### 1.30. What happens during the initial render of a React component?

**Interview answer:** When a UI component renders for the first time, it returns JSX. React uses this structure to create a Virtual DOM tree, which is a lightweight copy of the actual DOM. This Virtual DOM is then used to build and render the Real DOM in the browser.

<a id="qa-01-031"></a>
### 1.31. Can a React component render nothing? How would you do that?

**Interview answer:** Yes. A React component can return `null` when nothing should appear on screen. For example, `if (!isVisible) return null;` prevents that component from rendering UI.

<a id="qa-01-032"></a>
### 1.32. Render order of nested Parent → Child → GrandChild components?

**Interview answer:** For an ordinary initial render, React calls the parent component first because it must learn which children to render, then calls its child and grandchild. Once the render work is ready, React commits changes to the DOM. The actual order of effects, ref callbacks, and development Strict Mode calls is a different question, so I would not infer those from component function call order.

<a id="qa-01-033"></a>
### 1.33. Why does a React component need to return one root element?

**Interview answer:** A component must return one React value. When I need several sibling JSX elements, I wrap them in one parent, such as a `<div>` or a Fragment (`<>...</>`). A Fragment avoids adding an extra DOM element.

<a id="qa-01-034"></a>
### 1.34. What are inline conditional expressions?

**Interview answer:** Conditional rendering means choosing which JSX to show based on a condition. For simple cases I use a ternary, such as `isLoggedIn ? <Dashboard /> : <Login />`. For showing something only when true, I use `isLoading && <Spinner />`, but I avoid expressions like `0 && <Badge />` because React would display `0`.

**Optional coding illustration:**
```jsx
return isLoggedIn ? <Dashboard /> : <Login />;
```

<a id="qa-01-035"></a>
### 1.35. What is the difference between declarative and imperative programming in React?

**Interview answer:** Imperative programming tells the browser each step to perform, like finding an element and changing its text. Declarative programming describes the result I want. React is declarative: I write UI based on state, and React handles the DOM updates.

<a id="qa-01-036"></a>
### 1.36. What is `createRoot()` and why replace `ReactDOM.render()`?

**Interview answer:** `createRoot` is the modern React DOM API for mounting a client-rendered app. I create a root with a DOM element and call `root.render(<App />)`. It replaced the older `ReactDOM.render` flow and supports modern React rendering features.

<a id="qa-01-037"></a>
### 1.37. What is `React.createElement()`? What does it return?

**Interview answer:** `React.createElement` creates a React element object describing what should be rendered, including its type, props, and children. It does not create a real DOM node. JSX is the more readable syntax that compiles to React element creation.

<a id="qa-01-038"></a>
### 1.38. What is a switching component, and when would you use one?

**Interview answer:** A switching component chooses which child component to render based on a value such as a page name or status. For example, a map can connect `"home"` to `HomePage` and `"about"` to `AboutPage`. It keeps several conditional branches in one place.

<a id="qa-01-039"></a>
### 1.39. What does React.lazy do, and when would you use it?

**Interview answer:** `React.lazy` loads a component only when React needs it, instead of including its code in the initial bundle. I use it with a dynamic `import()` and a `Suspense` fallback. This can reduce the initial JavaScript download.

<a id="qa-01-040"></a>
### 1.40. Why React uses `className` over `class` attribute?

**Interview answer:** In React JSX, I generally use `className` to assign CSS classes to HTML elements, for example `<div className="card" />`. `class` is the HTML attribute name; `className` is the standard React prop name for HTML elements.

<a id="qa-01-041"></a>
### 1.41. Why is `React-dom` a separate package from `React`?

**Interview answer:** To decouple the core reconciliation/component model from any specific rendering target, enabling `react-native`, `react-art`, SSR (`react-dom/server`), etc., to share the same core.

<a id="qa-01-042"></a>
### 1.42. What would be the common mistake of function being called every time the component renders?

**Interview answer:** A common mistake is writing `onClick={handleClick()}` instead of `onClick={handleClick}`. The first calls the function while React is rendering; the second passes the function so it runs when the user clicks.

<a id="qa-01-043"></a>
### 1.43. Does React support all HTML attributes?

**Interview answer:** React supports standard HTML attributes and many custom attributes. JSX uses DOM-style names such as `className`, `htmlFor`, and `tabIndex`. I check the React attribute conventions rather than assume every attribute uses HTML spelling.

<a id="qa-01-044"></a>
### 1.44. How do you update a previously rendered React element?

**Interview answer:** React updates the UI when props or state change. In a modern app using `createRoot`, I normally update component state rather than calling the old `ReactDOM.render()` repeatedly.

<a id="qa-01-045"></a>
### 1.45. What types of values can a React component return?

**Interview answer:** A React component can return JSX elements, a string, a number, a fragment, an array of elements with keys, or `null` when it should render nothing.

<a id="qa-01-046"></a>
### 1.46. Should I learn ES6 before learning React?

**Interview answer:** No, you don’t have to learn es2015/es6 to learn react. But you may find many resources or React ecosystem uses ES6 extensively. Let's see some of the frequently used ES6 features,.

<a id="qa-01-047"></a>
### 1.47. What are synthetic events in React?

**Interview answer:** `SyntheticEvent` is a cross-browser wrapper around the browser's native event. Its API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers. The native events can be accessed directly from synthetic events using `nativeEvent` attribute.

<a id="qa-01-048"></a>
### 1.48. What are the limitations of React?

**Interview answer:** React focuses on building user interfaces rather than providing every part of an application framework. For routing, data fetching, and other concerns, I may need additional libraries or a framework such as Next.js. The flexible ecosystem also requires good architectural choices.

<a id="qa-01-049"></a>
### 1.49. What are the Pointer Events supported in React?

**Interview answer:** Pointer Events unify mouse, pen, and touch interaction under handlers such as `onPointerDown`, `onPointerMove`, and `onPointerUp`. I use them for drag, drawing, or gesture interfaces when I want one event model across input devices. I still account for keyboard interactions and touch-action behavior so controls remain accessible.

<a id="qa-01-050"></a>
### 1.50. How can you format strings, numbers, and dates in a React app?

**Interview answer:** I use JavaScript’s `Intl` APIs for dates, numbers, and currencies, or a localization library when the app needs translated messages. React simply renders the formatted result.

<a id="qa-01-051"></a>
### 1.51. Does modern React support Internet Explorer?

**Interview answer:** Modern React targets browsers that support current JavaScript and web platform features; Internet Explorer is not a supported target for modern React releases. For a project with a specific older-browser requirement, I would verify the exact React version, transpilation targets, polyfills, and browser test results rather than claiming blanket IE support.

<a id="qa-01-052"></a>
### 1.52. What are the main differences between React and Angular?

**Interview answer:** React is mainly a UI library, while Angular is a full application framework. React commonly uses JSX and a library-based ecosystem; Angular uses templates, dependency injection, and built-in framework conventions. Both can build large apps, and I would choose based on requirements and team experience.

<a id="qa-01-053"></a>
### 1.53. What is the history behind React evolution?

**Interview answer:** React was developed at Meta and introduced publicly in 2013. Its important evolution includes component-driven rendering, the Fiber architecture, Hooks in React 16.8, concurrent features in React 18, and Actions plus new rendering improvements in React 19. For interviews, I focus on how each change solved real UI problems rather than memorizing exact historical anecdotes.

<a id="qa-01-054"></a>
### 1.54. What is the purpose of displayName class property?

**Interview answer:** The displayName string is used in debugging messages. Usually, you don’t need to set it explicitly because it’s inferred from the name of the function or class that defines the component. You might want to set it explicitly if you want to display a different name for debugging purposes or when you create a higher-order component. For example, To ease debugging, choose a display name that communicates that it’s the result of a withSubscription HOC.

<a id="qa-01-055"></a>
### 1.55. Why does `0 && <Component/>` render "0" instead of nothing?

**Interview answer:** Logical AND returns the first falsy operand if `cond` is falsy; `0` is falsy but is still a valid renderable value, so React renders the literal "0" text instead of nothing. Fix: use a boolean (`cond > 0 && ...`) or a ternary.

<a id="qa-01-056"></a>
### 1.56. How does the newer JSX transform differ from the older transform?

**Interview answer:** The older JSX transform generated `React.createElement(...)` calls, so the React identifier had to be in scope. The newer transform uses helpers from `react/jsx-runtime`, so I do not need a default `React` import just to write JSX. I still import any Hooks or other APIs that I use.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-01-057"></a>
### 1.57. What are decorators in React, and when might you encounter them?

**Interview answer:** Decorators are syntax for wrapping or enhancing a class or method. In older React codebases, they were sometimes used with HOCs such as `connect`. They require the relevant language/toolchain support, and I generally prefer Hooks or normal wrapper functions in modern React.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-02"></a>
## 2. Components, Props & State

*120 questions — [Back to contents](#contents)*

<a id="qa-02-001"></a>
### 2.1. What is lifting state up?

**Interview answer:** Lifting state up means moving state into the closest parent shared by multiple components. The parent passes the value down through props and receives changes through callbacks. This gives the related components one source of truth.

**Optional coding illustration:**
```jsx
function Parent() {
  const [query, setQuery] = useState('');
  return <><Search value={query} onChange={setQuery} /><Results query={query} /></>;
}
```

<a id="qa-02-002"></a>
### 2.2. What is prop drilling and why is it a problem?

**Interview answer:** Prop drilling means passing a prop through several components that do not actually use it, just to reach a deeply nested child. I can reduce it with component composition, Context for shared values, or a state library when needed.

<a id="qa-02-003"></a>
### 2.3. What is React.Fragment and why is it useful?

**Interview answer:** A Fragment lets me group multiple elements without adding an extra DOM node. I use `<>...</>` for normal cases and `<React.Fragment key={id}>` when a Fragment inside a list needs a key.

<a id="qa-02-004"></a>
### 2.4. What is state in React?

**Interview answer:** State is data that a component remembers between renders, such as an input value or an open/closed flag. When I update state through React’s setter, React schedules a render so the UI can reflect the new value.

<a id="qa-02-005"></a>
### 2.5. What is state mutation and how to prevent it?

**Interview answer:** Mutating state means changing an existing object or array directly. React may not recognize the update correctly. Instead I create a new value, such as `setUsers(prev => [...prev, newUser])`.

<a id="qa-02-006"></a>
### 2.6. What is the difference between props and state in React?

**Interview answer:** Props are read-only values passed from a parent to a child. State is data a component manages and updates over time. For example, a parent might pass a `title` as a prop, while the child manages whether a dropdown is open using state.

<a id="qa-02-007"></a>
### 2.7. What are React Portals, and when would you use them?

**Interview answer:** A portal lets React render UI outside its parent DOM node. It is useful for modals and overlays, while events still follow the React component tree.

<a id="qa-02-008"></a>
### 2.8. What is the difference between controlled and uncontrolled components?

**Interview answer:** In a controlled input, React state holds the current value, and `onChange` updates it. In an uncontrolled input, the DOM holds the value and I normally read it using a ref. Controlled inputs are useful for validation and dynamic UI; uncontrolled inputs can be simpler for basic forms.

**Optional coding illustration:**
```jsx
const [name, setName] = useState('');
<input value={name} onChange={e => setName(e.target.value)} />
```

<a id="qa-02-009"></a>
### 2.9. Can you explain event bubbling through a React portal rendered outside the DOM parent?

**Interview answer:** Even when a portal renders a child into a DOM node outside its parent, React still keeps it in the same component tree. Events from the portal can bubble through React’s parent components, even if the DOM ancestry is different.

<a id="qa-02-010"></a>
### 2.10. How do you pass dynamic values to JSX attributes?

**Interview answer:** For a dynamic JSX attribute, I pass a JavaScript expression in curly braces, for example `src={imageUrl}` or `title={user.name}`. Quoted JSX attribute values are plain strings; variables are not interpolated inside those quotes.

<a id="qa-02-011"></a>
### 2.11. Do React state updates merge objects automatically?

**Interview answer:** In class components, `this.setState()` shallowly merges state objects. With the `useState` Hook, setting an object replaces the previous value, so I must copy unchanged fields myself.

**Optional coding illustration:**
```jsx
setUser(prev => ({ ...prev, name: 'Riya' })); // keep other fields
```

<a id="qa-02-012"></a>
### 2.12. How do you set default value for uncontrolled component?

**Interview answer:** In React, the value attribute on form elements will override the value in the DOM. With an uncontrolled component, you might want React to specify the initial value, but leave subsequent updates uncontrolled. To handle this case, you can specify a defaultValue attribute instead of value. The same applies for `select` and `textArea` inputs.

<a id="qa-02-013"></a>
### 2.13. How does Immer help with immutable state updates?

**Interview answer:** Immer lets me write update logic that looks like mutation while it creates a new immutable state value behind the scenes. Redux Toolkit uses Immer inside `createSlice`, so code such as `state.count += 1` is safe there.

<a id="qa-02-014"></a>
### 2.14. How does React batch multiple state updates?

**Interview answer:** React prevents component from re-rendering for each and every state update by grouping multiple state updates within an event handler. This strategy improves the application performance and this process known as batching. The older version of React only supported batching for browser events whereas React18 supported for asynchronous actions, timeouts and intervals along with native events.

<a id="qa-02-015"></a>
### 2.15. How do React components communicate with each other?

**Interview answer:** There are three common patterns. Parent to child: pass data using props. Child to parent: call a callback passed by the parent. Distant components: use Context or a shared state library when prop drilling becomes difficult. I choose the simplest solution that keeps one clear source of truth.

<a id="qa-02-016"></a>
### 2.16. How do you read updated state immediately after dispatching an action?

**Interview answer:** It depends on which `dispatch` I mean. With React's `useReducer`, calling `dispatch()` schedules an update, so the state variable in the current event handler still has its old snapshot. I use the updated state on the next render or in an effect. With a plain Redux store, reducers run synchronously, so `store.getState()` can read the new state immediately after dispatch; React components still re-render later.

<a id="qa-02-017"></a>
### 2.17. If we have var, let, and const, why do we need state variables?

**Interview answer:** Normal `let` and `const` variables do not tell React to update the screen, and local variables are recreated on each render. `useState` keeps values between renders and schedules a render when I update them.

<a id="qa-02-018"></a>
### 2.18. How do class components consume Context with contextType?

**Interview answer:** `contextType` is a class-component API for reading one Context value as `this.context`. I set `MyClass.contextType = ThemeContext` or use a static class property. In function components, `useContext(ThemeContext)` is simpler and can read multiple contexts, so it is my preferred approach for new code.

<a id="qa-02-019"></a>
### 2.19. What happens if you forget the key prop when rendering a list?

**Interview answer:** React warns when list elements lack stable keys. Keys let React match items between renders. Without stable keys, state may attach to the wrong item when the list changes.

<a id="qa-02-020"></a>
### 2.20. Render props pattern — headless component sharing fetch logic?

**Interview answer:** `DataFetcher` is a headless component — it manages fetching logic, the parent controls rendering. When `url` changes, effect re-runs. Key insight: Render props pass state and behavior to consumers via function props. Modern equivalent: custom hooks (more composable, no JSX nesting). Both patterns are valid — render props shine when you need JSX composition context.

<a id="qa-02-021"></a>
### 2.21. When and why should you split React Context providers?

**Interview answer:** I split Contexts when different values change at different rates. For example, theme settings and rapidly changing notifications should not live in one provider if that causes unrelated consumers to update.

<a id="qa-02-022"></a>
### 2.22. What are Keyed Fragments?

**Interview answer:** Keyed Fragments let a list item contain several sibling elements while keeping one stable key. I use `<React.Fragment key={item.id}>` because the short Fragment syntax cannot take a key.

<a id="qa-02-023"></a>
### 2.23. What are props?

**Interview answer:** Props are inputs passed into a React component by its parent. They let us customize a reusable component, and the receiving component should treat them as read-only.

<a id="qa-02-024"></a>
### 2.24. What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)?

**Interview answer:** Common causes: Parent re‑renders – by default, children re‑render even if props haven’t changed. Inline functions/objects passed as props – new references on every render. Context changes – any consumer re‑renders when context value changes. State updates that don’t change the value but still trigger re‑render (if using setState with new object reference).

<a id="qa-02-025"></a>
### 2.25. What does React do differently when a `key` changes vs stays the same?

**Interview answer:** If a component keeps the same type and key in the same position, React normally preserves its state across renders. If the key changes, React treats it as a different component, unmounts the old one, and mounts a fresh instance. I can use that behavior to reset a form, but I avoid changing keys accidentally because it loses local state.

**Optional coding illustration:**
```jsx
<EditForm key={selectedUserId} userId={selectedUserId} /> // new ID resets form
```

<a id="qa-02-026"></a>
### 2.26. What is a reducer? Why must reducers be pure functions?

**Interview answer:** A reducer is a function that calculates next state from current state and an action, like `(state, action) => nextState`. It should be pure so the same inputs always produce the same result, without network calls, timers, or mutation of external variables. This makes updates predictable and easy to test. Redux Toolkit lets us write immutable updates using Immer safely.

**Optional coding illustration:**
```jsx
function reducer(state, action) {
  if (action.type === 'increment') return { count: state.count + 1 };
  return state;
}
```

<a id="qa-02-027"></a>
### 2.27. What is JSX spread attributes (`{...props}`)? What's the risk?

**Interview answer:** Spreads an object's keys as individual props: `<Comp {...props} />`. Risk: passing unintended props through (e.g., leaking a prop the child doesn't expect, or overriding one accidentally depending on order).

<a id="qa-02-028"></a>
### 2.28. What is the controlled component pattern for reusable components?

**Interview answer:** A controlled reusable component receives its value and change handler from a parent. This lets the parent control its behavior. Some components also offer an uncontrolled mode that manages its own state by default.

<a id="qa-02-029"></a>
### 2.29. What is the Controlled/Uncontrolled hybrid pattern?

**Interview answer:** A reusable input can support two modes. In controlled mode, the parent passes `value` and `onChange`; the parent owns the state. In uncontrolled mode, the component manages its own value, often initialized by `defaultValue`. I decide the mode from the start and avoid switching between modes during the component's lifetime.

<a id="qa-02-030"></a>
### 2.30. What is the difference between a "key prop" warning and a "missing dependency" warning?

**Interview answer:** The key warning flags list items without stable identity (reconciliation risk); the missing-dependency warning (from the exhaustive-deps ESLint rule) flags a `useEffect`/`useMemo`/`useCallback` referencing a value not listed in its dependency array (stale-closure risk).

<a id="qa-02-031"></a>
### 2.31. What is the difference between a transition and a regular (synchronous) state update in terms of interruptibility?

**Interview answer:** A regular update renders to completion and commits as soon as possible (urgent). A transition's render work can be paused, abandoned, or restarted if a more urgent update comes in before it finishes, keeping the UI responsive.

<a id="qa-02-032"></a>
### 2.32. What is the Observer/Pub-Sub pattern's use in React outside of Context (e.g., a lightweight event bus for cross-cutting concerns)?

**Interview answer:** A module-level event emitter that components `subscribe`/`publish` to for concerns that don't fit cleanly into the component tree's data flow (e.g., a toast system triggered from non-component code, or a global "logout" event), avoiding the need to lift that state into React itself.

<a id="qa-02-033"></a>
### 2.33. What is the purpose of default value in context?

**Interview answer:** The defaultValue argument is only used when a component does not have a matching Provider above it in the tree. This can be helpful for testing components in isolation without wrapping them.

<a id="qa-02-034"></a>
### 2.34. What happens if you write a boolean prop without a value in JSX?

**Interview answer:** In JSX, writing a boolean prop without a value means `true`, such as `<Button disabled />`. For clarity, I can also write `<Button disabled={true} />`. It does not mean that any omitted prop automatically becomes true.

<a id="qa-02-035"></a>
### 2.35. When should you NOT use Context for state?

**Interview answer:** For frequently changing data (e.g., mouse position, animation frames), because every consumer re-renders. Use a dedicated state library with selectors (Zustand, Jotai, Redux) for fine-grained subscriptions.

<a id="qa-02-036"></a>
### 2.36. Why is state update asynchronous?

**Interview answer:** React batches state updates for performance. `setState()` / the setter from `useState()` schedules a re-render rather than immediately mutating state. Reading state right after calling the setter still returns the old value within the same event handler. This batching prevents unnecessary re-renders.

<a id="qa-02-037"></a>
### 2.37. When should you split a React component into smaller components?

**Interview answer:** I split a component when it has multiple independent responsibilities, when a part is reused, or when state and effects are hard to reason about. There is no universal line-count rule. For example, I might extract a data table's filters and pagination into smaller components while keeping their shared state at the appropriate parent level.

<a id="qa-02-038"></a>
### 2.38. Why are inline ref callbacks or functions not recommended?

**Interview answer:** Inline callback refs are not automatically bad, but creating a new callback each render can cause the previous ref to be detached and the next one attached. If the ref performs expensive work or manages external resources, I keep its identity stable or move cleanup into the callback. In React 19, callback refs can return a cleanup function.

<a id="qa-02-039"></a>
### 2.39. What is a wrapper component?

**Interview answer:** A wrapper component surrounds other components and adds shared behavior or layout. For example, I can create a Card or AuthLayout wrapper and pass its inner content through the `children` prop.

<a id="qa-02-040"></a>
### 2.40. What is the children prop in React, and why is it useful?

**Interview answer:** The `children` prop contains whatever I put between a component’s opening and closing tags. I use it for reusable layout components such as cards, modals, and panels that wrap arbitrary content.

<a id="qa-02-041"></a>
### 2.41. What is forwardRef, and when do you need it?

**Interview answer:** In React 18 and earlier, `forwardRef` lets a function component forward a parent ref to an inner DOM element, such as an input. It is useful for focus and scrolling. In React 19, function components can receive `ref` directly as a prop.

<a id="qa-02-042"></a>
### 2.42. What is the difference between an Element and a Component?

**Interview answer:** A React element is an object describing what should appear on screen, such as `<Button />`. A component is the function or class that defines how that UI is created. React calls the component to produce elements.

<a id="qa-02-043"></a>
### 2.43. What goes wrong when you use an array index as a key and reorder the list?

**Interview answer:** Array indexes are unstable identifiers when items are inserted, removed, or reordered. React may reuse the wrong component instance, so form inputs or local state can appear attached to the wrong item.

<a id="qa-02-044"></a>
### 2.44. What is the `key` prop and why is it important?

**Interview answer:** Keys tell React which list item is which across renders. I use stable IDs from the data, such as `key={user.id}`, rather than array indexes when items can be reordered. Keys only need to be unique among siblings.

**Optional coding illustration:**
```jsx
{todos.map(todo => <TodoItem key={todo.id} todo={todo} />)}
```

<a id="qa-02-045"></a>
### 2.45. What will happen if you use props in initial state?

**Interview answer:** If I copy a prop into initial state, future prop changes do not automatically update that state. I should usually use the prop directly or explicitly synchronize state when there is a good reason.

<a id="qa-02-046"></a>
### 2.46. Should you dispatch another action inside a reducer?

**Interview answer:** No, I should not dispatch another action from inside a reducer. A reducer must be a pure function: given the current state and an action, it returns the next state without side effects. If one action needs to trigger more work, I would do it in an event handler, an effect, or Redux middleware such as a thunk or listener middleware.

<a id="qa-02-047"></a>
### 2.47. What can cause a React component to re-render unexpectedly?

**Interview answer:** A component can re-render because its own state changes, its parent re-renders, or a Context value it uses changes. New object or function references can also defeat memoization. I first profile the issue, then consider moving state closer to its usage, stabilizing props, or using memoization where it helps.

<a id="qa-02-048"></a>
### 2.48. Can you explain difference between `key`-based remounting and conditional rendering?

**Interview answer:** Changing a component's `key` tells React it is a different instance, so React discards the old state and mounts it again. Conditional rendering can show or hide a component, but a stable key helps React preserve state when the same component remains in the same place.

<a id="qa-02-049"></a>
### 2.49. Can you explain conditional rendering in React?

**Interview answer:** Conditional rendering means showing different JSX based on a condition. I can use `if`, a ternary such as `isLoggedIn ? <Dashboard /> : <Login />`, or `&&` for showing something only when a condition is true.

<a id="qa-02-050"></a>
### 2.50. What is a function component in React?

**Interview answer:** A function component is a JavaScript function that receives props and returns React elements. It can use Hooks such as `useState` and `useEffect`. This is the standard style for new React components.

<a id="qa-02-051"></a>
### 2.51. Given users = \[{id:1, active:true}, {id:2, active:false}\], find all active user IDs?

**Interview answer:** I would filter the array for users whose `active` field is true and then map the result to their IDs: `users.filter(user => user.active).map(user => user.id)`. This creates a new array without modifying the original data.

<a id="qa-02-052"></a>
### 2.52. How do you pass data child → parent?

**Interview answer:** Pass a callback function as a prop. The child calls it with data, the parent receives it in the handler and updates its state. This maintains one-way data flow while still communicating upward.

<a id="qa-02-053"></a>
### 2.53. How do you prevent prop explosion in complex components?

**Interview answer:** I use compound components instead of many boolean props. Accept a config object. Use context for deeply shared state. Separate components for different variants rather than one component with 20 props.

<a id="qa-02-054"></a>
### 2.54. How do you update arrays inside state?

**Interview answer:** Eventhough arrays in JavaScript are mutable in nature, you need to treat them as immutable while storing them in a state. That means, similar to objects, the arrays cannot be updated directly inside state. Instead, you need to create a copy of the existing array and then set the state to use newly copied array. To ensure that arrays are not mutated, the mutation operations like direct direct assignment(arr**.

<a id="qa-02-055"></a>
### 2.55. How do you update nested objects inside state?

**Interview answer:** You cannot simply use spread syntax for all kinds of objects inside state. Because spread syntax is shallow and it copies properties for one level deep only. If the object has nested object structure, UI doesn't work as expected with regular JavaScript nested property mutation. Let's demonstrate this behavior with an example of User object which has address nested object inside of it.

<a id="qa-02-056"></a>
### 2.56. How would you create React class components without ES6?

**Interview answer:** Older React projects could create classes with the `create-react-class` package and methods such as `getInitialState`. In modern code, I prefer function components with Hooks; I would use this pattern only when maintaining legacy applications.

<a id="qa-02-057"></a>
### 2.57. How would you use and update the state object?

**Interview answer:** In a class component, I read state using `this.state` and update it with `this.setState`. In a function component, I use `useState`, such as `const [count, setCount] = useState(0)`, and call `setCount` to update the UI.

<a id="qa-02-058"></a>
### 2.58. Is it ref argument available for all functions or class components?

**Interview answer:** A plain function component in React 18 does not receive `ref` as an ordinary prop; I use `forwardRef` there. React 19 allows function components to accept `ref` as a prop. For DOM elements, I attach the ref directly to the element.

<a id="qa-02-059"></a>
### 2.59. Must prop be named as render for render props?

**Interview answer:** No. A render prop can have any name, such as `render`, `children`, or `rowRenderer`. What matters is that the prop receives a function that the component calls to decide what UI to render.

<a id="qa-02-060"></a>
### 2.60. What is a reducer, and how does it manage state?

**Interview answer:** A reducer is a function that receives the current state and an action, then returns the next state. It is useful when several kinds of actions update related data.

<a id="qa-02-061"></a>
### 2.61. How would you manage the visibility of a modal or sidebar shared between components?

**Interview answer:** It's ideal for managing the visibility of shared UI components like modals, drawers, or sidebars, especially when their state needs to be controlled from various parts of the app.

<a id="qa-02-062"></a>
### 2.62. Do React list keys need to be unique across the entire application?

**Interview answer:** No. A key needs to be unique only among sibling elements in the same rendered list. I normally use a stable database ID rather than an array index for lists that can change order.

<a id="qa-02-063"></a>
### 2.63. What causes re-renders in React, and how can you reduce unnecessary ones?

**Interview answer:** A state update usually triggers a render, and a parent render can cause children to render again. Context updates can re-render consumers too. I reduce unnecessary work by keeping state local, splitting Context when helpful, using stable keys, and applying `React.memo`, `useMemo`, or `useCallback` only where profiling shows value.

<a id="qa-02-064"></a>
### 2.64. Where is state stored in a React application?

**Interview answer:** React associates state with a component's position in the render tree, including its type and key. The state is not stored inside the JSX variable itself. If the component stays at the same position, its state is preserved; changing its key can deliberately reset the state. React manages the underlying state records internally.

<a id="qa-02-065"></a>
### 2.65. What are default props and PropTypes?

**Interview answer:** Default props provide fallback values when a parent does not supply a prop. In function components, I usually use default parameter values. PropTypes were used for runtime prop validation in older React projects; for modern apps, TypeScript is commonly preferred, and React 19 removed built-in prop-type checking.

<a id="qa-02-066"></a>
### 2.66. What are React elements vs React components?

**Interview answer:** A component is a function or class that defines reusable UI behavior. A React element is an object describing one instance of UI, for example `<Button label="Save" />`. React uses these elements when rendering components.

<a id="qa-02-067"></a>
### 2.67. What are stateful components?

**Interview answer:** A stateful component stores state that can change over time. Function components manage it with Hooks such as `useState` or `useReducer`.

<a id="qa-02-068"></a>
### 2.68. What are presentational vs container components?

**Interview answer:** A presentational component focuses on displaying UI. A container component handles data and state. With Hooks, I can separate these concerns without strictly following that older pattern.

<a id="qa-02-069"></a>
### 2.69. What are render props?

**Interview answer:** Render props means passing a function prop that returns UI. It lets a component share logic while the caller controls the appearance. Custom Hooks often replace this pattern today.

<a id="qa-02-070"></a>
### 2.70. What are the guidelines to be followed for writing reducers?

**Interview answer:** I keep reducers pure: the same state and action should produce the same result. I do not perform API calls or mutate the existing state inside a plain reducer. Redux Toolkit lets me write mutation-like code safely because Immer handles immutable updates.

<a id="qa-02-071"></a>
### 2.71. What are the problems of using render props with pure components?

**Interview answer:** If you create a function inside a render method, it negates the purpose of pure component. Because the shallow prop comparison will always return false for new props, and each render in this case will generate a new value for the render prop. You can solve this issue by defining the render function as instance method.

<a id="qa-02-072"></a>
### 2.72. What happens if a component wrapped in `memo()` has its own state changes?

**Interview answer:** The component will still re‑render when its internal state changes, regardless of `memo`. `React.memo` only controls re‑renders triggered by parent prop changes. State updates always cause a re‑render of the component (unless you use other optimizations like `useState` with a functional update that doesn't change the value).

<a id="qa-02-073"></a>
### 2.73. Why should we not update the state directly?

**Interview answer:** I never mutate React state directly because React relies on updates through its state setters and on new references to recognize changes. Instead of `items.push(x)`, I would use `setItems(prev => [...prev, x])`.

<a id="qa-02-074"></a>
### 2.74. What is `createSlice()` and what does it contain? (name, initialState, reducers)?

**Interview answer:** `createSlice` accepts an object with: `name`: A string used as prefix for action types. `initialState`: The initial state value. `reducers`: An object mapping action names to reducer functions (or `prepare` callbacks). Each reducer function receives `state` and `action` and can mutate the state (thanks to Immer). `extraReducers` (optional): Allows responding to actions not defined in the slice (e.g., from `createAsyncThunk`).

<a id="qa-02-075"></a>
### 2.75. What is an updater function? Should an updater function be used in all cases?

**Interview answer:** An updater function is a form of `setState` where you pass a function instead of a direct value. This function receives the previous state as an argument and returns the next state. The updater function expression looks like below, Here, `prevCount => prevCount + 1` is the updater function. In the React community, there's often a recommendation to use updater functions when updating state that depends on its previous value.

<a id="qa-02-076"></a>
### 2.76. What is colocation in React?

**Interview answer:** Keeping related code together -- state close to where it's used, styles next to components, tests next to source. Avoid premature abstraction. Move state up only when shared, not just to 'be organized'.

<a id="qa-02-077"></a>
### 2.77. What is composition vs inheritance in React?

**Interview answer:** Composition means building complex interfaces by combining smaller components with props and `children`, instead of inheriting behavior through class hierarchies. For example, a `Modal` accepts a heading and its content as children. React recommends composition because it is easier to reuse and maintain components with different layouts and behavior.

<a id="qa-02-078"></a>
### 2.78. What is flux?

**Interview answer:** Flux is an application architecture (not a framework or library) designed by Facebook to manage data flow in React applications. It was created as an alternative to the traditional MVC (Model-View-Controller) pattern, and it emphasizes a unidirectional data flow to make state changes more predictable and easier to debug. Flux complements React by organizing the way data moves through your application, especially in large-scale or complex projects.

<a id="qa-02-079"></a>
### 2.79. What is Hot Module Replacement (HMR)? Why does it matter for React development?

**Interview answer:** HMR swaps updated modules in a running app without a full page reload, preserving component state during development (e.g., keeping a form's typed input while you tweak its styling), dramatically speeding up the dev feedback loop.

<a id="qa-02-080"></a>
### 2.80. What is prop inversion of control?

**Interview answer:** Prop Inversion of Control (IoC) means a component stops bossing its pieces around and instead says to the developer using it: "You take the wheel, you decide how this part should work." Instead of hardcoding every single behavior inside the component and adding 50 different configuration props, the component hands control back over to you. const names = ["Alice", "Bob", "Charlie"]; items={names} renderItem={(name) => <span>👤 {name}</span>} />.

<a id="qa-02-081"></a>
### 2.81. What is prop type narrowing with discriminated unions (conceptually, even pre-TS)?

**Interview answer:** Structuring props so only a valid, mutually exclusive combination can be passed (e.g., `variant: 'link'` requiring `href`, `variant: 'button'` requiring `onClick`), preventing invalid prop combinations at the API design level.

<a id="qa-02-082"></a>
### 2.82. What is server state vs client state?

**Interview answer:** Server state is data fetched from a backend, such as users or orders. It often needs caching, refetching, and synchronization. Client state is data used to control the UI, such as the open modal or input value.

<a id="qa-02-083"></a>
### 2.83. What is a consumer?

**Interview answer:** A Consumer is a React component that subscribes to context changes. It requires a function as a child which receives current context value as argument and returns a react node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. Lets take a simple example,.

<a id="qa-02-084"></a>
### 2.84. What is test isolation, and why does it matter for React component tests?

**Interview answer:** Each test should run independently without leaking state (mocks, timers, DOM) into the next. RTL's `render` auto-cleans up the DOM after each test (via `afterEach(cleanup)`, often automatic), preventing one test's rendered output from bleeding into another's assertions.

<a id="qa-02-085"></a>
### 2.85. What is the "render in a loop with composition" pattern vs a monolithic configurable component?

**Interview answer:** Instead of one component with many conditional props controlling every variant (`<Card showHeader showFooter variant=...>`), composing smaller pieces (`<Card><Card.Header/><Card.Body/></Card>`) that the consumer assembles as needed, improving flexibility without prop explosion.

<a id="qa-02-086"></a>
### 2.86. What are the advantages and trade-offs of a React SPA?

**Interview answer:** A single-page application loads an app shell and updates views through client-side routing without a full reload on every navigation. It can feel very responsive after loading, but large JavaScript bundles and client-only data fetching can hurt initial load and SEO. I use code splitting, route-level data loading, and SSR when the product needs them.

<a id="qa-02-087"></a>
### 2.87. What is the difference between `interface` and `type` for defining props? When does it matter?

**Interview answer:** Both work for most prop definitions; `interface` supports declaration merging (useful for extending `Express.Request`-style ambient types) while `type` supports unions/intersections more directly. For simple component props, the choice is largely stylistic/team convention.

<a id="qa-02-088"></a>
### 2.88. What is the difference between `setState()` and `replaceState()` methods?

**Interview answer:** In class components, `setState` merges the provided object into existing state. `replaceState` was an older API that replaced the entire state and is not part of the normal modern class-component workflow. In function components, a `useState` setter replaces the stored value.

<a id="qa-02-089"></a>
### 2.89. What is the difference between normalized and nested state shape in a global store?

**Interview answer:** Normalized state stores entities by ID in flat lookup tables (like a database), avoiding duplication and making updates to a single entity cheap. Nested state embeds related data directly, which is simpler initially but causes duplication and update headaches as relationships grow.

<a id="qa-02-090"></a>
### 2.90. What are headless components?

**Interview answer:** A headless component provides logic, behavior and accessibility without enforcing its visual design. The consuming application decides how to style it.

<a id="qa-02-091"></a>
### 2.91. What is the provider pattern?

**Interview answer:** A component that wraps part of the tree and supplies shared state/functionality via context. Used extensively: `ThemeProvider`, `AuthProvider`, `QueryClientProvider`. Stacking providers is common.

<a id="qa-02-092"></a>
### 2.92. What is the purpose of callback function as an argument of `setState()`?

**Interview answer:** Class component `setState` can take a callback that runs after the state update is committed. I use it when I need to perform work after a class component updates. In function components, I usually use an Effect to respond to relevant committed state changes.

<a id="qa-02-093"></a>
### 2.93. What is the recommended approach of removing an array element in React state?

**Interview answer:** I use a non-mutating update, most often `setItems(items => items.filter(item => item.id !== removedId))`. `filter()` returns a new array, so React receives a new reference and can render the changed list. I avoid modifying the existing state array with `splice()` or `push()` and then setting the same reference.

<a id="qa-02-094"></a>
### 2.94. What is the render props pattern?

**Interview answer:** A component accepts a function prop (`render` or `children`) and calls it with shared data. `<Mouse render={({x,y}) => <Cursor x={x} y={y}/>}/>`. Flexible but can lead to callback hell; custom hooks are usually cleaner.

<a id="qa-02-095"></a>
### 2.95. What is the risk of trusting `window.postMessage` data without validation in a React component?

**Interview answer:** Any page can send a `postMessage` to your window; without checking `event.origin` against an allow-list and validating the message shape, a malicious page could inject fake data or trigger unintended state changes.

<a id="qa-02-096"></a>
### 2.96. What is the Slot pattern?

**Interview answer:** The Slot pattern lets a reusable component accept different pieces of UI for specific areas. For example, `<PageLayout header={<Nav />} sidebar={<Filters />}>` allows the caller to choose each region's content. It is useful when a design has a stable structure but different screens need different actions or panels.

<a id="qa-02-097"></a>
### 2.97. What is the state reducer pattern?

**Interview answer:** State Reducer Pattern gives the user of your component a "veto power" or steering wheel over how the component’s internal data changes. Instead of the component making all the rules about how its state updates, it handles the heavy lifting but passes every change through a custom function you provide. This lets you intercept and modify the changes before they actually happen.

<a id="qa-02-098"></a>
### 2.98. When did you get stuck while using React, and how did you fix it?

**Interview answer:** One example is an API response updating after the user has navigated to a different page. I would reproduce the issue, inspect Network and React DevTools, then cancel or ignore outdated requests using Effect cleanup. In a real interview, I would replace this example with an issue I personally solved.

<a id="qa-02-099"></a>
### 2.99. Why can't you update props in React?

**Interview answer:** The React philosophy is that props should be immutable (read-only) and top-down. This means that a parent can send any prop values to a child, but the child can't modify received props. This ensures predictable data flow. *The full document continues with all remaining sections. Due to length, the complete Q&A is provided in the downloadable markdown file.

<a id="qa-02-100"></a>
### 2.100. Why do you not required to use inheritance?

**Interview answer:** In React, it is recommend using composition instead of inheritance to reuse code between components. Both Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Whereas, If you want to reuse non-UI functionality between components, it is suggested to extracting it into a separate JavaScript module.

<a id="qa-02-101"></a>
### 2.101. Why we need to be careful when spreading props on DOM elements?

**Interview answer:** When we *spread props* we run into the risk of adding unknown HTML attributes, which is a bad practice. Instead we can use prop destructuring with `...rest` operator, so it will add only required props.

<a id="qa-02-102"></a>
### 2.102. When do you need to use refs?

**Interview answer:** There are few use cases to go for refs, Managing focus, text selection, or media playback. Triggering imperative animations. Integrating with third-party DOM libraries.

<a id="qa-02-103"></a>
### 2.103. Why do you need additional care for component libraries while using forward refs?

**Interview answer:** When a component library adds or changes ref forwarding, it changes what consumers receive from `ref`, so it can be a breaking public API change. I document the ref target and keep its type stable. In React 19 function components can accept `ref` as a prop; for older supported React versions I may still need `forwardRef`.

<a id="qa-02-104"></a>
### 2.104. Why is `isMounted()` an anti-pattern and what is the proper solution?

**Interview answer:** The primary use case for `isMounted()` is to avoid calling `setState()` after a component has been unmounted, because it will emit a warning. Checking `isMounted()` before calling `setState()` does eliminate the warning, but it also defeats the purpose of the warning. Using `isMounted()` is a code smell because the only reason you would check is because you think you might be holding a reference after the component has unmounted.

<a id="qa-02-105"></a>
### 2.105. Why is calling `setState` inside `render` dangerous?

**Interview answer:** Calling a state setter unconditionally while React is rendering a component can create an infinite render loop. Render logic should calculate UI from current props and state, not perform side effects. I put user-triggered updates in event handlers, and use Effects only when synchronizing with an external system.

<a id="qa-02-106"></a>
### 2.106. What is the difference between `super()` and `super(props)` in React using ES6 classes?

**Interview answer:** In a class constructor, `super()` calls the parent class constructor, while `super(props)` also passes the props to it. `super(props)` was common in older class-based React code. Function components do not use it.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-107"></a>
### 2.107. Which method must a class component implement?

**Interview answer:** In a class component, the required method is `render()`, which returns the UI. The constructor and lifecycle methods are optional. For new React code, I normally use a function component with Hooks instead, because it is simpler and easier to reuse stateful logic.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-108"></a>
### 2.108. What is a class component in React?

**Interview answer:** A class component is an ES6 class that extends `React.Component` and defines a `render()` method. It can hold state and use lifecycle methods. In new React code, I usually prefer function components with Hooks.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-109"></a>
### 2.109. Can you explain data flow in React?

**Interview answer:** React mainly follows one-way data flow. A parent passes data to a child through props; the child notifies the parent about changes using a callback. Shared state can be lifted to a common parent or placed in Context or a store. This makes it easier to know where a UI value comes from and who can change it.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-110"></a>
### 2.110. Does the statics object work with ES6 classes in React?

**Interview answer:** Older `React.createClass` components supported a `statics` object. In ES6 class components, I use the `static` keyword for class-level properties and methods. This is mainly relevant when maintaining legacy code.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-111"></a>
### 2.111. Is it mandatory to define constructor for React component?

**Interview answer:** No, a React class component does not require an explicit constructor. I add one only if I need initialization or binding logic that cannot be expressed with class field syntax. Function components do not have constructors; they use Hooks to manage state and effects.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-112"></a>
### 2.112. How can a class component subscribe to one Context using contextType?

**Interview answer:** In a class component, I can assign a Context object to the static `contextType` field and read its current value through `this.context`. Function components usually read Context with `useContext` instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-113"></a>
### 2.113. How was state initialized in older React.createClass components compared with ES6 classes?

**Interview answer:** ES6 class components initialize state in the constructor with `this.state = ...`. Older `React.createClass` components used `getInitialState()`. `React.createClass` is a legacy API, so I would not start a new project with it.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-114"></a>
### 2.114. What is the difference between Flow and PropTypes?

**Interview answer:** Flow is a _static analysis tool_ (static checker) which uses a superset of the language, allowing you to add type annotations to all of your code and catch an entire class of bugs at compile time. PropTypes is a _basic type checker_ (runtime checker) which has been patched onto React. It can't check anything other than the types of the props being passed to a given component.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-115"></a>
### 2.115. What is the constructor used for in a React class component?

**Interview answer:** In a class component, the constructor can initialize local state and bind event handlers. I call `super(props)` first if I need to use `this`. For function components, I use Hooks instead of a constructor.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-116"></a>
### 2.116. What did unmountComponentAtNode do in older React versions?

**Interview answer:** `unmountComponentAtNode` was an older React DOM API for removing a mounted tree. With `createRoot`, I use `root.unmount()` instead. This removes the tree and runs cleanup for its components.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-117"></a>
### 2.117. Why do class components sometimes call super(props) in the constructor?

**Interview answer:** A class constructor must call `super()` before accessing `this`. Passing `props` to `super(props)` also makes them available to the parent constructor. In most modern function components, this is not needed.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-118"></a>
### 2.118. What is unidirectional data flow in React?

**Interview answer:** Data flows parent → child via props. A child requests a change via a callback passed down, and the parent updates its own state, flowing back down as new props.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-119"></a>
### 2.119. What will happen if you use `setState()` in constructor?

**Interview answer:** In a class component's constructor, I initialize state using `this.state = {...}` rather than calling `setState`. Calling `setState` before the component mounts is unnecessary and can produce confusing behavior.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-120"></a>
### 2.120. Why are String Refs legacy?

**Interview answer:** If you worked with React before, you might be familiar with an older API where the `ref` attribute is a string, like `ref={'textInput'}`, and the DOM node is accessed as `this.refs.textInput`. We advise against it because string refs have below issues, and are considered legacy. String refs were removed in React v16. They force React to keep track of currently executing component.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-03"></a>
## 3. Rendering, Reconciliation & Lifecycle

*35 questions — [Back to contents](#contents)*

<a id="qa-03-001"></a>
### 3.1. What happens in React’s commit phase?

**Interview answer:** The commit phase is when React applies the necessary changes to the real DOM, updates refs, and runs certain lifecycle work and effects. This follows the render phase, where React works out what should change.

<a id="qa-03-002"></a>
### 3.2. What is React Fiber, and why was it introduced?

**Interview answer:** React Fiber is React’s internal architecture for organizing rendering work into smaller units. It helps React prioritize important updates, pause or restart render work, and keep the UI responsive. The final DOM changes happen during the commit phase.

<a id="qa-03-003"></a>
### 3.3. What is reconciliation, and how does React’s diffing algorithm work?

**Interview answer:** Reconciliation is how React compares the newly rendered UI with the previous one. It uses element types and keys to decide what can be reused, updated, or replaced. React then commits the required DOM changes. Stable keys are especially important for lists.

<a id="qa-03-004"></a>
### 3.4. How does React work behind the scenes (render → reconciliation → commit)?

**Interview answer:** Components execute to build a virtual DOM tree; React's Fiber architecture reconciles (diffs) the new tree against the previous one in an interruptible render phase; then applies minimal DOM mutations in an uninterruptible commit phase and runs effects.

<a id="qa-03-005"></a>
### 3.5. How is JavaScript strict mode different from React Strict Mode?

**Interview answer:** There are two different meanings of Strict Mode. JavaScript's `'use strict'` changes JavaScript language rules, such as disallowing accidental globals. React's `<StrictMode>` is a development tool that runs extra checks for render purity and Effect cleanup. React Strict Mode does not change variable scope rules.

<a id="qa-03-006"></a>
### 3.6. How does the React Fiber architecture change how rendering fundamentally works?

**Interview answer:** It replaces the old synchronous, recursive stack-based reconciler with an incremental one built on linked Fiber nodes — enabling pausable/resumable/abortable/prioritizable rendering work, which is the foundation for concurrent rendering, transitions, and Suspense.

<a id="qa-03-007"></a>
### 3.7. In what order do class mounting, state updates, and componentDidUpdate run?

**Interview answer:** On the initial mount, React renders the class component and then calls `componentDidMount`. If `componentDidMount` schedules state updates, React renders the updated state and then calls `componentDidUpdate`. Updates may be batched, so I avoid assuming one render per `setState` call. If the next value depends on the previous value, I use the updater form: `this.setState(prev => ({ count: prev.count + 1 }))`.

<a id="qa-03-008"></a>
### 3.8. What happens before React commits DOM updates?

**Interview answer:** Before React commits new DOM changes, it computes the next tree during the render phase and decides which mutations are needed. This work may be interrupted or abandoned before commit. React then applies the committed changes together. I keep render logic free of side effects because React can call it more than once.

<a id="qa-03-009"></a>
### 3.9. What are Strict Mode's dev-only behaviors?

**Interview answer:** In development, `<StrictMode>` intentionally re-renders components an extra time to expose impure rendering and runs an extra setup-and-cleanup cycle for Effects and callback refs. These checks do not run in production. The component must remain correct even when an Effect is set up again after cleanup.

<a id="qa-03-010"></a>
### 3.10. What is `getDerivedStateFromProps` and when would you use it?

**Interview answer:** A static class lifecycle that returns new state derived from props before every render. Rarely needed; usually derived state should be computed during render or via `useMemo`. Overuse leads to confusing state synchronization bugs.

<a id="qa-03-011"></a>
### 3.11. What is `PureComponent` vs `Component` in class components?

**Interview answer:** `React.Component` re-renders when it receives an update unless you manually prevent it, while `React.PureComponent` applies a shallow comparison of props and state to skip some updates. PureComponent is only an optimization; it assumes immutable state, so mutating nested objects can make changes invisible to that comparison. In function components I use `React.memo` when it helps.

<a id="qa-03-012"></a>
### 3.12. Can you explain different trees are produced because of different elements?

**Interview answer:** When React compares two elements with different types at the same position, it generally replaces the old subtree instead of trying to reuse it. Any state associated with that subtree is reset. For example, changing from `<LoginForm />` to `<SignupForm />` mounts a new component with fresh state. Stable element types and keys help React preserve state.

<a id="qa-03-013"></a>
### 3.13. What is the commit phase's "passive effects" vs "layout effects" ordering?

**Interview answer:** Layout effects (`useLayoutEffect`) run synchronously right after DOM mutation, before the browser paints. Passive effects (`useEffect`) run asynchronously after paint, so the user may briefly see the pre-effect UI.

<a id="qa-03-014"></a>
### 3.14. What is the methods order when component re-rendered?

**Interview answer:** An update can be caused by changes to props or state. The below methods are called in the following order when a component is being re-rendered. static getDerivedStateFromProps() shouldComponentUpdate() render() getSnapshotBeforeUpdate() componentDidUpdate().

<a id="qa-03-015"></a>
### 3.15. Can you explain elements of the same type are compared attribute-wise?

**Interview answer:** When React reconciles two DOM elements of the same type, such as two `<div>` elements, it can reuse the existing DOM node and update only changed props, styles, and children. If the element type changes, React generally replaces that subtree. This is why React updates an existing button's label without rebuilding the whole page.

<a id="qa-03-016"></a>
### 3.16. Can you explain Strict Mode in React?

**Interview answer:** Strict Mode is a development-only tool for finding bugs caused by impure rendering or missing Effect cleanup. It may re-run rendering and Effects in development to reveal problems. These extra checks do not run in the same way in production.

**Optional coding illustration:**
```jsx
<StrictMode><App /></StrictMode>
```

<a id="qa-03-017"></a>
### 3.17. What is the structure of a React Fiber tree?

**Interview answer:** A Fiber is an internal work record for a component or element. Fibers link to their child, sibling, and parent, which helps React traverse the tree and schedule rendering tasks.

<a id="qa-03-018"></a>
### 3.18. Is it possible to access a ref in the render method?

**Interview answer:** Yes, you can access a ref in the render method, but what you get from it depends on how you're using the ref and when in the component lifecycle you're rendering. For example, when using ref to access a DOM node (e.g., divRef.current), it's not immediately available on the first render.

<a id="qa-03-019"></a>
### 3.19. What are the different phases of component lifecycle?

**Interview answer:** React class components go through mounting, updating, and unmounting. Mounting creates the component, updating reacts to state or prop changes, and unmounting removes it and cleans up resources.

<a id="qa-03-020"></a>
### 3.20. What is `getSnapshotBeforeUpdate`?

**Interview answer:** A class lifecycle called right before the DOM is updated. Its return value is passed as 'snapshot' to `componentDidUpdate`. Used for reading scroll position or other DOM measurements before a commit.

<a id="qa-03-021"></a>
### 3.21. What is `shouldComponentUpdate` and its functional equivalent?

**Interview answer:** `shouldComponentUpdate` returns boolean to control re-rendering in class components. The functional equivalent is `React.memo` (shallow comparison) or a custom comparator passed as its second argument.

<a id="qa-03-022"></a>
### 3.22. What is event delegation in React?

**Interview answer:** React attaches a single event listener at the root DOM node and routes events to the correct handler using its internal fiber tree. This is efficient: one listener handles all events instead of per-element listeners.

<a id="qa-03-023"></a>
### 3.23. What is the lifecycle methods order in mounting?

**Interview answer:** The lifecycle methods are called in the following order when an instance of a component is being created and inserted into the DOM. `constructor()` `static getDerivedStateFromProps()` `render()` `componentDidMount()`.

<a id="qa-03-024"></a>
### 3.24. What is double buffering in React Fiber?

**Interview answer:** React can keep a current Fiber tree for the visible UI and a work-in-progress tree for the next render. It builds changes in the work-in-progress tree and switches to the completed result during commit. This is often described as double buffering.

<a id="qa-03-025"></a>
### 3.25. What is the recommended ordering of methods in component class?

**Interview answer:** Recommended ordering of methods from mounting to render stage: `static` methods `constructor()` `getChildContext()` `componentWillMount()` `componentDidMount()` `componentWillReceiveProps()` `shouldComponentUpdate()` `componentWillUpdate()` `componentDidUpdate()` `componentWillUnmount()` click handlers or event handlers like `onClickSubmit()` or `onChangeDescription()` getter methods for render like `getSelectReason()` or `getFooterContent()` optional render methods like `renderNavigation()` or `renderProfilePicture()` `render()`.

<a id="qa-03-026"></a>
### 3.26. Why do two sibling components with the same `key` cause a warning or misbehavior?

**Interview answer:** React uses `key` to uniquely identify items among siblings during reconciliation; duplicate keys make it ambiguous which DOM node/state belongs to which element, risking incorrect reuse.

<a id="qa-03-027"></a>
### 3.27. Why do you not need error boundaries for event handlers?

**Interview answer:** Error boundaries do not catch errors inside event handlers. React doesn’t need error boundaries to recover from errors in event handlers. Unlike the render method and lifecycle methods, the event handlers don’t happen during rendering. So if they throw, React still knows what to display on the screen. If you need to catch an error inside an event handler, use the regular JavaScript try / catch statement: Note that the above example is demonstrating regular JavaScript behavior and doesn’t use error boundaries.

<a id="qa-03-028"></a>
### 3.28. Why should not call setState in componentWillUnmount?

**Interview answer:** I should not call `setState` in `componentWillUnmount`, because the component is being removed and will not render again. I use this lifecycle method to remove subscriptions, timers, and listeners instead.

<a id="qa-03-029"></a>
### 3.29. What are the three main steps React follows to update the screen?

**Interview answer:** React updates the screen in three broad steps: trigger a render, render the component to work out the next UI, and commit necessary changes to the DOM.

<a id="qa-03-030"></a>
### 3.30. How does React work behind the scenes?

**Interview answer:** React is a powerful JavaScript library for building user interfaces. While it appears simple on the surface, React performs a lot of complex operations behind the scenes to efficiently update the UI. Here's an overview of how it works internally.

<a id="qa-03-031"></a>
### 3.31. What is the difference between mounting and updating in terms of effect behavior?

**Interview answer:** On mount, every effect with satisfied conditions runs for the first time. On update, only effects whose dependency array changed re-run (compare each value against its previous render).

<a id="qa-03-032"></a>
### 3.32. Should you use componentWillMount in a modern React application?

**Interview answer:** No. `componentWillMount` is a legacy lifecycle and should not be used in new React code. The `UNSAFE_componentWillMount` name exists for legacy classes, but it is unsafe with modern rendering. Initialize state in a constructor or class field; perform subscriptions or data-loading side effects in `componentDidMount` and clean them up in `componentWillUnmount`.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-033"></a>
### 3.33. What are the lifecycle methods going to be deprecated in React v16?

**Interview answer:** Older React class lifecycles such as `componentWillMount`, `componentWillReceiveProps`, and `componentWillUpdate` are deprecated for new code. The `UNSAFE_`-prefixed versions remain as legacy APIs, but should generally be avoided. I would replace them with state initialization, `componentDidMount`/`componentDidUpdate`, or function components and Effects depending on the actual job.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-034"></a>
### 3.34. Which is preferred option with in callback refs and findDOMNode()?

**Interview answer:** I prefer React refs and callback refs rather than the old `findDOMNode()` API. Refs make it clear which DOM element I need to focus or measure, while `findDOMNode` relies on finding a descendant of a component instance and is deprecated or unavailable in modern React usage. In React 19 I can pass `ref` directly through function-component props.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-035"></a>
### 3.35. Why is a component constructor called only once?

**Interview answer:** React's *reconciliation* algorithm assumes that without any information to the contrary, if a custom component appears in the same place on subsequent renders, it's the same component as before, so reuses the previous instance rather than creating a new one.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-04"></a>
## 4. Hooks (Core & Advanced)

*177 questions — [Back to contents](#contents)*

<a id="qa-04-001"></a>
### 4.1. Can you explain `useMemo` vs `React.memo` — how are they different?

**Interview answer:** `React.memo` prevents an entire *component* from re-rendering based on props; `useMemo` memoizes a *computed value* inside a component. They're often used together: `React.memo` on the child, `useMemo`/`useCallback` in the parent to keep the props it receives referentially stable.

<a id="qa-04-002"></a>
### 4.2. How does useRef differ from useState?

**Interview answer:** Both `useState` and `useRef` preserve data across renders, but they serve different purposes. Updating state schedules a re-render because it affects what the user sees. Updating `ref.current` does not re-render; it is better for a DOM node, timer ID, or previous value. I never use a ref as a substitute for state that must appear immediately in the UI.

**Optional coding illustration:**
```jsx
const inputRef = useRef(null);
<input ref={inputRef} />
<button onClick={() => inputRef.current?.focus()}>Focus</button>
```

<a id="qa-04-003"></a>
### 4.3. How is useTransition different from Suspense?

**Interview answer:** `Suspense` controls what fallback UI appears when a child suspends, such as while loading a lazy component. `useTransition` marks a state update as non-urgent, allowing React to keep the interface responsive while the new view is prepared. A transition can work with Suspense, but they solve different problems: fallback UI versus update priority.

<a id="qa-04-004"></a>
### 4.4. How can you avoid unstable dependencies in useEffect?

**Interview answer:** I avoid creating new objects or functions unnecessarily as Effect dependencies. If possible, I create the value inside the Effect or move constant values outside the component. When a stable reference is really required, I use `useMemo` or `useCallback` and include all reactive dependencies.

<a id="qa-04-005"></a>
### 4.5. How does useEffect behave with a dependency array?

**Interview answer:** An effect runs again when a value in its dependency array changes. This is how React keeps the effect synchronized with the latest props or state.

<a id="qa-04-006"></a>
### 4.6. Can you combine **useReducer** with **useContext**?

**Interview answer:** Yes. `useReducer` manages complex state transitions, and Context makes the current state and dispatch function available to nested components. For example, an `AuthProvider` can expose `user`, `status`, and `dispatch`. It is useful for moderate shared state, but a large or frequently changing store may benefit from a dedicated library with selectors.

<a id="qa-04-007"></a>
### 4.7. Can you have multiple useEffect hooks in a single component?

**Interview answer:** Yes. A component can have several `useEffect` calls, and each one can handle a separate concern, such as fetching data, setting a timer, or adding an event listener. Keeping effects focused makes cleanup and debugging easier.

<a id="qa-04-008"></a>
### 4.8. How are useEffect, useLayoutEffect, and useInsertionEffect different?

**Interview answer:** `useEffect` runs after React commits updates and is normally used for external synchronization. `useLayoutEffect` runs before the browser paints, so it is useful for layout measurement but can block painting. `useInsertionEffect` is mainly for CSS-in-JS libraries that need to insert styles at a specific stage.

<a id="qa-04-009"></a>
### 4.9. Can you explain useEffect, including its cleanup and dependency array?

**Interview answer:** `useEffect` lets you perform side effects (data fetching, subscriptions, DOM manipulations) in functional components. It runs after the browser paints. Dependency array: If omitted, effect runs after every render. If empty (`[]`), runs only once (mount). If values are provided, effect runs when any of those values change.

**Optional coding illustration:**
```jsx
useEffect(() => {
  const onResize = () => console.log(window.innerWidth);
  window.addEventListener('resize', onResize);
  return () => window.removeEventListener('resize', onResize);
}, []);
```

<a id="qa-04-010"></a>
### 4.10. When does the cleanup function returned by useEffect run?

**Interview answer:** An Effect cleanup runs before its next setup when dependencies change, and when its component unmounts. In development Strict Mode, React also performs an extra setup-and-cleanup check. I use cleanup to remove event listeners, unsubscribe, cancel timers, and abort requests to prevent stale work.

<a id="qa-04-011"></a>
### 4.11. How can Context and custom Hooks work together for feature flags?

**Interview answer:** -- Use a hook like `useFeatureFlag(flagKey)` that returns the current variation. This can be used in components to conditionally render or execute code.

<a id="qa-04-012"></a>
### 4.12. How would you manage event listeners with useEffect?

**Interview answer:** I add a listener inside `useEffect` and remove the same listener in its cleanup function. I also include changing values in the dependency array so the handler does not read stale state.

<a id="qa-04-013"></a>
### 4.13. Can you explain fix a `useEffect` that has missing dependencies (the ESLint exhaustive-deps warning)?

**Interview answer:** Never "fix" the warning by disabling the lint rule (`// eslint-disable-next-line`) unless you're certain the omitted value truly can't change in a way that matters — that's how stale-closure bugs get shipped. If you deliberately don't want the effect to re-run for a value that does change, wrap that value in a ref instead of lying to the dependency array.

<a id="qa-04-014"></a>
### 4.14. How do reactive dependencies in the useEffect dependency array affect its execution behavior?

**Interview answer:** The `useEffect` hook accepts an optional dependencies argument that accepts an array of reactive values. The dependency array determines when the effect runs. i.e, It makes `useEffect` reactive to changes in specified values. How Dependency Array Affects Behavior.

<a id="qa-04-015"></a>
### 4.15. How do you fetch data with `useEffect`? What are the pitfalls?

**Interview answer:** For a simple client-side request, I can fetch inside `useEffect` and clean it up using `AbortController`. I handle loading, success, and error states and include reactive dependencies. The main pitfalls are stale responses, duplicate fetches in development, request waterfalls, and missing caching. For production server state, I usually prefer route loaders or TanStack Query.

<a id="qa-04-016"></a>
### 4.16. How does `useOptimistic` (React 19) differ from manually managing optimistic state with `useState`?

**Interview answer:** `useOptimistic` manages a temporary optimistic view while an Action is pending. It calculates the optimistic value from real state and an optimistic update, then the UI settles back to the authoritative state when the action finishes. With manual `useState`, I must track pending updates and rollback myself. I still handle server errors and make sure successful updates refresh the real state.

<a id="qa-04-017"></a>
### 4.17. How does `useRef` differ from a regular variable?

**Interview answer:** Regular variables reset on every render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for functional components.

<a id="qa-04-018"></a>
### 4.18. How does useLayoutEffect work during server-side rendering (SSR)?

**Interview answer:** `useLayoutEffect` does not run on the server because there is no browser layout to measure. If a component needs layout information, I keep that logic in a client-side component or use `useEffect` when synchronous layout measurement is unnecessary.

<a id="qa-04-019"></a>
### 4.19. When would you use useReducer instead of useState?

**Interview answer:** I use `useState` for simple independent values, like a modal being open. I use `useReducer` when transitions are related or state has many actions, like a multi-step form with `NEXT`, `BACK`, and `RESET`. A reducer centralizes update rules; it does not automatically make the app faster or replace a global store.

**Optional coding illustration:**
```jsx
const [state, dispatch] = useReducer(reducer, { step: 1 });
dispatch({ type: 'next' });
```

<a id="qa-04-020"></a>
### 4.20. What can cause an infinite loop in useEffect?

**Interview answer:** An infinite effect loop usually happens when an effect updates state and then runs again because that state or another unstable dependency changed. I check the dependency list and move work to the right event handler or derived calculation.

<a id="qa-04-021"></a>
### 4.21. Does useImperativeHandle require forwardRef in React 19?

**Interview answer:** In React 19, a function component can accept `ref` as a normal prop and pass it to `useImperativeHandle`, so `forwardRef` is not required for new React 19 function components. In React 18 and earlier, `forwardRef` was normally how the parent ref reached the function component. I match the pattern to the React version used by the project.

<a id="qa-04-022"></a>
### 4.22. In what order do multiple useEffect Hooks execute?

**Interview answer:** React runs effects in the order they are declared within a component after the commit, while cleanup behavior depends on whether the dependencies changed or the component unmounted. I keep independent effects separate.

<a id="qa-04-023"></a>
### 4.23. What happens when you omit the useEffect dependency array?

**Interview answer:** If no dependency array is given, `useEffect` runs after each committed render. This is useful for effects that must follow every render, but can be costly and may create loops.

<a id="qa-04-024"></a>
### 4.24. How do you manage useEffect dependencies correctly?

**Interview answer:** List every value from the component that an effect reads and that can change, such as props, state, and functions. If an object or callback changes every render, move it inside the effect or make its identity stable. Do not suppress dependency warnings just to stop re-renders.

<a id="qa-04-025"></a>
### 4.25. Can you explain react.useMemo() memoizing a JSX element to skip a child's re-render?

**Interview answer:** `useMemo(() => <ExpensiveChild />, [])` can cache a React element object. When React sees the same element reference, it may reuse the previous subtree instead of rendering the child again. However, I usually prefer `React.memo(ExpensiveChild)` or moving state down because memoizing JSX directly can make code harder to read.

<a id="qa-04-026"></a>
### 4.26. When does the setup function inside useEffect run?

**Interview answer:** The setup function in `useEffect` runs after React commits the render. It runs again when dependencies change, after React cleans up the previous effect.

<a id="qa-04-027"></a>
### 4.27. What is a stale closure in useEffect, and how do you fix it?

**Interview answer:** A stale closure happens when an Effect or callback keeps using values captured during an earlier render. This often happens when dependencies are missing. I fix it by including the correct dependencies, using functional state updates where appropriate, or restructuring the Effect.

<a id="qa-04-028"></a>
### 4.28. How do you handle subscriptions safely in useEffect?

**Interview answer:** For a subscription, I subscribe in `useEffect` and return a cleanup function that unsubscribes. This prevents duplicate listeners and memory leaks when dependencies change or the component unmounts.

<a id="qa-04-029"></a>
### 4.29. When does useEffect cleanup run before the next effect?

**Interview answer:** When dependencies change, React runs the previous effect’s cleanup before running the next setup. It also runs cleanup when the component unmounts. In development Strict Mode, extra setup and cleanup checks may occur.

<a id="qa-04-030"></a>
### 4.30. Can you explain useEffect mount/unmount order when toggling between two sibling components?

**Interview answer:** When I conditionally switch from `<ComponentA />` to `<ComponentB />`, React unmounts the old component and mounts the new one because their types differ. Cleanup for A runs and B starts with fresh local state. If the same component type stays in the same position with the same key, its state is normally preserved.

<a id="qa-04-031"></a>
### 4.31. When do useEffect and useLayoutEffect run relative to browser paint?

**Interview answer:** `useLayoutEffect` runs after DOM updates but before the browser paints, so it can measure layout without visible flicker. `useEffect` is generally scheduled later and is the default for non-visual side effects.

<a id="qa-04-032"></a>
### 4.32. Why should you not make the useEffect callback itself async?

**Interview answer:** An effect callback must return nothing or a cleanup function, not a Promise. I define an async function inside the effect and call it, then cancel or ignore stale responses in cleanup.

<a id="qa-04-033"></a>
### 4.33. What happens when useEffect has an empty dependency array?

**Interview answer:** An effect with `[]` runs after the initial mount and cleans up when the component unmounts. In development Strict Mode, React may run an extra setup-and-cleanup cycle to help find bugs. Do not rely on the effect running exactly once in every environment.

<a id="qa-04-034"></a>
### 4.34. Can you explain useMemo recomputing when a dependency array value is a new array reference each render?

**Interview answer:** `useMemo` checks dependencies by identity using `Object.is`. If I create an array with `const data = [1, 2, 3]` on every render and use it as a dependency, the reference changes, so React recalculates the memoized value. I move constant data outside the component or memoize it when a stable reference is actually needed.

<a id="qa-04-035"></a>
### 4.35. Can you explain useTransition marking a state update as non-urgent?

**Interview answer:** `startTransition` marks related state updates as non-urgent; React can pause their rendering to keep the app responsive. `useTransition` also gives an `isPending` flag, which is useful for progress feedback. A transition does not guarantee that Suspense will appear—Suspense only shows a fallback if a child actually suspends.

<a id="qa-04-036"></a>
### 4.36. What are common `useEffect` mistakes?

**Interview answer:** Common Effect mistakes include leaving required dependencies out, using objects that change identity every render, forgetting cleanup, and calculating values in an Effect that could be derived during render. I also avoid putting user-triggered logic in an Effect when an event handler is clearer. Effects are mainly for synchronizing with external systems.

<a id="qa-04-037"></a>
### 4.37. What are the differences between `useEffect` and the experimental `useEvent`/Effect Event pattern?

**Interview answer:** An Effect synchronizes with an external system and re-runs when its dependencies change. An Effect Event, provided by `useEffectEvent` in newer React versions, lets Effect-related code read the latest props and state without making those values dependencies of the surrounding Effect. I would only use it in supported React versions.

<a id="qa-04-038"></a>
### 4.38. How do Effect Events compare with ordinary useEffect callbacks?

**Interview answer:** The older experimental `useEvent` discussions led to the Effect Event pattern, exposed as `useEffectEvent` in supported React versions. It lets effect-related callbacks read fresh props and state without making those values effect dependencies. I still use ordinary event handlers for user clicks.

<a id="qa-04-039"></a>
### 4.39. What are the use cases of useContext hook?

**Interview answer:** The `useContext` hook in React is used to share data across components without having to pass props manually through each level. Here are some common and effective use cases.

<a id="qa-04-040"></a>
### 4.40. What is the use of useEffect React Hooks?

**Interview answer:** The useEffect React Hook is used for performing the side effects in functional components. With the help of useEffect, you will inform React that your component requires something to be done after rendering the component or after a state change. The function you have passed(can be referred to as “effect”) will be remembered by React and call afterwards the performance of DOM updates is over.

<a id="qa-04-041"></a>
### 4.41. What happens if you return a Promise from useEffect?

**Interview answer:** You should NOT return a Promise from useEffect. React expects the function passed to useEffect to return either nothing (undefined) or a cleanup function (synchronous function). i.e, It does not expect or handle a returned Promise. If you still return a Promise, React will ignore it silently, and it may lead to bugs or warnings in strict mode.

<a id="qa-04-042"></a>
### 4.42. What is useContext? What are the steps to follow for useContext?

**Interview answer:** The `useContext` hook is a built-in React Hook that lets you access the value of a context inside a functional component without needing to wrap it in a <Context.Consumer> component. It helps you avoid prop drilling (passing props through multiple levels) by allowing components to access shared data like themes, authentication status, or user preferences.

<a id="qa-04-043"></a>
### 4.43. What is `useLayoutEffect` and how does it differ from `useEffect`?

**Interview answer:** Same API, but fires synchronously after DOM mutations and *before* the browser paints — used for reading layout (measurements) and making synchronous DOM adjustments to avoid visual flicker. `useEffect` is non-blocking and runs after paint.

<a id="qa-04-044"></a>
### 4.44. What is `useReducer` vs `useState`?

**Interview answer:** `useReducer` centralizes complex state transitions in one function via dispatched actions — better when state has multiple sub-values or next state depends on the action type; `useState` is simpler for independent, unrelated values.

<a id="qa-04-045"></a>
### 4.45. What is an infinite `useEffect` loop and how does it happen?

**Interview answer:** Setting state inside an effect that's also a dependency of that same effect (without a stabilizing condition), causing effect → state update → re-render → effect again, forever.

<a id="qa-04-046"></a>
### 4.46. What is Formik / React Hook Form used for?

**Interview answer:** Form state libraries handling values, validation, touched/error tracking, and submission. React Hook Form is uncontrolled-by-default (fewer re-renders, better performance for large forms); Formik uses controlled inputs (simpler mental model, more re-renders).

<a id="qa-04-047"></a>
### 4.47. What is React Hook Form and why is it popular?

**Interview answer:** Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood -- minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms.

<a id="qa-04-048"></a>
### 4.48. What is React Query (TanStack Query) / SWR, and why use them over manual `useEffect` fetching?

**Interview answer:** TanStack Query and SWR help manage data that comes from a server. They provide caching, background refetching, and loading or error states, so I do not need to rebuild those features manually in every `useEffect`.

<a id="qa-04-049"></a>
### 4.49. What is React.memo? How is it different from useMemo and useCallback?

**Interview answer:** Remember: React.memo works from outside, i.e, the props, and useMemo/useCallback work inside the component. You know how in React, whenever a component re-renders, all of its child components also re-render by default. And sometimes, this entire step becomes unnecessary. To prevent it from happening, we use the above three: React.memo, useMemo, & useCallback.

<a id="qa-04-050"></a>
### 4.50. What is React’s use() API and how does it differ from regular Hooks?

**Interview answer:** React's `use(resource)` reads a supported Promise or Context during render. If a Promise is pending, React suspends that subtree and a surrounding `Suspense` boundary can show its fallback; a rejected Promise goes to an error boundary. Unlike most Hooks, `use` can appear conditionally, but it must still be called inside a React component or Hook.

<a id="qa-04-051"></a>
### 4.51. What is the `useEffect` cleanup function?

**Interview answer:** Return a function from `useEffect` to run cleanup before the next effect or on unmount. Used to clear timers, cancel fetch, unsubscribe from observables, or remove event listeners.

<a id="qa-04-052"></a>
### 4.52. What is the difference between useMemo and useCallback?

**Interview answer:** useMemo memoizes the RESULT of a computation — returns cached value until deps change. Use for expensive calculations. useCallback memoizes a FUNCTION DEFINITION — returns same function reference until deps change. Use when passing callbacks to memoized child components. Key distinction: useMemo = memo(fn()), useCallback = memo(fn).

<a id="qa-04-053"></a>
### 4.53. What is the difference between useState and useRef hook?

**Interview answer:** useState causes components to re-render after state updates whereas useRef doesn't cause a component to re-render when the value or state changes. Essentially, useRef is like a "box" that can hold a mutable value in its (`.current`) property. useState allows us to update the state inside components. While useRef allows referencing DOM elements and tracking values.

<a id="qa-04-054"></a>
### 4.54. What problems does React Query solve vs raw `useEffect` fetching?

**Interview answer:** TanStack Query provides a cache for server data, deduplicates requests, handles retries and background refetching, and exposes useful loading and error states. With raw `useEffect`, I would have to build those features and handle race conditions myself. I still use plain effects for genuine subscriptions and synchronization with non-React APIs.

<a id="qa-04-055"></a>
### 4.55. How does React Context help you avoid prop drilling?

**Interview answer:** When a component calls `useContext(SomeContext)` but no matching `<SomeContext.Provider>` is present higher up in the component tree, the default value passed to `React.createContext(defaultValue)` is returned. In this case, `theme` will be 'light'. It's the default value you provided when you created the context. Note: If you don’t specify a default value, the context value will be undefined when used without a provider.

<a id="qa-04-056"></a>
### 4.56. What's a common pitfall when using useContext with objects?

**Interview answer:** A common pitfall when using `useContext` with objects is triggering unnecessary re-renders across all consuming components — even when only part of the context value changes. When you provide an object as the context value, React compares the entire object reference. If the object changes (even slightly), React assumes the whole context has changed, and all components using `useContext(MyContext)` will re-render, regardless of whether they use the part that changed.

<a id="qa-04-057"></a>
### 4.57. When does a child's useEffect cleanup run vs the parent's cleanup?

**Interview answer:** When a child is removed from the tree, React runs the child's Effect cleanup. The parent's cleanup runs only if that parent unmounts or its own Effect dependencies change. For example, toggling `showChild` off cleans up a child's subscription without necessarily affecting the parent's subscription.

<a id="qa-04-058"></a>
### 4.58. When is `useMemo`/`useCallback` actually worth it? Cost of overusing?

**Interview answer:** Worth it for expensive computations or memoized-child/dependency stability. Overuse adds comparison/storage overhead that can net lose for cheap computations. I would profile first, because memoization can add overhead when the original work is cheap.

<a id="qa-04-059"></a>
### 4.59. When should you use Redux/Zustand instead of Context + `useState`?

**Interview answer:** Context plus Hooks works well for modest shared state, like theme or authentication metadata. I consider Redux Toolkit or Zustand when many unrelated components update frequently, when I need selective subscriptions, complex async workflows, or debugging tools. I choose based on application complexity, not because a larger library is always better.

<a id="qa-04-060"></a>
### 4.60. Why is storing derived values in `useState` (and syncing via `useEffect`) usually an anti-pattern?

**Interview answer:** It creates two sources of truth that can get out of sync, adds an unnecessary extra render (state update → re-render), and is harder to reason about than just computing the value directly during render.

<a id="qa-04-061"></a>
### 4.61. How do you cancel a fetch request when a React component unmounts?

**Interview answer:** I use an `AbortController` inside `useEffect`, pass `controller.signal` to `fetch`, and call `controller.abort()` in the cleanup function. This cancels the request when the component unmounts or the Effect runs again and helps avoid outdated responses.

**Optional coding illustration:**
```jsx
useEffect(() => {
  const controller = new AbortController();
  fetch('/api/users', { signal: controller.signal }).catch(err => {
    if (err.name !== 'AbortError') console.error(err);
  });
  return () => controller.abort();
}, []);
```

<a id="qa-04-062"></a>
### 4.62. What are Actions and form Actions in modern React?

**Interview answer:** An Action is work triggered by a user interaction that may update data, often asynchronously. In React 19, form `action` functions can work with `useActionState`, `useFormStatus`, and `useOptimistic` for pending, result, and optimistic states. Whether an Action runs on the client or server depends on the framework and where the function is defined.

<a id="qa-04-063"></a>
### 4.63. Can you explain calling a hook conditionally inside an if block?

**Interview answer:** Calling a Hook inside an `if` block breaks the Rules of Hooks, because React identifies Hook state by call order. If the condition changes, later Hooks may read the wrong state or React can throw a hook-order error. I call the Hook unconditionally, then put conditional logic inside the Hook's callback or in the rendered UI.

<a id="qa-04-064"></a>
### 4.64. Can Hooks be used in class components?

**Interview answer:** No, React Hooks cannot be called inside class components. Hooks are designed for function components and custom Hooks. Existing class components can still use state and lifecycle methods, but if I want Hook-based logic I would extract it into a function component or share logic through appropriate component composition.

<a id="qa-04-065"></a>
### 4.65. Can React Hooks replace Redux?

**Interview answer:** The React Hook cannot be considered as a replacement for Redux (It is an open-source, JavaScript library useful in managing the application state) when it comes to the management of the global application state tree in large complex applications, even though the React will provide a useReducer hook that manages state transitions similar to Redux.

<a id="qa-04-066"></a>
### 4.66. Can useRef be used to store previous values?

**Interview answer:** Yes. A ref can remember the previous render's value without triggering another render. I create `const previous = useRef(value)` and set `previous.current = value` in an Effect after rendering. On the next render, it still holds the previous value. I use this for comparisons, not as the main source of visible UI state.

<a id="qa-04-067"></a>
### 4.67. Can useState take a function as an initial value?

**Interview answer:** Yes, `useState` can take a function as an initial value, and this is a useful feature in React called lazy initialization. This function is also known as initializer function. When you call useState(initialValue), you normally pass in a value directly: But if calculating that initial value is expensive or involves logic, you can pass a function that returns the value: This function avoids doing heavy computation on every render.

<a id="qa-04-068"></a>
### 4.68. Can you describe the useMemo() Hook?

**Interview answer:** The `useMemo()` Hook in React is used to optimize performance by memoizing the result of expensive calculations. It ensures that a function is only re-executed when its dependencies change, preventing unnecessary computations on every re-render. Syntax `computeExpensiveValue`: A function that returns the computed result. `dependencies`: An array of values that, when changed, will cause the memoized function to re-run.

<a id="qa-04-069"></a>
### 4.69. Can you dispatch multiple actions in a row with useReducer?

**Interview answer:** Yes, `useReducer` lets me call `dispatch` multiple times, but each dispatch schedules an update rather than immediately changing the state variable in the current closure. React may batch the updates. If multiple operations are logically one transaction, I may instead dispatch one action and let the reducer calculate the combined next state.

<a id="qa-04-070"></a>
### 4.70. Can you explain how useState works internally?

**Interview answer:** React’s hooks, including `useState`, rely on some internal machinery that keeps track of state per component and per hook call during rendering. Here's a simplified explanation of the internal mechanics: Hook List / Linked List React maintains a linked list or array of "hook states" for each component. When a component renders, React keeps track of which hook it is currently processing via a cursor/index.

<a id="qa-04-071"></a>
### 4.71. When would you use a custom Hook instead of a higher-order component or render prop?

**Interview answer:** Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when you need to wrap a component (e.g., code splitting, legacy compatibility). Render props: when JSX composition is specifically needed.

<a id="qa-04-072"></a>
### 4.72. How do you clean up side effects in a React component?

**Interview answer:** I return a cleanup function from `useEffect` for work that must be undone, such as an event listener, timer, socket subscription, or in-flight request. The cleanup runs before the Effect re-runs with changed dependencies and when the component unmounts. This prevents duplicate subscriptions and stale work from updating the wrong screen.

<a id="qa-04-073"></a>
### 4.73. How do React Hooks differ from class components?

**Interview answer:** Function components use Hooks such as `useState` and `useEffect` for state and side effects. Class components use `this.state`, `setState`, and lifecycle methods. I usually choose function components for new work because Hooks make logic sharing simpler, but I can maintain older class components too.

<a id="qa-04-074"></a>
### 4.74. Do Hooks cover all the functionalities provided by the classes?

**Interview answer:** Hooks cover most work that previously required class components, including state, side effects, refs, and Context. One important exception is traditional React error boundaries, which still use class-component lifecycle methods or a library that wraps them.

<a id="qa-04-075"></a>
### 4.75. Do Hooks replace render props and higher order components?

**Interview answer:** Hooks do not automatically replace every HOC or render-prop pattern, but they make sharing stateful logic simpler for most new components. I usually use a custom Hook first and keep HOCs or render props when their API or composition is useful.

<a id="qa-04-076"></a>
### 4.76. Does React Hook work with static typing?

**Interview answer:** Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. React Hooks are functions that are designed to make sure about all attributes must be statically typed. For enforcing stricter static typing within our code, we can make use of the React API with custom Hooks.

<a id="qa-04-077"></a>
### 4.77. What types of Hooks are available in React?

**Interview answer:** There are two types of Hooks in React. They are: 1. Built-in Hooks: The built-in Hooks are divided into 2 parts as given below: Basic Hooks: `useState()`: This functional component is used to set and retrieve the state. `useEffect()`: It enables for performing the side effects in the functional components.

<a id="qa-04-078"></a>
### 4.78. How would you build a simple component using React Hooks?

**Interview answer:** I will assume that you are having some coding knowledge about JavaScript and have installed Node on your system for creating a below given React Hook program. An installation of Node comes along with the command-line tools: npm and npx, where npm is useful to install the packages into a project and npx is useful in running commands of Node from the command line.

<a id="qa-04-079"></a>
### 4.79. Can you explain React Hooks and why they were introduced?

**Interview answer:** Hooks are functions that let function components use React features such as state, effects, refs and Context. They reduce the need for class components and help reuse stateful logic.

<a id="qa-04-080"></a>
### 4.80. What are Custom Hooks?

**Interview answer:** A Custom Hook is a function in JavaScript whose name begins with ‘use’ and which calls other hooks. It is a part of React v16.8 hook update and permits you for reusing the stateful logic without any need for component hierarchy restructuring. In almost all of the cases, custom hooks are considered to be sufficient for replacing render props and HoCs (Higher-Order components) and reducing the amount of nesting required.

<a id="qa-04-081"></a>
### 4.81. How do you share state logic between components using custom hooks?

**Interview answer:** A custom Hook extracts reusable stateful logic into a function whose name begins with `use`. For example, `useLocalStorage(key)` could manage a state value and synchronize it with browser storage. Calling the same custom Hook in two components does not automatically share one state instance—each call has its own Hook state unless the Hook connects to a shared store or Context.

<a id="qa-04-082"></a>
### 4.82. Can You Use Multiple Contexts in One Component?

**Interview answer:** Yes, it is possible. You can use multiple contexts inside the same component by calling useContext multiple times, once for each context. It can be achieved with below steps, Create multiple contexts using `createContext()`. Wrap your component tree with multiple `<Provider>`s. Call `useContext()` separately for each context in the same component.

<a id="qa-04-083"></a>
### 4.83. Can you use useRef to persist values across renders?

**Interview answer:** Yes. `useRef` preserves its `.current` value between renders without causing a new render when it changes. I use it for DOM references and mutable values such as timer IDs or previous values.

<a id="qa-04-084"></a>
### 4.84. How can you combine React Hooks to share stateful logic?

**Interview answer:** I can combine `useState`, `useEffect`, and `useContext` in a custom Hook to keep shared behavior in one place. Each use of that Hook still has its own local state unless it reads from a shared store or Context.

<a id="qa-04-085"></a>
### 4.85. Can you explain defining a child component inside a parent's render function?

**Interview answer:** Defining a component inside another component creates a new component function every time the parent renders. React can see that as a new component type and reset the child's state. I define components at module scope and pass values through props. This is different from defining an ordinary event handler inside a component, which is usually fine.

<a id="qa-04-086"></a>
### 4.86. Do I need to rewrite all my class components with hooks?

**Interview answer:** No. But you can try Hooks in a few components(or new components) without rewriting any existing code. Because there are no plans to remove classes in React.

<a id="qa-04-087"></a>
### 4.87. Does useMemo prevent re-rendering of child components?

**Interview answer:** No, `useMemo` by itself does not stop a child from re-rendering. It caches a calculation's result; if I also want to skip a child's render when its props stay the same, I can use `React.memo` and pass stable props.

<a id="qa-04-088"></a>
### 4.88. Types of side effects in React component?

**Interview answer:** A side effect is work that interacts with something outside rendering, such as a timer, API connection, event listener, or browser API. Some effects need cleanup, such as removing a listener, while others only update an external system. I use `useEffect` to synchronize with these systems.

<a id="qa-04-089"></a>
### 4.89. Can you explain how to create a simple React Hooks example program?

**Interview answer:** I create a function component and call `useState` at the top level, for example `const [count, setCount] = useState(0)`. I display the value in JSX and update it from a click handler. React then renders the new count.

<a id="qa-04-090"></a>
### 4.90. What are the Rules of Hooks, and why must you follow them?

**Interview answer:** The main Rules of Hooks are: call Hooks at the top level of a React function component or custom Hook, and keep the same call order on every render. Do not call them inside loops, conditionals, event handlers, or ordinary functions. The `eslint-plugin-react-hooks` rules help catch mistakes early.

<a id="qa-04-091"></a>
### 4.91. Can you explain force-updating a component after mutating a ref directly?

**Interview answer:** Changing `ref.current` alone does not cause a render. If I force a separate state update, the next render can read the updated ref, but that is usually a sign I should model the visible value as state instead. I use refs for timers, DOM access, or mutable values that should not update the display on every change.

<a id="qa-04-092"></a>
### 4.92. Can you explain functional update vs direct update?

**Interview answer:** A direct state update such as `setCount(count + 1)` uses the value from the current render's snapshot. If I make multiple dependent updates, I use `setCount(prev => prev + 1)` so each update receives the latest pending state. For object state, `useState` replaces the object, so I preserve existing fields with `{ ...prev, name: 'Bob' }`.

<a id="qa-04-093"></a>
### 4.93. How does React track Hooks internally?

**Interview answer:** React associates Hook state with a component and the order in which Hooks are called. That is why a Hook must not be called conditionally; changing the order would mix up its stored state.

<a id="qa-04-094"></a>
### 4.94. How do Hooks help manage component state?

**Interview answer:** Hooks let function components use state, effects, context, refs, and reusable logic. For simple local data, I use `useState`; for more complex state transitions, I may use `useReducer`.

<a id="qa-04-095"></a>
### 4.95. How do you avoid unnecessary object/function recreation?

**Interview answer:** Declare stable values outside the component when possible, use `useMemo` for objects/arrays, `useCallback` for functions, and avoid inline object literals as prop values in JSX.

<a id="qa-04-096"></a>
### 4.96. How do you avoid unnecessary re-renders caused by Context?

**Interview answer:** A Context consumer re-renders when the context value it reads changes. To reduce unnecessary work, I keep provider values stable where useful, split unrelated data into separate contexts, and move state closer to the components that use it. For rapidly changing global data, a selector-based store can avoid updating every consumer.

<a id="qa-04-097"></a>
### 4.97. How do you create and consume Context?

**Interview answer:** First I create a context, such as `const ThemeContext = createContext('light')`. Then I provide a value around part of the component tree and read it with `useContext(ThemeContext)`. In React 18 I write `<ThemeContext.Provider value={theme}>`; React 19 also accepts `<ThemeContext value={theme}>` as a provider.

**Optional coding illustration:**
```jsx
const ThemeContext = createContext('light');
function Label() {
  const theme = useContext(ThemeContext);
  return <span>{theme}</span>;
}
```

<a id="qa-04-098"></a>
### 4.98. How do you integrate a non-React library (e.g., D3, Leaflet)?

**Interview answer:** Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it.

<a id="qa-04-099"></a>
### 4.99. How do you manage focus after navigation in a SPA?

**Interview answer:** After route change, programmatically move focus to the new page's heading or a skip-link target. Use a ref and `ref.current.focus()` in `useEffect` when the route changes.

<a id="qa-04-100"></a>
### 4.100. How do you pass parent data to the 5th child component?

**Interview answer:** Options in order of preference: (1) Component composition --- restructure so the component needing data isn't 5 levels deep. (2) React Context --- create a context, wrap with Provider at the parent level, consume with useContext at the child --- no prop drilling needed. (3) State management (Redux/Zustand) --- store state globally, child subscribes directly. (4) Prop drilling --- workable for 2-3 levels, painful at 5 levels.

<a id="qa-04-101"></a>
### 4.101. How do you prevent an expensive component from blocking user input (e.g., a large table filtering as you type)?

**Interview answer:** `useTransition` to mark the expensive re-render as low priority, or `useDeferredValue` on the filter text, keeping the input responsive while the table catches up.

<a id="qa-04-102"></a>
### 4.102. How do you share logic between a Hook and an effect cleanup safely (avoiding duplicated subscribe/unsubscribe code)?

**Interview answer:** Define the subscribe/unsubscribe logic as named functions inside the effect (or a stable custom Hook), ensuring the same reference is used to both subscribe and later unsubscribe correctly.

<a id="qa-04-103"></a>
### 4.103. How do you use useRef to focus an input in React?

**Interview answer:** I create `const inputRef = useRef(null)`, pass it as `<input ref={inputRef} />`, and call `inputRef.current?.focus()` in a click handler. The `.current` value points to the DOM input after React mounts it.

<a id="qa-04-104"></a>
### 4.104. How does useLayoutEffect cause layout thrashing?

**Interview answer:** Layout thrashing happens when JavaScript repeatedly writes to layout-related styles and immediately reads measurements, forcing the browser to recalculate layout many times. Because `useLayoutEffect` runs before paint, excessive work there can block the display. I group DOM reads and writes, avoid forced synchronous layouts, and use `useEffect` for work that does not require measurement before paint.

<a id="qa-04-105"></a>
### 4.105. How does `useReducer` works? Explain with an example?

**Interview answer:** `useReducer` manages state through a reducer function. The reducer receives the current state and an action, and returns the next state. For a counter, I could dispatch `{ type: 'increment' }` or `{ type: 'reset' }` instead of putting all update logic inside click handlers.

<a id="qa-04-106"></a>
### 4.106. How does the performance of using Hooks will differ in comparison with the classes?

**Interview answer:** React Hooks will avoid a lot of overheads such as the instance creation, binding of events, etc., that are present with classes. Hooks in React will result in smaller component trees since they will be avoiding the nesting that exists in HOCs (Higher Order Components) and will render props which result in less amount of work to be done by React.

<a id="qa-04-107"></a>
### 4.107. How should you structure a large React application?

**Interview answer:** Feature-based folders (`features/auth`, `features/dashboard`) rather than type-based (`components/`, `containers/`) once the app grows; shared UI primitives in a common folder; business logic pushed into hooks/services; clear separation between UI, state, and data layers; TypeScript for safety at scale.

<a id="qa-04-108"></a>
### 4.108. How can you avoid unnecessary re-renders in a React application?

**Interview answer:** Keep state close to the component that uses it. Split large components, avoid passing new objects or callbacks when unnecessary, and memoize expensive work only when profiling shows a benefit.

<a id="qa-04-109"></a>
### 4.109. How would you ensure hooks followed the rules in your project?

**Interview answer:** I enable `eslint-plugin-react-hooks` so it checks Hook call order and effect dependencies. The plugin catches many common mistakes, such as calling a Hook inside an `if` or leaving reactive values out of an effect dependency list.

<a id="qa-04-110"></a>
### 4.110. How would you optimize a slow React application?

**Interview answer:** Diagnostic first --- profile with React DevTools Profiler to identify: Components rendering too often → add React.memo, fix prop references Expensive computations → wrap with useMemo Large bundle → code splitting with React.lazy, tree shaking Slow initial load → SSR/SSG, preloading critical resources Memory leaks → check useEffect cleanups, event listener removal Long list rendering → implement virtualization Network waterfall → parallel data fetching, caching with React Query/SWR.

<a id="qa-04-111"></a>
### 4.111. Is dispatch from useReducer asynchronous and does it update state immediately?

**Interview answer:** The `dispatch` function returned by `useReducer` is not asynchronous — it is a synchronous function call. When you call `dispatch(action)`, React synchronously invokes your reducer with the current state and the action, computes the new state, and schedules a re-render. However, the state variable does not update immediately within the same render cycle.

<a id="qa-04-112"></a>
### 4.112. Is Hooks cover all use cases for classes?

**Interview answer:** Hooks cover most common uses of class components, including state, effects, and Context. However, React's built-in error boundary mechanism still uses class lifecycle methods, so a Hook cannot replace a custom class-based error boundary directly. I normally write new components as functions and maintain legacy class components where necessary.

<a id="qa-04-113"></a>
### 4.113. Does a React state setter update the state variable immediately?

**Interview answer:** A `useState` setter schedules React to update state; it does not change the state variable inside the current render or event-handler closure. So reading `count` immediately after `setCount(count + 1)` still gives the old snapshot. If the new value depends on the previous one, I use `setCount(prev => prev + 1)`.

**Optional coding illustration:**
```jsx
setCount(prev => prev + 1); // queues an update
// count here still belongs to the current render snapshot
```

<a id="qa-04-114"></a>
### 4.114. What makes a custom Hook easy to maintain?

**Interview answer:** A good custom Hook does one clear job, names itself with `use`, has a small API, follows the Rules of Hooks, and cleans up subscriptions or timers.

<a id="qa-04-115"></a>
### 4.115. Map class lifecycle methods to hooks?

**Interview answer:** `componentDidMount` → `useEffect(() => {...}, [])` `componentDidUpdate` → `useEffect(() => {...}, [dep])` `componentWillUnmount` → cleanup function returned from `useEffect` `getDerivedStateFromProps` → compute derived state inline or in `useMemo`.

<a id="qa-04-116"></a>
### 4.116. Why might you memoize a Context provider value?

**Interview answer:** When a provider passes a new object on every render, Context consumers can update even if the meaningful values did not change. `useMemo` can stabilize that object, but splitting Contexts may be a better long-term solution.

<a id="qa-04-117"></a>
### 4.117. What does React Compiler optimize automatically?

**Interview answer:** React Compiler automatically optimizes eligible React code by memoizing work where it is safe, reducing the need for manual `useMemo`, `useCallback`, and `React.memo`. It is not a guarantee that every component is fast; I still measure performance and follow React's purity rules. For existing code, I check compiler compatibility before enabling it.

<a id="qa-04-118"></a>
### 4.118. How do you safely manage timers and intervals in React?

**Interview answer:** I create a timer inside `useEffect` and clear it in the cleanup using `clearTimeout` or `clearInterval`. This avoids timers running after the component has unmounted.

<a id="qa-04-119"></a>
### 4.119. What is the React use() API, and when is it useful?

**Interview answer:** React’s `use()` API can read a Promise or Context during rendering. If a Promise is pending, it can suspend the component so a nearby `Suspense` boundary shows a fallback.

<a id="qa-04-120"></a>
### 4.120. Can you explain useCallback returning a stable function reference across re-renders?

**Interview answer:** `useCallback` caches a function reference while its dependencies remain unchanged. For example, `const toggle = useCallback(() => setOpen(v => !v), [])` can keep a callback prop stable for a memoized child. It does not stop the parent from rendering, and using it everywhere usually adds complexity without a meaningful benefit.

**Optional coding illustration:**
```jsx
const onSelect = useCallback(id => setSelectedId(id), []);
```

<a id="qa-04-121"></a>
### 4.121. What happens when a useCallback dependency stays unchanged?

**Interview answer:** If a `useCallback` dependency has not changed, React can return the same function reference. That helps memoized children avoid rendering only because a callback prop got recreated.

<a id="qa-04-122"></a>
### 4.122. Can you explain useDeferredValue keeping input responsive during an expensive re-render?

**Interview answer:** `useDeferredValue` lets a slow part of the screen lag behind an urgent input update. For example, the search box updates immediately while a large filtered list renders with the previous query until the new one is ready. It does not throttle network calls by itself; I would still debounce or cancel requests if needed.

<a id="qa-04-123"></a>
### 4.123. What is referential equality, and why does it matter so much in React?

**Interview answer:** Referential equality asks whether two variables point to the same object or function, not just whether their contents look the same. React compares many dependencies and memoized props by reference. For example, `{ a: 1 } !== { a: 1 }`, so recreating an object each render can invalidate `useMemo` or cause a memoized child to render.

<a id="qa-04-124"></a>
### 4.124. When does useMemo recalculate a value?

**Interview answer:** `useMemo` recalculates its result when one of the listed dependencies changes. If the dependencies are unchanged, React can reuse the cached result. I use it for genuinely expensive calculations, not every expression.

<a id="qa-04-125"></a>
### 4.125. Can you explain useRef does not cause re-render?

**Interview answer:** `useRef` stores a value between renders, but changing `ref.current` does not schedule another render. I use state for anything that must appear on the screen and a ref for mutable values or DOM elements.

<a id="qa-04-126"></a>
### 4.126. How would you track the previous value of a prop or state with useRef?

**Interview answer:** I keep the previous value in `useRef` and update `ref.current` in an effect after render. The ref persists across renders without triggering another render.

<a id="qa-04-127"></a>
### 4.127. Can you explain useTransition keeps UI responsive?

**Interview answer:** I would keep the text input update urgent and wrap the expensive results update in `startTransition`. React can then keep typing responsive while it renders the lower-priority results. `isPending` tells us when the transition is still in progress.

<a id="qa-04-128"></a>
### 4.128. What are Custom React Hooks, and How Can You Develop One?

**Interview answer:** Custom Hooks in React are JavaScript functions that allow you to extract and reuse component logic using React's built-in Hooks like `useState`, `useEffect`, etc. They start with the word "use" and let you encapsulate logic that multiple components might share—such as fetching data, handling forms, or managing timers—without repeating code.

<a id="qa-04-129"></a>
### 4.129. What are the best practices for using React Hooks?

**Interview answer:** Following best practices ensures your hooks are predictable, maintainable, and bug-free. Follow the Rules of Hooks Only call hooks at the top level (not inside loops, conditions, or nested functions) Only call hooks from React functions (components or custom hooks) Use the ESLint Plugin Keep Hooks Focused and Simple Use Descriptive Names for Custom Hooks Properly Manage Dependencies Avoid Inline Object/Function Dependencies Clean Up Side Effects Always return a cleanup function when subscribing to events, timers, or external data sources.

<a id="qa-04-130"></a>
### 4.130. What are Higher-Order Components (HOCs)?

**Interview answer:** An HOC takes a component as input and returns an enhanced component. It was widely used for shared behavior; modern React often uses custom Hooks instead.

<a id="qa-04-131"></a>
### 4.131. What are stateless components?

**Interview answer:** If the behaviour of a component is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless you need to use a lifecycle hook in your components, you should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the `this` keyword altogether.

<a id="qa-04-132"></a>
### 4.132. What are the common usecases of useRef hook?

**Interview answer:** Some of the common cases are: \* Automatically focus an input when a component mounts. \* Scroll to a specific element. \* Measure element dimensions (`offsetWidth`, `clientHeight`). \* Control video/audio playback. \* Integrate with non-React libraries (like D3 or jQuery). ### What is useImperativeHandle Hook? Give an example. `useImperativeHandle` is a React Hook that allows a **child component to expose custom functions or properties** to its parent component, when using `ref`.

<a id="qa-04-133"></a>
### 4.133. What are the rules needs to follow for hooks?

**Interview answer:** I call Hooks only at the top level of React function components or custom Hooks. I do not call them in loops, conditions, or nested functions, because React must see the same Hook order on every render.

<a id="qa-04-134"></a>
### 4.134. What are the rules that must be followed while using React Hooks?

**Interview answer:** Hooks have two key rules: call them only at the top level, and call them only inside React function components or custom Hooks. These rules let React match each Hook with the right internal state.

<a id="qa-04-135"></a>
### 4.135. What are the sources used for introducing hooks?

**Interview answer:** Hooks got the ideas from several different sources. Below are some of them, Previous experiments with functional APIs in the react-future repository Community experiments with render prop APIs such as Reactions Component State variables and state cells in DisplayScript. Subscriptions in Rx. Reducer components in ReasonReact.

<a id="qa-04-136"></a>
### 4.136. What are the usecases of useLayoutEffect?

**Interview answer:** You need to use `useLayoutEffect` when your effect must run before the browser paints, such as: Reading layout measurements (e.g., element size, scroll position) Synchronously applying DOM styles to prevent visual flicker Animating layout or transitions Integrating with third-party libraries that require DOM manipulation If there's no visual or layout dependency, prefer `useEffect` — it's more performance-friendly.

<a id="qa-04-137"></a>
### 4.137. What do useActionState and useFormStatus do for React forms?

**Interview answer:** `useActionState` tracks the state returned by an Action, supplies an Action function, and reports whether it is pending. `useFormStatus` is a React DOM Hook used inside a descendant of a form to read the surrounding form's submission status. I use them for validation results, submit-button loading states, and server-backed forms in React 19.

<a id="qa-04-138"></a>
### 4.138. What happens if you call `useState` conditionally?

**Interview answer:** As per rules of React Hooks, hooks must be called unconditionally. For example, if you conditionally call it: React will throw a runtime error because it relies on the order of Hook calls, and conditional logic breaks that order.

<a id="qa-04-139"></a>
### 4.139. What happens if you use useLayoutEffect for non-layout logic?

**Interview answer:** `useLayoutEffect` runs before the browser paints, so it can delay visual updates. I reserve it for tasks such as reading an element's dimensions and adjusting its position without visible flicker. For analytics, network calls, timers, or ordinary subscriptions, `useEffect` is usually better because the browser can paint first.

<a id="qa-04-140"></a>
### 4.140. What is `useActionState` (React 19)?

**Interview answer:** Manages state for an async action. Returns `[state, dispatch, isPending]`. On form submission, calls the action with form data, updates state with the result, and tracks pending status automatically.

<a id="qa-04-141"></a>
### 4.141. What is `useCallback` and why is it used?

**Interview answer:** `useCallback` caches a function reference until its dependencies change. It can prevent unnecessary renders when passing a callback to a memoized child or when a stable function is needed in dependencies. For example, `useCallback(() => save(id), [id])` updates when `id` changes. I do not assume every inline function requires memoization.

<a id="qa-04-142"></a>
### 4.142. What does useDebugValue do?

**Interview answer:** `useDebugValue` adds a helpful label to a custom Hook in React DevTools. It does not affect the UI; it is only useful for debugging or inspecting reusable Hooks.

<a id="qa-04-143"></a>
### 4.143. How do useDeferredValue and useTransition differ?

**Interview answer:** `useTransition` marks updates I trigger as non-urgent and gives me an `isPending` flag. `useDeferredValue` lets a value lag behind when updating the UI is expensive. I use transitions when I control the update, and deferred values when I want a slower part of the UI to follow a changing value.

<a id="qa-04-144"></a>
### 4.144. What is `useId`? Why was it added?

**Interview answer:** `useId` generates a stable ID that works with both server rendering and hydration, mainly for accessibility relationships. For example, a label can use `htmlFor={id}` while the input uses `id={id}`. It should not be used to generate keys for list items; those keys must come from stable data IDs.

<a id="qa-04-145"></a>
### 4.145. When would you use useImperativeHandle in React?

**Interview answer:** `useImperativeHandle` lets a component expose a small custom interface through a ref. For example, a reusable input can expose `focus()` without exposing all its internal details. I use it only when a declarative prop is not enough.

<a id="qa-04-146"></a>
### 4.146. What is `useReducer`? Why do you use useReducer?

**Interview answer:** The `useReducer` hook is a React hook used to manage complex state logic inside functional components. It is conceptually similar to Redux. i.e, Instead of directly updating state like with `useState`, you dispatch an action to a reducer function, and the reducer returns the new state. The `useReducer` hook takes three arguments: `reducer`: A function `(state, action) => newState` that handles how state should change based on the action.

<a id="qa-04-147"></a>
### 4.147. What is `useRef`? What are its two main use cases?

**Interview answer:** `useRef(initialValue)` returns an object whose `current` property survives re-renders. Its two main uses are referencing a DOM element and storing a mutable value that does not need to trigger a render, such as a timer ID. If a value controls the visible interface, I store it in state instead.

**Optional coding illustration:**
```jsx
const timerRef = useRef(null);
// Updating timerRef.current does not cause a re-render.
```

<a id="qa-04-148"></a>
### 4.148. What is useState() in React?

**Interview answer:** `useState` lets a function component remember a value between renders. It returns the current value and a setter function. I call the setter when I want to update the value and the UI.

<a id="qa-04-149"></a>
### 4.149. What is useSyncExternalStore, and when would you use it?

**Interview answer:** `useSyncExternalStore` lets a component safely subscribe to data managed outside React, such as an external store. I give it a subscribe function and a function that reads the current snapshot. Most applications use it through a state-management library rather than directly.

<a id="qa-04-150"></a>
### 4.150. What is a "smart" vs "dumb" component?

**Interview answer:** Smart (container) components manage data/state/logic; dumb (presentational) components just render props. Largely replaced by custom Hooks + a single component today.

<a id="qa-04-151"></a>
### 4.151. What is a monorepo and how does it relate to React projects?

**Interview answer:** A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps.

<a id="qa-04-152"></a>
### 4.152. What is a render prop? How does it compare to Hooks?

**Interview answer:** A component that takes a function prop to determine what to render, sharing logic. Hooks avoid the "wrapper hell" render props create.

<a id="qa-04-153"></a>
### 4.153. What is focus management and why does it matter?

**Interview answer:** After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes.

<a id="qa-04-154"></a>
### 4.154. What is lazy initialization in `useState`?

**Interview answer:** `useState(() => expensiveCalc())` passes a function so the initial value is computed only once (on mount), not on every render. Useful for reading from `localStorage` or parsing data.

<a id="qa-04-155"></a>
### 4.155. What is the purpose of eslint plugin for hooks?

**Interview answer:** The ESLint plugin enforces rules of Hooks to avoid bugs. It assumes that any function starting with ”use” and a capital letter right after it is a Hook. In particular, the rule enforces that, Calls to Hooks are either inside a PascalCase function (assumed to be a component) or another useSomething function (assumed to be a custom Hook).

<a id="qa-04-156"></a>
### 4.156. What is the `React-error-boundary` library?

**Interview answer:** Provides `<ErrorBoundary fallback={...}>` and `<ErrorBoundary FallbackComponent={...}>`. Also provides `useErrorBoundary()` hook to imperatively throw errors into the nearest boundary and reset it.

<a id="qa-04-157"></a>
### 4.157. What is the `useTransition` hook for performance?

**Interview answer:** Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator.

<a id="qa-04-158"></a>
### 4.158. What is the container/presenter pattern and is it still relevant?

**Interview answer:** The container/presenter pattern separates data handling from UI rendering. The container fetches or prepares information, while the presenter displays it. Hooks make this separation more flexible today.

<a id="qa-04-159"></a>
### 4.159. What is the difference between `startTransition` and `useTransition`?

**Interview answer:** `startTransition` is the standalone function (usable outside components, e.g. in a vanilla event handler) for marking an update as a transition; `useTransition` is the Hook version that also gives you an `isPending` boolean for showing a pending UI state.

<a id="qa-04-160"></a>
### 4.160. What is the difference between a development build and a production build of a React app?

**Interview answer:** Development builds include extra warnings, Strict Mode double-invocation, unminified code with readable stack traces, and devtools hooks. Production builds strip these, minify/mangle code, and often run additional optimizations (dead code elimination), resulting in a smaller, faster bundle with less helpful error messages.

<a id="qa-04-161"></a>
### 4.161. What is the difference between optimistic and pessimistic updates?

**Interview answer:** Optimistic: update UI immediately assuming success, roll back on error (fast UX). Pessimistic: wait for server confirmation before updating UI (safe, may feel slow). React 19 has `useOptimistic` for the optimistic pattern.

<a id="qa-04-162"></a>
### 4.162. What is the order of hook execution in a component?

**Interview answer:** Hooks run top-to-bottom on every render in the same order. React relies on call order to associate hook state with the correct hook -- this is why hooks cannot be inside conditionals or loops. Think of React hooks like a numbered seating chart at a wedding. React doesn't remember your hooks by their actual names; it only tracks them by the exact order (seat number) they appear in your code.

<a id="qa-04-163"></a>
### 4.163. What is the risk of using `key` to force-remount a component during a transition?

**Interview answer:** It discards all internal state of the remounted subtree immediately rather than smoothly transitioning, defeating the purpose of `useTransition`'s "keep old UI visible while preparing new" behavior — generally these two patterns solve different problems and shouldn't be combined carelessly.

<a id="qa-04-164"></a>
### 4.164. What is the stable release for hooks support?

**Interview answer:** React Hooks became stable in React 16.8. That was the major release that enabled function components to use state and lifecycle-like behavior without class components. Today I focus on practical Hooks and the Rules of Hooks rather than memorizing older package compatibility lists.

<a id="qa-04-165"></a>
### 4.165. What is the testing pyramid for a React app?

**Interview answer:** Many fast unit tests (functions/hooks), a solid middle layer of integration tests (component interactions, user flows via RTL), and few slow E2E tests (full browser flows via Playwright/Cypress) — most effort belongs in the middle layer.

<a id="qa-04-166"></a>
### 4.166. What is the use() hook in React 19?

**Interview answer:** The `use()` hook allows you to read the value of a resource (Promise or Context) during render, with Suspense integration.

<a id="qa-04-167"></a>
### 4.167. What is the useId hook and when should you use it?

**Interview answer:** The `useId` hook is a React hook introduced in React 18 that generates unique IDs that are stable across server and client renders. It's primarily used for accessibility attributes like linking form labels to inputs.

<a id="qa-04-168"></a>
### 4.168. What is useInsertionEffect and who should use it?

**Interview answer:** `useInsertionEffect` is mainly intended for CSS-in-JS library authors who need to insert style rules before layout effects run. I would not use it for normal data fetching, DOM measurements, or application state. For most application side effects I use `useEffect`, and for DOM layout measurement I use `useLayoutEffect` when necessary.

<a id="qa-04-169"></a>
### 4.169. What are the two important Rules of Hooks?

**Interview answer:** Call Hooks only at the top level of React function components or custom Hooks, and do not call them in loops, conditions, or nested functions. This keeps their order stable between renders so React associates each Hook with the right state.

<a id="qa-04-170"></a>
### 4.170. What types of values can `useState` hold?

**Interview answer:** The `useState` hook accepts different types of values. Primitives: `number`, `string`, `boolean` Arrays Objects Functions `null` or `undefined` But you needs to be cautious with reference types (objects/arrays) because React compares old and new values by reference, so direct mutations won't trigger a re-render. For example, the correct and wrong ways of state updates as shown below,.

<a id="qa-04-171"></a>
### 4.171. When should you avoid using React’s useId?

**Interview answer:** I use `useId` for stable IDs that connect accessible labels and form elements. I do not use it as a React list key, a database ID, or an ID I need to predict. List keys should come from the data.

<a id="qa-04-172"></a>
### 4.172. When should you still apply manual performance optimizations in React?

**Interview answer:** I still optimize manually when profiling finds a real bottleneck, such as a slow list, expensive calculation, or unnecessary subscription update. Even with React Compiler, I first improve component structure and data flow, then apply targeted memoization or virtualization if needed.

<a id="qa-04-173"></a>
### 4.173. Why do React Hooks make use of refs?

**Interview answer:** Earlier, refs were only limited to class components but now it can also be accessible in function components through the useRef Hook in React. The refs are used for: Managing focus, media playback, or text selection. Integrating with DOM libraries by third-party. Triggering the imperative animations.

<a id="qa-04-174"></a>
### 4.174. Why do we use array destructuring (square brackets notation) in `useState`?

**Interview answer:** `useState` returns an array containing the current state value and the setter function. Array destructuring gives them clear names, such as `const [count, setCount] = useState(0)`, instead of accessing indexes `0` and `1` manually.

<a id="qa-04-175"></a>
### 4.175. Why React tab is not showing up in DevTools?

**Interview answer:** When the page loads, React DevTools sets a global named `__REACT_DEVTOOLS_GLOBAL_HOOK__`, then React communicates with that hook during initialization. If the website is not using React or if React fails to communicate with DevTools then it won't show up the tab.

<a id="qa-04-176"></a>
### 4.176. Why use functional updates with `useState`?

**Interview answer:** `setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

<a id="qa-04-177"></a>
### 4.177. When to use a Class Component over a Function Component?

**Interview answer:** After the addition of Hooks(i.e. React 16.8 onwards) it is always recommended to use Function components over Class components in React. Because you could use state, lifecycle methods and other features that were only available in class component present in function component too. But even there are two reasons to use Class components over Function components.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-05"></a>
## 5. Performance Optimization

*69 questions — [Back to contents](#contents)*

<a id="qa-05-001"></a>
### 5.1. Can you explain a React component re-renders again and again but you never called setState. Why?

**Interview answer:** Multiple causes are possible: Parent re-render: parent's state/props changed, triggering all children to re-render Inline objects/arrays as props: {} or [] creates new reference on every render Inline functions as props: () => {} creates new function instance each render Context value changed: if consuming a Context that updates frequently Custom hook with unstable return values causing cascading updates useEffect with missing/incorrect deps triggering setState in a loop.

<a id="qa-05-002"></a>
### 5.2. When is component memoization worth using?

**Interview answer:** Memoization is helpful when a component renders frequently with the same props and the render work is expensive. I would measure performance first rather than memoize every component.

<a id="qa-05-003"></a>
### 5.3. Can you explain techniques for dynamic code splitting and lazy loading in multi-route SPAs?

**Interview answer:** Route‑based code splitting – using `React.lazy` with `Suspense`: Component‑level lazy loading – for heavy components like modals, charts, or editors: Pre‑loading – start loading a chunk before navigation using `webpackPrefetch`: Pre‑fetching on hover – trigger dynamic import when user hovers over a link. Bundler configuration – ensure chunks are named and optimized (e.g., Webpack’s `splitChunks`).

<a id="qa-05-004"></a>
### 5.4. Given a slow React tree, how do you identify and fix the performance bottleneck?

**Interview answer:** Identify: Open React DevTools Profiler, record an interaction, and look at the flame graph — it shows which components rendered and how long each took. Turn on "Highlight updates when components render" to visually spot components re-rendering more than expected. Check the Profiler's "Why did this render?" info (or add manual `console.log` in render) to find the trigger — new props, new context value, or parent re-render.

<a id="qa-05-005"></a>
### 5.5. How do you reduce the performance cost of a component that re-renders on every scroll event?

**Interview answer:** Throttle/debounce the scroll handler, or better, derive the needed value (e.g., scroll position bucket) and only call `setState` when that derived value actually changes, avoiding a state update (and render) on every pixel of scroll.

<a id="qa-05-006"></a>
### 5.6. How does `React.memo` prevent re-renders? Limitations?

**Interview answer:** `React.memo` can skip rendering a child when its props are equal to the previous props. By default it compares each prop using `Object.is`, so newly created arrays, objects, or functions can cause a re-render. It does not block updates from the component's own state or Context. I use it for components that are measurably expensive, not by default.

<a id="qa-05-007"></a>
### 5.7. How does React Context work? When can it hurt performance?

**Interview answer:** Context provides a way to pass data through the component tree without prop drilling. It works by creating a `Provider` component that holds a value. Any component that consumes the context via `useContext` will re‑render when the context value changes. Performance pitfalls: If the context value changes frequently, many consumers may re‑render.

<a id="qa-05-008"></a>
### 5.8. How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)?

**Interview answer:** Rendering 100,000+ DOM nodes at once will severely degrade performance. The key is to render only what’s visible. Virtualization / Windowing Use libraries like `react-window` or `react-virtualized`. They render only the items that fit in the viewport plus a small buffer. Example with `react-window`: This dramatically reduces DOM nodes and memory usage.

<a id="qa-05-009"></a>
### 5.9. How does React apply queued state updates on the next render?

**Interview answer:** On the next render, React processes queued updates in order and calculates the new state. Functional updates like `setCount(c => c + 1)` are useful when the next value depends on the previous one.

<a id="qa-05-010"></a>
### 5.10. How does React.memo behave when a child receives an object prop?

**Interview answer:** `React.memo` compares props shallowly. If a parent creates a new object literal on every render, the object reference changes and the child can still render. I can stabilize that object with `useMemo` when needed.

<a id="qa-05-011"></a>
### 5.11. What happens when you call a state updater function in React?

**Interview answer:** Calling a state updater queues a React state update. React then calculates the next value and schedules a render. If the new value depends on the previous one, I pass a function such as `setCount(c => c + 1)`.

<a id="qa-05-012"></a>
### 5.12. What are React Suspense and React.lazy? How do they enable code splitting?

**Interview answer:** In React, all components are bundled together and loaded at once. This can slow down the initial load, especially if the app is large. To avoid this from happening, React has an in-built feature that loads components only when they are needed, and this is called code splitting. Both React Suspense and React.lazy are used together to implement this code-splitting.

<a id="qa-05-013"></a>
### 5.13. When would you use `React.memo`?

**Interview answer:** I use `React.memo` for: Components that receive the same props often but re‑render due to parent re‑renders. Large components that are expensive to re‑render. Pure functional components that depend on props only. Avoid over‑using `memo` because the shallow prop comparison itself costs time. Use it where profiling shows a benefit.

<a id="qa-05-014"></a>
### 5.14. What is `shouldComponentUpdate`? How does it relate to `React.memo`?

**Interview answer:** `shouldComponentUpdate(nextProps, nextState)` is a class lifecycle method that can return `false` to skip an unnecessary update. For function components, `React.memo` offers a similar prop-comparison optimization, but it is not identical: a memoized function component can still re-render because of its own state or Context changes.

<a id="qa-05-015"></a>
### 5.15. What is code splitting and how does React.lazy work internally?

**Interview answer:** Code splitting breaks the JS bundle into smaller chunks loaded on demand, improving initial load time. React.lazy(import('./Component')) creates a lazy component that triggers a dynamic import() when first rendered. Suspense provides the loading fallback UI while the chunk downloads. Internally, React.lazy wraps the promise --- during render, if the promise is pending, React 'throws' it (using Suspense's error boundary mechanism), shows fallback, and resumes rendering when resolved.

<a id="qa-05-016"></a>
### 5.16. What is code splitting? How with `React.lazy`/`Suspense`?

**Interview answer:** Code splitting divides the JavaScript bundle into chunks that can load when needed. In React, I can write `const Settings = lazy(() => import('./Settings'))` and render it inside `<Suspense fallback={<Spinner />}>`. This improves initial loading when a large screen is rarely visited, but I monitor loading waterfalls and provide useful fallbacks.

**Optional coding illustration:**
```jsx
const Reports = lazy(() => import('./Reports'));
return <Suspense fallback={<p>Loading...</p>}><Reports /></Suspense>;
```

<a id="qa-05-017"></a>
### 5.17. What is route based code splitting?

**Interview answer:** Route-based code splitting loads page code only when the user visits that route. I can use lazy imports with `React.lazy` and `Suspense`, or the router’s built-in lazy-loading features, to reduce the initial bundle size.

<a id="qa-05-018"></a>
### 5.18. What is the main performance pitfall of Context?

**Interview answer:** When a Context provider's value changes, components that consume that Context can re-render even if they only care about another field. For example, putting theme and live mouse coordinates in one context can make theme consumers update constantly. I split contexts by responsibility and keep rapidly changing state close to its consumers.

<a id="qa-05-019"></a>
### 5.19. What is the purpose of Suspense beyond lazy loading?

**Interview answer:** Beyond loading lazy components, Suspense can coordinate asynchronous rendering supported by React frameworks or Suspense-aware data libraries. For example, a streaming server-rendered page can show a placeholder for a slow section while other sections appear. Suspense is not a general replacement for handling every `fetch()` request in an Effect.

<a id="qa-05-020"></a>
### 5.20. What is the React DevTools Profiler used for?

**Interview answer:** The React DevTools Profiler records which components rendered and how much time they took. I use it to find expensive commits, frequent re-renders, and components whose props change unnecessarily. Then I test targeted fixes, such as moving state down, memoization, or list virtualization, and compare the profiler results.

<a id="qa-05-021"></a>
### 5.21. When does `React.memo` NOT help?

**Interview answer:** When props include a new object/function reference every render (must pair with `useMemo`/`useCallback`), when the component is cheap to render (comparison overhead > render cost), or when props genuinely change every time anyway.

<a id="qa-05-022"></a>
### 5.22. When is useCallback useful?

**Interview answer:** `useCallback` is useful when a stable function reference prevents unnecessary child renders or helps keep dependencies stable. I do not wrap every handler in `useCallback`; I use it when profiling or component behavior shows a real benefit.

<a id="qa-05-023"></a>
### 5.23. Why does React re-render the whole component function on every update rather than patching just changed JSX?

**Interview answer:** React reruns a function component to calculate its next UI because components describe the desired result declaratively. React then reconciles that result and updates only the necessary DOM nodes; rerendering a function does not mean rebuilding the whole DOM. Expensive calculations can be memoized when profiling proves it helps.

<a id="qa-05-024"></a>
### 5.24. What is the difference between virtualization and windowing? Trade-offs?

**Interview answer:** Virtualization is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. Windowing is a specific implementation (e.g., `react-window`) that renders a “window” of items. Trade-offs: Pros: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists.

<a id="qa-05-025"></a>
### 5.25. What is the Profiler API?

**Interview answer:** `React.Profiler` wraps a tree and calls `onRender(id, phase, actualDuration, ...)` after each commit. Used to programmatically measure render performance in development. React DevTools Profiler wraps this in a UI.

<a id="qa-05-026"></a>
### 5.26. What are loadable components?

**Interview answer:** Loadable components let me split my bundle and load parts of the UI on demand. Libraries such as Loadable Components are especially useful for setups needing advanced server-side rendering support.

<a id="qa-05-027"></a>
### 5.27. Can you explain a user complains about slow UI after data load --- how would you optimize rendering and improve UX?

**Interview answer:** Slow UI after data load typically means the initial render is expensive or the data processing blocks the main thread. Profile the render: Use React DevTools Profiler to identify which component is expensive. Look for large lists, complex calculations, or deeply nested component trees. Defer heavy work: Move expensive computations to a Web Worker.

<a id="qa-05-028"></a>
### 5.28. What are React’s resource preloading APIs used for?

**Interview answer:** React DOM offers helpers such as `preload` and `preinit` that tell the browser to fetch important resources early. I would use them for a critical font, stylesheet, or script when early loading improves page performance.

<a id="qa-05-029"></a>
### 5.29. Can a re-render happen without a commit?

**Interview answer:** Yes — in concurrent mode, React can render (compute the new tree) and then discard/restart that work if interrupted by a higher-priority update, never reaching commit.

<a id="qa-05-030"></a>
### 5.30. Can you force a component to re-render without calling setState?

**Interview answer:** By default, when your component's state or props change, your component will re-render. If your `render()` method depends on some other data, you can tell React that the component needs re-rendering by calling `forceUpdate()`. It is recommended to avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`.

<a id="qa-05-031"></a>
### 5.31. What is canary deployment, and why is it useful for React apps?

**Interview answer:** A canary deployment releases a new version to a small percentage of users first. I monitor errors and performance; if things look good, I increase traffic gradually. It helps me detect problems without affecting every user at once.

<a id="qa-05-032"></a>
### 5.32. Can you explain context re-render behavior – what should you know?

**Interview answer:** Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`.

<a id="qa-05-033"></a>
### 5.33. Can you explain cSS Animation Jank: A CSS animation is janky on mobile – how to identify and fix?

**Interview answer:** Identify: Use Chrome DevTools Performance tab, record while animation runs. Look for long Layout or Paint events. If they appear during animation, the property being animated is causing layout recalculations. Enable Paint flashing and Layout Shift Regions to visualize repaints. Common causes: Animating properties that trigger layout (e.g., `width`, `height`, `top`, `left`).

<a id="qa-05-034"></a>
### 5.34. What does React Compiler do at build time?

**Interview answer:** React Compiler can analyze components at build time and automatically memoize some values and calculations. Its goal is to reduce unnecessary work while keeping component behavior the same.

<a id="qa-05-035"></a>
### 5.35. How would you deploy a React application to staging and validate it?

**Interview answer:** I build the app with staging environment settings, deploy it to a staging host or cluster, and run smoke and end-to-end tests. I also check the browser console, API connections, performance, and error tracking before approving a production release.

<a id="qa-05-036"></a>
### 5.36. Does the lazy function support named exports?

**Interview answer:** `React.lazy` expects a Promise that resolves to a module with a default component export. For a named export, I can create a small intermediate module that re-exports it as default, or map the dynamic import to a default export.

<a id="qa-05-037"></a>
### 5.37. Does a child always re-render when its parent re-renders?

**Interview answer:** A parent rendering normally causes its non-memoized child components to render too. `React.memo` can skip a child render when its props compare equal, but the child can still render because of its own state or Context updates.

<a id="qa-05-038"></a>
### 5.38. Can you explain the concept of "controlled re‑render boundaries"?

**Interview answer:** I isolate frequently changing state so unrelated components do not render with it. I can move state closer to where it is used, split large components, and use `React.memo`, `useMemo`, or `useCallback` where profiling shows a benefit.

<a id="qa-05-039"></a>
### 5.39. Can you explain follow-up: What if we set the SAME value?

**Interview answer:** If state is updated to the same value according to `Object.is`, React can skip committing a meaningful update. For example, `setOpen(false)` when `open` is already false usually does not change the UI. I still avoid assuming that a component function can never be called, because React may render before deciding whether it can bail out.

<a id="qa-05-040"></a>
### 5.40. How would you prevent re-renders in React?

**Interview answer:** I first identify which state or prop changes are causing unnecessary renders. I keep state local where possible, split large components, and apply `React.memo` or stable props when profiling shows a benefit.

<a id="qa-05-041"></a>
### 5.41. How would you re-render the view when the browser is resized?

**Interview answer:** I listen for the window `resize` event inside an Effect, update state with the dimensions I need, and remove the listener in cleanup. For responsive layout alone, I prefer CSS media queries because they avoid JavaScript work.

<a id="qa-05-042"></a>
### 5.42. How would you implement a robust frontend monitoring and logging system?

**Interview answer:** A robust system combines error tracking, performance monitoring, user analytics, and structured logging. Error tracking: Use Sentry, Rollbar, or similar. Capture JavaScript errors, unhandled promise rejections, and React error boundaries. Upload source maps to get readable stack traces. Performance monitoring: Implement Real User Monitoring (RUM) with tools like Datadog RUM, New Relic Browser, or Google Analytics with Web Vitals.

<a id="qa-05-043"></a>
### 5.43. How would you improve Web Vitals (LCP, CLS, INP)?

**Interview answer:** I improve LCP by loading the main content and hero image early, reduce CLS by reserving space for images and avoiding unexpected layout shifts, and improve INP by reducing blocking JavaScript work. I measure with Lighthouse, DevTools, and real-user Web Vitals data before optimizing.

<a id="qa-05-044"></a>
### 5.44. How would you optimize a React list with 100,000 items?

**Interview answer:** I would render only visible rows using virtualization, such as `react-window` or TanStack Virtual. I would also paginate or fetch data in chunks, use stable keys, and move expensive filtering or sorting out of urgent updates. I would verify improvements using the React Profiler.

<a id="qa-05-045"></a>
### 5.45. Is it good to use arrow functions in render methods?

**Interview answer:** Yes, You can use. It is often the easiest way to pass parameters to callback functions. But you need to optimize the performance while using it. Note: Using an arrow function in render method creates a new function each time the component renders, which may have performance implications.

<a id="qa-05-046"></a>
### 5.46. Name a few techniques to optimize React app performance?

**Interview answer:** I would start by measuring with React DevTools Profiler. Then I would optimize expensive calculations, use list virtualization for long lists, code-split large bundles, keep state local, and memoize only where it helps.

<a id="qa-05-047"></a>
### 5.47. How do you avoid a poor user experience while feature flags are loading?

**Interview answer:** I can load feature flags asynchronously and show a sensible loading state or a safe default while waiting. I avoid flashing a feature that a user should not see. Real permissions still need server-side enforcement.

<a id="qa-05-048"></a>
### 5.48. What are common React performance optimization techniques? (practical guide)?

**Interview answer:** When you are optimizing performance in React, your primary concern is to always reduce unnecessary re-renders and avoid expensive work. These optimizations should be applied only after identifying actual bottlenecks. Here are some practical ways that you can use to tackle it: 1\. Prevent unnecessary re-renders - React.memo React.memo is used to memoize a component so it only re-renders when its props change.

<a id="qa-05-049"></a>
### 5.49. What are common React performance pitfalls?

**Interview answer:** Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading.

<a id="qa-05-050"></a>
### 5.50. What happens if a child uses React.memo() and parent props don't change?

**Interview answer:** If props are truly unchanged (by shallow comparison), React.memo prevents the child from re-rendering. However, if the parent passes inline objects ({}) or inline functions (() =\> {}) as props, these create new references on every parent render --- making React.memo ineffective. Solution: wrap objects in useMemo and functions in useCallback in the parent component to maintain stable references.

<a id="qa-05-051"></a>
### 5.51. What is a selector function? Why is memoizing selectors (e.g., with `reselect`) important?

**Interview answer:** A function deriving a value from state. Memoizing avoids recomputing (and returning a new reference for) the same derived value on every call when inputs haven't changed, which would otherwise break consumer re-render optimizations.

<a id="qa-05-052"></a>
### 5.52. What is the "render props waterfall" performance risk?

**Interview answer:** Deeply nested render-prop/HOC wrapping can cause every layer to re-render together even when only the innermost data changed, since each wrapper re-renders its children as part of its own render output.

<a id="qa-05-053"></a>
### 5.53. What will happen by defining nested function components?

**Interview answer:** Technically it is possible to write nested function components but it is not suggested to write nested function definitions. Because it leads to unexpected bugs and performance issues.

<a id="qa-05-054"></a>
### 5.54. Why are keys important in lists? What happens if keys are unstable?

**Interview answer:** Keys give each element a stable identity, allowing React to match items between re‑renders. Without keys, React might reuse DOM nodes incorrectly, leading to performance issues or broken UI (e.g., lost focus, incorrect state). If keys are unstable (e.g., using index when the list can reorder), React may re‑create elements unnecessarily or mix up internal state.

<a id="qa-05-055"></a>
### 5.55. Why function is preferred over object for `setState()`?

**Interview answer:** React may batch multiple `setState()` calls into a single update for performance. Because `this.props` and `this.state` may be updated asynchronously, you should not rely on their values for calculating the next state. This counter example will fail to update as expected: The preferred approach is to call `setState()` with function rather than object.

<a id="qa-05-056"></a>
### 5.56. Why we need to pass a function to setState()?

**Interview answer:** The reason behind for this is that `setState()` is an asynchronous operation. React batches state changes for performance reasons, so the state may not change immediately after `setState()` is called. That means you should not rely on the current state when calling `setState()` since you can't be sure what that state will be. The solution is to pass a function to `setState()`, with the previous state as an argument.

<a id="qa-05-057"></a>
### 5.57. How would you improve a React application with poor SEO and slow time to interactive (TTI)?

**Interview answer:** SEO issues: - Server‑Side Rendering (SSR) or **Static Site Generation (SSG)** with frameworks like Next.js. - Ensure meta tags (title, description, Open Graph) are rendered on the server. - Use semantic HTML. Slow TTI (Time to Interactive): - Code splitting -- lazy load non‑critical components and routes. - Bundle optimization -- tree shaking, minification, remove unused dependencies. - **Reduce JavaScript** -- audit bundle size, use lightweight alternatives. - Prioritize critical CSS -- inline above‑the‑fold styles, defer non‑critical CSS. - Use `preconnect` and `preload` for important resources. - Optimize images -- use modern formats.

<a id="qa-05-058"></a>
### 5.58. What is the 'why did you render' library?

**Interview answer:** A development utility that patches React to notify you when a component re-renders due to reference-equal props/state. Helps find components where `React.memo` or `useMemo` would be beneficial.

<a id="qa-05-059"></a>
### 5.59. How does the browser rendering pipeline work?

**Interview answer:** (1) Parse HTML → DOM tree. (2) Parse CSS → CSSOM tree. (3) Combine DOM + CSSOM → Render Tree (only visible elements). (4) Layout (Reflow): calculate position/size of each element. (5) Paint: fill in pixels for each element. (6) Compositing: combine layers (GPU). Optimization: minimize reflows (expensive) by batching DOM reads/writes, use transform/opacity for animations (GPU-composited, skip layout/paint), avoid layout thrashing (alternating read-write of layout properties).

<a id="qa-05-060"></a>
### 5.60. What is windowing technique?

**Interview answer:** Windowing is a technique that only renders a small subset of your rows at any given time, and can dramatically reduce the time it takes to re-render the components as well as the number of DOM nodes created. If your application renders long lists of data then this technique is recommended.

<a id="qa-05-061"></a>
### 5.61. What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)?

**Interview answer:** CDN (Content Delivery Network) Serve static assets (JS, CSS, images) from a CDN to reduce latency for users worldwide. Use a global CDN like Cloudflare, Fastly, or AWS CloudFront. Code Splitting Split code by routes using `React.lazy` and `Suspense`. This loads only the JavaScript needed for the current page.

<a id="qa-05-062"></a>
### 5.62. When would you still manually optimize components instead of relying on React Compiler?

**Interview answer:** I still use manual memoization or careful component structure when profiling shows a performance issue, or when code is outside the React Compiler’s optimizations. I optimize measured bottlenecks rather than every component by default.

<a id="qa-05-063"></a>
### 5.63. How does React identify expensive calculations and renders?

**Interview answer:** To find expensive rendering, I would profile the app with React DevTools Profiler and browser performance tools. Then I would look for slow calculations, large lists, or repeated child renders before applying memoization or virtualization.

<a id="qa-05-064"></a>
### 5.64. How would you investigate a React performance bottleneck using DevTools?

**Interview answer:** (1) Chrome Performance tab: record user interaction, look for long tasks (>50ms) in the flame chart, identify JS evaluation and layout/paint phases. (2) React DevTools Profiler: record interactions, see which components render and their render duration, look for 'why did this render' annotation. (3) Memory tab: take heap snapshots before/after interactions to find leaks. (4) Network tab: identify slow requests, bundle sizes, caching issues. (5) Coverage tab: see unused JS/CSS bytes. Combine all for complete picture.

<a id="qa-05-065"></a>
### 5.65. What would you check first when improving an existing website’s performance?

**Interview answer:** I measure first. I check Core Web Vitals, the browser Network and Performance panels, and React DevTools Profiler to identify whether the slowdown comes from a large bundle, slow API, expensive rendering, or repeated updates. Then I optimize the biggest bottleneck and measure again.

<a id="qa-05-066"></a>
### 5.66. What are Web Vitals and why do they matter?

**Interview answer:** Core Web Vitals are Google's metrics for user experience quality: LCP (Largest Contentful Paint) — loading performance, should be < 2.5s. CLS (Cumulative Layout Shift) — visual stability, should be < 0.1. INP (Interaction to Next Paint, replaced FID) — responsiveness, should be < 200ms. Also important: FCP (First Contentful Paint), TTFB (Time to First Byte), TTI (Time to Interactive).

<a id="qa-05-067"></a>
### 5.67. How would you identify and fix a memory leak in a production React SPA?

**Interview answer:** Identification: (1) Use Chrome Memory tab — take heap snapshots, compare before/after navigation. Growing detached DOM nodes and growing listener counts are red flags. (2) Chrome Performance monitor — watch JS heap size over time. Common causes & fixes: (1) Event listeners not removed — fix with cleanup in useEffect return. (2) Timers (setInterval) not cleared — clearInterval in cleanup. (3) Stale closures holding references — review useEffect deps. (4) Unsubscribed observables/WebSockets — close in cleanup. (5) Caching without eviction — implement LRU or max-size limits.

<a id="qa-05-068"></a>
### 5.68. What is `flushSync`? When would you need it?

**Interview answer:** `flushSync` forces React to process a state update and update the DOM synchronously inside its callback. I only use it when an external browser or third-party API requires an immediate DOM change, such as measuring right after a specific synchronous action. Overusing it can hurt performance or cause a Suspense fallback to appear unexpectedly.

<a id="qa-05-069"></a>
### 5.69. What is image lazy-loading in React? How do you implement it?

**Interview answer:** Image lazy loading postpones downloading images that are outside the viewport. For ordinary images I start with the native `loading='lazy'` attribute. I preserve image dimensions to avoid layout shift and make critical above-the-fold images eager or prioritized. For custom placeholders or animations I can use `IntersectionObserver`.

---

<a id="section-06"></a>
## 6. Context API & State Management (Redux/Zustand/MobX)

*77 questions — [Back to contents](#contents)*

<a id="qa-06-001"></a>
### 6.1. Why would you use Redux instead of local component state?

**Interview answer:** Redux is useful when many distant components need coordinated updates to shared application state. For small or isolated state, local `useState` or Context may be simpler.

<a id="qa-06-002"></a>
### 6.2. Compare Redux, MobX, Recoil/Jotai, Zustand, and Context for a large-scale app?

**Interview answer:** Redux (RTK): battle-tested, best DevTools/time-travel debugging, most boilerplate (mitigated by RTK), best for large teams needing strict patterns. MobX: less boilerplate via mutable observables, can be less predictable at scale. Recoil/Jotai: atomic, fine-grained, React-native mental model, newer ecosystem. Zustand: minimal API, great performance, good for medium complexity.

<a id="qa-06-003"></a>
### 6.3. What is a container component in Redux?

**Interview answer:** A Redux container is the part of an application that reads store state and dispatches actions for presentational components. Historically, `connect()` created container components. Today I usually use `useSelector` and `useDispatch` directly in a feature component or a custom Hook. The key idea is separating state coordination from UI presentation where it improves clarity.

<a id="qa-06-004"></a>
### 6.4. Can you explain context vs Redux – when to choose which?

**Interview answer:** Context: simple, low-frequency shared state (theme, auth, locale). Redux: complex update logic, middleware (logging, side effects), time-travel debugging, large team codebases, or when you need strict action-based mutations.

<a id="qa-06-005"></a>
### 6.5. How do you handle async logic with Redux Toolkit?

**Interview answer:** For async logic, I can use `createAsyncThunk` in Redux Toolkit. It creates pending, fulfilled, and rejected actions around an async request. For API fetching with caching, RTK Query is another good option.

<a id="qa-06-006"></a>
### 6.6. How do you get redux scaffolding using create-React-app?

**Interview answer:** Older Redux projects used Create React App templates for scaffolding. Today, I would usually start with Vite or another maintained build setup, install Redux Toolkit and React Redux, create the store, and wrap the app with `<Provider store={store}>`.

<a id="qa-06-007"></a>
### 6.7. How do you manage global state? Compare Context, Redux, and modern alternatives?

**Interview answer:** So, this question is more targeted towards ways that YOU would take to manage the global state. So while I write the answer down, it’s best that you personalize it with examples that seem fit to you. Managing global state in React really depends on its scope and complexity. Most of the time, you can use ‘useState’ or ‘useReducer’, which may work well for component-specific data.

<a id="qa-06-008"></a>
### 6.8. How do you persist Redux/Zustand state across page reloads?

**Interview answer:** `redux-persist` (Redux) or Zustand's built-in `persist` middleware serialize selected state to `localStorage`/`sessionStorage` and rehydrate on load. For example, I keep a modal's open/closed value in state and pass its title through props.

<a id="qa-06-009"></a>
### 6.9. How do you test components connected to Redux/Zustand?

**Interview answer:** Wrap the component in a test-specific store instance (seeded with known state) via the real `Provider`, rather than mocking the store entirely, so the real selector/dispatch wiring is exercised.

<a id="qa-06-010"></a>
### 6.10. How does Redux Toolkit work internally?

**Interview answer:** `createSlice` uses `createReducer` and `createAction` under the hood to generate reducers and action creators. It leverages Immer to allow immutable updates with mutable syntax. `configureStore` calls Redux’s `createStore`, applies default middleware (including `redux-thunk`), and enables the Redux DevTools Extension. `createAsyncThunk` returns a thunk that dispatches the lifecycle actions automatically and allows handling of the async operation.

<a id="qa-06-011"></a>
### 6.11. How Redux Form `initialValues` get updated from state?

**Interview answer:** In the legacy `redux-form` library, `initialValues` normally initialize the form once. If incoming props change and I want the form to reset from those new values, I can use the `enableReinitialize: true` configuration. I would use this carefully because it can overwrite edits. For new applications, I would usually consider a maintained form library such as React Hook Form rather than adopting Redux Form.

<a id="qa-06-012"></a>
### 6.12. How Relay is different from Redux?

**Interview answer:** Relay is similar to Redux in that they both use a single store. The main difference is that relay only manages state originated from the server, and all access to the state is used via GraphQL queries (for reading data) and mutations (for changing data). Relay caches the data for you and optimizes data fetching for you, by fetching only changed data and nothing more.

<a id="qa-06-013"></a>
### 6.13. How do you configure a Redux Toolkit store?

**Interview answer:** I use Redux Toolkit's `configureStore({ reducer: { users: usersReducer, auth: authReducer } })` to assemble the application store. It includes helpful middleware and Redux DevTools integration by default. Then I wrap the app with React Redux's `<Provider store={store}>` so components can use selectors and dispatch actions.

<a id="qa-06-014"></a>
### 6.14. How would you reset state in Redux?

**Interview answer:** For logout or reset, I can handle a dedicated action in the root reducer and return the initial state for the whole application or selected slices. I also clear any persisted sensitive state that should not survive the logout.

<a id="qa-06-015"></a>
### 6.15. How should you organize a Redux application?

**Interview answer:** I organize Redux code by feature, not by separating all actions and reducers into unrelated folders. For example, `features/users/usersSlice.ts` contains state and reducers, while nearby files contain selectors and API logic. Redux Toolkit's `createSlice` reduces boilerplate. This structure keeps related behavior together as the app grows.

<a id="qa-06-016"></a>
### 6.16. How does connect() work in React Redux, and what is the modern alternative?

**Interview answer:** `connect()` is the traditional React-Redux higher-order component. I would define `mapStateToProps` to select state and `mapDispatchToProps` for actions, then wrap the component with `connect()`. Today, I usually prefer `useSelector` and `useDispatch` in function components.

<a id="qa-06-017"></a>
### 6.17. How do you define a Redux Toolkit slice?

**Interview answer:** I call `createSlice` with a name, initial state, and reducers. Redux Toolkit then creates the reducer and action creators automatically. I can add `extraReducers` to handle actions from async thunks.

<a id="qa-06-018"></a>
### 6.18. Why is immutability important in Redux state updates?

**Interview answer:** Redux reducers should treat existing state as immutable and return the next state instead of modifying the old object directly. This makes updates predictable and easier to debug. Redux Toolkit uses Immer to make immutable updates simpler.

<a id="qa-06-019"></a>
### 6.19. How do you dispatch an action created by Redux Toolkit?

**Interview answer:** A Redux Toolkit slice creates action creators for each reducer. I can import one of those actions and call `dispatch(increment())` inside an event handler to update the store.

<a id="qa-06-020"></a>
### 6.20. How is Redux different from the React Context API?

**Interview answer:** Context is React's built-in way to provide a value to descendants without passing props through every layer. Redux is a separate state-management library with a central store, reducers, middleware, selectors, and debugging tools. I use Context for simple shared values such as theme and Redux Toolkit when many features need complex shared updates.

<a id="qa-06-021"></a>
### 6.21. Should I keep all component's state in Redux store?

**Interview answer:** No. I keep temporary UI state close to its component when it is only needed locally, such as a dropdown being open or a draft input value. I put state in Redux when multiple features need to coordinate updates or share a single source of truth. Storing everything globally makes an app harder to understand and can create unnecessary updates.

<a id="qa-06-022"></a>
### 6.22. What are Redux selectors and why use them?

**Interview answer:** Selectors are functions that take Redux state as an argument and return some data to pass to the component. For example, to get user details from the state: These selectors have two main benefits, The selector can compute derived data, allowing Redux to store the minimal possible state The selector is not recomputed unless one of its arguments changes.

<a id="qa-06-023"></a>
### 6.23. What are the advantages of formik over redux form library?

**Interview answer:** Formik keeps form values, validation, and submission handling close to the form instead of putting temporary input state in Redux. This usually reduces coupling and global-store updates. React Hook Form is another common option.

<a id="qa-06-024"></a>
### 6.24. What are the three main principles of Redux?

**Interview answer:** Redux follows three main ideas: one store is the central source of application state, state is read-only from the outside so changes happen through dispatched actions, and reducers calculate the next state with pure functions. In modern projects I use Redux Toolkit to implement these rules with less boilerplate and safer immutable updates.

<a id="qa-06-025"></a>
### 6.25. What are the differences between `call()` and `put()` in redux-saga?

**Interview answer:** In Redux-Saga, `call` describes an async function call that the saga middleware should execute. `put` describes dispatching an action to the Redux store. A common flow is to `call` an API and then `put` a success or failure action.

<a id="qa-06-026"></a>
### 6.26. How are Redux and MobX different as state-management approaches?

**Interview answer:** Redux uses actions and reducers to update mostly immutable state in a predictable flow. MobX uses observable values and automatically reacts when those values change. I choose based on the team’s preference for explicit updates versus automatic reactivity.

<a id="qa-06-027"></a>
### 6.27. What is middleware in Redux? Example?

**Interview answer:** Redux middleware runs between dispatching an action and reaching the reducer. It can handle logging, async requests, or cross-cutting behavior without putting side effects into reducers. For example, Redux Thunk lets an action creator run an API request and dispatch success or failure actions. Redux Toolkit configures useful middleware by default.

<a id="qa-06-028"></a>
### 6.28. What is Redux and why is it used?

**Interview answer:** Redux is a predictable state container: single source of truth (one global store), state is read-only (only changed by dispatching actions), changes via pure reducer functions. Benefits for large apps: predictable state transitions, easy debugging (Redux DevTools time-travel), centralized state logic, middleware for async operations, testable reducers.

<a id="qa-06-029"></a>
### 6.29. What is Redux Toolkit, and why is it recommended?

**Interview answer:** Redux Toolkit is the recommended way to write Redux. It reduces boilerplate with `configureStore` and `createSlice`, uses Immer for simpler immutable updates, and includes RTK Query for data fetching and caching. I use it when shared state becomes too complex for local state and Context alone.

**Optional coding illustration:**
```jsx
const counterSlice = createSlice({
  name: 'counter', initialState: { value: 0 },
  reducers: { increment: state => { state.value += 1; } }
});
```

<a id="qa-06-030"></a>
### 6.30. What is the Context API? When should you use it instead of prop drilling?

**Interview answer:** Prop drilling is the pattern of passing on data from the parent component through several levels down to the nested child component, but its process makes the code harder to maintain and debug. To avoid such problems, Context API, which is a built-in feature in React, helps in passing on the data, but without having to go through every level.

<a id="qa-06-031"></a>
### 6.31. What is the difference between Context API and Redux Toolkit?

**Interview answer:** Context API: built-in React, no extra library, ideal for low-frequency updates (theme, locale, auth user). Limitation: any context value change re-renders all consumers — bad for high-frequency state. Redux Toolkit: external library, single global store with selectors — components only re-render when their specific slice changes. Better for: complex state, frequent updates, time-travel debugging, multiple teams.

<a id="qa-06-032"></a>
### 6.32. What is Zustand and how does it differ from Redux?

**Interview answer:** A minimal hook-based store with no reducers/actions boilerplate — plain objects with setter functions; components subscribe to specific slices, avoiding unnecessary re-renders, with a much smaller API surface than Redux.

<a id="qa-06-033"></a>
### 6.33. When should you use Context vs. Redux/Zustand?

**Interview answer:** Context: simple, low-frequency shared values (theme, auth user, locale). Redux/Zustand: complex update logic, frequent updates, middleware needs, or when many unrelated consumers must avoid re-rendering on unrelated state changes.

<a id="qa-06-034"></a>
### 6.34. Where and why have you used Redux Toolkit in your projects?

**Interview answer:** Common scenarios: Large‑scale apps with complex shared state: Shopping carts, user authentication, multi‑step forms. Real‑time dashboards: To manage data from WebSockets across many components. Apps with complex async flows: To maintain loading/error states in a consistent manner. When multiple features need access to the same data: E.g., user profile, preferences, notifications.

<a id="qa-06-035"></a>
### 6.35. Can Redux only be used with React?

**Interview answer:** Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. Redux simply provides a subscription mechanism which can be used by any other code.

<a id="qa-06-036"></a>
### 6.36. Can you explain careful selection of complementary packages?

**Interview answer:** Redux is more minimal by design and provides extension points such as middleware and store enhancers. This has led to a large ecosystem, but it also means you must thoughtfully choose and configure additional packages for features like undo/redo, persistence, or form handling—something Flux explicitly leaves out but may be simpler to manage in smaller setups.

<a id="qa-06-037"></a>
### 6.37. What is a presentational component in Redux?

**Interview answer:** A presentational component mainly receives props and displays the UI. It does not need to know where global state comes from. This makes it easier to reuse and test.

<a id="qa-06-038"></a>
### 6.38. Do I need to keep all my state into Redux? Should I ever use React internal state?

**Interview answer:** It is up to the developer's decision, i.e., it is developer's job to determine what kinds of state make up your application, and where each piece of state should live. Some users prefer to keep every single piece of data in Redux, to maintain a fully serializable and controlled version of their application at all times. Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, inside a component's internal state.

<a id="qa-06-039"></a>
### 6.39. Do you need to have a particular build tool to use Redux?

**Interview answer:** Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. You should be able to use it regardless of your JavaScript build process. Redux also offers a UMD build that can be used directly without any build process at all.

<a id="qa-06-040"></a>
### 6.40. How would you access Redux store outside a component?

**Interview answer:** You just need to export the store from the module where it created with `createStore()`. Also, it shouldn't pollute the global window object.

<a id="qa-06-041"></a>
### 6.41. What are the trade-offs of static typing in Flux-style and Redux applications?

**Interview answer:** Static types help detect mistakes in action payloads and state shapes before runtime. Modern Redux Toolkit has strong TypeScript support, so I would choose based on maintainability rather than assume Redux cannot be typed.

<a id="qa-06-042"></a>
### 6.42. Give an example of Reselect usage?

**Interview answer:** Reselect creates memoized selectors for Redux. For example, a selector can calculate the total value of items in a cart and reuse its previous result when the input state has not changed. That avoids repeating an expensive calculation after unrelated updates.

<a id="qa-06-043"></a>
### 6.43. Explain reducers and extraReducers – when to use each?

**Interview answer:** `reducers`: Used for actions that are directly handled by this slice. RTK automatically generates action creators with the same names. Good for synchronous, slice‑specific updates. `extraReducers`: Used to respond to actions defined elsewhere (e.g., thunks, actions from other slices). It’s often used with `builder` callback to handle `pending`, `fulfilled`, `rejected` of async thunks.

<a id="qa-06-044"></a>
### 6.44. What are the downsides of Redux compared to Flux?

**Interview answer:** Redux puts state in one predictable store and changes it through actions and pure reducers. That structure helps debugging but can add boilerplate or complexity compared with simpler Flux-style or local-state solutions. I choose it when the app actually needs shared state management.

<a id="qa-06-045"></a>
### 6.45. What are the features of Redux DevTools?

**Interview answer:** Redux DevTools shows dispatched actions, state changes, and the order in which updates happened. I use it to debug unexpected state changes and replay actions when investigating a bug.

<a id="qa-06-046"></a>
### 6.46. What are the main features of Redux Form?

**Interview answer:** Some of the main features of Redux Form are: Field values persistence via Redux store. Validation (sync/async) and submission. Formatting, parsing and normalization of field values.

<a id="qa-06-047"></a>
### 6.47. How do you avoid unnecessary re-renders with `useSelector`?

**Interview answer:** I make Redux `useSelector` select the smallest state value a component needs. Returning a new object from a selector on every store update can trigger extra renders, so I use memoized selectors with Reselect or `shallowEqual` where appropriate. I profile before adding memoization, because narrow primitive selectors are often enough.

<a id="qa-06-048"></a>
### 6.48. What are the main features of Reselect library?

**Interview answer:** Let's see the main features of Reselect library, Selectors can compute derived data, allowing Redux to store the minimal possible state. Selectors are efficient. A selector is not recomputed unless one of its arguments changes. Selectors are composable. They can be used as input to other selectors.

<a id="qa-06-049"></a>
### 6.49. What are typical middleware choices for handling asynchronous calls in Redux?

**Interview answer:** Some of the popular middleware choices for handling asynchronous calls in Redux eco system are `Redux Thunk, Redux Promise, Redux Saga`.

<a id="qa-06-050"></a>
### 6.50. What is an action in Redux?

**Interview answer:** *Actions* are plain JavaScript objects or payloads of information that send data from your application to your store. They are the only source of information for the store. Actions must have a type property that indicates the type of action being performed. For example, let's take an action which represents adding a new todo item.

<a id="qa-06-051"></a>
### 6.51. What is createAsyncThunk() and why is it used?

**Interview answer:** createAsyncThunk handles async operations (API calls) in Redux. It takes an action type string and an async payload creator function. It automatically dispatches three action types: actionName/pending (loading), actionName/fulfilled (success with data), actionName/rejected (error). Handle these in extraReducers with builder.addCase().

<a id="qa-06-052"></a>
### 6.52. What is Jotai and how does the atomic model work?

**Interview answer:** Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

<a id="qa-06-053"></a>
### 6.53. What is MobX?

**Interview answer:** MobX is a simple, scalable and battle tested state management solution for applying functional reactive programming (TFRP). For React application, you need to install below packages,.

<a id="qa-06-054"></a>
### 6.54. What is Recoil/Jotai? What problem do atom-based libraries solve?

**Interview answer:** Atom-based state libraries such as Jotai model state as small independent pieces called atoms. Components subscribe to the atoms they actually use, so unrelated updates can avoid extra re-renders. This can be useful when a large shared state has many independently changing values. The API and maintenance trade-offs depend on the library.

<a id="qa-06-055"></a>
### 6.55. What is Redux Form?

**Interview answer:** Redux Form works with React and Redux to enable a form in React to use Redux to store all of its state. Redux Form can be used with raw HTML5 inputs, but it also works very well with common UI frameworks like Material UI, React Widgets and React Bootstrap.

<a id="qa-06-056"></a>
### 6.56. What is Redux Thunk vs Redux Saga?

**Interview answer:** Thunk: action creators return functions (`dispatch`, `getState` access) for simple async logic using Promises — simple, minimal API. Saga: generator-based middleware for complex async flows (cancellation, race conditions, sequencing) — more powerful, steeper learning curve.

<a id="qa-06-057"></a>
### 6.57. What is Redux Thunk?

**Interview answer:** Redux Thunk middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch()` and `getState()` as parameters.

<a id="qa-06-058"></a>
### 6.58. What is redux-saga?

**Interview answer:** `redux-saga` is a library that aims to make side effects (asynchronous things like data fetching and impure things like accessing the browser cache) in React/Redux applications easier and better. It is available in NPM.

<a id="qa-06-059"></a>
### 6.59. What is Redux?

**Interview answer:** Redux is a predictable global state-management library. Components dispatch actions, reducers calculate the next state, and the store holds the application state. Today, I usually write Redux using Redux Toolkit to avoid repetitive boilerplate.

<a id="qa-06-060"></a>
### 6.60. What is the "single source of truth" principle in state management?

**Interview answer:** Each piece of data should have exactly one authoritative place it lives; everything else derives from or references it, avoiding sync bugs from duplicated copies.

<a id="qa-06-061"></a>
### 6.61. What is the `useSelector` / `useDispatch` pattern in Redux?

**Interview answer:** useSelector is for reading data. It lets your component "grab" a specific piece of state from the global Redux store useDispatch is for changing data. It gives you a dispatch function. You use this function to send "actions" (requests) to the Redux store telling it to update the data.

<a id="qa-06-062"></a>
### 6.62. What is the difference between global state and server state (cache)?

**Interview answer:** Global state (UI preferences, auth) is owned entirely by the client. Server state (fetched API data) is actually owned by the server and the client just holds a cached, possibly-stale copy — better managed by a data-fetching library (React Query) than a generic state store.

<a id="qa-06-063"></a>
### 6.63. What is the flux architecture pattern?

**Interview answer:** Unidirectional data flow: Action → Dispatcher → Store → View → (user interaction) → Action. Redux is inspired by Flux. Data always flows one way, making state changes predictable and traceable.

<a id="qa-06-064"></a>
### 6.64. What is the mental model of redux-saga?

**Interview answer:** Saga is like a separate thread in your application, that's solely responsible for side effects. `redux-saga` is a redux middleware, which means this thread can be started, paused and cancelled from the main application with normal Redux actions, it has access to the full Redux application state and it can dispatch Redux actions as well.

<a id="qa-06-065"></a>
### 6.65. What is the proper way to access Redux store?

**Interview answer:** The best way to access your store in a component is to use the `connect()` function, that creates a new component that wraps around your existing one. This pattern is called Higher-Order Components, and is generally the preferred way of extending a component's functionality in React. This allows you to map state and action creators to your component, and have them passed in automatically as your store updates.

<a id="qa-06-066"></a>
### 6.66. What is the purpose of the constants in Redux?

**Interview answer:** Constants allows you to easily find all usages of that specific functionality across the project when you use an IDE. It also prevents you from introducing silly bugs caused by typos – in which case, you will get a `ReferenceError` immediately. Normally we will save them in a single file (`constants.js` or `actionTypes.js`). In Redux, you use them in two places.

<a id="qa-06-067"></a>
### 6.67. What is the use of the `ownProps` parameter in `mapStateToProps()` and `mapDispatchToProps()`?

**Interview answer:** If the `ownProps` parameter is specified, React Redux will pass the props that were passed to the component into your connect functions. So, if you use a connected component: The `ownProps` inside your `mapStateToProps()` and `mapDispatchToProps()` functions will be an object: You can use this object to decide what to return from those functions.

<a id="qa-06-068"></a>
### 6.68. What problems does Redux solve in large React applications?

**Interview answer:** State sharing: Avoids prop drilling for deeply nested components. Predictability: State changes happen via pure reducers, making it easier to debug with time‑travel. Separation of concerns: UI logic is decoupled from state management. Middleware: Enables handling side effects (async actions, logging) in a structured way. DevTools: Excellent debugging capabilities.

<a id="qa-06-069"></a>
### 6.69. Whats the purpose of `at` symbol in the Redux connect decorator?

**Interview answer:** The `@` syntax indicates a decorator in toolchains that support decorators. Older React Redux examples used it to wrap class components with `connect`. In modern code, I generally prefer `useSelector` and `useDispatch` instead.

<a id="qa-06-070"></a>
### 6.70. How would you provide feature flags throughout a React application?

**Interview answer:** I can place a feature-flag provider near the app root and read flags through Context or a custom Hook. Components then show or hide features based on flags. Sensitive access rules must still be enforced by the server.

<a id="qa-06-071"></a>
### 6.71. When would you decide NOT to use Redux and choose a simpler solution?

**Interview answer:** Redux adds complexity. I would choose a simpler alternative when: The app is small or has limited state: If state is mostly local, React’s `useState`/`useReducer` + context is sufficient. State updates are simple and infrequent: For example, a form‑driven app with little cross‑component communication. The team is unfamiliar with Redux patterns: Introducing it would slow development.

<a id="qa-06-072"></a>
### 6.72. Why are Redux state functions called reducers?

**Interview answer:** Reducers always return the accumulation of the state (based on all previous and current actions). Therefore, they act as a reducer of state. Each time a Redux reducer is called, the state and action are passed as parameters. This state is then reduced (or accumulated) based on the action, and then the next state is returned. You could reduce a collection of actions and an initial state (of the store) on which to perform these actions to get the resulting final state.

<a id="qa-06-073"></a>
### 6.73. What is reselect and how it works?

**Interview answer:** *Reselect* is a selector library (for Redux) which uses *memoization* concept. It was originally written to compute derived data from Redux-like applications state, but it can't be tied to any architecture or library. Reselect keeps a copy of the last inputs/outputs of the last call, and recomputes the result only if one of the inputs changes.

<a id="qa-06-074"></a>
### 6.74. What is createSlice() and what does it contain?

**Interview answer:** createSlice() accepts: name (action type prefix), initialState, reducers object (sync action handlers), and extraReducers (async thunk handlers). It auto-generates: action creators (slice.actions.actionName), action types (slice.name/actionName), and the reducer function. Reducers inside createSlice can mutate state directly because RTK uses Immer under the hood — Immer converts mutations into immutable updates.

<a id="qa-06-075"></a>
### 6.75. What is the Provider hell problem, and how do you avoid it?

**Interview answer:** Deeply nesting many separate Context Providers at the app root (`<A><B><C><D>`) becomes unreadable. Avoid by composing providers into a single wrapper component, or combining related, co-changing contexts into one.

<a id="qa-06-076"></a>
### 6.76. Can you explain the Redux Toolkit flow?

**Interview answer:** (1) createSlice() defines state shape, reducers (sync), and generates action creators. (2) configureStore() combines slices into the global store, auto-adds DevTools and middleware. (3) createAsyncThunk() handles async operations — dispatches pending/fulfilled/rejected actions. (4) extraReducers handles async thunk lifecycle in slices. (5) Components use useSelector() to read state and useDispatch() to send actions. (6) Store notifies all subscribers on state change, React re-renders connected components.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-06-077"></a>
### 6.77. How does async flow work in Redux Toolkit?

**Interview answer:** Define a thunk using `createAsyncThunk`. Inside the payload creator, perform async work (e.g., fetch). Dispatch the thunk from a component. The thunk dispatches the `pending` action immediately. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-07"></a>
## 7. Routing & Navigation

*32 questions — [Back to contents](#contents)*

<a id="qa-07-001"></a>
### 7.1. What do useParams, useNavigate and useSearchParams do in React Router?

**Interview answer:** `useParams` reads dynamic path segments. `useNavigate` programmatically navigates. `useSearchParams` reads/writes the query string. The backend still needs to authorize requests even if the UI hides or redirects a route.

<a id="qa-07-002"></a>
### 7.2. How do you prevent open redirect vulnerabilities in a React Router app (e.g., a `?redirect=` query param)?

**Interview answer:** Validate that the redirect target is a relative, same-origin path (not an arbitrary external URL) before calling `navigate()`/`window.location`, rejecting or ignoring untrusted absolute URLs. The backend still needs to authorize requests even if the UI hides or redirects a route.

<a id="qa-07-003"></a>
### 7.3. How do you test a component with React Router routes?

**Interview answer:** Wrap it in `<MemoryRouter initialEntries={['/some/path']}>` to simulate a specific URL without a real browser, then assert on rendered route content or navigation behavior. The backend still needs to authorize requests even if the UI hides or redirects a route.

<a id="qa-07-004"></a>
### 7.4. How React Router is different from history library?

**Interview answer:** React Router is a wrapper around the `history` library which handles interaction with the browser's `window.history` with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node.

<a id="qa-07-005"></a>
### 7.5. How can data be passed between routes in React Router?

**Interview answer:** For a value needed on the next page, I can pass navigation state or URL parameters in React Router. For long-lived shared data, Context or a store is more reliable than passing it through multiple routes.

<a id="qa-07-006"></a>
### 7.6. What are nested routes in React Router v6?

**Interview answer:** Child `<Route>` elements inside a parent `<Route>`. The parent renders an `<Outlet/>` where child content appears. Enables layouts where outer shell (nav, sidebar) persists and inner content changes with URL.

<a id="qa-07-007"></a>
### 7.7. What are route actions in React Router?

**Interview answer:** Functions that handle form submissions and mutations on a route. Called when a Form is submitted to that route. Work with React Router's data APIs for full progressive enhancement.

<a id="qa-07-008"></a>
### 7.8. What are route loaders in React Router v6.4+?

**Interview answer:** Functions defined on routes that fetch data before the component renders. The component receives data via `useLoaderData()`. Eliminates loading spinners inside components -- data is ready before render.

<a id="qa-07-009"></a>
### 7.9. What are the `<Router>` components of React Router v6?

**Interview answer:** React Router v6 provides below 4 `<Router>` components: `<BrowserRouter>`:Uses the HTML5 history API for standard web apps. `<HashRouter>`:Uses hash-based routing for static servers. `<MemoryRouter>`:Uses in-memory routing for testing and non-browser environments. `<StaticRouter>`:Provides static routing for server-side rendering (SSR).

<a id="qa-07-010"></a>
### 7.10. What is client-side routing? How does it differ from server routing?

**Interview answer:** Client-side routing updates which page component is displayed without requiring a full document reload for every route. React Router uses browser history and route matching for navigation. The server must still serve the application shell on direct visits to clean URLs, and route guards in the browser are not a substitute for backend authorization.

<a id="qa-07-011"></a>
### 7.11. What is React Router and what are its main components?

**Interview answer:** React Router connects URLs to UI. I declare routes with `<Routes>` and `<Route>` in declarative mode, navigate with `<Link>` or `useNavigate`, read parameters with `useParams`, and render nested routes through `<Outlet>`. Its Data and Framework modes also support loaders and actions. I match the APIs to the Router version and mode used by the project.

**Optional coding illustration:**
```jsx
<BrowserRouter>
  <Routes><Route path="/users/:id" element={<UserPage />} /></Routes>
</BrowserRouter>
```

<a id="qa-07-012"></a>
### 7.12. What is route matching precedence in React Router v6?

**Interview answer:** V6 uses a ranking algorithm based on specificity (static segments rank higher than dynamic `:param` segments, which rank higher than wildcards) rather than "first match wins" order.

<a id="qa-07-013"></a>
### 7.13. What is the difference between `Router` and `Link` in React Router?

**Interview answer:** `Router` (e.g., `BrowserRouter`): Provides the routing context and handles history management. It is the parent component that enables navigation and URL sync. `Link`: A component that renders an anchor (`<a>`) with the `to` prop. It allows navigation without a full page reload, using client‑side routing.

<a id="qa-07-014"></a>
### 7.14. How do you define nested routes (v6+)?

**Interview answer:** In React Router, I nest child routes inside a parent route and place `<Outlet />` in the parent's component to display the matched child. For example, a dashboard layout can render shared navigation while nested `/dashboard/reports` and `/dashboard/users` routes render inside the Outlet. This avoids duplicating layout code.

<a id="qa-07-015"></a>
### 7.15. How do you implement a layout route (shared header/sidebar across multiple pages)?

**Interview answer:** I define a parent layout route that renders the common header, sidebar, and an `<Outlet />`. The child routes appear in that Outlet while the shared layout remains mounted. This pattern is useful for dashboards with multiple pages because it centralizes navigation and avoids rebuilding the same layout in each page.

<a id="qa-07-016"></a>
### 7.16. How do you implement protected/private routes?

**Interview answer:** A protected route checks the user's authentication state and shows the page or navigates to login. In React Router I may wrap the route element or use a route loader to redirect before rendering. This protects the user experience, but the backend must independently validate the session and enforce authorization for every API request.

<a id="qa-07-017"></a>
### 7.17. What is the difference between BrowserRouter and HashRouter?

**Interview answer:** `BrowserRouter` uses clean URLs via History API (needs server config for refresh). `HashRouter` uses `#` fragments, never hitting the server, zero config but less clean.

<a id="qa-07-018"></a>
### 7.18. How do you redirect after a successful form submission/mutation?

**Interview answer:** Call `navigate('/success')` imperatively after the async action resolves, or return a `redirect()` response from a route action (data API), which React Router handles automatically.

<a id="qa-07-019"></a>
### 7.19. How does client-side routing work?

**Interview answer:** A router library (React Router, TanStack Router) listens to the browser history API (`pushState`, `popstate`) and renders different components based on the current URL – without full page reloads.

<a id="qa-07-020"></a>
### 7.20. How is React different from Angular or Vue?

**Interview answer:** React: View library, uses JSX + JS composition, lightweight. Angular: Full framework with DI, routing, forms built-in, uses TypeScript + decorators + templates. Vue: Sits between React and Angular, uses SFC (Single File Components), more approachable than Angular but more opinionated than React.

<a id="qa-07-021"></a>
### 7.21. What is the difference between `useNavigate` and `<Navigate>`?

**Interview answer:** `useNavigate()` returns an imperative function for programmatic navigation (after form submit, in event handlers). `<Navigate>` is a component that redirects declaratively as part of JSX render output.

**Optional coding illustration:**
```jsx
const navigate = useNavigate();
<button onClick={() => navigate('/dashboard')}>Continue</button>
```

<a id="qa-07-022"></a>
### 7.22. How do you pass state through navigation without putting it in the URL?

**Interview answer:** I can pass navigation state with `navigate('/checkout', { state: { fromCart: true } })` and read it in the destination using `useLocation().state`. It is useful for temporary navigation context, not critical or secret data. It is not encoded in the URL, and it is not a dependable source of truth for direct visits or all navigation histories.

<a id="qa-07-023"></a>
### 7.23. How do you protect routes (auth guards)?

**Interview answer:** In the loader, check auth status and redirect if not authenticated. Or create a `RequireAuth` wrapper component that checks auth state and renders `<Navigate to='/login'/>` if not authenticated.

<a id="qa-07-024"></a>
### 7.24. How do you prevent navigation away from a page with unsaved changes?

**Interview answer:** For unsaved changes I first track whether the form is dirty. In a React Router data-router setup, I can use a navigation blocker to display a confirmation dialog for in-app navigation. I may also use `beforeunload` for browser close or refresh, understanding that browser support and messaging are limited. I do not assume the blocker protects against data loss without saving drafts.

<a id="qa-07-025"></a>
### 7.25. What are search params and how do you use them?

**Interview answer:** URL query string parameters (`?tab=settings&page=2`). `useSearchParams()` returns `[searchParams, setSearchParams]`. Use as UI state (tab, filter, page) so users can share/bookmark specific views.

<a id="qa-07-026"></a>
### 7.26. What are loaders and actions (v6.4+ data APIs)?

**Interview answer:** A React Router loader fetches data for a route before its UI is rendered, and the component reads the result with `useLoaderData`. An action handles a route mutation, often submitted through `<Form>`, and can return errors or redirect. These APIs belong to React Router's Data/Framework modes, not every Router setup.

<a id="qa-07-027"></a>
### 7.27. What is `<NavLink>`? How does it differ from `<Link>`?

**Interview answer:** Same as `<Link>` but automatically applies an "active" styling/class when its `to` matches the current URL, useful for nav menus.

<a id="qa-07-028"></a>
### 7.28. What is the purpose of `push()` and `replace()` methods of `history`?

**Interview answer:** A history instance has two methods for navigation purpose. `push()` `replace()` If you think of the history as an array of visited locations, `push()` will add a new location to the array and `replace()` will replace the current location in the array with the new one.

<a id="qa-07-029"></a>
### 7.29. How do you programmatically navigate using React Router v4?

**Interview answer:** In React Router v4, programmatic navigation was usually done through the `history` object, such as `history.push("/profile")`. In React Router v6, I use the `useNavigate` Hook instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-07-030"></a>
### 7.30. How would you get query parameters in React Router v4?

**Interview answer:** In React Router v4, the query string is available in `location.search`, and I can parse it using `URLSearchParams` or a query-string library. In React Router v6, I normally use `useSearchParams` instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-07-031"></a>
### 7.31. What are the benefits of React Router V4?

**Interview answer:** React Router v4 moved toward component-based routing with APIs such as `BrowserRouter`, `Route`, and `Switch`. It allowed routes to be declared alongside UI. For modern projects, I would use React Router v6 or newer APIs rather than copy v4 syntax.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-07-032"></a>
### 7.32. How did routing syntax change from React Router v5 to v6?

**Interview answer:** That warning belongs to older React Router APIs. In React Router v5, `Switch` selected the first matching route. In React Router v6, `Routes` replaces `Switch`, and each child route normally uses an `element` prop.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-08"></a>
## 8. Forms & Controlled Components

*14 questions — [Back to contents](#contents)*

<a id="qa-08-001"></a>
### 8.1. How do you do form validation in React without a library?

**Interview answer:** Without a library, I keep field values and error messages in state, validate required fields and formats when the user submits or blurs an input, and display clear errors next to the relevant fields. I also validate on the server because browser validation can be bypassed. For large forms with many fields, a library can reduce repetitive code.

<a id="qa-08-002"></a>
### 8.2. What is Formik?

**Interview answer:** Formik is a React form library that manages field values, touched state, submission, and validation. I can connect it to a schema validator such as Yup. It is useful for existing applications or teams that already use Formik; I would also compare React Hook Form for performance and API fit in a new project.

<a id="qa-08-003"></a>
### 8.3. What is the popular choice for form handling?

**Interview answer:** There is no single required React form library. React Hook Form is a common choice for larger client-side forms because it minimizes unnecessary re-renders and works well with schema validators such as Zod. Formik is also widely used. For a small form, ordinary controlled inputs or React 19 form Actions may be simpler.

<a id="qa-08-004"></a>
### 8.4. How do you build a controlled form in React?

**Interview answer:** In a controlled form, the input value comes from React state, and its `onChange` handler updates that state. For example, `const [name, setName] = useState('')` with `<input value={name} onChange={e => setName(e.target.value)} />`. This makes validation and conditional UI easier, although every keystroke causes a state update.

<a id="qa-08-005"></a>
### 8.5. How would you prevent a function from being called multiple times?

**Interview answer:** I use debouncing when I want to wait until repeated events stop, such as search typing. I use throttling when I want to limit the maximum frequency of calls, such as scroll or resize handling.

<a id="qa-08-006"></a>
### 8.6. What is a factory/builder pattern for creating typed, reusable form field components?

**Interview answer:** A function that generates a pre-configured, typed field component bound to a specific form library/schema (e.g., `createFormField<FormValues>()`), reducing repetitive boilerplate across many similar fields while preserving type safety.

<a id="qa-08-007"></a>
### 8.7. What is the difference between `onChange` and `onInput` in React forms?

**Interview answer:** React's `onChange` fires on every value change (behaving like the native `input` event), unlike the native DOM `change` event which only fires on blur/commit — React normalizes this for consistency.

<a id="qa-08-008"></a>
### 8.8. How do you handle a form submit without refreshing the page?

**Interview answer:** In a traditional controlled React form, I handle `onSubmit`, call `event.preventDefault()`, validate the input, and submit the data using `fetch` or a mutation Hook. I show pending, success, and error states. In React 19, a `<form action={someAction}>` can also handle submission through an Action without the old manual handler pattern.

**Optional coding illustration:**
```jsx
function handleSubmit(e) { e.preventDefault(); save({ email }); }
<form onSubmit={handleSubmit}><button type="submit">Save</button></form>
```

*Added to improve practical form interview coverage.*

<a id="qa-08-009"></a>
### 8.9. How do you prevent a user from submitting the same form twice?

**Interview answer:** I track whether the request is pending, disable or guard the submit action while it runs, and show the user progress. For a React 19 form Action I can read pending state with `useFormStatus` from a child component. The server should also make critical operations idempotent, because disabling a browser button is not enough to prevent duplicate requests.

*Added to improve practical form interview coverage.*

<a id="qa-08-010"></a>
### 8.10. How do you show validation errors accessibly?

**Interview answer:** I show a clear error next to each field, connect it to the input using `aria-describedby`, and mark invalid fields with `aria-invalid`. On submit, I move focus to the first invalid field or an error summary. I avoid relying on color alone and keep server-side validation errors visible too.

*Added to improve practical form interview coverage.*

<a id="qa-08-011"></a>
### 8.11. How do you upload a file from a React form?

**Interview answer:** I use `<input type='file'>` to let the user select a file and read the chosen `File` from the input. I usually send it as `FormData` using `fetch` or a suitable upload client. I validate file type and size in the UI for usability, but the server must validate and securely store the file as well.

*Added to improve practical form interview coverage.*

<a id="qa-08-012"></a>
### 8.12. How do you handle checkbox and select values in a controlled form?

**Interview answer:** For a checkbox I control its `checked` property and update state from `event.target.checked`. For a select I control `value` and read `event.target.value`. I use `value` for text and select fields, but not for a checkbox's boolean state. This avoids common bugs caused by treating every input identically.

*Added to improve practical form interview coverage.*

<a id="qa-08-013"></a>
### 8.13. How would you handle dependent fields in a large form?

**Interview answer:** I keep related form data in one predictable model, derive options from the selected values, and reset dependent fields when their parent field changes. For example, choosing a country can change the list of available states. I avoid storing duplicated derived values when they can be calculated, and I use a form library when repeated dynamic fields become hard to maintain.

*Added to improve practical form interview coverage.*

<a id="qa-08-014"></a>
### 8.14. How do you decide between a form library and ordinary React state?

**Interview answer:** For a short form with two or three fields, `useState` and a submit handler are often sufficient. For long forms with nested fields, validation schemas, and dynamic arrays, React Hook Form or a similar library reduces boilerplate and can limit unnecessary re-renders. I consider the team's experience and the specific form complexity rather than adding a library by default.

*Added to improve practical form interview coverage.*

---

<a id="section-09"></a>
## 9. Data Fetching & React Query/Suspense

*22 questions — [Back to contents](#contents)*

<a id="qa-09-001"></a>
### 9.1. How do you deduplicate identical simultaneous requests?

**Interview answer:** TanStack Query deduplicates simultaneous requests that share the same query key, so several mounted components can use one in-flight fetch. Each component subscribes to the cached result instead of starting a separate network request. This reduces duplicate traffic and keeps UI state consistent; I still design query keys to include all parameters affecting the result.

<a id="qa-09-002"></a>
### 9.2. How does the data-fetching process work with Suspense?

**Interview answer:** With Suspense, a component can pause rendering while a supported resource is not ready. React shows the nearest Suspense fallback until it can continue rendering. I generally use this with `React.lazy` or a framework or data library that supports Suspense.

<a id="qa-09-003"></a>
### 9.3. How do staleTime and gcTime affect TanStack Query caching?

**Interview answer:** In TanStack Query, `staleTime` controls how long fetched data is considered fresh. While fresh, it normally avoids automatic refetching on triggers such as mounting. `gcTime` controls how long an inactive query stays in memory before garbage collection. For example, I may use a longer `staleTime` for rarely changing country codes than for live notifications.

<a id="qa-09-004"></a>
### 9.4. How do SWR and TanStack Query compare for data fetching?

**Interview answer:** SWR and TanStack Query both help cache and revalidate server data in React. SWR emphasizes a lightweight fetching experience, while TanStack Query has broader built-in tools for mutations, pagination, invalidation, and complex cache policies. I choose according to the application's requirements and existing stack rather than assuming one is universally better.

<a id="qa-09-005"></a>
### 9.5. What are the patterns for data fetching in React?

**Interview answer:** I choose the fetching approach based on where the data is needed. For simple client-only data I can use `fetch` with `useEffect`, but I need cancellation and loading/error handling. For reusable server-state caching, I use TanStack Query or SWR. In route-based apps I prefer route loaders or server-side fetching where supported to avoid waterfalls.

<a id="qa-09-006"></a>
### 9.6. What is `Suspense`? How does it work for data fetching?

**Interview answer:** `Suspense` shows a fallback while its children are not ready to render, such as when `React.lazy` is loading a component or a supported framework data source suspends. It does not automatically handle arbitrary `fetch()` calls inside `useEffect`; those calls need their own loading UI unless they use a Suspense-enabled integration.

<a id="qa-09-007"></a>
### 9.7. What is an optimistic update in TanStack Query, and how would you implement it?

**Interview answer:** An optimistic update means showing the expected result before the server confirms it. With TanStack Query, I can update the cached data in `onMutate`, then restore it if the request fails and invalidate the query afterward to sync with the server.

<a id="qa-09-008"></a>
### 9.8. What is parallel data fetching in Server Components, and why does it matter?

**Interview answer:** Parallel fetching means starting independent requests together instead of waiting for one to finish before starting the next. In a Server Component I can start multiple Promises, then await them with `Promise.all`. This reduces request waterfalls and often improves time to first content. Requests with real dependencies must still be sequential.

<a id="qa-09-009"></a>
### 9.9. What is parallel vs sequential data fetching?

**Interview answer:** Sequential: `await A`, then `await B` – total time = A + B. Parallel: `await Promise.all([A,B])` – total time = max(A,B). In Server Components, initiate fetches without awaiting them first, then await together.

<a id="qa-09-010"></a>
### 9.10. What is prefetching in React Query? When would you use it?

**Interview answer:** `queryClient.prefetchQuery(...)` loads data into the cache before it's needed (e.g., on hover over a link, or in a route loader), so the eventual component render finds data already cached.

<a id="qa-09-011"></a>
### 9.11. What is React Query (TanStack Query)?

**Interview answer:** TanStack Query manages asynchronous server state in the client. `useQuery` fetches and caches reads, while `useMutation` manages writes. It supports request deduplication, retries, stale-data policies, background refetching, and invalidation. I use stable query keys and invalidate or update relevant cached data after successful mutations.

**Optional coding illustration:**
```jsx
const { data, isPending, error } = useQuery({
  queryKey: ['users'], queryFn: fetchUsers
});
```

<a id="qa-09-012"></a>
### 9.12. What is React Query's caching model?

**Interview answer:** Data is cached by query key. `staleTime` controls how long data is considered fresh (no background refetch). `cacheTime` controls how long unused data stays in cache. Queries refetch on window focus, reconnect, or stale threshold.

<a id="qa-09-013"></a>
### 9.13. What is the difference between `isLoading` and `isFetching` in React Query?

**Interview answer:** In TanStack Query, `isFetching` means a request is currently running, including background refetches. `isLoading` describes an initial fetch with no usable data in the current version's query-state model. I use the version's documented flags when deciding between a full-page loader and a small refresh indicator.

<a id="qa-09-014"></a>
### 9.14. What is the difference between a "query" and a "mutation" in React Query?

**Interview answer:** A query reads server data and is identified by a query key, so TanStack Query can cache and refetch it. A mutation changes server data, such as creating or deleting a record, and is typically triggered by a user action. After a successful mutation, I invalidate or update the affected queries so the UI reflects the server's result.

<a id="qa-09-015"></a>
### 9.15. Why can Suspense boundaries be nested, and what determines which one catches a given suspension?

**Interview answer:** The nearest ancestor Suspense boundary to the component that suspended catches it and shows its fallback, letting different parts of a tree show independent loading states rather than one fallback blocking the entire page.

<a id="qa-09-016"></a>
### 9.16. What is `useInfiniteQuery`? When is it used?

**Interview answer:** `useInfiniteQuery` in TanStack Query manages multiple pages of data, such as a feed that loads as the user scrolls. I provide an initial page parameter, a query function, and `getNextPageParam` to tell it what to load next. The Hook provides `fetchNextPage`, `hasNextPage`, and page data for the UI.

<a id="qa-09-017"></a>
### 9.17. What is optimistic UI? How do you implement it?

**Interview answer:** Optimistic UI updates the screen before the server confirms a change, so an interaction feels immediate. For example, I may display a newly added comment while the request is pending. If it fails, I show an error and restore or reconcile the previous state. React 19 has `useOptimistic`, and TanStack Query offers mutation lifecycle callbacks.

<a id="qa-09-018"></a>
### 9.18. What is query invalidation? How do you trigger a refetch after a mutation?

**Interview answer:** Query invalidation tells TanStack Query that cached data may be outdated. After a successful mutation, I call something like `queryClient.invalidateQueries({ queryKey: ['todos'] })`. Matching active queries can refetch so the user sees updated server data. I choose a specific query key to avoid unnecessary refetching of unrelated data.

<a id="qa-09-019"></a>
### 9.19. How do you cancel a query automatically when its component unmounts?

**Interview answer:** React Query handles this internally by default for the underlying fetch (via `AbortSignal` passed to the query function) when a query becomes unused and its `gcTime` conditions are met or when manually cancelled via `queryClient.cancelQueries`.

<a id="qa-09-020"></a>
### 9.20. How does React prioritize work with its Scheduler?

**Interview answer:** React uses an internal Scheduler to control how updates are prioritized: Urgent tasks like clicks and inputs are processed immediately. Non-urgent tasks (like data fetching) can be delayed or paused. This improves responsiveness and allows for time slicing in Concurrent Mode.

<a id="qa-09-021"></a>
### 9.21. What does it mean for a component to "suspend"? What triggers it?

**Interview answer:** A component suspends when it throws a Promise during render (directly, via `use()`, or via a Suspense-integrated data-fetching library), signaling to React "I'm not ready yet" so the nearest Suspense boundary shows its fallback until the promise resolves.

<a id="qa-09-022"></a>
### 9.22. What is SWR?

**Interview answer:** SWR is a React data-fetching library that caches server data and keeps it fresh. It can return cached content immediately and revalidate in the background, simplifying loading and refetching logic.

---

<a id="section-10"></a>
## 10. React 18/19, Concurrent Features

*22 questions — [Back to contents](#contents)*

<a id="qa-10-001"></a>
### 10.1. How would you ensure a React app performs well at 100k concurrent users?

**Interview answer:** CDN for static assets, SSR/SSG for fast first paint, aggressive HTTP/query caching (React Query), server-side pagination (never load full datasets), route-level code splitting, error boundaries everywhere, and production monitoring/alerting from day one.

<a id="qa-10-002"></a>
### 10.2. Is it possible to prevent automatic batching?

**Interview answer:** Yes, it is possible to prevent automatic batching default behavior. There might be cases where you need to re-render your component after each state update or updating one state depends on another state variable. Considering this situation, React introduced `flushSync` method from `react-dom` API for the usecases where you need to flush state updates to DOM immediately.

<a id="qa-10-003"></a>
### 10.3. What are React 19 Actions?

**Interview answer:** React 19 Actions are functions that perform user-triggered work, often asynchronously, and integrate with pending, error, and optimistic UI state. React provides `useActionState`, `useOptimistic`, and React DOM's `useFormStatus` for common workflows. For example, a profile form can submit through an Action and display its pending or validation state.

<a id="qa-10-004"></a>
### 10.4. What are Server Actions (React 19 / Next.js)?

**Interview answer:** Functions marked `'use server'` that can be called directly from Client Components (e.g., as a `<form action={fn}>`) without hand-writing an API route; React serializes arguments, executes on the server, and streams the result back — includes automatic CSRF protection and progressive enhancement (forms work without JS).

<a id="qa-10-005"></a>
### 10.5. What are the most important React 19 features?

**Interview answer:** React 19 introduced Actions for async updates and forms, including `useActionState`, `useOptimistic`, and React DOM's `useFormStatus`. It also supports passing `ref` to function components as a prop, using Context directly as a provider, and improved metadata and resource-loading behavior. I would mention the specific feature relevant to the role rather than just saying it improves performance.

**Optional coding illustration:**
```jsx
const [state, formAction, isPending] = useActionState(saveProfile, { error: null });
<form action={formAction}><input name="name" /><button disabled={isPending}>Save</button></form>
```

<a id="qa-10-006"></a>
### 10.6. What is Concurrent Rendering?

**Interview answer:** Concurrent rendering lets React prepare some updates in a way that can be interrupted, so urgent user interactions can stay responsive. It does not mean React rendering runs on a separate JavaScript thread.

<a id="qa-10-007"></a>
### 10.7. What is concurrent rendering? When does it help vs hurt?

**Interview answer:** Concurrent rendering means React can interrupt or restart low-priority rendering work so urgent user interactions stay responsive. It is not true simultaneous execution of JavaScript on multiple threads. Features such as transitions use this scheduling. It helps with expensive UI updates but requires components to render purely and avoids side effects during rendering.

<a id="qa-10-008"></a>
### 10.8. What is streaming SSR and how does React 18+ improve it?

**Interview answer:** Streaming SSR sends parts of the server-rendered HTML as they become ready instead of waiting for the entire page. React can use Suspense boundaries to show fallbacks for slower sections and progressively deliver their content.

<a id="qa-10-009"></a>
### 10.9. How does concurrent rendering help React prioritize updates?

**Interview answer:** React can interrupt lower-priority rendering work to handle more urgent updates, such as typing. This helps keep the interface responsive during expensive UI changes. Concurrent rendering does not make all work happen in parallel on multiple CPU threads.

<a id="qa-10-010"></a>
### 10.10. What is the "two render passes" behavior you might see in React 18 Strict Mode, and why doesn't it indicate a bug by itself?

**Interview answer:** Strict Mode intentionally renders twice in development to help surface components/effects that aren't pure or properly cleaned up; the second pass's output is discarded and this never happens in production, so by itself it's a detection tool, not a sign of broken app behavior.

<a id="qa-10-011"></a>
### 10.11. What are Server Actions, and when would you use them?

**Interview answer:** A Server Action, often called a Server Function in React-based frameworks, is a server-side function that can be invoked through a supported framework integration, commonly from a form. It is useful for authenticated mutations such as saving a profile. It is not the same as a normal client function, and the server must still validate input and permissions.

<a id="qa-10-012"></a>
### 10.12. What is the difference between async mode and concurrent mode?

**Interview answer:** “Async Mode” was an older name used during React’s concurrent-rendering development. Modern React uses concurrent features instead of switching an entire app into an “async mode.”.

<a id="qa-10-013"></a>
### 10.13. What are the key features introduced in React 18?

**Interview answer:** React 18, released in March 2022, introduced several groundbreaking features focused on performance and user experience: Automatic Batching Batch multiple state updates together (even in async code) to reduce re-renders. Concurrent Features useTransition: Mark updates as non-urgent useDeferredValue: Defer expensive re-renders Suspense on Server: SSR with Suspense support New createRoot API Streaming SSR with Suspense Stream HTML from server and hydrate components as they arrive.

<a id="qa-10-014"></a>
### 10.14. How does React Compiler preserve the behavior of components?

**Interview answer:** React Compiler aims to optimize repeated calculations and renders without changing what the user sees. The component must still follow React’s rules, especially purity and immutable state updates.

<a id="qa-10-015"></a>
### 10.15. When can concurrent rendering add complexity instead of improving performance?

**Interview answer:** Concurrent rendering can make timing assumptions unsafe if code mutates shared state during render or relies on synchronous updates. It helps when the app has urgent and non-urgent work, but I should keep rendering pure and avoid adding transitions without a user-visible benefit.

<a id="qa-10-016"></a>
### 10.16. Can I use JavaScript urls in react16.9?

**Interview answer:** Legacy API: As of React 19, `javascript:` URLs are no longer supported and may throw errors. In React 16.9, `javascript:` URLs would log a warning in the console because URLs starting with `javascript:` are dangerous security vulnerabilities (XSS attacks). Modern Best Practice: Never use `javascript:` URLs Use proper event handlers instead.

<a id="qa-10-017"></a>
### 10.17. Is there a functional-component equivalent of error boundaries?

**Interview answer:** React still relies on error boundaries to catch rendering errors in descendant components. In ordinary React, a custom error boundary is built as a class component using `getDerivedStateFromError` and optionally `componentDidCatch`. In a function-component app, I can use a library such as `react-error-boundary` without writing my own boundary class.

<a id="qa-10-018"></a>
### 10.18. What is `startTransition`?

**Interview answer:** `startTransition` marks a state update as non-urgent. React can prioritize urgent interactions, such as typing, while it prepares the slower update. I use it when a heavy UI update should not block immediate feedback.

<a id="qa-10-019"></a>
### 10.19. How does React break rendering into work units and schedule them?

**Interview answer:** React breaks rendering into units of work (small tasks). These units are scheduled based on priority using the React Scheduler. If time runs out (e.g., user starts typing), React can pause and yield control back to the browser.

<a id="qa-10-020"></a>
### 10.20. Are custom DOM attributes supported in React v16?

**Interview answer:** Note: This question references React v16, which is outdated. The information below applies to React 16+, including current versions (React 18/19). Yes. Starting with React 16, React no longer ignores unknown DOM attributes. If you write JSX with an attribute that React doesn't recognize, React will pass it through to the DOM.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-10-021"></a>
### 10.21. Can you explain batching in React 18 vs React 17?

**Interview answer:** Before React 18, React mainly batched state updates inside React event handlers. React 18 with `createRoot` expanded automatic batching to many updates from promises, timeouts, and native event handlers. For example, two setters in one timeout normally produce one render, not two. React still keeps separate user events logically separate and provides `flushSync` for rare immediate DOM requirements.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-10-022"></a>
### 10.22. What is the behavior of uncaught errors in React 16?

**Interview answer:** Note: This behavior was introduced in React 16 and continues in React 18/19. In React 16+, errors that are not caught by any error boundary will result in unmounting of the whole React component tree. The reason behind this decision is that it is worse to leave corrupted UI in place than to completely remove it. For example, it is worse for a payments app to display a wrong amount than to render nothing.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-11"></a>
## 11. SSR, Next.js & Server Components

*39 questions — [Back to contents](#contents)*

<a id="qa-11-001"></a>
### 11.1. Can you explain browser downloads the JS bundle (hydration)?

**Interview answer:** With server-rendered React, the browser first displays HTML sent by the server. It then downloads the JavaScript needed for interactive components and React hydrates the existing markup by attaching behavior. If server and client initial output differ, hydration can warn or recover by rerendering affected parts. The goal is a fast initial view without losing interactivity.

<a id="qa-11-002"></a>
### 11.2. How do environment variables work differently between server and client code in Next.js?

**Interview answer:** Only variables prefixed `NEXT_PUBLIC_` are inlined into the client bundle and accessible in browser code; unprefixed variables are only available in server-side code (Server Components, API routes, `getServerSideProps`), keeping secrets out of the client bundle.

<a id="qa-11-003"></a>
### 11.3. How do you fetch data in the App Router?

**Interview answer:** In the Next.js App Router, Server Components can be async and fetch data directly with `await`. That keeps server-only logic and credentials off the client. Client Components use supported client data-fetching approaches when the data must update after interaction. I avoid unnecessary waterfalls by starting independent requests in parallel.

<a id="qa-11-004"></a>
### 11.4. How does Next.js handle image optimization?

**Interview answer:** Next.js provides the `Image` component to help deliver appropriately sized and optimized images. It can generate responsive image URLs and use modern formats where supported, while dimensions or a `fill` layout help prevent layout shift. I still choose sensible source images, alt text, and priority settings for important above-the-fold content.

<a id="qa-11-005"></a>
### 11.5. How would you implement Server-Side Rendering (SSR) for a React application? When to use SSR, SSG, ISR?

**Interview answer:** SSR (Server‑Side Rendering): Render React components to HTML on the server for each request. Improves initial page load and SEO. Can be implemented with frameworks like Next.js (using `getServerSideProps`).

<a id="qa-11-006"></a>
### 11.6. Can you explain server Action vs API route?

**Interview answer:** A Server Action is callable directly from components/forms with Next.js handling the network call. An API route is an explicit, stable HTTP endpoint. The backend still needs to authorize requests even if the UI hides or redirects a route.

<a id="qa-11-007"></a>
### 11.7. Can you explain rSC vs SSR – what's the difference?

**Interview answer:** SSR renders components on the server to HTML and then hydrates on the client (components run on both). RSC components run ONLY on the server, never hydrate, and can be async. They reduce client bundle size significantly.

<a id="qa-11-008"></a>
### 11.8. How would you load feature flags on the server in a Next.js app?

**Interview answer:** In Next.js, I can read feature flags on the server and pass the result to the page so the correct UI appears on the first render. The exact API depends on whether the project uses the Pages Router or App Router.

<a id="qa-11-009"></a>
### 11.9. Can you explain sSR vs SSG vs ISR?

**Interview answer:** CSR renders most of the initial UI in the browser after JavaScript loads. SSR creates HTML for each request on the server. SSG prebuilds HTML ahead of time, and ISR refreshes cached static pages after deployment according to revalidation rules. I choose among these methods based on freshness, personalization, SEO, and infrastructure cost. For example, a blog can use SSG or ISR, while a signed-in dashboard often needs dynamic data.

<a id="qa-11-010"></a>
### 11.10. What is streaming SSR? How does `Suspense` enable it?

**Interview answer:** Streaming SSR lets the server send the page shell before all slower content is ready. React can use `Suspense` boundaries to send placeholder HTML first, then stream completed sections when their data or components are available. This improves perceived loading for complex pages, but it still needs appropriate hydration for interactive client components.

<a id="qa-11-011"></a>
### 11.11. What are the differences between page router and app router in nextjs?

**Interview answer:** The Next.js Pages Router uses a `pages/` directory and data APIs such as `getServerSideProps`; the App Router uses `app/` with layouts, Server Components, and nested loading and error boundaries. Both can serve production applications. For a new app I would usually consider App Router, while preserving Pages Router conventions when maintaining an existing app.

<a id="qa-11-012"></a>
### 11.12. What is "hydration cost" in SSR apps, and how do you reduce it?

**Interview answer:** The time/CPU spent re-running component JS to attach event listeners to server-rendered HTML. Reduce via selective/progressive hydration (Suspense boundaries), reducing the amount of interactive (Client Component) code shipped, and deferring non-critical component hydration.

<a id="qa-11-013"></a>
### 11.13. What is hydration?

**Interview answer:** Hydration is React's process of making server-rendered HTML interactive on the client. React uses `hydrateRoot` to attach behavior while preserving matching markup. The first client render should match the server output; differences caused by dates, random numbers, browser-only state, or invalid markup can create hydration mismatches.

**Optional coding illustration:**
```jsx
// Client entry point for server-rendered markup:
hydrateRoot(document.getElementById('root'), <App />);
```

<a id="qa-11-014"></a>
### 11.14. What is hydration? How do hydration mismatches occur?

**Interview answer:** Hydration is the process where React attaches event listeners and reconciles the server‑rendered HTML with the client‑side virtual DOM. It allows interactive components to “take over” the static markup. Hydration mismatches occur when the HTML generated on the server differs from the initial render on the client (e.g., due to different data, random values, or browser‑only APIs).

<a id="qa-11-015"></a>
### 11.15. What is request middleware in Next.js, and when would you use it?

**Interview answer:** Middleware or an early request handler in Next.js can inspect requests before a page is served, such as redirecting unauthenticated users or rewriting a route. The exact file name and runtime depend on the Next.js version. I use it for routing decisions, but I still check authorization inside server code and data APIs.

<a id="qa-11-016"></a>
### 11.16. What is ReactDOMServer?

**Interview answer:** React DOM server-rendering APIs generate HTML for React components outside the browser. Modern streaming APIs include `renderToPipeableStream` for Node environments and `renderToReadableStream` where web streams are supported. Older APIs like `renderToString` still exist but do not support streaming in the same way. I prefer a framework to manage routing, streaming, and hydration.

<a id="qa-11-017"></a>
### 11.17. What is server-side rendering (SSR), and how does it differ from client-side rendering?

**Interview answer:** With SSR, the server generates HTML for the initial page, so users can see content before all client JavaScript finishes loading. With client-side rendering, the browser builds the UI after JavaScript runs. SSR can improve initial content delivery, but interactive SSR pages usually still need hydration.

<a id="qa-11-018"></a>
### 11.18. What is the "FOUC" (flash of unstyled content) risk with runtime CSS-in-JS in SSR, and how is it mitigated?

**Interview answer:** If styles are injected client-side after hydration, the user may briefly see unstyled markup. Mitigated by extracting critical CSS server-side and inlining it in the initial HTML response (most CSS-in-JS libraries provide an SSR extraction API for this).

<a id="qa-11-019"></a>
### 11.19. What is the difference between a dynamic and a static route segment caching behavior in the App Router?

**Interview answer:** Static and dynamic rendering are framework-specific Next.js concepts. A route that can be pre-rendered and cached may serve a static result, while a route using request-specific data can require dynamic rendering. The exact caching defaults have changed across Next.js releases, so I check the version and explicitly configure freshness or revalidation for each data source.

<a id="qa-11-020"></a>
### 11.20. What is the Next.js App Router, and how does it differ from the Page Router?

**Interview answer:** File-system routing via `app/` (vs. `pages/`); components are Server Components by default (vs. all Client Components); native nested layouts (`layout.js`) and built-in `loading.js`/`error.js` for Suspense/error boundaries per route; native async data fetching with `fetch`; native Server Actions support.

<a id="qa-11-021"></a>
### 11.21. What is the security consideration around React Server Components and passing data from server to client?

**Interview answer:** Data passed as props from a Server Component into a Client Component is serialized and does ship to the browser; sensitive fields fetched server-side must be explicitly excluded from what's passed down, not just "kept on the server" by assumption.

<a id="qa-11-022"></a>
### 11.22. When to use client and server components?

**Interview answer:** You can efficiently build nextjs application if you are aware about which part of the application needs to use client components and which other parts needs to use server components. The common cases of both client and server components are listed below: Client components: Whenever your need to add interactivity and event listeners such as onClick(), onChange(), etc to the pages If you need to use State and Lifecycle Effects like useState(), useReducer(), useEffect() etc.

<a id="qa-11-023"></a>
### 11.23. How are React Server Components different from Client Components?

**Interview answer:** Server Components run on the server and can access server resources without sending their component code to the browser. Client Components can use client-side interactivity, state and event handlers. They work together in frameworks that support the architecture.

<a id="qa-11-024"></a>
### 11.24. What is the difference between `next/link` prefetching and a manual `router.prefetch()` call?

**Interview answer:** `<Link>` automatically prefetches linked pages' code/data when they enter the viewport (in production). `router.prefetch()` lets you trigger the same prefetching imperatively (e.g., on hover or a predicted next action) outside of a visible `<Link>`.

<a id="qa-11-025"></a>
### 11.25. How do you prevent waterfall requests in a component tree?

**Interview answer:** I prevent request waterfalls by starting independent data requests in parallel rather than waiting for one to finish before launching the next. On the server, I can start Promises together and then `await Promise.all(...)`. In client applications, route loaders or `useQueries` can help. Sequential fetching is still necessary when one request depends on another's result.

<a id="qa-11-026"></a>
### 11.26. Is it possible to use async/await in plain React?

**Interview answer:** Yes, you can use `async/await` in plain React, as long as your JavaScript environment supports ES2017+. Nowadays most modern browsers and build tools support ES2017+ version. If you're using **Create React App, Next.js, Remix**, or any modern React setup, `async/await` is supported out of the box through Babel.

<a id="qa-11-027"></a>
### 11.27. What are Next.js `loading.js` and `error.js`?

**Interview answer:** `loading.js`: automatically wraps the page in Suspense – shown while the page is loading. `error.js`: an error boundary for the route – shown when the page throws. They are React components with special Next.js behavior.

<a id="qa-11-028"></a>
### 11.28. What are React Server Components (RSC)?

**Interview answer:** Components that run only on the server. They can directly access databases, file systems, and APIs. Their code never ships to the client. They cannot use hooks or browser APIs. They interleave with Client Components.

<a id="qa-11-029"></a>
### 11.29. What is `getStaticPaths` (Pages Router)? When is it needed?

**Interview answer:** Defines which dynamic routes (`[slug].js`) to pre-render at build time for SSG, specifying a `fallback` strategy for paths not pre-rendered.

<a id="qa-11-030"></a>
### 11.30. What is ISR (Incremental Static Regeneration)?

**Interview answer:** ISR stands for Incremental Static Regeneration. In Next.js, it lets a page remain statically generated while its content is refreshed after a configured revalidation period. I use it for pages that should be fast but do not require completely live data.

<a id="qa-11-031"></a>
### 11.31. What is NextJS and major features of it?

**Interview answer:** Next.js is a React framework that provides routing, server rendering, static generation, data fetching support, and build optimization. I use it when a project needs features beyond client-side React, such as SEO-friendly pages or server-side functionality.

<a id="qa-11-032"></a>
### 11.32. What is selective hydration? Why does it matter?

**Interview answer:** React hydrates parts of the page as their HTML/JS arrive and as the user interacts, rather than waiting for the whole page.

<a id="qa-11-033"></a>
### 11.33. What is SSG (Static Site Generation)?

**Interview answer:** Pre-rendering pages to HTML at build time. Fastest delivery via CDN. Used for content that doesn't change per request (blogs, docs, marketing). Next.js uses `getStaticProps` and `generateStaticParams`.

<a id="qa-11-034"></a>
### 11.34. What is streaming SSR?

**Interview answer:** Sending HTML to the browser in chunks as components finish rendering on the server. Parts of the page become interactive progressively. React 18's `renderToPipeableStream` / `renderToReadableStream` enable this.

<a id="qa-11-035"></a>
### 11.35. What does the "use client" directive mean in Next.js?

**Interview answer:** In Next.js App Router, `"use client"` marks a module as a Client Component entry point. I use it when a component needs client-side state, event handlers, or browser APIs. Components without that directive are Server Components by default in the App Router.

<a id="qa-11-036"></a>
### 11.36. What is the `use server` directive (Next.js Server Actions)?

**Interview answer:** `'use server'` marks a function (or an entire file) as a Server Action — code that always runs on the server, even when called from a Client Component, similar in spirit to an RPC call. Under the hood, calling a `'use server'` function from the client triggers a POST request to the server; React serializes the arguments, runs the function on the server, and streams the result back.

<a id="qa-11-037"></a>
### 11.37. What is the risk of putting sensitive logic/secrets in a Client Component by mistake?

**Interview answer:** Anything in a `'use client'` module (and its non-server imports) ships to the browser bundle, so secrets or sensitive business logic placed there become visible/extractable by anyone inspecting the client JS.

<a id="qa-11-038"></a>
### 11.38. How would you implement server-side rendering for a React application?

**Interview answer:** Approaches: - Frameworks: Next.js (recommended), Remix, or custom Node server with React's `renderToString`/`renderToPipeableStream`. - Data fetching: Fetch data on the server (e.g., `getServerSideProps` in Next.js) and pass it as props to the component. - Hydration: Server‑rendered HTML is sent to client; React attaches event listeners and reconciles. - Performance: Use streaming SSR (`renderToPipeableStream`) for faster TTFB. - Caching: Use CDN caching with `stale-while-revalidate` for pages. - Challenges: Ensure server and client environment compatibility (avoid `window` usage in server). Use `useEffect` for client‑only code.

<a id="qa-11-039"></a>
### 11.39. What replaced ReactDOMServer.renderToNodeStream for streaming SSR?

**Interview answer:** `renderToNodeStream` was an older Node.js API for streaming React HTML and is no longer the recommended server-rendering approach. Modern React uses streaming APIs such as `renderToPipeableStream` on Node.js or `renderToReadableStream` in supported web stream environments. I normally let a framework handle the stream, Suspense boundaries, and hydration.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-12"></a>
## 12. Error Handling & Error Boundaries

*16 questions — [Back to contents](#contents)*

<a id="qa-12-001"></a>
### 12.1. Which types of errors are caught by a React error boundary?

**Interview answer:** Error boundaries catch errors thrown while rendering descendant components and during supported lifecycle work. They do not automatically catch event-handler errors, most async callbacks, or errors thrown in the boundary itself.

<a id="qa-12-002"></a>
### 12.2. How do you create an error boundary?

**Interview answer:** A React error boundary is a class component that uses `static getDerivedStateFromError()` to show fallback UI and `componentDidCatch()` to log errors. I wrap risky feature areas so one broken widget does not necessarily crash the entire screen. I still handle async failures and event-handler errors separately because boundaries do not catch all error types.

**Optional coding illustration:**
```jsx
class ErrorBoundary extends React.Component {
  state = { failed: false };
  static getDerivedStateFromError() { return { failed: true }; }
  render() { return this.state.failed ? <p>Something went wrong</p> : this.props.children; }
}
```

<a id="qa-12-003"></a>
### 12.3. How do you log errors caught by an Error Boundary to a monitoring service (e.g., Sentry)?

**Interview answer:** Call the logging SDK inside `componentDidCatch(error, errorInfo)`, which receives both the error and the component stack trace, then report it before rendering the fallback UI.

<a id="qa-12-004"></a>
### 12.4. How do you reset an Error Boundary after the user retries (e.g., clicking "Try again")?

**Interview answer:** Change the boundary's `key` prop to force a fresh mount, or use `react-error-boundary`'s `resetErrorBoundary`/`onReset` support to clear the caught error and re-render children.

<a id="qa-12-005"></a>
### 12.5. How do you test error boundaries?

**Interview answer:** I render an error boundary around a test component that throws. Then I check that the fallback UI appears and any error-reporting callback is called. I also make sure expected test errors do not hide unrelated failures.

<a id="qa-12-006"></a>
### 12.6. What are the methods invoked during error handling?

**Interview answer:** React error boundaries use two main class methods. `static getDerivedStateFromError(error)` returns state that can show a fallback UI after a descendant fails. `componentDidCatch(error, info)` receives the error and component stack for logging. I use them together but still handle event-handler and asynchronous errors separately.

<a id="qa-12-007"></a>
### 12.7. What is an Error Boundary? What errors does it NOT catch?

**Interview answer:** An error boundary catches rendering and lifecycle errors thrown by components below it and can show fallback UI. It does not catch ordinary errors in event handlers, server-side rendering, or most asynchronous callbacks. For those I use `try/catch`, Promise rejection handling, and centralized monitoring. An error boundary also cannot catch an error thrown by itself.

<a id="qa-12-008"></a>
### 12.8. What is the benefit of component stack trace from error boundary?

**Interview answer:** An error boundary can provide a component stack trace showing where a rendering error occurred in the component hierarchy. That makes it easier to debug errors beyond the normal JavaScript stack trace.

<a id="qa-12-009"></a>
### 12.9. What is the difference between a recoverable and an unrecoverable error in a React app's error-handling strategy?

**Interview answer:** A recoverable error (e.g., a failed API call) can show an inline retry UI while the rest of the app keeps working. An unrecoverable error (e.g., corrupted app state) may require a full Error Boundary fallback or forced reload, since continuing to render could produce further incorrect behavior.

<a id="qa-12-010"></a>
### 12.10. Why can't a single top-level Error Boundary be a complete error-handling strategy?

**Interview answer:** One crash anywhere takes down the entire app's UI behind a single fallback; nesting boundaries around independent sections (widgets, routes) isolates failures so one broken part doesn't block the rest.

<a id="qa-12-011"></a>
### 12.11. Can you describe about componentDidCatch lifecycle method signature?

**Interview answer:** `componentDidCatch(error, info)` is a class lifecycle method used by error boundaries. `error` is the thrown error, while `info.componentStack` helps locate the component tree where it happened. I use it for logging and recovery UI.

<a id="qa-12-012"></a>
### 12.12. What is global error monitoring in React apps?

**Interview answer:** Pair error boundaries with a monitoring SDK (Sentry, LogRocket). Use `window.onerror` and `window.onunhandledrejection` for uncaught async errors. Error boundaries call `componentDidCatch` which logs to the service.

<a id="qa-12-013"></a>
### 12.13. What is the purpose of getDerivedStateFromError?

**Interview answer:** `static getDerivedStateFromError(error)` runs when a descendant throws during rendering and returns a state update, often to show fallback UI. I can pair it with `componentDidCatch` for logging.

<a id="qa-12-014"></a>
### 12.14. What is the proper placement for error boundaries?

**Interview answer:** The granularity of error boundaries usage is up to the developer based on project needs. You can follow either of these approaches, You can wrap top-level route components to display a generic error message for the entire application. You can also wrap individual components in an error boundary to protect them from crashing the rest of the application.

<a id="qa-12-015"></a>
### 12.15. What is the behavior of an uncaught error with no error boundary present (React 16+)?

**Interview answer:** The entire component tree unmounts — React's philosophy is that leaving corrupted UI on screen (e.g., a payments app showing a wrong amount) is worse than showing nothing. Always wrap critical sections in boundaries to avoid full-app blank-outs.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-12-016"></a>
### 12.16. How are error boundaries handled in React v15?

**Interview answer:** ⚠️ LEGACY: This question is only relevant for historical context. React v15 is extremely outdated (released in 2016). React v15 provided very basic support for error boundaries using the `unstable_handleError` method. This was an experimental feature that was later redesigned and renamed to `componentDidCatch` in React v16. Modern Error Boundaries (React 16+): Use `static getDerivedStateFromError(error)` for UI fallback Use `componentDidCatch(error, info)` for logging Work consistently across server and client rendering.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-13"></a>
## 13. Design Patterns (HOC, Render Props, Compound Components)

*25 questions — [Back to contents](#contents)*

<a id="qa-13-001"></a>
### 13.1. How would you define a clean API for a reusable React component?

**Interview answer:** For a reusable component, I define a small, consistent props API. I include only useful options such as `variant`, `size`, `disabled`, and event handlers, and I pass through appropriate accessibility attributes. Clear defaults make the component easy to use.

<a id="qa-13-002"></a>
### 13.2. How do you create HOC using render props?

**Interview answer:** You can implement most higher-order components (HOC) using a regular component with a render prop. For example, if you would prefer to have a withMouse HOC instead of a `<Mouse>`{=html} component, you could easily create one using a regular `<Mouse>`{=html} with a render prop. This way render props gives the flexibility of using either pattern.

<a id="qa-13-003"></a>
### 13.3. How do you build a reusable modal?

**Interview answer:** I use a portal to render outside the app root. Manage open state via controlled pattern. Trap focus inside for accessibility. Close on Escape key and overlay click. Accept children for flexible content.

<a id="qa-13-004"></a>
### 13.4. What is a higher-order component (HOC)? Give an example?

**Interview answer:** A higher-order component is a function that accepts a component and returns a new component with extra behavior. For example, `withAuth(Profile)` could add a login check. HOCs are common in older libraries, but I now prefer custom Hooks for sharing logic when possible because they are usually easier to trace and type.

<a id="qa-13-005"></a>
### 13.5. How do you design a component library that's flexible and consistent org-wide?

**Interview answer:** I build a component library around accessible primitives, consistent design tokens, and small, well-typed props. For example, every Button should follow the same variants, disabled behavior, keyboard semantics, and focus styling. I document components in Storybook, test them with keyboard and accessibility checks, and version changes carefully to avoid breaking consumers.

<a id="qa-13-006"></a>
### 13.6. What is the difference between a Compound Component and a Slot-based component?

**Interview answer:** Compound Components implicitly share state via Context between a fixed set of sub-components (`<Tabs.Tab>` knows which `<Tabs>` it belongs to). Slot-based components explicitly receive arbitrary content/components as props without that implicit shared-state wiring.

<a id="qa-13-007"></a>
### 13.7. How would you develop a React component in isolation?

**Interview answer:** I build and test a reusable component in isolation using Storybook or a small development page. I define example props, states, and accessibility behavior before connecting it to the wider application.

<a id="qa-13-008"></a>
### 13.8. How would you version the API of a shared React component library?

**Interview answer:** I use semantic versioning for a shared component library: major for breaking API changes, minor for backward-compatible features, and patch for fixes. I document changes and give migration notes when props change.

<a id="qa-13-009"></a>
### 13.9. How would you build a reusable React component library?

**Interview answer:** I begin with accessible, reusable components that expose simple props and sensible defaults. I test variants in Storybook, keep shared design tokens consistent, and publish the library with clear versioning and documentation.

<a id="qa-13-010"></a>
### 13.10. How would you document reusable React components for a team?

**Interview answer:** I document components in Storybook with examples of their props, variants, behavior, and accessibility requirements. This helps teammates understand when and how to use each component.

<a id="qa-13-011"></a>
### 13.11. How do you create a generic, reusable component?

**Interview answer:** A generic reusable component accepts different data types while preserving type safety. For example, a `List<T>` component can take an array of `T` items plus a `renderItem(item: T)` function. The caller decides how a row appears, and TypeScript checks that the renderer receives the right item type.

<a id="qa-13-012"></a>
### 13.12. What is the purpose of forward ref in HOCs?

**Interview answer:** Normally a ref on a higher-order component points to the wrapper. Forwarding the ref lets the parent access the wrapped component or inner element when required.

<a id="qa-13-013"></a>
### 13.13. What are HOC factory implementations?

**Interview answer:** There are two main ways of implementing HOCs in React. Props Proxy (PP) and Inheritance Inversion (II). But they follow different approaches for manipulating the WrappedComponent. Props Proxy In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name Props Proxy.

<a id="qa-13-014"></a>
### 13.14. Can you explain higher-Order Component (HOC) that logs props on every render?

**Interview answer:** Every time `LoggedButton` renders, logs `Button rendered with: { label: 'Submit', onClick: [Function] }`. HOC concern: If `App` re-renders, `withLogger(Button)` is a new component type per render if defined inside — always define HOCs outside components.

<a id="qa-13-015"></a>
### 13.15. What is render hijacking in React?

**Interview answer:** The concept of render hijacking is the ability to control what a component will output from another component. It actually means that you decorate your component by wrapping it into a Higher-Order component. By wrapping you can inject additional props or make other changes, which can cause changing logic of rendering. It does not actually enables hijacking, but by using HOC you make your component behave in different way.

<a id="qa-13-016"></a>
### 13.16. How do you pass a component as a prop (not just data)?

**Interview answer:** Pass the element or component reference itself as a prop value: `<Layout icon={<HomeIcon/>} />` or `<Layout Icon={HomeIcon} />`, letting the parent customize rendered content.

<a id="qa-13-017"></a>
### 13.17. What is the trade-off of the Compound Components pattern vs a single component with a declarative config object/array prop?

**Interview answer:** Compound Components give a more flexible, JSX-native, readable API (the consumer controls layout/order freely) but require more setup (Context plumbing) and are less convenient to generate dynamically from data; a config-array prop is easier to generate programmatically but less flexible for custom layout per-item.

<a id="qa-13-018"></a>
### 13.18. How does the "Compound Components" pattern handle components that aren't direct children (e.g., nested in a wrapper div)?

**Interview answer:** Using `React.Children.map`/`cloneElement` (older approach, fragile with nesting) or, more robustly, Context — so sub-components can be nested arbitrarily deep and still read shared state/behavior without relying on direct parent-child positioning.

<a id="qa-13-019"></a>
### 13.19. What do you analyze before designing a reusable React component?

**Interview answer:** Before building a reusable component, I identify its purpose, states, sizes, variants, interactions, and accessibility requirements. Then I design a small prop API and test it across different use cases.

<a id="qa-13-020"></a>
### 13.20. How would you organize folders in a large React codebase?

**Interview answer:** Two common folder styles are organizing by file type, such as `components`, `hooks`, and `pages`, or organizing by feature, such as `auth` and `dashboard`. For larger apps, I prefer feature-based folders so related code stays together.

<a id="qa-13-021"></a>
### 13.21. What are the limitations of higher-order components (HOCs)?

**Interview answer:** HOCs can add extra wrapper layers, make debugging and prop names harder to follow, and cause prop collisions. In modern React, I usually prefer Hooks for sharing stateful logic and composition for UI reuse.

<a id="qa-13-022"></a>
### 13.22. What is a design system / component library pattern?

**Interview answer:** A design system is a shared set of design tokens, reusable components, accessibility patterns, and documentation. For example, the same Button, Input, and Dialog components can be used across multiple applications. It improves consistency and development speed, but the library needs clear APIs, tests, versioning, and ownership to stay reliable.

<a id="qa-13-023"></a>
### 13.23. What is the "props getter" pattern used by headless libraries (e.g., downshift)?

**Interview answer:** Instead of exposing raw state, the Hook returns functions like `getInputProps()` / `getItemProps()` that spread the correct ARIA attributes and event handlers onto the consumer's own markup, bundling correct behavior without dictating the DOM structure.

<a id="qa-13-024"></a>
### 13.24. What is the Compound Components pattern?

**Interview answer:** The Compound Components pattern lets related components share state and work together. For example, `<Tabs><Tabs.List>...</Tabs.List><Tabs.Panel>...</Tabs.Panel></Tabs>` gives callers control over the structure while the parent manages which tab is active. Context usually connects the parts. It is flexible, but documentation and accessibility need extra care.

<a id="qa-13-025"></a>
### 13.25. What is a monorepo, and what tools help manage one for a React codebase (e.g., sharing a component library across apps)?

**Interview answer:** A single repository containing multiple packages/apps (e.g., a shared UI library plus several apps consuming it). Tools like Turborepo, Nx, or Yarn/pnpm workspaces manage shared dependencies, incremental builds, and task caching across the packages.

---

<a id="section-14"></a>
## 14. Testing React Applications

*26 questions — [Back to contents](#contents)*

<a id="qa-14-001"></a>
### 14.1. Give a simple example of Jest test case?

**Interview answer:** Let's write a test for a function that adds two numbers in `sum.js` file: Create a file named `sum.test.js` which contains actual test: And then add the following section to your `package.json`: Finally, run `yarn test` or `npm test` and Jest will print a result.

<a id="qa-14-002"></a>
### 14.2. Can you explain `getBy` vs `queryBy` vs `findBy` – when do you use each?

**Interview answer:** `getBy`: throws if not found (use when element should exist) `queryBy`: returns null if not found (use for asserting absence) `findBy`: async, returns Promise – use when element appears after async operation.

<a id="qa-14-003"></a>
### 14.3. How do you test that a component is accessible?

**Interview answer:** I test accessible behavior using semantic HTML, keyboard interactions, and queries such as `getByRole`. I can run an automated accessibility checker such as `axe` or `jest-axe` against the rendered component to catch many problems. Automated checks cannot prove full accessibility, so I also test focus order and screen readers for critical flows.

<a id="qa-14-004"></a>
### 14.4. What roles do render, screen and userEvent play in React Testing Library?

**Interview answer:** In React Testing Library, `render` mounts the component in a test DOM, `screen` provides queries such as `getByRole`, and `userEvent` simulates realistic actions like typing and clicking. I use them together to assert on visible behavior: render a form, type into an input, click Submit, and verify the result.

<a id="qa-14-005"></a>
### 14.5. What is React Testing Library (RTL)?

**Interview answer:** React Testing Library renders components in a test DOM and encourages checking what a user can see and do. I select elements by roles, labels, or text, simulate actions with `userEvent`, and assert on the resulting UI. I avoid testing component internals because implementation details can change even when behavior stays correct.

**Optional coding illustration:**
```jsx
render(<Counter />);
await userEvent.setup().click(screen.getByRole('button', { name: /increment/i }));
expect(screen.getByText('1')).toBeInTheDocument();
```

<a id="qa-14-006"></a>
### 14.6. What is visual regression testing, and how would you implement it?

**Interview answer:** Visual regression testing catches unintended UI changes by comparing screenshots of components or pages against approved baselines. Implementation: Tools: Percy (integrated with Storybook), Chromatic, or open‑source tools like Playwright with screenshot comparison. Workflow: Capture screenshots of each component/page in a controlled environment (e.g., Storybook).

<a id="qa-14-007"></a>
### 14.7. What is Vitest and how does it differ from Jest?

**Interview answer:** Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects.

<a id="qa-14-008"></a>
### 14.8. Why does RTL discourage test IDs/class names? When is `data-testid` appropriate?

**Interview answer:** React Testing Library prefers queries such as `getByRole` and `getByLabelText` because they resemble how users and assistive technology find controls. Queries by CSS class or test ID can hide accessibility problems and break during refactors. I use `data-testid` only when an element has no suitable accessible role, label, or text.

<a id="qa-14-009"></a>
### 14.9. How do you mock API calls with `msw`?

**Interview answer:** Mock Service Worker intercepts network requests and returns controlled test responses without changing how the component fetches data. I define handlers for success, loading, and failure cases, then render the component and assert on the UI. This creates realistic tests while avoiding dependence on a live backend.

<a id="qa-14-010"></a>
### 14.10. How do you test async behavior (e.g., API calls)?

**Interview answer:** I mock network responses using MSW or a fetch mock, render the component, and wait for observable UI with `findByRole` or `waitFor`. For example, after the request completes I expect a user name to appear; for failure I expect an alert. I avoid arbitrary timeouts and ensure each test resets its mock state.

<a id="qa-14-011"></a>
### 14.11. How do you test components with context?

**Interview answer:** To test a Context consumer, I render it inside a test Provider that supplies a known value. React Testing Library's `wrapper` option lets me reuse a set of providers across tests. I then assert on what the component displays or does, rather than inspecting the internal implementation of `useContext`.

<a id="qa-14-012"></a>
### 14.12. How do you test components wrapped in Providers/Router?

**Interview answer:** A custom `render` wrapper that wraps the component in needed providers, reused across tests. The backend still needs to authorize requests even if the UI hides or redirects a route.

<a id="qa-14-013"></a>
### 14.13. How do you test error states (e.g., a failed API call shows an error message)?

**Interview answer:** Mock the request to reject/return an error response via `msw`, render the component, and assert the error UI appears via `findByText`/`findByRole`. For example, I keep a modal's open/closed value in state and pass its title through props.

<a id="qa-14-014"></a>
### 14.14. How do you test user interactions?

**Interview answer:** I use `userEvent` with React Testing Library to simulate typing, selecting an option, or clicking a button, then assert on the resulting UI. For example, after typing in a search box, I check that matching items appear. I generally prefer `userEvent` over firing low-level events manually because it better resembles real user interactions.

<a id="qa-14-015"></a>
### 14.15. How do you test a component that fetches data in `useEffect`?

**Interview answer:** I mock network responses using Mock Service Worker, render the component with React Testing Library, then assert on the loading and resolved UI. For example, `await screen.findByText('Profile loaded')` waits for asynchronous rendering. I also test the error path. I avoid testing internal state directly because the user only sees the rendered result.

<a id="qa-14-016"></a>
### 14.16. How do you test custom hooks?

**Interview answer:** For custom Hooks, I use React Testing Library's `renderHook` to run the Hook in a test component. I wrap manual updates in `act` when needed and assert on the exposed values. If the Hook reads Context, I provide a wrapper with the required provider. I test behavior, cleanup, and error handling instead of private implementation details.

<a id="qa-14-017"></a>
### 14.17. What is `act()`? Why does RTL warn about updates outside it?

**Interview answer:** React's `act()` helps tests flush updates and Effects before asserting on rendered UI. React Testing Library already wraps many common interactions, so I rarely call `act` directly. A warning usually means asynchronous updates are still pending or a timer or Promise was not awaited. I fix the test to wait for observable behavior instead of suppressing the warning.

<a id="qa-14-018"></a>
### 14.18. What is Mock Service Worker (MSW)?

**Interview answer:** Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly.

<a id="qa-14-019"></a>
### 14.19. How do you test a component using fake timers (e.g., a debounce or a countdown)?

**Interview answer:** `jest.useFakeTimers()`, trigger the action, then `jest.advanceTimersByTime(ms)` or `jest.runAllTimers()` to fast-forward, asserting the expected state after the delay — avoiding real wall-clock waits in tests.

<a id="qa-14-020"></a>
### 14.20. What is Shallow Renderer in React testing?

**Interview answer:** Shallow rendering tests only one level of a component without rendering its children. It was common in older test suites, but today I generally prefer React Testing Library, which tests the output and behavior users can observe.

<a id="qa-14-021"></a>
### 14.21. What is the difference between visual regression testing and contract testing?

**Interview answer:** Visual regression tests compare screenshots to detect unintended UI changes. Contract tests check whether two systems agree on an API or data format. One tests appearance; the other tests integration compatibility.

<a id="qa-14-022"></a>
### 14.22. What is the difference between shallow and deep rendering?

**Interview answer:** Shallow rendering tests one component level in tools such as Enzyme; renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees.

<a id="qa-14-023"></a>
### 14.23. What are the RTL query priorities?

**Interview answer:** Priority order: `getByRole` (most like how screen readers work) > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByDisplayValue` > `getByAltText` > `getByTitle` > `getByTestId` (last resort).

<a id="qa-14-024"></a>
### 14.24. What is snapshot testing? When is it useful vs risky?

**Interview answer:** Serializes rendered output for comparison; useful for stable presentational components, risky as a primary strategy (hard to meaningfully review, easy to blindly update).

<a id="qa-14-025"></a>
### 14.25. How would you test a React application at different levels?

**Interview answer:** I test pure utility functions with unit tests, component interactions with React Testing Library, and important user journeys with end-to-end tests such as Playwright. I also use visual regression tests where the exact appearance matters.

<a id="qa-14-026"></a>
### 14.26. Is ReactTestUtils still recommended for testing React?

**Interview answer:** `react-dom/test-utils` was an older React testing API; many of its utilities have been removed or deprecated in modern React versions. For component behavior today, I use React Testing Library with a modern test runner such as Vitest or Jest. The modern `act` helper comes from React itself, and I avoid relying on the old `react-addons-test-utils` package.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-15"></a>
## 15. TypeScript with React

*21 questions — [Back to contents](#contents)*

<a id="qa-15-001"></a>
### 15.1. Why use TypeScript with React?

**Interview answer:** TypeScript checks the shapes of props, state, events, and API models while I develop a React app. It catches missing required props and incorrect function arguments before runtime and improves editor autocomplete. It does not validate live server responses by itself, so I still use runtime validation when data comes from an untrusted source.

<a id="qa-15-002"></a>
### 15.2. How do you avoid `any` when typing a third-party library without TypeScript definitions?

**Interview answer:** Write a local `.d.ts` declaration file with minimal type definitions for the parts you use, or check if `@types/<package>` exists on DefinitelyTyped before falling back to `any`/`unknown` with manual runtime checks.

<a id="qa-15-003"></a>
### 15.3. How do you design a reusable button component?

**Interview answer:** Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type` props. Use TypeScript to type them. Forward refs for DOM access. Avoid hardcoding styles -- use class variants or a styling system. Compose with an icon slot.

<a id="qa-15-004"></a>
### 15.4. How do you type children in React with TypeScript?

**Interview answer:** For normal nested JSX content, I type `children` as `React.ReactNode`, such as `type Props = { children: React.ReactNode }`. `React.ReactElement` is narrower and requires a React element. I can also use `PropsWithChildren<Props>`. I choose based on what the component actually accepts rather than automatically allowing all children.

**Optional coding illustration:**
```jsx
type CardProps = { title: string; children: React.ReactNode };
function Card({ title, children }: CardProps) {
  return <section><h2>{title}</h2>{children}</section>;
}
```

<a id="qa-15-005"></a>
### 15.5. How would you use TypeScript in `create-React-app` application?

**Interview answer:** Starting from react-scripts@3.3.0+ releases onwards, you can now optionally start a new app from a template by appending `--template [template-name]` to the creation command. If you don't select a template, it will create your project with base template. Remember that templates are always named in the format `cra-template-[template-name]`, here you only need to fill the `[template-name]` section.

<a id="qa-15-006"></a>
### 15.6. What is `PropTypes`? How does it differ from TypeScript?

**Interview answer:** PropTypes checks the types of props at runtime in development and reports warnings; it is a separate library. TypeScript checks types during compilation, so it catches many mistakes earlier but its types disappear at runtime. For modern TypeScript React apps, I generally use TypeScript and validate external data separately.

<a id="qa-15-007"></a>
### 15.7. Can you explain `React.FC` vs explicit return type – which is better?

**Interview answer:** `React.FC<Props>` and a normal function with typed props both provide type checking. I usually prefer `function Button({label}: ButtonProps) { ... }` because the props and return type are straightforward, and I can type `children` explicitly when needed. `React.FC` is still valid; it is mainly a team style choice rather than a performance difference.

<a id="qa-15-008"></a>
### 15.8. What is a discriminated union and when is it useful in React?

**Interview answer:** A union type sharing a common literal field (e.g., `type Action = {type:'increment'} | {type:'setValue', payload:number}`) — lets TypeScript narrow the exact shape inside a `switch`/`if` on that field, ideal for typing reducer actions.

<a id="qa-15-009"></a>
### 15.9. How do you say that props are readonly?

**Interview answer:** Props are read-only inputs passed from a parent to a component. I should never assign to or mutate them inside the child. If something needs to change, I update state in the appropriate component and pass the new value down.

<a id="qa-15-010"></a>
### 15.10. How do you type a component that accepts all native `<button>` props plus custom ones?

**Interview answer:** I extend the native button props so my reusable button supports standard attributes such as `disabled`, `type`, and `onClick`. For example: `type Props = React.ComponentPropsWithRef<'button'> & { variant?: 'primary' | 'secondary' }`. Then I forward the relevant props to `<button>`. In React 19, a function component can receive `ref` as a prop; older versions generally use `forwardRef`.

<a id="qa-15-011"></a>
### 15.11. How do you type a React function component’s props in TypeScript?

**Interview answer:** I define a `type` or `interface` for the props and use it in the component parameter, for example `function Button({ label }: { label: string })`. This lets TypeScript catch missing or incorrect props before runtime.

<a id="qa-15-012"></a>
### 15.12. How do you type event handlers?

**Interview answer:** I type React events using the element involved: `React.ChangeEvent<HTMLInputElement>` for a text input and `React.MouseEvent<HTMLButtonElement>` for a button. For example, `const onChange = (e: React.ChangeEvent<HTMLInputElement>) => setName(e.target.value)`. When possible, I let TypeScript infer the event type from an inline JSX handler.

<a id="qa-15-013"></a>
### 15.13. How do you type `useContext` so consumers get a properly-typed value (and a helpful error if used outside the Provider)?

**Interview answer:** Type the context as `createContext<ContextType | undefined>(undefined)`, then write a custom `useMyContext()` Hook that throws a clear error if the value is `undefined`, letting consumers use a properly-narrowed, non-nullable type.

<a id="qa-15-014"></a>
### 15.14. How do you type `useRef` for a DOM node vs a mutable value?

**Interview answer:** For a DOM input, I use `const inputRef = useRef<HTMLInputElement>(null)`, because the element is not mounted at first and `current` may be null. For a mutable numeric value, I use `useRef<number>(0)`. Both persist across renders, but updating the ref does not trigger a re-render.

<a id="qa-15-015"></a>
### 15.15. How do you type `useState` when the initial value doesn't convey the full type?

**Interview answer:** When the initial value does not show the full type, I provide a generic, for example `useState<User | null>(null)`. That tells TypeScript the state can later hold a `User` object or `null`.

<a id="qa-15-016"></a>
### 15.16. How do you type a custom Hook's tuple return value?

**Interview answer:** If a custom Hook returns a fixed pair of values, I type it as a tuple rather than letting TypeScript infer a general array. For example, `function useToggle(): [boolean, () => void]` describes a boolean followed by a function. This ensures consumers get the right type when they destructure the result.

<a id="qa-15-017"></a>
### 15.17. How do you type a reducer function and its actions for `useReducer`?

**Interview answer:** Define a discriminated union for actions (`type Action = { type: 'increment' } | { type: 'set'; payload: number }`), then `function reducer(state: State, action: Action): State`, letting TypeScript narrow `action.payload` based on `action.type` inside each case.

<a id="qa-15-018"></a>
### 15.18. How do you type a `forwardRef` component?

**Interview answer:** In TypeScript, older React projects can type forwarded refs with `forwardRef<HTMLInputElement, Props>(...)`. This makes the forwarded DOM node and props type-safe. In React 19, a function component can also type and accept `ref` directly as a prop.

<a id="qa-15-019"></a>
### 15.19. How React PropTypes allow different types for one prop?

**Interview answer:** PropTypes supports several possible types for one prop through `PropTypes.oneOfType`. For example, `PropTypes.oneOfType([PropTypes.string, PropTypes.number])` allows either a string or a number. In TypeScript code, I normally use a union type instead.

<a id="qa-15-020"></a>
### 15.20. What is `satisfies` and how is it useful for typing component configuration objects?

**Interview answer:** `satisfies` checks a value against a type without widening/changing the value's inferred type, useful for config objects (e.g., a theme or route map) where you want both validation against a shape and precise literal-type inference preserved for later use.

<a id="qa-15-021"></a>
### 15.21. What is Flow?

**Interview answer:** Flow is a static type checker designed to find type errors in JavaScript. Flow types can express much more fine-grained distinctions than traditional type systems. For example, Flow helps you catch errors involving `null`, unlike most type systems.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-16"></a>
## 16. Styling in React

*15 questions — [Back to contents](#contents)*

<a id="qa-16-001"></a>
### 16.1. How would you use Font Awesome icons in React?

**Interview answer:** I can install a React icon library, such as Font Awesome's React package, import the required icon component, and render it in JSX. I prefer importing only the icons I use to avoid unnecessarily large bundles.

<a id="qa-16-002"></a>
### 16.2. Is it recommended to use CSS In JS technique in React?

**Interview answer:** CSS-in-JS is one valid styling approach, but it is not automatically the best choice. It can help with component-scoped styles and prop-based variants; some runtime approaches add JavaScript overhead and SSR complexity. For a new app I compare CSS Modules, utility CSS such as Tailwind, and CSS-in-JS based on the design system and rendering requirements.

<a id="qa-16-003"></a>
### 16.3. What is a "zero-runtime" CSS-in-JS library (e.g., vanilla-extract, Panda CSS)? How does it differ from `styled-components`?

**Interview answer:** It extracts styles to static CSS files at build time rather than injecting `<style>` tags at runtime, giving CSS-in-JS's developer ergonomics (colocated, typed styles) without the runtime performance cost.

<a id="qa-16-004"></a>
### 16.4. What is CSS-in-JS? Trade-offs vs traditional CSS?

**Interview answer:** CSS-in-JS lets me define styles in JavaScript, sometimes using component props for variants. Libraries such as Emotion and styled-components offer component-level styling, but runtime implementations can increase JavaScript work and require careful SSR setup. CSS Modules or utility CSS may be simpler when runtime dynamic styling is not needed.

<a id="qa-16-005"></a>
### 16.5. What is Tailwind CSS? How does it differ from CSS-in-JS?

**Interview answer:** Tailwind CSS provides utility classes such as `flex`, `p-4`, and `text-sm` that I combine directly in JSX. Unlike many runtime CSS-in-JS approaches, Tailwind generates CSS during the build process. It is fast for consistent UI work, but I still extract reusable components and tokens so long class lists do not become hard to maintain.

<a id="qa-16-006"></a>
### 16.6. What is the purpose of a `postcss`/Tailwind build step in a React project, and how does it interact with the bundler?

**Interview answer:** PostCSS (often running Tailwind's engine) transforms authored CSS — expanding utility classes, adding vendor prefixes (autoprefixer), purging unused classes — before the bundler includes the resulting CSS in the final build output.

<a id="qa-16-007"></a>
### 16.7. How would you use styles in React?

**Interview answer:** The `style` attribute accepts a JavaScript object with camelCased properties rather than a CSS string. This is consistent with the DOM style JavaScript property, is more efficient, and prevents XSS security holes. Style keys are camelCased in order to be consistent with accessing the properties on DOM nodes in JavaScript (e.g. `node.style.backgroundImage`).

<a id="qa-16-008"></a>
### 16.8. How do you keep component styling encapsulated and themeable?

**Interview answer:** I scope styles with CSS Modules, utility CSS, or a well-structured component library so one component's styles do not accidentally affect others. For theme support I prefer shared design tokens and CSS variables, such as `--surface-color`, rather than hardcoding colors in every component. This makes dark mode and design updates easier.

<a id="qa-16-009"></a>
### 16.9. What are CSS Modules? How do they prevent collisions?

**Interview answer:** CSS Modules give classes local scope by generating unique names during the build. I import a stylesheet as an object, such as `import styles from './Card.module.css'`, and write `className={styles.card}`. This avoids accidental style collisions between components without requiring a runtime styling library.

<a id="qa-16-010"></a>
### 16.10. How would you add Bootstrap to a React application?

**Interview answer:** Bootstrap can be added to your React app in a three possible ways, Using the Bootstrap CDN: This is the easiest way to add bootstrap. Add both bootstrap CSS and JS resources in a head tag. Bootstrap as Dependency: If you are using a build tool or a module bundler such as Webpack, then this is the preferred option for adding Bootstrap to your React application React Bootstrap Package: In this case, you can add Bootstrap to our React app is by using a package that has rebuilt Bootstrap components to work particularly as React components.

<a id="qa-16-011"></a>
### 16.11. Give an example of Styled Components?

**Interview answer:** Lets create `<Title>` and `<Wrapper>` components with specific styles for each. These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

<a id="qa-16-012"></a>
### 16.12. What are the different ways to style a React component?

**Interview answer:** I can style React with plain CSS, CSS Modules, utility classes such as Tailwind, inline styles, or CSS-in-JS. I choose based on the team’s design system, maintainability, and runtime needs.

<a id="qa-16-013"></a>
### 16.13. What is the benefit of styles modules?

**Interview answer:** It is recommended to avoid hard coding style values in components. Any values that are likely to be used across different UI components should be extracted into their own modules. For example, these styles could be extracted into a separate component: ``javascript export const colors = { white, black, blue, }; export const space = **.

<a id="qa-16-014"></a>
### 16.14. How do you theme a React app (light/dark mode) cleanly?

**Interview answer:** Define theme values as CSS custom properties or a theme object, toggle a root-level class/attribute (`data-theme="dark"`) or Context provider, and have styled components/CSS reference the theme tokens rather than hardcoded values.

<a id="qa-16-015"></a>
### 16.15. How would you implement theme customization in React?

**Interview answer:** I can store the chosen theme in state or Context, then apply a class or `data-theme` attribute to the app. CSS variables let me switch colors without changing each component.

---

<a id="section-17"></a>
## 17. Security & Accessibility

*19 questions — [Back to contents](#contents)*

<a id="qa-17-001"></a>
### 17.1. What tools help check React app accessibility?

**Interview answer:** I combine automated and manual accessibility checks. ESLint rules catch many JSX mistakes early; tools such as axe and Lighthouse inspect the rendered DOM. For important workflows I test keyboard-only navigation, focus indicators, contrast, and a screen reader like NVDA or VoiceOver. No single automated tool proves that a UI is fully accessible.

<a id="qa-17-002"></a>
### 17.2. Why does accessibility matter in React apps?

**Interview answer:** Accessibility makes React interfaces usable with keyboards, screen readers, and other assistive technology. React itself does not replace semantic HTML rules. SPAs need extra care with focus management and page announcements after client-side navigation. I use native controls first and test essential flows with real keyboard interaction.

<a id="qa-17-003"></a>
### 17.3. How do you securely store auth tokens in a React app?

**Interview answer:** HttpOnly cookies: cannot be accessed by JS, protected from XSS (but vulnerable to CSRF). `localStorage`: accessible to JS, vulnerable to XSS. Best practice: HttpOnly cookies + CSRF tokens, not `localStorage` for sensitive tokens.

<a id="qa-17-004"></a>
### 17.4. How would you use innerHTML in React?

**Interview answer:** The `dangerouslySetInnerHTML` attribute is React's replacement for using `innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a `__html` object as key and HTML text as value. In this example MyComponent uses `dangerouslySetInnerHTML` attribute for setting HTML markup.

<a id="qa-17-005"></a>
### 17.5. How does React help prevent XSS, and what risks remain?

**Interview answer:** React escapes ordinary JSX text values, which prevents many simple XSS attacks. XSS can still happen if I insert untrusted HTML with `dangerouslySetInnerHTML`, accept unsafe URLs, or use a third-party library that writes to the DOM. I avoid raw HTML when possible and use a trusted sanitizer and strict Content Security Policy where appropriate.

**Optional coding illustration:**
```jsx
<div>{userInput}</div> // React escapes the string
// Avoid inserting untrusted HTML with dangerouslySetInnerHTML.
```

<a id="qa-17-006"></a>
### 17.6. What are ARIA roles and attributes?

**Interview answer:** ARIA roles and attributes help assistive technology understand custom UI. For example, `aria-expanded` communicates whether a dropdown is open, and `aria-describedby` links an input to its help text. I prefer native semantic elements such as `<button>` and `<label>` first, because ARIA does not automatically add keyboard behavior.

<a id="qa-17-007"></a>
### 17.7. What is dangerouslySetInnerHTML, and what are its security risks?

**Interview answer:** `dangerouslySetInnerHTML` inserts a raw HTML string into the DOM. It is useful only when rendering trusted or carefully sanitized HTML, such as rich-text content. I avoid passing user input directly because it can create cross-site scripting vulnerabilities.

<a id="qa-17-008"></a>
### 17.8. What is `eslint-plugin-jsx-a11y`? What does it catch?

**Interview answer:** `eslint-plugin-jsx-a11y` statically checks JSX for common accessibility issues, such as images without useful alt text, invalid ARIA attributes, and clickable elements without keyboard support. It catches problems early in the editor and CI pipeline. It does not replace actual keyboard and screen-reader testing.

<a id="qa-17-009"></a>
### 17.9. What is a CSRF attack and how do you prevent it in React apps?

**Interview answer:** Cross-Site Request Forgery tricks a user's browser into making authenticated requests to your API. Prevent with CSRF tokens in headers, `SameSite` cookie attribute, and not relying solely on cookies for auth.

<a id="qa-17-010"></a>
### 17.10. What is color contrast, and how do you verify a React app meets WCAG requirements?

**Interview answer:** Sufficient contrast between text and background colors for readability, especially for low-vision users. Verify with tools like the axe DevTools extension, Lighthouse's accessibility audit, or a contrast-checker against WCAG AA/AAA thresholds.

<a id="qa-17-011"></a>
### 17.11. Why does accessibility matter in React SPAs specifically?

**Interview answer:** In a React SPA, changing routes does not always reload the document, so browser focus and page-title behavior may not reset automatically. I update the document title, move focus to the new page's main heading when appropriate, and provide skip links and semantic landmarks. I check these behaviors with a keyboard and screen reader.

<a id="qa-17-012"></a>
### 17.12. How do you prevent a dependency supply-chain attack from affecting a React app?

**Interview answer:** Pin exact dependency versions (lockfile committed), run `npm audit`/Snyk in CI, review new dependencies before adding them, and consider a private registry proxy that vets packages.

<a id="qa-17-013"></a>
### 17.13. How do you prevent clickjacking in a React app?

**Interview answer:** For Web Components with imperative methods, I attach a React ref to their DOM node and call the method through `ref.current` after mount. A small wrapper component helps keep that integration reusable.

<a id="qa-17-014"></a>
### 17.14. How would you implement role-based access control (RBAC) in React?

**Interview answer:** Store roles in an auth Context; a `usePermissions`/`useCan` hook checks role against required permissions; wrap protected UI or routes with conditional rendering/loader-level redirects — but always enforce authorization server-side too, since client checks are only a UX convenience.

<a id="qa-17-015"></a>
### 17.15. What is a Subresource Integrity (SRI) hash, and when would a React app use one?

**Interview answer:** A hash attribute on a `<script>`/`<link>` tag verifying a CDN-loaded file hasn't been tampered with; relevant when loading a library (e.g., via a CDN `<script>` tag in an HTML template) from a third-party host outside your build pipeline.

<a id="qa-17-016"></a>
### 17.16. What is the risk of exposing API keys/secrets in a client-side React bundle?

**Interview answer:** Anything bundled for the browser (including `NEXT_PUBLIC_`-prefixed or hardcoded values) is visible to anyone inspecting the JS; secrets must stay server-side, with the client calling a backend proxy instead.

<a id="qa-17-017"></a>
### 17.17. What is a focus trap?

**Interview answer:** Confines keyboard focus within a modal/dialog so Tab doesn't reach content behind it. Required for accessible modals. Libraries: `focus-trap-react`, `@radix-ui/react-dialog` handle this automatically.

<a id="qa-17-018"></a>
### 17.18. What is a skip link?

**Interview answer:** A visually hidden link at the top of the page that becomes visible on focus and links to the main content area. Allows keyboard users to skip repetitive navigation. Required for WCAG 2.1 AA compliance.

<a id="qa-17-019"></a>
### 17.19. Can you explain user Authentication and Session Management?

**Interview answer:** I keep authentication state in a shared provider or a dedicated auth library, protect routes in the UI, and validate every sensitive request on the backend. I prefer secure session cookies where appropriate and never treat client-side route guards as authorization.

---

<a id="section-18"></a>
## 18. React Ecosystem & Build Tools

*35 questions — [Back to contents](#contents)*

<a id="qa-18-001"></a>
### 18.1. How would you access current locale with React Intl?

**Interview answer:** With React Intl, I can read the current locale through `useIntl()` and its returned `intl.locale` value. In older code I may see `injectIntl`, but Hooks are usually simpler in modern function components.

<a id="qa-18-002"></a>
### 18.2. How would you format a date using React Intl?

**Interview answer:** React Intl provides `formatDate` through the `useIntl()` API. I call it with a date and formatting options so the result matches the current locale, such as day, month, and year order.

<a id="qa-18-003"></a>
### 18.3. How would you use FormattedMessage as a placeholder with React Intl?

**Interview answer:** The ` ` components from `react-intl` return elements, not plain text, so they can't be used for placeholders, alt text, etc. In that case, you should use lower level API `formatMessage()`. You can inject the `intl` object into your component using `injectIntl()` higher-order component and then format the message using `formatMessage()` available on that object. ****.

<a id="qa-18-004"></a>
### 18.4. How can Polymer web components be used in a React app?

**Interview answer:** You need to follow below steps to use Polymer in React, Create a Polymer element: Create the Polymer component HTML tag by importing it in a HTML document, e.g. import it in the `index.html` of your React application: Use that element in the JSX file: ****.

<a id="qa-18-005"></a>
### 18.5. How would you implement internationalization (i18n) in React?

**Interview answer:** `react-intl` or `react-i18next`. Extract all strings to message catalogs. `useIntl()` hook for formatting. Support RTL layouts (`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies via Intl API. Lazy load language bundles.

<a id="qa-18-006"></a>
### 18.6. Can you explain a/B Testing: How to implement A/B testing without affecting current users?

**Interview answer:** Implementation: Use a feature flag service (e.g., LaunchDarkly, Optimizely) that can assign users to variants. Variant assignment – deterministic based on user ID or cookie, so users see consistent experience. Initialization – fetch assignment early (e.g., on app boot) and store in context. Render conditionally based on variant. Avoid layout shift – ensure that variant components have the same dimensions as the control.

<a id="qa-18-007"></a>
### 18.7. How does tree shaking work in modern bundlers?

**Interview answer:** Tree shaking is a dead‑code elimination technique that removes unused exports from the final bundle. Bundlers like Webpack and Rollup analyze the import/export graph and only include code that is actually used. This relies on ES modules being statically analyzable.

<a id="qa-18-008"></a>
### 18.8. How would you avoid using relative path imports in create-React-app?

**Interview answer:** Create a file called `.env` in the project root and write the import path: After that restart the development server. Now you should be able to import anything inside `src/app` without relative paths.

<a id="qa-18-009"></a>
### 18.9. Can you explain webpack vs Vite vs esbuild/SWC for a React app?

**Interview answer:** Webpack is a highly configurable bundler; Vite provides a fast development server using native module loading and builds optimized production bundles. esbuild and SWC are fast compiler tools often used inside larger build systems. I choose based on project integrations, build speed, and production requirements rather than assuming a tool is always fastest.

<a id="qa-18-010"></a>
### 18.10. What environment variables are safe to expose in a React app?

**Interview answer:** Only non-secret config: API base URLs, feature flags, analytics IDs. Never: API secret keys, database credentials, private keys. Vite exposes `VITE_` prefixed vars; CRA exposes `REACT_APP_` prefixed vars – all are visible in the bundle.

<a id="qa-18-011"></a>
### 18.11. What is the difference between a bundler and a compiler/transpiler in the React toolchain (e.g., Webpack vs Babel/SWC)?

**Interview answer:** A compiler/transpiler (Babel, SWC) transforms source syntax (JSX, newer JS, TypeScript) into code the target environment understands. A bundler (Webpack, Rollup, Vite's build step) combines many modules/files into optimized output bundles, handling code splitting, asset processing, and dependency graphs — they're complementary, often used together.

<a id="qa-18-012"></a>
### 18.12. How do you implement feature flags in a React application?

**Interview answer:** I integrate feature flags through a provider or SDK and expose a small custom Hook, such as `useFeatureFlag('newDashboard')`. The component renders a safe default while flags load and reacts to updates. Flags can control rollouts or experiments, but I still enforce permissions and security checks on the backend; a client flag is not an authorization boundary.

<a id="qa-18-013"></a>
### 18.13. What are the main features of React Intl?

**Interview answer:** React Intl helps format translated messages, dates, times, numbers, currencies, and plural forms. I use it to make an application consistent across languages and regions without manually formatting every value.

<a id="qa-18-014"></a>
### 18.14. What is the purpose of registerServiceWorker in React?

**Interview answer:** React creates a service worker for you without any configuration by default. The service worker is a web API that helps you cache your assets and other files so that when the user is offline or on a slow network, he/she can still see results on the screen, as such, it helps you build a better user experience, that's what you should know about service worker for now.

<a id="qa-18-015"></a>
### 18.15. How would you debug your React Native?

**Interview answer:** Press `Command + D` and a webpage should open up at `http://localhost:8081/debugger-ui`. Enable *Pause On Caught Exceptions* for a better debugging experience. Press `Command + Option + I` to open the Chrome Developer tools, or open it via `View` -> `Developer` -> `Developer Tools`. You should now be able to debug as you normally would.

<a id="qa-18-016"></a>
### 18.16. How would you do logging in React Native?

**Interview answer:** In React Native I use the development logging and debugging tools provided by the current React Native and Expo toolchain, rather than relying on obsolete console instructions tied to very old versions. I can inspect logs, network activity, and stack traces, then use a crash-reporting service for production issues. I avoid logging secrets or personal data.

<a id="qa-18-017"></a>
### 18.17. What is blue-green deployment, and how would you use it for a frontend?

**Interview answer:** Blue-green deployment keeps the current version running in one environment and prepares a new version in another. After testing the new version, I switch traffic to it. If something fails, I can route users back to the previous environment.

<a id="qa-18-018"></a>
### 18.18. What compatibility issues should you consider when using React in different environments?

**Interview answer:** React can render to different environments, but a feature that depends on browser APIs must be guarded when used in server rendering or React Native. I check compatibility before using DOM-specific code.

<a id="qa-18-019"></a>
### 18.19. What checks should run in a React application’s build and test pipeline?

**Interview answer:** My CI pipeline runs linting, TypeScript checks, unit and integration tests, and a production build. For critical features, I add end-to-end tests and deploy the verified build to staging.

<a id="qa-18-020"></a>
### 18.20. How does the React Hooks ESLint plugin help prevent Hook mistakes?

**Interview answer:** The ESLint Hooks plugin checks rules such as calling Hooks in the same order and providing required dependencies for effects. I keep those rules enabled so mistakes are caught during development instead of at runtime.

<a id="qa-18-021"></a>
### 18.21. What are the popular React-specific linters?

**Interview answer:** ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types. Another popular plugin is `eslint-plugin-jsx-a11y`, which will help fix common issues with accessibility.

<a id="qa-18-022"></a>
### 18.22. What is `TestRenderer` package in React?

**Interview answer:** This package provides a renderer that can be used to render components to pure JavaScript objects, without depending on the DOM or a native mobile environment. This package makes it easy to grab a snapshot of the platform view hierarchy (similar to a DOM tree) rendered by a ReactDOM or React Native without using a browser or `jsdom`.

<a id="qa-18-023"></a>
### 18.23. What is code-splitting?

**Interview answer:** Code splitting breaks a large JavaScript bundle into smaller pieces that load when needed. In React, I can use `React.lazy` with a dynamic `import()` and wrap the component in `Suspense` to show a fallback while its code loads.

<a id="qa-18-024"></a>
### 18.24. What is the purpose of ESLint and Prettier in a React project?

**Interview answer:** ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other -- ESLint for rules, Prettier for style.

<a id="qa-18-025"></a>
### 18.25. What is the difference between React Native and React?

**Interview answer:** React is a JavaScript library, supporting both front end web and being run on the server, for building user interfaces and web applications. React Native is a mobile framework that compiles to native app components, allowing you to build native mobile applications (iOS, Android, and Windows) in JavaScript that allows you to use React to build your components, and implements React under the hood.

<a id="qa-18-026"></a>
### 18.26. What is the role of Babel in a React project?

**Interview answer:** Transpiles modern JS and JSX to browser-compatible JS. Plugins transform JSX to `createElement` calls. In Vite projects, esbuild handles transpilation faster; Babel is less common in new setups.

<a id="qa-18-027"></a>
### 18.27. How would you roll out a new frontend release to production safely?

**Interview answer:** I release gradually using a canary or rolling deployment, monitor errors and user metrics, and have a rollback plan. I also consider CDN cache invalidation and compatibility with the backend API.

<a id="qa-18-028"></a>
### 18.28. Can you explain library Upgrade: A component breaks when upgrading a library version -- how do you manage dependencies?

**Interview answer:** Approach: 1. Read release notes and changelogs carefully for breaking changes. 2. Test in isolation -- create a branch, upgrade the library, run tests, and manually test affected components. 3. **Use dependency management tools** -- `npm outdated` to see which libraries can be upgraded. `npm audit` for security. 4.

<a id="qa-18-029"></a>
### 18.29. How do you handle localization and internationalization in React?

**Interview answer:** Internationalization makes an app work across languages and regions; localization supplies translations and local formats. In React, I use translation resources and locale-aware formatting for dates, numbers, and currency.

<a id="qa-18-030"></a>
### 18.30. What should you expect in a React machine-coding interview round?

**Interview answer:** In a machine-coding round, I may be asked to build a small feature such as a todo app, searchable table, or modal within a limited time. I explain my component structure, manage state clearly, handle edge cases, and keep the code testable.

<a id="qa-18-031"></a>
### 18.31. How would you roll back a faulty frontend release?

**Interview answer:** I would switch traffic back to the last stable build or redeploy the previous version. Then I would check monitoring and logs, identify the root cause, and prepare a tested fix.

<a id="qa-18-032"></a>
### 18.32. What is chaos engineering for frontend?

**Interview answer:** Chaos engineering is the practice of intentionally introducing failures to test system resilience. For frontend, it means simulating network issues, slow responses, API errors, or resource constraints to ensure the UI degrades gracefully. Examples: Network throttling – simulate slow 3G to test lazy loading and timeouts. API failures – mock 5xx responses and ensure error states appear.

<a id="qa-18-033"></a>
### 18.33. What are the features of create React app?

**Interview answer:** Create React App used to provide a ready-made React build setup with development scripts, testing, bundling, and production builds. It is now a legacy approach; for new work I would choose a maintained framework or a tool like Vite.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-18-034"></a>
### 18.34. Why is Create React App deprecated, and what should new projects use?

**Interview answer:** Create React App is deprecated for new apps. Its older tooling and limited integration for routing, SSR, and other app features made maintenance harder. For a simple client-rendered React application, I would start with a maintained build tool such as Vite. For a full-stack or server-rendered application, I would consider a React framework.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-18-035"></a>
### 18.35. What is Vite, and why is it preferred over Create React App today?

**Interview answer:** Vite uses native ES modules for near-instant dev-server startup and Rollup for optimized production builds; CRA (webpack-based, no longer actively maintained) is significantly slower in dev and is no longer recommended for new projects — Vite (SPAs) or Next.js (SSR/full-stack) are the modern defaults.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-19"></a>
## 19. Legacy, Ecosystem & Additional Concepts

*9 questions — [Back to contents](#contents)*

<a id="qa-19-001"></a>
### 19.1. How do you access imperative API of web components?

**Interview answer:** Web Components may expose imperative methods through their DOM elements. In React I attach a ref to the custom element, then call the method once the element exists, such as `widgetRef.current?.open()`. For repeated use, I can wrap the Web Component in a React component with a typed interface. I also listen for custom events according to the component's API.

<a id="qa-19-002"></a>
### 19.2. How would you programmatically trigger click event in React?

**Interview answer:** You could use the ref prop to acquire a reference to the underlying `HTMLInputElement` object through a callback, store the reference as a class property, then use that reference to later trigger a click from your event handlers using the `HTMLElement.click` method. This can be done in two steps: Create ref in render method: Apply click event in your event handler.

<a id="qa-19-003"></a>
### 19.3. What are capture phase events?

**Interview answer:** React event handlers support capture and bubble phases. A capture handler, such as `onClickCapture`, runs on the way down the event path before bubbling handlers. I use it only when I need to observe or coordinate an event early.

<a id="qa-19-004"></a>
### 19.4. What are the advantages of React over Vue.js?

**Interview answer:** React and Vue can both build modern frontends. React offers a large ecosystem, flexible component composition, and a strong hiring and library community. Vue can be easier to adopt for some teams because of its integrated conventions. I would choose based on the team, requirements, and ecosystem rather than claiming one is always better.

<a id="qa-19-005"></a>
### 19.5. What does MVW mean, and is it useful for modern React interviews?

**Interview answer:** MVW, or Model–View–Whatever, is a broad historical label for JavaScript UI architectures. Its drawbacks depend on the specific framework, not the pattern name. In a React interview I would focus on the concrete trade-off: separating data and presentation helps maintainability, but poorly organized shared state and manual DOM updates can increase complexity. This is a low-priority legacy topic.

<a id="qa-19-006"></a>
### 19.6. What happened to event pooling?

**Interview answer:** In React 16 and earlier, `SyntheticEvent` objects were pooled and reused – accessing event properties asynchronously returned null. React 17 removed pooling. `event.persist()` is no longer needed.

<a id="qa-19-007"></a>
### 19.7. When do we need a Higher Order Component?

**Interview answer:** A higher-order component is useful when I need to wrap multiple existing components with the same behavior, especially in older codebases. A typical example is an authentication wrapper. In modern function components I often prefer a custom Hook, because it shares logic without adding layers to the component tree.

<a id="qa-19-008"></a>
### 19.8. What are React Mixins?

**Interview answer:** String refs such as `ref='myInput'` are a legacy pattern and should not be used in new React code. I use `useRef` or callback refs so the reference is explicit and compatible with function components. Legacy class code may contain string refs, but they are not a recommended modern API.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-19-009"></a>
### 19.9. Why is ReactDOM.render considered a legacy API?

**Interview answer:** `ReactDOM.render()` is a legacy mounting API from older React versions. Modern client-rendered React uses `createRoot(container).render(<App />)` from `react-dom/client`. If HTML was rendered on the server, I use `hydrateRoot` instead. I would recognize `ReactDOM.render` when maintaining legacy projects but would not choose it for a new app.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

## Official references

Use these for version-sensitive topics and deeper examples.
- [React 19 official release](https://react.dev/blog/2024/12/05/react-19)
- [React Hooks and built-in APIs](https://react.dev/reference/react/hooks)
- [React render and commit](https://react.dev/learn/render-and-commit)
- [React Strict Mode](https://react.dev/reference/react/StrictMode)
- [React useEffect](https://react.dev/reference/react/useEffect)
- [React useOptimistic](https://react.dev/reference/react/useOptimistic)
- [React useActionState](https://react.dev/reference/react/useActionState)
- [React useFormStatus](https://react.dev/reference/react-dom/hooks/useFormStatus)
- [React 19 upgrade guide](https://react.dev/blog/2024/04/25/react-19-upgrade-guide)
- [Sunsetting Create React App](https://react.dev/blog/2025/02/14/sunsetting-create-react-app)
- [React Compiler v1.0](https://react.dev/blog/2025/10/07/react-compiler-1)
- [React Router documentation](https://reactrouter.com/start/modes)
