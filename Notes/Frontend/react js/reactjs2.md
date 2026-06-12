# ⚛️ React.js – Comprehensive Interview Question Bank

**225+ Questions across 18 sections**

*Fundamentals · Hooks · Patterns · Performance · TypeScript · Testing · RSC · Senior Scenarios*

---

## 📋 Table of Contents

### Section 1: Fundamentals & JSX
| # | Question |
|---|----------|
| Q1 | [What is React and what problem does it solve?](#q1-what-is-react-and-what-problem-does-it-solve) |
| Q2 | [How is React different from Angular or Vue?](#q2-how-is-react-different-from-angular-or-vue) |
| Q3 | [What is JSX and why does React use it?](#q3-what-is-jsx-and-why-does-react-use-it) |
| Q4 | [What does JSX compile to?](#q4-what-does-jsx-compile-to) |
| Q5 | [Can you use React without JSX?](#q5-can-you-use-react-without-jsx) |
| Q6 | [What is the Virtual DOM?](#q6-what-is-the-virtual-dom) |
| Q7 | [How does the Virtual DOM improve performance?](#q7-how-does-the-virtual-dom-improve-performance) |
| Q8 | [What are React elements vs React components?](#q8-what-are-react-elements-vs-react-components) |
| Q9 | [What is `createRoot()` and why was it introduced in React 18?](#q9-what-is-createroot-and-why-was-it-introduced-in-react-18) |
| Q10 | [What are pure components?](#q10-what-are-pure-components) |
| Q11 | [What is the difference between an element and a component instance?](#q11-what-is-the-difference-between-an-element-and-a-component-instance) |
| Q12 | [What does 'declarative' mean in React?](#q12-what-does-declarative-mean-in-react) |
| Q13 | [What is the React DevTools and what can you do with it?](#q13-what-is-the-react-devtools-and-what-can-you-do-with-it) |
| Q14 | [What are the rules of JSX?](#q14-what-are-the-rules-of-jsx) |
| Q15 | [What is a React SPA and what are its trade-offs?](#q15-what-is-a-react-spa-and-what-are-its-trade-offs) |

### Section 2: Components, Props & State
| # | Question |
|---|----------|
| Q16 | [What is a React component?](#q16-what-is-a-react-component) |
| Q17 | [Functional vs class components – key differences?](#q17-functional-vs-class-components--key-differences) |
| Q18 | [What are props?](#q18-what-are-props) |
| Q19 | [How do you pass data child → parent?](#q19-how-do-you-pass-data-child--parent) |
| Q20 | [What is prop drilling and why is it a problem?](#q20-what-is-prop-drilling-and-why-is-it-a-problem) |
| Q21 | [What is state in React?](#q21-what-is-state-in-react) |
| Q22 | [What is the difference between props and state?](#q22-what-is-the-difference-between-props-and-state) |
| Q23 | [Why is state update asynchronous?](#q23-why-is-state-update-asynchronous) |
| Q24 | [What is lifting state up?](#q24-what-is-lifting-state-up) |
| Q25 | [What is the `key` prop and why is it important?](#q25-what-is-the-key-prop-and-why-is-it-important) |
| Q26 | [Why avoid array index as key?](#q26-why-avoid-array-index-as-key) |
| Q27 | [Controlled vs uncontrolled components?](#q27-controlled-vs-uncontrolled-components) |
| Q28 | [What are fragments?](#q28-what-are-fragments) |
| Q29 | [What are portals?](#q29-what-are-portals) |
| Q30 | [What are default props and PropTypes?](#q30-what-are-default-props-and-proptypes) |
| Q31 | [What is the children prop?](#q31-what-is-the-children-prop) |
| Q32 | [When should a component be split into smaller components?](#q32-when-should-a-component-be-split-into-smaller-components) |
| Q33 | [What is the difference between element and component re-render?](#q33-what-is-the-difference-between-element-and-component-re-render) |
| Q34 | [What are presentational vs container components?](#q34-what-are-presentational-vs-container-components) |
| Q35 | [What happens if you mutate state directly?](#q35-what-happens-if-you-mutate-state-directly) |

### Section 3: Rendering, Reconciliation & Lifecycle
| # | Question |
|---|----------|
| Q36 | [What is reconciliation?](#q36-what-is-reconciliation) |
| Q37 | [How does React's diffing algorithm work (O(n))?](#q37-how-does-reacts-diffing-algorithm-work-on) |
| Q38 | [What is React Fiber?](#q38-what-is-react-fiber) |
| Q39 | [What are the three main lifecycle phases?](#q39-what-are-the-three-main-lifecycle-phases) |
| Q40 | [Map class lifecycle methods to hooks.](#q40-map-class-lifecycle-methods-to-hooks) |
| Q41 | [What is the order of hook execution in a component?](#q41-what-is-the-order-of-hook-execution-in-a-component) |
| Q42 | [What causes unnecessary re-renders?](#q42-what-causes-unnecessary-re-renders) |
| Q43 | [What is hydration?](#q43-what-is-hydration) |
| Q44 | [What causes hydration mismatches and how do you fix them?](#q44-what-causes-hydration-mismatches-and-how-do-you-fix-them) |
| Q45 | [What is Strict Mode?](#q45-what-is-strict-mode) |
| Q46 | [What is `getDerivedStateFromProps` and when would you use it?](#q46-what-is-getderivedstatefromprops-and-when-would-you-use-it) |
| Q47 | [What is `getSnapshotBeforeUpdate`?](#q47-what-is-getsnapshotbeforeupdate) |
| Q48 | [Explain the commit phase vs render phase.](#q48-explain-the-commit-phase-vs-render-phase) |
| Q49 | [What happens when a parent re-renders?](#q49-what-happens-when-a-parent-re-renders) |
| Q50 | [What is `shouldComponentUpdate` and its functional equivalent?](#q50-what-is-shouldcomponentupdate-and-its-functional-equivalent) |

### Section 4: Core Hooks
| # | Question |
|---|----------|
| Q51 | [What is `useState`?](#q51-what-is-usestate) |
| Q52 | [Why use functional updates with `useState`?](#q52-why-use-functional-updates-with-usestate) |
| Q53 | [What is lazy initialization in `useState`?](#q53-what-is-lazy-initialization-in-usestate) |
| Q54 | [What is `useEffect`?](#q54-what-is-useeffect) |
| Q55 | [What is the `useEffect` cleanup function?](#q55-what-is-the-useeffect-cleanup-function) |
| Q56 | [What are stale closures in `useEffect`?](#q56-what-are-stale-closures-in-useeffect) |
| Q57 | [What is `useRef`?](#q57-what-is-useref) |
| Q58 | [How does `useRef` differ from a regular variable?](#q58-how-does-useref-differ-from-a-regular-variable) |
| Q59 | [What is `useContext`?](#q59-what-is-usecontext) |
| Q60 | [What is `useReducer`?](#q60-what-is-usereducer) |
| Q61 | [What is `useMemo`?](#q61-what-is-usememo) |
| Q62 | [What is `useCallback`?](#q62-what-is-usecallback) |
| Q63 | [`useMemo` vs `useCallback` – what's the difference?](#q63-usememo-vs-usecallback--whats-the-difference) |
| Q64 | [What is `useLayoutEffect`?](#q64-what-is-uselayouteffect) |
| Q65 | [What is `useImperativeHandle`?](#q65-what-is-useimperativehandle) |
| Q66 | [What are the Rules of Hooks?](#q66-what-are-the-rules-of-hooks) |
| Q67 | [How do you create a custom hook?](#q67-how-do-you-create-a-custom-hook) |
| Q68 | [What is `useId`?](#q68-what-is-useid) |
| Q69 | [What is `useDebugValue`?](#q69-what-is-usedebugvalue) |
| Q70 | [Situation: `useEffect` runs infinitely – what's wrong?](#q70-situation-useeffect-runs-infinitely--whats-wrong) |

### Section 5: Advanced Hooks & Performance
| # | Question |
|---|----------|
| Q71 | [What is `React.memo`?](#q71-what-is-reactmemo) |
| Q72 | [When does `React.memo` NOT help?](#q72-when-does-reactmemo-not-help) |
| Q73 | [How do you avoid unnecessary object/function recreation?](#q73-how-do-you-avoid-unnecessary-objectfunction-recreation) |
| Q74 | [What is windowing/virtualization and when do you need it?](#q74-what-is-windowingvirtualization-and-when-do-you-need-it) |
| Q75 | [What is code splitting?](#q75-what-is-code-splitting) |
| Q76 | [What is `React.lazy` and how does it work?](#q76-what-is-reactlazy-and-how-does-it-work) |
| Q77 | [What is the Profiler API?](#q77-what-is-the-profiler-api) |
| Q78 | [How do you measure and fix excessive re-renders?](#q78-how-do-you-measure-and-fix-excessive-re-renders) |
| Q79 | [What is the `useTransition` hook for performance?](#q79-what-is-the-usetransition-hook-for-performance) |
| Q80 | [What is `useDeferredValue`?](#q80-what-is-usedeferredvalue) |
| Q81 | [Situation: A search input lags as user types – how do you fix it?](#q81-situation-a-search-input-lags-as-user-types--how-do-you-fix-it) |
| Q82 | [What is tree shaking?](#q82-what-is-tree-shaking) |
| Q83 | [What are common React performance pitfalls?](#q83-what-are-common-react-performance-pitfalls) |
| Q84 | [What is the 'why did you render' library?](#q84-what-is-the-why-did-you-render-library) |
| Q85 | [What is the difference between optimistic and pessimistic updates?](#q85-what-is-the-difference-between-optimistic-and-pessimistic-updates) |

### Section 6: Context & State Management
| # | Question |
|---|----------|
| Q86 | [What is the Context API?](#q86-what-is-the-context-api) |
| Q87 | [Context re-render behavior – what should you know?](#q87-context-re-render-behavior--what-should-you-know) |
| Q88 | [When should you NOT use Context for state?](#q88-when-should-you-not-use-context-for-state) |
| Q89 | [Context vs Redux – when to choose which?](#q89-context-vs-redux--when-to-choose-which) |
| Q90 | [What is Zustand and how does it differ from Redux?](#q90-what-is-zustand-and-how-does-it-differ-from-redux) |
| Q91 | [What is Jotai and how does the atomic model work?](#q91-what-is-jotai-and-how-does-the-atomic-model-work) |
| Q92 | [What is server state vs client state?](#q92-what-is-server-state-vs-client-state) |
| Q93 | [What is React Query (TanStack Query)?](#q93-what-is-react-query-tanstack-query) |
| Q94 | [Situation: Two components on different branches need the same data – what do you do?](#q94-situation-two-components-on-different-branches-need-the-same-data--what-do-you-do) |
| Q95 | [What is the Redux Toolkit (RTK)?](#q95-what-is-the-redux-toolkit-rtk) |
| Q96 | [What is the `useSelector` / `useDispatch` pattern in Redux?](#q96-what-is-the-useselector--usedispatch-pattern-in-redux) |
| Q97 | [Situation: Context is causing performance issues in a large app – what do you do?](#q97-situation-context-is-causing-performance-issues-in-a-large-app--what-do-you-do) |
| Q98 | [What is the flux architecture pattern?](#q98-what-is-the-flux-architecture-pattern) |

### Section 7: Component Patterns & Architecture
| # | Question |
|---|----------|
| Q99 | [What are Higher-Order Components (HOCs)?](#q99-what-are-higher-order-components-hocs) |
| Q100 | [What is the render props pattern?](#q100-what-is-the-render-props-pattern) |
| Q101 | [What are compound components?](#q101-what-are-compound-components) |
| Q102 | [What is the provider pattern?](#q102-what-is-the-provider-pattern) |
| Q103 | [What is the state reducer pattern?](#q103-what-is-the-state-reducer-pattern) |
| Q104 | [What is the controlled component pattern for reusable components?](#q104-what-is-the-controlled-component-pattern-for-reusable-components) |
| Q105 | [Custom hooks vs HOCs vs render props – when to use each?](#q105-custom-hooks-vs-hocs-vs-render-props--when-to-use-each) |
| Q106 | [How should you structure a large React application?](#q106-how-should-you-structure-a-large-react-application) |
| Q107 | [What is colocation in React?](#q107-what-is-colocation-in-react) |
| Q108 | [What is the container/presenter pattern and is it still relevant?](#q108-what-is-the-containerpresenter-pattern-and-is-it-still-relevant) |
| Q109 | [How do you design a reusable button component?](#q109-how-do-you-design-a-reusable-button-component) |
| Q110 | [How do you build a reusable modal?](#q110-how-do-you-build-a-reusable-modal) |
| Q111 | [What is prop inversion of control?](#q111-what-is-prop-inversion-of-control) |
| Q112 | [What are headless components?](#q112-what-are-headless-components) |
| Q113 | [How do you prevent prop explosion in complex components?](#q113-how-do-you-prevent-prop-explosion-in-complex-components) |

### Section 8: Error Handling & Boundaries
| # | Question |
|---|----------|
| Q114 | [What is an error boundary?](#q114-what-is-an-error-boundary) |
| Q115 | [How do you create an error boundary?](#q115-how-do-you-create-an-error-boundary) |
| Q116 | [What errors can't error boundaries catch?](#q116-what-errors-cant-error-boundaries-catch) |
| Q117 | [Is there a functional equivalent of error boundaries?](#q117-is-there-a-functional-equivalent-of-error-boundaries) |
| Q118 | [What is the `react-error-boundary` library?](#q118-what-is-the-react-error-boundary-library) |
| Q119 | [Situation: A third-party component throws – how do you handle it?](#q119-situation-a-third-party-component-throws--how-do-you-handle-it) |
| Q120 | [How do you handle errors in `useEffect`?](#q120-how-do-you-handle-errors-in-useeffect) |
| Q121 | [What is global error monitoring in React apps?](#q121-what-is-global-error-monitoring-in-react-apps) |

### Section 9: React 18, 19 & Concurrency
| # | Question |
|---|----------|
| Q122 | [What is concurrent rendering?](#q122-what-is-concurrent-rendering) |
| Q123 | [What is automatic batching in React 18?](#q123-what-is-automatic-batching-in-react-18) |
| Q124 | [What is `startTransition`?](#q124-what-is-starttransition) |
| Q125 | [What is `useTransition`?](#q125-what-is-usetransition) |
| Q126 | [What is `useDeferredValue`?](#q126-what-is-usedeferredvalue) |
| Q127 | [What is Suspense?](#q127-what-is-suspense) |
| Q128 | [What is streaming SSR?](#q128-what-is-streaming-ssr) |
| Q129 | [What are React Server Components (RSC)?](#q129-what-are-react-server-components-rsc) |
| Q130 | [RSC vs SSR – what's the difference?](#q130-rsc-vs-ssr--whats-the-difference) |
| Q131 | [What is the 'use client' directive?](#q131-what-is-the-use-client-directive) |
| Q132 | [What are React 19 Actions?](#q132-what-are-react-19-actions) |
| Q133 | [What is `useActionState` (React 19)?](#q133-what-is-useactionstate-react-19) |
| Q134 | [What is `useOptimistic` (React 19)?](#q134-what-is-useoptimistic-react-19) |
| Q135 | [What is `useFormStatus`?](#q135-what-is-useformstatus) |
| Q136 | [Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?](#q136-situation-you-need-to-keep-the-ui-responsive-during-a-heavy-filter-operation-on-10k-items--how) |

### Section 10: Routing & Navigation
| # | Question |
|---|----------|
| Q137 | [How does client-side routing work?](#q137-how-does-client-side-routing-work) |
| Q138 | [What is React Router and what are its main components?](#q138-what-is-react-router-and-what-are-its-main-components) |
| Q139 | [What are nested routes in React Router v6?](#q139-what-are-nested-routes-in-react-router-v6) |
| Q140 | [What is the `Outlet` component?](#q140-what-is-the-outlet-component) |
| Q141 | [What are route loaders in React Router v6.4+?](#q141-what-are-route-loaders-in-react-router-v64) |
| Q142 | [What are route actions in React Router?](#q142-what-are-route-actions-in-react-router) |
| Q143 | [What is code splitting at the route level?](#q143-what-is-code-splitting-at-the-route-level) |
| Q144 | [How do you protect routes (auth guards)?](#q144-how-do-you-protect-routes-auth-guards) |
| Q145 | [What is the difference between `useNavigate` and `<Navigate>`?](#q145-what-is-the-difference-between-usenavigate-and-navigate) |
| Q146 | [What are search params and how do you use them?](#q146-what-are-search-params-and-how-do-you-use-them) |

### Section 11: Data Fetching & SSR / Next.js
| # | Question |
|---|----------|
| Q147 | [What are the patterns for data fetching in React?](#q147-what-are-the-patterns-for-data-fetching-in-react) |
| Q148 | [What is SWR?](#q148-what-is-swr) |
| Q149 | [What is React Query's caching model?](#q149-what-is-react-querys-caching-model) |
| Q150 | [What is optimistic mutation in React Query?](#q150-what-is-optimistic-mutation-in-react-query) |
| Q151 | [What is SSR with React?](#q151-what-is-ssr-with-react) |
| Q152 | [What is SSG (Static Site Generation)?](#q152-what-is-ssg-static-site-generation) |
| Q153 | [What is ISR (Incremental Static Regeneration)?](#q153-what-is-isr-incremental-static-regeneration) |
| Q154 | [What is the Next.js App Router?](#q154-what-is-the-nextjs-app-router) |
| Q155 | [What are Next.js `loading.js` and `error.js`?](#q155-what-are-nextjs-loadingjs-and-errorjs) |
| Q156 | [Situation: API data is needed in multiple components – how do you avoid duplicate fetches?](#q156-situation-api-data-is-needed-in-multiple-components--how-do-you-avoid-duplicate-fetches) |
| Q157 | [What is parallel vs sequential data fetching?](#q157-what-is-parallel-vs-sequential-data-fetching) |

### Section 12: Forms, Events & DOM Integration
| # | Question |
|---|----------|
| Q158 | [Controlled vs uncontrolled forms – trade-offs in practice?](#q158-controlled-vs-uncontrolled-forms--trade-offs-in-practice) |
| Q159 | [What is React Hook Form and why is it popular?](#q159-what-is-react-hook-form-and-why-is-it-popular) |
| Q160 | [What is Formik?](#q160-what-is-formik) |
| Q161 | [How do you do form validation in React without a library?](#q161-how-do-you-do-form-validation-in-react-without-a-library) |
| Q162 | [What are synthetic events?](#q162-what-are-synthetic-events) |
| Q163 | [What is event delegation in React?](#q163-what-is-event-delegation-in-react) |
| Q164 | [What happened to event pooling?](#q164-what-happened-to-event-pooling) |
| Q165 | [How do you integrate a non-React library (e.g., D3, Leaflet)?](#q165-how-do-you-integrate-a-non-react-library-eg-d3-leaflet) |
| Q166 | [What is `forwardRef`?](#q166-what-is-forwardref) |
| Q167 | [What is focus management and why does it matter?](#q167-what-is-focus-management-and-why-does-it-matter) |
| Q168 | [Situation: A dropdown closes when you click inside it – what's likely wrong?](#q168-situation-a-dropdown-closes-when-you-click-inside-it--whats-likely-wrong) |

### Section 13: TypeScript with React
| # | Question |
|---|----------|
| Q169 | [Why use TypeScript with React?](#q169-why-use-typescript-with-react) |
| Q170 | [How do you type component props with TypeScript?](#q170-how-do-you-type-component-props-with-typescript) |
| Q171 | [`React.FC` vs explicit return type – which is better?](#q171-reactfc-vs-explicit-return-type--which-is-better) |
| Q172 | [How do you type `useState` with TypeScript?](#q172-how-do-you-type-usestate-with-typescript) |
| Q173 | [How do you type `useRef`?](#q173-how-do-you-type-useref) |
| Q174 | [How do you type event handlers?](#q174-how-do-you-type-event-handlers) |
| Q175 | [How do you type `useReducer`?](#q175-how-do-you-type-usereducer) |
| Q176 | [How do you type context?](#q176-how-do-you-type-context) |
| Q177 | [What is a discriminated union and when is it useful in React?](#q177-what-is-a-discriminated-union-and-when-is-it-useful-in-react) |
| Q178 | [How do you type children in React with TypeScript?](#q178-how-do-you-type-children-in-react-with-typescript) |

### Section 14: Testing React
| # | Question |
|---|----------|
| Q179 | [What is the testing pyramid for React?](#q179-what-is-the-testing-pyramid-for-react) |
| Q180 | [What is React Testing Library?](#q180-what-is-react-testing-library) |
| Q181 | [What are the RTL query priorities?](#q181-what-are-the-rtl-query-priorities) |
| Q182 | [`getBy` vs `queryBy` vs `findBy` – when do you use each?](#q182-getby-vs-queryby-vs-findby--when-do-you-use-each) |
| Q183 | [How do you test user interactions?](#q183-how-do-you-test-user-interactions) |
| Q184 | [How do you test async behavior (e.g., API calls)?](#q184-how-do-you-test-async-behavior-eg-api-calls) |
| Q185 | [What is Mock Service Worker (MSW)?](#q185-what-is-mock-service-worker-msw) |
| Q186 | [How do you test custom hooks?](#q186-how-do-you-test-custom-hooks) |
| Q187 | [How do you test components with context?](#q187-how-do-you-test-components-with-context) |
| Q188 | [How do you test error boundaries?](#q188-how-do-you-test-error-boundaries) |
| Q189 | [What is the difference between shallow and deep rendering?](#q189-what-is-the-difference-between-shallow-and-deep-rendering) |
| Q190 | [What is Vitest and how does it differ from Jest?](#q190-what-is-vitest-and-how-does-it-differ-from-jest) |

### Section 15: Accessibility (a11y) in React
| # | Question |
|---|----------|
| Q191 | [Why does accessibility matter in React apps?](#q191-why-does-accessibility-matter-in-react-apps) |
| Q192 | [What are ARIA roles and attributes?](#q192-what-are-aria-roles-and-attributes) |
| Q193 | [How do you manage focus after navigation in a SPA?](#q193-how-do-you-manage-focus-after-navigation-in-a-spa) |
| Q194 | [What is a focus trap?](#q194-what-is-a-focus-trap) |
| Q195 | [How do you handle keyboard navigation in custom components?](#q195-how-do-you-handle-keyboard-navigation-in-custom-components) |
| Q196 | [What tools help check React app accessibility?](#q196-what-tools-help-check-react-app-accessibility) |
| Q197 | [What is a skip link?](#q197-what-is-a-skip-link) |

### Section 16: Security in React
| # | Question |
|---|----------|
| Q198 | [How does React prevent XSS by default?](#q198-how-does-react-prevent-xss-by-default) |
| Q199 | [What is `dangerouslySetInnerHTML` and why is it dangerous?](#q199-what-is-dangerouslysetinnerhtml-and-why-is-it-dangerous) |
| Q200 | [What is a CSRF attack and how do you prevent it in React apps?](#q200-what-is-a-csrf-attack-and-how-do-you-prevent-it-in-react-apps) |
| Q201 | [What is a CORS issue and how do you handle it?](#q201-what-is-a-cors-issue-and-how-do-you-handle-it) |
| Q202 | [How do you securely store auth tokens in a React app?](#q202-how-do-you-securely-store-auth-tokens-in-a-react-app) |
| Q203 | [What environment variables are safe to expose in a React app?](#q203-what-environment-variables-are-safe-to-expose-in-a-react-app) |

### Section 17: Build, Tooling & Ecosystem
| # | Question |
|---|----------|
| Q204 | [What is Vite and why is it preferred over CRA?](#q204-what-is-vite-and-why-is-it-preferred-over-cra) |
| Q205 | [What is the role of Babel in a React project?](#q205-what-is-the-role-of-babel-in-a-react-project) |
| Q206 | [What is HMR (Hot Module Replacement)?](#q206-what-is-hmr-hot-module-replacement) |
| Q207 | [What is the purpose of ESLint and Prettier in a React project?](#q207-what-is-the-purpose-of-eslint-and-prettier-in-a-react-project) |
| Q208 | [What is the `eslint-plugin-react-hooks` plugin?](#q208-what-is-the-eslint-plugin-react-hooks-plugin) |
| Q209 | [What is Storybook?](#q209-what-is-storybook) |
| Q210 | [What is a monorepo and how does it relate to React projects?](#q210-what-is-a-monorepo-and-how-does-it-relate-to-react-projects) |
| Q211 | [What is bundle analysis and how do you do it?](#q211-what-is-bundle-analysis-and-how-do-you-do-it) |

### Section 18: Senior-Level Scenario Questions
| # | Question |
|---|----------|
| Q212 | [Design a real-time chat UI in React.](#q212-design-a-real-time-chat-ui-in-react) |
| Q213 | [How would you migrate a large class-based codebase to hooks?](#q213-how-would-you-migrate-a-large-class-based-codebase-to-hooks) |
| Q214 | [Design a form wizard with multiple steps in React.](#q214-design-a-form-wizard-with-multiple-steps-in-react) |
| Q215 | [How would you implement infinite scroll?](#q215-how-would-you-implement-infinite-scroll) |
| Q216 | [How would you build a drag-and-drop kanban board?](#q216-how-would-you-build-a-drag-and-drop-kanban-board) |
| Q217 | [How would you architect a React app for a team of 20 developers?](#q217-how-would-you-architect-a-react-app-for-a-team-of-20-developers) |
| Q218 | [Situation: The app is slow on mobile – how do you diagnose and fix it?](#q218-situation-the-app-is-slow-on-mobile--how-do-you-diagnose-and-fix-it) |
| Q219 | [How would you implement role-based access control (RBAC) in React?](#q219-how-would-you-implement-role-based-access-control-rbac-in-react) |
| Q220 | [How would you handle real-time data updates (live prices, scores)?](#q220-how-would-you-handle-real-time-data-updates-live-prices-scores) |
| Q221 | [How do you implement a feature flag system?](#q221-how-do-you-implement-a-feature-flag-system) |
| Q222 | [Situation: A critical bug is in production – what's your process?](#q222-situation-a-critical-bug-is-in-production--whats-your-process) |
| Q223 | [How would you implement internationalization (i18n) in React?](#q223-how-would-you-implement-internationalization-i18n-in-react) |
| Q224 | [How do you ensure a React app performs well at 100k users?](#q224-how-do-you-ensure-a-react-app-performs-well-at-100k-users) |
| Q225 | [How would you design a design system in React?](#q225-how-would-you-design-a-design-system-in-react) |

---

## Section 1: Fundamentals & JSX

*Core concepts every React developer must know cold.*

---

#### Q1. What is React and what problem does it solve?

React is a JavaScript library by Meta for building UIs using a declarative, component-based model. It solves the complexity of keeping the UI in sync with application state by reacting to state changes automatically and efficiently updating the DOM.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q2. How is React different from Angular or Vue?

React is a view library (handles only UI); Angular is a full framework with DI, routing, forms built-in; Vue sits in between. React uses JSX + JS composition, Angular uses TypeScript + decorators + templates, Vue uses SFC (Single File Components).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q3. What is JSX and why does React use it?

JSX is a syntax extension allowing HTML-like markup inside JS. At build time it compiles to `React.createElement()` calls. It improves readability, catches errors earlier via the compiler, and makes component trees visually clear.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q4. What does JSX compile to?

JSX compiles to `React.createElement(type, props, ...children)` in React <17, and to the automatic `jsx()` runtime in React 17+. Both produce plain JavaScript objects (React elements) describing the UI.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q5. Can you use React without JSX?

Yes. `React.createElement('div', {className:'box'}, 'Hello')` is valid but verbose. JSX is purely syntactic sugar; the output is identical JS objects.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q6. What is the Virtual DOM?

An in-memory lightweight JS tree that mirrors the real DOM. React renders to the virtual DOM first, diffs two versions (reconciliation), and applies only the minimal set of real DOM mutations needed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q7. How does the Virtual DOM improve performance?

Real DOM mutations are expensive (layout, paint, composite). React batches changes and applies minimal updates. The diffing algorithm is O(n) using heuristics (same type → update; different type → destroy and replace).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q8. What are React elements vs React components?

React Elements (The Lego Brick)
An element is a single, plain blueprint of what you want to see on the screen. It doesn't actually do anything yet; it’s just a simple JavaScript object that describes a piece of the UI.

Analogy: A single Lego block or a sketch of a window.

What it looks like: { type: 'div', props: { className: 'box', children: 'Hello' } }

React Components (The Factory / Blueprint)
A component is the factory, function, or template that creates those elements. It takes in some data (called props) and outputs React elements.

Analogy: The master blueprint or the factory mold that can stamp out hundreds of Lego blocks.

What it looks like: A JavaScript function like function Button() { return <button /> }.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q9. What is `createRoot()` and why was it introduced in React 18?

`createRoot()` replaces `ReactDOM.render()`. It opts the app into React 18's concurrent features (automatic batching, `startTransition`, Suspense improvements). `ReactDOM.render()` runs in legacy mode without those features.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q10. What are pure components?

Components that produce the same output for the same props/state. `React.PureComponent` (class) and `React.memo` (function) implement shallow-equality checks to skip redundant renders.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q11. What is the difference between an element and a component instance?

An element is a description object (`{type, props}`). An instance is the internal object React creates for class components to hold state and lifecycle. Functional components have no instance; hooks store state in React's fiber node instead.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q12. What does 'declarative' mean in React?

You describe what the UI should look like for a given state. React figures out how to make the DOM match. Imperative code would manually manipulate the DOM step by step; declarative code just re-renders with new state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q13. What is the React DevTools and what can you do with it?

A browser extension that lets you inspect the component tree, view props/state/context, highlight re-renders, and use the Profiler to record timing and flame graphs of render performance.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q14. What are the rules of JSX?

Must return a single root element (or Fragment); all tags must be closed; attributes use camelCase (`className`, `onClick`, `htmlFor`); JS expressions go inside `{}`; cannot use reserved words like 'class' or 'for'.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q15. What is a React SPA and what are its trade-offs?

Think of a React SPA (Single Page Application) like a modern video game rather than a traditional book.

Instead of turning to a completely new physical page every time you click a link (which causes the browser to reload and flash white), a SPA loads one single blank page at the very beginning. Then, it uses JavaScript to dynamically erase old content and snap new content into place instantly.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 2: Components, Props & State

*The building blocks of every React application.*

---

#### Q16. What is a React component?

A reusable, self-contained piece of UI. It's a function (or class) that accepts props and returns React elements. Components can be composed together to build complex UIs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q17. Functional vs class components – key differences?

Functional: plain JS functions, use hooks for state/lifecycle, simpler, preferred since React 16.8. Class: extend `React.Component`, use `this.state` and lifecycle methods, support error boundaries natively. New code should use functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q18. What are props?

Read-only inputs passed from parent to child. Props flow downward (one-way data flow). Mutating props directly is forbidden; instead lift state or use callbacks.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q19. How do you pass data child → parent?

Pass a callback function as a prop. The child calls it with data, the parent receives it in the handler and updates its state. This maintains one-way data flow while still communicating upward.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q20. What is prop drilling and why is it a problem?

Passing props through many intermediate components that don't use them just to reach a deep child. It creates tight coupling and makes refactoring hard. Solved by Context, state management libraries, or component composition.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q21. What is state in React?

Mutable data owned by a component. When state changes, React schedules a re-render. State is private to the component unless shared via props or context. `useState` / `useReducer` manage it in functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q22. What is the difference between props and state?

Props are external, immutable (from parent). State is internal, mutable (managed by the component). Props configure a component; state tracks what changes over time inside it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q23. Why is state update asynchronous?

React batches state updates for performance. `setState()` / the setter from `useState()` schedules a re-render rather than immediately mutating state. Reading state right after calling the setter still returns the old value within the same event handler.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q24. What is lifting state up?

Moving shared state to the nearest common ancestor of components that need it, then passing it down via props and up via callbacks. This keeps state as the single source of truth.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q25. What is the `key` prop and why is it important?

A special string or number that uniquely identifies a list item. React uses keys to match items between renders for efficient reconciliation. Wrong or missing keys cause incorrect DOM reuse and subtle bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q26. Why avoid array index as key?

When items are reordered, inserted, or deleted, index-based keys cause React to reuse DOM nodes incorrectly. Use stable unique IDs (DB id, UUID) instead.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q27. Controlled vs uncontrolled components?

Controlled Components (The Micromanaged Employee)
A controlled component is completely managed by React. React keeps track of every single keystroke in its internal memory (state).

Analogy: A boss who asks for an update every time an employee writes a single sentence.

How it works: When you type into an input box, it triggers an onChange event. React updates its state with the new letter, and then React tells the input box to display that new state.

Why use it? Because React knows exactly what is in the box at all times, you can easily do things like disable a "Submit" button until an email address is formatted correctly, or force all text to be uppercase as the user types.

Uncontrolled Components (The Independent Worker)
An uncontrolled component is left to manage itself. The browser (DOM) keeps track of what is typed in the box, just like a traditional HTML website.

Analogy: A suggestion box. You don't monitor people as they write their suggestions; you just use a key to open the box and read whatever is inside only when you actually need it.

How it works: You don't bother saving every keystroke to React's state. Instead, you attach a ref (a reference) to the input. When the user finally clicks "Submit", React uses that ref to reach into the DOM and pull the final value out.

Why use it? It requires less code to set up. It’s great for very simple forms where you don't need instant validation while the user is typing.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q28. What are fragments?

Syntax for returning multiple elements without an extra DOM node: `<> </>` or `<React.Fragment>`. Keyed fragments use the long form: `<React.Fragment key={id}>`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q29. What are portals?

A React Portal is like a teleportation device for your UI. It lets you write the code for a component inside a parent, but physically display it somewhere else on the page (usually floating over the whole screen).

Use it for: Popups, modals, and tooltips so they don't get cut off or trapped by their parent container's layout rules.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q30. What are default props and PropTypes?

defaultProps (The Backup Plan)
This provides a fallback value just in case a parent component forgets to pass a prop.

Analogy: If you don't explicitly choose a side dish, the restaurant automatically defaults to giving you fries.

PropTypes (The Bouncer)
This checks the props coming in to make sure they are the correct type (like a number, a string, or a boolean) and warns you in the developer console if someone made a mistake.

Analogy: A bouncer checking IDs. If a developer tries to pass the word "Twenty" into an age prop that expects the actual number 20, PropTypes throws a warning flag.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q31. What is the children prop?

When you build a reusable component, you don't always know exactly what content will go inside it. The children prop is a special built-in placeholder that tells React, "Take whatever the developer types between my opening and closing tags, and display it right here."
```
function PictureFrame(props) {
  return (
    <div className="thick-wooden-border">
      {/* React will drop the content right here */}
      {props.children} 
    </div>
  );
}
```
```
<PictureFrame>
  <h1>My Summer Vacation</h1>
  <img src="beach.jpg" alt="The Beach" />
</PictureFrame>
```
In this example, both the <h1> and the <img> are automatically bundled together and passed into PictureFrame as props.children.
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q32. When should a component be split into smaller components?

When it exceeds ~150 lines, has distinct logical sections, when part of it needs to be reused, or when different parts change at different frequencies. Each component should have a single clear responsibility.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q33. What is the difference between element and component re-render?

Elements are plain objects; React creates/updates them every render cheaply. A component re-renders when its state or props change, executing the function body again. Only DOM nodes actually affected get updated in the real DOM.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q34. What are presentational vs container components?

Presentational: concern is how things look, receive data via props, rarely have own state. Container: concern is how things work, handle data fetching and state, pass data to presentational children. The pattern is less strict now that hooks exist.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q35. What happens if you mutate state directly?

React does not detect the change and won't re-render. Always return new references: `setState([...arr])` or `setState({...obj})`. Direct mutation causes stale UI and hard-to-debug bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 3: Rendering, Reconciliation & Lifecycle

*Understanding how React decides what to render and when.*

---

#### Q36. What is reconciliation?

The process of diffing the new React element tree against the previous one to compute minimal DOM mutations. React uses two heuristics: same type → update props; different type → unmount old, mount new. Keys help reconcile lists.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q37. How does React's diffing algorithm work (O(n))?

React compares trees level by level. If root elements differ in type, it destroys the old tree. For same-type DOM elements it updates only changed attributes. For same-type components it updates props and re-renders. Keys enable efficient list diffing.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q38. What is React Fiber?

The Problem (Old React)
Before Fiber, when React started updating the screen, it had to finish the entire job in one single blast without stopping. If it was a massive update (like rendering a huge list), the browser would freeze. If a user tried to click a button or type during that freeze, the app felt broken and laggy.

The Solution (React Fiber)
Fiber changes the way React works by breaking the massive update job into tiny, bite-sized tasks.

Because the work is split up, React gains three superpowers:

Pause & Resume: It can do a little bit of work, pause to let the browser breathe, and then pick up right where it left off.

Prioritize: If a user clicks a button while React is busy rendering a hidden menu, React will pause the menu, handle the button click immediately (high priority), and then go back to the menu.

Abort: If you switch pages mid-load, React can instantly throw away the half-finished work of the old page instead of wasting time finishing it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q39. What are the three main lifecycle phases?

Mounting (component added to DOM), Updating (props/state change → re-render), Unmounting (component removed from DOM). Class components have explicit methods; hooks model these via `useEffect`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q40. Map class lifecycle methods to hooks.

- `componentDidMount` → `useEffect(() => {...}, [])`
- `componentDidUpdate` → `useEffect(() => {...}, [dep])`
- `componentWillUnmount` → cleanup function returned from `useEffect`
- `getDerivedStateFromProps` → compute derived state inline or in `useMemo`

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q41. What is the order of hook execution in a component?

Hooks run top-to-bottom on every render in the same order. React relies on call order to associate hook state with the correct hook – this is why hooks cannot be inside conditionals or loops.
Think of React hooks like a numbered seating chart at a wedding.

React doesn't remember your hooks by their actual names; it only tracks them by the exact order (seat number) they appear in your code.

How it Works
Render 1: React notes that Seat 1 is a useState for a username, and Seat 2 is a useEffect for fetching data.

Render 2: React expects the exact same setup. It goes to Seat 1, grabs the username state, goes to Seat 2, and runs the effect.

Why Hooks Can't Be in if Statements or Loops
If you hide a hook inside an if condition, and that condition turns false, that hook doesn't run.

The Disaster: The hook in Seat 2 disappears. The hook that used to be in Seat 3 slides over into Seat 2. React gets totally confused and hands the wrong data to the wrong hook, crashing your app.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q42. What causes unnecessary re-renders?

New object/array/function references created inline in JSX; context value changing; parent re-rendering; global state updates. Fix: memoize with `React.memo`, `useMemo`, `useCallback`, or restructure state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q43. What is hydration?

Attaching React's event handlers and internal state to server-rendered HTML without re-rendering it. React expects the client-side output to exactly match server HTML; mismatches cause warnings or errors.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q44. What causes hydration mismatches and how do you fix them?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q45. What is Strict Mode?

Think of React Strict Mode like a stress tester or a spellcheck for your code.

It is a special wrapper tool (<React.StrictMode>) you place around your app. It doesn't show anything on the screen itself, but it activates extra checks behind the scenes.

The Secret Weapon: The "Double Run"
In development, Strict Mode will deliberately run your components, state updates, and useEffect hooks twice every time they load.

Why does it do this? Good React code should be predictable. Running a component twice should produce the exact same result. If running your code a second time suddenly breaks a feature, causes a visual glitch, or leaves a background timer running, Strict Mode has successfully exposed a hidden bug (called a "side effect") before it reaches your users.

Warning System: It also watches your code and prints warning messages in the browser console if you are using old, outdated React features that will break in future updates.

⚠️ The Golden Rule
Strict Mode only works in development. When you publish your app to the live internet (production), React automatically turns off all the double-running and warnings so your live website runs at 100% full speed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q46. What is `getDerivedStateFromProps` and when would you use it?

A static class lifecycle that returns new state derived from props before every render. Rarely needed; usually derived state should be computed during render or via `useMemo`. Overuse leads to confusing state synchronization bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q47. What is `getSnapshotBeforeUpdate`?

A class lifecycle called right before the DOM is updated. Its return value is passed as 'snapshot' to `componentDidUpdate`. Used for reading scroll position or other DOM measurements before a commit.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q48. Explain the commit phase vs render phase.

Render phase: React calls component functions, runs reconciliation – pure, may be paused/aborted. Commit phase: React applies DOM mutations, runs layout effects (`useLayoutEffect`), then passive effects (`useEffect`) – cannot be interrupted.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q49. What happens when a parent re-renders?

All child components re-render by default unless wrapped in `React.memo` or the subtree is stable. Re-rendering means the function runs again; it does not mean the DOM changes – React still diffs before touching the DOM.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q50. What is `shouldComponentUpdate` and its functional equivalent?

`shouldComponentUpdate` returns boolean to control re-rendering in class components. The functional equivalent is `React.memo` (shallow comparison) or a custom comparator passed as its second argument.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 4: Core Hooks

*Mastering the hooks that power modern React.*

---

#### Q51. What is `useState`?

Declares state in a functional component. Returns `[value, setter]`. The setter schedules a re-render with the new value. Multiple `useState` calls are independent.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q52. Why use functional updates with `useState`?

`setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q53. What is lazy initialization in `useState`?

`useState(() => expensiveCalc())` passes a function so the initial value is computed only once (on mount), not on every render. Useful for reading from `localStorage` or parsing data.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q54. What is `useEffect`?

Runs side effects after render (data fetching, subscriptions, DOM manipulation). Dependency array controls when it runs: `[]` → once on mount; `[a,b]` → when a or b changes; omitted → every render.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q55. What is the `useEffect` cleanup function?

Return a function from `useEffect` to run cleanup before the next effect or on unmount. Used to clear timers, cancel fetch, unsubscribe from observables, or remove event listeners.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q56. What are stale closures in `useEffect`?

When an effect captures a variable from a previous render. If the dependency array is incomplete, the effect uses the old value. Fix: add the variable to deps, or use a ref to always access the latest value.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q57. What is `useRef`?

Returns a mutable `{current}` object that persists across renders without triggering re-renders. Two main uses: (1) accessing DOM nodes directly, (2) storing instance variables like timers or previous values.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q58. How does `useRef` differ from a regular variable?

Regular variables reset on every render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for functional components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q59. What is `useContext`?

Subscribes to a React context. Receives the current context value and re-renders whenever it changes. Eliminates prop drilling for shared data like theme, locale, auth, or feature flags.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q60. What is `useReducer`?

Like `useState` but manages state via a `reducer(state, action) => newState` function. Better for complex state with multiple sub-values, or when next state depends on action type. Pairs well with `useContext` for mini-Redux patterns.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q61. What is `useMemo`?

Memoizes the result of an expensive computation. Re-computes only when dependencies change. Use for: heavy calculations, creating stable object/array references, derived data from props.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q62. What is `useCallback`?

Memoizes a function reference. Prevents child components that receive the function as prop from re-rendering unnecessarily, and prevents effects from re-running when a callback is a dependency.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q63. `useMemo` vs `useCallback` – what's the difference?

`useMemo(() => fn(), deps)` memoizes the return value of `fn`. `useCallback(fn, deps)` memoizes `fn` itself. `useCallback(fn, deps) === useMemo(() => fn, deps)`. Choose `useMemo` for values, `useCallback` for functions.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q64. What is `useLayoutEffect`?

Same signature as `useEffect` but fires synchronously after DOM mutations and before browser paint. Use for: reading layout (scroll position, dimensions) and synchronously updating the DOM to avoid flicker.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q65. What is `useImperativeHandle`?

Customizes the ref value exposed when `forwardRef` is used. Lets a parent call specific methods on a child (e.g., `child.focus()`) without exposing the entire DOM node or component internals.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q66. What are the Rules of Hooks?

1. Only call hooks at the top level – not inside conditions, loops, or nested functions.
2. Only call hooks from React function components or custom hooks.

These rules ensure hooks are called in the same order every render.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q67. How do you create a custom hook?

A function whose name starts with 'use' that calls other hooks. It extracts and reuses stateful logic without changing component hierarchy. E.g., `useWindowSize()`, `useFetch()`, `useDebounce()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q68. What is `useId`?

Generates a stable, unique ID that is consistent between server and client renders. Use for accessibility attributes like `aria-labelledby` or `htmlFor` where IDs must match across SSR and hydration.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q69. What is `useDebugValue`?

Used inside custom hooks to display a label in React DevTools. Helps identify what a custom hook is doing when inspecting components. The second argument is a formatting function called only in DevTools.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q70. Situation: `useEffect` runs infinitely – what's wrong?

Most likely a dependency that changes on every render: an object/array created inline (`{} !== {}` every render), or a function without `useCallback`. Fix: memoize the dependency, move it outside the component, or restructure state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 5: Advanced Hooks & Performance

*Optimizing React apps for real-world scale.*

---

#### Q71. What is `React.memo`?

A HOC that wraps a functional component. On re-render of the parent, React shallowly compares old and new props; if equal, it skips re-rendering the child. Accepts a custom comparator as second argument.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q72. When does `React.memo` NOT help?

When props include new object/function references on every parent render (must pair with `useMemo`/`useCallback`). When the component is cheap to render (overhead of comparison > render cost). When props always change.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q73. How do you avoid unnecessary object/function recreation?

Declare stable values outside the component when possible, use `useMemo` for objects/arrays, `useCallback` for functions, and avoid inline object literals as prop values in JSX.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q74. What is windowing/virtualization and when do you need it?

Rendering only visible list items in a large dataset instead of all of them. Libraries: `react-window`, `react-virtual`, `TanStack Virtual`. Use when rendering 1000+ items causes frame drops or memory pressure.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q75. What is code splitting?

Splitting the JS bundle into smaller chunks loaded on demand. `React.lazy` + `Suspense` enable component-level splitting. Route-level splitting is most impactful (each route loads only its JS).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q76. What is `React.lazy` and how does it work?

`React.lazy(() => import('./Comp'))` creates a lazy-loaded component. React suspends rendering until the chunk loads, showing the nearest `Suspense` fallback. Only works with default exports.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q77. What is the Profiler API?

`React.Profiler` wraps a tree and calls `onRender(id, phase, actualDuration, ...)` after each commit. Used to programmatically measure render performance in development. React DevTools Profiler wraps this in a UI.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q78. How do you measure and fix excessive re-renders?

Use React DevTools 'Highlight Updates' to spot components re-rendering. Record a Profiler session to see flame charts. Then: add `React.memo`, split context, move state closer to usage, or batch updates.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q79. What is the `useTransition` hook for performance?

Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q80. What is `useDeferredValue`?

Accepts a value and returns a deferred copy that trails behind during heavy renders. UI stays responsive with the current value while React concurrently renders the expensive output with the new value.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q81. Situation: A search input lags as user types – how do you fix it?

Separate the input state (urgent) from the search results state (deferred). Use `useDeferredValue` or `useTransition` on the results update. This lets the input remain responsive while results compute asynchronously.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q82. What is tree shaking?

Bundlers (webpack, Rollup, Vite) remove unused exports from the final bundle using static analysis of import/export. Use named exports and avoid side-effectful imports to enable effective tree shaking.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q83. What are common React performance pitfalls?

Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q84. What is the 'why did you render' library?

A development utility that patches React to notify you when a component re-renders due to reference-equal props/state. Helps find components where `React.memo` or `useMemo` would be beneficial.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q85. What is the difference between optimistic and pessimistic updates?

Optimistic: update UI immediately assuming success, roll back on error (fast UX). Pessimistic: wait for server confirmation before updating UI (safe, may feel slow). React 19 has `useOptimistic` for the optimistic pattern.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 6: Context & State Management

*Managing state at every scale.*

---

#### Q86. What is the Context API?

A built-in React mechanism for sharing values across the component tree without prop drilling. Three parts: `React.createContext()` (creates context), `Provider` (supplies value), `useContext()` (consumes value).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q87. Context re-render behavior – what should you know?

Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q88. When should you NOT use Context for state?

For frequently changing data (e.g., mouse position, animation frames), because every consumer re-renders. Use a dedicated state library with selectors (Zustand, Jotai, Redux) for fine-grained subscriptions.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q89. Context vs Redux – when to choose which?

Context: simple, low-frequency shared state (theme, auth, locale). Redux: complex update logic, middleware (logging, side effects), time-travel debugging, large team codebases, or when you need strict action-based mutations.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q90. What is Zustand and how does it differ from Redux?

Zustand is a minimal state library using hooks. No boilerplate, no reducers/actions required. Stores are plain JS objects with setter functions. Components subscribe to specific slices to avoid unnecessary re-renders.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q91. What is Jotai and how does the atomic model work?

Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q92. What is server state vs client state?

Server state: data from APIs (users, posts) – needs caching, refetching, synchronization, background updates. Client state: local UI state (modal open, form values) – synchronous, lives only in the browser.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q93. What is React Query (TanStack Query)?

A library for fetching, caching, synchronizing, and updating server state. Provides `useQuery` (fetch), `useMutation` (create/update/delete), automatic background refetching, cache invalidation, and stale-while-revalidate.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q94. Situation: Two components on different branches need the same data – what do you do?

Options: (1) Lift state to nearest common ancestor. (2) Put it in Context. (3) Use a global state store. (4) If server data, use React Query – both components call the same `useQuery` key and share a cache automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q95. What is the Redux Toolkit (RTK)?

The official, recommended way to write Redux. Reduces boilerplate with `createSlice` (combines actions + reducers), `configureStore`, and RTK Query (built-in data fetching/caching layer).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q96. What is the `useSelector` / `useDispatch` pattern in Redux?

useSelector is for reading data. It lets your component "grab" a specific piece of state from the global Redux store
useDispatch is for changing data. It gives you a dispatch function. You use this function to send "actions" (requests) to the Redux store telling it to update the data.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q97. Situation: Context is causing performance issues in a large app – what do you do?

Split into multiple smaller contexts by concern. Memoize provider values. Move high-frequency state to a store with selectors (Zustand, Jotai). Use context only for rarely-changing values.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q98. What is the flux architecture pattern?

Unidirectional data flow: Action → Dispatcher → Store → View → (user interaction) → Action. Redux is inspired by Flux. Data always flows one way, making state changes predictable and traceable.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 7: Component Patterns & Architecture

*Patterns that make React code reusable, scalable, and maintainable.*

---

#### Q99. What are Higher-Order Components (HOCs)?

Functions that take a component and return a new component with enhanced behavior. E.g., `withAuth(Component)` wraps it to redirect if unauthenticated. HOCs are less common now that custom hooks exist.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q100. What is the render props pattern?

The Render Props pattern is a way to share a specific behavior or piece of data between components by using a function as a prop.

[⬆ Back to Table of Contents](#-table-of-contents) 

---

#### Q101. What are compound components?

Compound Components are a group of components that work together as a team to handle one big job, sharing a hidden brain behind the scenes. E.g., `<Select>`, `<Select.Option>`, `<Select.Trigger>`. The parent manages state; children are compositionally flexible. Used in UI libraries (Headless UI, Radix).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q102. What is the provider pattern?

A component that wraps part of the tree and supplies shared state/functionality via context. Used extensively: `ThemeProvider`, `AuthProvider`, `QueryClientProvider`. Stacking providers is common.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q103. What is the state reducer pattern?

State Reducer Pattern gives the user of your component a "veto power" or steering wheel over how the component’s internal data changes.

Instead of the component making all the rules about how its state updates, it handles the heavy lifting but passes every change through a custom function you provide. This lets you intercept and modify the changes before they actually happen.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q104. What is the controlled component pattern for reusable components?
This pattern creates a flexible component that can run on "autopilot" OR be manually "steered" by its parent.

Instead of forcing a component to be strictly controlled or strictly uncontrolled, you build it to support both modes seamlessly.
A reusable component can work in two modes: uncontrolled (manages own state) or controlled (parent provides `value` + `onChange`). Example: an `<Accordion>` that works out of the box but can also be fully controlled.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q105. Custom hooks vs HOCs vs render props – when to use each?

Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when you need to wrap a component (e.g., code splitting, legacy compatibility). Render props: when JSX composition is specifically needed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q106. How should you structure a large React application?

Feature-based folder structure (`features/auth`, `features/dashboard`). Shared UI components in `components/`. Keep business logic in hooks/services. Clear separation between UI, state, and data layers. TypeScript for safety.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q107. What is colocation in React?

Keeping related code together – state close to where it's used, styles next to components, tests next to source. Avoid premature abstraction. Move state up only when shared, not just to 'be organized'.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q108. What is the container/presenter pattern and is it still relevant?

Separating data logic (container) from UI (presenter). Less strictly followed now – hooks handle data logic inside any component. But the concept of separating concerns is still valuable, enforced by custom hooks.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q109. How do you design a reusable button component?

Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type` props. Use TypeScript to type them. Forward refs for DOM access. Avoid hardcoding styles – use class variants or a styling system. Compose with an icon slot.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q110. How do you build a reusable modal?

Use a portal to render outside the app root. Manage open state via controlled pattern. Trap focus inside for accessibility. Close on Escape key and overlay click. Accept children for flexible content.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q111. What is prop inversion of control?

Prop Inversion of Control (IoC) means a component stops bossing its pieces around and instead says to the developer using it: "You take the wheel, you decide how this part should work."

Instead of hardcoding every single behavior inside the component and adding 50 different configuration props, the component hands control back over to you.

const names = ["Alice", "Bob", "Charlie"];

<List 
  items={names} 
  renderItem={(name) => <span>👤 {name}</span>} 
/>

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q112. What are headless components?

Components that provide behavior, accessibility, and state management with no UI – consumers apply their own styles. Examples: Radix UI, Headless UI, React Aria. Powerful for design systems needing full styling control.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q113. How do you prevent prop explosion in complex components?

Use compound components instead of many boolean props. Accept a config object. Use context for deeply shared state. Separate components for different variants rather than one component with 20 props.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 8: Error Handling & Boundaries

*Making React apps resilient to failures.*

---

#### Q114. What is an error boundary?

A class component that implements `getDerivedStateFromError()` and/or `componentDidCatch()`. It catches rendering errors in its subtree and renders a fallback UI instead of crashing the whole app.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q115. How do you create an error boundary?

Class component with `static getDerivedStateFromError(error) { return {hasError:true} }` to render fallback, and `componentDidCatch(error, info)` for logging. Render fallback UI when `hasError` is true.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q116. What errors can't error boundaries catch?

Event handler errors, async code (`setTimeout`, promises), server-side rendering errors, and errors in the error boundary itself. Handle async errors with `try/catch` or `window.onerror`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q117. Is there a functional equivalent of error boundaries?

Not built-in to React as of React 18. `react-error-boundary` library provides a functional wrapper. React 19 is expected to improve this. You must use a class component or a wrapper library.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q118. What is the `react-error-boundary` library?

Provides `<ErrorBoundary fallback={...}>` and `<ErrorBoundary FallbackComponent={...}>`. Also provides `useErrorBoundary()` hook to imperatively throw errors into the nearest boundary and reset it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q119. Situation: A third-party component throws – how do you handle it?

Wrap it in an error boundary. Log errors in `componentDidCatch` to a monitoring service (Sentry, Datadog). Show a friendly fallback. Optionally provide a 'Try Again' button that resets the boundary state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q120. How do you handle errors in `useEffect`?

Wrap async calls in `try/catch` inside the effect. Update an error state and render error UI. For network errors, consider retry logic (react-query handles this automatically with its error/retry API).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q121. What is global error monitoring in React apps?

Pair error boundaries with a monitoring SDK (Sentry, LogRocket). Use `window.onerror` and `window.onunhandledrejection` for uncaught async errors. Error boundaries call `componentDidCatch` which logs to the service.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 9: React 18, 19 & Concurrency

*The cutting edge of React's capabilities.*

---

#### Q122. What is concurrent rendering?

React can work on multiple UI versions simultaneously, pausing, aborting, or resuming renders based on priority. Urgent updates (typing) interrupt non-urgent ones (data rendering). Enabled by `createRoot()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q123. What is automatic batching in React 18?

React 18 batches multiple `setState` calls in async contexts (`setTimeout`, Promises, native event handlers) into one re-render. Previously, only synchronous event handlers were batched. Reduces render count.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q124. What is `startTransition`?

Marks a state update as non-urgent. React processes urgent updates first and defers the transition. If a newer transition comes in, the in-progress one is aborted. Used for navigation, search, filtering.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q125. What is `useTransition`?

Hook version of `startTransition`. Returns `[isPending, startTransition]`. `isPending` is true while the transition is rendering. Use it to show loading spinners without setting separate loading state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q126. What is `useDeferredValue`?

Defers updating a value until after more urgent renders complete. Useful when you receive a value you can't control (e.g., from a prop) but want to defer expensive computation based on it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q127. What is Suspense?

A component that shows a fallback while children are 'suspended'. Components suspend by throwing a Promise. React catches it, shows the fallback, and retries when the Promise resolves. Used with `lazy()` and data-fetching libraries.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q128. What is streaming SSR?

Sending HTML to the browser in chunks as components finish rendering on the server. Parts of the page become interactive progressively. React 18's `renderToPipeableStream` / `renderToReadableStream` enable this.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q129. What are React Server Components (RSC)?

Components that run only on the server. They can directly access databases, file systems, and APIs. Their code never ships to the client. They cannot use hooks or browser APIs. They interleave with Client Components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q130. RSC vs SSR – what's the difference?

SSR renders components on the server to HTML and then hydrates on the client (components run on both). RSC components run ONLY on the server, never hydrate, and can be async. They reduce client bundle size significantly.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q131. What is the 'use client' directive?

Placed at the top of a file to mark it and its imports as Client Components in the RSC architecture. Required for any component using hooks, event handlers, or browser APIs when using Next.js App Router.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q132. What are React 19 Actions?

Functions that handle async mutations (form submissions, data updates). They can be synchronous or async. React 19 provides `useActionState`, `useFormStatus`, and `useOptimistic` to manage their state automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q133. What is `useActionState` (React 19)?

Manages state for an async action. Returns `[state, dispatch, isPending]`. On form submission, calls the action with form data, updates state with the result, and tracks pending status automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q134. What is `useOptimistic` (React 19)?

Shows an optimistic state update immediately while an async action is pending. When the action completes (or fails), React reverts to the actual state. Provides smooth UX without complex manual state management.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q135. What is `useFormStatus`?

A hook available inside a form child component. Returns `{pending, data, method, action}` of the parent form's submission. Lets you disable inputs or show spinners without prop drilling from the form.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q136. Situation: You need to keep the UI responsive during a heavy filter operation on 10k items – how?

Store the raw list. Put the filter input update in urgent state. Wrap the filtered results computation in `useTransition` or `useDeferredValue`. React renders the input update immediately; filter results follow when resources free up.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 10: Routing & Navigation

*Building navigable, URL-driven React applications.*

---

#### Q137. How does client-side routing work?

A router library (React Router, TanStack Router) listens to the browser history API (`pushState`, `popstate`) and renders different components based on the current URL – without full page reloads.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q138. What is React Router and what are its main components?

`<BrowserRouter>` or `<RouterProvider>`: wraps the app. `<Routes>`/`<Route>`: declare URL → component mappings. `<Link>`: navigation without reload. `useNavigate()`, `useParams()`, `useSearchParams()`, `useLocation()`: hooks for router state.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q139. What are nested routes in React Router v6?

Child `<Route>` elements inside a parent `<Route>`. The parent renders an `<Outlet/>` where child content appears. Enables layouts where outer shell (nav, sidebar) persists and inner content changes with URL.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q140. What is the `Outlet` component?

A placeholder rendered by a parent route where its matching child route's element is shown. Enables nested layouts. Multiple outlets can be named for parallel rendering in advanced scenarios.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q141. What are route loaders in React Router v6.4+?

Functions defined on routes that fetch data before the component renders. The component receives data via `useLoaderData()`. Eliminates loading spinners inside components – data is ready before render.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q142. What are route actions in React Router?

Functions that handle form submissions and mutations on a route. Called when a Form is submitted to that route. Work with React Router's data APIs for full progressive enhancement.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q143. What is code splitting at the route level?

Use `React.lazy()` for each route's component wrapped in `Suspense`. Only the JS for the current route loads initially. Subsequent routes load their chunk on demand – dramatically reduces initial bundle size.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q144. How do you protect routes (auth guards)?

In the loader, check auth status and redirect if not authenticated. Or create a `RequireAuth` wrapper component that checks auth state and renders `<Navigate to='/login'/>` if not authenticated.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q145. What is the difference between `useNavigate` and `<Navigate>`?

`useNavigate()` returns an imperative function for programmatic navigation (after form submit, in event handlers). `<Navigate>` is a component that redirects declaratively as part of JSX render output.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q146. What are search params and how do you use them?

URL query string parameters (`?tab=settings&page=2`). `useSearchParams()` returns `[searchParams, setSearchParams]`. Use as UI state (tab, filter, page) so users can share/bookmark specific views.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 11: Data Fetching & SSR / Next.js

*Getting data into React apps efficiently.*

---

#### Q147. What are the patterns for data fetching in React?

1. `useEffect` + fetch (basic)
2. Custom `useFetch` hook
3. React Query / SWR (recommended for server state)
4. Route loaders (React Router v6.4+)
5. Server Components with async/await (Next.js App Router)

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q148. What is SWR?

Stale-While-Revalidate: a data fetching hook from Vercel. Returns cached data immediately (stale), then revalidates in the background. Simple API: `const {data, error, isLoading} = useSWR(key, fetcher)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q149. What is React Query's caching model?

Data is cached by query key. `staleTime` controls how long data is considered fresh (no background refetch). `cacheTime` controls how long unused data stays in cache. Queries refetch on window focus, reconnect, or stale threshold.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q150. What is optimistic mutation in React Query?

In `useMutation`'s `onMutate`, update the cache optimistically. In `onError`, roll back via context passed from `onMutate`. In `onSettled`, invalidate/refetch to sync with server. Provides instant UI feedback.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q151. What is SSR with React?

Rendering React components on the server to HTML strings. Improves FCP (First Contentful Paint) and SEO. Client then hydrates the HTML. Next.js handles SSR automatically with `getServerSideProps` or Server Components.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q152. What is SSG (Static Site Generation)?

Pre-rendering pages to HTML at build time. Fastest delivery via CDN. Used for content that doesn't change per request (blogs, docs, marketing). Next.js uses `getStaticProps` and `generateStaticParams`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q153. What is ISR (Incremental Static Regeneration)?

SSG with time-based revalidation. Pages are statically generated but regenerated in the background after a specified interval. Serves stale page while regenerating fresh version. Set with `revalidate` in Next.js.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q154. What is the Next.js App Router?

File-system based routing using `app/` directory with `layout.js`, `page.js`, `loading.js`, `error.js` conventions. Pages are Server Components by default. Client Components use `'use client'` directive.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q155. What are Next.js `loading.js` and `error.js`?

`loading.js`: automatically wraps the page in Suspense – shown while the page is loading. `error.js`: an error boundary for the route – shown when the page throws. They are React components with special Next.js behavior.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q156. Situation: API data is needed in multiple components – how do you avoid duplicate fetches?

Use React Query – same query key deduplicates concurrent requests. Or fetch at a high level (loader, server component) and pass data down. Avoid fetching the same data in sibling components independently.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q157. What is parallel vs sequential data fetching?

Sequential: `await A`, then `await B` – total time = A + B. Parallel: `await Promise.all([A,B])` – total time = max(A,B). In Server Components, initiate fetches without awaiting them first, then await together.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 12: Forms, Events & DOM Integration

*Handling user input and DOM interactions correctly.*

---

#### Q158. Controlled vs uncontrolled forms – trade-offs in practice?

Controlled: every keystroke updates state → always have current value for validation, but can cause re-renders. Uncontrolled with ref: only read on submit → fewer renders, but can't do real-time validation easily.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q159. What is React Hook Form and why is it popular?

Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood – minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q160. What is Formik?

A form library providing values, errors, touched state, and handlers. Uses controlled components. Simpler API for moderate forms. Yup integration for schema validation. Slower than React Hook Form for large forms.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q161. How do you do form validation in React without a library?

Track values and errors in state. Validate in `onChange` (real-time) or `onBlur` (on leave) or `onSubmit`. Set error messages in state and display them. For complex forms, a library is usually worth the dependency.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q162. What are synthetic events?

React wraps native browser events in `SyntheticEvent`, providing a consistent cross-browser API. Event properties (`target`, `value`, `preventDefault`, `stopPropagation`) work identically across browsers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q163. What is event delegation in React?

React attaches a single event listener at the root DOM node and routes events to the correct handler using its internal fiber tree. Efficient: one listener handles all events instead of per-element listeners.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q164. What happened to event pooling?

In React 16 and earlier, `SyntheticEvent` objects were pooled and reused – accessing event properties asynchronously returned null. React 17 removed pooling. `event.persist()` is no longer needed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q165. How do you integrate a non-React library (e.g., D3, Leaflet)?

Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q166. What is `forwardRef`?

`React.forwardRef((props, ref) => ...)` passes a ref from a parent through a functional component to a DOM node or child component. Required because refs are not regular props and cannot be passed through as-is.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q167. What is focus management and why does it matter?

After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q168. Situation: A dropdown closes when you click inside it – what's likely wrong?

The click propagates to the document's mousedown handler which closes the dropdown before the button inside registers its click. Fix: call `e.stopPropagation()` on the dropdown container's mousedown, or check if click target is inside the ref.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 13: TypeScript with React

*Writing type-safe React applications.*

---

#### Q169. Why use TypeScript with React?

Catches type errors at compile time (wrong prop types, missing required props). Enables autocomplete, refactoring safety, and self-documenting component APIs. Reduces runtime bugs significantly in large codebases.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q170. How do you type component props with TypeScript?

Define an interface or type alias: `interface Props {name: string; onClick: () => void}`. Pass as generic to FC: `const Comp: React.FC<Props> = ({name, onClick}) => ...` or just define props inline: `function Comp({name}: Props)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q171. `React.FC` vs explicit return type – which is better?

Explicit: `function Comp({name}: Props): JSX.Element` is more explicit about what's returned. `React.FC<Props>` implicitly types children and return. The React team no longer recommends `React.FC` – prefer explicit typing.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q172. How do you type `useState` with TypeScript?

`useState<Type>(initialValue)`. For nullable: `useState<User | null>(null)`. TypeScript infers the type from initial value in simple cases; be explicit when the initial value doesn't reveal the full type.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q173. How do you type `useRef`?

For DOM nodes: `useRef<HTMLInputElement>(null)` – `ref.current` can be null. For mutable values: `useRef<number>(0)` – not null. Use the appropriate overload based on usage.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q174. How do you type event handlers?

`React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`. Or use inline type: `(e: React.ChangeEvent<HTMLInputElement>) => void`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q175. How do you type `useReducer`?

Define State and Action types (often a discriminated union for Action). `useReducer<Reducer<State, Action>>(reducer, initial)`. TypeScript infers dispatch type automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q176. How do you type context?

`createContext<ContextType | undefined>(undefined)`. In `useContext` wrapper hook, assert non-null or throw if context is undefined. This avoids the need to check for undefined in every consumer.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q177. What is a discriminated union and when is it useful in React?

A union type with a common literal property ('type' or 'status') that narrows the type: `type Action = {type:'increment'} | {type:'setValue', payload:number}`. TypeScript can infer the correct shape in switch/case.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q178. How do you type children in React with TypeScript?

`React.ReactNode`: anything renderable (most flexible). `React.ReactElement`: a React element only. `React.PropsWithChildren<Props>`: adds optional children to any props type. Prefer `ReactNode` for general children.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 14: Testing React

*Writing confident tests for React components.*

---

#### Q179. What is the testing pyramid for React?

Unit tests (fast, many): individual functions/hooks. Integration tests (medium): component interactions, user flows. E2E tests (slow, few): full browser flows via Playwright or Cypress. Focus effort on the middle layer.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q180. What is React Testing Library?

A testing library that renders components to a DOM (via jsdom) and provides user-centric queries (`getByRole`, `getByText`, `getByLabelText`). Encourages testing behavior, not implementation details.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q181. What are the RTL query priorities?

Priority order: `getByRole` (most like how screen readers work) > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByDisplayValue` > `getByAltText` > `getByTitle` > `getByTestId` (last resort).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q182. `getBy` vs `queryBy` vs `findBy` – when do you use each?

- `getBy`: throws if not found (use when element should exist)
- `queryBy`: returns null if not found (use for asserting absence)
- `findBy`: async, returns Promise – use when element appears after async operation

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q183. How do you test user interactions?

Use `userEvent` from `@testing-library/user-event` (more realistic than `fireEvent` – triggers all real browser events). `userEvent.click()`, `userEvent.type()`, `userEvent.selectOptions()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q184. How do you test async behavior (e.g., API calls)?

Mock fetch or use MSW (Mock Service Worker). Use `findBy*` or `waitFor(() => expect(...))` to wait for async DOM updates. Never use arbitrary `setTimeout` in tests.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q185. What is Mock Service Worker (MSW)?

Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q186. How do you test custom hooks?

Use `renderHook` from `@testing-library/react`. `act()` wraps state updates. `const {result} = renderHook(() => useCounter(0)); act(() => result.current.increment()); expect(result.current.count).toBe(1)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q187. How do you test components with context?

Wrap with the real Provider (or a test Provider with controlled values) in the render call. RTL's `render` accepts a wrapper option: `render(<Comp/>, {wrapper: TestProviders})`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q188. How do you test error boundaries?

Suppress `console.error` in the test. Render a component that throws inside an error boundary. Assert the fallback UI renders. Use `jest.spyOn(console, 'error').mockImplementation(() => {})` to silence expected errors.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q189. What is the difference between shallow and deep rendering?

Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q190. What is Vitest and how does it differ from Jest?

Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 15: Accessibility (a11y) in React

*Building React apps usable by everyone.*

---

#### Q191. Why does accessibility matter in React apps?

SPAs often break native browser accessibility (focus management, history, page titles). React renders JS-controlled UI that screen readers may not handle correctly without explicit a11y handling.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q192. What are ARIA roles and attributes?

ARIA (Accessible Rich Internet Applications) attributes like `role`, `aria-label`, `aria-describedby`, `aria-expanded`, `aria-hidden` provide semantic meaning to custom components for screen readers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q193. How do you manage focus after navigation in a SPA?

After route change, programmatically move focus to the new page's heading or a skip-link target. Use a ref and `ref.current.focus()` in `useEffect` when the route changes.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q194. What is a focus trap?

Confines keyboard focus within a modal/dialog so Tab doesn't reach content behind it. Required for accessible modals. Libraries: `focus-trap-react`, `@radix-ui/react-dialog` handle this automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q195. How do you handle keyboard navigation in custom components?

Implement `onKeyDown` for keyboard interactions (Enter/Space for activation, arrow keys for navigation, Escape to close). Follow WAI-ARIA authoring practices for each widget type (menu, dialog, tabs, combobox).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q196. What tools help check React app accessibility?

- `eslint-plugin-jsx-a11y` (static analysis)
- `@axe-core/react` (runtime checks in development)
- Browser extensions: Axe DevTools, WAVE
- Lighthouse a11y audit
- Manual screen reader testing (NVDA, VoiceOver)

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q197. What is a skip link?

A visually hidden link at the top of the page that becomes visible on focus and links to the main content area. Allows keyboard users to skip repetitive navigation. Required for WCAG 2.1 AA compliance.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 16: Security in React

*Common vulnerabilities and how React handles them.*

---

#### Q198. How does React prevent XSS by default?

React escapes all values rendered in JSX. Strings are HTML-encoded before being inserted into the DOM. You cannot accidentally inject script tags through regular JSX expressions.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q199. What is `dangerouslySetInnerHTML` and why is it dangerous?

Sets raw HTML on a DOM node, bypassing React's XSS protection. If the HTML contains user input, it can execute arbitrary scripts. Always sanitize with DOMPurify before using it.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q200. What is a CSRF attack and how do you prevent it in React apps?

Cross-Site Request Forgery tricks a user's browser into making authenticated requests to your API. Prevent with CSRF tokens in headers, `SameSite` cookie attribute, and not relying solely on cookies for auth.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q201. What is a CORS issue and how do you handle it?

Cross-Origin Resource Sharing: browsers block requests to different origins. Configure the server to send correct `Access-Control-Allow-Origin` headers. In development, use a proxy in `vite.config` or CRA's proxy setting.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q202. How do you securely store auth tokens in a React app?

HttpOnly cookies: cannot be accessed by JS, protected from XSS (but vulnerable to CSRF). `localStorage`: accessible to JS, vulnerable to XSS. Best practice: HttpOnly cookies + CSRF tokens, not `localStorage` for sensitive tokens.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q203. What environment variables are safe to expose in a React app?

Only non-secret config: API base URLs, feature flags, analytics IDs. Never: API secret keys, database credentials, private keys. Vite exposes `VITE_` prefixed vars; CRA exposes `REACT_APP_` prefixed vars – all are visible in the bundle.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 17: Build, Tooling & Ecosystem

*The infrastructure around a React application.*

---

#### Q204. What is Vite and why is it preferred over CRA?

Vite uses native ES modules for dev server (near-instant startup) and Rollup for production builds. Much faster than CRA's webpack-based dev server. CRA is no longer maintained.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q205. What is the role of Babel in a React project?

Transpiles modern JS and JSX to browser-compatible JS. Plugins transform JSX to `createElement` calls. In Vite projects, esbuild handles transpilation faster; Babel is less common in new setups.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q206. What is HMR (Hot Module Replacement)?

Replaces changed modules in the browser without full page reload. React's Fast Refresh preserves component state during HMR. Dramatically speeds up development iteration.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q207. What is the purpose of ESLint and Prettier in a React project?

ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other – ESLint for rules, Prettier for style.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q208. What is the `eslint-plugin-react-hooks` plugin?

Enforces Rules of Hooks: 'rules-of-hooks' (hooks only in function components/custom hooks) and 'exhaustive-deps' (all effect dependencies declared). Install in every React project.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q209. What is Storybook?

A development environment for building, documenting, and testing UI components in isolation. Write stories for different component states. Used for design systems, component libraries, and visual regression testing.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q210. What is a monorepo and how does it relate to React projects?

A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q211. What is bundle analysis and how do you do it?

Inspect what's in your production bundle to find large dependencies. Vite: `rollup-plugin-visualizer`. Webpack: `webpack-bundle-analyzer`. Look for: duplicate libraries, large unused imports, unnecessarily large dependencies.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 18: Senior-Level Scenario Questions

*Open-ended design and debugging scenarios for experienced developers.*

---

#### Q212. Design a real-time chat UI in React.

WebSocket for live messages. `useEffect` to subscribe/unsubscribe. Messages in `useState` or `useReducer`. Virtualized message list for performance. Optimistic updates when sending. Error boundary for connection failures. Reconnect logic in a custom hook.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q213. How would you migrate a large class-based codebase to hooks?

Incrementally – convert leaf components first, then move up. Map lifecycle methods to `useEffect` patterns. Extract shared logic to custom hooks. Maintain tests throughout. Use codemods for mechanical transforms. Don't big-bang rewrite.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q214. Design a form wizard with multiple steps in React.

Store step index in state. Store all step data in a reducer or React Hook Form with a persistent form context. Each step validates before proceeding. Preserve data when navigating back. Consider URL-based step state for shareable links.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q215. How would you implement infinite scroll?

Use `IntersectionObserver` to detect when a sentinel element at the bottom is visible. Trigger the next page fetch. Append results to existing list. Use React Query's `useInfiniteQuery` for built-in pagination support. Virtualize for 1000+ items.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q216. How would you build a drag-and-drop kanban board?

Use `dnd-kit` or `@hello-pangea/dnd`. Model board state as `{columns: {id: {cards: []}}}`. On drag end, update state with new column/position. Optimistic updates. Sync to backend with debounce or on drop. Accessibility: keyboard drag support via dnd-kit.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q217. How would you architect a React app for a team of 20 developers?

Feature-based folder structure. Shared component library (with Storybook). TypeScript throughout. Agreed state management strategy (React Query for server, Zustand for client global). ESLint + Prettier + husky pre-commit hooks. Module boundaries enforced by Nx or ESLint import rules.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q218. Situation: The app is slow on mobile – how do you diagnose and fix it?

Throttle CPU in DevTools to simulate mobile. Use Lighthouse for performance audit. Check bundle size (code split aggressively). Profile renders with React DevTools. Remove render-blocking JS. Lazy load images and offscreen components. Reduce animation complexity.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q219. How would you implement role-based access control (RBAC) in React?

Store user roles in auth context. Create a `usePermissions` hook that checks roles. Wrap protected components with a `Can` component or conditional rendering. Protect routes in the router (loader-level redirect). Never trust client-side checks alone – enforce on the server.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q220. How would you handle real-time data updates (live prices, scores)?

WebSockets or SSE (Server-Sent Events). Custom `useWebSocket` hook managing connection lifecycle. Update local cache (`queryClient.setQueryData`) on incoming messages. Show live indicator. Handle reconnection with exponential backoff.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q221. How do you implement a feature flag system?

Feature flag service (LaunchDarkly, Unleash, homegrown). Fetch flags at app init, store in context. `useFeatureFlag('feature-name')` hook returns boolean. Guard components with conditional rendering. Allow runtime flag changes without redeploy.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q222. Situation: A critical bug is in production – what's your process?

Check monitoring (Sentry) for error details, affected users, first occurrence. Reproduce locally. Deploy a hotfix or feature-flag it off. Post-mortem: add a test to prevent regression. Update error boundary to catch similar errors more gracefully.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q223. How would you implement internationalization (i18n) in React?

`react-intl` or `react-i18next`. Extract all strings to message catalogs. `useIntl()` hook for formatting. Support RTL layouts (`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies via Intl API. Lazy load language bundles.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q224. How do you ensure a React app performs well at 100k users?

CDN for static assets. SSR/SSG for fast initial loads. Aggressive caching (React Query, HTTP cache headers). Server-side pagination, never load all data. Code splitting per route. Error boundaries everywhere. Monitoring and alerting from day one.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q225. How would you design a design system in React?

Separate npm package. Primitive components (Button, Input, Text). Compound components for complex widgets. Design tokens (CSS variables). Storybook for documentation. Chromatic for visual regression. Semantic versioning with changelogs. TypeScript for consumer safety.

[⬆ Back to Table of Contents](#-table-of-contents)

---

*225 questions across 18 sections. Happy studying! ⚛️*
