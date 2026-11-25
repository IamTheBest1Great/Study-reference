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

**Interview answer:** Yes. JSX is optional in React. We can create elements directly with `React.createElement()`, for example `React.createElement('h1', null, 'Hello')`. JSX is simply a more readable syntax for describing the same UI, so I prefer it in real projects.

<a id="qa-01-002"></a>
### 1.2. How would you add a page title and meta tags in a React application?

**Interview answer:** In React 19, I can render `<title>` and `<meta>` directly inside a component, and React places supported metadata in the document head. In older versions, I would use React Helmet or a framework's metadata API. For SEO, I would also consider server rendering or prerendering rather than relying only on client-side metadata.

<a id="qa-01-003"></a>
### 1.3. Does the cost of inline arrow functions in JSX always matter?

**Interview answer:** No. Creating an inline arrow function on each render is usually inexpensive. It becomes relevant when the function is passed to a memoized child or used as a Hook dependency, because its reference changes. I would profile the application first and use `useCallback` when a stable reference provides a real benefit.

<a id="qa-01-004"></a>
### 1.4. How does React keep DOM updates efficient?

**Interview answer:** React keeps DOM updates efficient through reconciliation. When state or props change, React calculates the next UI, compares it with the previous representation, and commits only the required changes to the real DOM. Batching can also reduce rendering work. This does not mean React is always faster than direct DOM manipulation.

<a id="qa-01-005"></a>
### 1.5. How can we find the version of React at runtime in the browser?

**Interview answer:** I can check the React version loaded by my application using `React.version`, or by importing `version` from `react`. This is useful when investigating compatibility problems or confirming which React runtime is actually being used.

<a id="qa-01-006"></a>
### 1.6. How do you write comments in JSX?

**Interview answer:** Inside JSX, I use a JavaScript block comment inside curly braces, such as `{/* Comment */}`. Outside the JSX markup, normal JavaScript comments (`//` or `/* ... */`) work as usual.

<a id="qa-01-007"></a>
### 1.7. How do style objects work in JSX (`style={{...}}`)?

**Interview answer:** React accepts inline styles as a JavaScript object. The outer braces enter JavaScript from JSX, and the inner braces define the object. CSS property names are generally camelCase, such as `backgroundColor`. React adds `px` to many numeric values, but properties like `opacity`, `zIndex`, and `fontWeight` are unitless.

<a id="qa-01-008"></a>
### 1.8. How do you print falsy values in JSX?

**Interview answer:** React does not visibly render booleans, `null`, or `undefined`. To display those values, I can convert them to strings with `String(value)`. Numeric zero is different: React renders `0`, even though it is falsy in JavaScript. An empty string produces no visible text.

<a id="qa-01-009"></a>
### 1.9. How would you loop inside JSX?

**Interview answer:** I normally use `map()` to transform an array into JSX elements. I give each sibling a stable, unique key, usually a database ID, so React can match items during reconciliation. This is particularly important when a list can be inserted into, deleted from, or reordered.

**Optional coding illustration:**
```jsx
const items = [{ id: 1, name: 'Asha' }];
return <ul>{items.map(item => <li key={item.id}>{item.name}</li>)}</ul>;
```

<a id="qa-01-010"></a>
### 1.10. What is the Virtual DOM, and how does React update the UI?

**Interview answer:** The Virtual DOM is React's in-memory representation of the desired UI. When state or props change, React renders a new representation, reconciles it with the previous tree, and commits the necessary changes to the real DOM. A component re-render does not necessarily mean its DOM changes. This makes UI updates predictable without manually manipulating DOM nodes.

<a id="qa-01-011"></a>
### 1.11. How is event handling in React different from plain HTML?

**Interview answer:** React event handlers use camelCase names such as `onClick` and receive JavaScript functions rather than HTML event-handler strings. React also provides a consistent event interface with methods like `preventDefault()` and `stopPropagation()`. For example, I use `onClick={handleClick}` to run a handler when the user clicks.

<a id="qa-01-012"></a>
### 1.12. How does JSX help prevent injection attacks?

**Interview answer:** React escapes text values inserted into JSX by default. If untrusted input contains HTML or script markup, React normally displays it as text rather than interpreting it as executable HTML. This helps prevent XSS, but it is not complete protection. I avoid unsafe HTML insertion and sanitize any HTML that must be rendered.

<a id="qa-01-013"></a>
### 1.13. How do you pass an event handler or arguments to a JSX event?

**Interview answer:** I pass the handler reference, such as `onClick={handleSave}`, so React calls it when the event occurs. When I need to supply an argument, I use an arrow function, such as `onClick={() => handleSave(id)}`. Calling `handleSave(id)` directly would execute it during rendering instead.

**Optional coding illustration:**
```jsx
<button onClick={handleSave}>Save</button>
<button onClick={() => deleteUser(user.id)}>Delete</button>
```

<a id="qa-01-014"></a>
### 1.14. How do you associate a label with an input in JSX?

**Interview answer:** I use `htmlFor` on a JSX label and give the corresponding input the same `id`. For example, `<label htmlFor="email">Email</label>` connects to `<input id="email" />`. This improves accessibility and lets users focus the input by clicking its label.

<a id="qa-01-015"></a>
### 1.15. What is React, and why would you use it?

**Interview answer:** React is an open-source JavaScript library for building interactive user interfaces using reusable components. It follows a declarative approach: I describe how the UI should look based on props and state, and React manages the necessary updates. I use it because component composition, one-way data flow, and its ecosystem make complex applications easier to develop and maintain.

<a id="qa-01-016"></a>
### 1.16. Why do React component names begin with a capital letter?

**Interview answer:** Capitalization tells JSX whether a tag is a DOM element or a component reference. A lowercase tag such as `<div>` is treated as a host element, while `<UserCard>` refers to a custom React component. That is why I use PascalCase for component names.

<a id="qa-01-017"></a>
### 1.17. What are the rules of JSX?

**Interview answer:** JSX requires adjacent sibling elements to be grouped into a single expression, usually with a parent element or Fragment. Tags must be closed, most DOM properties use camelCase, and JavaScript expressions go inside curly braces. For HTML elements I use `className` and `htmlFor` instead of `class` and `for`.

<a id="qa-01-018"></a>
### 1.18. What is JSX, and how does it become browser-readable JavaScript?

**Interview answer:** JSX is a JavaScript syntax extension that allows HTML-like markup inside JavaScript. Browsers do not understand it directly, so a build tool transforms it into JavaScript that creates React elements. The classic transform uses `React.createElement()`, while the modern transform uses functions from `react/jsx-runtime`.

<a id="qa-01-019"></a>
### 1.19. What is React Dev Tools?

**Interview answer:** React DevTools helps me inspect a React application's component tree, props, state, and Hooks. Its Components panel is useful for debugging UI behavior, while its Profiler helps identify expensive renders and verify performance improvements.

<a id="qa-01-020"></a>
### 1.20. What is React Intl?

**Interview answer:** React Intl is an internationalization library that helps applications support different languages and regional formats. I use it to translate messages, format dates, numbers and currencies, and handle pluralization based on the user's locale rather than hardcoding formatting rules.

<a id="qa-01-021"></a>
### 1.21. What is React proptype array with shape?

**Interview answer:** `PropTypes.arrayOf()` validates the elements of an array, and `PropTypes.shape()` describes an object's expected properties. In older React applications, I can combine them as `PropTypes.arrayOf(PropTypes.shape({ id: PropTypes.number.isRequired }))`. React 19 removed built-in prop-type checking for function components. I prefer TypeScript for static typing and separate runtime validation for untrusted API data.

<a id="qa-01-022"></a>
### 1.22. What is React scripts?

**Interview answer:** `react-scripts` is the package used by Create React App to handle development, testing, and production builds without manually configuring tools like Webpack and Babel. Typical commands are `npm start`, `npm test`, and `npm run build`. For new applications, I would prefer Vite or a suitable maintained React framework.

<a id="qa-01-023"></a>
### 1.23. How are the render phase and commit phase different in React?

**Interview answer:** The render phase calculates what the UI should look like and determines the necessary changes, without mutating the DOM. The commit phase applies those changes and runs commit-related work such as layout effects. Rendering can be restarted or discarded; it does not guarantee a commit. This is why render logic must remain pure.

<a id="qa-01-024"></a>
### 1.24. How is the Virtual DOM different from the real DOM?

**Interview answer:** The real DOM is the browser's actual document tree. The Virtual DOM is React's in-memory representation of the UI. React compares rendered descriptions and commits the required changes to the real DOM. It does not replace the browser DOM or guarantee that every operation is faster.

<a id="qa-01-025"></a>
### 1.25. How are error boundaries different from JavaScript try/catch?

**Interview answer:** `try/catch` handles exceptions in the code it executes, such as an awaited request or an event handler. An error boundary handles errors thrown while rendering descendant React components or during their relevant lifecycle work, and displays fallback UI. I use both: boundaries for UI recovery and ordinary error handling for asynchronous operations and event handlers.

<a id="qa-01-026"></a>
### 1.26. How should React components be named for readability and debugging?

**Interview answer:** I use descriptive PascalCase names such as `UserProfile` or `IncidentTable`. These names make the component's purpose clear and help with React DevTools and stack traces. For anonymous wrappers or higher-order components, I can set `displayName` explicitly when the inferred name is not useful.

<a id="qa-01-027"></a>
### 1.27. Can you import an SVG file and use it as a React component?

**Interview answer:** Yes, if the build setup supports converting SVG files to components. Create React App has an SVG component import convention, and Vite can use a plugin such as SVGR. This lets me pass props to the SVG. If I only need a static image, importing its URL and rendering an `<img>` is simpler.

<a id="qa-01-028"></a>
### 1.28. Can I use web components in React application?

**Interview answer:** Yes. React can render browser custom elements such as `<my-widget>`. These Web Components have their own properties, attributes, and events. Integration is easier in React 19, but for older React versions I would check whether a ref or event adapter is needed for the component's API.

<a id="qa-01-029"></a>
### 1.29. Can you list down top websites or applications using React as front end framework?

**Interview answer:** Well-known historical examples of React adoption include Facebook, Instagram, Airbnb, and Pinterest. React is a useful choice for complex interactive interfaces because it encourages reusable components and declarative updates. I would not assume that every part of those products still uses the same frontend stack today.

<a id="qa-01-030"></a>
### 1.30. What happens during the initial render of a React component?

**Interview answer:** On an initial client render, React calls the root component and then its descendants to calculate the UI. It builds its internal representation of the tree, reconciles the work, and commits the required DOM nodes into the container. The browser then lays out and paints the interface. React does not start by copying an existing DOM tree.

<a id="qa-01-031"></a>
### 1.31. Can a React component render nothing? How would you do that?

**Interview answer:** Yes. A component can return `null` to produce no visible UI, for example `if (!isVisible) return null;`. This is useful for conditional rendering. Returning `null` does not itself unmount the component, so its own state can remain preserved.

<a id="qa-01-032"></a>
### 1.32. Render order of nested Parent → Child → GrandChild components?

**Interview answer:** In an ordinary initial render, React calls the Parent, then Child, then GrandChild because each component's result determines its descendants. React commits the finished work afterward. Component function call order is different from Effect and ref callback ordering, and development Strict Mode can introduce extra calls.

<a id="qa-01-033"></a>
### 1.33. Why does a React component need to return one root element?

**Interview answer:** A JavaScript function returns one value, so adjacent JSX elements must be grouped into one expression. I usually use a Fragment to avoid adding an unnecessary DOM wrapper. React does not actually require a single root DOM node: returning an array of elements with stable keys is also valid.

<a id="qa-01-034"></a>
### 1.34. What are inline conditional expressions?

**Interview answer:** Inline conditional expressions let me choose JSX based on a condition. I use a ternary for two alternatives and logical AND to display something only when a condition is true. For numeric conditions, I use an explicit comparison such as `items.length > 0 && <List />` to avoid rendering an unwanted zero.

**Optional coding illustration:**
```jsx
return isLoggedIn ? <Dashboard /> : <Login />;
```

<a id="qa-01-035"></a>
### 1.35. What is the difference between declarative and imperative programming in React?

**Interview answer:** Imperative programming describes each step needed to change the UI, such as locating a DOM element and setting its text. Declarative programming describes the desired result. React is declarative because I render UI from state and props, and React determines how to update the DOM when those values change.

<a id="qa-01-036"></a>
### 1.36. What is `createRoot()` and why replace `ReactDOM.render()`?

**Interview answer:** `createRoot()` is the client mounting API introduced in React 18. I create a root using `createRoot(container)` and then call `root.render(<App />)`. It enables the modern rendering architecture and features such as automatic batching and transitions. The older `ReactDOM.render()` API was removed in React 19.

<a id="qa-01-037"></a>
### 1.37. What is `React.createElement()`? What does it return?

**Interview answer:** `React.createElement(type, props, ...children)` creates a React element object describing what React should render. It contains the element's type, props, and other React metadata. It does not directly create a DOM node. JSX is a more readable way to describe React elements.

<a id="qa-01-038"></a>
### 1.38. What is a switching component, and when would you use one?

**Interview answer:** A switching component is a conditional rendering pattern, not a special React API. It selects one child component based on a value such as a status or selected tab. For example, a request status can select a loading view, error view, or results view. A switch statement or component map keeps those branches organized.

<a id="qa-01-039"></a>
### 1.39. What does React.lazy do, and when would you use it?

**Interview answer:** `React.lazy()` lets me defer loading a component's code until it is first needed for rendering. I use a dynamic import and wrap the lazy component in `Suspense` to show fallback UI while its module loads. This is useful for route-level code splitting and reducing the initial bundle, though the deferred load introduces its own latency.

<a id="qa-01-040"></a>
### 1.40. Why React uses `className` over `class` attribute?

**Interview answer:** React uses `className` for HTML elements because its DOM props generally follow JavaScript DOM property conventions. For example, `<div className="card" />` assigns the `card` CSS class. The resulting browser HTML still uses the `class` attribute.

<a id="qa-01-041"></a>
### 1.41. Why is `React-dom` a separate package from `React`?

**Interview answer:** The `react` package provides the core component model and APIs, while `react-dom` provides browser DOM rendering and server-rendering APIs. Separating React's platform-independent model from its renderers allows React Native and other renderers to use the same component concepts without depending on the browser DOM.

<a id="qa-01-042"></a>
### 1.42. What would be the common mistake of function being called every time the component renders?

**Interview answer:** The common mistake is writing `onClick={handleClick()}` instead of `onClick={handleClick}`. The first evaluates the function during rendering; the second passes its reference so React can invoke it on a click. If the incorrectly invoked function updates state, it can also create a render loop.

<a id="qa-01-043"></a>
### 1.43. Does React support all HTML attributes?

**Interview answer:** React supports standard HTML and SVG attributes along with many custom attributes, but JSX often uses DOM-style names such as `className`, `htmlFor`, and `tabIndex`. The `aria-*` and `data-*` attributes retain their usual spelling. I follow React's documented conventions when passing attributes.

<a id="qa-01-044"></a>
### 1.44. How do you update a previously rendered React element?

**Interview answer:** React elements are immutable descriptions of UI. Rather than modifying an existing element, I update the component's state or props so React can produce a new description and reconcile it with the previous one. At the root level, I can also call `root.render()` again, but component state is the usual approach.

<a id="qa-01-045"></a>
### 1.45. What types of values can a React component return?

**Interview answer:** A component can return valid React nodes, including JSX elements, strings, numbers, Fragments, arrays of nodes, portals, and empty values such as `null`. Boolean values and `undefined` produce no visible output in modern React. An ordinary JavaScript object is not a valid child.

<a id="qa-01-046"></a>
### 1.46. Should I learn ES6 before learning React?

**Interview answer:** ES6 is not strictly required before learning React, but a solid understanding of modern JavaScript makes React much easier to learn. I would focus on arrow functions, modules, destructuring, spread syntax, array methods, closures, promises, and async/await, because these are commonly used in components and Hooks.

<a id="qa-01-047"></a>
### 1.47. What are synthetic events in React?

**Interview answer:** A SyntheticEvent is React's wrapper around a native browser event. It provides a consistent interface for event properties and methods such as `preventDefault()` and `stopPropagation()`. I can access the original browser event through `nativeEvent`. React DOM no longer pools these event objects starting with React 17.

<a id="qa-01-048"></a>
### 1.48. What are the limitations of React?

**Interview answer:** React focuses on the UI rather than providing a complete application architecture. Depending on the project, I may need additional solutions for routing, data fetching, and state management. Its flexibility also means teams must establish consistent conventions. Poor state placement or excessive rendering can introduce performance problems, so architecture and profiling matter.

<a id="qa-01-049"></a>
### 1.49. What are the Pointer Events supported in React?

**Interview answer:** Pointer Events provide one event model for mouse, touch, and pen input. In React, I use handlers such as `onPointerDown`, `onPointerMove`, and `onPointerUp` for drag interactions or drawing tools. I also consider pointer capture, touch-action behavior, and keyboard accessibility.

<a id="qa-01-050"></a>
### 1.50. How can you format strings, numbers, and dates in a React app?

**Interview answer:** I use JavaScript's built-in formatting APIs, such as `Intl.NumberFormat` for numbers and currencies and `Intl.DateTimeFormat` for dates. For translated messages, I can use React Intl. React simply renders the formatted value, so there is no need to hardcode regional formatting.

<a id="qa-01-051"></a>
### 1.51. Does modern React support Internet Explorer?

**Interview answer:** Modern React does not officially support Internet Explorer. React 18 and later depend on browser capabilities that IE does not fully provide. If a legacy application requires IE, I would verify the exact React version and browser targets rather than assuming polyfills alone can make current React compatible.

<a id="qa-01-052"></a>
### 1.52. What are the main differences between React and Angular?

**Interview answer:** React is primarily a UI library, whereas Angular is a more comprehensive application framework. React uses JSX and lets teams choose supporting libraries; Angular provides templates, dependency injection, routing, and framework conventions. Both can build large applications, so I would choose based on the team's experience and project requirements.

<a id="qa-01-053"></a>
### 1.53. What is the history behind React evolution?

**Interview answer:** React was developed at Facebook and open-sourced in 2013. Important milestones include Fiber in React 16, Hooks in React 16.8, concurrent rendering features in React 18, and Actions and other improvements in React 19. These changes improved scheduling, stateful logic reuse, and asynchronous UI handling.

<a id="qa-01-054"></a>
### 1.54. What is the purpose of displayName class property?

**Interview answer:** `displayName` gives a component a readable name in React DevTools and debugging messages. React usually infers the name from the function or class. I set it explicitly for anonymous wrappers or higher-order components when the automatic name does not explain what the component represents.

<a id="qa-01-055"></a>
### 1.55. Why does `0 && <Component/>` render "0" instead of nothing?

**Interview answer:** JavaScript's logical AND operator returns its first falsy operand or its last operand if all are truthy. When the first operand is `0`, the expression evaluates to zero, which React renders as text. I avoid this by using `items.length > 0 && <List />` or a ternary that returns `null` when the list is empty.

<a id="qa-01-056"></a>
### 1.56. How does the newer JSX transform differ from the older transform?

**Interview answer:** The classic JSX transform generated `React.createElement()` calls, so the React identifier had to be in scope. The newer transform automatically imports helper functions from `react/jsx-runtime`. Therefore, I do not need a default React import solely to use JSX, but I still import APIs such as `useState` when I call them.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-01-057"></a>
### 1.57. What are decorators in React, and when might you encounter them?

**Interview answer:** Decorators are a language feature for enhancing classes or other supported declarations; they are not a React API. Older React code sometimes used decorators with higher-order components such as Redux's `connect`. In modern code, I generally use Hooks or ordinary wrapper functions, and I check toolchain support if maintaining decorator-based code.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-02"></a>
## 2. Components, Props & State

*120 questions — [Back to contents](#contents)*

<a id="qa-02-001"></a>
### 2.1. What is lifting state up?

**Interview answer:** Lifting state up means moving shared state to the closest common ancestor of the components that need it. The parent owns the state and passes values and callbacks down through props. For example, two sibling inputs that must stay synchronized can read and update the same parent state instead of maintaining separate copies.

**Optional coding illustration:**
```jsx
function Parent() {
  const [query, setQuery] = useState('');
  return <><Search value={query} onChange={setQuery} /><Results query={query} /></>;
}
```

<a id="qa-02-002"></a>
### 2.2. What is prop drilling and why is it a problem?

**Interview answer:** Prop drilling happens when data is passed through several intermediate components that do not actually need it, just so a deeply nested component can receive it. This can make the component hierarchy harder to maintain. I first consider composition, and use Context or a shared store when the data genuinely belongs to many distant components.

<a id="qa-02-003"></a>
### 2.3. What is React.Fragment and why is it useful?

**Interview answer:** A Fragment groups multiple React elements without adding an extra DOM node. I use `<>...</>` for simple grouping and `<Fragment key={id}>...</Fragment>` when a group needs a list key. This is useful when an extra wrapper would affect the layout or produce invalid HTML.

<a id="qa-02-004"></a>
### 2.4. What is state in React?

**Interview answer:** State is a component's memory for values that can change over time. React preserves state between renders, and updating it through a setter schedules a new render. For example, I use `useState` for the current value of a counter, input, or selected tab. I treat state as an immutable snapshot of the current render.

<a id="qa-02-005"></a>
### 2.5. What is state mutation and how to prevent it?

**Interview answer:** State mutation means modifying an existing state object or array directly instead of creating an updated value. This can break React's equality checks and alter earlier render snapshots. I avoid it by using immutable operations such as object spread, `map`, and `filter`, or Immer for more complex nested updates.

<a id="qa-02-006"></a>
### 2.6. What is the difference between props and state in React?

**Interview answer:** Props are read-only values received from a parent, whereas state is data owned and managed by a component. Both can affect rendered output. For example, a product card receives the product as props but may maintain local state for whether its details are expanded. A child requests changes to props through a parent callback.

<a id="qa-02-007"></a>
### 2.7. What are React Portals, and when would you use them?

**Interview answer:** A portal allows React to render a component's DOM nodes into a different DOM container using `createPortal`. The component still belongs to the same React tree, so Context and React event propagation continue to work. I use portals for modals and tooltips that need to escape a parent's clipping or stacking context.

<a id="qa-02-008"></a>
### 2.8. What is the difference between controlled and uncontrolled components?

**Interview answer:** A controlled component receives its current value from React state or props and requests changes through a callback. An uncontrolled input lets the DOM keep its current value, often using a default value and a ref to read it. I choose controlled inputs when the UI must react to the value immediately and uncontrolled inputs when simpler DOM-managed behavior is sufficient.

**Optional coding illustration:**
```jsx
const [name, setName] = useState('');
<input value={name} onChange={e => setName(e.target.value)} />
```

<a id="qa-02-009"></a>
### 2.9. Can you explain event bubbling through a React portal rendered outside the DOM parent?

**Interview answer:** Events from a portal propagate according to the React component tree, not just the physical DOM hierarchy. Therefore, a click inside a portaled modal can trigger a handler on its logical React parent even though the DOM nodes are in different containers. I account for this when implementing backdrop clicks or nested interactions.

<a id="qa-02-010"></a>
### 2.10. How do you pass dynamic values to JSX attributes?

**Interview answer:** I pass a JavaScript expression inside curly braces to set a JSX attribute dynamically. For example, `src={imageUrl}` uses a variable and `disabled={isSaving}` uses a boolean. Quoted attributes such as `src="imageUrl"` are literal strings rather than variable references.

<a id="qa-02-011"></a>
### 2.11. Do React state updates merge objects automatically?

**Interview answer:** It depends on the state API. A class component's `this.setState()` shallowly merges the supplied object with existing state. In contrast, a `useState` setter replaces its previous value. When updating one property of an object with `useState`, I explicitly preserve the other fields using the spread operator or an immutable update helper.

**Optional coding illustration:**
```jsx
setUser(prev => ({ ...prev, name: 'Riya' })); // keep other fields
```

<a id="qa-02-012"></a>
### 2.12. How do you set default value for uncontrolled component?

**Interview answer:** For an uncontrolled input, I use `defaultValue` to specify its initial value and let the DOM manage subsequent changes. For a checkbox or radio input, I use `defaultChecked`. Unlike `value` or `checked`, these defaults do not control the current value on every render.

<a id="qa-02-013"></a>
### 2.13. How does Immer help with immutable state updates?

**Interview answer:** Immer lets me describe immutable updates using familiar mutation-like syntax. It provides a draft that tracks changes and produces a new state with structural sharing. For example, Redux Toolkit's reducers can assign `state.user.name = name` safely because Immer manages the draft. I do not mutate actual React or Redux state outside that mechanism.

<a id="qa-02-014"></a>
### 2.14. How does React batch multiple state updates?

**Interview answer:** Batching means React groups multiple state updates into a single rendering pass when possible. React 18 with a modern root also batches updates from sources such as promises, timers, and native event handlers. This reduces unnecessary rendering. If the next value depends on the previous one, I use a functional updater so queued updates are applied correctly.

<a id="qa-02-015"></a>
### 2.15. How do React components communicate with each other?

**Interview answer:** React uses one-way data flow. A parent communicates with children through props, and children request changes by calling callbacks supplied by the parent. Siblings can share state through their closest common ancestor. For distant components that need shared data, I consider Context or a suitable external store.

<a id="qa-02-016"></a>
### 2.16. How do you read updated state immediately after dispatching an action?

**Interview answer:** It depends on the type of dispatch. React's `useReducer` dispatch schedules an update, so reading the state variable immediately afterward still gives the current render's snapshot. A plain Redux action, on the other hand, normally updates the store synchronously through its reducer, so `store.getState()` can read the new value after dispatch. React subscribers render according to React's scheduling.

<a id="qa-02-017"></a>
### 2.17. If we have var, let, and const, why do we need state variables?

**Interview answer:** A regular local variable is recreated when a component function runs again, and assigning to it does not notify React to update the UI. State persists across renders and its setter schedules an update. I use state for a displayed value, a regular variable for temporary calculations, and a ref for persistent mutable data that does not determine the UI.

<a id="qa-02-018"></a>
### 2.18. How do class components consume Context with contextType?

**Interview answer:** A class component can set `static contextType = MyContext` and then access the nearest provider's value through `this.context`. This mechanism supports one Context per class. A class that needs several Contexts can use nested consumers or a wrapper function component that reads them and passes the values as props.

<a id="qa-02-019"></a>
### 2.19. What happens if you forget the key prop when rendering a list?

**Interview answer:** React warns when siblings in a dynamic list lack keys because it needs stable identities to match elements across renders. Without explicit keys, matching can fall back to position, which can cause state to follow the wrong item after insertion or reordering. I use stable IDs that are unique within the list.

<a id="qa-02-020"></a>
### 2.20. Render props pattern — headless component sharing fetch logic?

**Interview answer:** A headless data component can own fetching, loading, and error logic and accept a render function that determines the UI. For example, it might call `render({ data, loading, error })`, allowing different screens to share behavior but display different markup. In modern React, I often prefer a custom Hook for reusable fetching logic because it avoids an extra wrapper.

<a id="qa-02-021"></a>
### 2.21. When and why should you split React Context providers?

**Interview answer:** I split Context providers when their values have different responsibilities or update frequencies. For example, combining rapidly changing notifications with a rarely changing theme can cause theme consumers to update unnecessarily. Separating those values gives consumers a narrower subscription and makes the shared-state architecture easier to maintain.

<a id="qa-02-022"></a>
### 2.22. What are Keyed Fragments?

**Interview answer:** A keyed Fragment lets a group of sibling elements have a stable identity in a list without an additional DOM wrapper. I use the explicit `<Fragment key={item.id}>...</Fragment>` syntax because the short `<>...</>` syntax does not accept keys. This is useful when mapping an item to multiple sibling nodes.

<a id="qa-02-023"></a>
### 2.23. What are props?

**Interview answer:** Props are read-only inputs that a parent passes to a React component. They can contain data, callbacks, or React nodes. I use them to customize reusable components and keep one-way data flow. If a child needs to request a change, it calls a callback supplied by the parent rather than mutating its props.

<a id="qa-02-024"></a>
### 2.24. What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)?

**Interview answer:** A component may render again when its parent renders, when its own state changes, or when a consumed Context changes. New object and function props can also defeat memoization. I start by colocating state, reducing unnecessary updates and measuring with the Profiler. I then use `memo`, `useMemo`, or `useCallback` when stable references and render boundaries actually help.

<a id="qa-02-025"></a>
### 2.25. What does React do differently when a `key` changes vs stays the same?

**Interview answer:** React associates a component's state with its position, type, and key in the tree. Keeping the same type and key at the corresponding position normally preserves its state. Changing the key tells React that it represents a different identity, so the old component is unmounted and a fresh one is mounted. I use this deliberately to reset a form.

**Optional coding illustration:**
```jsx
<EditForm key={selectedUserId} userId={selectedUserId} /> // new ID resets form
```

<a id="qa-02-026"></a>
### 2.26. What is a reducer? Why must reducers be pure functions?

**Interview answer:** A reducer is a pure function that takes the current state and an action and returns the next state. Purity means it does not mutate its inputs or perform side effects, and the same inputs produce the same result. That makes state transitions predictable and testable. I keep API calls and other effects outside reducers.

**Optional coding illustration:**
```jsx
function reducer(state, action) {
  if (action.type === 'increment') return { count: state.count + 1 };
  return state;
}
```

<a id="qa-02-027"></a>
### 2.27. What is JSX spread attributes (`{...props}`)? What's the risk?

**Interview answer:** JSX spread attributes pass the properties of an object as props, for example `<Button {...buttonProps} />`. This is useful for wrappers, but blindly forwarding everything can hide a component's API, override explicit values depending on prop order, or pass unwanted attributes to the DOM. I destructure or explicitly forward the supported props where appropriate.

<a id="qa-02-028"></a>
### 2.28. What is the controlled component pattern for reusable components?

**Interview answer:** A reusable controlled component receives its value through a prop and exposes a callback such as `onChange` to request updates. The parent remains the source of truth. For example, a reusable select can receive `value={selectedId}` and `onChange={setSelectedId}`, making it easy to coordinate with a form or other components.

<a id="qa-02-029"></a>
### 2.29. What is the Controlled/Uncontrolled hybrid pattern?

**Interview answer:** A controlled/uncontrolled hybrid component supports either a parent-owned value or its own internal state initialized with a default value. For example, a dialog might accept `open` and `onOpenChange`, or `defaultOpen`. I define the ownership contract clearly and avoid switching modes unexpectedly during the component's lifetime.

<a id="qa-02-030"></a>
### 2.30. What is the difference between a "key prop" warning and a "missing dependency" warning?

**Interview answer:** A key warning concerns React's ability to identify sibling elements during reconciliation. A missing-dependency warning comes from the Hooks lint rules and indicates that an Effect or memoized callback may capture stale reactive values. I fix keys with stable item identities and fix dependencies by accurately declaring or restructuring the reactive logic.

<a id="qa-02-031"></a>
### 2.31. What is the difference between a transition and a regular (synchronous) state update in terms of interruptibility?

**Interview answer:** An urgent update, such as typing into a controlled input, should be reflected promptly. A transition marks rendering work as non-urgent, allowing React to interrupt or restart it if higher-priority work arrives. I use transitions for expensive result views while keeping input state urgent. This affects scheduling, not the speed of synchronous calculations.

<a id="qa-02-032"></a>
### 2.32. What is the Observer/Pub-Sub pattern's use in React outside of Context (e.g., a lightweight event bus for cross-cutting concerns)?

**Interview answer:** An event bus implements the publish-subscribe pattern: publishers emit events and subscribers receive them without a direct component relationship. I might use one for cross-cutting concerns like notifications triggered outside React. I clean up subscriptions and avoid using an event bus as an invisible replacement for predictable shared state.

<a id="qa-02-033"></a>
### 2.33. What is the purpose of default value in context?

**Interview answer:** The default value passed to `createContext()` is the fallback returned when a consumer has no matching provider above it. It is not an initial provider value that automatically changes. If a provider explicitly supplies `undefined`, consumers receive that value instead of the default. I choose a sensible fallback or use a guard to detect a missing provider.

<a id="qa-02-034"></a>
### 2.34. What happens if you write a boolean prop without a value in JSX?

**Interview answer:** A boolean prop written without an explicit value is equivalent to passing `true`. For example, `<Button disabled />` is shorthand for `<Button disabled={true} />`. To pass false, I write `disabled={false}` or use a boolean expression. The string `"false"` is not the same as the boolean false.

<a id="qa-02-035"></a>
### 2.35. When should you NOT use Context for state?

**Interview answer:** I avoid putting rapidly changing values in a broad Context provider when only a few consumers need those values. A changed provider value can trigger all consumers of that Context. I keep local state local, split providers, or use a selector-based external store when I need fine-grained subscriptions.

<a id="qa-02-036"></a>
### 2.36. Why is state update asynchronous?

**Interview answer:** A state setter schedules an update instead of changing the state variable in the currently executing render. React can queue and batch updates for efficiency. That is why logging state immediately after a setter may show the old value. I use functional updaters when calculating from previous state, and read the result on the next render.

<a id="qa-02-037"></a>
### 2.37. When should you split a React component into smaller components?

**Interview answer:** I split a component when it has multiple responsibilities, repeated UI, or independent state that makes it difficult to understand or test. For example, a dashboard can have separate filter, table, and pagination components. I avoid splitting every small element automatically because excessive abstraction can also make the code harder to follow.

<a id="qa-02-038"></a>
### 2.38. Why are inline ref callbacks or functions not recommended?

**Interview answer:** An inline callback ref has a new function identity on each render. React may detach the previous callback ref and attach the new one, even if the DOM node remains the same. If this causes repeated imperative work, I use a stable callback or an object ref. I also ensure any callback-ref cleanup is correct.

<a id="qa-02-039"></a>
### 2.39. What is a wrapper component?

**Interview answer:** A wrapper component composes other components and adds behavior or structure around them, such as layout, authorization, or error handling. It usually accepts `children` and renders them inside its own UI. For example, a protected route wrapper can show its children when authenticated and redirect otherwise.

<a id="qa-02-040"></a>
### 2.40. What is the children prop in React, and why is it useful?

**Interview answer:** `children` is the prop representing the content nested between a component's opening and closing JSX tags. It allows reusable components to accept arbitrary content without knowing its details. For example, a Card can render its own border and layout while displaying whatever content the caller provides inside it.

<a id="qa-02-041"></a>
### 2.41. What is forwardRef, and when do you need it?

**Interview answer:** A ref lets a parent access a child's DOM node or an exposed imperative handle. In React 18 and earlier, function components commonly use `forwardRef` to receive and pass that ref. React 19 supports receiving `ref` as a prop directly in function components. I expose refs only when imperative access, such as focusing an input, is necessary.

<a id="qa-02-042"></a>
### 2.42. What is the difference between an Element and a Component?

**Interview answer:** A component is a function or class that defines reusable UI behavior. A React element is an immutable description of what to render, created by JSX or an element-creation API. For example, `Button` is a component type, while `<Button label="Save" />` is a React element describing an instance of that type.

<a id="qa-02-043"></a>
### 2.43. What goes wrong when you use an array index as a key and reorder the list?

**Interview answer:** If I use an array index as a key and reorder or insert items, the same key may now refer to different data. React can preserve a component's state at that position, causing an input value or selected status to appear on the wrong item. Stable data IDs avoid this identity mismatch.

<a id="qa-02-044"></a>
### 2.44. What is the `key` prop and why is it important?

**Interview answer:** The `key` prop tells React which element corresponds to which sibling across renders. Stable keys help React preserve the correct component state when items move, appear, or disappear. I use IDs unique among siblings rather than random values or indexes for dynamic lists. Keys are React metadata, not ordinary props received by the child.

**Optional coding illustration:**
```jsx
{todos.map(todo => <TodoItem key={todo.id} todo={todo} />)}
```

<a id="qa-02-045"></a>
### 2.45. What will happen if you use props in initial state?

**Interview answer:** When I initialize state from props, the initializer runs when that state is created; later prop changes do not automatically synchronize the state. This can lead to stale or duplicated data. I derive the value directly from props unless I deliberately need an independent editable copy or a reset mechanism such as a changed key.

<a id="qa-02-046"></a>
### 2.46. Should you dispatch another action inside a reducer?

**Interview answer:** No, I should not dispatch another action from inside a reducer. A reducer must be a pure function: given the existing state and an action, it returns the updated state without side effects. If one action needs to trigger more work, I would do it in an event handler, an effect, or Redux middleware such as a thunk or listener middleware.

<a id="qa-02-047"></a>
### 2.47. What can cause a React component to re-render unexpectedly?

**Interview answer:** Unexpected renders can come from parent updates, changed Context values, external-store subscriptions, local state, or unstable prop references. I use React DevTools Profiler to determine the actual trigger. I then consider state colocation, narrower subscriptions, or memoization where there is evidence of unnecessary work.

<a id="qa-02-048"></a>
### 2.48. Can you explain difference between `key`-based remounting and conditional rendering?

**Interview answer:** Changing a key forces React to treat a component as a new identity, which discards its previous local state. Conditional rendering removes a component when its condition becomes false, also unmounting it if the component is absent from the tree. If the same component remains at the same position with the same key, state can be preserved. I use keys for deliberate identity resets.

<a id="qa-02-049"></a>
### 2.49. Can you explain conditional rendering in React?

**Interview answer:** Conditional rendering means choosing what UI to display based on state, props, or another expression. I use early returns or `if` statements for larger branches, a ternary for two alternatives, and boolean `&&` for optional content. I make numeric conditions explicitly boolean so an empty count does not accidentally render zero.

<a id="qa-02-050"></a>
### 2.50. What is a function component in React?

**Interview answer:** A function component is a JavaScript function that accepts props and returns React nodes describing its UI. It can manage state and synchronize with external systems through Hooks. I prefer function components for new React code because they work naturally with composition and custom Hooks.

<a id="qa-02-051"></a>
### 2.51. Given users = \[{id:1, active:true}, {id:2, active:false}\], find all active user IDs?

**Interview answer:** I would filter the users to keep those with `active: true`, then map the result to their IDs: `users.filter(user => user.active).map(user => user.id)`. For the given input, the result is `[1]`. This is a declarative approach and does not mutate the original array.

<a id="qa-02-052"></a>
### 2.52. How do you pass data child → parent?

**Interview answer:** A child cannot directly update its parent's state. Instead, the parent passes a callback prop, and the child calls it with the new value or event. For example, a search input can call `onSearchChange(value)`, while its parent owns the search state and decides how to update it.

<a id="qa-02-053"></a>
### 2.53. How do you prevent prop explosion in complex components?

**Interview answer:** I reduce prop explosion by separating responsibilities into smaller components and using composition or `children` for customizable content. I group related data into a meaningful object when that improves the API, and use Context for genuinely shared values. I avoid replacing a long prop list with a single unstructured configuration object that hides the same complexity.

<a id="qa-02-054"></a>
### 2.54. How do you update arrays inside state?

**Interview answer:** I treat arrays in React state as immutable. To add an item I use `setItems(prev => [...prev, item])`; to remove one I use `filter()`, and to update an item I use `map()`. I avoid mutating the original array with `push`, `splice`, or direct index assignment because React relies on new references to detect changes reliably.

<a id="qa-02-055"></a>
### 2.55. How do you update nested objects inside state?

**Interview answer:** For nested state, I create new objects along the path being updated while preserving unchanged fields. For example, `setUser(prev => ({ ...prev, address: { ...prev.address, city } }))`. This preserves immutability. If updates become deeply nested, I consider restructuring state or using Immer to make the update clearer.

<a id="qa-02-056"></a>
### 2.56. How would you create React class components without ES6?

**Interview answer:** Older React versions supported `React.createClass` for defining components without ES6 classes. It used an object with methods such as `render` and `getInitialState`. That API is legacy; for a maintained modern application I use a function component or an ES6 class where necessary.

<a id="qa-02-057"></a>
### 2.57. How would you use and update the state object?

**Interview answer:** I read the current state to describe the UI and update it through React's state API. In a function component, I use the setter returned by `useState`; in a class, I use `this.setState`. For updates that depend on previous state, I use an updater function and avoid mutating state objects directly.

<a id="qa-02-058"></a>
### 2.58. Is it ref argument available for all functions or class components?

**Interview answer:** In older React versions, refs are not ordinary props for function components; a function needs `forwardRef` to receive the forwarded ref argument. A class component ref normally points to its instance. React 19 lets function components receive `ref` as a prop. I distinguish these behaviors by React version and component type.

<a id="qa-02-059"></a>
### 2.59. Must prop be named as render for render props?

**Interview answer:** No. A render prop is any prop whose function value is called to determine rendered output. It can be named `render`, `children`, or another meaningful name. The important part is the contract: the component supplies data or behavior and the function returns the UI to display.

<a id="qa-02-060"></a>
### 2.60. What is a reducer, and how does it manage state?

**Interview answer:** A reducer is a function that receives the existing state and an action, then returns the updated state. It is useful when several kinds of actions update related data.

<a id="qa-02-061"></a>
### 2.61. How would you manage the visibility of a modal or sidebar shared between components?

**Interview answer:** It is ideal for managing the visibility of shared UI components like modals, drawers, or sidebars, especially when their state needs to be controlled from various parts of the app.

<a id="qa-02-062"></a>
### 2.62. Do React list keys need to be unique across the entire application?

**Interview answer:** No. A key needs to be unique only among sibling elements in the same rendered list. I typically use a stable database ID rather than an array index for lists that can change order.

<a id="qa-02-063"></a>
### 2.63. What causes re-renders in React, and how can you reduce unnecessary ones?

**Interview answer:** React can render a component because its state changes, its parent renders, its consumed Context changes, or an external subscription updates. I reduce unnecessary work by keeping state near its consumers, splitting Context where appropriate, and using stable props and memoization for expensive components. I verify the bottleneck with profiling before optimizing.

<a id="qa-02-064"></a>
### 2.64. Where is state stored in a React application?

**Interview answer:** React owns component state and associates it with the component's identity and position in the rendered tree. A state variable in a function is the snapshot provided for that render, not the persistent storage itself. State can also live in an external store or a server-data cache when the application's requirements justify it.

<a id="qa-02-065"></a>
### 2.65. What are default props and PropTypes?

**Interview answer:** Default props provide fallback values when a parent does not supply a prop. In function components, I generally use default parameter values. PropTypes were used for runtime prop validation in older React projects; for modern apps, TypeScript is commonly preferred, and React 19 removed built-in prop-type checking.

<a id="qa-02-066"></a>
### 2.66. What are React elements vs React components?

**Interview answer:** A React component is a reusable definition of UI, usually a function or class. An element is the object that describes a component or host element at a particular point in the UI tree. JSX such as `<UserCard name="Asha" />` creates an element; React evaluates its component type as part of rendering.

<a id="qa-02-067"></a>
### 2.67. What are stateful components?

**Interview answer:** A stateful component owns or manages data that changes over time and affects its rendered output. For example, a counter stores its current count and updates it when a button is clicked. Function components use Hooks such as `useState` or `useReducer`, and class components use `this.state` and `setState`.

<a id="qa-02-068"></a>
### 2.68. What are presentational vs container components?

**Interview answer:** A presentational component focuses on how data is displayed, while a container handles data fetching, state, and business logic. This separation improves reuse and testing. In modern React, I can often extract the container logic into a custom Hook and keep the visual component focused on presentation.

<a id="qa-02-069"></a>
### 2.69. What are render props?

**Interview answer:** Render props share behavior through a function prop. A component manages logic and calls that function with useful data, allowing its consumer to decide what UI is rendered. For example, a mouse-position tracker can supply coordinates to different visualizations. Custom Hooks often provide the same logic reuse with less nesting.

<a id="qa-02-070"></a>
### 2.70. What are the guidelines to be followed for writing reducers?

**Interview answer:** I keep reducers pure: the same state and action should produce the same result. I do not perform API requests or mutate the existing state inside a plain reducer. Redux Toolkit lets me write mutation-like code safely because Immer handles immutable updates.

<a id="qa-02-071"></a>
### 2.71. What are the problems of using render props with pure components?

**Interview answer:** A render prop is often a function. If I create that function inline, its reference changes every time the parent renders, so a PureComponent or memoized component may no longer skip the render. When this is a measured problem, I can use a stable class method or `useCallback` with the correct dependencies.

<a id="qa-02-072"></a>
### 2.72. What happens if a component wrapped in `memo()` has its own state changes?

**Interview answer:** A memoized component can still re-render when its own state or consumed Context changes. `React.memo` primarily allows React to skip parent-driven renders when props are unchanged. It does not freeze the component. A state update to an identical value may still be skipped by React.

<a id="qa-02-073"></a>
### 2.73. Why should we not update the state directly?

**Interview answer:** Directly mutating state can change an existing render snapshot and may leave React with the same object reference, so it cannot reliably detect the intended update. I use a setter and return a new object or array. For example, `setItems(prev => [...prev, newItem])` safely adds an item without mutating the existing array.

<a id="qa-02-074"></a>
### 2.74. What is `createSlice()` and what does it contain? (name, initialState, reducers)?

**Interview answer:** `createSlice` accepts an object with: `name`: A string used as prefix for action types. `initialState`: The initial state value. `reducers`: An object mapping action names to reducer functions (or `prepare` callbacks). Each reducer function receives `state` and `action` and can mutate the state (thanks to Immer). `extraReducers` (optional): Allows responding to actions not defined in the slice (for example, from `createAsyncThunk`).

<a id="qa-02-075"></a>
### 2.75. What is an updater function? Should an updater function be used in all cases?

**Interview answer:** An updater function receives the pending previous state and returns the next state. For example, `setCount(prev => prev + 1)` is useful when the new value depends on the old value, especially with batched updates. I use a direct value for independent replacements such as `setOpen(false)`; an updater is not necessary in every case.

<a id="qa-02-076"></a>
### 2.76. What is colocation in React?

**Interview answer:** Keeping related code together; state close to where it's used, styles next to components, tests next to source. Avoid premature abstraction. Move state up only when shared, not just to 'be organized'.

<a id="qa-02-077"></a>
### 2.77. What is composition vs inheritance in React?

**Interview answer:** Composition builds complex components by combining smaller components through props and `children`. Inheritance would share behavior through a class hierarchy. React generally favors composition because it makes dependencies and customization explicit. I extract reusable stateful logic into Hooks and reusable pure logic into ordinary functions.

<a id="qa-02-078"></a>
### 2.78. What is flux?

**Interview answer:** Flux is an application architecture (not a framework or library) designed by Facebook to manage data flow in React applications. It was created as an alternative to the traditional MVC (Model-View-Controller) pattern, and it emphasizes a unidirectional data flow to make state changes easier to reason about and easier to debug. Flux complements React by organizing the way data moves through your application, especially in large-scale or complex projects.

<a id="qa-02-079"></a>
### 2.79. What is Hot Module Replacement (HMR)? Why does it matter for React development?

**Interview answer:** HMR swaps updated modules in a running app without a full page reload, preserving component state during development (for example, keeping a form's typed input while you tweak its styling), dramatically speeding up the dev feedback loop.

<a id="qa-02-080"></a>
### 2.80. What is prop inversion of control?

**Interview answer:** Prop inversion of control means giving a component's consumer control over a particular behavior or rendered section instead of hardcoding every decision inside the component. For example, a table can accept a function for rendering each row. This improves flexibility but requires a clear API so consumers do not need to know internal implementation details.

<a id="qa-02-081"></a>
### 2.81. What is prop type narrowing with discriminated unions (conceptually, even pre-TS)?

**Interview answer:** Structuring props so only a valid, mutually exclusive combination can be passed (for example, `variant: 'link'` requiring `href`, `variant: 'button'` requiring `onClick`), preventing invalid prop combinations at the API design level.

<a id="qa-02-082"></a>
### 2.82. What is server state vs client state?

**Interview answer:** Client state represents UI-owned data such as selected tabs, open dialogs, and draft values. Server state represents remote data that may become stale or change outside the application. I manage local UI state with React or a client store, and use a server-state solution such as TanStack Query or RTK Query for caching, fetching, and invalidation.

<a id="qa-02-083"></a>
### 2.83. What is a consumer?

**Interview answer:** A Consumer is a React component that subscribes to context changes. It requires a function as a child which receives current context value as argument and returns a react node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. Lets take a simple example.

<a id="qa-02-084"></a>
### 2.84. What is test isolation, and why does it matter for React component tests?

**Interview answer:** Test isolation means each test runs with its own predictable setup and does not depend on the state left by another test. In React tests, I create fresh providers or stores, reset mocks, and clean up subscriptions and timers. This prevents order-dependent failures and makes it easier to reproduce bugs.

<a id="qa-02-085"></a>
### 2.85. What is the "render in a loop with composition" pattern vs a monolithic configurable component?

**Interview answer:** Instead of creating one large component with many configuration flags, I can compose smaller reusable components and render them from a list of data. For example, I map field definitions to individual form-field components. This improves separation of concerns, although I avoid introducing a generic abstraction before repeated behavior is clear.

<a id="qa-02-086"></a>
### 2.86. What are the advantages and trade-offs of a React SPA?

**Interview answer:** A React SPA provides fast client-side navigation and can maintain shared UI state without full page reloads. Its trade-offs include larger initial JavaScript downloads, client-side routing configuration, and potential SEO or accessibility challenges. I mitigate these with code splitting, accessible navigation, caching, and server rendering or prerendering where needed.

<a id="qa-02-087"></a>
### 2.87. What is the difference between `interface` and `type` for defining props? When does it matter?

**Interview answer:** Both TypeScript interfaces and type aliases can describe component props. Interfaces support declaration merging and extension, while type aliases can directly represent unions and intersections. I use a discriminated union when props must support mutually exclusive variants. For a simple object-shaped props contract, either is usually appropriate.

<a id="qa-02-088"></a>
### 2.88. What is the difference between `setState()` and `replaceState()` methods?

**Interview answer:** `setState()` in a class component shallowly merges the supplied partial state with existing state. `replaceState()` was a legacy API used to replace the entire state object and is not a modern React class API. In a function component, a `useState` setter replaces its value, so I explicitly preserve fields that should remain unchanged.

<a id="qa-02-089"></a>
### 2.89. What is the difference between normalized and nested state shape in a global store?

**Interview answer:** Nested state stores related entities inside one another, which can be intuitive but creates deep updates and duplicate data. Normalized state stores entities by ID and represents relationships using those IDs. For complex shared collections, normalization simplifies updates and selectors. For simple local UI state, a nested structure may be perfectly reasonable.

<a id="qa-02-090"></a>
### 2.90. What are headless components?

**Interview answer:** A headless component provides reusable behavior and often accessibility features without imposing a visual design. For example, a headless select can manage keyboard navigation and selection while the consumer controls the markup and styling. This is useful for building consistent behavior across differently styled design systems.

<a id="qa-02-091"></a>
### 2.91. What is the provider pattern?

**Interview answer:** The provider pattern wraps part of the component tree and makes shared data or behavior available through Context. For example, an AuthProvider can expose the signed-in user and login actions. Consumers access that data without intermediate components forwarding props. I keep providers scoped to the parts of the tree that need them.

<a id="qa-02-092"></a>
### 2.92. What is the purpose of callback function as an argument of `setState()`?

**Interview answer:** Class component `setState` can take a callback that runs after the state update is committed. I use it when I need to perform work after a class component updates. In function components, I generally use an Effect to respond to relevant committed state changes.

<a id="qa-02-093"></a>
### 2.93. What is the recommended approach of removing an array element in React state?

**Interview answer:** I remove an item from a state array with `filter()` and pass the resulting array to the state setter, for example `setItems(prev => prev.filter(item => item.id !== id))`. This creates a new array without modifying existing state and works well with queued updates because it uses the pending previous value.

<a id="qa-02-094"></a>
### 2.94. What is the render props pattern?

**Interview answer:** The render-props pattern lets a component share logic by accepting a function that returns UI. The component owns behavior, such as fetching or tracking a value, and calls the supplied function with the necessary data. It is a composition technique; I often use custom Hooks instead when only stateful logic needs to be shared.

<a id="qa-02-095"></a>
### 2.95. What is the risk of trusting `window.postMessage` data without validation in a React component?

**Interview answer:** `window.postMessage` can receive data from another window or frame, so treating every incoming message as trusted can expose sensitive behavior or data. I verify the expected `event.origin` and source, validate the message structure, and only allow supported actions. When sending messages, I use a specific target origin rather than `*` whenever possible.

<a id="qa-02-096"></a>
### 2.96. What is the Slot pattern?

**Interview answer:** The slot pattern exposes named places where a consumer can insert custom UI. In React, I can implement slots through props such as `header`, `footer`, or `actions`, or use `children` for a default content area. It makes layouts customizable without requiring inheritance or a large number of configuration flags.

<a id="qa-02-097"></a>
### 2.97. What is the state reducer pattern?

**Interview answer:** The state reducer pattern lets a reusable component manage default state transitions while allowing the consumer to influence them through a reducer-like callback. For example, a dropdown can expose a state reducer to prevent closing under certain conditions. It provides inversion of control, but I document the expected actions and keep updates predictable.

<a id="qa-02-098"></a>
### 2.98. When did you get stuck while using React, and how did you fix it?

**Interview answer:** A suitable example is a stale API response overwriting the UI after navigation or a filter change. I would explain how I reproduced the issue, identified the outdated request in DevTools, and added cancellation or a guard in Effect cleanup. In an actual interview, I would use a real issue I personally solved and describe its verified outcome rather than invent experience.

<a id="qa-02-099"></a>
### 2.99. Why can't you update props in React?

**Interview answer:** The React philosophy is that props should be immutable (read-only) and top-down. In other words, a parent can send any prop values to a child, but the child can't modify received props. This ensures predictable data flow. *The full document continues with all remaining sections. Due to length, the complete Q&A is provided in the downloadable markdown file.

<a id="qa-02-100"></a>
### 2.100. Why do you not required to use inheritance?

**Interview answer:** React favors composition over inheritance. I combine components through props, `children`, and component composition rather than creating class hierarchies. For shared non-UI logic, I use custom Hooks or ordinary JavaScript functions. This keeps component relationships explicit and easier to maintain.

<a id="qa-02-101"></a>
### 2.101. Why we need to be careful when spreading props on DOM elements?

**Interview answer:** Blindly spreading props onto a DOM element can pass component-only values, unexpected event handlers, or invalid attributes into the browser. It can also override intended behavior depending on spread order. I destructure internal props and explicitly forward supported DOM attributes, particularly in reusable component libraries.

<a id="qa-02-102"></a>
### 2.102. When do you need to use refs?

**Interview answer:** I use refs when I need to access a DOM node or keep a mutable value across renders without updating the UI. Common examples include focusing an input, controlling media, storing a timer ID, and integrating a third-party DOM library. If a value determines what the UI displays, I use state instead.

<a id="qa-02-103"></a>
### 2.103. Why do you need additional care for component libraries while using forward refs?

**Interview answer:** Forwarding a ref from a component library changes what consumers can access imperatively, so it is part of the public API. Changing the target node can break existing integrations. I expose a predictable DOM node or a limited imperative handle, document the contract, and account for the different ref APIs in React 18 and React 19.

<a id="qa-02-104"></a>
### 2.104. Why is `isMounted()` an anti-pattern and what is the proper solution?

**Interview answer:** `isMounted()` was a legacy way to check whether a component remained mounted before updating it. It often hid the real problem: work such as a subscription or request was not cleaned up. I instead unsubscribe, clear timers, or cancel or ignore stale async results in lifecycle cleanup or Effect cleanup.

<a id="qa-02-105"></a>
### 2.105. Why is calling `setState` inside `render` dangerous?

**Interview answer:** Calling a state setter unconditionally during rendering can immediately schedule another render, which repeats the same setter and creates an infinite loop. Rendering should normally be pure. I update state in event handlers, use Effects for external synchronization, and calculate derived values directly during render when possible.

<a id="qa-02-106"></a>
### 2.106. What is the difference between `super()` and `super(props)` in React using ES6 classes?

**Interview answer:** In an ES6 class constructor, `super()` calls the base constructor, while `super(props)` also passes the received props to React.Component. Passing props lets `this.props` be initialized correctly during constructor execution. If I define a React class constructor, I normally use `super(props)` before accessing `this`.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-107"></a>
### 2.107. Which method must a class component implement?

**Interview answer:** In a class component, the required method is `render()`, which returns the UI. The constructor and lifecycle methods are optional. For new React code, I typically use a function component with Hooks instead, because it is simpler and easier to reuse stateful logic.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-108"></a>
### 2.108. What is a class component in React?

**Interview answer:** A class component is an ES6 class that extends `React.Component` and defines a `render()` method. It can hold state and use lifecycle methods. In new React code, I generally prefer function components with Hooks.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-109"></a>
### 2.109. Can you explain data flow in React?

**Interview answer:** React mainly follows one-way data flow. A parent passes data to a child through props; the child notifies the parent about changes using a callback. Shared state can be lifted to a common parent or placed in Context or a store. That makes it easier to know where a UI value comes from and who can change it.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-110"></a>
### 2.110. Does the statics object work with ES6 classes in React?

**Interview answer:** The `statics` configuration object belonged to the old `React.createClass` API. ES6 class components instead use JavaScript static methods or properties, such as `static contextType = MyContext`. Modern function components can also have properties assigned directly to the function where an API expects them.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-111"></a>
### 2.111. Is it mandatory to define constructor for React component?

**Interview answer:** No. A React class component only needs to implement `render()`; a constructor is optional. If I need to initialize state, class field syntax is often sufficient. I define a constructor only when it is necessary, and call `super(props)` before using `this`.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-112"></a>
### 2.112. How can a class component subscribe to one Context using contextType?

**Interview answer:** A class can subscribe to a Context by declaring `static contextType = MyContext` or assigning `MyClass.contextType = MyContext`. It then reads the nearest matching provider's value from `this.context` and updates when that Context changes. This API subscribes the class to one Context.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-113"></a>
### 2.113. How was state initialized in older React.createClass components compared with ES6 classes?

**Interview answer:** Legacy `React.createClass` components used `getInitialState()` to return the initial state object. ES6 class components initialize `this.state` in the constructor or with a class field. For function components, I use `useState` or `useReducer` to define initial state instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-114"></a>
### 2.114. What is the difference between Flow and PropTypes?

**Interview answer:** Flow is a static type checker that analyzes JavaScript code before runtime. PropTypes historically provided runtime warnings about invalid React props during development. Static types help catch problems earlier but do not validate arbitrary external data at runtime. In new projects I generally use TypeScript plus appropriate runtime validation for external inputs.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-115"></a>
### 2.115. What is the constructor used for in a React class component?

**Interview answer:** The constructor in a React class component is used for initialization, such as defining the initial state or binding methods. It must call `super(props)` before accessing `this`. I do not perform subscriptions or network requests inside the constructor because those belong in lifecycle methods with appropriate cleanup.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-116"></a>
### 2.116. What did unmountComponentAtNode do in older React versions?

**Interview answer:** `unmountComponentAtNode(container)` was the legacy React DOM API for unmounting a previously rendered tree from a container. It allowed React to remove the component tree and run cleanup. With the modern `createRoot` API, I retain the root reference and call `root.unmount()` instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-117"></a>
### 2.117. Why do class components sometimes call super(props) in the constructor?

**Interview answer:** A derived JavaScript class must call `super()` before accessing `this`. React class components commonly use `super(props)` so the base React.Component constructor receives the props and `this.props` is available during initialization. If no constructor is needed, I simply omit it.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-118"></a>
### 2.118. What is unidirectional data flow in React?

**Interview answer:** Data flows parent → child via props. A child requests a change via a callback passed down, and the parent updates its own state, flowing back down as new props.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-119"></a>
### 2.119. What will happen if you use `setState()` in constructor?

**Interview answer:** In a class constructor, I initialize state by assigning `this.state` directly rather than calling `setState()`. The component has not mounted yet, so scheduling an update there is not the appropriate initialization mechanism. Subsequent state changes after initialization should use `this.setState()`.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-02-120"></a>
### 2.120. Why are String Refs legacy?

**Interview answer:** String refs such as `ref="input"` were a legacy class component API that exposed nodes through `this.refs`. They depended on implicit ownership and were difficult to compose. They were removed in React 19, so modern code should use object refs created with `createRef` or `useRef`, or callback refs.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-03"></a>
## 3. Rendering, Reconciliation & Lifecycle

*35 questions — [Back to contents](#contents)*

<a id="qa-03-001"></a>
### 3.1. What happens in React’s commit phase?

**Interview answer:** The commit phase is when React applies completed rendering work to the host environment. For React DOM, it performs necessary DOM mutations, updates refs, and runs commit-related lifecycle methods and layout effects. Passive effects run separately after the commit. A render that is abandoned does not reach this phase.

<a id="qa-03-002"></a>
### 3.2. What is React Fiber, and why was it introduced?

**Interview answer:** Fiber is React's internal reconciliation architecture introduced in React 16. It represents units of work in a tree, allowing React to track component state and schedule rendering more flexibly. Later concurrent features can interrupt or restart non-urgent rendering work. Fiber is an implementation detail rather than an API that I directly use.

<a id="qa-03-003"></a>
### 3.3. What is reconciliation, and how does React’s diffing algorithm work?

**Interview answer:** Reconciliation is how React matches the next rendered element tree against the previous tree. It uses heuristics based on element type, position, and keys to decide what to preserve, update, or replace. Stable keys are especially important for lists. After reconciliation, React commits the required DOM changes rather than replacing the whole page.

<a id="qa-03-004"></a>
### 3.4. How does React work behind the scenes (render → reconciliation → commit)?

**Interview answer:** When an update is scheduled, React renders components to calculate the next UI. During reconciliation, it determines how the new elements correspond to the previous tree. Once work is ready, the commit phase applies necessary DOM changes, updates refs, and runs relevant effects. Rendering itself must remain pure because React may restart or discard it.

<a id="qa-03-005"></a>
### 3.5. How is JavaScript strict mode different from React Strict Mode?

**Interview answer:** JavaScript strict mode is a language feature that enables stricter syntax and runtime behavior, often through `'use strict'`. React Strict Mode is a development tool that intentionally performs extra checks for impure rendering, missing Effect cleanup, and other issues. They are independent mechanisms despite the similar names.

<a id="qa-03-006"></a>
### 3.6. How does the React Fiber architecture change how rendering fundamentally works?

**Interview answer:** Fiber divides React's rendering work into units that can be scheduled and tracked. This supports prioritizing updates and, with concurrent features, pausing or restarting non-urgent render work. The commit phase still applies completed changes consistently. It improves React's ability to keep interactive UI responsive during complex updates.

<a id="qa-03-007"></a>
### 3.7. In what order do class mounting, state updates, and componentDidUpdate run?

**Interview answer:** On mount, a class initializes state, renders its output, and runs `componentDidMount` after commit. When a later state or prop update occurs, React renders again if necessary and calls `componentDidUpdate` after the update is committed. `componentDidUpdate` does not run for the initial mount, and skipped renders may skip it as well.

<a id="qa-03-008"></a>
### 3.8. What happens before React commits DOM updates?

**Interview answer:** Before committing DOM changes, React runs the render and reconciliation work needed to determine the next UI. It can reuse existing elements, calculate updates, or discard unfinished work. For class components, `getSnapshotBeforeUpdate` can read the existing DOM immediately before mutations. Actual DOM updates belong to commit.

<a id="qa-03-009"></a>
### 3.9. What are Strict Mode's dev-only behaviors?

**Interview answer:** React Strict Mode enables development-only checks, including extra calls to rendering logic and additional Effect or ref cleanup/setup checks where applicable. These checks help expose impure renders and missing cleanup. They do not mean production always renders twice, and I fix the underlying issue rather than disabling Strict Mode to hide it.

<a id="qa-03-010"></a>
### 3.10. What is `getDerivedStateFromProps` and when would you use it?

**Interview answer:** `getDerivedStateFromProps` is a static class lifecycle method that can return a partial state update before rendering, or `null` if no update is needed. It is rarely necessary because copying props into state creates synchronization problems. I prefer deriving values during render, using controlled state, or resetting a component with a key when appropriate.

<a id="qa-03-011"></a>
### 3.11. What is `PureComponent` vs `Component` in class components?

**Interview answer:** `React.Component` provides the standard class component behavior. `React.PureComponent` adds a shallow comparison of props and state to skip some unnecessary updates. It works best with immutable data; mutating nested objects can hide meaningful changes. In function components, `React.memo` provides a related props-based optimization.

<a id="qa-03-012"></a>
### 3.12. Can you explain different trees are produced because of different elements?

**Interview answer:** When React encounters different element types at the same position, such as changing a `div` to a `section` or replacing one component type with another, it generally replaces that subtree. The old component's local state is discarded. If the type and identity remain the same, React can preserve the existing state and update only what is needed.

<a id="qa-03-013"></a>
### 3.13. What is the commit phase's "passive effects" vs "layout effects" ordering?

**Interview answer:** Layout effects run after React updates the DOM and before the browser repaints, making them suitable for measuring layout or preventing visible flicker. Passive effects usually run after paint, although React can run them earlier in some interaction-related cases. I prefer `useEffect` unless the work must happen before paint.

<a id="qa-03-014"></a>
### 3.14. What is the methods order when component re-rendered?

**Interview answer:** For a normal class component update, the relevant order is `getDerivedStateFromProps`, `shouldComponentUpdate`, `render`, `getSnapshotBeforeUpdate`, and `componentDidUpdate`. If React skips rendering, later lifecycle methods may not run. I use this sequence to understand which work is safe before and after DOM updates.

<a id="qa-03-015"></a>
### 3.15. Can you explain elements of the same type are compared attribute-wise?

**Interview answer:** When two host elements have the same type and identity, React can reuse the existing DOM node and update the attributes or properties that changed. It then reconciles their children. For example, changing a `div` class name does not normally require replacing the entire element. This reduces unnecessary DOM mutations.

<a id="qa-03-016"></a>
### 3.16. Can you explain Strict Mode in React?

**Interview answer:** React Strict Mode is a development-only tool that helps identify unsafe or impure behavior. I enable it around the relevant component tree so React can perform additional rendering and cleanup checks. If an Effect subscribes twice without cleanup or a render mutates data, Strict Mode helps reveal that bug before production.

**Optional coding illustration:**
```jsx
<StrictMode><App /></StrictMode>
```

<a id="qa-03-017"></a>
### 3.17. What is the structure of a React Fiber tree?

**Interview answer:** A Fiber is an internal React work unit representing a component or host element. Fibers contain information such as type, pending and memoized props, state, and links to their child, sibling, and parent. React tracks current and work-in-progress versions as it prepares updates. These are implementation details that can evolve across versions.

<a id="qa-03-018"></a>
### 3.18. Is it possible to access a ref in the render method?

**Interview answer:** A ref object can exist during render, but reading or writing its `current` value during render is generally discouraged because rendering must remain pure. A DOM ref is not attached until commit, so it is initially null. I normally access it in an event handler or Effect, with predictable initialization as a narrow exception.

<a id="qa-03-019"></a>
### 3.19. What are the different phases of component lifecycle?

**Interview answer:** A component's lifecycle can be described as mounting, updating, and unmounting. Mounting introduces it to the tree, updating recalculates its UI after changes, and unmounting removes it and releases resources. Class components have lifecycle methods, while function components use Effects to synchronize external resources and clean them up when appropriate.

<a id="qa-03-020"></a>
### 3.20. What is `getSnapshotBeforeUpdate`?

**Interview answer:** `getSnapshotBeforeUpdate` is a class lifecycle method called immediately before React mutates the DOM for an update. It captures information from the existing DOM, such as scroll position, and passes the returned snapshot to `componentDidUpdate`. It is useful when post-update behavior depends on the pre-update layout.

<a id="qa-03-021"></a>
### 3.21. What is `shouldComponentUpdate` and its functional equivalent?

**Interview answer:** `shouldComponentUpdate` is a class lifecycle method that lets React skip an update when it returns false. `React.memo` serves a similar optimization purpose for function components by comparing props, but it does not block their own state or Context updates. A custom comparator is possible, although I prefer the default comparison unless profiling justifies one.

<a id="qa-03-022"></a>
### 3.22. What is event delegation in React?

**Interview answer:** React uses event delegation for many supported events. Instead of attaching every handler separately to each DOM node, modern React generally listens at the root container and dispatches events to the appropriate components. Some events require different handling, so it is not accurate to say every event uses a single listener.

<a id="qa-03-023"></a>
### 3.23. What is the lifecycle methods order in mounting?

**Interview answer:** For normal class mounting, React calls the constructor if defined, then `getDerivedStateFromProps`, then `render`, and finally `componentDidMount` after the DOM is committed. Legacy unsafe methods should not be used for new code. Development Strict Mode can introduce extra calls for checks.

<a id="qa-03-024"></a>
### 3.24. What is double buffering in React Fiber?

**Interview answer:** Double buffering in Fiber refers to React maintaining the current committed tree and a work-in-progress tree while preparing updates. React can build the next version without immediately modifying the currently displayed UI. When work is committed, the finished tree becomes current. This supports flexible scheduling and consistent commits.

<a id="qa-03-025"></a>
### 3.25. What is the recommended ordering of methods in component class?

**Interview answer:** There is no mandatory method order beyond JavaScript syntax and React lifecycle behavior. For readability, I group static configuration and initialization first, lifecycle methods together, event handlers and helper functions next, and `render()` near the end. I follow the team's conventions to make class components easier to navigate.

<a id="qa-03-026"></a>
### 3.26. Why do two sibling components with the same `key` cause a warning or misbehavior?

**Interview answer:** Keys identify React elements among their siblings. If two siblings share the same key, React cannot reliably associate each element with its previous identity, which can lead to incorrect state reuse or unexpected list behavior. I use stable, unique IDs within each sibling list.

<a id="qa-03-027"></a>
### 3.27. Why do you not need error boundaries for event handlers?

**Interview answer:** Event handlers run outside the rendering process, so a normal exception in a click handler does not prevent React from knowing what UI to display. Error boundaries do not catch ordinary event-handler errors. I handle them with `try/catch`, rejected-Promise handling, and suitable user feedback or logging.

<a id="qa-03-028"></a>
### 3.28. Why should not call setState in componentWillUnmount?

**Interview answer:** `componentWillUnmount` is intended for cleanup, such as removing listeners, clearing timers, or cancelling work. Calling `setState()` there is unnecessary because the component is being removed and will not display another update. I release resources rather than trying to update state during unmounting.

<a id="qa-03-029"></a>
### 3.29. What are the three main steps React follows to update the screen?

**Interview answer:** React updates the screen through three steps: a trigger schedules an initial render or state update, the render phase calculates the next UI, and the commit phase applies necessary changes to the DOM. The browser then paints the result. Rendering does not always produce a DOM change.

<a id="qa-03-030"></a>
### 3.30. How does React work behind the scenes?

**Interview answer:** React schedules updates when state, props, or subscribed values change. It renders components and reconciles the returned elements with the previous tree, then commits necessary host changes. React's scheduling and batching can reduce or prioritize work. I distinguish component renders from actual DOM changes when debugging performance.

<a id="qa-03-031"></a>
### 3.31. What is the difference between mounting and updating in terms of effect behavior?

**Interview answer:** An Effect's setup runs when its component mounts, and on later commits when its dependencies require resynchronization. Before rerunning that Effect, React cleans up the previous setup. On unmount, the cleanup releases the remaining resources. Development Strict Mode can also test setup and cleanup with an extra cycle.

<a id="qa-03-032"></a>
### 3.32. Should you use componentWillMount in a modern React application?

**Interview answer:** No. `componentWillMount` is a legacy lifecycle method and is unsafe for modern rendering behavior. I initialize class state in the constructor or class fields, and perform subscriptions or client-side side effects in `componentDidMount`. In function components, I choose state initialization or Effects based on the actual task.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-033"></a>
### 3.33. What are the lifecycle methods going to be deprecated in React v16?

**Interview answer:** The old `componentWillMount`, `componentWillReceiveProps`, and `componentWillUpdate` lifecycles were deprecated and given `UNSAFE_` names during the React 16 lifecycle transition. Their assumptions do not fit interruptible rendering. I use modern lifecycle methods or Hooks, avoiding derived state and side effects during render unless the API explicitly supports the pattern.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-034"></a>
### 3.34. Which is preferred option with in callback refs and findDOMNode()?

**Interview answer:** I prefer explicit refs over `findDOMNode()`, because refs identify the intended DOM node without depending on a component's internal output. They also work better with component composition and Strict Mode. `findDOMNode` was deprecated and removed in React 19, so I use object refs, callback refs, or deliberate ref forwarding.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-03-035"></a>
### 3.35. Why is a component constructor called only once?

**Interview answer:** A class constructor initializes a newly created component instance, so it is not called on every ordinary update. If React remounts the component because its identity changes, a new constructor call occurs. Development Strict Mode may also invoke constructors an extra time to check purity, so I do not rely on an absolute guarantee of one call.

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

**Interview answer:** The dependency array tells React which reactive values an Effect depends on. React compares each dependency using `Object.is` and reruns the Effect if one changes. With `[]`, the Effect is associated with mounting; without an array, it runs after every committed render. Cleanup runs before a changed-dependency setup and on unmount.

<a id="qa-04-006"></a>
### 4.6. Can you combine **useReducer** with **useContext**?

**Interview answer:** Yes. `useReducer` manages complex state transitions, and Context makes the existing state and dispatch function available to nested components. For example, an `AuthProvider` can expose `user`, `status`, and `dispatch`. It is useful for moderate shared state, but a large or frequently changing store may benefit from a dedicated library with selectors.

<a id="qa-04-007"></a>
### 4.7. Can you have multiple useEffect hooks in a single component?

**Interview answer:** Yes. A component can have several `useEffect` calls, and each one can handle a separate concern, such as fetching data, setting a timer, or adding an event listener. Keeping effects focused makes cleanup and debugging easier.

<a id="qa-04-008"></a>
### 4.8. How are useEffect, useLayoutEffect, and useInsertionEffect different?

**Interview answer:** `useEffect` runs after React commits updates and is normally used for external synchronization. `useLayoutEffect` runs before the browser paints, so it is useful for layout measurement but can block painting. `useInsertionEffect` is mainly for CSS-in-JS libraries that need to insert styles at a specific stage.

<a id="qa-04-009"></a>
### 4.9. Can you explain useEffect, including its cleanup and dependency array?

**Interview answer:** `useEffect` synchronizes a component with an external system, such as a subscription or network request. With no dependency array it runs after every committed render; with `[]` it runs on mount; and with dependencies it runs again when they change. React runs cleanup before the next setup and on unmount. Development Strict Mode can also perform an extra setup-cleanup cycle. Effects usually run after paint, but that is not guaranteed for every interaction.

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

**Interview answer:** I create a Context provider that supplies feature flag values and a custom Hook such as `useFeatureFlag(key)` that reads a specific flag. Components can then conditionally render features without prop drilling. I define safe defaults while flags are loading and remember that frontend flags do not replace backend authorization.

<a id="qa-04-012"></a>
### 4.12. How would you manage event listeners with useEffect?

**Interview answer:** I add a listener inside `useEffect` and remove the same listener in its cleanup function. I also include changing values in the dependency array so the handler does not read stale state.

<a id="qa-04-013"></a>
### 4.13. Can you explain fix a `useEffect` that has missing dependencies (the ESLint exhaustive-deps warning)?

**Interview answer:** I fix exhaustive-deps warnings by including every reactive value read by the Effect. If that causes repeated runs, I examine the design: move event-driven work to a handler, derive values during render, or move object creation inside the Effect. For non-reactive logic I may use an Effect Event where supported, rather than suppressing dependencies and risking stale closures.

<a id="qa-04-014"></a>
### 4.14. How do reactive dependencies in the useEffect dependency array affect its execution behavior?

**Interview answer:** The `useEffect` hook accepts an optional dependencies argument that accepts an array of reactive values. The dependency array determines when the effect runs. i.e, It makes `useEffect` reactive to changes in specified values. How Dependency Array Affects Behavior.

<a id="qa-04-015"></a>
### 4.15. How do you fetch data with `useEffect`? What are the pitfalls?

**Interview answer:** For a simple client-side request, I can fetch inside `useEffect` and clean it up using `AbortController`. I handle loading, success, and error states and include reactive dependencies. The main pitfalls are stale responses, duplicate fetches in development, request waterfalls, and missing caching. For production server state, I generally prefer route loaders or TanStack Query.

<a id="qa-04-016"></a>
### 4.16. How does `useOptimistic` (React 19) differ from manually managing optimistic state with `useState`?

**Interview answer:** `useOptimistic` manages a temporary optimistic view while an Action is pending. It calculates the optimistic value from real state and an optimistic update, then the UI settles back to the authoritative state when the action finishes. With manual `useState`, I must track pending updates and rollback myself. I still handle server errors and make sure successful updates refresh the real state.

<a id="qa-04-017"></a>
### 4.17. How does `useRef` differ from a regular variable?

**Interview answer:** Regular variables reset on each render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for function components.

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

**Interview answer:** An infinite effect loop usually happens when an effect updates state and then runs again because that state or another unstable dependency changed. I inspect the dependency list and move work to the right event handler or derived calculation.

<a id="qa-04-021"></a>
### 4.21. Does useImperativeHandle require forwardRef in React 19?

**Interview answer:** In React 19, a function component can accept `ref` as a normal prop and pass it to `useImperativeHandle`, so `forwardRef` is not required for new React 19 function components. In React 18 and earlier, `forwardRef` was normally how the parent ref reached the function component. I match the pattern to the React version used by the project.

<a id="qa-04-022"></a>
### 4.22. In what order do multiple useEffect Hooks execute?

**Interview answer:** React runs effects in the order they are declared within a component after the commit, while cleanup behavior depends on whether the dependencies changed or the component unmounted. I keep independent effects separate.

<a id="qa-04-023"></a>
### 4.23. What happens when you omit the useEffect dependency array?

**Interview answer:** If no dependency array is given, `useEffect` runs after each committed render. This is particularly useful for effects that must follow every render, but can be costly and may create loops.

<a id="qa-04-024"></a>
### 4.24. How do you manage useEffect dependencies correctly?

**Interview answer:** List every value from the component that an effect reads and that can change, such as props, state, and functions. If an object or callback changes every render, move it inside the effect or make its identity stable. Do not suppress dependency warnings just to stop re-renders.

<a id="qa-04-025"></a>
### 4.25. Can you explain react.useMemo() memoizing a JSX element to skip a child's re-render?

**Interview answer:** `useMemo(() => <ExpensiveChild />, [])` can cache a React element object. When React sees the same element reference, it may reuse the previous subtree instead of rendering the child again. However, I generally prefer `React.memo(ExpensiveChild)` or moving state down because memoizing JSX directly can make code harder to read.

<a id="qa-04-026"></a>
### 4.26. When does the setup function inside useEffect run?

**Interview answer:** An Effect's setup runs after React commits the component. It runs on mount and again when its dependencies change, after cleanup of the previous setup. The exact relationship to browser paint depends on the interaction and scheduling. Development Strict Mode may also run an extra setup-cleanup cycle.

<a id="qa-04-027"></a>
### 4.27. What is a stale closure in useEffect, and how do you fix it?

**Interview answer:** A stale closure happens when an Effect or callback keeps using values captured during an earlier render. This often happens when dependencies are missing. I fix it by including the correct dependencies, using functional state updates where appropriate, or restructuring the Effect.

<a id="qa-04-028"></a>
### 4.28. How do you handle subscriptions safely in useEffect?

**Interview answer:** For a subscription, I subscribe in `useEffect` and return a cleanup function that unsubscribes. That prevents duplicate listeners and memory leaks when dependencies change or the component unmounts.

<a id="qa-04-029"></a>
### 4.29. When does useEffect cleanup run before the next effect?

**Interview answer:** When dependencies change, React runs the previous effect’s cleanup before running the next setup. It also runs cleanup on unmount. In development Strict Mode, extra setup and cleanup checks may occur.

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

**Interview answer:** An empty dependency array means the Effect's setup runs when the component mounts, and its cleanup runs on unmount. In development Strict Mode, React can run an additional setup-cleanup-setup cycle to test cleanup. It is therefore better to think of this as mount-related synchronization, not a guarantee of exactly one execution.

<a id="qa-04-034"></a>
### 4.34. Can you explain useMemo recomputing when a dependency array value is a new array reference each render?

**Interview answer:** `useMemo` checks dependencies by identity using `Object.is`. If I create an array with `const data = [1, 2, 3]` on each render and use it as a dependency, the reference changes, so React recalculates the memoized value. I move constant data outside the component or memoize it when a stable reference is actually needed.

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

**Interview answer:** The useEffect React Hook is used for performing side effects in function components. With the help of useEffect, you will inform React that your component requires something to be done after rendering the component or after a state change. The function you have passed(can be referred to as “effect”) will be remembered by React and call afterwards the performance of DOM updates is over.

<a id="qa-04-041"></a>
### 4.41. What happens if you return a Promise from useEffect?

**Interview answer:** An Effect callback must return either a cleanup function or nothing. An `async` callback returns a Promise, which React cannot use as cleanup and may warn about or fail when cleaning up. I define an async function inside the Effect, call it there, and return synchronous cleanup that cancels or ignores outdated work.

<a id="qa-04-042"></a>
### 4.42. What is useContext? What are the steps to follow for useContext?

**Interview answer:** The `useContext` hook is a built-in React Hook that lets you access the value of a context inside a function component without needing to wrap it in a <Context.Consumer> component. It helps you avoid prop drilling (passing props through multiple levels) by allowing components to access shared data like themes, authentication status, or user preferences.

<a id="qa-04-043"></a>
### 4.43. What is `useLayoutEffect` and how does it differ from `useEffect`?

**Interview answer:** `useLayoutEffect` has a similar API to `useEffect`, but runs after DOM mutations and before browser repaint. I use it for layout measurement or positioning that must happen before the user sees the screen. `useEffect` is my default for non-visual synchronization because layout effects can block paint. Passive Effects usually run later, but not invariably after paint.

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

**Interview answer:** Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood; minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms.

<a id="qa-04-048"></a>
### 4.48. What is React Query (TanStack Query) / SWR, and why use them over manual `useEffect` fetching?

**Interview answer:** TanStack Query and SWR help manage data that comes from a server. They provide caching, background refetching, and loading or error states, so I do not need to rebuild those features manually in every `useEffect`.

<a id="qa-04-049"></a>
### 4.49. What is React.memo? How is it different from useMemo and useCallback?

**Interview answer:** `React.memo` can skip a component's parent-driven render when its props have not changed. `useMemo` caches a calculated value inside a component, while `useCallback` caches a function reference. I use them for different optimization problems and do not assume they prevent all renders. I profile before introducing memoization.

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

**Interview answer:** useState causes components to re-render after state updates whereas useRef doesn't cause a component to re-render when the value or state changes. useRef is like a "box" that can hold a mutable value in its (`.current`) property. useState allows us to update the state inside components. While useRef allows referencing DOM elements and tracking values.

<a id="qa-04-054"></a>
### 4.54. What problems does React Query solve vs raw `useEffect` fetching?

**Interview answer:** TanStack Query provides a cache for server data, deduplicates requests, handles retries and background refetching, and exposes useful loading and error states. With raw `useEffect`, I would have to build those features and handle race conditions myself. I still use plain effects for genuine subscriptions and synchronization with non-React APIs.

<a id="qa-04-055"></a>
### 4.55. How does React Context help you avoid prop drilling?

**Interview answer:** Context lets an ancestor provide shared data directly to interested descendants without passing the value through every intermediate component. I create a Context, wrap the relevant tree in a provider, and read it using `useContext`. The consumer receives the nearest provider's value, or the Context default when there is no matching provider.

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

**Interview answer:** I use an `AbortController` inside `useEffect`, pass `controller.signal` to `fetch`, and call `controller.abort()` in the cleanup function. This cancels the request on unmount or the Effect runs again and helps avoid outdated responses.

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

**Interview answer:** The React Hook cannot be considered as a replacement for Redux (It is an open-source, JavaScript library useful in managing the app state) when it comes to the management of the global application state tree in large complex applications, even though the React will provide a useReducer hook that manages state transitions similar to Redux.

<a id="qa-04-066"></a>
### 4.66. Can useRef be used to store previous values?

**Interview answer:** Yes. A ref can remember the previous render's value without triggering another render. I create `const previous = useRef(value)` and set `previous.current = value` in an Effect after rendering. On the next render, it still holds the previous value. I use this for comparisons, not as the main source of visible UI state.

<a id="qa-04-067"></a>
### 4.67. Can useState take a function as an initial value?

**Interview answer:** Yes. Passing a function to `useState`, such as `useState(() => calculateInitialValue())`, performs lazy initialization. React calls the initializer when initializing the state rather than on each render. The function must be pure because development Strict Mode may call it twice to detect impurities.

<a id="qa-04-068"></a>
### 4.68. Can you describe the useMemo() Hook?

**Interview answer:** The `useMemo()` Hook in React is used to optimize performance by memoizing the result of expensive calculations. It ensures that a function is only re-executed when its dependencies change, preventing unnecessary computations on every re-render. Syntax `computeExpensiveValue`: A function that returns the computed result. `dependencies`: An array of values that, when changed, will cause the memoized function to re-run.

<a id="qa-04-069"></a>
### 4.69. Can you dispatch multiple actions in a row with useReducer?

**Interview answer:** Yes, `useReducer` lets me call `dispatch` multiple times, but each dispatch schedules an update rather than immediately changing the state value in the current closure. React may batch the updates. If multiple operations are logically one transaction, I may instead dispatch one action and let the reducer calculate the combined next state.

<a id="qa-04-070"></a>
### 4.70. Can you explain how useState works internally?

**Interview answer:** React’s hooks, including `useState`, rely on some internal machinery that keeps track of state per component and per hook call during rendering. Here's a simplified explanation of the internal mechanics: Hook List / Linked List React maintains a linked list or array of "hook states" for each component. When a component renders, React keeps track of which hook it is currently processing via a cursor/index.

<a id="qa-04-071"></a>
### 4.71. When would you use a custom Hook instead of a higher-order component or render prop?

**Interview answer:** Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when we need to wrap a component (for example, code splitting, legacy compatibility). Render props: when JSX composition is specifically needed.

<a id="qa-04-072"></a>
### 4.72. How do you clean up side effects in a React component?

**Interview answer:** I return a cleanup function from `useEffect` for work that must be undone, such as an event listener, timer, socket subscription, or in-flight request. The cleanup runs before the Effect re-runs with changed dependencies and on unmount. That prevents duplicate subscriptions and stale work from updating the wrong screen.

<a id="qa-04-073"></a>
### 4.73. How do React Hooks differ from class components?

**Interview answer:** Function components use Hooks such as `useState` and `useEffect` for state and side effects. Class components use `this.state`, `setState`, and lifecycle methods. I usually choose function components for new work because Hooks make logic sharing simpler, but I can maintain older class components too.

<a id="qa-04-074"></a>
### 4.74. Do Hooks cover all the functionalities provided by the classes?

**Interview answer:** Hooks cover most work that previously required class components, including state, side effects, refs, and Context. One important exception is traditional React error boundaries, which still use class-component lifecycle methods or a library that wraps them.

<a id="qa-04-075"></a>
### 4.75. Do Hooks replace render props and higher order components?

**Interview answer:** Hooks do not automatically replace every HOC or render-prop pattern, but they make sharing stateful logic simpler for most new components. I generally use a custom Hook first and keep HOCs or render props when their API or composition is useful.

<a id="qa-04-076"></a>
### 4.76. Does React Hook work with static typing?

**Interview answer:** Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. React Hooks are functions that are designed to make sure about all attributes must be statically typed. For enforcing stricter static typing within our code, we can use the React API with custom Hooks.

<a id="qa-04-077"></a>
### 4.77. What types of Hooks are available in React?

**Interview answer:** React provides built-in Hooks for state (`useState`, `useReducer`), Context (`useContext`), Effects (`useEffect`, `useLayoutEffect`), refs (`useRef`), performance (`useMemo`, `useCallback`, `useTransition`), and other specialized use cases. Custom Hooks combine built-in Hooks to reuse stateful logic across components.

<a id="qa-04-078"></a>
### 4.78. How would you build a simple component using React Hooks?

**Interview answer:** I would build a counter using a function component and `useState`. I initialize the count with `const [count, setCount] = useState(0)`, display it in JSX, and use `onClick={() => setCount(c => c + 1)}` on a button. This demonstrates how a state update causes React to render the new UI.

<a id="qa-04-079"></a>
### 4.79. Can you explain React Hooks and why they were introduced?

**Interview answer:** Hooks are functions that let function components use React features such as state, effects, refs and Context. They reduce the need for class components and help reuse stateful logic.

<a id="qa-04-080"></a>
### 4.80. What are Custom Hooks?

**Interview answer:** A custom Hook is a JavaScript function whose name starts with `use` and that can call React Hooks. It extracts reusable stateful logic, such as a subscription, data-fetching workflow, or form behavior, without adding extra component nesting. Each call has its own state unless it deliberately connects to shared state.

<a id="qa-04-081"></a>
### 4.81. How do you share state logic between components using custom hooks?

**Interview answer:** A custom Hook extracts reusable stateful logic into a function whose name begins with `use`. For example, `useLocalStorage(key)` could manage a state value and synchronize it with browser storage. Calling the same custom Hook in two components does not automatically share one state instance—each call has its own Hook state unless the Hook connects to a shared store or Context.

<a id="qa-04-082"></a>
### 4.82. Can You Use Multiple Contexts in One Component?

**Interview answer:** Yes. A component can consume multiple Contexts by calling `useContext` separately for each one, for example `useContext(AuthContext)` and `useContext(ThemeContext)`. I provide the corresponding values above the component and keep unrelated Contexts separate when that helps maintainability or performance.

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

**Interview answer:** No. Existing class components can continue to work, and a project can contain both function and class components. I introduce Hooks in new components or refactor existing components when there is a clear maintainability benefit, rather than rewriting working code only to adopt Hooks.

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

**Interview answer:** I call ordinary Hooks at the top level of function components or custom Hooks, never inside loops, conditionals, or event handlers. React relies on consistent Hook call order to associate state with the correct call. The special `use()` API is an exception to the conditional-call restriction, but it has its own rules. I use the Hooks ESLint plugin to catch violations.

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

**Interview answer:** Hooks let function components use state, effects, context, refs, and reusable logic. For simple local data, I use `useState`; for more involved state transitions, I may use `useReducer`.

<a id="qa-04-095"></a>
### 4.95. How do you avoid unnecessary object/function recreation?

**Interview answer:** I move values that do not depend on props or state outside the component. When reference identity actually matters, I use `useMemo` for computed objects or arrays and `useCallback` for callbacks, with complete dependencies. Creating a new value during render is not automatically a performance problem, so I avoid unnecessary memoization.

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

**Interview answer:** After a client-side route change, I move focus to a meaningful element such as the new page heading when appropriate, because SPA navigation does not always provide the same focus behavior as a full page load. I can use a ref and call `focus()` after navigation. I also update the document title and preserve expected keyboard behavior.

<a id="qa-04-100"></a>
### 4.100. How do you pass parent data to the 5th child component?

**Interview answer:** Options in order of preference: (1) Component composition. restructure so the component needing data isn't 5 levels deep. (2) React Context. create a context, wrap with Provider at the parent level, consume with useContext at the child. no prop drilling needed. (3) State management (Redux/Zustand). store state globally, child subscribes directly. (4) Prop drilling. workable for 2-3 levels, painful at 5 levels.

<a id="qa-04-101"></a>
### 4.101. How do you prevent an expensive component from blocking user input (e.g., a large table filtering as you type)?

**Interview answer:** I keep the input state urgent and use `useDeferredValue` for the value consumed by an expensive table, or `useTransition` for the non-urgent result update. I also profile the filtering and consider memoization, virtualization, or moving expensive computation off the main thread. Transitions prioritize rendering but do not make a long synchronous calculation faster.

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

**Interview answer:** `useReducer` manages state through a reducer function. The reducer receives the existing state and an action, and returns the updated state. For a counter, I could dispatch `{ type: 'increment' }` or `{ type: 'reset' }` instead of putting all update logic inside click handlers.

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

**Interview answer:** Diagnostic first. profile with React DevTools Profiler to identify: Components rendering too often → add React.memo, fix prop references Expensive computations → wrap with useMemo Large bundle → code splitting with React.lazy, tree shaking Slow initial load → SSR/SSG, preloading critical resources Memory leaks → check useEffect cleanups, event listener removal Long list rendering → implement virtualization Network waterfall → parallel data fetching, caching with React Query/SWR.

<a id="qa-04-111"></a>
### 4.111. Is dispatch from useReducer asynchronous and does it update state immediately?

**Interview answer:** Calling `dispatch(action)` from `useReducer` schedules a state update; it does not synchronously replace the state variable in the current render. React processes the queued action with the reducer to calculate the next state. I read the new state in the next render or an Effect rather than expecting `dispatch()` to return it.

<a id="qa-04-112"></a>
### 4.112. Is Hooks cover all use cases for classes?

**Interview answer:** Hooks cover most common uses of class components, including state, effects, and Context. However, React's built-in error boundary mechanism still uses class lifecycle methods, so a Hook cannot replace a custom class-based error boundary directly. I normally write new components as functions and maintain legacy class components where necessary.

<a id="qa-04-113"></a>
### 4.113. Does a React state setter update the state variable immediately?

**Interview answer:** A `useState` setter schedules React to update state; it does not change the state value inside the current render or event-handler closure. So reading `count` immediately after `setCount(count + 1)` still gives the old snapshot. If the new value depends on the previous one, I use `setCount(prev => prev + 1)`.

**Optional coding illustration:**
```jsx
setCount(prev => prev + 1); // queues an update
// count here still belongs to the current render snapshot
```

<a id="qa-04-114"></a>
### 4.114. What makes a custom Hook easy to maintain?

**Interview answer:** A maintainable custom Hook has a descriptive `use` name, one clear responsibility, a small input/output contract, and predictable state behavior. I keep dependencies accurate and clean up any external subscriptions or timers. I avoid coupling the Hook to unrelated components and test the behavior it exposes.

<a id="qa-04-115"></a>
### 4.115. Map class lifecycle methods to hooks?

**Interview answer:** `componentDidMount` → `useEffect(() => {...}, [])` `componentDidUpdate` → `useEffect(() => {...}, [dep])` `componentWillUnmount` → cleanup function returned from `useEffect` `getDerivedStateFromProps` → compute derived state inline or in `useMemo`.

<a id="qa-04-116"></a>
### 4.116. Why might you memoize a Context provider value?

**Interview answer:** When a provider passes a new object on each render, Context consumers can update even if the meaningful values did not change. `useMemo` can stabilize that object, but splitting Contexts may be a better long-term solution.

<a id="qa-04-117"></a>
### 4.117. What does React Compiler optimize automatically?

**Interview answer:** React Compiler automatically optimizes eligible React code by memoizing work where it is safe, reducing the need for manual `useMemo`, `useCallback`, and `React.memo`. It is not a guarantee that every component is fast; I still measure performance and follow React's purity rules. For existing code, I check compiler compatibility before enabling it.

<a id="qa-04-118"></a>
### 4.118. How do you safely manage timers and intervals in React?

**Interview answer:** I create timers and intervals inside an Effect when they are tied to a component's lifecycle. The cleanup calls `clearTimeout` or `clearInterval` so old timers cannot continue running after an update or unmount. For state updates based on the previous value, I use functional updaters to avoid stale closures.

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

**Interview answer:** When all of a `useCallback` Hook's dependencies are unchanged, React can return the previously cached function reference. This helps when a memoized child receives the callback as a prop or another Hook relies on its identity. It does not make the callback's execution faster or eliminate the need for correct dependencies.

<a id="qa-04-122"></a>
### 4.122. Can you explain useDeferredValue keeping input responsive during an expensive re-render?

**Interview answer:** `useDeferredValue` lets a slow part of the screen lag behind an urgent input update. For example, the search box updates immediately while a large filtered list renders with the previous query until the new one is ready. It does not throttle network calls by itself; I would still debounce or cancel requests if necessary.

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

**Interview answer:** I can store the previous committed value in a ref and update that ref in an Effect when the value changes. This lets event handlers or subsequent Effects access the prior value without triggering a render. If the previous value must be displayed in the UI, I use a suitable state-based pattern rather than relying on a ref read during rendering.

<a id="qa-04-127"></a>
### 4.127. Can you explain useTransition keeps UI responsive?

**Interview answer:** I would keep the text input update urgent and wrap the expensive results update in `startTransition`. React can then keep typing responsive while it renders the lower-priority results. `isPending` tells us when the transition is still in progress.

<a id="qa-04-128"></a>
### 4.128. What are Custom React Hooks, and How Can You Develop One?

**Interview answer:** Custom Hooks in React are JavaScript functions that allow you to extract and reuse component logic using React's built-in Hooks like `useState`, `useEffect`, etc. They start with the word "use" and let you encapsulate logic that multiple components might share—such as fetching data, handling forms, or managing timers—without repeating code.

<a id="qa-04-129"></a>
### 4.129. What are the best practices for using React Hooks?

**Interview answer:** I follow the Rules of Hooks, keep custom Hooks focused, and use descriptive names. I include all reactive Effect dependencies, clean up subscriptions and timers, and avoid storing derived data unnecessarily. I use the Hooks ESLint rules and apply memoization only when it solves a real performance or identity problem.

<a id="qa-04-130"></a>
### 4.130. What are Higher-Order Components (HOCs)?

**Interview answer:** A higher-order component is a function that accepts a component and returns an enhanced component. For example, an HOC can inject authentication information or wrap a component with logging. Custom Hooks are often simpler for reusing stateful logic, but HOCs remain useful when I need to wrap or enhance a component's interface.

<a id="qa-04-131"></a>
### 4.131. What are stateless components?

**Interview answer:** A stateless component does not manage its own changing state. It renders based on inputs such as props or Context. Function components can be either stateful or stateless because Hooks allow them to manage state. I use stateless components for reusable presentation when state belongs elsewhere.

<a id="qa-04-132"></a>
### 4.132. What are the common usecases of useRef hook?

**Interview answer:** Some of the common cases are: \* Automatically focus an input when a component mounts. \* Scroll to a specific element. \* Measure element dimensions (`offsetWidth`, `clientHeight`). \* Control video/audio playback. \* Integrate with non-React libraries (like D3 or jQuery). ### What is useImperativeHandle Hook? Give an example. `useImperativeHandle` is a React Hook that allows a **child component to expose custom functions or properties** to its parent component, when using `ref`.

<a id="qa-04-133"></a>
### 4.133. What are the rules needs to follow for hooks?

**Interview answer:** I call Hooks only at the top level of React function components or custom Hooks. I do not call them in loops, conditions, or nested functions, because React must see the same Hook order on each render.

<a id="qa-04-134"></a>
### 4.134. What are the rules that must be followed while using React Hooks?

**Interview answer:** Hooks have two key rules: call them only at the top level, and call them only inside React function components or custom Hooks. These rules let React match each Hook with the right internal state.

<a id="qa-04-135"></a>
### 4.135. What are the sources used for introducing hooks?

**Interview answer:** Hooks were influenced by earlier experiments in functional component APIs and stateful logic reuse, including render-prop patterns and subscription-based approaches. The key motivation was to let function components reuse stateful behavior without complex nesting or classes. I would focus on that design motivation rather than memorizing historical experiments.

<a id="qa-04-136"></a>
### 4.136. What are the usecases of useLayoutEffect?

**Interview answer:** I use `useLayoutEffect` when work must happen before the browser repaints, such as measuring a tooltip and correcting its position to avoid flicker. It can also help integrate libraries that require synchronous layout measurements. For network requests, subscriptions, or ordinary non-visual synchronization, I prefer `useEffect`.

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

**Interview answer:** The `useReducer` hook is a React hook used to manage complex state logic inside function components. It is conceptually similar to Redux. i.e, Instead of directly updating state like with `useState`, you dispatch an action to a reducer function, and the reducer returns the new state. The `useReducer` hook takes three arguments: `reducer`: A function `(state, action) => newState` that handles how state should change based on the action.

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

**Interview answer:** A smart or container component handles state, data access, and application logic. A dumb or presentational component focuses on displaying its inputs and notifying the parent through callbacks. These are design roles, not different React component types. Custom Hooks let me separate logic from presentation without always requiring a separate container.

<a id="qa-04-151"></a>
### 4.151. What is a monorepo and how does it relate to React projects?

**Interview answer:** A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps.

<a id="qa-04-152"></a>
### 4.152. What is a render prop? How does it compare to Hooks?

**Interview answer:** A render prop is a function supplied to a component that determines what UI it renders using the data or behavior it exposes. This shares logic through composition. Custom Hooks can share stateful logic with less nesting, while render props remain useful when the consumer needs control over the rendered output.

<a id="qa-04-153"></a>
### 4.153. What is focus management and why does it matter?

**Interview answer:** After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes.

<a id="qa-04-154"></a>
### 4.154. What is lazy initialization in `useState`?

**Interview answer:** Lazy initialization means passing a function to `useState`, such as `useState(() => expensiveCalc())`. React uses its result as the initial state instead of recalculating it on every render. The initializer should be pure; development Strict Mode may invoke it more than once to check purity.

<a id="qa-04-155"></a>
### 4.155. What is the purpose of eslint plugin for hooks?

**Interview answer:** The ESLint plugin enforces rules of Hooks to avoid bugs. It assumes that any function starting with ”use” and a capital letter right after it is a Hook. In particular, the rule enforces that, Calls to Hooks are either inside a PascalCase function (assumed to be a component) or another useSomething function (assumed to be a custom Hook).

<a id="qa-04-156"></a>
### 4.156. What is the `React-error-boundary` library?

**Interview answer:** `react-error-boundary` is a library that provides reusable error boundaries, customizable fallback UI, and reset behavior. Its `useErrorBoundary()` Hook can report an error to a nearby boundary or reset it. I use it to avoid repeatedly implementing class-based boundary logic while preserving useful recovery and logging behavior.

<a id="qa-04-157"></a>
### 4.157. What is the `useTransition` hook for performance?

**Interview answer:** Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator.

<a id="qa-04-158"></a>
### 4.158. What is the container/presenter pattern and is it still relevant?

**Interview answer:** The container/presenter pattern separates data handling from UI rendering. The container fetches or prepares information, while the presenter displays it. Hooks make this separation more flexible today.

<a id="qa-04-159"></a>
### 4.159. What is the difference between `startTransition` and `useTransition`?

**Interview answer:** `startTransition` is the standalone function (usable outside components, for example, in a vanilla event handler) for marking an update as a transition; `useTransition` is the Hook version that also gives you an `isPending` boolean for showing a pending UI state.

<a id="qa-04-160"></a>
### 4.160. What is the difference between a development build and a production build of a React app?

**Interview answer:** Development builds include extra warnings, Strict Mode double-invocation, unminified code with readable stack traces, and devtools hooks. Production builds strip these, minify/mangle code, and often run additional optimizations (dead code elimination), resulting in a smaller, faster bundle with less helpful error messages.

<a id="qa-04-161"></a>
### 4.161. What is the difference between optimistic and pessimistic updates?

**Interview answer:** An optimistic update changes the UI immediately before the server confirms success, then reconciles or rolls back the result if the request fails. A pessimistic update waits for confirmation before changing the UI. I choose optimistic updates for reversible, low-risk actions and wait for confirmation when correctness matters more than immediate feedback.

<a id="qa-04-162"></a>
### 4.162. What is the order of hook execution in a component?

**Interview answer:** Ordinary Hooks are called in source-code order during rendering. React uses that consistent ordering to associate each Hook call with its stored state. This is why ordinary Hooks must not be conditional. Effect callbacks are different: their setup and cleanup run at their appropriate phases after rendering, not simply when the Hook call is encountered.

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

**Interview answer:** The React 19 `use()` API reads a resource such as a Promise or Context during rendering. Reading a pending supported Promise can suspend the component and show the nearest Suspense fallback. Unlike ordinary Hooks, `use()` may be called conditionally, but it still must be used within a React component or Hook and follows specific restrictions.

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

**Interview answer:** `useState` can store primitives, arrays, objects, functions, `null`, or `undefined`. I treat objects and arrays as immutable and create a new reference when changing them. If I want to store a function itself, I wrap it in another function because React interprets function arguments as initializers or updaters.

<a id="qa-04-171"></a>
### 4.171. When should you avoid using React’s useId?

**Interview answer:** I use `useId` for stable IDs that connect accessible labels and form elements. I do not use it as a React list key, a database ID, or an ID I need to predict. List keys should come from the data.

<a id="qa-04-172"></a>
### 4.172. When should you still apply manual performance optimizations in React?

**Interview answer:** I still optimize manually when profiling finds a real bottleneck, such as a slow list, expensive calculation, or unnecessary subscription update. Even with React Compiler, I first improve component structure and data flow, then apply targeted memoization or virtualization if necessary.

<a id="qa-04-173"></a>
### 4.173. Why do React Hooks make use of refs?

**Interview answer:** Earlier, refs were only limited to class components but now it can also be accessible in function components through the useRef Hook in React. The refs are used for: Managing focus, media playback, or text selection. Integrating with DOM libraries by third-party. Triggering the imperative animations.

<a id="qa-04-174"></a>
### 4.174. Why do we use array destructuring (square brackets notation) in `useState`?

**Interview answer:** `useState` returns an array containing the existing state value and the setter function. Array destructuring gives them clear names, such as `const [count, setCount] = useState(0)`, instead of accessing indexes `0` and `1` manually.

<a id="qa-04-175"></a>
### 4.175. Why React tab is not showing up in DevTools?

**Interview answer:** When the page loads, React DevTools sets a global named `__REACT_DEVTOOLS_GLOBAL_HOOK__`, then React communicates with that hook during initialization. If the website is not using React or if React fails to communicate with DevTools then it won't show up the tab.

<a id="qa-04-176"></a>
### 4.176. Why use functional updates with `useState`?

**Interview answer:** `setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

<a id="qa-04-177"></a>
### 4.177. When to use a Class Component over a Function Component?

**Interview answer:** I prefer function components and Hooks for most new React code because they make logic reuse and state management straightforward. I may still use a class when maintaining an existing class-based codebase or implementing a native error boundary, which has class lifecycle APIs. A maintained error-boundary library can provide a convenient functional-facing interface.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

---

<a id="section-05"></a>
## 5. Performance Optimization

*69 questions — [Back to contents](#contents)*

<a id="qa-05-001"></a>
### 5.1. Can you explain a React component re-renders again and again but you never called setState. Why?

**Interview answer:** A component can render even if it never calls its own state setter. Its parent may render, its props or consumed Context may change, or an external-store subscription may trigger an update. I use the Profiler to identify the actual cause. Unstable object or function props can prevent a memoized child from skipping these renders.

<a id="qa-05-002"></a>
### 5.2. When is component memoization worth using?

**Interview answer:** Memoization is helpful when a component renders frequently with the same props and the render work is expensive. I would measure performance first rather than memoize every component.

<a id="qa-05-003"></a>
### 5.3. Can you explain techniques for dynamic code splitting and lazy loading in multi-route SPAs?

**Interview answer:** Route‑based code splitting – using `React.lazy` with `Suspense`: Component‑level lazy loading – for heavy components like modals, charts, or editors: Pre‑loading – start loading a chunk before navigation using `webpackPrefetch`: Pre‑fetching on hover – trigger dynamic import when user hovers over a link. Bundler configuration – ensure chunks are named and optimized (for example, Webpack’s `splitChunks`).

<a id="qa-05-004"></a>
### 5.4. Given a slow React tree, how do you identify and fix the performance bottleneck?

**Interview answer:** I first reproduce the slow interaction and record it using React DevTools Profiler and browser performance tools. I identify which components render, how long they take, and what triggers the work. Based on the evidence, I might colocate state, stabilize props, memoize expensive calculations, or virtualize a list. I profile again to verify the improvement.

<a id="qa-05-005"></a>
### 5.5. How do you reduce the performance cost of a component that re-renders on every scroll event?

**Interview answer:** Throttle/debounce the scroll handler, or better, derive the needed value (for example, scroll position bucket) and only call `setState` when that derived value actually changes, avoiding a state update (and render) on every pixel of scroll.

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

**Interview answer:** `React.memo` compares props shallowly. If a parent creates a new object literal on each render, the object reference changes and the child can still render. I can stabilize that object with `useMemo` when necessary.

<a id="qa-05-011"></a>
### 5.11. What happens when you call a state updater function in React?

**Interview answer:** Calling a state updater queues a React state update. React then calculates the next value and schedules a render. If the new value depends on the previous one, I pass a function such as `setCount(c => c + 1)`.

<a id="qa-05-012"></a>
### 5.12. What are React Suspense and React.lazy? How do they enable code splitting?

**Interview answer:** In React, all components are bundled together and loaded at once. This can slow down the initial load, especially if the app is large. To avoid this from happening, React has an in-built feature that loads components only when they are needed, and this is called code splitting. Both React Suspense and React.lazy are used together to implement this code-splitting.

<a id="qa-05-013"></a>
### 5.13. When would you use `React.memo`?

**Interview answer:** I use `React.memo` for: Components that receive the same props often but re‑render due to parent re‑renders. Large components that are expensive to re‑render. Pure function components that depend on props only. Avoid over‑using `memo` because the shallow prop comparison itself costs time. Use it where profiling shows a benefit.

<a id="qa-05-014"></a>
### 5.14. What is `shouldComponentUpdate`? How does it relate to `React.memo`?

**Interview answer:** `shouldComponentUpdate(nextProps, nextState)` is a class lifecycle method that can return `false` to skip an unnecessary update. For function components, `React.memo` offers a similar prop-comparison optimization, but it is not identical: a memoized function component can still re-render because of its own state or Context changes.

<a id="qa-05-015"></a>
### 5.15. What is code splitting and how does React.lazy work internally?

**Interview answer:** Code splitting breaks the JS bundle into smaller chunks loaded on demand, improving initial load time. React.lazy(import('./Component')) creates a lazy component that triggers a dynamic import() when first rendered. Suspense provides the loading fallback UI while the chunk downloads. Internally, React.lazy wraps the promise. during render, if the promise is pending, React 'throws' it (using Suspense's error boundary mechanism), shows fallback, and resumes rendering when resolved.

<a id="qa-05-016"></a>
### 5.16. What is code splitting? How with `React.lazy`/`Suspense`?

**Interview answer:** Code splitting divides the JavaScript bundle into chunks that can load when necessary. In React, I can write `const Settings = lazy(() => import('./Settings'))` and render it inside `<Suspense fallback={<Spinner />}>`. That improves initial loading when a large screen is rarely visited, but I monitor loading waterfalls and provide useful fallbacks.

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

**Interview answer:** `React.memo` is less useful when a component is cheap to render or its props genuinely change on every parent render. New object or function references can also defeat the default comparison. It does not stop updates from local state or Context. I measure first rather than memoizing every component.

<a id="qa-05-022"></a>
### 5.22. When is useCallback useful?

**Interview answer:** `useCallback` is useful when a stable function reference prevents unnecessary child renders or helps keep dependencies stable. I do not wrap every handler in `useCallback`; I use it when profiling or component behavior shows a real benefit.

<a id="qa-05-023"></a>
### 5.23. Why does React re-render the whole component function on every update rather than patching just changed JSX?

**Interview answer:** React reruns a function component to calculate its next UI because components describe the desired result declaratively. React then reconciles that result and updates only the necessary DOM nodes; rerendering a function does not mean rebuilding the whole DOM. Expensive calculations can be memoized when profiling proves it helps.

<a id="qa-05-024"></a>
### 5.24. What is the difference between virtualization and windowing? Trade-offs?

**Interview answer:** Virtualization is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. Windowing is a specific implementation (for example, `react-window`) that renders a “window” of items. Trade-offs: Pros: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists.

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

**Interview answer:** Yes. React may calculate a new UI and then discard or restart that render, for example when more urgent work interrupts a transition. Only completed work that is committed changes the actual DOM. This is why I keep rendering pure and perform side effects in appropriate handlers or Effects.

<a id="qa-05-030"></a>
### 5.30. Can you force a component to re-render without calling setState?

**Interview answer:** By default, when your component's state or props change, your component will re-render. If your `render()` method depends on some other data, you can tell React that the component needs re-rendering by calling `forceUpdate()`. I would generally avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`.

<a id="qa-05-031"></a>
### 5.31. What is canary deployment, and why is it useful for React apps?

**Interview answer:** A canary deployment releases a new version to a small percentage of users first. I monitor errors and performance; if things look good, I increase traffic gradually. It helps me detect problems without affecting every user at once.

<a id="qa-05-032"></a>
### 5.32. Can you explain context re-render behavior – what should you know?

**Interview answer:** Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`.

<a id="qa-05-033"></a>
### 5.33. Can you explain cSS Animation Jank: A CSS animation is janky on mobile – how to identify and fix?

**Interview answer:** I record the animation using browser performance tools on a representative mobile device and look for long JavaScript, layout, or paint tasks. I avoid repeatedly animating layout-heavy properties such as `width` or `top` where a transform or opacity animation can achieve the same result. I also check image size, main-thread work, and reduced-motion accessibility.

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

**Interview answer:** Yes, We can use. It is often the easiest way to pass parameters to callback functions. But we need to optimize the performance while using it. Note: Using an arrow function in render method creates a new function each time the component renders, which may have performance implications.

<a id="qa-05-046"></a>
### 5.46. Name a few techniques to optimize React app performance?

**Interview answer:** I would start by measuring with React DevTools Profiler. Then I would optimize expensive calculations, use list virtualization for long lists, code-split large bundles, keep state local, and memoize only where it helps.

<a id="qa-05-047"></a>
### 5.47. How do you avoid a poor user experience while feature flags are loading?

**Interview answer:** I can load feature flags asynchronously and show a sensible loading state or a safe default while waiting. I avoid flashing a feature that a user should not see. Real permissions still need server-side enforcement.

<a id="qa-05-048"></a>
### 5.48. What are common React performance optimization techniques? (practical guide)?

**Interview answer:** I start by profiling the application. Depending on the bottleneck, I may colocate state, use stable keys, memoize expensive calculations or components, virtualize long lists, split bundles by route, and optimize network requests and images. I verify the improvement afterward instead of applying all optimizations automatically.

<a id="qa-05-049"></a>
### 5.49. What are common React performance pitfalls?

**Interview answer:** Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading.

<a id="qa-05-050"></a>
### 5.50. What happens if a child uses React.memo() and parent props don't change?

**Interview answer:** If a memoized child receives the same props by React's default `Object.is` comparisons, React can skip a parent-driven render. However, its own state or Context changes can still trigger rendering. If new object or callback references defeat memoization, I simplify the props or stabilize them when profiling shows a benefit.

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

**Interview answer:** Keys give each element a stable identity, allowing React to match items between re‑renders. Without keys, React might reuse DOM nodes incorrectly, leading to performance issues or broken UI (for example, lost focus, incorrect state). If keys are unstable (for example, using index when the list can reorder), React may re‑create elements unnecessarily or mix up internal state.

<a id="qa-05-055"></a>
### 5.55. Why function is preferred over object for `setState()`?

**Interview answer:** React may batch multiple `setState()` calls into a single update for performance. Because `this.props` and `this.state` may be updated asynchronously, we should not rely on their values for calculating the updated state. This counter example will fail to update as expected: The preferred approach is to call `setState()` with function rather than object.

<a id="qa-05-056"></a>
### 5.56. Why we need to pass a function to setState()?

**Interview answer:** I pass a function to a state setter when the next state depends on the pending previous state. React queues and may batch updates, so reading the current render's state directly can produce stale results. For example, repeated `setCount(c => c + 1)` calls correctly apply each increment. Direct values are fine for independent replacements.

<a id="qa-05-057"></a>
### 5.57. How would you improve a React application with poor SEO and slow time to interactive (TTI)?

**Interview answer:** SEO issues: - Server‑Side Rendering (SSR) or **Static Site Generation (SSG)** with frameworks like Next.js. - Ensure meta tags (title, description, Open Graph) are rendered on the server. - Use semantic HTML. Slow TTI (Time to Interactive): - Code splitting; lazy load non‑critical components and routes. - Bundle optimization; tree shaking, minification, remove unused dependencies. - **Reduce JavaScript**; audit bundle size, use lightweight alternatives. - Prioritize critical CSS; inline above‑the‑fold styles, defer non‑critical CSS. - Use `preconnect` and `preload` for important resources. - Optimize images; use modern formats.

<a id="qa-05-058"></a>
### 5.58. What is the 'why did you render' library?

**Interview answer:** Why Did You Render is a development debugging library that helps identify potentially avoidable React renders, including renders caused by new references whose contents are effectively unchanged. I use it together with React DevTools Profiler to investigate problems rather than treating every reported render as a bug.

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

**Interview answer:** I reproduce repeated navigation or the affected interaction, compare heap snapshots, and look for retained objects, detached DOM nodes, or steadily growing memory. Common causes are uncleared timers, event listeners, subscriptions, WebSockets, and unbounded caches. I fix cleanup or eviction and repeat the same measurement to confirm memory stabilizes.

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

**Interview answer:** I use Redux when shared client state is needed by many unrelated components or when updates require a predictable, centralized workflow. It provides explicit actions, reducers, selectors, and debugging tools. For state used by only one component, `useState` or `useReducer` is usually simpler, so I do not move every value into Redux.

<a id="qa-06-002"></a>
### 6.2. Compare Redux, MobX, Recoil/Jotai, Zustand, and Context for a large-scale app?

**Interview answer:** Redux (RTK): battle-tested, best DevTools/time-travel debugging, most boilerplate (mitigated by RTK), best for large teams needing strict patterns. MobX: less boilerplate via mutable observables, can be less predictable at scale. Recoil/Jotai: atomic, fine-grained, React-native mental model, newer ecosystem. Zustand: minimal API, great performance, good for medium complexity.

<a id="qa-06-003"></a>
### 6.3. What is a container component in Redux?

**Interview answer:** A Redux container is the part of an application that reads store state and dispatches actions for presentational components. Historically, `connect()` created container components. Today I generally use `useSelector` and `useDispatch` directly in a feature component or a custom Hook. The key idea is separating state coordination from UI presentation where it improves clarity.

<a id="qa-06-004"></a>
### 6.4. Can you explain context vs Redux – when to choose which?

**Interview answer:** Context is useful for shared values such as theme, locale, or authentication information, especially when updates are relatively simple. Redux Toolkit is useful for more complex shared state, selective subscriptions, middleware, and predictable action-based updates. I choose based on the data's ownership, update frequency, and debugging requirements.

<a id="qa-06-005"></a>
### 6.5. How do you handle async logic with Redux Toolkit?

**Interview answer:** For async logic, I can use `createAsyncThunk` in Redux Toolkit. It creates pending, fulfilled, and rejected actions around an async request. For API fetching with caching, RTK Query is another good option.

<a id="qa-06-006"></a>
### 6.6. How do you get redux scaffolding using create-React-app?

**Interview answer:** Older Redux projects used Create React App templates for scaffolding. Today, I would usually start with Vite or another maintained build setup, install Redux Toolkit and React Redux, create the store, and wrap the app with `<Provider store={store}>`.

<a id="qa-06-007"></a>
### 6.7. How do you manage global state? Compare Context, Redux, and modern alternatives?

**Interview answer:** So, this question is more targeted towards ways that YOU would take to manage the global state. So while I write the answer down, it’s best that you personalize it with examples that seem fit to you. Managing global state in React really depends on its scope and complexity. Most of the time, we can use ‘useState’ or ‘useReducer’, which may work well for component-specific data.

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

**Interview answer:** Relay is similar to Redux in that they both use a single store. The key distinction is that relay only manages state originated from the server, and all access to the state is used via GraphQL queries (for reading data) and mutations (for changing data). Relay caches the data for you and optimizes data fetching for you, by fetching only changed data and nothing more.

<a id="qa-06-013"></a>
### 6.13. How do you configure a Redux Toolkit store?

**Interview answer:** I use Redux Toolkit's `configureStore({ reducer: { users: usersReducer, auth: authReducer } })` to assemble the app store. It includes helpful middleware and Redux DevTools integration by default. Then I wrap the app with React Redux's `<Provider store={store}>` so components can use selectors and dispatch actions.

<a id="qa-06-014"></a>
### 6.14. How would you reset state in Redux?

**Interview answer:** For logout or reset, I can handle a dedicated action in the root reducer and return the initial state for the whole application or selected slices. I also clear any persisted sensitive state that should not survive the logout.

<a id="qa-06-015"></a>
### 6.15. How should you organize a Redux application?

**Interview answer:** I organize Redux code by feature, not by separating all actions and reducers into unrelated folders. For example, `features/users/usersSlice.ts` contains state and reducers, while nearby files contain selectors and API logic. Redux Toolkit's `createSlice` reduces boilerplate. This structure keeps related behavior together as the app grows.

<a id="qa-06-016"></a>
### 6.16. How does connect() work in React Redux, and what is the modern alternative?

**Interview answer:** `connect()` is the traditional React-Redux higher-order component. I would define `mapStateToProps` to select state and `mapDispatchToProps` for actions, then wrap the component with `connect()`. Today, I generally prefer `useSelector` and `useDispatch` in function components.

<a id="qa-06-017"></a>
### 6.17. How do you define a Redux Toolkit slice?

**Interview answer:** I call `createSlice` with a name, initial state, and reducers. Redux Toolkit then creates the reducer and action creators automatically. I can add `extraReducers` to handle actions from async thunks.

<a id="qa-06-018"></a>
### 6.18. Why is immutability important in Redux state updates?

**Interview answer:** Redux reducers should treat existing state as immutable and return the updated state instead of modifying the old object directly. This makes updates predictable and easier to debug. Redux Toolkit uses Immer to make immutable updates simpler.

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

**Interview answer:** Redux follows three main ideas: one store is the central source of application state, state is read-only from the outside so changes happen through dispatched actions, and reducers calculate the updated state with pure functions. In modern projects I use Redux Toolkit to implement these rules with less boilerplate and safer immutable updates.

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

**Interview answer:** I use Context for relatively simple shared values and keep local state near the components that own it. Redux Toolkit or Zustand becomes useful when many unrelated components need frequently changing shared state and selective subscriptions. Redux offers more conventions and middleware; Zustand offers a smaller store API. I choose the simplest solution that meets the requirements.

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

**Interview answer:** A presentational component mainly receives props and displays the UI. It does not need to know where global state comes from. That makes it easier to reuse and test.

<a id="qa-06-038"></a>
### 6.38. Do I need to keep all my state into Redux? Should I ever use React internal state?

**Interview answer:** It is up to the developer's decision, that is, it is developer's job to determine what kinds of state make up your application, and where each piece of state should live. Some users prefer to keep every single piece of data in Redux, to maintain a fully serializable and controlled version of their application at all times. Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, inside a component's internal state.

<a id="qa-06-039"></a>
### 6.39. Do you need to have a particular build tool to use Redux?

**Interview answer:** Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. We should be able to use it regardless of your JavaScript build process. Redux also offers a UMD build that can be used directly without any build process at all.

<a id="qa-06-040"></a>
### 6.40. How would you access Redux store outside a component?

**Interview answer:** Outside a React component, I can access a Redux store through its `getState()` and `dispatch()` methods. For a client-only app, I may import the configured store, but injecting the store where needed often improves testability. In server-rendered applications, I avoid sharing a global store across requests because it can leak user-specific state.

<a id="qa-06-041"></a>
### 6.41. What are the trade-offs of static typing in Flux-style and Redux applications?

**Interview answer:** Static types help detect mistakes in action payloads and state shapes before runtime. Modern Redux Toolkit has strong TypeScript support, so I would choose based on maintainability rather than assume Redux cannot be typed.

<a id="qa-06-042"></a>
### 6.42. Give an example of Reselect usage?

**Interview answer:** Reselect creates memoized selectors for Redux. For example, a selector can calculate the total value of items in a cart and reuse its previous result when the input state has not changed. That avoids repeating an expensive calculation after unrelated updates.

<a id="qa-06-043"></a>
### 6.43. Explain reducers and extraReducers – when to use each?

**Interview answer:** `reducers`: Used for actions that are directly handled by this slice. RTK automatically generates action creators with the same names. Good for synchronous, slice‑specific updates. `extraReducers`: Used to respond to actions defined elsewhere (for example, thunks, actions from other slices). It’s often used with `builder` callback to handle `pending`, `fulfilled`, `rejected` of async thunks.

<a id="qa-06-044"></a>
### 6.44. What are the downsides of Redux compared to Flux?

**Interview answer:** Redux puts state in one predictable store and changes it through actions and pure reducers. That structure helps debugging but can add boilerplate or complexity compared with simpler Flux-style or local-state solutions. I choose it when the app actually needs shared state management.

<a id="qa-06-045"></a>
### 6.45. What are the features of Redux DevTools?

**Interview answer:** Redux DevTools shows dispatched actions, state changes, and the order in which updates happened. I use it to debug unexpected state changes and replay actions when investigating a bug.

<a id="qa-06-046"></a>
### 6.46. What are the main features of Redux Form?

**Interview answer:** Redux Form is an older library that stores form state in Redux and supports field registration, validation, submission, and value formatting or normalization. This makes form values accessible through the global store, but can create unnecessary global updates. In new projects I usually keep form state local using React Hook Form or another suitable form solution.

<a id="qa-06-047"></a>
### 6.47. How do you avoid unnecessary re-renders with `useSelector`?

**Interview answer:** I make Redux `useSelector` select the smallest state value a component needs. Returning a new object from a selector on every store update can trigger extra renders, so I use memoized selectors with Reselect or `shallowEqual` where appropriate. I profile before adding memoization, because narrow primitive selectors are often enough.

<a id="qa-06-048"></a>
### 6.48. What are the main features of Reselect library?

**Interview answer:** Reselect creates memoized selectors that calculate derived data from store state. It avoids repeating the result calculation when relevant inputs have not changed, and selectors can be composed from other selectors. This helps keep Redux state minimal and can preserve result references to avoid unnecessary component updates.

<a id="qa-06-049"></a>
### 6.49. What are typical middleware choices for handling asynchronous calls in Redux?

**Interview answer:** Common Redux async middleware includes Redux Thunk and Redux Saga; older projects may also use Promise middleware. Thunk works well for straightforward async operations, while Saga can coordinate complex cancellation and event workflows. Redux Toolkit includes thunk support by default, and I often use RTK Query for server-data fetching and caching.

<a id="qa-06-050"></a>
### 6.50. What is an action in Redux?

**Interview answer:** *Actions* are plain JavaScript objects or payloads of information that send data from your application to your store. They are the only source of information for the store. Actions must have a type property that indicates the type of action being performed. For example, let's take an action which represents adding a new todo item.

<a id="qa-06-051"></a>
### 6.51. What is createAsyncThunk() and why is it used?

**Interview answer:** createAsyncThunk handles async operations (API requests) in Redux. It takes an action type string and an async payload creator function. It automatically dispatches three action types: actionName/pending (loading), actionName/fulfilled (success with data), actionName/rejected (error). Handle these in extraReducers with builder.addCase().

<a id="qa-06-052"></a>
### 6.52. What is Jotai and how does the atomic model work?

**Interview answer:** Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

<a id="qa-06-053"></a>
### 6.53. What is MobX?

**Interview answer:** MobX is a reactive state-management library that tracks observable values and automatically updates computations or observers that depend on them. It uses observables, computed values, and actions. In React, observer components update when tracked data changes. Its mutable-looking reactive model differs from Redux's explicit immutable update flow.

<a id="qa-06-054"></a>
### 6.54. What is Recoil/Jotai? What problem do atom-based libraries solve?

**Interview answer:** Atom-based state libraries such as Jotai model state as small independent pieces called atoms. Components subscribe to the atoms they actually use, so unrelated updates can avoid extra re-renders. This can be useful when a large shared state has many independently changing values. The API and maintenance trade-offs depend on the library.

<a id="qa-06-055"></a>
### 6.55. What is Redux Form?

**Interview answer:** Redux Form works with React and Redux to enable a form in React to use Redux to store all of its state. Redux Form can be used with raw HTML5 inputs, but it also works very well with common UI frameworks like Material UI, React Widgets and React Bootstrap.

<a id="qa-06-056"></a>
### 6.56. What is Redux Thunk vs Redux Saga?

**Interview answer:** Redux Thunk allows action creators to return functions that receive `dispatch` and `getState`, making straightforward async workflows easy to implement. Redux Saga uses generator functions and declarative effects to coordinate more complex tasks such as cancellation and races. I prefer Thunk or RTK Query for typical API use cases and Saga when orchestration warrants it.

<a id="qa-06-057"></a>
### 6.57. What is Redux Thunk?

**Interview answer:** Redux Thunk middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch()` and `getState()` as parameters.

<a id="qa-06-058"></a>
### 6.58. What is redux-saga?

**Interview answer:** `redux-saga` is a library that aims to make side effects (asynchronous things like data fetching and impure things like accessing the browser cache) in React/Redux applications easier and better. It is available in NPM.

<a id="qa-06-059"></a>
### 6.59. What is Redux?

**Interview answer:** Redux is a predictable global state-management library. Components dispatch actions, reducers calculate the updated state, and the store holds the app state. Today, I usually write Redux using Redux Toolkit to avoid repetitive boilerplate.

<a id="qa-06-060"></a>
### 6.60. What is the "single source of truth" principle in state management?

**Interview answer:** Single source of truth means each piece of state has one authoritative owner. Other components read it or derive values from it instead of maintaining independent copies that can become inconsistent. This does not mean every value must be global; local state, URL state, and server caches can each own the data appropriate to them.

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

**Interview answer:** In React Redux's `connect`, an optional `ownProps` argument exposes the props passed to the connected component. I can use it in `mapStateToProps` to select data by a prop such as `userId`, or in `mapDispatchToProps` to bind an action to that ID. Modern function components often achieve this with Hooks instead.

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

**Interview answer:** Reducers always return the accumulation of the state (based on all previous and current actions). Therefore, they act as a reducer of state. Each time a Redux reducer is called, the state and action are passed as parameters. This state is then reduced (or accumulated) based on the action, and then the updated state is returned. You could reduce a collection of actions and an initial state (of the store) on which to perform these actions to get the resulting final state.

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

**Interview answer:** Define a thunk using `createAsyncThunk`. Inside the payload creator, perform async work (for example, fetch). Dispatch the thunk from a component. The thunk dispatches the `pending` action immediately. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.

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

**Interview answer:** Functions defined on routes that fetch data before the component renders. The component receives data via `useLoaderData()`. Eliminates loading spinners inside components; data is ready before render.

<a id="qa-07-009"></a>
### 7.9. What are the `<Router>` components of React Router v6?

**Interview answer:** React Router v6 includes BrowserRouter for normal browser-history navigation, HashRouter for hash-based URLs, MemoryRouter for in-memory navigation such as tests, and StaticRouter for server rendering. The v6 data-router APIs also provide alternatives such as `createBrowserRouter` with `RouterProvider`.

<a id="qa-07-010"></a>
### 7.10. What is client-side routing? How does it differ from server routing?

**Interview answer:** Client-side routing updates which page component is displayed without requiring a full document reload for every route. React Router uses browser history and route matching for navigation. The server must still serve the app shell on direct visits to clean URLs, and route guards in the browser are not a substitute for backend authorization.

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

**Interview answer:** React Router v6 ranks candidate routes by specificity rather than simply choosing the first declaration. Static segments generally rank above dynamic parameters, which rank above splats. For example, `/users/new` is preferred over `/users/:id` for that exact URL. This makes route matching more predictable.

<a id="qa-07-013"></a>
### 7.13. What is the difference between `Router` and `Link` in React Router?

**Interview answer:** `Router` (for example, `BrowserRouter`): Provides the routing context and handles history management. It is the parent component that enables navigation and URL sync. `Link`: A component that renders an anchor (`<a>`) with the `to` prop. It allows navigation without a full page reload, using client‑side routing.

<a id="qa-07-014"></a>
### 7.14. How do you define nested routes (v6+)?

**Interview answer:** In React Router, I nest child routes inside a parent route and place `<Outlet />` in the parent's component to display the matched child. For example, a dashboard layout can render shared navigation while nested `/dashboard/reports` and `/dashboard/users` routes render inside the Outlet. That avoids duplicating layout code.

<a id="qa-07-015"></a>
### 7.15. How do you implement a layout route (shared header/sidebar across multiple pages)?

**Interview answer:** I define a parent layout route that renders the common header, sidebar, and an `<Outlet />`. The child routes appear in that Outlet while the shared layout remains mounted. This pattern is useful for dashboards with multiple pages because it centralizes navigation and avoids rebuilding the same layout in each page.

<a id="qa-07-016"></a>
### 7.16. How do you implement protected/private routes?

**Interview answer:** A protected route checks the user's authentication state and shows the page or navigates to login. In React Router I may wrap the route element or use a route loader to redirect before rendering. This protects the user experience, but the backend must independently validate the session and enforce authorization for every API request.

<a id="qa-07-017"></a>
### 7.17. What is the difference between BrowserRouter and HashRouter?

**Interview answer:** `BrowserRouter` uses the browser History API to provide clean URLs, but the server must return the application for client-side routes on refresh. `HashRouter` stores the route in the URL fragment, which is not sent to the server. I use BrowserRouter by default and consider HashRouter when hosting does not support route rewrites.

<a id="qa-07-018"></a>
### 7.18. How do you redirect after a successful form submission/mutation?

**Interview answer:** After a successful asynchronous submission, I can call `navigate('/success')` from a React Router event handler. In a data-router route action, I can return a `redirect()` response instead. I perform navigation only after success and keep the user on the form with meaningful error feedback if the request fails.

<a id="qa-07-019"></a>
### 7.19. How does client-side routing work?

**Interview answer:** A router library (React Router, TanStack Router) listens to the browser history API (`pushState`, `popstate`) and renders different components based on the current URL – without full page reloads.

<a id="qa-07-020"></a>
### 7.20. How is React different from Angular or Vue?

**Interview answer:** React is mainly a UI library that uses JSX and composition. Angular is a comprehensive framework with built-in routing, forms, and dependency injection. Vue provides a progressive framework with single-file components and its own reactive model. I compare their ecosystem, architecture, and team familiarity rather than treating one as universally better.

<a id="qa-07-021"></a>
### 7.21. What is the difference between `useNavigate` and `<Navigate>`?

**Interview answer:** `useNavigate()` gives me an imperative navigation function, useful after a successful submission or in an event handler. `<Navigate>` expresses navigation declaratively as part of the component output, such as rendering a redirect for an unauthenticated user. I choose the API that fits where the navigation decision is made.

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

**Interview answer:** Search parameters are values in a URL's query string, such as `?tab=settings&page=2`. React Router's `useSearchParams()` returns the current parameters and a setter that updates the URL. I use them for shareable filters, pagination, or tabs so users can bookmark the view and use browser navigation naturally.

<a id="qa-07-026"></a>
### 7.26. What are loaders and actions (v6.4+ data APIs)?

**Interview answer:** A React Router loader fetches data for a route before its UI is rendered, and the component reads the result with `useLoaderData`. An action handles a route mutation, often submitted through `<Form>`, and can return errors or redirect. These APIs belong to React Router's Data/Framework modes, not every Router setup.

<a id="qa-07-027"></a>
### 7.27. What is `<NavLink>`? How does it differ from `<Link>`?

**Interview answer:** `NavLink` is similar to React Router's `Link`, but it exposes whether the destination matches the current route, allowing active navigation styling and relevant accessibility attributes. I use it for menus and sidebars; a normal `Link` is sufficient for navigation that does not need an active state.

<a id="qa-07-028"></a>
### 7.28. What is the purpose of `push()` and `replace()` methods of `history`?

**Interview answer:** In older history-based routing APIs, `push()` adds a new entry to browser history, while `replace()` replaces the current entry. I use replace for redirects where users should not return to the previous page with Back, such as after login. In React Router v6, I use `navigate(path, { replace: true })` for the equivalent behavior.

<a id="qa-07-029"></a>
### 7.29. How do you programmatically navigate using React Router v4?

**Interview answer:** In React Router v4, programmatic navigation was usually done through the `history` object, such as `history.push("/profile")`. In React Router v6, I use the `useNavigate` Hook instead.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-07-030"></a>
### 7.30. How would you get query parameters in React Router v4?

**Interview answer:** In React Router v4, the query string is available in `location.search`, and I can parse it using `URLSearchParams` or a query-string library. In React Router v6, I typically use `useSearchParams` instead.

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

**Interview answer:** A function that generates a pre-configured, typed field component bound to a specific form library/schema (for example, `createFormField<FormValues>()`), reducing repetitive boilerplate across many similar fields while preserving type safety.

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

**Interview answer:** For a checkbox I control its `checked` property and update state from `event.target.checked`. For a select I control `value` and read `event.target.value`. I use `value` for text and select fields, but not for a checkbox's boolean state. That avoids common bugs caused by treating every input identically.

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

**Interview answer:** TanStack Query deduplicates simultaneous requests that share the same query key, so several mounted components can use one in-flight fetch. Each component subscribes to the cached result instead of starting a separate network request. That reduces duplicate traffic and keeps UI state consistent; I still design query keys to include all parameters affecting the result.

<a id="qa-09-002"></a>
### 9.2. How does the data-fetching process work with Suspense?

**Interview answer:** With Suspense, a component can pause rendering while a supported resource is not ready. React shows the nearest Suspense fallback until it can continue rendering. I generally use this with `React.lazy` or a framework or data library that supports Suspense.

<a id="qa-09-003"></a>
### 9.3. How do staleTime and gcTime affect TanStack Query caching?

**Interview answer:** In TanStack Query, `staleTime` controls how long fetched data is considered fresh. While fresh, it normally avoids automatic refetching on triggers such as mounting. `gcTime` controls how long an inactive query stays in memory before garbage collection. For example, I may use a longer `staleTime` for rarely changing country codes than for live notifications.

<a id="qa-09-004"></a>
### 9.4. How do SWR and TanStack Query compare for data fetching?

**Interview answer:** SWR and TanStack Query both help cache and revalidate server data in React. SWR emphasizes a lightweight fetching experience, while TanStack Query has broader built-in tools for mutations, pagination, invalidation, and complex cache policies. I choose according to the application’s requirements and existing stack rather than assuming one is universally better.

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

**Interview answer:** Parallel fetching means starting independent requests together instead of waiting for one to finish before starting the next. In a Server Component I can start multiple Promises, then await them with `Promise.all`. That reduces request waterfalls and often improves time to first content. Requests with real dependencies must still be sequential.

<a id="qa-09-009"></a>
### 9.9. What is parallel vs sequential data fetching?

**Interview answer:** Sequential fetching waits for one request before starting the next, which is necessary when the second request depends on the first result. Parallel fetching starts independent requests together and awaits them with `Promise.all()`. This can reduce total waiting time to approximately that of the slowest request, rather than the sum of all request times.

<a id="qa-09-010"></a>
### 9.10. What is prefetching in React Query? When would you use it?

**Interview answer:** `queryClient.prefetchQuery(...)` loads data into the cache before it's needed (for example, on hover over a link, or in a route loader), so the eventual component render finds data already cached.

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

**Interview answer:** Optimistic UI updates the screen before the server confirms a change, so an interaction feels immediate. For example, I may display a newly added comment while the request is pending. If it fails, I show an error and restore or reconcile the prior state. React 19 has `useOptimistic`, and TanStack Query offers mutation lifecycle callbacks.

<a id="qa-09-018"></a>
### 9.18. What is query invalidation? How do you trigger a refetch after a mutation?

**Interview answer:** Query invalidation tells TanStack Query that cached data may be outdated. After a successful mutation, I call something like `queryClient.invalidateQueries({ queryKey: ['todos'] })`. Matching active queries can refetch so the user sees updated server data. I choose a specific query key to avoid unnecessary refetching of unrelated data.

<a id="qa-09-019"></a>
### 9.19. How do you cancel a query automatically when its component unmounts?

**Interview answer:** React Query handles this internally by default for the underlying fetch (via `AbortSignal` passed to the query function) when a query becomes unused and its `gcTime` conditions are met or when manually cancelled via `queryClient.cancelQueries`.

<a id="qa-09-020"></a>
### 9.20. How does React prioritize work with its Scheduler?

**Interview answer:** React uses an internal Scheduler to control how updates are prioritized: Urgent tasks like clicks and inputs are processed immediately. Non-urgent tasks (like data fetching) can be delayed or paused. That improves responsiveness and allows for time slicing in Concurrent Mode.

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

**Interview answer:** Yes. `flushSync` from `react-dom` can force React to flush a state update to the DOM synchronously when an external API needs to see the updated DOM immediately. I use it sparingly because it can reduce performance. When the next state only depends on the previous value, I use a functional updater instead of forcing a synchronous commit.

<a id="qa-10-003"></a>
### 10.3. What are React 19 Actions?

**Interview answer:** React 19 Actions are functions that perform user-triggered work, often asynchronously, and integrate with pending, error, and optimistic UI state. React provides `useActionState`, `useOptimistic`, and React DOM's `useFormStatus` for common workflows. For example, a profile form can submit through an Action and display its pending or validation state.

<a id="qa-10-004"></a>
### 10.4. What are Server Actions (React 19 / Next.js)?

**Interview answer:** Functions marked `'use server'` that can be called directly from Client Components (for example, as a `<form action={fn}>`) without hand-writing an API route; React serializes arguments, executes on the server, and streams the result back — includes automatic CSRF protection and progressive enhancement (forms work without JS).

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

**Interview answer:** In React 16.9, JavaScript URLs generated security warnings. In modern React, these URLs are blocked or otherwise unsafe to rely on. I do not use `javascript:` links: I use buttons and proper event handlers, and validate untrusted URL values to prevent XSS.

<a id="qa-10-017"></a>
### 10.17. Is there a functional-component equivalent of error boundaries?

**Interview answer:** React still relies on error boundaries to catch rendering errors in descendant components. In ordinary React, a custom error boundary is built as a class component using `getDerivedStateFromError` and optionally `componentDidCatch`. In a function-component app, I can use a library such as `react-error-boundary` without writing my own boundary class.

<a id="qa-10-018"></a>
### 10.18. What is `startTransition`?

**Interview answer:** `startTransition` marks a state update as non-urgent. React can prioritize urgent interactions, such as typing, while it prepares the slower update. I use it when a heavy UI update should not block immediate feedback.

<a id="qa-10-019"></a>
### 10.19. How does React break rendering into work units and schedule them?

**Interview answer:** React breaks rendering into units of work (small tasks). These units are scheduled based on priority using the React Scheduler. If time runs out (for example, user starts typing), React can pause and yield control back to the browser.

<a id="qa-10-020"></a>
### 10.20. Are custom DOM attributes supported in React v16?

**Interview answer:** Yes. React 16 introduced broader support for passing custom DOM attributes through to the browser. Modern React still supports custom attributes, subject to naming and value rules and exceptions for unsafe event-like attributes. I normally use `data-*` for application-specific DOM metadata.

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

**Interview answer:** Streaming SSR lets the server send the page shell before all slower content is ready. React can use `Suspense` boundaries to send placeholder HTML first, then stream completed sections when their data or components are available. That improves perceived loading for complex pages, but it still needs appropriate hydration for interactive client components.

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

**Interview answer:** Hydration is the process where React attaches event listeners and reconciles the server‑rendered HTML with the client‑side virtual DOM. It allows interactive components to “take over” the static markup. Hydration mismatches occur when the HTML generated on the server differs from the initial render on the client (for example, due to different data, random values, or browser‑only APIs).

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

**Interview answer:** Static and dynamic rendering are framework-specific Next.js concepts. A route that can be pre-rendered and cached may serve a static result, while a route using request-specific data can require dynamic rendering. The exact caching defaults have changed across Next.js releases, so I inspect the version and explicitly configure freshness or revalidation for each data source.

<a id="qa-11-020"></a>
### 11.20. What is the Next.js App Router, and how does it differ from the Page Router?

**Interview answer:** File-system routing via `app/` (vs. `pages/`); components are Server Components by default (vs. all Client Components); native nested layouts (`layout.js`) and built-in `loading.js`/`error.js` for Suspense/error boundaries per route; native async data fetching with `fetch`; native Server Actions support.

<a id="qa-11-021"></a>
### 11.21. What is the security consideration around React Server Components and passing data from server to client?

**Interview answer:** Data passed as props from a Server Component into a Client Component is serialized and does ship to the browser; sensitive fields fetched server-side must be explicitly excluded from what's passed down, not just "kept on the server" by assumption.

<a id="qa-11-022"></a>
### 11.22. When to use client and server components?

**Interview answer:** I use Server Components for server-side data access and UI that does not require browser state or event handlers. I use Client Components when interactivity, Hooks such as `useState` or `useEffect`, or browser APIs are needed. In a framework such as Next.js, I keep client boundaries small to reduce shipped JavaScript and avoid exposing server-only data.

<a id="qa-11-023"></a>
### 11.23. How are React Server Components different from Client Components?

**Interview answer:** Server Components run on the server and can access server resources without sending their component code to the browser. Client Components can use client-side interactivity, state and event handlers. They work together in frameworks that support the architecture.

<a id="qa-11-024"></a>
### 11.24. What is the difference between `next/link` prefetching and a manual `router.prefetch()` call?

**Interview answer:** `<Link>` automatically prefetches linked pages' code/data when they enter the viewport (in production). `router.prefetch()` lets you trigger the same prefetching imperatively (for example, on hover or a predicted next action) outside of a visible `<Link>`.

<a id="qa-11-025"></a>
### 11.25. How do you prevent waterfall requests in a component tree?

**Interview answer:** I prevent request waterfalls by starting independent data requests in parallel rather than waiting for one to finish before launching the next. On the server, I can start Promises together and then `await Promise.all(...)`. In client applications, route loaders or `useQueries` can help. Sequential fetching is still necessary when one request depends on another's result.

<a id="qa-11-026"></a>
### 11.26. Is it possible to use async/await in plain React?

**Interview answer:** Yes. Async/await is a JavaScript feature and can be used in React event handlers, data-fetching functions, and async functions called from Effects. The Effect callback itself should not be async because it must return cleanup or nothing. Ordinary Client Components should render synchronously; supported Server Components can be async.

<a id="qa-11-027"></a>
### 11.27. What are Next.js `loading.js` and `error.js`?

**Interview answer:** `loading.js`: automatically wraps the page in Suspense – shown while the page is loading. `error.js`: an error boundary for the route – shown when the page throws. They are React components with special Next.js behavior.

<a id="qa-11-028"></a>
### 11.28. What are React Server Components (RSC)?

**Interview answer:** Components that run only on the server. They can directly access databases, file systems, and APIs. Their code never ships to the client. They cannot use hooks or browser APIs. They interleave with Client Components.

<a id="qa-11-029"></a>
### 11.29. What is `getStaticPaths` (Pages Router)? When is it needed?

**Interview answer:** In the Next.js Pages Router, `getStaticPaths` specifies which dynamic route parameters should be generated at build time. It works with `getStaticProps` and defines fallback behavior for paths that were not pre-rendered. In the App Router, the equivalent build-time parameter-generation API is `generateStaticParams`.

<a id="qa-11-030"></a>
### 11.30. What is ISR (Incremental Static Regeneration)?

**Interview answer:** ISR stands for Incremental Static Regeneration. In Next.js, it lets a page remain statically generated while its content is refreshed after a configured revalidation period. I use it for pages that should be fast but do not require completely live data.

<a id="qa-11-031"></a>
### 11.31. What is NextJS and major features of it?

**Interview answer:** Next.js is a React framework that provides routing, server rendering, static generation, data fetching support, and build optimization. I use it when a project needs features beyond client-side React, such as SEO-friendly pages or server-side functionality.

<a id="qa-11-032"></a>
### 11.32. What is selective hydration? Why does it matter?

**Interview answer:** Selective hydration allows React to prioritize hydration of parts of a server-rendered page instead of waiting for the entire page to become interactive. Suspense boundaries help React coordinate this work as code and HTML arrive. It improves responsiveness, particularly when a user interacts with a section that needs to hydrate.

<a id="qa-11-033"></a>
### 11.33. What is SSG (Static Site Generation)?

**Interview answer:** Static Site Generation creates a page's HTML at build time rather than generating it for each request. This makes it suitable for content such as documentation, marketing pages, or blogs that can be served from a CDN. Next.js supports static generation through APIs such as `getStaticProps` in the Pages Router and static rendering in the App Router.

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

**Interview answer:** I would normally choose an SSR-capable React framework such as Next.js. The server fetches the required data, renders HTML, and sends it to the browser, where React hydrates the interactive components. A custom server can use React DOM's server APIs, including streaming. I address cache safety, server/client consistency, and hydration cost rather than assuming SSR automatically makes every page faster.

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

**Interview answer:** I report the error and its component stack from a class error boundary's `componentDidCatch(error, info)` to a monitoring service such as Sentry. I include useful context such as the route and release version without exposing sensitive user data. The boundary renders fallback UI, while monitoring helps developers investigate the failure.

<a id="qa-12-004"></a>
### 12.4. How do you reset an Error Boundary after the user retries (e.g., clicking "Try again")?

**Interview answer:** To retry after an error boundary catches a failure, I clear its error state and render the child again. Changing its key forces a fresh mount, or a library such as `react-error-boundary` can provide `resetErrorBoundary` and `onReset`. I also reset or retry the operation that caused the error so the same failure does not immediately recur.

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

**Interview answer:** A recoverable error (for example, a failed API request) can show an inline retry UI while the rest of the app keeps working. An unrecoverable error (for example, corrupted app state) may require a full Error Boundary fallback or forced reload, since continuing to render could produce further incorrect behavior.

<a id="qa-12-010"></a>
### 12.10. Why can't a single top-level Error Boundary be a complete error-handling strategy?

**Interview answer:** One crash anywhere takes down the entire app's UI behind a single fallback; nesting boundaries around independent sections (widgets, routes) isolates failures so one broken part doesn't block the rest.

<a id="qa-12-011"></a>
### 12.11. Can you describe about componentDidCatch lifecycle method signature?

**Interview answer:** `componentDidCatch(error, info)` is a class lifecycle method used by error boundaries. `error` is the thrown error, while `info.componentStack` helps locate the component tree where it happened. I use it for logging and recovery UI.

<a id="qa-12-012"></a>
### 12.12. What is global error monitoring in React apps?

**Interview answer:** I combine error boundaries with application-wide monitoring. Boundaries report descendant render errors through `componentDidCatch`, and global error and unhandled-rejection listeners can capture failures outside rendering. I include relevant diagnostic context, avoid logging secrets, and configure alerting so production issues can be investigated efficiently.

<a id="qa-12-013"></a>
### 12.13. What is the purpose of getDerivedStateFromError?

**Interview answer:** `static getDerivedStateFromError(error)` runs when a descendant throws during rendering and returns a state update, often to show fallback UI. I can pair it with `componentDidCatch` for logging.

<a id="qa-12-014"></a>
### 12.14. What is the proper placement for error boundaries?

**Interview answer:** I place error boundaries at meaningful UI boundaries, such as application routes or independently recoverable widgets. A top-level boundary protects the overall application, while more granular boundaries prevent a failure in one section from hiding unrelated content. I also provide useful fallback UI, logging, and a retry mechanism where appropriate.

<a id="qa-12-015"></a>
### 12.15. What is the behavior of an uncaught error with no error boundary present (React 16+)?

**Interview answer:** The entire component tree unmounts — React's philosophy is that leaving corrupted UI on screen (for example, a payments app showing a wrong amount) is worse than showing nothing. Always wrap critical sections in boundaries to avoid full-app blank-outs.

*Version note: this question involves legacy or version-dependent behavior; use the modern approach described in the answer.*

<a id="qa-12-016"></a>
### 12.16. How are error boundaries handled in React v15?

**Interview answer:** React 15 had an experimental `unstable_handleError` API. React 16 introduced the modern error-boundary model, and later class APIs include `getDerivedStateFromError` for fallback state and `componentDidCatch` for logging. These boundaries handle descendant rendering errors on the client, not ordinary server-rendering exceptions. I use the modern APIs in maintained applications.

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

**Interview answer:** I can implement a higher-order component by wrapping a render-prop component and passing the data it supplies into the wrapped component. For example, a `withMouse(Component)` wrapper could render `<Mouse render={position => <Component {...props} position={position} />} />`. This adapts the same reusable behavior to an HOC interface.

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

**Interview answer:** I document reusable components using a tool such as Storybook. I include their props, supported variants, common interaction states, accessibility requirements, and examples. I also explain any important constraints, such as controlled versus uncontrolled behavior, so other developers can integrate the component without reading its implementation.

<a id="qa-13-011"></a>
### 13.11. How do you create a generic, reusable component?

**Interview answer:** A generic reusable component accepts different data types while preserving type safety. For example, a `List<T>` component can take an array of `T` items plus a `renderItem(item: T)` function. The caller decides how a row appears, and TypeScript checks that the renderer receives the right item type.

<a id="qa-13-012"></a>
### 13.12. What is the purpose of forward ref in HOCs?

**Interview answer:** A ref passed to an HOC does not automatically reach the wrapped component in older React versions. Forwarding the ref explicitly lets the parent access the intended DOM node or imperative handle. I use `forwardRef` for older React versions or accept and pass the ref prop in React 19, while keeping the exposed API intentional.

<a id="qa-13-013"></a>
### 13.13. What are HOC factory implementations?

**Interview answer:** There are two main ways of implementing HOCs in React. Props Proxy (PP) and Inheritance Inversion (II). But they follow different approaches for manipulating the WrappedComponent. Props Proxy In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name Props Proxy.

<a id="qa-13-014"></a>
### 13.14. Can you explain higher-Order Component (HOC) that logs props on every render?

**Interview answer:** Every time `LoggedButton` renders, logs `Button rendered with: { label: 'Submit', onClick: [Function] }`. HOC concern: If `App` re-renders, `withLogger(Button)` is a new component type per render if defined inside — always define HOCs outside components.

<a id="qa-13-015"></a>
### 13.15. What is render hijacking in React?

**Interview answer:** Render hijacking is a historical term for a wrapper influencing a component's rendered output. For example, an HOC may inject props, choose a fallback, or conditionally render the wrapped component. I prefer explicit composition and avoid overriding a component's internal render behavior because that creates tight coupling.

<a id="qa-13-016"></a>
### 13.16. How do you pass a component as a prop (not just data)?

**Interview answer:** I can pass an already-created React element, such as `icon={<HomeIcon />}`, when the parent defines the content. Alternatively, I pass a component reference such as `Icon={HomeIcon}` when the receiving component needs to instantiate it with its own props. This is a useful composition pattern for customizable layouts.

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

**Interview answer:** HOCs can add extra wrapper layers, make debugging and prop names harder to follow, and cause prop collisions. In modern React, I generally prefer Hooks for sharing stateful logic and composition for UI reuse.

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

**Interview answer:** A single repository containing multiple packages/apps (for example, a shared UI library plus several apps consuming it). Tools like Turborepo, Nx, or Yarn/pnpm workspaces manage shared dependencies, incremental builds, and task caching across the packages.

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

**Interview answer:** Visual regression testing catches unintended UI changes by comparing screenshots of components or pages against approved baselines. Implementation: Tools: Percy (integrated with Storybook), Chromatic, or open‑source tools like Playwright with screenshot comparison. Workflow: Capture screenshots of each component/page in a controlled environment (for example, Storybook).

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

**Interview answer:** To test a Context consumer, I render it inside a test Provider that supplies a known value. React Testing Library's `wrapper` option lets me reuse a set of providers across tests. After that, I assert on what the component displays or does, rather than inspecting the internal implementation of `useContext`.

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

**Interview answer:** For custom Hooks, I use React Testing Library's `renderHook` to run the Hook in a test component. I wrap manual updates in `act` when necessary and assert on the exposed values. If the Hook reads Context, I provide a wrapper with the required provider. I test behavior, cleanup, and error handling instead of private implementation details.

<a id="qa-14-017"></a>
### 14.17. What is `act()`? Why does RTL warn about updates outside it?

**Interview answer:** React's `act()` helps tests flush updates and Effects before asserting on rendered UI. React Testing Library already wraps many common interactions, so I rarely call `act` directly. A warning usually means asynchronous updates are still pending or a timer or Promise was not awaited. I fix the test to wait for observable behavior instead of suppressing the warning.

<a id="qa-14-018"></a>
### 14.18. What is Mock Service Worker (MSW)?

**Interview answer:** Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly.

<a id="qa-14-019"></a>
### 14.19. How do you test a component using fake timers (e.g., a debounce or a countdown)?

**Interview answer:** I use fake timers to test time-dependent behavior without waiting in real time. For example, I enable Jest fake timers, trigger the debounced input, advance time using `jest.advanceTimersByTime()`, and assert the expected result. I coordinate timer advancement with React's `act` when needed and restore real timers after the test to avoid leaking state.

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

**Interview answer:** Snapshot testing serializes output and compares it against a previously stored snapshot. It can catch unexpected changes in stable UI or data structures. However, large snapshots are easy to update blindly and may not verify actual user behavior. I use small, meaningful snapshots alongside behavioral tests rather than as the primary testing strategy.

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

**Interview answer:** Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type` props. Use TypeScript to type them. Forward refs for DOM access. Avoid hardcoding styles; use class variants or a styling system. Compose with an icon slot.

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

**Interview answer:** In a legacy Create React App setup, I can create a TypeScript project using `npx create-react-app my-app --template typescript`. It configures TypeScript and `.tsx` files. For a new application, I would normally use a maintained Vite React TypeScript template or framework instead of CRA.

<a id="qa-15-006"></a>
### 15.6. What is `PropTypes`? How does it differ from TypeScript?

**Interview answer:** PropTypes checks the types of props at runtime in development and reports warnings; it is a separate library. TypeScript checks types during compilation, so it catches many mistakes earlier but its types disappear at runtime. For modern TypeScript React apps, I generally use TypeScript and validate external data separately.

<a id="qa-15-007"></a>
### 15.7. Can you explain `React.FC` vs explicit return type – which is better?

**Interview answer:** `React.FC<Props>` and a normal function with typed props both provide type checking. I generally prefer `function Button({label}: ButtonProps) { ... }` because the props and return type are straightforward, and I can type `children` explicitly when necessary. `React.FC` is still valid; it is mainly a team style choice rather than a performance difference.

<a id="qa-15-008"></a>
### 15.8. What is a discriminated union and when is it useful in React?

**Interview answer:** A union type sharing a common literal field (for example, `type Action = {type:'increment'} | {type:'setValue', payload:number}`) — lets TypeScript narrow the exact shape inside a `switch`/`if` on that field, ideal for typing reducer actions.

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

**Interview answer:** For a DOM input, I use `const inputRef = useRef<HTMLInputElement>(null)`, because the element is not mounted at first and `current` may be null. For a mutable numeric value, I use `useRef<number>(0)`. Both persist across renders, but updating the ref does not schedule a re-render.

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

**Interview answer:** PropTypes supports several possible types for one prop through `PropTypes.oneOfType`. For example, `PropTypes.oneOfType([PropTypes.string, PropTypes.number])` allows either a string or a number. In TypeScript code, I typically use a union type instead.

<a id="qa-15-020"></a>
### 15.20. What is `satisfies` and how is it useful for typing component configuration objects?

**Interview answer:** `satisfies` checks a value against a type without widening/changing the value's inferred type, useful for config objects (for example, a theme or route map) where you want both validation against a shape and precise literal-type inference preserved for later use.

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

**Interview answer:** The `style` attribute accepts a JavaScript object with camelCased properties rather than a CSS string. This is consistent with the DOM style JavaScript property, is more efficient, and prevents XSS security holes. Style keys are camelCased to be consistent with accessing the properties on DOM nodes in JavaScript (for example, `node.style.backgroundImage`).

<a id="qa-16-008"></a>
### 16.8. How do you keep component styling encapsulated and themeable?

**Interview answer:** I scope styles with CSS Modules, utility CSS, or a well-structured component library so one component's styles do not accidentally affect others. For theme support I prefer shared design tokens and CSS variables, such as `--surface-color`, rather than hardcoding colors in every component. This makes dark mode and design updates easier.

<a id="qa-16-009"></a>
### 16.9. What are CSS Modules? How do they prevent collisions?

**Interview answer:** CSS Modules give classes local scope by generating unique names during the build. I import a stylesheet as an object, such as `import styles from './Card.module.css'`, and write `className={styles.card}`. That avoids accidental style collisions between components without requiring a runtime styling library.

<a id="qa-16-010"></a>
### 16.10. How would you add Bootstrap to a React application?

**Interview answer:** I can install Bootstrap as a dependency and import its CSS, include its CSS through a CDN, or use React Bootstrap for React-friendly components. I generally prefer a package-managed setup because versions are controlled by the project. If using interactive Bootstrap behavior, I avoid conflicting DOM manipulation and choose the appropriate integration.

<a id="qa-16-011"></a>
### 16.11. Give an example of Styled Components?

**Interview answer:** Lets create `<Title>` and `<Wrapper>` components with specific styles for each. These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

<a id="qa-16-012"></a>
### 16.12. What are the different ways to style a React component?

**Interview answer:** I can style React with plain CSS, CSS Modules, utility classes such as Tailwind, inline styles, or CSS-in-JS. I choose based on the team’s design system, maintainability, and runtime needs.

<a id="qa-16-013"></a>
### 16.13. What is the benefit of styles modules?

**Interview answer:** CSS Modules scope class names locally to a component, which reduces naming collisions and unintended global styling. I can import `styles` from a `.module.css` file and use `className={styles.card}`. For shared colors and spacing, I separately use design tokens or CSS variables to keep the visual system consistent.

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

**Interview answer:** I reduce supply-chain risk by using a committed lockfile and reproducible installs, reviewing new dependencies and their maintainers, and scanning packages for known vulnerabilities in CI. I also limit unnecessary dependencies and review updates before deployment. Automated audits help, but they do not guarantee protection against malicious packages or newly discovered vulnerabilities.

<a id="qa-17-013"></a>
### 17.13. How do you prevent clickjacking in a React app?

**Interview answer:** For Web Components with imperative methods, I attach a React ref to their DOM node and call the method through `ref.current` after mount. A small wrapper component helps keep that integration reusable.

<a id="qa-17-014"></a>
### 17.14. How would you implement role-based access control (RBAC) in React?

**Interview answer:** Store roles in an auth Context; a `usePermissions`/`useCan` hook checks role against required permissions; wrap protected UI or routes with conditional rendering/loader-level redirects — but always enforce authorization server-side too, since client checks are only a UX convenience.

<a id="qa-17-015"></a>
### 17.15. What is a Subresource Integrity (SRI) hash, and when would a React app use one?

**Interview answer:** A hash attribute on a `<script>`/`<link>` tag verifying a CDN-loaded file hasn't been tampered with; relevant when loading a library (for example, via a CDN `<script>` tag in an HTML template) from a third-party host outside your build pipeline.

<a id="qa-17-016"></a>
### 17.16. What is the risk of exposing API keys/secrets in a client-side React bundle?

**Interview answer:** Anything bundled for the browser (including `NEXT_PUBLIC_`-prefixed or hardcoded values) is visible to anyone inspecting the JS; secrets must stay server-side, with the client calling a backend proxy instead.

<a id="qa-17-017"></a>
### 17.17. What is a focus trap?

**Interview answer:** A focus trap keeps keyboard focus inside an active modal dialog so pressing Tab or Shift+Tab cannot move focus to background controls. I use an accessible dialog implementation that also handles initial focus, Escape, and restoring focus to the trigger when the modal closes. This is important for keyboard and assistive-technology users.

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

**Interview answer:** `FormattedMessage` renders React content rather than necessarily returning a plain string, so I use React Intl's `formatMessage()` for string-valued attributes such as placeholders and alt text. In a function component, I can call `useIntl()` and then `intl.formatMessage({ id: 'search.placeholder' })`.

<a id="qa-18-004"></a>
### 18.4. How can Polymer web components be used in a React app?

**Interview answer:** Polymer components are Web Components, so I first load or register the custom element and then render its tag in JSX. Depending on the component and React version, I may use refs to set properties or attach custom event listeners. For new integrations, I evaluate standard custom elements rather than assuming Polymer is required.

<a id="qa-18-005"></a>
### 18.5. How would you implement internationalization (i18n) in React?

**Interview answer:** `react-intl` or `react-i18next`. Extract all strings to message catalogs. `useIntl()` hook for formatting. Support RTL layouts (`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies via Intl API. Lazy load language bundles.

<a id="qa-18-006"></a>
### 18.6. Can you explain a/B Testing: How to implement A/B testing without affecting current users?

**Interview answer:** I use a feature flag or experimentation service to assign eligible users consistently to control and treatment variants. I load the assignment early, render the appropriate version, and collect relevant metrics. I avoid exposing incomplete variants to other users, monitor errors and layout shifts, and maintain a kill switch to disable the experiment if necessary.

<a id="qa-18-007"></a>
### 18.7. How does tree shaking work in modern bundlers?

**Interview answer:** Tree shaking is a dead‑code elimination technique that removes unused exports from the final bundle. Bundlers like Webpack and Rollup analyze the import/export graph and only include code that is actually used. This relies on ES modules being statically analyzable.

<a id="qa-18-008"></a>
### 18.8. How would you avoid using relative path imports in create-React-app?

**Interview answer:** Create a file called `.env` in the project root and write the import path: After that restart the development server. Now we should be able to import anything inside `src/app` without relative paths.

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

**Interview answer:** `registerServiceWorker` was a helper used by older Create React App templates to register a browser service worker. Service workers can cache resources and support offline behavior or background capabilities. React itself does not automatically create or register one. In a modern app, I configure service-worker registration and cache invalidation explicitly if needed.

<a id="qa-18-015"></a>
### 18.15. How would you debug your React Native?

**Interview answer:** For React Native debugging, I use the development menu, React Native DevTools where supported, logs, and native platform tools when investigating Android or iOS issues. Older versions used Chrome remote debugging, but the tooling is version-dependent. I reproduce the issue on the target device and inspect both JavaScript and native behavior as appropriate.

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

**Interview answer:** Code splitting breaks a large JavaScript bundle into smaller pieces that load when necessary. In React, I can use `React.lazy` with a dynamic `import()` and wrap the component in `Suspense` to show a fallback while its code loads.

<a id="qa-18-024"></a>
### 18.24. What is the purpose of ESLint and Prettier in a React project?

**Interview answer:** ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other; ESLint for rules, Prettier for style.

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

**Interview answer:** I review the release notes and breaking changes, upgrade the dependency in a separate branch, and run automated tests and targeted manual checks. I identify affected APIs and migrate them incrementally where possible. I commit the updated lockfile, validate in staging, and deploy gradually with a rollback plan. Security updates may require a faster but still controlled process.

<a id="qa-18-029"></a>
### 18.29. How do you handle localization and internationalization in React?

**Interview answer:** Internationalization makes an app work across languages and regions; localization supplies translations and local formats. In React, I use translation resources and locale-aware formatting for dates, numbers, and currency.

<a id="qa-18-030"></a>
### 18.30. What should you expect in a React machine-coding interview round?

**Interview answer:** In a machine-coding round, I may be asked to build a small feature such as a todo app, searchable table, or modal within a limited time. I explain my component structure, manage state clearly, handle edge cases, and keep the code testable.

<a id="qa-18-031"></a>
### 18.31. How would you roll back a faulty frontend release?

**Interview answer:** I would switch traffic back to the last stable build or redeploy the previous version. Then I would verify monitoring and logs, identify the root cause, and prepare a tested fix.

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

**Interview answer:** React DOM pooled SyntheticEvent objects in React 16 and earlier, so event properties could become null after the handler returned unless the event was persisted. React 17 removed event pooling on the web, so `event.persist()` is no longer necessary there. I still distinguish browser events from version-dependent React Native behavior.

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
