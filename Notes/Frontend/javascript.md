# JavaScript Questions & Answers

## Table of Contents

### JavaScript Fundamentals

#### Junior

1. [What is JavaScript and where does it run?](#1-what-is-javascript-and-where-does-it-run)
2. [What are the primitive types in JavaScript?](#2-what-are-the-primitive-types-in-javascript)
3. [What is JavaScript and where can it run?](#3-what-is-javascript-and-where-can-it-run)
4. [What are the primitive data types in JavaScript?](#4-what-are-the-primitive-data-types-in-javascript)
5. [What is strict mode?](#5-what-is-strict-mode)

#### Intermediate

6. [What is the ECMAScript specification?](#6-what-is-the-ecmascript-specification)
7. [What is `typeof` and what are its quirks?](#7-what-is-typeof-and-what-are-its-quirks)
8. [What is type coercion?](#8-what-is-type-coercion)
9. [What is `NaN` and how do you check for it?](#9-what-is-nan-and-how-do-you-check-for-it)
10. [What is the difference between `null` and `undefined`?](#10-what-is-the-difference-between-null-and-undefined)
11. [What is the difference between JavaScript and ECMAScript?](#11-what-is-the-difference-between-javascript-and-ecmascript)
12. [Is JavaScript compiled or interpreted?](#12-is-javascript-compiled-or-interpreted)
13. [What is the JavaScript engine and how does it work?](#13-what-is-the-javascript-engine-and-how-does-it-work)
14. [What is single-threaded execution in JavaScript?](#14-what-is-single-threaded-execution-in-javascript)
15. [What is the `typeof` operator?](#15-what-is-the-typeof-operator)
16. [What is polymorphism in JavaScript?](#16-what-is-polymorphism-in-javascript)
17. [How does JavaScript handle integer overflow?](#17-how-does-javascript-handle-integer-overflow)
18. [What are the tricky parts of `==` type coercion rules?](#18-what-are-the-tricky-parts-of-type-coercion-rules)
19. [What is the difference between pass-by-value and pass-by-reference?](#19-what-is-the-difference-between-pass-by-value-and-pass-by-reference)

### Variables, Scope & Execution Context

#### Junior

20. [What is hoisting?](#20-what-is-hoisting)
21. [What is scope? Explain global, function, and block scope.](#21-what-is-scope-explain-global-function-and-block-scope)

#### Intermediate

22. [What is variable shadowing?](#22-what-is-variable-shadowing)
23. [Stuffing Variables Inside Text (Interpolation)](#23-stuffing-variables-inside-text-interpolation)
24. [What is variable hoisting?](#24-what-is-variable-hoisting)
25. [What is the Temporal Dead Zone (TDZ)?](#25-what-is-the-temporal-dead-zone-tdz)
26. [What is scope in JavaScript?](#26-what-is-scope-in-javascript)
27. [What is the execution context?](#27-what-is-the-execution-context)
28. [What is scope chain resolution?](#28-what-is-scope-chain-resolution)
29. [What is the module scope?](#29-what-is-the-module-scope)
30. [What is the difference between global, function, and block scope?](#30-what-is-the-difference-between-global-function-and-block-scope)
31. [What is the scope chain?](#31-what-is-the-scope-chain)
32. [What is lexical scope?](#32-what-is-lexical-scope)
33. [What is an execution context?](#33-what-is-an-execution-context)
34. [What is the difference between function scope and block scope?](#34-what-is-the-difference-between-function-scope-and-block-scope)
35. [What are the differences between `var`, `let`, and `const`?](#35-what-are-the-differences-between-var-let-and-const)
36. [What is the call stack?](#36-what-is-the-call-stack)
37. [What is the difference between `var`, `let`, and `const`?](#37-what-is-the-difference-between-var-let-and-const)

### Functions & Functional Programming

#### Junior

38. [What is a callback function?](#38-what-is-a-callback-function)
39. [What is a callback and what is callback hell?](#39-what-is-a-callback-and-what-is-callback-hell)

#### Intermediate

40. [Explain the difference between eager and lazy evaluation in JavaScript.](#40-explain-the-difference-between-eager-and-lazy-evaluation-in-javascript)
41. [What is IIFE (Immediately Invoked Function Expression) and why was it used?](#41-what-is-iife-immediately-invoked-function-expression-and-why-was-it-used)
42. [What is the difference between a function declaration and a function expression?](#42-what-is-the-difference-between-a-function-declaration-and-a-function-expression)
43. [What are arrow functions and how do they differ from regular functions?](#43-what-are-arrow-functions-and-how-do-they-differ-from-regular-functions)
44. [What is a higher-order function?](#44-what-is-a-higher-order-function)
45. [What is function composition?](#45-what-is-function-composition)
46. [What is a pure function?](#46-what-is-a-pure-function)
47. [What is a recursive function and what is tail call optimization?](#47-what-is-a-recursive-function-and-what-is-tail-call-optimization)
48. [What are callbacks and what problems do they have?](#48-what-are-callbacks-and-what-problems-do-they-have)
49. [What are the core principles of functional programming?](#49-what-are-the-core-principles-of-functional-programming)
50. [What is the difference between function declaration and function expression?](#50-what-is-the-difference-between-function-declaration-and-function-expression)
51. [What is the difference between a method and a function?](#51-what-is-the-difference-between-a-method-and-a-function)
52. [What is functional programming?](#52-what-is-functional-programming)
53. [What is function composition vs piping?](#53-what-is-function-composition-vs-piping)
54. [Callback functions – what are they? Callback hell.](#54-callback-functions-what-are-they-callback-hell)
55. [What is the `arguments` object?](#55-what-is-the-arguments-object)
56. [What are rest parameters and the spread operator?](#56-what-are-rest-parameters-and-the-spread-operator)
57. [No `arguments` Object](#57-no-arguments-object)
58. [What is the rest parameter (`...args`)?](#58-what-is-the-rest-parameter-args)
59. [What does "first-class functions" mean?](#59-what-does-first-class-functions-mean)
60. [What is a first-class function?](#60-what-is-a-first-class-function)
61. [What is partial application?](#61-what-is-partial-application)

#### Advanced

62. [Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)](#62-why-does-javascript-have-closures-data-privacy-hooks-callbacks-memoization)
63. [What is currying?](#63-what-is-currying)
64. [What is function currying?](#64-what-is-function-currying)
65. [What is memoization?](#65-what-is-memoization)

#### Senior / Scenario

66. [Design a rate limiter function in JavaScript.](#66-design-a-rate-limiter-function-in-javascript)
67. [How would you implement a deep equality function?](#67-how-would-you-implement-a-deep-equality-function)
68. [Design a pipeline function (like `|>` operator) in JavaScript.](#68-design-a-pipeline-function-like-operator-in-javascript)
69. [Implement a deep clone function.](#69-implement-a-deep-clone-function)
70. [Implement a debounce function from scratch.](#70-implement-a-debounce-function-from-scratch)
71. [Implement a throttle function from scratch.](#71-implement-a-throttle-function-from-scratch)
72. [How would you implement `curry` function from scratch?](#72-how-would-you-implement-curry-function-from-scratch)
73. [How would you implement memoization with a complex cache key?](#73-how-would-you-implement-memoization-with-a-complex-cache-key)
74. [Implement debounce and throttle functions.](#74-implement-debounce-and-throttle-functions)
75. [Implement a deep clone function (deep copy).](#75-implement-a-deep-clone-function-deep-copy)

### `this`, Call Context & Binding

#### Intermediate

76. [Why does `this` lose context in callbacks?](#76-why-does-this-lose-context-in-callbacks)
77. [How do arrow functions differ from regular functions regarding `this`?](#77-how-do-arrow-functions-differ-from-regular-functions-regarding-this)
78. [The `this` Keyword (The Biggest Difference)](#78-the-this-keyword-the-biggest-difference)
79. [What are the four rules of `this` binding?](#79-what-are-the-four-rules-of-this-binding)
80. [How does `this` work in arrow functions?](#80-how-does-this-work-in-arrow-functions)

#### Senior / Scenario

81. [Situation: `this` is `undefined` inside a class method used as a callback — how do you fix it?](#81-situation-this-is-undefined-inside-a-class-method-used-as-a-callback-how-do-you-fix-it)
82. [Situation: `this` is `undefined` or `window` inside a callback – why?](#82-situation-this-is-undefined-or-window-inside-a-callback-why)

### Objects, Arrays & Data Manipulation

#### Junior

83. [What is a Set?](#83-what-is-a-set)

#### Intermediate

84. [What is immutability and how do you achieve it in JavaScript?](#84-what-is-immutability-and-how-do-you-achieve-it-in-javascript)
85. [What is `Reflect` in JavaScript?](#85-what-is-reflect-in-javascript)
86. [What are the most important array methods?](#86-what-are-the-most-important-array-methods)
87. [How do you remove duplicates from an array?](#87-how-do-you-remove-duplicates-from-an-array)
88. [What is array destructuring?](#88-what-is-array-destructuring)
89. [What is object destructuring?](#89-what-is-object-destructuring)
90. [What is the spread operator for objects?](#90-what-is-the-spread-operator-for-objects)
91. [What is object shorthand property syntax?](#91-what-is-object-shorthand-property-syntax)
92. [What is `Object.freeze()` vs `Object.seal()`?](#92-what-is-objectfreeze-vs-objectseal)
93. [What is `Object.create()`?](#93-what-is-objectcreate)
94. [What are the differences between `Map` and a plain object?](#94-what-are-the-differences-between-map-and-a-plain-object)
95. [What is the difference between `==` comparisons and `Object.is`?](#95-what-is-the-difference-between-comparisons-and-objectis)
96. [What is the difference between `Object.keys`, `Object.values`, `Object.entries`, and `Object.fromEntries`?](#96-what-is-the-difference-between-objectkeys-objectvalues-objectentries-and-objectfromentries)
97. [What are the ways to create objects in JavaScript?](#97-what-are-the-ways-to-create-objects-in-javascript)
98. [What is destructuring?](#98-what-is-destructuring)
99. [What is the spread operator?](#99-what-is-the-spread-operator)
100. [What is `Object.keys()`, `Object.values()`, `Object.entries()`?](#100-what-is-objectkeys-objectvalues-objectentries)
101. [What is array and object destructuring with defaults?](#101-what-is-array-and-object-destructuring-with-defaults)
102. [What does `flat()` and `flatMap()` do?](#102-what-does-flat-and-flatmap-do)
103. [What is a Map vs a plain object?](#103-what-is-a-map-vs-a-plain-object)
104. [What is the difference between `Object.assign()` and spread?](#104-what-is-the-difference-between-objectassign-and-spread)
105. [What is the Proxy object and how is it used?](#105-what-is-the-proxy-object-and-how-is-it-used)
106. [Explain the difference between `Array.from()` and spread on a NodeList.](#106-explain-the-difference-between-arrayfrom-and-spread-on-a-nodelist)
107. [How does JavaScript sort arrays by default and what is the gotcha?](#107-how-does-javascript-sort-arrays-by-default-and-what-is-the-gotcha)
108. [What is the difference between `Object.create(null)` and `{}`?](#108-what-is-the-difference-between-objectcreatenull-and)
109. [What are property descriptors?](#109-what-are-property-descriptors)
110. [What is a WeakMap and when would you use it?](#110-what-is-a-weakmap-and-when-would-you-use-it)
111. [What is a WeakSet?](#111-what-is-a-weakset)
112. [What are `Map` and `Set`?](#112-what-are-map-and-set)
113. [What are Proxy and Reflect?](#113-what-are-proxy-and-reflect)
114. [What are computed property names?](#114-what-are-computed-property-names)
115. [What is method chaining?](#115-what-is-method-chaining)
116. [What is immutability and why does it matter?](#116-what-is-immutability-and-why-does-it-matter)

#### Advanced

117. [How do you deep clone an object in JavaScript?](#117-how-do-you-deep-clone-an-object-in-javascript)
118. [How do you deep clone an object?](#118-how-do-you-deep-clone-an-object)
119. [How does `structuredClone` differ from `JSON.parse(JSON.stringify())`?](#119-how-does-structuredclone-differ-from-jsonparsejsonstringify)
120. [What is the difference between shallow copy and deep copy?](#120-what-is-the-difference-between-shallow-copy-and-deep-copy)
121. [What is `structuredClone()`?](#121-what-is-structuredclone)

### Prototypes, Inheritance & Classes

#### Intermediate

122. [What is a constructor function?](#122-what-is-a-constructor-function)
123. [What is the `prototype` property on functions?](#123-what-is-the-prototype-property-on-functions)
124. [What is the difference between `__proto__` and `prototype`?](#124-what-is-the-difference-between-proto-and-prototype)
125. [What is prototypal delegation vs classical inheritance?](#125-what-is-prototypal-delegation-vs-classical-inheritance)
126. [What is a prototype in JavaScript?](#126-what-is-a-prototype-in-javascript)
127. [What is prototypal inheritance?](#127-what-is-prototypal-inheritance)
128. [What is the difference between classical and prototypal inheritance?](#128-what-is-the-difference-between-classical-and-prototypal-inheritance)
129. [What is `Object.getPrototypeOf()`?](#129-what-is-objectgetprototypeof)
130. [What are private class fields?](#130-what-are-private-class-fields)
131. [What is a class in JavaScript?](#131-what-is-a-class-in-javascript)
132. [What is a constructor?](#132-what-is-a-constructor)
133. [What is inheritance with `extends` and `super`?](#133-what-is-inheritance-with-extends-and-super)
134. [What is the difference between composition and inheritance?](#134-what-is-the-difference-between-composition-and-inheritance)
135. [What is the difference between static and instance methods?](#135-what-is-the-difference-between-static-and-instance-methods)
136. [What is `instanceof` and how does it work?](#136-what-is-instanceof-and-how-does-it-work)
137. [What are static methods and properties?](#137-what-are-static-methods-and-properties)
138. [What are getters and setters?](#138-what-are-getters-and-setters)
139. [What is encapsulation and how is it achieved in JS?](#139-what-is-encapsulation-and-how-is-it-achieved-in-js)
140. [What is a mixin?](#140-what-is-a-mixin)

#### Advanced

141. [What is the prototype chain?](#141-what-is-the-prototype-chain)

#### Senior / Scenario

142. [What are mixins and how do you implement them in JavaScript?](#142-what-are-mixins-and-how-do-you-implement-them-in-javascript)
143. [Explain how `Array.prototype.reduce` works from scratch.](#143-explain-how-arrayprototypereduce-works-from-scratch)
144. [Implement `Array.prototype.flat` from scratch.](#144-implement-arrayprototypeflat-from-scratch)

### ES6+ Modern JavaScript

#### Intermediate

145. [What is the logical assignment operators (`&&=`, `||=`, `??=`)?](#145-what-is-the-logical-assignment-operators)
146. [What is the `void` operator?](#146-what-is-the-void-operator)
147. [What is an iterator?](#147-what-is-an-iterator)
148. [What are iterators and iterables?](#148-what-are-iterators-and-iterables)
149. [What is optional chaining (`?.`)?](#149-what-is-optional-chaining)
150. [What is nullish coalescing (`??`)?](#150-what-is-nullish-coalescing)
151. [What are template literals?](#151-what-are-template-literals)
152. [What are tagged template literals?](#152-what-are-tagged-template-literals)
153. [What is the nullish coalescing operator (`??`)?](#153-what-is-the-nullish-coalescing-operator)
154. [What is `BigInt` and when do you use it?](#154-what-is-bigint-and-when-do-you-use-it)
155. [What is the difference between `for...in` and `for...of`?](#155-what-is-the-difference-between-forin-and-forof)
156. [What is an iterable?](#156-what-is-an-iterable)
157. [What is `Symbol` and why was it introduced?](#157-what-is-symbol-and-why-was-it-introduced)
158. [What are well-known Symbols?](#158-what-are-well-known-symbols)
159. [What is `Symbol.toPrimitive` used for?](#159-what-is-symboltoprimitive-used-for)
160. [What is the `for...of` loop?](#160-what-is-the-forof-loop)
161. [What is `globalThis`?](#161-what-is-globalthis)
162. [What are default parameters?](#162-what-are-default-parameters)
163. [What are Symbols?](#163-what-are-symbols)

#### Advanced

164. [What is a generator function?](#164-what-is-a-generator-function)

#### Senior / Scenario

165. [How do generators implement iterators?](#165-how-do-generators-implement-iterators)

### Asynchronous JavaScript

#### Junior

166. [What is a Promise?](#166-what-is-a-promise)

#### Intermediate

167. [What are ES6 classes?](#167-what-are-es6-classes)
168. [What are ES6 classes and how do they relate to prototypes?](#168-what-are-es6-classes-and-how-do-they-relate-to-prototypes)
169. [How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)](#169-how-do-javascript-engines-optimize-code-jit-hidden-classes-inline-caching)
170. [What is the Event Loop?](#170-what-is-the-event-loop)
171. [What is the difference between the Microtask Queue and the Macrotask Queue?](#171-what-is-the-difference-between-the-microtask-queue-and-the-macrotask-queue)
172. [How does Promise chaining work?](#172-how-does-promise-chaining-work)
173. [What is `Promise.all()`?](#173-what-is-promiseall)
174. [What are `Promise.allSettled`, `Promise.race`, and `Promise.any`?](#174-what-are-promiseallsettled-promiserace-and-promiseany)
175. [What is `async/await`?](#175-what-is-asyncawait)
176. [What happens if you `await` a non-Promise value?](#176-what-happens-if-you-await-a-non-promise-value)
177. [What is the difference between `setTimeout(fn, 0)` and `Promise.resolve().then(fn)`?](#177-what-is-the-difference-between-settimeoutfn-0-and-promiseresolvethenfn)
178. [What is the danger of floating Promises?](#178-what-is-the-danger-of-floating-promises)
179. [Explain how JavaScript handles concurrency with the event loop, Workers, and SharedArrayBuffer.](#179-explain-how-javascript-handles-concurrency-with-the-event-loop-workers-and-sharedarraybuffer)
180. [Explain how you'd port a callback-based API to use Promises.](#180-explain-how-youd-port-a-callback-based-api-to-use-promises)
181. [What is synchronous vs asynchronous code?](#181-what-is-synchronous-vs-asynchronous-code)
182. [What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?](#182-what-are-the-call-stack-web-apis-callback-queue-and-microtask-queue)
183. [What is the difference between macrotasks and microtasks?](#183-what-is-the-difference-between-macrotasks-and-microtasks)
184. [What are the states of a Promise?](#184-what-are-the-states-of-a-promise)
185. [What is promise chaining?](#185-what-is-promise-chaining)
186. [What is `Promise.allSettled()`?](#186-what-is-promiseallsettled)
187. [What is `Promise.race()`?](#187-what-is-promiserace)
188. [What is `Promise.any()`?](#188-what-is-promiseany)
189. [What is an unhandled promise rejection?](#189-what-is-an-unhandled-promise-rejection)
190. [What does `finally` do in a Promise chain?](#190-what-does-finally-do-in-a-promise-chain)
191. [Explain the JavaScript event loop in detail. Microtasks vs macrotasks.](#191-explain-the-javascript-event-loop-in-detail-microtasks-vs-macrotasks)
192. [Event loop: Why does a Promise run before setTimeout? (Microtasks vs macrotasks)](#192-event-loop-why-does-a-promise-run-before-settimeout-microtasks-vs-macrotasks)
193. [How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)](#193-how-to-handle-multiple-independent-api-calls-efficiently-promiseall-allsettled)
194. [What are the advantages of `Promise.allSettled` over `Promise.all`?](#194-what-are-the-advantages-of-promiseallsettled-over-promiseall)
195. [Multiple API Calls: How to load a dashboard with independent APIs efficiently? (Promise.all, allSettled)](#195-multiple-api-calls-how-to-load-a-dashboard-with-independent-apis-efficiently-promiseall-allsettled)
196. [Correct async iteration patterns:](#196-correct-async-iteration-patterns)
197. [What are `AbortController` and `AbortSignal`?](#197-what-are-abortcontroller-and-abortsignal)
198. [What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?](#198-what-is-settimeout-vs-setinterval-vs-requestanimationframe)
199. [What is the difference between `setTimeout` and `setInterval`?](#199-what-is-the-difference-between-settimeout-and-setinterval)
200. [Explain AbortController and request cancellation.](#200-explain-abortcontroller-and-request-cancellation)

#### Senior / Scenario

201. [How would you implement structured concurrency in JavaScript?](#201-how-would-you-implement-structured-concurrency-in-javascript)
202. [How do you handle errors with `async/await`?](#202-how-do-you-handle-errors-with-asyncawait)
203. [How do you handle errors in Promises vs async/await?](#203-how-do-you-handle-errors-in-promises-vs-asyncawait)
204. [How do you implement `Promise.all` from scratch?](#204-how-do-you-implement-promiseall-from-scratch)
205. [How do you handle errors in Promises?](#205-how-do-you-handle-errors-in-promises)
206. [Implement `Promise.all` from scratch.](#206-implement-promiseall-from-scratch)
207. [Implement a custom Promise (conceptually).](#207-implement-a-custom-promise-conceptually)
208. [Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.](#208-implement-promiseall-promiserace-promiseallsettled-from-scratch)
209. [In a live application where users report slowness, how would you identify whether the issue is due to the event loop blocking or inefficient code?](#209-in-a-live-application-where-users-report-slowness-how-would-you-identify-whether-the-issue-is-due-to-the-event-loop-blocking-or-inefficient-code)
210. [Situation: Output the order of `setTimeout`, Promise, and synchronous code.](#210-situation-output-the-order-of-settimeout-promise-and-synchronous-code)
211. [Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.](#211-situation-a-for-loop-with-var-and-settimeout-doesnt-behave-as-expected-explain-and-fix)
212. [Design a retry mechanism with exponential backoff for API calls.](#212-design-a-retry-mechanism-with-exponential-backoff-for-api-calls)
213. [Situation: You need to run 100 API calls but limit concurrency to 5 — how?](#213-situation-you-need-to-run-100-api-calls-but-limit-concurrency-to-5-how)
214. [How would you implement server-sent events (SSE) on the client side?](#214-how-would-you-implement-server-sent-events-sse-on-the-client-side)
215. [Situation: Design a retry mechanism for a failed API call.](#215-situation-design-a-retry-mechanism-for-a-failed-api-call)
216. [Situation: How do you cancel a fetch request?](#216-situation-how-do-you-cancel-a-fetch-request)
217. [Implement `Promise.all` from scratch (already covered above).](#217-implement-promiseall-from-scratch-already-covered-above)
218. [How would you handle multiple API calls efficiently without blocking the UI?](#218-how-would-you-handle-multiple-api-calls-efficiently-without-blocking-the-ui)

### DOM, Browser APIs & Events

#### Intermediate

219. [What is the DOM?](#219-what-is-the-dom)
220. [What is the difference between `localStorage`, `sessionStorage`, and cookies?](#220-what-is-the-difference-between-localstorage-sessionstorage-and-cookies)
221. [How do you select DOM elements?](#221-how-do-you-select-dom-elements)
222. [How do you create, append, and remove DOM elements?](#222-how-do-you-create-append-and-remove-dom-elements)
223. [What is the `DOMContentLoaded` vs `load` event?](#223-what-is-the-domcontentloaded-vs-load-event)
224. [What is `localStorage` vs `sessionStorage` vs cookies?](#224-what-is-localstorage-vs-sessionstorage-vs-cookies)
225. [How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)](#225-how-does-the-browser-rendering-pipeline-work-html-css-layout-paint-composite)
226. [What is event bubbling and capturing?](#226-what-is-event-bubbling-and-capturing)
227. [What is `MutationObserver`?](#227-what-is-mutationobserver)
228. [What is `ResizeObserver`?](#228-what-is-resizeobserver)
229. [What is the History API?](#229-what-is-the-history-api)
230. [What is the Fetch API vs XMLHttpRequest?](#230-what-is-the-fetch-api-vs-xmlhttprequest)
231. [What is the Web Worker API?](#231-what-is-the-web-worker-api)
232. [What is `requestAnimationFrame`?](#232-what-is-requestanimationframe)
233. [What is reflow and repaint?](#233-what-is-reflow-and-repaint)
234. [What is `event.stopPropagation()` vs `event.preventDefault()`?](#234-what-is-eventstoppropagation-vs-eventpreventdefault)
235. [What is the difference between `addEventListener` and `onclick`?](#235-what-is-the-difference-between-addeventlistener-and-onclick)
236. [What is the `fetch` API?](#236-what-is-the-fetch-api)
237. [What is the Intersection Observer API?](#237-what-is-the-intersection-observer-api)
238. [What is the MutationObserver API?](#238-what-is-the-mutationobserver-api)
239. [What are Web Workers?](#239-what-are-web-workers)
240. [What is `requestAnimationFrame` and why use it for animations?](#240-what-is-requestanimationframe-and-why-use-it-for-animations)

#### Senior / Scenario

241. [Explain how you would implement virtual scrolling in vanilla JavaScript.](#241-explain-how-you-would-implement-virtual-scrolling-in-vanilla-javascript)
242. [How do you ensure JavaScript is accessible?](#242-how-do-you-ensure-javascript-is-accessible)
243. [How would you implement feature detection in JavaScript?](#243-how-would-you-implement-feature-detection-in-javascript)
244. [Design a simple virtual DOM diffing algorithm.](#244-design-a-simple-virtual-dom-diffing-algorithm)
245. [Situation: Users report your web app crashes their browser tab — what do you investigate?](#245-situation-users-report-your-web-app-crashes-their-browser-tab-what-do-you-investigate)

### Modules, Tooling & TypeScript

#### Intermediate

246. [What is the difference between JavaScript and TypeScript?](#246-what-is-the-difference-between-javascript-and-typescript)
247. [What is the JavaScript pipeline operator proposal?](#247-what-is-the-javascript-pipeline-operator-proposal)
248. [What is the TC39 proposal process and how do you track upcoming JavaScript features?](#248-what-is-the-tc39-proposal-process-and-how-do-you-track-upcoming-javascript-features)
249. [What is TypeScript and how does it relate to JavaScript?](#249-what-is-typescript-and-how-does-it-relate-to-javascript)
250. [What are named exports vs default exports in ES modules?](#250-what-are-named-exports-vs-default-exports-in-es-modules)
251. [What is dynamic `import()`?](#251-what-is-dynamic-import)
252. [What is tree shaking and how does it relate to ES modules?](#252-what-is-tree-shaking-and-how-does-it-relate-to-es-modules)
253. [What is the CommonJS module system?](#253-what-is-the-commonjs-module-system)
254. [What are ES Modules (ESM)?](#254-what-are-es-modules-esm)
255. [What is the difference between named and namespace imports?](#255-what-is-the-difference-between-named-and-namespace-imports)
256. [What is module federation?](#256-what-is-module-federation)
257. [What are package.json `exports` and `main` fields?](#257-what-are-packagejson-exports-and-main-fields)
258. [Explain the JavaScript module resolution algorithm.](#258-explain-the-javascript-module-resolution-algorithm)
259. [What is the Module pattern?](#259-what-is-the-module-pattern)
260. [What is the Revealing Module pattern?](#260-what-is-the-revealing-module-pattern)
261. [What are ES Modules (`import`/`export`)?](#261-what-are-es-modules-importexport)
262. [What is the difference between default and named exports?](#262-what-is-the-difference-between-default-and-named-exports)
263. [What is CommonJS (`require`/`module.exports`)?](#263-what-is-commonjs-requiremoduleexports)
264. [What is the difference between CommonJS and ES Modules?](#264-what-is-the-difference-between-commonjs-and-es-modules)
265. [What is a bundler (Webpack, Rollup, Vite)?](#265-what-is-a-bundler-webpack-rollup-vite)
266. [What are source maps?](#266-what-are-source-maps)
267. [What is tree shaking?](#267-what-is-tree-shaking)
268. [What is transpilation and what does Babel do?](#268-what-is-transpilation-and-what-does-babel-do)
269. [What is source mapping?](#269-what-is-source-mapping)
270. [What is npm and what is `package.json`?](#270-what-is-npm-and-what-is-packagejson)
271. [What is the difference between `dependencies` and `devDependencies`?](#271-what-is-the-difference-between-dependencies-and-devdependencies)
272. [What are the basic types in TypeScript?](#272-what-are-the-basic-types-in-typescript)
273. [What is `any` vs `unknown` in TypeScript?](#273-what-is-any-vs-unknown-in-typescript)
274. [What is a type assertion?](#274-what-is-a-type-assertion)
275. [What is a union type vs intersection type?](#275-what-is-a-union-type-vs-intersection-type)
276. [What are generics in TypeScript?](#276-what-are-generics-in-typescript)
277. [What is the difference between `interface` and `type`?](#277-what-is-the-difference-between-interface-and-type)
278. [What is type narrowing?](#278-what-is-type-narrowing)

### Error Handling & Debugging

#### Intermediate

279. [What are the types of errors in JavaScript?](#279-what-are-the-types-of-errors-in-javascript)
280. [How do you debug JavaScript effectively?](#280-how-do-you-debug-javascript-effectively)
281. [What is the `Error` object?](#281-what-is-the-error-object)
282. [How do you create custom error types?](#282-how-do-you-create-custom-error-types)
283. [What is `try/catch/finally` and how does `finally` behave?](#283-what-is-trycatchfinally-and-how-does-finally-behave)
284. [What is the `Error.cause` property (ES2022)?](#284-what-is-the-errorcause-property-es2022)
285. [What is a `try/catch/finally` block?](#285-what-is-a-trycatchfinally-block)
286. [What are the built-in error types?](#286-what-are-the-built-in-error-types)
287. [How do you create a custom error?](#287-how-do-you-create-a-custom-error)

#### Senior / Scenario

288. [How do you handle JavaScript errors in a production application end-to-end?](#288-how-do-you-handle-javascript-errors-in-a-production-application-end-to-end)
289. [How would you design JavaScript error handling for a large team?](#289-how-would-you-design-javascript-error-handling-for-a-large-team)
290. [Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?](#290-situation-error-thrown-inside-settimeout-does-trycatch-catch-it)

### Performance & Memory

#### Intermediate

291. [How does V8 optimize JavaScript?](#291-how-does-v8-optimize-javascript)
292. [How do you approach writing JavaScript for low-powered devices?](#292-how-do-you-approach-writing-javascript-for-low-powered-devices)
293. [How do you profile and optimize a JavaScript animation that's dropping frames?](#293-how-do-you-profile-and-optimize-a-javascript-animation-thats-dropping-frames)
294. [When NOT to use JavaScript: CPU-heavy tasks, long-running blocking logic – use backend or workers.](#294-when-not-to-use-javascript-cpu-heavy-tasks-long-running-blocking-logic-use-backend-or-workers)
295. [What is a closure memory leak and how do you avoid it?](#295-what-is-a-closure-memory-leak-and-how-do-you-avoid-it)
296. [What are memory leaks in JavaScript and what causes them?](#296-what-are-memory-leaks-in-javascript-and-what-causes-them)
297. [What is a memory leak and what causes them?](#297-what-is-a-memory-leak-and-what-causes-them)
298. [How do you profile JavaScript performance?](#298-how-do-you-profile-javascript-performance)
299. [What causes memory leaks in frontend applications? How to prevent them?](#299-what-causes-memory-leaks-in-frontend-applications-how-to-prevent-them)

#### Advanced

300. [What is the JavaScript garbage collection impact of closures?](#300-what-is-the-javascript-garbage-collection-impact-of-closures)
301. [What is garbage collection in JavaScript?](#301-what-is-garbage-collection-in-javascript)
302. [How does garbage collection work in JavaScript?](#302-how-does-garbage-collection-work-in-javascript)
303. [How does garbage collection work in V8?](#303-how-does-garbage-collection-work-in-v8)

#### Senior / Scenario

304. [A page is consuming too much memory over time — how would you detect and prevent memory leaks?](#304-a-page-is-consuming-too-much-memory-over-time-how-would-you-detect-and-prevent-memory-leaks)

### Security

#### Intermediate

305. [What is a timing attack and how does it relate to JavaScript?](#305-what-is-a-timing-attack-and-how-does-it-relate-to-javascript)
306. [How do you securely handle user input in JavaScript?](#306-how-do-you-securely-handle-user-input-in-javascript)
307. [What is prototype pollution?](#307-what-is-prototype-pollution)
308. [What is XSS (Cross-Site Scripting) and how do you prevent it?](#308-what-is-xss-cross-site-scripting-and-how-do-you-prevent-it)
309. [What is Content Security Policy (CSP)?](#309-what-is-content-security-policy-csp)
310. [What is XSS (Cross-Site Scripting)?](#310-what-is-xss-cross-site-scripting)
311. [What is CSRF (Cross-Site Request Forgery)?](#311-what-is-csrf-cross-site-request-forgery)
312. [What are CORS and SOP (Same-Origin Policy)?](#312-what-are-cors-and-sop-same-origin-policy)
313. [What is clickjacking and how do you prevent it?](#313-what-is-clickjacking-and-how-do-you-prevent-it)

#### Senior / Scenario

314. [How do you handle JavaScript in a security-sensitive context (e.g., fintech)?](#314-how-do-you-handle-javascript-in-a-security-sensitive-context-eg-fintech)

### Testing

#### Intermediate

315. [How do you test asynchronous code in Jest?](#315-how-do-you-test-asynchronous-code-in-jest)
316. [What is the testing pyramid for JavaScript?](#316-what-is-the-testing-pyramid-for-javascript)
317. [What is Jest and what does it provide?](#317-what-is-jest-and-what-does-it-provide)
318. [What is the difference between `jest.fn()`, `jest.spyOn()`, and `jest.mock()`?](#318-what-is-the-difference-between-jestfn-jestspyon-and-jestmock)
319. [What are snapshot tests?](#319-what-are-snapshot-tests)
320. [What is test-driven development (TDD)?](#320-what-is-test-driven-development-tdd)
321. [What is property-based testing?](#321-what-is-property-based-testing)
322. [What is unit testing?](#322-what-is-unit-testing)
323. [What is Jest?](#323-what-is-jest)
324. [What is TDD (Test-Driven Development)?](#324-what-is-tdd-test-driven-development)
325. [What is the difference between unit, integration, and E2E tests?](#325-what-is-the-difference-between-unit-integration-and-e2e-tests)
326. [What is code coverage and what metrics matter?](#326-what-is-code-coverage-and-what-metrics-matter)
327. [What are mocks, stubs, and spies?](#327-what-are-mocks-stubs-and-spies)
328. [What is code coverage?](#328-what-is-code-coverage)

### Node.js & Runtime

#### Junior

329. [What is Node.js?](#329-what-is-nodejs)

#### Intermediate

330. [What is the Node.js event loop and how does it differ from the browser's?](#330-what-is-the-nodejs-event-loop-and-how-does-it-differ-from-the-browsers)
331. [What is the Node.js event loop vs the browser event loop?](#331-what-is-the-nodejs-event-loop-vs-the-browser-event-loop)
332. [How do you write JavaScript that works in both browser and Node.js?](#332-how-do-you-write-javascript-that-works-in-both-browser-and-nodejs)
333. [What is the difference between the browser and Node.js environments?](#333-what-is-the-difference-between-the-browser-and-nodejs-environments)
334. [What is the `cluster` module?](#334-what-is-the-cluster-module)
335. [What are Node.js streams?](#335-what-are-nodejs-streams)
336. [What is `Buffer` in Node.js?](#336-what-is-buffer-in-nodejs)
337. [What are Worker Threads in Node.js?](#337-what-are-worker-threads-in-nodejs)
338. [What is the difference between `require` resolution and ESM resolution in Node.js?](#338-what-is-the-difference-between-require-resolution-and-esm-resolution-in-nodejs)
339. [What is `process.nextTick()`?](#339-what-is-processnexttick)

#### Senior / Scenario

340. [Situation: A Node.js server is leaking memory — how do you diagnose it?](#340-situation-a-nodejs-server-is-leaking-memory-how-do-you-diagnose-it)
341. [How would you handle large JSON files in Node.js?](#341-how-would-you-handle-large-json-files-in-nodejs)

### Advanced JavaScript & Architecture

#### Intermediate

342. [What would you look for when reviewing a junior developer's JavaScript PR?](#342-what-would-you-look-for-when-reviewing-a-junior-developers-javascript-pr)
343. [How do you make a JavaScript library tree-shakeable?](#343-how-do-you-make-a-javascript-library-tree-shakeable)
344. [What is a closure?](#344-what-is-a-closure)
345. [Give a practical use case for closures.](#345-give-a-practical-use-case-for-closures)
346. [What is a common closure bug in loops?](#346-what-is-a-common-closure-bug-in-loops)
347. [What are practical uses of closures?](#347-what-are-practical-uses-of-closures)
348. [Explain closures with a real-world example](#348-explain-closures-with-a-real-world-example)
349. [What is `this` in JavaScript?](#349-what-is-this-in-javascript)
350. [How do `call`, `apply`, and `bind` work?](#350-how-do-call-apply-and-bind-work)
351. [What are the four rules that determine `this`?](#351-what-are-the-four-rules-that-determine-this)
352. [What is hard binding and when do you use it?](#352-what-is-hard-binding-and-when-do-you-use-it)
353. [What is explicit binding with `call`, `apply`, and `bind`?](#353-what-is-explicit-binding-with-call-apply-and-bind)
354. [What does `bind` return?](#354-what-does-bind-return)
355. [What is `this` in a class?](#355-what-is-this-in-a-class)
356. [What is the difference between `map` and `forEach`?](#356-what-is-the-difference-between-map-and-foreach)
357. [What is the difference between `forEach` and `map`?](#357-what-is-the-difference-between-foreach-and-map)
358. [What does `super` do in a class?](#358-what-does-super-do-in-a-class)
359. [What are the trade-offs between using `class` and factory functions in JavaScript?](#359-what-are-the-trade-offs-between-using-class-and-factory-functions-in-javascript)
360. [Cannot Be Constructors](#360-cannot-be-constructors)
361. [How do you run async operations in parallel vs sequentially?](#361-how-do-you-run-async-operations-in-parallel-vs-sequentially)
362. [What is the difference between sequential and parallel async execution?](#362-what-is-the-difference-between-sequential-and-parallel-async-execution)
363. [What is `createAsyncThunk()` and why is it used?](#363-what-is-createasyncthunk-and-why-is-it-used)
364. [How does async flow work in Redux Toolkit?](#364-how-does-async-flow-work-in-redux-toolkit)
365. [What is event delegation?](#365-what-is-event-delegation)
366. [How do you detect and prevent infinite loops in user-submitted code?](#366-how-do-you-detect-and-prevent-infinite-loops-in-user-submitted-code)
367. [How do you safely handle `JSON.parse` with unknown input?](#367-how-do-you-safely-handle-jsonparse-with-unknown-input)
368. [What is tail call optimization?](#368-what-is-tail-call-optimization)
369. [What is the difference between `==` and `===`?](#369-what-is-the-difference-between-and)
370. [What are truthy and falsy values?](#370-what-are-truthy-and-falsy-values)
371. [What is the difference between a statement and an expression?](#371-what-is-the-difference-between-a-statement-and-an-expression)
372. [What is lexical scoping?](#372-what-is-lexical-scoping)
373. [How does `reduce` work?](#373-how-does-reduce-work)
374. [What is the difference between `slice` and `splice`?](#374-what-is-the-difference-between-slice-and-splice)
375. [What does `new` do step by step?](#375-what-does-new-do-step-by-step)
376. [What is `console.table`, `console.group`, and `console.time`?](#376-what-is-consoletable-consolegroup-and-consoletime)
377. [What is the difference between `innerHTML`, `textContent`, and `innerText`?](#377-what-is-the-difference-between-innerhtml-textcontent-and-innertext)
378. [What is `IntersectionObserver`?](#378-what-is-intersectionobserver)
379. [What is the difference between debounce and throttle?](#379-what-is-the-difference-between-debounce-and-throttle)
380. [What is lazy loading?](#380-what-is-lazy-loading)
381. [What is a functor?](#381-what-is-a-functor)
382. [What is a monad (in practical JS terms)?](#382-what-is-a-monad-in-practical-js-terms)
383. [What is point-free style?](#383-what-is-point-free-style)
384. [What is `eval()` and why is it dangerous?](#384-what-is-eval-and-why-is-it-dangerous)
385. [What is an IIFE and why is it used?](#385-what-is-an-iife-and-why-is-it-used)
386. [What is the difference between `call` and `apply`?](#386-what-is-the-difference-between-call-and-apply)
387. [What is `hasOwnProperty`?](#387-what-is-hasownproperty)
388. [What is the difference between `map`, `filter`, and `reduce`?](#388-what-is-the-difference-between-map-filter-and-reduce)
389. [What is the difference between `find` and `filter`?](#389-what-is-the-difference-between-find-and-filter)
390. [Multi-line Text Made Easy](#390-multi-line-text-made-easy)
391. [What are ES2020+ features you should know?](#391-what-are-es2020-features-you-should-know)
392. [What is CORS?](#392-what-is-cors)
393. [What is debouncing?](#393-what-is-debouncing)
394. [What is throttling?](#394-what-is-throttling)
395. [What is the Singleton pattern?](#395-what-is-the-singleton-pattern)
396. [What is the Observer / Pub-Sub pattern?](#396-what-is-the-observer-pub-sub-pattern)
397. [What is the Factory pattern?](#397-what-is-the-factory-pattern)
398. [What is the Decorator pattern?](#398-what-is-the-decorator-pattern)
399. [What is the Strategy pattern?](#399-what-is-the-strategy-pattern)
400. [What is the Proxy pattern?](#400-what-is-the-proxy-pattern)
401. [What is the Command pattern?](#401-what-is-the-command-pattern)
402. [What are side effects?](#402-what-are-side-effects)
403. [Why is `eval()` dangerous?](#403-why-is-eval-dangerous)

#### Advanced

404. [What are async generators and when would you use them?](#404-what-are-async-generators-and-when-would-you-use-them)
405. [What is the `Atomics` API and when do you need it?](#405-what-is-the-atomics-api-and-when-do-you-need-it)
406. [What is `WeakRef` and `FinalizationRegistry`?](#406-what-is-weakref-and-finalizationregistry)
407. [What are transducers?](#407-what-are-transducers)

#### Senior / Scenario

408. [How would you architect a state management system in vanilla JavaScript?](#408-how-would-you-architect-a-state-management-system-in-vanilla-javascript)
409. [How would you compile a simple expression language to JavaScript?](#409-how-would-you-compile-a-simple-expression-language-to-javascript)
410. [How would you implement a JavaScript interpreter in JavaScript?](#410-how-would-you-implement-a-javascript-interpreter-in-javascript)
411. [How would you build an offline-first JavaScript web app?](#411-how-would-you-build-an-offline-first-javascript-web-app)
412. [Design a JavaScript plugin system.](#412-design-a-javascript-plugin-system)
413. [Situation: Classic loop closure bug – `var` in a for loop.](#413-situation-classic-loop-closure-bug-var-in-a-for-loop)
414. [Situation: `this` is `undefined` in a class method — what are the possible causes?](#414-situation-this-is-undefined-in-a-class-method-what-are-the-possible-causes)
415. [How would you build a JavaScript SDK for a REST API?](#415-how-would-you-build-a-javascript-sdk-for-a-rest-api)
416. [Situation: An async function is silently failing — how do you debug it?](#416-situation-an-async-function-is-silently-failing-how-do-you-debug-it)
417. [You have a feature using closures, but it's causing unexpected behavior in production — how would you debug and fix it?](#417-you-have-a-feature-using-closures-but-its-causing-unexpected-behavior-in-production-how-would-you-debug-and-fix-it)
418. [How would you implement an event emitter from scratch?](#418-how-would-you-implement-an-event-emitter-from-scratch)
419. [How would you design a client-side caching layer?](#419-how-would-you-design-a-client-side-caching-layer)
420. [How would you implement debounce and throttle from scratch?](#420-how-would-you-implement-debounce-and-throttle-from-scratch)
421. [How would you implement a publish/subscribe system with topics and wildcards?](#421-how-would-you-implement-a-publishsubscribe-system-with-topics-and-wildcards)
422. [Situation: `JSON.stringify` is dropping data — explain why and how to fix it.](#422-situation-jsonstringify-is-dropping-data-explain-why-and-how-to-fix-it)
423. [How would you build an undo/redo system?](#423-how-would-you-build-an-undoredo-system)
424. [How would you implement a simple reactive system (like Vue's reactivity)?](#424-how-would-you-implement-a-simple-reactive-system-like-vues-reactivity)
425. [How would you architect a real-time collaborative editing feature?](#425-how-would-you-architect-a-real-time-collaborative-editing-feature)
426. [Situation: Your third-party script is blocking the main thread — how do you fix it?](#426-situation-your-third-party-script-is-blocking-the-main-thread-how-do-you-fix-it)
427. [How would you implement a simple dependency injection container?](#427-how-would-you-implement-a-simple-dependency-injection-container)
428. [How would you implement a persistent undo history that survives page reload?](#428-how-would-you-implement-a-persistent-undo-history-that-survives-page-reload)
429. [How would you implement a simple template engine?](#429-how-would-you-implement-a-simple-template-engine)
430. [How would you implement an event emitter?](#430-how-would-you-implement-an-event-emitter)
431. [How would you implement infinite scrolling with vanilla JS?](#431-how-would-you-implement-infinite-scrolling-with-vanilla-js)
432. [Situation & Scenario](#432-situation-scenario)
433. [Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.](#433-explain-call-apply-and-bind-with-use-cases-implement-polyfills)
434. [Implement `map`, `reduce`, `filter` from scratch.](#434-implement-map-reduce-filter-from-scratch)
435. [Implement a custom hook like `useDebounce` or `useFetch` (React).](#435-implement-a-custom-hook-like-usedebounce-or-usefetch-react)
436. [What is circular dependency and how do you handle it?](#436-what-is-circular-dependency-and-how-do-you-handle-it)

### Output & Tricky Questions

#### Intermediate

437. [What is the output of `0.1 + 0.2 === 0.3` and why?](#437-what-is-the-output-of-01-02-03-and-why)
438. [What is the output: `typeof null`?](#438-what-is-the-output-typeof-null)
439. [What is the output: `[] == ![]`?](#439-what-is-the-output)
440. [What is the output?](#440-what-is-the-output)
441. [What is the output? (Node.js)](#441-what-is-the-output-nodejs)
442. [What is the output or behavior?](#442-what-is-the-output-or-behavior)
443. [Implement: Given a string, find the first non-repeating character.](#443-implement-given-a-string-find-the-first-non-repeating-character)
444. [Implement: Flatten array to any depth.](#444-implement-flatten-array-to-any-depth)
445. [Implement: Check if a string is a palindrome (ignoring spaces/punctuation).](#445-implement-check-if-a-string-is-a-palindrome-ignoring-spacespunctuation)
446. [Implement: Deep merge two objects.](#446-implement-deep-merge-two-objects)
447. [Implement: `chunk(array, size)` — split array into chunks.](#447-implement-chunkarray-size-split-array-into-chunks)
448. [Implement: `pipe` with error handling and async support.](#448-implement-pipe-with-error-handling-and-async-support)
449. [Implement: `once` — function that can only be called once.](#449-implement-once-function-that-can-only-be-called-once)
450. [Implement: `compose` vs `pipe` — output prediction.](#450-implement-compose-vs-pipe-output-prediction)
451. [What is the output? (Most asked JS output question)](#451-what-is-the-output-most-asked-js-output-question)
452. [What is the output? (Ultimate async challenge)](#452-what-is-the-output-ultimate-async-challenge)

---

## JavaScript Fundamentals

### Junior

#### 1. What is JavaScript and where does it run?

[↑ Back to Table of Contents](#table-of-contents)


JavaScript is a high-level, interpreted, single-threaded, dynamically typed programming language originally designed for web browsers. It now runs in many environments (Node.js, Deno, Bun, embedded systems) thanks to standalone JS engines like V8, SpiderMonkey, and JavaScriptCore.

---

#### 2. What are the primitive types in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


`string`, `number`, `bigint`, `boolean`, `undefined`, `null`, `symbol`. Primitives are immutable and stored by value. Everything else (objects, arrays, functions) is an object stored by reference.

---

#### 3. What is JavaScript and where can it run?

[↑ Back to Table of Contents](#table-of-contents)


JavaScript is a high-level, dynamic, interpreted programming language originally designed for browser scripting. Today it runs in browsers (via JS engines like V8 in Chrome), on servers (Node.js), in mobile apps (React Native), desktop apps (Electron), and IoT devices – anywhere a JS runtime is embedded.

---

#### 4. What are the primitive data types in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


There are 7 primitives: `string`, `number`, `boolean`, `undefined`, `null`, `symbol` (ES6), and `bigint` (ES2020). Everything else is an `object` (arrays, functions, dates, etc. are objects). Primitives are immutable and stored by value; objects are stored by reference.

---

#### 5. What is strict mode?

[↑ Back to Table of Contents](#table-of-contents)


`'use strict'` at the top of a file or function enables strict mode. It prevents use of undeclared variables, disables `with`, makes `this` undefined in regular functions (not `window`), disallows duplicate parameter names, and throws on otherwise-silent errors.

---

### Intermediate

#### 6. What is the ECMAScript specification?

[↑ Back to Table of Contents](#table-of-contents)


ECMAScript (ES) is the standardized specification that JavaScript implements, maintained by TC39. Versions like ES5, ES6/ES2015, ES2020, ES2022 added major features. New proposals move through a 5-stage process (Stage 0–4) before being incorporated into the spec.

---

#### 7. What is `typeof` and what are its quirks?

[↑ Back to Table of Contents](#table-of-contents)


`typeof` returns a string indicating the type. Notable quirks: `typeof null === 'object'` (historical bug), `typeof function(){}  === 'function'` (special case), `typeof undeclaredVar === 'undefined'` (safe without ReferenceError).

---

#### 8. What is type coercion?

[↑ Back to Table of Contents](#table-of-contents)


JavaScript automatically converts types when operating on mixed-type values. Example: `'5' - 2 = 3` (string coerced to number), `'5' + 2 = '52'` (number coerced to string for `+`). Implicit coercion can cause bugs; use explicit conversion (`Number()`, `String()`, `Boolean()`) for clarity.

---

#### 9. What is `NaN` and how do you check for it?

[↑ Back to Table of Contents](#table-of-contents)


`NaN` (Not-a-Number) is the result of invalid numeric operations (`'abc' * 2`, `0/0`). Its type is `'number'`. Weirdly, `NaN !== NaN`. Check with `Number.isNaN(value)` (strict – only true for actual NaN) or `isNaN(value)` (coerces first, less reliable).

---

#### 10. What is the difference between `null` and `undefined`?

[↑ Back to Table of Contents](#table-of-contents)


`undefined`: a variable has been declared but not assigned a value; also the return value of functions that don't return anything. `null`: an intentional absence of value, explicitly assigned by a developer. `typeof undefined === 'undefined'`; `typeof null === 'object'` (a historic bug in JS).

---

#### 11. What is the difference between JavaScript and ECMAScript?

[↑ Back to Table of Contents](#table-of-contents)


ECMAScript (ES) is the specification/standard. JavaScript is the most popular implementation of that standard. TC39 (a committee) maintains the ECMAScript spec and releases yearly updates (ES2015/ES6, ES2016… ES2024). Browsers and Node.js implement these features over time.

---

#### 12. Is JavaScript compiled or interpreted?

[↑ Back to Table of Contents](#table-of-contents)


Technically both. Modern JS engines (V8, SpiderMonkey) use JIT (Just-In-Time) compilation. Code is first parsed into an AST, then compiled to bytecode, then hot paths are compiled to optimized machine code at runtime. JavaScript starts running your code immediately without making you wait (like an interpreter). But as it runs, it secretly figures out which parts of your code are used the most and fully translates them into lightning-fast machine code in the background (like a compiler).

---

#### 13. What is the JavaScript engine and how does it work?

[↑ Back to Table of Contents](#table-of-contents)


A JavaScript engine is like a smart translator and office manager for your code. It does three main things:

Translates & Runs: It reads your text code, converts it into a quick shorthand (bytecode) the computer understands, and runs it immediately.

Speeds Up (JIT): It watches your code as it runs. If it sees a specific action you repeat constantly, it instantly upgrades that part into ultra-fast machine code.

Cleans Up (Garbage Collection): It holds onto the data you are currently using, and automatically throws away old data you no longer need so your computer doesn't slow down or crash.

---

#### 14. What is single-threaded execution in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


JavaScript has one call stack and one thread of execution – it can only do one thing at a time. Long-running tasks block everything else. The event loop enables asynchronous behavior by offloading tasks (timers, network) to Web APIs and processing their callbacks when the stack is empty.

---

#### 15. What is the `typeof` operator?

[↑ Back to Table of Contents](#table-of-contents)


Returns a string describing the type of a value: `'string'`, `'number'`, `'boolean'`, `'undefined'`, `'object'`, `'function'`, `'symbol'`, `'bigint'`. Known quirks: `typeof null === 'object'` (bug), `typeof function(){} === 'function'` (functions are objects but get their own typeof result).

---

#### 16. What is polymorphism in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Different objects responding to the same interface/method call in different ways. In JS, achieved through method overriding in subclasses. Since JS is duck-typed, any object with the right method can be used polymorphically without explicit inheritance.

---

#### 17. How does JavaScript handle integer overflow?

[↑ Back to Table of Contents](#table-of-contents)


JavaScript's `Number` type is a 64-bit IEEE 754 float. Safe integer range is `-(2^53 - 1)` to `2^53 - 1` (`Number.MAX_SAFE_INTEGER`). Beyond this, integers lose precision (no overflow/crash, just wrong values). Use `BigInt` for arbitrary-precision integers.

---

#### 18. What are the tricky parts of `==` type coercion rules?

[↑ Back to Table of Contents](#table-of-contents)


Key rules: if one side is a number, convert the other to number. If one side is a boolean, convert boolean to number first. Objects are converted to primitives via `valueOf()` then `toString()`. `null == undefined` is `true`, but `null == 0` is `false`. `NaN == NaN` is `false`. These inconsistencies are why `===` is always preferred.

---

#### 19. What is the difference between pass-by-value and pass-by-reference?

[↑ Back to Table of Contents](#table-of-contents)


Primitives are passed by value — a copy is made. Objects (including arrays) are passed by reference — both the caller and the function reference the same object in memory. However, reassigning the parameter doesn't affect the original; only mutations do.

---

## Variables, Scope & Execution Context

### Junior

#### 20. What is hoisting?

[↑ Back to Table of Contents](#table-of-contents)


Hoisting is JavaScript's behavior where variable and function declarations are moved to the top of their containing scope during compilation.

- `var` declarations are hoisted and initialized with `undefined`.
- `let` and `const` are hoisted but remain uninitialized (in the Temporal Dead Zone).
- Function declarations are hoisted entirely (both name and body), so they can be called before they appear in code.

```javascript
console.log(foo); // undefined (var)
var foo = 'bar';

sayHello(); // "Hello!" – function declaration hoisted
function sayHello() { console.log("Hello!"); }

// Arrow function (assigned to var) – only variable is hoisted, not the assignment
// sayHi(); // TypeError: sayHi is not a function
var sayHi = () => console.log("Hi");
```

---

#### 21. What is scope? Explain global, function, and block scope.

[↑ Back to Table of Contents](#table-of-contents)


**Scope** defines where variables and functions are accessible during runtime.

- **Global scope**: Variables declared outside any function or block are globally accessible. In browsers, global variables become properties of `window`.
- **Function scope**: Variables declared with `var`, `let`, or `const` inside a function are accessible only within that function.
- **Block scope**: Introduced with ES6; `let` and `const` are block-scoped, meaning they are confined to the nearest `{ }` (e.g., `if`, `for`, `while`). `var` ignores block scope.

```javascript
if (true) {
  var a = 1;   // function-scoped (or global)
  let b = 2;   // block-scoped
  const c = 3; // block-scoped
}
console.log(a); // 1
// console.log(b); // ReferenceError: b is not defined
// console.log(c); // ReferenceError: c is not defined
```

---

### Intermediate

#### 22. What is variable shadowing?

[↑ Back to Table of Contents](#table-of-contents)


Declaring a variable in an inner scope with the same name as one in an outer scope. The inner declaration shadows the outer one within its scope. The outer variable is unchanged and becomes accessible again outside the inner scope.

---

#### 23. Stuffing Variables Inside Text (Interpolation)

[↑ Back to Table of Contents](#table-of-contents)


Instead of using the plus sign (`+`) to awkwardly glue text and variables together, you can inject variables or math directly into the text using the **`${}`** placeholder. JavaScript will evaluate whatever is inside the brackets on the fly.

* **The Old, Messy Way:** ```javascript
"Hello, " + name + "! You are " + (age + 1) + " next year.";
```

```


* **The New, Clean Way:** ```javascript
`Hello, ${name}! You are ${age + 1} next year.`;
```


```

---

#### 24. What is variable hoisting?

[↑ Back to Table of Contents](#table-of-contents)


Declarations (not initializations) are moved to the top of their scope during compilation. `var` declarations are hoisted and initialized to `undefined`. `let` and `const` are hoisted but not initialized — accessing them before declaration throws a ReferenceError (Temporal Dead Zone).

---

#### 25. What is the Temporal Dead Zone (TDZ)?

[↑ Back to Table of Contents](#table-of-contents)


The period between the start of a block scope and the `let`/`const` declaration being executed. Accessing the variable in this window throws a `ReferenceError`. It exists because hoisting moves the binding to the top of the block but doesn't initialize it until the declaration line is reached.

---

#### 26. What is scope in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Scope defines where variables are accessible. JavaScript has global scope, function scope, and block scope (ES6+). The scope chain is the hierarchy of scopes searched when resolving a variable name, from innermost outward.

---

#### 27. What is the execution context?

[↑ Back to Table of Contents](#table-of-contents)


An abstract concept representing the environment in which JavaScript code runs. Each context has a Variable Environment (scope), a `this` binding, and an Outer Environment reference. The Global Execution Context is created first; function calls create new ones pushed onto the Call Stack.

---

#### 28. What is scope chain resolution?

[↑ Back to Table of Contents](#table-of-contents)


When a variable is referenced, JS searches the current scope first, then each outer scope up to global. If not found, a `ReferenceError` is thrown. This chain is established at function definition time (lexical scoping).

---

#### 29. What is the module scope?

[↑ Back to Table of Contents](#table-of-contents)


In ES modules (`.mjs` or `<script type="module">`), the top-level is module scope — not global. Variables declared at the top are not on `window`. Modules also enforce strict mode by default.

---

#### 30. What is the difference between global, function, and block scope?

[↑ Back to Table of Contents](#table-of-contents)


Global scope: variables declared outside any function/block, accessible everywhere. Function scope: variables declared with `var` inside a function, accessible only within that function. Block scope: variables declared with `let`/`const` inside `{}`, accessible only within that block.

---

#### 31. What is the scope chain?

[↑ Back to Table of Contents](#table-of-contents)


When JS looks up a variable, it starts in the current scope and moves outward to enclosing scopes until it reaches the global scope. This chain of scopes is the scope chain. If not found in global scope, a `ReferenceError` is thrown.

---

#### 32. What is lexical scope?

[↑ Back to Table of Contents](#table-of-contents)


The scope of a variable is determined by its position in the source code at write time, not at runtime. Inner functions have access to variables in their outer (enclosing) functions. This is decided when the code is parsed, not when it runs.

---

#### 33. What is an execution context?

[↑ Back to Table of Contents](#table-of-contents)


An execution context is simply the environment or workspace that JavaScript sets up to run your code.

Think of it as a desk prepared for a specific task. Every time JavaScript runs a script or calls a function, it sets up a new desk with all the tools and information needed to do that specific job.

What is inside this workspace?
Every execution context holds three crucial things:

The Variables: The actual data and functions you created for this specific task.

The Scope Chain (Lexical Environment): A map that tells the code which other desks it is allowed to look at if it can't find a variable locally.

The this Keyword: A pointer that tells the code who currently "owns" this workspace.

The Two Main Types
Global Execution Context (The Main Office): This is the very first desk created when your program starts up. There is only one global context, and it handles all the code that isn't inside a function. It stays active until you close the webpage or app.

Function Execution Context (Temporary Project Rooms): Every single time you call (or execute) a function, JavaScript instantly builds a brand new, temporary desk just for that function. Once the function finishes its job and returns a value, that desk is completely packed up and thrown away.

---

#### 34. What is the difference between function scope and block scope?

[↑ Back to Table of Contents](#table-of-contents)


Function scope (`var`): the variable is accessible anywhere within the enclosing function. Block scope (`let`/`const`): the variable is accessible only within the `{}` block it was declared in (if statement, for loop, etc.). This difference matters most inside control structures like loops and conditionals.

The core difference is: var creates one single variable that gets reused over and over, while let creates a brand-new variable for every single turn (iteration) of the loop.

This difference matters most when you introduce a delay, like a setTimeout.

The Code Example
Look at these two loops. They look identical, but they behave completely differently:

JavaScript
// Using VAR
for (var i = 1; i <= 3; i++) {
  setTimeout(() => console.log("var:", i), 1000);
}

// Using LET
for (let i = 1; i <= 3; i++) {
  setTimeout(() => console.log("let:", i), 1000);
}
The Output (after 1 second):
var prints: 4, 4, 4

let prints: 1, 2, 3

Why does this happen?
The var behavior (One shared bucket)
Because var is function-scoped, JavaScript creates just one variable named i.

The loop runs instantly from 1 to 3, and ends when i becomes 4.

One second later, the setTimeout timers wake up and look for i.

They all look at that same single bucket, which now holds the number 4. So, it prints 4 three times.

The let behavior (Unique buckets)
Because let is block-scoped, JavaScript creates a brand-new i variable for every single round of the loop.

In round 1, a bucket is made where i = 1.

In round 2, a fresh bucket is made where i = 2.

In round 3, another fresh bucket is made where i = 3.

One second later, each setTimeout looks back at the specific, unique bucket created during its specific round. So, it prints 1, 2, 3.

---

#### 35. What are the differences between `var`, `let`, and `const`?

[↑ Back to Table of Contents](#table-of-contents)


`var`: function-scoped, hoisted, can be re-declared, no block scoping. `let`: block-scoped, not hoisted usably (TDZ), cannot be re-declared. `const`: block-scoped, must be initialized, cannot be reassigned (though object contents can be mutated). Prefer `const` by default, `let` when reassignment is needed, avoid `var`.

---

#### 36. What is the call stack?

[↑ Back to Table of Contents](#table-of-contents)


A stack data structure that tracks function calls. When a function is called, its execution context is pushed onto the stack. When it returns, it's popped off. If the stack overflows (infinite recursion), you get a `RangeError: Maximum call stack size exceeded`.

---

#### 37. What is the difference between `var`, `let`, and `const`?

[↑ Back to Table of Contents](#table-of-contents)


`var`: function-scoped, hoisted and initialized to `undefined`, can be redeclared. `let`: block-scoped, hoisted but not initialized (TDZ), cannot be redeclared. `const`: block-scoped, must be initialized at declaration, cannot be reassigned (but object contents can be mutated). Always prefer `const` by default, `let` when reassignment is needed, avoid `var`.

---

## Functions & Functional Programming

### Junior

#### 38. What is a callback function?

[↑ Back to Table of Contents](#table-of-contents)


A function passed as an argument to another function and called later (usually after an async operation or event). The foundation of async JavaScript before Promises. Still used in event handlers, array methods (`forEach`, `map`), and APIs like `setTimeout`.

**What**  
A callback function is a function you pass into another function as an argument, so that it can be executed later (often after a task completes or an event occurs).

**Why**  
- Enables asynchronous behavior (code doesn’t block while waiting).  
- Allows custom logic to be injected into generic functions (like array methods).  
- Forms the foundation of event-driven programming.

**When**  
- Waiting for an asynchronous operation (file read, API call, timer).  
- Handling user interactions (clicks, key presses).  
- Reusing a function’s skeleton while changing the “what to do next” part.

**Where** (real examples)

```js
// 1. Timers
setTimeout(() => console.log('Done'), 1000);

// 2. Event listeners
button.addEventListener('click', () => alert('Clicked'));

// 3. Array methods
[1, 2, 3].map(x => x * 2);   // callback: x => x*2

// 4. Custom async operation
function fetchData(url, callback) {
  // simulate async
  setTimeout(() => callback('Data from ' + url), 500);
}
fetchData('/api', data => console.log(data));
```

> **Note**: In modern JS, promises and `async/await` often replace callbacks for complex async flows, but callbacks are still everywhere in event handling and simple async APIs.

---

#### 39. What is a callback and what is callback hell?

[↑ Back to Table of Contents](#table-of-contents)


A callback is a function passed to another function to be called later. Callback hell: deeply nested callbacks where each async step requires another callback, creating a pyramid of doom. Makes code hard to read, debug, and maintain. Solved by Promises and async/await.

---

### Intermediate

#### 40. Explain the difference between eager and lazy evaluation in JavaScript.

[↑ Back to Table of Contents](#table-of-contents)


Eager: values are computed immediately when defined. Lazy: values are computed only when needed. Generators implement lazy sequences. `&&` and `||` are lazy (short-circuit). Proxies enable lazy object initialization. Lazy evaluation avoids unnecessary computation and enables infinite sequences.

---

#### 41. What is IIFE (Immediately Invoked Function Expression) and why was it used?

[↑ Back to Table of Contents](#table-of-contents)


`(function() { /* code */ })()` — a function defined and immediately called. Used pre-ES6 to create a local scope and avoid polluting the global namespace. With `let`/`const` and ES modules, IIFEs are rarely needed today.

---

#### 42. What is the difference between a function declaration and a function expression?

[↑ Back to Table of Contents](#table-of-contents)


Declaration: `function foo() {}` — hoisted in its entirety, can be called before definition. Expression: `const foo = function() {}` — not hoisted; calling before initialization throws a `ReferenceError` (or `TypeError` for `var`).

---

#### 43. What are arrow functions and how do they differ from regular functions?

[↑ Back to Table of Contents](#table-of-contents)


Arrow functions (`() => {}`) are concise and have no own `this`, `arguments`, `super`, or `new.target`. They inherit `this` lexically from the enclosing scope. They cannot be used as constructors (`new` throws), cannot be used as methods with a dynamic `this`, and don't have a `prototype` property.

---

#### 44. What is a higher-order function?

[↑ Back to Table of Contents](#table-of-contents)


A function that takes one or more functions as arguments, returns a function, or both. Examples: `Array.prototype.map`, `filter`, `reduce`, `setTimeout`. They're the backbone of functional programming in JavaScript.

---

#### 45. What is function composition?

[↑ Back to Table of Contents](#table-of-contents)


Combining multiple functions where the output of one becomes the input of the next: `compose(f, g)(x)` = `f(g(x))`. Libraries like Lodash/fp and Ramda provide `compose`/`pipe`. Core to functional programming – build complex behavior from small, pure functions.
**What**  
Function composition combines simple functions into a pipeline. The output of one function becomes the input of the next.  
`compose(f, g)(x)` means `f(g(x))` — right-to-left. `pipe` is left-to-right.

**Why**  
- Build complex behavior from small, pure, reusable functions.  
- Makes code more readable, declarative, and easier to test.  
- Avoids nesting lots of function calls.

**When**  
- Processing data through multiple transformations (e.g., sanitize, format, display).  
- Functional programming pipelines (map → filter → reduce).  
- Middleware patterns (request processing, event handling).  
- Anytime you can break a task into discrete, composable steps.

 1. Data formatting pipeline
Transform a raw user input into a clean, formatted string
2. Request middleware in Express/Node
Each middleware is a function that modifies the request/response, and composition chains them.

---

#### 46. What is a pure function?

[↑ Back to Table of Contents](#table-of-contents)


A function that: (1) always returns the same output for the same input, and (2) has no side effects (doesn't modify external state, make network calls, write to DOM, etc.). Pure functions are predictable, testable, and easy to reason about.

---

#### 47. What is a recursive function and what is tail call optimization?

[↑ Back to Table of Contents](#table-of-contents)


A function that calls itself. Each call adds a frame to the call stack. Tail call optimization (TCO) — when the recursive call is the last operation — allows the engine to reuse the current stack frame. TCO is specified in ES6 but only Safari implements it reliably.

---

#### 48. What are callbacks and what problems do they have?

[↑ Back to Table of Contents](#table-of-contents)


A function passed as an argument to be called when an async operation completes. Problems: callback hell (deeply nested, hard to read), difficult error handling, no return values, inversion of control. Solved by Promises and async/await.

---

#### 49. What are the core principles of functional programming?

[↑ Back to Table of Contents](#table-of-contents)


Pure functions, immutability, function composition, avoiding shared state and side effects, declarative style. FP makes code more predictable and testable. JavaScript is multi-paradigm — FP can be applied selectively.

---

#### 50. What is the difference between function declaration and function expression?

[↑ Back to Table of Contents](#table-of-contents)


Function declaration: `function foo() {}` — hoisted fully, available before its line in code. Function expression: `const foo = function() {}` — not hoisted (the variable is hoisted as `undefined`). Arrow functions are always expressions. Named function expressions are useful for recursion and stack traces.

---

#### 51. What is the difference between a method and a function?

[↑ Back to Table of Contents](#table-of-contents)


A function is a standalone callable. A method is a function that is a property of an object. When called as a method (`obj.method()`), `this` refers to the object. When called as a standalone function, `this` is `undefined` (strict mode) or the global object.

**What**  
- A **function** is a standalone block of code, defined independently.  
- A **method** is a function that belongs to an object (a property whose value is a function).  
The key difference is the value of `this` — inside a method, `this` refers to the object the method is called on; inside a regular function call, `this` is `undefined` (strict mode) or the global object.

**Why**  
- Methods allow objects to encapsulate behavior that operates on their own data.  
- Knowing the difference helps avoid bugs with `this` (e.g., when passing a method as a callback, you might lose the intended `this`).

**When / Where**  
- Use **functions** for general reusable logic, independent of any object:  
  `function add(a, b) { return a + b; }`
- Use **methods** to define how an object behaves, acting on its own properties:  
  ```js
  const user = {
    name: 'Alice',
    greet() { console.log(`Hi, I'm ${this.name}`); }
  };
  user.greet(); // this = user
  ```
- When you need a method’s `this` bound permanently (e.g., in event handlers), you might use `.bind()` or arrow functions.

In short: **all methods are functions, but not all functions are methods** — the distinction is how they’re called and what `this` they see.

---

#### 52. What is functional programming?

[↑ Back to Table of Contents](#table-of-contents)


A programming paradigm treating computation as evaluation of mathematical functions. Key principles: pure functions, immutability, no side effects, function composition, declarative style. JavaScript supports both OOP and FP — you can mix them. Libraries: Ramda, Lodash/fp.

---

#### 53. What is function composition vs piping?

[↑ Back to Table of Contents](#table-of-contents)


Both combine functions. **Composition** (`compose`): right-to-left — `compose(f, g)(x)` = `f(g(x))`. **Piping** (`pipe`): left-to-right — `pipe(g, f)(x)` = `f(g(x))`. Pipe is more readable for most developers (data flows left to right). Both create new functions from combining existing ones.

---

#### 54. Callback functions – what are they? Callback hell.

[↑ Back to Table of Contents](#table-of-contents)


A **callback** is a function passed as an argument to another function, to be executed later. Callback hell refers to deeply nested callbacks that become hard to read and maintain:

```javascript
getUser((user) => {
  getOrders(user.id, (orders) => {
    getOrderDetails(orders[0].id, (details) => {
      // ...
    });
  });
});
```

Solutions: Promises, `async/await`.

---

##### `this`, Call Context & Binding

---

#### 55. What is the `arguments` object?

[↑ Back to Table of Contents](#table-of-contents)


An array-like object available inside regular functions (not arrow functions) containing all passed arguments. It's not a real array (no `map`, `filter`). In modern JS, prefer rest parameters. `arguments` is useful in legacy code or when you need to accept arbitrary number of args without naming them.

The **`arguments` object** is an array-like collection of all values passed to a regular function. It’s automatically available inside the function body.

```js
function showArgs() {
  console.log(arguments);
}

showArgs(1, 'hello', true); // [1, 'hello', true]  (array-like)
```

**Key points:**
- It’s not a real array — no `.map()`, `.filter()`, etc.
- Works only in regular functions (not arrow functions).
- In modern JavaScript, **rest parameters** (`...args`) are preferred because they give you an actual array and clearer code.  
  `function showArgs(...args) { console.log(args); }`

---

#### 56. What are rest parameters and the spread operator?

[↑ Back to Table of Contents](#table-of-contents)


Rest (`...args`): collects remaining arguments into an array inside a function definition. Spread (`...arr`): expands an iterable into individual elements at a call site or in an array/object literal. Same syntax, opposite directions.

---

#### 57. No `arguments` Object

[↑ Back to Table of Contents](#table-of-contents)


* **Regular functions** have a built-in local variable called `arguments` that contains a list of all the values passed into the function.
* **Arrow functions** do not have this. If you need a list of inputs, you must use modern rest parameters instead (like `(...args) => {}`).

---

#### 58. What is the rest parameter (`...args`)?

[↑ Back to Table of Contents](#table-of-contents)


Collects all remaining arguments into an array: `function sum(...nums) { return nums.reduce((a,b) => a+b, 0); }`. Must be the last parameter. Unlike `arguments`, rest parameters are real arrays with all array methods.

---

#### 59. What does "first-class functions" mean?

[↑ Back to Table of Contents](#table-of-contents)


Functions can be assigned to variables, passed as arguments, returned from other functions, and stored in data structures — just like any other value. This enables higher-order functions, callbacks, currying, and functional programming patterns.

---

#### 60. What is a first-class function?

[↑ Back to Table of Contents](#table-of-contents)


Functions are first-class citizens in JavaScript — they can be assigned to variables, passed as arguments to other functions, returned from functions, stored in arrays/objects, and have properties attached to them. This enables functional programming patterns.

---

#### 61. What is partial application?

[↑ Back to Table of Contents](#table-of-contents)


Fixing some arguments of a function, producing a function with fewer arguments. Unlike currying (one argument at a time), partial application fixes any number. `const double = multiply.bind(null, 2)`. Useful for creating specialized functions from general ones.

---

### Advanced

#### 62. Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)

[↑ Back to Table of Contents](#table-of-contents)


Closures are a fundamental feature that allows functions to “remember” their lexical scope even when executed outside that scope.

**Use cases**:
- **Data privacy**: Encapsulate variables not exposed globally (e.g., module pattern, factory functions).
- **React Hooks**: `useState` and `useEffect` rely on closures to maintain state across renders.
- **Callbacks**: Preserve context in asynchronous operations.
- **Memoization**: Cache results of expensive functions (e.g., `useMemo`, `_.memoize`).
- **Function factories**: Create functions with pre‑configured arguments.

---

##### Functions

---

#### 63. What is currying?

[↑ Back to Table of Contents](#table-of-contents)


Transforming a function that takes multiple arguments into a chain of functions each taking one argument: `f(a, b, c)` becomes `f(a)(b)(c)`. Enables partial application and composition. Libraries like Lodash provide `_.curry`.

---

#### 64. What is function currying?

[↑ Back to Table of Contents](#table-of-contents)


Transforming a function that takes multiple arguments into a sequence of functions each taking a single argument. `add(1)(2)(3)` instead of `add(1, 2, 3)`. Enables partial application and functional composition. Useful for creating reusable, specialized functions.

```javascript
const curry = fn => {
  return function curried(...args) {
    if (args.length >= fn.length) return fn(...args);
    return (...more) => curried(...args, ...more);
  };
};
```
**Function currying** transforms a multi-argument function into a chain of single-argument functions.  
So instead of `add(1, 2, 3)` you call `add(1)(2)(3)`.

- Each step returns a new function until all expected arguments are supplied.
- It enables **partial application** – fixing some arguments now, the rest later.
- In your code, `curry(fn)` checks if enough arguments have been collected (`args.length >= fn.length`). If yes, it calls the original function; if not, it returns a new function that waits for more arguments.

Currying makes it easy to create reusable, specialized functions from a generic one.

---

#### 65. What is memoization?

[↑ Back to Table of Contents](#table-of-contents)


An optimization technique that caches the results of function calls. On subsequent calls with the same arguments, returns the cached result instead of recomputing. Useful for expensive pure functions. Trade-off: memory vs speed.

```javascript
function memoize(fn) {
  const cache = new Map();
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache.has(key)) return cache.get(key);
    const result = fn.apply(this, args);
    cache.set(key, result);
    return result;
  };
}
```

---

### Senior / Scenario

#### 66. Design a rate limiter function in JavaScript.

[↑ Back to Table of Contents](#table-of-contents)


Track call timestamps in a sliding window or token bucket. `function rateLimit(fn, limit, window) { let calls = []; return (...args) => { const now = Date.now(); calls = calls.filter(t => now - t < window); if (calls.length >= limit) throw new Error('Rate limited'); calls.push(now); return fn(...args); }; }`. For async queuing instead of throwing, use a Promise queue with delay.

---

#### 67. How would you implement a deep equality function?

[↑ Back to Table of Contents](#table-of-contents)


Handle primitives with `===`. Handle `null` explicitly. Check same type and same constructor. For arrays, check length then recurse over indices. For objects, check same keys then recurse over values. Handle `Date`, `RegExp`, `Map`, `Set`, and circular references. `Object.is` for NaN/+0/-0 edge cases.

---

#### 68. Design a pipeline function (like `|>` operator) in JavaScript.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const pipe = (...fns) => x => fns.reduce((acc, fn) => fn(acc), x);
const process = pipe(trim, toLowerCase, removeSpecialChars, truncate(50));
process(input);
```
For async pipelines: `const pipeAsync = (...fns) => x => fns.reduce(async (acc, fn) => fn(await acc), x)`.

---

#### 69. Implement a deep clone function.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function deepClone(value) {
  if (value === null || typeof value !== 'object') return value;
  if (value instanceof Date) return new Date(value);
  if (value instanceof Array) return value.map(deepClone);
  if (value instanceof Map) return new Map([...value].map(([k,v]) => [deepClone(k), deepClone(v)]));
  if (value instanceof Set) return new Set([...value].map(deepClone));
  return Object.fromEntries(Object.entries(value).map(([k,v]) => [k, deepClone(v)]));
}
// Note: use structuredClone() in production — handles circular references and more types.
```

---

#### 70. Implement a debounce function from scratch.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function debounce(fn, delay) {
  let timer = null;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => {
      fn.apply(this, args);
      timer = null;
    }, delay);
  };
}
```

---

#### 71. Implement a throttle function from scratch.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function throttle(fn, limit) {
  let lastCall = 0;
  return function(...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      return fn.apply(this, args);
    }
  };
}
```

---

#### 72. How would you implement `curry` function from scratch?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn.apply(this, args);
    }
    return function(...more) {
      return curried.apply(this, args.concat(more));
    };
  };
}
const add = curry((a, b, c) => a + b + c);
add(1)(2)(3); // 6
add(1, 2)(3); // 6
add(1)(2, 3); // 6
```

---

#### 73. How would you implement memoization with a complex cache key?

[↑ Back to Table of Contents](#table-of-contents)


For single-argument functions, a `Map` is sufficient. For multiple arguments, serialize args: `JSON.stringify(args)` (fast but fails for functions, undefined, circular refs). For robust solution: use a WeakMap for object args (prevents memory leaks) with a trie-like structure for multiple args (as in libraries like `memoize-one`).

---

#### 74. Implement debounce and throttle functions.

[↑ Back to Table of Contents](#table-of-contents)


**Debounce**: Delays function execution until after a period of inactivity. Useful for search inputs, window resize.
```javascript
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}
```

**Throttle**: Ensures a function is called at most once per interval. Useful for scroll events, button clicks.
```javascript
function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => (inThrottle = false), limit);
    }
  };
}
```

---

#### 75. Implement a deep clone function (deep copy).

[↑ Back to Table of Contents](#table-of-contents)


**Using `structuredClone` (modern)**:
```javascript
const clone = structuredClone(original);
```

**Manual implementation** (handles objects, arrays, dates, maps, sets, and cyclic references):
```javascript
function deepClone(obj, map = new WeakMap()) {
  if (obj === null || typeof obj !== 'object') return obj;
  if (map.has(obj)) return map.get(obj);
  let clone;
  if (obj instanceof Date) clone = new Date(obj);
  else if (obj instanceof Map) {
    clone = new Map();
    map.set(obj, clone);
    obj.forEach((val, key) => clone.set(deepClone(key, map), deepClone(val, map)));
    return clone;
  } else if (obj instanceof Set) {
    clone = new Set();
    map.set(obj, clone);
    obj.forEach(val => clone.add(deepClone(val, map)));
    return clone;
  } else if (obj instanceof Array) {
    clone = [];
    map.set(obj, clone);
    obj.forEach((item, i) => clone[i] = deepClone(item, map));
  } else {
    clone = {};
    map.set(obj, clone);
    for (let key in obj) {
      if (obj.hasOwnProperty(key)) clone[key] = deepClone(obj[key], map);
    }
  }
  return clone;
}
```

---

## `this`, Call Context & Binding

### Intermediate

#### 76. Why does `this` lose context in callbacks?

[↑ Back to Table of Contents](#table-of-contents)


When a method is passed as a callback, it becomes a standalone function reference. The implicit binding (to the original object) is lost. Fix: `fn.bind(this)`, arrow function wrapper, or store `const self = this` (old pattern).

---

#### 77. How do arrow functions differ from regular functions regarding `this`?

[↑ Back to Table of Contents](#table-of-contents)


Arrow functions have no own `this`. They inherit `this` from the enclosing lexical scope at the time of definition. This makes them ideal for callbacks and event handlers where you want `this` to refer to the surrounding context, not the caller.

---

#### 78. The `this` Keyword (The Biggest Difference)

[↑ Back to Table of Contents](#table-of-contents)


* **Regular functions** create their own `this` value depending on *how* and *where* they are called. It can change dynamically.
* **Arrow functions** don't have their own `this`. They inherit `this` from the code surrounding them (lexical scope). They never change their mind about what `this` means.

---

#### 79. What are the four rules of `this` binding?

[↑ Back to Table of Contents](#table-of-contents)


1. **Default binding**: standalone function call → `this` is global object (or `undefined` in strict mode).
2. **Implicit binding**: method call `obj.fn()` → `this` is `obj`.
3. **Explicit binding**: `fn.call(ctx)`, `fn.apply(ctx)`, `fn.bind(ctx)` → `this` is `ctx`.
4. **New binding**: `new Fn()` → `this` is the newly created object.

Arrow functions ignore all these rules and use lexical `this`.
The `this` keyword in JavaScript is like a pronoun (like "he", "she", or "it"). Its meaning changes entirely depending on **how** a function is called.

Here are the 4 simple rules JavaScript uses to figure out what `this` means, ordered from lowest to highest priority:

---

#### 80. How does `this` work in arrow functions?

[↑ Back to Table of Contents](#table-of-contents)


Arrow functions have no own `this`. They capture `this` from the enclosing lexical scope at the time they are defined. This makes them ideal for callbacks and methods that need to access the outer `this`, eliminating the need for `const self = this` or `.bind(this)`.
Arrow functions do **not** have their own `this` keyword. Instead, they act like a sponge and **absorb the `this` value from the code directly surrounding them** (their parent scope).

Once an arrow function captures its parent's `this`, it is permanently locked in and can never change.

---

### Senior / Scenario

#### 81. Situation: `this` is `undefined` inside a class method used as a callback — how do you fix it?

[↑ Back to Table of Contents](#table-of-contents)


Three options: (1) bind in the constructor: `this.method = this.method.bind(this)`. (2) Use a class field arrow function: `method = () => {}` (most common in React). (3) Use an arrow function at the call site: `element.addEventListener('click', () => this.method())`.

---

#### 82. Situation: `this` is `undefined` or `window` inside a callback – why?

[↑ Back to Table of Contents](#table-of-contents)


When a method is passed as a callback, it loses its implicit binding. `setTimeout(obj.method, 0)` — `method` is called without `obj` as context. Fix: use `.bind(obj)`, wrap in arrow function `() => obj.method()`, or use an arrow function class field for the method definition.
When you pass an object's method as a callback, the function is detached from its object and called without context. In non‑strict mode `this` becomes the global object (`window`), in strict mode it’s `undefined`.

```js
const obj = {
  name: 'Alice',
  greet() { console.log(this.name); }
};

setTimeout(obj.greet, 0); // `this` is window/undefined → error
```

**Why** – `setTimeout(obj.greet)` passes the function reference, not the invocation `obj.greet()`. The call site inside `setTimeout` is just `callback()`, not `obj.callback()`, so the implicit binding is lost.

**Fix** (choose one):

1. **`bind`**: `setTimeout(obj.greet.bind(obj), 0)`
2. **Arrow wrapper**: `setTimeout(() => obj.greet(), 0)`
3. **Arrow method (class field)** if using a class:
   ```js
   class MyClass {
     greet = () => console.log(this.name);
   }
   ```

---

##### Objects, Arrays & Data Manipulation

---

## Objects, Arrays & Data Manipulation

### Junior

#### 83. What is a Set?

[↑ Back to Table of Contents](#table-of-contents)


A collection of unique values (no duplicates). Values can be of any type. `Set` has methods: `add`, `has`, `delete`, `clear`, `size`. Iterable. Useful for deduplication, tracking unique items, and set math (union/intersection with spread + filter).

---

### Intermediate

#### 84. What is immutability and how do you achieve it in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Never mutating data — always creating new values. Use spread/`Object.assign` for objects, `map`/`filter`/`slice` for arrays. Libraries: Immer (mutable-looking updates that produce immutable results). `Object.freeze` for shallow freezing.

---

#### 85. What is `Reflect` in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


A built-in object with static methods mirroring Proxy handler traps. `Reflect.get(obj, key)`, `Reflect.set(obj, key, val)`, `Reflect.has(obj, key)`, etc. Used inside Proxy handlers to invoke default behavior after custom logic. Also useful as a cleaner alternative to some `Object` methods.

---

#### 86. What are the most important array methods?

[↑ Back to Table of Contents](#table-of-contents)


Mutation: `push`, `pop`, `shift`, `unshift`, `splice`, `sort`, `reverse`. Non-mutating: `map`, `filter`, `reduce`, `find`, `findIndex`, `some`, `every`, `includes`, `indexOf`, `slice`, `flat`, `flatMap`, `concat`. Creation: `Array.from()`, `Array.of()`, `Array.isArray()`. Prefer non-mutating methods for predictability.

---

#### 87. How do you remove duplicates from an array?

[↑ Back to Table of Contents](#table-of-contents)


`[...new Set(arr)]` — most concise for primitives. `Array.from(new Set(arr))` — equivalent. For objects (by property): `arr.filter((v, i, a) => a.findIndex(t => t.id === v.id) === i)`. Set works by value equality for primitives; for objects, it checks reference equality.

---

#### 88. What is array destructuring?

[↑ Back to Table of Contents](#table-of-contents)


`const [a, b, ...rest] = arr` — extracts array elements into named variables by position. Default values: `const [a = 0] = []`. Swap variables: `[a, b] = [b, a]`. Skip elements: `const [, second] = arr`.

---

#### 89. What is object destructuring?

[↑ Back to Table of Contents](#table-of-contents)


`const {name, age: years = 0} = obj` — extracts properties by name into variables, with optional renaming and defaults. Nested: `const {address: {city}} = obj`. In function params: `function fn({name, age}) {}`.

---

#### 90. What is the spread operator for objects?

[↑ Back to Table of Contents](#table-of-contents)


`{...obj1, ...obj2}` creates a shallow merge. Later keys override earlier ones. Used to create modified copies without mutation: `const updated = {...user, age: 31}`. Only copies own enumerable properties.

---

#### 91. What is object shorthand property syntax?

[↑ Back to Table of Contents](#table-of-contents)


`const name = 'Alice'; const obj = {name}` is shorthand for `{name: name}`. Method shorthand: `{greet() {}}` instead of `{greet: function() {}}`. Computed property names: `{[dynamicKey]: value}`.

---

#### 92. What is `Object.freeze()` vs `Object.seal()`?

[↑ Back to Table of Contents](#table-of-contents)


`Object.freeze(obj)`: prevents adding, deleting, or modifying any properties. Shallow — nested objects can still be mutated. `Object.seal(obj)`: prevents adding or deleting properties, but allows modifying existing ones. Use freeze for truly immutable objects; use seal when shape must be fixed but values can change.

---

#### 93. What is `Object.create()`?

[↑ Back to Table of Contents](#table-of-contents)


Creates a new object with the specified object as its prototype. `const child = Object.create(parent)` — `child` inherits from `parent` without needing a constructor. Passing `null` creates an object with no prototype at all (truly empty object, no `toString` etc.).

---

#### 94. What are the differences between `Map` and a plain object?

[↑ Back to Table of Contents](#table-of-contents)


`Map`: any key type, ordered by insertion, `size` property, iterable directly, no prototype pollution. Object: only string/Symbol keys, not reliably ordered (though modern engines maintain insertion order for string keys), must use `hasOwnProperty`. Use `Map` for dictionaries with non-string keys or when key order matters.

---

#### 95. What is the difference between `==` comparisons and `Object.is`?

[↑ Back to Table of Contents](#table-of-contents)


`Object.is(a, b)` is like `===` but handles two edge cases: `Object.is(NaN, NaN) === true` and `Object.is(+0, -0) === false`. Used internally by React and Redux for comparison logic. Regular `===` treats `NaN !== NaN` and `+0 === -0`.

---

#### 96. What is the difference between `Object.keys`, `Object.values`, `Object.entries`, and `Object.fromEntries`?

[↑ Back to Table of Contents](#table-of-contents)


`Object.keys(obj)`: own enumerable string key names. `Object.values(obj)`: own enumerable values. `Object.entries(obj)`: own enumerable `[key, value]` pairs. `Object.fromEntries(iterable)`: creates an object from key-value pairs (inverse of `entries`). Together, these enable functional transformations: `Object.fromEntries(Object.entries(obj).map(([k, v]) => [k, transform(v)]))`.

---

#### 97. What are the ways to create objects in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Object literal `{}`, `new Object()`, `Object.create(proto)`, constructor functions with `new`, ES6 classes with `new`, factory functions returning `{}`. Object literals and classes are the most common. Factory functions offer more flexibility and avoid `new`/`this` complexity.

---

#### 98. What is destructuring?

[↑ Back to Table of Contents](#table-of-contents)


Extracting values from arrays or objects into distinct variables. `const {a, b} = obj`, `const [x, y] = arr`. Supports renaming (`{a: localName}`), defaults (`{a = 0}`), nested destructuring, and rest (`{a, ...rest}`). Works in function parameters, variable declarations, and assignments.

---

#### 99. What is the spread operator?

[↑ Back to Table of Contents](#table-of-contents)


`...` spreads an iterable into individual elements. For arrays: `[...arr1, ...arr2]` (concatenate/copy). For objects: `{...obj1, ...obj2}` (merge/clone). In function calls: `fn(...args)`. Creates shallow copies — nested objects are still references.

---

#### 100. What is `Object.keys()`, `Object.values()`, `Object.entries()`?

[↑ Back to Table of Contents](#table-of-contents)


`Object.keys(obj)`: returns array of own enumerable property names. `Object.values(obj)`: returns array of own enumerable property values. `Object.entries(obj)`: returns array of `[key, value]` pairs. All iterate only over own enumerable string-keyed properties (not prototype, not symbols).

---

#### 101. What is array and object destructuring with defaults?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const { a = 10, b: renamed = 20 } = { a: 5 };
// a = 5, renamed = 20

const [x = 1, y = 2] = [10];
// x = 10, y = 2
```
Defaults apply only when the value is `undefined`, not `null`.

---

#### 102. What does `flat()` and `flatMap()` do?

[↑ Back to Table of Contents](#table-of-contents)


`arr.flat(depth)`: flattens nested arrays up to specified depth (default 1). `arr.flat(Infinity)` fully flattens. `arr.flatMap(fn)`: equivalent to `arr.map(fn).flat(1)` but more efficient. Useful for mapping to arrays and then flattening one level.

---

#### 103. What is a Map vs a plain object?

[↑ Back to Table of Contents](#table-of-contents)


`Map`: any type as key (including objects), maintains insertion order, has `.size`, iterable directly, better performance for frequent additions/deletions, no prototype pollution risk. Plain object: string/symbol keys only, prototype chain pollution risk, JSON-serializable, simpler syntax. Use `Map` when keys are non-strings or when frequently mutating entries.

---

#### 104. What is the difference between `Object.assign()` and spread?

[↑ Back to Table of Contents](#table-of-contents)


Both create shallow copies/merges. Differences: `Object.assign` invokes setters on the target; spread doesn't. `Object.assign` mutates the target; spread always creates a new object. `Object.assign` copies inherited enumerable properties from the source if they're own properties; spread copies own enumerable properties. For most cases, they're interchangeable.

---

#### 105. What is the Proxy object and how is it used?

[↑ Back to Table of Contents](#table-of-contents)


`new Proxy(target, handler)` creates an object that intercepts operations on `target` (property access, assignment, deletion, function calls). Handler traps: `get`, `set`, `has`, `deleteProperty`, `apply`. Used for: validation, logging, reactive data (Vue 3), default values, access control.

```javascript
const safe = new Proxy({}, {
  get: (obj, key) => key in obj ? obj[key] : `Property "${key}" not found`,
  set: (obj, key, value) => {
    if (typeof value !== 'number') throw new TypeError('Numbers only!');
    obj[key] = value; return true;
  }
});
```

---

#### 106. Explain the difference between `Array.from()` and spread on a NodeList.

[↑ Back to Table of Contents](#table-of-contents)


Both convert array-like/iterables to arrays. `Array.from(nodeList)` works on any array-like (has `length` and indexed items — even without `Symbol.iterator`). Spread `[...nodeList]` requires the object to be iterable (`Symbol.iterator`). NodeLists are iterable in modern browsers, so both work there. `Array.from` also accepts a map function as second argument.

---

#### 107. How does JavaScript sort arrays by default and what is the gotcha?

[↑ Back to Table of Contents](#table-of-contents)


`Array.prototype.sort()` converts elements to strings and sorts lexicographically by default. `[10, 9, 2, 1, 100].sort()` gives `[1, 10, 100, 2, 9]`. For numeric sort, always provide a comparator: `arr.sort((a, b) => a - b)` for ascending. `.sort()` mutates the original array.

---

#### 108. What is the difference between `Object.create(null)` and `{}`?

[↑ Back to Table of Contents](#table-of-contents)


`{}` creates an object with `Object.prototype` in its prototype chain — it has `toString`, `hasOwnProperty`, `valueOf`, etc. `Object.create(null)` creates a truly empty object with NO prototype — no inherited methods. Useful as a pure hash map (no risk of key collisions with prototype properties like `'toString'` or `'constructor'`).

---

##### Prototypes, Inheritance & Classes

---

#### 109. What are property descriptors?

[↑ Back to Table of Contents](#table-of-contents)


Each property has hidden attributes: `value`, `writable` (can be changed), `enumerable` (appears in loops), `configurable` (can be deleted/reconfigured). Access via `Object.getOwnPropertyDescriptor(obj, 'key')`. Set via `Object.defineProperty(obj, 'key', descriptor)`. Getters/setters replace `value` and `writable` with `get` and `set`.

---

#### 110. What is a WeakMap and when would you use it?

[↑ Back to Table of Contents](#table-of-contents)


"A WeakMap is a collection of key-value pairs where keys must be objects, and those keys are held weakly."

The "Why" (The Killer Feature)
"Because the keys are held weakly, a WeakMap prevents memory leaks. If an object used as a key is deleted anywhere else in your application, JavaScript automatically wipes out its entry from the WeakMap and frees up that memory."

---

#### 111. What is a WeakSet?

[↑ Back to Table of Contents](#table-of-contents)


"A WeakSet is a collection of unique objects that are held weakly."

The "Why" (The Killer Feature)
"Because it holds objects weakly, it prevents memory leaks. If an object stored inside a WeakSet has no other active references left in your application, JavaScript's garbage collector will automatically wipe it out of the WeakSet and free up the memory."

---

#### 112. What are `Map` and `Set`?

[↑ Back to Table of Contents](#table-of-contents)


`Map`: key-value pairs where keys can be any type (objects, functions). Ordered by insertion. Has `size`, `get`, `set`, `has`, `delete`, `forEach`. `Set`: collection of unique values of any type. Used for deduplication and membership tests. Both are iterable.

---

#### 113. What are Proxy and Reflect?

[↑ Back to Table of Contents](#table-of-contents)


`Proxy` wraps an object and intercepts fundamental operations (get, set, delete, apply, construct) via handler traps. `Reflect` provides the same set of operations as static methods. Used for: validation, reactive systems (Vue 3), logging, access control, mocking.

---

#### 114. What are computed property names?

[↑ Back to Table of Contents](#table-of-contents)


ES6 syntax to use an expression as a property key: `const key = 'name'; const obj = { [key]: 'Alice' }` — creates `{name: 'Alice'}`. Useful for dynamic property names, especially in reducers or when building objects from variables.

---

#### 115. What is method chaining?

[↑ Back to Table of Contents](#table-of-contents)


Returning `this` from methods to allow calling multiple methods on the same object in sequence: `builder.setName('x').setAge(5).build()`. Common in jQuery, Lodash, query builders, and the Builder pattern. Makes code more fluent and readable.

---

#### 116. What is immutability and why does it matter?

[↑ Back to Table of Contents](#table-of-contents)


Data that cannot be changed after creation. Instead of mutating, create new data. Benefits: predictability, easier debugging, safe sharing between functions, enables undo/redo, time-travel debugging. In JS: use `const` for bindings, spread for objects/arrays, `Object.freeze()` for true immutability, or libraries like Immer.

---

### Advanced

#### 117. How do you deep clone an object in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


`structuredClone(obj)` — the modern standard, handles most types (Map, Set, Date, circular refs) but not functions or class instances. `JSON.parse(JSON.stringify(obj))` — only handles JSON-safe types. Lodash `_.cloneDeep` handles edge cases. Manual recursive clone for custom needs.

---

#### 118. How do you deep clone an object?

[↑ Back to Table of Contents](#table-of-contents)


Best method (modern): `structuredClone(obj)` — handles circular references, dates, maps, sets. Legacy: `JSON.parse(JSON.stringify(obj))` — simple but loses functions, `undefined`, `Date` objects become strings, can't handle circular references. For complex needs: Lodash `_.cloneDeep()`.

---

#### 119. How does `structuredClone` differ from `JSON.parse(JSON.stringify())`?

[↑ Back to Table of Contents](#table-of-contents)


`structuredClone`: handles `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`, circular references, `undefined`, `Infinity`, `NaN`. Does not clone functions or class instances (throws). `JSON.parse(JSON.stringify())`: drops `undefined`, functions, Symbols; converts `Date` to string; throws on circular refs; converts `Infinity`/`NaN` to `null`. Use `structuredClone` for general-purpose deep cloning.

---

#### 120. What is the difference between shallow copy and deep copy?

[↑ Back to Table of Contents](#table-of-contents)


Shallow copy: copies the top-level properties. Nested objects/arrays are still referenced (not duplicated). Methods: spread `{...obj}`, `Object.assign({}, obj)`, `arr.slice()`. Deep copy: copies all levels recursively — changes in copy don't affect original. Methods: `structuredClone()`, `JSON.parse(JSON.stringify(obj))` (with limitations), or libraries like Lodash `_.cloneDeep`.

---

#### 121. What is `structuredClone()`?

[↑ Back to Table of Contents](#table-of-contents)


A built-in global function for deep cloning objects. Handles circular references, `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`. Does NOT clone functions, DOM nodes, or class instances (their prototype). Available in modern browsers and Node.js 17+. Preferred over `JSON.parse(JSON.stringify())`.

---

## Prototypes, Inheritance & Classes

### Intermediate

#### 122. What is a constructor function?

[↑ Back to Table of Contents](#table-of-contents)


A regular function called with `new`. The `new` keyword: (1) creates a new object, (2) sets its `[[Prototype]]` to the constructor's `.prototype`, (3) sets `this` to the new object, (4) returns `this` implicitly (unless an object is explicitly returned).

---

#### 123. What is the `prototype` property on functions?

[↑ Back to Table of Contents](#table-of-contents)


Every function has a `.prototype` object. When the function is used as a constructor with `new`, the created instance's `[[Prototype]]` points to this object. Methods placed on `.prototype` are shared among all instances.

---

#### 124. What is the difference between `__proto__` and `prototype`?

[↑ Back to Table of Contents](#table-of-contents)


`prototype` is a property on constructor functions. When you use `new`, the created object's `[[Prototype]]` is set to the constructor's `prototype`. `__proto__` is the actual prototype link on every object instance (the accessor for `[[Prototype]]`). Use `Object.getPrototypeOf()` instead of `__proto__` in production code.
To understand the difference, think of a constructor function as a **Factory** and the objects it creates as **Products**.

---

#### 125. What is prototypal delegation vs classical inheritance?

[↑ Back to Table of Contents](#table-of-contents)


Classical inheritance copies behavior from parent to child at class definition time. Prototypal delegation links objects at runtime — the child delegates to the parent when a property isn't found. JS uses delegation; classes are a syntactic layer over it.

---

#### 126. What is a prototype in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Every JavaScript object has an internal `[[Prototype]]` link pointing to another object (or null). When a property isn't found on an object, JavaScript walks up the prototype chain looking for it. This is how objects inherit properties and methods.

---

#### 127. What is prototypal inheritance?

[↑ Back to Table of Contents](#table-of-contents)


Objects inherit directly from other objects through the prototype chain. This differs from classical OOP where classes inherit from classes. In JS, inheritance is delegation — if an object doesn't have a property, it delegates the lookup to its prototype.

---

#### 128. What is the difference between classical and prototypal inheritance?

[↑ Back to Table of Contents](#table-of-contents)


Classical (Java/C++): Classes are blueprints, objects are instances, inheritance copies behavior from parent class to child class. Prototypal (JS): Objects inherit from objects directly through a live prototype link — delegation, not copying. Changes to the prototype affect all inheriting objects.

---

#### 129. What is `Object.getPrototypeOf()`?

[↑ Back to Table of Contents](#table-of-contents)


Returns the prototype of an object (`[[Prototype]]`). The standard alternative to `__proto__`. Use `Object.setPrototypeOf()` to change an object's prototype (though this is slow and discouraged — use `Object.create()` at construction time instead).

---

#### 130. What are private class fields?

[↑ Back to Table of Contents](#table-of-contents)


Declared with `#` prefix: `#privateField`. Accessible only inside the class body — not on instances, not via `Object.keys()`, not from subclasses. Enforced by the runtime (unlike the convention of `_private`). Also supports private methods and private static fields.

---

#### 131. What is a class in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


A template for creating objects, introduced in ES6. Syntactic sugar over constructor functions and prototypes. Defines a constructor, methods (on the prototype), static members (on the class itself), and private fields. Classes are NOT hoisted the same way as function declarations — they're in the TDZ.

---

#### 132. What is a constructor?

[↑ Back to Table of Contents](#table-of-contents)


The special `constructor()` method in a class, called automatically when `new ClassName()` is used. It sets up the initial state of the instance via `this`. If not defined, a default empty constructor is used. In derived classes, `super()` must be called before accessing `this`.

---

#### 133. What is inheritance with `extends` and `super`?

[↑ Back to Table of Contents](#table-of-contents)


`extends` sets up the prototype chain between classes. `super()` in a derived constructor calls the parent's constructor. `super.method()` calls a parent's method. A derived class must call `super()` before accessing `this` in the constructor — otherwise `ReferenceError`.

---

#### 134. What is the difference between composition and inheritance?

[↑ Back to Table of Contents](#table-of-contents)


Inheritance ("is-a"): extend a base class to reuse behavior — creates tight coupling, fragile base class problem. Composition ("has-a"): combine small, focused objects/functions to build complex behavior — more flexible, loosely coupled. Prefer composition over inheritance for reusability (famous GoF principle).

---

#### 135. What is the difference between static and instance methods?

[↑ Back to Table of Contents](#table-of-contents)


Instance methods are defined on the class body and accessible on instances. Static methods are defined with `static` and accessible on the class itself (not instances). Used for factory methods, utility helpers, or methods that don't need `this`.

---

#### 136. What is `instanceof` and how does it work?

[↑ Back to Table of Contents](#table-of-contents)


`obj instanceof Constructor` walks the prototype chain of `obj` looking for `Constructor.prototype`. Returns `true` if found. Can give unexpected results with multiple frames (different global contexts). Prefer duck typing or `Object.getPrototypeOf()` for robust checks.

---

#### 137. What are static methods and properties?

[↑ Back to Table of Contents](#table-of-contents)


Defined on the class itself, not on instances. Called as `ClassName.method()`. Cannot access instance properties via `this` (though `this` refers to the class). Used for utility functions, factory methods, or class-level constants. `static #private` is also supported.

---

#### 138. What are getters and setters?

[↑ Back to Table of Contents](#table-of-contents)


`get` and `set` keywords create accessor properties. `get` defines a function called when the property is read; `set` defines a function called when it's assigned. Allow computed or validated properties with a simple property-access syntax. Defined in class body or via `Object.defineProperty`.

---

#### 139. What is encapsulation and how is it achieved in JS?

[↑ Back to Table of Contents](#table-of-contents)


Bundling data and methods that operate on that data, restricting direct access to internal state. Achieved via: closures (private state in factory functions), private class fields (`#field`), and conventions like `_private` (not enforced). Forces consumers to use the public API.

---

#### 140. What is a mixin?

[↑ Back to Table of Contents](#table-of-contents)


A pattern to add methods from one object to another without inheritance. `Object.assign(TargetClass.prototype, mixin)`. Enables sharing behavior across unrelated class hierarchies. No native mixin support in JS — it's a convention using `Object.assign` or object spread.

---

### Advanced

#### 141. What is the prototype chain?

[↑ Back to Table of Contents](#table-of-contents)


The series of linked objects through which JavaScript resolves property lookups. `obj` → `obj.__proto__` → `obj.__proto__.__proto__` → ... → `Object.prototype` → `null`. If the property isn't found anywhere in the chain, the result is `undefined` (for property access) or `TypeError` (for method call).
**What**  
The prototype chain is JavaScript’s mechanism for inheritance. Every object has an internal link to another object (its **prototype**). When you access a property, JavaScript looks for it on the object itself; if not found, it moves to the object’s prototype, then to that prototype’s prototype, and so on, until the chain ends at `null`.

**Why**  
- Enables **shared behavior** – methods are defined once on a prototype and used by all inheriting objects, saving memory.  
- Provides built‑in functionality (e.g., arrays get `push`/`pop` from `Array.prototype`, all objects get `toString` from `Object.prototype`).  
- Allows you to **override** inherited properties by placing them directly on the object.

**When & Where**  
- **Every property or method lookup** on an object uses the prototype chain.  
- **Creating objects** with constructor functions or `class` – instances link to the constructor’s `.prototype`.  
- **Inheritance patterns** – `Object.create()` to set a specific prototype.  
- **Checking relationships** with `instanceof` (which traverses the chain).  
- **Avoiding errors** – if a method doesn’t exist anywhere in the chain, calling it throws a `TypeError` (e.g., `obj.nonExistent()`) while simply reading a missing property gives `undefined`.

**Simple example**  
```js
const animal = { eats: true };
const rabbit = Object.create(animal);   // rabbit.__proto__ === animal

console.log(rabbit.eats);   // true        (found on animal)
console.log(rabbit.toString());  // method found on Object.prototype
// chain: rabbit → animal → Object.prototype → null
```

Visual chain: `rabbit` → `animal` → `Object.prototype` → `null`.

---

### Senior / Scenario

#### 142. What are mixins and how do you implement them in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


A mixin adds methods from one object to another without inheritance: `Object.assign(Target.prototype, MixinA, MixinB)`. Since JS only has single inheritance (via prototype chain), mixins allow composing multiple behaviors. Higher-order class mixins are more composable: `const Serializable = (Base) => class extends Base { serialize() {} }`.

---

#### 143. Explain how `Array.prototype.reduce` works from scratch.

[↑ Back to Table of Contents](#table-of-contents)


Takes a callback `(accumulator, currentValue, index, array) => newAccumulator` and an optional initial value. If no initial value, uses the first element. Iterates each element, passing the accumulator (starts as initial value or first element) to the callback, using the return value as the next accumulator. Returns the final accumulator.

---

#### 144. Implement `Array.prototype.flat` from scratch.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function flat(arr, depth = 1) {
  if (depth === 0) return arr.slice();
  return arr.reduce((acc, item) => {
    if (Array.isArray(item)) {
      acc.push(...flat(item, depth - 1));
    } else {
      acc.push(item);
    }
    return acc;
  }, []);
}
```

---

## ES6+ Modern JavaScript

### Intermediate

#### 145. What is the logical assignment operators (`&&=`, `||=`, `??=`)?

[↑ Back to Table of Contents](#table-of-contents)


Short-circuit assignment operators. `a &&= b` — assign `b` to `a` only if `a` is truthy. `a ||= b` — assign `b` to `a` only if `a` is falsy. `a ??= b` — assign `b` to `a` only if `a` is `null`/`undefined`. More concise than full if-statements for conditional assignment.

---

#### 146. What is the `void` operator?

[↑ Back to Table of Contents](#table-of-contents)


`void expression` evaluates the expression and returns `undefined`. Used in `<a href="void(0)">` to prevent navigation. Also used in arrow functions to explicitly return `undefined` and signal no return value is intended: `const handler = () => void doSomething()`. Rarely needed in modern code.

---

#### 147. What is an iterator?

[↑ Back to Table of Contents](#table-of-contents)


An object with a `next()` method that returns `{value, done}`. `done: true` signals exhaustion. `for...of`, spread, destructuring, and `Array.from` all consume iterators automatically.

---

#### 148. What are iterators and iterables?

[↑ Back to Table of Contents](#table-of-contents)


"Iterable is the data structure you want to loop over, and Iterator is the pointer that actually does the looping."

1. The Iterable (The "Loopable" Object)
An object is iterable if it contains a special method called [Symbol.iterator]. This method is a green light that tells JavaScript, "Yes, I can be stepped through."

Examples: Arrays, Strings, Maps, and Sets are all built-in iterables.

2. The Iterator (The Tracker)
An iterator is the actual machine returned by that [Symbol.iterator] method. It is a simple object with a .next() method.

Every time JavaScript calls .next(), the iterator returns the next item in line as an object:

{ value: "item", done: false }

When it finally runs out of data, it returns { value: undefined, done: true } to signal the end.

The "Book" Analogy
Think of an Iterable like a Book (it holds all the content). Think of the Iterator like a Pointer Finger tracking the words. The finger knows exactly where you currently are and moves to the .next() word when you tell it to.

Why this matters in JavaScript
Under the hood, modern features like the for...of loop, the spread operator (...), and destructuring don't actually know how to read arrays or strings directly. Instead, they secretly request the object's iterator and repeatedly call .next() until done becomes true.

---

#### 149. What is optional chaining (`?.`)?

[↑ Back to Table of Contents](#table-of-contents)


Safely accesses deeply nested properties without throwing if an intermediate value is `null`/`undefined`. `obj?.a?.b?.c` returns `undefined` instead of throwing. Works for method calls (`obj.fn?.()`) and array access (`arr?.[0]`). Short-circuits the rest of the expression when it encounters `null`/`undefined`.

---

#### 150. What is nullish coalescing (`??`)?

[↑ Back to Table of Contents](#table-of-contents)


`value ?? 'default'` — returns the right side only when the left side is `null` or `undefined`. Unlike `||`, it does not short-circuit on `0`, `''`, or `false`. Use `??` when `0` and `''` are valid values.

---

#### 151. What are template literals?

[↑ Back to Table of Contents](#table-of-contents)


Backtick strings (`` ` ``) supporting multi-line text and embedded expressions via `${}`. Tagged templates allow a function to process the template string. Used for HTML strings, SQL queries, styled-components, and i18n.

---

#### 152. What are tagged template literals?

[↑ Back to Table of Contents](#table-of-contents)


A function called with a template literal. The function receives the string parts as an array and the interpolated values as separate arguments. Used by libraries like styled-components, GraphQL (`gql\`...\``), and SQL query builders to process template strings safely.

---

#### 153. What is the nullish coalescing operator (`??`)?

[↑ Back to Table of Contents](#table-of-contents)


Returns the right-hand value when the left-hand value is `null` or `undefined` (not just falsy). `const val = input ?? 'default'` — if `input` is `0` or `''`, those are used (unlike `||` which would fall back to 'default'). Use `??` when `0` or empty string are valid values.

---

##### Modules & Tooling

---

#### 154. What is `BigInt` and when do you use it?

[↑ Back to Table of Contents](#table-of-contents)


A numeric type for integers of arbitrary size: `9007199254740993n`. Append `n` to a literal or use `BigInt(value)`. Cannot be mixed with regular `Number` in operations. Use when: working with IDs from languages that use 64-bit integers, cryptography, precise large integer arithmetic, or any value exceeding `Number.MAX_SAFE_INTEGER`.

---

#### 155. What is the difference between `for...in` and `for...of`?

[↑ Back to Table of Contents](#table-of-contents)


`for...in`: iterates over enumerable property KEYS (including inherited ones) of an object. Avoid on arrays (iterates indices as strings + any added prototype properties). `for...of`: iterates over VALUES of any iterable. Cannot be used on plain objects directly (they aren't iterable by default).

---

#### 156. What is an iterable?

[↑ Back to Table of Contents](#table-of-contents)


An object implementing the iterable protocol: a `[Symbol.iterator]()` method that returns an iterator. Arrays, strings, Maps, Sets, and generators are iterable. Custom iterables can be created by implementing this method.

---

#### 157. What is `Symbol` and why was it introduced?

[↑ Back to Table of Contents](#table-of-contents)


`Symbol()` creates a unique, immutable primitive. Introduced in ES6 to create non-string property keys that avoid naming collisions — critical for metaprogramming hooks like `Symbol.iterator`, `Symbol.toPrimitive`, `Symbol.hasInstance`.

---

#### 158. What are well-known Symbols?

[↑ Back to Table of Contents](#table-of-contents)


Built-in Symbols used to customize JS behavior: `Symbol.iterator` (makes object iterable), `Symbol.toPrimitive` (custom type coercion), `Symbol.hasInstance` (customizes `instanceof`), `Symbol.species` (customizes derived instances), `Symbol.toStringTag` (customizes `Object.prototype.toString`).

---

#### 159. What is `Symbol.toPrimitive` used for?

[↑ Back to Table of Contents](#table-of-contents)


Allows an object to define its own coercion to a primitive. The method receives a hint (`'number'`, `'string'`, or `'default'`) and should return the appropriate primitive. Example use: custom value objects (Money, Color) that behave naturally in arithmetic or string contexts.

---

#### 160. What is the `for...of` loop?

[↑ Back to Table of Contents](#table-of-contents)


Iterates over values of any iterable (arrays, strings, Maps, Sets, generators). `for (const item of arr) {}`. Supports `break`, `continue`, `return`. Unlike `forEach`, works with generators and custom iterables. Unlike `for...in`, iterates values not property names.

---

#### 161. What is `globalThis`?

[↑ Back to Table of Contents](#table-of-contents)


A standard way to access the global object regardless of environment. `window` in browsers, `global` in Node.js, `self` in Web Workers. `globalThis` normalizes these across environments for portable code.

---

#### 162. What are default parameters?

[↑ Back to Table of Contents](#table-of-contents)


ES6 syntax to provide default values for function parameters: `function greet(name = 'World') {}`. Defaults are used when the argument is `undefined` (not when it's `null`). Defaults can be expressions and can reference earlier parameters.

Default parameters let you set a fallback value for a function’s argument in case it’s missing or explicitly `undefined`. You define them right in the parameter list with `=`.

```js
function greet(name = 'World') {
  console.log(`Hello, ${name}!`);
}

greet();          // Hello, World!  (name is undefined → default kicks in)
greet('Alice');   // Hello, Alice!
greet(null);      // Hello, null!   (null does NOT trigger the default)
```

**Key points:**
- The default is used only when the argument is `undefined`, not when it’s `null` or any other falsy value.
- Defaults can be any expression, and they can refer to parameters defined earlier (e.g., `function sum(a, b = a) {…}`).

---

#### 163. What are Symbols?

[↑ Back to Table of Contents](#table-of-contents)


A unique, immutable primitive value. `Symbol('desc')` creates a Symbol; no two Symbols are equal. Used as unique property keys (avoid naming collisions), to implement well-known behaviors (`Symbol.iterator`, `Symbol.toPrimitive`), and for truly private-ish object properties. Not enumerable in `for...in` or `Object.keys()`.

---

### Advanced

#### 164. What is a generator function?

[↑ Back to Table of Contents](#table-of-contents)


Declared with `function*`, it returns a generator object that implements the iterator protocol. Uses `yield` to pause execution and return a value. Execution resumes on `.next()`. Useful for lazy sequences, infinite data streams, and implementing async flows (before async/await).

```javascript
function* range(start, end) {
  for (let i = start; i <= end; i++) yield i;
}
[...range(1, 5)]; // [1, 2, 3, 4, 5]
```
**What**  
A generator function is declared with `function*` and uses `yield` to pause and resume execution. Calling it returns a **generator object** (an iterator) that you control by calling `.next()`. Each `yield` returns a value, and the function pauses until the next `.next()`.

**Why**  
- Produce lazy sequences — values are computed on demand, saving memory.  
- Enable infinite streams (e.g., unique IDs) without freezing.  
- Simplify async flows before `async/await` existed (e.g., with libraries like `co`).  
- Can receive values via `.next(val)` for two-way communication.

**When**  
- Processing large or infinite data sets lazily.  
- Implementing custom iterable objects.  
- Managing async tasks in a synchronous-looking style (though mostly replaced by `async/await`).  
- Any case where you need to pause and resume logic.

**Where** (real examples)

```js
// Lazy range (from your example)
function* range(start, end) {
  for (let i = start; i <= end; i++) yield i;
}
[...range(1, 5)]; // [1, 2, 3, 4, 5]

// Infinite unique IDs
function* idMaker() {
  let id = 0;
  while (true) yield id++;
}
const gen = idMaker();
gen.next().value; // 0, 1, 2, ...

// Two-way communication
function* echo() {
  const received = yield 'Speak';
  yield `You said: ${received}`;
}
const e = echo();
e.next();          // { value: 'Speak', done: false }
e.next('Hello');   // { value: 'You said: Hello', done: false }
```

---

### Senior / Scenario

#### 165. How do generators implement iterators?

[↑ Back to Table of Contents](#table-of-contents)


`function*` creates a generator function returning a generator object that is both an iterable and an iterator. `yield` pauses execution and provides the next value. `yield*` delegates to another iterable. Generator's `next()` resumes from the last `yield`.

---

## Asynchronous JavaScript

### Junior

#### 166. What is a Promise?

[↑ Back to Table of Contents](#table-of-contents)


An object representing the eventual completion or failure of an async operation. Created with `new Promise((resolve, reject) => {...})`. Provides `.then()` for success, `.catch()` for error, `.finally()` for cleanup. Promises are chainable and avoid callback hell. They're always asynchronous — `.then` callbacks always run after the current synchronous code.

---

### Intermediate

#### 167. What are ES6 classes?

[↑ Back to Table of Contents](#table-of-contents)


Syntactic sugar over prototype-based inheritance. `class Foo extends Bar { constructor() { super(); } method() {} }` compiles to constructor functions and prototype assignments. Classes enforce `new` (cannot be called without it), are not hoisted usably, and run in strict mode.

---

#### 168. What are ES6 classes and how do they relate to prototypes?

[↑ Back to Table of Contents](#table-of-contents)


ES6 classes are syntactic sugar over prototypal inheritance. `class Animal { speak() {} }` creates `Animal.prototype.speak`. `class Dog extends Animal {}` sets `Dog.prototype.__proto__ = Animal.prototype`. Under the hood, it's still prototype-based — no classical inheritance actually occurs.

---

#### 169. How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)

[↑ Back to Table of Contents](#table-of-contents)


Modern engines (V8, SpiderMonkey) use **Just‑In‑Time (JIT)** compilation, combining interpretation and compilation.

- **Interpretation**: Code starts as bytecode, executed by an interpreter (Ignition in V8). This allows fast startup.
- **JIT compilation**: Hot functions (executed many times) are compiled to machine code by optimizing compilers (TurboFan in V8) for faster execution.
- **Hidden classes**: Instead of dynamic dictionary lookups, objects with the same shape (property names and order) share a hidden class, enabling fast property access via fixed offsets.
- **Inline caching**: When a property is accessed repeatedly, the engine caches the property location based on the hidden class, avoiding repeated lookup overhead.

---

##### Asynchronous JavaScript

---

#### 170. What is the Event Loop?

[↑ Back to Table of Contents](#table-of-contents)


The mechanism that allows JavaScript to perform non-blocking async operations despite being single-threaded. It continuously checks if the call stack is empty, then takes tasks from the task queue and pushes them onto the stack. This enables handling timers, network responses, and user events without blocking the main thread.

---

#### 171. What is the difference between the Microtask Queue and the Macrotask Queue?

[↑ Back to Table of Contents](#table-of-contents)


Microtasks (Promise `.then`, `queueMicrotask`, `MutationObserver`) run after every task before the next task and before rendering. Macrotasks (`setTimeout`, `setInterval`, I/O, `setImmediate`) run one per event loop iteration. Microtasks always drain completely before the next macrotask.

---

#### 172. How does Promise chaining work?

[↑ Back to Table of Contents](#table-of-contents)


Each `.then()` returns a new Promise. If the handler returns a value, the next `.then` receives it. If it returns a Promise, the next `.then` waits for it to settle. This flattening eliminates nested callbacks. Errors propagate down the chain to the nearest `.catch`.

---

#### 173. What is `Promise.all()`?

[↑ Back to Table of Contents](#table-of-contents)


Takes an iterable of Promises, returns a Promise that resolves with an array of all resolved values when ALL promises resolve. Rejects immediately if ANY promise rejects (fail-fast). Use for parallel operations where all results are needed and any failure should abort.

---

#### 174. What are `Promise.allSettled`, `Promise.race`, and `Promise.any`?

[↑ Back to Table of Contents](#table-of-contents)


`allSettled`: waits for all, resolves with array of `{status, value/reason}` — never rejects. `race`: settles with the first Promise to settle (fulfill or reject). `any`: fulfills with the first fulfillment; rejects with `AggregateError` only if all reject.

---

#### 175. What is `async/await`?

[↑ Back to Table of Contents](#table-of-contents)


Syntactic sugar over Promises. `async` functions always return a Promise. `await` pauses execution of the async function until the awaited Promise resolves, then returns the resolved value. Makes async code look and behave more like synchronous code. Under the hood, it's still Promises.

---

#### 176. What happens if you `await` a non-Promise value?

[↑ Back to Table of Contents](#table-of-contents)


`await 42` is valid — it simply returns `42`. The value is wrapped in `Promise.resolve()` first. This means `await` is safe to use even if you're not sure if a function returns a Promise.

---

#### 177. What is the difference between `setTimeout(fn, 0)` and `Promise.resolve().then(fn)`?

[↑ Back to Table of Contents](#table-of-contents)


Both defer execution, but Promise callbacks (microtasks) run before setTimeout callbacks (macrotasks). `setTimeout(fn, 0)` adds to the macrotask queue; `Promise.resolve().then(fn)` adds to the microtask queue, which drains before the next macrotask.

---

#### 178. What is the danger of floating Promises?

[↑ Back to Table of Contents](#table-of-contents)


A Promise that is not awaited and has no `.catch()`. If it rejects, the error is silently swallowed or triggers `unhandledRejection`. Always `await` or `.catch()` every Promise. ESLint rules like `no-floating-promises` (from TypeScript-eslint) catch this statically.

---

#### 179. Explain how JavaScript handles concurrency with the event loop, Workers, and SharedArrayBuffer.

[↑ Back to Table of Contents](#table-of-contents)


The event loop handles concurrency at the application level — non-blocking I/O via callbacks, interleaved on the single main thread. Web Workers provide true parallelism — separate threads with no shared memory (communicate via `postMessage`). `SharedArrayBuffer` allows workers to share memory for performance-critical scenarios, requiring `Atomics` for synchronization. These three layers allow JavaScript to scale from simple async to multi-threaded parallelism.

---

#### 180. Explain how you'd port a callback-based API to use Promises.

[↑ Back to Table of Contents](#table-of-contents)


`function promisify(fn) { return (...args) => new Promise((resolve, reject) => { fn(...args, (err, result) => err ? reject(err) : resolve(result)); }); }`. Node.js provides `util.promisify` for Node-style (error-first) callbacks. For event-based APIs: wrap in a Promise that resolves on the success event and rejects on the error event.

---

#### 181. What is synchronous vs asynchronous code?

[↑ Back to Table of Contents](#table-of-contents)


Synchronous: executes line by line, each line waits for the previous to finish. Asynchronous: initiates an operation and moves on; the result is handled later via callback, promise, or async/await. JS is single-threaded, so async operations are managed by the event loop, not true parallelism.

---

#### 182. What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?

[↑ Back to Table of Contents](#table-of-contents)


**Call Stack**: where synchronous code executes (LIFO). **Web APIs**: browser-provided async capabilities (setTimeout, fetch, DOM events) — offloaded from JS thread. **Callback Queue (macrotask queue)**: where timer/event callbacks wait. **Microtask Queue**: where Promise callbacks and `queueMicrotask` wait. Microtasks run before the next macrotask.

---

#### 183. What is the difference between macrotasks and microtasks?

[↑ Back to Table of Contents](#table-of-contents)


**Macrotasks** (task queue): `setTimeout`, `setInterval`, `setImmediate`, I/O, UI rendering. One macrotask runs per event loop iteration. **Microtasks**: Promises (`.then`, `.catch`, `.finally`), `queueMicrotask`, `MutationObserver`. ALL microtasks are processed after each macrotask, before the next macrotask runs. Microtasks have priority.

---

#### 184. What are the states of a Promise?

[↑ Back to Table of Contents](#table-of-contents)


**Pending**: initial state, operation in progress. **Fulfilled**: operation completed successfully — `resolve()` was called. **Rejected**: operation failed — `reject()` was called. Once settled (fulfilled or rejected), a Promise is immutable — it can never change state again.

---

#### 185. What is promise chaining?

[↑ Back to Table of Contents](#table-of-contents)


`.then()` returns a new Promise, so you can chain multiple async operations: `fetchUser().then(user => fetchPosts(user.id)).then(posts => render(posts)).catch(handleError)`. Each `.then` receives the resolved value of the previous one. Errors propagate down the chain to the nearest `.catch`.

---

#### 186. What is `Promise.allSettled()`?

[↑ Back to Table of Contents](#table-of-contents)


Like `Promise.all()` but never rejects. Waits for ALL promises to settle and returns an array of `{status: 'fulfilled', value}` or `{status: 'rejected', reason}` objects. Use when you need all results regardless of individual failures (e.g., multiple independent API calls).

---

#### 187. What is `Promise.race()`?

[↑ Back to Table of Contents](#table-of-contents)


Returns a Promise that settles (resolves or rejects) as soon as the FIRST promise in the iterable settles. Use for timeouts: `Promise.race([fetch(url), timeout(5000)])`. The other promises continue running but their outcomes are ignored.

---

#### 188. What is `Promise.any()`?

[↑ Back to Table of Contents](#table-of-contents)


Returns a Promise that resolves as soon as ANY promise resolves. Rejects only if ALL promises reject (with an `AggregateError`). Opposite short-circuit behavior from `Promise.all()`. Use when you want the fastest successful result (e.g., trying multiple CDNs).

---

#### 189. What is an unhandled promise rejection?

[↑ Back to Table of Contents](#table-of-contents)


A Promise that rejects with no `.catch` handler. In Node.js, unhandled rejections emit a warning and can crash the process. In browsers, they fire `window.onunhandledrejection`. Listen to `process.on('unhandledRejection', handler)` in Node.js for a global safety net.

---

#### 190. What does `finally` do in a Promise chain?

[↑ Back to Table of Contents](#table-of-contents)


`.finally(fn)` runs `fn` regardless of whether the promise resolved or rejected. Useful for cleanup (hiding loading spinners, closing connections). It doesn't receive the resolved value or rejection reason. It passes the original outcome to the next handler in the chain.

---

#### 191. Explain the JavaScript event loop in detail. Microtasks vs macrotasks.

[↑ Back to Table of Contents](#table-of-contents)


The **event loop** is the mechanism that enables JavaScript’s non‑blocking, asynchronous behavior despite being single‑threaded. It continuously checks the **call stack** and **task queues**, moving tasks to the stack when it’s empty.

There are two main queues:
- **Macrotask (Callback) queue**: Contains tasks like `setTimeout`, `setInterval`, `setImmediate`, I/O events, and UI rendering.
- **Microtask queue**: Contains tasks like `Promise` callbacks (`.then`, `.catch`, `.finally`), `queueMicrotask`, and `MutationObserver`. Microtasks have higher priority.

**Process:**
1. Execute all synchronous code (call stack frames).
2. When the stack is empty, the event loop first processes **all** microtasks in the microtask queue (in FIFO order). If new microtasks are added during this phase, they are also processed before moving to macrotasks.
3. After microtasks are exhausted, one macrotask is taken from the macrotask queue and executed.
4. The browser may perform rendering (if needed) between macrotask cycles.
5. Repeat.

```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// Output: 1,4,3,2
// Explanation: synchronous 1,4; microtask (promise) 3; macrotask 2.
```

---

#### 192. Event loop: Why does a Promise run before setTimeout? (Microtasks vs macrotasks)

[↑ Back to Table of Contents](#table-of-contents)


Promises’ callbacks (`.then`, `.catch`) are **microtasks**, while `setTimeout` callbacks are **macrotasks**. After each macrotask (including the initial script execution), the event loop drains the entire microtask queue before taking the next macrotask. Therefore, a settled promise’s callback always runs before any scheduled `setTimeout`.

---

#### 193. How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)

[↑ Back to Table of Contents](#table-of-contents)


- Use `Promise.all` when you need all to succeed or fail fast (reject on first error).
- Use `Promise.allSettled` when you want to know the outcome of each independent call, regardless of failures (e.g., analytics, fallback data).

---

#### 194. What are the advantages of `Promise.allSettled` over `Promise.all`?

[↑ Back to Table of Contents](#table-of-contents)


`Promise.allSettled` never rejects; it always resolves with an array of objects describing each promise’s outcome. This is useful when you need to wait for multiple operations and handle errors individually, without failing the whole batch.

---

#### 195. Multiple API Calls: How to load a dashboard with independent APIs efficiently? (Promise.all, allSettled)

[↑ Back to Table of Contents](#table-of-contents)


**Options**:
- **`Promise.all`** – if all calls must succeed for the dashboard to render. Fails fast if any fails.
- **`Promise.allSettled`** – if you want to load independent widgets, each can show its own error state. Waits for all calls to complete (or fail) before rendering.
- **`Promise.race`** – rarely used; for timeouts.

**Implementation**:
```javascript
useEffect(() => {
  const fetchData = async () => {
    setLoading(true);
    const results = await Promise.allSettled([
      fetch('/api/users'),
      fetch('/api/stats'),
      fetch('/api/notifications')
    ]);
    // process each result: if fulfilled, set data; if rejected, set error
    setLoading(false);
  };
  fetchData();
}, []);
```

**Performance**:
- Consider **parallel requests** with `Promise.all` for speed.
- Use **React Query** or **SWR** for automatic caching and retries.

---

#### 196. Correct async iteration patterns:

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const arr = [1, 2, 3];

// Sequential (each waits for previous):
async function sequential() {
  for (const n of arr) {
    await new Promise(r => setTimeout(r, n * 100));
    console.log('seq:', n);
  }
}
// Output: seq:1, seq:2, seq:3 (in order, ~600ms total)

// Parallel (all start simultaneously):
async function parallel() {
  await Promise.all(arr.map(async (n) => {
    await new Promise(r => setTimeout(r, n * 100));
    console.log('par:', n);
  }));
}
// Output: par:1, par:2, par:3 (in order of completion, ~300ms total)

// Parallel with results in order:
async function parallelOrdered() {
  const results = await Promise.all(
    arr.map(n => new Promise(r => setTimeout(() => r(n * 2), n * 100)))
  );
  console.log(results); // [2, 4, 6] — always in original order
}
```

---

#### 197. What are `AbortController` and `AbortSignal`?

[↑ Back to Table of Contents](#table-of-contents)


`AbortController` creates a controller with an associated `AbortSignal`. Passing the signal to `fetch` allows cancelling the request by calling `controller.abort()`. The signal can also be passed to any API that supports abort signals for consistent cancellation.

---

#### 198. What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?

[↑ Back to Table of Contents](#table-of-contents)


`setTimeout(fn, delay)`: calls `fn` once after `delay` ms (minimum — actual time may be longer). `setInterval(fn, delay)`: calls `fn` repeatedly every `delay` ms. `requestAnimationFrame(fn)`: calls `fn` before the next browser repaint (~60fps). Use rAF for animations; it's paused when the tab is hidden and syncs with display refresh rate.

---

#### 199. What is the difference between `setTimeout` and `setInterval`?

[↑ Back to Table of Contents](#table-of-contents)


| | `setTimeout` | `setInterval` |
|---|--------------|---------------|
| **Execution** | Runs once after a delay | Runs repeatedly at a fixed interval |
| **Drift** | No cumulative delay | Can drift if execution time exceeds interval |
| **Cancellation** | `clearTimeout(id)` | `clearInterval(id)` |

**Important**: Both schedule macrotasks. If the callback takes longer than the interval, `setInterval` may queue multiple calls back‑to‑back, causing congestion. A common pattern to avoid this is recursive `setTimeout`:

```javascript
function repeat() {
  // do work
  setTimeout(repeat, delay);
}
```

---

#### 200. Explain AbortController and request cancellation.

[↑ Back to Table of Contents](#table-of-contents)


`AbortController` provides a standard way to cancel asynchronous operations (e.g., fetch, timers). It works via an `AbortSignal` attached to the operation.

```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch('/api', { signal })
  .then(response => response.json())
  .catch(err => {
    if (err.name === 'AbortError') console.log('Fetch aborted');
  });

// Cancel after 1 second
setTimeout(() => controller.abort(), 1000);
```

**Use cases**: Cancelling fetch requests when a component unmounts, implementing debounced search, aborting expensive computations.

---

### Senior / Scenario

#### 201. How would you implement structured concurrency in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Group async operations so all are cancelled/resolved together. Model with an `AbortController` shared among tasks. Pattern: `async function withTimeout(fn, ms) { const ac = new AbortController(); const timer = setTimeout(() => ac.abort(), ms); try { return await fn(ac.signal); } finally { clearTimeout(timer); } }`. The TC39 `Async Context` proposal and `AbortSignal.any()` improve this further. Libraries like `effect-ts` provide structured concurrency primitives.

---

#### 202. How do you handle errors with `async/await`?

[↑ Back to Table of Contents](#table-of-contents)


Wrap `await` calls in `try/catch` blocks. The `catch` block receives the rejection reason. You can also handle errors with `.catch()` on the async function call. For multiple operations, you can have one try/catch or separate ones depending on error handling needs.

```javascript
async function fetchData() {
  try {
    const res = await fetch(url);
    const data = await res.json();
    return data;
  } catch (err) {
    console.error('Failed:', err);
  }
}
```

---

#### 203. How do you handle errors in Promises vs async/await?

[↑ Back to Table of Contents](#table-of-contents)


Promises: `.catch(handler)` at the end of the chain. Async/await: `try/catch` block, or `.catch()` on the returned Promise. Unhandled rejections: listen to `process.on('unhandledRejection')` (Node) or `window.addEventListener('unhandledrejection')` (browser).

---

#### 204. How do you implement `Promise.all` from scratch?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    const results = [];
    let remaining = promises.length;
    if (remaining === 0) return resolve([]);
    promises.forEach((p, i) => {
      Promise.resolve(p).then(val => {
        results[i] = val;
        if (--remaining === 0) resolve(results);
      }, reject);
    });
  });
}
```

---

#### 205. How do you handle errors in Promises?

[↑ Back to Table of Contents](#table-of-contents)


`.catch(fn)` at the end of a chain handles any rejection in the chain. Can also pass a rejection handler as the second argument to `.then(null, onRejected)`. In `async/await`, use `try/catch`. Always handle promise rejections — unhandled rejections crash Node.js and cause console warnings in browsers.

---

#### 206. Implement `Promise.all` from scratch.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    const results = [];
    let pending = promises.length;
    if (pending === 0) return resolve([]);
    promises.forEach((promise, i) => {
      Promise.resolve(promise).then(value => {
        results[i] = value;
        if (--pending === 0) resolve(results);
      }).catch(reject);
    });
  });
}
```

---

#### 207. Implement a custom Promise (conceptually).

[↑ Back to Table of Contents](#table-of-contents)


A custom Promise implementation involves managing states (`pending`, `fulfilled`, `rejected`), handling `.then` callbacks (both onFulfilled and onRejected), and supporting chaining and async resolution.

```javascript
class MyPromise {
  constructor(executor) {
    this.state = 'pending';
    this.value = undefined;
    this.handlers = []; // stores { onFulfilled, onRejected }

    const resolve = (value) => {
      if (this.state !== 'pending') return;
      this.state = 'fulfilled';
      this.value = value;
      this.handlers.forEach(h => this._runHandler(h));
    };

    const reject = (reason) => {
      if (this.state !== 'pending') return;
      this.state = 'rejected';
      this.value = reason;
      this.handlers.forEach(h => this._runHandler(h));
    };

    try {
      executor(resolve, reject);
    } catch (err) {
      reject(err);
    }
  }

  _runHandler(handler) {
    if (this.state === 'pending') {
      this.handlers.push(handler);
      return;
    }
    const cb = this.state === 'fulfilled' ? handler.onFulfilled : handler.onRejected;
    if (!cb) {
      // propagate
      const next = this.state === 'fulfilled' ? handler.resolve : handler.reject;
      next(this.value);
      return;
    }
    try {
      const result = cb(this.value);
      handler.resolve(result);
    } catch (err) {
      handler.reject(err);
    }
  }

  then(onFulfilled, onRejected) {
    return new MyPromise((resolve, reject) => {
      this._runHandler({ onFulfilled, onRejected, resolve, reject });
    });
  }

  catch(onRejected) {
    return this.then(null, onRejected);
  }

  // static methods (all, race) would be added similarly
}
```

---

#### 208. Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.

[↑ Back to Table of Contents](#table-of-contents)


**Promise.all**:
```javascript
Promise.myAll = function(promises) {
  return new Promise((resolve, reject) => {
    if (!Array.isArray(promises)) reject(new TypeError('Not an array'));
    const results = new Array(promises.length);
    let completed = 0;
    if (promises.length === 0) resolve(results);
    promises.forEach((p, i) => {
      Promise.resolve(p).then(
        val => {
          results[i] = val;
          completed++;
          if (completed === promises.length) resolve(results);
        },
        err => reject(err)
      );
    });
  });
};
```

**Promise.race**:
```javascript
Promise.myRace = function(promises) {
  return new Promise((resolve, reject) => {
    promises.forEach(p => {
      Promise.resolve(p).then(resolve, reject);
    });
  });
};
```

**Promise.allSettled**:
```javascript
Promise.myAllSettled = function(promises) {
  return new Promise(resolve => {
    const results = [];
    let remaining = promises.length;
    if (remaining === 0) resolve(results);
    promises.forEach((p, i) => {
      Promise.resolve(p).then(
        value => results[i] = { status: 'fulfilled', value },
        reason => results[i] = { status: 'rejected', reason }
      ).finally(() => {
        remaining--;
        if (remaining === 0) resolve(results);
      });
    });
  });
};
```

---

#### 209. In a live application where users report slowness, how would you identify whether the issue is due to the event loop blocking or inefficient code?

[↑ Back to Table of Contents](#table-of-contents)


**Answer:**  
I would use a combination of monitoring, profiling, and diagnostic tools.

- **Monitor event loop lag:** Use the `perf_hooks` module or libraries like `event-loop-lag` to measure the delay between a scheduled task and its execution. High lag (>10‑20ms) indicates blocking.
- **Profiling:** Take CPU profiles using `node --inspect` and Chrome DevTools, or use `clinic` (Clinic.js) to visualise hotspots. A flat flame graph with long‑running synchronous functions points to blocking code.
- **Check for synchronous I/O:** Look for `fs.readFileSync`, heavy crypto, or JSON parsing of large objects in the main thread.
- **Use `process._getActiveHandles()` and `process._getActiveRequests()`** to see if too many pending operations are accumulating.
- **APM tools:** New Relic, Datadog, or Dynatrace can show event loop latency and transaction traces.
- **Inefficient code:** If the event loop is not blocked but operations are slow (e.g., slow database queries, N+1 problems), profiling will show time spent in callbacks or promises rather than a single synchronous block. In that case, the fix is optimising the async operations, not removing blocking code.

---

##### DOM & Browser APIs

---

#### 210. Situation: Output the order of `setTimeout`, Promise, and synchronous code.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// Output: 1, 4, 3, 2
```
Synchronous code runs first (1, 4). Microtasks (Promises) run before macrotasks (setTimeout). So 3 runs before 2.

---

#### 211. Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.

[↑ Back to Table of Contents](#table-of-contents)


`for (var i = 0; i < 5; i++) setTimeout(() => console.log(i), 0)` prints `5` five times. `var` is function-scoped — all callbacks close over the same `i`. Fix 1: `let` in the loop (block-scoped, new binding per iteration). Fix 2: IIFE `(function(i) { setTimeout(...) })(i)`. Fix 3: `setTimeout(console.log, 0, i)`.

---

#### 212. Design a retry mechanism with exponential backoff for API calls.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
async function withRetry(fn, retries = 3, baseDelay = 100) {
  for (let attempt = 0; attempt < retries; attempt++) {
    try { return await fn(); }
    catch (err) {
      if (attempt === retries - 1) throw err;
      const delay = baseDelay * 2 ** attempt + Math.random() * 100;
      await new Promise(r => setTimeout(r, delay));
    }
  }
}
```
Jitter prevents thundering herd when many clients retry simultaneously.

---

#### 213. Situation: You need to run 100 API calls but limit concurrency to 5 — how?

[↑ Back to Table of Contents](#table-of-contents)


Implement a concurrency limiter: maintain a running count and a queue. When running < limit, start a task. When a task completes, start the next queued one. Or use `p-limit` (npm). Alternatively, chunk the array into groups of 5 and `await Promise.all(chunk)` per group — less dynamic but simple for batch processing.

---

#### 214. How would you implement server-sent events (SSE) on the client side?

[↑ Back to Table of Contents](#table-of-contents)


`const source = new EventSource('/events')`. `source.onmessage = e => handle(e.data)`. `source.addEventListener('customEvent', handler)`. `source.onerror` for reconnection logic. SSE auto-reconnects on disconnect. One-way server-to-client only. Use `source.close()` to stop. Better than polling; simpler than WebSockets for push-only scenarios.

---

#### 215. Situation: Design a retry mechanism for a failed API call.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
async function fetchWithRetry(url, options = {}, retries = 3, delay = 1000) {
  try {
    const res = await fetch(url, options);
    if (!res.ok) throw new Error(`HTTP ${res.status}`);
    return await res.json();
  } catch (err) {
    if (retries === 0) throw err;
    await new Promise(r => setTimeout(r, delay));
    return fetchWithRetry(url, options, retries - 1, delay * 2); // exponential backoff
  }
}
```

---

#### 216. Situation: How do you cancel a fetch request?

[↑ Back to Table of Contents](#table-of-contents)


Use `AbortController`. Create a controller, pass its signal to `fetch`, and call `controller.abort()` to cancel. The fetch rejects with an `AbortError`.

```javascript
const controller = new AbortController();
const timeout = setTimeout(() => controller.abort(), 5000);
try {
  const res = await fetch(url, { signal: controller.signal });
  clearTimeout(timeout);
  return await res.json();
} catch (err) {
  if (err.name === 'AbortError') console.log('Request cancelled');
  else throw err;
}
```

---

#### 217. Implement `Promise.all` from scratch (already covered above).

[↑ Back to Table of Contents](#table-of-contents)


*(No answer text was present in the source.)*

---

#### 218. How would you handle multiple API calls efficiently without blocking the UI?

[↑ Back to Table of Contents](#table-of-contents)


**Answer:**  
In a Node.js backend, “blocking the UI” usually refers to blocking the event loop. For frontend, it’s about keeping the UI responsive. I’ll cover both.

**Backend (Node.js):**
- Use `Promise.all` or `Promise.allSettled` to run independent API calls in parallel.
- Avoid sequential `await` calls unless there is a dependency.
- Offload CPU‑intensive tasks to worker threads (`worker_threads`) or a separate service so the main event loop remains free.
- Use streaming and back‑pressure when dealing with large payloads to avoid memory pressure.

**Frontend (Browser):**
- Use `Promise.all` for parallel requests, but be mindful of browser connection limits (usually 6 per origin). Group requests accordingly.
- Implement request caching (e.g., with React Query or SWR) to avoid duplicate calls.
- Show skeleton loaders or optimistic UI so the user perceives responsiveness.
- If calls are heavy, use Web Workers to process data without blocking the main thread.
- Debounce or throttle user‑triggered API calls (e.g., search inputs) to reduce unnecessary requests.

---

## DOM, Browser APIs & Events

### Intermediate

#### 219. What is the DOM?

[↑ Back to Table of Contents](#table-of-contents)


The Document Object Model — a tree-structured representation of an HTML document created by the browser. JavaScript uses the DOM API to read and manipulate the page's structure, content, and styles. Each HTML element becomes a Node object with properties and methods.

---

#### 220. What is the difference between `localStorage`, `sessionStorage`, and cookies?

[↑ Back to Table of Contents](#table-of-contents)


`localStorage`: key-value, persists across sessions, same-origin, up to ~5MB. `sessionStorage`: same-origin, cleared when tab closes. Cookies: sent with every HTTP request (server access), can have expiry, `HttpOnly` flag prevents JS access. Use cookies for auth tokens, `localStorage` for non-sensitive client-only data.

---

#### 221. How do you select DOM elements?

[↑ Back to Table of Contents](#table-of-contents)


`document.getElementById('id')` — returns single element. `document.querySelector('css-selector')` — returns first match. `document.querySelectorAll('css-selector')` — returns NodeList of all matches. `document.getElementsByClassName('cls')` / `getElementsByTagName('tag')` — live HTMLCollections. Prefer `querySelector`/`querySelectorAll` for flexibility.

---

#### 222. How do you create, append, and remove DOM elements?

[↑ Back to Table of Contents](#table-of-contents)


Create: `document.createElement('div')`. Set content: `el.textContent = 'text'` or `el.setAttribute('class', 'box')`. Append: `parent.appendChild(el)` or `parent.append(el)` (newer, accepts strings). Insert: `parent.insertBefore(el, ref)` or `el.insertAdjacentElement('position', newEl)`. Remove: `el.remove()` or `parent.removeChild(el)`.

---

#### 223. What is the `DOMContentLoaded` vs `load` event?

[↑ Back to Table of Contents](#table-of-contents)


`DOMContentLoaded`: fires when HTML is fully parsed and DOM is ready — before images/stylesheets finish loading. `load` (on `window`): fires when ALL resources (images, styles, scripts) have loaded. Use `DOMContentLoaded` for DOM manipulation that doesn't depend on images; use `load` when you need images to be loaded.

---

#### 224. What is `localStorage` vs `sessionStorage` vs cookies?

[↑ Back to Table of Contents](#table-of-contents)


`localStorage`: persists until explicitly cleared, ~5MB, origin-scoped, not sent with requests. `sessionStorage`: persists per tab until tab closes, ~5MB, not sent with requests. `cookies`: sent with every HTTP request (for auth), can have expiry, smaller (~4KB), can be HttpOnly (not accessible by JS) — critical for security.

---

#### 225. How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)

[↑ Back to Table of Contents](#table-of-contents)


The browser rendering pipeline typically involves these steps (per frame):

1. **Parsing HTML** → DOM tree, CSS → CSSOM tree.
2. **Style**: Combine DOM and CSSOM into a render tree (visible nodes with computed styles).
3. **Layout (Reflow)**: Calculate geometry (position, size) for each node in the render tree.
4. **Paint**: Fill in pixels – draw text, colors, images, borders, shadows (creates layers).
5. **Composite**: Combine layers (GPU) and draw to screen.

**Optimizations**:
- Changing properties that affect layout (width, height, position) trigger **layout + paint + composite**.
- Changing paint‑only properties (color, background) trigger **paint + composite**.
- Changing transform/opacity (on a separate layer) triggers **composite only** (the fastest).

---

##### ES6+ Modern Features

---

#### 226. What is event bubbling and capturing?

[↑ Back to Table of Contents](#table-of-contents)


Events propagate in three phases: **Capture phase** (top → target), **Target phase** (at element), **Bubble phase** (target → top). By default, event listeners use bubbling. Pass `true` or `{capture: true}` to `addEventListener` to listen during capture phase. Most events bubble; some don't (e.g., `focus`, `blur` — use `focusin`/`focusout`).

---

#### 227. What is `MutationObserver`?

[↑ Back to Table of Contents](#table-of-contents)


Watches for DOM changes (child additions, attribute changes, text modifications) and fires a callback asynchronously with a list of `MutationRecord` objects. More efficient than polling. Used in libraries for tracking DOM changes without reflow.

---

#### 228. What is `ResizeObserver`?

[↑ Back to Table of Contents](#table-of-contents)


Watches when an element's size changes and fires a callback. Better than `window.resize` (which fires for the whole window). Used for responsive components that need to react to their own size — container queries in JS.

---

#### 229. What is the History API?

[↑ Back to Table of Contents](#table-of-contents)


`history.pushState(state, title, url)` — adds an entry to the browser's history stack and changes the URL without a page reload. `history.replaceState()` — replaces current entry. `window.onpopstate` — fires when user navigates back/forward. Foundation of client-side routing in SPAs.

---

#### 230. What is the Fetch API vs XMLHttpRequest?

[↑ Back to Table of Contents](#table-of-contents)


`fetch` is Promise-based, cleaner syntax, supports streams, no built-in timeout/progress. `XMLHttpRequest` is callback-based, supports progress events and synchronous calls (avoid sync). `fetch` does not reject on HTTP errors (only on network failure) — always check `response.ok`.

---

#### 231. What is the Web Worker API?

[↑ Back to Table of Contents](#table-of-contents)


Runs JavaScript in a background thread, separate from the main thread. Communicates via `postMessage`/`onmessage`. No DOM access. Used for CPU-intensive tasks (image processing, data parsing, encryption) to avoid blocking the main thread.

---

#### 232. What is `requestAnimationFrame`?

[↑ Back to Table of Contents](#table-of-contents)


Schedules a callback before the next browser repaint. Runs at the display refresh rate (~60fps). Better than `setTimeout` for animations — synchronized with the browser's paint cycle, paused in background tabs, and not subject to throttling.

---

#### 233. What is reflow and repaint?

[↑ Back to Table of Contents](#table-of-contents)


**Reflow (layout)**: browser recalculates positions/dimensions of elements — expensive, cascades. Triggered by: adding/removing elements, changing size/position/font. **Repaint**: browser redraws pixels — less expensive. Triggered by: changing color, visibility, shadow. Minimize by batching DOM changes, using `documentFragment`, CSS transforms (GPU-composited), and avoiding reading layout properties in a loop.

---

#### 234. What is `event.stopPropagation()` vs `event.preventDefault()`?

[↑ Back to Table of Contents](#table-of-contents)


`stopPropagation()`: stops the event from bubbling up (or capturing down) to parent elements. `preventDefault()`: prevents the browser's default action (form submission, link navigation, checkbox toggle). They are independent — you can call one, both, or neither. `stopImmediatePropagation()` also prevents other listeners on the same element.

---

#### 235. What is the difference between `addEventListener` and `onclick`?

[↑ Back to Table of Contents](#table-of-contents)


`onclick` is an element property — only one handler can be set (later assignment overrides). `addEventListener` allows multiple handlers for the same event on the same element, supports capture phase, and can be removed with `removeEventListener`. Always prefer `addEventListener`.

---

#### 236. What is the `fetch` API?

[↑ Back to Table of Contents](#table-of-contents)


A modern Promise-based API for HTTP requests, replacing `XMLHttpRequest`. `fetch(url, options)` returns a Promise of a `Response`. You must call `.json()`, `.text()`, or `.blob()` to read the body (also async). A `fetch` only rejects on network failure — not on 4xx/5xx responses (check `response.ok`).

---

#### 237. What is the Intersection Observer API?

[↑ Back to Table of Contents](#table-of-contents)


An async API to observe when an element enters or leaves the viewport (or another element). More performant than scroll event listeners. Use for: lazy loading images, infinite scroll, animations on scroll, analytics visibility tracking.

---

#### 238. What is the MutationObserver API?

[↑ Back to Table of Contents](#table-of-contents)


Watches for changes to the DOM tree (child additions/removals, attribute changes, text changes). Fires asynchronously (as a microtask). Use when you need to react to DOM changes made by third-party scripts or when you can't use your own state management.

---

#### 239. What are Web Workers?

[↑ Back to Table of Contents](#table-of-contents)


Background threads that run JS code without blocking the main thread. No DOM access. Communicate with the main thread via `postMessage`/`onmessage`. Use for CPU-intensive tasks (image processing, crypto, parsing large JSON). Shared Workers can be accessed by multiple tabs. Service Workers intercept network requests.

---

#### 240. What is `requestAnimationFrame` and why use it for animations?

[↑ Back to Table of Contents](#table-of-contents)


Schedules a callback before the browser's next repaint (~60fps). Pauses automatically when tab is hidden (saves battery/CPU). Passes a timestamp for smooth, frame-rate-independent animations. Much better than `setInterval` for visual updates because it syncs with the display refresh cycle.

---

### Senior / Scenario

#### 241. Explain how you would implement virtual scrolling in vanilla JavaScript.

[↑ Back to Table of Contents](#table-of-contents)


Calculate item height. Determine total scroll height. Render only visible items + buffer. On scroll, update the range of visible indices. Translate the rendered container with `transform: translateY` instead of `top` (avoids reflow). Recycle DOM nodes instead of creating/destroying them.

---

#### 242. How do you ensure JavaScript is accessible?

[↑ Back to Table of Contents](#table-of-contents)


Manage focus after dynamic content changes. Announce dynamic updates via `aria-live` regions. Don't rely solely on color or hover states. Ensure all interactive elements are keyboard operable (Enter/Space, arrow keys per ARIA patterns). Test with screen readers (NVDA, VoiceOver). Use eslint-plugin-jsx-a11y for automated linting.

---

#### 243. How would you implement feature detection in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Check for the feature's existence before using it: `if ('IntersectionObserver' in window)`. For methods: `if (typeof arr.flat === 'function')`. For CSS: `CSS.supports('display', 'grid')`. Prefer feature detection over user-agent sniffing (unreliable). Use polyfills for missing features rather than forking code.

---

#### 244. Design a simple virtual DOM diffing algorithm.

[↑ Back to Table of Contents](#table-of-contents)


Represent nodes as `{type, props, children}` objects. Diff function: if types differ, replace entirely. If same type, diff props — apply changed/removed/added props to the real DOM node. Recurse into children: use keys for stable matching; add/remove/patch as needed. Apply all changes in the commit phase after the full diff.

---

#### 245. Situation: Users report your web app crashes their browser tab — what do you investigate?

[↑ Back to Table of Contents](#table-of-contents)


Check for infinite loops (missing loop exit condition, infinite recursion). Check memory usage in Task Manager / DevTools Memory tab — look for heap growth. Check for WebSocket or polling connections sending enormous payloads. Look for `setInterval` without `clearInterval`. Check for canvas or WebGL without proper cleanup. Use `performance.memory` API and heap snapshots to narrow down.

---

## Modules, Tooling & TypeScript

### Intermediate

#### 246. What is the difference between JavaScript and TypeScript?

[↑ Back to Table of Contents](#table-of-contents)


TypeScript is a statically typed superset of JavaScript that compiles down to plain JS. TypeScript adds interfaces, generics, enums, and type annotations. These are erased at compile time – runtime behavior is identical to JS.

---

#### 247. What is the JavaScript pipeline operator proposal?

[↑ Back to Table of Contents](#table-of-contents)


The `|>` operator (Stage 2) allows `value |> fn1(%) |> fn2(%)`, making pipelines readable without nesting or composition helpers. `%` is the placeholder for the piped value. Still in proposal — use Babel plugin for early access. Competing with the Hack-style (with %) and F#-style (without) proposals.

---

#### 248. What is the TC39 proposal process and how do you track upcoming JavaScript features?

[↑ Back to Table of Contents](#table-of-contents)


Proposals go through 5 stages: Stage 0 (idea), Stage 1 (proposal), Stage 2 (draft spec), Stage 3 (candidate — implementations begin), Stage 4 (finished — included in next ES spec). Track at the tc39/proposals GitHub repo. Stage 3 proposals are generally safe to use with Babel/TypeScript. Stage 4 proposals ship in the next ECMAScript edition.

---

#### 249. What is TypeScript and how does it relate to JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


TypeScript is a superset of JavaScript — all valid JS is valid TypeScript. It adds static type annotations that are removed at compile time (transpiled to plain JS). Provides compile-time type checking, better IDE support, and self-documenting code. Maintained by Microsoft.

---

#### 250. What are named exports vs default exports in ES modules?

[↑ Back to Table of Contents](#table-of-contents)


Named: `export const foo = 1` — imported as `import {foo} from './mod'`. Default: `export default function(){}` — imported as `import anything from './mod'`. A module can have many named exports but only one default. Named exports are generally preferred for tree-shaking and explicitness.

---

#### 251. What is dynamic `import()`?

[↑ Back to Table of Contents](#table-of-contents)


`import('./module.js')` returns a Promise that resolves to the module's namespace object. Enables lazy loading and code splitting — load code on demand rather than upfront. Unlike static `import`, it can be inside conditions or functions.

---

#### 252. What is tree shaking and how does it relate to ES modules?

[↑ Back to Table of Contents](#table-of-contents)


Tree shaking removes unused exports from the final bundle using static analysis. Only works with ES module syntax (`import`/`export`) — not CommonJS (`require`). Write named exports, avoid side-effectful imports, mark packages as `"sideEffects": false` in `package.json`.

---

#### 253. What is the CommonJS module system?

[↑ Back to Table of Contents](#table-of-contents)


Node.js's original module system: `require()` to import, `module.exports` or `exports.foo` to export. Synchronous, evaluated at load time. Still widely used in Node.js server code and older packages. Being gradually replaced by ESM.

---

#### 254. What are ES Modules (ESM)?

[↑ Back to Table of Contents](#table-of-contents)


The standard JS module system: `import`/`export`. Static — imports are resolved at parse time, enabling tree shaking. Asynchronous loading in browsers. `"type": "module"` in `package.json` enables ESM in Node.js. `.mjs` extension also works.

---

#### 255. What is the difference between named and namespace imports?

[↑ Back to Table of Contents](#table-of-contents)


Named: `import {foo, bar} from './mod'` — imports specific exports. Namespace: `import * as mod from './mod'` — imports all exports as properties of a single object. Namespace imports prevent tree shaking of unused exports.

---

#### 256. What is module federation?

[↑ Back to Table of Contents](#table-of-contents)


A Webpack 5 feature (and now broader concept) allowing multiple independently deployed applications to share code at runtime. Module A can dynamically load components from Module B's deployed bundle. Used in micro-frontend architectures.

---

#### 257. What are package.json `exports` and `main` fields?

[↑ Back to Table of Contents](#table-of-contents)


`main`: entry point for CommonJS/legacy resolvers. `exports`: modern conditional exports — specify different entry points for ESM, CJS, browser, Node, types. `exports` takes precedence over `main` in modern tooling. Enables dual CJS/ESM packages.

---

#### 258. Explain the JavaScript module resolution algorithm.

[↑ Back to Table of Contents](#table-of-contents)


For bare specifiers (`import 'lodash'`): check `node_modules`, resolve `package.json exports`/`main`. For relative paths (`./util`): try exact, then `.js`, `.mjs`, `.cjs`, `/index.js`. For browsers: relies on import maps or bundlers (no `node_modules` resolution natively). TypeScript adds path aliases and `baseUrl` on top.

---

#### 259. What is the Module pattern?

[↑ Back to Table of Contents](#table-of-contents)


Uses an IIFE or ES modules to encapsulate private state and expose a public API. Prevents global namespace pollution. The classic pre-module pattern:
```javascript
const counter = (function() {
  let count = 0;
  return { increment: () => ++count, getCount: () => count };
})();
```

---

#### 260. What is the Revealing Module pattern?

[↑ Back to Table of Contents](#table-of-contents)


A variation of the Module pattern where all functions/variables are defined privately, and an object literal is returned that reveals only the public members by name. Makes clear what's public and what's private.

---

#### 261. What are ES Modules (`import`/`export`)?

[↑ Back to Table of Contents](#table-of-contents)


The official standard module system. Static `import`/`export` declarations are analyzed at parse time (enables tree shaking). Modules have their own scope, are strict by default, run once (cached), and support cyclic dependencies. Works in modern browsers (`<script type="module">`) and Node.js (`.mjs` or `"type":"module"` in package.json).

---

#### 262. What is the difference between default and named exports?

[↑ Back to Table of Contents](#table-of-contents)


Named: `export const foo = 1` — imported as `import { foo } from './m'`. Can have many per file. Import name must match (or be aliased with `as`). Default: `export default value` — imported as `import anything from './m'`. Only one per file. Named exports are preferred for tree-shaking and refactoring safety.

---

#### 263. What is CommonJS (`require`/`module.exports`)?

[↑ Back to Table of Contents](#table-of-contents)


Node.js's original module system. `const x = require('./x')` — synchronous, evaluated at runtime. `module.exports = value` to export. Modules are cached after the first load. Can export a function, object, or primitive. Cannot be statically analyzed (limits tree shaking).

---

#### 264. What is the difference between CommonJS and ES Modules?

[↑ Back to Table of Contents](#table-of-contents)


CJS: synchronous `require`, `module.exports`, dynamic (can be conditional), not statically analyzable, default in Node.js. ESM: asynchronous, static `import`/`export`, tree-shakeable, `this` is `undefined` at module level, supported in browsers natively. ESM is the future standard; Node.js supports both.

---

#### 265. What is a bundler (Webpack, Rollup, Vite)?

[↑ Back to Table of Contents](#table-of-contents)


A tool that takes JavaScript modules (and other assets) and combines them into optimized files for deployment. Handles dependency resolution, code splitting, tree shaking, minification, and asset processing. Webpack: powerful, configurable, most popular. Rollup: great for libraries (clean ESM output). Vite: fast dev server with native ESM + Rollup for production.

---

##### Performance & Memory

---

#### 266. What are source maps?

[↑ Back to Table of Contents](#table-of-contents)


Files that map minified/compiled production code back to the original source. Enable readable stack traces and breakpoints in DevTools despite bundling and transpilation. Generated by bundlers (webpack, Vite) with a configuration option.

---

#### 267. What is tree shaking?

[↑ Back to Table of Contents](#table-of-contents)


Dead code elimination based on static analysis of ES module imports/exports. Bundlers (Rollup, Webpack, Vite) detect exported code that's never imported and exclude it from the bundle. Requires: ES modules (not CJS), no side-effectful imports, correct `sideEffects` field in package.json.

---

#### 268. What is transpilation and what does Babel do?

[↑ Back to Table of Contents](#table-of-contents)


Transpilation converts modern JS (ES2022+) to older JS (ES5) so it runs in older browsers. Babel: a popular transpiler with plugin/preset system. Transforms JSX, TypeScript, and modern syntax. In Vite projects, esbuild handles basic transpilation faster; Babel needed only for advanced transforms.

---

#### 269. What is source mapping?

[↑ Back to Table of Contents](#table-of-contents)


A file (`.map`) that maps minified/transpiled code back to the original source. Enables debugging production code with original source in DevTools. Generated by bundlers/transpilers. Should be served in staging, sometimes restricted in production.

---

#### 270. What is npm and what is `package.json`?

[↑ Back to Table of Contents](#table-of-contents)


npm (Node Package Manager): the default package manager for Node.js. Manages project dependencies, scripts, and publishing. `package.json`: manifest file containing project metadata, dependencies, devDependencies, scripts (`start`, `test`, `build`), version, and configuration for tools.

---

#### 271. What is the difference between `dependencies` and `devDependencies`?

[↑ Back to Table of Contents](#table-of-contents)


`dependencies`: packages needed to run the app in production (Express, React, Lodash). `devDependencies`: packages needed only during development (Jest, ESLint, Babel, TypeScript). Distinguishing them matters for keeping production `node_modules` lean. `npm install --production` skips devDependencies.

---

#### 272. What are the basic types in TypeScript?

[↑ Back to Table of Contents](#table-of-contents)


Primitive: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`. Object: `object`, `array` (`number[]` or `Array<number>`), tuple (`[string, number]`), `enum`. Special: `any` (opts out of checking), `unknown` (safe any), `never` (never returns), `void` (no return value).

---

#### 273. What is `any` vs `unknown` in TypeScript?

[↑ Back to Table of Contents](#table-of-contents)


`any`: disables type checking entirely — you can do anything with it. Unsafe. `unknown`: type-safe alternative to `any`. You can't perform operations on `unknown` without first narrowing its type (type guard, assertion). Prefer `unknown` over `any` when type is truly unknown.

---

#### 274. What is a type assertion?

[↑ Back to Table of Contents](#table-of-contents)


Telling TypeScript "trust me, I know the type of this value." `const el = document.getElementById('btn') as HTMLButtonElement`. Doesn't do runtime conversion — purely compile-time. Use when you have more context than the type system. Can use `as Type` or `<Type>value` (JSX incompatible).

---

#### 275. What is a union type vs intersection type?

[↑ Back to Table of Contents](#table-of-contents)


Union (`A | B`): the value can be type A OR type B. Use with type guards to narrow. Intersection (`A & B`): the value must satisfy BOTH type A AND type B — combines all properties. Union is OR; intersection is AND.

---

#### 276. What are generics in TypeScript?

[↑ Back to Table of Contents](#table-of-contents)


A way to write reusable code that works with multiple types. `function identity<T>(arg: T): T { return arg; }`. The type parameter `T` is a placeholder filled in at usage. Used in containers, utilities, and APIs to maintain type safety without losing flexibility.

---

#### 277. What is the difference between `interface` and `type`?

[↑ Back to Table of Contents](#table-of-contents)


`interface`: can be merged (declaration merging), better for object shapes and OOP. `type`: more flexible — can represent primitives, unions, intersections, tuples, mapped types. Both can extend each other (`interface extends type` and vice versa). For objects, either works; prefer `interface` for public APIs, `type` for complex type math.

---

#### 278. What is type narrowing?

[↑ Back to Table of Contents](#table-of-contents)


Reducing a broad type to a more specific type within a code branch using type guards. Methods: `typeof` checks, `instanceof`, `in` operator, truthiness checks, equality checks, discriminated unions, user-defined type predicates (`fn(x): x is Type`). TypeScript understands these patterns and narrows the type automatically.

---

## Error Handling & Debugging

### Intermediate

#### 279. What are the types of errors in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


`SyntaxError` (code cannot be parsed), `ReferenceError` (undefined variable), `TypeError` (wrong type, null access), `RangeError` (value out of range), `URIError`, `EvalError`. All extend `Error`. Custom errors extend `Error` with a name property.

---

#### 280. How do you debug JavaScript effectively?

[↑ Back to Table of Contents](#table-of-contents)


`debugger` statement (pauses in DevTools), `console.log/table/trace/time`, breakpoints in DevTools, conditional breakpoints, watch expressions, the Call Stack panel (for async), and network panel for API calls. For production: error monitoring (Sentry), structured logging.

---

#### 281. What is the `Error` object?

[↑ Back to Table of Contents](#table-of-contents)


Has properties: `name` (type of error, e.g., `'TypeError'`), `message` (description), `stack` (stack trace string, non-standard but universally supported), `cause` (ES2022 — error that caused this one, for chaining). Create with `new Error('message')`.

---

#### 282. How do you create custom error types?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}
```
Throw with `throw new ValidationError(...)`. Catch with `instanceof ValidationError`.

---

#### 283. What is `try/catch/finally` and how does `finally` behave?

[↑ Back to Table of Contents](#table-of-contents)


`try` runs code that might throw. `catch(e)` handles thrown errors. `finally` runs no matter what — even if `try` returns or `catch` throws. If `finally` returns a value, it overrides the `try`/`catch` return — a subtle behavior to be aware of.

---

#### 284. What is the `Error.cause` property (ES2022)?

[↑ Back to Table of Contents](#table-of-contents)


`throw new Error('message', {cause: originalError})` — chains errors to preserve the original cause. `error.cause` holds the original error. Useful for wrapping low-level errors with higher-level context without losing the original stack trace.

---

#### 285. What is a `try/catch/finally` block?

[↑ Back to Table of Contents](#table-of-contents)


`try`: code that might throw. `catch(err)`: runs if an error is thrown — `err` is the Error object. `finally`: always runs regardless of success or failure — used for cleanup. `throw` can throw any value, but throw Error objects for best debuggability (stack trace).

---

#### 286. What are the built-in error types?

[↑ Back to Table of Contents](#table-of-contents)


`Error` (base), `TypeError` (wrong type), `ReferenceError` (variable not found), `SyntaxError` (invalid syntax, usually parse-time), `RangeError` (value out of range, e.g., stack overflow), `URIError` (malformed URI), `EvalError` (eval-related, rare). Each is a constructor — check with `err instanceof TypeError`.

---

#### 287. How do you create a custom error?

[↑ Back to Table of Contents](#table-of-contents)


Extend the `Error` class:
```javascript
class AppError extends Error {
  constructor(message, statusCode) {
    super(message);
    this.name = 'AppError';
    this.statusCode = statusCode;
  }
}
throw new AppError('Not found', 404);
```
Setting `this.name` is important for readable stack traces.

---

### Senior / Scenario

#### 288. How do you handle JavaScript errors in a production application end-to-end?

[↑ Back to Table of Contents](#table-of-contents)


Error boundaries (React) for UI crashes. `window.onerror` and `window.onunhandledrejection` for unhandled errors. Integrate Sentry/Datadog with breadcrumbs and user context. Source maps for readable stack traces. Alert on error rate spikes. `try/catch` for expected failures with user-facing messages. Structured logging for server-side.

---

#### 289. How would you design JavaScript error handling for a large team?

[↑ Back to Table of Contents](#table-of-contents)


Establish error taxonomy — `ValidationError`, `NetworkError`, `NotFoundError` all extending `AppError` with codes. Central `handleError` function that: logs structured data, triggers monitoring, maps to user messages. Lint rules for no floating promises, no empty catch blocks. Document error contracts for every public function. Integration tests for error paths.

---

#### 290. Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?

[↑ Back to Table of Contents](#table-of-contents)


No. The `try/catch` has already exited by the time the `setTimeout` callback runs (it runs in a future event loop iteration). Handle errors inside the callback itself with an inner `try/catch`, or use `window.onerror` / `process.on('uncaughtException')` for a global handler.

---

## Performance & Memory

### Intermediate

#### 291. How does V8 optimize JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


JIT (Just-In-Time) compilation: interprets first, then compiles hot code to machine code. Hidden classes: V8 creates internal type shapes for objects — keep object property order consistent. Inline caching: caches property lookup results. Avoid deoptimization triggers: type changes, `arguments`, `eval`, `try/catch` in hot loops.

---

#### 292. How do you approach writing JavaScript for low-powered devices?

[↑ Back to Table of Contents](#table-of-contents)


Minimize main thread work — offload to Workers. Avoid long tasks (> 50ms). Use passive event listeners. Reduce layout thrash — batch reads and writes. Minimize repaints. Prefer CSS animations over JS animations. Code split aggressively. Avoid large dependency bundles. Test on real low-end devices with CPU throttling in DevTools. Use the `scheduler` API (when available) to yield to the browser.

---

#### 293. How do you profile and optimize a JavaScript animation that's dropping frames?

[↑ Back to Table of Contents](#table-of-contents)


Use Chrome DevTools Performance tab to record frames. Look for long tasks (red bars) on the main thread. Move expensive calculations to a Worker. Avoid layout thrash — read all properties before writing. Use `transform` and `opacity` for GPU-accelerated animations. Use `requestAnimationFrame` for timing. Reduce paint area with `will-change: transform`.

---

#### 294. When NOT to use JavaScript: CPU-heavy tasks, long-running blocking logic – use backend or workers.

[↑ Back to Table of Contents](#table-of-contents)


**Scenarios**:
- **Large data processing** (sorting, filtering, complex calculations) – offload to Web Workers or the backend.
- **Image/video processing** – use backend services or Canvas + WebGL with off‑thread rendering.
- **Intensive animations** – use CSS animations/transitions instead of JS, or requestAnimationFrame with careful batching.
- **Real‑time ML inference** – consider WebAssembly or backend.

**Why**:
- JavaScript runs on the main thread; blocking it leads to jank, unresponsiveness.
- Web Workers run in a separate thread, allowing parallel execution without blocking UI.
- Backend offloading is ideal for heavy or security‑sensitive tasks.

---

##### Variables, Scope & Execution Context

---

#### 295. What is a closure memory leak and how do you avoid it?

[↑ Back to Table of Contents](#table-of-contents)


If a closure holds a reference to a large object or DOM node and is never released, that memory can't be garbage collected. Avoid by: nullifying references when no longer needed, removing event listeners, avoiding closures that capture large objects unnecessarily, and using `WeakMap`/`WeakRef` for holding references that shouldn't prevent GC.

---

#### 296. What are memory leaks in JavaScript and what causes them?

[↑ Back to Table of Contents](#table-of-contents)


Memory that is allocated but never freed because references still exist. Common causes: event listeners not removed, closures holding references, global variables, detached DOM nodes still referenced in JS, interval/timeout callbacks holding references.

---

#### 297. What is a memory leak and what causes them?

[↑ Back to Table of Contents](#table-of-contents)


Memory that is no longer needed but not released because references still exist. Common causes: forgotten event listeners (not removed), closures holding large objects, global variables accumulating data, DOM references held after nodes are removed, detached DOM nodes, `setInterval` never cleared.

---

#### 298. How do you profile JavaScript performance?

[↑ Back to Table of Contents](#table-of-contents)


Browser DevTools Performance panel: record, then analyze flame chart for long tasks, scripting time, rendering. Memory panel: take heap snapshots to find leaks. `console.time()` / `console.timeEnd()` for rough timing. `performance.mark()` / `performance.measure()` for precise custom measurements via Performance API.

---

#### 299. What causes memory leaks in frontend applications? How to prevent them?

[↑ Back to Table of Contents](#table-of-contents)


Common memory leaks:
- **Global variables**: Accidentally creating globals (`function foo() { x = 10; }`) – use `'use strict'`.
- **Forgotten timers**: `setInterval` / `setTimeout` not cleared.
- **Event listeners** not removed when elements are removed.
- **Closures** holding references to large objects.
- **Detached DOM elements**: Removing elements but still referencing them in JavaScript.
- **Out of scope references**: Variables captured in closures but no longer needed.

**Prevention**:
- Use `let`/`const` and strict mode.
- Clean up timers and listeners in lifecycle hooks (e.g., `componentWillUnmount`, `useEffect` cleanup).
- Avoid storing large data in global scope.
- Use weak references (`WeakMap`, `WeakSet`) for caching or metadata.
- Profile with Chrome DevTools (Memory tab) to identify leaks.

---

### Advanced

#### 300. What is the JavaScript garbage collection impact of closures?

[↑ Back to Table of Contents](#table-of-contents)


A closure keeps references to all variables in its outer scope alive, even those not explicitly used — in some engines. This can cause large objects to be retained unintentionally. Fix: nullify references when done (`largeData = null`), extract only needed values from outer scope rather than capturing the whole scope, use WeakRef for caches.

---

#### 301. What is garbage collection in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


JS engines automatically free memory that is no longer reachable. The most common algorithm is mark-and-sweep: starting from roots (global, stack), the engine marks all reachable objects and sweeps the rest. Closures can cause unintentional memory retention.

---

#### 302. How does garbage collection work in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


JS uses automatic GC, primarily via mark-and-sweep: starting from roots (global, stack), mark all reachable objects. Anything unreachable is garbage and its memory is freed. Modern engines use generational GC (young/old generation), incremental GC, and idle-time GC to minimize pauses.

---

#### 303. How does garbage collection work in V8?

[↑ Back to Table of Contents](#table-of-contents)


V8 uses a **generational, mark‑and‑sweep** garbage collector.

- **Heap**: Divided into **young generation** (newly allocated objects) and **old generation** (objects that survive multiple collections).
- **Minor GC (Scavenger)**: Runs frequently on the young generation, copying surviving objects to a survivor space. Very fast.
- **Major GC (Mark‑Sweep / Mark‑Compact)**: Runs less often on the old generation. It marks reachable objects, sweeps unreachable ones, and compacts to reduce fragmentation.
- **Incremental marking**: Long pauses are avoided by interleaving marking with JavaScript execution.

---

### Senior / Scenario

#### 304. A page is consuming too much memory over time — how would you detect and prevent memory leaks?

[↑ Back to Table of Contents](#table-of-contents)


**Answer:**  
Memory leaks in Node.js usually come from global caches, event listeners not removed, or lingering references.

- **Detection:**
  - Monitor heap size using `process.memoryUsage()` and look for steady growth.
  - Take heap snapshots (Chrome DevTools or `node --inspect`) and compare before/after operations to find objects that should have been garbage collected but persist.
  - Use `--trace-gc` to see GC activity; if GC runs frequently but heap grows, there’s a leak.
- **Common culprits:**
  - **Event listeners:** Forgetting `removeListener` on `EventEmitter` or `process.on`. Use tools like `why-is-node-running` to see pending listeners.
  - **Caches:** Unbounded caches (e.g., `Map` or object) that never expire. Implement TTL or size limits (use `lru-cache`).
  - **Closures:** Accidentally retaining large objects in closure scopes referenced by long‑living callbacks.
  - **Global variables:** Attaching large data to `global` or `module.exports` unintentionally.
- **Prevention:**
  - Use weak references (`WeakMap`, `WeakSet`) for caching when appropriate.
  - Always remove listeners in cleanup functions (e.g., `on('data', handler)` paired with `off('data', handler)`).
  - For HTTP servers, ensure responses are ended and streams are destroyed.
  - Use tools like `memwatch-next` or `node-memwatch` to detect leaks in tests.

---

##### Security

---

## Security

### Intermediate

#### 305. What is a timing attack and how does it relate to JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Inferring secret information from the time it takes to perform operations. String comparison with `===` short-circuits on the first mismatch — timing varies by how much matches. Use constant-time comparison for sensitive values (HMAC verification). `crypto.timingSafeEqual` in Node.js.

---

#### 306. How do you securely handle user input in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Never trust user input. Validate on both client (UX) and server (security). Escape before inserting into DOM (use `textContent`). Sanitize HTML with DOMPurify if HTML is needed. Use parameterized queries for databases. Encode for the output context (HTML, URL, JS).

---

#### 307. What is prototype pollution?

[↑ Back to Table of Contents](#table-of-contents)


An attack where `__proto__`, `constructor`, or `prototype` properties are set on user-supplied objects, affecting all objects in the application. Can be used to override methods on `Object.prototype`. Prevention: validate input keys (reject `__proto__`), use `Object.create(null)` for dictionaries, use `Map` instead of plain objects for user data.

---

#### 308. What is XSS (Cross-Site Scripting) and how do you prevent it?

[↑ Back to Table of Contents](#table-of-contents)


Injecting malicious scripts into pages viewed by other users. Prevention: never insert user-controlled HTML via `innerHTML` — use `textContent`. Use Content Security Policy (CSP) headers. Sanitize with DOMPurify when HTML is required. Escape output server-side.

---

#### 309. What is Content Security Policy (CSP)?

[↑ Back to Table of Contents](#table-of-contents)


An HTTP header that tells browsers which sources of content are allowed (scripts, styles, images, fonts). Mitigates XSS by blocking inline scripts and unauthorized external scripts. `Content-Security-Policy: script-src 'self' https://trusted.com`. Use `nonce` or `hash` for necessary inline scripts.

---

#### 310. What is XSS (Cross-Site Scripting)?

[↑ Back to Table of Contents](#table-of-contents)


An attack where malicious scripts are injected into web pages viewed by other users. Types: Stored (persisted in DB), Reflected (in URL), DOM-based (via client-side JS). Prevention: escape all user output (use `textContent` not `innerHTML`), CSP headers, sanitize with DOMPurify, avoid `eval()`.

---

#### 311. What is CSRF (Cross-Site Request Forgery)?

[↑ Back to Table of Contents](#table-of-contents)


Tricks authenticated users into making unintended requests to a site they're logged into. Prevention: CSRF tokens (unique per session, validated server-side), `SameSite=Strict` or `SameSite=Lax` cookies, check `Origin`/`Referer` headers, avoid side effects from GET requests.

---

##### Testing

---

#### 312. What are CORS and SOP (Same-Origin Policy)?

[↑ Back to Table of Contents](#table-of-contents)


SOP: browsers block JS from accessing resources from a different origin (protocol + domain + port). CORS: server opts in to cross-origin access via `Access-Control-Allow-Origin` headers. Preflight `OPTIONS` requests check permissions for non-simple requests.

---

#### 313. What is clickjacking and how do you prevent it?

[↑ Back to Table of Contents](#table-of-contents)


An attack where a transparent iframe overlays a legitimate site, tricking users into clicking on hidden elements. Prevention: `X-Frame-Options: DENY` or `SAMEORIGIN` HTTP header, or CSP `frame-ancestors 'none'` directive.

---

### Senior / Scenario

#### 314. How do you handle JavaScript in a security-sensitive context (e.g., fintech)?

[↑ Back to Table of Contents](#table-of-contents)


Subresource Integrity (SRI) on external scripts. Strict CSP. No `eval`, `new Function`, `innerHTML` with user data. Sanitize all inputs. HTTPS everywhere. `HttpOnly`/`Secure` cookies. Dependency auditing (`npm audit`). Regular penetration testing. Runtime Application Self-Protection (RASP). Code review for timing attacks and prototype pollution.

---

## Testing

### Intermediate

#### 315. How do you test asynchronous code in Jest?

[↑ Back to Table of Contents](#table-of-contents)


Return a Promise from the test, or use `async/await`. Use `done` callback for callback-style APIs. Jest's fake timers (`jest.useFakeTimers()`) control `setTimeout`/`setInterval`. Mock `fetch` or use MSW for network calls. `await waitFor(() => expect(...))` for async DOM updates.

---

#### 316. What is the testing pyramid for JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Unit tests (fast, many): individual functions, modules. Integration tests (medium): interactions between units, API calls. E2E tests (slow, few): full browser flows. Focus the most effort on integration tests — they give the best coverage-to-cost ratio for most JS apps.

---

#### 317. What is Jest and what does it provide?

[↑ Back to Table of Contents](#table-of-contents)


A zero-config testing framework: test runner, assertion library (`expect`), mocking (`jest.fn()`, `jest.mock()`), snapshot testing, code coverage. Works for both browser and Node.js code. The most popular JS testing solution.

---

#### 318. What is the difference between `jest.fn()`, `jest.spyOn()`, and `jest.mock()`?

[↑ Back to Table of Contents](#table-of-contents)


`jest.fn()`: creates a standalone mock function. `jest.spyOn(obj, 'method')`: replaces `obj.method` with a spy, preserving the original implementation by default. `jest.mock('./module')`: replaces an entire module with auto-mocked versions. Use `mockImplementation` or `mockReturnValue` to control behavior.

---

#### 319. What are snapshot tests?

[↑ Back to Table of Contents](#table-of-contents)


`expect(value).toMatchSnapshot()` serializes the value and saves it to a file on first run. Subsequent runs compare against the snapshot. Fast to write but prone to false positives — only use for stable, simple outputs. Prefer explicit assertions for complex behavior.

---

#### 320. What is test-driven development (TDD)?

[↑ Back to Table of Contents](#table-of-contents)


Red-Green-Refactor cycle: (1) write a failing test, (2) write the minimum code to pass, (3) refactor. TDD produces high test coverage, drives better API design, and reduces over-engineering. Can be slower initially but pays off in fewer bugs and confident refactoring.

---

#### 321. What is property-based testing?

[↑ Back to Table of Contents](#table-of-contents)


Instead of specific inputs, you define properties that should hold for any input. A library (fast-check, JSVerify) generates hundreds of random test cases. Excellent for finding edge cases you wouldn't think to write manually. Useful for pure functions and data transformation logic.

---

#### 322. What is unit testing?

[↑ Back to Table of Contents](#table-of-contents)


Testing individual functions or modules in isolation. Fast, focused, no external dependencies (use mocks/stubs). Verifies that a unit of code produces the correct output for a given input. Foundation of the testing pyramid. Tools: Jest, Vitest, Mocha.

---

#### 323. What is Jest?

[↑ Back to Table of Contents](#table-of-contents)


The most popular JavaScript testing framework. Zero-config by default, built-in mocking, code coverage, snapshot testing, and assertion library. Works with Node.js and browser environments (via jsdom). Supports TypeScript via Babel or ts-jest.

---

#### 324. What is TDD (Test-Driven Development)?

[↑ Back to Table of Contents](#table-of-contents)


Write tests first (failing), then write the minimum code to make them pass, then refactor. Cycle: Red → Green → Refactor. Benefits: forces clear requirements, prevents over-engineering, provides instant regression coverage. Can be slower initially but reduces debugging time.

---

#### 325. What is the difference between unit, integration, and E2E tests?

[↑ Back to Table of Contents](#table-of-contents)


**Unit**: tests one function/module in isolation — fast, deterministic. **Integration**: tests how multiple units work together — may use real database/service or mocks. **E2E**: tests the full application in a real browser — slowest, most realistic (Playwright, Cypress). Balance: many unit, some integration, few E2E.

---

##### Node.js & Runtime

---

#### 326. What is code coverage and what metrics matter?

[↑ Back to Table of Contents](#table-of-contents)


Percentage of code executed during tests: line, branch, function, statement coverage. Branch coverage is most meaningful — tests every code path. 100% coverage doesn't guarantee bug-free code; it only shows what was executed, not what was asserted correctly.

---

#### 327. What are mocks, stubs, and spies?

[↑ Back to Table of Contents](#table-of-contents)


**Mock**: replaces an entire module or function with a fake implementation. **Stub**: provides canned responses for specific calls (controls what a dependency returns). **Spy**: wraps real implementation to record calls (what args, how many times). Jest's `jest.fn()` and `jest.spyOn()` cover all these.

---

#### 328. What is code coverage?

[↑ Back to Table of Contents](#table-of-contents)


A metric showing what percentage of your code is executed by tests. Types: line coverage, branch coverage (if/else paths), function coverage, statement coverage. Run with `jest --coverage`. 100% coverage doesn't mean bug-free — focus on meaningful tests, not chasing numbers.

---

## Node.js & Runtime

### Junior

#### 329. What is Node.js?

[↑ Back to Table of Contents](#table-of-contents)


A JavaScript runtime built on Chrome's V8 engine. Enables server-side JavaScript. Non-blocking I/O via an event loop (powered by libuv). Single-threaded for JS execution but uses threads internally for I/O. Ideal for I/O-heavy apps (APIs, real-time, streaming); less ideal for CPU-heavy tasks (use Worker Threads).

---

##### Output & Tricky Questions

---

### Intermediate

#### 330. What is the Node.js event loop and how does it differ from the browser's?

[↑ Back to Table of Contents](#table-of-contents)


Node.js uses libuv for I/O and has additional phases: timers (`setTimeout`/`setInterval`), pending callbacks, idle, poll (I/O), check (`setImmediate`), close callbacks. `setImmediate` runs after I/O in the check phase — before a `setTimeout(fn, 0)` in I/O context.

---

#### 331. What is the Node.js event loop vs the browser event loop?

[↑ Back to Table of Contents](#table-of-contents)


Both use the event loop pattern but with different phases. Node.js (libuv): has explicit phases — timers → pending callbacks → idle/prepare → poll (I/O) → check (setImmediate) → close callbacks. Browser event loop is simpler. Key difference: Node has `setImmediate` and `process.nextTick` (runs before everything else in the current iteration).

---

#### 332. How do you write JavaScript that works in both browser and Node.js?

[↑ Back to Table of Contents](#table-of-contents)


Avoid environment-specific globals (`window`, `document`, `process`, `require`). Use feature detection. Use bundlers (Vite, Rollup) with appropriate targets. Write code against standard APIs (Fetch, Web Streams — now available in Node 18+). Publish CJS/ESM dual packages for library code.

---

#### 333. What is the difference between the browser and Node.js environments?

[↑ Back to Table of Contents](#table-of-contents)


Browser: has DOM, window, document, browser APIs (fetch, localStorage, alert), sandboxed. Node.js: has no DOM, has `process`, `__dirname`, `__filename`, `require`, built-in modules (`fs`, `http`, `path`, `crypto`, `os`), full file system access, can run servers. Both run the same JS language.

---

#### 334. What is the `cluster` module?

[↑ Back to Table of Contents](#table-of-contents)


Allows spawning multiple Node.js processes sharing the same port. Master process forks workers (one per CPU core). Distributes incoming connections across workers. Used to take advantage of multi-core CPUs since Node.js is single-threaded.

---

#### 335. What are Node.js streams?

[↑ Back to Table of Contents](#table-of-contents)


`Readable`, `Writable`, `Duplex`, `Transform` streams handle data in chunks rather than loading everything into memory. Pipe-able: `readStream.pipe(transformStream).pipe(writeStream)`. Essential for large file processing, HTTP responses, and real-time data.

---

#### 336. What is `Buffer` in Node.js?

[↑ Back to Table of Contents](#table-of-contents)


A fixed-size allocation of raw binary data (a subclass of `Uint8Array`). Used when dealing with file I/O, network protocols, or binary data. `Buffer.from('hello', 'utf8')`, `buf.toString('hex')`. Distinct from ArrayBuffer/TypedArrays in the browser.

---

#### 337. What are Worker Threads in Node.js?

[↑ Back to Table of Contents](#table-of-contents)


`worker_threads` module runs JS in parallel threads within the same process. Unlike `cluster` (separate processes), workers share memory via `SharedArrayBuffer`. Used for CPU-intensive tasks — image resizing, compression, parsing.

---

#### 338. What is the difference between `require` resolution and ESM resolution in Node.js?

[↑ Back to Table of Contents](#table-of-contents)


`require` looks for `.js`, then `index.js`, then checks `package.json main`. ESM requires explicit file extensions and respects the `exports` field. ESM cannot `require()` synchronously. Mixing both requires careful package configuration.

---

#### 339. What is `process.nextTick()`?

[↑ Back to Table of Contents](#table-of-contents)


Schedules a callback to run at the end of the current iteration of the Node.js event loop, before any I/O events or timers. Runs before Promises (microtasks) in Node.js's implementation. Use sparingly — too many nextTick callbacks can starve the event loop.

---

### Senior / Scenario

#### 340. Situation: A Node.js server is leaking memory — how do you diagnose it?

[↑ Back to Table of Contents](#table-of-contents)


Take heap snapshots with `node --inspect` and Chrome DevTools. Use `clinic.js` or `0x`. Look for growing retained size in heap snapshots. Common culprits: global caches without eviction, event listeners not removed, closures capturing large objects, `setInterval` not cleared. Take multiple snapshots over time and diff them.

---

#### 341. How would you handle large JSON files in Node.js?

[↑ Back to Table of Contents](#table-of-contents)


Don't load the entire file into memory with `JSON.parse`. Use streaming JSON parsers: `JSONStream`, `oboe`, or `stream-json`. Read the file as a Readable stream and pipe through the parser. Process records one at a time. For extremely large files, consider a line-delimited JSON format (NDJSON) which is easier to stream.

---

## Advanced JavaScript & Architecture

### Intermediate

#### 342. What would you look for when reviewing a junior developer's JavaScript PR?

[↑ Back to Table of Contents](#table-of-contents)


Missing `await` or unhandled Promises. Mutable data where immutable patterns were intended. `var` instead of `let`/`const`. Callback-style code where Promises/async-await are cleaner. Missing error handling. Potential XSS with `innerHTML`. Performance issues: loops inside loops, DOM queries in loops, missing debounce on event handlers. Missing tests for edge cases.

---

#### 343. How do you make a JavaScript library tree-shakeable?

[↑ Back to Table of Contents](#table-of-contents)


Use named exports (not a single default export object). Avoid side effects at module load time. Mark the package as `"sideEffects": false` in `package.json` (or list files that do have side effects). Use ES module format. Avoid importing one large utility that pulls in everything — provide granular per-function imports.

---

#### 344. What is a closure?

[↑ Back to Table of Contents](#table-of-contents)


A closure is a function that remembers and has access to variables from its outer (lexical) scope even after the outer function has returned. The inner function retains a reference to the outer scope's environment. Closures are fundamental to JavaScript – every function is technically a closure.

```javascript
function makeCounter() {
  let count = 0;
  return function() {
    return ++count; // accesses count from outer scope
  };
}
const counter = makeCounter();
counter(); // 1
counter(); // 2
```

---

#### 345. Give a practical use case for closures.

[↑ Back to Table of Contents](#table-of-contents)


A counter factory: `function makeCounter() { let count = 0; return () => ++count; }`. Each call to `makeCounter()` creates an independent counter with private state. The inner function closes over `count` and it cannot be accessed or modified externally.

---

#### 346. What is a common closure bug in loops?

[↑ Back to Table of Contents](#table-of-contents)


Using `var` in a `for` loop with async callbacks — all callbacks close over the same `var i`. Fix: use `let` (creates a new binding per iteration), or wrap in an IIFE to capture the current value. This is a classic interview trap.

---

#### 347. What are practical uses of closures?

[↑ Back to Table of Contents](#table-of-contents)


Data privacy/encapsulation (module pattern), factory functions, memoization, partial application, event handlers that remember state, maintaining state in async operations, and implementing the module pattern before ES modules existed.

---

#### 348. Explain closures with a real-world example

[↑ Back to Table of Contents](#table-of-contents)


A **closure** is the combination of a function and the lexical environment within which that function was declared. The inner function retains access to variables from its outer scope even after the outer function has returned.

**Real-world example: Counter factory**

```javascript
function createCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
// `count` is private and persists because the inner function closes over it.
```

**Use cases:** Data privacy, function factories, partial application, maintaining state in callbacks.

---

#### 349. What is `this` in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


`this` is a keyword that refers to the context in which a function is called — not where it was defined (except in arrow functions). Its value is determined at call time, not definition time. It can be the global object, the calling object, a class instance, or `undefined` (strict mode).

**What**  
`this` is a keyword that refers to the **execution context** of the current function call. Its value is determined **at call time** (except arrow functions, which use the `this` from their surrounding scope).

**Why**  
- Allows methods to access the object they belong to.  
- Enables reusable functions that can work on different objects depending on how they are called.  
- Essential for object‑oriented patterns and event handling.

**When**  
- Inside object methods (`obj.method()`) – `this` is `obj`.  
- In standalone function calls (strict mode: `undefined`; non‑strict: global object).  
- In event handlers – `this` is the element that received the event.  
- In constructor functions / classes – `this` is the new instance.  
- When you explicitly bind `this` using `.call()`, `.apply()`, or `.bind()`.  
- In arrow functions – `this` is lexically inherited (they don’t have their own).

**Where** (real examples)

```js
// Object method
const user = {
  name: 'Alice',
  greet() { console.log(this.name); }
};
user.greet(); // this = user -> 'Alice'

// Lost context (common pitfall)
const greetFn = user.greet;
greetFn(); // this = undefined (strict) or window -> error

// Event listener
button.addEventListener('click', function() {
  console.log(this); // the button element
});

// Arrow function – lexical this
const user2 = {
  name: 'Bob',
  greet: () => console.log(this.name) // this is from outer scope, not user2
};

// Constructor / class
class Person {
  constructor(name) { this.name = name; }
  say() { console.log(this.name); }
}
const p = new Person('Eve');
p.say(); // this = the instance

// Explicit binding
function show() { console.log(this); }
show.call({ id: 42 }); // this = { id: 42 }
```

> **Key rule**: Look at **how** the function is called, not where it’s written (except arrows).

---

#### 350. How do `call`, `apply`, and `bind` work?

[↑ Back to Table of Contents](#table-of-contents)


`fn.call(thisArg, a, b)` — invokes `fn` with `this` set to `thisArg`, args listed individually. `fn.apply(thisArg, [a, b])` — same but args as an array. `fn.bind(thisArg, a)` — returns a new function permanently bound to `thisArg` with optional pre-filled args (partial application).

---

#### 351. What are the four rules that determine `this`?

[↑ Back to Table of Contents](#table-of-contents)


1. Default binding: standalone function call → `undefined` (strict) or `global`. 2. Implicit binding: method call `obj.fn()` → `this = obj`. 3. Explicit binding: `fn.call(obj)` / `fn.apply(obj)` / `fn.bind(obj)`. 4. `new` binding: `new Fn()` → `this` is the new instance. Arrow functions ignore all rules and inherit `this` lexically.

---

#### 352. What is hard binding and when do you use it?

[↑ Back to Table of Contents](#table-of-contents)


`fn.bind(thisArg, ...args)` returns a new function permanently bound to `thisArg`. The binding cannot be overridden even with `call`, `apply`, or `new`. Used when passing methods as callbacks and when partially applying arguments.

---

#### 353. What is explicit binding with `call`, `apply`, and `bind`?

[↑ Back to Table of Contents](#table-of-contents)


All three methods allow you to explicitly set `this`. `call(thisArg, arg1, arg2)` calls immediately with individual args. `apply(thisArg, [args])` calls immediately with args as array. `bind(thisArg, ...args)` returns a new function with `this` permanently bound — doesn't call immediately.

---

#### 354. What does `bind` return?

[↑ Back to Table of Contents](#table-of-contents)


`bind` returns a new function with `this` permanently bound to the specified value. The original function is unchanged. The bound function can also have arguments pre-filled (partial application). Calling `bind` multiple times only applies the first binding.

---

#### 355. What is `this` in a class?

[↑ Back to Table of Contents](#table-of-contents)


Inside a class method, `this` refers to the instance of the class. In the constructor, `this` is the newly created object. Static methods have `this` bound to the class itself, not an instance. Arrow function class fields capture `this` at creation time (safe for callbacks).

---

#### 356. What is the difference between `map` and `forEach`?

[↑ Back to Table of Contents](#table-of-contents)


`map` returns a new array of transformed values — it's a pure transformation. `forEach` returns `undefined` and is used purely for side effects (logging, mutations). Prefer `map` when you need the results; `forEach` only for side effects.

---

#### 357. What is the difference between `forEach` and `map`?

[↑ Back to Table of Contents](#table-of-contents)


`forEach` executes a side effect for each element, returns `undefined`. `map` transforms each element and returns a new array. Don't use `map` when you don't need the returned array (use `forEach` for side effects). Can't break out of either — use `for...of` or `some`/`every` for early exit.

---

#### 358. What does `super` do in a class?

[↑ Back to Table of Contents](#table-of-contents)


In a constructor, `super()` calls the parent class constructor — required in subclass constructors before accessing `this`. In a method, `super.method()` calls the parent class's version of that method.

---

#### 359. What are the trade-offs between using `class` and factory functions in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Classes: familiar syntax, `instanceof` works, better performance for many instances (shared prototype methods), native `private` fields (ES2022). Factory functions: no `new` required, naturally encapsulated private data via closure, easy mixins, more flexible, no prototype chain confusion. Factory functions are preferred in functional codebases; classes in OOP-heavy codebases.

---

#### 360. Cannot Be Constructors

[↑ Back to Table of Contents](#table-of-contents)


* **Regular functions** can be used with the `new` keyword to create new objects (like a blueprint).
* **Arrow functions** will throw an error if you try to use `new` with them. They cannot be used as constructors.

---

#### 361. How do you run async operations in parallel vs sequentially?

[↑ Back to Table of Contents](#table-of-contents)


Sequential: `await a(); await b()` — total time = a + b. Parallel: `const [r1, r2] = await Promise.all([a(), b()])` — total time = max(a, b). A common mistake is `await` inside `for...of` when operations are independent — use `Promise.all` instead.

---

#### 362. What is the difference between sequential and parallel async execution?

[↑ Back to Table of Contents](#table-of-contents)


Sequential: `await a(); await b();` — B starts only after A finishes. Total time = A + B. Parallel: `await Promise.all([a(), b()])` — both start simultaneously. Total time = max(A, B). Use parallel when operations are independent; sequential when one depends on the other.

---

#### 363. What is `createAsyncThunk()` and why is it used?

[↑ Back to Table of Contents](#table-of-contents)


`createAsyncThunk` is a function that creates a thunk action that handles asynchronous requests. It takes an action type prefix and a payload creator (async function). It automatically dispatches `pending`, `fulfilled`, and `rejected` actions based on the promise. This reduces boilerplate for loading states and error handling.

---

#### 364. How does async flow work in Redux Toolkit?

[↑ Back to Table of Contents](#table-of-contents)


1. Define a thunk using `createAsyncThunk`.
2. Inside the payload creator, perform async work (e.g., fetch).
3. Dispatch the thunk from a component.
4. The thunk dispatches the `pending` action immediately.
5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.
6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data).

---

#### 365. What is event delegation?

[↑ Back to Table of Contents](#table-of-contents)


Attaching a single event listener to a parent element instead of individual listeners on each child. Uses event bubbling — events from children bubble up to the parent. Check `event.target` to determine which child was clicked. More efficient for dynamic lists; fewer memory-consuming listeners.

---

#### 366. How do you detect and prevent infinite loops in user-submitted code?

[↑ Back to Table of Contents](#table-of-contents)


Run in a sandboxed Web Worker. Inject a counter that increments on each iteration and throws after a limit. Use a timer in the host to terminate the Worker after a timeout. Never run untrusted code in the main thread or with `eval` in the host environment.

---

#### 367. How do you safely handle `JSON.parse` with unknown input?

[↑ Back to Table of Contents](#table-of-contents)


Always wrap in `try/catch`. Validate the parsed structure — don't assume it matches your expected schema. Use a validation library (Zod, Yup) to parse and validate in one step: `const result = MySchema.safeParse(JSON.parse(input))`. Never trust server or external data structure without validation.

---

#### 368. What is tail call optimization?

[↑ Back to Table of Contents](#table-of-contents)


A JS engine optimization where if a function's last action is calling another function (`return fn()`), the current stack frame can be replaced instead of adding a new one — enabling O(1) stack space for tail-recursive functions. Specified in ES6 strict mode, but only Safari actually implements it. In practice, use loops or trampolining for deep recursion.

---

#### 369. What is the difference between `==` and `===`?

[↑ Back to Table of Contents](#table-of-contents)


`===` (strict equality): compares value AND type — no coercion. `==` (loose equality): performs type coercion before comparing. `1 == '1'` is `true`; `1 === '1'` is `false`. Always prefer `===` to avoid unexpected coercion bugs.

---

#### 370. What are truthy and falsy values?

[↑ Back to Table of Contents](#table-of-contents)


Falsy: `false`, `0`, `-0`, `0n`, `''` (empty string), `null`, `undefined`, `NaN`. Everything else is truthy, including `'0'`, `[]`, `{}`, and `'false'`. Used in boolean contexts like `if` conditions and `&&`/`||` operators.

---

#### 371. What is the difference between a statement and an expression?

[↑ Back to Table of Contents](#table-of-contents)


An expression produces a value (`2 + 2`, `fn()`, `x ? a : b`). A statement performs an action (`if`, `for`, `return`, `throw`). Some constructs can be either — function declarations are statements; function expressions are expressions.

---

#### 372. What is lexical scoping?

[↑ Back to Table of Contents](#table-of-contents)


Lexical scoping means a function's scope is determined by where it is defined in the source code, not where it is called. Inner functions have access to the variables of their outer functions at the time of definition.

---

#### 373. How does `reduce` work?

[↑ Back to Table of Contents](#table-of-contents)


`array.reduce((accumulator, currentValue, index, array) => newAccumulator, initialValue)`. Iterates the array, passing the accumulated result to each callback. Can replace `map`, `filter`, and many other operations. Always provide an initial value to avoid bugs on empty arrays.

---

#### 374. What is the difference between `slice` and `splice`?

[↑ Back to Table of Contents](#table-of-contents)


`slice(start, end)`: non-mutating, returns a shallow copy of a portion. `splice(start, deleteCount, ...items)`: mutates the original array, removes and/or inserts elements in-place, returns removed elements.

---

#### 375. What does `new` do step by step?

[↑ Back to Table of Contents](#table-of-contents)


1. Creates a new empty object. 2. Sets its `[[Prototype]]` to `Constructor.prototype`. 3. Calls the constructor with `this` set to the new object. 4. If the constructor explicitly returns an object, that object is returned; otherwise, the new object created in step 1 is returned.

---

#### 376. What is `console.table`, `console.group`, and `console.time`?

[↑ Back to Table of Contents](#table-of-contents)


`console.table(arr)`: renders arrays/objects as a formatted table. `console.group(label)` / `console.groupEnd()`: collapses related logs. `console.time(label)` / `console.timeEnd(label)`: measures time between calls. `console.trace()`: prints current call stack.

---

#### 377. What is the difference between `innerHTML`, `textContent`, and `innerText`?

[↑ Back to Table of Contents](#table-of-contents)


`innerHTML`: gets/sets HTML content (parses HTML — XSS risk with user input). `textContent`: gets/sets text content of an element and all descendants (no HTML parsing — safe, fast, includes hidden elements). `innerText`: like `textContent` but respects CSS (doesn't include hidden elements, triggers layout). Use `textContent` for safety and performance.

---

#### 378. What is `IntersectionObserver`?

[↑ Back to Table of Contents](#table-of-contents)


Observes when an element enters or leaves the viewport (or a container). Callbacks fire when the intersection ratio crosses thresholds. Used for: lazy loading images, infinite scroll, triggering animations on scroll, analytics (view tracking).

---

#### 379. What is the difference between debounce and throttle?

[↑ Back to Table of Contents](#table-of-contents)


Debounce: waits for a pause in calls — only fires once after the activity stops. Good for: search input, form validation on type. Throttle: fires at regular intervals during continuous activity — guarantees execution frequency. Good for: scroll position tracking, drag events, game loops.

---

#### 380. What is lazy loading?

[↑ Back to Table of Contents](#table-of-contents)


Deferring loading of resources (images, modules, components) until they're actually needed. Reduces initial page load. For images: `<img loading="lazy">` or Intersection Observer. For code: dynamic `import()` — `const mod = await import('./module.js')`. Both reduce time-to-interactive.

---

#### 381. What is a functor?

[↑ Back to Table of Contents](#table-of-contents)


An object with a `map` method that applies a function to the value inside it and returns the same type. Arrays are functors. Promises are almost functors (`.then`). Functors allow you to transform values inside containers without extracting them — a key FP concept.

---

#### 382. What is a monad (in practical JS terms)?

[↑ Back to Table of Contents](#table-of-contents)


A pattern for sequencing operations with context — essentially anything with a `flatMap`/`chain` method that flattens one level. Promises behave monadically (`.then` flattens nested promises). Used in libraries like fp-ts. Understanding monads enables cleaner async and nullable handling.

---

#### 383. What is point-free style?

[↑ Back to Table of Contents](#table-of-contents)


Writing functions without explicitly mentioning their arguments. `const double = map(x => x * 2)` vs `const double = arr => arr.map(x => x * 2)`. The first is point-free. Achievable through currying and composition. Can improve readability but can also obscure intent if overused.

---

#### 384. What is `eval()` and why is it dangerous?

[↑ Back to Table of Contents](#table-of-contents)


Executes a string as JavaScript code. Security risk: if the string contains user input, it enables code injection. Performance risk: prevents V8 optimization of the surrounding scope. Almost never necessary — use `JSON.parse`, `Function` constructor only if unavoidable, never with untrusted input.

---

#### 385. What is an IIFE and why is it used?

[↑ Back to Table of Contents](#table-of-contents)


Immediately Invoked Function Expression: `(function() { ... })()`. The function is defined and immediately called. Used to create a private scope (avoiding polluting global scope), especially before ES modules. Still used for initialization code or when you need a block-like scope in older environments.

What?
An IIFE (pronounced "Iffy") stands for Immediately Invoked Function Expression. It is simply a JavaScript function that runs the exact moment it is defined.

JavaScript
(function() {
  console.log("I run instantly!");
})();
Why?
To create a private bubble for your code.

Before modern JavaScript, any variable you created could accidentally overwrite someone else's variable (polluting the global scope). Because functions have their own scope, wrapping your code in an IIFE keeps all your variables safely locked inside, invisible to the rest of the program.

When?
In the past: It was used constantly as the primary way to build safe, isolated code modules.

Today: It is less common now because we have modern tools (let, const, and JavaScript Modules) that handle privacy automatically.

Current uses: You will still see it used for initialization code that only needs to run once when a page loads, or to instantly run an async function at the top level of a file.

---

#### 386. What is the difference between `call` and `apply`?

[↑ Back to Table of Contents](#table-of-contents)


Both call a function immediately with a given `this`. The only difference is how additional arguments are passed: `call` takes individual arguments (`fn.call(ctx, a, b, c)`), while `apply` takes an array (`fn.apply(ctx, [a, b, c])`). Use `apply` when you already have args in an array.

---

#### 387. What is `hasOwnProperty`?

[↑ Back to Table of Contents](#table-of-contents)


`obj.hasOwnProperty('key')` returns `true` only if `key` is a direct property of `obj`, not inherited through the prototype chain. Use it when iterating with `for...in` to distinguish own properties from inherited ones. Alternative: `Object.hasOwn(obj, 'key')` (ES2022).

---

#### 388. What is the difference between `map`, `filter`, and `reduce`?

[↑ Back to Table of Contents](#table-of-contents)


`map(fn)`: transforms each element, returns new array of same length. `filter(fn)`: returns new array with only elements where `fn` returns truthy. `reduce(fn, initial)`: accumulates all elements into a single value (sum, object, nested array, etc.). All are non-mutating.

---

#### 389. What is the difference between `find` and `filter`?

[↑ Back to Table of Contents](#table-of-contents)


`find(fn)`: returns the first element where `fn` is truthy, or `undefined` if none. Short-circuits. `filter(fn)`: returns a new array of all elements where `fn` is truthy — never short-circuits. Use `find` when you need one result; use `filter` when you need all matches.

---

#### 390. Multi-line Text Made Easy

[↑ Back to Table of Contents](#table-of-contents)


With regular strings, you can't just hit the "Enter" key to start a new line without your code breaking (you used to have to inject messy `\n` characters everywhere). With template literals, what you see is what you get.

```javascript
// This just works naturally:
const emailTemplate = `
  Hi Customer,
  
  Thank you for your order!
  
  Best,
  The Team
`;

```

---

#### 391. What are ES2020+ features you should know?

[↑ Back to Table of Contents](#table-of-contents)


Optional chaining `?.`, nullish coalescing `??`, `Promise.allSettled()`, `BigInt`, `globalThis`, dynamic import `import()`, `String.matchAll()`, logical assignment `&&=`/`||=`/`??=` (ES2021), `Array.at()` (ES2022), `Object.hasOwn()` (ES2022), `structuredClone()` (ES2022), top-level `await` (ES2022).

---

#### 392. What is CORS?

[↑ Back to Table of Contents](#table-of-contents)


Cross-Origin Resource Sharing — a browser security mechanism that restricts cross-origin HTTP requests. Servers must send `Access-Control-Allow-Origin` headers to allow cross-origin access. Simple requests (GET, POST with certain content-types) go through; complex requests trigger a preflight `OPTIONS` request. CORS is a browser restriction — it doesn't apply to server-to-server requests.

---

#### 393. What is debouncing?

[↑ Back to Table of Contents](#table-of-contents)


Delays executing a function until a specified time has passed since the last call. Used for search-as-you-type (wait until typing stops), window resize handlers, autosave. The timer resets on each call — only the final call after the pause executes.

```javascript
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}
```

---

#### 394. What is throttling?

[↑ Back to Table of Contents](#table-of-contents)


Ensures a function executes at most once per specified interval, regardless of how many times it's called. Used for scroll handlers, mousemove, resize (when you want regular updates, not just after stopping).

```javascript
function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  };
}
```

---

#### 395. What is the Singleton pattern?

[↑ Back to Table of Contents](#table-of-contents)


Ensures only one instance of an object exists. In JS, module-level variables are naturally singletons (module is cached after first import). Classic implementation uses a closure that stores the instance and returns it on all subsequent calls.

---

#### 396. What is the Observer / Pub-Sub pattern?

[↑ Back to Table of Contents](#table-of-contents)


Objects (subscribers) register interest in events. When an event occurs, the publisher notifies all subscribers. EventEmitter in Node.js, `addEventListener` in the browser, Redux's store, and RxJS all implement this pattern. Decouples the event source from event consumers.

---

#### 397. What is the Factory pattern?

[↑ Back to Table of Contents](#table-of-contents)


A function that creates and returns objects without using `new` and classes directly. Allows encapsulating creation logic and returning different object types based on input. More flexible than constructors — can return cached instances, different implementations, or augmented objects.

---

#### 398. What is the Decorator pattern?

[↑ Back to Table of Contents](#table-of-contents)


Wraps an object or function to extend its behavior without modifying the original. In JS: higher-order functions (`withLogging(fn)`), ES decorators (TC39 proposal, used in TypeScript/Angular), or manually wrapping objects. Used for logging, caching, authentication, validation.

---

#### 399. What is the Strategy pattern?

[↑ Back to Table of Contents](#table-of-contents)


Defines a family of algorithms, encapsulates each, and makes them interchangeable. In JS, pass different functions to the same interface: `sort(arr, ascendingStrategy)` vs `sort(arr, descendingStrategy)`. Eliminates complex if/else chains, follows Open/Closed Principle.

---

#### 400. What is the Proxy pattern?

[↑ Back to Table of Contents](#table-of-contents)


Wraps an object to intercept and control access to its properties. ES6 `Proxy` enables this natively. Use for: validation, logging, access control, caching, reactive systems (Vue 3 uses Proxy for reactivity), API mocking.

---

#### 401. What is the Command pattern?

[↑ Back to Table of Contents](#table-of-contents)


Encapsulates a request as an object, enabling undo/redo, queuing, logging, and parameterization of operations. In JS: `{ execute: fn, undo: fn }`. Used in text editors, Redux (actions are commands), and task queues.

---

#### 402. What are side effects?

[↑ Back to Table of Contents](#table-of-contents)


Any interaction with the outside world from within a function: modifying external variables, DOM manipulation, network requests, logging, reading from `Date.now()`. Functions with side effects are harder to test and predict. FP separates pure computation from side effects — push side effects to the edges of your program.

---

#### 403. Why is `eval()` dangerous?

[↑ Back to Table of Contents](#table-of-contents)


Executes arbitrary code strings — a major XSS vector if user input reaches it. Bypasses security, slows performance (JIT can't optimize code inside eval), and makes debugging harder. Never use `eval()` with untrusted input. Also avoid `Function()`, `setTimeout('code string')`, `setInterval('code string')`.

---

### Advanced

#### 404. What are async generators and when would you use them?

[↑ Back to Table of Contents](#table-of-contents)


Declared with `async function*`, they combine async and generator behavior. Each `yield` can produce a value asynchronously. Consumed with `for await...of`. Useful for paginated APIs, streaming data, or any async sequence.

---

#### 405. What is the `Atomics` API and when do you need it?

[↑ Back to Table of Contents](#table-of-contents)


`Atomics` provides atomic operations on `SharedArrayBuffer` for safe inter-thread communication in Worker threads. Without atomics, concurrent writes cause data races. `Atomics.wait`, `Atomics.notify` implement mutex-like synchronization. Rarely needed — only for low-level concurrent algorithms in Workers.

---

#### 406. What is `WeakRef` and `FinalizationRegistry`?

[↑ Back to Table of Contents](#table-of-contents)


`WeakRef` holds a weak reference to an object — if the object is GC'd, `ref.deref()` returns `undefined`. `FinalizationRegistry` registers a callback to run after an object is collected. Used for: caches that shouldn't prevent GC, tracking live instances for debugging. The GC timing is non-deterministic — don't rely on these for critical logic.

---

#### 407. What are transducers?

[↑ Back to Table of Contents](#table-of-contents)


Composable algorithmic transformations that are independent of the input source. Combine multiple `map`/`filter` operations into one pass over a collection, eliminating intermediate arrays. Used in performance-sensitive functional pipelines.

---

### Senior / Scenario

#### 408. How would you architect a state management system in vanilla JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


A central `Store` class holding state object. `dispatch(action)` runs the reducer to produce new state (immutably). `subscribe(listener)` adds observers; `unsubscribe` removes them. `getState()` returns current state. Middleware support: wrap `dispatch` with a chain of middleware functions. Notify subscribers after each dispatch.

---

#### 409. How would you compile a simple expression language to JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Lexer: tokenize the input string into tokens (numbers, operators, identifiers, parentheses). Parser: build an Abstract Syntax Tree (AST) using recursive descent. Code generator: walk the AST and emit JavaScript (or evaluate directly from the AST). Libraries: Acorn (JS parser), Chevrotain (parser toolkit).

---

#### 410. How would you implement a JavaScript interpreter in JavaScript?

[↑ Back to Table of Contents](#table-of-contents)


Tokenize input into a stream of tokens (lexer). Parse tokens into an AST (parser — use recursive descent for simplicity). Evaluate the AST recursively (interpreter): for literals, return the value; for binary expressions, evaluate both sides; for identifiers, look up in an environment object; for function calls, evaluate the function and arguments then apply. This is the basis of js-interpreter and Babel plugins.

---

#### 411. How would you build an offline-first JavaScript web app?

[↑ Back to Table of Contents](#table-of-contents)


Service Worker for caching assets and API responses (Cache API). Background sync for deferring requests when offline. IndexedDB for structured client-side storage. Optimistic UI updates that sync when connection restores. Conflict resolution strategy (last-write-wins or CRDT). Workbox simplifies service worker caching strategies.

---

#### 412. Design a JavaScript plugin system.

[↑ Back to Table of Contents](#table-of-contents)


A `PluginManager` class with `register(plugin)` and `run(hook, context)`. Plugins are objects with hook names as keys: `{beforeSave: async (ctx) => {...}}`. Manager maintains a `Map<hookName, Plugin[]>`. On `run`, iterate plugins for that hook in registration order. Support async hooks with sequential `await` or parallel `Promise.all`. Provide `context` object for plugins to share state.

---

#### 413. Situation: Classic loop closure bug – `var` in a for loop.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);
}
// Logs: 3, 3, 3 — not 0, 1, 2
```
Because `var` is function-scoped, all callbacks share the same `i`. When they run, the loop has finished and `i` is `3`. Fix: use `let` (block-scoped, creates a new binding per iteration), use `setTimeout` with a closure factory, or use `forEach`.

---

#### 414. Situation: `this` is `undefined` in a class method — what are the possible causes?

[↑ Back to Table of Contents](#table-of-contents)


The method was destructured from the instance (`const {method} = instance`). It was passed as a callback without binding. It's a static method being called on an instance. It's an async method and `this` was lost in a callback inside it. Fixes: bind in the constructor, use class field arrow functions, or use `fn.bind(instance)` at the call site.

---

#### 415. How would you build a JavaScript SDK for a REST API?

[↑ Back to Table of Contents](#table-of-contents)


A class or factory accepting `baseURL` and auth credentials. Each resource (users, posts) gets methods (`getAll`, `getById`, `create`, `update`, `delete`). Central `request` method handles: setting auth headers, base URL, error parsing, retry logic, and type coercion. Generate TypeScript types from OpenAPI spec. Version the SDK with semantic versioning.

---

#### 416. Situation: An async function is silently failing — how do you debug it?

[↑ Back to Table of Contents](#table-of-contents)


Check for missing `await` (the Promise is returned but not awaited). Check for caught errors that are swallowed silently in `.catch(() => {})`. Add `process.on('unhandledRejection')`. Use `Promise.all` carefully — a rejection can be missed if the result isn't awaited. Enable the `no-floating-promises` ESLint rule.

---

#### 417. You have a feature using closures, but it's causing unexpected behavior in production — how would you debug and fix it?

[↑ Back to Table of Contents](#table-of-contents)


**Answer:**  
Closure issues often stem from variable capture inside loops, asynchronous callbacks, or stale state.

- **Reproduce locally:** Write a test that mimics production behavior. Use `console.log` or a debugger to inspect captured variables.
- **Check loop closures:** If the feature uses `var` inside a loop, the closure shares the same variable reference. Replace with `let` (block‑scoped) or use an IIFE to capture the current value.
- **Asynchronous closures:** When a callback accesses a variable that changes after the closure is created, the value may be outdated. Example:  
  ```javascript
  for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100); // works with let
  }
  ```
  With `var`, all would log `3`. The fix is to use `let` or wrap in a function.
- **State in React hooks (if applicable):** Stale closures often appear with `useEffect` or `useCallback` when dependencies are missing. Use exhaustive‑deps rules and verify captured values.
- **Production debugging:** Add structured logging that includes the closure‑bound values at key points. Use remote debugging via `--inspect` if possible, or log snapshots.
- **Fix:** Once identified, refactor to avoid mutating captured variables or use explicit dependencies (e.g., `useCallback` with proper deps). Consider replacing closures with explicit parameters where appropriate.

---

##### Advanced & Senior-Level Scenarios

---

#### 418. How would you implement an event emitter from scratch?

[↑ Back to Table of Contents](#table-of-contents)


Store handlers in a `Map<string, Set<Function>>`. `on(event, handler)`: add handler to the Set. `off(event, handler)`: remove it. `emit(event, ...args)`: iterate the Set and call each handler. `once(event, handler)`: wrap handler to call `off` after first invocation.

---

#### 419. How would you design a client-side caching layer?

[↑ Back to Table of Contents](#table-of-contents)


LRU (Least Recently Used) cache: doubly linked list + Map for O(1) get/set. `get(key)`: move node to front. `set(key, val)`: add to front, evict tail if over capacity. Add TTL: store expiry timestamp, check on `get`. Add stale-while-revalidate: return stale value while background-fetching fresh data.

---

#### 420. How would you implement debounce and throttle from scratch?

[↑ Back to Table of Contents](#table-of-contents)


Debounce: `function debounce(fn, delay) { let timer; return (...args) => { clearTimeout(timer); timer = setTimeout(() => fn(...args), delay); }; }`. Throttle (leading): track `lastCall`. If `Date.now() - lastCall >= delay`, call `fn` and update `lastCall`. Trailing throttle: use `setTimeout` and cancel if called again within the window.

---

#### 421. How would you implement a publish/subscribe system with topics and wildcards?

[↑ Back to Table of Contents](#table-of-contents)


Map topic strings to subscriber Sets. For wildcards (`*`), on publish check each subscriber's pattern against the topic using a regex or glob match. Namespace topics with `.` separator for hierarchical subscriptions (`user.*` matches `user.created`, `user.deleted`).

---

#### 422. Situation: `JSON.stringify` is dropping data — explain why and how to fix it.

[↑ Back to Table of Contents](#table-of-contents)


`JSON.stringify` silently omits: `undefined` values in objects (and `undefined` itself), functions, `Symbol` keys and values, and `Infinity`/`NaN` (become `null`). Circular references throw. Fix: use a replacer function as the second argument to handle special values, or use a library like `flatted` for circular refs.

---

#### 423. How would you build an undo/redo system?

[↑ Back to Table of Contents](#table-of-contents)


Maintain two stacks: undo stack and redo stack. On action: push current state to undo, clear redo. On undo: pop from undo → apply → push to redo. On redo: pop from redo → apply → push to undo. For commands (not full state snapshots), store `do`/`undo` function pairs to avoid cloning large state objects.

---

#### 424. How would you implement a simple reactive system (like Vue's reactivity)?

[↑ Back to Table of Contents](#table-of-contents)


Track the currently executing effect in a global variable. `reactive(obj)`: wrap with `Proxy`. On `get`, if an effect is running, add it to that property's subscriber Set (track). On `set`, call all subscribers (trigger). Effects run their function, which accesses reactive properties, automatically subscribing. This is Vue 3's reactivity core.

---

#### 425. How would you architect a real-time collaborative editing feature?

[↑ Back to Table of Contents](#table-of-contents)


Operational Transformation (OT) or CRDT (Conflict-free Replicated Data Type) algorithms to handle concurrent edits. WebSocket for real-time transport. Server applies and broadcasts operations. Yjs and Automerge are production-ready CRDT libraries. Awareness protocol for cursor/presence sharing.

---

#### 426. Situation: Your third-party script is blocking the main thread — how do you fix it?

[↑ Back to Table of Contents](#table-of-contents)


Load with `defer` (executes after HTML parse, in order) or `async` (executes immediately when downloaded). Move to a Web Worker for CPU work. Use dynamic `import()` to load only when needed. Evaluate if the script is necessary at all — audit with Lighthouse third-party audit. Use `scheduler.postTask` (Chrome) to yield control.

---

#### 427. How would you implement a simple dependency injection container?

[↑ Back to Table of Contents](#table-of-contents)


A container maps tokens (strings, Symbols, or classes) to factories. `register(token, factory)`: store the factory. `resolve(token)`: call the factory, injecting dependencies by calling `resolve` for each declared dependency. Handle circular dependencies by detecting cycles. Supports singletons by caching resolved instances.

---

#### 428. How would you implement a persistent undo history that survives page reload?

[↑ Back to Table of Contents](#table-of-contents)


Store the action history (not full state snapshots) in `localStorage` or `IndexedDB`. On load, replay the action log to reconstruct state. For large histories, use snapshots at intervals: store the base snapshot plus a delta log since the last snapshot. Limit history length to control storage size.

---

#### 429. How would you implement a simple template engine?

[↑ Back to Table of Contents](#table-of-contents)


Replace `{{variable}}` placeholders with values from a context object: `str.replace(/\{\{(\w+)\}\}/g, (_, key) => context[key] ?? '')`. For loops and conditionals, parse into an AST and evaluate. For production use: Handlebars, Mustache, or Nunjucks. For type safety: tagged template literals with TypeScript.

---

#### 430. How would you implement an event emitter?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
class EventEmitter {
  constructor() { this.events = {}; }
  on(event, listener) {
    (this.events[event] ??= []).push(listener);
    return this;
  }
  off(event, listener) {
    this.events[event] = (this.events[event] || []).filter(l => l !== listener);
    return this;
  }
  emit(event, ...args) {
    (this.events[event] || []).forEach(l => l(...args));
    return this;
  }
  once(event, listener) {
    const wrapper = (...args) => { listener(...args); this.off(event, wrapper); };
    return this.on(event, wrapper);
  }
}
```

---

#### 431. How would you implement infinite scrolling with vanilla JS?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const sentinel = document.querySelector('#sentinel');
const observer = new IntersectionObserver(entries => {
  if (entries[0].isIntersecting && !isLoading) {
    isLoading = true;
    fetchNextPage().then(items => {
      renderItems(items);
      isLoading = false;
      if (hasMore) observer.observe(sentinel); // re-observe after render
    });
  }
}, { rootMargin: '200px' }); // load 200px before sentinel is visible
observer.observe(sentinel);
```



*300 questions across 20 sections. Master these and crack 95% of JavaScript interviews! 🟨*

---

#### 432. Situation & Scenario

[↑ Back to Table of Contents](#table-of-contents)


**Problem:** Implement `Promise.all`, `Promise.race`, `Promise.any`, `Promise.allSettled` from scratch.

```javascript
// Promise.all — resolves when ALL resolve, rejects on first rejection
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    const results = new Array(promises.length);
    let remaining = promises.length;
    if (remaining === 0) return resolve([]);
    promises.forEach((p, i) => {
      Promise.resolve(p)
        .then(val => { results[i] = val; if (--remaining === 0) resolve(results); })
        .catch(reject);
    });
  });
}

// Promise.race — settles when FIRST settles (either way)
function promiseRace(promises) {
  return new Promise((resolve, reject) => {
    promises.forEach(p => Promise.resolve(p).then(resolve).catch(reject));
  });
}

// Promise.any — resolves when FIRST resolves, rejects only if ALL reject
function promiseAny(promises) {
  return new Promise((resolve, reject) => {
    const errors = [];
    let remaining = promises.length;
    if (remaining === 0) return reject(new AggregateError([], 'All promises rejected'));
    promises.forEach((p, i) => {
      Promise.resolve(p).then(resolve).catch(err => {
        errors[i] = err;
        if (--remaining === 0) reject(new AggregateError(errors, 'All promises rejected'));
      });
    });
  });
}

// Promise.allSettled — waits for ALL, never rejects
function promiseAllSettled(promises) {
  return promiseAll(promises.map(p =>
    Promise.resolve(p)
      .then(value => ({ status: 'fulfilled', value }))
      .catch(reason => ({ status: 'rejected', reason }))
  ));
}
```

---

##### Polyfills & Implementations

---

#### 433. Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.

[↑ Back to Table of Contents](#table-of-contents)


All three are used to control the `this` value in functions.

- **`call(thisArg, arg1, arg2, ...)`**: Invokes the function immediately with a given `this` and arguments passed individually.
- **`apply(thisArg, [argsArray])`**: Same as `call`, but arguments are passed as an array.
- **`bind(thisArg, ...args)`**: Returns a new function with the `this` bound permanently; can be called later.

**Use cases:**
- Borrowing methods: e.g., `Array.prototype.slice.call(arguments)`
- Function currying: `const multiply = (a,b) => a*b; const double = multiply.bind(null, 2);`
- Event handlers: ensure `this` refers to the class instance.

**Polyfills:**

```javascript
// call polyfill
Function.prototype.myCall = function(context, ...args) {
  context = context || globalThis;
  const uniqueId = Symbol(); // avoid property collision
  context[uniqueId] = this;
  const result = context[uniqueId](...args);
  delete context[uniqueId];
  return result;
};

// apply polyfill
Function.prototype.myApply = function(context, argsArray) {
  context = context || globalThis;
  const uniqueId = Symbol();
  context[uniqueId] = this;
  const result = context[uniqueId](...argsArray);
  delete context[uniqueId];
  return result;
};

// bind polyfill (simplified)
Function.prototype.myBind = function(context, ...boundArgs) {
  const fn = this;
  return function(...args) {
    return fn.apply(context, boundArgs.concat(args));
  };
};
```

---

#### 434. Implement `map`, `reduce`, `filter` from scratch.

[↑ Back to Table of Contents](#table-of-contents)


**`map`**:
```javascript
Array.prototype.myMap = function(callback, thisArg) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (i in this) { // skip empty slots (sparse arrays)
      result.push(callback.call(thisArg, this[i], i, this));
    }
  }
  return result;
};
```

**`filter`**:
```javascript
Array.prototype.myFilter = function(callback, thisArg) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (i in this && callback.call(thisArg, this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};
```

**`reduce`**:
```javascript
Array.prototype.myReduce = function(callback, initialValue) {
  let accumulator = initialValue;
  let startIndex = 0;
  if (arguments.length < 2) {
    if (this.length === 0) throw new TypeError('Reduce of empty array with no initial value');
    accumulator = this[0];
    startIndex = 1;
  }
  for (let i = startIndex; i < this.length; i++) {
    if (i in this) {
      accumulator = callback(accumulator, this[i], i, this);
    }
  }
  return accumulator;
};
```

---

#### 435. Implement a custom hook like `useDebounce` or `useFetch` (React).

[↑ Back to Table of Contents](#table-of-contents)


**`useDebounce`**:
```javascript
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
```javascript
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

---

##### Advanced JavaScript

---

#### 436. What is circular dependency and how do you handle it?

[↑ Back to Table of Contents](#table-of-contents)


Module A imports B, and B imports A. Both module systems handle it but the imported value may be `undefined` at evaluation time. Fix: restructure to extract shared code to a third module C, or use lazy imports (dynamic `import()`).

---

## Output & Tricky Questions

### Intermediate

#### 437. What is the output of `0.1 + 0.2 === 0.3` and why?

[↑ Back to Table of Contents](#table-of-contents)


`false`. JavaScript uses IEEE 754 double-precision floating point. `0.1 + 0.2` is `0.30000000000000004`. Binary can't represent 0.1 or 0.2 exactly. Fix: `Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON`, or use `toFixed()` for display, or use integer arithmetic (work in cents not dollars).

---

#### 438. What is the output: `typeof null`?

[↑ Back to Table of Contents](#table-of-contents)


`'object'`. This is a well-known bug in JavaScript that has persisted since its first implementation and cannot be fixed without breaking existing code. The original implementation used low-order bits to tag types, and null's representation had the same bits as object tags.

---

#### 439. What is the output: `[] == ![]`?

[↑ Back to Table of Contents](#table-of-contents)


`true`. Steps: `![]` is `false` (arrays are truthy). `[] == false` → `[] == 0` (false to number). `[] == 0` → `'' == 0` (array to primitive → empty string). `'' == 0` → `0 == 0` → `true`. This is a classic demonstration of why `==` should be avoided.

---

#### 440. What is the output?

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const a = { toString() { return 'A'; } };
const b = { toString() { return 'B'; } };
const obj = {};
obj[a] = 1;
obj[b] = 2;
console.log(obj[a]);
console.log(Object.keys(obj));
```

**Output:**
```
2
['[object Object]']
```

**Explanation:** Objects as property keys get converted via `toString()`. If you don't define `toString`, objects convert to `'[object Object]'`. But our objects DO define `toString` — however, `obj[a]` uses the object-to-string conversion which calls `toString()`, giving `'A'` and `'B'` as keys!

**Wait — re-evaluating:** JS calls `[Symbol.toPrimitive]` or `valueOf()` first, then `toString()`. For property access `obj[a]`, it converts `a` using the abstract `ToPropertyKey` which calls `ToString(ToPrimitive(a, hint String))`. Since these objects define `toString()`, they give `'A'` and `'B'`.

**Corrected Output:**
```
2
['A', 'B']
```

`obj['A'] = 1`, then `obj['B'] = 2`. `obj[a]` → `obj['A']` = `1`. Wait no — `obj[b] = 2` sets `obj['B'] = 2`, but then `obj[a]` = `obj['A']` = `1`. So:

**Final Output:**
```
1
['A', 'B']
```

**Lesson:** Objects as keys use their `toString()` method — define it to control keys, or use `Map` for true object keys.

---

#### 441. What is the output? (Node.js)

[↑ Back to Table of Contents](#table-of-contents)


```javascript
setImmediate(() => console.log('setImmediate'));
process.nextTick(() => console.log('nextTick'));
Promise.resolve().then(() => console.log('Promise'));
setTimeout(() => console.log('setTimeout'), 0);
console.log('sync');
```

**Output (Node.js):**
```
sync
nextTick
Promise
setTimeout / setImmediate (order may vary)
```

**Explanation:** Order in Node.js: synchronous → `process.nextTick` (before microtasks) → Promise microtasks → macrotasks (setTimeout, setImmediate). `nextTick` has higher priority than Promises. `setTimeout(0)` vs `setImmediate` order is non-deterministic in some contexts.

---

#### 442. What is the output or behavior?

[↑ Back to Table of Contents](#table-of-contents)


```jsx
function App() {
  const [count, setCount] = React.useState(0);
  const renderCount = React.useRef(0);
  renderCount.current++;

  return (
    <div>
      <p>State count: {count}</p>
      <p>Render count: {renderCount.current}</p>
      <button onClick={() => setCount(c => c + 1)}>Increment state</button>
      <button onClick={() => { renderCount.current++; console.log(renderCount.current); }}>
        Increment ref
      </button>
    </div>
  );
}
```

**Behavior:**
- Clicking "Increment state" re-renders, both counts update visually.
- Clicking "Increment ref" DOES NOT re-render. `renderCount.current` changes in memory but UI doesn't update. The console shows updated value but the page doesn't re-render.

**Explanation:** Changing `ref.current` never triggers a re-render. `renderCount.current++` in the render body runs on every render (counting correctly), but it's only visible because a STATE change causes a re-render.

---

#### 443. Implement: Given a string, find the first non-repeating character.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function firstNonRepeating(str) {
  const freq = {};
  for (const ch of str) {
    freq[ch] = (freq[ch] || 0) + 1;
  }
  for (const ch of str) {
    if (freq[ch] === 1) return ch;
  }
  return null;
}

console.log(firstNonRepeating('aabbcde')); // 'c'
console.log(firstNonRepeating('aabb'));    // null
console.log(firstNonRepeating('abcabc')); // null

// Alternative using Map (preserves insertion order):
function firstNonRepeatingMap(str) {
  const map = new Map();
  for (const ch of str) map.set(ch, (map.get(ch) || 0) + 1);
  for (const [ch, count] of map) {
    if (count === 1) return ch;
  }
  return null;
}
```

---

#### 444. Implement: Flatten array to any depth.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
// Using recursion:
function flatten(arr, depth = Infinity) {
  if (depth === 0) return [...arr];
  return arr.reduce((flat, item) => {
    if (Array.isArray(item)) {
      flat.push(...flatten(item, depth - 1));
    } else {
      flat.push(item);
    }
    return flat;
  }, []);
}

// Using stack (iterative, handles very deep arrays without stack overflow):
function flattenStack(arr) {
  const stack = [...arr];
  const result = [];
  while (stack.length) {
    const item = stack.pop();
    if (Array.isArray(item)) {
      stack.push(...item);
    } else {
      result.unshift(item); // unshift to maintain order
    }
  }
  return result;
}

console.log(flatten([1, [2, [3, [4]], 5]]));   // [1, 2, 3, 4, 5]
console.log(flatten([1, [2, [3, [4]]]], 1));   // [1, 2, [3, [4]]]
```

---

#### 445. Implement: Check if a string is a palindrome (ignoring spaces/punctuation).

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function isPalindrome(str) {
  const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  return cleaned === cleaned.split('').reverse().join('');
}

// Two-pointer approach (O(1) space):
function isPalindromePointers(str) {
  const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  let left = 0, right = cleaned.length - 1;
  while (left < right) {
    if (cleaned[left] !== cleaned[right]) return false;
    left++;
    right--;
  }
  return true;
}

console.log(isPalindrome('A man, a plan, a canal: Panama')); // true
console.log(isPalindrome('race a car'));                      // false
```

---

#### 446. Implement: Deep merge two objects.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function deepMerge(target, source) {
  const result = { ...target };
  for (const key of Object.keys(source)) {
    if (
      source[key] !== null &&
      typeof source[key] === 'object' &&
      !Array.isArray(source[key]) &&
      key in target &&
      typeof target[key] === 'object' &&
      !Array.isArray(target[key])
    ) {
      result[key] = deepMerge(target[key], source[key]);
    } else {
      result[key] = source[key];
    }
  }
  return result;
}

const a = { x: 1, nested: { y: 2, z: 3 } };
const b = { nested: { y: 99, w: 4 }, extra: 5 };
console.log(deepMerge(a, b));
// { x: 1, nested: { y: 99, z: 3, w: 4 }, extra: 5 }
```

---

#### 447. Implement: `chunk(array, size)` — split array into chunks.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function chunk(arr, size) {
  if (size <= 0) throw new Error('Chunk size must be positive');
  const result = [];
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size));
  }
  return result;
}

// Alternative with reduce:
const chunk2 = (arr, size) =>
  arr.reduce((acc, _, i) =>
    i % size === 0 ? [...acc, arr.slice(i, i + size)] : acc, []);

console.log(chunk([1,2,3,4,5,6,7], 3)); // [[1,2,3],[4,5,6],[7]]
console.log(chunk([1,2,3,4], 2));        // [[1,2],[3,4]]
```

---

#### 448. Implement: `pipe` with error handling and async support.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const pipeAsync = (...fns) => (input) =>
  fns.reduce((promise, fn) => promise.then(fn), Promise.resolve(input));

// Usage:
const processUser = pipeAsync(
  async (id) => {
    const res = await fetch(`/api/users/${id}`);
    return res.json();
  },
  (user) => ({ ...user, fullName: `${user.firstName} ${user.lastName}` }),
  async (user) => {
    await fetch(`/api/log`, { method: 'POST', body: JSON.stringify(user) });
    return user;
  }
);

processUser(1).then(console.log).catch(console.error);
```

---

#### 449. Implement: `once` — function that can only be called once.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
function once(fn) {
  let called = false;
  let result;
  return function(...args) {
    if (!called) {
      called = true;
      result = fn.apply(this, args);
    }
    return result;
  };
}

const initialize = once(() => {
  console.log('initializing...');
  return { initialized: true };
});

initialize(); // initializing... → { initialized: true }
initialize(); // returns cached result, no log
initialize(); // returns cached result, no log
```

---

#### 450. Implement: `compose` vs `pipe` — output prediction.

[↑ Back to Table of Contents](#table-of-contents)


```javascript
const add10 = x => x + 10;
const multiply2 = x => x * 2;
const subtract3 = x => x - 3;

const pipe = (...fns) => x => fns.reduce((v, f) => f(v), x);
const compose = (...fns) => x => fns.reduceRight((v, f) => f(v), x);

const pipeFn = pipe(add10, multiply2, subtract3);
const composeFn = compose(subtract3, multiply2, add10);

console.log(pipeFn(5));     // (5+10)*2-3 = 27
console.log(composeFn(5));  // (5+10)*2-3 = 27 — SAME because same order

// Different ordering:
const p2 = pipe(subtract3, multiply2, add10);
const c2 = compose(add10, multiply2, subtract3);
console.log(p2(5));  // (5-3)*2+10 = 14
console.log(c2(5));  // (5-3)*2+10 = 14 — compose reverses the array
```

---

#### 451. What is the output? (Most asked JS output question)

[↑ Back to Table of Contents](#table-of-contents)


```javascript
for (var i = 0; i < 5; i++) {
  setTimeout(function() { console.log(i); }, i * 1000);
}
```

**Output:** `5, 5, 5, 5, 5` (each after 0s, 1s, 2s, 3s, 4s)

**Fix 1 — let:**
```javascript
for (let i = 0; i < 5; i++) {
  setTimeout(() => console.log(i), i * 1000); // 0,1,2,3,4
}
```

**Fix 2 — IIFE:**
```javascript
for (var i = 0; i < 5; i++) {
  (function(j) {
    setTimeout(() => console.log(j), j * 1000);
  })(i); // 0,1,2,3,4
}
```

**Fix 3 — bind:**
```javascript
for (var i = 0; i < 5; i++) {
  setTimeout(console.log.bind(null, i), i * 1000); // 0,1,2,3,4
}
```

---

#### 452. What is the output? (Ultimate async challenge)

[↑ Back to Table of Contents](#table-of-contents)


```javascript
console.log('script start');

async function async1() {
  console.log('async1 start');
  await async2();
  console.log('async1 end');
}

async function async2() {
  console.log('async2');
}

setTimeout(function() {
  console.log('setTimeout');
}, 0);

async1();

new Promise(function(resolve) {
  console.log('promise1');
  resolve();
}).then(function() {
  console.log('promise2');
}).then(function() {
  console.log('promise3');
});

console.log('script end');
```

**Output:**
```
script start
async1 start
async2
promise1
script end
async1 end
promise2
promise3
setTimeout
```

**Step-by-step:**
1. `script start` — sync
2. `async1()` called → `async1 start` — sync (before first await)
3. `await async2()` → calls `async2`, logs `async2` — sync up to async2's return
4. `await` suspends async1 — control returns
5. `new Promise(executor)` runs synchronously → `promise1`, resolve() called
6. `.then` callbacks queued as microtasks
7. `script end` — sync code done
8. Microtask queue: `async1 end` (resumed after await), then `promise2`, then `promise3`
9. Macrotask: `setTimeout`

---

## Polyfills & Implementations Reference

[↑ Back to Table of Contents](#table-of-contents)

1. Array Methods
text
✓ map()      - Transform array elements
✓ filter()   - Filter array elements
✓ reduce()   - Accumulate array values
✓ forEach()  - Iterate array
✓ flat()     - Flatten nested arrays
✓ includes() - Check if element exists
2. Function Methods
text
✓ call()     - Invoke function with context
✓ apply()    - Invoke function with array args
✓ bind()     - Create function with context
3. Promise Methods
text
✓ all()           - Wait for all promises
✓ allSettled()    - Wait for all (success/error)
✓ any()           - First successful promise
✓ race()          - First resolved promise
4. Advanced 
text
✓ debounce()
✓ throttle()
✓ deepCopy()
✓ deepMerge()
✓ flatten()
✓ useEffect() (React hook polyfill)

## Complete Polyfills for Array Methods (Most Asked)

Here are the **complete code implementations** for all 6 most asked array polyfills:

***

### 1️⃣ **Array.map()** - Transform Array Elements

#### **What it does:**
Creates a new array by applying a function to each element.

#### **Polyfill:**
```javascript
Array.prototype.myMap = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    result.push(callback(this[i], i, this));
  }
  return result;
};

// Usage
const arr = [1, 2, 3, 4, 5];
const multiplied = arr.myMap((num, index) => num * 2);
console.log(multiplied); // [2, 4, 6, 8, 10]
```

#### **Key Points:**
- ✅ Returns **new array** (doesn't modify original)
- ✅ Callback receives: `value`, `index`, `array`
- ✅ Length of result = length of original array [dev](https://dev.to/pawan16123/javascript-most-asked-polyfills-25e3)

***

### 2️⃣ **Array.filter()** - Filter Array Elements

#### **What it does:**
Creates a new array with elements that pass a test (return true).

#### **Polyfill:**
```javascript
Array.prototype.myFilter = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};

// Usage
const arr = [1, 2, 3, 4, 5, 6];
const evenNumbers = arr.myFilter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4, 6]
```

#### **Key Points:**
- ✅ Returns **new array** with only matching elements
- ✅ Callback must return `true` to include element
- ✅ Result length can be less than original [medium](https://medium.com/@aniketbkangane9637/javascript-polyfills-for-map-filter-and-reduce-most-asked-interview-questions-edc20d9ae937)

***

### 3️⃣ **Array.reduce()** - Accumulate Array Values

#### **What it does:**
Reduces array to a single value by accumulating.

#### **Polyfill:**
```javascript
Array.prototype.myReduce = function(callback, initialValue) {
  let accumulator;
  let startIndex;
  
  // Handle initialValue
  if (initialValue !== undefined) {
    accumulator = initialValue;
    startIndex = 0;
  } else {
    accumulator = this[0];
    startIndex = 1;
  }
  
  for (let i = startIndex; i < this.length; i++) {
    accumulator = callback(accumulator, this[i], i, this);
  }
  
  return accumulator;
};

// Usage
const arr = [1, 2, 3, 4, 5];
const sum = arr.myReduce((acc, num) => acc + num, 0);
console.log(sum); // 15

// Without initialValue
const sum2 = arr.myReduce((acc, num) => acc + num);
console.log(sum2); // 15 (starts with arr[0])
```

#### **Key Points:**
- ✅ Returns **single value** (not array)
- ✅ Takes `initialValue` (optional)
- ✅ Callback receives: `accumulator`, `currentValue`, `index`, `array`
- ✅ If no initialValue, starts with `arr[0]` [medium](https://medium.com/@imPradhyumn/polyfills-for-map-filter-and-reduce-in-7914ea26bf37)

***

### 4️⃣ **Array.forEach()** - Iterate Array

#### **What it does:**
Executes callback for each element (no return value).

#### **Polyfill:**
```javascript
Array.prototype.myForEach = function(callback) {
  for (let i = 0; i < this.length; i++) {
    callback(this[i], i, this);
  }
  // Returns undefined
};

// Usage
const arr = [1, 2, 3, 4, 5];
arr.myForEach((num, index) => {
  console.log(`Index ${index}: ${num}`);
});

// Output:
// Index 0: 1
// Index 1: 2
// Index 2: 3
// Index 3: 4
// Index 4: 5
```

#### **Key Points:**
- ✅ Returns **undefined** (no new array)
- ✅ Just executes callback for side effects
- ✅ Callback receives: `value`, `index`, `array` [dev](https://dev.to/umerjaved178/polyfills-for-foreach-map-filter-reduce-in-javascript-1h13)

***

### 5️⃣ **Array.flat()** - Flatten Nested Arrays

#### **What it does:**
Flattens nested arrays into a single-level array.

#### **Polyfill:**
```javascript
Array.prototype.myFlat = function(depth = 1) {
  const result = [];
  
  const flatten = (arr, currentDepth) => {
    for (let i = 0; i < arr.length; i++) {
      if (Array.isArray(arr[i]) && currentDepth < depth) {
        flatten(arr[i], currentDepth + 1);
      } else {
        result.push(arr[i]);
      }
    }
  };
  
  flatten(this, 0);
  return result;
};

// Usage
const nested = [1, [2, 3], [4, [5, 6]], 7];
const flattened = nested.myFlat();
console.log(flattened); // [1, 2, 3, 4, 5, 6, 7]

// With depth
const nested2 = [1, [2, [3,  [medium](https://medium.com/@imPradhyumn/polyfills-for-map-filter-and-reduce-in-7914ea26bf37)]]];
const flattened2 = nested2.myFlat(2);
console.log(flattened2); // [1, 2, 3,  [medium](https://medium.com/@imPradhyumn/polyfills-for-map-filter-and-reduce-in-7914ea26bf37)]
```

#### **Key Points:**
- ✅ Returns **new flattened array**
- ✅ `depth` parameter (default = 1)
- ✅ Uses recursion for nested arrays
- ✅ `myFlat(Infinity)` flattens all levels [medium](https://medium.com/@mynkmishra/polyfills-in-javascript-1-3-17d4927ebd49)

***

### 6️⃣ **Array.includes()** - Check Element Exists

#### **What it does:**
Checks if array contains a specific element.

#### **Polyfill:**
```javascript
Array.prototype.myIncludes = function(searchElement, fromIndex = 0) {
  // Handle negative fromIndex
  if (fromIndex < 0) {
    fromIndex = Math.max(this.length + fromIndex, 0);
  }
  
  // Handle fromIndex beyond array length
  if (fromIndex >= this.length) {
    return false;
  }
  
  for (let i = fromIndex; i < this.length; i++) {
    // Use SameValueZero algorithm (handles NaN)
    if (this[i] === searchElement || 
        (this[i] !== this[i] && searchElement !== searchElement)) {
      return true;
    }
  }
  
  return false;
};

// Usage
const arr = [1, 2, 3, 4, 5];
console.log(arr.myIncludes(3)); // true
console.log(arr.myIncludes(6)); // false
console.log(arr.myIncludes(3, 2)); // true (from index 2)
console.log(arr.myIncludes(3, 5)); // false (fromIndex beyond length)
```

#### **Key Points:**
- ✅ Returns **boolean** (`true`/`false`)
- ✅ `fromIndex` parameter (default = 0)
- ✅ Handles `NaN` correctly (uses SameValueZero)
- ✅ Negative `fromIndex` works correctly [github](https://github.com/siddhigate/js-polyfills)

***

### 📊 **Comparison Table**

| Method | Returns | Modifies Original | Callback Params |
|--------|---------|-------------------|-----------------|
| `map()` | New Array | ❌ No | `value, index, array` |
| `filter()` | New Array | ❌ No | `value, index, array` |
| `reduce()` | Single Value | ❌ No | `acc, value, index, array` |
| `forEach()` | `undefined` | ❌ No | `value, index, array` |
| `flat()` | New Array | ❌ No | None (uses recursion) |
| `includes()` | `boolean` | ❌ No | None (uses loop) |

***



#### **Key Differences to Remember:**

```javascript
// map vs forEach
[1,2,3].map(x => x * 2);  // [2, 4, 6] (returns new array)
[1,2,3].forEach(x => x * 2); // undefined (returns nothing)

// filter vs map
[1,2,3].filter(x => x > 1); // [2, 3] (only matches)
[1,2,3].map(x => x > 1); // [false, true, true] (all transformed)

// reduce vs map
[1,2,3].reduce((a, b) => a + b, 0); // 6 (single value)
[1,2,3].map(x => x); // [1, 2, 3] (new array)
```

***

### ✅ **Complete Test Suite**

```javascript
// Test all polyfills
const testArray = [1, 2, 3, 4, 5];

console.log('map:', testArray.myMap(x => x * 2)); // [2, 4, 6, 8, 10]
console.log('filter:', testArray.myFilter(x => x > 3)); // [4, 5]
console.log('reduce:', testArray.myReduce((a, b) => a + b, 0)); // 15
console.log('forEach:', testArray.myForEach(x => console.log(x))); // 1,2,3,4,5
console.log('flat:', [1, [2, 3], [4,  [medium](https://medium.com/@mynkmishra/polyfills-in-javascript-1-3-17d4927ebd49)]].myFlat()); // [1, 2, 3, 4, 5]
console.log('includes:', testArray.myIncludes(3)); // true
```

## Complete Polyfills: Function, Promise & Advanced Methods

Here are the **complete code implementations** for Function methods, Promise methods, and Advanced utility functions:

***

### 📚 **2. Function Methods Polyfills**

#### **2.1 Function.call()** - Invoke Function with Context

```javascript
Function.prototype.myCall = function(context, ...args) {
  // Handle null/undefined context (points to global)
  context = context || window;
  
  // Create unique symbol to avoid conflicts
  const fnSymbol = Symbol('fn');
  
  // Attach function to context
  context[fnSymbol] = this;
  
  // Invoke with args
  const result = context[fnSymbol](...args);
  
  // Clean up
  delete context[fnSymbol];
  
  return result;
};

// Usage
function greet(first, last) {
  return `Hello ${first} ${last}, I'm ${this.name}`;
}

const person = { name: 'John' };
console.log(greet.myCall(person, 'John', 'Doe')); // "Hello John Doe, I'm John"
```

**Key Points:**
- ✅ Executes function **immediately**
- ✅ Sets `this` context explicitly
- ✅ Args are **comma-separated** [youtube](https://www.youtube.com/watch?v=w_7tJqNy4_c)

***

#### **2.2 Function.apply()** - Invoke Function with Array Args

```javascript
Function.prototype.myApply = function(context, argsArray) {
  // Handle null/undefined context
  context = context || window;
  
  // Create unique symbol
  const fnSymbol = Symbol('fn');
  
  // Attach function to context
  context[fnSymbol] = this;
  
  // Handle undefined/null argsArray
  let result;
  if (argsArray === undefined || argsArray === null) {
    result = context[fnSymbol]();
  } else {
    // Must be array-like
    result = context[fnSymbol](...argsArray);
  }
  
  // Clean up
  delete context[fnSymbol];
  
  return result;
};

// Usage
function sum(a, b, c) {
  return a + b + c;
}

const numbers = [1, 2, 3];
console.log(sum.myApply(null, numbers)); // 6
```

**Key Points:**
- ✅ Executes function **immediately**
- ✅ Sets `this` context explicitly
- ✅ Args are **array** format 
***

#### **2.3 Function.bind()** - Create Function with Context

```javascript
Function.prototype.myBind = function(context, ...initialArgs) {
  // Save reference to original function
  const self = this;
  
  // Create unique symbol
  const fnSymbol = Symbol('fn');
  
  return function(...newArgs) {
    // Attach function to context
    context[fnSymbol] = self;
    
    // Merge initialArgs + newArgs
    const combinedArgs = [...initialArgs, ...newArgs];
    
    // Invoke with args
    const result = context[fnSymbol](...combinedArgs);
    
    // Clean up
    delete context[fnSymbol];
    
    return result;
  };
};

// Usage
function greet(first, last) {
  return `Hello ${first} ${last}, I'm ${this.name}`;
}

const person = { name: 'Jane' };
const boundGreet = greet.myBind(person, 'Jane');

console.log(boundGreet('Doe')); // "Hello Jane Doe, I'm Jane"
```

**Key Points:**
- ✅ Returns **new function** (doesn't execute immediately)
- ✅ Sets `this` context permanently
- ✅ Can set initial args [youtube](https://www.youtube.com/watch?v=w_7tJqNy4_c)

***

#### **2.4 compare: call vs apply vs bind**

| Method | Executes? | Args Format | Returns |
|--------|-----------|-------------|---------|
| `call()` | ✅ Immediately | Comma-separated | Result |
| `apply()` | ✅ Immediately | Array | Result |
| `bind()` | ❌ Returns function | Comma-separated | Function |

 [rahuulmiishra.medium](https://rahuulmiishra.medium.com/interviewer-write-the-polyfill-of-call-apply-and-bind-in-2-different-ways-844156550be9)

***

### 📚 **3. Promise Methods Polyfills**

#### **3.1 Promise.all()** - Wait for All Promises

```javascript
Promise.myAll = function(promises) {
  return new Promise((resolve, reject) => {
    const results = [];
    let completed = 0;
    
    if (promises.length === 0) {
      resolve(results);
      return;
    }
    
    promises.forEach((promise, index) => {
      Promise.resolve(promise).then(value => {
        results[index] = value;
        completed++;
        
        if (completed === promises.length) {
          resolve(results);
        }
      }).catch(reject);
    });
  });
};

// Usage
Promise.myAll([
  Promise.resolve(1),
  Promise.resolve(2),
  Promise.resolve(3)
]).then(results => console.log(results)); // [1, 2, 3]
```

**Key Points:**
- ✅ Returns **Promise** that resolves when all succeed
- ✅ If **any fails**, entire Promise rejects
- ✅ Results maintain **original order** [dev](https://dev.to/paharihacker/mastering-javascript-promises-a-guide-to-polyfills-and-advanced-techniques-4p3c)

***

#### **3.2 Promise.allSettled()** - Wait for All (Success/Error)

```javascript
Promise.myAllSettled = function(promises) {
  return new Promise((resolve) => {
    const results = [];
    let completed = 0;
    
    if (promises.length === 0) {
      resolve(results);
      return;
    }
    
    promises.forEach((promise, index) => {
      Promise.resolve(promise).then(value => {
        results[index] = { status: 'fulfilled', value: value };
        completed++;
        
        if (completed === promises.length) {
          resolve(results);
        }
      }).catch(error => {
        results[index] = { status: 'rejected', reason: error };
        completed++;
        
        if (completed === promises.length) {
          resolve(results);
        }
      });
    });
  });
};

// Usage
Promise.myAllSettled([
  Promise.resolve(1),
  Promise.reject('Error'),
  Promise.resolve(3)
]).then(results => console.log(results));
// [
//   { status: 'fulfilled', value: 1 },
//   { status: 'rejected', reason: 'Error' },
//   { status: 'fulfilled', value: 3 }
// ]
```

**Key Points:**
- ✅ Returns **Promise** that resolves after all settle
- ✅ Ignores failures (waits for all)
- ✅ Returns status + value/reason [medium](https://medium.com/@flintBits/a-step-by-step-guide-to-polyfilling-javascript-promises-9d7ec3551f8c)

***

#### **3.3 Promise.any()** - First Successful Promise

```javascript
Promise.myAny = function(promises) {
  return new Promise((resolve, reject) => {
    let rejectedCount = 0;
    
    if (promises.length === 0) {
      reject(new TypeError('Promise.any() on empty array'));
      return;
    }
    
    promises.forEach((promise, index) => {
      Promise.resolve(promise).then(value => {
        resolve(value);
      }).catch(error => {
        rejectedCount++;
        
        if (rejectedCount === promises.length) {
          reject(error);
        }
      });
    });
  });
};

// Usage
Promise.myAny([
  Promise.reject('Error 1'),
  Promise.resolve(2),
  Promise.resolve(3)
]).then(result => console.log(result)); // 2
```

**Key Points:**
- ✅ Returns **Promise** that resolves on **first success**
- ✅ Only rejects if **all fail**
- ✅ Ignores rejections until all fail [dev](https://dev.to/mandy8055/which-promise-method-do-you-need-da9)

***

#### **3.4 Promise.race()** - First Resolved Promise

```javascript
Promise.myRace = function(promises) {
  return new Promise((resolve, reject) => {
    if (promises.length === 0) {
      // Never settles (pending forever)
      return;
    }
    
    promises.forEach(promise => {
      Promise.resolve(promise).then(resolve).catch(reject);
    });
  });
};

// Usage
Promise.myRace([
  Promise.resolve(1),
  new Promise(resolve => setTimeout(() => resolve(2), 100)),
  new Promise(resolve => setTimeout(() => resolve(3), 50))
]).then(result => console.log(result)); // 3 (first to complete)
```

**Key Points:**
- ✅ Returns **Promise** that resolves on **first completion**
- ✅ If first is **rejection**, entire Promise rejects
- ✅ `race([])` never settles [dev](https://dev.to/paharihacker/mastering-javascript-promises-a-guide-to-polyfills-and-advanced-techniques-4p3c)

***

#### **3.5 compare: Promise Methods**

| Method | Resolves When | Rejects When |
|--------|---------------|--------------|
| `all()` | All succeed | Any fails |
| `allSettled()` | All settle | Never (always resolves) |
| `any()` | First succeeds | All fail |
| `race()` | First completes | First rejects |

 [dev](https://dev.to/mandy8055/which-promise-method-do-you-need-da9)

***

### 📚 **4. Advanced Utility Polyfills**

#### **4.1 debounce()** - Delay Execution Until Gap

```javascript
function debounce(callback, delay) {
  let timer;
  
  return function(...args) {
    // Clear previous timer
    clearTimeout(timer);
    
    // Set new timer
    timer = setTimeout(() => {
      callback(...args);
    }, delay);
  };
}

// Usage
const searchInput = document.getElementById('search');
const debouncedSearch = debounce((value) => {
  console.log('Searching for:', value);
}, 500);

searchInput.addEventListener('input', (e) => {
  debouncedSearch(e.target.value);
});

// Only calls search after 500ms of no typing
```

**Key Points:**
- ✅ Delays execution until **no calls** for `delay` ms
- ✅ Useful for: search input, resize events
- ✅ **Last call** executes [medium](https://medium.com/@kumarazad2917/debounce-throttling-with-polyfill-in-javascript-e368711f180a)

***

#### **4.2 throttle()** - Limit Execution Frequency

```javascript
function throttle(callback, delay) {
  let isThrottled = false;
  
  return function(...args) {
    if (!isThrottled) {
      callback(...args);
      isThrottled = true;
      
      setTimeout(() => {
        isThrottled = false;
      }, delay);
    }
  };
}

// Usage
const scrollContainer = document.getElementById('scroll');
const throttledScroll = throttle(() => {
  console.log('Scroll position:', window.scrollY);
}, 100);

scrollContainer.addEventListener('scroll', throttledScroll);

// Executes at most once every 100ms
```

**Key Points:**
- ✅ Executes at **most once** per `delay` ms
- ✅ **First call** executes immediately
- ✅ Useful for: scroll, mousemove events [blog.stackademic](https://blog.stackademic.com/interview9-polyfill-for-debounce-and-throttle-in-javascript-c1ea63553a0b?gi=876fae31fd66)

***

#### **4.3 deepCopy()** - Clone Object Recursively

```javascript
function deepCopy(obj) {
  // Handle non-objects
  if (obj === null || typeof obj !== 'object') {
    return obj;
  }
  
  // Handle Date
  if (obj instanceof Date) {
    return new Date(obj);
  }
  
  // Handle Array
  if (Array.isArray(obj)) {
    return obj.map(item => deepCopy(item));
  }
  
  // Handle Object
  const copy = {};
  for (const key in obj) {
    if (obj.hasOwnProperty(key)) {
      copy[key] = deepCopy(obj[key]);
    }
  }
  
  return copy;
}

// Usage
const original = {
  a: 1,
  b: { c: 2, d: [3, 4, 5] },
  e: new Date()
};

const copy = deepCopy(original);
copy.b.c = 99;

console.log(original.b.c); // 2 (unchanged)
console.log(copy.b.c); // 99 (changed)
```

**Key Points:**
- ✅ Creates **new object** (no reference)
- ✅ Handles nested objects, arrays, dates
- ✅ Recursively copies all levels [reddit](https://www.reddit.com/r/developersIndia/comments/1cmerp8/what_all_polyfills_have_you_written_in_frontend/)

***

#### **4.4 deepMerge()** - Merge Objects Recursively

```javascript
function deepMerge(obj1, obj2) {
  const result = {};
  
  // Copy all keys from obj1
  for (const key in obj1) {
    if (obj1.hasOwnProperty(key)) {
      result[key] = obj1[key];
    }
  }
  
  // Merge keys from obj2
  for (const key in obj2) {
    if (obj2.hasOwnProperty(key)) {
      // If both are objects, merge recursively
      if (
        typeof result[key] === 'object' &&
        typeof obj2[key] === 'object' &&
        !Array.isArray(result[key]) &&
        !Array.isArray(obj2[key])
      ) {
        result[key] = deepMerge(result[key], obj2[key]);
      } else {
        result[key] = obj2[key];
      }
    }
  }
  
  return result;
}

// Usage
const obj1 = {
  a: 1,
  b: { c: 2, d: 3 }
};

const obj2 = {
  b: { c: 99, e: 4 },
  f: 5
};

const merged = deepMerge(obj1, obj2);
console.log(merged);
// { a: 1, b: { c: 99, d: 3, e: 4 }, f: 5 }
```

**Key Points:**
- ✅ **Merges** objects recursively
- ✅ obj2 **overwrites** obj1 properties
- ✅ Nested objects **merged** (not replaced) [reddit](https://www.reddit.com/r/developersIndia/comments/1cmerp8/what_all_polyfills_have_you_written_in_frontend/)

***

#### **4.5 flatten()** - Flatten Nested Arrays (Alternative)

```javascript
function flatten(arr, depth = 1) {
  const result = [];
  
  function flattenHelper(array, currentDepth) {
    for (const item of array) {
      if (Array.isArray(item) && currentDepth < depth) {
        flattenHelper(item, currentDepth + 1);
      } else {
        result.push(item);
      }
    }
  }
  
  flattenHelper(arr, 0);
  return result;
}

// Usage
const nested = [1, [2, 3], [4, [5, 6]], 7];
console.log(flatten(nested)); // [1, 2, 3, 4, 5, 6, 7]
console.log(flatten(nested, 2)); // [1, 2, 3, 4, 5, 6, 7]
console.log(flatten(nested, 1)); // [1, 2, 3, 4, [5, 6], 7]
```

**Key Points:**
- ✅ Flattens nested arrays
- ✅ `depth` parameter (default = 1)
- ✅ Uses recursion [blog.stackademic](https://blog.stackademic.com/interview9-polyfill-for-debounce-and-throttle-in-javascript-c1ea63553a0b?gi=876fae31fd66)

***

#### **4.6 useEffect()** - React Hook Polyfill (Simplified)

```javascript
// Simplified useEffect polyfill (for understanding)
const useEffect = (callback, dependencies = []) => {
  let prevDependencies = [];
  
  // Compare dependencies
  const hasChanged = dependencies.some((dep, i) => dep !== prevDependencies[i]);
  
  if (hasChanged || dependencies.length === 0) {
    callback();
    prevDependencies = [...dependencies];
  }
};

// Note: This is NOT a real React implementation, just for understanding
```

**Key Points:**
- ✅ React hook for side effects
- ✅ Runs on mount (no deps) or when deps change
- ✅ Real implementation uses React internals [reddit](https://www.reddit.com/r/developersIndia/comments/1cmerp8/what_all_polyfills_have_you_written_in_frontend/)

***

### 🎯 **Interview Priority**

#### **Must Know:**
1. ✅ `call()` / `apply()` / `bind()`
2. ✅ `Promise.all()`
3. ✅ `debounce()` / `throttle()`

#### **Should Know:**
4. ✅ `Promise.allSettled()` / `any()` / `race()`
5. ✅ `deepCopy()`

#### **Nice to Know:**
6. ✅ `deepMerge()` / `flatten()`

***
