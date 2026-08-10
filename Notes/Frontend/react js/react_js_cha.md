# React.js — Complete Union of React JS Interview Questions & Answers

> **Scope:** Union of the supplied documents, limited to **React.js and its React web ecosystem**. **React Native is excluded.** Duplicate/near-duplicate questions are consolidated into one entry.

## Table of Contents

### React Architecture, LLD & Scenarios

- [Design a Carousel that can handle 1000+ images efficiently.](#design-a-carousel-that-can-handle-1000-images-efficiently)
- [Design a Config-Driven Form Renderer using a JSON schema.](#design-a-config-driven-form-renderer-using-a-json-schema)
- [Design a Data Table with sorting, filtering, pagination, and performance trade-offs.](#design-a-data-table-with-sorting-filtering-pagination-and-performance-trade-offs)
- [Design a Dropdown / Select component with keyboard navigation and accessibility.](#design-a-dropdown--select-component-with-keyboard-navigation-and-accessibility)
- [Design a file upload component with progress tracking and chunked uploads.](#design-a-file-upload-component-with-progress-tracking-and-chunked-uploads)
- [Design a Modal/Dialog component -- focus trapping, accessibility, backdrop behavior.](#design-a-modaldialog-component----focus-trapping-accessibility-backdrop-behavior)
- [Design a Modal/Dialog component with focus trapping and accessibility.](#design-a-modaldialog-component-with-focus-trapping-and-accessibility)
- [Design a Notification / Toast system with queueing, auto-dismiss, and priority.](#design-a-notification--toast-system-with-queueing-auto-dismiss-and-priority)
- [Design a Posts with Comments system – how do you manage deeply nested data?](#design-a-posts-with-comments-system--how-do-you-manage-deeply-nested-data)
- [Design a Progress Bar / Stepper with configurable steps and validation logic.](#design-a-progress-bar--stepper-with-configurable-steps-and-validation-logic)
- [Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.](#design-a-search-with-autocomplete--typeahead--debouncing-caching-race-conditions)
- [Design a Star Rating component – how would you support half or partial ratings?](#design-a-star-rating-component--how-would-you-support-half-or-partial-ratings)
- [Design a state management solution for a complex analytics/dashboard app.](#design-a-state-management-solution-for-a-complex-analyticsdashboard-app)
- [Design a state management solution for a complex app.](#design-a-state-management-solution-for-a-complex-app)
- [Design a Tabs component that supports dynamic content loading and async data.](#design-a-tabs-component-that-supports-dynamic-content-loading-and-async-data)
- [Design a theme-able, extensible component library.](#design-a-theme-able-extensible-component-library)
- [Design a Todo List application with add, edit, delete, and mark‑as‑complete.](#design-a-todo-list-application-with-add-edit-delete-and-markascomplete)
- [Design a Toggle / Switch component -- controlled vs uncontrolled patterns.](#design-a-toggle--switch-component----controlled-vs-uncontrolled-patterns)
- [Design an Accordion component -- should it allow single or multiple panels open? Why?](#design-an-accordion-component----should-it-allow-single-or-multiple-panels-open-why)
- [Design an E-commerce Filter system (price, category, rating) with scalable state.](#design-an-e-commerce-filter-system-price-category-rating-with-scalable-state)
- [Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.](#design-an-e-commerce-frontend-with-filters-price-category-rating-and-scalable-state-updates)
- [How do you design a reusable button component?](#how-do-you-design-a-reusable-button-component)
- [How do you handle real-time updates efficiently in React?](#how-do-you-handle-real-time-updates-efficiently-in-react)
- [How do you integrate feature flags (LaunchDarkly, etc.) in React ecosystems?](#how-do-you-integrate-feature-flags-launchdarkly-etc-in-react-ecosystems)
- [How do you structure a large-scale React application across multiple teams?](#how-do-you-structure-a-large-scale-react-application-across-multiple-teams)
- [How does React Fiber architecture change rendering?](#how-does-react-fiber-architecture-change-rendering)
- [How would you architect a React app for a team of 20 developers?](#how-would-you-architect-a-react-app-for-a-team-of-20-developers)
- [How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue‑green deployments?](#how-would-you-design-a-cicd-pipeline-for-frontend-apps-with-staging-canary-and-bluegreen-deployments)
- [How would you design a design system in React?](#how-would-you-design-a-design-system-in-react)
- [How would you design a reusable component library for a large team?](#how-would-you-design-a-reusable-component-library-for-a-large-team)
- [How would you design a state management solution for a complex analytics/dashboard app?](#how-would-you-design-a-state-management-solution-for-a-complex-analyticsdashboard-app)
- [How would you design a theme-able, extensible component library?](#how-would-you-design-a-theme-able-extensible-component-library)
- [How would you design component structure for scalability in a production-level app?](#how-would-you-design-component-structure-for-scalability-in-a-production-level-app)
- [How would you design SSR/SSG/hydration strategy for a React app?](#how-would-you-design-ssrssghydration-strategy-for-a-react-app)
- [How would you handle real-time updates in a React application efficiently?](#how-would-you-handle-real-time-updates-in-a-react-application-efficiently)
- [How would you structure a large-scale React application?](#how-would-you-structure-a-large-scale-react-application)
- [In a large-scale application, components are re-rendering unnecessarily — how would you identify and fix performance issues?](#in-a-large-scale-application-components-are-re-rendering-unnecessarily--how-would-you-identify-and-fix-performance-issues)
- [Real-time Updates: How to handle real-time updates efficiently in React?](#real-time-updates-how-to-handle-real-time-updates-efficiently-in-react)
- [Redux vs Context API vs Zustand – how do you decide in a large-scale application?](#redux-vs-context-api-vs-zustand--how-do-you-decide-in-a-large-scale-application)
- [Scenario: Context API causes frequent re‑renders – why and how to fix?](#scenario-context-api-causes-frequent-rerenders--why-and-how-to-fix)
- [What is Fiber architecture in React?](#what-is-fiber-architecture-in-react)
- [What is the flux architecture pattern?](#what-is-the-flux-architecture-pattern)
- [You are building a real-time dashboard --- how would you manage frequent state updates without affecting performance?](#you-are-building-a-real-time-dashboard-----how-would-you-manage-frequent-state-updates-without-affecting-performance)
- [❓ What is the difference between Redux, Context, and Zustand for large-scale apps?](#-what-is-the-difference-between-redux-context-and-zustand-for-large-scale-apps)

### React Routing, Forms & Data Fetching

- [Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.](#explain-techniques-for-dynamic-code-splitting-and-lazy-loading-in-multi-route-spas)
- [How do you do form validation in React without a library?](#how-do-you-do-form-validation-in-react-without-a-library)
- [How do you programmatically navigate using React Router v4?](#how-do-you-programmatically-navigate-using-react-router-v4)
- [How does new JSX transform different from old transform?](#how-does-new-jsx-transform-different-from-old-transform)
- [How is the new JSX transform different from old transform??](#how-is-the-new-jsx-transform-different-from-old-transform)
- [How React Router is different from history library?](#how-react-router-is-different-from-history-library)
- [How to add Google Analytics for React Router?](#how-to-add-google-analytics-for-react-router)
- [How to fetch data with React Hooks?](#how-to-fetch-data-with-react-hooks)
- [How to get history on React Router v4?](#how-to-get-history-on-react-router-v4)
- [How to get query parameters in React Router v4?](#how-to-get-query-parameters-in-react-router-v4)
- [How to pass data between sibling components using React router?](#how-to-pass-data-between-sibling-components-using-react-router)
- [How to pass params to `history.push` method in React Router v4?](#how-to-pass-params-to-historypush-method-in-react-router-v4)
- [How to perform automatic redirect after login?](#how-to-perform-automatic-redirect-after-login)
- [What are route actions in React Router?](#what-are-route-actions-in-react-router)
- [What are route loaders in React Router v6.4+?](#what-are-route-loaders-in-react-router-v64)
- [What are the advantages of formik over redux form library?](#what-are-the-advantages-of-formik-over-redux-form-library)
- [What are the benefits of React Router V4?](#what-are-the-benefits-of-react-router-v4)
- [What are the patterns for data fetching in React?](#what-are-the-patterns-for-data-fetching-in-react)
- [What are the `<Router>` components of React Router v6?](#what-are-the-router-components-of-react-router-v6)
- [What is Formik?](#what-is-formik)
- [What is optimistic mutation in React Query?](#what-is-optimistic-mutation-in-react-query)
- [What is React Hook Form and why is it popular?](#what-is-react-hook-form-and-why-is-it-popular)
- [What is React Query (TanStack Query)?](#what-is-react-query-tanstack-query)
- [What is React Router?](#what-is-react-router)
- [What is React Router and what are its main components?](#what-is-react-router-and-what-are-its-main-components)
- [What is route based code splitting?](#what-is-route-based-code-splitting)
- [What is routing in React? How does it work?](#what-is-routing-in-react-how-does-it-work)
- [What is the difference between `Router` and `Link` in React Router?](#what-is-the-difference-between-router-and-link-in-react-router)
- [What is the popular choice for form handling?](#what-is-the-popular-choice-for-form-handling)
- [What is useEffect hook? How to fetch data with React Hooks?](#what-is-useeffect-hook-how-to-fetch-data-with-react-hooks)

### Context & State Management

- [Can I dispatch an action in reducer?](#can-i-dispatch-an-action-in-reducer)
- [Can React Hook replaces Redux?](#can-react-hook-replaces-redux)
- [Can Redux only be used with React?](#can-redux-only-be-used-with-react)
- [Can useRef be used to store previous values?](#can-useref-be-used-to-store-previous-values)
- [Can You Use Multiple Contexts in One Component?](#can-you-use-multiple-contexts-in-one-component)
- [Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).](#compare-redux-mobx-and-recoil-for-enterprise-scale-state-management-pros-and-cons)
- [Context re-render behavior – what should you know?](#context-re-render-behavior--what-should-you-know)
- [Context Re-renders: Context API causes frequent re-renders – why and how to fix?](#context-re-renders-context-api-causes-frequent-re-renders--why-and-how-to-fix)
- [Context vs Redux – when to choose which?](#context-vs-redux--when-to-choose-which)
- [Do I need to keep all my state into Redux? Should I ever use react internal state?](#do-i-need-to-keep-all-my-state-into-redux-should-i-ever-use-react-internal-state)
- [Do you need to have a particular build tool to use Redux?](#do-you-need-to-have-a-particular-build-tool-to-use-redux)
- [Explain reducers and extraReducers – when to use each?](#explain-reducers-and-extrareducers--when-to-use-each)
- [Explain the flow of Redux Toolkit.](#explain-the-flow-of-redux-toolkit)
- [Explain the Redux data flow (action → reducer → store → view).](#explain-the-redux-data-flow-action--reducer--store--view)
- [Give an example on How to use context?](#give-an-example-on-how-to-use-context)
- [How do you make sure that user remains authenticated on page refresh while using Context API State Management?](#how-do-you-make-sure-that-user-remains-authenticated-on-page-refresh-while-using-context-api-state-management)
- [How do you manage global state? Compare Context, Redux, and modern alternatives.](#how-do-you-manage-global-state-compare-context-redux-and-modern-alternatives)
- [How do you solve performance corner cases while using context?](#how-do-you-solve-performance-corner-cases-while-using-context)
- [How do you test components with context?](#how-do-you-test-components-with-context)
- [How do you type context?](#how-do-you-type-context)
- [How do you type `useReducer`?](#how-do-you-type-usereducer)
- [How do you use contextType?](#how-do-you-use-contexttype)
- [How does async flow work in Redux Toolkit?](#how-does-async-flow-work-in-redux-toolkit)
- [How does React Context work? When can it hurt performance?](#how-does-react-context-work-when-can-it-hurt-performance)
- [How does Redux Toolkit work internally?](#how-does-redux-toolkit-work-internally)
- [How Relay is different from Redux?](#how-relay-is-different-from-redux)
- [How to add multiple middlewares to Redux?](#how-to-add-multiple-middlewares-to-redux)
- [How to set initial state in Redux?](#how-to-set-initial-state-in-redux)
- [Is dispatch from useReducer asynchronous and does it update state immediately?](#is-dispatch-from-usereducer-asynchronous-and-does-it-update-state-immediately)
- [Situation: Context is causing performance issues in a large app – what do you do?](#situation-context-is-causing-performance-issues-in-a-large-app--what-do-you-do)
- [What are React 19 Actions?](#what-are-react-19-actions)
- [What are Server Actions in React 19?](#what-are-server-actions-in-react-19)
- [What are the differences between Flux and Redux?](#what-are-the-differences-between-flux-and-redux)
- [What are the differences between Redux and MobX?](#what-are-the-differences-between-redux-and-mobx)
- [What are the main features of Redux Form?](#what-are-the-main-features-of-redux-form)
- [What are the use cases of useContext hook?](#what-are-the-use-cases-of-usecontext-hook)
- [What are typical middleware choices for handling asynchronous calls in Redux?](#what-are-typical-middleware-choices-for-handling-asynchronous-calls-in-redux)
- [What is an action in Redux?](#what-is-an-action-in-redux)
- [What is context?](#what-is-context)
- [What is `createSlice()` and what does it contain? (name, initialState, reducers)](#what-is-createslice-and-what-does-it-contain-name-initialstate-reducers)
- [What is flux?](#what-is-flux)
- [What is Jotai and how does the atomic model work?](#what-is-jotai-and-how-does-the-atomic-model-work)
- [What is MobX?](#what-is-mobx)
- [What is Redux Toolkit and why is it recommended over plain Redux?](#what-is-redux-toolkit-and-why-is-it-recommended-over-plain-redux)
- [What is Relay?](#what-is-relay)
- [What is the Context API?](#what-is-the-context-api)
- [What is the Context API? When should you use it instead of prop drilling?](#what-is-the-context-api-when-should-you-use-it-instead-of-prop-drilling)
- [What is the purpose of default value in context?](#what-is-the-purpose-of-default-value-in-context)
- [What is the Redux Toolkit (RTK)?](#what-is-the-redux-toolkit-rtk)
- [What is the state reducer pattern?](#what-is-the-state-reducer-pattern)
- [What is the `useSelector` / `useDispatch` pattern in Redux?](#what-is-the-useselector--usedispatch-pattern-in-redux)
- [What is the useSyncExternalStore hook?](#what-is-the-usesyncexternalstore-hook)
- [What is `useActionState` (React 19)?](#what-is-useactionstate-react-19)
- [What is `useContext`?](#what-is-usecontext)
- [What is `useReducer`?](#what-is-usereducer)
- [What is useReducer, and when would you use it over useState?](#what-is-usereducer-and-when-would-you-use-it-over-usestate)
- [What is Zustand and how does it differ from Redux?](#what-is-zustand-and-how-does-it-differ-from-redux)
- [What problems does Redux solve in large React applications?](#what-problems-does-redux-solve-in-large-react-applications)
- [What would the context value be for no matching provider?](#what-would-the-context-value-be-for-no-matching-provider)
- [When should you NOT use Context for state?](#when-should-you-not-use-context-for-state)
- [Where and why have you used Redux Toolkit in your projects?](#where-and-why-have-you-used-redux-toolkit-in-your-projects)
- [❓ What is Redux and why is it used?](#-what-is-redux-and-why-is-it-used)
- [❓ What is the difference between Context API and Redux Toolkit?](#-what-is-the-difference-between-context-api-and-redux-toolkit)

### Hooks

- [Build a custom hook like `useDebounce` or `useFetch`.](#build-a-custom-hook-like-usedebounce-or-usefetch-)
- [Can Hooks be used in class components?](#can-hooks-be-used-in-class-components)
- [Can you describe the useMemo() Hook?](#can-you-describe-the-usememo-hook)
- [Can you have multiple useEffect hooks in a single component?](#can-you-have-multiple-useeffect-hooks-in-a-single-component)
- [Custom hooks vs HOCs vs render props – when to use each?](#custom-hooks-vs-hocs-vs-render-props--when-to-use-each)
- [Difference between `useEffect`, `useLayoutEffect`, and `useInsertionEffect`.](#difference-between-useeffect--uselayouteffect--and-useinsertioneffect-)
- [Difference between `useMemo` and `React.memo`.](#difference-between-usememo-and-reactmemo-)
- [Differentiate React Hooks vs Classes.](#differentiate-react-hooks-vs-classes)
- [Do Hooks cover all the functionalities provided by the classes?](#do-hooks-cover-all-the-functionalities-provided-by-the-classes)
- [Do Hooks replace render props and higher order components?](#do-hooks-replace-render-props-and-higher-order-components)
- [Does React Hook work with static typing?](#does-react-hook-work-with-static-typing)
- [Explain about types of Hooks in React.](#explain-about-types-of-hooks-in-react)
- [Explain how to create a simple React Hooks example program.](#explain-how-to-create-a-simple-react-hooks-example-program)
- [Explain React Hooks.](#explain-react-hooks)
- [Explain `useEffect` deeply: cleanup function, dependency array pitfalls.](#explain-useeffect-deeply-cleanup-function-dependency-array-pitfalls)
- [How do you create a custom hook?](#how-do-you-create-a-custom-hook)
- [How do you share state logic between components using custom hooks?](#how-do-you-share-state-logic-between-components-using-custom-hooks)
- [How do you test custom hooks?](#how-do-you-test-custom-hooks)
- [How do you type `useRef`?](#how-do-you-type-useref)
- [How does the performance of using Hooks will differ in comparison with the classes?](#how-does-the-performance-of-using-hooks-will-differ-in-comparison-with-the-classes)
- [How does `useRef` differ from a regular variable?](#how-does-useref-differ-from-a-regular-variable)
- [How to ensure hooks followed the rules in your project?](#how-to-ensure-hooks-followed-the-rules-in-your-project)
- [How would you build a custom hook library?](#how-would-you-build-a-custom-hook-library)
- [Implement a custom hook like `useDebounce` or `useFetch` (React).](#implement-a-custom-hook-like-usedebounce-or-usefetch-react)
- [Is Hooks cover all use cases for classes?](#is-hooks-cover-all-use-cases-for-classes)
- [Situation: `useEffect` runs infinitely – what's wrong?](#situation-useeffect-runs-infinitely--whats-wrong)
- [What are Custom Hooks?](#what-are-custom-hooks)
- [What are Custom React Hooks, and How Can You Develop One?](#what-are-custom-react-hooks-and-how-can-you-develop-one)
- [What are hooks?](#what-are-hooks)
- [What are stale closures in `useEffect`?](#what-are-stale-closures-in-useeffect)
- [What are the best practices for using React Hooks?](#what-are-the-best-practices-for-using-react-hooks)
- [What are the common usecases of useRef hook?](#what-are-the-common-usecases-of-useref-hook)
- [What are the rules needs to follow for hooks?](#what-are-the-rules-needs-to-follow-for-hooks)
- [What are the Rules of Hooks?](#what-are-the-rules-of-hooks)
- [What are the rules that must be followed while using React Hooks?](#what-are-the-rules-that-must-be-followed-while-using-react-hooks)
- [What are the sources used for introducing hooks?](#what-are-the-sources-used-for-introducing-hooks)
- [What is a hook?](#what-is-a-hook)
- [What is a hook? Why were hooks introduced?](#what-is-a-hook-why-were-hooks-introduced)
- [What is lazy initialization in `useState`?](#what-is-lazy-initialization-in-usestate)
- [What is React Hooks?](#what-is-react-hooks)
- [What is React.memo? How is it different from useMemo and useCallback?](#what-is-reactmemo-how-is-it-different-from-usememo-and-usecallback)
- [What is the difference between useEffect and useLayoutEffect?](#what-is-the-difference-between-useeffect-and-uselayouteffect)
- [What is the difference between useMemo and React.memo?](#what-is-the-difference-between-usememo-and-reactmemo)
- [What is the difference between useState and useRef hook?](#what-is-the-difference-between-usestate-and-useref-hook)
- [What is the `eslint-plugin-react-hooks` plugin?](#what-is-the-eslint-plugin-react-hooks-plugin)
- [What is the order of hook execution in a component?](#what-is-the-order-of-hook-execution-in-a-component)
- [What is the purpose of eslint plugin for hooks?](#what-is-the-purpose-of-eslint-plugin-for-hooks)
- [What is the stable release for hooks support?](#what-is-the-stable-release-for-hooks-support)
- [What is the use of useEffect React Hooks?](#what-is-the-use-of-useeffect-react-hooks)
- [What is the use() hook in React 19?](#what-is-the-use-hook-in-react-19)
- [What is the useDebugValue hook?](#what-is-the-usedebugvalue-hook)
- [What is the useDeferredValue hook?](#what-is-the-usedeferredvalue-hook)
- [What is the useId hook and when should you use it?](#what-is-the-useid-hook-and-when-should-you-use-it)
- [What is the useInsertionEffect hook?](#what-is-the-useinsertioneffect-hook)
- [What is the useOptimistic hook?](#what-is-the-useoptimistic-hook)
- [What is the useTransition hook and how does it differ from useDeferredValue?](#what-is-the-usetransition-hook-and-how-does-it-differ-from-usedeferredvalue)
- [What is the `useTransition` hook for performance?](#what-is-the-usetransition-hook-for-performance)
- [What is `useCallback` and why is it used?](#what-is-usecallback-and-why-is-it-used)
- [What is `useDebugValue`?](#what-is-usedebugvalue)
- [What is `useDeferredValue`?](#what-is-usedeferredvalue)
- [What is `useEffect`?](#what-is-useeffect)
- [What is `useImperativeHandle`?](#what-is-useimperativehandle)
- [What is `useLayoutEffect`?](#what-is-uselayouteffect)
- [What is `useMemo`?](#what-is-usememo)
- [What is `useOptimistic` (React 19)?](#what-is-useoptimistic-react-19)
- [What is `useRef`?](#what-is-useref)
- [What is `useState`?](#what-is-usestate)
- [What is useState() in React?](#what-is-usestate-in-react)
- [What is `useTransition`?](#what-is-usetransition)
- [What problems does `useMemo` actually solve? When should you NOT use it?](#what-problems-does-usememo-actually-solve-when-should-you-not-use-it)
- [What rules need to be followed for hooks?](#what-rules-need-to-be-followed-for-hooks)
- [When and how often does React invoke the setup and cleanup functions inside a useEffect hook?](#when-and-how-often-does-react-invoke-the-setup-and-cleanup-functions-inside-a-useeffect-hook)
- [Why do React Hooks make use of refs?](#why-do-react-hooks-make-use-of-refs)
- [Why do we use array destructuring (square brackets notation) in `useState`?](#why-do-we-use-array-destructuring-square-brackets-notation-in-usestate)
- [Why use functional updates with `useState`?](#why-use-functional-updates-with-usestate)
- [❓ What is the difference between useEffect, useLayoutEffect, and useInsertionEffect?](#-what-is-the-difference-between-useeffect-uselayouteffect-and-useinsertioneffect)
- [❓ What is the difference between useMemo and useCallback?](#-what-is-the-difference-between-usememo-and-usecallback)

### Performance & Concurrent React

- [A React component re-renders again and again but you never called setState. Why?](#a-react-component-re-renders-again-and-again-but-you-never-called-setstate-why)
- [Can you force a component to re-render without calling setState?](#can-you-force-a-component-to-re-render-without-calling-setstate)
- [CPU vs memory bottlenecks – how to identify and fix?](#cpu-vs-memory-bottlenecks--how-to-identify-and-fix)
- [Design an Image Gallery with lazy loading and skeleton placeholders.](#design-an-image-gallery-with-lazy-loading-and-skeleton-placeholders)
- [How do you balance performance vs feature delivery?](#how-do-you-balance-performance-vs-feature-delivery)
- [How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)](#how-do-you-debug-a-performance-bottleneck-in-a-react-app-using-devtools-profiler-performance-tab)
- [How do you detect and prevent memory leaks in long-running SPAs?](#how-do-you-detect-and-prevent-memory-leaks-in-long-running-spas)
- [How do you ensure a React app performs well at 100k users?](#how-do-you-ensure-a-react-app-performs-well-at-100k-users)
- [How do you measure and fix excessive re-renders?](#how-do-you-measure-and-fix-excessive-re-renders)
- [How do you memoize a component?](#how-do-you-memoize-a-component)
- [How does the Virtual DOM improve performance?](#how-does-the-virtual-dom-improve-performance)
- [How to focus an input element on page load?](#how-to-focus-an-input-element-on-page-load)
- [How to prevent re-renders in React?](#how-to-prevent-re-renders-in-react)
- [How to re-render the view when the browser is resized?](#how-to-re-render-the-view-when-the-browser-is-resized)
- [How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)](#how-would-you-handle-a-large-dataset-without-blocking-the-main-thread-web-workers-virtualization)
- [How would you improve Web Vitals (LCP, CLS, INP)?](#how-would-you-improve-web-vitals-lcp-cls-inp)
- [How would you optimize a React application rendering 100,000+ items in a list?](#how-would-you-optimize-a-react-application-rendering-100000-items-in-a-list)
- [How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)](#how-would-you-optimize-a-react-application-rendering-100k-items-in-a-list-virtualization-windowing-pagination)
- [Name a few techniques to optimize React app performance.](#name-a-few-techniques-to-optimize-react-app-performance)
- [Situation: A search input lags as user types -- how do you fix it?](#situation-a-search-input-lags-as-user-types----how-do-you-fix-it)
- [What are common React performance optimization techniques? (practical guide)](#what-are-common-react-performance-optimization-techniques-practical-guide)
- [What are common React performance pitfalls?](#what-are-common-react-performance-pitfalls)
- [What are React Suspense and React.lazy? How do they enable code splitting?](#what-are-react-suspense-and-reactlazy-how-do-they-enable-code-splitting)
- [What are the two ways of formatting in React Intl?](#what-are-the-two-ways-of-formatting-in-react-intl)
- [What causes unnecessary re-renders?](#what-causes-unnecessary-re-renders)
- [What causes unnecessary re-renders in React?](#what-causes-unnecessary-re-renders-in-react)
- [What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)](#what-causes-unnecessary-re-renders-in-react-how-to-avoid-them-memoization-stable-props-colocated-state)
- [What happens if a child uses React.memo() and parent props don't change?](#what-happens-if-a-child-uses-reactmemo-and-parent-props-dont-change)
- [What happens if a component wrapped in `memo()` has its own state changes?](#what-happens-if-a-component-wrapped-in-memo-has-its-own-state-changes)
- [What happens when a parent re-renders?](#what-happens-when-a-parent-re-renders)
- [What is code splitting?](#what-is-code-splitting)
- [What is code splitting and how does React.lazy work internally?](#what-is-code-splitting-and-how-does-reactlazy-work-internally)
- [What is code-splitting?](#what-is-code-splitting)
- [What is Concurrent Rendering?](#what-is-concurrent-rendering)
- [What is concurrent rendering? When does it help vs hurt?](#what-is-concurrent-rendering-when-does-it-help-vs-hurt)
- [What is React lazy function?](#what-is-react-lazy-function)
- [What is React memo function?](#what-is-react-memo-function)
- [What is `React.lazy` and how does it work?](#what-is-reactlazy-and-how-does-it-work)
- [What is `React.memo`?](#what-is-reactmemo)
- [What is `startTransition`?](#what-is-starttransition)
- [What is Suspense?](#what-is-suspense)
- [What is suspense component?](#what-is-suspense-component)
- [What is the difference between async mode and concurrent mode?](#what-is-the-difference-between-async-mode-and-concurrent-mode)
- [What is the difference between element and component re-render?](#what-is-the-difference-between-element-and-component-re-render)
- [What is the difference between virtualization and windowing? Trade-offs.](#what-is-the-difference-between-virtualization-and-windowing-trade-offs)
- [What is the methods order when component re-rendered?](#what-is-the-methods-order-when-component-re-rendered)
- [What is the Profiler API?](#what-is-the-profiler-api)
- [What is the purpose of ESLint and Prettier in a React project?](#what-is-the-purpose-of-eslint-and-prettier-in-a-react-project)
- [What is the purpose of Suspense beyond lazy loading?](#what-is-the-purpose-of-suspense-beyond-lazy-loading)
- [What is windowing technique?](#what-is-windowing-technique)
- [What is windowing/virtualization and when do you need it?](#what-is-windowingvirtualization-and-when-do-you-need-it)
- [What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)](#what-strategies-would-you-use-to-improve-page-load-time-for-a-global-audience-cdn-lazy-loading-code-splitting-image-optimization)
- [When does `React.memo` NOT help?](#when-does-reactmemo-not-help)
- [When to Still Use Manual Optimization](#when-to-still-use-manual-optimization)
- [When would you use `React.memo`?](#when-would-you-use-reactmemo)
- [❓ How do you debug a performance bottleneck in a React app using DevTools?](#-how-do-you-debug-a-performance-bottleneck-in-a-react-app-using-devtools)
- [❓ If given an existing website to analyze and improve performance, what is your first step?](#-if-given-an-existing-website-to-analyze-and-improve-performance-what-is-your-first-step)
- [❓ What are Web Vitals and why do they matter?](#-what-are-web-vitals-and-why-do-they-matter)
- [❓ What is re-rendering and why does it happen?](#-what-is-re-rendering-and-why-does-it-happen)
- [❓ You notice a memory leak in a production SPA — how do you identify and fix it?](#-you-notice-a-memory-leak-in-a-production-spa--how-do-you-identify-and-fix-it)

### React 18/19, SSR & Server Components

- [Explain React Server Components vs Client Components.](#explain-react-server-components-vs-client-components)
- [How does React 18's automatic batching work?](#how-does-react-18s-automatic-batching-work)
- [How would you implement SSR for a React application?](#how-would-you-implement-ssr-for-a-react-application)
- [What are React Server components?](#what-are-react-server-components)
- [What are the key features introduced in React 18?](#what-are-the-key-features-introduced-in-react-18)
- [What causes hydration mismatches and how do you fix them?](#what-causes-hydration-mismatches-and-how-do-you-fix-them)
- [What is automatic batching in React 18?](#what-is-automatic-batching-in-react-18)
- [What is `createRoot()` and why was it introduced in React 18?](#what-is-createroot-and-why-was-it-introduced-in-react-18)
- [What is hydration?](#what-is-hydration)
- [What is hydration? How do hydration mismatches occur?](#what-is-hydration-how-do-hydration-mismatches-occur)
- [What is hydration in React?](#what-is-hydration-in-react)
- [What is React hydration?](#what-is-react-hydration)
- [What is server-side rendering (SSR)? How does it differ from client-side rendering?](#what-is-server-side-rendering-ssr-how-does-it-differ-from-client-side-rendering)
- [What is SSR with React?](#what-is-ssr-with-react)
- [What is state batching? What changed in React 18 regarding batching?](#what-is-state-batching-what-changed-in-react-18-regarding-batching)
- [What is streaming SSR?](#what-is-streaming-ssr)
- [What is Streaming SSR and how does React 18+ improve it?](#what-is-streaming-ssr-and-how-does-react-18-improve-it)
- [What is the 'use client' directive?](#what-is-the-use-client-directive)
- [❓ Difference between CSR, SSR, SSG, and ISR?](#-difference-between-csr-ssr-ssg-and-isr)
- [❓ What is state batching? What changed in React 18?](#-what-is-state-batching-what-changed-in-react-18)

### Rendering, Reconciliation & Lifecycle

- [A user complains about slow UI after data load --- how would you optimize rendering and improve UX?](#a-user-complains-about-slow-ui-after-data-load-----how-would-you-optimize-rendering-and-improve-ux)
- [Can you describe about componentDidCatch lifecycle method signature?](#can-you-describe-about-componentdidcatch-lifecycle-method-signature)
- [Explain conditional rendering in React.](#explain-conditional-rendering-in-react)
- [Explain Strict Mode in React.](#explain-strict-mode-in-react)
- [How are error boundaries handled in React v15?](#how-are-error-boundaries-handled-in-react-v15)
- [How do you create an error boundary?](#how-do-you-create-an-error-boundary)
- [How do you test error boundaries?](#how-do-you-test-error-boundaries)
- [How does React's diffing algorithm work (O(n))?](#how-does-reacts-diffing-algorithm-work-on)
- [How to make AJAX call and in which component lifecycle methods should I make an AJAX call?](#how-to-make-ajax-call-and-in-which-component-lifecycle-methods-should-i-make-an-ajax-call)
- [How to prevent component from rendering?](#how-to-prevent-component-from-rendering)
- [Is it good to use arrow functions in render methods?](#is-it-good-to-use-arrow-functions-in-render-methods)
- [What are error boundaries?](#what-are-error-boundaries)
- [What are error boundaries in React v16?](#what-are-error-boundaries-in-react-v16)
- [What are the different phases of component lifecycle?](#what-are-the-different-phases-of-component-lifecycle)
- [What are the lifecycle methods going to be deprecated in React v16?](#what-are-the-lifecycle-methods-going-to-be-deprecated-in-react-v16)
- [What are the lifecycle methods of React?](#what-are-the-lifecycle-methods-of-react)
- [What are the possible return types of render method?](#what-are-the-possible-return-types-of-render-method)
- [What are the rules covered by diffing algorithm?](#what-are-the-rules-covered-by-diffing-algorithm)
- [What is an error boundary?](#what-is-an-error-boundary)
- [What is diffing algorithm?](#what-is-diffing-algorithm)
- [What is React Fiber?](#what-is-react-fiber)
- [What is reconciliation?](#what-is-reconciliation)
- [What is reconciliation? How does React's diffing algorithm work?](#what-is-reconciliation-how-does-reacts-diffing-algorithm-work)
- [What is reconciliation in React? How does the diffing algorithm work?](#what-is-reconciliation-in-react-how-does-the-diffing-algorithm-work)
- [What is re‑rendering, and why does it happen?](#what-is-rerendering-and-why-does-it-happen)
- [What is Strict Mode?](#what-is-strict-mode)
- [What is strict mode in React?](#what-is-strict-mode-in-react)
- [What is the benefit of component stack trace from error boundary?](#what-is-the-benefit-of-component-stack-trace-from-error-boundary)
- [What is the benefit of strict mode?](#what-is-the-benefit-of-strict-mode)
- [What is the difference between shallow and deep rendering?](#what-is-the-difference-between-shallow-and-deep-rendering)
- [What is the difference between try catch block and error boundaries?](#what-is-the-difference-between-try-catch-block-and-error-boundaries)
- [What is the main goal of React Fiber?](#what-is-the-main-goal-of-react-fiber)
- [What is the purpose of render method of `react-dom`?](#what-is-the-purpose-of-render-method-of-react-dom)
- [Why do not you need error boundaries for event handlers?](#why-do-not-you-need-error-boundaries-for-event-handlers)
- [Why does strict mode render twice in React?](#why-does-strict-mode-render-twice-in-react)
- [❓ What is reconciliation in React?](#-what-is-reconciliation-in-react)

### Components, Props & State

- [Can I import an SVG file as react component?](#can-i-import-an-svg-file-as-react-component)
- [Can I use web components in react application?](#can-i-use-web-components-in-react-application)
- [Controlled vs uncontrolled components?](#controlled-vs-uncontrolled-components)
- [Controlled vs uncontrolled forms -- trade-offs in practice?](#controlled-vs-uncontrolled-forms----trade-offs-in-practice)
- [Explain about types of side effects in React component.](#explain-about-types-of-side-effects-in-react-component)
- [Explain React state and props.](#explain-react-state-and-props)
- [Explain the concept of "controlled re‑render boundaries".](#explain-the-concept-of-controlled-rerender-boundaries)
- [Functional vs class components – key differences?](#functional-vs-class-components--key-differences)
- [Give an example of Styled Components?](#give-an-example-of-styled-components)
- [How do you access imperative API of web components?](#how-do-you-access-imperative-api-of-web-components)
- [How do you access props in attribute quotes?](#how-do-you-access-props-in-attribute-quotes)
- [How do you approach developing a reusable component from a design?](#how-do-you-approach-developing-a-reusable-component-from-a-design)
- [How do you create HOC using render props?](#how-do-you-create-hoc-using-render-props)
- [How do you pass an event handler to a component?](#how-do-you-pass-an-event-handler-to-a-component)
- [How do you pass parent data to the 5th child component?](#how-do-you-pass-parent-data-to-the-5th-child-component)
- [How do you prevent prop explosion in complex components?](#how-do-you-prevent-prop-explosion-in-complex-components)
- [How do you say that props are readonly?](#how-do-you-say-that-props-are-readonly)
- [How do you say that state updates are merged?](#how-do-you-say-that-state-updates-are-merged)
- [How do you set default value for uncontrolled component?](#how-do-you-set-default-value-for-uncontrolled-component)
- [How do you type children in React with TypeScript?](#how-do-you-type-children-in-react-with-typescript)
- [How do you type component props with TypeScript?](#how-do-you-type-component-props-with-typescript)
- [How do you update arrays inside state?](#how-do-you-update-arrays-inside-state)
- [How do you update nested objects inside state?](#how-do-you-update-nested-objects-inside-state)
- [How do you use immer library for state updates?](#how-do-you-use-immer-library-for-state-updates)
- [How does React batch multiple state updates?](#how-does-react-batch-multiple-state-updates)
- [How to apply validation on props in React?](#how-to-apply-validation-on-props-in-react)
- [How to create a switching component for displaying different pages?](#how-to-create-a-switching-component-for-displaying-different-pages)
- [How to create components in React?](#how-to-create-components-in-react)
- [How to create props proxy for HOC component?](#how-to-create-props-proxy-for-hoc-component)
- [How to create react class components without ES6?](#how-to-create-react-class-components-without-es6)
- [How to debug forwardRefs in DevTools?](#how-to-debug-forwardrefs-in-devtools)
- [How to import and export components using React and ES6?](#how-to-import-and-export-components-using-react-and-es6)
- [How to listen to state changes?](#how-to-listen-to-state-changes)
- [How to pass data between react components?](#how-to-pass-data-between-react-components)
- [How to pass numbers to React component?](#how-to-pass-numbers-to-react-component)
- [How to prevent unnecessary updates using setState?](#how-to-prevent-unnecessary-updates-using-setstate)
- [How to set state with a dynamic key name?](#how-to-set-state-with-a-dynamic-key-name)
- [How to update a component every second?](#how-to-update-a-component-every-second)
- [If we have `var`, `let`, `const`, why do we need state variables?](#if-we-have-var--let--const--why-do-we-need-state-variables)
- [Implement Debouncing and Throttling in a search or scroll-heavy component.](#implement-debouncing-and-throttling-in-a-search-or-scroll-heavy-component)
- [Is it keys should be globally unique?](#is-it-keys-should-be-globally-unique)
- [Is it mandatory to define constructor for React component?](#is-it-mandatory-to-define-constructor-for-react-component)
- [Is it prop must be named as render for render props?](#is-it-prop-must-be-named-as-render-for-render-props)
- [Is it ref argument available for all functions or class components?](#is-it-ref-argument-available-for-all-functions-or-class-components)
- [Library Upgrade: A component breaks when upgrading a library version -- how do you manage dependencies?](#library-upgrade-a-component-breaks-when-upgrading-a-library-version----how-do-you-manage-dependencies)
- [Must prop be named as render for render props?](#must-prop-be-named-as-render-for-render-props)
- [Situation: A third-party component throws -- how do you handle it?](#situation-a-third-party-component-throws----how-do-you-handle-it)
- [Situation: Two components on different branches need the same data – what do you do?](#situation-two-components-on-different-branches-need-the-same-data--what-do-you-do)
- [What are components? Functional vs class components.](#what-are-components-functional-vs-class-components)
- [What are compound components?](#what-are-compound-components)
- [What are controlled components?](#what-are-controlled-components)
- [What are controlled vs. uncontrolled components?](#what-are-controlled-vs-uncontrolled-components)
- [What are default props?](#what-are-default-props)
- [What are default props and PropTypes?](#what-are-default-props-and-proptypes)
- [What are fragments?](#what-are-fragments)
- [What are headless components?](#what-are-headless-components)
- [What are Higher Order Components?](#what-are-higher-order-components)
- [What are Higher-Order Components (HOCs)?](#what-are-higher-order-components-hocs)
- [What are HOC factory implementations?](#what-are-hoc-factory-implementations)
- [What are Keyed Fragments?](#what-are-keyed-fragments)
- [What are keys in React?](#what-are-keys-in-react)
- [What are loadable components?](#what-are-loadable-components)
- [What are portals?](#what-are-portals)
- [What are portals in React?](#what-are-portals-in-react)
- [What are presentational vs container components?](#what-are-presentational-vs-container-components)
- [What are props?](#what-are-props)
- [What are props in React?](#what-are-props-in-react)
- [What are pure components?](#what-are-pure-components)
- [What are React elements vs React components?](#what-are-react-elements-vs-react-components)
- [What are React Portals, and when would you use them?](#what-are-react-portals-and-when-would-you-use-them)
- [What are render props?](#what-are-render-props)
- [What are state and props?](#what-are-state-and-props)
- [What are state and props? Difference between them.](#what-are-state-and-props-difference-between-them)
- [What are stateful components?](#what-are-stateful-components)
- [What are stateless components?](#what-are-stateless-components)
- [What are Styled Components?](#what-are-styled-components)
- [What are the differences between controlled and uncontrolled components?](#what-are-the-differences-between-controlled-and-uncontrolled-components)
- [What are the differences between functional and class components?](#what-are-the-differences-between-functional-and-class-components)
- [What are the different ways to style a React component?](#what-are-the-different-ways-to-style-a-react-component)
- [What are the exceptions on React component naming?](#what-are-the-exceptions-on-react-component-naming)
- [What are the hidden reasons a component re‑renders even when props don't change?](#what-are-the-hidden-reasons-a-component-rerenders-even-when-props-dont-change)
- [What are the limitations with HOCs?](#what-are-the-limitations-with-hocs)
- [What are the possible ways of updating objects in state?](#what-are-the-possible-ways-of-updating-objects-in-state)
- [What are the preferred and non-preferred array operations for updating the state?](#what-are-the-preferred-and-non-preferred-array-operations-for-updating-the-state)
- [What are the problems of using render props with pure components?](#what-are-the-problems-of-using-render-props-with-pure-components)
- [What are uncontrolled components?](#what-are-uncontrolled-components)
- [What happens if you mutate state directly?](#what-happens-if-you-mutate-state-directly)
- [What is a React component?](#what-is-a-react-component)
- [What is a switching component?](#what-is-a-switching-component)
- [What is a wrapper component?](#what-is-a-wrapper-component)
- [What is children prop?](#what-is-children-prop)
- [What is `forwardRef`?](#what-is-forwardref)
- [What is forwardRef, and when do you need it?](#what-is-forwardref-and-when-do-you-need-it)
- [What is lifting state up?](#what-is-lifting-state-up)
- [What is Lifting State Up in React?](#what-is-lifting-state-up-in-react)
- [What is prop drilling and why is it a problem?](#what-is-prop-drilling-and-why-is-it-a-problem)
- [What is prop drilling in React?](#what-is-prop-drilling-in-react)
- [What is prop drilling? Problems and solutions.](#what-is-prop-drilling-problems-and-solutions)
- [What is React.Fragment and why is it useful?](#what-is-reactfragment-and-why-is-it-useful)
- [What is server state vs client state?](#what-is-server-state-vs-client-state)
- [What is state in React?](#what-is-state-in-react)
- [What is state mutation and how to prevent it?](#what-is-state-mutation-and-how-to-prevent-it)
- [What is the container/presenter pattern and is it still relevant?](#what-is-the-containerpresenter-pattern-and-is-it-still-relevant)
- [What is the controlled component pattern for reusable components?](#what-is-the-controlled-component-pattern-for-reusable-components)
- [What is the difference between an Element and a Component?](#what-is-the-difference-between-an-element-and-a-component)
- [What is the difference between props and state?](#what-is-the-difference-between-props-and-state)
- [What is the difference between state and props?](#what-is-the-difference-between-state-and-props)
- [What is the difference between `super()` and `super(props)` in React using ES6 classes?](#what-is-the-difference-between-super-and-superprops-in-react-using-es6-classes)
- [What is the impact of indexes as keys?](#what-is-the-impact-of-indexes-as-keys)
- [What is the `key` prop and why is it important?](#what-is-the-key-prop-and-why-is-it-important)
- [What is the purpose of forward ref in HOCs?](#what-is-the-purpose-of-forward-ref-in-hocs)
- [What is the purpose of getDerivedStateFromError?](#what-is-the-purpose-of-getderivedstatefromerror)
- [What is the purpose of unmountComponentAtNode method?](#what-is-the-purpose-of-unmountcomponentatnode-method)
- [What is the purpose of using super constructor with props argument?](#what-is-the-purpose-of-using-super-constructor-with-props-argument)
- [What is the recommended approach of removing an array element in React state?](#what-is-the-recommended-approach-of-removing-an-array-element-in-react-state)
- [What is the recommended ordering of methods in component class?](#what-is-the-recommended-ordering-of-methods-in-component-class)
- [What is the render props pattern?](#what-is-the-render-props-pattern)
- [What is the required method to be defined for a class component?](#what-is-the-required-method-to-be-defined-for-a-class-component)
- [What is the typical use case of portals?](#what-is-the-typical-use-case-of-portals)
- [What will happen if you use props in initial state?](#what-will-happen-if-you-use-props-in-initial-state)
- [What would be the common mistake of function being called every time the component renders?](#what-would-be-the-common-mistake-of-function-being-called-every-time-the-component-renders)
- [When component props defaults to true?](#when-component-props-defaults-to-true)
- [When should a component be split into smaller components?](#when-should-a-component-be-split-into-smaller-components)
- [When to use a Class Component over a Function Component?](#when-to-use-a-class-component-over-a-function-component)
- [Why are keys important in lists? What happens if keys are unstable?](#why-are-keys-important-in-lists-what-happens-if-keys-are-unstable)
- [Why avoid array index as key?](#why-avoid-array-index-as-key)
- [Why can't you update props in React?](#why-cant-you-update-props-in-react)
- [Why do you need additional care for component libraries while using forward refs?](#why-do-you-need-additional-care-for-component-libraries-while-using-forward-refs)
- [Why fragments are better than container divs?](#why-fragments-are-better-than-container-divs)
- [Why is a component constructor called only once?](#why-is-a-component-constructor-called-only-once)
- [Why is state update asynchronous?](#why-is-state-update-asynchronous)
- [Why should component names start with capital letter?](#why-should-component-names-start-with-capital-letter)
- [Why should not call setState in componentWillUnmount?](#why-should-not-call-setstate-in-componentwillunmount)
- [Why should we not update the state directly?](#why-should-we-not-update-the-state-directly)
- [Why we need to be careful when spreading props on DOM elements?](#why-we-need-to-be-careful-when-spreading-props-on-dom-elements)
- [❓ If we have var, let, and const, why do we need state variables?](#-if-we-have-var-let-and-const-why-do-we-need-state-variables)
- [❓ What is prop drilling and how do you solve it?](#-what-is-prop-drilling-and-how-do-you-solve-it)

### TypeScript, Testing, Accessibility & Security

- [Describe about data flow in react?](#describe-about-data-flow-in-react)
- [Explain contract testing between frontend and backend.](#explain-contract-testing-between-frontend-and-backend)
- [Have you worked with Storybook? How do you use it?](#have-you-worked-with-storybook-how-do-you-use-it)
- [How do you ensure code quality with testing? (unit, integration, e2e)](#how-do-you-ensure-code-quality-with-testing-unit-integration-e2e)
- [How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)](#how-do-you-ensure-secure-handling-of-sensitive-user-data-on-the-client-side-xss-csp-csrf-token-leakage)
- [How do you test async behavior (e.g., API calls)?](#how-do-you-test-async-behavior-eg-api-calls)
- [How does React prevent XSS by default?](#how-does-react-prevent-xss-by-default)
- [How React PropTypes allow different types for one prop?](#how-react-proptypes-allow-different-types-for-one-prop)
- [How to use TypeScript in `create-react-app` application?](#how-to-use-typescript-in-create-react-app-application)
- [What are flaky test detection strategies?](#what-are-flaky-test-detection-strategies)
- [What are the benefits of using typescript with reactjs?](#what-are-the-benefits-of-using-typescript-with-reactjs)
- [What is Flow?](#what-is-flow)
- [What is Mock Service Worker (MSW)?](#what-is-mock-service-worker-msw)
- [What is React Testing Library?](#what-is-react-testing-library)
- [What is Shallow Renderer in React testing?](#what-is-shallow-renderer-in-react-testing)
- [What is the difference between Flow and PropTypes?](#what-is-the-difference-between-flow-and-proptypes)
- [What is the testing pyramid for React?](#what-is-the-testing-pyramid-for-react)
- [What is visual regression testing? How would you implement it?](#what-is-visual-regression-testing-how-would-you-implement-it)
- [What is Vitest and how does it differ from Jest?](#what-is-vitest-and-how-does-it-differ-from-jest)
- [What tools help check React app accessibility?](#what-tools-help-check-react-app-accessibility)
- [Why does accessibility matter in React apps?](#why-does-accessibility-matter-in-react-apps)
- [Why use TypeScript with React?](#why-use-typescript-with-react)
- [❓ What is the difference between visual regression testing and contract testing?](#-what-is-the-difference-between-visual-regression-testing-and-contract-testing)

### React Ecosystem & Libraries

- [Give an example of Reselect usage?](#give-an-example-of-reselect-usage)
- [How to access current locale with React Intl?](#how-to-access-current-locale-with-react-intl)
- [How to add Bootstrap to a react application?](#how-to-add-bootstrap-to-a-react-application)
- [How to format date using React Intl?](#how-to-format-date-using-react-intl)
- [How to use Font Awesome icons in React?](#how-to-use-font-awesome-icons-in-react)
- [How to use `<FormattedMessage>` as placeholder using React Intl?](#how-to-use-formattedmessage-as-placeholder-using-react-intl)
- [How to use Polymer in React?](#how-to-use-polymer-in-react)
- [How would you implement internationalization (i18n) in React?](#how-would-you-implement-internationalization-i18n-in-react)
- [Is it recommended to use CSS In JS technique in React?](#is-it-recommended-to-use-css-in-js-technique-in-react)
- [What are the benefits of new JSX transform?](#what-are-the-benefits-of-new-jsx-transform)
- [What are the features of create react app?](#what-are-the-features-of-create-react-app)
- [What are the main features of React Intl?](#what-are-the-main-features-of-react-intl)
- [What are the main features of Reselect library?](#what-are-the-main-features-of-reselect-library)
- [What is React Intl?](#what-is-react-intl)
- [What is react scripts?](#what-is-react-scripts)
- [What is reselect and how it works?](#what-is-reselect-and-how-it-works)
- [What is the purpose of registerServiceWorker in React?](#what-is-the-purpose-of-registerserviceworker-in-react)

### Fundamentals & JSX

- [Can you use React without JSX?](#can-you-use-react-without-jsx)
- [Do browsers understand JSX code?](#do-browsers-understand-jsx-code)
- [Does React support all HTML attributes?](#does-react-support-all-html-attributes)
- [How do you print falsy values in JSX?](#how-do-you-print-falsy-values-in-jsx)
- [How do you update rendered elements?](#how-do-you-update-rendered-elements)
- [How JSX prevents Injection Attacks?](#how-jsx-prevents-injection-attacks)
- [How to bind methods or event handlers in JSX callbacks?](#how-to-bind-methods-or-event-handlers-in-jsx-callbacks)
- [How to loop inside JSX?](#how-to-loop-inside-jsx)
- [How to use innerHTML in React?](#how-to-use-innerhtml-in-react)
- [How to use React label element?](#how-to-use-react-label-element)
- [How Virtual DOM works?](#how-virtual-dom-works)
- [Is it possible to use react without JSX?](#is-it-possible-to-use-react-without-jsx)
- [What are synthetic events?](#what-are-synthetic-events)
- [What are synthetic events in React?](#what-are-synthetic-events-in-react)
- [What are the limitations of React?](#what-are-the-limitations-of-react)
- [What are the major features of React?](#what-are-the-major-features-of-react)
- [What does 'declarative' mean in React?](#what-does-declarative-mean-in-react)
- [What does JSX compile to?](#what-does-jsx-compile-to)
- [What is a React SPA and what are its trade-offs?](#what-is-a-react-spa-and-what-are-its-trade-offs)
- [What is `dangerouslySetInnerHTML` and why is it dangerous?](#what-is-dangerouslysetinnerhtml-and-why-is-it-dangerous)
- [What is JSX?](#what-is-jsx)
- [What is JSX and how is it rendered in the browser?](#what-is-jsx-and-how-is-it-rendered-in-the-browser)
- [What is JSX and why does React use it?](#what-is-jsx-and-why-does-react-use-it)
- [What is NextJS and major features of it?](#what-is-nextjs-and-major-features-of-it)
- [What is the browser support for react applications?](#what-is-the-browser-support-for-react-applications)
- [What is the difference between createElement and cloneElement?](#what-is-the-difference-between-createelement-and-cloneelement)
- [What is the difference between Imperative and Declarative in React?](#what-is-the-difference-between-imperative-and-declarative-in-react)
- [What is the difference between Real DOM and Virtual DOM?](#what-is-the-difference-between-real-dom-and-virtual-dom)
- [What is the React DevTools and what can you do with it?](#what-is-the-react-devtools-and-what-can-you-do-with-it)
- [What is the reason behind multiple JSX tags to be wrapped?](#what-is-the-reason-behind-multiple-jsx-tags-to-be-wrapped)
- [What is the Virtual DOM?](#what-is-the-virtual-dom)
- [What is the virtual DOM? How does react use the virtual DOM to render the UI?](#what-is-the-virtual-dom-how-does-react-use-the-virtual-dom-to-render-the-ui)
- [Why React tab is not showing up in DevTools?](#why-react-tab-is-not-showing-up-in-devtools)
- [Why you get "Router may have only one child element" warning?](#why-you-get-router-may-have-only-one-child-element-warning)

### React Fundamentals & Miscellaneous

- [Are custom DOM attributes supported in React v16?](#are-custom-dom-attributes-supported-in-react-v16)
- [Can I use javascript urls in react16.9?](#can-i-use-javascript-urls-in-react169)
- [Can you list down top websites or applications using react as front end framework?](#can-you-list-down-top-websites-or-applications-using-react-as-front-end-framework)
- [Does the statics object work with ES6 classes in React?](#does-the-statics-object-work-with-es6-classes-in-react)
- [How can we find the version of React at runtime in the browser?](#how-can-we-find-the-version-of-react-at-runtime-in-the-browser)
- [How do you apply vendor prefixes to inline styles in React?](#how-do-you-apply-vendor-prefixes-to-inline-styles-in-react)
- [How do you avoid unnecessary object/function recreation?](#how-do-you-avoid-unnecessary-objectfunction-recreation)
- [How do you build a reusable modal?](#how-do-you-build-a-reusable-modal)
- [How do you integrate a non-React library (e.g., D3, Leaflet)?](#how-do-you-integrate-a-non-react-library-eg-d3-leaflet)
- [How do you pass data child → parent?](#how-do-you-pass-data-child--parent)
- [How do you pass parent data to a deeply nested child (e.g., 5th child)?](#how-do-you-pass-parent-data-to-a-deeply-nested-child-eg-5th-child)
- [How do you render Array, Strings and Numbers in React 16 Version?](#how-do-you-render-array-strings-and-numbers-in-react-16-version)
- [How do you type event handlers?](#how-do-you-type-event-handlers)
- [How does React updates screen in an application?](#how-does-react-updates-screen-in-an-application)
- [How events are different in React?](#how-events-are-different-in-react)
- [How is React different from Angular or Vue?](#how-is-react-different-from-angular-or-vue)
- [How It Works](#how-it-works)
- [How should you structure a large React application?](#how-should-you-structure-a-large-react-application)
- [How to conditionally apply class attributes?](#how-to-conditionally-apply-class-attributes)
- [How to define constants in React?](#how-to-define-constants-in-react)
- [How to implement _default_ or _NotFound_ page?](#how-to-implement-default-or-notfound-page)
- [How to pretty print JSON with React?](#how-to-pretty-print-json-with-react)
- [How to programmatically trigger click event in React?](#how-to-programmatically-trigger-click-event-in-react)
- [How to use class field declarations syntax in React classes?](#how-to-use-class-field-declarations-syntax-in-react-classes)
- [How to use styles in React?](#how-to-use-styles-in-react)
- [How to write comments in React?](#how-to-write-comments-in-react)
- [How would you implement a robust frontend monitoring and logging system?](#how-would-you-implement-a-robust-frontend-monitoring-and-logging-system)
- [How would you implement role-based access control (RBAC) in React?](#how-would-you-implement-role-based-access-control-rbac-in-react)
- [How would you optimize a slow React application?](#how-would-you-optimize-a-slow-react-application)
- [How you use decorators in React?](#how-you-use-decorators-in-react)
- [Implement Virtual Scrolling for very large lists.](#implement-virtual-scrolling-for-very-large-lists)
- [Is it possible to use async/await in plain React?](#is-it-possible-to-use-asyncawait-in-plain-react)
- [`React.FC` vs explicit return type -- which is better?](#reactfc-vs-explicit-return-type----which-is-better)
- [Should I learn ES6 before learning ReactJS?](#should-i-learn-es6-before-learning-reactjs)
- [Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?](#situation-you-need-to-keep-the-ui-responsive-during-a-heavy-filter-operation-on-10k-items--how)
- [What are inline conditional expressions?](#what-are-inline-conditional-expressions)
- [What are React Mixins?](#what-are-react-mixins)
- [What are the advantages of React over Vue.js?](#what-are-the-advantages-of-react-over-vuejs)
- [What are the advantages of using React?](#what-are-the-advantages-of-using-react)
- [What are the common folder structures for React?](#what-are-the-common-folder-structures-for-react)
- [What are the drawbacks of MVW pattern?](#what-are-the-drawbacks-of-mvw-pattern)
- [What are the methods invoked during error handling?](#what-are-the-methods-invoked-during-error-handling)
- [What are the popular React-specific linters?](#what-are-the-popular-react-specific-linters)
- [What happened to event pooling?](#what-happened-to-event-pooling)
- [What is a consumer?](#what-is-a-consumer)
- [What is a focus trap?](#what-is-a-focus-trap)
- [What is an updater function? Should an updater function be used in all cases?](#what-is-an-updater-function-should-an-updater-function-be-used-in-all-cases)
- [What is chaos engineering for frontend?](#what-is-chaos-engineering-for-frontend)
- [What is colocation in React?](#what-is-colocation-in-react)
- [What is createAsyncThunk() and why is it used?](#what-is-createasyncthunk-and-why-is-it-used)
- [What is event delegation in React?](#what-is-event-delegation-in-react)
- [What is focus management and why does it matter?](#what-is-focus-management-and-why-does-it-matter)
- [What is prop inversion of control?](#what-is-prop-inversion-of-control)
- [What is React?](#what-is-react)
- [What is React and what problem does it solve?](#what-is-react-and-what-problem-does-it-solve)
- [What is React Dev Tools?](#what-is-react-dev-tools)
- [What is React JS?](#what-is-react-js)
- [What is React proptype array with shape?](#what-is-react-proptype-array-with-shape)
- [What is render hijacking in react?](#what-is-render-hijacking-in-react)
- [What is `TestRenderer` package in React?](#what-is-testrenderer-package-in-react)
- [What is the 'why did you render' library?](#what-is-the-why-did-you-render-library)
- [What is the behavior of uncaught errors in react 16?](#what-is-the-behavior-of-uncaught-errors-in-react-16)
- [What is the benefit of styles modules?](#what-is-the-benefit-of-styles-modules)
- [What is the difference between optimistic and pessimistic updates?](#what-is-the-difference-between-optimistic-and-pessimistic-updates)
- [What is the difference between React and Angular?](#what-is-the-difference-between-react-and-angular)
- [What is the difference between React and ReactDOM?](#what-is-the-difference-between-react-and-reactdom)
- [What is the main purpose of constructor?](#what-is-the-main-purpose-of-constructor)
- [What is the provider pattern?](#what-is-the-provider-pattern)
- [What is the purpose of displayName class property?](#what-is-the-purpose-of-displayname-class-property)
- [What is the purpose of ReactTestUtils package?](#what-is-the-purpose-of-reacttestutils-package)
- [What is the React Compiler (React Forget)?](#what-is-the-react-compiler-react-forget)
- [What is the `react-error-boundary` library?](#what-is-the-react-error-boundary-library)
- [What is the role of Babel in a React project?](#what-is-the-role-of-babel-in-a-react-project)
- [What is the use of `react-dom` package?](#what-is-the-use-of-react-dom-package)
- [What is `useFormStatus`?](#what-is-useformstatus)
- [What is your favorite React stack?](#what-is-your-favorite-react-stack)
- [When did you get stuck while using React, and how did you fix it?](#when-did-you-get-stuck-while-using-react-and-how-did-you-fix-it)
- [When do you need to use refs?](#when-do-you-need-to-use-refs)
- [When to Use](#when-to-use)
- [Why are inline ref callbacks or functions not recommended?](#why-are-inline-ref-callbacks-or-functions-not-recommended)
- [Why do you not required to use inheritance?](#why-do-you-not-required-to-use-inheritance)
- [Why React uses `className` over `class` attribute?](#why-react-uses-classname-over-class-attribute)
- [Why React.js? What problems does it solve?](#why-reactjs-what-problems-does-it-solve)
- [Why ReactDOM is separated from React?](#why-reactdom-is-separated-from-react)
- [❓ What is createSlice() and what does it contain?](#-what-is-createslice-and-what-does-it-contain)

---

## Questions & Answers

## React Architecture, LLD & Scenarios

### Design a Carousel that can handle 1000+ images efficiently.

**Requirements**: Smooth sliding, load images on demand, avoid memory bloat.

**Design**:
- **Virtualization**: Only render current, previous, next slide (buffer). Use `transform: translateX` for sliding.
- **Lazy loading**: Use `IntersectionObserver` or `loading="lazy"` on images. Preload next image.
- **DOM nodes**: Maintain only a few slide elements; reuse them as index changes.
- **Memory**: Unload images that are far away by removing `src` and letting GC collect.
- **Accessibility**: Keyboard arrows, ARIA roles.

---

### Design a Config-Driven Form Renderer using a JSON schema.

**Requirements**: Render forms from a JSON definition, with validation, conditional fields, and custom components.

**Design**:
- **Schema structure**: `{ fields: [{ name, type, label, validation, conditions, options }] }`.
- **Renderer**: Iterate over fields; map `type` to a React component (text input, select, date picker). Use a component registry.
- **Validation**: Integrate with Zod or Yup; generate validation schema dynamically.
- **Conditional fields**: Use `useWatch` (React Hook Form) to listen to values and filter fields based on conditions.
- **State management**: Use `react-hook-form` for form state and validation.
- **Extensibility**: Allow consumers to pass custom field components.

---

### Design a Data Table with sorting, filtering, pagination, and performance trade-offs.

**Requirements**: Table with large datasets, support sorting on columns, filtering, pagination.

**Design**:
- **Data fetching**: Choose client‑side (if dataset manageable) or server‑side (if huge). Server‑side reduces memory but increases network calls.
- **State**: Store current page, page size, sort column/direction, filters.
- **Rendering**: Virtualize rows if many visible at once. Use `React.memo` for rows.
- **Sorting**: On column click, update state; if server‑side, fetch new data; if client‑side, sort array (memoize).
- **Filtering**: Text inputs with debounce; if client‑side, filter array.
- **Trade‑offs**: Client‑side allows instant filtering/sorting but limits data size. Server‑side more scalable but adds latency.

---

### Design a Dropdown / Select component with keyboard navigation and accessibility.

**Requirements**: Custom dropdown that supports selection, keyboard
navigation (arrow keys, Enter, Esc), and ARIA attributes.

**Design**: - **Structure**: Button (trigger) + popup list. Use
`role="combobox"`, `aria-expanded`, `aria-haspopup="listbox"`. -
**Keyboard**: - Arrow down/up: move focus through options, update
`aria-activedescendant`. - Enter/Space: select focused option. - Esc:
close without selection. - **Focus management**: Keep focus on the
trigger; manage active descendant. - **Virtualization** if many
options. - **Outside click**: Use `useRef` and event listener to close
when clicking outside. - **Portal** for popup to avoid overflow
clipping.

**Implementation**:

``` jsx
const Dropdown = ({ options, value, onChange }) => {
  const [isOpen, setIsOpen] = useState(false);
  const [highlightedIndex, setHighlightedIndex] = useState(-1);
  // handle keyboard events
  // render button and list with aria attributes
};
```

------------------------------------------------------------------------

---

### 165. State, Data & UI Systems

------------------------------------------------------------------------

---

---

### Design a file upload component with progress tracking and chunked uploads.

**Requirements**: - Upload large files in chunks. - Show progress per
chunk and overall. - Support pause/resume, retry, and cancellation.

**Design**: - **Chunking**: Split file into chunks of size (e.g., 1MB).
Maintain a chunk queue. - **Upload logic**: Use `fetch` with `PUT` or
`POST` and `Range` headers, or a custom API endpoint that accepts
chunks. For each chunk, send a request with chunk index and total
chunks. - **Progress**: Track per‑chunk status (pending, uploading,
completed). Calculate overall progress (uploaded bytes / total bytes).
Use `XMLHttpRequest` or `fetch` with `upload.onprogress`. - **Resume**:
Store upload state (uploaded chunks) in `localStorage` or IndexedDB;
resume by sending only missing chunks. - **Error handling**: Retry
failed chunks with exponential backoff. - **Abort**: Use
`AbortController` to cancel ongoing requests. - **UI**: Display progress
bar, list of files, cancel/pause buttons.

---

---

### Design a Modal/Dialog component -- focus trapping, accessibility, backdrop behavior.

**Requirements**: Modal that traps focus, is keyboard accessible (ESC to
close), has backdrop, and is accessible.

**Design**: - **Props**: `isOpen`, `onClose`, `title`, `children`,
`closeOnBackdropClick`, `closeOnEsc`. - **Focus trapping**: Use
`useEffect` to move focus to the first focusable element inside modal on
open, and restore focus to the trigger on close. Use a ref to track
focusable elements. - **Accessibility**: Set `role="dialog"`,
`aria-modal="true"`, `aria-labelledby` referencing title. Ensure
backdrop is inert to screen readers. - **Backdrop**: Render a
semi‑transparent overlay; on click, call `onClose` if
`closeOnBackdropClick`. - **Portal**: Render modal at the end of the
`body` using `ReactDOM.createPortal` to avoid stacking issues.

**Implementation**:

``` jsx
const Modal = ({ isOpen, onClose, children }) => {
  useEffect(() => {
    const handleEsc = (e) => { if (e.key === 'Escape') onClose(); };
    if (isOpen) {
      document.addEventListener('keydown', handleEsc);
      // trap focus logic
    }
    return () => document.removeEventListener('keydown', handleEsc);
  }, [isOpen, onClose]);

  if (!isOpen) return null;
  return ReactDOM.createPortal(/* modal JSX */, document.body);
};
```

---

### Design a Modal/Dialog component with focus trapping and accessibility.

**Answer:** Key requirements: (1) Focus trap: when modal opens, focus
moves inside; Tab cycles only within modal; Escape closes. (2)
aria-modal='true', role='dialog', aria-labelledby pointing to title. (3)
Return focus to trigger element on close. (4) Backdrop click to close
(optional). (5) Render in portal (ReactDOM.createPortal) to avoid
z-index and overflow issues. (6) Lock body scroll while open.
Implementation: useEffect to handle keyboard events and focus
management, ref on modal container for focus trap logic.

---

---

### Design a Notification / Toast system with queueing, auto-dismiss, and priority.

**Requirements**: Manage multiple toasts; auto‑dismiss after timeout; queue when limit reached; support priorities (error stays longer, etc.)

**Design**:
- **Store**: Use a state array of notifications, each with id, message, type, priority, timeout.
- **Queue**: When adding, if current visible count >= max, push to queue. On dismiss, show next from queue.
- **Auto‑dismiss**: `setTimeout` per notification; clear on manual close. Higher priority = longer duration.
- **Positioning**: Use portal to render fixed container.
- **API**: `toast.success()`, `toast.error()`, etc., returning dismiss function.

```jsx
const ToastContainer = () => {
  const [notifications, setNotifications] = useState([]);
  const addToast = (toast) => { /* manage queue */ };
  const removeToast = (id) => { /* remove from array and trigger next */ };
  // render list of Toasts
};
```

---

### Design a Posts with Comments system – how do you manage deeply nested data?

**Requirements**: Display posts, each with comments, comments may have nested replies.

**Design**:
- **Data structure**: Use normalized state (e.g., entities for posts, users, comments). Store comments as map with parent references. Build tree on demand.
- **State management**: Redux Toolkit with `createEntityAdapter` for normalized data. Or use React Query for server state and local state for UI.
- **Rendering**: Recursive component for comment tree. Use memoization to avoid re‑renders on deep trees.
- **Optimistic updates**: When adding comment, update local state immediately, then sync with server.
- **Performance**: Use virtual scrolling for long comment threads.

---

### Design a Progress Bar / Stepper with configurable steps and validation logic.

**Requirements**: Show a multi‑step process (e.g., form steps). Each
step can have validation before proceeding. Visual indication of
completed/active/pending steps.

**Design**: - **Props**: `steps` array (each with label, component),
`validateStep` function per step, `onComplete`. - **State**:
`currentStep`, `stepData` (collected data). - **Behavior**: When user
clicks "Next", run validation; if passes, move to next step. When
"Previous", go back. On last step, call `onComplete`. - **Styling**: Use
CSS classes for step indicators (completed, active, pending). Use `flex`
or `grid`.

**Implementation**:

``` jsx
const Stepper = ({ steps, onComplete }) => {
  const [current, setCurrent] = useState(0);
  const [data, setData] = useState({});
  const handleNext = async () => {
    const isValid = await steps[current].validate?.(data);
    if (isValid !== false) {
      if (current === steps.length - 1) onComplete(data);
      else setCurrent(prev => prev + 1);
    }
  };
  // render step content and navigation
};
```

---

### Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.

**Requirements**: Input with suggestions, async fetching, prevent out‑of‑order responses.

**Design**:
- **Debouncing**: 300ms delay; cancel previous timer.
- **Caching**: Map (key = query) to suggestions; check cache before fetch.
- **Race condition**: Use request ID or `AbortController`. Each new request aborts previous.
- **Accessibility**: ARIA combobox, listbox, option. Keyboard navigation.
- **Highlighting**: Use `dangerouslySetInnerHTML` or regex replace to highlight matched text.

---

### Performance & Optimization

---

### Design a Star Rating component – how would you support half or partial ratings?

**Requirements**: Display a star rating (1‑5). Support whole, half, or custom fractional values.

**Design**:
- **Props**: `value` (number), `onChange` (for interactive), `precision` (0.5 or 0.1), `size`, `readOnly`.
- **Implementation**: Render 5 stars, each star can be partially filled using a technique like:
  - Two overlapping elements (a full star and a half star) with clip‑path or width percentage.
  - SVG with gradient or mask.
- **Interaction**: On click, determine mouse position within the star to compute fractional value.
- **Accessibility**: Use `role="slider"` with `aria-valuenow`, keyboard support (arrow keys).

**Example approach**:
```jsx
const Star = ({ filled, fraction, onClick }) => {
  // fraction: 0 (empty), 0.5 (half), 1 (full)
  // Use background image or SVG with linear gradient
};
```

---

### Design a state management solution for a complex analytics/dashboard app.

**Requirements**: Real‑time data, multiple widgets, filters that affect
many components.

**Design**: - **Store**: Redux Toolkit with slices for: - Filters
(global time range, date picker) - Widget data (each widget's data,
loading, error) - User preferences - **Normalization**: Use
`createEntityAdapter` for time‑series data. - **Async**:
`createAsyncThunk` for API calls; caching with `selectors` that return
memoized data. - **WebSocket integration**: Middleware that dispatches
actions on incoming messages. - **Performance**: Use `useSelector` with
shallow equality or memoized selectors. Use `React.memo` for widgets. -
**Derived data**: Use Reselect to compute aggregated metrics only when
raw data changes.

------------------------------------------------------------------------

---

---

### Design a state management solution for a complex app.

**Requirements**: - Handle asynchronous data, caching, optimistic
updates. - Manage shared state across many features. - Ensure
performance.

**Design**: - **Global state**: Use Redux Toolkit with slices per
feature. Use `createEntityAdapter` for normalized data. - **Async
logic**: `createAsyncThunk` for API calls; handle loading/error
states. - **Caching**: Implement a cache layer with expiration; use
selectors to retrieve cached data. - **Optimistic updates**: Update the
store optimistically on user actions; if the request fails, rollback
using the previous state snapshot. - **Derived state**: Use
`createSelector` (Reselect) for memoized derived data. - **Cross‑slice
communication**: Use `extraReducers` to listen to actions from other
slices. - **Performance**: Use selectors that compute only when needed.
Use `React.memo` and `useCallback` to avoid re‑renders.

------------------------------------------------------------------------

---

---

### Design a Tabs component that supports dynamic content loading and async data.

**Requirements**: Tabs should be able to load content dynamically (e.g.,
each tab's content may be fetched from an API when selected). Support
async loading states.

**Design**: - **Props**: `tabs` array (each with label, content load
function or component). - **State**: `activeTab` index, `loading` per
tab, `content` cache per tab. - **Behavior**: When a tab becomes active,
if its content hasn't been loaded, trigger async load and show loading
spinner. - **Accessibility**: Use ARIA roles (`tablist`, `tab`,
`tabpanel`). Handle keyboard navigation (arrow keys). - **Performance**:
Cache loaded content to avoid re‑fetching.

**Implementation**:

``` jsx
const Tabs = ({ tabs }) => {
  const [active, setActive] = useState(0);
  const [contentCache, setContentCache] = useState({});
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    if (!contentCache[active] && tabs[active].load) {
      setLoading(true);
      tabs[active].load().then(data => {
        setContentCache(prev => ({ ...prev, [active]: data }));
        setLoading(false);
      });
    }
  }, [active, contentCache, tabs]);

  const activeContent = contentCache[active] ?? (tabs[active].content || <div>No content</div>);
  return ( /* JSX with tab buttons and panel */ );
};
```

------------------------------------------------------------------------

---

---

### Design a theme-able, extensible component library.

**Requirements**: - Support light/dark themes, custom brand colors. -
Allow consumers to override styles. - Be extensible with new components.

**Design**: - **Styling approach**: Use CSS‑in‑JS (emotion,
styled‑components) with theming via `ThemeProvider` or use CSS variables
for dynamic theming. - **Base styles**: Provide a set of design tokens
(colors, spacing, typography) as CSS custom properties. - **Theme
object**: Define theme object with `colors`, `spacing`, etc. Use React
Context to pass theme. - **Component API**: Use polymorphic `as` prop to
allow rendering as different elements. Provide variant props
(`variant="primary"`). - **Extensibility**: Allow consumers to pass
custom class names and `style` props. Use composition over
inheritance. - **Documentation**: Provide Storybook for interactive
documentation. - **Tree shaking**: Use barrel exports but ensure proper
configuration for bundlers to only include used components.

---

---

### Design a Todo List application with add, edit, delete, and mark‑as‑complete.

**Requirements**: Manage a list of todos; each todo has an id, text, and
completed flag. Support adding, editing, deleting, and toggling
completion.

**Design considerations**: - **State**: Use `useState` (or `useReducer`
for complex updates) to store todos array. - **Edit mode**: Track which
todo is being edited (or use a separate edit field). -
**Accessibility**: Keyboard navigation, focus management. -
**Persistence**: Optionally store in `localStorage`. - **Performance**:
Use `useCallback` for handlers, `React.memo` for each todo item to avoid
unnecessary re‑renders.

**Implementation skeleton**:

``` jsx
const TodoApp = () => {
  const [todos, setTodos] = useState([]);
  const [newTodo, setNewTodo] = useState('');
  const [editId, setEditId] = useState(null);
  const [editText, setEditText] = useState('');

  const addTodo = () => { /* add new todo */ };
  const toggleTodo = (id) => { /* toggle completed */ };
  const deleteTodo = (id) => { /* delete todo */ };
  const startEdit = (todo) => { /* set editId, editText */ };
  const saveEdit = () => { /* update todo text */ };

  return ( /* JSX with input, list of TodoItem components */ );
};
```

---

### Design a Toggle / Switch component -- controlled vs uncontrolled patterns.

**Requirements**: A switch that can be controlled (value passed from
parent) or uncontrolled (internal state). Support `onChange` callback.

**Design**: - **Uncontrolled**: Internal `useState`, initial value from
`defaultChecked`. - **Controlled**: Parent manages value via `checked`
prop; component becomes read‑only to parent updates. - **Both
patterns**: Check if `checked` prop is defined; if yes, use controlled;
otherwise use internal state. - **Accessibility**: `role="switch"`,
`aria-checked`, keyboard support (Space/Enter). - **Styling**: Use CSS
pseudo‑elements for slider effect.

``` jsx
const Toggle = ({ checked: controlledChecked, defaultChecked = false, onChange }) => {
  const [internalChecked, setInternalChecked] = useState(defaultChecked);
  const isControlled = controlledChecked !== undefined;
  const current = isControlled ? controlledChecked : internalChecked;

  const handleToggle = () => {
    const newValue = !current;
    if (!isControlled) setInternalChecked(newValue);
    onChange?.(newValue);
  };
  return <button role="switch" aria-checked={current} onClick={handleToggle} />;
};
```

---

### Design an Accordion component -- should it allow single or multiple panels open? Why?

**Requirements**: Accordion collapses/expands sections. Decide on
behavior (single open at a time vs. multiple open).

**Design**: - **Props**: `allowMultiple` boolean, `children` (array of
panel items), optionally `defaultOpen` indices. - **State**: Store
`openIndices` (array if multiple, single index if single). - **Why
choose single vs multiple?** - **Single** (default) is simpler and keeps
UI tidy; useful for limited vertical space or step‑by‑step flows. -
**Multiple** gives user flexibility; good for settings panels where
users may want to see several sections at once.

**Implementation**:

``` jsx
const Accordion = ({ allowMultiple = false, children }) => {
  const [open, setOpen] = useState([]); // array of indices

  const toggle = (index) => {
    if (allowMultiple) {
      setOpen(prev => prev.includes(index) ? prev.filter(i => i !== index) : [...prev, index]);
    } else {
      setOpen(prev => prev[0] === index ? [] : [index]);
    }
  };
  return ( /* render children with open state */ );
};
```

------------------------------------------------------------------------

---

---

### Design an E-commerce Filter system (price, category, rating) with scalable state.

**Answer:** State shape: { filters: { category: \[\], priceRange: \[0,
1000\], rating: 0 }, sort: 'price-asc', page: 1 }. Keep filters in URL
query params --- enables shareable links, browser back/forward
navigation. Derived state: filteredProducts = useMemo(filterFn,
\[products, filters\]) --- never store filtered results in state. Each
filter updates URL, URL drives state (single source of truth). Debounce
price range slider to avoid excessive filtering. Server-side filtering
for large catalogs.

---

### 162. Controlled vs uncontrolled components -- explain with examples.

-   **Controlled component**: Form input whose value is controlled by
    React state. The input's value is set via `value` prop and updates
    via `onChange`. React is the single source of truth.

    ``` jsx
    const [value, setValue] = useState('');
    <input value={value} onChange={e => setValue(e.target.value)} />
    ```

-   **Uncontrolled component**: The DOM itself manages the input state.
    You access the current value via a ref (`useRef`).

    ``` jsx
    const inputRef = useRef();
    <input ref={inputRef} />
    // later: inputRef.current.value
    ```

---

---

### Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.

**Requirements**: - Multiple filter facets that update the product
list. - Efficient state updates without causing excessive re‑renders. -
Pagination or infinite scroll.

**Design**: - **State**: Use a global store (Redux or Zustand) for
filters and product list. Filters: price range, category (multi‑select),
rating, etc. - **Filter logic**: Combine filters into a query object; on
filter change, update the query and fetch new products. Debounce price
slider input. - **Caching**: Cache product pages based on filter query
to avoid redundant requests. - **UI performance**: Use `React.memo` for
product cards; use `useSelector` with memoized selectors (Reselect) to
derive filtered products only when relevant filters change. -
**Pagination**: Implement either offset‑based pagination or
cursor‑based; load more on scroll or via "Load More" button. - **URL
synchronization**: Keep filters in URL query parameters for shareability
and persistence on refresh.

---

---

### How do you design a reusable button component?

Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type`
props. Use TypeScript to type them. Forward refs for DOM access. Avoid
hardcoding styles -- use class variants or a styling system. Compose
with an icon slot.

------------------------------------------------------------------------

---

---

### How do you handle real-time updates efficiently in React?

-   Use WebSockets or Server‑Sent Events (SSE) for pushing updates.
-   Manage connections with custom hooks that handle lifecycle (connect
    on mount, disconnect on unmount).
-   Use `useRef` to store the connection object.
-   Throttle or debounce UI updates if they are frequent.
-   Use `useReducer` or state management to batch updates.
-   Leverage `React.memo` and careful component structure to avoid
    re‑rendering large parts of the UI.
-   Use virtualization for large lists.

------------------------------------------------------------------------

---

---

### How do you integrate feature flags (LaunchDarkly, etc.) in React ecosystems?

**Goal**: Control feature rollout, A/B testing, and safe releases.

**Integration**:

1.  **Provider** -- Wrap the app with a feature flag provider (e.g.,
    `LaunchDarklyProvider`). Initialize flags early, usually in the root
    component or a higher‑order component.

2.  **Context / Hooks** -- Use a hook like `useFeatureFlag(flagKey)`
    that returns the current variation. This can be used in components
    to conditionally render or execute code.

3.  **Performance** -- Load flags asynchronously; use a loading state
    (e.g., show a skeleton) until flags are ready, especially for
    critical flags that affect layout.

4.  **Server‑side** -- For Next.js, fetch flags in `getServerSideProps`
    or `getStaticProps` to avoid layout shifts. Use LaunchDarkly's
    server‑side SDK to evaluate flags on the server.

5.  **Testing** -- Mock feature flags in unit tests. In end‑to‑end
    tests, set flags via API or by injecting cookies.

6.  **Cleanup** -- Once a feature is fully rolled out, remove the flag
    code to avoid clutter. Use the SDK's ability to archive flags.

**Example**: \> "We used LaunchDarkly with React. We wrapped our app in
a provider that initialized flags from localStorage first (for caching)
then streamed updates via WebSocket. We created a `useFlag` hook that
returned the flag value and automatically re‑rendered when the flag
changed. For A/B tests, we used the `variation` to track analytics
events. In Next.js, we fetched flags on the server using the Node SDK
and passed them to the page via props, ensuring no layout shift."

------------------------------------------------------------------------

---

---

### How do you structure a large-scale React application across multiple teams?

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

---

### How does React Fiber architecture change rendering?

React Fiber (introduced in React 16) is a complete rewrite of the reconciliation engine. It enables **incremental rendering**, splitting work into chunks and prioritizing updates (e.g., user input over data fetching). Fiber makes React capable of:
    - Pausing, aborting, or reusing work.
    - Assigning priorities to different types of updates.
    - Supporting concurrent rendering and Suspense.

---

### How would you architect a React app for a team of 20 developers?

Feature-based folder structure. Shared component library (with
Storybook). TypeScript throughout. Agreed state management strategy
(React Query for server, Zustand for client global). ESLint + Prettier +
husky pre-commit hooks. Module boundaries enforced by Nx or ESLint
import rules.

------------------------------------------------------------------------

---

---

### How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue‑green deployments?

A robust pipeline enables safe, gradual rollouts.

1. **Build & Test** (PR / main)  
   - Lint, type check, unit/integration tests.  
   - Build the application (generating static assets).  
   - Run contract tests, visual regression tests.  
   - Upload source maps to error tracking.

2. **Deploy to Staging**  
   - Deploy to a staging environment (e.g., using a Kubernetes cluster or static hosting).  
   - Run end‑to‑end tests against staging.  
   - Perform performance testing (Lighthouse CI).

3. **Canary Deployment**  
   - Deploy new version to a small percentage of production traffic (e.g., 1–5%).  
   - Monitor error rates, latency, and Core Web Vitals.  
   - Use feature flags to control exposure further.  
   - If metrics stay within thresholds, gradually increase traffic.

4. **Blue‑Green Deployment**  
   - Maintain two identical environments: blue (current) and green (new).  
   - Deploy new version to green, run smoke tests.  
   - Switch router (load balancer) to green instantly.  
   - If issues arise, switch back to blue.  

5. **Full Production Rollout**  
   - After canary passes, deploy to all pods (rolling update).  
   - Invalidate CDN caches if needed (use versioned asset names to avoid stale content).  
   - Post‑deployment monitoring for 30 minutes, then close the canary.

**Tools**: GitHub Actions/GitLab CI, ArgoCD for Kubernetes, AWS CodeDeploy for blue‑green, LaunchDarkly for feature flags.

---

---

### How would you design a design system in React?

Separate npm package. Primitive components (Button, Input, Text).
Compound components for complex widgets. Design tokens (CSS variables).
Storybook for documentation. Chromatic for visual regression. Semantic
versioning with changelogs. TypeScript for consumer safety.

------------------------------------------------------------------------

*225 questions across 18 sections. Happy studying! ⚛️*

------------------------------------------------------------------------

---

### 237. Given users = \[{id:1, active:true}, {id:2, active:false}\], find all active user IDs.

``` javascript
// Clean array
const activeIds = users
  .filter(u => u.active)
  .map(u => u.id); // [1]

// With nulls/empty objects: [{id:1, active:true}, null, {}, {id:2}]
const activeIdsSafe = users
  .filter(u => u && u.id && u.active)
  .map(u => u.id);
```

**Answer:** The defensive version handles nulls, empty objects, and
missing properties. Always validate data before accessing nested
properties in real-world scenarios.

---

---

### How would you design a reusable component library for a large team?

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

------------------------------------------------------------------------

---

---

### How would you design a state management solution for a complex analytics/dashboard app?

For a dashboard app with: - Real‑time data (WebSockets) - Multiple
widgets that can be individually refreshed - Filters that affect many
widgets - Large datasets (need virtualization)

Approach: 1. Use Redux Toolkit for global state (filters, user settings,
notifications). 2. Use `createEntityAdapter` for normalized data (e.g.,
metrics, widgets). 3. Use `createAsyncThunk` for API calls with
cancellation support (AbortController). 4. For real‑time updates, use a
custom middleware to listen to WebSocket messages and dispatch actions.
5. Use `useSelector` with memoized selectors (Reselect) to avoid
re‑renders. 6. For widget‑specific state (e.g., expanded/collapsed),
keep it locally in the widget component to avoid global re‑renders. 7.
Leverage React.memo for widget components that receive stable props. 8.
Use Suspense and lazy loading for heavy dashboard sections.

This combines the predictability of Redux with localized state for
performance.

---

---

### How would you design a theme-able, extensible component library?

**Design**: - **Styling**: Use CSS custom properties (variables) for
theming. Provide default theme values. - **Theme provider**: Use React
Context to pass a theme object (colors, spacing, typography) to all
components. - **Component API**: Support `className` and `style` props
for overrides. Use `polymorphic` components (`as` prop). -
**Extensibility**: Expose base components that can be composed. Allow
consumers to pass custom render props. - **Documentation**: Storybook
with interactive examples and theme switching. - **Tree shaking**: Use
ES modules and named exports; configure bundler to eliminate unused
components.

------------------------------------------------------------------------

---

---

### How would you design component structure for scalability in a production-level app?

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

------------------------------------------------------------------------

---

---

### How would you design SSR/SSG/hydration strategy for a React app?

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

------------------------------------------------------------------------

---

---

### How would you handle real-time updates in a React application efficiently?

Options by use case: (1) WebSockets: bidirectional, persistent
connection --- best for chat, collaborative editing, live cursors. Use
socket.io or native WebSocket API. (2) Server-Sent Events (SSE): server
→ client only, uses HTTP --- best for live feeds, notifications, stock
prices. (3) Long polling: fallback for environments that block
WebSockets. React integration: connect in useEffect, cleanup on unmount,
update state with incoming data, use Redux or Zustand for normalization.
Optimization: batch rapid updates with throttle, use Immer for immutable
updates.

------------------------------------------------------------------------

---

---

### How would you structure a large-scale React application?

Feature-based folder structure: src/features/auth/,
src/features/dashboard/ etc. Each feature contains: components/, hooks/,
slices/, api/, types/. Shared: src/components/ui/ (design system),
src/hooks/ (shared hooks), src/utils/, src/api/ (base client). Key
decisions: (1) Route-level code splitting for each feature. (2) Barrel
exports (index.ts) for clean imports. (3) Absolute imports configured
with path aliases. (4) Strict TypeScript throughout. (5) Global state
only for truly global data --- prefer local state + context for feature
state.

---

---

### In a large-scale application, components are re-rendering unnecessarily — how would you identify and fix performance issues?

**Answer:**  
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

---

---

### Real-time Updates: How to handle real-time updates efficiently in React?

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

------------------------------------------------------------------------

---

---

### Redux vs Context API vs Zustand – how do you decide in a large-scale application?

| | Redux | Context API | Zustand |
|---|-------|-------------|---------|
| **Use case** | Large apps, complex state, frequent updates | Simple state, medium nesting, low update frequency | Small‑medium apps, simple API, minimal boilerplate |
| **Performance** | Optimized with selectors, middleware | Can cause re‑renders; requires careful splitting | Very performant, minimal re‑renders |
| **Boilerplate** | Higher (but RTK reduces it) | Low | Very low |
| **Tooling** | Excellent (DevTools) | Basic | Good |
| **Learning curve** | Steeper | Easy | Easy |

**Decision**: For large‑scale apps with many features, complex async logic, and need for time‑travel debugging, Redux (with RTK) is a solid choice. If you need a lighter alternative with good performance and less boilerplate, Zustand is popular. Context is best for static or low‑frequency updates (e.g., theme, localization) and not recommended for high‑frequency state.

---

### Scenario: Context API causes frequent re‑renders – why and how to fix?

**Why**: The context value is an object that gets re‑created on every render of the provider, causing all consumers to re‑render. Even if the actual data hasn’t changed, the reference changed.

    **Fixes**:
    - Memoize the context value with `useMemo` to keep the same object unless dependencies change.
    - Split contexts into smaller, focused contexts so consumers only subscribe to what they need.
    - Use state management libraries (like Redux) that allow selective subscriptions.
    - Use `useContextSelector` or similar pattern if available.

---

### What is Fiber architecture in React?

React Fiber (introduced in React 16) is a complete rewrite of the core
reconciliation engine. It breaks rendering work into small units
(fibers) that can be paused, prioritized, aborted, or restarted. This
enables: concurrent rendering, time-slicing, Suspense, and better
scheduling. Each fiber is a JS object representing a component instance
with links to parent, child, and sibling fibers. The work-loop processes
fibers incrementally, yielding to the browser between frames to maintain
60fps.

------------------------------------------------------------------------

---

---

### What is the flux architecture pattern?

Unidirectional data flow: Action → Dispatcher → Store → View → (user interaction) → Action. Redux is inspired by Flux. Data always flows one way, making state changes predictable and traceable.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### You are building a real-time dashboard --- how would you manage frequent state updates without affecting performance?

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

------------------------------------------------------------------------

---

---

### ❓ What is the difference between Redux, Context, and Zustand for large-scale apps?

**Answer:** Redux Toolkit: most mature, excellent DevTools, enforces strict patterns, good for teams with complex state machines. Best when: large team, complex async flows, need for time-travel debugging. Context API: built-in, zero config, fine for infrequent updates. Problems with high-frequency updates (every consumer re-renders on any change). Zustand: minimal boilerplate, fast, component only re-renders on subscribed slice change, easy async. Best when: Redux feels too heavy but Context too limited. Decision matrix: Context for themes/auth, Zustand for medium complexity, RTK for enterprise.

---

## React Routing, Forms & Data Fetching

### Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.

**Route‑based code splitting** – using `React.lazy` with `Suspense`:

```jsx
const Home = React.lazy(() => import('./routes/Home'));
const About = React.lazy(() => import('./routes/About'));

function App() {
  return (
    <Suspense fallback={<Loading />}>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Suspense>
  );
}
```

**Component‑level lazy loading** – for heavy components like modals, charts, or editors:

```jsx
const HeavyChart = React.lazy(() => import('./HeavyChart'));
// then use it with Suspense
```

**Pre‑loading** – start loading a chunk before navigation using `webpackPrefetch`:

```jsx
import(/* webpackPrefetch: true */ './HeavyComponent');
```

**Pre‑fetching on hover** – trigger dynamic import when user hovers over a link.

**Bundler configuration** – ensure chunks are named and optimized (e.g., Webpack’s `splitChunks`).

---

---

### How do you do form validation in React without a library?

Track values and errors in state. Validate in `onChange` (real-time) or
`onBlur` (on leave) or `onSubmit`. Set error messages in state and
display them. For complex forms, a library is usually worth the
dependency.

------------------------------------------------------------------------

---

---

### How do you programmatically navigate using React Router v4?

There are three different ways to achieve programmatic routing/navigation within components.

        1.  **Using the `withRouter()` higher-order function:**

            The `withRouter()` higher-order function will inject the history object as a prop of the component. This object provides `push()` and `replace()` methods to avoid the usage of context.

            ```jsx harmony
            import { withRouter } from "react-router-dom"; // this also works with 'react-router-native'

            const Button = withRouter(({ history }) => (
              <button
                type="button"
                onClick={() => {
                  history.push("/new-location");
                }}
              >
                {"Click Me!"}
              </button>
            ));
            ```

        2.  **Using `<Route>` component and render props pattern:**

            The `<Route>` component passes the same props as `withRouter()`, so you will be able to access the history methods through the history prop.

            ```jsx harmony
            import { Route } from "react-router-dom";

            const Button = () => (
              <Route
                render={({ history }) => (
                  <button
                    type="button"
                    onClick={() => {
                      history.push("/new-location");
                    }}
                  >
                    {"Click Me!"}
                  </button>
                )}
              />
            );
            ```

        3.  **Using context:**

            This option is not recommended and treated as unstable API.

            ```jsx harmony
            const Button = (props, context) => (
              <button
                type="button"
                onClick={() => {
                  context.history.push("/new-location");
                }}
              >
                {"Click Me!"}
              </button>
            );

            Button.contextTypes = {
              history: React.PropTypes.shape({
                push: React.PropTypes.func.isRequired,
              }),
            };
            ```

    ****

---

### How does new JSX transform different from old transform?

The new JSX transform doesn’t require React to be in scope. i.e, You don't need to import React package for simple scenarios.

Let's take an example to look at the main differences between the old and the new transform,

**Old Transform:**


```
import React from 'react';

function App() {
  return <h1>Good morning!!</h1>;
}

```

Now JSX transform convert the above code into regular JavaScript as below,


```
import React from 'react';

function App() {
  return React.createElement('h1', null, 'Good morning!!');
}

```

**New Transform:**

The new JSX transform doesn't require any React imports


```
function App() {
  return <h1>Good morning!!</h1>;
}

```

Under the hood JSX transform compiles to below code


```
import { jsx as _jsx } from 'react/jsx-runtime';

function App() {
  return _jsx('h1', { children: 'Good morning!!' });
}

```

**Note:** You still need to import React to use Hooks.

---

### How is the new JSX transform different from old transform??

The new JSX transform doesn't require React to be in scope. i.e, You
don't need to import React package for simple scenarios.

     Let's take an example to look at the main differences between the old and the new transform,

     **Old Transform:**

     ```js
     import React from "react";

     function App() {
       return <h1>Good morning!!</h1>;
     }
     ```

     Now JSX transform convert the above code into regular JavaScript as below,

     ```js
     import React from "react";

     function App() {
       return React.createElement("h1", null, "Good morning!!");
     }
     ```

     **New Transform:**

     The new JSX transform doesn't require any React imports

     ```js
     function App() {
       return <h1>Good morning!!</h1>;
     }
     ```

     Under the hood JSX transform compiles to below code

     ```js
     import { jsx as _jsx } from "react/jsx-runtime";

     function App() {
       return _jsx("h1", { children: "Good morning!!" });
     }
     ```

     **Note:** You still need to import React to use Hooks.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How React Router is different from history library?

React Router is a wrapper around the `history` library which handles interaction with the browser's `window.history` with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node.

    ****

---

### How to add Google Analytics for React Router?

Add a listener on the `history` object to record each page view:

        ```javascript
        history.listen(function (location) {
          window.ga("set", "page", location.pathname + location.search);
          window.ga("send", "pageview", location.pathname + location.search);
        });
        ```

    ****

---

### How to fetch data with React Hooks?

The effect hook called `useEffect` is used to fetch the data with axios from the API and to set the data in the local state of the component with the state hook’s update function.

Let's take an example in which it fetches list of react articles from the API


```
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function App() {
  const [data, setData] = useState({ hits: [] });

  useEffect(async () => {
    const result = await axios('http://hn.algolia.com/api/v1/search?query=react');

    setData(result.data);
  }, []);

  return (
    <ul>
      {data.hits.map((item) => (
        <li key={item.objectID}>
          <a href={item.url}>{item.title}</a>
        </li>
      ))}
    </ul>
  );
}

export default App;

```

Remember we provided an empty array as second argument to the effect hook to avoid activating it on component updates but only for the mounting of the component. i.e, It fetches only for component mount.

[

---

### How to get history on React Router v4?

Below are the list of steps to get history object on React Router v4,

        1.  Create a module that exports a `history` object and import this module across the project.

            For example, create `history.js` file:

            ```javascript
            import { createBrowserHistory } from "history";

            export default createBrowserHistory({
              /* pass a configuration object here if needed */
            });
            ```

        2.  You should use the `<Router>` component instead of built-in routers. Import the above `history.js` inside `index.js` file:

            ```jsx harmony
            import { Router } from "react-router-dom";
            import history from "./history";
            import App from "./App";

            ReactDOM.render(
              <Router history={history}>
                <App />
              </Router>,
              holder
            );
            ```

        3.  You can also use push method of `history` object similar to built-in history object:

            ```javascript
            // some-other-file.js
            import history from "./history";

            history.push("/go-here");
            ```

    ****

---

### How to get query parameters in React Router v4?

The ability to parse query strings was taken out of React Router v4 because there have been user requests over the years to support different implementation. So the decision has been given to users to choose the implementation they like. The recommended approach is to use query strings library.

        ```javascript
        const queryString = require("query-string");
        const parsed = queryString.parse(props.location.search);
        ```

        You can also use `URLSearchParams` if you want something native:

        ```javascript
        const params = new URLSearchParams(props.location.search);
        const foo = params.get("name");
        ```

        You should use a _polyfill_ for IE11.

    ****

---

### How to pass data between sibling components using React router?

Passing data between sibling components of React is possible using React Router with the help of `history.push` and `match.params`.

    In the code given below, we have a Parent component` AppDemo.js` and have two Child Components `HomePage` and `AboutPage`. Everything is kept inside a Router by using React-router Route. It is also having a route for `/about/{params}` where we will pass the data.

import React, { Component } from 'react'; class AppDemo extends
Component { render() { return ( `<Router>`{=html}
```{=html}
<div className="AppDemo">
```
      <ul>
        <li>
          <NavLink to="/"  activeStyle={{ color:'blue' }}>Home</NavLink>
        </li>
        <li>
          <NavLink to="/about"  activeStyle={{ color:'blue' }}>About

`</NavLink>`{=html}
```{=html}
</li>
```
```{=html}
</ul>
```
             <Route path="/about/:aboutId" component={AboutPage} />
             <Route path="/about" component={AboutPage} />
             <Route path="/" component={HomePage} />
      </div>
    </Router>

); } } export default AppDemo;


    The HomePage is a functional component with a button. On button click, we are using `props.history.push(‘/about/’ + data)` to programmatically navigate into `/about/data`.

export default function HomePage(props) { const handleClick = (data) =\>
{ props.history.push('/about/' + data); } return (

<div>

    <button onClick={() => handleClick('DemoButton')}>To About</button>

</div>

) }


    Also, the functional component AboutPage will obtain the data passed by `props.match.params.aboutId`.

export default function AboutPage(props) {
if(!props.match.params.aboutId) { return

<div>

No Data Yet

</div>

} return (

<div>

    {`Data obtained from HomePage is ${props.match.params.aboutId}`}

</div>

) }


    After button click in the HomePage the page will look like below:

---

### How to pass params to `history.push` method in React Router v4?

While navigating you can pass props to the `history` object:

        ```javascript
        this.props.history.push({
          pathname: "/template",
          search: "?name=sudheer",
          state: { detail: response.data },
        });
        ```

        The `search` property is used to pass query params in `push()` method.

    ****

---

### How to perform automatic redirect after login?

The react-router package will provide the component `<Redirect>` in React Router. Rendering of a `<Redirect>` component will navigate to a newer location. In the history stack, the current location will be overridden by the new location just like the server-side redirects.

import React, { Component } from 'react' import { Redirect } from
'react-router' export default class LoginDemoComponent extends Component
{ render() { if (this.state.isLoggedIn === true) { return
`<Redirect to="/your/redirect/page" />`{=html} } else { return

<div>

{'Please complete login'}

</div>

} } }


    ### Conclusion

    React has got more popularity among the top IT companies like Facebook, PayPal, Instagram, Uber, etc., around the world especially in India. Hooks is becoming a trend in the React community as it removes the state management complexities.

    This article includes the most frequently asked ReactJS and React Hooks interview questions and answers that will help you in interview preparations. Also, remember that your success during the interview is not all about your technical skills, it will also be based on your state of mind and the good impression that you will make at first. All the best!!

    ### Useful References and Resources:

    - "Beginning React with Hooks " book by Greg Lim
    - “Learn React Hooks” book by Daniel Bugl
    - [Node.js vs React.js](https://www.interviewbit.com/blog/node-js-vs-react-js/)
    - [React Native Interview Questions](https://www.interviewbit.com/react-native-interview-questions/)
    - [Angular Interview Questions and Answers](https://www.interviewbit.com/angular-interview-questions/)

---

### What are route actions in React Router?

Functions that handle form submissions and mutations on a route. Called
when a Form is submitted to that route. Work with React Router's data
APIs for full progressive enhancement.

------------------------------------------------------------------------

---

---

### What are route loaders in React Router v6.4+?

Functions defined on routes that fetch data before the component
renders. The component receives data via `useLoaderData()`. Eliminates
loading spinners inside components -- data is ready before render.

------------------------------------------------------------------------

---

---

### What are the advantages of formik over redux form library?

Below are the main reasons to recommend formik over redux form library,

1. The form state is inherently short-term and local, so tracking it in Redux (or any kind of Flux library) is unnecessary.
2. Redux-Form calls your entire top-level Redux reducer multiple times ON EVERY SINGLE KEYSTROKE. This way it increases input latency for large apps.
3. Redux-Form is 22.5 kB minified gzipped whereas Formik is 12.7 kB

[

---

### What are the benefits of React Router V4?

Below are the main benefits of React Router V4 module,

         1. In React Router v4(version 4), the API is completely about components. A router can be visualized as a single component(`<BrowserRouter>`) which wraps specific child router components(`<Route>`).
         2. You don't need to manually set history. The router module will take care history by wrapping routes with `<BrowserRouter>` component.
         3. The application size is reduced by adding only the specific router module(Web, core, or native)

    ****

---

### What are the patterns for data fetching in React?

1.  `useEffect` + fetch (basic)
2.  Custom `useFetch` hook
3.  React Query / SWR (recommended for server state)
4.  Route loaders (React Router v6.4+)
5.  Server Components with async/await (Next.js App Router)

------------------------------------------------------------------------

---

---

### What are the `<Router>` components of React Router v6?

React Router v6 provides below 4 `<Router>` components:

        1.  `<BrowserRouter>`:Uses the HTML5 history API for standard web apps.
        2.  `<HashRouter>`:Uses hash-based routing for static servers.
        3.  `<MemoryRouter>`:Uses in-memory routing for testing and non-browser environments.
        4.  `<StaticRouter>`:Provides static routing for server-side rendering (SSR).

        The above components will create _browser_, _hash_, _memory_ and _static_ history instances. React Router v6 makes the properties and methods of the `history` instance associated with your router available through the context in the `router` object.

    ****

---

### What is Formik?

A form library providing values, errors, touched state, and handlers. Uses controlled components. Simpler API for moderate forms. Yup integration for schema validation. Slower than React Hook Form for large forms.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is optimistic mutation in React Query?

In `useMutation`'s `onMutate`, update the cache optimistically. In
`onError`, roll back via context passed from `onMutate`. In `onSettled`,
invalidate/refetch to sync with server. Provides instant UI feedback.

------------------------------------------------------------------------

---

---

### What is React Hook Form and why is it popular?

Register inputs with `register()`, validation via resolver (Yup, Zod).
Uncontrolled under the hood -- minimal re-renders (only on submit or
validated field change). Better performance than Formik for large forms.

------------------------------------------------------------------------

---

---

### What is React Query (TanStack Query)?

A library for fetching, caching, synchronizing, and updating server
state. Provides `useQuery` (fetch), `useMutation`
(create/update/delete), automatic background refetching, cache
invalidation, and stale-while-revalidate.

------------------------------------------------------------------------

---

## React Hooks

---

### What is React Router?

React Router refers to the standard library used for routing in React. It permits us for building a single-page web application in React with navigation without even refreshing the page when the user navigates. It also allows to change the browser URL and will keep the user interface in sync with the URL. React Router will make use of the component structure for calling the components, using which appropriate information can be shown. Since React is a component-based framework, it’s not necessary to include and use this package. Any other compatible routing library would also work with React.

    The major components of React Router are given below:

    - **BrowserRouter:** It is a router implementation that will make use of the HTML5 history API (pushState, popstate, and event replaceState) for keeping your UI to be in sync with the URL. It is the parent component useful in storing all other components.
    - **Routes: **It is a newer component that has been introduced in the React v6 and an upgrade of the component.
    - **Route: **It is considered to be a conditionally shown component and some UI will be rendered by this whenever there is a match between its path and the current URL.
    - **Link:** It is useful in creating links to various routes and implementing navigation all over the application. It works similarly to the anchor tag in HTML.

---

### What is React Router and what are its main components?

`<BrowserRouter>` or `<RouterProvider>`: wraps the app.
`<Routes>`/`<Route>`: declare URL → component mappings. `<Link>`:
navigation without reload. `useNavigate()`, `useParams()`,
`useSearchParams()`, `useLocation()`: hooks for router state.

------------------------------------------------------------------------

---

---

### What is route based code splitting?

One of the best place to do code splitting is with routes. The entire page is going to re-render at once so users are unlikely to interact with other elements in the page at the same time. Due to this, the user experience won't be disturbed.

Let us take an example of route based website using libraries like React Router with React.lazy,


```
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import React, { Suspense, lazy } from 'react';

const Home = lazy(() => import('./routes/Home'));
const About = lazy(() => import('./routes/About'));

const App = () => (
  <Router>
    <Suspense fallback={<div>Loading...</div>}>
      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
      </Switch>
    </Suspense>
  </Router>
);

```

In the above code, the code splitting will happen at each route level.

[

---

### What is routing in React? How does it work?

Routing in React is the process of mapping URL paths to different components, enabling a single‑page application (SPA) to simulate multiple pages. React Router (or other libraries) listens to URL changes, matches the path against defined routes, and renders the corresponding component without a full browser refresh. It leverages the browser’s History API (`pushState`, `replaceState`) to manage navigation and updates the UI accordingly.

### Controlled vs uncontrolled components – explain with examples.

- **Controlled component**: Form input whose value is controlled by React state. The input’s value is set via `value` prop and updates via `onChange`. React is the single source of truth.
  ```jsx
  const [value, setValue] = useState('');
  <input value={value} onChange={e => setValue(e.target.value)} />
  ```
- **Uncontrolled component**: The DOM itself manages the input state. You access the current value via a ref (`useRef`).
  ```jsx
  const inputRef = useRef();
  <input ref={inputRef} />
  // later: inputRef.current.value
  ```

---

### What is the difference between `Router` and `Link` in React Router?

-   **`Router`** (e.g., `BrowserRouter`): Provides the routing context
    and handles history management. It is the parent component that
    enables navigation and URL sync.
-   **`Link`**: A component that renders an anchor (`<a>`) with the `to`
    prop. It allows navigation without a full page reload, using
    client‑side routing.

------------------------------------------------------------------------

---

---

### What is the popular choice for form handling?

`Formik` is a form library for react which provides solutions such as validation, keeping track of the visited fields, and handling form submission.

In detail, You can categorize them as follows,

1. Getting values in and out of form state
2. Validation and error messages
3. Handling form submission

It is used to create a scalable, performant, form helper with a minimal API to solve annoying stuff.

[

---

### What is useEffect hook? How to fetch data with React Hooks?

The `useEffect` hook is a React Hook that lets you perform **side
effects** in function components. Side effects are operations that
interact with the outside world or system and aren't directly related to
rendering UI --- such as fetching data, setting up subscriptions,
timers, manually manipulating the DOM, etc.

     In function components, useEffect replaces the class component lifecycle methods(`componentDidMount`, `componentDidUpdate` and `componentWillUnmount`) with a single, unified API.     

     **Syntax**
     ```js
     useEffect(() => {
        // Side effect logic here

        return () => {
        // Cleanup logic (optional)
        };
        }, **

------------------------------------------------------------------------

---

---

## Context & State Management

### Can I dispatch an action in reducer?

Dispatching an action within a reducer is an **anti-pattern**. Your reducer should be _without side effects_, simply digesting the action payload and returning a new state object. Adding listeners and dispatching actions within the reducer can lead to chained actions and other side effects.

    ****

---

### Can React Hook replaces Redux?

The React Hook cannot be considered as a replacement for Redux (It is an open-source, JavaScript library useful in managing the application state) when it comes to the management of the global application state tree in large complex applications, even though the React will provide a useReducer hook that manages state transitions similar to Redux. Redux is very useful at a lower level of component hierarchy to handle the pieces of a state which are dependent on each other, instead of a declaration of multiple useState hooks.

In commercial web applications which is larger, the complexity will be high, so using only React Hook may not be sufficient. Few developers will try to tackle the challenge with the help of React Hooks and others will combine React Hooks with the Redux.

---

### Can Redux only be used with React?

Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. Redux simply provides a subscription mechanism which can be used by any other code.

[

---

### Can useRef be used to store previous values?

Yes, `useRef` is a common pattern when you want to compare current and
previous props or state without causing re-renders.

        **Example: Storing previous state value**
        ```js
        import { useEffect, useRef, useState } from 'react';
        
        function PreviousValueExample() {
          const **

------------------------------------------------------------------------

---

---

### Can You Use Multiple Contexts in One Component?

Yes, it is possible. You can use multiple contexts inside the same
component by calling useContext multiple times, once for each context.

     It can be achieved with below steps,

        *   Create multiple contexts using `createContext()`.
        *   Wrap your component tree with multiple `<Provider>`s.
        *   Call `useContext()` separately for each context in the same component.
     
     **Example: Using `ThemeContext` and `UserContext` Together**
     ```js
     import React, { createContext, useContext } from 'react';

      // Step 1: Create two contexts
      const ThemeContext = createContext();
      const UserContext = createContext();

      function Dashboard() {
        // Step 2: Use both contexts
        const theme = useContext(ThemeContext);
        const user = useContext(UserContext);

        return (
          <div style={{ background: theme === 'dark' ? '#333' : '#fff' }}>
            <h1>Welcome, {user.name}</h1>
            <p>Current theme: {theme}</p>
          </div>
        );
      }

      // Step 3: Provide both contexts
      function App() {
        return (
          <ThemeContext.Provider value="dark">
            <UserContext.Provider value={{ name: 'Sudheer' }}>
              <Dashboard />
            </UserContext.Provider>
          </ThemeContext.Provider>
        );
      }

      export default App;
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).

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

---

### Context re-render behavior – what should you know?

Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### Context Re-renders: Context API causes frequent re-renders – why and how to fix?

**Why**:
    - When the context value changes, **all consumers** re‑render, regardless of which part of the value they use.
    - If the context value is an object that is re‑created on each render (e.g., `<Provider value={{ user, setUser }}>`), every consumer re‑renders.

    **Fixes**:
    - **Memoize the context value** with `useMemo`.
    - **Split contexts** into smaller pieces (e.g., `UserContext`, `ThemeContext`) so consumers only subscribe to what changes.
    - Use **`useContextSelector`** (if using a library like `use-context-selector`) to subscribe only to specific parts.
    - Move state down to the components that actually need it (colocate state).

    **Example**:
    ```jsx
    const value = useMemo(() => ({ user, setUser }), [user]);
    <Provider value={value}>{children}</Provider>

------------------------------------------------------------------------

---

---

### Context vs Redux – when to choose which?

Context: simple, low-frequency shared state (theme, auth, locale). Redux: complex update logic, middleware (logging, side effects), time-travel debugging, large team codebases, or when you need strict action-based mutations.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### Do I need to keep all my state into Redux? Should I ever use react internal state?

It is up to developer decision. i.e, It is developer job to determine what kinds of state make up your application, and where each piece of state should live. Some users prefer to keep every single piece of data in Redux, to maintain a fully serializable and controlled version of their application at all times. Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, inside a component's internal state.

Below are the thumb rules to determine what kind of data should be put into Redux

1. Do other parts of the application care about this data?
2. Do you need to be able to create further derived data based on this original data?
3. Is the same data being used to drive multiple components?
4. Is there value to you in being able to restore this state to a given point in time (ie, time travel debugging)?
5. Do you want to cache the data (i.e, use what's in state if it's already there instead of re-requesting it)?

[

---

### Do you need to have a particular build tool to use Redux?

Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. You should be able to use it regardless of your JavaScript build process. Redux also offers a UMD build that can be used directly without any build process at all.

[

---

### Explain reducers and extraReducers – when to use each?

- **`reducers`**: Used for actions that are directly handled by this slice. RTK automatically generates action creators with the same names. Good for synchronous, slice‑specific updates.
- **`extraReducers`**: Used to respond to actions defined elsewhere (e.g., thunks, actions from other slices). It’s often used with `builder` callback to handle `pending`, `fulfilled`, `rejected` of async thunks. It allows a slice to react to actions that are not its own.

---

### Explain the flow of Redux Toolkit.

1. **Define slices** using `createSlice`. Each slice contains `name`, `initialState`, and `reducers` (functions that handle actions). Reducers can be simple or use `prepare` callbacks.
2. **Combine slices** (if needed) and configure the store with `configureStore`.
3. **Dispatch actions** using the generated action creators (e.g., `increment()`).
4. **Use hooks** (`useSelector`, `useDispatch`) in React components to read state and dispatch actions.
5. **Async logic**: Use `createAsyncThunk` to define thunks that handle async requests and dispatch pending/fulfilled/rejected actions.

---

### Explain the Redux data flow (action → reducer → store → view).

1. **Action**: A plain object with a `type` field describing what happened (e.g., `{ type: 'INCREMENT' }`). Dispatched from the UI.
2. **Reducer**: A pure function that takes the current state and an action, and returns a new state (immutable update). Reducers combine to form the root reducer.
3. **Store**: Holds the state tree. Provides `dispatch`, `getState`, and `subscribe`.
4. **View**: React components subscribe to the store and re‑render when the state changes.

---

### Give an example on How to use context?

**Context** is designed to share data that can be considered **global**
for a tree of React components.

    For example, in the code below lets manually thread through a “theme” prop in order to style the Button component.

    ```javascript
    //Lets create a context with a default theme value "luna"
    const ThemeContext = React.createContext("luna");
    // Create App component where it uses provider to pass theme value in the tree
    class App extends React.Component {
      render() {
        return (
          <ThemeContext.Provider value="nova">
            <Toolbar />
          </ThemeContext.Provider>
        );
      }
    }
    // A middle component where you don't need to pass theme prop anymore
    function Toolbar(props) {
      return (
        <div>
          <ThemedButton />
        </div>
      );
    }
    // Lets read theme value in the button component to use
    class ThemedButton extends React.Component {
      static contextType = ThemeContext;
      render() {
        return <Button theme={this.context} />;
      }
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you make sure that user remains authenticated on page refresh while using Context API State Management?

When a user logs in and reload, to persist the state generally we add the load user action in the useEffect hooks in the main App.js. While using Redux, loadUser action can be easily accessed.

**App.js**


```
import { loadUser } from '../actions/auth';
store.dispatch(loadUser());

```

- But while using **Context API**, to access context in App.js, wrap the AuthState in index.js so that App.js can access the auth context. Now whenever the page reloads, no matter what route you are on, the user will be authenticated as **loadUser** action will be triggered on each re-render.

**index.js**


```
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import AuthState from './context/auth/AuthState';

ReactDOM.render(
  <React.StrictMode>
    <AuthState>
      <App />
    </AuthState>
  </React.StrictMode>,
  document.getElementById('root'),
);

```

**App.js**


```
const authContext = useContext(AuthContext);

const { loadUser } = authContext;

useEffect(() => {
  loadUser();
}, []);

```

**loadUser**


```
const loadUser = async () => {
  const token = sessionStorage.getItem('token');

  if (!token) {
    dispatch({
      type: ERROR,
    });
  }
  setAuthToken(token);

  try {
    const res = await axios('/api/auth');

    dispatch({
      type: USER_LOADED,
      payload: res.data.data,
    });
  } catch (err) {
    console.error(err);
  }
};

```

[

---

### How do you manage global state? Compare Context, Redux, and modern alternatives.

So, this question is more targeted towards ways that YOU would take to manage the global state. So while I write the answer down, it’s best that you personalize it with examples that seem fit to you.

Managing global state in React really depends on its scope and complexity.

Most of the time, you can use ‘useState’ or ‘useReducer’, which may work well for component-specific data. But there are many circumstances under which different features can be used,

1\. Context API - This is used when the state has to be shared with multiple components, and it helps in avoiding prop drilling,g but please keep in mind that it can cause all consumers to re-render on updates.

2\. Redux - When the state becomes more complex and interdependent throughout the application, external libraries like Redux are used. It provides a centralized store, predictable updates, and middleware support, but it comes with additional boilerplate.

When you look into modern alternatives, Zustand and Jotai provide simpler APIs and more efficient updates, which are usually suitable for mid-sized applications.

Here are some distinctions that you can note:

Client state & Server state:

- Client state can be managed with local state, Context, or Redux.
- Server state is better handled by tools like React Query, which manage caching and synchronization.

When NOT to use Redux: Redux is unnecessary for small or moderately complex applications, or when most of the state is server state.

So, here’s what you should do:

Start with local state, then move to Context for shared state, and then use external libraries only when complexity or performance demands it.

---

### How do you solve performance corner cases while using context?

The context uses reference identity to determine when to re-render,
there are some gotchas that could trigger unintentional renders in
consumers when a provider's parent re-renders.

    For example, the code below will re-render all consumers every time the Provider re-renders because a new object is always created for value.

    ```javascript
    class App extends React.Component {
      render() {
        return (
          <Provider value={{ something: "something" }}>
            <Toolbar />
          </Provider>
        );
      }
    }
    ```

    This can be solved by lifting up the value to parent state,

    ```javascript
    class App extends React.Component {
      constructor(props) {
        super(props);
        this.state = {
          value: { something: "something" },
        };
      }

      render() {
        return (
          <Provider value={this.state.value}>
            <Toolbar />
          </Provider>
        );
      }
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you test components with context?

Wrap with the real Provider (or a test Provider with controlled values)
in the render call. RTL's `render` accepts a wrapper option:
`render(<Comp/>, {wrapper: TestProviders})`.

------------------------------------------------------------------------

---

---

### How do you type context?

`createContext<ContextType | undefined>(undefined)`. In `useContext`
wrapper hook, assert non-null or throw if context is undefined. This
avoids the need to check for undefined in every consumer.

------------------------------------------------------------------------

---

---

### How do you type `useReducer`?

Define State and Action types (often a discriminated union for Action). `useReducer<Reducer<State, Action>>(reducer, initial)`. TypeScript infers dispatch type automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you use contextType?

ContextType is used to consume the context object. The contextType property can be used in two ways,

1. **contextType as property of class:** The contextType property on a class can be assigned a Context object created by React.createContext(). After that, you can consume the nearest current value of that Context type using this.context in any of the lifecycle methods and render function.

Lets assign contextType property on MyClass as below,


```
   class MyClass extends React.Component {
     componentDidMount() {
       let value = this.context;
       /* perform a side-effect at mount using the value of MyContext */
     }
     componentDidUpdate() {
       let value = this.context;
       /* ... */
     }
     componentWillUnmount() {
       let value = this.context;
       /* ... */
     }
     render() {
       let value = this.context;
       /* render something based on the value of MyContext */
     }
   }
   MyClass.contextType = MyContext;

```

1. **Static field** You can use a static class field to initialize your contextType using public class field syntax.

```
   class MyClass extends React.Component {
     static contextType = MyContext;
     render() {
       let value = this.context;
       /* render something based on the value */
     }
   }

```

[

---

### How does async flow work in Redux Toolkit?

1. Define a thunk using `createAsyncThunk`.
2. Inside the payload creator, perform async work (e.g., fetch).
3. Dispatch the thunk from a component.
4. The thunk dispatches the `pending` action immediately.
5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.
6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data).

---

### How does React Context work? When can it hurt performance?

Context provides a way to pass data through the component tree without prop drilling. It works by creating a `Provider` component that holds a value. Any component that consumes the context via `useContext` will re‑render when the context value changes.

**Performance pitfalls**:
- If the context value changes frequently, many consumers may re‑render.
- When a component consumes context, it cannot be memoized based on props alone; it will re‑render whenever the context value changes, even if the component’s own props didn’t change.
- Using context for global state that changes often (e.g., animations) can cause excessive re‑renders.

---

### How does Redux Toolkit work internally?

- `createSlice` uses `createReducer` and `createAction` under the hood to generate reducers and action creators. It leverages Immer to allow immutable updates with mutable syntax.
- `configureStore` calls Redux’s `createStore`, applies default middleware (including `redux-thunk`), and enables the Redux DevTools Extension.
- `createAsyncThunk` returns a thunk that dispatches the lifecycle actions automatically and allows handling of the async operation.

---

### How Relay is different from Redux?

Relay is similar to Redux in that they both use a single store. The main difference is that relay only manages state originated from the server, and all access to the state is used via *GraphQL* queries (for reading data) and mutations (for changing data). Relay caches the data for you and optimizes data fetching for you, by fetching only changed data and nothing more.

---

### How to add multiple middlewares to Redux?

You can use `applyMiddleware()`.

For example, you can add `redux-thunk` and `logger` passing them as arguments to `applyMiddleware()`:


```
import { createStore, applyMiddleware } from 'redux';
const createStoreWithMiddleware = applyMiddleware(ReduxThunk, logger)(createStore);

```

[

---

### How to set initial state in Redux?

You need to pass initial state as second argument to createStore:


```
const rootReducer = combineReducers({
  todos: todos,
  visibilityFilter: visibilityFilter,
});

const initialState = {
  todos: [{ id: 123, name: 'example', completed: false }],
};

const store = createStore(rootReducer, initialState);

```

[

---

### Is dispatch from useReducer asynchronous and does it update state immediately?

The `dispatch` function returned by `useReducer` is **not asynchronous**
--- it is a **synchronous** function call. When you call
`dispatch(action)`, React **synchronously** invokes your reducer with
the current state and the action, computes the new state, and
**schedules a re-render**. However, the **state variable does not update
immediately** within the same render cycle. The updated state is only
available in the **next render**.

     This behavior is similar to `useState`'s `setState` — React **batches** state updates for performance optimization, meaning the component does not re-render immediately after each `dispatch` call. Instead, React processes all dispatched actions and re-renders once with the final state.

     #### Key Points

     1. **`dispatch` is synchronous:** The reducer runs immediately when `dispatch` is called.
     2. **State update is not immediate in the current render:** The state variable still holds the old value until the next render.
     3. **React batches updates:** Multiple `dispatch` calls within the same event handler result in a single re-render.
     4. **Reducer is a pure function:** It computes the new state without side effects.

     #### Example demonstrating that state does not update immediately

     ```jsx
     import React, { useReducer } from 'react';

     function reducer(state, action) {
       switch (action.type) {
         case 'increment':
           return { count: state.count + 1 };
         default:
           return state;
       }
     }

     function Counter() {
       const **

284. ### How does useContext works? Explain with an example

     The `useContext` hook can be used for authentication state
     management across multiple components and pages in a React
     application.

     Let's build a simple authentication flow with:

     -   **Login and Logout buttons**
     -   Global `AuthContext` to share state
     -   Components that can **access and update** auth status

     **1. Create the Auth Context:**

     You can define `AuthProvider` which holds and provides `user`,
     `login()`, and `logout()` via context. \`\`\`js // AuthContext.js
     import React, { createContext, useContext, useState } from 'react';

     const AuthContext = createContext();

     export function AuthProvider({ children }) { const \*\*

------------------------------------------------------------------------

---

---

### Situation: Context is causing performance issues in a large app – what do you do?

Split into multiple smaller contexts by concern. Memoize provider values. Move high-frequency state to a store with selectors (Zustand, Jotai). Use context only for rarely-changing values.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are React 19 Actions?

Functions that handle async mutations (form submissions, data updates).
They can be synchronous or async. React 19 provides `useActionState`,
`useFormStatus`, and `useOptimistic` to manage their state
automatically.

------------------------------------------------------------------------

---

---

### What are Server Actions in React 19?

**Server Actions** allow you to call server-side functions directly from
client components without writing API endpoints.

     #### Basic Server Action
     ```jsx
     // app/actions.js
     'use server'

     export async function createPost(formData) {
       const title = formData.get('title');
       const content = formData.get('content');
       
       const post = await db.posts.create({
         title,
         content,
         userId: await getCurrentUser()
       });
       
       revalidatePath('/posts');
       redirect(`/posts/${post.id}`);
     }
     ```

     #### Using in Forms
     ```jsx
     // app/new-post.jsx
     import { createPost } from './actions';

     export default function NewPost() {
       return (
         <form action={createPost}>
           <input name="title" required />
           <textarea name="content" required />
           <button type="submit">Create Post</button>
         </form>
       );
     }
     ```

     #### With useFormState for Loading States
     ```jsx
     'use client'
     import { useFormState } from 'react-dom';
     import { createPost } from './actions';

     export default function NewPost() {
       const **

------------------------------------------------------------------------

---

---

### What are the differences between Flux and Redux?

Below are the major differences between Flux and Redux

| FluxRedux                                      |                                            |
| ---------------------------------------------- | ------------------------------------------ |
| State is mutable                               | State is immutable                         |
| The Store contains both state and change logic | The Store and change logic are separate    |
| There are multiple stores exist                | There is only one store exist              |
| All the stores are disconnected and flat       | Single store with hierarchical reducers    |
| It has a singleton dispatcher                  | There is no concept of dispatcher          |
| React components subscribe to the store        | Container components uses connect function |

[

---

### What are the differences between Redux and MobX?

Below are the main differences between Redux and MobX,

| TopicReduxMobX |                                                               |                                                                        |
| -------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Definition     | It is a javascript library for managing the application state | It is a library for reactively managing the state of your applications |
| Programming    | It is mainly written in ES6                                   | It is written in JavaScript(ES5)                                       |
| Data Store     | There is only one large store exist for data storage          | There is more than one store for storage                               |
| Usage          | Mainly used for large and complex applications                | Used for simple applications                                           |
| Performance    | Need to be improved                                           | Provides better performance                                            |
| How it stores  | Uses JS Object to store                                       | Uses observable to store the data                                      |

[

---

### What are the main features of Redux Form?

Some of the main features of Redux Form are:

1. Field values persistence via Redux store.
2. Validation (sync/async) and submission.
3. Formatting, parsing and normalization of field values.

[

---

### What are the use cases of useContext hook?

The `useContext` hook in React is used to share data across components
without having to pass props manually through each level. Here are some
common and effective use cases:

        1.  **Theme Customization**  
            `useContext` can be used to manage application-wide themes, such as light and dark modes, ensuring consistent styling and enabling user-driven customization.
        2.  **Localization and Internationalization**  
            It supports localization by providing translated strings or locale-specific content to components, adapting the application for users in different regions.
        3.  **User Authentication and Session Management**  
            `useContext` allows global access to authentication status and user data. This enables conditional rendering of components and helps manage protected routes or user-specific UI elements.
        4.  **Shared Modal or Sidebar Visibility**  
            It's ideal for managing the visibility of shared UI components like modals, drawers, or sidebars, especially when their state needs to be controlled from various parts of the app.
        5.  **Combining with** `**useReducer**` **for Global State Management**  
            When combined with `useReducer`, `useContext` becomes a powerful tool for managing more complex global state logic. This pattern helps maintain cleaner, scalable state logic without introducing external libraries like Redux.
             Some of the common use cases of useContext are listed below,

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are typical middleware choices for handling asynchronous calls in Redux?

Some of the popular middleware choices for handling asynchronous calls in Redux eco system are `Redux Thunk, Redux Promise, Redux Saga`.

[

---

### What is an action in Redux?

*Actions* are plain JavaScript objects or payloads of information that send data from your application to your store. They are the only source of information for the store. Actions must have a type property that indicates the type of action being performed.

For example, let's take an action which represents adding a new todo item:


```
{
  type: ADD_TODO,
  text: 'Add todo item'
}

```

[

---

### What is context?

*Context* provides a way to pass data through the component tree without
having to pass props down manually at every level.

    For example, authenticated users, locale preferences, UI themes need to be accessed in the application by many components.

    ```javascript
    const { Provider, Consumer } = React.createContext(defaultValue);
    ```

    ****

------------------------------------------------------------------------

---

---

### What is `createSlice()` and what does it contain? (name, initialState, reducers)

`createSlice` accepts an object with:
- `name`: A string used as prefix for action types.
- `initialState`: The initial state value.
- `reducers`: An object mapping action names to reducer functions (or `prepare` callbacks). Each reducer function receives `state` and `action` and can mutate the state (thanks to Immer).
- `extraReducers` (optional): Allows responding to actions not defined in the slice (e.g., from `createAsyncThunk`).

It returns an object with `actions` (action creators) and `reducer` (slice reducer).

---

### What is flux?

**Flux** is an **application architecture** (not a framework or library) designed by Facebook to manage **data flow** in React applications. It was created as an alternative to the traditional **MVC (Model-View-Controller)** pattern, and it emphasizes a **unidirectional data flow** to make state changes more predictable and easier to debug.

           Flux complements React by organizing the way data moves through your application, especially in large-scale or complex projects.

           #### Core Concepts of Flux

           Flux operates using **four key components**, each with a specific responsibility:
           *   **Actions**
                 *   Plain JavaScript objects or functions that describe _what happened_ (e.g., user interactions or API responses).
                 *   Example: `{ type: 'ADD_TODO', payload: 'Buy milk' }`
           *   **Dispatcher**
                 *   A central hub that receives actions and **dispatches** them to the appropriate stores.
                 *   There is **only one dispatcher** in a Flux application.
           *   **Stores**
                 *   Hold the **application state** and business logic.
                 *   Respond to actions from the dispatcher and update themselves accordingly.
                 *   They **emit change events** that views can listen to.
           *   **Views (React Components)**
                 *   Subscribe to stores and **re-render** when the data changes.
                 *   They can also trigger new actions (e.g., on user input).

           The workflow between dispatcher, stores and views components with distinct inputs and outputs as follows:

           !**

---

### What is Jotai and how does the atomic model work?

Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is MobX?

MobX is a simple, scalable and battle tested state management solution for applying functional reactive programming (TFRP). For reactJs application, you need to install below packages,


```
npm install mobx --save
npm install mobx-react --save

```

[

---

### What is Redux Toolkit and why is it recommended over plain Redux?

Redux Toolkit (RTK) is the official, opinionated toolset for Redux. It simplifies common patterns, reduces boilerplate, and includes best practices out of the box:

- **`configureStore`**: Sets up the store with good defaults (middleware, devtools).
- **`createSlice`**: Automatically generates action creators and reducers.
- **`createAsyncThunk`**: Handles asynchronous actions with loading states.
- **Immer integration**: Allows writing mutable‑looking code in reducers (actual immutability is handled).
- **Redux DevTools** automatically enabled.

---

### What is Relay?

Relay is a JavaScript framework for providing a data layer and client-server communication to web applications using the React view layer.

[

---

### What is the Context API?

A built-in React mechanism for sharing values across the component tree
without prop drilling. Three parts: `React.createContext()` (creates
context), `Provider` (supplies value), `useContext()` (consumes value).

------------------------------------------------------------------------

---

---

### What is the Context API? When should you use it instead of prop drilling?

Prop drilling is the pattern of passing on data from the parent component through several levels down to the nested child component, but its process makes the code harder to maintain and debug.

    To avoid such problems, Context API, which is a built-in feature in React, helps in passing on the data, but without having to go through every level.

    This is how it works:

    You create a context using React.createContext(), then wrap part of your app with a Provider, and lastly, consume the value using useContext()

    Now, how does this actually help?

    For example:

    - current user (auth)
    - theme (dark/light)
    - language/locale

    These are values that are needed across many components at different levels. Passing them manually quickly becomes messy, so Context helps in keeping it cleaner.

    But here’s where it gets a little confusing,

    Context is not meant for everything.

    If the data changes very frequently, such as form input or animations, then Context might even end up hurting the performance.

    And why is that?

    Because whenever the context value changes, all components consuming it re-render.

    So the better way to understand this is that you can use Context for global, relatively stable data and keep local or frequently changing state inside components.

    You can also split contexts based on how often they update, instead of putting everything into one.

    That’s the difference between Context and Redux!

    Context is built into React and works well for simpler cases.

    Redux, on the other hand, adds things like middleware, devtools, better control over updates

    …but it also comes with more setup.

    **You can be asked some follow-up questions here, like:**

    Q. What happens if Context values change frequently?

    Your ans: All consuming components re-render.

    Q. How do you optimize it?

    Your ans: I split contexts based on their use and memoize the value passed to the Provider.

---

### What is the purpose of default value in context?

The defaultValue argument is only used when a component does not have a
matching Provider above it in the tree. This can be helpful for testing
components in isolation without wrapping them.

     Below code snippet provides default theme value as Luna.

     ```javascript
     const MyContext = React.createContext(defaultValue);
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the Redux Toolkit (RTK)?

The official, recommended way to write Redux. Reduces boilerplate with `createSlice` (combines actions + reducers), `configureStore`, and RTK Query (built-in data fetching/caching layer).

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the state reducer pattern?

State Reducer Pattern gives the user of your component a "veto power" or
steering wheel over how the component's internal data changes.

Instead of the component making all the rules about how its state
updates, it handles the heavy lifting but passes every change through a
custom function you provide. This lets you intercept and modify the
changes before they actually happen.

------------------------------------------------------------------------

---

---

### What is the `useSelector` / `useDispatch` pattern in Redux?

useSelector is for reading data. It lets your component "grab" a specific piece of state from the global Redux store
useDispatch is for changing data. It gives you a dispatch function. You use this function to send "actions" (requests) to the Redux store telling it to update the data.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the useSyncExternalStore hook?

The `useSyncExternalStore` hook is designed to **subscribe to external
stores** (non-React state sources) in a way that's compatible with
concurrent rendering. It's primarily used by library authors for state
management libraries.

     #### Syntax
     ```js
     const state = useSyncExternalStore(subscribe, getSnapshot, getServerSnapshot?);
     ```

     - **subscribe**: Function to subscribe to the store, returns an unsubscribe function
     - **getSnapshot**: Function that returns the current store value
     - **getServerSnapshot**: Optional function for SSR that returns the initial server snapshot

     #### Example: Browser Online Status
     ```jsx
     import { useSyncExternalStore } from 'react';

     function getSnapshot() {
       return navigator.onLine;
     }

     function subscribe(callback) {
       window.addEventListener('online', callback);
       window.addEventListener('offline', callback);
       return () => {
         window.removeEventListener('online', callback);
         window.removeEventListener('offline', callback);
       };
     }

     function useOnlineStatus() {
       return useSyncExternalStore(subscribe, getSnapshot, () => true);
     }

     function StatusBar() {
       const isOnline = useOnlineStatus();
       return <h1>{isOnline ? '✅ Online' : '❌ Disconnected'}</h1>;
     }
     ```

     This hook ensures that when the external store changes, React re-renders consistently without tearing (showing inconsistent data).

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is `useActionState` (React 19)?

Manages state for an async action. Returns `[state, dispatch, isPending]`. On form submission, calls the action with form data, updates state with the result, and tracks pending status automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useContext`?

Subscribes to a React context. Receives the current context value and re-renders whenever it changes. Eliminates prop drilling for shared data like theme, locale, auth, or feature flags.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useReducer`?

Like `useState` but manages state via a `reducer(state, action) => newState` function. Better for complex state with multiple sub-values, or when next state depends on action type. Pairs well with `useContext` for mini-Redux patterns.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is useReducer, and when would you use it over useState?

useReducer and useState are React hooks that manage state within functional components.

    Here,

    useRender is used for more complex state logic, and useState carries out simpler values.

    Here’s how they work:

    With useState, you directly update values with

setCount(count + 1);


    Now you already know what change you want, so you update it immediately.

    The approach becomes a little different when it comes to useReducer. You will describe what happened, and a separate function then decides how to update the state.

    For example:

     

const \[state, dispatch\] = useReducer(reducer, { count: 0 });


    Here:

    - state - holds the current value
    - dispatch - used to send actions
    - reducer - a function that updates the state

    Looking at the reducer function,

     

function reducer(state, action) { if (action.type === "increment") {
return { count: state.count + 1 }; } return state; }


    Here, the reducer receives the current ‘state’ and an ‘action’, then it checks what kind of action it is (action.type), and based on that, it returns a new state.

    At first, this feels like extra steps compared to useState. But it becomes useful when state is more complex.

    For example, in a form with multiple fields, instead of writing many useState calls, you can handle all updates in one reducer function.

    This keeps all the logic in one place instead of spreading it across different handlers.

---

### What is Zustand and how does it differ from Redux?

Zustand is a minimal state library using hooks. No boilerplate, no reducers/actions required. Stores are plain JS objects with setter functions. Components subscribe to specific slices to avoid unnecessary re-renders.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What problems does Redux solve in large React applications?

- **State sharing**: Avoids prop drilling for deeply nested components.
- **Predictability**: State changes happen via pure reducers, making it easier to debug with time‑travel.
- **Separation of concerns**: UI logic is decoupled from state management.
- **Middleware**: Enables handling side effects (async actions, logging) in a structured way.
- **DevTools**: Excellent debugging capabilities.

---

### What would the context value be for no matching provider?

When a component calls `useContext(SomeContext)` but **no matching**
`<SomeContext.Provider>` **is present higher up in the component tree**,
the **default value** passed to `React.createContext(defaultValue)` is
returned.

     ```js
     const ThemeContext = React.createContext('light'); // 'light' is the default value

     function ThemedComponent() {
       const theme = useContext(ThemeContext);
       return <div>Current theme: {theme}</div>;
     }

     // No ThemeContext.Provider anywhere in the tree
     ```
     In this case, `theme` will be 'light'. It's the default value you provided when you created the context.

     **Note:** If you don’t specify a default value, the context value will be undefined when used without a provider:

     ```jsx
     const AuthContext = React.createContext(); // No default

     function Profile() {
       const auth = useContext(AuthContext);
       // auth will be undefined if there's no AuthContext.Provider
     }
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### When should you NOT use Context for state?

For frequently changing data (e.g., mouse position, animation frames),
because every consumer re-renders. Use a dedicated state library with
selectors (Zustand, Jotai, Redux) for fine-grained subscriptions.

------------------------------------------------------------------------

---

---

### Where and why have you used Redux Toolkit in your projects?

Common scenarios:
- **Large‑scale apps with complex shared state**: Shopping carts, user authentication, multi‑step forms.
- **Real‑time dashboards**: To manage data from WebSockets across many components.
- **Apps with complex async flows**: To maintain loading/error states in a consistent manner.
- **When multiple features need access to the same data**: E.g., user profile, preferences, notifications.

---

### ❓ What is Redux and why is it used?

**Answer:** Redux is a predictable state container: single source of truth (one global store), state is read-only (only changed by dispatching actions), changes via pure reducer functions. Benefits for large apps: predictable state transitions, easy debugging (Redux DevTools time-travel), centralized state logic, middleware for async operations, testable reducers. Redux Toolkit (RTK) is the modern recommended approach — reduces boilerplate with createSlice, createAsyncThunk, and immer-based immutable updates.

### ❓ Explain the Redux Toolkit flow.

**Answer:** (1) createSlice() defines state shape, reducers (sync), and generates action creators. (2) configureStore() combines slices into the global store, auto-adds DevTools and middleware. (3) createAsyncThunk() handles async operations — dispatches pending/fulfilled/rejected actions. (4) extraReducers handles async thunk lifecycle in slices. (5) Components use useSelector() to read state and useDispatch() to send actions. (6) Store notifies all subscribers on state change, React re-renders connected components.

---

### ❓ What is the difference between Context API and Redux Toolkit?

**Answer:** Context API: built-in React, no extra library, ideal for low-frequency updates (theme, locale, auth user). Limitation: any context value change re-renders all consumers — bad for high-frequency state. Redux Toolkit: external library, single global store with selectors — components only re-render when their specific slice changes. Better for: complex state, frequent updates, time-travel debugging, multiple teams. Decision: use Context for simple/infrequent state, Redux Toolkit for complex apps with many state updates.

---

## Hooks

### Build a custom hook like `useDebounce` or `useFetch`.

**`useDebounce`** (example):

``` javascript
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

**`useFetch`** (example):

``` javascript
function useFetch(url, options = {}) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const abortController = new AbortController();
    const fetchData = async () => {
      try {
        const res = await fetch(url, { ...options, signal: abortController.signal });
        if (!res.ok) throw new Error('Network error');
        const json = await res.json();
        setData(json);
        setLoading(false);
      } catch (err) {
        if (err.name !== 'AbortError') {
          setError(err);
          setLoading(false);
        }
      }
    };
    fetchData();
    return () => abortController.abort();
  }, [url, ...Object.values(options)]); // caution: options can cause infinite loops
  return { data, loading, error };
}
```

------------------------------------------------------------------------

---

---

### Can Hooks be used in class components?

No, Hooks cannot be used inside class components. They are specially
designed for function components. This is because hooks depend on the
sequence in which they are called during a component's render, something
that's only guaranteed in functional components. However, both class and
function components can coexist in the same application.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Can you describe the useMemo() Hook?

The `useMemo()` Hook in React is used to **optimize performance** by
**memoizing the result of expensive calculations**. It ensures that a
function is **only re-executed when its dependencies change**,
preventing unnecessary computations on every re-render.

     #### Syntax

     ```js
      const memoizedValue = useMemo(() => computeExpensiveValue(arg), **

------------------------------------------------------------------------

---

---

### Can you have multiple useEffect hooks in a single component?

Yes, multiple useEffect hooks are allowed and recommended when you want
to separate concerns.

      ```jsx
      useEffect(() => {
        // Handles API fetch
      }, **

------------------------------------------------------------------------

---

---

### Custom hooks vs HOCs vs render props – when to use each?

Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when you need to wrap a component (e.g., code splitting, legacy compatibility). Render props: when JSX composition is specifically needed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### Difference between `useEffect`, `useLayoutEffect`, and `useInsertionEffect`.

- **`useEffect`**: Runs asynchronously after the browser paints. Suitable for most side effects.
- **`useLayoutEffect`**: Runs synchronously after all DOM mutations but before the browser paints. Useful for measuring layout or making visual updates that should appear before paint (e.g., scrolling to an element). Use sparingly as it blocks painting.
- **`useInsertionEffect`**: A newer hook (React 18) intended for CSS‑in‑JS libraries to inject styles before layout effects fire. Not meant for general use.

---

### Difference between `useMemo` and `React.memo`.

-   **`useMemo`**: A hook that memoizes the result of a computation. It
    recalculates only when its dependencies change. Used to optimize
    expensive calculations inside a component.
-   **`React.memo`**: A higher‑order component that memoizes a
    component. It prevents re‑rendering if the props have not changed
    (shallow comparison). It wraps the whole component, not a value.

---

---

### Differentiate React Hooks vs Classes.

| React HooksClasses                                                                  |                                                                                                               |
    | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
    | It is used in functional components of React.                                       | It is used in class-based components of React.                                                                |
    | It will not require a declaration of any kind of constructor.                       | It is necessary to declare the constructor inside the class component.                                        |
    | It does not require the use of `this` keyword in state declaration or modification. | Keyword `this` will be used in state declaration (`this.state`) and in modification (`this.setState()`).      |
    | It is easier to use because of the `useState` functionality.                        | No specific function is available for helping us to access the state and its corresponding setState variable. |
    | React Hooks can be helpful in implementing Redux and context API.                   | Because of the long setup of state declarations, class states are generally not preferred.                    |

---

### Do Hooks cover all the functionalities provided by the classes?

Our goal is for Hooks to cover all the functionalities for classes at its earliest. There are no Hook equivalents for the following methods that are not introduced in Hooks yet:

- `getSnapshotBeforeUpdate()`
- `getDerivedStateFromError()`
- `componentDidCatch()`

Since it is an early time for Hooks, few third-party libraries may not be compatible with Hooks at present, but they will be added soon.

---

### Do Hooks replace render props and higher order components?

Both render props and higher-order components render only a single child
but in most of the cases Hooks are a simpler way to serve this by
reducing nesting in your tree.

    ****

------------------------------------------------------------------------

---

---

### Does React Hook work with static typing?

Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. React Hooks are functions that are designed to make sure about all attributes must be statically typed. For enforcing stricter static typing within our code, we can make use of the React API with custom Hooks.

---

### Explain about types of Hooks in React.

There are two types of Hooks in React. They are:

    **1. Built-in Hooks:** The built-in Hooks are divided into 2 parts as given below:

    - **Basic Hooks:**
      - `useState()`: This functional component is used to set and retrieve the state.
      - `useEffect()`: It enables for performing the side effects in the functional components.
      - `useContext()`: It is used for creating common data that is to be accessed by the components hierarchy without having to pass the props down to each level.
    - **Additional Hooks:**
      - `useReducer()` : It is used when there is a complex state logic that is having several sub-values or when the upcoming state is dependent on the previous state. It will also enable you to optimization of component performance that will trigger deeper updates as it is permitted to pass the dispatch down instead of callbacks.
      - `useMemo()` : This will be used for recomputing the memoized value when there is a change in one of the dependencies. This optimization will help for avoiding expensive calculations on each render.
      - `useCallback()` : This is useful while passing callbacks into the optimized child components and depends on the equality of reference for the prevention of unneeded renders.
      - `useImperativeHandle()`:  It will enable modifying the instance that will be passed with the ref object.
      - `useDebugValue()`: It is used for displaying a label for custom hooks in React DevTools.
      - `useRef()` : It will permit creating a reference to the DOM element directly within the functional component.
      - `useLayoutEffect()`: It is used for the reading layout from the DOM and re-rendering synchronously.

    **2. Custom Hooks: **A custom Hook is basically a function of JavaScript. The Custom Hook working is similar to a regular function. The “use” at the beginning of the Custom Hook Name is required for React to understand that this is a custom Hook and also it will describe that this specific function follows the rules of Hooks. Moreover, developing custom Hooks will enable you for extracting component logic from within reusable functions.

---

### Explain how to create a simple React Hooks example program.

I will assume that you are having some coding knowledge about JavaScript and have installed Node on your system for creating a below given React Hook program. An installation of Node comes along with the command-line tools: npm and npx, where npm is useful to install the packages into a project and npx is useful in running commands of Node from the command line. The npx looks in the current project folder for checking whether a command has been installed there. When the command is not available on your computer, the npx will look in the npmjs.com repository, then the latest version of the command script will be loaded and will run without locally installing it. This feature is useful in creating a skeleton React application within a few key presses.

    Open the Terminal inside the folder of your choice, and run the following command:

npx create-react-app react-items-with-hooks


    Here, the `create-react-app` is an app initializer created by Facebook, to help with the easy and quick creation of React application, providing options to customize it while creating the application? The above command will create a new folder named react-items-with-hooks and it will be initialized with a basic React application. Now, you will be able to open the project in your favourite IDE. You can see an src folder inside the project along with the main application component `App.js`. This file is having a single function `App()` which will return an element and it will make use of an extended JavaScript syntax(JSX) for defining the component.

    JSX will permit you for writing HTML-style template syntax directly into the JavaScript file. This mixture of JavaScript and HTML will be converted by React toolchain into pure JavaScript that will render the HTML element.

    It is possible to define your own React components by writing a function that will return a JSX element. You can try this by creating a new file `src/SearchItem.js`and put the following code into it.

import React from 'react'; export function SearchItem() { return (

<div>

     <div className="search-input">
       <input type="text" placeholder="SearchItem"/>
     </div>
     <h1 className="h1">Search Results</h1>
     <div className="items">
       <table>
         <thead>
           <tr>
             <th className="itemname-col">Item Name</th>
             <th className="price-col">Price</th>
             <th className="quantity-col">Quantity</th>
           </tr>
         </thead>
         <tbody></tbody>
       </table>
     </div>

</div>

); }


    This is all about how you can create a component. It will only display the empty table and doesn’t do anything. But you will be able to use the Search component in the application. Open the file `src/App.js` and add the import statement given below to the top of the file.

import { SearchItem } from './SearchItem';


    Now, from the logo.svg, import will be removed and then contents of returned value in the function `App()` will be replaced with the following code:

::: {classname="App"}
```{=html}
<header>
```
Items with Hooks
```{=html}
</header>
```
`<SearchItem/>`{=html}
:::


    You can notice that the element \<SearchItem/> has been used just similar to an HTML element. The JSX syntax will enable for including the components in this approach directly within the JavaScript code. Your application can be tested by running the below-given command in your terminal.

    `npm start`

    This command will compile your application and open your default browser into [http://localhost:4000](http://localhost:4000/). This command can be kept on running when code development is in progress to make sure that the application is up-to-date, and also this browser page will be reloaded each time you modify and save the code.

    This application will work finely, but it doesn’t look nice as it doesn’t react to any input from the user. You can make it more interactive by adding a state with React Hooks, adding authentication, etc.

---

### Explain React Hooks.

**What are Hooks? **Hooks are functions that let us “hook into” React state and lifecycle features from a **functional component.**

    React Hooks** cannot** be used in class components. They let us write components without class.

    **Why were Hooks introduced in React?**

    React hooks were introduced in the 16.8 version of React. Previously, functional components were called stateless components. Only class components were used for state management and lifecycle methods. The need to change a functional component to a class component, whenever state management or lifecycle methods were to be used, led to the development of Hooks.

    *Example of a hook: ***useState hook:**

    In functional components, the useState hook lets us define a state for a component:

function Person(props) { // We are declaring a state variable called
name. // setName is a function to update/change the value of name let
\[name, setName\] = useState(''); }


    The state variable “name” can be directly used inside the HTML.

---

### Explain `useEffect` deeply: cleanup function, dependency array pitfalls.

`useEffect` lets you perform side effects (data fetching, subscriptions, DOM manipulations) in functional components. It runs after the browser paints.

- **Dependency array**: If omitted, effect runs after every render. If empty (`[]`), runs only once (mount). If values are provided, effect runs when any of those values change.
- **Cleanup function**: Return a function from `useEffect` – it runs before the component unmounts and before the next effect execution (to clean up previous subscriptions). Useful for canceling requests, clearing timers, removing event listeners.

**Pitfalls**:
- Missing dependencies can lead to stale data or infinite loops.
- Including unnecessary dependencies may cause excessive re‑runs.
- Using objects or arrays as dependencies without memoization can cause unwanted re‑runs because reference changes every render.

---

### How do you create a custom hook?

A function whose name starts with 'use' that calls other hooks. It
extracts and reuses stateful logic without changing component hierarchy.
E.g., `useWindowSize()`, `useFetch()`, `useDebounce()`.

------------------------------------------------------------------------

---

---

### How do you share state logic between components using custom hooks?

Custom hooks allow you to **extract and share stateful logic** between
components without changing their hierarchy. The state itself is not
shared---each component using the hook gets its own isolated state.

     #### Example: useLocalStorage Hook
     ```jsx
     import { useState, useEffect } from 'react';

     function useLocalStorage(key, initialValue) {
       // Get stored value or use initial value
       const **

------------------------------------------------------------------------

---

---

### How do you test custom hooks?

Use `renderHook` from `@testing-library/react`. `act()` wraps state updates. `const {result} = renderHook(() => useCounter(0)); act(() => result.current.increment()); expect(result.current.count).toBe(1)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you type `useRef`?

For DOM nodes: `useRef<HTMLInputElement>(null)` – `ref.current` can be null. For mutable values: `useRef<number>(0)` – not null. Use the appropriate overload based on usage.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How does the performance of using Hooks will differ in comparison with the classes?

- React Hooks will avoid a lot of overheads such as the instance creation, binding of events, etc., that are present with classes.
- Hooks in React will result in smaller component trees since they will be avoiding the nesting that exists in HOCs (Higher Order Components) and will render props which result in less amount of work to be done by React.

---

### How does `useRef` differ from a regular variable?

Regular variables reset on every render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How to ensure hooks followed the rules in your project?

React team released an ESLint plugin called **eslint-plugin-react-hooks** that enforces these two rules. You can add this plugin to your project using the below command,


```
npm install eslint-plugin-react-hooks@next

```

And apply the below config in your ESLint config file,


```
// Your ESLint configuration
{
  "plugins": [
    // ...
    "react-hooks"
  ],
  "rules": {
    // ...
    "react-hooks/rules-of-hooks": "error"
  }
}

```

**Note:** This plugin is intended to use in Create React App by default.

[

---

### How would you build a custom hook library?

A custom hook library is a collection of reusable hooks. Steps: 1.
Design hooks with clear APIs, handling edge cases. 2. Write them as pure
functions that follow the Rules of Hooks. 3. Document with examples and
TypeScript types. 4. Publish to npm or a private registry. 5. Include
tests (React Testing Library) and ensure they work across versions.

------------------------------------------------------------------------

---

## React Performance & Concurrent Features

---

### Implement a custom hook like `useDebounce` or `useFetch` (React).

**`useDebounce`**:

``` javascript
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

``` javascript
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

------------------------------------------------------------------------

---

---

### Is Hooks cover all use cases for classes?

Hooks doesn't cover all use cases of classes but there is a plan to add them soon. Currently there are no Hook equivalents to the uncommon **getSnapshotBeforeUpdate** and **componentDidCatch** lifecycles yet.

[

---

### Situation: `useEffect` runs infinitely – what's wrong?

Most likely a dependency that changes on every render: an object/array created inline (`{} !== {}` every render), or a function without `useCallback`. Fix: memoize the dependency, move it outside the component, or restructure state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are Custom Hooks?

A Custom Hook is a function in Javascript whose name begins with ‘use’ and which calls other hooks. It is a part of React v16.8 hook update and permits you for reusing the stateful logic without any need for component hierarchy restructuring.

    In almost all of the cases, custom hooks are considered to be sufficient for replacing render props and HoCs (Higher-Order components) and reducing the amount of nesting required. Custom Hooks will allow you for avoiding multiple layers of abstraction or wrapper hell that might come along with Render Props and HoCs.

    The **disadvantage** of Custom Hooks is it cannot be used inside of the classes.

    ## React Interview Questions for Experienced

---

### What are Custom React Hooks, and How Can You Develop One?

**Custom Hooks** in React are JavaScript functions that allow you to
**extract and reuse component logic** using React's built-in Hooks like
`useState`, `useEffect`, etc.

      They start with the word **"use"** and let you encapsulate logic that multiple components might share—such as fetching data, handling forms, or managing timers—without repeating code.

      Let's explain the custom hook usage with `useFetchData` example. The `useFetchData` custom Hook is a reusable function in React that simplifies the process of fetching data from an API. It encapsulates common logic such as initiating the fetch request, managing loading and error states, and storing the fetched data. By using built-in Hooks like `useState` and `useEffect`, `useFetchData` provides a clean interface that returns the `data`, `loading`, and `error` values, which can be directly used in components.

      ```jsx
      import { useState, useEffect } from 'react';

      function useFetchData(url) {
        const **

309. ### How does React Fiber works? Explain in detail.

     React Fiber is the **core engine** that enables advanced features
     like **concurrent rendering**, **prioritization**, and
     **interruptibility** in React. Here's how it works:

     \### 1. **Fiber Tree Structure**

     Each component in your app is represented by a **Fiber node** in a
     tree structure. A Fiber node contains:

     -   Component type
     -   Props & state
     -   Pointers to parent, child, and sibling nodes
     -   Effect tags to track changes (e.g., update, placement)
     -   This forms the **Fiber Tree**, a data structure React uses
         instead of the traditional call stack.

     \### 2. **Two Phases of Rendering**

     \#### **A. Render Phase (work-in-progress)**

     -   React builds a **work-in-progress Fiber tree**.

     -   It walks through each component (begin phase), calculates what
         needs to change, and collects side effects (complete phase).

     -   This phase is **interruptible**---React can pause it and resume
         later. \#### **B. Commit Phase**

     -   React applies changes to the **Real DOM**.

     -   Runs lifecycle methods (e.g., `componentDidMount`,
         `useEffect`).

     -   This phase is **non-interruptible** but fast.

     \### 3. **Work Units and Scheduling**

     -   React breaks rendering into **units of work** (small tasks).
     -   These units are scheduled based on **priority** using the
         **React Scheduler**.
     -   If time runs out (e.g., user starts typing), React can **pause
         and yield** control back to the browser.

     \### 4. **Double Buffering with Two Trees**

     -   React maintains two trees:
     -   **Current Tree** -- what's visible on the screen.
     -   **Work-In-Progress Tree** -- the next version being built in
         memory.
     -   Only after the new tree is fully ready, React **commits** it,
         making it the new current tree.

     \### 5. **Concurrency and Prioritization**

     -   React can prepare multiple versions of UI at once (e.g., during
         slow data loading).
     -   Updates can be **assigned priorities**, so urgent updates (like
         clicks) are handled faster than background work.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are hooks?

Hooks is a new feature(React 16.8) that lets you use state and other React features without writing a class.

Let's see an example of useState hook example,


```
import { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}

```

[

---

### What are stale closures in `useEffect`?

When an effect captures a variable from a previous render. If the dependency array is incomplete, the effect uses the old value. Fix: add the variable to deps, or use a ref to always access the latest value.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are the best practices for using React Hooks?

Following best practices ensures your hooks are predictable,
maintainable, and bug-free.

     #### 1. **Follow the Rules of Hooks**
     - Only call hooks at the top level (not inside loops, conditions, or nested functions)
     - Only call hooks from React functions (components or custom hooks)

     #### 2. **Use the ESLint Plugin**
     ```bash
     npm install eslint-plugin-react-hooks --save-dev
     ```
     ```json
     {
       "plugins": **

---

---

### What are the common usecases of useRef hook?

Some of the common cases are: \* Automatically focus an input when a
component mounts. \* Scroll to a specific element. \* Measure element
dimensions (`offsetWidth`, `clientHeight`). \* Control video/audio
playback. \* Integrate with non-React libraries (like D3 or jQuery).

------------------------------------------------------------------------

301. ### What is useImperativeHandle Hook? Give an example.

     `useImperativeHandle` is a React Hook that allows a **child
     component** to expose **custom functions or properties** to its
     **parent component**, when using `ref`. It is typically used with
     `forwardRef` and is very useful in cases like **modals**,
     **dialogs**, **custom inputs**, etc., where the parent needs to
     **control behavior imperatively** (e.g., open, close, reset).

     **Example: Dialog component** \`\`\`js import React, { useRef,
     useState, useImperativeHandle, forwardRef, } from 'react'; import
     './Dialog.css';

     const Dialog = forwardRef((props, ref) =\> { const \*\*

------------------------------------------------------------------------

---

---

### What are the rules needs to follow for hooks?

You need to follow two rules in order to use hooks,

1. Call Hooks only at the top level of your react functions. i.e, You shouldn’t call Hooks inside loops, conditions, or nested functions. This will ensure that Hooks are called in the same order each time a component renders and it preserves the state of Hooks between multiple useState and useEffect calls.
2. Call Hooks from React Functions only. i.e, You shouldn’t call Hooks from regular JavaScript functions.

[

---

### What are the Rules of Hooks?

1. Only call hooks at the top level – not inside conditions, loops, or nested functions.
2. Only call hooks from React function components or custom hooks.

These rules ensure hooks are called in the same order every render.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are the rules that must be followed while using React Hooks?

There are 2 rules which must be followed while you code with Hooks:

    - React Hooks must be called only at the top level. It is not allowed to call them inside the nested functions, loops, or conditions.
    - It is allowed to call the Hooks only from the React Function Components.

---

### What are the sources used for introducing hooks?

Hooks got the ideas from several different sources. Below are some of
them,

     1. Previous experiments with functional APIs in the react-future repository
     2. Community experiments with render prop APIs such as Reactions Component
     3. State variables and state cells in DisplayScript.
     4. Subscriptions in Rx.
     5. Reducer components in ReasonReact.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is a hook?

Hooks are functions that let you 'hook into' React state and lifecycle
features from function components. Rules: (1) Only call hooks at the top
level --- not inside loops, conditions, or nested functions. (2) Only
call hooks from React function components or custom hooks. Common
built-in hooks: useState, useEffect, useContext, useRef, useMemo,
useCallback, useReducer. Custom hooks are functions starting with 'use'
that compose built-in hooks for reusable stateful logic.

------------------------------------------------------------------------

---

---

### What is a hook? Why were hooks introduced?

Hooks are functions that let you "hook into" React state and lifecycle
features from functional components. They were introduced in React 16.8
to allow using state, side effects, and other React features without
writing classes.

Reasons for hooks: - Reuse stateful logic across components without
complex patterns like HOCs or render props. - Simplify component logic
by grouping related code (e.g., `useEffect` for side effects). - Avoid
the complexity of `this` binding and class lifecycle methods. - Improve
tree‑shaking and reduce bundle size.

------------------------------------------------------------------------

---

---

### What is lazy initialization in `useState`?

`useState(() => expensiveCalc())` passes a function so the initial value is computed only once (on mount), not on every render. Useful for reading from `localStorage` or parsing data.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is React Hooks?

React Hooks are the built-in functions that permit developers for using the state and lifecycle methods within React components. These are newly added features made available in React 16.8 version. Each lifecycle of a component is having 3 phases which include mount, unmount, and update. Along with that, components have properties and states. Hooks will allow using these methods by developers for improving the reuse of code with higher flexibility navigating the component tree.

    Using Hook, all features of React can be used without writing class components. ***For example***, before React version 16.8, it required a class component for managing the state of a component. But now using the useState hook, we can keep the state in a functional component.

---

### What is React.memo? How is it different from useMemo and useCallback?

Remember: React.memo works from outside, i.e, the props, and useMemo/useCallback work inside the component.

    You know how in React, whenever a component re-renders, all of its child components also re-render by default. And sometimes, this entire step becomes unnecessary.

    To prevent it from happening, we use the above three: React.memo, useMemo, & useCallback.

    But how are they different? Let me explain!

    **React.memo**

    It is an HOC (higher-order component) that is used to optimize performance and prevent a component from re-rendering if its props haven’t changed.

    In this case, React checks to see if the props are the same as before,

    - If yes, it skips render
    - If no, then re-render

    This comes in use a lot when a component ends up receiving the same data again and again. (becomes quite inconvenient!)

    But you should be careful,

    Even if the data looks the same, React may still think it changed.

    For example:

\<Child user={{ name: "Kamala" }} /\>


    Here, a new object is created every time, so React thinks props have changed, and then a re-render happens.

    Now, to prevent this from happening, we use: useMemo & useCallback

    **a.** **useMemo** stores/memorizes a value, so it doesn’t get recreated on every render.

    Eg:

const user = useMemo(() =\> ({ name: "Kamala" }), \[\]);


    Now the same object is reused, and React.memo can work properly.

    **b. useCallback** is similar, but for functions.

    Eg:

     

const handleClick = useCallback(() =\> { console.log("clicked"); },
\[\]);


    Without this, a new function is created every render, which can also break React.memo.

    You might be asked as a follow-up if a component wrapped in React.memo still re-renders, then what’s the problem. You can answer this by listing errors, such as if Parent passes inline objects/functions, or the component consumes context.

---

### What is the difference between useEffect and useLayoutEffect?

Both useEffect and useLayoutEffect run after React updates the DOM.

    But here’s how they both differ:

    1\. useEffect runs after the browser has painted the update. So the user already sees the UI change, and then your effect runs in the background.

    This is why it’s non-blocking and used for things like API calls, subscriptions, and logging.

    Here,

     

useEffect(() =\> { console.log("runs after paint"); });


    2\. useLayoutEffect runs before the browser paints.

    So React updates the DOM, then your effect runs, and only after that does the browser show anything.

    Like this:

     

useLayoutEffect(() =\> { console.log("runs before paint"); });


    Because of this, it is synchronous and blocks the UI until it finishes.

    So, how do they come in use?

    Imagine that you need to measure an element’s size or adjust its position,

    If you use useEffect, the browser will first show the UI, and then your adjustment happens. Also, remember that this can cause a visible flicker.

    With useLayoutEffect, the adjustment happens before anything is shown, so the user never sees that intermediate state.

    Now, which one is best to use when?

    - useEffect, in most cases!
    - useLayouteffect, only when you need to make visual changes before the screen updates

    Here’s what they can ask as a follow-up in interviews:

    Q. When can useLayoutEffect hurt performance?

    Your ans: Since it blocks painting, heavy or slow logic inside it can delay rendering and make the UI feel laggy.

    ## React MCQ Questions

    1\.

     \_\_\_\_\_\_ is a necessary API for every React.js component.

    renderComponent

    render

    SetinitialComponent

    All of the above

    2\.

    React is mainly used for developing \_\_\_\_\_\_.

    Connectivity

    Database

    User interface

    Design platform

    3\.

    The Keys given to a list of elements in React should be \_\_\_\_\_\_.

    Not necessarily unique

    Unique among the siblings only

    Unique in the DOM (Document Object Model)

    None of the above

    4\.

    The number of elements that can be returned by a valid React component is \_\_\_\_\_\_.

    5

    1

    3

    2

    5\.

    What are the ReactJS limitations?

    React will use inline templating and JSX which might seem awkward to a few developers

    ReactJS is only for the view layer of the application, which means we will make use of other technologies as well for getting complete tooling set for the application development

    The React library is too large

    All of these

    6\.

    What function will permit for rendering the React content in an HTML page?

    React.render()

    ReactDOM.start()

    React.mount()

    ReactDOM.render()

    7\.

    What is meant by the state in React?

    Internal storage of component

    External storage of component

    Permanent storage

    None of the above

    8\.

    What is React or ReactJS?

    Component-based Javascript library

    Javascript framework

    Javascript file

    None of the above

    9\.

    What is the declarative approach for rendering a dynamic list of components depending on array values?

    Using \<Each/> component

    Using reduce array method

    Using Array.map() method

    Using for or while loop

    10\.

    What is the usage of setState?

    Replacing the state fully instead of the default merge action

    Accessing the earlier state before the setState operation

    Invoking the code after the setState operation is performed

    None of these

    11\.

    What is used for passing the data to a component from outside?

    Render with arguments

    setState

    PropTypes

    props

    12\.

    Which command can be used for the creation of React app?

    npm install create-react-app

    install -g create-react-app

    npm install -g create-react-app

    None of the above

    13\.

    Which of the following comes under the advantages of React?

    Integration with other frameworks (like BackboneJS, Angular, etc.) becomes easier because it is only a view library

    Increases the performance of an application using Virtual DOM

    Can render both on server and client side

    All of the above

    14\.

    Which of the following statements related to the “webpack” command is true?

    It runs React local development server

    It is used to transpile all the JavaScript into a single file

    It is a module bundler

    None of the above

    15\.

    \_\_\_\_\_\_ will help to keep the data unidirectional in React.

    Dom

    Props

    JSX

    Flux

---

### What is the difference between useMemo and React.memo?

React.memo is a HOC (Higher Order Component) that memoizes an entire
component --- prevents re-render if props haven't changed (shallow
comparison). useMemo is a hook that memoizes a computed value inside a
component. Use React.memo on child components that receive stable props
and render expensively. Use useMemo for expensive calculations within a
component. They work together: React.memo stops the component from
re-rendering, useMemo stops expensive recalculations inside.

------------------------------------------------------------------------

---

---

### What is the difference between useState and useRef hook?

1.  useState causes components to re-render after state updates whereas
    useRef doesn't cause a component to re-render when the value or
    state changes. Essentially, useRef is like a "box" that can hold a
    mutable value in its (`.current`) property.
    2.  useState allows us to update the state inside components. While
        useRef allows referencing DOM elements and tracking values.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the `eslint-plugin-react-hooks` plugin?

Enforces Rules of Hooks: 'rules-of-hooks' (hooks only in function
components/custom hooks) and 'exhaustive-deps' (all effect dependencies
declared). Install in every React project.

------------------------------------------------------------------------

---

---

### What is the order of hook execution in a component?

Hooks run top-to-bottom on every render in the same order. React relies
on call order to associate hook state with the correct hook -- this is
why hooks cannot be inside conditionals or loops. Think of React hooks
like a numbered seating chart at a wedding.

React doesn't remember your hooks by their actual names; it only tracks
them by the exact order (seat number) they appear in your code.

How it Works Render 1: React notes that Seat 1 is a useState for a
username, and Seat 2 is a useEffect for fetching data.

Render 2: React expects the exact same setup. It goes to Seat 1, grabs
the username state, goes to Seat 2, and runs the effect.

Why Hooks Can't Be in if Statements or Loops If you hide a hook inside
an if condition, and that condition turns false, that hook doesn't run.

The Disaster: The hook in Seat 2 disappears. The hook that used to be in
Seat 3 slides over into Seat 2. React gets totally confused and hands
the wrong data to the wrong hook, crashing your app.

------------------------------------------------------------------------

---

---

### What is the purpose of eslint plugin for hooks?

The ESLint plugin enforces rules of Hooks to avoid bugs. It assumes that any function starting with ”use” and a capital letter right after it is a Hook. In particular, the rule enforces that,

1. Calls to Hooks are either inside a PascalCase function (assumed to be a component) or another useSomething function (assumed to be a custom Hook).
2. Hooks are called in the same order on every render.

[

---

### What is the stable release for hooks support?

React includes a stable implementation of React Hooks in 16.8 release for below packages

1. React DOM
2. React DOM Server
3. React Test Renderer
4. React Shallow Renderer

[

---

### What is the use of useEffect React Hooks?

The useEffect React Hook is used for performing the side effects in functional components. With the help of useEffect, you will inform React that your component requires something to be done after rendering the component or after a state change. The function you have passed(can be referred to as “effect”) will be remembered by React and call afterwards the performance of DOM updates is over. Using this, we can perform various calculations such as data fetching, setting up document title, manipulating DOM directly, etc, that don’t target the output value. The useEffect hook will run by default after the first render and also after each update of the component. React will guarantee that the DOM will be updated by the time when the effect has run by it.

    The useEffect React Hook will accept 2 arguments: `useEffect(callback,[dependencies]);`

    Where the first argument callback represents the function having the logic of side-effect and it will be immediately executed after changes were being pushed to DOM. The second argument dependencies represent an optional array of dependencies. The useEffect() will execute the callback only if there is a change in dependencies in between renderings.

    **Example:**

import { useEffect } from 'react'; function WelcomeGreetings({ name }) {
const msg = `Hi, ${name}!`; // Calculates output useEffect(() =\> {
document.title = `Welcome to you ${name}`; // Side-effect! }, \[name\]);
return

<div>

{msg}

</div>

; // Calculates output }


    The above code will update the document title which is considered to be a side-effect as it will not calculate the component output directly. That is why updating of document title has been placed in a callback and provided to useEffect().

    Consider you don’t want to execute document title update each time on rendering of WelcomeGreetings component and you want it to be executed only when the name prop changes then you need to supply name as a dependency to `useEffect(callback, [name])`.

---

### What is the use() hook in React 19?

The `use()` hook allows you to read the value of a resource (Promise or
Context) during render, with Suspense integration.

     #### Reading Promises
     ```jsx
     import { use, Suspense } from 'react';

     function UserProfile({ userPromise }) {
       const user = use(userPromise); // Suspends until resolved
       
       return (
         <div>
           <h1>{user.name}</h1>
           <p>{user.email}</p>
         </div>
       );
     }

     function App() {
       const userPromise = fetchUser(123);
       
       return (
         <Suspense fallback={<div>Loading...</div>}>
           <UserProfile userPromise={userPromise} />
         </Suspense>
       );
     }
     ```

     #### Reading Context
     ```jsx
     import { use } from 'react';
     import { ThemeContext } from './context';

     function Button() {
       const theme = use(ThemeContext);
       return <button className={theme}>Click me</button>;
     }
     ```

     #### Key Differences from Other Hooks

     | Feature | use() | useContext() | useState() |
     |---------|-------|--------------|------------|
     | Can be called conditionally | ✅ Yes | ❌ No | ❌ No |
     | Can be called in loops | ✅ Yes | ❌ No | ❌ No |
     | Suspends for Promises | ✅ Yes | ❌ N/A | ❌ N/A |
     | Reads Context | ✅ Yes | ✅ Yes | ❌ N/A |

     #### Conditional Usage (Unique!)
     ```jsx
     function Component({ showUser, userPromise }) {
       // ✅ This is allowed with use()!
       const user = showUser ? use(userPromise) : null;
       
       return user ? <div>{user.name}</div> : <div>No user</div>;
     }
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the useDebugValue hook?

The `useDebugValue` hook is used to **display a label** for custom hooks
in **React DevTools**. It helps developers debug custom hooks by showing
meaningful information.

     #### Syntax
     ```js
     useDebugValue(value);
     useDebugValue(value, formatFn); // With optional formatter
     ```

     #### Example: Custom Hook with Debug Value
     ```jsx
     import { useState, useEffect, useDebugValue } from 'react';

     function useOnlineStatus() {
       const **

------------------------------------------------------------------------

---

---

### What is the useDeferredValue hook?

The `useDeferredValue` hook is used to **defer updating a part of the
UI** to keep other parts responsive. It accepts a value and returns a
"deferred" version of that value that may lag behind. This is useful for
optimizing performance when rendering expensive components.

     #### Syntax
     ```js
     const deferredValue = useDeferredValue(value);
     ```

     #### Example: Search with Deferred Results
     ```jsx
     import { useState, useDeferredValue, useMemo } from 'react';

     function SearchResults({ query }) {
       // Expensive computation or large list filtering
       const results = useMemo(() => {
         return largeDataSet.filter(item => 
           item.name.toLowerCase().includes(query.toLowerCase())
         );
       }, **

------------------------------------------------------------------------

---

---

### What is the useId hook and when should you use it?

The `useId` hook is a React hook introduced in React 18 that generates
**unique IDs** that are stable across server and client renders. It's
primarily used for **accessibility attributes** like linking form labels
to inputs.

     #### Syntax
     ```js
     const id = useId();
     ```

     #### Example: Accessible Form Input
     ```jsx
     import { useId } from 'react';

     function EmailField() {
       const id = useId();
       
       return (
         <div>
           <label htmlFor={id}>Email:</label>
           <input id={id} type="email" />
         </div>
       );
     }
     ```

---

### What is the useInsertionEffect hook?

The `useInsertionEffect` hook is designed for **CSS-in-JS library
authors** to inject styles into the DOM before any layout effects run.
It fires synchronously before DOM mutations.

     #### Syntax
     ```js
     useInsertionEffect(() => {
       // Insert styles here
       return () => {
         // Cleanup
       };
     }, **

------------------------------------------------------------------------

---

---

### What is the useOptimistic hook?

`useOptimistic` enables optimistic UI updates - showing changes
immediately before server confirmation.

     #### Basic Usage
     ```jsx
     import { useOptimistic } from 'react';

     function TodoList({ todos, addTodo }) {
       const **

------------------------------------------------------------------------

---

---

### What is the useTransition hook and how does it differ from useDeferredValue?

The `useTransition` hook allows you to mark certain state updates as
**non-urgent transitions**, keeping the UI responsive during expensive
re-renders. It returns a `isPending` flag and a `startTransition`
function.

     #### Syntax
     ```js
     const **

------------------------------------------------------------------------

---

---

### What is the `useTransition` hook for performance?

Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useCallback` and why is it used?

The `useCallback` is a React Hook used to memoize **function
definitions** between renders. It returns the same function reference
unless its dependencies change. This is especially useful when passing
callbacks to optimized child components (e.g. those wrapped in
`React.memo`) to prevent unnecessary re-renders.

        **Example:**
        
        ```css
        const handleClick = useCallback(() => {
          console.log('Button clicked');
        }, **

------------------------------------------------------------------------

---

---

### What is `useDebugValue`?

Used inside custom hooks to display a label in React DevTools. Helps identify what a custom hook is doing when inspecting components. The second argument is a formatting function called only in DevTools.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useDeferredValue`?

Accepts a value and returns a deferred copy that trails behind during heavy renders. UI stays responsive with the current value while React concurrently renders the expensive output with the new value.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useEffect`?

Runs side effects after render (data fetching, subscriptions, DOM manipulation). Dependency array controls when it runs: `[]` → once on mount; `[a,b]` → when a or b changes; omitted → every render.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useImperativeHandle`?

Customizes the ref value exposed when `forwardRef` is used. Lets a parent call specific methods on a child (e.g., `child.focus()`) without exposing the entire DOM node or component internals.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useLayoutEffect`?

Same signature as `useEffect` but fires synchronously after DOM mutations and before browser paint. Use for: reading layout (scroll position, dimensions) and synchronously updating the DOM to avoid flicker.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useMemo`?

Memoizes the result of an expensive computation. Re-computes only when dependencies change. Use for: heavy calculations, creating stable object/array references, derived data from props.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useOptimistic` (React 19)?

Shows an optimistic state update immediately while an async action is
pending. When the action completes (or fails), React reverts to the
actual state. Provides smooth UX without complex manual state
management.

------------------------------------------------------------------------

---

---

### What is `useRef`?

Returns a mutable `{current}` object that persists across renders without triggering re-renders. Two main uses: (1) accessing DOM nodes directly, (2) storing instance variables like timers or previous values.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is `useState`?

Declares state in a functional component. Returns `[value, setter]`. The setter schedules a re-render with the new value. Multiple `useState` calls are independent.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is useState() in React?

The useState() is a built-in React Hook that allows you for having state variables in functional components. It should be used when the DOM has something that is dynamically manipulating/controlling.

In the below-given example code, The useState(0) will return a tuple where the count is the first parameter that represents the counter’s current state and the second parameter setCounter method will allow us to update the state of the counter.

```
...
const [count, setCounter] = useState(0);
const [otherStuffs, setOtherStuffs] = useState(...);
...
const setCount = () => {
   setCounter(count + 1);
   setOtherStuffs(...);
   ...
};
```

We can make use of setCounter() method for updating the state of count anywhere. In this example, we are using setCounter() inside the setCount function where various other things can also be done. The idea with the usage of hooks is that we will be able to keep our code more functional and avoid class-based components if they are not required.

---

### What is `useTransition`?

Hook version of `startTransition`. Returns `[isPending, startTransition]`. `isPending` is true while the transition is rendering. Use it to show loading spinners without setting separate loading state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What problems does `useMemo` actually solve? When should you NOT use it?

`useMemo` solves unnecessary recomputation of expensive calculations on every render. It also helps maintain referential equality for objects/arrays that are dependencies of other hooks (like `useEffect`).

**When NOT to use it**:
- For trivial calculations (e.g., `a + b`); the overhead of memoization may exceed the cost.
- Over‑using `useMemo` can make code less readable and lead to bugs if dependencies are mishandled.
- It does not guarantee that the value won’t be recomputed if React decides to re‑mount the component (e.g., during memory pressure).

---

### What rules need to be followed for hooks?

You need to follow two rules in order to use hooks,

         1. **Call Hooks only at the top level of your react functions:** You should always use hooks at the top level of react function before any early returns. i.e, You shouldn’t call Hooks inside loops, conditions, or nested functions. This will ensure that Hooks are called in the same order each time a component renders and it preserves the state of Hooks between multiple re-renders due to `useState` and `useEffect` calls.

         Let's see the difference using an example,
         **Correct usage:**:
         ```jsx
         function UserProfile() {
          // Correct: Hooks called at the top level
          const **

---

### When and how often does React invoke the setup and cleanup functions inside a useEffect hook?

1.  **Setup Function Execution (`useEffect`)**

          The setup function (or the main function) you pass to `useEffect` runs at specific points:

            1.  **After the component is mounted** (if the dependency array is empty `**

------------------------------------------------------------------------

---

---

### Why do React Hooks make use of refs?

Earlier, refs were only limited to class components but now it can also be accessible in function components through the useRef Hook in React.

    The refs are used for:

    - Managing focus, media playback, or text selection.
    - Integrating with DOM libraries by third-party.
    - Triggering the imperative animations.

---

### Why do we use array destructuring (square brackets notation) in `useState`?

When we declare a state variable with `useState`, it returns a pair — an array with two items. The first item is the current value, and the second is a function that updates the value. Using [0] and [1] to access them is a bit confusing because they have a specific meaning. This is why we use array destructuring instead.

For example, the array index access would look as follows:


```
var userStateVariable = useState('userProfile'); // Returns an array pair
var user = userStateVariable[0]; // Access first item
var setUser = userStateVariable[1]; // Access second item

```

Whereas with array destructuring the variables can be accessed as follows:


```
const [user, setUser] = useState('userProfile');

```

[

---

### Why use functional updates with `useState`?

`setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### ❓ What is the difference between useEffect, useLayoutEffect, and useInsertionEffect?

**Answer:** useEffect: runs AFTER paint (asynchronous) — doesn't block browser from painting. Good for: data fetching, subscriptions, analytics. useLayoutEffect: runs synchronously AFTER DOM mutations but BEFORE paint — blocks painting. Use when you need to read/write DOM layout (element size/position) to avoid visual flicker. useInsertionEffect: runs BEFORE DOM mutations — specifically for CSS-in-JS libraries to inject styles before any layout effects read styles. Hierarchy: useInsertionEffect → DOM mutations → useLayoutEffect → paint → useEffect.

---

### ❓ What is the difference between useMemo and useCallback?

**Answer:** useMemo memoizes the RESULT of a computation — returns cached value until deps change. Use for expensive calculations. useCallback memoizes a FUNCTION DEFINITION — returns same function reference until deps change. Use when passing callbacks to memoized child components. Key distinction: useMemo = memo(fn()), useCallback = memo(fn). When NOT to use useMemo: (1) simple calculations where memoization overhead exceeds savings. (2) Values that change on every render anyway. Overusing them adds memory and comparison overhead.

---

## Performance & Concurrent React

### A React component re-renders again and again but you never called setState. Why?

Multiple causes are possible:

    Parent re-render: parent's state/props changed, triggering all children to re-render
    Inline objects/arrays as props: {} or [] creates new reference on every render
    Inline functions as props: () => {} creates new function instance each render
    Context value changed: if consuming a Context that updates frequently
    Custom hook with unstable return values causing cascading updates
    useEffect with missing/incorrect deps triggering setState in a loop

---

### Can you force a component to re-render without calling setState?

By default, when your component's state or props change, your component
will re-render. If your `render()` method depends on some other data,
you can tell React that the component needs re-rendering by calling
`forceUpdate()`.

    ```javascript
    component.forceUpdate(callback);
    ```

    It is recommended to avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`.

    ****

------------------------------------------------------------------------

---

---

### CPU vs memory bottlenecks – how to identify and fix?

**CPU bottlenecks** – JavaScript execution causing long tasks, jank, high CPU usage.
- **Identify**: Chrome DevTools Performance tab; look for long “Script” tasks.
- **Fix**: Code splitting, Web Workers for heavy computations, throttle/debounce event handlers, use `useTransition` to prioritize UI updates, avoid expensive renders.

**Memory bottlenecks** – Leaks causing growing memory consumption, eventual slowdown or crash.
- **Identify**: Memory tab, take heap snapshots; compare after user actions to see retained objects.
- **Fix**: Clean up event listeners, intervals, WebSocket connections; avoid retaining large data in closures; use weak references (`WeakMap`, `WeakSet`) for caching; unmount components properly; use `useEffect` cleanup.

---

### Edge caching vs CDN caching strategies.

- **Edge caching** (also often provided by CDNs) caches static assets at edge locations (points of presence) close to users. Typically for static files (JS, CSS, images). You can configure cache headers (`Cache-Control`) and invalidation strategies.
- **CDN caching** can also cache dynamic responses (HTML) using strategies like “stale‑while‑revalidate” to serve stale content while refreshing in the background. Useful for SSR pages.
- **Strategies**:
  - Use `Cache-Control: public, max-age=31536000, immutable` for versioned assets.
  - For HTML, use `s-maxage` and `stale-while-revalidate` for CDNs.
  - Use surrogate keys to purge specific resources.

---

---

### Design an Image Gallery with lazy loading and skeleton placeholders.

**Requirements**: Grid of images, load as user scrolls, show skeleton while loading.

**Design**:
- **Lazy loading**: Use `IntersectionObserver` to set `src` when image enters viewport. Fallback `loading="lazy"` for simpler.
- **Skeletons**: Show a placeholder div with the same dimensions (aspect ratio) and a pulse animation.
- **Responsive**: Use CSS Grid or flex with `object-fit: cover`.
- **Error handling**: On error, show broken image icon.
- **Performance**: Use `srcset` for responsive images, WebP format.

---

### How do you balance performance vs feature delivery?

Framework: performance is a feature, not a tax. Approach: (1) Establish performance budgets upfront (e.g., LCP < 2.5s, bundle size < 200KB). (2) Automate performance checks in CI — fail builds that regress metrics. (3) Address performance debt in dedicated sprints, not as afterthoughts. (4) Use data: is this optimization worth the effort? (5) Good software design (proper abstractions, avoiding premature optimization) often prevents performance issues. (6) When deadlines force trade-offs, document the debt and schedule payback.

---

### How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)

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

------------------------------------------------------------------------

---

---

### How do you detect and prevent memory leaks in long-running SPAs?

**Detection**:
- Use Chrome DevTools Memory tab: take heap snapshots before and after a series of user actions that should free memory.
- Look for retained objects that are no longer needed (e.g., detached DOM elements, large arrays).
- Use `performance.memory` (Chrome) to monitor memory usage over time.
- Use the “Performance monitor” to watch JS heap size.

**Prevention**:
- Always clean up `setInterval`/`setTimeout` in `useEffect` cleanup.
- Remove event listeners in cleanup.
- Cancel subscriptions (WebSocket, fetch with AbortController) on unmount.
- Avoid storing large data in global variables or closures that persist.
- Use `useRef` for values that shouldn’t cause re‑renders but be cautious about holding references.
- For caches, use `WeakMap`/`WeakSet` to allow garbage collection when keys are no longer referenced.
- Profile your app after implementing cleanup to ensure no accumulation.

---

### How do you ensure a React app performs well at 100k users?

CDN for static assets. SSR/SSG for fast initial loads. Aggressive
caching (React Query, HTTP cache headers). Server-side pagination, never
load all data. Code splitting per route. Error boundaries everywhere.
Monitoring and alerting from day one.

------------------------------------------------------------------------

---

---

### How do you measure and fix excessive re-renders?

Use React DevTools 'Highlight Updates' to spot components re-rendering. Record a Profiler session to see flame charts. Then: add `React.memo`, split context, move state closer to usage, or batch updates.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you memoize a component?

There are memoize libraries available which can be used on function
components.

    For example `moize` library can memoize the component in another component.

    ```jsx harmony
    import moize from "moize";
    import Component from "./components/Component"; // this module exports a non-memoized component

    const MemoizedFoo = moize.react(Component);

    const Consumer = () => {
      <div>
        {"I will memoize the following entry:"}
        <MemoizedFoo />
      </div>;
    };
    ```

    **Update:** Since React v16.6.0, we have a `React.memo`. It provides a higher order component which memoizes component unless the props change. To use it, simply wrap the component using React.memo before you use it.

    ```js
    const MemoComponent = React.memo(function MemoComponent(props) {
      /* render using props */
    });
    OR;
    export default React.memo(MyFunctionComponent);
    ```

    ****

------------------------------------------------------------------------

---

## React Context & Component Patterns

---

### How does the Virtual DOM improve performance?

Real DOM mutations are expensive (layout, paint, composite). React
batches changes and applies minimal updates. The diffing algorithm is
O(n) using heuristics (same type → update; different type → destroy and
replace).

------------------------------------------------------------------------

---

---

### How to focus an input element on page load?

You need to use `useEffect` hook to set focus on input field during page load time for functional component.

        ```jsx harmony
        import React, { useEffect, useRef } from "react";

        const App = () => {
          const inputElRef = useRef(null);

          useEffect(() => {
            inputElRef.current.focus();
          }, **

---

### How to prevent re-renders in React?

-   **Reason for re-renders in React:**
    -   Re-rendering of a component and its child components occur when
        props or the state of the component has been changed.
    -   Re-rendering components that are not updated, affects the
        performance of an application.
-   **How to prevent re-rendering:**

Consider the following components:

    class Parent extends React.Component {
    state = { messageDisplayed: false };
    componentDidMount() {
      this.setState({ messageDisplayed: true });
    }
    render() {
      console.log("Parent is getting rendered");
      return (
        <div className="App">
          <Message />
        </div>
      );
    }
    }
    class Message extends React.Component {
    constructor(props) {
      super(props);
      this.state = { message: "Hello, this is vivek" };
    }  
    render() {
      console.log("Message is getting rendered");
      return (
        <div>
          <p>{this.state.message}</p>
        </div>
      );
    }
    }

-   The** Parent** component is the parent component and
    the **Message** is the child component. Any change in the parent
    component will lead to re-rendering of the child component as well.
    To prevent the re-rendering of child components, we use the
    shouldComponentUpdate( ) method:

> \*\*Note- Use shouldComponentUpdate( ) method only when you are sure
> that it's a static component.

    class Message extends React.Component {
    constructor(props) {
      super(props);
      this.state = { message: "Hello, this is vivek" };
    }
    shouldComponentUpdate() {
      console.log("Does not get rendered");
      return false;
    }
    render() {
      console.log("Message is getting rendered");
      return (
        <div>
          <p>{this.state.message}</p>
        </div>
      );
    }
    }

As one can see in the code above, we have returned **false** from the
shouldComponentUpdate( ) method, which prevents the child component from
re-rendering.

------------------------------------------------------------------------

---

---

### How to re-render the view when the browser is resized?

It is possible to listen to the resize event
in **componentDidMount()** and then update the width and height
dimensions. It requires the removal of the event listener in
the **componentWillUnmount()** method.

Using the below-given code, we can render the view when the browser is
resized.

    class WindowSizeDimensions extends React.Component {
     constructor(props){
       super(props);
       this.updateDimension = this.updateDimension.bind(this);
     }
      
     componentWillMount() {
       this.updateDimension()
     }
     componentDidMount() {
       window.addEventListener('resize', this.updateDimension)
     }
     componentWillUnmount() {
       window.removeEventListener('resize', this.updateDimension)
     }
     updateDimension() {
       this.setState({width: window.innerWidth, height: window.innerHeight})
     }
     render() {
       return <span>{this.state.width} x {this.state.height}</span>
     }
    }

------------------------------------------------------------------------

---

---

### How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)

**Web Workers** – offload data processing, sorting, filtering, or any CPU‑intensive task to a background thread.
- The worker processes the dataset and returns a result (e.g., filtered list) to the main thread.
- The main thread remains responsive for UI updates.

**Virtualization** – as described, reduces the number of DOM nodes, so the main thread has less work to do.

**Chunking / Time‑slicing** – break up heavy work into smaller chunks using `setTimeout` or `scheduler.postTask` to allow the browser to handle user interactions in between.

**Streaming / Pagination** – load data incrementally rather than all at once.

**WebAssembly** – if dataset processing is extremely heavy, consider using Wasm for performance (though overkill for most cases).

---

---

### How would you improve Web Vitals (LCP, CLS, INP)?

**Largest Contentful Paint (LCP)** – Largest element painted (usually hero image or text block)  
- Optimize server response time (TTFB) with CDN and caching.
- Prioritize loading of LCP element: use `<link rel="preload">` for LCP images.
- Avoid lazy‑loading the LCP image.
- Minimize render‑blocking resources (CSS/JS) – defer non‑critical scripts.
- Use server‑side rendering or static generation for fast initial paint.

**Cumulative Layout Shift (CLS)** – Unexpected layout shifts  
- Always set explicit `width` and `height` on images, videos, and iframes.
- Reserve space for dynamic content (e.g., using `aspect-ratio` or placeholder skeletons).
- Insert new content (like ads) in a reserved space.
- Avoid injecting UI elements above existing content.

**Interaction to Next Paint (INP)** – Responsiveness to user input  
- Break up long tasks (use `setTimeout` or `scheduler.yield` in React 18+).
- Use `useTransition` for non‑urgent state updates to keep UI responsive.
- Optimize event handlers: avoid heavy work; offload to Web Workers if possible.
- Reduce JavaScript execution time overall (code splitting, tree shaking).

---

---

### How would you optimize a React application rendering 100,000+ items in a list?

Multi-layer approach:

    Virtualization/windowing: use react-window or react-virtual — render only visible rows (~10-20 items), recycle DOM nodes as user scrolls
    Pagination or infinite scroll: load chunks of 20-50 items instead of all at once
    Memoize list items with React.memo to prevent re-renders on unrelated state changes
    Use stable keys — avoid index as key if items can reorder
    Debounce filter/search operations
    Web Workers for heavy sorting/filtering computations off the main thread
    Code splitting: lazy load the list component if not immediately needed

---

### How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)

Rendering 100,000+ DOM nodes at once will severely degrade performance.
The key is to render only what's visible.

**Virtualization / Windowing**\
- Use libraries like `react-window` or `react-virtualized`. They render
only the items that fit in the viewport plus a small buffer. - Example
with `react-window`:
`jsx   import { FixedSizeList as List } from 'react-window';   const Row = ({ index, style }) => <div style={style}>Item {index}</div>;   <List height={600} itemCount={100000} itemSize={35} width={300}>     {Row}   </List>` -
This dramatically reduces DOM nodes and memory usage.

**Pagination**\
- If virtualization is not sufficient or if data comes from an API,
implement pagination (offset-based or cursor) to load data in chunks. -
Combine pagination with virtualization for very large datasets where
loading all data upfront is impractical.

**Optimizations within each row**\
- Use `React.memo` on row components to avoid re‑rendering when props
(e.g., item data) haven't changed. - Avoid inline functions/objects in
row props.

**Measuring and adjusting**\
- Use the React DevTools Profiler to ensure only visible rows re‑render
on scroll.

------------------------------------------------------------------------

---

---

### Name a few techniques to optimize React app performance.

There are many ways through which one can optimize the performance of a React app, let’s have a look at some of them:

    - **Using useMemo( )** -
      - It is a React hook that is used for caching CPU-Expensive functions.
      - Sometimes in a React app, a CPU-Expensive function gets called repeatedly due to re-renders of a component, which can lead to slow rendering.
        useMemo( ) hook can be used to cache such functions. By using useMemo( ), the CPU-Expensive function gets called only when it is needed.
    - **Using React.PureComponent -**
      - It is a base component class that checks the state and props of a component to know whether the component should be updated.
      - Instead of using the simple React.Component, we can use React.PureComponent to reduce the re-renders of a component unnecessarily.
    - **Maintaining State Colocation -**
      - This is a process of moving the state as close to where you need it as possible.
      - Sometimes in React app, we have a lot of unnecessary states inside the parent component which makes the code less readable and harder to maintain. Not to forget, having many states inside a single component leads to unnecessary re-renders for the component.
      - It is better to shift states which are less valuable to the parent component, to a separate component.
    - **Lazy Loading -**
      -  It is a technique used to reduce the load time of a React app. Lazy loading helps reduce the risk of web app performances to a minimum.

---

### Situation: A search input lags as user types -- how do you fix it?

Separate the input state (urgent) from the search results state
(deferred). Use `useDeferredValue` or `useTransition` on the results
update. This lets the input remain responsive while results compute
asynchronously.

------------------------------------------------------------------------

---

---

### What are common React performance optimization techniques? (practical guide)

When you are optimizing performance in React, your primary concern is to always reduce unnecessary re-renders and avoid expensive work. These optimizations should be applied only after identifying actual bottlenecks.

Here are some practical ways that you can use to tackle it:

1\. Prevent unnecessary re-renders - React.memo

React.memo is used to memoize a component so it only re-renders when its props change. This is especially helpful for child components that end up receiving the same props because of the parent updates. This can be particularly effective when you combine it with stable props.

2\. Stabilize props - useCallback, useMemo

- useCallback is used to memoize functions so that new function references are not created on every render, especially when passing callbacks to memoized children.
- useMemo is used to cache the result of expensive computations so they are only recalculated when dependencies change. It should only be used when the computation is actually costly.

3\. Reduce initial load - Code Splitting

Using React.lazy and Suspense, components can be loaded only when you need them instead of bundling everything upfront. This can basically help you with reducing the initial bundle size and improving load time, especially in large applications.

4\. Minimize re-render scope - State Colocation

State should be kept as close as possible to where it is used. Lifting state too high causes more components to re-render unnecessarily. Also, colocating state limits updates to only the relevant parts of the UI.

5\. Optimize large lists - Virtualization

For long lists, libraries like react-window render only the visible items instead of the entire dataset. This significantly reduces DOM nodes and improves rendering performance.

Note - How to approach optimization!

You need to understand that optimization should not be done prematurely.

The correct approach is to use the React DevTools Profiler to identify which components are re-rendering frequently and consuming time, and then apply these techniques selectively.

Now, you are good to go!

## React Modern Patterns & Performance

---

### What are common React performance pitfalls?

Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are React Suspense and React.lazy? How do they enable code splitting?

In React, all components are bundled together and loaded at once. This can slow down the initial load, especially if the app is large. To avoid this from happening, React has an in-built feature that loads components only when they are needed, and this is called code splitting.

    Both React Suspense and React.lazy are used together to implement this code-splitting.

    So if you are importing a component like this:

import Profile from "./Profile";


    You can try writing:

const Profile = React.lazy(() =\> import("./Profile"));


    So that your component doesn’t load immediately, and that it would only download when React tries to render it.

    But there’s something you need to watch out for:

    While the component is loading, React needs to show something on the screen.

    And you can use ‘Suspense’ for that:

     

`<Suspense fallback={<p>`{=html}Loading...
```{=html}
</p>
```
}\> `<Profile />`{=html} `</Suspense>`{=html}


    So what happens is:

    - React tries to render \<Profile />
    - It sees that the component is still loading
    - Rendering is paused for that part
    - The fallback (Loading...) is shown
    - Once the file loads, React renders the actual component

    You can use this at different levels:

    - for entire pages like routes
    - or for smaller parts of the UI

    You can also wrap multiple components in one Suspense, or create separate ones if you want different loading states.

    You should note that in newer React versions, Suspense is also used for things like data fetching and server components.

---

### What are the two ways of formatting in React Intl?

The library provides two ways to format strings, numbers, and dates:

        1.  **Using react components:**

            ```jsx harmony
            <FormattedMessage
              id={"account"}
              defaultMessage={"The amount is less than minimum balance."}
            />
            ```

        2.  **Using an API:**

            ```javascript
            const messages = defineMessages({
              accountMessage: {
                id: "account",
                defaultMessage: "The amount is less than minimum balance.",
              },
            });

            formatMessage(messages.accountMessage);
            ```

    ****

---

### What causes unnecessary re-renders?

New object/array/function references created inline in JSX; context value changing; parent re-rendering; global state updates. Fix: memoize with `React.memo`, `useMemo`, `useCallback`, or restructure state.

---

### What causes unnecessary re-renders in React?

Common causes:

    Parent component re-renders — all children re-render by default
    Inline objects/functions as props — new reference on every render
    Context value changes — all consumers re-render
    State updates higher in the tree than needed
    Missing React.memo on stable pure components
    useEffect triggering setState in a loop (missing deps or infinite loop)

---

### What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)

**Common causes**:
- Parent re‑renders – by default, children re‑render even if props haven’t changed.
- Inline functions/objects passed as props – new references on every render.
- Context changes – any consumer re‑renders when context value changes.
- State updates that don’t change the value but still trigger re‑render (if using setState with new object reference).

**How to avoid**:
- **`React.memo`** – wrap functional components to prevent re‑renders when props (shallow‑compared) don’t change.
- **`useMemo`** – memoize expensive computations or object/array values.
- **`useCallback`** – memoize functions to avoid new references.
- **Colocate state** – move state down to the component that needs it, rather than lifting it unnecessarily high.
- **Splitting context** – break large contexts into smaller ones so consumers only subscribe to what they use.
- **`useReducer` instead of multiple `useState`** – can help group related state updates and reduce re‑renders if implemented with care.

---

---

### What happens if a child uses React.memo() and parent props don't change?

If props are truly unchanged (by shallow comparison), React.memo
prevents the child from re-rendering. However, if the parent passes
inline objects ({}) or inline functions (() =\> {}) as props, these
create new references on every parent render --- making React.memo
ineffective. Solution: wrap objects in useMemo and functions in
useCallback in the parent component to maintain stable references.

------------------------------------------------------------------------

---

---

### What happens if a component wrapped in `memo()` has its own state changes?

The component will still re‑render when its internal state changes,
regardless of `memo`. `React.memo` only controls re‑renders triggered by
parent prop changes. State updates always cause a re‑render of the
component (unless you use other optimizations like `useState` with a
functional update that doesn't change the value).

------------------------------------------------------------------------

---

---

### What happens when a parent re-renders?

All child components re-render by default unless wrapped in `React.memo` or the subtree is stable. Re-rendering means the function runs again; it does not mean the DOM changes – React still diffs before touching the DOM.

---

### What is code splitting?

Splitting the JS bundle into smaller chunks loaded on demand. `React.lazy` + `Suspense` enable component-level splitting. Route-level splitting is most impactful (each route loads only its JS).

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is code splitting and how does React.lazy work internally?

Code splitting breaks the JS bundle into smaller chunks loaded on
demand, improving initial load time. React.lazy(import('./Component'))
creates a lazy component that triggers a dynamic import() when first
rendered. Suspense provides the loading fallback UI while the chunk
downloads. Internally, React.lazy wraps the promise --- during render,
if the promise is pending, React 'throws' it (using Suspense's error
boundary mechanism), shows fallback, and resumes rendering when
resolved. React Router supports route-level splitting natively.

------------------------------------------------------------------------

---

---

### What is code-splitting?

Code-Splitting is a feature supported by bundlers like Webpack and Browserify which can create multiple bundles that can be dynamically loaded at runtime. The react project supports code splitting via dynamic import() feature.

         For example, in the below code snippets, it will make moduleA.js and all its unique dependencies as a separate chunk that only loads after the user clicks the 'Load' button.

         **moduleA.js**

         ```javascript
         const moduleA = "Hello";

         export { moduleA };
         ```

         **App.js**

         ```javascript
         export default function App {
           function handleClick() {
             import("./moduleA")
               .then(({ moduleA }) => {
                 // Use moduleA
               })
               .catch((err) => {
                 // Handle failure
               });
           };

          return (
            <div>
              <button onClick={this.handleClick}>Load</button>
            </div>
          );
         }
         ```

      <details><summary><b>See Class</b></summary>
        <p>

      ```javascript
        import React, { Component } from "react";

         class App extends Component {
           handleClick = () => {
             import("./moduleA")
               .then(({ moduleA }) => {
                 // Use moduleA
               })
               .catch((err) => {
                 // Handle failure
               });
           };

           render() {
             return (
               <div>
                 <button onClick={this.handleClick}>Load</button>
               </div>
             );
           }
         }

         export default App;

```{=html}
</p>
```
```{=html}
</details>
```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is Concurrent Rendering?

The Concurrent rendering makes React apps to be more responsive by rendering component trees without blocking the main UI thread. It allows React to interrupt a long-running render to handle a high-priority event. i.e, When you enabled concurrent Mode, React will keep an eye on other tasks that need to be done, and if there's something with a higher priority it will pause what it is currently rendering and let the other task finish first. You can enable this in two ways,


```
// 1. Part of an app by wrapping with ConcurrentMode
<React.unstable_ConcurrentMode>
  <Something />
</React.unstable_ConcurrentMode>;

// 2. Whole app using createRoot
ReactDOM.unstable_createRoot(domNode).render(<App />);

```

[

---

### What is concurrent rendering? When does it help vs hurt?

Concurrent rendering allows React to work on multiple tasks simultaneously, interrupting low‑priority work to handle high‑priority updates (like typing). It helps keep the UI responsive.

    **When it helps**: During heavy computations, data fetching, or large list updates – the app stays interactive.
    **When it may hurt**: Not all apps need it; it adds complexity and can cause subtle bugs if components assume synchronous rendering.

---

### What is React lazy function?

The `React.lazy` function lets you render a dynamic import as a regular
component. It will automatically load the bundle containing the
`OtherComponent` when the component gets rendered. This must return a
Promise which resolves to a module with a default export containing a
React component.

     ```jsx
     const OtherComponent = React.lazy(() => import("./OtherComponent"));

     function MyComponent() {
       return (
         <div>
           <OtherComponent />
         </div>
       );
     }
     ```

     **Note:**
     `React.lazy` and `Suspense` is not yet available for server-side rendering. If you want to do code-splitting in a server rendered app, we still recommend React Loadable.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is React memo function?

Class components can be restricted from re-rendering when their input
props are the same using **PureComponent or shouldComponentUpdate**. Now
you can do the same with function components by wrapping them in
**React.memo**.

     ```jsx
     const MyComponent = React.memo(function MyComponent(props) {
       /* only rerenders if props change */
     });
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is `React.lazy` and how does it work?

`React.lazy(() => import('./Comp'))` creates a lazy-loaded component.
React suspends rendering until the chunk loads, showing the nearest
`Suspense` fallback. Only works with default exports.

------------------------------------------------------------------------

---

---

### What is `React.memo`?

A HOC that wraps a functional component. On re-render of the parent,
React shallowly compares old and new props; if equal, it skips
re-rendering the child. Accepts a custom comparator as second argument.

------------------------------------------------------------------------

---

---

### What is `startTransition`?

Marks a state update as non-urgent. React processes urgent updates first and defers the transition. If a newer transition comes in, the in-progress one is aborted. Used for navigation, search, filtering.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is Suspense?

A component that shows a fallback while children are 'suspended'.
Components suspend by throwing a Promise. React catches it, shows the
fallback, and retries when the Promise resolves. Used with `lazy()` and
data-fetching libraries.

------------------------------------------------------------------------

---

---

### What is suspense component?

React Suspense is a built-in feature that lets you defer rendering part
of your component tree until some condition(asynchronous operation) is
met---usually, data or code has finished loading. While waiting,
Suspense lets you display a fallback UI like a spinner or placeholder.

     1. Lazy loading components uses suspense feature,

        If the module containing the dynamic import is not yet loaded by the time parent component renders, you must show some fallback content while you’re waiting for it to load using a loading indicator. This can be done using **Suspense** component.

        ```javascript
        const OtherComponent = React.lazy(() => import("./OtherComponent"));

        function MyComponent() {
          return (
            <div>
              <Suspense fallback={<div>Loading...</div>}>
                <OtherComponent />
              </Suspense>
            </div>
          );
        }
        ```
        The above component shows fallback UI instead real component until `OtherComponent` is fully loaded.

     2. As an another example, suspend until async data(data fetching) is ready
      ```jsx
        function UserProfile() {
          const user = use(fetchUser()); // throws a promise internally
          return <div>{user.name}</div>;
        }

        function App() {
          return (
            <Suspense fallback={<div>Loading user...</div>}>
              <UserProfile />
            </Suspense>
          );
        }

    ```
     

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the difference between async mode and concurrent mode?

Both refers the same thing. Previously concurrent Mode being referred to as "Async Mode" by React team. The name has been changed to highlight React’s ability to perform work on different priority levels. So it avoids the confusion from other approaches to Async Rendering.

[

---

### What is the difference between element and component re-render?

Elements are plain objects; React creates/updates them every render cheaply. A component re-renders when its state or props change, executing the function body again. Only DOM nodes actually affected get updated in the real DOM.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the difference between virtualization and windowing? Trade-offs.

**Virtualization** is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. **Windowing** is a specific implementation (e.g., `react-window`) that renders a “window” of items.

**Trade-offs**:
- **Pros**: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists.
- **Cons**: Adds complexity; layout calculations can be tricky for variable heights. Accessibility can suffer if not implemented carefully (screen readers may not see all items). Scrolling might feel different.

---

---

### What is the methods order when component re-rendered?

An update can be caused by changes to props or state. The below methods
are called in the following order when a component is being re-rendered.

    1.  static getDerivedStateFromProps()
    2.  shouldComponentUpdate()
    3.  render()
    4.  getSnapshotBeforeUpdate()
    5.  componentDidUpdate()

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the Profiler API?

`React.Profiler` wraps a tree and calls `onRender(id, phase, actualDuration, ...)` after each commit. Used to programmatically measure render performance in development. React DevTools Profiler wraps this in a UI.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the purpose of ESLint and Prettier in a React project?

ESLint: static analysis, catches bugs and enforces coding standards
(with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated
code formatting. They complement each other -- ESLint for rules,
Prettier for style.

------------------------------------------------------------------------

---

---

### What is the purpose of Suspense beyond lazy loading?

Suspense is a generic mechanism for orchestrating asynchronous dependencies in React. Besides lazy loading components, it can be used for data fetching (with libraries like Relay, Next.js) or any asynchronous operation that integrates with Suspense. It lets components “wait” for something before rendering, with a fallback UI.

---

### What is windowing technique?

Windowing is a technique that only renders a small subset of your rows at any given time, and can dramatically reduce the time it takes to re-render the components as well as the number of DOM nodes created. If your application renders long lists of data then this technique is recommended. Both react-window and react-virtualized are popular windowing libraries which provides several reusable components for displaying lists, grids, and tabular data.

[

---

### What is windowing/virtualization and when do you need it?

Rendering only visible list items in a large dataset instead of all of them. Libraries: `react-window`, `react-virtual`, `TanStack Virtual`. Use when rendering 1000+ items causes frame drops or memory pressure.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)

**CDN (Content Delivery Network)**  
- Serve static assets (JS, CSS, images) from a CDN to reduce latency for users worldwide. Use a global CDN like Cloudflare, Fastly, or AWS CloudFront.

**Code Splitting**  
- Split code by routes using `React.lazy` and `Suspense`. This loads only the JavaScript needed for the current page.
- Use dynamic imports for heavy components that are not needed immediately.

**Lazy Loading**  
- Images: use `loading="lazy"` attribute on `<img>`.
- Off‑screen components: load them only when they become visible (using Intersection Observer).

**Image Optimization**  
- Serve responsive images with `srcset` and `sizes`.
- Use modern formats (WebP, AVIF) and fallbacks.
- Compress images; use CDN image optimization services (e.g., Imgix, Cloudinary).

**Font Optimization**  
- Use `font-display: swap` to avoid invisible text during loading.
- Preload critical fonts with `<link rel="preload">`.
- Subset fonts to reduce size.

**Resource Hints**  
- Use `preconnect` for origins you’ll connect to (e.g., API, CDN).
- Use `dns-prefetch` for third‑party domains.

**Minification & Compression**  
- Ensure your bundler (Webpack, Vite) minifies code and uses Brotli or Gzip compression.

**HTTP/2 or HTTP/3**  
- Enable HTTP/2 for multiplexing; consider HTTP/3 for better performance.

**Service Worker**  
- Cache static assets for repeat visits.

---

---

### When does `React.memo` NOT help?

When props include new object/function references on every parent render
(must pair with `useMemo`/`useCallback`). When the component is cheap to
render (overhead of comparison \> render cost). When props always
change.

------------------------------------------------------------------------

---

---

### When to Still Use Manual Optimization

```jsx
     // For external libraries without Compiler support
     import { expensiveLibFunction } from 'old-library';

     function MyComponent() {
       // May still need manual memoization here
       const result = useMemo(() => expensiveLibFunction(), []);
       return <div>{result}</div>;
     }
     ```

     #### Compatibility
     - Works with React 18.3+ and React 19
     - Compatible with TypeScript
     - Works with all React hooks
     - Supports Server Components and Client Components

327. ### What is Streaming SSR and how does React 18+ improve it?

     **Streaming SSR** sends HTML to the browser in chunks as it's generated, rather than waiting for the entire page. React 18+ dramatically improves this with Suspense integration.

     #### Traditional SSR (Pre-React 18)
     ```
     Server: Wait for ALL data → Generate ALL HTML → Send to client
     Client: Receive HTML → Download ALL JS → Hydrate ALL components
     Problem: Slow components block entire page!
     ```

     #### Streaming SSR (React 18+)
     ```
     Server: Send HTML as it's ready, wrap slow parts in <Suspense>
     Client: Render immediately, hydrate progressively
     Benefit: User sees content faster!
     ```

     #### Basic Example
     ```jsx
     import { Suspense } from 'react';

     export default function Page() {
       return (
         <html>
           <body>
             {/* Sent immediately */}
             <header>
               <h1>My App</h1>
             </header>

             {/* Sent immediately with fallback */}
             <Suspense fallback={<div>Loading comments...</div>}>
               <Comments /> {/* Streamed when ready */}
             </Suspense>

             {/* Also streamed separately */}
             <Suspense fallback={<div>Loading recommendations...</div>}>
               <Recommendations /> {/* Streamed when ready */}
             </Suspense>

             <footer>© 2026</footer>
           </body>
         </html>
       );
     }
     ```

     #### Server Component with Data Fetching
     ```jsx
     // This is a Server Component (async!)
     async function Comments() {
       const comments = await db.comments.findMany();
       
       return (
         <ul>
           {comments.map(comment => (
             <li key={comment.id}>{comment.text}</li>
           ))}
         </ul>
       );
     }
     ```

---

### When would you use `React.memo`?

Use `React.memo` for: - Components that receive the same props often but
re‑render due to parent re‑renders. - Large components that are
expensive to re‑render. - Pure functional components that depend on
props only.

Avoid over‑using `memo` because the shallow prop comparison itself costs
time. Use it where profiling shows a benefit.

---

---

### ❓ How do you debug a performance bottleneck in a React app using DevTools?

**Answer:** (1) Chrome Performance tab: record user interaction, look for long tasks (>50ms) in the flame chart, identify JS evaluation and layout/paint phases. (2) React DevTools Profiler: record interactions, see which components render and their render duration, look for 'why did this render' annotation. (3) Memory tab: take heap snapshots before/after interactions to find leaks. (4) Network tab: identify slow requests, bundle sizes, caching issues. (5) Coverage tab: see unused JS/CSS bytes. Combine all for complete picture.

---

### ❓ If given an existing website to analyze and improve performance, what is your first step?

**Answer:** Start with measurement before optimization. (1) Run Lighthouse audit in Chrome DevTools — get baseline scores for Performance, Accessibility, SEO. (2) Check Core Web Vitals in the Performance tab and real user data in Search Console. (3) Use Network tab to analyze waterfall — identify render-blocking resources, large bundles, slow API calls. (4) Check Coverage tab for unused JS/CSS. (5) Look for layout shifts in the Layout Shift Regions feature. Measure → identify bottleneck → fix → measure again. Never optimize blind.

---

### ❓ What are Web Vitals and why do they matter?

**Answer:** Core Web Vitals are Google's metrics for user experience quality: LCP (Largest Contentful Paint) — loading performance, should be < 2.5s. CLS (Cumulative Layout Shift) — visual stability, should be < 0.1. INP (Interaction to Next Paint, replaced FID) — responsiveness, should be < 200ms. Also important: FCP (First Contentful Paint), TTFB (Time to First Byte), TTI (Time to Interactive). These directly affect SEO rankings (Google uses them as ranking signals) and user experience metrics.

---

### ❓ What is re-rendering and why does it happen?

**Answer:** Re-rendering is React calling your component function again to compute new JSX output. Causes: (1) Component's own state changes via setState/dispatch. (2) Parent component re-renders (by default, all children re-render). (3) Context value changes. (4) Subscribed store changes (Redux, Zustand). Important: re-rendering doesn't always mean DOM update — React diffs and only applies necessary DOM changes. Prevent unnecessary re-renders with React.memo, useMemo, useCallback, and proper state co-location.

---

### ❓ You notice a memory leak in a production SPA — how do you identify and fix it?

**Answer:** Identification: (1) Use Chrome Memory tab — take heap snapshots, compare before/after navigation. Growing detached DOM nodes and growing listener counts are red flags. (2) Chrome Performance monitor — watch JS heap size over time. Common causes & fixes: (1) Event listeners not removed — fix with cleanup in useEffect return. (2) Timers (setInterval) not cleared — clearInterval in cleanup. (3) Stale closures holding references — review useEffect deps. (4) Unsubscribed observables/WebSockets — close in cleanup. (5) Caching without eviction — implement LRU or max-size limits.

---

## React 18/19, SSR & Server Components

### Explain React Server Components vs Client Components.

- **Server Components**: Run on the server and send a special JSON-like format to the client. They never re‑render on the client and can access server resources (databases, file system) directly. They reduce bundle size and improve performance.
    - **Client Components**: Run in the browser and can have interactivity, state, and effects. They are the traditional React components.

    In the new React architecture, components are “use client” or “use server” directives. Server Components can import Client Components, but not vice versa.

---

### How does React 18's automatic batching work?

Automatic batching in React 18 groups multiple state updates from any
source (not just event handlers) into a single re‑render. This is
enabled by default when using `createRoot`. It reduces unnecessary
renders and improves performance. You can opt out using `flushSync`.

------------------------------------------------------------------------

---

---

### How would you implement SSR for a React application?

**Approaches**: - **Frameworks**: Next.js (recommended), Remix, or
custom Node server with React's
`renderToString`/`renderToPipeableStream`. - **Data fetching**: Fetch
data on the server (e.g., `getServerSideProps` in Next.js) and pass it
as props to the component. - **Hydration**: Server‑rendered HTML is sent
to client; React attaches event listeners and reconciles. -
**Performance**: Use streaming SSR (`renderToPipeableStream`) for faster
TTFB. - **Caching**: Use CDN caching with `stale-while-revalidate` for
pages. - **Challenges**: Ensure server and client environment
compatibility (avoid `window` usage in server). Use `useEffect` for
client‑only code.

------------------------------------------------------------------------

This comprehensive guide covers the most common component design
questions with practical considerations and implementation insights.
Each design can be expanded with full code examples, but the key is to
understand the trade‑offs, accessibility, performance, and scalability
aspects.

---

---

### What are React Server components?

React Server Component is a way to write React component that gets
rendered in the server-side with the purpose of improving React app
performance. These components allow us to load components from the
backend.

     **Note:** React Server Components is still under development and not recommended for production yet.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are the key features introduced in React 18?

React 18, released in March 2022, introduced several groundbreaking
features focused on performance and user experience:

     #### 1. **Automatic Batching**
     Batch multiple state updates together (even in async code) to reduce re-renders.
     ```jsx
     // Before React 18: Only batched in event handlers
     // After React 18: Batched everywhere
     setTimeout(() => {
       setCount(c => c + 1);
       setFlag(f => !f);
       // Only 1 re-render in React 18!
     }, 1000);
     ```

     #### 2. **Concurrent Features**
     - **useTransition**: Mark updates as non-urgent
     - **useDeferredValue**: Defer expensive re-renders
     - **Suspense on Server**: SSR with Suspense support

     #### 3. **New createRoot API**
     ```jsx
     // Old way (React 17)
     ReactDOM.render(<App />, document.getElementById('root'));

     // New way (React 18)
     import { createRoot } from 'react-dom/client';
     const root = createRoot(document.getElementById('root'));
     root.render(<App />);
     ```

     #### 4. **Streaming SSR with Suspense**
     Stream HTML from server and hydrate components as they arrive.

     #### 5. **New Hooks**
     - `useId`: Generate unique IDs for accessibility
     - `useSyncExternalStore`: Subscribe to external stores
     - `useInsertionEffect`: For CSS-in-JS libraries

     #### 6. **Strict Mode Improvements**
     Double-invokes effects in development to catch bugs.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What causes hydration mismatches and how do you fix them?

Think of a hydration mismatch like a blueprint mix-up between two
different builders.

When using Server-Side Rendering (SSR), the Server builds the HTML
webpage first and sends it to the browser. Then, React boots up in the
browser, reads that HTML, and tries to "adopt" it (this adoption process
is called hydration).

A hydration mismatch happens when the HTML that the server built does
not exactly match what React expects to see in the browser. React gets
confused and throws an error.

🚨 What Causes It? (The Differences) Timestamps: The server creates the
HTML at 10:00:00 AM. The browser downloads and reads it at 10:00:03 AM.
Because the seconds don't match, React panics.

Browser-Only Secrets: The server doesn't have a screen or a hard drive,
so it doesn't know what window.innerWidth or localStorage is. If your
code uses these, the server will output a blank space, but the browser
will try to fill it in with real data.

Random Numbers: If you use Math.random(), the server might roll a 4, but
the browser rolls a 7.

🛠️ How to Fix It The Best Way (useEffect): Keep the server text generic
or empty at first. Use a useEffect hook to calculate the time, random
numbers, or browser data after the page has fully loaded in the browser.

The "Ignore It" Way (suppressHydrationWarning): If you have a minor,
harmless mismatch (like a text timestamp), you can add this attribute to
your HTML tag to tell React: "I know they don't match, please don't yell
at me."

The "Skip Server" Way: Turn off server-rendering for that specific
component completely so it only ever builds on the browser.

------------------------------------------------------------------------

---

---

### What is automatic batching in React 18?

React 18 batches multiple `setState` calls in async contexts
(`setTimeout`, Promises, native event handlers) into one re-render.
Previously, only synchronous event handlers were batched. Reduces render
count.

------------------------------------------------------------------------

---

---

### What is `createRoot()` and why was it introduced in React 18?

`createRoot()` replaces `ReactDOM.render()`. It opts the app into React
18's concurrent features (automatic batching, `startTransition`,
Suspense improvements). `ReactDOM.render()` runs in legacy mode without
those features.

------------------------------------------------------------------------

---

---

### What is hydration?

Attaching React's event handlers and internal state to server-rendered
HTML without re-rendering it. React expects the client-side output to
exactly match server HTML; mismatches cause warnings or errors.

------------------------------------------------------------------------

---

---

### What is hydration? How do hydration mismatches occur?

Hydration is the process where React attaches event listeners and
reconciles the server‑rendered HTML with the client‑side virtual DOM. It
allows interactive components to "take over" the static markup.

**Hydration mismatches** occur when the HTML generated on the server
differs from the initial render on the client (e.g., due to different
data, random values, or browser‑only APIs). React will then attempt to
patch the mismatch, which can cause performance issues and break user
experience.

------------------------------------------------------------------------

---

---

### What is hydration in React?

Hydration is the process where React 'attaches' event handlers and makes
a server-rendered HTML page interactive. SSR sends HTML to the browser
(fast first paint). React then downloads, parses JS and runs hydration
--- it walks the existing DOM and attaches React's event system without
re-creating DOM nodes. Hydration mismatch errors occur when
server-rendered HTML doesn't match what React would render on client
(e.g., browser-specific values, Date.now(), Math.random()). React 18 has
selective/partial hydration via Suspense.

------------------------------------------------------------------------

---

---

### What is React hydration?

React hydration is used to add client-side JavaScript interactivity to
pre-rendered static HTML generated by the server. It is used only for
server-side rendering(SSR) to enhance the initial rendering time and
make it SEO friendly application. This hydration acts as a bridge to
reduce the gap between server side and client-side rendering.

      After the page loaded with generated static HTML, React will add application state and interactivity by attaching all event handlers for the respective elements. Let's demonstrate this with an example.

      Consider that React DOM API(using `renderToString`) generated HTML for `<App>` component which contains `<button>` element to increment the counter.

      ```jsx
      import {useState} from 'react';
      import { renderToString } from 'react-dom/server';

      export default function App() {
        const **

------------------------------------------------------------------------

---

---

### What is server-side rendering (SSR)? How does it differ from client-side rendering?

With server-side rendering, i.e, SSR, you don’t have to entirely build the UI in the browser; instead of that, it helps by generating the HTML on the server for each request and sending it to the browser.

After the HTML is delivered, the browser displays content immediately, and React then hydrates the page to make it interactive.

You can be asked the difference between Client-side-rendering and server-side rendering, so here are some points that you can keep in mind:

| **Server-side renderingClient-side Rendering**                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| The initial render is done on the server as HTML before reaching the browser.The initial render is done on the browser using JS.                                   |
| You can see the content immediately on first load.CSR is a bit slower, the screen is blank, or it shows a loading process till JS executes.                        |
| The server prepares the HTML, so the browser only needs to display it initially.The browser is responsible for creating and updating the DOM.                      |
| The first render is faster because the content is already prepared.The first render might take time or feel slower on slow devices/networks.                       |
| It is easy for a search engine to index content since it is present in the HTML.Search engines may come across difficulties here. (if JS is not executed properly) |
| Requires a hydration step - because everything is rendered on a client.No hydration required.                                                                      |
| Part of the rendering work is done on the server to help reduce the client’s initial workload.Most of the application logic is sent to the client as JavaScript.   |

To quickly understand the advantages of SSR:

- It has a faster initial load time,
- Better SEO
- And improved perceived performance

Now, here are some things you need to look out for,

It has a higher server load, complex infrastructure, and hydration mismatch issues, sometimes even a slight delay before full interactivity.

You can also be asked questions like, " What is hydration? In the interviews, so here’s how you can answer -

Hydration is the process by which React attaches event listeners and restores component state on top of the server-rendered HTML.

- It converts static HTML into a fully interactive React app
- Must match the server-rendered output to avoid errors

You should also note some modern approaches made by React:

1\. Frameworks like Next.js provide built-in SSR support, which helps in mixing SSR, CSR, and SSG.

2\. Static Site Generation (SSG), here pages are pre-rendered at build time, and it is faster than SSR but less dynamic.

3\. Streaming SSR, the server sends HTML in chunks, which improves time-to-first-byte and progressive rendering.

4\. React Server Components (RSC) run only on the server and are never sent to the client as JavaScript. They practically help in reducing bundle size and improving performance.

With this, it can fetch data directly on the server and send only the required UI output to the client.

---

### What is SSR with React?

Rendering React components on the server to HTML strings. Improves FCP
(First Contentful Paint) and SEO. Client then hydrates the HTML. Next.js
handles SSR automatically with `getServerSideProps` or Server
Components.

------------------------------------------------------------------------

---

---

### What is state batching? What changed in React 18 regarding batching?

State batching is the process of grouping multiple state updates into a
single re‑render to improve performance. In React 17 and earlier,
batching only happened inside React event handlers (e.g., `onClick`).
Updates inside promises, `setTimeout`, or native events were not
batched.

**React 18** introduced **automatic batching** for all updates,
regardless of where they originate (promises, timeouts, etc.), using
`createRoot`. This reduces unnecessary re‑renders.

---

---

### What is streaming SSR?

Sending HTML to the browser in chunks as components finish rendering on the server. Parts of the page become interactive progressively. React 18's `renderToPipeableStream` / `renderToReadableStream` enable this.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is Streaming SSR and how does React 18+ improve it?

**Streaming SSR** sends HTML to the browser in chunks as it's generated,
rather than waiting for the entire page. React 18+ dramatically improves
this with Suspense integration.

     #### Traditional SSR (Pre-React 18)
     ```
     Server: Wait for ALL data → Generate ALL HTML → Send to client
     Client: Receive HTML → Download ALL JS → Hydrate ALL components
     Problem: Slow components block entire page!
     ```

     #### Streaming SSR (React 18+)
     ```
     Server: Send HTML as it's ready, wrap slow parts in <Suspense>
     Client: Render immediately, hydrate progressively
     Benefit: User sees content faster!
     ```

     #### Basic Example
     ```jsx
     import { Suspense } from 'react';

     export default function Page() {
       return (
         <html>
           <body>
             {/* Sent immediately */}
             <header>
               <h1>My App</h1>
             </header>

             {/* Sent immediately with fallback */}
             <Suspense fallback={<div>Loading comments...</div>}>
               <Comments /> {/* Streamed when ready */}
             </Suspense>

             {/* Also streamed separately */}
             <Suspense fallback={<div>Loading recommendations...</div>}>
               <Recommendations /> {/* Streamed when ready */}
             </Suspense>

             <footer>© 2026</footer>
           </body>
         </html>
       );
     }
     ```

     #### Server Component with Data Fetching
     ```jsx
     // This is a Server Component (async!)
     async function Comments() {
       const comments = await db.comments.findMany();
       
       return (
         <ul>
           {comments.map(comment => (
             <li key={comment.id}>{comment.text}</li>
           ))}
         </ul>
       );
     }
     ```

---

### What is the 'use client' directive?

Placed at the top of a file to mark it and its imports as Client Components in the RSC architecture. Required for any component using hooks, event handlers, or browser APIs when using Next.js App Router.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### ❓ Difference between CSR, SSR, SSG, and ISR?

**Answer:** CSR (Client-Side Rendering): blank HTML, all rendering in browser JS. Fast interactions after initial load, poor SEO/TTI. SSR (Server-Side Rendering): server renders HTML per request. Good SEO, slower TTFB under load, needs server. SSG (Static Site Generation): HTML pre-built at build time. Fastest delivery, perfect for content that rarely changes (docs, blogs). ISR (Incremental Static Regeneration, Next.js): pages pre-built, then selectively rebuilt in background after stale time — combines SSG speed with SSR freshness. Choose: SEO + dynamic = SSR; SEO + static = SSG; no SEO = CSR.

---

---

### ❓ What is state batching? What changed in React 18?

**Answer:** State batching = multiple setState calls in one event handler are combined into one re-render. In React 17, batching only happened in event handlers — setState calls inside setTimeout or Promises caused separate re-renders. React 18 introduced automatic batching everywhere — all setState calls (even in async code, setTimeout, Promises, native events) are batched. This means fewer re-renders and better performance. Use flushSync() to opt out of batching when you need synchronous DOM updates.

---

## Rendering, Reconciliation & Lifecycle

### A user complains about slow UI after data load --- how would you optimize rendering and improve UX?

Slow UI after data load typically means the initial render is expensive
or the data processing blocks the main thread.

-   **Profile the render:** Use React DevTools Profiler to identify
    which component is expensive. Look for large lists, complex
    calculations, or deeply nested component trees.
-   **Defer heavy work:**
    -   Move expensive computations to a Web Worker.
    -   Use `useDeferredValue` or `startTransition` to mark non‑urgent
        updates (React 18) so the UI stays responsive.
    -   Split the data into chunks and render progressively (e.g.,
        pagination or infinite scroll).
-   **Virtualise large lists:** With `react‑window` or
    `react‑virtualized`, only render visible items.
-   **Optimise images and media:** Lazy load images, use proper formats,
    and serve scaled images.
-   **Improve perceived performance:** Show skeleton screens or
    placeholder loaders immediately, then fill in data as it arrives.
    This reduces perceived lag.
-   **Memoise derived data:** Use `useMemo` to avoid recalculating
    expensive derived state on every render.
-   **Avoid layout thrashing:** Batch DOM reads/writes. In React, this
    is less common but can happen with third‑party libraries.

------------------------------------------------------------------------

---

---

### Can you describe about componentDidCatch lifecycle method signature?

The **componentDidCatch** lifecycle method is invoked after an error has been thrown by a descendant component. The method receives two parameters,

         1. error: - The error object which was thrown
         2. info: - An object with a componentStack key contains the information about which component threw the error.

         The method structure would be as follows

         ```javascript
         componentDidCatch(error, info);
         ```

    ****

---

### Explain conditional rendering in React.

Conditional rendering refers to the dynamic output of user interface markups based on a condition state. It works in the same way as JavaScript conditions. Using conditional rendering, it is possible to toggle specific application functions, API data rendering, hide or show elements, decide permission levels, authentication handling, and so on.

There are different approaches for implementing conditional rendering in React. Some of them are:

- Using if-else conditional logic which is suitable for smaller as well as for medium-sized applications
- Using ternary operators, which takes away some amount of complication from if-else statements
- Using element variables, which will enable us to write cleaner code.

## React Architecture & Advanced Concepts

---

### Explain Strict Mode in React.

StrictMode is a tool added in **version 16.3** of React to highlight potential problems in an application. It performs additional checks on the application.

function App() { return ( \<React.StrictMode\>
```{=html}
<div classname="App">
```
       <Header/>
       <div>
         Page Content
       </div>
       <Footer/>
     </div>

\</React.StrictMode\> ); }


    To enable StrictMode, `<React.StrictMode>` tags need to be added inside the application:

import React from "react"; import ReactDOM from "react-dom"; import App
from "./App"; const rootElement = document.getElementById("root");
ReactDOM.render( \<React.StrictMode\> `<App />`{=html}
\</React.StrictMode\>, rootElement );


    StrictMode currently helps with the following issues:

    - **Identifying components with unsafe lifecycle methods: **
      - Certain lifecycle methods are unsafe to use in asynchronous react applications. With the use of third-party libraries, it becomes difficult to ensure that certain lifecycle methods are not used.
      - StrictMode helps in providing us with a warning if any of the class components use an unsafe lifecycle method.
    - **Warning about the usage of legacy string API:**
      - If one is using an older version of React, **callback ref** is the recommended way to manage **refs** instead of using the **string refs**. StrictMode gives a warning if we are using **string refs** to manage refs.
    - **Warning about the usage of findDOMNode:**
      - Previously, findDOMNode( ) method was used to search the tree of a DOM node. This method is deprecated in React. Hence, the StrictMode gives us a warning about the usage of this method.
    - **Warning about the usage of legacy context API (because the API is error-prone).**

---

### How are error boundaries handled in React v15?

**⚠️ LEGACY:** This question is only relevant for historical context.
React v15 is extremely outdated (released in 2016).

    React v15 provided very basic support for _error boundaries_ using the `unstable_handleError` method. This was an experimental feature that was later redesigned and renamed to `componentDidCatch` in React v16.

    **Modern Error Boundaries (React 16+):**
    - Use `static getDerivedStateFromError(error)` for UI fallback
    - Use `componentDidCatch(error, info)` for logging
    - Work consistently across server and client rendering

    ****

------------------------------------------------------------------------

---

---

### How do you create an error boundary?

Class component with
`static getDerivedStateFromError(error) { return {hasError:true} }` to
render fallback, and `componentDidCatch(error, info)` for logging.
Render fallback UI when `hasError` is true.

------------------------------------------------------------------------

---

---

### How do you test error boundaries?

Suppress `console.error` in the test. Render a component that throws inside an error boundary. Assert the fallback UI renders. Use `jest.spyOn(console, 'error').mockImplementation(() => {})` to silence expected errors.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How does React's diffing algorithm work (O(n))?

React compares trees level by level. If root elements differ in type, it
destroys the old tree. For same-type DOM elements it updates only
changed attributes. For same-type components it updates props and
re-renders. Keys enable efficient list diffing.

------------------------------------------------------------------------

---

---

### How to make AJAX call and in which component lifecycle methods should I make an AJAX call?

You can use AJAX libraries such as Axios, jQuery AJAX, and the browser
built-in `fetch`. You should fetch data in the `componentDidMount()`
lifecycle method. This is so you can use `setState()` to update your
component when the data is retrieved.

    For example, the employees list fetched from API and set local state:

    ```jsx harmony
    class MyComponent extends React.Component {
      constructor(props) {
        super(props);
        this.state = {
          employees: **

------------------------------------------------------------------------

---

### 114. 21. Explain conditional rendering in React.

Conditional rendering refers to the dynamic output of user interface
markups based on a condition state. It works in the same way as
JavaScript conditions. Using conditional rendering, it is possible to
toggle specific application functions, API data rendering, hide or show
elements, decide permission levels, authentication handling, and so on.

There are different approaches for implementing conditional rendering in
React. Some of them are:

-   Using if-else conditional logic which is suitable for smaller as
    well as for medium-sized applications
-   Using ternary operators, which takes away some amount of
    complication from if-else statements
-   Using element variables, which will enable us to write cleaner code.

---

---

### How to prevent component from rendering?

You can prevent component from rendering by returning null based on
specific condition. This way it can conditionally render component.

    ```javascript
    function Greeting(props) {
      if (!props.loggedIn) {
        return null;
      }

      return <div className="greeting">welcome, {props.name}</div>;
    }
    ```

    ```javascript
    class User extends React.Component {
      constructor(props) {
        super(props);
        this.state = {loggedIn: false, name: 'John'};
      }

      render() {
       return (
           <div>
             //Prevent component render if it is not loggedIn
             <Greeting loggedIn={this.state.loggedIn} />
             <UserDetails name={this.state.name}>
           </div>
       );
      }
    ```

    In the above example, the `greeting` component skips its rendering section by applying condition and returning null value.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Is it good to use arrow functions in render methods?

Yes, You can use. It is often the easiest way to pass parameters to callback functions. But you need to optimize the performance while using it.


```
class Foo extends Component {
  handleClick() {
    console.log('Click happened');
  }
  render() {
    return <button onClick={() => this.handleClick()}>Click Me</button>;
  }
}

```

**Note:** Using an arrow function in render method creates a new function each time the component renders, which may have performance implications

[

---

### What are error boundaries?

Introduced in version 16 of React, Error boundaries provide a way for us to catch errors that occur in the render phase.

    - **What is an error boundary?**

    Any component which uses one of the following lifecycle methods is considered an error boundary.
    In what places can an error boundary detect an error?

    1. Render phase
    2. Inside a lifecycle method
    3. Inside the constructor

    **Without using error boundaries:**

class CounterComponent extends React.Component{ constructor(props){
super(props); this.state = { counterValue: 0 } this.incrementCounter =
this.incrementCounter.bind(this); } incrementCounter(){
this.setState(prevState =\> counterValue = prevState+1); } render(){
if(this.state.counter === 2){ throw new Error('Crashed'); } return(
```{=html}
<div>
```
      <button onClick={this.incrementCounter}>Increment Value</button>
      <p>Value of counter: {this.state.counterValue}</p>
    </div>

) } }


    In the code above, when the counterValue equals 2, we throw an error inside the render method.

    When we are not using the error boundary, instead of seeing an error, we see a blank page. Since any error inside the render method leads to unmounting of the component. To display an error that occurs inside the render method, we use error boundaries.

    **With error boundaries: **As mentioned above, error boundary is a component using one or both of the following methods: **static getDerivedStateFromError and componentDidCatch.**

    Let’s create an error boundary to handle errors in the render phase:

class ErrorBoundary extends React.Component { constructor(props) {
super(props); this.state = { hasError: false }; } static
getDerivedStateFromError(error) {\
return { hasError: true };  } componentDidCatch(error, errorInfo) {\
logErrorToMyService(error, errorInfo);  } render() { if
(this.state.hasError) {\
return
```{=html}
<h4>
```
Something went wrong
```{=html}
</h4>
```
} return this.props.children; } }


    In the code above, **getDerivedStateFromError** function renders the fallback UI interface when the render method has an error.

    **componentDidCatch** logs the error information to an error tracking service.

    Now with the error boundary, we can render the CounterComponent in the following way:

`<ErrorBoundary>`{=html} `<CounterComponent/>`{=html}
`</ErrorBoundary>`{=html}

---

### What are error boundaries in React v16?

**Note:** Error boundaries were introduced in React 16 and remain valid
in current React versions (18/19).

    _Error boundaries_ are components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed.

    A class component becomes an error boundary if it defines these lifecycle methods:
    - `static getDerivedStateFromError(error)` - for rendering fallback UI
    - `componentDidCatch(error, info)` - for logging error information

    ```jsx harmony
    class ErrorBoundary extends React.Component {
      constructor(props) {
        super(props);
        this.state = { hasError: false };
      }

      static getDerivedStateFromError(error) {
        // Update state so the next render will show the fallback UI
        return { hasError: true };
      }

      componentDidCatch(error, info) {
        // Log error to an error reporting service
        console.error('Error caught by boundary:', error, info);
        logErrorToMyService(error, info);
      }

      render() {
        if (this.state.hasError) {
          // Render custom fallback UI
          return <h1>Something went wrong.</h1>;
        }
        return this.props.children;
      }
    }
    ```

    Usage:

    ```jsx harmony
    <ErrorBoundary>
      <MyWidget />
    </ErrorBoundary>
    ```

    **Note:** Error boundaries currently only work with class components. There is no hook equivalent yet, though `use()` hook in React 19 provides some error handling capabilities.

    ****

------------------------------------------------------------------------

---

---

### What are the different phases of component lifecycle?

The component lifecycle has three distinct lifecycle phases:

        1. **Mounting:** The component is ready to mount in the browser DOM. This phase covers initialization from `constructor()`, `getDerivedStateFromProps()`, `render()`, and `componentDidMount()` lifecycle methods.

        2. **Updating:** In this phase, the component gets updated in two ways, sending the new props and updating the state either from `setState()` or `forceUpdate()`. This phase covers `getDerivedStateFromProps()`, `shouldComponentUpdate()`, `render()`, `getSnapshotBeforeUpdate()` and `componentDidUpdate()` lifecycle methods.

        3. **Unmounting:** In this last phase, the component is not needed and gets unmounted from the browser DOM. This phase includes `componentWillUnmount()` lifecycle method.

        It's worth mentioning that React internally has a concept of phases when applying changes to the DOM. They are separated as follows

        4. **Render** The component will render without any side effects. This applies to Pure components and in this phase, React can pause, abort, or restart the render.

        5. **Pre-commit** Before the component actually applies the changes to the DOM, there is a moment that allows React to read from the DOM through the `getSnapshotBeforeUpdate()`.

        6. **Commit** React works with the DOM and executes the final lifecycles respectively `componentDidMount()` for mounting, `componentDidUpdate()` for updating, and `componentWillUnmount()` for unmounting.

        React 16.3+ Phases (or an **

---

### What are the lifecycle methods going to be deprecated in React v16?

**⚠️ FULLY DEPRECATED:** These lifecycle methods have been deprecated
and removed from React 17+.

    The following lifecycle methods were deprecated due to unsafe coding practices and problems with async rendering:

    1. `componentWillMount()` - **REMOVED in React 17**
    2. `componentWillReceiveProps()` - **REMOVED in React 17**
    3. `componentWillUpdate()` - **REMOVED in React 17**

    **Timeline:**
    - React 16.3: Methods aliased with `UNSAFE_` prefix
    - React 17+: Unprefixed versions completely removed
    - Current (React 18/19): Only `UNSAFE_` versions exist (not recommended)

    **Modern Alternatives:**

    | Deprecated Method | Modern Replacement |
    |---|---|
    | `componentWillMount()` | `constructor()` or `componentDidMount()` |
    | `componentWillReceiveProps()` | `static getDerivedStateFromProps()` or `componentDidUpdate()` |
    | `componentWillUpdate()` | `getSnapshotBeforeUpdate()` + `componentDidUpdate()` |

    **Best Practice:** Use functional components with hooks instead:
    - `useEffect()` for side effects
    - `useState()` for state management
    - `useMemo()`/`useCallback()` for optimization

    ****

------------------------------------------------------------------------

---

---

### What are the lifecycle methods of React?

React lifecycle hooks will have the methods that will be automatically called at different phases in the component lifecycle and thus it provides good control over what happens at the invoked point. It provides the power to effectively control and manipulate what goes on throughout the component lifecycle.

    For example, if you are developing the YouTube application, then the application will make use of a network for buffering the videos and it consumes the power of the battery (assume only these two). After playing the video if the user switches to any other application, then you should make sure that the resources like network and battery are being used most efficiently. You can stop or pause the video buffering which in turn stops the battery and network usage when the user switches to another application after video play.

    So we can say that the developer will be able to produce a quality application with the help of lifecycle methods and it also helps developers to make sure to plan what and how to do it at different points of birth, growth, or death of user interfaces.

    The various lifecycle methods are:

    - `constructor()`: This method will be called when the component is initiated before anything has been done. It helps to set up the initial state and initial values.
    - `getDerivedStateFromProps()`: This method will be called just before element(s) rendering in the DOM. It helps to set up the state object depending on the initial props. The getDerivedStateFromProps() method will have a state as an argument and it returns an object that made changes to the state. This will be the first method to be called on an updating of a component.
    - `render()`: This method will output or re-render the HTML to the DOM with new changes. The render() method is an essential method and will be called always while the remaining methods are optional and will be called only if they are defined.
    - `componentDidMount()`: This method will be called after the rendering of the component. Using this method, you can run statements that need the component to be already kept in the DOM.
    - `shouldComponentUpdate()`: The Boolean value will be returned by this method which will specify whether React should proceed further with the rendering or not. The default value for this method will be True.
    - `getSnapshotBeforeUpdate()`: This method will provide access for the props as well as for the state before the update. It is possible to check the previously present value before the update, even after the update.
    - `componentDidUpdate()`: This method will be called after the component has been updated in the DOM.
    - `componentWillUnmount()`: This method will be called when the component removal from the DOM is about to happen.

---

### What are the possible return types of render method?

Below are the list of following types used and return from render method,

1. **React elements:** Elements that instruct React to render a DOM node. It includes html elements such as `<div/>` and user defined elements.
2. **Arrays and fragments:** Return multiple elements to render as Arrays and Fragments to wrap multiple elements
3. **Portals:** Render children into a different DOM subtree.
4. **String and numbers:** Render both Strings and Numbers as text nodes in the DOM
5. **Booleans or null:** Doesn't render anything but these types are used to conditionally render content.

[

---

### What are the rules covered by diffing algorithm?

When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements. It covers the below rules during reconciliation algorithm,

1. **Elements Of Different Types:** Whenever the root elements have different types, React will tear down the old tree and build the new tree from scratch. For example, elements to, or from to of different types lead a full rebuild.
2. **DOM Elements Of The Same Type:** When comparing two React DOM elements of the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes. Lets take an example with same DOM elements except className attribute,

```
<div className="show" title="ReactJS" />

<div className="hide" title="ReactJS" />

```

1. **Component Elements Of The Same Type:** When a component updates, the instance stays the same, so that state is maintained across renders. React updates the props of the underlying component instance to match the new element, and calls componentWillReceiveProps() and componentWillUpdate() on the underlying instance. After that, the render() method is called and the diff algorithm recurses on the previous result and the new result.
2. **Recursing On Children:** when recursing on the children of a DOM node, React just iterates over both lists of children at the same time and generates a mutation whenever there’s a difference. For example, when adding an element at the end of the children, converting between these two trees works well.

```
<ul>
  <li>first</li>
  <li>second</li>
</ul>

<ul>
  <li>first</li>
  <li>second</li>
  <li>third</li>
</ul>


```

1. **Handling keys:** React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree. For example, adding a key can make the tree conversion efficient,

```
<ul>
  <li key="2015">Duke</li>
  <li key="2016">Villanova</li>
</ul>

<ul>
  <li key="2014">Connecticut</li>
  <li key="2015">Duke</li>
  <li key="2016">Villanova</li>
</ul>

```

[

---

### What is an error boundary?

A class component that implements `getDerivedStateFromError()` and/or
`componentDidCatch()`. It catches rendering errors in its subtree and
renders a fallback UI instead of crashing the whole app.

------------------------------------------------------------------------

---

---

### What is diffing algorithm?

React needs to use algorithms to find out how to efficiently update the UI to match the most recent tree. The diffing algorithms is generating the minimum number of operations to transform one tree into another. However, the algorithms have a complexity in the order of O(n3) where n is the number of elements in the tree.

In this case, for displaying 1000 elements would require in the order of one billion comparisons. This is far too expensive. Instead, React implements a heuristic O(n) algorithm based on two assumptions:

1. Two elements of different types will produce different trees.
2. The developer can hint at which child elements may be stable across different renders with a key prop.

[

---

### What is React Fiber?

The Problem (Old React) Before Fiber, when React started updating the
screen, it had to finish the entire job in one single blast without
stopping. If it was a massive update (like rendering a huge list), the
browser would freeze. If a user tried to click a button or type during
that freeze, the app felt broken and laggy.

The Solution (React Fiber) Fiber changes the way React works by breaking
the massive update job into tiny, bite-sized tasks.

Because the work is split up, React gains three superpowers:

Pause & Resume: It can do a little bit of work, pause to let the browser
breathe, and then pick up right where it left off.

Prioritize: If a user clicks a button while React is busy rendering a
hidden menu, React will pause the menu, handle the button click
immediately (high priority), and then go back to the menu.

Abort: If you switch pages mid-load, React can instantly throw away the
half-finished work of the old page instead of wasting time finishing it.

------------------------------------------------------------------------

---

---

### What is reconciliation?

The process of diffing the new React element tree against the previous
one to compute minimal DOM mutations. React uses two heuristics: same
type → update props; different type → unmount old, mount new. Keys help
reconcile lists.

------------------------------------------------------------------------

---

---

### What is reconciliation? How does React's diffing algorithm work?

So this concept is not very difficult once you read its rules and uses!

What you should do here is get familiar with the concept right now, have
a read, and then, in the end, I'll mention a short answer-like paragraph
that you can use during your interview.

So to understand Reconciliation:

Reconciliation is the internal algo process React uses to compare the
previous Virtual DOM tree with the newly generated Virtual DOM tree
after a state or prop changes.

Here's what happens to make it work:

1.  React re-renders the component to produce a new Virtual DOM tree
2.  It compares this tree with the previous Virtual DOM tree
3.  It computes a set of changes called mutations
4.  It applies only those changes to the real DOM

And so, this process is used to avoid unnecessary DOM operations, which
end up being expensive.

Coming to React's Diffing Algorithm -

React's Diffing Algorithm is a part of the reconciliation process, where
its primary goal is to minimize DOM updates.

Now it is important to understand how this takes place, so please look
into this carefully:

-   The expensive but optimal component is (O(n3 ) )
-   React uses a tree-diffing algorithm to minimize DOM
-   Hence, it uses a heuristic O(n) algorithm instead of specific
    assumptions

What it essentially does is compare root elements, then if they differ,
the entire subtree is replaced, and if they match, then its attributes
and the recursion on children are compared.

There are some rules of diffing that you really need to keep in mind:

**1. Different trees are produced because of different elements**

If the root elements have different types, React:

-   unmounts the old component tree,
-   destroys associated DOM nodes,
-   mounts a new tree.

Example:

    <div /> → <section />

This triggers a full rebuild of that subtree.

**2. Elements of the same type are compared attribute-wise**

If element types are the same, React updates only the changed
attributes, and then recursively compares child elements

**3. Keys are used to match children in lists**

When reconciling lists, React uses the key prop to identify which items
have stayed the same, moved, or have been added or removed

For eg:

    items.map(item => <li key={item.id}>{item.name}</li>)

There is a reason why these keys are critical:

-   They provide a stable identity across renders
-   Prevent incorrect reuse of DOM nodes
-   Preserve component state

Without stable keys, React falls back to index-based matching

What you must also note is that Reordering can lead to state being
assigned to the wrong component, unnecessary re-renders, and even UI
inconsistencies.

You must be wondering why the complexity is O(n) instead of O(n³) -

A full tree comparison would require checking every node against every
other node, which then results in O(n³) complexity.

React reduces this to O(n) using two assumptions:

-   Different element types produce different subtrees - Because of
    this, there is no need to deeply compare and replace directly
-   Keys uniquely identify elements in lists - Enables efficient
    matching of children without exhaustive comparison

These heuristics make React perform reconciliation in linear time
relative to the number of elements.

Now this was all you needed to know about reconciliation,

Here's a short answer that you can prepare if the interviewer isn't
expecting anything detailed:

-   Reconciliation is the process by which React compares the previous
    and new Virtual DOM trees to compute the minimal DOM updates. It
    uses a heuristic O(n) diffing algorithm based on two assumptions:
    elements of different types produce different trees, and keys
    provide a stable identity for list elements.

Now you are good to go!

------------------------------------------------------------------------

---

---

### What is reconciliation in React? How does the diffing algorithm work?

Reconciliation is React's algorithm for determining which parts of the
DOM need to be updated when state or props change. It uses a **virtual
DOM** (a lightweight representation) and compares it with the previous
version.

**Diffing algorithm (simplified)**: - **Elements of different types**:
The whole subtree is torn down and rebuilt. - **Elements of the same
type**: React keeps the same DOM node and only updates changed
attributes (e.g., `className`). Then it recursively diffs children. -
**List children with keys**: Keys help identify which items have
changed, been added, or removed. Without stable keys, the algorithm may
re‑render more than necessary.

------------------------------------------------------------------------

---

---

### What is re‑rendering, and why does it happen?

Re‑rendering is the process where React updates the UI to reflect the current state and props. It happens when:
- A component’s state changes.
- Its props change.
- Its parent re‑renders (by default).
- A context value it uses changes.
- A custom hook triggers an update.

React batches updates for performance; re‑rendering does not necessarily mean the DOM is updated – React computes the difference (reconciliation) and only updates the DOM where needed.

---

### What is Strict Mode?

Think of React Strict Mode like a stress tester or a spellcheck for your
code.

It is a special wrapper tool (\<React.StrictMode\>) you place around
your app. It doesn't show anything on the screen itself, but it
activates extra checks behind the scenes.

The Secret Weapon: The "Double Run" In development, Strict Mode will
deliberately run your components, state updates, and useEffect hooks
twice every time they load.

Why does it do this? Good React code should be predictable. Running a
component twice should produce the exact same result. If running your
code a second time suddenly breaks a feature, causes a visual glitch, or
leaves a background timer running, Strict Mode has successfully exposed
a hidden bug (called a "side effect") before it reaches your users.

Warning System: It also watches your code and prints warning messages in
the browser console if you are using old, outdated React features that
will break in future updates.

⚠️ The Golden Rule Strict Mode only works in development. When you
publish your app to the live internet (production), React automatically
turns off all the double-running and warnings so your live website runs
at 100% full speed.

------------------------------------------------------------------------

---

---

### What is strict mode in React?

`React.StrictMode` is a useful component for highlighting potential
problems in an application. Just like `<Fragment>`, `<StrictMode>` does
not render any extra DOM elements. It activates additional checks and
warnings for its descendants. These checks apply for *development mode*
only.

     ```jsx harmony
     import { StrictMode } from "react";

     function App() {
       return (
         <div>
           <Header />
           <StrictMode>
             <div>
               <ComponentOne />
               <ComponentTwo />
             </div>
           </StrictMode>
           <Header />
         </div>
       );
     }
     ```

     In the example above, the _strict mode_ checks apply to `<ComponentOne>` and `<ComponentTwo>` components only. i.e., Part of the application only.

     **Note:** Frameworks such as NextJS has this flag enabled by default.

     ****

------------------------------------------------------------------------

---

---

### What is the benefit of component stack trace from error boundary?

Apart from error messages and javascript stack, React16 will display the
component stack trace with file names and line numbers using error
boundary concept.

     For example, BuggyCounter component displays the component stack trace as below,

     !**

------------------------------------------------------------------------

---

## React Rendering, Reconciliation & Lifecycle

---

### What is the benefit of strict mode?

The `<StrictMode>`{=html} will be helpful in the below cases,

     1. To find the bugs caused by impure rendering where the components will re-render twice.
     2. To find the bugs caused by missing cleanup of effects where the components will re-run effects one more extra time.
     3. Identifying components with **unsafe lifecycle methods**.
     4. Warning about **legacy string ref** API usage.
     5. Detecting unexpected **side effects**.
     6. Detecting **legacy context** API.
     7. Warning about deprecated **findDOMNode** usage

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the difference between shallow and deep rendering?

Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the difference between try catch block and error boundaries?

Try catch block works with imperative code whereas error boundaries are meant for declarative code to render on the screen.

For example, the try catch block used for below imperative code


```
try {
  showButton();
} catch (error) {
  // ...
}

```

Whereas error boundaries wrap declarative code as below,


```
<ErrorBoundary>
  <MyComponent />
</ErrorBoundary>

```

So if an error occurs in a **componentDidUpdate** method caused by a **setState** somewhere deep in the tree, it will still correctly propagate to the closest error boundary.

[

---

### What is the main goal of React Fiber?

The goal of _React Fiber_ is to increase its suitability for areas like animation, layout, and gestures. Its headline feature is **incremental rendering**: the ability to split rendering work into chunks and spread it out over multiple frames.

        Its main goals are:

        *   **Incremental Rendering** – Breaks work into chunks for smoother updates.
        *   **Interruptible Rendering** – Pauses and resumes rendering to keep the UI responsive.
        *   **Prioritization** – Handles high-priority updates (e.g. animations) before low-priority ones.
        *   **Concurrency Support** – Enables working on multiple UI versions simultaneously.
        *   **Better Error Handling** – Supports component-level error boundaries.
        *   **Suspense Support** – Allows waiting for async data before rendering.
        *   **Improved DevTools** – Enables better debugging and performance tracking.

        ****

---

### What is the purpose of render method of `react-dom`?

This method is used to render a React element into the DOM in the
supplied container and return a reference to the component. If the React
element was previously rendered into container, it will perform an
update on it and only mutate the DOM as necessary to reflect the latest
changes.

    ```
    ReactDOM.render(element, container, **

------------------------------------------------------------------------

---

### 119. Component Re-renders Unexpectedly: Component re-renders even when props don't change -- hidden reasons.

**Common hidden reasons**: - **Parent re‑renders** -- by default, a
component re‑renders when its parent re‑renders, even if props are
identical. Fix: use `React.memo`. - **Inline functions/objects** passed
as props create new references each render. Fix: use `useCallback` and
`useMemo`. - **Context changes** -- if the component consumes any
context, a context update triggers re‑render. - **State updates that set
the same value** -- React 18 may still re‑render even if value hasn't
changed (though it usually doesn't for primitive values). - **Key
changes** -- if a component's key changes, React treats it as a new
component and unmounts/mounts.

**Debug**: - Use `why-did-you-render` library to log prop changes. - Use
React DevTools Profiler to see why a component rendered (highlight
updates).

------------------------------------------------------------------------

---

---

### Why do not you need error boundaries for event handlers?

Error boundaries do not catch errors inside event handlers. Event handlers don't happened or invoked during rendering time unlike render method or lifecycle methods. So React knows how to recover these kind of errors in event handlers. If still you need to catch an error inside event handler, use the regular JavaScript try / catch statement as below


```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { error: null };
  }

  handleClick = () => {
    try {
      // Do something that could throw
    } catch (error) {
      this.setState({ error });
    }
  };

  render() {
    if (this.state.error) {
      return <h1>Caught an error.</h1>;
    }
    return <div onClick={this.handleClick}>Click Me</div>;
  }
}

```

The above code is catching the error using vanilla javascript try/catch block instead of error boundaries.

[

---

### Why does strict mode render twice in React?

StrictMode renders components twice in development mode(not production)
in order to detect any problems with your code and warn you about those
problems. This is used to detect accidental side effects in the render
phase. If you used `create-react-app` development tool then it
automatically enables StrictMode by default.

     ```js
     const root = createRoot(document.getElementById("root"));
     root.render(
       <StrictMode>
         <App />
       </StrictMode>
     );
     ```

     If you want to disable this behavior then you can simply remove `strict` mode.

     ```js
     const root = createRoot(document.getElementById("root"));
     root.render(<App />);
     ```

     To detect side effects the following functions are invoked twice:

     1. Function component bodies, excluding the code inside event handlers.
     2. Functions passed to `useState`, `useMemo`, or `useReducer` (any other Hook)
     3. Class component's `constructor`, `render`, and `shouldComponentUpdate` methods
     4. Class component static `getDerivedStateFromProps` method
     5. State updater functions

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### ❓ What is reconciliation in React?

**Answer:** Reconciliation is React's algorithm for diffing the previous virtual DOM tree with the new one and determining the minimal set of real DOM changes needed. Key heuristics: (1) Elements of different types produce entirely different trees. (2) Elements with stable keys are matched across renders. (3) Same type = update props in place. React's Fiber architecture enables incremental reconciliation — work can be paused, prioritized, and resumed, unlike the old synchronous stack reconciler.

---

## Components, Props & State

### Can I import an SVG file as react component?

You can import SVG directly as component instead of loading it as a file. This feature is available with `react-scripts@2.0.0` and higher.

         ```jsx harmony
         import { ReactComponent as Logo } from "./logo.svg";

         const App = () => (
           <div>
             {/* Logo is an actual react component */}
             <Logo />
           </div>
         );
         ```

         **Note**: Don't forget about the curly braces in the import.

    ****

---

### Can I use web components in react application?

Yes, you can use web components in a react application. Even though many
developers won't use this combination, it may require especially if you
are using third-party UI components that are written using Web
Components.

     For example, let us use `Vaadin` date picker web component as below,

     ```javascript
     import "./App.css";
     import "@vaadin/vaadin-date-picker";
     export default function App() {
       return (
         <div className="App">
           <vaadin-date-picker label="When were you born?"></vaadin-date-picker>
         </div>
       );
     }
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

### 193. Component Design Fundamentals

---

### Controlled vs uncontrolled components?

Controlled Components (The Micromanaged Employee) A controlled component
is completely managed by React. React keeps track of every single
keystroke in its internal memory (state).

Analogy: A boss who asks for an update every time an employee writes a
single sentence.

How it works: When you type into an input box, it triggers an onChange
event. React updates its state with the new letter, and then React tells
the input box to display that new state.

Why use it? Because React knows exactly what is in the box at all times,
you can easily do things like disable a "Submit" button until an email
address is formatted correctly, or force all text to be uppercase as the
user types.

Uncontrolled Components (The Independent Worker) An uncontrolled
component is left to manage itself. The browser (DOM) keeps track of
what is typed in the box, just like a traditional HTML website.

Analogy: A suggestion box. You don't monitor people as they write their
suggestions; you just use a key to open the box and read whatever is
inside only when you actually need it.

How it works: You don't bother saving every keystroke to React's state.
Instead, you attach a ref (a reference) to the input. When the user
finally clicks "Submit", React uses that ref to reach into the DOM and
pull the final value out.

Why use it? It requires less code to set up. It's great for very simple
forms where you don't need instant validation while the user is typing.

------------------------------------------------------------------------

---

---

### Controlled vs uncontrolled forms -- trade-offs in practice?

Controlled: every keystroke updates state → always have current value
for validation, but can cause re-renders. Uncontrolled with ref: only
read on submit → fewer renders, but can't do real-time validation
easily.

------------------------------------------------------------------------

---

---

### Explain about types of side effects in React component.

There are two types of side effects in React component. They are:

    - **Effects without Cleanup: **This side effect will be used in useEffect which does not restrict the browser from screen update. It also improves the responsiveness of an application. A few common examples are network requests, Logging, manual DOM mutations, etc.
    - **Effects with Cleanup:** Some of the Hook effects will require the cleanup after updating of DOM is done. For example, if you want to set up an external data source subscription, it requires cleaning up the memory else there might be a problem of memory leak. It is a known fact that React will carry out the cleanup of memory when the unmounting of components happens. But the effects will run for each render() method rather than for any specific method. Thus we can say that, before execution of the effects succeeding time the React will also cleanup effects from the preceding render.

    Get Access to 250+ Guides with Scaler Mobile App!

    Experience free learning content on the Scaler Mobile App

    4.5

    100K+

    Play Store

---

### Explain React state and props.

| PropsState                        |                                            |
    | --------------------------------- | ------------------------------------------ |
    | Immutable                         | Owned by its component                     |
    | Has better performance            | Locally scoped                             |
    | Can be passed to child components | Writeable/Mutable                          |
    |                                   | has setState() method to modify properties |
    |                                   | Changes to state can be asynchronous       |
    |                                   | can only be passed as props                |

    - **React State**
      Every component in react has a built-in state object, which contains all the property values that belong to that component.
      In other words, the state object controls the behaviour of a component. Any change in the property values of the state object leads to the re-rendering of the component.

    > Note- State object is not available in functional components but, we can use React Hooks to add state to a functional component.

    **How to declare a state object?**

    *Example: *

class Car extends React.Component{ constructor(props){ super(props);
this.state = { brand: "BMW", color: "black" } } }


    **How to use and update the state object?**

class Car extends React.Component { constructor(props) { super(props);
this.state = { brand: "BMW", color: "Black" }; } changeColor() {
this.setState(prevState =\> { return { color: "Red" }; }); } render() {
return (
```{=html}
<div>
```
      <button onClick={() => this.changeColor()}>Change Color</button>
      <p>{this.state.color}</p>
    </div>

); } }


    As one can see in the code above, we can use the state by calling **this.state.propertyName** and we can change the state object property using **setState** method.

    - **React Props**

    Every React component accepts a single object argument called props (which stands for “properties”).  These props can be passed to a component using HTML attributes and the component accepts these props as an argument.

    Using props, we can pass data from one component to another.

    *Passing props to a component:*

    While rendering a component, we can pass the props as an HTML attribute:

`<Car brand="Mercedes"/>`{=html}


    The component receives the props:

    *In Class component:*

class Car extends React.Component { constructor(props) { super(props);
this.state = { brand: this.props.brand, color: "Black" }; } }


    *In Functional component:*

function Car(props) { let \[brand, setBrand\] = useState(props.brand); }


    > Note- Props are read-only. They cannot be manipulated or changed inside a component.

---

### Explain the concept of "controlled re‑render boundaries".

A controlled re‑render boundary is a technique to isolate parts of the UI that re‑render frequently from those that don’t. This can be achieved by:
    - Using `React.memo` on child components.
    - Moving state down to the components that need it.
    - Lifting state up only as necessary.
    - Using `useMemo` and `useCallback` to stabilize props.
    - Structuring context to avoid unnecessary consumers.

---

### Functional vs class components – key differences?

Functional: plain JS functions, use hooks for state/lifecycle, simpler, preferred since React 16.8. Class: extend `React.Component`, use `this.state` and lifecycle methods, support error boundaries natively. New code should use functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### Give an example of Styled Components?

Lets create `<Title>` and `<Wrapper>` components with specific styles for each.

         ```javascript
         import React from "react";
         import styled from "styled-components";

         // Create a <Title> component that renders an <h1> which is centered, red and sized at 1.5em
         const Title = styled.h1`
           font-size: 1.5em;
           text-align: center;
           color: palevioletred;
         `;

         // Create a <Wrapper> component that renders a <section> with some padding and a papayawhip background
         const Wrapper = styled.section`
           padding: 4em;
           background: papayawhip;
         `;
         ```

         These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

         ```jsx harmony
         <Wrapper>
           <Title>{"Lets start first styled component!"}</Title>
         </Wrapper>
         ```

    ****

---

### How do you access imperative API of web components?

Web Components often expose an imperative API to implement its functions. You will need to use a **ref** to interact with the DOM node directly if you want to access imperative API of a web component. But if you are using third-party Web Components, the best solution is to write a React component that behaves as a **wrapper** for your Web Component.

[

---

### How do you access props in attribute quotes?

React (or JSX) doesn't support variable interpolation inside an attribute value. The below representation won't work:

        ```jsx harmony
        <img className="image" src="images/{this.props.image}" />
        ```

        But you can put any JS expression inside curly braces as the entire attribute value. So the below expression works:

        ```jsx harmony
        <img className="image" src={"images/" + this.props.image} />
        ```

        Using _template strings_ will also work:

        ```jsx harmony
        <img className="image" src={`images/${this.props.image}`} />
        ```

        ****

---

### How do you approach developing a reusable component from a design?

1.  **Understand the component** -- identify its purpose, variations
    (sizes, colors, states), and behavior (hover, disabled).\
2.  **Define API** -- props for variants, event handlers, and
    accessibility attributes.\
3.  **Build in isolation** -- use Storybook to develop without
    distractions.\
4.  **Style with CSS modules / styled‑components** -- ensure styles are
    encapsulated and themable.\
5.  **Implement accessibility** -- proper ARIA roles, keyboard
    navigation, focus management.\
6.  **Write tests** -- unit tests for logic, integration tests for
    interactions, visual regression tests.\
7.  **Document** -- in Storybook, with prop tables, usage examples, and
    design guidelines.\
8.  **Publish** -- to a shared package or monorepo for reuse.

------------------------------------------------------------------------

---

---

### How do you create HOC using render props?

You can implement most higher-order components (HOC) using a regular
component with a render prop. For example, if you would prefer to have a
withMouse HOC instead of a `<Mouse>`{=html} component, you could easily
create one using a regular `<Mouse>`{=html} with a render prop.

    ```javascript
    function withMouse(Component) {
      return class extends React.Component {
        render() {
          return (
            <Mouse
              render={(mouse) => <Component {...this.props} mouse={mouse} />}
            />
          );
        }
      };
    }
    ```

    This way render props gives the flexibility of using either pattern.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you pass an event handler to a component?

You can pass event handlers and other functions as props to child
components. The functions can be passed to child component as below,

     ```jsx
     function Button({ onClick }) {
       return <button onClick={onClick}>Download</button>;
     }

     export default function downloadExcel() {
       function handleClick() {
         alert("Downloaded");
       }

       return <Button onClick={handleClick}></Button>;
     }
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you pass parent data to the 5th child component?

Options in order of preference: (1) Component composition ---
restructure so the component needing data isn't 5 levels deep. (2) React
Context --- create a context, wrap with Provider at the parent level,
consume with useContext at the child --- no prop drilling needed. (3)
State management (Redux/Zustand) --- store state globally, child
subscribes directly. (4) Prop drilling --- workable for 2-3 levels,
painful at 5 levels. For most cases, Context is the right answer.

---

---

### How do you prevent prop explosion in complex components?

Use compound components instead of many boolean props. Accept a config object. Use context for deeply shared state. Separate components for different variants rather than one component with 20 props.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you say that props are readonly?

When you declare a component as a function or a class, it must never
modify its own props.

     Let us take a below capital function,

     ```javascript
     function capital(amount, interest) {
       return amount + interest;
     }
     ```

     The above function is called “pure” because it does not attempt to change their inputs, and always return the same result for the same inputs. Hence, React has a single rule saying "All React components must act like pure functions with respect to their props."

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you say that state updates are merged?

When you call setState() in the component, React merges the object you provide into the current state.

For example, let us take a facebook user with posts and comments details as state variables,


```
  constructor(props) {
    super(props);
    this.state = {
      posts: [],
      comments: []
    };
  }

```

Now you can update them independently with separate `setState()` calls as below,


```
componentDidMount() {
    fetchPosts().then(response => {
      this.setState({
        posts: response.posts
      });
    });

    fetchComments().then(response => {
      this.setState({
        comments: response.comments
      });
    });
  }

```

As mentioned in the above code snippets, `this.setState({comments})` updates only comments variable without modifying or replacing posts variable.

[

---

### How do you set default value for uncontrolled component?

In React, the value attribute on form elements will override the value
in the DOM. With an uncontrolled component, you might want React to
specify the initial value, but leave subsequent updates uncontrolled. To
handle this case, you can specify a **defaultValue** attribute instead
of **value**.

     ```javascript
     render() {
       return (
         <form onSubmit={this.handleSubmit}>
           <label>
             User Name:
             <input
               defaultValue="John"
               type="text"
               ref={this.input} />
           </label>
           <input type="submit" value="Submit" />
         </form>
       );
     }
     ```

     The same applies for `select` and `textArea` inputs. But you need to use **defaultChecked** for `checkbox` and `radio` inputs.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you type children in React with TypeScript?

`React.ReactNode`: anything renderable (most flexible). `React.ReactElement`: a React element only. `React.PropsWithChildren<Props>`: adds optional children to any props type. Prefer `ReactNode` for general children.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you type component props with TypeScript?

Define an interface or type alias: `interface Props {name: string; onClick: () => void}`. Pass as generic to FC: `const Comp: React.FC<Props> = ({name, onClick}) => ...` or just define props inline: `function Comp({name}: Props)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you update arrays inside state?

Eventhough arrays in JavaScript are mutable in nature, you need to treat
them as immutable while storing them in a state. That means, similar to
objects, the arrays cannot be updated directly inside state. Instead,
you need to create a copy of the existing array and then set the state
to use newly copied array.

      To ensure that arrays are not mutated, the mutation operations like direct direct assignment(arr**

------------------------------------------------------------------------

---

---

### How do you update nested objects inside state?

You cannot simply use spread syntax for all kinds of objects inside
state. Because spread syntax is shallow and it copies properties for one
level deep only. If the object has nested object structure, UI doesn't
work as expected with regular JavaScript nested property mutation. Let's
demonstrate this behavior with an example of User object which has
address nested object inside of it.

      ```jsx
      const user = {
        name: "John",
        age: 32,
        address: {
          country: "Singapore",
          postalCode: 440004,
        },
      };
      ```

      If you try to update the country nested field in a regular javascript fashion(as shown below) then user profile screen won't be updated with latest value.

      ```js
      user.address.country = "Germany";
      ```

      This issue can be fixed by flattening all the fields into a top-level object or create a new object for each nested object and point it to it's parent object. In this example, first you need to create copy of address object and update it with the latest value. Later, the address object should be linked to parent user object something like below.

      ```js
      setUser({
        ...user,
        address: {
          ...user.address,
          country: "Germany",
        },
      });
      ```

      This approach is bit verbose and not easy for deep hierarchical state updates. But this workaround can be used for few levels of nested objects without much hassle.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you use immer library for state updates?

Immer library enforces the immutability of state based on
**copy-on-write** mechanism. It uses JavaScript proxy to keep track of
updates to immutable states. Immer has 3 main states as below,

      1. **Current state:** It refers to actual state
      2. **Draft state:** All new changes will be applied to this state. In this state, draft is just a proxy of the current state.
      3. **Next state:** It is formed after all mutations applied to the draft state

      Immer can be used by following below instructions,

      1. Install the dependency using `npm install use-immer` command
      2. Replace `useState` hook with `useImmer` hook by importing at the top
      3. The setter function of `useImmer` hook can be used to update the state.

      For example, the mutation syntax of immer library simplifies the nested address object of user state as follows,

      ```jsx
      import { useImmer } from "use-immer";
      const **

------------------------------------------------------------------------

---

---

### How does React batch multiple state updates?

React prevents component from re-rendering for each and every state
update by grouping multiple state updates within an event handler. This
strategy improves the application performance and this process known as
**batching**. The older version of React only supported batching for
browser events whereas React18 supported for asynchronous actions,
timeouts and intervals along with native events. This improved version
of batching is called **automatic batching**.

      Let's demonstrate this automatic batching feature with a below example.

      ```jsx
      import { useState } from "react";

      export default function BatchingState() {
        const **

------------------------------------------------------------------------

---

---

### How to apply validation on props in React?

When the application is running in _development mode_, React will automatically check all props that we set on components to make sure they have _correct type_. If the type is incorrect, React will generate warning messages in the console. It's disabled in _production mode_ due to performance impact. The mandatory props are defined with `isRequired`.

        The set of predefined prop types:

        1. `PropTypes.number`
        2. `PropTypes.string`
        3. `PropTypes.array`
        4. `PropTypes.object`
        5. `PropTypes.func`
        6. `PropTypes.node`
        7. `PropTypes.element`
        8. `PropTypes.bool`
        9. `PropTypes.symbol`
        10. `PropTypes.any`

        We can define `propTypes` for `User` component as below:

        ```jsx harmony
        import React from "react";
        import PropTypes from "prop-types";

        class User extends React.Component {
          static propTypes = {
            name: PropTypes.string.isRequired,
            age: PropTypes.number.isRequired,
          };

          render() {
            return (
              <>
                <h1>{`Welcome, ${this.props.name}`}</h1>
                <h2>{`Age, ${this.props.age}`}</h2>
              </>
            );
          }
        }
        ```

        **Note:** In React v15.5 _PropTypes_ were moved from `React.PropTypes` to `prop-types` library.
        
        **Modern Recommendation:** While PropTypes are still supported, **TypeScript** is now the industry standard for type checking in React applications. Consider using TypeScript for better type safety, IDE support, and compile-time error detection.

        _The Equivalent Functional Component_

        ```jsx harmony
        import React from "react";
        import PropTypes from "prop-types";

        function User({ name, age }) {
          return (
            <>
              <h1>{`Welcome, ${name}`}</h1>
              <h2>{`Age, ${age}`}</h2>
            </>
          );
        }

        User.propTypes = {
          name: PropTypes.string.isRequired,
          age: PropTypes.number.isRequired,
        };
        ```
        
        _Modern TypeScript Version_

        ```tsx
        import React from "react";

        interface UserProps {
          name: string;
          age: number;
        }

        function User({ name, age }: UserProps) {
          return (
            <>
              <h1>{`Welcome, ${name}`}</h1>
              <h2>{`Age, ${age}`}</h2>
            </>
          );
        }
        ```

        ****

---

### How to create a switching component for displaying different pages?

A switching component refers to a component that will render one of the multiple components. We should use an object for mapping prop values to components.

A below-given example will show you how to display different pages based on page prop using switching component:

```
import HomePage from './HomePage'
import AboutPage from './AboutPage'
import FacilitiesPage from './FacilitiesPage'
import ContactPage from './ContactPage'
import HelpPage from './HelpPage'
const PAGES = {
 home: HomePage,
 about: AboutPage,
 facilitiess: FacilitiesPage,
 contact: ContactPage
 help: HelpPage
}
const Page = (props) => {
 const Handler = PAGES[props.page] || HelpPage
 return <Handler {...props} />
}
// The PAGES object keys can be used in the prop types for catching errors during dev-time.
Page.propTypes = {
 page: PropTypes.oneOf(Object.keys(PAGES)).isRequired
}
```

---

### How to create components in React?

Components are the building blocks of creating User Interfaces(UI) in React. There are two possible ways to create a component.

        1. **Function Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the one and only one parameter and return React elements to render the output:

           ```jsx harmony
           function Greeting({ message }) {
             return <h1>{`Hello, ${message}`}</h1>;
           }
           ```

        2. **Class Components:** You can also use ES6 class to define a component. The above function component can be written as a class component:

           ```jsx harmony
           class Greeting extends React.Component {
             render() {
               return <h1>{`Hello, ${this.props.message}`}</h1>;
             }
           }
           ```

        ****

---

### How to create props proxy for HOC component?

You can add/edit props passed to the component using *props proxy*
pattern like this:

    ```jsx harmony
    function HOC(WrappedComponent) {
      return class Test extends Component {
        render() {
          const newProps = {
            title: "New Header",
            footer: false,
            showFeatureX: false,
            showFeatureY: true,
          };

          return <WrappedComponent {...this.props} {...newProps} />;
        }
      };
    }
    ```

    ****

------------------------------------------------------------------------

---

---

### How to create react class components without ES6?

If you don't use ES6 then you may need to use the create-react-class
module instead. For default props, you need to define getDefaultProps()
as a function on the passed object. Whereas for initial state, you have
to provide a separate getInitialState method that returns the initial
state.

    ```javascript
    var Greeting = createReactClass({
      getDefaultProps: function () {
        return {
          name: "Jhohn",
        };
      },
      getInitialState: function () {
        return { message: this.props.message };
      },
      handleClick: function () {
        console.log(this.state.message);
      },
      render: function () {
        return <h1>Hello, {this.props.name}</h1>;
      },
    });
    ```

    **Note:** If you use createReactClass then auto binding is available for all methods. i.e, You don't need to use `.bind(this)` with in constructor for event handlers.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to debug forwardRefs in DevTools?

**React.forwardRef** accepts a render function as parameter and DevTools uses this function to determine what to display for the ref forwarding component.

For example, If you don't name the render function or not using displayName property then it will appear as ”ForwardRef” in the DevTools,


```
const WrappedComponent = React.forwardRef((props, ref) => {
  return <LogProps {...props} forwardedRef={ref} />;
});

```

But If you name the render function then it will appear as **”ForwardRef(myFunction)”**


```
const WrappedComponent = React.forwardRef(function myFunction(props, ref) {
  return <LogProps {...props} forwardedRef={ref} />;
});

```

As an alternative, You can also set displayName property for forwardRef function,


```
function logProps(Component) {
  class LogProps extends React.Component {
    // ...
  }

  function forwardRef(props, ref) {
    return <LogProps {...props} forwardedRef={ref} />;
  }

  // Give this component a more helpful display name in DevTools.
  // e.g. "ForwardRef(logProps(MyComponent))"
  const name = Component.displayName || Component.name;
  forwardRef.displayName = `logProps(${name})`;

  return React.forwardRef(forwardRef);
}

```

[

---

### How to import and export components using React and ES6?

You should use default for exporting the components

        ```jsx harmony
        import User from "user";

        export default function MyProfile {
            return <User type="customer">//...</User>;
        }
        ```

        <details><summary><b>See Class</b></summary>
        <p>
         ```jsx harmony
         import React from "react";
         import User from "user";

        export default class MyProfile extends React.Component {
        render() {
        return <User type="customer">//...</User>;
        }
        }

        ```
        </p>
        </details>

        With the export specifier, the MyProfile is going to be the member and exported to this module and the same can be imported without mentioning the name in other components.
        ```

    ****

---

### How to listen to state changes?

The `componentDidUpdate` lifecycle method will be called when state
changes. You can compare provided state and props values with current
state and props to determine if something meaningful changed.

    ```
    componentDidUpdate(object prevProps, object prevState)
    ```

    **Note:** The previous releases of ReactJS also uses `componentWillUpdate(object nextProps, object nextState)` for state changes. It has been deprecated in latest releases.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to pass data between react components?

**Parent Component to Child Component (using props)**

    With the help of props, we can send data from a parent to a child component.

    **How do we do this?**

    Consider the following Parent Component:

import ChildComponent from "./Child"; function ParentComponent(props) {
let \[counter, setCounter\] = useState(0);

    let increment = () => setCounter(++counter);

    return (
      <div>
        <button onClick={increment}>Increment Counter</button>
        <ChildComponent counterValue={counter} />
      </div>
    );

}


    As one can see in the code above, we are rendering the child component inside the parent component, by providing a prop called counterValue. The value of the counter is being passed from the parent to the child component.

    We can use the data passed by the parent component in the following way:

function ChildComponent(props) { return (

<div>

    <p>Value of counter: {props.counterValue}</p>

</div>

); }


    We use the **props.counterValue** to display the data passed on by the parent component.

    **Child Component to Parent Component (using callbacks)**

    This one is a bit tricky. We follow the steps below:

    - Create a callback in the parent component which takes in the data needed as a parameter.
    - Pass this callback as a prop to the child component.
    - Send data from the child component using the callback.

    We are considering the same example above but in this case, we are going to pass the updated counterValue from child to parent.

    **Step1 and Step2: **Create a callback in the parent component, pass this callback as a prop.

function ParentComponent(props) { let \[counter, setCounter\] =
useState(0); let callback = valueFromChild =\>
setCounter(valueFromChild); return (

<div>

    <p>Value of counter: {counter}</p>
    <ChildComponent callbackFunc={callback} counterValue={counter} />

</div>

); }


    As one can see in the code above, we created a function called callback which takes in the data received from the child component as a parameter.

    Next, we passed the function callback as a prop to the child component.

    **Step3: **Pass data from the child to the parent component.

function ChildComponent(props) { let childCounterValue =
props.counterValue; return (

<div>

    <button onClick={() => props.callbackFunc(++childCounterValue)}>
      Increment Counter
    </button>

</div>

); }


    In the code above, we have used the props.counterValue and set it to a variable called childCounterValue.

    Next, on button click, we pass the incremented childCounterValue to the **props.callbackFunc**.

    This way, we can pass data from the child to the parent component.

---

### How to pass numbers to React component?

We can pass `numbers` as `props` to React component using curly braces `{}` where as `strings` in double quotes `""` or single quotes `''`

         ```jsx
         import React from "react";

         const ChildComponent = ({ name, age }) => {
           return (
             <>
               My Name is {name} and Age is {age}
             </>
           );
         };

         const ParentComponent = () => {
           return (
             <>
               <ChildComponent name="Chetan" age={30} />
             </>
           );
         };

         export default ParentComponent;
         ```

    ****

---

### How to prevent unnecessary updates using setState?

You can compare current value of the state with an existing state value and decide whether to rerender the page or not. If the values are same then you need to return **null** to stop re-rendering otherwise return the latest state value.

For example, the user profile information is conditionally rendered as follows,


```
getUserProfile = (user) => {
  const latestAddress = user.address;
  this.setState((state) => {
    if (state.address === latestAddress) {
      return null;
    } else {
      return { title: latestAddress };
    }
  });
};

```

[

---

### How to set state with a dynamic key name?

If you are using ES6 or the Babel transpiler to transform your JSX code
then you can accomplish this with *computed property names*.

    ```javascript
    handleInputChange(event) {
      this.setState({ **

------------------------------------------------------------------------

---

---

### How to update a component every second?

You need to use `setInterval()` to trigger the change, but you also need
to clear the timer when the component unmounts to prevent errors and
memory leaks.

    ```javascript
    componentDidMount() {
      this.interval = setInterval(() => this.setState({ time: Date.now() }), 1000)
    }

    componentWillUnmount() {
      clearInterval(this.interval)
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### If we have `var`, `let`, `const`, why do we need state variables?

Regular JavaScript variables do not trigger re‑renders when they change. State variables (`useState`) are designed to:
- Preserve values across renders.
- Trigger a re‑render when updated (via the setter function).
- Work within React’s reconciliation cycle. Without them, changes to variables would not be reflected in the UI.

---

### Implement Debouncing and Throttling in a search or scroll-heavy component.

**Debouncing** (search input):
```jsx
const debouncedSearch = useCallback(
  debounce((query) => { /* fetch */ }, 300),
  []
);
const handleChange = (e) => debouncedSearch(e.target.value);
```

**Throttling** (scroll event):
```jsx
const throttledScroll = useCallback(
  throttle(() => { /* handle scroll */ }, 200),
  []
);
useEffect(() => {
  window.addEventListener('scroll', throttledScroll);
  return () => window.removeEventListener('scroll', throttledScroll);
}, []);
```

---

### Is it keys should be globally unique?

Keys used within arrays should be unique among their siblings but they don’t need to be globally unique. i.e, You can use the same keys with two different arrays.

For example, the below book component uses two arrays with different arrays,


```
function Book(props) {
  const index = (
    <ul>
      {props.pages.map((page) => (
        <li key={page.id}>{page.title}</li>
      ))}
    </ul>
  );
  const content = props.pages.map((page) => (
    <div key={page.id}>
      <h3>{page.title}</h3>
      <p>{page.content}</p>
      <p>{page.pageNumber}</p>
    </div>
  ));
  return (
    <div>
      {index}
      <hr />
      {content}
    </div>
  );
}

```

[

---

### Is it mandatory to define constructor for React component?

No, it is not mandatory. i.e, If you don't initialize state and you
don't bind methods, you don't need to implement a constructor for your
React component.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Is it prop must be named as render for render props?

Even though the pattern named render props, you don't have to use a prop
named render to use this pattern. i.e, Any prop that is a function that
a component uses to know what to render is technically a "render prop".
Lets take an example with the children prop for render props,

    <Mouse
      children={(mouse) => (
        <p>
          The mouse position is {mouse.x}, {mouse.y}
        </p>
      )}
    />

Actually children prop doesn't need to be named in the list of
"attributes" in JSX element. Instead, you can keep it directly inside
element,

    <Mouse>
      {(mouse) => (
        <p>
          The mouse position is {mouse.x}, {mouse.y}
        </p>
      )}
    </Mouse>

While using this above technique(without any name), explicitly state
that children should be a function in your propTypes.

    Mouse.propTypes = {
      children: PropTypes.func.isRequired,
    };

------------------------------------------------------------------------

---

---

### Is it ref argument available for all functions or class components?

Regular function or class components don’t receive the ref argument, and ref is not available in props either. The second ref argument only exists when you define a component with React.forwardRef call.

[

---

### Library Upgrade: A component breaks when upgrading a library version -- how do you manage dependencies?

**Approach**: 1. **Read release notes** and changelogs carefully for
breaking changes. 2. **Test in isolation** -- create a branch, upgrade
the library, run tests, and manually test affected components. 3. **Use
dependency management tools** -- `npm outdated` to see which libraries
can be upgraded. `npm audit` for security. 4. **Pin exact versions** in
`package.json` for critical libraries to avoid unexpected upgrades. 5.
**Use version ranges** for non‑critical ones, but lock with
`package-lock.json` or `yarn.lock`. 6. **Implement abstraction** -- wrap
external libraries in your own adapter components to isolate changes. 7.
**Stagger upgrades** -- upgrade one library at a time to isolate issues.
8. **Rollback** -- if a critical break occurs, revert the version and
investigate later.

**For major upgrades** (e.g., React 16 → 17 → 18): - Use codemods (like
`react-codemod`) to automate migration. - Run in development mode to
catch deprecation warnings. - Test across all browsers and devices.

------------------------------------------------------------------------

---

---

### Must prop be named as render for render props?

Even though the pattern named render props, you don't have to use a prop
named render to use this pattern. i.e, Any prop that is a function that
a component uses to know what to render is technically a "render prop".
Lets take an example with the children prop for render props,

     ```javascript
     <Mouse
       children={(mouse) => (
         <p>
           The mouse position is {mouse.x}, {mouse.y}
         </p>
       )}
     />
     ```

     Actually children prop doesn’t need to be named in the list of “attributes” in JSX element. Instead, you can keep it directly inside element,

     ```javascript
     <Mouse>
       {(mouse) => (
         <p>
           The mouse position is {mouse.x}, {mouse.y}
         </p>
       )}
     </Mouse>
     ```

     While using this above technique(without any name), explicitly state that children should be a function in your propTypes.

     ```javascript
     Mouse.propTypes = {
       children: PropTypes.func.isRequired,
     };
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Situation: A third-party component throws -- how do you handle it?

Wrap it in an error boundary. Log errors in `componentDidCatch` to a
monitoring service (Sentry, Datadog). Show a friendly fallback.
Optionally provide a 'Try Again' button that resets the boundary state.

------------------------------------------------------------------------

---

---

### Situation: Two components on different branches need the same data – what do you do?

Options: (1) Lift state to nearest common ancestor. (2) Put it in Context. (3) Use a global state store. (4) If server data, use React Query – both components call the same `useQuery` key and share a cache automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are components? Functional vs class components.

Components are the building blocks of a React application. They accept inputs (props) and return React elements describing what should appear on screen.

- **Functional components**: Plain JavaScript functions that accept props and return JSX. They are simpler, support hooks, and are the preferred way to write components today.
- **Class components**: ES6 classes that extend `React.Component` and must implement a `render` method. They have lifecycle methods (`componentDidMount`, etc.) and state management via `this.state` and `this.setState`.

---

### What are compound components?

Compound Components are a group of components that work together as a team to handle one big job, sharing a hidden brain behind the scenes. E.g., `<Select>`, `<Select.Option>`, `<Select.Trigger>`. The parent manages state; children are compositionally flexible. Used in UI libraries (Headless UI, Radix).

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are controlled components?

A **controlled component** is a React component that **fully manages the form element's state**(e.g, elements like `<input>`, `<textarea>`, or `<select>`))  using React's internal state mechanism. i.e, The component does not manage its own internal state — instead, React acts as the single source of truth for form data.

        The controlled components will be implemented using the below steps,

        1. Initialize the state using `useState` hooks in function components or inside constructor for class components.
        2. Set the value of the form element to the respective state variable.
        3. Create an event handler(`onChange`) to handle the user input changes through `useState`'s updater function or `setState` from class component.
        4. Attach the above event handler to form element's change or click events

        **Note:** React re-renders the component every time the input value changes.

       For example, the name input field updates the username using `handleChange` event handler as below,

       ```javascript
       import React, { useState } from "react";

       function UserProfile() {
         const **

---

### What are controlled vs. uncontrolled components?

Controlled: form input value is driven by React state --- every
keystroke calls onChange which updates state which re-renders. React is
the source of truth. Enables: validation on every keystroke, conditional
disabling, programmatic control. Uncontrolled: input value lives in the
DOM --- React reads it via ref only when needed (on submit). Source of
truth is the DOM. Uncontrolled is simpler for basic forms; controlled is
needed for real-time validation, conditional logic, or syncing with
other state.

------------------------------------------------------------------------

---

---

### What are default props?

The _defaultProps_ can be defined as a property on the component to set the default values for the props. These default props are used when props not supplied(i.e., undefined props), but not for `null` or `0` as props. That means, If you provide null value then it remains null value. It's the same behavior with 0 as well.

         For example, let us create color default prop for the button component,

         ```javascript
         function MyButton {
           // ...
         }

         MyButton.defaultProps = {
           color: "red",
         };
         ```

         If `props.color` is not provided then it will set the default value to 'red'. i.e, Whenever you try to access the color prop it uses the default value

         ```javascript
         function MyButton() {
           return <MyButton />; // props.color will contain red value
         }
         ```

    ****

---

### What are default props and PropTypes?

defaultProps (The Backup Plan) This provides a fallback value just in
case a parent component forgets to pass a prop.

Analogy: If you don't explicitly choose a side dish, the restaurant
automatically defaults to giving you fries.

PropTypes (The Bouncer) This checks the props coming in to make sure
they are the correct type (like a number, a string, or a boolean) and
warns you in the developer console if someone made a mistake.

Analogy: A bouncer checking IDs. If a developer tries to pass the word
"Twenty" into an age prop that expects the actual number 20, PropTypes
throws a warning flag.

------------------------------------------------------------------------

---

---

### What are fragments?

Syntax for returning multiple elements without an extra DOM node: `<> </>` or `<React.Fragment>`. Keyed fragments use the long form: `<React.Fragment key={id}>`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are headless components?

Components that provide behavior, accessibility, and state management with no UI – consumers apply their own styles. Examples: Radix UI, Headless UI, React Aria. Powerful for design systems needing full styling control.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are Higher Order Components?

Simply put, Higher-Order Component(HOC) is a function that takes in a component and returns a new component. 

**When do we need a Higher Order Component?**

While developing React applications, we might develop components that are quite similar to each other with minute differences. In most cases, developing similar components might not be an issue but, while developing larger applications we need to keep our code **DRY**, therefore, we want an **abstraction** that allows us to define this logic in a single place and share it across components. HOC allows us to create that abstraction.

**Example of a HOC:**

Consider the following components having similar functionality. The following component displays the list of articles:

```
// "GlobalDataSource" is some global data source
class ArticlesList extends React.Component {
 constructor(props) {
   super(props);
   this.handleChange = this.handleChange.bind(this);
   this.state = {
     articles: GlobalDataSource.getArticles(),
   };
 }
 componentDidMount() {
   // Listens to the changes added
   GlobalDataSource.addChangeListener(this.handleChange);
 }
 componentWillUnmount() {
   // Listens to the changes removed
   GlobalDataSource.removeChangeListener(this.handleChange);
 }
 handleChange() {
   // States gets Update whenver data source changes
   this.setState({
     articles: GlobalDataSource.getArticles(),
   });
 }
 render() {
   return (
     <div>
       {this.state.articles.map((article) => (
         <ArticleData article={article} key={article.id} />
       ))}
     </div>
   );
 }
}
```

The following component displays the list of users:

```
// "GlobalDataSource" is some global data source
class UsersList extends React.Component {
 constructor(props) {
   super(props);
   this.handleChange = this.handleChange.bind(this);
   this.state = {
     users: GlobalDataSource.getUsers(),
   };
 }
 componentDidMount() {
   // Listens to the changes added
   GlobalDataSource.addChangeListener(this.handleChange);
 }
 componentWillUnmount() {
   // Listens to the changes removed
   GlobalDataSource.removeChangeListener(this.handleChange);
 }
 handleChange() {
   // States gets Update whenver data source changes
   this.setState({
     users: GlobalDataSource.getUsers(),
   });
 }
 render() {
   return (
     <div>
       {this.state.users.map((user) => (
         <UserData user={user} key={user.id} />
       ))}
     </div>
   );
 }
}
```

Notice the above components, both have similar functionality but, they are calling different methods to an API endpoint.

Let’s create a Higher Order Component to create an abstraction:

```
// Higher Order Component which takes a component
// as input and returns another component
// "GlobalDataSource" is some global data source
function HOC(WrappedComponent, selectData) {
 return class extends React.Component {
   constructor(props) {
     super(props);
     this.handleChange = this.handleChange.bind(this);
     this.state = {
       data: selectData(GlobalDataSource, props),
     };
   }
   componentDidMount() {
     // Listens to the changes added
     GlobalDataSource.addChangeListener(this.handleChange);
   }
   componentWillUnmount() {
     // Listens to the changes removed
     GlobalDataSource.removeChangeListener(this.handleChange);
   }
   handleChange() {
     this.setState({
       data: selectData(GlobalDataSource, this.props),
     });
   }
   render() {
     // Rendering the wrapped component with the latest data data
     return <WrappedComponent data={this.state.data} {...this.props} />;
   }
 };
}
```

We know HOC is a function that takes in a component and returns a component.

In the code above, we have created a function called HOC which returns a component and performs functionality that can be shared across both the **ArticlesList** component and **UsersList** Component.

The second parameter in the HOC function is the function that calls the method on the API endpoint.

We have reduced the duplicated code of the **componentDidUpdate** and **componentDidMount** functions.

Using the concept of Higher-Order Components, we can now render the **ArticlesList** and **UsersList **components in the following way:

```
const ArticlesListWithHOC = HOC(ArticlesList, (GlobalDataSource) => GlobalDataSource.getArticles());
const UsersListWithHOC = HOC(UsersList, (GlobalDataSource) => GlobalDataSource.getUsers());
```

Remember, we are not trying to change the functionality of each component, we are trying to share a single functionality across multiple components using HOC.

---

### What are Higher-Order Components (HOCs)?

Functions that take a component and return a new component with enhanced behavior. E.g., `withAuth(Component)` wraps it to redirect if unauthenticated. HOCs are less common now that custom hooks exist.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are HOC factory implementations?

There are two main ways of implementing HOCs in React.

    1.  Props Proxy (PP) and
    2.  Inheritance Inversion (II).

    But they follow different approaches for manipulating the _WrappedComponent_.

    **Props Proxy**

    In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name **Props Proxy**.

    ```jsx
    function ppHOC(WrappedComponent) {
      return class PP extends React.Component {
        render() {
          return <WrappedComponent {...this.props} />;
        }
      };
    }
    ```

    **Inheritance Inversion**

    In this approach, the returned HOC class (Enhancer) extends the WrappedComponent. It is called Inheritance Inversion because instead of the WrappedComponent extending some Enhancer class, it is passively extended by the Enhancer. In this way the relationship between them seems **inverse**.

    ```jsx
    function iiHOC(WrappedComponent) {
      return class Enhancer extends WrappedComponent {
        render() {
          return super.render();
        }
      };
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are Keyed Fragments?

The Fragments declared with the explicit syntax may have keys. The general use case is mapping a collection to an array of fragments as below,


```
function Glossary(props) {
  return (
    <dl>
      {props.items.map((item) => (
        // Without the `key`, React will fire a key warning
        <React.Fragment key={item.id}>
          <dt>{item.term}</dt>
          <dd>{item.description}</dd>
        </React.Fragment>
      ))}
    </dl>
  );
}

```

**Note:** key is the only attribute that can be passed to Fragment. In the future, there might be a support for additional attributes, such as event handlers.

[

---

### What are keys in React?

A key is a special string attribute that needs to be included when using lists of elements.

    Example of a list using key -

const ids = \[1,2,3,4,5\]; const listElements = ids.map((id)=\>{ return(
```{=html}
<li key="{id.toString()}">
```
{id}
```{=html}
</li>
```
) })


    **Importance of keys -**

    - Keys help react identify which elements were added, changed or removed.
    - Keys should be given to array elements for providing a unique identity for each element.
    - Without keys, React does not understand the order or uniqueness of each element.
    - With keys, React has an idea of which particular element was deleted, edited, and added.
    - Keys are generally used for displaying a list of data coming from an API.

    > \*\*\*Note- Keys used within arrays should be unique among siblings. They need not be globally unique.

    ## Learn via our Video Courses

    [Rahul Janghu](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [**Python Course for Beginners With Certification: Mastering the Essentials**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [4.90](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 273136](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Aditya Jain](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli)

    [**Free Data Structures and Algorithms (DSA) in C++ Online Course with Certificate**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli)

    [4.5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli)

    [Enrolled: 45488](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli)

    [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli)

    [**C++ Course: Learn the Essentials**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli)

    [Enrolled: 82805](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==)

    [**Python and SQL for Data Science Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 79131](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==)

    [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=)

    [**Node JS Certification Course - Master the Fundamentals**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=)

    [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 27194](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=)

    [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli)

    [**SQL for Beginners: Learn SQL using MySQL and Database Design Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli)

    [Enrolled: 59986](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli)

    [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [**JavaScript Course With Certification: Unlocking the Power of JavaScript**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 98373](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [**Computer Networking Course: Master Computer Networking**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 40401](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Sumeet malik](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=)

    [**NSET Course: Mathematics**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=)

    [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 13703](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Sumeet malik](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=)

    [**NSET Course: Logical reasoning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=)

    [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 12705](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli)

    [**Operating System Course: Learn Fundamentals of Operating System**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli)

    [Enrolled: 39702](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=)

    [**Microsoft Malware Detection using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 1578](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==)

    [**Netflix Movie Recommendation System using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 2950](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli)

    [**Amazon Fashion Discovery Engine using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli)

    [Enrolled: 990](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==)

    [**Personalized Cancer Diagnosis using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 952](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli)

    [**Facebook Friend Recommendation using Graph Mining**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli)

    [Enrolled: 709](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=)

    [**Predicting tags for Stackoverflow using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 564](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==)

    [**Quora Question Pair Similarity Problem using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 636](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=)

    [**Taxi demand prediction in New York City using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 680](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=)

    [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [**React JS Free Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 29162](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Yash Raj](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [**AWS Free Course with Certificate for Beginners**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 17390](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Subhesh Kumar](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==)

    [**Object Oriented Programming in Java Course Online**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==)

    [4.95](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 14722](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [**Free Maths for Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 11674](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [**Deep Learning Course: Deep Dive into Deep Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Enrolled: 10662](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Jamshaid Sohail](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [**PyTorch for Deep Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Enrolled: 4313](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli)

    [**Supervised Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli)

    [Enrolled: 17407](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli)

    [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [**Unsupervised Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 5206](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=)

    [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=)

    [**Maths for Programmers**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=)

    [Enrolled: 7881](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=)

    [Gaurav Sisodia](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli)

    [**Keras & TensorFlow for Deep Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli)

    [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli)

    [Enrolled: 4201](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli)

    [Arnav Gupta](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==)

    [**Spring Boot Course: Certified Course for Essential Skills**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==)

    [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==)

    [Enrolled: 24148](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==)

    [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==)

---

### What are loadable components?

If you want to do code-splitting in a server rendered app, it is recommend to use Loadable Components because React.lazy and Suspense is not yet available for server-side rendering. Loadable lets you render a dynamic import as a regular component.

Lets take an example,


```
import loadable from '@loadable/component';

const OtherComponent = loadable(() => import('./OtherComponent'));

function MyComponent() {
  return (
    <div>
      <OtherComponent />
    </div>
  );
}

```

Now OtherComponent will be loaded in a separated bundle

[

---

### What are portals?

A React Portal is like a teleportation device for your UI. It lets you write the code for a component inside a parent, but physically display it somewhere else on the page (usually floating over the whole screen).

Use it for: Popups, modals, and tooltips so they don't get cut off or trapped by their parent container's layout rules.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are portals in React?

A Portal is a React feature that enables rendering children into a DOM node that exists outside the parent component's DOM hierarchy, while still preserving the React component hierarchy. Portals help avoid CSS stacking issues—for example, elements with position: fixed may not behave as expected inside a parent with transform. Portals solve this by rendering content (like modals or tooltips) outside such constrained DOM contexts.

        ```javascript
        ReactDOM.createPortal(child, container);
        ```
        *   `child`: Any valid React node (e.g., JSX, string, fragment).
        *   `container`: A real DOM node (e.g., `document.getElementById('modal-root')`).

        Even though the content renders elsewhere in the DOM, it still behaves like a normal child in React. It has access to context, state, and event handling.

        **Example:- Modal:**
        ```jsx
        function Modal({ children }) {
          return ReactDOM.createPortal(
            <div className="modal">{children}</div>,
            document.body)
          );
        }
        ```
        The above code will render the modal content into the body element in the HTML, not inside the component's usual location.

        ****

---

### What are presentational vs container components?

Presentational: concern is how things look, receive data via props, rarely have own state. Container: concern is how things work, handle data fetching and state, pass data to presentational children. The pattern is less strict now that hooks exist.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are props?

Read-only inputs passed from parent to child. Props flow downward
(one-way data flow). Mutating props directly is forbidden; instead lift
state or use callbacks.

------------------------------------------------------------------------

---

---

### What are props in React?

The props in React are the inputs to a component of React. They can be single-valued or objects having a set of values that will be passed to components of React during creation by using a naming convention that almost looks similar to HTML-tag attributes. We can say that props are the data passed from a parent component into a child component.

    The main purpose of props is to provide different component functionalities such as:

    - Passing custom data to the React component.
    - Using through `this.props.reactProp` inside render() method of the component.
    - Triggering state changes.

    For example, consider we are creating an element with reactProp property as given below: `<Element reactProp = "1" />`
    This reactProp name will be considered as a property attached to the native props object of React which already exists on each component created with the help of React library: `props.reactProp;`.

---

### What are pure components?

Components that produce the same output for the same props/state. `React.PureComponent` (class) and `React.memo` (function) implement shallow-equality checks to skip redundant renders.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are React elements vs React components?

React Elements (The Lego Brick) An element is a single, plain blueprint
of what you want to see on the screen. It doesn't actually do anything
yet; it's just a simple JavaScript object that describes a piece of the
UI.

Analogy: A single Lego block or a sketch of a window.

What it looks like: { type: 'div', props: { className: 'box', children:
'Hello' } }

React Components (The Factory / Blueprint) A component is the factory,
function, or template that creates those elements. It takes in some data
(called props) and outputs React elements.

Analogy: The master blueprint or the factory mold that can stamp out
hundreds of Lego blocks.

What it looks like: A JavaScript function like function Button() {
return `<button />`{=html} }.

------------------------------------------------------------------------

---

---

### What are React Portals, and when would you use them?

When you work with React, you might have noticed how a component renders inside its parent in the DOM.

    But even so, there are times when you don’t necessarily want that.

    For example, think of a modal. Even if the modal component is written deep inside your component tree, you usually want it to appear at the top of the page, and not stuck inside some parent container.

    And to mitigate this very problem, Portals are used.

    So, you don't have to render from your usual place, and run something like:

ReactDOM.createPortal(child, container)


    This practically commands to render the component elsewhere in the DOM.

    Now, here’s how you can set it up:

    First write,

     

::: {#modal-root}
:::


    Then, from anywhere in your React app, you can render into it like this:

     

ReactDOM.createPortal(`<Modal />`{=html},
document.getElementById("modal-root"));


    Even when it’s done, you need to keep this in mind that even though the modal is rendered outside the parent in the DOM, it still showcases like a normal React child. Which means that it still receives props, it still has access to context, and event handling still works.

    In fact, event bubbling can take place here. If you click inside a modal rendered via a portal, the event still bubbles up to the parent component in the React tree, and not based on the DOM structure.

    Now, coming to when to use these Portals,

    You can say that mostly when UI needs to “break out” of layout restrictions like overflow: hidden, z-index stacking issues.

    That’s why they’re commonly used for modals, tooltips, dropdowns, and toast notifications.

---

### What are render props?

**Render Props** is a simple technique for sharing code between
components using a prop whose value is a function. The below component
uses render prop which returns a React element.

    ```jsx harmony
    <DataProvider render={(data) => <h1>{`Hello ${data.target}`}</h1>} />
    ```

    Libraries such as React Router and DownShift are using this pattern.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are state and props?

Props (properties) are read-only data passed FROM parent TO child
components --- like function arguments. They cannot be modified by the
receiving component. State is mutable data managed INSIDE a component.
When state changes, React re-renders that component and its children.
Key distinction: props flow down (parent → child), events/callbacks flow
up (child → parent). Props changes cause re-renders too --- React
re-renders a component whenever its parent re-renders OR its own state
changes.

------------------------------------------------------------------------

---

---

### What are state and props? Difference between them.

- **Props** (short for properties): Read‑only data passed from parent to child. They are immutable within the child component.
- **State**: Mutable data managed within a component. When state changes, the component re‑renders.

| | Props | State |
|---|-------|-------|
| Mutability | Immutable (cannot be changed by child) | Mutable (changed via `setState` or hook setters) |
| Ownership | Owned by parent, used by child | Owned by the component itself |
| Purpose | Configure component, pass data down | Handle dynamic data that changes over time |

---

### What are stateful components?

If the behaviour of a component is dependent on the _state_ of the component then it can be termed as stateful component. These _stateful components_ are either function components with hooks or _class components_.

        Let's take an example of function stateful component which update the state based on click event,

        ```javascript
        import React, {useState} from 'react';

        const App = (props) => {
        const **

---

### What are stateless components?

If the behaviour of a component is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless you need to use a lifecycle hook in your components, you should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the `this` keyword altogether.

        ****

---

### What are Styled Components?

`styled-components` is a JavaScript library for styling React applications. It removes the mapping between styles and components, and lets you write actual CSS augmented with JavaScript.

    ****

---

### What are the differences between controlled and uncontrolled components?

Controlled and uncontrolled components are just different approaches to handling input from elements in react. 

    | FeatureUncontrolledControlledName attrs   |    |    |    |
    | ----------------------------------------- | -- | -- | -- |
    | One-time value retrieval (e.g. on submit) | ✔️ | ✔️ | ✔️ |
    | Validating on submit                      | ✔️ | ✔️ | ✔️ |
    | Field-level Validation                    | ❌  | ✔️ | ✔️ |
    | Conditionally disabling submit button     | ❌  | ✔️ | ✔️ |
    | Enforcing input format                    | ❌  | ✔️ | ✔️ |
    | several inputs for one piece of data      | ❌  | ✔️ | ✔️ |
    | dynamic inputs                            | ❌  | ✔️ | 🤔 |

    - **Controlled component: **In a controlled component, the value of the input element is controlled by React. We store the state of the input element inside the code, and by using event-based callbacks, any changes made to the input element will be reflected in the code as well.

    When a user enters data inside the input element of a controlled component, onChange function gets triggered and inside the code, we check whether the value entered is valid or invalid. If the value is valid, we change the state and re-render the input element with the new value.

    Example of a controlled component:

function FormValidation(props) { let \[inputValue, setInputValue\] =
useState(""); let updateInput = e =\> { setInputValue(e.target.value);
}; return (

<div>

    <form>
      <input type="text" value={inputValue} onChange={updateInput} />
    </form>

</div>

); }


    As one can see in the code above, the value of the input element is determined by the state of the** inputValue **variable. Any changes made to the input element is handled by the **updateInput** function.

    - **Uncontrolled component:** In an uncontrolled component, the value of the input element is handled by the DOM itself. Input elements inside uncontrolled components work just like normal HTML input form elements.

    The state of the input element is handled by the DOM. Whenever the value of the input element is changed, event-based callbacks are not called. Basically, react does not perform any action when there are changes made to the input element.

    Whenever use enters data inside the input field, the updated data is shown directly. To access the value of the input element, we can use **ref**.

    Example of an uncontrolled component:

function FormValidation(props) { let inputValue = React.createRef(); let
handleSubmit = e =\> {
alert(`Input value: ${inputValue.current.value}`); e.preventDefault();
}; return (

<div>

    <form onSubmit={handleSubmit}>
      <input type="text" ref={inputValue} />
      <button type="submit">Submit</button>
    </form>

</div>

); }


    As one can see in the code above, we are **not** using **onChange** function to govern the changes made to the input element. Instead, we are using **ref** to access the value of the input element.

---

### What are the differences between functional and class components?

Before the introduction of Hooks in React, functional components were called stateless components and were behind class components on a feature basis. After the introduction of Hooks, functional components are equivalent to class components.

Although functional components are the new trend, the react team insists on keeping class components in React. Therefore, it is important to know how these components differ.

On the following basis let’s compare functional and class components:

- **Declaration**

Functional components are nothing but JavaScript functions and therefore can be declared using an arrow function or the function keyword:

```
  function card(props){
   return(
      <div className="main-container">
        <h2>Title of the card</h2>
      </div>
    )
   }
   const card = (props) =>{
    return(
      <div className="main-container">
        <h2>Title of the card</h2>
      </div>
    )
   }
```

Class components, on the other hand, are declared using the ES6 class:

```
 class Card extends React.Component{
  constructor(props){
     super(props);
   }
    render(){
      return(
        <div className="main-container">
          <h2>Title of the card</h2>
        </div>
      )
    }
   }
```

- **Handling props**

Let’s render the following component with props and analyse how functional and class components handle props:

```
<Student Info name="Vivek" rollNumber="23" />
```

In functional components, the handling of props is pretty straightforward. Any prop provided as an argument to a functional component can be directly used inside HTML elements:

```
 function StudentInfo(props){
   return(
     <div className="main">
       <h2>{props.name}</h2>
       <h4>{props.rollNumber}</h4>
     </div>
   )
 }
```

In the case of class components, props are handled in a different way:

```
 class StudentInfo extends React.Component{
   constructor(props){
     super(props);
    }
    render(){
      return(
        <div className="main">
          <h2>{this.props.name}</h2>
          <h4>{this.props.rollNumber}</h4> 
        </div>
      )
    }
   }
```

As we can see in the code above, **this **keyword is used in the case of class components.

- **Handling state**

Functional components use React hooks to handle state. It uses the useState hook to set the state of a variable inside the component:

```
 function ClassRoom(props){
   let [studentsCount,setStudentsCount] = useState(0);
    const addStudent = () => {
      setStudentsCount(++studentsCount);
   }
    return(
      <div>
        <p>Number of students in class room: {studentsCount}</p>
        <button onClick={addStudent}>Add Student</button>
      </div>
    )
   }
```

Since useState hook returns an array of two items, the first item contains the current state, and the second item is a function used to update the state.

In the code above, using array destructuring we have set the variable name to studentsCount with a current value of “0” and setStudentsCount is the function that is used to update the state.

For reading the state, we can see from the code above, the variable name can be directly used to read the current state of the variable.

We cannot use React Hooks inside class components, therefore state handling is done very differently in a class component:

Let’s take the same above example and convert it into a class component:

```
class ClassRoom extends React.Component{
        constructor(props){
            super(props);
            this.state = {studentsCount : 0};
            
            this.addStudent = this.addStudent.bind(this);
         }
            
            addStudent(){
            this.setState((prevState)=>{
               return {studentsCount: prevState.studentsCount++}
            });
         }
            
            render(){
             return(
               <div>
                 <p>Number of students in class room: {this.state.studentsCount}</p>
                 <button onClick={this.addStudent}>Add Student</button>
               </div>
             )
           }
         }  
```

In the code above, we see we are using **this.state** to add the variable studentsCount and setting the value to “0”.

For reading the state, we are using **this.state.studentsCount**.

For updating the state, we need to first bind the addStudent function to **this**. Only then, we will be able to use the **setState** function which is used to update the state. 

Advance your career with  **Mock Assessments**

Real-world coding challenges for top company interviews

Real-Life Problems

Detailed reports

**Attempt Now**

---

### What are the different ways to style a React component?

There are many different ways through which one can style a React component. Some of the ways are :

- **Inline Styling: **We can directly style an element using inline style attributes. Make sure the value of style is a JavaScript object:

```
class RandomComponent extends React.Component {
 render() {
   return (
     <div>
       <h3 style={{ color: "Yellow" }}>This is a heading</h3>
       <p style={{ fontSize: "32px" }}>This is a paragraph</p>
     </div>
   );
 }
}
```

- **Using JavaScript object: **We can create a separate JavaScript object and set the desired style properties. This object can be used as the value of the inline style attribute.

```
class RandomComponent extends React.Component {
 paragraphStyles = {
   color: "Red",
   fontSize: "32px"
 };

 headingStyles = {
   color: "blue",
   fontSize: "48px"
 };

 render() {
   return (
     <div>
       <h3 style={this.headingStyles}>This is a heading</h3>
       <p style={this.paragraphStyles}>This is a paragraph</p>
     </div>
   );
 }
}
```

- **CSS Stylesheet: **We can create a separate CSS file and write all the styles for the component inside that file. This file needs to be imported inside the component file.

```
import './RandomComponent.css';

class RandomComponent extends React.Component {
 render() {
   return (
     <div>
       <h3 className="heading">This is a heading</h3>
       <p className="paragraph">This is a paragraph</p>
     </div>
   );
 }
}
```

- **CSS Modules:** We can create a separate CSS module and import this module inside our component. Create a file with “.module.css”‘ extension, styles.module.css:

```
.paragraph{
 color:"red";
 border:1px solid black;
}
```

We can import this file inside the component and use it:

```
import styles from  './styles.module.css';

class RandomComponent extends React.Component {
 render() {
   return (
     <div>
       <h3 className="heading">This is a heading</h3>
       <p className={styles.paragraph} >This is a paragraph</p>
     </div>
   );
 }
}
```

---

### What are the exceptions on React component naming?

The component names should start with an uppercase letter but there are few exceptions to this convention. The lowercase tag names with a dot (property accessors) are still considered as valid component names.
        For example, the below tag can be compiled to a valid component,

        ```jsx harmony
             render() {
                  return (
                    <obj.component/> // `React.createElement(obj.component)`
                  )
            }
        ```

        ****

---

### What are the hidden reasons a component re‑renders even when props don't change?

- **Parent re‑render**: By default, when a parent re‑renders, all its children re‑render, regardless of prop changes. (Fixed with `React.memo`)
    - **Inline functions/objects**: If you pass an inline function or object as prop, the child sees a new reference on every render, causing a re‑render (unless the child is memoized and uses deep comparison or the prop is memoized).
    - **Context changes**: If the component consumes a context that changes, it re‑renders.
    - **Hooks with changing dependencies**: `useEffect`, `useMemo`, `useCallback` dependencies may cause re‑execution of hooks, but not necessarily the whole component re‑render.
    - **State updates that set the same value**: In React 18, if you set state to the same value (using `setState(prev => prev)`), it may still cause a re‑render in some cases (but not in strict mode?).

---

### What are the limitations with HOCs?

Higher-order components come with a few caveats apart from its benefits. Below are the few listed in an order,

1. **Don’t use HOCs inside the render method:** It is not recommended to apply a HOC to a component within the render method of a component.

```
render() {
  // A new version of EnhancedComponent is created on every render
  // EnhancedComponent1 !== EnhancedComponent2
  const EnhancedComponent = enhance(MyComponent);
  // That causes the entire subtree to unmount/remount each time!
  return <EnhancedComponent />;
}

```

The above code impact performance by remounting a component that causes the state of that component and all of its children to be lost. Instead, apply HOCs outside the component definition so that the resulting component is created only once.

1. **Static methods must be copied over:** When you apply a HOC to a component the new component does not have any of the static methods of the original component

```
// Define a static method
WrappedComponent.staticMethod = function () {
  /*...*/
};
// Now apply a HOC
const EnhancedComponent = enhance(WrappedComponent);

// The enhanced component has no static method
typeof EnhancedComponent.staticMethod === 'undefined'; // true

```

You can overcome this by copying the methods onto the container before returning it,


```
function enhance(WrappedComponent) {
  class Enhance extends React.Component {
    /*...*/
  }
  // Must know exactly which method(s) to copy :(
  Enhance.staticMethod = WrappedComponent.staticMethod;
  return Enhance;
}

```

1. **Refs aren’t passed through:** For HOCs you need to pass through all props to the wrapped component but this does not work for refs. This is because ref is not really a prop similar to key. In this case you need to use the React.forwardRef API

[

---

### What are the possible ways of updating objects in state?

1.  **Calling `setState()` with an object to merge with state:**

        - Using `Object.assign()` to create a copy of the object:

          ```javascript
          const user = Object.assign({}, this.state.user, { age: 42 });
          this.setState({ user });
          ```

        - Using _spread operator_:

          ```javascript
          const user = { ...this.state.user, age: 42 };
          this.setState({ user });
          ```

    2.  **Calling `setState()` with a function:**

        ``` javascript
        this.setState((prevState) => ({
          user: {
            ...prevState.user,
            age: 42,
          },
        }));
        ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are the preferred and non-preferred array operations for updating the state?

The below table represent preferred and non-preferred array operations
for updating the component state.

      | Action    | Preferred            | Non-preferred              |
      | --------- | -------------------- | -------------------------- |
      | Adding    | concat, **

------------------------------------------------------------------------

---

---

### What are the problems of using render props with pure components?

If you create a function inside a render method, it negates the purpose
of pure component. Because the shallow prop comparison will always
return false for new props, and each render in this case will generate a
new value for the render prop. You can solve this issue by defining the
render function as instance method.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are uncontrolled components?

The **Uncontrolled components** are form elements (like `<input>`, `<textarea>`, or `<select>`) that **manage their own state internally** via the **DOM**, rather than through React state.
        You can query the DOM using a `ref` to find its current value when you need it. This is a bit more like traditional HTML.

        The uncontrolled components will be implemented using the below steps,

        1. Create a ref using `useRef` react hook in function component or `React.createRef()` in class based component.
        2. Attach this `ref` to the form element.
        3. The form element value can be accessed directly through `ref` in event handlers or `componentDidMount` for class components

        In the below UserProfile component, the `username` input is accessed using ref.

        ```jsx harmony
        import React, { useRef } from "react";

        function UserProfile() {
          const usernameRef = useRef(null);

          const handleSubmit = (event) => {
            event.preventDefault();
            console.log("The submitted username is: " + usernameRef.current.value);
          };

          return (
            <form onSubmit={handleSubmit}>
              <label>
                Username:
                <input type="text" ref={usernameRef} />
              </label>
              <button type="submit">Submit</button>
            </form>
          );
        }
        ```
        **Note:** Here, DOM is in charge of the value. React only accesses the value when needed (via `ref`).

        **Benefits:**
         *   **Less boilerplate** — no need for `useState` and `onChange`.
         *   Useful for **quick form setups** or when integrating with **non-React code**.
         *   Slightly better **performance** in very large forms (fewer re-renders).

        In most cases, it's recommend to use controlled components to implement forms. In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself.

        <details><summary><b>See Class</b></summary>
        <p>

        ```jsx harmony
        class UserProfile extends React.Component {
          constructor(props) {
            super(props);
            this.handleSubmit = this.handleSubmit.bind(this);
            this.input = React.createRef();
          }

          handleSubmit(event) {
            alert("A name was submitted: " + this.input.current.value);
            event.preventDefault();
          }

          render() {
            return (
              <form onSubmit={this.handleSubmit}>
                <label>
                  {"Name:"}
                  <input type="text" ref={this.input} />
                </label>
                <input type="submit" value="Submit" />
              </form>
            );
          }
        }
        ```

        </p>
        </details>

    ****

---

### What happens if you mutate state directly?

React does not detect the change and won't re-render. Always return new references: `setState([...arr])` or `setState({...obj})`. Direct mutation causes stale UI and hard-to-debug bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is a React component?

A reusable, self-contained piece of UI. It's a function (or class) that
accepts props and returns React elements. Components can be composed
together to build complex UIs.

------------------------------------------------------------------------

---

---

### What is a switching component?

A _switching component_ is a component that renders one of many components. We need to use object to map prop values to components.

        For example, a switching component to display different pages based on `page` prop:

        ```jsx harmony
        import HomePage from "./HomePage";
        import AboutPage from "./AboutPage";
        import ServicesPage from "./ServicesPage";
        import ContactPage from "./ContactPage";

        const PAGES = {
          home: HomePage,
          about: AboutPage,
          services: ServicesPage,
          contact: ContactPage,
        };

        const Page = (props) => {
          const Handler = PAGES**

---

### What is a wrapper component?

A wrapper in React is a component that wraps or surrounds another
component or group of components. It can be used for a variety of
purposes such as adding additional functionality, styling, or layout to
the wrapped components.

     For example, consider a simple component that displays a message:

     ```javascript
     const Message = ({ text }) => {
       return <p>{text}</p>;
     };
     ```

     We can create a wrapper component that will add a border to the message component:

     ```javascript
     const MessageWrapper = (props) => {
       return (
         <div style={{ border: "1px solid black" }}>
           <Message {...props} />
         </div>
       );
     };
     ```

     Now we can use the MessageWrapper component instead of the Message component and the message will be displayed with a border:

     ```javascript
     <MessageWrapper text="Hello World" />
     ```

     Wrapper component can also accept its own props and pass them down to the wrapped component, for example, we can create a wrapper component that will add a title to the message component:

     ```javascript
     const MessageWrapperWithTitle = ({ title, ...props }) => {
       return (
         <div>
           <h3>{title}</h3>
           <Message {...props} />
         </div>
       );
     };
     ```

     Now we can use the MessageWrapperWithTitle component and pass title props:

     ```javascript
     <MessageWrapperWithTitle title="My Message" text="Hello World" />
     ```

     This way, the wrapper component can add additional functionality, styling, or layout to the wrapped component while keeping the wrapped component simple and reusable.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is children prop?

The `children` prop is a special prop in React used to pass elements between the opening and closing tags of a component. It is commonly used in layout and wrapper componnents. 

        A simple usage of children prop looks as below,

        ```jsx harmony
        function MyDiv({ children }){
            return (
              <div>
                {children}
              </div>;
            );
        }

        export default function Greeting() {
          return (
            <MyDiv>
              <span>{"Hello"}</span>
              <span>{"World"}</span>
            </MyDiv>
          );
        }
        ```
        Here, everything inside `<MyDiv>...</MyDiv>` is passed as children to the custom div component.

        The children can be text, JSX elements, fragments, arrays and functions(for advance use case like render props).

        <details><summary><b>See Class</b></summary>
        <p>

        ```jsx harmony
        const MyDiv = React.createClass({
          render: function () {
            return <div>{this.props.children}</div>;
          },
        });

        ReactDOM.render(
          <MyDiv>
            <span>{"Hello"}</span>
            <span>{"World"}</span>
          </MyDiv>,
          node
        );
        ```

        </p>
        </details>

        **Note:** There are several methods available in the legacy React API to work with this prop. These include `React.Children.map`, `React.Children.forEach`, `React.Children.count`, `React.Children.only`, `React.Children.toArray`.

        ****

---

### What is `forwardRef`?

`React.forwardRef((props, ref) => ...)` passes a ref from a parent through a functional component to a DOM node or child component. Required because refs are not regular props and cannot be passed through as-is.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is forwardRef, and when do you need it?

This one is simple!

    You can use forwardRef to pass a ref from the parent component through the child component to a DOM element or another component inside it.

    You need it particularly because, by default, function components do not accept ref, as ref is not a regular prop, and it is handled separately by React.

    forwardRef is needed because it enables access to a child component’s DOM node, it helps in imperative actions like

.focus()


    ,

.scrollIntoView()


    , and measuring layout.

     

    So, when you don’t use forwardRef, the parent won’t be able to directly interact with the child’s internal DOM elements, and hence it may hinder when required to reuse.

    **This is how forwardRef works -**

    React.forwardRef wraps a functional component and provides ref as a second argument.

    This is the pattern:

     

const Input = React.forwardRef((props, ref) =\> { return \<input
ref={ref} {...props} /\>; });


    Here’s how you can use it:

     

const inputRef = useRef(); `<Input ref={inputRef} />`{=html}


    Now the parent can directly call:

inputRef.current.focus();


    Some common use cases are - integrating DOM libraries, focus management, triggering animations, measuring DOM elements, etc.

---

### What is lifting state up?

Moving shared state to the nearest common ancestor of components that
need it, then passing it down via props and up via callbacks. This keeps
state as the single source of truth.

------------------------------------------------------------------------

---

---

### What is Lifting State Up in React?

When several components need to share the same changing data then it is recommended to _lift the shared state up_ to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

        ****

---

### What is prop drilling and why is it a problem?

Passing props through many intermediate components that don't use them just to reach a deep child. It creates tight coupling and makes refactoring hard. Solved by Context, state management libraries, or component composition.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is prop drilling in React?

Sometimes while developing React applications, there is a need to pass data from a component that is higher in the hierarchy to a component that is deeply nested. To pass data between such components, we pass props from a source component and keep passing the prop to the next component in the hierarchy till we reach the deeply nested component.

    The **disadvantage** of using prop drilling is that the components that should otherwise be not aware of the data have access to the data.

---

### What is prop drilling? Problems and solutions.

Prop drilling is passing data through multiple layers of components via props, even when intermediate components don’t need that data. This makes code harder to maintain and refactor.

**Solutions**:
- **Context API**: Create a context and provide values at a higher level, then consume them deep down.
- **State management libraries**: Redux, Zustand, etc.
- **Component composition**: Instead of passing props, pass components as children or use render props to flatten the hierarchy.

---

### What is React.Fragment and why is it useful?

React's Fragment helps in grouping multiple elements together by being careful not to add an extra element to the DOM.

    Just like you know in React, every component MUST return a single parent element, and a fragment just acts like that parent, except it doesn’t actually show up in the final HTML.

    I’ll explain this to you with an example!

    If you write:

     

return ( \<\>
```{=html}
<h1>
```
Hello
```{=html}
</h1>
```
    <p>World</p>

\</\> );


    React will group these elements together using Fragment, but in the browser, it will render as:

     

```{=html}
<h1>
```
Hello
```{=html}
</h1>
```
```{=html}
<p>
```
World
```{=html}
</p>
```

    This shows that the Fragment is only used by React internally; it does not create an HTML element like a \<div>.

    Why do we use Fragment?

    Because sometimes using \<div> might cause some problems like breaking layouts on flexbox or grid, or creating invalid HTML (yes, this happens!)

    You can use it in these 2 ways:

    - \<React.Fragment> ... \</React.Fragment>
    - <> ... \</> - (short syntax)

    One thing you need to keep in mind is that only React.Fragment supports props like key, which comes in hand when rendering lists.

---

### What is server state vs client state?

Server state: data from APIs (users, posts) -- needs caching,
refetching, synchronization, background updates. Client state: local UI
state (modal open, form values) -- synchronous, lives only in the
browser.

------------------------------------------------------------------------

---

---

### What is state in React?

Mutable data owned by a component. When state changes, React schedules a re-render. State is private to the component unless shared via props or context. `useState` / `useReducer` manage it in functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is state mutation and how to prevent it?

`State mutation` happens when you try to update the state of a component
without actually using `setState` function. This can happen when you are
trying to do some computations using a state variable and unknowingly
save the result in the same state variable. This is the main reason why
it is advised to return new instances of state variables from the
reducers by using Object.assign({}, ...) or spread syntax.

    This can cause unknown issues in the UI as the value of the state variable got updated without telling React to check what all components were being affected from this update and it can cause UI bugs.

    Ex:

    ```javascript
    class A extends React.component {
      constructor(props) {
        super(props);
        this.state = {
          loading: false
        }
     }

    componentDidMount() {
      let { loading } = this.state;
      loading = (() => true)(); // Trying to perform an operation and directly saving in a state variable
    }

    ```

    **How to prevent it:** Make sure your state variables are immutable by either enforcing immutability by using plugins like Immutable.js, always using `setState` to make updates, and returning new instances in reducers when sending updated state values.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the container/presenter pattern and is it still relevant?

Separating data logic (container) from UI (presenter). Less strictly followed now – hooks handle data logic inside any component. But the concept of separating concerns is still valuable, enforced by custom hooks.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the controlled component pattern for reusable components?

This pattern creates a flexible component that can run on "autopilot" OR
be manually "steered" by its parent.

Instead of forcing a component to be strictly controlled or strictly
uncontrolled, you build it to support both modes seamlessly. A reusable
component can work in two modes: uncontrolled (manages own state) or
controlled (parent provides `value` + `onChange`). Example: an
`<Accordion>` that works out of the box but can also be fully
controlled.

------------------------------------------------------------------------

---

---

### What is the difference between an Element and a Component?

**Element:**
          - A React **Element** is a plain JavaScript object that describes what you want to see on the UI. It represents a DOM node or a component at a specific point in time. 
          - Elements are immutable: once created, you cannot change their properties. Instead, you create new elements to reflect updates.
          - Elements can be nested within other elements through their `props`.
          - Creating an element is a fast, lightweight operation—it does **not** create any actual DOM nodes or render anything to the screen directly.

            **Example (without JSX):**
            ```js
            const element = React.createElement("button", { id: "login-btn" }, "Login");
            ```

            **Equivalent JSX syntax:**
            ```jsx
            <button id="login-btn">Login</button>
            ```

            **The object returned by `React.createElement`:**
            ```js
            {
              type: 'button',
              props: {
                id: 'login-btn',
                children: 'Login'
              }
            }
            ```
            Elements are then passed to the React DOM renderer (e.g., `ReactDOM.render()`), which translates them to actual DOM nodes.


          **Component:**
          - A **Component** is a function or class that returns an element (or a tree of elements) to describe part of the UI. Components can accept inputs (called **props**) and manage their own state (in case of class or function components with hooks).
          - Components allow you to split the UI into independent, reusable pieces, each isolated and composable.
          - You can define a component using a function or a class:

            **Example (Function Component with JSX):**
            ```jsx
            const Button = ({ handleLogin }) => (
              <button id="login-btn" onClick={handleLogin}>
                Login
              </button>
            );
            ```

            When JSX is compiled, it's transformed into a tree of `React.createElement` calls:

            ```js
            const Button = ({ handleLogin }) =>
              React.createElement(
                "button",
                { id: "login-btn", onClick: handleLogin },
                "Login"
              );
            ```


          **In summary:**
          - **Elements** are the smallest building blocks in React—objects that describe what you want to see.
          - **Components** are functions or classes that return elements and encapsulate logic, structure, and behavior for parts of your UI.

           > Think of **elements** as the instructions for creating UI, and **components** as reusable blueprints that combine logic and structure to generate those instructions.

        ****

---

### What is the difference between props and state?

Props are external, immutable (from parent). State is internal, mutable
(managed by the component). Props configure a component; state tracks
what changes over time inside it.

------------------------------------------------------------------------

---

---

### What is the difference between state and props?

In React, both **state** and **props** are plain JavaScript objects, but they serve different purposes and have distinct behaviors:

        ### State
        - **Definition:**  
          State is a data structure that is managed within a component. It represents information that can change over the lifetime of the component.
        - **Mutability:**  
          State is mutable, meaning it can be changed using the setter function (`setState` in class components or the updater function from `useState` in functional components).
        - **Scope:**  
          State is local to the component where it is defined. Only that component can modify its own state.
        - **Usage:**  
          State is typically used for data that needs to change in response to user actions, network responses, or other dynamic events.
        - **Re-rendering:**  
          Updating the state triggers a re-render of the component and its descendants.

        ### Props
        - **Definition:**  
          Props (short for “properties”) are inputs to a component, provided by its parent component.
        - **Mutability:**  
          Props are read-only. A component cannot modify its own props; they are immutable from the component’s perspective.
        - **Scope:**  
          Props are used to pass data and event handlers down the component tree, enabling parent components to configure or communicate with their children.
        - **Usage:**  
          Props are commonly used to make components reusable and configurable. They allow the same component to be rendered with different data or behavior.
        - **Analogy:**  
          Think of props as arguments to a function, whereas state is like variables declared inside the function.

        ### Summary Table

        | Feature   | State                               | Props                             |
        |-----------|-------------------------------------|-----------------------------------|
        | Managed by| The component itself                | Parent component                  |
        | Mutable   | Yes                                 | No (read-only)                    |
        | Scope     | Local to the component              | Passed from parent to child       |
        | Usage     | Manage dynamic data and UI changes  | Configure and customize component |
        | Update    | Using setState/useState             | Cannot be updated by the component|


        ****

---

### What is the difference between `super()` and `super(props)` in React using ES6 classes?

When you want to access `this.props` in `constructor()` then you should
pass props to `super()` method.

    **Using `super(props)`:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super(props);
        console.log(this.props); // { name: 'John', ... }
      }
    }
    ```

    **Using `super()`:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super();
        console.log(this.props); // undefined
      }
    }
    ```

    Outside `constructor()` both will display same value for `this.props`.

    ****

------------------------------------------------------------------------

---

---

### What is the impact of indexes as keys?

Keys should be stable, predictable, and unique so that React can keep track of elements.

        In the below code snippet each element's key will be based on ordering, rather than tied to the data that is being represented. This limits the optimizations that React can do and creates confusing bugs in the application.

        ```jsx harmony
        {
          todos.map((todo, index) => <Todo {...todo} key={index} />);
        }
        ```

        If you use element data for unique key, assuming `todo.id` is unique to this list and stable, React would be able to reorder elements without needing to reevaluate them as much.

        ```jsx harmony
        {
          todos.map((todo) => <Todo {...todo} key={todo.id} />);
        }
        ```

        **Note:** If you don't specify `key` prop at all, React will use index as a key's value while iterating over an array of data.

        ****

---

### What is the `key` prop and why is it important?

A special string or number that uniquely identifies a list item. React uses keys to match items between renders for efficient reconciliation. Wrong or missing keys cause incorrect DOM reuse and subtle bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the purpose of forward ref in HOCs?

Refs will not get passed through because ref is not a prop. It handled differently by React just like **key**. If you add a ref to a HOC, the ref will refer to the outermost container component, not the wrapped component. In this case, you can use Forward Ref API. For example, we can explicitly forward refs to the inner FancyButton component using the React.forwardRef API.

The below HOC logs all props,


````
```javascript
function logProps(Component) {
  class LogProps extends React.Component {
    componentDidUpdate(prevProps) {
      console.log('old props:', prevProps);
      console.log('new props:', this.props);
    }

    render() {
      const {forwardedRef, ...rest} = this.props;

      // Assign the custom prop "forwardedRef" as a ref
      return <Component ref={forwardedRef} {...rest} />;
    }
  }

  return React.forwardRef((props, ref) => {
    return <LogProps {...props} forwardedRef={ref} />;
  });
}
```

````

Let's use this HOC to log all props that get passed to our “fancy button” component,


````
```javascript
class FancyButton extends React.Component {
  focus() {
    // ...
  }

  // ...
}
export default logProps(FancyButton);
```

````

Now lets create a ref and pass it to FancyButton component. In this case, you can set focus to button element.


````
```javascript
import FancyButton from './FancyButton';

const ref = React.createRef();
ref.current.focus();
<FancyButton
  label="Click Me"
  handleClick={handleClick}
  ref={ref}
/>;
```

````

[

---

### What is the purpose of getDerivedStateFromError?

This lifecycle method is invoked after an error has been thrown by a descendant component. It receives the error that was thrown as a parameter and should return a value to update state.

The signature of the lifecycle method is as follows,


```
static getDerivedStateFromError(error)

```

Let us take error boundary use case with the above lifecycle method for demonistration purpose,


```
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    // Update state so the next render will show the fallback UI.
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      // You can render any custom fallback UI
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children;
  }
}

```

[

---

### What is the purpose of unmountComponentAtNode method?

This method is available from react-dom package and it removes a mounted React component from the DOM and clean up its event handlers and state. If no component was mounted in the container, calling this function does nothing. Returns true if a component was unmounted and false if there was no component to unmount.

The method signature would be as follows,


```
ReactDOM.unmountComponentAtNode(container);

```

[

---

### What is the purpose of using super constructor with props argument?

A child class constructor cannot make use of `this` reference until the
`super()` method has been called. The same applies to ES6 sub-classes as
well. The main reason for passing props parameter to `super()` call is
to access `this.props` in your child constructors.

    **Passing props:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super(props);

        console.log(this.props); // prints { name: 'John', age: 42 }
      }
    }
    ```

    **Not passing props:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super();

        console.log(this.props); // prints undefined

        // but props parameter is still available
        console.log(props); // prints { name: 'John', age: 42 }
      }

      render() {
        // no difference outside constructor
        console.log(this.props); // prints { name: 'John', age: 42 }
      }
    }
    ```

    The above code snippets reveals that `this.props` is different only within the constructor. It would be the same outside the constructor.

    ****

------------------------------------------------------------------------

---

---

### What is the recommended approach of removing an array element in React state?

The better approach is to use `Array.prototype.filter()` method.

    For example, let's create a `removeItem()` method for updating the state.

    ```javascript
    removeItem(index) {
      this.setState({
        data: this.state.data.filter((item, i) => i !== index)
      })
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

## React Fundamentals & JSX

---

### What is the recommended ordering of methods in component class?

*Recommended* ordering of methods from *mounting* to *render stage*:

    1. `static` methods
    2. `constructor()`
    3. `getChildContext()`
    4. `componentWillMount()`
    5. `componentDidMount()`
    6. `componentWillReceiveProps()`
    7. `shouldComponentUpdate()`
    8. `componentWillUpdate()`
    9. `componentDidUpdate()`
    10. `componentWillUnmount()`
    11. click handlers or event handlers like `onClickSubmit()` or `onChangeDescription()`
    12. getter methods for render like `getSelectReason()` or `getFooterContent()`
    13. optional render methods like `renderNavigation()` or `renderProfilePicture()`
    14. `render()`

    ****

------------------------------------------------------------------------

---

---

### What is the render props pattern?

The Render Props pattern is a way to share a specific behavior or piece of data between components by using a function as a prop.

[⬆ Back to Table of Contents](#-table-of-contents) 

---

---

### What is the required method to be defined for a class component?

The `render()` method is the only required method in a class component.
i.e, All methods other than render method are optional for a class
component.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the typical use case of portals?

React portals are very useful when a parent component has overflow: hidden or has properties that affect the stacking context(z-index,position,opacity etc styles) and you need to visually “break out” of its container.

For example, dialogs, global message notifications, hovercards, and tooltips.

[

---

### What will happen if you use props in initial state?

If the props on the component are changed without the component being
refreshed, the new prop value will never be displayed because the
constructor function will never update the current state of the
component. The initialization of state from props only runs when the
component is first created.

    The below component won't display the updated input value:

    ```jsx harmony
    class MyComponent extends React.Component {
      constructor(props) {
        super(props);

        this.state = {
          records: **

------------------------------------------------------------------------

---

---

### What would be the common mistake of function being called every time the component renders?

You need to make sure that function is not being called while passing
the function as a parameter.

    ```jsx harmony
    render() {
      // Wrong: handleClick is called instead of passed as a reference!
      return <button onClick={this.handleClick()}>{'Click Me'}</button>
    }
    ```

    Instead, pass the function itself without parenthesis:

    ```jsx harmony
    render() {
      // Correct: handleClick is passed as a reference!
      return <button onClick={this.handleClick}>{'Click Me'}</button>
    }
    ```

    ****

------------------------------------------------------------------------

---

---

### When component props defaults to true?

If you pass no value for a prop, it defaults to true. This behavior is
available so that it matches the behavior of HTML.

     For example, below expressions are equivalent,

     ```javascript
     <MyInput autocomplete />

     <MyInput autocomplete={true} />
     ```

     **Note:** It is not recommended to use this approach because it can be confused with the ES6 object shorthand (example, `{name}` which is short for `{name: name}`)

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### When should a component be split into smaller components?

When it exceeds \~150 lines, has distinct logical sections, when part of
it needs to be reused, or when different parts change at different
frequencies. Each component should have a single clear responsibility.

------------------------------------------------------------------------

---

---

### When to use a Class Component over a Function Component?

After the addition of Hooks(i.e. React 16.8 onwards) it is always
recommended to use Function components over Class components in React.
Because you could use state, lifecycle methods and other features that
were only available in class component present in function component
too.

    But even there are two reasons to use Class components over Function components.

    1. If you need a React functionality whose Function component equivalent is not present yet, like Error Boundaries.
    2. In older versions, If the component needs _state or lifecycle methods_ then you need to use class component.

    So the summary to this question is as follows:

    **Use Function Components:**

    - If you don't need state or lifecycle methods, and your component is purely presentational.
    - For simplicity, readability, and modern code practices, especially with the use of React Hooks for state and side effects.

    **Use Class Components:**

    - If you need to manage state or use lifecycle methods.
    - In scenarios where backward compatibility or integration with older code is necessary.

    **Note:** You can also use reusable **

------------------------------------------------------------------------

---

---

### Why are keys important in lists? What happens if keys are unstable?

Keys give each element a stable identity, allowing React to match items between re‑renders. Without keys, React might reuse DOM nodes incorrectly, leading to performance issues or broken UI (e.g., lost focus, incorrect state). If keys are unstable (e.g., using index when the list can reorder), React may re‑create elements unnecessarily or mix up internal state.

---

### Why avoid array index as key?

When items are reordered, inserted, or deleted, index-based keys cause React to reuse DOM nodes incorrectly. Use stable unique IDs (DB id, UUID) instead.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### Why can't you update props in React?

The React philosophy is that props should be _immutable_(read only) and _top-down_. This means that a parent can send any prop values to a child, but the child can't modify received props.

    ****

---

### Why do you need additional care for component libraries while using forward refs?

When you start using forwardRef in a component library, you should treat
it as a breaking change and release a new major version of your library.
This is because your library likely has a different behavior such as
what refs get assigned to, and what types are exported. These changes
can break apps and other libraries that depend on the old behavior.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Why fragments are better than container divs?

Below are the list of reasons to prefer fragments over container DOM elements,

        1. Fragments are a bit faster and use less memory by not creating an extra DOM node. This only has a real benefit on very large and deep trees.
        2. Some CSS mechanisms like _Flexbox_ and _CSS Grid_ have a special parent-child relationships, and adding divs in the middle makes it hard to keep the desired layout.
        3. The DOM Inspector is less cluttered.

        ****

---

### Why is a component constructor called only once?

React's *reconciliation* algorithm assumes that without any information
to the contrary, if a custom component appears in the same place on
subsequent renders, it's the same component as before, so reuses the
previous instance rather than creating a new one.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Why is state update asynchronous?

React batches state updates for performance. `setState()` / the setter
from `useState()` schedules a re-render rather than immediately mutating
state. Reading state right after calling the setter still returns the
old value within the same event handler.

------------------------------------------------------------------------

---

---

### Why should component names start with capital letter?

If you are rendering your component using JSX, the name of that component has to begin with a capital letter otherwise React will throw an error as an unrecognized tag. This convention is because only HTML elements and SVG tags can begin with a lowercase letter.

        ```jsx harmony
        function SomeComponent {
          // Code goes here
        }
        ```

        You can define function component whose name starts with lowercase letter, but when it's imported it should have a capital letter. Here lowercase is fine:

        ```jsx harmony
        function myComponent {
          render() {
            return <div />;
          }
        }

        export default myComponent;
        ```

        While when imported in another file it should start with capital letter:

        ```jsx harmony
        import MyComponent from "./myComponent";
        ```

        ****

---

### Why should not call setState in componentWillUnmount?

You should not call `setState()` in `componentWillUnmount()` because once a component instance is unmounted, it will never be mounted again.

[

---

### Why should we not update the state directly?

If you try to update the state directly then it won't re-render the
component.

``` javascript
//Wrong
this.state.message = "Hello world";
```

Instead use `setState()` method. It schedules an update to a component's
state object. When state changes, the component responds by
re-rendering.

``` javascript
//Correct
this.setState({ message: "Hello World" });
```

**Note:** You can directly assign to the state object either in
*constructor* or using latest javascript's class field declaration
syntax.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Why we need to be careful when spreading props on DOM elements?

When we *spread props* we run into the risk of adding unknown HTML
attributes, which is a bad practice. Instead we can use prop
destructuring with `...rest` operator, so it will add only required
props.

    For example,

    ```jsx harmony
    const ComponentA = () => (
      <ComponentB isDisplay={true} className={"componentStyle"} />
    );

    const ComponentB = ({ isDisplay, ...domProps }) => (
      <div {...domProps}>{"ComponentB"}</div>
    );
    ```

    ****

------------------------------------------------------------------------

---

---

### ❓ If we have var, let, and const, why do we need state variables?

**Answer:** Regular variables (var/let/const) are reset on every re-render — React calls the function component again, so local variables start fresh. useState persists values across renders AND triggers a re-render when changed. Without useState, changing a variable wouldn't notify React to update the UI. State is React's mechanism for: (1) persisting values across renders, (2) triggering UI updates when values change. Think of useState as a variable that React 'watches' and responds to.

---

### ❓ What is prop drilling and how do you solve it?

**Answer:** Prop drilling is passing data through multiple intermediate components that don't need it, just to reach a deeply nested child. Problems: tight coupling, boilerplate, harder refactoring. Solutions: (1) Context API — for global or subtree-wide state. (2) Redux/Zustand — for complex global state. (3) Component composition — restructure to avoid deep nesting. (4) Component elevation — lift the consuming component higher. Use the simplest solution: composition first, then Context, then Redux.

---

## TypeScript, Testing, Accessibility & Security

### Describe about data flow in react?

React implements one-way reactive data flow using props which reduce
boilerplate and is easier to understand than traditional two-way data
binding.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Explain contract testing between frontend and backend.

Contract testing ensures that the frontend and backend agree on the structure of API requests and responses, without running full end‑to‑end tests.

- **Tools**: Pact (consumer‑driven contract testing), OpenAPI (Swagger) validators, or GraphQL schema checks.  
- **Process**:
  1. **Consumer (frontend) defines expectations** – writes a “pact” describing the request it will send and the expected response.  
  2. **Pact file** is shared with the provider (backend).  
  3. **Provider verifies** – runs tests against its actual code to ensure it can satisfy the contract.  
- **Benefits**: Detects breaking API changes early; allows frontend and backend to develop independently; reduces need for expensive end‑to‑end tests.

**Example**: Using Pact.js, a frontend test would set up an interaction, generate a pact file, and the backend verifies it during CI. If either side changes the contract, CI fails.

---

---

### Have you worked with Storybook? How do you use it?

Yes, Storybook is essential for developing and documenting UI components in isolation.

**Uses**:
- **Component development**: Build components without needing the full app context.  
- **Visual testing**: Integrate with Chromatic or Percy for visual regression.  
- **Documentation**: Write stories with controls, knobs, and docs addon to showcase props and usage.  
- **Accessibility checks**: Use the a11y addon to catch violations.  
- **Design system distribution**: Publish Storybook as a static site for team reference.  

**Integration**: We maintain a shared Storybook in our monorepo where all UI components are showcased. On PR, a Chromatic build runs and comments the diff preview. Developers are required to update stories when changing components.

---

---

### How do you ensure code quality with testing? (unit, integration, e2e)

A balanced test pyramid:

- **Unit tests** (Jest, Vitest) – test individual functions, hooks, and components in isolation. Cover edge cases, pure logic. Aim for high coverage on critical business logic.  
- **Integration tests** (React Testing Library) – test how components work together. Focus on user interactions, state updates, and API mocks. Avoid testing implementation details.  
- **End‑to‑end tests** (Playwright, Cypress) – test critical user journeys across real browsers. Keep them small and focused (e.g., login, checkout). Run on staging before deployment.  

**Quality gates**:  
- Enforce minimum coverage thresholds (e.g., 80%) for new code.  
- Run tests in CI; block merge if any fail.  
- Use mutation testing (Stryker) to detect weak tests.  
- Include accessibility testing (axe) in integration/e2e tests.  

**Developer experience**: Fast feedback with watch mode, local test runner, and test data factories.

---

---

### How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)

**Defense in depth**:

-   **XSS (Cross‑Site Scripting)** -- Use libraries that auto‑escape
    (React by default escapes content). Avoid `dangerouslySetInnerHTML`;
    if necessary, sanitize with DOMPurify. Set `Content-Security-Policy`
    (CSP) to restrict script sources.
-   **CSP** -- Implement strict CSP headers (e.g., `default-src 'self'`,
    `script-src 'self'`). Use nonces for inline scripts. Test with
    report‑only mode first.
-   **CSRF (Cross‑Site Request Forgery)** -- Use `SameSite=Lax` cookies,
    anti‑CSRF tokens, or double‑submit cookies. In SPAs, store tokens in
    memory (not localStorage) and use them in custom headers.
-   **Token leakage** -- Avoid storing access tokens in `localStorage`
    (vulnerable to XSS). Prefer httpOnly cookies with `Secure` and
    `SameSite=Strict`. If using JWT in memory, ensure it's not exposed
    in URLs or logs.
-   **Sensitive data in URLs** -- Never put tokens or PII in URLs (they
    appear in server logs, referrer headers).
-   **Third‑party scripts** -- Carefully vet them; use Subresource
    Integrity (SRI) to ensure they aren't tampered with.
-   **Audit tools** -- Use Lighthouse Security audits, OWASP ZAP, or npm
    packages like `helmet` for Express.

**Example**: \> "We migrated from storing JWT in localStorage to
httpOnly cookies with SameSite=Lax, which eliminated XSS‑based token
theft. We implemented a strict CSP with `script-src 'self'` and used
nonces for dynamically injected scripts. For forms, we included CSRF
tokens and validated them on the server. We also ran regular security
scans using Snyk and automated OWASP ZAP in CI."

------------------------------------------------------------------------

---

---

### How do you test async behavior (e.g., API calls)?

Mock fetch or use MSW (Mock Service Worker). Use `findBy*` or `waitFor(() => expect(...))` to wait for async DOM updates. Never use arbitrary `setTimeout` in tests.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How does React prevent XSS by default?

React escapes all values rendered in JSX. Strings are HTML-encoded
before being inserted into the DOM. You cannot accidentally inject
script tags through regular JSX expressions.

------------------------------------------------------------------------

---

---

### How React PropTypes allow different types for one prop?

You can use `oneOfType()` method of `PropTypes`.

For example, the height property can be defined with either `string` or `number` type as below:


```
Component.PropTypes = {
  size: PropTypes.oneOfType([PropTypes.string, PropTypes.number]),
};

```

[

---

### How to use TypeScript in `create-react-app` application?

Starting from [react-scripts@2.1.0](mailto\:react-scripts@2.1.0) or higher, there is a built-in support for typescript. i.e, `create-react-app` now supports typescript natively. You can just pass `--typescript` option as below


```
npx create-react-app my-app --typescript

# or

yarn create react-app my-app --typescript

```

But for lower versions of react scripts, just supply `--scripts-version` option as `react-scripts-ts` while you create a new project. `react-scripts-ts` is a set of adjustments to take the standard `create-react-app` project pipeline and bring TypeScript into the mix.

Now the project layout should look like the following:


```
my-app/
├─ .gitignore
├─ images.d.ts
├─ node_modules/
├─ public/
├─ src/
│  └─ ...
├─ package.json
├─ tsconfig.json
├─ tsconfig.prod.json
├─ tsconfig.test.json
└─ tslint.json

```

## Miscellaneous

[

---

### What are flaky test detection strategies?

Flaky tests are those that sometimes pass and sometimes fail without code changes. Detection strategies:

- **Retry mechanism**: Run tests multiple times (e.g., 3–5) in CI; if they fail at least once but also pass, mark as flaky.  
- **Statistical analysis**: Collect test run history; use tools like `flaky` (Python) or built‑in CI features (GitHub Actions, CircleCI) to flag tests with high variance.  
- **Isolation**: Run tests in different orders, with random seed values (e.g., Jest’s `--randomize`), or with environment variations to reveal flakiness.  
- **Screenshot diffs**: For visual tests, flaky may come from timing or non‑deterministic rendering. Use tools like Percy or Chromatic that handle baseline comparisons.  
- **Quarantine**: Move flaky tests to a separate suite that doesn’t block deployments until fixed. Track them with a flaky test dashboard.

**Prevention**: Avoid hardcoded timers; use `waitFor` utilities; ensure mocks are properly reset; avoid relying on network state; use deterministic data.

---

---

### What are the benefits of using typescript with reactjs?

Below are some of the benefits of using typescript with Reactjs,

1. It is possible to use latest JavaScript features
2. Use of interfaces for complex type definitions
3. IDEs such as VS Code was made for TypeScript
4. Avoid bugs with the ease of readability and Validation

[

---

### What is Flow?

_Flow_ is a _static type checker_ designed to find type errors in JavaScript. Flow types can express much more fine-grained distinctions than traditional type systems. For example, Flow helps you catch errors involving `null`, unlike most type systems.

    ****

---

### What is Mock Service Worker (MSW)?

Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is React Testing Library?

A testing library that renders components to a DOM (via jsdom) and
provides user-centric queries (`getByRole`, `getByText`,
`getByLabelText`). Encourages testing behavior, not implementation
details.

------------------------------------------------------------------------

---

---

### What is Shallow Renderer in React testing?

*Shallow rendering* is useful for writing unit test cases in React. It
lets you render a component *one level deep* and assert facts about what
its render method returns, without worrying about the behavior of child
components, which are not instantiated or rendered.

    For example, if you have the following component:

    ```javascript
    function MyComponent() {
      return (
        <div>
          <span className={"heading"}>{"Title"}</span>
          <span className={"description"}>{"Description"}</span>
        </div>
      );
    }
    ```

    Then you can assert as follows:

    ```jsx harmony
    import ShallowRenderer from "react-test-renderer/shallow";

    // in your test
    const renderer = new ShallowRenderer();
    renderer.render(<MyComponent />);

    const result = renderer.getRenderOutput();

    expect(result.type).toBe("div");
    expect(result.props.children).toEqual(**

------------------------------------------------------------------------

---

## React Routing, Forms & Data Fetching

---

### What is the difference between Flow and PropTypes?

Flow is a _static analysis tool_ (static checker) which uses a superset of the language, allowing you to add type annotations to all of your code and catch an entire class of bugs at compile time.

         PropTypes is a _basic type checker_ (runtime checker) which has been patched onto React. It can't check anything other than the types of the props being passed to a given component. If you want more flexible typechecking for your entire project Flow/TypeScript are appropriate choices.

    ****

---

### What is the testing pyramid for React?

Unit tests (fast, many): individual functions/hooks. Integration tests
(medium): component interactions, user flows. E2E tests (slow, few):
full browser flows via Playwright or Cypress. Focus effort on the middle
layer.

------------------------------------------------------------------------

---

---

### What is visual regression testing? How would you implement it?

Visual regression testing catches unintended UI changes by comparing screenshots of components or pages against approved baselines.

**Implementation**:

- **Tools**: Percy (integrated with Storybook), Chromatic, or open‑source tools like Playwright with screenshot comparison.  
- **Workflow**:
  1. Capture screenshots of each component/page in a controlled environment (e.g., Storybook).  
  2. Store baseline images (e.g., in Percy’s cloud).  
  3. On each pull request, run a new build, capture new screenshots, and compare.  
  4. Review any differences; if intentional, approve as new baseline.  
  5. Fail CI if unapproved changes are detected.  

**Considerations**:  
- Use consistent viewport sizes and mock data to avoid false positives.  
- Ignore dynamic elements (timestamps, random IDs) with attribute masking.  
- Run only on relevant components to keep feedback fast.

---

---

### What is Vitest and how does it differ from Jest?

Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What tools help check React app accessibility?

-   `eslint-plugin-jsx-a11y` (static analysis)
-   `@axe-core/react` (runtime checks in development)
-   Browser extensions: Axe DevTools, WAVE
-   Lighthouse a11y audit
-   Manual screen reader testing (NVDA, VoiceOver)

------------------------------------------------------------------------

---

---

### Why does accessibility matter in React apps?

SPAs often break native browser accessibility (focus management,
history, page titles). React renders JS-controlled UI that screen
readers may not handle correctly without explicit a11y handling.

------------------------------------------------------------------------

---

---

### Why use TypeScript with React?

Catches type errors at compile time (wrong prop types, missing required props). Enables autocomplete, refactoring safety, and self-documenting component APIs. Reduces runtime bugs significantly in large codebases.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### ❓ What is the difference between visual regression testing and contract testing?

**Answer:** Visual regression testing: captures screenshots of components, compares against baseline — catches unintended CSS/layout changes. Tools: Chromatic (Storybook-based), Percy, Playwright screenshots. Contract testing (frontend-backend): verifies the API response shape matches what the frontend expects — catches backend changes that break frontend before integration. Tools: Pact.js, MSW (Mock Service Worker). Both are important: visual regression for UI stability, contract testing for API stability.

---

---

## React Ecosystem & Libraries

### Give an example of Reselect usage?

Let's take calculations and different amounts of a shipment order with the simplified usage of Reselect:


```
import { createSelector } from 'reselect';

const shopItemsSelector = (state) => state.shop.items;
const taxPercentSelector = (state) => state.shop.taxPercent;

const subtotalSelector = createSelector(shopItemsSelector, (items) =>
  items.reduce((acc, item) => acc + item.value, 0),
);

const taxSelector = createSelector(
  subtotalSelector,
  taxPercentSelector,
  (subtotal, taxPercent) => subtotal * (taxPercent / 100),
);

export const totalSelector = createSelector(subtotalSelector, taxSelector, (subtotal, tax) => ({
  total: subtotal + tax,
}));

let exampleState = {
  shop: {
    taxPercent: 8,
    items: [
      { name: 'apple', value: 1.2 },
      { name: 'orange', value: 0.95 },
    ],
  },
};

console.log(subtotalSelector(exampleState)); // 2.15
console.log(taxSelector(exampleState)); // 0.172
console.log(totalSelector(exampleState)); // { total: 2.322 }

```

[

---

### How to access current locale with React Intl?

You can get the current locale in any component of your application using `injectIntl()`:

        ```jsx harmony
        import { injectIntl, intlShape } from "react-intl";

        const MyComponent = ({ intl }) => (
          <div>{`The current locale is ${intl.locale}`}</div>
        );

        MyComponent.propTypes = {
          intl: intlShape.isRequired,
        };

        export default injectIntl(MyComponent);
        ```

    ****

---

### How to add Bootstrap to a react application?

Bootstrap can be added to your React app in a three possible ways,

     1. Using the Bootstrap CDN:
        This is the easiest way to add bootstrap. Add both bootstrap CSS and JS resources in a head tag.
     2. Bootstrap as Dependency:
        If you are using a build tool or a module bundler such as Webpack, then this is the preferred option for adding Bootstrap to your React application
        ```javascript
        npm install bootstrap
        ```
     3. React Bootstrap Package:
        In this case, you can add Bootstrap to our React app is by using a package that has rebuilt Bootstrap components to work particularly as React components. Below packages are popular in this category,
        1. react-bootstrap
        2. reactstrap

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to format date using React Intl?

The `injectIntl()` higher-order component will give you access to the `formatDate()` method via the props in your component. The method is used internally by instances of `FormattedDate` and it returns the string representation of the formatted date.

         ```jsx harmony
         import { injectIntl, intlShape } from "react-intl";

         const stringDate = this.props.intl.formatDate(date, {
           year: "numeric",
           month: "numeric",
           day: "numeric",
         });

         const MyComponent = ({ intl }) => (
           <div>{`The formatted date is ${stringDate}`}</div>
         );

         MyComponent.propTypes = {
           intl: intlShape.isRequired,
         };

         export default injectIntl(MyComponent);
         ```

        ****

    ## React Testing

---

### How to use Font Awesome icons in React?

The below steps followed to include Font Awesome in React:

         1. Install `font-awesome`:

            ```console
            $ npm install --save font-awesome
            ```

         2. Import `font-awesome` in your `index.js` file:

            ```javascript
            import "font-awesome/css/font-awesome.min.css";
            ```

         3. Add Font Awesome classes in `className`:

            ```javascript
            function MyComponent {
              return <div><i className={'fa fa-spinner'} /></div>
            }
            ```

    ****

---

### How to use `<FormattedMessage>` as placeholder using React Intl?

The `<Formatted... />` components from `react-intl` return elements, not plain text, so they can't be used for placeholders, alt text, etc. In that case, you should use lower level API `formatMessage()`. You can inject the `intl` object into your component using `injectIntl()` higher-order component and then format the message using `formatMessage()` available on that object.

        ```jsx harmony
        import React from "react";
        import { injectIntl, intlShape } from "react-intl";

        const MyComponent = ({ intl }) => {
          const placeholder = intl.formatMessage({ id: "messageId" });
          return <input placeholder={placeholder} />;
        };

        MyComponent.propTypes = {
          intl: intlShape.isRequired,
        };

        export default injectIntl(MyComponent);
        ```

    ****

---

### How to use Polymer in React?

You need to follow below steps to use Polymer in React,

         1. Create a Polymer element:

            ```jsx harmony
            <link
              rel="import"
              href="../../bower_components/polymer/polymer.html"
            />;
            Polymer({
              is: "calendar-element",
              ready: function () {
                this.textContent = "I am a calendar";
              },
            });
            ```

         2. Create the Polymer component HTML tag by importing it in a HTML document, e.g. import it in the `index.html` of your React application:

            ```html
            <link
              rel="import"
              href="./src/polymer-components/calendar-element.html"
            />
            ```

         3. Use that element in the JSX file:

            ```javascript
            export default function MyComponent {
              return <calendar-element />;
            }
            ```

    ****

---

### How would you implement internationalization (i18n) in React?

`react-intl` or `react-i18next`. Extract all strings to message
catalogs. `useIntl()` hook for formatting. Support RTL layouts
(`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies
via Intl API. Lazy load language bundles.

------------------------------------------------------------------------

---

---

### Is it recommended to use CSS In JS technique in React?

React does not have any opinion about how styles are defined but if you are a beginner then good starting point is to define your styles in a separate \*.css file as usual and refer to them using className. This functionality is not part of React but came from third-party libraries. But If you want to try a different approach(CSS-In-JS) then styled-components library is a good option.

[

---

### What are the benefits of new JSX transform?

There are three major benefits of new JSX transform,

     1. It is possible to use JSX without importing React packages
     2. The compiled output might improve the bundle size in a small amount
     3. The future improvements provides the flexibility to reduce the number of concepts to learn React.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are the features of create react app?

Below are the list of some of the features provided by create react app.

    1.  React, JSX, ES6, Typescript and Flow syntax support.
    2.  Autoprefixed CSS
    3.  CSS Reset/Normalize
    4.  A live development server
    5.  A fast interactive unit test runner with built-in support for coverage reporting
    6.  A build script to bundle JS, CSS, and images for production, with hashes and sourcemaps
    7.  An offline-first service worker and a web app manifest, meeting all the Progressive Web App criteria.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are the main features of React Intl?

Below are the main features of React Intl,

        1.  Display numbers with separators.
        2.  Display dates and times correctly.
        3.  Display dates relative to "now".
        4.  Pluralize labels in strings.
        5.  Support for 150+ languages.
        6.  Runs in the browser and Node.
        7.  Built on standards.

    ****

---

### What are the main features of Reselect library?

Let's see the main features of Reselect library,

1. Selectors can compute derived data, allowing Redux to store the minimal possible state.
2. Selectors are efficient. A selector is not recomputed unless one of its arguments changes.
3. Selectors are composable. They can be used as input to other selectors.

---

### What is React Intl?

The _React Intl_ library makes internationalization in React straightforward, with off-the-shelf components and an API that can handle everything from formatting strings, dates, and numbers, to pluralization. React Intl is part of _FormatJS_ which provides bindings to React via its components and API.

    ****

---

### What is react scripts?

The `react-scripts` package is a set of scripts from the
create-react-app starter pack which helps you kick off projects without
configuring. The `react-scripts start` command sets up the development
environment and starts a server, as well as hot module reloading.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is reselect and how it works?

*Reselect* is a **selector library** (for Redux) which uses *memoization* concept. It was originally written to compute derived data from Redux-like applications state, but it can't be tied to any architecture or library.

Reselect keeps a copy of the last inputs/outputs of the last call, and recomputes the result only if one of the inputs changes. If the the same inputs are provided twice in a row, Reselect returns the cached output. It's memoization and cache are fully customizable.

[

---

### What is the purpose of registerServiceWorker in React?

React creates a service worker for you without any configuration by default. The service worker is a web API that helps you cache your assets and other files so that when the user is offline or on a slow network, he/she can still see results on the screen, as such, it helps you build a better user experience, that's what you should know about service worker for now. It's all about adding offline capabilities to your site.

         ```jsx
         import React from "react";
         import ReactDOM from "react-dom";
         import App from "./App";
         import registerServiceWorker from "./registerServiceWorker";

         ReactDOM.render(<App />, document.getElementById("root"));
         registerServiceWorker();
         ```

    ****

---

## Fundamentals & JSX

### Can you use React without JSX?

Yes. `React.createElement('div', {className:'box'}, 'Hello')` is valid
but verbose. JSX is purely syntactic sugar; the output is identical JS
objects.

------------------------------------------------------------------------

---

---

### Do browsers understand JSX code?

No, browsers can't understand JSX code. You need a transpiler to convert
your JSX to regular Javascript that browsers can understand. The most
widely used transpiler right now is Babel.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

### 287. Poor SEO & Slow TTI: React app has poor SEO and slow TTI -- frontend-level solutions.

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

------------------------------------------------------------------------

---

---

### Does React support all HTML attributes?

As of React 16, both standard or custom DOM attributes are fully supported. Since React components often take both custom and DOM-related props, React uses the camelCase convention just like the DOM APIs.

Let us take few props with respect to standard HTML attributes,


```
<div tabIndex="-1" />      // Just like node.tabIndex DOM API
<div className="Button" /> // Just like node.className DOM API
<input readOnly={true} />  // Just like node.readOnly DOM API

```

These props work similarly to the corresponding HTML attributes, with the exception of the special cases. It also support all SVG attributes.

[

---

### How do you print falsy values in JSX?

The falsy values such as false, null, undefined, and true are valid
children but they don't render anything. If you still want to display
them then you need to convert it to string. Let's take an example on how
to convert to a string,

     ```javascript
     <div>My JavaScript variable is {String(myVariable)}.</div>
     ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you update rendered elements?

You can update UI(represented by rendered element) by passing the newly created element to ReactDOM's render method.

For example, lets take a ticking clock example, where it updates the time by calling render method multiple times,


```
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);

```

[

---

### How JSX prevents Injection Attacks?

React DOM escapes any values embedded in JSX before rendering them. Thus
it ensures that you can never inject anything that's not explicitly
written in your application. Everything is converted to a string before
being rendered.

     For example, you can embed user input as below,

     ```javascript
     const name = response.potentiallyMaliciousInput;
     const element = <h1>{name}</h1>;
     ```

     This way you can prevent XSS(Cross-site-scripting) attacks in the application.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to bind methods or event handlers in JSX callbacks?

There are 3 possible ways to achieve this in class components:

1.  **Binding in Constructor:** In JavaScript classes, the methods are
    not bound by default. The same rule applies for React event handlers
    defined as class methods. Normally we bind them in constructor.

    ``` javascript
    class User extends Component {
      constructor(props) {
        super(props);
        this.handleClick = this.handleClick.bind(this);
      }
      handleClick() {
        console.log("SingOut triggered");
      }
      render() {
        return <button onClick={this.handleClick}>SingOut</button>;
      }
    }
    ```

2.  **Public class fields syntax:** If you don't like to use bind
    approach then *public class fields syntax* can be used to correctly
    bind callbacks. The Create React App enables this syntax by default.

    `jsx harmony handleClick = () => {   console.log("SingOut triggered", this); };`

    `jsx harmony <button onClick={this.handleClick}>SingOut</button>`

3.  **Arrow functions in callbacks:** It is possible to use *arrow
    functions* directly in the callbacks.

    `jsx harmony handleClick() {     console.log('SingOut triggered'); } render() {     return <button onClick={() => this.handleClick()}>SignOut</button>; }`

**Note:** If the callback is passed as prop to child components, those
components might do an extra re-rendering. In those cases, it is
preferred to go with `.bind()` or *public class fields syntax* approach
considering performance.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to loop inside JSX?

You can simply use `Array.prototype.map` with ES6 _arrow function_ syntax.

        For example, the `items` array of objects is mapped into an array of components:

        ```jsx harmony
        <tbody>
          {items.map((item) => (
            <SomeComponent key={item.id} name={item.name} />
          ))}
        </tbody>
        ```

        But you can't iterate using `for` loop:

        ```jsx harmony
        <tbody>
          for (let i = 0; i < items.length; i++) {
            <SomeComponent key={items**

---

### How to use innerHTML in React?

The `dangerouslySetInnerHTML` attribute is React's replacement for using
`innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to
use this attribute considering cross-site scripting (XSS) attacks. You
just need to pass a `__html` object as key and HTML text as value.

    In this example MyComponent uses `dangerouslySetInnerHTML` attribute for setting HTML markup:

    ```jsx harmony
    function createMarkup() {
      return { __html: "First &middot; Second" };
    }

    function MyComponent() {
      return <div dangerouslySetInnerHTML={createMarkup()} />;
    }
    ```

    ****

------------------------------------------------------------------------

---

---

### How to use React label element?

If you try to render a `<label>` element bound to a text input using the standard `for` attribute, then it produces HTML missing that attribute and prints a warning to the console.

        ```jsx harmony
        <label for={'user'}>{'User'}</label>
        <input type={'text'} id={'user'} />
        ```

        Since `for` is a reserved keyword in JavaScript, use `htmlFor` instead.

        ```jsx harmony
        <label htmlFor={'user'}>{'User'}</label>
        <input type={'text'} id={'user'} />
        ```

        ****

---

### How Virtual DOM works?

The *Virtual DOM* works in five simple steps.

    **1. Initial Render**  
        When a UI component renders for the first time, it returns JSX. React uses this structure to create a Virtual DOM tree, which is a lightweight copy of the actual DOM. This Virtual DOM is then used to build and render the Real DOM in the browser.

    **2. State or Props Change**  
        When the component's state or props change, React creates a new Virtual DOM reflecting the updated UI. However, it doesn't immediately update the Real DOM; instead, it works in memory to prepare for an efficient update.
               
      !**

------------------------------------------------------------------------

---

---

### Is it possible to use react without JSX?

Yes, JSX is not mandatory for using React. Actually it is convenient
when you don't want to set up compilation in your build environment.
Each JSX element is just syntactic sugar for calling
`React.createElement(component, props, ...children)`.

    For example, let us take a greeting example with JSX,

    ```javascript
    class Greeting extends React.Component {
      render() {
        return <div>Hello {this.props.message}</div>;
      }
    }

    ReactDOM.render(
      <Greeting message="World" />,
      document.getElementById("root")
    );
    ```

    You can write the same code without JSX as below,

    ```javascript
    class Greeting extends React.Component {
      render() {
        return React.createElement("div", null, `Hello ${this.props.message}`);
      }
    }

    ReactDOM.render(
      React.createElement(Greeting, { message: "World" }, null),
      document.getElementById("root")
    );
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What are synthetic events?

React wraps native browser events in `SyntheticEvent`, providing a consistent cross-browser API. Event properties (`target`, `value`, `preventDefault`, `stopPropagation`) work identically across browsers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are synthetic events in React?

`SyntheticEvent` is a cross-browser wrapper around the browser's native event. Its API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers. The native events can be accessed directly from synthetic events using `nativeEvent` attribute.

        Let's take an example of `BookStore` title search component with the ability to get all native event properties

        ```js
        function BookStore() {
          function handleTitleChange(e) {
            console.log("The new title is:", e.target.value);
            console.log('Synthetic event:', e); // React SyntheticEvent
            console.log('Native event:', e.nativeEvent); // Browser native event
            e.stopPropagation();
            e.preventDefault();
          }

          return <input name="title" onChange={handleTitleChange} />;
        }
        ```
        
        List of common synthetic events are:

        *   `onClick`
        *   `onChange`
        *   `onSubmit`
        *   `onKeyDown`, `onKeyUp`
        *   `onFocus`, `onBlur`
        *   `onMouseEnter`, `onMouseLeave`
        *   `onTouchStart`, `onTouchEnd`

        ****

---

### What are the limitations of React?

The few limitations of React are as given below:

- React is not a full-blown framework as it is only a library.
- The components of React are numerous and will take time to fully grasp the benefits of all.
- It might be difficult for beginner programmers to understand React.
- Coding might become complex as it will make use of inline templating and JSX.

**You can download a PDF version of React Interview Questions.**

[**Download PDF**](javascript\:void\(0\))

###

---

---

### What are the major features of React?

React offers a powerful set of features that have made it one of the most popular JavaScript libraries for building user interfaces:

        **Core Features:**

        - **Component-Based Architecture**: React applications are built using components - independent, reusable pieces of code that return HTML via a render function. This modular approach enables better code organization, reusability, and maintenance.

        - **Virtual DOM**: React creates an in-memory data structure cache, computes the resulting differences, and efficiently updates only the changed parts in the browser DOM. This approach significantly improves performance compared to direct DOM manipulation.

        - **JSX (JavaScript XML)**: A syntax extension that allows writing HTML-like code in JavaScript. JSX makes the code more readable and expressive while providing the full power of JavaScript.

        - **Unidirectional Data Flow**: React follows a one-way data binding model where data flows from parent to child components. This makes the code more predictable and easier to debug.

        - **Declarative UI**: React allows you to describe what your UI should look like for a given state, and it handles the DOM updates when the underlying data changes.

        **Advanced Features:**

        - **React Hooks**: Introduced in React 16.8, hooks allow using state and other React features in functional components without writing classes.

        - **Context API**: Provides a way to share values between components without explicitly passing props through every level of the component tree.

        - **Error Boundaries**: Components that catch JavaScript errors anywhere in their child component tree and display fallback UI instead of crashing.

        - **Server-Side Rendering (SSR)**: Enables rendering React components on the server before sending HTML to the client, improving performance and SEO.

        - **Concurrent Mode**: A set of new features (in development) that help React apps stay responsive and gracefully adjust to the user's device capabilities and network speed.

        - **React Server Components**: A new feature that allows components to be rendered entirely on the server, reducing bundle size and improving performance.

        - **Suspense**: A feature that lets your components "wait" for something before rendering, supporting code-splitting and data fetching with cleaner code.

        These features collectively make React powerful for building everything from small widgets to complex, large-scale web applications.

        ****

---

### What does 'declarative' mean in React?

You describe what the UI should look like for a given state. React
figures out how to make the DOM match. Imperative code would manually
manipulate the DOM step by step; declarative code just re-renders with
new state.

------------------------------------------------------------------------

---

---

### What does JSX compile to?

JSX compiles to `React.createElement(type, props, ...children)` in React
\<17, and to the automatic `jsx()` runtime in React 17+. Both produce
plain JavaScript objects (React elements) describing the UI.

------------------------------------------------------------------------

---

---

### What is a React SPA and what are its trade-offs?

Think of a React SPA (Single Page Application) like a modern video game
rather than a traditional book.

Instead of turning to a completely new physical page every time you
click a link (which causes the browser to reload and flash white), a SPA
loads one single blank page at the very beginning. Then, it uses
JavaScript to dynamically erase old content and snap new content into
place instantly.

------------------------------------------------------------------------

---

---

### What is `dangerouslySetInnerHTML` and why is it dangerous?

Sets raw HTML on a DOM node, bypassing React's XSS protection. If the HTML contains user input, it can execute arbitrary scripts. Always sanitize with DOMPurify before using it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is JSX?

JSX stands for JavaScript XML. It allows us to write HTML inside JavaScript and place them in the DOM without using functions like appendChild( ) or createElement( ).

    As stated in the official docs of React, JSX provides syntactic sugar for React.createElement( ) function.

    > Note- We can create react applications without using JSX as well.

    Let’s understand **how JSX works**:

    Without using JSX, we would have to create an element by the following process:

const text = React.createElement('p', {}, 'This is a text'); const
container = React.createElement('div','{}',text );
ReactDOM.render(container,rootElement);


    **Using JSX**, the above code can be simplified:

const container = (

<div>

```{=html}
<p>
```
This is a text
```{=html}
</p>
```

</div>

); ReactDOM.render(container,rootElement);


    As one can see in the code above, we are directly using HTML inside JavaScript.

---

### What is JSX and how is it rendered in the browser?

JSX is a syntax extension that lets you write HTML-like code in
JavaScript. Browsers don't understand JSX --- a build tool (Babel/SWC)
transpiles it to React.createElement() calls. React.createElement(type,
props, ...children) returns a plain JavaScript object (React element).
React then uses these element objects to build and diff the virtual DOM.
With React 17+, you no longer need to import React in every file for JSX
thanks to the automatic JSX transform.

------------------------------------------------------------------------

---

---

### What is JSX and why does React use it?

JSX is a syntax extension allowing HTML-like markup inside JS. At build
time it compiles to `React.createElement()` calls. It improves
readability, catches errors earlier via the compiler, and makes
component trees visually clear.

------------------------------------------------------------------------

---

---

### What is NextJS and major features of it?

Next.js is a popular and lightweight framework for static and server‑rendered applications built with React. It also provides styling and routing solutions. Below are the major features provided by NextJS,

1. Server-rendered by default
2. Automatic code splitting for faster page loads
3. Simple client-side routing (page based)
4. Webpack-based dev environment which supports (HMR)
5. Able to implement with Express or any other Node.js HTTP server
6. Customizable with your own Babel and Webpack configurations

[

---

### What is the browser support for react applications?

React supports all popular browsers, including Internet Explorer 9 and above, although some polyfills are required for older browsers such as IE 9 and IE 10. If you use **es5-shim and es5-sham** polyfill then it even support old browsers that doesn't support ES5 methods.

[

---

### What is the difference between createElement and cloneElement?

Both `React.createElement` and `React.cloneElement` are used to work with React elements, but they serve different purposes.

        #### **createElement:** 
        Creates a new React element from scratch. JSX elements will be transpiled to `React.createElement()` functions to create React elements which are going to be used for the object representation of UI.
        **Syntax:**
        ```jsx
        React.createElement(type, props, ...children)
        ```
        **Example:**
        ```jsx
        React.createElement('button', { className: 'btn' }, 'Click Me')
        ```
        #### **cloneElement:**
         The `cloneElement` method is used to clone an existing React element and optionally adds or overrides props.

        **Syntax:**
        ```jsx
        React.cloneElement(element, newProps, ...children)
        ```
        **Example:**
        ```jsx
        const button = <button className="btn">Click Me</button>;
        const cloned = React.cloneElement(button, { className: 'btn-primary' });
        // Result: <button className="btn-primary">Click Me</button>
        ```
        ****

---

### What is the difference between Imperative and Declarative in React?

Imagine a simple UI component, such as a "Like" button. When you tap it,
it turns blue if it was previously grey, and grey if it was previously
blue.

     The imperative way of doing this would be:

     ```javascript
     if (user.likes()) {
       if (hasBlue()) {
         removeBlue();
         addGrey();
       } else {
         removeGrey();
         addBlue();
       }
     }
     ```

     Basically, you have to check what is currently on the screen and handle all the changes necessary to redraw it with the current state, including undoing the changes from the previous state. You can imagine how complex this could be in a real-world scenario.

     In contrast, the declarative approach would be:

     ```javascript
     if (this.state.liked) {
       return <blueLike />;
     } else {
       return <greyLike />;
     }
     ```

     Because the declarative approach separates concerns, this part of it only needs to handle how the UI should look in a specific state, and is therefore much simpler to understand.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the difference between Real DOM and Virtual DOM?

Below are the main differences between Real DOM and Virtual DOM,

     | Real DOM                             | Virtual DOM                          |
     | ------------------------------------ | ------------------------------------ |
     | Updates are slow                     | Updates are fast                     |
     | DOM manipulation is very expensive.  | DOM manipulation is very easy        |
     | You can update HTML directly.        | You Can’t directly update HTML       |
     | It causes too much of memory wastage | There is no memory wastage           |
     | Creates a new DOM if element updates | It updates the JSX if element update |

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the React DevTools and what can you do with it?

A browser extension that lets you inspect the component tree, view
props/state/context, highlight re-renders, and use the Profiler to
record timing and flame graphs of render performance.

------------------------------------------------------------------------

---

---

### What is the reason behind multiple JSX tags to be wrapped?

Behind the scenes, JSX is transformed into plain javascript objects. It
is not possible to return two or more objects from a function without
wrapping into an array. This is the reason you can't simply return two
or more JSX tags from a function without wrapping them into a single
parent tag or a Fragment.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is the Virtual DOM?

An in-memory lightweight JS tree that mirrors the real DOM. React
renders to the virtual DOM first, diffs two versions (reconciliation),
and applies only the minimal set of real DOM mutations needed.

------------------------------------------------------------------------

---

---

### What is the virtual DOM? How does react use the virtual DOM to render the UI?

As stated by the react team, virtual DOM is a concept where a virtual
representation of the real DOM is kept inside the memory and is synced
with the real DOM by a library such as ReactDOM.

**Why was virtual DOM introduced?** 

DOM manipulation is an integral part of any web application, but DOM
manipulation is quite slow when compared to other operations in
JavaScript. The efficiency of the application gets affected when several
DOM manipulations are being done. Most JavaScript frameworks update the
entire DOM even when a small part of the DOM changes.

For example, consider a list that is being rendered inside the DOM. If
one of the items in the list changes, the entire list gets rendered
again instead of just rendering the item that was changed/updated. This
is called inefficient updating.

To address the problem of inefficient updating, the react team
introduced the concept of virtual DOM.

**How does it work?**

For every DOM object, there is a corresponding virtual DOM object(copy),
which has the same properties. The main difference between the real DOM
object and the virtual DOM object is that any changes in the virtual DOM
object will not reflect on the screen directly. Consider a virtual DOM
object as a blueprint of the real DOM object. Whenever a JSX element
gets rendered, every virtual DOM object gets updated.

> \*\*Note- One may think updating every virtual DOM object might be
> inefficient, but that's not the case. Updating the virtual DOM is much
> faster than updating the real DOM since we are just updating the
> blueprint of the real DOM.

React uses two virtual DOMs to render the user interface. One of them is
used to store the current state of the objects and the other to store
the previous state of the objects. Whenever the virtual DOM gets
updated, react compares the two virtual DOMs and gets to know about
which virtual DOM objects were updated. After knowing which objects were
updated, react renders only those objects inside the real DOM instead of
rendering the complete real DOM. This way, with the use of virtual DOM,
react solves the problem of inefficient updating.

------------------------------------------------------------------------

---

---

### Why React tab is not showing up in DevTools?

When the page loads, _React DevTools_ sets a global named `__REACT_DEVTOOLS_GLOBAL_HOOK__`, then React communicates with that hook during initialization. If the website is not using React or if React fails to communicate with DevTools then it won't show up the tab.

    ****

---

### Why you get "Router may have only one child element" warning?

You have to wrap your Route's in a `<Switch>` block because `<Switch>` is unique in that it renders a route exclusively.

        At first you need to add `Switch` to your imports:

        ```javascript
        import { Switch, Router, Route } from "react-router";
        ```

        Then define the routes within `<Switch>` block:

        ```jsx harmony
        <Router>
          <Switch>
            <Route {/* ... */} />
            <Route {/* ... */} />
          </Switch>
        </Router>
        ```

    ****

---

## React Fundamentals & Miscellaneous

### Are custom DOM attributes supported in React v16?

**Note:** This question references React v16, which is outdated. The
information below applies to React 16+, including current versions
(React 18/19).

    Yes. Starting with React 16, React no longer ignores unknown DOM attributes. If you write JSX with an attribute that React doesn't recognize, React will pass it through to the DOM.

    For example, let's take a look at the below attribute:

    ```jsx harmony
    <div mycustomattribute={"something"} />
    ```

    In React 15 and earlier, this would render an empty div:

    ```html
    <div />
    ```

    In React 16 and later (including React 18/19), any unknown attributes will end up in the DOM:

    ```html
    <div mycustomattribute="something" />
    ```

    This is useful for supplying browser-specific non-standard attributes, trying new DOM APIs, and integrating with opinionated third-party libraries.

    ****

------------------------------------------------------------------------

---

---

### Can I use javascript urls in react16.9?

Yes, you can use javascript: URLs but it will log a warning in the console. Because URLs starting with javascript: are dangerous by including unsanitized output in a tag like `<a href>` and create a security hole.


```
const companyProfile = {
  website: "javascript: alert('Your website is hacked')",
};
// It will log a warning
<a href={companyProfile.website}>More details</a>;

```

Remember that the future versions will throw an error for javascript URLs.

[

---

### Can you list down top websites or applications using react as front end framework?

Below are the `top 10 websites` using React as their front-end
framework,

     1. Facebook
     2. Uber
     3. Instagram
     4. WhatsApp
     5. Khan Academy
     6. Airbnb
     7. Dropbox
     8. Flipboard
     9. Netflix
     10. PayPal

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### Does the statics object work with ES6 classes in React?

No, `statics` only works with `React.createClass()`:

    ```javascript
    someComponent = React.createClass({
      statics: {
        someMethod: function () {
          // ..
        },
      },
    });
    ```

    But you can write statics inside ES6+ classes as below,

    ```javascript
    class Component extends React.Component {
      static propTypes = {
        // ...
      };

      static someMethod() {
        // ...
      }
    }
    ```

    or writing them outside class as below,

    ```javascript
    class Component extends React.Component {
       ....
    }

    Component.propTypes = {...}
    Component.someMethod = function(){....}
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How can we find the version of React at runtime in the browser?

You can use `React.version` to get the version.

    ```jsx harmony
    const REACT_VERSION = React.version;

    ReactDOM.render(
      <div>{`React version: ${REACT_VERSION}`}</div>,
      document.getElementById("app")
    );
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How do you apply vendor prefixes to inline styles in React?

React _does not_ apply _vendor prefixes_ automatically. You need to add vendor prefixes manually.

        ```jsx harmony
        <div
          style={{
            transform: "rotate(90deg)",
            WebkitTransform: "rotate(90deg)", // note the capital 'W' here
            msTransform: "rotate(90deg)", // 'ms' is the only lowercase vendor prefix
          }}
        />
        ```

    ****

---

### How do you avoid unnecessary object/function recreation?

Declare stable values outside the component when possible, use `useMemo` for objects/arrays, `useCallback` for functions, and avoid inline object literals as prop values in JSX.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you build a reusable modal?

Use a portal to render outside the app root. Manage open state via controlled pattern. Trap focus inside for accessibility. Close on Escape key and overlay click. Accept children for flexible content.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you integrate a non-React library (e.g., D3, Leaflet)?

Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you pass data child → parent?

Pass a callback function as a prop. The child calls it with data, the parent receives it in the handler and updates its state. This maintains one-way data flow while still communicating upward.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How do you pass parent data to a deeply nested child (e.g., 5th child)?

Using **Context** is the most common approach. Create a context, wrap the parent tree with a `Provider`, and consume the context in the deeply nested child via `useContext` or `Context.Consumer`. Alternatively, use a state management library like Redux that provides global state.

---

### How do you render Array, Strings and Numbers in React 16 Version?

**Arrays**: Unlike older releases, you don't need to make sure **render** method return a single element in React16. You are able to return multiple sibling elements without a wrapping element by returning an array.

For example, let us take the below list of developers,


```
const ReactJSDevs = () => {
  return [<li key="1">John</li>, <li key="2">Jackie</li>, <li key="3">Jordan</li>];
};

```

You can also merge this array of items in another array component.


```
const JSDevs = () => {
  return (
    <ul>
      <li>Brad</li>
      <li>Brodge</li>
      <ReactJSDevs />
      <li>Brandon</li>
    </ul>
  );
};

```

**Strings and Numbers:** You can also return string and number type from the render method.


```
render() {
return 'Welcome to ReactJS questions';
}
// Number
render() {
return 2018;
}

```

[

---

### How do you type event handlers?

`React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`. Or use inline type: `(e: React.ChangeEvent<HTMLInputElement>) => void`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How does React updates screen in an application?

React updates UI in three steps,

     1. **Triggering or initiating a render:** The component is going to triggered for render in two ways.

        1. **Initial render:** When the app starts, you can trigger the initial render by calling `creatRoot` with the target DOM node followed by invoking component's `render` method. For example, the following code snippet renders `App` component on root DOM node.

        ```jsx
        import { createRoot } from "react-dom/client";

        const root = createRoot(document.getElementById("root"));
        root.render(<App />);
        ```

        2. **Re-render when the state updated:** When you update the component state using the state setter function, the componen't state automatically queues for a render.

     2. **Rendering components:** After triggering a render, React will call your components to display them on the screen. React will call the root component for initial render and call the function component whose state update triggered the render. This is a recursive process for all nested components of the target component.

     3. **Commit changes to DOM:** After calling components, React will modify the DOM for initial render using `appendChild()` DOM API and apply minimal necessary DOM updates for re-renders based on differences between rerenders.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How events are different in React?

Handling events in React elements has some syntactic differences:

        1. React event handlers are named using camelCase, rather than lowercase.
        2. With JSX you pass a function as the event handler, rather than a string.

        ****

---

### How is React different from Angular or Vue?

React is a view library (handles only UI); Angular is a full framework
with DI, routing, forms built-in; Vue sits in between. React uses JSX +
JS composition, Angular uses TypeScript + decorators + templates, Vue
uses SFC (Single File Components).

------------------------------------------------------------------------

---

---

### How It Works

1. Server starts sending HTML immediately
     2. When it hits `<Suspense>`, it sends the fallback
     3. Continues streaming rest of the page
     4. When data is ready, sends the actual component
     5. Client replaces fallback with real content
     6. Hydration happens independently per component

     #### Selective Hydration
     ```jsx
     function App() {
       return (
         <div>
           <header>Header</header> {/* Hydrates first */}
           
           <Suspense fallback={<Spinner />}>
             <HeavyComponent /> {/* Hydrates when user interacts */}
           </Suspense>
           
           <Suspense fallback={<Spinner />}>
             <Comments /> {/* Hydrates independently */}
           </Suspense>
         </div>
       );
     }
     ```

     #### Benefits
     - **Faster TTFB** (Time to First Byte): User sees content sooner
     - **Better UX**: Progressive loading instead of blank screen
     - **Prioritized hydration**: Interactive elements hydrate first
     - **Resilient**: Slow components don't block fast ones

     #### Next.js App Router Example
     ```jsx
     // app/page.tsx
     import { Suspense } from 'react';
     import ProductList from './ProductList';
     import Reviews from './Reviews';

     export default function ProductPage() {
       return (
         <div>
           <h1>Product Page</h1>
           
           {/* Streams product list first */}
           <Suspense fallback={<ProductSkeleton />}>
             <ProductList />
           </Suspense>

           {/* Reviews stream separately */}
           <Suspense fallback={<ReviewSkeleton />}>
             <Reviews />
           </Suspense>
         </div>
       );
     }

     // These are async Server Components
     async function ProductList() {
       const products = await fetchProducts(); // Doesn't block Reviews
       return <div>{/* render products */}</div>;
     }

     async function Reviews() {
       const reviews = await fetchReviews(); // Doesn't block ProductList
       return <div>{/* render reviews */}</div>;
     }
     ```

     #### Key Requirements
     - Use React 18+ with `createRoot` and `hydrateRoot`
     - Wrap slow components in `<Suspense>`
     - Use frameworks supporting streaming (Next.js, Remix, etc.)
     - Server must support streaming responses

------------------------------------------------------------------------

---

---

### How should you structure a large React application?

Feature-based folder structure (`features/auth`, `features/dashboard`). Shared UI components in `components/`. Keep business logic in hooks/services. Clear separation between UI, state, and data layers. TypeScript for safety.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### How to conditionally apply class attributes?

You shouldn't use curly braces inside quotes because it is going to be evaluated as a string.

        ```jsx harmony
        <div className="btn-panel {this.props.visible ? 'show' : 'hidden'}">
        ```

        Instead you need to move curly braces outside (don't forget to include spaces between class names):

        ```jsx harmony
        <div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>
        ```

        _Template strings_ will also work:

        ```jsx harmony
        <div className={`btn-panel ${this.props.visible ? 'show' : 'hidden'}`}>
        ```

        ****

---

### How to define constants in React?

You can use ES7 `static` field to define constant.

    ```javascript
    class MyComponent extends React.Component {
      static DEFAULT_PAGINATION = 10;
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to implement _default_ or _NotFound_ page?

A `<Switch>` renders the first child `<Route>` that matches. A `<Route>` with no path always matches. So you just need to simply drop path attribute as below

        ```jsx harmony
        <Switch>
          <Route exact path="/" component={Home} />
          <Route path="/user" component={User} />
          <Route component={NotFound} />
        </Switch>
        ```

    ****

---

### How to pretty print JSON with React?

We can use `<pre>` tag so that the formatting of the `JSON.stringify()` is retained:

        ```jsx harmony
        const data = { name: "John", age: 42 };

        function User {
            return <pre>{JSON.stringify(data, null, 2)}</pre>;
        }

        const container = createRoot(document.getElementById("container"));

        container.render(<User />);
        ```

          <details><summary><b>See Class</b></summary>
          <p>

        ```jsx harmony
        const data = { name: "John", age: 42 };

        class User extends React.Component {
          render() {
            return <pre>{JSON.stringify(data, null, 2)}</pre>;
          }
        }

        React.render(<User />, document.getElementById("container"));
        ```

          </p>
          </details>

    ****

---

### How to programmatically trigger click event in React?

You could use the ref prop to acquire a reference to the underlying
`HTMLInputElement` object through a callback, store the reference as a
class property, then use that reference to later trigger a click from
your event handlers using the `HTMLElement.click` method.

    This can be done in two steps:

    1.  Create ref in render method:

        ```jsx harmony
        <input ref={(input) => (this.inputElement = input)} />
        ```

    2.  Apply click event in your event handler:

        ```javascript
        this.inputElement.click();
        ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to use class field declarations syntax in React classes?

React Class Components can be made much more concise using the class
field declarations. You can initialize the local state without using the
constructor and declare class methods by using arrow functions without
the extra need to bind them.

    Let's take a counter example to demonstrate class field declarations for state without using constructor and methods without binding,

    ```jsx
    class Counter extends Component {
      state = { value: 0 };

      handleIncrement = () => {
        this.setState((prevState) => ({
          value: prevState.value + 1,
        }));
      };

      handleDecrement = () => {
        this.setState((prevState) => ({
          value: prevState.value - 1,
        }));
      };

      render() {
        return (
          <div>
            {this.state.value}

            <button onClick={this.handleIncrement}>+</button>
            <button onClick={this.handleDecrement}>-</button>
          </div>
        );
      }
    }
    ```

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### How to use styles in React?

The `style` attribute accepts a JavaScript object with camelCased properties rather than a CSS string. This is consistent with the DOM style JavaScript property, is more efficient, and prevents XSS security holes.

        ```jsx harmony
        const divStyle = {
          color: "blue",
          backgroundImage: "url(" + imgUrl + ")",
        };

        function HelloWorldComponent() {
          return <div style={divStyle}>Hello World!</div>;
        }
        ```

        Style keys are camelCased in order to be consistent with accessing the properties on DOM nodes in JavaScript (e.g. `node.style.backgroundImage`).

        ****

---

### How to write comments in React?

The comments in React/JSX are similar to JavaScript Multiline comments but are wrapped in curly braces.

        **Single-line comments:**

        ```jsx harmony
        <div>
          {/* Single-line comments(In vanilla JavaScript, the single-line comments are represented by double slash(//)) */}
          {`Welcome ${user}, let's play React`}
        </div>
        ```

        **Multi-line comments:**

        ```jsx harmony
        <div>
          {/* Multi-line comments for more than
           one line */}
          {`Welcome ${user}, let's play React`}
        </div>
        ```

        You can use `//` and `/* */` in JS logic, hooks, and functions.

        ****

---

### How would you implement a robust frontend monitoring and logging system?

A robust system combines **error tracking**, **performance monitoring**, **user analytics**, and **structured logging**.

- **Error tracking**: Use Sentry, Rollbar, or similar. Capture JavaScript errors, unhandled promise rejections, and React error boundaries. Upload source maps to get readable stack traces.  
- **Performance monitoring**: Implement Real User Monitoring (RUM) with tools like Datadog RUM, New Relic Browser, or Google Analytics with Web Vitals. Track Core Web Vitals (LCP, CLS, INP), custom timings (e.g., time to checkout), and resource loading.  
- **Logging**: For client‑side, send structured logs to a backend endpoint (e.g., via `fetch`). Use a correlation ID across frontend and backend to trace requests. Avoid logging sensitive data.  
- **User analytics**: Use tools like Mixpanel or Amplitude to track feature usage, funnel conversions, and user flows.  
- **Alerts**: Set up alerts on error rate spikes, performance regressions, or business metric thresholds. Use tools like Sentry’s alert rules or Datadog monitors.  
- **Implementation**: Wrap the app in a monitoring provider that initializes SDKs, attaches user context, and buffers logs. Ensure logging doesn’t block the main thread – send data asynchronously in idle periods.

---

---

### How would you implement role-based access control (RBAC) in React?

Store user roles in auth context. Create a `usePermissions` hook that
checks roles. Wrap protected components with a `Can` component or
conditional rendering. Protect routes in the router (loader-level
redirect). Never trust client-side checks alone -- enforce on the
server.

------------------------------------------------------------------------

---

---

### How would you optimize a slow React application?

Diagnostic first --- profile with React DevTools Profiler to identify:

Components rendering too often → add React.memo, fix prop references
Expensive computations → wrap with useMemo Large bundle → code splitting
with React.lazy, tree shaking Slow initial load → SSR/SSG, preloading
critical resources Memory leaks → check useEffect cleanups, event
listener removal Long list rendering → implement virtualization Network
waterfall → parallel data fetching, caching with React Query/SWR

------------------------------------------------------------------------

---

---

### How you use decorators in React?

You can *decorate* your *class* components, which is the same as passing
the component into a function. **Decorators** are flexible and readable
way of modifying component functionality.

    ```jsx harmony
    @setTitle("Profile")
    class Profile extends React.Component {
      //....
    }

    /*
      title is a string that will be set as a document title
      WrappedComponent is what our decorator will receive when
      put directly above a component class as seen in the example above
    */
    const setTitle = (title) => (WrappedComponent) => {
      return class extends React.Component {
        componentDidMount() {
          document.title = title;
        }

        render() {
          return <WrappedComponent {...this.props} />;
        }
      };
    };
    ```

    **Note:** Decorators are a feature that didn't make it into ES7, but are currently a _stage 2 proposal_.

    ****

------------------------------------------------------------------------

---

---

### Implement Virtual Scrolling for very large lists.

**Requirements**: Efficiently render 100k+ items by only rendering visible portion.

**Design**:
- **Library**: `react-window` or `react-virtualized`.
- **Manual implementation**:
  - Compute total height = itemHeight * itemCount.
  - Track scrollTop; calculate start index = floor(scrollTop / itemHeight), end index = start + visibleCount + buffer.
  - Render only those items, absolutely positioned or using `transform: translateY`.
  - Use `useRef` to listen to scroll events and throttle.

**Edge cases**: Variable heights require measuring each item; libraries handle that.

---

### Is it possible to use async/await in plain React?

Yes, you can use `async/await` in plain React, as long as your
JavaScript environment supports ES2017+. Nowadays most modern browsers
and build tools support ES2017+ version. If you're using **Create React
App**, **Next.js**, **Remix**, or any modern React setup, `async/await`
is supported out of the box through **Babel**.

    ### Example Usage

    ```jsx
    import { useEffect, useState } from 'react';

    function UserProfile() {
      const **

------------------------------------------------------------------------

---

---

### `React.FC` vs explicit return type -- which is better?

Explicit: `function Comp({name}: Props): JSX.Element` is more explicit
about what's returned. `React.FC<Props>` implicitly types children and
return. The React team no longer recommends `React.FC` -- prefer
explicit typing.

------------------------------------------------------------------------

---

---

### Should I learn ES6 before learning ReactJS?

No, you don’t have to learn es2015/es6 to learn react. But you may find many resources or React ecosystem uses ES6 extensively. Let's see some of the frequently used ES6 features,

1. **Destructuring:** To get props and use them in a component

```
   // in es 5
   var someData = this.props.someData;
   var dispatch = this.props.dispatch;

   // in es6
   const { someData, dispatch } = this.props;

```

1. Spread operator: Helps in passing props down into a component

```
   // in es 5
   <SomeComponent someData={this.props.someData} dispatch={this.props.dispatch} />

   // in es6
   <SomeComponent {...this.props} />

```

1. Arrow functions: Makes compact syntax

```
   // es 5
   var users = usersList.map(function (user) {
     return <li>{user.name}</li>;
   });
   // es 6
   const users = usersList.map((user) => <li>{user.name}</li>);

```

[

---

### Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?

Store the raw list. Put the filter input update in urgent state. Wrap the filtered results computation in `useTransition` or `useDeferredValue`. React renders the input update immediately; filter results follow when resources free up.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What are inline conditional expressions?

You can use either _if statements_ or _ternary expressions_ which are available in JS(and JSX in React) to conditionally execute or render expressions. Apart from these approaches, you can also embed any expressions in JSX by wrapping them in curly braces and then followed by JS logical operator `&&`. It is helpful to render elements conditionally within a single line and commonly used for concise logic, especially in JSX rendering.

        ```jsx harmony
        <h1>Hello!</h1>;
        {
          messages.length > 0 && !isLogin ? (
            <h2>You have {messages.length} unread messages.</h2>
          ) : (
            <h2>You don't have unread messages.</h2>
          );
        }
        ```

        ****

---

### What are React Mixins?

**⚠️ DEPRECATED:** Mixins are considered legacy and should not be used
in modern React applications.

    _Mixins_ were a way to share common functionality between components using `React.createClass()`. However, they caused several problems:
    - Implicit dependencies
    - Name clashes
    - Snowballing complexity

    One of the most commonly used mixins was `PureRenderMixin`:

    ```javascript
    const PureRenderMixin = require("react-addons-pure-render-mixin");

    const Button = React.createClass({
      mixins: **

------------------------------------------------------------------------

---

---

### What are the advantages of React over Vue.js?

React has the following advantages over Vue.js:

         1. Gives more flexibility in large apps developing.
         2. Easier to test.
         3. Suitable for mobile apps creating.
         4. More information and solutions available.

    **Note:** The above list of advantages are purely opinionated and it vary based on the professional experience. But they are helpful as base parameters.

    ****

---

### What are the advantages of using React?

MVC is generally abbreviated as Model View Controller.

- **Use of Virtual DOM to improve efficiency: **React uses virtual DOM to render the view. As the name suggests, virtual DOM is a virtual representation of the real DOM. Each time the data changes in a react app, a new virtual DOM gets created. Creating a virtual DOM is much faster than rendering the UI inside the browser. Therefore, with the use of virtual DOM, the efficiency of the app improves.
- **Gentle learning curve:** React has a gentle learning curve when compared to frameworks like Angular. Anyone with little knowledge of javascript can start building web applications using React.
- **SEO friendly:** React allows developers to develop engaging user interfaces that can be easily navigated in various search engines. It also allows server-side rendering, which boosts the SEO of an app.
- **Reusable components: **React uses component-based architecture for developing applications. Components are independent and reusable bits of code. These components can be shared across various applications having similar functionality. The re-use of components increases the pace of development.
- **Huge ecosystem of libraries to choose from: **React provides you with the freedom to choose the tools, libraries, and architecture for developing an application based on your requirement.

---

---

### What are the common folder structures for React?

There are two common practices for React project file structure.

         1.  **Grouping by features or routes:**

            One common way to structure projects is locate CSS, JS, and tests together, grouped by feature or route.

            ```
            common/
            ├─ Avatar.js
            ├─ Avatar.css
            ├─ APIUtils.js
            └─ APIUtils.test.js
            feed/
            ├─ index.js
            ├─ Feed.js
            ├─ Feed.css
            ├─ FeedStory.js
            ├─ FeedStory.test.js
            └─ FeedAPI.js
            profile/
            ├─ index.js
            ├─ Profile.js
            ├─ ProfileHeader.js
            ├─ ProfileHeader.css
            └─ ProfileAPI.js
            ```

         2.  **Grouping by file type:**

            Another popular way to structure projects is to group similar files together.

            ```
            api/
            ├─ APIUtils.js
            ├─ APIUtils.test.js
            ├─ ProfileAPI.js
            └─ UserAPI.js
            components/
            ├─ Avatar.js
            ├─ Avatar.css
            ├─ Feed.js
            ├─ Feed.css
            ├─ FeedStory.js
            ├─ FeedStory.test.js
            ├─ Profile.js
            ├─ ProfileHeader.js
            └─ ProfileHeader.css
            ```

    ****

---

### What are the drawbacks of MVW pattern?

1. DOM manipulation is very expensive which causes applications to behave slow and inefficient.
         2. Due to circular dependencies, a complicated model was created around models and views.
         3. Lot of data changes happens for collaborative applications(like Google Docs).
         4. No way to do undo (travel back in time) easily without adding so much extra code.

    ****

---

### What are the methods invoked during error handling?

Below methods are called when there is an error during rendering, in a lifecycle method, or in the constructor of any child component.

1. static getDerivedStateFromError()
2. componentDidCatch()

[

---

### What are the popular React-specific linters?

ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types.

        Another popular plugin is `eslint-plugin-jsx-a11y`, which will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with `alt` text and `tabindex`, for example, will not be picked up by regular plugins.

    ****

    ## React Router

    ****

---

### What happened to event pooling?

In React 16 and earlier, `SyntheticEvent` objects were pooled and reused – accessing event properties asynchronously returned null. React 17 removed pooling. `event.persist()` is no longer needed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is a consumer?

A Consumer is a React component that subscribes to context changes. It requires a function as a child which receives current context value as argument and returns a react node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree.

Lets take a simple example,


```
<MyContext.Consumer>
  {value => /* render something based on the context value */}
</MyContext.Consumer>

```

[

---

### What is a focus trap?

Confines keyboard focus within a modal/dialog so Tab doesn't reach content behind it. Required for accessible modals. Libraries: `focus-trap-react`, `@radix-ui/react-dialog` handle this automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is an updater function? Should an updater function be used in all cases?

An **updater function** is a form of `setState` where you pass a
**function** instead of a direct value. This function receives the
**previous state** as an argument and returns the **next state**.

     The updater function expression looks like below,
     ```js
     setCount(prevCount => prevCount + 1); // Safe and predictable
     ```
     Here, `prevCount => prevCount + 1` is the updater function.

     In the React community, there's often a recommendation to use updater functions when updating state that depends on its previous value. This helps prevent unexpected behaviors that can arise from working with outdated or "stale" state.

     While using an updater function is a good habit, it's not always necessary. In most cases, React batches updates and ensures that the state is up-to-date at the beginning of the event handler, so you typically don’t run into stale state issues during a single synchronous event.
     However, if you’re doing multiple updates to the same state variable within a single handler, using the updater form ensures that each update correctly uses the latest state value, rather than a potentially outdated one.

     **Example: Multiple Updates in One Handler**
     ```js
     function handleCount() {
        setCounter(a => a + 1);
        setCounter(a => a + 1);
        setCounter(a => a + 1);
     }
     ```

     In this example, `a => a + 1` is an **updater function**. React queues these updater functions and applies them sequentially, each using the most recent state value. As a result, the counter will correctly increment by 3.

     In many cases, such as setting state based on user input or assigning static values, you don’t need the updater function:
     ```js
     setName('Sudheer');
     ```
     

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is chaos engineering for frontend?

Chaos engineering is the practice of intentionally introducing failures to test system resilience. For frontend, it means simulating network issues, slow responses, API errors, or resource constraints to ensure the UI degrades gracefully.

**Examples**:
- **Network throttling** – simulate slow 3G to test lazy loading and timeouts.  
- **API failures** – mock 5xx responses and ensure error states appear.  
- **JavaScript exceptions** – inject errors to test error boundaries and fallback UI.  
- **Resource exhaustion** – simulate low memory or high CPU to see if the app remains responsive.

**Tools**:  
- Browser DevTools network throttling.  
- Chaos Monkey for frontend (e.g., using a library that randomly blocks requests).  
- Custom middleware in development to inject latency or errors.  

**Goal**: Build confidence that the app won’t crash under adverse conditions and provides clear feedback to users.

---

---

### What is colocation in React?

Keeping related code together -- state close to where it's used, styles
next to components, tests next to source. Avoid premature abstraction.
Move state up only when shared, not just to 'be organized'.

------------------------------------------------------------------------

---

---

### What is createAsyncThunk() and why is it used?

createAsyncThunk handles async operations (API calls) in Redux. It takes
an action type string and an async payload creator function. It
automatically dispatches three action types: actionName/pending
(loading), actionName/fulfilled (success with data), actionName/rejected
(error). Handle these in extraReducers with builder.addCase(). This
standardizes async state management and eliminates manual loading/error
state boilerplate.

------------------------------------------------------------------------

---

### 208. Given an array of users, find all active user ids.

**Array**:
`users = [{ id: 1, active: true }, { id: 2, active: false }]`\
Also with `null`, `{}`, etc.

``` javascript
function getActiveIds(users) {
  return users
    .filter(user => user && typeof user === 'object' && user.active === true)
    .map(user => user.id);
}
```

---

---

### What is event delegation in React?

React attaches a single event listener at the root DOM node and routes
events to the correct handler using its internal fiber tree. Efficient:
one listener handles all events instead of per-element listeners.

------------------------------------------------------------------------

---

---

### What is focus management and why does it matter?

After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is prop inversion of control?

Prop Inversion of Control (IoC) means a component stops bossing its pieces around and instead says to the developer using it: "You take the wheel, you decide how this part should work."

Instead of hardcoding every single behavior inside the component and adding 50 different configuration props, the component hands control back over to you.

const names = ["Alice", "Bob", "Charlie"];

<List 
  items={names} 
  renderItem={(name) => <span>👤 {name}</span>} 
/>

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is React?

React is a front-end and open-source JavaScript library which is useful in developing user interfaces specifically for applications with a single page. It is helpful in building complex and reusable user interface(UI) components of mobile and web applications as it follows the component-based approach.

The important features of React are:

- It supports server-side rendering.
- It will make use of the virtual DOM rather than real DOM (Data Object Model) as RealDOM manipulations are expensive.
- It follows unidirectional data binding or data flow.
- It uses reusable or composable UI components for developing the view.

**Create a free personalised study plan**

Get into your dream companies with expert guidance

Real-Life Problems

Prep for Target Roles

Custom Plan Duration

[**Create My Plan**](https://www.interviewbit.com/interview-preparation-kit/)

---

---

### What is React and what problem does it solve?

React is a JavaScript library by Meta for building UIs using a
declarative, component-based model. It solves the complexity of keeping
the UI in sync with application state by reacting to state changes
automatically and efficiently updating the DOM.

------------------------------------------------------------------------

---

---

### What is React Dev Tools?

_React Developer Tools_ let you inspect the component hierarchy, including component props and state. It exists both as a browser extension (for Chrome and Firefox), and as a standalone app (works with other environments including Safari, IE, and React Native).

         The official extensions available for different browsers or environments.

         1. **Chrome extension**
         2. **Firefox extension**
         3. **Standalone app** (Safari, React Native, etc)

    ****

---

### What is React JS?

React is a declarative, component-based JavaScript library for building
user interfaces. Declarative means you describe WHAT the UI should look
like for a given state --- React handles HOW the DOM updates. Components
are reusable, isolated pieces of UI that manage their own state and
props. React uses a virtual DOM to efficiently update the real DOM, a
unidirectional data flow (props flow down, events flow up), and JSX for
writing HTML-like syntax in JavaScript.

------------------------------------------------------------------------

---

---

### What is React proptype array with shape?

If you want to pass an array of objects to a component with a particular
shape then use `React.PropTypes.shape()` as an argument to
`React.PropTypes.arrayOf()`.

    ```javascript
    ReactComponent.propTypes = {
      arrayWithShape: React.PropTypes.arrayOf(
        React.PropTypes.shape({
          color: React.PropTypes.string.isRequired,
          fontSize: React.PropTypes.number.isRequired,
        })
      ).isRequired,
    };
    ```

    ****

------------------------------------------------------------------------

---

---

### What is render hijacking in react?

The concept of render hijacking is the ability to control what a
component will output from another component. It means that you decorate
your component by wrapping it into a Higher-Order component. By
wrapping, you can inject additional props or make other changes, which
can cause changing logic of rendering. It does not actually enable
hijacking, but by using HOC you make your component behave differently.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### What is `TestRenderer` package in React?

This package provides a renderer that can be used to render components
to pure JavaScript objects, without depending on the DOM or a native
mobile environment. This package makes it easy to grab a snapshot of the
platform view hierarchy (similar to a DOM tree) rendered by a ReactDOM
or React Native without using a browser or `jsdom`.

    ```jsx harmony
    import TestRenderer from "react-test-renderer";

    const Link = ({ page, children }) => <a href={page}>{children}</a>;

    const testRenderer = TestRenderer.create(
      <Link page={"https://www.facebook.com/"}>{"Facebook"}</Link>
    );

    console.log(testRenderer.toJSON());
    // {
    //   type: 'a',
    //   props: { href: 'https://www.facebook.com/' },
    //   children: **

------------------------------------------------------------------------

---

---

### What is the 'why did you render' library?

A development utility that patches React to notify you when a component re-renders due to reference-equal props/state. Helps find components where `React.memo` or `useMemo` would be beneficial.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the behavior of uncaught errors in react 16?

**Note:** This behavior was introduced in React 16 and continues in React 18/19.
         
         In React 16+, errors that are not caught by any error boundary will result in unmounting of the whole React component tree. The reason behind this decision is that it is worse to leave corrupted UI in place than to completely remove it. For example, it is worse for a payments app to display a wrong amount than to render nothing.

         **Best Practice:** Always wrap your application or critical sections in error boundaries to prevent complete unmounting and provide a better user experience.

         ```jsx
         <ErrorBoundary fallback={<ErrorPage />}>
           <App />
         </ErrorBoundary>
         ```

    ****

---

### What is the benefit of styles modules?

It is recommended to avoid hard coding style values in components. Any values that are likely to be used across different UI components should be extracted into their own modules.

        For example, these styles could be extracted into a separate component:

        ```javascript
        export const colors = {
          white,
          black,
          blue,
        };

        export const space = **

---

### What is the difference between optimistic and pessimistic updates?

Optimistic: update UI immediately assuming success, roll back on error (fast UX). Pessimistic: wait for server confirmation before updating UI (safe, may feel slow). React 19 has `useOptimistic` for the optimistic pattern.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the difference between React and Angular?

Let's see the difference between React and Angular in a table format.

         | React                                                                                       | Angular                                                                                                                            |
         | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
         | React is a library and has only the View layer                                              | Angular is a framework and has complete MVC functionality                                                                          |
         | React handles rendering on the server side                                                  | AngularJS renders only on the client side but Angular 2 and above renders on the server side                                       |
         | React uses JSX that looks like HTML in JS which can be confusing                            | Angular follows the template approach for HTML, which makes code shorter and easy to understand                                    |
         | React Native, which is a React type to build mobile applications are faster and more stable | Ionic, Angular's mobile native app is relatively less stable and slower                                                            |
         | In React, data flows only in one way and hence debugging is easy                            | In Angular, data flows both way i.e it has two-way data binding between children and parent and hence debugging is often difficult |

    **Note:** The above list of differences are purely opinionated and it vary based on the professional experience. But they are helpful as base parameters.

    ****

---

### What is the difference between React and ReactDOM?

The `react` package contains `React.createElement()`, `React.Component`,
`React.Children`, and other helpers related to elements and component
classes. You can think of these as the isomorphic or universal helpers
that you need to build components. The `react-dom` package contains
`ReactDOM.render()`, and in `react-dom/server` we have *server-side
rendering* support with `ReactDOMServer.renderToString()` and
`ReactDOMServer.renderToStaticMarkup()`.

    ****

------------------------------------------------------------------------

---

---

### What is the main purpose of constructor?

The constructor is mainly used for two purposes,

1. To initialize local state by assigning object to this.state
2. For binding event handler methods to the instance For example, the below code covers both the above cases,

```
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}

```

[

---

### What is the provider pattern?

A component that wraps part of the tree and supplies shared state/functionality via context. Used extensively: `ThemeProvider`, `AuthProvider`, `QueryClientProvider`. Stacking providers is common.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is the purpose of displayName class property?

The displayName string is used in debugging messages. Usually, you don’t need to set it explicitly because it’s inferred from the name of the function or class that defines the component. You might want to set it explicitly if you want to display a different name for debugging purposes or when you create a higher-order component.

         For example, To ease debugging, choose a display name that communicates that it’s the result of a withSubscription HOC.

         ```javascript
         function withSubscription(WrappedComponent) {
           class WithSubscription extends React.Component {
             /* ... */
           }
           WithSubscription.displayName = `WithSubscription(${getDisplayName(
             WrappedComponent
           )})`;
           return WithSubscription;
         }
         function getDisplayName(WrappedComponent) {
           return (
             WrappedComponent.displayName || WrappedComponent.name || "Component"
           );
         }
         ```

    ****

---

### What is the purpose of ReactTestUtils package?

_ReactTestUtils_ are provided in the `with-addons` package and allow you to perform actions against a simulated DOM for the purpose of unit testing.

    ****

---

### What is the React Compiler (React Forget)?

The **React Compiler** (formerly known as React Forget) automatically
optimizes your components by adding memoization where needed -
eliminating the need for manual `useMemo`, `useCallback`, and
`React.memo`.

     #### Before React Compiler
     ```jsx
     function TodoList({ todos, filter }) {
       // Manual optimization needed
       const filteredTodos = useMemo(() => {
         return todos.filter(todo => todo.status === filter);
       }, **

------------------------------------------------------------------------

---

---

### What is the `react-error-boundary` library?

Provides `<ErrorBoundary fallback={...}>` and
`<ErrorBoundary FallbackComponent={...}>`. Also provides
`useErrorBoundary()` hook to imperatively throw errors into the nearest
boundary and reset it.

------------------------------------------------------------------------

---

---

### What is the role of Babel in a React project?

Transpiles modern JS and JSX to browser-compatible JS. Plugins transform
JSX to `createElement` calls. In Vite projects, esbuild handles
transpilation faster; Babel is less common in new setups.

------------------------------------------------------------------------

---

---

### What is the use of `react-dom` package?

The `react-dom` package provides *DOM-specific methods* that can be used
at the top level of your app. Most of the components are not required to
use this module. Some of the methods of this package are:

    1. `render()`
    2. `hydrate()`
    3. `unmountComponentAtNode()`
    4. `findDOMNode()`
    5. `createPortal()`

    ****

------------------------------------------------------------------------

---

---

### What is `useFormStatus`?

A hook available inside a form child component. Returns `{pending, data, method, action}` of the parent form's submission. Lets you disable inputs or show spinners without prop drilling from the form.

[⬆ Back to Table of Contents](#-table-of-contents)

---

---

### What is your favorite React stack?

Even though the tech stack varies from developer to developer, the most
popular stack is used in react boilerplate project code. It mainly uses
Redux and redux-saga for state management and asynchronous side-effects,
react-router for routing purpose, styled-components for styling react
components, axios for invoking REST api, and other supported stack such
as webpack, reselect, ESNext, Babel. You can clone the project
https://github.com/react-boilerplate/react-boilerplate and start working
on any new react project.

------------------------------------------------------------------------

------------------------------------------------------------------------

---

---

### When did you get stuck while using React, and how did you fix it?

**Approach**: Describe a technical problem that had you stuck for a
while, how you debugged it, and what you learned.

**Example**: \> "I was building a drag‑and‑drop kanban board with React.
The issue was that after dropping a card, the state updated correctly,
but the card would visually jump back to its original position for a
split second before snapping to the new column. \> \> **What I tried**:
I checked the reducer, verified that the state was immutable, and used
`React.memo` on the card components. Nothing worked. \> \> **How I fixed
it**: I realized that the drag library I was using (`react-dnd`) was
updating the DOM imperatively during the drag. After the drop, React
would reconcile its virtual DOM and reset the card's inline styles. I
solved it by resetting the drag preview style in a `useLayoutEffect`
after the state update, ensuring that React's reconciliation happened
after the drop animation. \> \> **Lesson**: I learned that mixing
imperative DOM manipulation (like drag libraries) with React's
declarative model requires careful timing. I also became more proficient
in `useLayoutEffect` and the React lifecycle."

------------------------------------------------------------------------

---

---

### When do you need to use refs?

There are few use cases to go for refs,

1. Managing focus, text selection, or media playback.
2. Triggering imperative animations.
3. Integrating with third-party DOM libraries.

[

---

### When to Use

- ✅ Toggling likes/favorites
     - ✅ Adding/removing items from lists
     - ✅ Sending messages in chat
     - ✅ Any action where immediate feedback improves UX
     - ❌ Financial transactions (wait for confirmation)
     - ❌ Critical operations requiring server validation

326. ### What is the React Compiler (React Forget)?

     The **React Compiler** (formerly known as React Forget) automatically optimizes your components by adding memoization where needed - eliminating the need for manual `useMemo`, `useCallback`, and `React.memo`.

     #### Before React Compiler
     ```jsx
     function TodoList({ todos, filter }) {
       // Manual optimization needed
       const filteredTodos = useMemo(() => {
         return todos.filter(todo => todo.status === filter);
       }, [todos, filter]);

       const handleToggle = useCallback((id) => {
         toggleTodo(id);
       }, [toggleTodo]);

       return (
         <div>
           {filteredTodos.map(todo => (
             <TodoItem 
               key={todo.id} 
               todo={todo} 
               onToggle={handleToggle} 
             />
           ))}
         </div>
       );
     }

     // Need to wrap in React.memo
     export default React.memo(TodoList);
     ```

     #### With React Compiler
     ```jsx
     function TodoList({ todos, filter }) {
       // Compiler automatically optimizes this!
       const filteredTodos = todos.filter(todo => todo.status === filter);

       const handleToggle = (id) => {
         toggleTodo(id);
       };

       return (
         <div>
           {filteredTodos.map(todo => (
             <TodoItem 
               key={todo.id} 
               todo={todo} 
               onToggle={handleToggle} 
             />
           ))}
         </div>
       );
     }

     // No React.memo needed!
     export default TodoList;
     ```

---

### Why are inline ref callbacks or functions not recommended?

If the ref callback is defined as an inline function, it will get called twice during updates, first with null and then again with the DOM element. This is because a new instance of the function is created with each render, so React needs to clear the old ref and set up the new one.


```
class UserForm extends Component {
  handleSubmit = () => {
    console.log('Input Value is: ', this.input.value);
  };

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <input type="text" ref={(input) => (this.input = input)} /> // Access DOM input in handle
        submit
        <button type="submit">Submit</button>
      </form>
    );
  }
}

```

But our expectation is for the ref callback to get called once, when the component mounts. One quick fix is to use the ES7 class property syntax to define the function


```
class UserForm extends Component {
  handleSubmit = () => {
    console.log('Input Value is: ', this.input.value);
  };

  setSearchInput = (input) => {
    this.input = input;
  };

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <input type="text" ref={this.setSearchInput} /> // Access DOM input in handle submit
        <button type="submit">Submit</button>
      </form>
    );
  }
}

```

**Note:** In React v16.3, [

---

### Why do you not required to use inheritance?

In React, it is recommend using composition instead of inheritance to reuse code between components. Both Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Whereas, If you want to reuse non-UI functionality between components, it is suggested to extracting it into a separate JavaScript module. Later components import it and use that function, object, or a class, without extending it.

[

---

### Why React uses `className` over `class` attribute?

React uses **className** instead of **class** because of a JavaScript naming conflict with the class keyword.

        1. `class` is a reserved keyword in JavaScript
            In JavaScript, class is used to define ES6 classes:
          
            ```js
            class Person {
              constructor(name) {
                this.name = name;
              }
            }
            ```
            If you try to use class as a variable or property name, it will throw a syntax error. Since JSX is just JavaScript with XML-like syntax, using class directly in JSX would break the parser.

        2. JSX Is JavaScript
        
            When you write JSX like this:
            ```jsx
            <div class="btn">Click</div>
            ```
            It will be compiled to:
            ```jsx
            React.createElement('div', { class: 'btn' }, 'Click');
            ```
            But `class` is invalid in this object literal context (since it clashes with the JS keyword), hence React instead uses className.
            ```jsx
            <div className="btn">Click</div>
            ```
            which compiles to:
            ```jsx
            React.createElement('div', { className: 'btn' }, 'Click');
            ```
            React then translates `className` to` class` in the final HTML DOM.

        3. Aligns with DOM APIs
            In vanilla JavaScript, you interact with element classes using:
            ```js
            element.className = 'my-class';
            ```
            React follows this convention, staying consistent with the DOM API's property name rather than HTML’s attribute.

        ****

---

### Why React.js? What problems does it solve?

React solves several frontend challenges: - **Declarative UI**: Instead
of imperatively manipulating the DOM, you describe what the UI should
look like for a given state. React handles updates efficiently. -
**Component‑based architecture**: Encourages reusability,
maintainability, and separation of concerns. - **Efficient updates**:
Virtual DOM diffing minimizes costly DOM manipulations. -
**Unidirectional data flow**: Makes data flow predictable and easier to
debug. - **Ecosystem and community**: Rich tooling, libraries (React
Router, Redux), and strong community support.

------------------------------------------------------------------------

---

---

### Why ReactDOM is separated from React?

The React team worked on extracting all DOM-related features into a
separate library called *ReactDOM*. React v0.14 is the first release in
which the libraries are split. By looking at some of the packages,
`react-native`, `react-art`, `react-canvas`, and `react-three`, it has
become clear that the beauty and essence of React has nothing to do with
browsers or the DOM.

    To build more environments that React can render to, React team planned to split the main React package into two: `react` and `react-dom`. This paves the way to writing components that can be shared between the web version of React and React Native.
