# JavaScript Interview Questions — Theoretical / Conceptual

A consolidated, deduplicated collection of **conceptual and theoretical core JavaScript interview questions**, compiled from every relevant file in the Frontend study-reference folder and organized section-wise. Hands-on coding/implementation tasks and real-world scenario questions are in their own companion documents.

**Total unique questions: 411**

## Table of Contents

- [Closures, Scope & Hoisting](#closures-scope-hoisting) (23)
  - [1. Explain closures with a real-world example?](#1-explain-closures-with-a-real-world-example)
  - [2. How do arrow functions differ from regular functions regarding `this`?](#2-how-do-arrow-functions-differ-from-regular-functions-regarding-this)
  - [3. How does `this` work in arrow functions?](#3-how-does-this-work-in-arrow-functions)
  - [4. What is `this` in JavaScript?](#4-what-is-this-in-javascript)
  - [5. What is a closure memory leak and how do you avoid it?](#5-what-is-a-closure-memory-leak-and-how-do-you-avoid-it)
  - [6. What is a closure?](#6-what-is-a-closure)
  - [7. What is a common closure bug in loops?](#7-what-is-a-common-closure-bug-in-loops)
  - [8. What is an execution context?](#8-what-is-an-execution-context)
  - [9. What is hoisting?](#9-what-is-hoisting)
  - [10. What is lexical scope?](#10-what-is-lexical-scope)
  - [11. What is scope chain resolution?](#11-what-is-scope-chain-resolution)
  - [12. What is scope in JavaScript?](#12-what-is-scope-in-javascript)
  - [13. What is scope? Explain global, function, and block scope.](#13-what-is-scope-explain-global-function-and-block-scope)
  - [14. What is the call stack?](#14-what-is-the-call-stack)
  - [15. What is the difference between function declaration and function expression?](#15-what-is-the-difference-between-function-declaration-and-function-expression)
  - [16. What is the difference between function scope and block scope?](#16-what-is-the-difference-between-function-scope-and-block-scope)
  - [17. What is the difference between implicit and explicit global variables?](#17-what-is-the-difference-between-implicit-and-explicit-global-variables)
  - [18. What is the scope chain?](#18-what-is-the-scope-chain)
  - [19. What is the Singleton pattern?](#19-what-is-the-singleton-pattern)
  - [20. What is the Temporal Dead Zone (TDZ)?](#20-what-is-the-temporal-dead-zone-tdz)
  - [21. What is variable hoisting?](#21-what-is-variable-hoisting)
  - [22. Why do we get `ReferenceError: Cannot access 'x' before initialization`?](#22-why-do-we-get-referenceerror-cannot-access-x-before-initialization)
  - [23. Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)](#23-why-does-javascript-have-closures-data-privacy-hooks-callbacks-memoization)
- [`this`, call/apply/bind & Functions](#this-callapplybind-functions) (14)
  - [24. Arrow Function as a Class Field?](#24-arrow-function-as-a-class-field)
  - [25. How do `call`, `apply`, and `bind` work?](#25-how-do-call-apply-and-bind-work)
  - [26. What are Arrow Functions?](#26-what-are-arrow-functions)
  - [27. What are the four rules that determine `this`?](#27-what-are-the-four-rules-that-determine-this)
  - [28. What is a first-class function?](#28-what-is-a-first-class-function)
  - [29. What is a higher-order function?](#29-what-is-a-higher-order-function)
  - [30. What is a pure function?](#30-what-is-a-pure-function)
  - [31. What is an IIFE and why is it used?](#31-what-is-an-iife-and-why-is-it-used)
  - [32. What is currying?](#32-what-is-currying)
  - [33. What is function currying?](#33-what-is-function-currying)
  - [34. What is IIFE (Immediately Invoked Function Expression) and why was it used?](#34-what-is-iife-immediately-invoked-function-expression-and-why-was-it-used)
  - [35. What is partial application?](#35-what-is-partial-application)
  - [36. What is point-free style?](#36-what-is-point-free-style)
  - [37. Why does `this` lose context in callbacks?](#37-why-does-this-lose-context-in-callbacks)
- [Prototypes, Classes & OOP](#prototypes-classes-oop) (53)
  - [38. `__proto__` (The Link on the Product)](#38-proto-the-link-on-the-product)
  - [39. `prototype` (The Blueprint on the Factory)](#39-prototype-the-blueprint-on-the-factory)
  - [40. Explain the concept of specificity in CSS.](#40-explain-the-concept-of-specificity-in-css)
  - [41. How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)](#41-how-do-javascript-engines-optimize-code-jit-hidden-classes-inline-caching)
  - [42. How do you implement dark mode across an app?](#42-how-do-you-implement-dark-mode-across-an-app)
  - [43. How does JavaScript sort arrays by default and what is the gotcha?](#43-how-does-javascript-sort-arrays-by-default-and-what-is-the-gotcha)
  - [44. How does prototypal inheritance work?](#44-how-does-prototypal-inheritance-work)
  - [45. How does the `this` keyword behave in arrow functions, class methods, and event handlers?](#45-how-does-the-this-keyword-behave-in-arrow-functions-class-methods-and-event-handlers)
  - [46. How does V8 optimize JavaScript?](#46-how-does-v8-optimize-javascript)
  - [47. What are arrow functions and how do they differ from regular functions?](#47-what-are-arrow-functions-and-how-do-they-differ-from-regular-functions)
  - [48. What are ES6 classes and how do they relate to prototypes?](#48-what-are-es6-classes-and-how-do-they-relate-to-prototypes)
  - [49. What are ES6 classes?](#49-what-are-es6-classes)
  - [50. What are getters and setters?](#50-what-are-getters-and-setters)
  - [51. What are private class fields?](#51-what-are-private-class-fields)
  - [52. What are private fields in classes?](#52-what-are-private-fields-in-classes)
  - [53. What are static methods and properties?](#53-what-are-static-methods-and-properties)
  - [54. What are the differences between `Map` and a plain object?](#54-what-are-the-differences-between-map-and-a-plain-object)
  - [55. What are the trade-offs between using `class` and factory functions in JavaScript?](#55-what-are-the-trade-offs-between-using-class-and-factory-functions-in-javascript)
  - [56. What are the ways to create objects in JavaScript?](#56-what-are-the-ways-to-create-objects-in-javascript)
  - [57. What are well-known Symbols?](#57-what-are-well-known-symbols)
  - [58. What does "first-class functions" mean?](#58-what-does-first-class-functions-mean)
  - [59. What does `new` do step by step?](#59-what-does-new-do-step-by-step)
  - [60. What does `super` do in a class?](#60-what-does-super-do-in-a-class)
  - [61. What is `hasOwnProperty`?](#61-what-is-hasownproperty)
  - [62. What is `instanceof` and how does it work?](#62-what-is-instanceof-and-how-does-it-work)
  - [63. What is `Object.create()`?](#63-what-is-objectcreate)
  - [64. What is `Object.getPrototypeOf()`?](#64-what-is-objectgetprototypeof)
  - [65. What is `structuredClone()`?](#65-what-is-structuredclone)
  - [66. What is `this` in a class?](#66-what-is-this-in-a-class)
  - [67. What is a class in JavaScript?](#67-what-is-a-class-in-javascript)
  - [68. What is a constructor function?](#68-what-is-a-constructor-function)
  - [69. What is a constructor?](#69-what-is-a-constructor)
  - [70. What is a Map vs a plain object?](#70-what-is-a-map-vs-a-plain-object)
  - [71. What is a mixin?](#71-what-is-a-mixin)
  - [72. What is a prototype in JavaScript?](#72-what-is-a-prototype-in-javascript)
  - [73. What is a pseudo-class? Give examples (:hover, :nth-child, etc.).](#73-what-is-a-pseudo-class-give-examples-hover-nth-child-etc)
  - [74. What is encapsulation and how is it achieved in JS?](#74-what-is-encapsulation-and-how-is-it-achieved-in-js)
  - [75. What is inheritance with `extends` and `super`?](#75-what-is-inheritance-with-extends-and-super)
  - [76. What is polymorphism in JavaScript?](#76-what-is-polymorphism-in-javascript)
  - [77. What is prototypal delegation vs classical inheritance?](#77-what-is-prototypal-delegation-vs-classical-inheritance)
  - [78. What is prototypal inheritance?](#78-what-is-prototypal-inheritance)
  - [79. What is prototype pollution?](#79-what-is-prototype-pollution)
  - [80. What is the `Array.prototype.at()` method?](#80-what-is-the-arrayprototypeat-method)
  - [81. What is the `prototype` property on functions?](#81-what-is-the-prototype-property-on-functions)
  - [82. What is the difference between `__proto__` and `prototype`?](#82-what-is-the-difference-between-proto-and-prototype)
  - [83. What is the difference between `for...in` and `for...of`?](#83-what-is-the-difference-between-forin-and-forof)
  - [84. What is the difference between `Object.create(null)` and `{}`?](#84-what-is-the-difference-between-objectcreatenull-and)
  - [85. What is the difference between classical and prototypal inheritance?](#85-what-is-the-difference-between-classical-and-prototypal-inheritance)
  - [86. What is the difference between composition and inheritance?](#86-what-is-the-difference-between-composition-and-inheritance)
  - [87. What is the difference between static and instance methods?](#87-what-is-the-difference-between-static-and-instance-methods)
  - [88. What is the Factory pattern?](#88-what-is-the-factory-pattern)
  - [89. What is the prototype chain?](#89-what-is-the-prototype-chain)
  - [90. When & Where?](#90-when-where)
- [ES6+ Features (Destructuring, Spread/Rest, Modules)](#es6-features-destructuring-spreadrest-modules) (55)
  - [91. Can you declare a `let` variable in a `switch` block without curly braces?](#91-can-you-declare-a-let-variable-in-a-switch-block-without-curly-braces)
  - [92. Explain AbortController and request cancellation.](#92-explain-abortcontroller-and-request-cancellation)
  - [93. Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.](#93-explain-techniques-for-dynamic-code-splitting-and-lazy-loading-in-multi-route-spas)
  - [94. Explain the JavaScript module resolution algorithm.](#94-explain-the-javascript-module-resolution-algorithm)
  - [95. Give a practical use case for closures.](#95-give-a-practical-use-case-for-closures)
  - [96. How do you analyze bundle size and fix tree shaking failures?](#96-how-do-you-analyze-bundle-size-and-fix-tree-shaking-failures)
  - [97. How do you make a JavaScript library tree-shakeable?](#97-how-do-you-make-a-javascript-library-tree-shakeable)
  - [98. How to create a truly immutable object?](#98-how-to-create-a-truly-immutable-object)
  - [99. If we have `var`, `let`, `const`, why do we need state variables?](#99-if-we-have-var-let-const-why-do-we-need-state-variables)
  - [100. Implicit Binding (The Object Before the Dot)](#100-implicit-binding-the-object-before-the-dot)
  - [101. What are computed property names?](#101-what-are-computed-property-names)
  - [102. What are default parameters?](#102-what-are-default-parameters)
  - [103. What are ES Modules (`import`/`export`)?](#103-what-are-es-modules-importexport)
  - [104. What are ES Modules (ESM)?](#104-what-are-es-modules-esm)
  - [105. What are mocks, stubs, and spies?](#105-what-are-mocks-stubs-and-spies)
  - [106. What are named exports vs default exports in ES modules?](#106-what-are-named-exports-vs-default-exports-in-es-modules)
  - [107. What are package.json `exports` and `main` fields?](#107-what-are-packagejson-exports-and-main-fields)
  - [108. What are rest parameters and the spread operator?](#108-what-are-rest-parameters-and-the-spread-operator)
  - [109. What are tagged template literals?](#109-what-are-tagged-template-literals)
  - [110. What are the differences between `var`, `let`, and `const`?](#110-what-are-the-differences-between-var-let-and-const)
  - [111. What are Worker Threads in Node.js?](#111-what-are-worker-threads-in-nodejs)
  - [112. What is a recursive function and what is tail call optimization?](#112-what-is-a-recursive-function-and-what-is-tail-call-optimization)
  - [113. What is a type assertion?](#113-what-is-a-type-assertion)
  - [114. What is CommonJS (`require`/`module.exports`)?](#114-what-is-commonjs-requiremoduleexports)
  - [115. What is destructuring?](#115-what-is-destructuring)
  - [116. What is immutability and why does it matter?](#116-what-is-immutability-and-why-does-it-matter)
  - [117. What is memoization?](#117-what-is-memoization)
  - [118. What is module federation?](#118-what-is-module-federation)
  - [119. What is nullish coalescing (`??`)?](#119-what-is-nullish-coalescing)
  - [120. What is object destructuring?](#120-what-is-object-destructuring)
  - [121. What is object shorthand property syntax?](#121-what-is-object-shorthand-property-syntax)
  - [122. What is optional chaining (`?.`)?](#122-what-is-optional-chaining)
  - [123. What is tail call optimization?](#123-what-is-tail-call-optimization)
  - [124. What is the `cluster` module?](#124-what-is-the-cluster-module)
  - [125. What is the `for...of` loop?](#125-what-is-the-forof-loop)
  - [126. What is the `void` operator?](#126-what-is-the-void-operator)
  - [127. What is the AbortController used for?](#127-what-is-the-abortcontroller-used-for)
  - [128. What is the CommonJS module system?](#128-what-is-the-commonjs-module-system)
  - [129. What is the difference between `jest.fn()`, `jest.spyOn()`, and `jest.mock()`?](#129-what-is-the-difference-between-jestfn-jestspyon-and-jestmock)
  - [130. What is the difference between `let` and `const` in terms of object mutation?](#130-what-is-the-difference-between-let-and-const-in-terms-of-object-mutation)
  - [131. What is the difference between `var`, `let`, and `const`?](#131-what-is-the-difference-between-var-let-and-const)
  - [132. What is the difference between CommonJS and ES Modules?](#132-what-is-the-difference-between-commonjs-and-es-modules)
  - [133. What is the difference between default and named exports?](#133-what-is-the-difference-between-default-and-named-exports)
  - [134. What is the difference between JavaScript and ECMAScript?](#134-what-is-the-difference-between-javascript-and-ecmascript)
  - [135. What is the difference between unit, integration, and E2E tests?](#135-what-is-the-difference-between-unit-integration-and-e2e-tests)
  - [136. What is the ECMAScript specification?](#136-what-is-the-ecmascript-specification)
  - [137. What is the Module pattern?](#137-what-is-the-module-pattern)
  - [138. What is the module scope?](#138-what-is-the-module-scope)
  - [139. What is the nullish coalescing operator (`??`)?](#139-what-is-the-nullish-coalescing-operator)
  - [140. What is the rest parameter (`...args`)?](#140-what-is-the-rest-parameter-args)
  - [141. What is the Revealing Module pattern?](#141-what-is-the-revealing-module-pattern)
  - [142. What is the spread operator for objects?](#142-what-is-the-spread-operator-for-objects)
  - [143. What is throttling?](#143-what-is-throttling)
  - [144. What is tree shaking and how does it relate to ES modules?](#144-what-is-tree-shaking-and-how-does-it-relate-to-es-modules)
  - [145. What is tree shaking?](#145-what-is-tree-shaking)
- [Arrays, Objects & Data Structures](#arrays-objects-data-structures) (25)
  - [146. Explain the difference between `Array.from()` and spread on a NodeList.](#146-explain-the-difference-between-arrayfrom-and-spread-on-a-nodelist)
  - [147. How do you deep clone an object?](#147-how-do-you-deep-clone-an-object)
  - [148. How do you flatten an array?](#148-how-do-you-flatten-an-array)
  - [149. How do you remove duplicates from an array?](#149-how-do-you-remove-duplicates-from-an-array)
  - [150. How do you safely handle `JSON.parse` with unknown input?](#150-how-do-you-safely-handle-jsonparse-with-unknown-input)
  - [151. How does `reduce` work?](#151-how-does-reduce-work)
  - [152. How does `structuredClone` differ from `JSON.parse(JSON.stringify())`?](#152-how-does-structuredclone-differ-from-jsonparsejsonstringify)
  - [153. How to avoid?](#153-how-to-avoid)
  - [154. How to check if a variable is an array?](#154-how-to-check-if-a-variable-is-an-array)
  - [155. How to convert an array-like object to an array?](#155-how-to-convert-an-array-like-object-to-an-array)
  - [156. What are the basic types in TypeScript?](#156-what-are-the-basic-types-in-typescript)
  - [157. What are the most important array methods?](#157-what-are-the-most-important-array-methods)
  - [158. What are the performance implications of `map`, `filter`, `reduce` chains?](#158-what-are-the-performance-implications-of-map-filter-reduce-chains)
  - [159. What does `flat()` and `flatMap()` do?](#159-what-does-flat-and-flatmap-do)
  - [160. What is `Object.keys()`, `Object.values()`, `Object.entries()`?](#160-what-is-objectkeys-objectvalues-objectentries)
  - [161. What is a WeakMap and when would you use it?](#161-what-is-a-weakmap-and-when-would-you-use-it)
  - [162. What is a WeakSet?](#162-what-is-a-weakset)
  - [163. What is array and object destructuring with defaults?](#163-what-is-array-and-object-destructuring-with-defaults)
  - [164. What is explicit binding with `call`, `apply`, and `bind`?](#164-what-is-explicit-binding-with-call-apply-and-bind)
  - [165. What is the `arguments` object?](#165-what-is-the-arguments-object)
  - [166. What is the difference between `forEach` and `map`?](#166-what-is-the-difference-between-foreach-and-map)
  - [167. What is the difference between `function` and `=>` in terms of `arguments` object?](#167-what-is-the-difference-between-function-and-in-terms-of-arguments-object)
  - [168. What is the difference between `map`, `filter`, and `reduce`?](#168-what-is-the-difference-between-map-filter-and-reduce)
  - [169. What is the difference between `Object.keys`, `Object.values`, `Object.entries`, and `Object.fromEntries`?](#169-what-is-the-difference-between-objectkeys-objectvalues-objectentries-and-objectfromentries)
  - [170. What is the difference between shallow copy and deep copy?](#170-what-is-the-difference-between-shallow-copy-and-deep-copy)
- [Type Coercion, Equality & Data Types](#type-coercion-equality-data-types) (11)
  - [171. What are Symbols?](#171-what-are-symbols)
  - [172. What are the primitive data types in JavaScript?](#172-what-are-the-primitive-data-types-in-javascript)
  - [173. What are the tricky parts of `==` type coercion rules?](#173-what-are-the-tricky-parts-of-type-coercion-rules)
  - [174. What are truthy and falsy values?](#174-what-are-truthy-and-falsy-values)
  - [175. What is `NaN` and how do you check for it?](#175-what-is-nan-and-how-do-you-check-for-it)
  - [176. What is `typeof` and what are its quirks?](#176-what-is-typeof-and-what-are-its-quirks)
  - [177. What is the difference between `==` comparisons and `Object.is`?](#177-what-is-the-difference-between-comparisons-and-objectis)
  - [178. What is the difference between `null` and `undefined`?](#178-what-is-the-difference-between-null-and-undefined)
  - [179. What is the logical assignment operators (`&&=`, `||=`, `??=`)?](#179-what-is-the-logical-assignment-operators)
  - [180. What is type coercion?](#180-what-is-type-coercion)
  - [181. What is type narrowing?](#181-what-is-type-narrowing)
- [Asynchronous JavaScript (Promises, async/await, Event Loop)](#asynchronous-javascript-promises-asyncawait-event-loop) (57)
  - [182. Callback functions – what are they? Callback hell.](#182-callback-functions-what-are-they-callback-hell)
  - [183. Event loop: Why does a Promise run before setTimeout? (Microtasks vs macrotasks)](#183-event-loop-why-does-a-promise-run-before-settimeout-microtasks-vs-macrotasks)
  - [184. Explain how JavaScript handles concurrency with the event loop, Workers, and SharedArrayBuffer.](#184-explain-how-javascript-handles-concurrency-with-the-event-loop-workers-and-sharedarraybuffer)
  - [185. Explain how you'd port a callback-based API to use Promises.](#185-explain-how-youd-port-a-callback-based-api-to-use-promises)
  - [186. Explain the JavaScript event loop in detail. Microtasks vs macrotasks.](#186-explain-the-javascript-event-loop-in-detail-microtasks-vs-macrotasks)
  - [187. How do you run async operations in parallel vs sequentially?](#187-how-do-you-run-async-operations-in-parallel-vs-sequentially)
  - [188. How do you test asynchronous code in Jest?](#188-how-do-you-test-asynchronous-code-in-jest)
  - [189. How does async flow work in Redux Toolkit?](#189-how-does-async-flow-work-in-redux-toolkit)
  - [190. How does Promise chaining work?](#190-how-does-promise-chaining-work)
  - [191. How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)](#191-how-to-handle-multiple-independent-api-calls-efficiently-promiseall-allsettled)
  - [192. How would you implement a robust frontend monitoring and logging system?](#192-how-would-you-implement-a-robust-frontend-monitoring-and-logging-system)
  - [193. Multiple API Calls: How to load a dashboard with independent APIs efficiently? (Promise.all, allSettled)](#193-multiple-api-calls-how-to-load-a-dashboard-with-independent-apis-efficiently-promiseall-allsettled)
  - [194. What are `Promise.allSettled`, `Promise.race`, and `Promise.any`?](#194-what-are-promiseallsettled-promiserace-and-promiseany)
  - [195. What are async generators and when would you use them?](#195-what-are-async-generators-and-when-would-you-use-them)
  - [196. What are callbacks and what problems do they have?](#196-what-are-callbacks-and-what-problems-do-they-have)
  - [197. What are ES2020+ features you should know?](#197-what-are-es2020-features-you-should-know)
  - [198. What are generators?](#198-what-are-generators)
  - [199. What are practical uses of closures?](#199-what-are-practical-uses-of-closures)
  - [200. What are the advantages of `Promise.allSettled` over `Promise.all`?](#200-what-are-the-advantages-of-promiseallsettled-over-promiseall)
  - [201. What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?](#201-what-are-the-call-stack-web-apis-callback-queue-and-microtask-queue)
  - [202. What are the states of a Promise?](#202-what-are-the-states-of-a-promise)
  - [203. What causes memory leaks in frontend applications? How to prevent them?](#203-what-causes-memory-leaks-in-frontend-applications-how-to-prevent-them)
  - [204. What does `finally` do in a Promise chain?](#204-what-does-finally-do-in-a-promise-chain)
  - [205. What happens if you `await` a non-Promise value?](#205-what-happens-if-you-await-a-non-promise-value)
  - [206. What is `async/await`?](#206-what-is-asyncawait)
  - [207. What is `createAsyncThunk()` and why is it used?](#207-what-is-createasyncthunk-and-why-is-it-used)
  - [208. What is `process.nextTick()`?](#208-what-is-processnexttick)
  - [209. What is `Promise.allSettled()`?](#209-what-is-promiseallsettled)
  - [210. What is `requestAnimationFrame` and why use it for animations?](#210-what-is-requestanimationframe-and-why-use-it-for-animations)
  - [211. What is `requestAnimationFrame`?](#211-what-is-requestanimationframe)
  - [212. What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?](#212-what-is-settimeout-vs-setinterval-vs-requestanimationframe)
  - [213. What is a callback and what is callback hell?](#213-what-is-a-callback-and-what-is-callback-hell)
  - [214. What is a callback function?](#214-what-is-a-callback-function)
  - [215. What is a monad (in practical JS terms)?](#215-what-is-a-monad-in-practical-js-terms)
  - [216. What is a Promise?](#216-what-is-a-promise)
  - [217. What is an unhandled promise rejection?](#217-what-is-an-unhandled-promise-rejection)
  - [218. What is dynamic `import()`?](#218-what-is-dynamic-import)
  - [219. What is lazy loading?](#219-what-is-lazy-loading)
  - [220. What is Node.js?](#220-what-is-nodejs)
  - [221. What is promise chaining?](#221-what-is-promise-chaining)
  - [222. What is single-threaded execution in JavaScript?](#222-what-is-single-threaded-execution-in-javascript)
  - [223. What is synchronous vs asynchronous code?](#223-what-is-synchronous-vs-asynchronous-code)
  - [224. What is the `fetch` API?](#224-what-is-the-fetch-api)
  - [225. What is the danger of floating Promises?](#225-what-is-the-danger-of-floating-promises)
  - [226. What is the difference between `Promise` and `async/await`?](#226-what-is-the-difference-between-promise-and-asyncawait)
  - [227. What is the difference between `setTimeout(fn, 0)` and `Promise.resolve().then(fn)`?](#227-what-is-the-difference-between-settimeoutfn-0-and-promiseresolvethenfn)
  - [228. What is the difference between `setTimeout` and `setInterval`?](#228-what-is-the-difference-between-settimeout-and-setinterval)
  - [229. What is the difference between macrotasks and microtasks?](#229-what-is-the-difference-between-macrotasks-and-microtasks)
  - [230. What is the difference between sequential and parallel async execution?](#230-what-is-the-difference-between-sequential-and-parallel-async-execution)
  - [231. What is the difference between the Microtask Queue and the Macrotask Queue?](#231-what-is-the-difference-between-the-microtask-queue-and-the-macrotask-queue)
  - [232. What is the Event Loop?](#232-what-is-the-event-loop)
  - [233. What is the event loop? How does it work with the call stack and task queue?](#233-what-is-the-event-loop-how-does-it-work-with-the-call-stack-and-task-queue)
  - [234. What is the MutationObserver API?](#234-what-is-the-mutationobserver-api)
  - [235. What is the Node.js event loop and how does it differ from the browser's?](#235-what-is-the-nodejs-event-loop-and-how-does-it-differ-from-the-browsers)
  - [236. What is the Node.js event loop vs the browser event loop?](#236-what-is-the-nodejs-event-loop-vs-the-browser-event-loop)
  - [237. What would you look for when reviewing a junior developer's JavaScript PR?](#237-what-would-you-look-for-when-reviewing-a-junior-developers-javascript-pr)
  - [238. Why is `eval()` dangerous?](#238-why-is-eval-dangerous)
- [DOM, BOM & Events](#dom-bom-events) (21)
  - [239. Explain event bubbling and capturing.](#239-explain-event-bubbling-and-capturing)
  - [240. How do you create, append, and remove DOM elements?](#240-how-do-you-create-append-and-remove-dom-elements)
  - [241. How do you detect and prevent memory leaks in long-running SPAs?](#241-how-do-you-detect-and-prevent-memory-leaks-in-long-running-spas)
  - [242. How do you securely handle user input in JavaScript?](#242-how-do-you-securely-handle-user-input-in-javascript)
  - [243. How do you select and manipulate DOM elements?](#243-how-do-you-select-and-manipulate-dom-elements)
  - [244. How do you select DOM elements?](#244-how-do-you-select-dom-elements)
  - [245. How do you work with cookies in JavaScript?](#245-how-do-you-work-with-cookies-in-javascript)
  - [246. How does `addEventListener` work? How to remove listeners?](#246-how-does-addeventlistener-work-how-to-remove-listeners)
  - [247. What are memory leaks in JavaScript and what causes them?](#247-what-are-memory-leaks-in-javascript-and-what-causes-them)
  - [248. What are side effects?](#248-what-are-side-effects)
  - [249. What are Web Workers?](#249-what-are-web-workers)
  - [250. What is `MutationObserver`?](#250-what-is-mutationobserver)
  - [251. What is event delegation? When would you use it?](#251-what-is-event-delegation-when-would-you-use-it)
  - [252. What is reflow and repaint?](#252-what-is-reflow-and-repaint)
  - [253. What is the `DOMContentLoaded` vs `load` event?](#253-what-is-the-domcontentloaded-vs-load-event)
  - [254. What is the difference between `addEventListener` and `onclick`?](#254-what-is-the-difference-between-addeventlistener-and-onclick)
  - [255. What is the difference between the browser and Node.js environments?](#255-what-is-the-difference-between-the-browser-and-nodejs-environments)
  - [256. What is the difference between virtualization and windowing? Trade-offs.](#256-what-is-the-difference-between-virtualization-and-windowing-trade-offs)
  - [257. What is the DOM?](#257-what-is-the-dom)
  - [258. What is the Observer / Pub-Sub pattern?](#258-what-is-the-observer-pub-sub-pattern)
  - [259. What is XSS (Cross-Site Scripting)?](#259-what-is-xss-cross-site-scripting)
- [Error Handling & Debugging](#error-handling-debugging) (7)
  - [260. How do you implement a CSS animation? How to debug janky animations on mobile?](#260-how-do-you-implement-a-css-animation-how-to-debug-janky-animations-on-mobile)
  - [261. What is `try/catch/finally` and how does `finally` behave?](#261-what-is-trycatchfinally-and-how-does-finally-behave)
  - [262. What is `WeakRef` and `FinalizationRegistry`?](#262-what-is-weakref-and-finalizationregistry)
  - [263. What is a `try/catch/finally` block?](#263-what-is-a-trycatchfinally-block)
  - [264. What is source mapping?](#264-what-is-source-mapping)
  - [265. What is TDD (Test-Driven Development)?](#265-what-is-tdd-test-driven-development)
  - [266. What is the `Error.cause` property (ES2022)?](#266-what-is-the-errorcause-property-es2022)
- [Performance (Debounce, Throttle, Memoization)](#performance-debounce-throttle-memoization) (5)
  - [267. Describe the hardest production bug you fixed.](#267-describe-the-hardest-production-bug-you-fixed)
  - [268. How does garbage collection work in V8?](#268-how-does-garbage-collection-work-in-v8)
  - [269. What is a memory leak and what causes them?](#269-what-is-a-memory-leak-and-what-causes-them)
  - [270. What is garbage collection in JavaScript?](#270-what-is-garbage-collection-in-javascript)
  - [271. What is the JavaScript garbage collection impact of closures?](#271-what-is-the-javascript-garbage-collection-impact-of-closures)
- [Generators, Iterators & Symbols](#generators-iterators-symbols) (8)
  - [272. What are iterators and iterables?](#272-what-are-iterators-and-iterables)
  - [273. What are Proxy and Reflect?](#273-what-are-proxy-and-reflect)
  - [274. What is `Reflect` in JavaScript?](#274-what-is-reflect-in-javascript)
  - [275. What is `Symbol.toPrimitive` used for?](#275-what-is-symboltoprimitive-used-for)
  - [276. What is `Symbol` and why was it introduced?](#276-what-is-symbol-and-why-was-it-introduced)
  - [277. What is a generator function?](#277-what-is-a-generator-function)
  - [278. What is an iterable?](#278-what-is-an-iterable)
  - [279. What is the Proxy object and how is it used?](#279-what-is-the-proxy-object-and-how-is-it-used)
- [Regular Expressions & String Manipulation](#regular-expressions-string-manipulation) (1)
  - [280. How would you implement a publish/subscribe system with topics and wildcards?](#280-how-would-you-implement-a-publishsubscribe-system-with-topics-and-wildcards)
- [Modules, Build Tools & Browser APIs](#modules-build-tools-browser-apis) (10)
  - [281. How do you detect and prevent infinite loops in user-submitted code?](#281-how-do-you-detect-and-prevent-infinite-loops-in-user-submitted-code)
  - [282. What are source maps?](#282-what-are-source-maps)
  - [283. What is a bundler (Webpack, Rollup, Vite)?](#283-what-is-a-bundler-webpack-rollup-vite)
  - [284. What is Jest?](#284-what-is-jest)
  - [285. What is the difference between `dependencies` and `devDependencies`?](#285-what-is-the-difference-between-dependencies-and-devdependencies)
  - [286. What is the Fetch API vs XMLHttpRequest?](#286-what-is-the-fetch-api-vs-xmlhttprequest)
  - [287. What is the JavaScript pipeline operator proposal?](#287-what-is-the-javascript-pipeline-operator-proposal)
  - [288. What is the TC39 proposal process and how do you track upcoming JavaScript features?](#288-what-is-the-tc39-proposal-process-and-how-do-you-track-upcoming-javascript-features)
  - [289. What is the Web Worker API?](#289-what-is-the-web-worker-api)
  - [290. What is transpilation and what does Babel do?](#290-what-is-transpilation-and-what-does-babel-do)
- [General / Miscellaneous JavaScript Concepts](#general-miscellaneous-javascript-concepts) (121)
  - [291. Compare WebSockets, SSE, and WebRTC for real‑time features.](#291-compare-websockets-sse-and-webrtc-for-realtime-features)
  - [292. CPU vs memory bottlenecks – how to identify and fix?](#292-cpu-vs-memory-bottlenecks-how-to-identify-and-fix)
  - [293. Explain the difference between eager and lazy evaluation in JavaScript.](#293-explain-the-difference-between-eager-and-lazy-evaluation-in-javascript)
  - [294. Explain the difference between localStorage, sessionStorage, and cookies.](#294-explain-the-difference-between-localstorage-sessionstorage-and-cookies)
  - [295. Explain the IntersectionObserver API and its use cases (lazy loading, infinite scroll).](#295-explain-the-intersectionobserver-api-and-its-use-cases-lazy-loading-infinite-scroll)
  - [296. How do you avoid layout thrashing?](#296-how-do-you-avoid-layout-thrashing)
  - [297. How do you balance performance vs feature delivery?](#297-how-do-you-balance-performance-vs-feature-delivery)
  - [298. How do you build PWAs with service workers, manifest files, and offline‑first experiences?](#298-how-do-you-build-pwas-with-service-workers-manifest-files-and-offlinefirst-experiences)
  - [299. How do you check if a property exists in an object?](#299-how-do-you-check-if-a-property-exists-in-an-object)
  - [300. How do you check page load behavior using browser developer tools? What metrics do you look at?](#300-how-do-you-check-page-load-behavior-using-browser-developer-tools-what-metrics-do-you-look-at)
  - [301. How do you ensure accessibility beyond ARIA labels?](#301-how-do-you-ensure-accessibility-beyond-aria-labels)
  - [302. How do you ensure code quality with testing? (unit, integration, e2e)](#302-how-do-you-ensure-code-quality-with-testing-unit-integration-e2e)
  - [303. How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)](#303-how-do-you-ensure-secure-handling-of-sensitive-user-data-on-the-client-side-xss-csp-csrf-token-leakage)
  - [304. How do you extract spacing, font sizes, and colors from Figma designs?](#304-how-do-you-extract-spacing-font-sizes-and-colors-from-figma-designs)
  - [305. How do you implement scalable code review workflows (linters, pre‑commit hooks, pair programming)?](#305-how-do-you-implement-scalable-code-review-workflows-linters-precommit-hooks-pair-programming)
  - [306. How do you manage shared libraries and dependencies in a monorepo?](#306-how-do-you-manage-shared-libraries-and-dependencies-in-a-monorepo)
  - [307. How do you mentor juniors through code walkthroughs, tech spikes, and 1:1s?](#307-how-do-you-mentor-juniors-through-code-walkthroughs-tech-spikes-and-11s)
  - [308. How do you optimize images and fonts?](#308-how-do-you-optimize-images-and-fonts)
  - [309. How do you profile and optimize a JavaScript animation that's dropping frames?](#309-how-do-you-profile-and-optimize-a-javascript-animation-thats-dropping-frames)
  - [310. How do you profile JavaScript performance?](#310-how-do-you-profile-javascript-performance)
  - [311. How do you write JavaScript that works in both browser and Node.js?](#311-how-do-you-write-javascript-that-works-in-both-browser-and-nodejs)
  - [312. How does JavaScript handle implicit coercion in arithmetic?](#312-how-does-javascript-handle-implicit-coercion-in-arithmetic)
  - [313. How does JavaScript handle integer overflow?](#313-how-does-javascript-handle-integer-overflow)
  - [314. How does strict mode affect scoping and variable declaration?](#314-how-does-strict-mode-affect-scoping-and-variable-declaration)
  - [315. How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)](#315-how-does-the-browser-rendering-pipeline-work-html-css-layout-paint-composite)
  - [316. How does the history API work for routing?](#316-how-does-the-history-api-work-for-routing)
  - [317. How It Works (Follow the Link)](#317-how-it-works-follow-the-link)
  - [318. How JavaScript keeps track of multiple functions?](#318-how-javascript-keeps-track-of-multiple-functions)
  - [319. How to center an element horizontally? Vertically? Both?](#319-how-to-center-an-element-horizontally-vertically-both)
  - [320. How would you check cumulative layout shifts (CLS) on a page?](#320-how-would-you-check-cumulative-layout-shifts-cls-on-a-page)
  - [321. How would you create a responsive layout with CSS Grid?](#321-how-would-you-create-a-responsive-layout-with-css-grid)
  - [322. How would you improve Web Vitals (LCP, CLS, INP)?](#322-how-would-you-improve-web-vitals-lcp-cls-inp)
  - [323. Is JavaScript compiled or interpreted?](#323-is-javascript-compiled-or-interpreted)
  - [324. Peak Traffic Failure: A critical UI feature fails during peak traffic – how do you mitigate?](#324-peak-traffic-failure-a-critical-ui-feature-fails-during-peak-traffic-how-do-you-mitigate)
  - [325. Style with CSS modules / styled‑components?](#325-style-with-css-modules-styledcomponents)
  - [326. UI Glitches: Users report intermittent UI glitches in different browsers – how do you troubleshoot?](#326-ui-glitches-users-report-intermittent-ui-glitches-in-different-browsers-how-do-you-troubleshoot)
  - [327. What are `AbortController` and `AbortSignal`?](#327-what-are-abortcontroller-and-abortsignal)
  - [328. What are `Map` and `Set`?](#328-what-are-map-and-set)
  - [329. What are container queries?](#329-what-are-container-queries)
  - [330. What are CORS and SOP (Same-Origin Policy)?](#330-what-are-cors-and-sop-same-origin-policy)
  - [331. What are CSS custom properties (variables)?](#331-what-are-css-custom-properties-variables)
  - [332. What are flaky test detection strategies?](#332-what-are-flaky-test-detection-strategies)
  - [333. What are generics in TypeScript?](#333-what-are-generics-in-typescript)
  - [334. What are Node.js streams?](#334-what-are-nodejs-streams)
  - [335. What are preload, prefetch, and priority hints?](#335-what-are-preload-prefetch-and-priority-hints)
  - [336. What are property descriptors?](#336-what-are-property-descriptors)
  - [337. What are semantic tags in HTML? Give examples.](#337-what-are-semantic-tags-in-html-give-examples)
  - [338. What are snapshot tests?](#338-what-are-snapshot-tests)
  - [339. What are symbols used for?](#339-what-are-symbols-used-for)
  - [340. What are the built-in error types?](#340-what-are-the-built-in-error-types)
  - [341. What are the core principles of functional programming?](#341-what-are-the-core-principles-of-functional-programming)
  - [342. What are the different ways to handle forms in JavaScript?](#342-what-are-the-different-ways-to-handle-forms-in-javascript)
  - [343. What are the types of errors in JavaScript?](#343-what-are-the-types-of-errors-in-javascript)
  - [344. What are transducers?](#344-what-are-transducers)
  - [345. What are Web Vitals and why do they matter?](#345-what-are-web-vitals-and-why-do-they-matter)
  - [346. What does `bind` return?](#346-what-does-bind-return)
  - [347. What is `any` vs `unknown` in TypeScript?](#347-what-is-any-vs-unknown-in-typescript)
  - [348. What is `BigInt` and when do you use it?](#348-what-is-bigint-and-when-do-you-use-it)
  - [349. What is `Buffer` in Node.js?](#349-what-is-buffer-in-nodejs)
  - [350. What is `console.table`, `console.group`, and `console.time`?](#350-what-is-consoletable-consolegroup-and-consoletime)
  - [351. What is `event.stopPropagation()` vs `event.preventDefault()`?](#351-what-is-eventstoppropagation-vs-eventpreventdefault)
  - [352. What is `globalThis`?](#352-what-is-globalthis)
  - [353. What is `IntersectionObserver`?](#353-what-is-intersectionobserver)
  - [354. What is `Object.freeze()` vs `Object.seal()`?](#354-what-is-objectfreeze-vs-objectseal)
  - [355. What is `ResizeObserver`?](#355-what-is-resizeobserver)
  - [356. What is a functor?](#356-what-is-a-functor)
  - [357. What is a timing attack and how does it relate to JavaScript?](#357-what-is-a-timing-attack-and-how-does-it-relate-to-javascript)
  - [358. What is a union type vs intersection type?](#358-what-is-a-union-type-vs-intersection-type)
  - [359. What is atomic design methodology?](#359-what-is-atomic-design-methodology)
  - [360. What is chaos engineering for frontend?](#360-what-is-chaos-engineering-for-frontend)
  - [361. What is clickjacking and how do you prevent it?](#361-what-is-clickjacking-and-how-do-you-prevent-it)
  - [362. What is code coverage and what metrics matter?](#362-what-is-code-coverage-and-what-metrics-matter)
  - [363. What is code coverage?](#363-what-is-code-coverage)
  - [364. What is Content Security Policy (CSP)?](#364-what-is-content-security-policy-csp)
  - [365. What is CORS?](#365-what-is-cors)
  - [366. What is CSRF (Cross-Site Request Forgery)?](#366-what-is-csrf-cross-site-request-forgery)
  - [367. What is debouncing?](#367-what-is-debouncing)
  - [368. What is Flexbox? Explain main concepts.](#368-what-is-flexbox-explain-main-concepts)
  - [369. What is function composition vs piping?](#369-what-is-function-composition-vs-piping)
  - [370. What is functional programming?](#370-what-is-functional-programming)
  - [371. What is immutability and how do you achieve it in JavaScript?](#371-what-is-immutability-and-how-do-you-achieve-it-in-javascript)
  - [372. What is JavaScript and where can it run?](#372-what-is-javascript-and-where-can-it-run)
  - [373. What is Jest and what does it provide?](#373-what-is-jest-and-what-does-it-provide)
  - [374. What is method chaining?](#374-what-is-method-chaining)
  - [375. What is npm and what is `package.json`?](#375-what-is-npm-and-what-is-packagejson)
  - [376. What is property descriptor?](#376-what-is-property-descriptor)
  - [377. What is property-based testing?](#377-what-is-property-based-testing)
  - [378. What is strict mode?](#378-what-is-strict-mode)
  - [379. What is the `Atomics` API and when do you need it?](#379-what-is-the-atomics-api-and-when-do-you-need-it)
  - [380. What is the `Error` object?](#380-what-is-the-error-object)
  - [381. What is the Command pattern?](#381-what-is-the-command-pattern)
  - [382. What is the Decorator pattern?](#382-what-is-the-decorator-pattern)
  - [383. What is the difference between `innerHTML`, `textContent`, and `innerText`?](#383-what-is-the-difference-between-innerhtml-textcontent-and-innertext)
  - [384. What is the difference between `interface` and `type`?](#384-what-is-the-difference-between-interface-and-type)
  - [385. What is the difference between `Object.assign()` and spread?](#385-what-is-the-difference-between-objectassign-and-spread)
  - [386. What is the difference between `reduce` and `reduceRight`?](#386-what-is-the-difference-between-reduce-and-reduceright)
  - [387. What is the difference between `require` resolution and ESM resolution in Node.js?](#387-what-is-the-difference-between-require-resolution-and-esm-resolution-in-nodejs)
  - [388. What is the difference between a statement and an expression?](#388-what-is-the-difference-between-a-statement-and-an-expression)
  - [389. What is the difference between CSR, SSR, SSG, and ISR?](#389-what-is-the-difference-between-csr-ssr-ssg-and-isr)
  - [390. What is the difference between debounce and throttle?](#390-what-is-the-difference-between-debounce-and-throttle)
  - [391. What is the difference between named and namespace imports?](#391-what-is-the-difference-between-named-and-namespace-imports)
  - [392. What is the difference between pass-by-value and pass-by-reference?](#392-what-is-the-difference-between-pass-by-value-and-pass-by-reference)
  - [393. What is the History API?](#393-what-is-the-history-api)
  - [394. What is the JavaScript engine and how does it work?](#394-what-is-the-javascript-engine-and-how-does-it-work)
  - [395. What is the purpose of the meta tags?](#395-what-is-the-purpose-of-the-meta-tags)
  - [396. What is the ResizeObserver?](#396-what-is-the-resizeobserver)
  - [397. What is the Strategy pattern?](#397-what-is-the-strategy-pattern)
  - [398. What is the testing pyramid for JavaScript?](#398-what-is-the-testing-pyramid-for-javascript)
  - [399. What is TypeScript and how does it relate to JavaScript?](#399-what-is-typescript-and-how-does-it-relate-to-javascript)
  - [400. What is unit testing?](#400-what-is-unit-testing)
  - [401. What is visual regression testing? How would you implement it?](#401-what-is-visual-regression-testing-how-would-you-implement-it)
  - [402. What is XSS (Cross-Site Scripting) and how do you prevent it?](#402-what-is-xss-cross-site-scripting-and-how-do-you-prevent-it)
  - [403. What is your approach to multi‑tenant frontend applications?](#403-what-is-your-approach-to-multitenant-frontend-applications)
  - [404. What is your framework for identifying, prioritizing, and reducing technical debt?](#404-what-is-your-framework-for-identifying-prioritizing-and-reducing-technical-debt)
  - [405. What is your strategy for fluid responsive design using CSS Grid, Flexbox, and container queries?](#405-what-is-your-strategy-for-fluid-responsive-design-using-css-grid-flexbox-and-container-queries)
  - [406. What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)](#406-what-strategies-would-you-use-to-improve-page-load-time-for-a-global-audience-cdn-lazy-loading-code-splitting-image-optimization)
  - [407. What tools and practices do you use for frontend observability, error tracking, and performance monitoring?](#407-what-tools-and-practices-do-you-use-for-frontend-observability-error-tracking-and-performance-monitoring)
  - [408. What tools do you use for frontend performance analysis? (Lighthouse, WebPageTest, Chrome DevTools)](#408-what-tools-do-you-use-for-frontend-performance-analysis-lighthouse-webpagetest-chrome-devtools)
  - [409. When NOT to use JavaScript: CPU-heavy tasks, long-running blocking logic – use backend or workers.](#409-when-not-to-use-javascript-cpu-heavy-tasks-long-running-blocking-logic-use-backend-or-workers)
  - [410. When NOT to use JavaScript?](#410-when-not-to-use-javascript)
  - [411. When to use?](#411-when-to-use)

---

## Closures, Scope & Hoisting

### 1. Explain closures with a real-world example?

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

[↑ Back to top](#table-of-contents)

### 2. How do arrow functions differ from regular functions regarding `this`?

Arrow functions have no own `this`. They inherit `this` from the enclosing lexical scope at the time of definition. This makes them ideal for callbacks and event handlers where you want `this` to refer to the surrounding context, not the caller.

[↑ Back to top](#table-of-contents)

### 3. How does `this` work in arrow functions?

Arrow functions have no own `this`. They capture `this` from the enclosing lexical scope at the time they are defined. This makes them ideal for callbacks and methods that need to access the outer `this`, eliminating the need for `const self = this` or `.bind(this)`.
Arrow functions do **not** have their own `this` keyword. Instead, they act like a sponge and **absorb the `this` value from the code directly surrounding them** (their parent scope).

Once an arrow function captures its parent's `this`, it is permanently locked in and can never change.

[↑ Back to top](#table-of-contents)

### 4. What is `this` in JavaScript?

`this` refers to the execution context's subject — the object a method belongs to when called. Its value depends on how the function is called: method call → the object; regular function call → `undefined` (strict) or `global`; arrow function → inherited from enclosing scope; `new` → the new instance.

[↑ Back to top](#table-of-contents)

### 5. What is a closure memory leak and how do you avoid it?

If a closure holds a reference to a large object or DOM node and is never released, that memory can't be garbage collected. Avoid by: nullifying references when no longer needed, removing event listeners, avoiding closures that capture large objects unnecessarily, and using `WeakMap`/`WeakRef` for holding references that shouldn't prevent GC.

[↑ Back to top](#table-of-contents)

### 6. What is a closure?

A closure is a function that retains access to its lexical scope even after the outer function has returned. The inner function "closes over" the variables of the outer function. Used for data privacy, partial application, memoization, and module patterns.

**Q19. Give a practical use case for closures.**

A counter factory: `function makeCounter() { let count = 0; return () => ++count; }`. Each call to `makeCounter()` creates an independent counter with private state. The inner function closes over `count` and it cannot be accessed or modified externally.

[↑ Back to top](#table-of-contents)

### 7. What is a common closure bug in loops?

Using `var` in a `for` loop with async callbacks — all callbacks close over the same `var i`. Fix: use `let` (creates a new binding per iteration), or wrap in an IIFE to capture the current value. This is a classic interview trap.

[↑ Back to top](#table-of-contents)

### 8. What is an execution context?

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

[↑ Back to top](#table-of-contents)

### 9. What is hoisting?

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

[↑ Back to top](#table-of-contents)

### 10. What is lexical scope?

The scope of a variable is determined by its position in the source code at write time, not at runtime. Inner functions have access to variables in their outer (enclosing) functions. This is decided when the code is parsed, not when it runs.

[↑ Back to top](#table-of-contents)

### 11. What is scope chain resolution?

When a variable is referenced, JS searches the current scope first, then each outer scope up to global. If not found, a `ReferenceError` is thrown. This chain is established at function definition time (lexical scoping).

[↑ Back to top](#table-of-contents)

### 12. What is scope in JavaScript?

Scope defines the accessibility of variables and functions in different parts of your code. JavaScript has global scope, function scope, and block scope (ES6+). Scope determines where variables can be read or written.

[↑ Back to top](#table-of-contents)

### 13. What is scope? Explain global, function, and block scope.

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

[↑ Back to top](#table-of-contents)

### 14. What is the call stack?

A stack data structure that tracks function calls. When a function is called, its execution context is pushed onto the stack. When it returns, it's popped off. If the stack overflows (infinite recursion), you get a `RangeError: Maximum call stack size exceeded`.

[↑ Back to top](#table-of-contents)

### 15. What is the difference between function declaration and function expression?

Function declaration: `function foo() {}` — hoisted fully, available before its line in code. Function expression: `const foo = function() {}` — not hoisted (the variable is hoisted as `undefined`). Arrow functions are always expressions. Named function expressions are useful for recursion and stack traces.

[↑ Back to top](#table-of-contents)

### 16. What is the difference between function scope and block scope?

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

[↑ Back to top](#table-of-contents)

### 17. What is the difference between implicit and explicit global variables?

A: Explicit globals are declared with `var` in global scope. Implicit globals occur when assigning to an undeclared variable (without `var`, `let`, `const`) – this creates a property on the global object (but is not hoisted). In strict mode, this throws an error.

[↑ Back to top](#table-of-contents)

### 18. What is the scope chain?

When JS looks up a variable, it starts in the current scope and moves outward to enclosing scopes until it reaches the global scope. This chain of scopes is the scope chain. If not found in global scope, a `ReferenceError` is thrown.

[↑ Back to top](#table-of-contents)

### 19. What is the Singleton pattern?

Ensures only one instance of an object exists. In JS, module-level variables are naturally singletons (module is cached after first import). Classic implementation uses a closure that stores the instance and returns it on all subsequent calls.

[↑ Back to top](#table-of-contents)

### 20. What is the Temporal Dead Zone (TDZ)?

The TDZ is the period from entering a block scope until the variable is declared with `let` or `const`. During this time, accessing the variable results in a `ReferenceError`. It prevents accidental use of variables before they are ready.

```javascript
{
// TDZ for a starts here
// console.log(a); // ReferenceError
let a = 10; // TDZ ends here
}

```

[↑ Back to top](#table-of-contents)

### 21. What is variable hoisting?

Declarations (not initializations) are moved to the top of their scope during compilation. `var` declarations are hoisted and initialized to `undefined`. `let` and `const` are hoisted but not initialized — accessing them before declaration throws a ReferenceError (Temporal Dead Zone).

[↑ Back to top](#table-of-contents)

### 22. Why do we get `ReferenceError: Cannot access 'x' before initialization`?

This error occurs when trying to access a `let` or `const` variable before its declaration line is executed, because they are hoisted but not initialized. The time between entering the scope and the actual declaration is the **Temporal Dead Zone (TDZ)**.

[↑ Back to top](#table-of-contents)

### 23. Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)

Closures are a fundamental feature that allows functions to “remember” their lexical scope even when executed outside that scope.

**Use cases**:
- **Data privacy**: Encapsulate variables not exposed globally (e.g., module pattern, factory functions).
- **React Hooks**: `useState` and `useEffect` rely on closures to maintain state across renders.
- **Callbacks**: Preserve context in asynchronous operations.
- **Memoization**: Cache results of expensive functions (e.g., `useMemo`, `_.memoize`).
- **Function factories**: Create functions with pre‑configured arguments.

[↑ Back to top](#table-of-contents)

## `this`, call/apply/bind & Functions

### 24. Arrow Function as a Class Field?

```javascript
class MyClass {
greet = () => {
console.log(this.name);
};
}
```

Arrow functions do not have their own `this`; they inherit `this` from the surrounding scope where the instance was created. Using an arrow function for a class method automatically locks `this` to the instance.

[↑ Back to top](#table-of-contents)

### 25. How do `call`, `apply`, and `bind` work?

`fn.call(thisArg, a, b)` — invokes `fn` with `this` set to `thisArg`, args listed individually. `fn.apply(thisArg, [a, b])` — same but args as an array. `fn.bind(thisArg, a)` — returns a new function permanently bound to `thisArg` with optional pre-filled args (partial application).

[↑ Back to top](#table-of-contents)

### 26. What are Arrow Functions?

Arrow functions (`() => {}`) are a shorter, modern way to write functions in JavaScript.

```javascript
// Regular Function
function greeting(name) {
return "Hello " + name;
}

// Arrow Function
const greeting = (name) => "Hello " + name;

```

[↑ Back to top](#table-of-contents)

### 27. What are the four rules that determine `this`?

1. Default binding: standalone function call → `undefined` (strict) or `global`. 2. Implicit binding: method call `obj.fn()` → `this = obj`. 3. Explicit binding: `fn.call(obj)` / `fn.apply(obj)` / `fn.bind(obj)`. 4. `new` binding: `new Fn()` → `this` is the new instance. Arrow functions ignore all rules and inherit `this` lexically.

[↑ Back to top](#table-of-contents)

### 28. What is a first-class function?

Functions are first-class citizens in JavaScript — they can be assigned to variables, passed as arguments to other functions, returned from functions, stored in arrays/objects, and have properties attached to them. This enables functional programming patterns.

[↑ Back to top](#table-of-contents)

### 29. What is a higher-order function?

A function that takes one or more functions as arguments, returns a function, or both. Examples: `Array.prototype.map`, `filter`, `reduce`, `setTimeout`. They're the backbone of functional programming in JavaScript.

[↑ Back to top](#table-of-contents)

### 30. What is a pure function?

A function that: (1) always returns the same output for the same input, and (2) has no side effects (doesn't modify external state, make network calls, write to DOM, etc.). Pure functions are predictable, testable, and easy to reason about.

[↑ Back to top](#table-of-contents)

### 31. What is an IIFE and why is it used?

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

[↑ Back to top](#table-of-contents)

### 32. What is currying?

Transforming a function that takes multiple arguments into a chain of functions each taking one argument: `f(a, b, c)` becomes `f(a)(b)(c)`. Enables partial application and composition. Libraries like Lodash provide `_.curry`.

[↑ Back to top](#table-of-contents)

### 33. What is function currying?

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

[↑ Back to top](#table-of-contents)

### 34. What is IIFE (Immediately Invoked Function Expression) and why was it used?

`(function() { /* code */ })()` — a function defined and immediately called. Used pre-ES6 to create a local scope and avoid polluting the global namespace. With `let`/`const` and ES modules, IIFEs are rarely needed today.

[↑ Back to top](#table-of-contents)

### 35. What is partial application?

Fixing some arguments of a function, producing a function with fewer arguments. Unlike currying (one argument at a time), partial application fixes any number. `const double = multiply.bind(null, 2)`. Useful for creating specialized functions from general ones.

[↑ Back to top](#table-of-contents)

### 36. What is point-free style?

Writing functions without explicitly mentioning their arguments. `const double = map(x => x * 2)` vs `const double = arr => arr.map(x => x * 2)`. The first is point-free. Achievable through currying and composition. Can improve readability but can also obscure intent if overused.

[↑ Back to top](#table-of-contents)

### 37. Why does `this` lose context in callbacks?

When a method is passed as a callback, it becomes a standalone function reference. The implicit binding (to the original object) is lost. Fix: `fn.bind(this)`, arrow function wrapper, or store `const self = this` (old pattern).

[↑ Back to top](#table-of-contents)

## Prototypes, Classes & OOP

### 38. `__proto__` (The Link on the Product)

* **What it belongs to:** Every single **object instance** — the individual products created by the factory.
* **What it is:** It’s an internal pointer or link that points directly back to the factory's blueprint (`prototype`). If an object is asked to perform a method or find a property it doesn't own directly, it uses `__proto__` to check its blueprint.
* **Analogy:** A digital barcode on your individual iPhone that points back to the master factory blueprint so it knows how to operate.

[↑ Back to top](#table-of-contents)

### 39. `prototype` (The Blueprint on the Factory)

* **What it belongs to:** Only **constructor functions** (or classes) — the factories.
* **What it is:** It’s the blueprint that holds all the shared properties, methods, and tools the factory wants every product to have.
* **Analogy:** The master schematic sitting inside an iPhone factory.

[↑ Back to top](#table-of-contents)

### 40. Explain the concept of specificity in CSS.

Specificity determines which CSS rule is applied when multiple rules target the same element. It is calculated as a 4‑part score: inline styles, IDs, classes/pseudo‑classes, elements/pseudo‑elements.

- Inline styles: 1,0,0,0
- ID: 0,1,0,0
- Class, attribute, pseudo‑class: 0,0,1,0
- Element, pseudo‑element: 0,0,0,1

Higher score wins. If equal, later rule wins (order matters). `!important` overrides all but should be used sparingly.

[↑ Back to top](#table-of-contents)

### 41. How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)

Modern engines (V8, SpiderMonkey) use **Just‑In‑Time (JIT)** compilation, combining interpretation and compilation.

- **Interpretation**: Code starts as bytecode, executed by an interpreter (Ignition in V8). This allows fast startup.
- **JIT compilation**: Hot functions (executed many times) are compiled to machine code by optimizing compilers (TurboFan in V8) for faster execution.
- **Hidden classes**: Instead of dynamic dictionary lookups, objects with the same shape (property names and order) share a hidden class, enabling fast property access via fixed offsets.
- **Inline caching**: When a property is accessed repeatedly, the engine caches the property location based on the hidden class, avoiding repeated lookup overhead.

[↑ Back to top](#table-of-contents)

### 42. How do you implement dark mode across an app?

**Implementation**:
- **CSS custom properties**: Define colors as variables (`--bg`, `--text`). Switch theme by changing a class on the root element (e.g., `.dark`).
- **Theme provider**: Use React context to store theme preference (`light`, `dark`, `system`). Apply the class accordingly.
- **Persistence**: Save preference in `localStorage`.
- **System preference**: Use `prefers-color-scheme` media query to set default.
- **Transition**: Add smooth transitions for color changes.

[↑ Back to top](#table-of-contents)

### 43. How does JavaScript sort arrays by default and what is the gotcha?

`Array.prototype.sort()` converts elements to strings and sorts lexicographically by default. `[10, 9, 2, 1, 100].sort()` gives `[1, 10, 100, 2, 9]`. For numeric sort, always provide a comparator: `arr.sort((a, b) => a - b)` for ascending. `.sort()` mutates the original array.

[↑ Back to top](#table-of-contents)

### 44. How does prototypal inheritance work?

Every JavaScript object has an internal `[[Prototype]]` (accessible via `__proto__` or `Object.getPrototypeOf()`). When accessing a property, JavaScript first looks on the object itself; if not found, it follows the prototype chain until it reaches `null`. This is the basis of inheritance.

```javascript
const parent = { a: 1 };
const child = Object.create(parent);
child.b = 2;
console.log(child.a); // 1 (from parent)
console.log(child.b); // 2
console.log(child.toString); // from Object.prototype

```

[↑ Back to top](#table-of-contents)

### 45. How does the `this` keyword behave in arrow functions, class methods, and event handlers?

- **Arrow functions**: Lexical `this` (inherits from enclosing context). In an event listener, if you use an arrow function, `this` will refer to the enclosing context (e.g., the component, not the DOM element). In a class method, if defined as an arrow property, `this` is bound to the instance.
- **Class methods**: Regular class methods have `this` bound to the instance when called as `obj.method()`. But if passed as a callback, `this` can be lost; solutions: bind, arrow method, or using `.bind` in constructor.
- **Event handlers (DOM)**: In regular function event handlers, `this` refers to the element that received the event. In arrow functions, `this` is lexical (often the window or surrounding context). Use regular function if you need the element.

[↑ Back to top](#table-of-contents)

### 46. How does V8 optimize JavaScript?

JIT (Just-In-Time) compilation: interprets first, then compiles hot code to machine code. Hidden classes: V8 creates internal type shapes for objects — keep object property order consistent. Inline caching: caches property lookup results. Avoid deoptimization triggers: type changes, `arguments`, `eval`, `try/catch` in hot loops.

[↑ Back to top](#table-of-contents)

### 47. What are arrow functions and how do they differ from regular functions?

Arrow functions (`() => {}`) are concise and have no own `this`, `arguments`, `super`, or `new.target`. They inherit `this` lexically from the enclosing scope. They cannot be used as constructors (`new` throws), cannot be used as methods with a dynamic `this`, and don't have a `prototype` property.

[↑ Back to top](#table-of-contents)

### 48. What are ES6 classes and how do they relate to prototypes?

ES6 classes are syntactic sugar over prototypal inheritance. `class Animal { speak() {} }` creates `Animal.prototype.speak`. `class Dog extends Animal {}` sets `Dog.prototype.__proto__ = Animal.prototype`. Under the hood, it's still prototype-based — no classical inheritance actually occurs.

[↑ Back to top](#table-of-contents)

### 49. What are ES6 classes?

Syntactic sugar over prototype-based inheritance. `class Foo extends Bar { constructor() { super(); } method() {} }` compiles to constructor functions and prototype assignments. Classes enforce `new` (cannot be called without it), are not hoisted usably, and run in strict mode.

[↑ Back to top](#table-of-contents)

### 50. What are getters and setters?

`get` and `set` keywords create accessor properties. `get` defines a function called when the property is read; `set` defines a function called when it's assigned. Allow computed or validated properties with a simple property-access syntax. Defined in class body or via `Object.defineProperty`.

[↑ Back to top](#table-of-contents)

### 51. What are private class fields?

Declared with `#` prefix: `#privateField`. Accessible only inside the class body — not on instances, not via `Object.keys()`, not from subclasses. Enforced by the runtime (unlike the convention of `_private`). Also supports private methods and private static fields.

[↑ Back to top](#table-of-contents)

### 52. What are private fields in classes?

A: Using `#` prefix (e.g., `#privateField`). They are truly private, cannot be accessed outside the class, and are not enumerable.

[↑ Back to top](#table-of-contents)

### 53. What are static methods and properties?

Defined on the class itself, not on instances. Called as `ClassName.method()`. Cannot access instance properties via `this` (though `this` refers to the class). Used for utility functions, factory methods, or class-level constants. `static #private` is also supported.

[↑ Back to top](#table-of-contents)

### 54. What are the differences between `Map` and a plain object?

`Map`: any key type, ordered by insertion, `size` property, iterable directly, no prototype pollution. Object: only string/Symbol keys, not reliably ordered (though modern engines maintain insertion order for string keys), must use `hasOwnProperty`. Use `Map` for dictionaries with non-string keys or when key order matters.

[↑ Back to top](#table-of-contents)

### 55. What are the trade-offs between using `class` and factory functions in JavaScript?

Classes: familiar syntax, `instanceof` works, better performance for many instances (shared prototype methods), native `private` fields (ES2022). Factory functions: no `new` required, naturally encapsulated private data via closure, easy mixins, more flexible, no prototype chain confusion. Factory functions are preferred in functional codebases; classes in OOP-heavy codebases.

[↑ Back to top](#table-of-contents)

### 56. What are the ways to create objects in JavaScript?

Object literal `{}`, `new Object()`, `Object.create(proto)`, constructor functions with `new`, ES6 classes with `new`, factory functions returning `{}`. Object literals and classes are the most common. Factory functions offer more flexibility and avoid `new`/`this` complexity.

[↑ Back to top](#table-of-contents)

### 57. What are well-known Symbols?

Built-in Symbols used to customize JS behavior: `Symbol.iterator` (makes object iterable), `Symbol.toPrimitive` (custom type coercion), `Symbol.hasInstance` (customizes `instanceof`), `Symbol.species` (customizes derived instances), `Symbol.toStringTag` (customizes `Object.prototype.toString`).

[↑ Back to top](#table-of-contents)

### 58. What does "first-class functions" mean?

Functions can be assigned to variables, passed as arguments, returned from other functions, and stored in data structures — just like any other value. This enables higher-order functions, callbacks, currying, and functional programming patterns.

[↑ Back to top](#table-of-contents)

### 59. What does `new` do step by step?

1. Creates a new empty object. 2. Sets its `[[Prototype]]` to `Constructor.prototype`. 3. Calls the constructor with `this` set to the new object. 4. If the constructor explicitly returns an object, that object is returned; otherwise, the new object created in step 1 is returned.

[↑ Back to top](#table-of-contents)

### 60. What does `super` do in a class?

In a constructor, `super()` calls the parent class constructor — required in subclass constructors before accessing `this`. In a method, `super.method()` calls the parent class's version of that method.

[↑ Back to top](#table-of-contents)

### 61. What is `hasOwnProperty`?

`obj.hasOwnProperty('key')` returns `true` only if `key` is a direct property of `obj`, not inherited through the prototype chain. Use it when iterating with `for...in` to distinguish own properties from inherited ones. Alternative: `Object.hasOwn(obj, 'key')` (ES2022).

[↑ Back to top](#table-of-contents)

### 62. What is `instanceof` and how does it work?

`obj instanceof Constructor` walks the prototype chain of `obj` looking for `Constructor.prototype`. Returns `true` if found. Can give unexpected results with multiple frames (different global contexts). Prefer duck typing or `Object.getPrototypeOf()` for robust checks.

[↑ Back to top](#table-of-contents)

### 63. What is `Object.create()`?

Creates a new object with the specified object as its prototype. `const child = Object.create(parent)` — `child` inherits from `parent` without needing a constructor. Passing `null` creates an object with no prototype at all (truly empty object, no `toString` etc.).

[↑ Back to top](#table-of-contents)

### 64. What is `Object.getPrototypeOf()`?

Returns the prototype of an object (`[[Prototype]]`). The standard alternative to `__proto__`. Use `Object.setPrototypeOf()` to change an object's prototype (though this is slow and discouraged — use `Object.create()` at construction time instead).

[↑ Back to top](#table-of-contents)

### 65. What is `structuredClone()`?

A built-in global function for deep cloning objects. Handles circular references, `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`. Does NOT clone functions, DOM nodes, or class instances (their prototype). Available in modern browsers and Node.js 17+. Preferred over `JSON.parse(JSON.stringify())`.

[↑ Back to top](#table-of-contents)

### 66. What is `this` in a class?

Inside a class method, `this` refers to the instance of the class. In the constructor, `this` is the newly created object. Static methods have `this` bound to the class itself, not an instance. Arrow function class fields capture `this` at creation time (safe for callbacks).

[↑ Back to top](#table-of-contents)

### 67. What is a class in JavaScript?

A template for creating objects, introduced in ES6. Syntactic sugar over constructor functions and prototypes. Defines a constructor, methods (on the prototype), static members (on the class itself), and private fields. Classes are NOT hoisted the same way as function declarations — they're in the TDZ.

[↑ Back to top](#table-of-contents)

### 68. What is a constructor function?

A regular function called with `new`. The `new` keyword: (1) creates a new object, (2) sets its `[[Prototype]]` to the constructor's `.prototype`, (3) sets `this` to the new object, (4) returns `this` implicitly (unless an object is explicitly returned).

[↑ Back to top](#table-of-contents)

### 69. What is a constructor?

The special `constructor()` method in a class, called automatically when `new ClassName()` is used. It sets up the initial state of the instance via `this`. If not defined, a default empty constructor is used. In derived classes, `super()` must be called before accessing `this`.

[↑ Back to top](#table-of-contents)

### 70. What is a Map vs a plain object?

`Map`: any type as key (including objects), maintains insertion order, has `.size`, iterable directly, better performance for frequent additions/deletions, no prototype pollution risk. Plain object: string/symbol keys only, prototype chain pollution risk, JSON-serializable, simpler syntax. Use `Map` when keys are non-strings or when frequently mutating entries.

[↑ Back to top](#table-of-contents)

### 71. What is a mixin?

A pattern to add methods from one object to another without inheritance. `Object.assign(TargetClass.prototype, mixin)`. Enables sharing behavior across unrelated class hierarchies. No native mixin support in JS — it's a convention using `Object.assign` or object spread.

[↑ Back to top](#table-of-contents)

### 72. What is a prototype in JavaScript?

Every JavaScript object has an internal `[[Prototype]]` link pointing to another object (or null). When a property isn't found on an object, JavaScript walks up the prototype chain looking for it. This is how objects inherit properties and methods.

[↑ Back to top](#table-of-contents)

### 73. What is a pseudo-class? Give examples (:hover, :nth-child, etc.).

A pseudo‑class defines a special state of an element. It is denoted by a single colon `:`.

Examples:
- `:hover` – when the user hovers over an element.
- `:focus` – when an element has focus (e.g., input).
- `:nth-child(an+b)` – selects elements based on their position in a parent.
- `:first-child`, `:last-child`.
- `:not(selector)` – excludes elements.
- `:is()` – matches any of the selectors.
- `:checked` – for radio/checkbox input.

[↑ Back to top](#table-of-contents)

### 74. What is encapsulation and how is it achieved in JS?

Bundling data and methods that operate on that data, restricting direct access to internal state. Achieved via: closures (private state in factory functions), private class fields (`#field`), and conventions like `_private` (not enforced). Forces consumers to use the public API.

[↑ Back to top](#table-of-contents)

### 75. What is inheritance with `extends` and `super`?

`extends` sets up the prototype chain between classes. `super()` in a derived constructor calls the parent's constructor. `super.method()` calls a parent's method. A derived class must call `super()` before accessing `this` in the constructor — otherwise `ReferenceError`.

[↑ Back to top](#table-of-contents)

### 76. What is polymorphism in JavaScript?

Different objects responding to the same interface/method call in different ways. In JS, achieved through method overriding in subclasses. Since JS is duck-typed, any object with the right method can be used polymorphically without explicit inheritance.

[↑ Back to top](#table-of-contents)

### 77. What is prototypal delegation vs classical inheritance?

Classical inheritance copies behavior from parent to child at class definition time. Prototypal delegation links objects at runtime — the child delegates to the parent when a property isn't found. JS uses delegation; classes are a syntactic layer over it.

[↑ Back to top](#table-of-contents)

### 78. What is prototypal inheritance?

Objects inherit directly from other objects through the prototype chain. This differs from classical OOP where classes inherit from classes. In JS, inheritance is delegation — if an object doesn't have a property, it delegates the lookup to its prototype.

[↑ Back to top](#table-of-contents)

### 79. What is prototype pollution?

An attack where `__proto__`, `constructor`, or `prototype` properties are set on user-supplied objects, affecting all objects in the application. Can be used to override methods on `Object.prototype`. Prevention: validate input keys (reject `__proto__`), use `Object.create(null)` for dictionaries, use `Map` instead of plain objects for user data.

[↑ Back to top](#table-of-contents)

### 80. What is the `Array.prototype.at()` method?

A: `at(index)` allows negative indexing to access elements from the end: `arr.at(-1)` returns last element, equivalent to `arr[arr.length-1]`.

[↑ Back to top](#table-of-contents)

### 81. What is the `prototype` property on functions?

Every function has a `.prototype` object. When the function is used as a constructor with `new`, the created instance's `[[Prototype]]` points to this object. Methods placed on `.prototype` are shared among all instances.

[↑ Back to top](#table-of-contents)

### 82. What is the difference between `__proto__` and `prototype`?

`prototype` is a property on constructor functions. When you use `new`, the created object's `[[Prototype]]` is set to the constructor's `prototype`. `__proto__` is the actual prototype link on every object instance (the accessor for `[[Prototype]]`). Use `Object.getPrototypeOf()` instead of `__proto__` in production code.
To understand the difference, think of a constructor function as a **Factory** and the objects it creates as **Products**.

[↑ Back to top](#table-of-contents)

### 83. What is the difference between `for...in` and `for...of`?

`for...in`: iterates over enumerable property KEYS (including inherited ones) of an object. Avoid on arrays (iterates indices as strings + any added prototype properties). `for...of`: iterates over VALUES of any iterable. Cannot be used on plain objects directly (they aren't iterable by default).

[↑ Back to top](#table-of-contents)

### 84. What is the difference between `Object.create(null)` and `{}`?

`{}` creates an object with `Object.prototype` in its prototype chain — it has `toString`, `hasOwnProperty`, `valueOf`, etc. `Object.create(null)` creates a truly empty object with NO prototype — no inherited methods. Useful as a pure hash map (no risk of key collisions with prototype properties like `'toString'` or `'constructor'`).

[↑ Back to top](#table-of-contents)

### 85. What is the difference between classical and prototypal inheritance?

Classical (Java/C++): Classes are blueprints, objects are instances, inheritance copies behavior from parent class to child class. Prototypal (JS): Objects inherit from objects directly through a live prototype link — delegation, not copying. Changes to the prototype affect all inheriting objects.

[↑ Back to top](#table-of-contents)

### 86. What is the difference between composition and inheritance?

Inheritance ("is-a"): extend a base class to reuse behavior — creates tight coupling, fragile base class problem. Composition ("has-a"): combine small, focused objects/functions to build complex behavior — more flexible, loosely coupled. Prefer composition over inheritance for reusability (famous GoF principle).

[↑ Back to top](#table-of-contents)

### 87. What is the difference between static and instance methods?

Instance methods are defined on the class body and accessible on instances. Static methods are defined with `static` and accessible on the class itself (not instances). Used for factory methods, utility helpers, or methods that don't need `this`.

[↑ Back to top](#table-of-contents)

### 88. What is the Factory pattern?

A function that creates and returns objects without using `new` and classes directly. Allows encapsulating creation logic and returning different object types based on input. More flexible than constructors — can return cached instances, different implementations, or augmented objects.

[↑ Back to top](#table-of-contents)

### 89. What is the prototype chain?

The series of linked objects through which JavaScript resolves property lookups. `obj` → `obj.__proto__` → `obj.__proto__.__proto__` → ... → `Object.prototype` → `null`. If the property isn't found anywhere in the chain, the result is `undefined` (for property access) or `TypeError` (for method call).

[↑ Back to top](#table-of-contents)

### 90. When & Where?

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

[↑ Back to top](#table-of-contents)

## ES6+ Features (Destructuring, Spread/Rest, Modules)

### 91. Can you declare a `let` variable in a `switch` block without curly braces?

A: Yes, but each `case` shares the same block scope. Using `let` in multiple cases without a block will cause a redeclaration error. It's safer to wrap cases in `{}`.

[↑ Back to top](#table-of-contents)

### 92. Explain AbortController and request cancellation.

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

[↑ Back to top](#table-of-contents)

### 93. Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.

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

[↑ Back to top](#table-of-contents)

### 94. Explain the JavaScript module resolution algorithm.

For bare specifiers (`import 'lodash'`): check `node_modules`, resolve `package.json exports`/`main`. For relative paths (`./util`): try exact, then `.js`, `.mjs`, `.cjs`, `/index.js`. For browsers: relies on import maps or bundlers (no `node_modules` resolution natively). TypeScript adds path aliases and `baseUrl` on top.

[↑ Back to top](#table-of-contents)

### 95. Give a practical use case for closures.

A counter factory: `function makeCounter() { let count = 0; return () => ++count; }`. Each call to `makeCounter()` creates an independent counter with private state. The inner function closes over `count` and it cannot be accessed or modified externally.

[↑ Back to top](#table-of-contents)

### 96. How do you analyze bundle size and fix tree shaking failures?

**Analysis**:
- Use `webpack-bundle-analyzer`, `rollup-plugin-visualizer`, or Next.js’ built‑in bundle analysis.
- Check for large libraries, duplicated modules, or unexpected code.

**Fixing tree shaking**:
- Ensure your code uses ES modules (`import`/`export`). CommonJS (`require`) often prevents tree shaking.
- Avoid side‑effects in modules; set `sideEffects: false` in `package.json` if safe.
- Use named imports instead of default imports for libraries that support it (e.g., `import { throttle } from 'lodash-es'`).
- Configure bundler to treat modules with side‑effects properly.
- Remove unused exports (dead code) by ensuring bundler’s mode is `production`.

[↑ Back to top](#table-of-contents)

### 97. How do you make a JavaScript library tree-shakeable?

Use named exports (not a single default export object). Avoid side effects at module load time. Mark the package as `"sideEffects": false` in `package.json` (or list files that do have side effects). Use ES module format. Avoid importing one large utility that pulls in everything — provide granular per-function imports.

[↑ Back to top](#table-of-contents)

### 98. How to create a truly immutable object?

A:
- `Object.freeze(obj)` – prevents adding/removing properties and makes all existing properties non-writable (shallow).
- For deep freeze, recursively freeze.
- Using `const` only prevents reassignment, not mutation.

[↑ Back to top](#table-of-contents)

### 99. If we have `var`, `let`, `const`, why do we need state variables?

Regular JavaScript variables do not trigger re‑renders when they change. State variables (`useState`) are designed to:
- Preserve values across renders.
- Trigger a re‑render when updated (via the setter function).
- Work within React’s reconciliation cycle. Without them, changes to variables would not be reflected in the UI.

[↑ Back to top](#table-of-contents)

### 100. Implicit Binding (The Object Before the Dot)

When a function is called as a method inside an object, `this` refers to the **object directly to the left of the dot**.

```javascript
const user = {
name: "Alice",
greet() { console.log(this.name); }
};

user.greet(); // 📍 Prints: "Alice" (because 'user' is left of the dot)

```

[↑ Back to top](#table-of-contents)

### 101. What are computed property names?

ES6 syntax to use an expression as a property key: `const key = 'name'; const obj = { [key]: 'Alice' }` — creates `{name: 'Alice'}`. Useful for dynamic property names, especially in reducers or when building objects from variables.

[↑ Back to top](#table-of-contents)

### 102. What are default parameters?

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

[↑ Back to top](#table-of-contents)

### 103. What are ES Modules (`import`/`export`)?

The official standard module system. Static `import`/`export` declarations are analyzed at parse time (enables tree shaking). Modules have their own scope, are strict by default, run once (cached), and support cyclic dependencies. Works in modern browsers (`<script type="module">`) and Node.js (`.mjs` or `"type":"module"` in package.json).

[↑ Back to top](#table-of-contents)

### 104. What are ES Modules (ESM)?

The standard JS module system: `import`/`export`. Static — imports are resolved at parse time, enabling tree shaking. Asynchronous loading in browsers. `"type": "module"` in `package.json` enables ESM in Node.js. `.mjs` extension also works.

[↑ Back to top](#table-of-contents)

### 105. What are mocks, stubs, and spies?

**Mock**: replaces an entire module or function with a fake implementation. **Stub**: provides canned responses for specific calls (controls what a dependency returns). **Spy**: wraps real implementation to record calls (what args, how many times). Jest's `jest.fn()` and `jest.spyOn()` cover all these.

[↑ Back to top](#table-of-contents)

### 106. What are named exports vs default exports in ES modules?

Named: `export const foo = 1` — imported as `import {foo} from './mod'`. Default: `export default function(){}` — imported as `import anything from './mod'`. A module can have many named exports but only one default. Named exports are generally preferred for tree-shaking and explicitness.

[↑ Back to top](#table-of-contents)

### 107. What are package.json `exports` and `main` fields?

`main`: entry point for CommonJS/legacy resolvers. `exports`: modern conditional exports — specify different entry points for ESM, CJS, browser, Node, types. `exports` takes precedence over `main` in modern tooling. Enables dual CJS/ESM packages.

[↑ Back to top](#table-of-contents)

### 108. What are rest parameters and the spread operator?

Rest (`...args`): collects remaining arguments into an array inside a function definition. Spread (`...arr`): expands an iterable into individual elements at a call site or in an array/object literal. Same syntax, opposite directions.

[↑ Back to top](#table-of-contents)

### 109. What are tagged template literals?

A function called with a template literal. The function receives the string parts as an array and the interpolated values as separate arguments. Used by libraries like styled-components, GraphQL (`gql\`...\``), and SQL query builders to process template strings safely.

[↑ Back to top](#table-of-contents)

### 110. What are the differences between `var`, `let`, and `const`?

`var`: function-scoped, hoisted, can be re-declared, no block scoping. `let`: block-scoped, not hoisted usably (TDZ), cannot be re-declared. `const`: block-scoped, must be initialized, cannot be reassigned (though object contents can be mutated). Prefer `const` by default, `let` when reassignment is needed, avoid `var`.

[↑ Back to top](#table-of-contents)

### 111. What are Worker Threads in Node.js?

`worker_threads` module runs JS in parallel threads within the same process. Unlike `cluster` (separate processes), workers share memory via `SharedArrayBuffer`. Used for CPU-intensive tasks — image resizing, compression, parsing.

[↑ Back to top](#table-of-contents)

### 112. What is a recursive function and what is tail call optimization?

A function that calls itself. Each call adds a frame to the call stack. Tail call optimization (TCO) — when the recursive call is the last operation — allows the engine to reuse the current stack frame. TCO is specified in ES6 but only Safari implements it reliably.

[↑ Back to top](#table-of-contents)

### 113. What is a type assertion?

Telling TypeScript "trust me, I know the type of this value." `const el = document.getElementById('btn') as HTMLButtonElement`. Doesn't do runtime conversion — purely compile-time. Use when you have more context than the type system. Can use `as Type` or `<Type>value` (JSX incompatible).

[↑ Back to top](#table-of-contents)

### 114. What is CommonJS (`require`/`module.exports`)?

Node.js's original module system. `const x = require('./x')` — synchronous, evaluated at runtime. `module.exports = value` to export. Modules are cached after the first load. Can export a function, object, or primitive. Cannot be statically analyzed (limits tree shaking).

[↑ Back to top](#table-of-contents)

### 115. What is destructuring?

Extracting values from arrays or objects into distinct variables. `const {a, b} = obj`, `const [x, y] = arr`. Supports renaming (`{a: localName}`), defaults (`{a = 0}`), nested destructuring, and rest (`{a, ...rest}`). Works in function parameters, variable declarations, and assignments.

[↑ Back to top](#table-of-contents)

### 116. What is immutability and why does it matter?

Data that cannot be changed after creation. Instead of mutating, create new data. Benefits: predictability, easier debugging, safe sharing between functions, enables undo/redo, time-travel debugging. In JS: use `const` for bindings, spread for objects/arrays, `Object.freeze()` for true immutability, or libraries like Immer.

[↑ Back to top](#table-of-contents)

### 117. What is memoization?

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

[↑ Back to top](#table-of-contents)

### 118. What is module federation?

A Webpack 5 feature (and now broader concept) allowing multiple independently deployed applications to share code at runtime. Module A can dynamically load components from Module B's deployed bundle. Used in micro-frontend architectures.

[↑ Back to top](#table-of-contents)

### 119. What is nullish coalescing (`??`)?

`value ?? 'default'` — returns the right side only when the left side is `null` or `undefined`. Unlike `||`, it does not short-circuit on `0`, `''`, or `false`. Use `??` when `0` and `''` are valid values.

[↑ Back to top](#table-of-contents)

### 120. What is object destructuring?

`const {name, age: years = 0} = obj` — extracts properties by name into variables, with optional renaming and defaults. Nested: `const {address: {city}} = obj`. In function params: `function fn({name, age}) {}`.

[↑ Back to top](#table-of-contents)

### 121. What is object shorthand property syntax?

`const name = 'Alice'; const obj = {name}` is shorthand for `{name: name}`. Method shorthand: `{greet() {}}` instead of `{greet: function() {}}`. Computed property names: `{[dynamicKey]: value}`.

[↑ Back to top](#table-of-contents)

### 122. What is optional chaining (`?.`)?

Safely accesses deeply nested properties without throwing if an intermediate value is `null`/`undefined`. `obj?.a?.b?.c` returns `undefined` instead of throwing. Works for method calls (`obj.fn?.()`) and array access (`arr?.[0]`). Short-circuits the rest of the expression when it encounters `null`/`undefined`.

[↑ Back to top](#table-of-contents)

### 123. What is tail call optimization?

A JS engine optimization where if a function's last action is calling another function (`return fn()`), the current stack frame can be replaced instead of adding a new one — enabling O(1) stack space for tail-recursive functions. Specified in ES6 strict mode, but only Safari actually implements it. In practice, use loops or trampolining for deep recursion.

[↑ Back to top](#table-of-contents)

### 124. What is the `cluster` module?

Allows spawning multiple Node.js processes sharing the same port. Master process forks workers (one per CPU core). Distributes incoming connections across workers. Used to take advantage of multi-core CPUs since Node.js is single-threaded.

[↑ Back to top](#table-of-contents)

### 125. What is the `for...of` loop?

Iterates over values of any iterable (arrays, strings, Maps, Sets, generators). `for (const item of arr) {}`. Supports `break`, `continue`, `return`. Unlike `forEach`, works with generators and custom iterables. Unlike `for...in`, iterates values not property names.

[↑ Back to top](#table-of-contents)

### 126. What is the `void` operator?

`void expression` evaluates the expression and returns `undefined`. Used in `<a href="void(0)">` to prevent navigation. Also used in arrow functions to explicitly return `undefined` and signal no return value is intended: `const handler = () => void doSomething()`. Rarely needed in modern code.

[↑ Back to top](#table-of-contents)

### 127. What is the AbortController used for?

`AbortController` allows cancelling asynchronous operations like fetch requests, timers, or any operation that accepts an `AbortSignal`. It provides a way to clean up pending requests on component unmount or user action.

Example:

```javascript
const controller = new AbortController();
fetch(url, { signal: controller.signal })
.then(res => res.json())
.catch(err => {
if (err.name === 'AbortError') console.log('Fetch aborted');
});
// later
controller.abort();
```

It can also be used with `addEventListener` to remove listeners via `signal`.

[↑ Back to top](#table-of-contents)

### 128. What is the CommonJS module system?

Node.js's original module system: `require()` to import, `module.exports` or `exports.foo` to export. Synchronous, evaluated at load time. Still widely used in Node.js server code and older packages. Being gradually replaced by ESM.

[↑ Back to top](#table-of-contents)

### 129. What is the difference between `jest.fn()`, `jest.spyOn()`, and `jest.mock()`?

`jest.fn()`: creates a standalone mock function. `jest.spyOn(obj, 'method')`: replaces `obj.method` with a spy, preserving the original implementation by default. `jest.mock('./module')`: replaces an entire module with auto-mocked versions. Use `mockImplementation` or `mockReturnValue` to control behavior.

[↑ Back to top](#table-of-contents)

### 130. What is the difference between `let` and `const` in terms of object mutation?

A: `const` prevents reassignment of the variable, but if the variable holds an object, the object's properties can still be mutated. To freeze an object, use `Object.freeze()`.

[↑ Back to top](#table-of-contents)

### 131. What is the difference between `var`, `let`, and `const`?

`var`: function-scoped, hoisted and initialized to `undefined`, can be redeclared. `let`: block-scoped, hoisted but not initialized (TDZ), cannot be redeclared. `const`: block-scoped, must be initialized at declaration, cannot be reassigned (but object contents can be mutated). Always prefer `const` by default, `let` when reassignment is needed, avoid `var`.

[↑ Back to top](#table-of-contents)

### 132. What is the difference between CommonJS and ES Modules?

CJS: synchronous `require`, `module.exports`, dynamic (can be conditional), not statically analyzable, default in Node.js. ESM: asynchronous, static `import`/`export`, tree-shakeable, `this` is `undefined` at module level, supported in browsers natively. ESM is the future standard; Node.js supports both.

[↑ Back to top](#table-of-contents)

### 133. What is the difference between default and named exports?

Named: `export const foo = 1` — imported as `import { foo } from './m'`. Can have many per file. Import name must match (or be aliased with `as`). Default: `export default value` — imported as `import anything from './m'`. Only one per file. Named exports are preferred for tree-shaking and refactoring safety.

[↑ Back to top](#table-of-contents)

### 134. What is the difference between JavaScript and ECMAScript?

ECMAScript (ES) is the specification/standard. JavaScript is the most popular implementation of that standard. TC39 (a committee) maintains the ECMAScript spec and releases yearly updates (ES2015/ES6, ES2016… ES2024). Browsers and Node.js implement these features over time.

[↑ Back to top](#table-of-contents)

### 135. What is the difference between unit, integration, and E2E tests?

**Unit**: tests one function/module in isolation — fast, deterministic. **Integration**: tests how multiple units work together — may use real database/service or mocks. **E2E**: tests the full application in a real browser — slowest, most realistic (Playwright, Cypress). Balance: many unit, some integration, few E2E.

[↑ Back to top](#table-of-contents)

### 136. What is the ECMAScript specification?

ECMAScript (ES) is the standardized specification that JavaScript implements, maintained by TC39. Versions like ES5, ES6/ES2015, ES2020, ES2022 added major features. New proposals move through a 5-stage process (Stage 0–4) before being incorporated into the spec.

[↑ Back to top](#table-of-contents)

### 137. What is the Module pattern?

Uses an IIFE or ES modules to encapsulate private state and expose a public API. Prevents global namespace pollution. The classic pre-module pattern:

```javascript
const counter = (function() {
let count = 0;
return { increment: () => ++count, getCount: () => count };
})();
```

[↑ Back to top](#table-of-contents)

### 138. What is the module scope?

In ES modules (`.mjs` or `<script type="module">`), the top-level is module scope — not global. Variables declared at the top are not on `window`. Modules also enforce strict mode by default.

[↑ Back to top](#table-of-contents)

### 139. What is the nullish coalescing operator (`??`)?

Returns the right-hand value when the left-hand value is `null` or `undefined` (not just falsy). `const val = input ?? 'default'` — if `input` is `0` or `''`, those are used (unlike `||` which would fall back to 'default'). Use `??` when `0` or empty string are valid values.

[↑ Back to top](#table-of-contents)

### 140. What is the rest parameter (`...args`)?

Collects all remaining arguments into an array: `function sum(...nums) { return nums.reduce((a,b) => a+b, 0); }`. Must be the last parameter. Unlike `arguments`, rest parameters are real arrays with all array methods.

[↑ Back to top](#table-of-contents)

### 141. What is the Revealing Module pattern?

A variation of the Module pattern where all functions/variables are defined privately, and an object literal is returned that reveals only the public members by name. Makes clear what's public and what's private.

[↑ Back to top](#table-of-contents)

### 142. What is the spread operator for objects?

`{...obj1, ...obj2}` creates a shallow merge. Later keys override earlier ones. Used to create modified copies without mutation: `const updated = {...user, age: 31}`. Only copies own enumerable properties.

[↑ Back to top](#table-of-contents)

### 143. What is throttling?

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

[↑ Back to top](#table-of-contents)

### 144. What is tree shaking and how does it relate to ES modules?

Tree shaking removes unused exports from the final bundle using static analysis. Only works with ES module syntax (`import`/`export`) — not CommonJS (`require`). Write named exports, avoid side-effectful imports, mark packages as `"sideEffects": false` in `package.json`.

[↑ Back to top](#table-of-contents)

### 145. What is tree shaking?

Dead code elimination based on static analysis of ES module imports/exports. Bundlers (Rollup, Webpack, Vite) detect exported code that's never imported and exclude it from the bundle. Requires: ES modules (not CJS), no side-effectful imports, correct `sideEffects` field in package.json.

[↑ Back to top](#table-of-contents)

## Arrays, Objects & Data Structures

### 146. Explain the difference between `Array.from()` and spread on a NodeList.

Both convert array-like/iterables to arrays. `Array.from(nodeList)` works on any array-like (has `length` and indexed items — even without `Symbol.iterator`). Spread `[...nodeList]` requires the object to be iterable (`Symbol.iterator`). NodeLists are iterable in modern browsers, so both work there. `Array.from` also accepts a map function as second argument.

[↑ Back to top](#table-of-contents)

### 147. How do you deep clone an object?

Best method (modern): `structuredClone(obj)` — handles circular references, dates, maps, sets. Legacy: `JSON.parse(JSON.stringify(obj))` — simple but loses functions, `undefined`, `Date` objects become strings, can't handle circular references. For complex needs: Lodash `_.cloneDeep()`.

[↑ Back to top](#table-of-contents)

### 148. How do you flatten an array?

A: `flat()` (ES2019): `[1,[2,3]].flat()` → `[1,2,3]`. For deeper, pass depth or `Infinity`. Polyfill via `reduce` and recursion.

[↑ Back to top](#table-of-contents)

### 149. How do you remove duplicates from an array?

`[...new Set(arr)]` — most concise for primitives. `Array.from(new Set(arr))` — equivalent. For objects (by property): `arr.filter((v, i, a) => a.findIndex(t => t.id === v.id) === i)`. Set works by value equality for primitives; for objects, it checks reference equality.

[↑ Back to top](#table-of-contents)

### 150. How do you safely handle `JSON.parse` with unknown input?

Always wrap in `try/catch`. Validate the parsed structure — don't assume it matches your expected schema. Use a validation library (Zod, Yup) to parse and validate in one step: `const result = MySchema.safeParse(JSON.parse(input))`. Never trust server or external data structure without validation.

[↑ Back to top](#table-of-contents)

### 151. How does `reduce` work?

`array.reduce((accumulator, currentValue, index, array) => newAccumulator, initialValue)`. Iterates the array, passing the accumulated result to each callback. Can replace `map`, `filter`, and many other operations. Always provide an initial value to avoid bugs on empty arrays.

[↑ Back to top](#table-of-contents)

### 152. How does `structuredClone` differ from `JSON.parse(JSON.stringify())`?

`structuredClone`: handles `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`, circular references, `undefined`, `Infinity`, `NaN`. Does not clone functions or class instances (throws). `JSON.parse(JSON.stringify())`: drops `undefined`, functions, Symbols; converts `Date` to string; throws on circular refs; converts `Infinity`/`NaN` to `null`. Use `structuredClone` for general-purpose deep cloning.

[↑ Back to top](#table-of-contents)

### 153. How to avoid?

- **`React.memo`** – wrap functional components to prevent re‑renders when props (shallow‑compared) don’t change.
- **`useMemo`** – memoize expensive computations or object/array values.
- **`useCallback`** – memoize functions to avoid new references.
- **Colocate state** – move state down to the component that needs it, rather than lifting it unnecessarily high.
- **Splitting context** – break large contexts into smaller ones so consumers only subscribe to what they use.
- **`useReducer` instead of multiple `useState`** – can help group related state updates and reduce re‑renders if implemented with care.

[↑ Back to top](#table-of-contents)

### 154. How to check if a variable is an array?

- `Array.isArray(arr)` – preferred, works across realms.
- `arr instanceof Array` – may fail if array comes from another iframe.
- `Object.prototype.toString.call(arr) === '[object Array]'` – reliable fallback.

[↑ Back to top](#table-of-contents)

### 155. How to convert an array-like object to an array?

A: `Array.from(arrayLike)`, `[...arrayLike]`, or `Array.prototype.slice.call(arrayLike)`.

[↑ Back to top](#table-of-contents)

### 156. What are the basic types in TypeScript?

Primitive: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`. Object: `object`, `array` (`number[]` or `Array<number>`), tuple (`[string, number]`), `enum`. Special: `any` (opts out of checking), `unknown` (safe any), `never` (never returns), `void` (no return value).

[↑ Back to top](#table-of-contents)

### 157. What are the most important array methods?

Mutation: `push`, `pop`, `shift`, `unshift`, `splice`, `sort`, `reverse`. Non-mutating: `map`, `filter`, `reduce`, `find`, `findIndex`, `some`, `every`, `includes`, `indexOf`, `slice`, `flat`, `flatMap`, `concat`. Creation: `Array.from()`, `Array.of()`, `Array.isArray()`. Prefer non-mutating methods for predictability.

[↑ Back to top](#table-of-contents)

### 158. What are the performance implications of `map`, `filter`, `reduce` chains?

A: Each method creates a new array and loops through the entire array. For large arrays, consider using a single `reduce` to avoid multiple passes.

[↑ Back to top](#table-of-contents)

### 159. What does `flat()` and `flatMap()` do?

`arr.flat(depth)`: flattens nested arrays up to specified depth (default 1). `arr.flat(Infinity)` fully flattens. `arr.flatMap(fn)`: equivalent to `arr.map(fn).flat(1)` but more efficient. Useful for mapping to arrays and then flattening one level.

[↑ Back to top](#table-of-contents)

### 160. What is `Object.keys()`, `Object.values()`, `Object.entries()`?

`Object.keys(obj)`: returns array of own enumerable property names. `Object.values(obj)`: returns array of own enumerable property values. `Object.entries(obj)`: returns array of `[key, value]` pairs. All iterate only over own enumerable string-keyed properties (not prototype, not symbols).

[↑ Back to top](#table-of-contents)

### 161. What is a WeakMap and when would you use it?

"A WeakMap is a collection of key-value pairs where keys must be objects, and those keys are held weakly."

The "Why" (The Killer Feature)
"Because the keys are held weakly, a WeakMap prevents memory leaks. If an object used as a key is deleted anywhere else in your application, JavaScript automatically wipes out its entry from the WeakMap and frees up that memory."

[↑ Back to top](#table-of-contents)

### 162. What is a WeakSet?

"A WeakSet is a collection of unique objects that are held weakly."

The "Why" (The Killer Feature)
"Because it holds objects weakly, it prevents memory leaks. If an object stored inside a WeakSet has no other active references left in your application, JavaScript's garbage collector will automatically wipe it out of the WeakSet and free up the memory."

[↑ Back to top](#table-of-contents)

### 163. What is array and object destructuring with defaults?

```javascript
const { a = 10, b: renamed = 20 } = { a: 5 };
// a = 5, renamed = 20

const [x = 1, y = 2] = [10];
// x = 10, y = 2
```

Defaults apply only when the value is `undefined`, not `null`.

[↑ Back to top](#table-of-contents)

### 164. What is explicit binding with `call`, `apply`, and `bind`?

All three methods allow you to explicitly set `this`. `call(thisArg, arg1, arg2)` calls immediately with individual args. `apply(thisArg, [args])` calls immediately with args as array. `bind(thisArg, ...args)` returns a new function with `this` permanently bound — doesn't call immediately.

[↑ Back to top](#table-of-contents)

### 165. What is the `arguments` object?

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

[↑ Back to top](#table-of-contents)

### 166. What is the difference between `forEach` and `map`?

`forEach` executes a side effect for each element, returns `undefined`. `map` transforms each element and returns a new array. Don't use `map` when you don't need the returned array (use `forEach` for side effects). Can't break out of either — use `for...of` or `some`/`every` for early exit.

[↑ Back to top](#table-of-contents)

### 167. What is the difference between `function` and `=>` in terms of `arguments` object?

A: Regular functions have an `arguments` array-like object containing passed arguments. Arrow functions do not have their own `arguments`; they inherit from the parent scope.

[↑ Back to top](#table-of-contents)

### 168. What is the difference between `map`, `filter`, and `reduce`?

`map(fn)`: transforms each element, returns new array of same length. `filter(fn)`: returns new array with only elements where `fn` returns truthy. `reduce(fn, initial)`: accumulates all elements into a single value (sum, object, nested array, etc.). All are non-mutating.

[↑ Back to top](#table-of-contents)

### 169. What is the difference between `Object.keys`, `Object.values`, `Object.entries`, and `Object.fromEntries`?

`Object.keys(obj)`: own enumerable string key names. `Object.values(obj)`: own enumerable values. `Object.entries(obj)`: own enumerable `[key, value]` pairs. `Object.fromEntries(iterable)`: creates an object from key-value pairs (inverse of `entries`). Together, these enable functional transformations: `Object.fromEntries(Object.entries(obj).map(([k, v]) => [k, transform(v)]))`.

[↑ Back to top](#table-of-contents)

### 170. What is the difference between shallow copy and deep copy?

Shallow copy: copies the top-level properties. Nested objects/arrays are still referenced (not duplicated). Methods: spread `{...obj}`, `Object.assign({}, obj)`, `arr.slice()`. Deep copy: copies all levels recursively — changes in copy don't affect original. Methods: `structuredClone()`, `JSON.parse(JSON.stringify(obj))` (with limitations), or libraries like Lodash `_.cloneDeep`.

[↑ Back to top](#table-of-contents)

## Type Coercion, Equality & Data Types

### 171. What are Symbols?

A unique, immutable primitive value. `Symbol('desc')` creates a Symbol; no two Symbols are equal. Used as unique property keys (avoid naming collisions), to implement well-known behaviors (`Symbol.iterator`, `Symbol.toPrimitive`), and for truly private-ish object properties. Not enumerable in `for...in` or `Object.keys()`.

[↑ Back to top](#table-of-contents)

### 172. What are the primitive data types in JavaScript?

There are 7 primitives: `string`, `number`, `boolean`, `undefined`, `null`, `symbol` (ES6), and `bigint` (ES2020). Everything else is an `object` (arrays, functions, dates, etc. are objects). Primitives are immutable and stored by value; objects are stored by reference.

[↑ Back to top](#table-of-contents)

### 173. What are the tricky parts of `==` type coercion rules?

Key rules: if one side is a number, convert the other to number. If one side is a boolean, convert boolean to number first. Objects are converted to primitives via `valueOf()` then `toString()`. `null == undefined` is `true`, but `null == 0` is `false`. `NaN == NaN` is `false`. These inconsistencies are why `===` is always preferred.

[↑ Back to top](#table-of-contents)

### 174. What are truthy and falsy values?

Falsy: `false`, `0`, `-0`, `0n`, `''` (empty string), `null`, `undefined`, `NaN`. Everything else is truthy, including `'0'`, `[]`, `{}`, and `'false'`. Used in boolean contexts like `if` conditions and `&&`/`||` operators.

[↑ Back to top](#table-of-contents)

### 175. What is `NaN` and how do you check for it?

`NaN` (Not-a-Number) is the result of invalid numeric operations (`'abc' * 2`, `0/0`). Its type is `'number'`. Weirdly, `NaN !== NaN`. Check with `Number.isNaN(value)` (strict – only true for actual NaN) or `isNaN(value)` (coerces first, less reliable).

[↑ Back to top](#table-of-contents)

### 176. What is `typeof` and what are its quirks?

`typeof` returns a string indicating the type. Notable quirks: `typeof null === 'object'` (historical bug), `typeof function(){}  === 'function'` (special case), `typeof undeclaredVar === 'undefined'` (safe without ReferenceError).

[↑ Back to top](#table-of-contents)

### 177. What is the difference between `==` comparisons and `Object.is`?

`Object.is(a, b)` is like `===` but handles two edge cases: `Object.is(NaN, NaN) === true` and `Object.is(+0, -0) === false`. Used internally by React and Redux for comparison logic. Regular `===` treats `NaN !== NaN` and `+0 === -0`.

[↑ Back to top](#table-of-contents)

### 178. What is the difference between `null` and `undefined`?

`undefined`: a variable has been declared but not assigned a value; also the return value of functions that don't return anything. `null`: an intentional absence of value, explicitly assigned by a developer. `typeof undefined === 'undefined'`; `typeof null === 'object'` (a historic bug in JS).

[↑ Back to top](#table-of-contents)

### 179. What is the logical assignment operators (`&&=`, `||=`, `??=`)?

Short-circuit assignment operators. `a &&= b` — assign `b` to `a` only if `a` is truthy. `a ||= b` — assign `b` to `a` only if `a` is falsy. `a ??= b` — assign `b` to `a` only if `a` is `null`/`undefined`. More concise than full if-statements for conditional assignment.

[↑ Back to top](#table-of-contents)

### 180. What is type coercion?

JavaScript automatically converts types when operating on mixed-type values. Example: `'5' - 2 = 3` (string coerced to number), `'5' + 2 = '52'` (number coerced to string for `+`). Implicit coercion can cause bugs; use explicit conversion (`Number()`, `String()`, `Boolean()`) for clarity.

[↑ Back to top](#table-of-contents)

### 181. What is type narrowing?

Reducing a broad type to a more specific type within a code branch using type guards. Methods: `typeof` checks, `instanceof`, `in` operator, truthiness checks, equality checks, discriminated unions, user-defined type predicates (`fn(x): x is Type`). TypeScript understands these patterns and narrows the type automatically.

[↑ Back to top](#table-of-contents)

## Asynchronous JavaScript (Promises, async/await, Event Loop)

### 182. Callback functions – what are they? Callback hell.

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

[↑ Back to top](#table-of-contents)

### 183. Event loop: Why does a Promise run before setTimeout? (Microtasks vs macrotasks)

Promises’ callbacks (`.then`, `.catch`) are **microtasks**, while `setTimeout` callbacks are **macrotasks**. After each macrotask (including the initial script execution), the event loop drains the entire microtask queue before taking the next macrotask. Therefore, a settled promise’s callback always runs before any scheduled `setTimeout`.

[↑ Back to top](#table-of-contents)

### 184. Explain how JavaScript handles concurrency with the event loop, Workers, and SharedArrayBuffer.

The event loop handles concurrency at the application level — non-blocking I/O via callbacks, interleaved on the single main thread. Web Workers provide true parallelism — separate threads with no shared memory (communicate via `postMessage`). `SharedArrayBuffer` allows workers to share memory for performance-critical scenarios, requiring `Atomics` for synchronization. These three layers allow JavaScript to scale from simple async to multi-threaded parallelism.

[↑ Back to top](#table-of-contents)

### 185. Explain how you'd port a callback-based API to use Promises.

`function promisify(fn) { return (...args) => new Promise((resolve, reject) => { fn(...args, (err, result) => err ? reject(err) : resolve(result)); }); }`. Node.js provides `util.promisify` for Node-style (error-first) callbacks. For event-based APIs: wrap in a Promise that resolves on the success event and rejects on the error event.

[↑ Back to top](#table-of-contents)

### 186. Explain the JavaScript event loop in detail. Microtasks vs macrotasks.

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

[↑ Back to top](#table-of-contents)

### 187. How do you run async operations in parallel vs sequentially?

Sequential: `await a(); await b()` — total time = a + b. Parallel: `const [r1, r2] = await Promise.all([a(), b()])` — total time = max(a, b). A common mistake is `await` inside `for...of` when operations are independent — use `Promise.all` instead.

[↑ Back to top](#table-of-contents)

### 188. How do you test asynchronous code in Jest?

Return a Promise from the test, or use `async/await`. Use `done` callback for callback-style APIs. Jest's fake timers (`jest.useFakeTimers()`) control `setTimeout`/`setInterval`. Mock `fetch` or use MSW for network calls. `await waitFor(() => expect(...))` for async DOM updates.

[↑ Back to top](#table-of-contents)

### 189. How does async flow work in Redux Toolkit?

1. Define a thunk using `createAsyncThunk`.
2. Inside the payload creator, perform async work (e.g., fetch).
3. Dispatch the thunk from a component.
4. The thunk dispatches the `pending` action immediately.
5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.
6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data).

[↑ Back to top](#table-of-contents)

### 190. How does Promise chaining work?

Each `.then()` returns a new Promise. If the handler returns a value, the next `.then` receives it. If it returns a Promise, the next `.then` waits for it to settle. This flattening eliminates nested callbacks. Errors propagate down the chain to the nearest `.catch`.

[↑ Back to top](#table-of-contents)

### 191. How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)

- Use `Promise.all` when you need all to succeed or fail fast (reject on first error).
- Use `Promise.allSettled` when you want to know the outcome of each independent call, regardless of failures (e.g., analytics, fallback data).

[↑ Back to top](#table-of-contents)

### 192. How would you implement a robust frontend monitoring and logging system?

A robust system combines **error tracking**, **performance monitoring**, **user analytics**, and **structured logging**.

- **Error tracking**: Use Sentry, Rollbar, or similar. Capture JavaScript errors, unhandled promise rejections, and React error boundaries. Upload source maps to get readable stack traces.
- **Performance monitoring**: Implement Real User Monitoring (RUM) with tools like Datadog RUM, New Relic Browser, or Google Analytics with Web Vitals. Track Core Web Vitals (LCP, CLS, INP), custom timings (e.g., time to checkout), and resource loading.
- **Logging**: For client‑side, send structured logs to a backend endpoint (e.g., via `fetch`). Use a correlation ID across frontend and backend to trace requests. Avoid logging sensitive data.
- **User analytics**: Use tools like Mixpanel or Amplitude to track feature usage, funnel conversions, and user flows.
- **Alerts**: Set up alerts on error rate spikes, performance regressions, or business metric thresholds. Use tools like Sentry’s alert rules or Datadog monitors.
- **Implementation**: Wrap the app in a monitoring provider that initializes SDKs, attaches user context, and buffers logs. Ensure logging doesn’t block the main thread – send data asynchronously in idle periods.

[↑ Back to top](#table-of-contents)

### 193. Multiple API Calls: How to load a dashboard with independent APIs efficiently? (Promise.all, allSettled)

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

[↑ Back to top](#table-of-contents)

### 194. What are `Promise.allSettled`, `Promise.race`, and `Promise.any`?

`allSettled`: waits for all, resolves with array of `{status, value/reason}` — never rejects. `race`: settles with the first Promise to settle (fulfill or reject). `any`: fulfills with the first fulfillment; rejects with `AggregateError` only if all reject.

[↑ Back to top](#table-of-contents)

### 195. What are async generators and when would you use them?

Declared with `async function*`, they combine async and generator behavior. Each `yield` can produce a value asynchronously. Consumed with `for await...of`. Useful for paginated APIs, streaming data, or any async sequence.

[↑ Back to top](#table-of-contents)

### 196. What are callbacks and what problems do they have?

A function passed as an argument to be called when an async operation completes. Problems: callback hell (deeply nested, hard to read), difficult error handling, no return values, inversion of control. Solved by Promises and async/await.

[↑ Back to top](#table-of-contents)

### 197. What are ES2020+ features you should know?

Optional chaining `?.`, nullish coalescing `??`, `Promise.allSettled()`, `BigInt`, `globalThis`, dynamic import `import()`, `String.matchAll()`, logical assignment `&&=`/`||=`/`??=` (ES2021), `Array.at()` (ES2022), `Object.hasOwn()` (ES2022), `structuredClone()` (ES2022), top-level `await` (ES2022).

[↑ Back to top](#table-of-contents)

### 198. What are generators?

A: Functions that can be paused and resumed, defined with `function*`. They return an iterator that yields values via `yield`. Useful for lazy evaluation, infinite sequences, and async flows.

[↑ Back to top](#table-of-contents)

### 199. What are practical uses of closures?

Data privacy/encapsulation (module pattern), factory functions, memoization, partial application, event handlers that remember state, maintaining state in async operations, and implementing the module pattern before ES modules existed.

[↑ Back to top](#table-of-contents)

### 200. What are the advantages of `Promise.allSettled` over `Promise.all`?

`Promise.allSettled` never rejects; it always resolves with an array of objects describing each promise’s outcome. This is useful when you need to wait for multiple operations and handle errors individually, without failing the whole batch.

[↑ Back to top](#table-of-contents)

### 201. What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?

**Call Stack**: where synchronous code executes (LIFO). **Web APIs**: browser-provided async capabilities (setTimeout, fetch, DOM events) — offloaded from JS thread. **Callback Queue (macrotask queue)**: where timer/event callbacks wait. **Microtask Queue**: where Promise callbacks and `queueMicrotask` wait. Microtasks run before the next macrotask.

[↑ Back to top](#table-of-contents)

### 202. What are the states of a Promise?

**Pending**: initial state, operation in progress. **Fulfilled**: operation completed successfully — `resolve()` was called. **Rejected**: operation failed — `reject()` was called. Once settled (fulfilled or rejected), a Promise is immutable — it can never change state again.

[↑ Back to top](#table-of-contents)

### 203. What causes memory leaks in frontend applications? How to prevent them?

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

[↑ Back to top](#table-of-contents)

### 204. What does `finally` do in a Promise chain?

`.finally(fn)` runs `fn` regardless of whether the promise resolved or rejected. Useful for cleanup (hiding loading spinners, closing connections). It doesn't receive the resolved value or rejection reason. It passes the original outcome to the next handler in the chain.

[↑ Back to top](#table-of-contents)

### 205. What happens if you `await` a non-Promise value?

`await 42` is valid — it simply returns `42`. The value is wrapped in `Promise.resolve()` first. This means `await` is safe to use even if you're not sure if a function returns a Promise.

[↑ Back to top](#table-of-contents)

### 206. What is `async/await`?

Syntactic sugar over Promises. `async` functions always return a Promise. `await` pauses execution of the async function until the awaited Promise resolves, then returns the resolved value. Makes async code look and behave more like synchronous code. Under the hood, it's still Promises.

[↑ Back to top](#table-of-contents)

### 207. What is `createAsyncThunk()` and why is it used?

`createAsyncThunk` is a function that creates a thunk action that handles asynchronous requests. It takes an action type prefix and a payload creator (async function). It automatically dispatches `pending`, `fulfilled`, and `rejected` actions based on the promise. This reduces boilerplate for loading states and error handling.

[↑ Back to top](#table-of-contents)

### 208. What is `process.nextTick()`?

Schedules a callback to run at the end of the current iteration of the Node.js event loop, before any I/O events or timers. Runs before Promises (microtasks) in Node.js's implementation. Use sparingly — too many nextTick callbacks can starve the event loop.

[↑ Back to top](#table-of-contents)

### 209. What is `Promise.allSettled()`?

Like `Promise.all()` but never rejects. Waits for ALL promises to settle and returns an array of `{status: 'fulfilled', value}` or `{status: 'rejected', reason}` objects. Use when you need all results regardless of individual failures (e.g., multiple independent API calls).

[↑ Back to top](#table-of-contents)

### 210. What is `requestAnimationFrame` and why use it for animations?

Schedules a callback before the browser's next repaint (~60fps). Pauses automatically when tab is hidden (saves battery/CPU). Passes a timestamp for smooth, frame-rate-independent animations. Much better than `setInterval` for visual updates because it syncs with the display refresh cycle.

[↑ Back to top](#table-of-contents)

### 211. What is `requestAnimationFrame`?

Schedules a callback before the next browser repaint. Runs at the display refresh rate (~60fps). Better than `setTimeout` for animations — synchronized with the browser's paint cycle, paused in background tabs, and not subject to throttling.

[↑ Back to top](#table-of-contents)

### 212. What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?

`setTimeout(fn, delay)`: calls `fn` once after `delay` ms (minimum — actual time may be longer). `setInterval(fn, delay)`: calls `fn` repeatedly every `delay` ms. `requestAnimationFrame(fn)`: calls `fn` before the next browser repaint (~60fps). Use rAF for animations; it's paused when the tab is hidden and syncs with display refresh rate.

[↑ Back to top](#table-of-contents)

### 213. What is a callback and what is callback hell?

A callback is a function passed to another function to be called later. Callback hell: deeply nested callbacks where each async step requires another callback, creating a pyramid of doom. Makes code hard to read, debug, and maintain. Solved by Promises and async/await.

[↑ Back to top](#table-of-contents)

### 214. What is a callback function?

A function passed as an argument to another function and called later (usually after an async operation or event). The foundation of async JavaScript before Promises. Still used in event handlers, array methods (`forEach`, `map`), and APIs like `setTimeout`.

[↑ Back to top](#table-of-contents)

### 215. What is a monad (in practical JS terms)?

A pattern for sequencing operations with context — essentially anything with a `flatMap`/`chain` method that flattens one level. Promises behave monadically (`.then` flattens nested promises). Used in libraries like fp-ts. Understanding monads enables cleaner async and nullable handling.

[↑ Back to top](#table-of-contents)

### 216. What is a Promise?

An object representing the eventual completion or failure of an async operation. Created with `new Promise((resolve, reject) => {...})`. Provides `.then()` for success, `.catch()` for error, `.finally()` for cleanup. Promises are chainable and avoid callback hell. They're always asynchronous — `.then` callbacks always run after the current synchronous code.

[↑ Back to top](#table-of-contents)

### 217. What is an unhandled promise rejection?

A Promise that rejects with no `.catch` handler. In Node.js, unhandled rejections emit a warning and can crash the process. In browsers, they fire `window.onunhandledrejection`. Listen to `process.on('unhandledRejection', handler)` in Node.js for a global safety net.

[↑ Back to top](#table-of-contents)

### 218. What is dynamic `import()`?

`import('./module.js')` returns a Promise that resolves to the module's namespace object. Enables lazy loading and code splitting — load code on demand rather than upfront. Unlike static `import`, it can be inside conditions or functions.

[↑ Back to top](#table-of-contents)

### 219. What is lazy loading?

Deferring loading of resources (images, modules, components) until they're actually needed. Reduces initial page load. For images: `<img loading="lazy">` or Intersection Observer. For code: dynamic `import()` — `const mod = await import('./module.js')`. Both reduce time-to-interactive.

[↑ Back to top](#table-of-contents)

### 220. What is Node.js?

A JavaScript runtime built on Chrome's V8 engine. Enables server-side JavaScript. Non-blocking I/O via an event loop (powered by libuv). Single-threaded for JS execution but uses threads internally for I/O. Ideal for I/O-heavy apps (APIs, real-time, streaming); less ideal for CPU-heavy tasks (use Worker Threads).

[↑ Back to top](#table-of-contents)

### 221. What is promise chaining?

`.then()` returns a new Promise, so you can chain multiple async operations: `fetchUser().then(user => fetchPosts(user.id)).then(posts => render(posts)).catch(handleError)`. Each `.then` receives the resolved value of the previous one. Errors propagate down the chain to the nearest `.catch`.

[↑ Back to top](#table-of-contents)

### 222. What is single-threaded execution in JavaScript?

JavaScript has one call stack and one thread of execution – it can only do one thing at a time. Long-running tasks block everything else. The event loop enables asynchronous behavior by offloading tasks (timers, network) to Web APIs and processing their callbacks when the stack is empty.

[↑ Back to top](#table-of-contents)

### 223. What is synchronous vs asynchronous code?

Synchronous: executes line by line, each line waits for the previous to finish. Asynchronous: initiates an operation and moves on; the result is handled later via callback, promise, or async/await. JS is single-threaded, so async operations are managed by the event loop, not true parallelism.

[↑ Back to top](#table-of-contents)

### 224. What is the `fetch` API?

A modern Promise-based API for HTTP requests, replacing `XMLHttpRequest`. `fetch(url, options)` returns a Promise of a `Response`. You must call `.json()`, `.text()`, or `.blob()` to read the body (also async). A `fetch` only rejects on network failure — not on 4xx/5xx responses (check `response.ok`).

[↑ Back to top](#table-of-contents)

### 225. What is the danger of floating Promises?

A Promise that is not awaited and has no `.catch()`. If it rejects, the error is silently swallowed or triggers `unhandledRejection`. Always `await` or `.catch()` every Promise. ESLint rules like `no-floating-promises` (from TypeScript-eslint) catch this statically.

[↑ Back to top](#table-of-contents)

### 226. What is the difference between `Promise` and `async/await`?

A: Promises are objects representing eventual completion; `async/await` is syntactic sugar over promises, making asynchronous code look synchronous. `await` can only be used inside `async` functions.

[↑ Back to top](#table-of-contents)

### 227. What is the difference between `setTimeout(fn, 0)` and `Promise.resolve().then(fn)`?

Both defer execution, but Promise callbacks (microtasks) run before setTimeout callbacks (macrotasks). `setTimeout(fn, 0)` adds to the macrotask queue; `Promise.resolve().then(fn)` adds to the microtask queue, which drains before the next macrotask.

[↑ Back to top](#table-of-contents)

### 228. What is the difference between `setTimeout` and `setInterval`?

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

[↑ Back to top](#table-of-contents)

### 229. What is the difference between macrotasks and microtasks?

**Macrotasks** (task queue): `setTimeout`, `setInterval`, `setImmediate`, I/O, UI rendering. One macrotask runs per event loop iteration. **Microtasks**: Promises (`.then`, `.catch`, `.finally`), `queueMicrotask`, `MutationObserver`. ALL microtasks are processed after each macrotask, before the next macrotask runs. Microtasks have priority.

[↑ Back to top](#table-of-contents)

### 230. What is the difference between sequential and parallel async execution?

Sequential: `await a(); await b();` — B starts only after A finishes. Total time = A + B. Parallel: `await Promise.all([a(), b()])` — both start simultaneously. Total time = max(A, B). Use parallel when operations are independent; sequential when one depends on the other.

[↑ Back to top](#table-of-contents)

### 231. What is the difference between the Microtask Queue and the Macrotask Queue?

Microtasks (Promise `.then`, `queueMicrotask`, `MutationObserver`) run after every task before the next task and before rendering. Macrotasks (`setTimeout`, `setInterval`, I/O, `setImmediate`) run one per event loop iteration. Microtasks always drain completely before the next macrotask.

[↑ Back to top](#table-of-contents)

### 232. What is the Event Loop?

The mechanism that allows JavaScript to perform non-blocking async operations despite being single-threaded. It continuously checks if the call stack is empty, then takes tasks from the task queue and pushes them onto the stack. This enables handling timers, network responses, and user events without blocking the main thread.

[↑ Back to top](#table-of-contents)

### 233. What is the event loop? How does it work with the call stack and task queue?

A: The event loop continuously checks if the call stack is empty; if so, it takes tasks from the task queue (or microtask queue) and pushes them onto the stack. Asynchronous operations (setTimeout, promises) are handled via the event loop.

[↑ Back to top](#table-of-contents)

### 234. What is the MutationObserver API?

Watches for changes to the DOM tree (child additions/removals, attribute changes, text changes). Fires asynchronously (as a microtask). Use when you need to react to DOM changes made by third-party scripts or when you can't use your own state management.

[↑ Back to top](#table-of-contents)

### 235. What is the Node.js event loop and how does it differ from the browser's?

Node.js uses libuv for I/O and has additional phases: timers (`setTimeout`/`setInterval`), pending callbacks, idle, poll (I/O), check (`setImmediate`), close callbacks. `setImmediate` runs after I/O in the check phase — before a `setTimeout(fn, 0)` in I/O context.

[↑ Back to top](#table-of-contents)

### 236. What is the Node.js event loop vs the browser event loop?

Both use the event loop pattern but with different phases. Node.js (libuv): has explicit phases — timers → pending callbacks → idle/prepare → poll (I/O) → check (setImmediate) → close callbacks. Browser event loop is simpler. Key difference: Node has `setImmediate` and `process.nextTick` (runs before everything else in the current iteration).

[↑ Back to top](#table-of-contents)

### 237. What would you look for when reviewing a junior developer's JavaScript PR?

Missing `await` or unhandled Promises. Mutable data where immutable patterns were intended. `var` instead of `let`/`const`. Callback-style code where Promises/async-await are cleaner. Missing error handling. Potential XSS with `innerHTML`. Performance issues: loops inside loops, DOM queries in loops, missing debounce on event handlers. Missing tests for edge cases.

[↑ Back to top](#table-of-contents)

### 238. Why is `eval()` dangerous?

Executes arbitrary code strings — a major XSS vector if user input reaches it. Bypasses security, slows performance (JIT can't optimize code inside eval), and makes debugging harder. Never use `eval()` with untrusted input. Also avoid `Function()`, `setTimeout('code string')`, `setInterval('code string')`.

[↑ Back to top](#table-of-contents)

## DOM, BOM & Events

### 239. Explain event bubbling and capturing.

Events propagate in three phases: **capturing** (from window down to target), **target**, and **bubbling** (from target back up). By default, event listeners are registered for the bubbling phase. To listen in capturing phase, set `useCapture: true` in `addEventListener`.

- **Bubbling** – the event triggers on the target element and then on each ancestor.
- **Capturing** – the event triggers on ancestors first, then the target.

[↑ Back to top](#table-of-contents)

### 240. How do you create, append, and remove DOM elements?

Create: `document.createElement('div')`. Set content: `el.textContent = 'text'` or `el.setAttribute('class', 'box')`. Append: `parent.appendChild(el)` or `parent.append(el)` (newer, accepts strings). Insert: `parent.insertBefore(el, ref)` or `el.insertAdjacentElement('position', newEl)`. Remove: `el.remove()` or `parent.removeChild(el)`.

[↑ Back to top](#table-of-contents)

### 241. How do you detect and prevent memory leaks in long-running SPAs?

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

[↑ Back to top](#table-of-contents)

### 242. How do you securely handle user input in JavaScript?

Never trust user input. Validate on both client (UX) and server (security). Escape before inserting into DOM (use `textContent`). Sanitize HTML with DOMPurify if HTML is needed. Use parameterized queries for databases. Encode for the output context (HTML, URL, JS).

[↑ Back to top](#table-of-contents)

### 243. How do you select and manipulate DOM elements?

**Selecting**:
- `document.getElementById(id)` – single element.
- `document.querySelector(selector)` – first match.
- `document.querySelectorAll(selector)` – NodeList.
- `document.getElementsByClassName(class)` – HTMLCollection.
- `document.getElementsByTagName(tag)`.

**Manipulating**:
- Change content: `element.textContent`, `element.innerHTML`.
- Attributes: `element.setAttribute(name, value)`, `element.getAttribute(name)`.
- Classes: `classList.add()`, `remove()`, `toggle()`, `contains()`.
- Styles: `element.style.property = value` (inline).
- Create elements: `document.createElement(tag)`, append with `appendChild` or `append`.

[↑ Back to top](#table-of-contents)

### 244. How do you select DOM elements?

`document.getElementById('id')` — returns single element. `document.querySelector('css-selector')` — returns first match. `document.querySelectorAll('css-selector')` — returns NodeList of all matches. `document.getElementsByClassName('cls')` / `getElementsByTagName('tag')` — live HTMLCollections. Prefer `querySelector`/`querySelectorAll` for flexibility.

[↑ Back to top](#table-of-contents)

### 245. How do you work with cookies in JavaScript?

- **Read**: `document.cookie` returns a string of all cookies; parse manually.
- **Write**: `document.cookie = "name=value; expires=...; path=...; secure"`.
- **Delete**: Set expiry date in past.
- Libraries like `js-cookie` simplify.

[↑ Back to top](#table-of-contents)

### 246. How does `addEventListener` work? How to remove listeners?

`addEventListener(event, callback, options)` attaches an event handler. It does not overwrite existing handlers (unlike `onclick` property). You can pass `{ once: true }` for one‑time execution.

To remove, use `removeEventListener` with the same function reference. That’s why anonymous functions cannot be removed unless stored in a variable.

[↑ Back to top](#table-of-contents)

### 247. What are memory leaks in JavaScript and what causes them?

Memory that is allocated but never freed because references still exist. Common causes: event listeners not removed, closures holding references, global variables, detached DOM nodes still referenced in JS, interval/timeout callbacks holding references.

[↑ Back to top](#table-of-contents)

### 248. What are side effects?

Any interaction with the outside world from within a function: modifying external variables, DOM manipulation, network requests, logging, reading from `Date.now()`. Functions with side effects are harder to test and predict. FP separates pure computation from side effects — push side effects to the edges of your program.

[↑ Back to top](#table-of-contents)

### 249. What are Web Workers?

Background threads that run JS code without blocking the main thread. No DOM access. Communicate with the main thread via `postMessage`/`onmessage`. Use for CPU-intensive tasks (image processing, crypto, parsing large JSON). Shared Workers can be accessed by multiple tabs. Service Workers intercept network requests.

[↑ Back to top](#table-of-contents)

### 250. What is `MutationObserver`?

Watches for DOM changes (child additions, attribute changes, text modifications) and fires a callback asynchronously with a list of `MutationRecord` objects. More efficient than polling. Used in libraries for tracking DOM changes without reflow.

[↑ Back to top](#table-of-contents)

### 251. What is event delegation? When would you use it?

Event delegation is a technique where a single event listener is attached to a parent element to handle events on its children, leveraging event bubbling. This reduces memory usage and works for dynamically added elements.

**Use cases**:
- Handling clicks on many similar items (e.g., list items, buttons).
- When elements are added/removed dynamically (e.g., chat messages, todo items).

Example:

```javascript
document.querySelector('#list').addEventListener('click', (e) => {
if (e.target.matches('li')) {
console.log('Item clicked:', e.target.textContent);
}
});

```

[↑ Back to top](#table-of-contents)

### 252. What is reflow and repaint?

**Reflow (layout)**: browser recalculates positions/dimensions of elements — expensive, cascades. Triggered by: adding/removing elements, changing size/position/font. **Repaint**: browser redraws pixels — less expensive. Triggered by: changing color, visibility, shadow. Minimize by batching DOM changes, using `documentFragment`, CSS transforms (GPU-composited), and avoiding reading layout properties in a loop.

[↑ Back to top](#table-of-contents)

### 253. What is the `DOMContentLoaded` vs `load` event?

`DOMContentLoaded`: fires when HTML is fully parsed and DOM is ready — before images/stylesheets finish loading. `load` (on `window`): fires when ALL resources (images, styles, scripts) have loaded. Use `DOMContentLoaded` for DOM manipulation that doesn't depend on images; use `load` when you need images to be loaded.

[↑ Back to top](#table-of-contents)

### 254. What is the difference between `addEventListener` and `onclick`?

`onclick` is an element property — only one handler can be set (later assignment overrides). `addEventListener` allows multiple handlers for the same event on the same element, supports capture phase, and can be removed with `removeEventListener`. Always prefer `addEventListener`.

[↑ Back to top](#table-of-contents)

### 255. What is the difference between the browser and Node.js environments?

Browser: has DOM, window, document, browser APIs (fetch, localStorage, alert), sandboxed. Node.js: has no DOM, has `process`, `__dirname`, `__filename`, `require`, built-in modules (`fs`, `http`, `path`, `crypto`, `os`), full file system access, can run servers. Both run the same JS language.

[↑ Back to top](#table-of-contents)

### 256. What is the difference between virtualization and windowing? Trade-offs.

**Virtualization** is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. **Windowing** is a specific implementation (e.g., `react-window`) that renders a “window” of items.

**Trade-offs**:
- **Pros**: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists.
- **Cons**: Adds complexity; layout calculations can be tricky for variable heights. Accessibility can suffer if not implemented carefully (screen readers may not see all items). Scrolling might feel different.

[↑ Back to top](#table-of-contents)

### 257. What is the DOM?

The Document Object Model — a tree-structured representation of an HTML document created by the browser. JavaScript uses the DOM API to read and manipulate the page's structure, content, and styles. Each HTML element becomes a Node object with properties and methods.

[↑ Back to top](#table-of-contents)

### 258. What is the Observer / Pub-Sub pattern?

Objects (subscribers) register interest in events. When an event occurs, the publisher notifies all subscribers. EventEmitter in Node.js, `addEventListener` in the browser, Redux's store, and RxJS all implement this pattern. Decouples the event source from event consumers.

[↑ Back to top](#table-of-contents)

### 259. What is XSS (Cross-Site Scripting)?

An attack where malicious scripts are injected into web pages viewed by other users. Types: Stored (persisted in DB), Reflected (in URL), DOM-based (via client-side JS). Prevention: escape all user output (use `textContent` not `innerHTML`), CSP headers, sanitize with DOMPurify, avoid `eval()`.

[↑ Back to top](#table-of-contents)

## Error Handling & Debugging

### 260. How do you implement a CSS animation? How to debug janky animations on mobile?

**Implementing animation**:
- Define keyframes with `@keyframes`.
- Apply with `animation` property: `animation: name duration timing-function delay iteration-count direction fill-mode;`

**Debugging janky animations**:
- Use Chrome DevTools Performance tab to record and identify long tasks and layout/paint events.
- Check that you are animating only **compositor‑only** properties: `transform` and `opacity`. Avoid animating `width`, `height`, `top`, `left`, etc., which trigger layout.
- Enable the “Paint flashing” option in DevTools to see repaints.
- Use `will-change` sparingly for elements you will animate (e.g., `will-change: transform`).
- On mobile, reduce animation complexity; test with throttled CPU.

[↑ Back to top](#table-of-contents)

### 261. What is `try/catch/finally` and how does `finally` behave?

`try` runs code that might throw. `catch(e)` handles thrown errors. `finally` runs no matter what — even if `try` returns or `catch` throws. If `finally` returns a value, it overrides the `try`/`catch` return — a subtle behavior to be aware of.

[↑ Back to top](#table-of-contents)

### 262. What is `WeakRef` and `FinalizationRegistry`?

`WeakRef` holds a weak reference to an object — if the object is GC'd, `ref.deref()` returns `undefined`. `FinalizationRegistry` registers a callback to run after an object is collected. Used for: caches that shouldn't prevent GC, tracking live instances for debugging. The GC timing is non-deterministic — don't rely on these for critical logic.

[↑ Back to top](#table-of-contents)

### 263. What is a `try/catch/finally` block?

`try`: code that might throw. `catch(err)`: runs if an error is thrown — `err` is the Error object. `finally`: always runs regardless of success or failure — used for cleanup. `throw` can throw any value, but throw Error objects for best debuggability (stack trace).

[↑ Back to top](#table-of-contents)

### 264. What is source mapping?

A file (`.map`) that maps minified/transpiled code back to the original source. Enables debugging production code with original source in DevTools. Generated by bundlers/transpilers. Should be served in staging, sometimes restricted in production.

[↑ Back to top](#table-of-contents)

### 265. What is TDD (Test-Driven Development)?

Write tests first (failing), then write the minimum code to make them pass, then refactor. Cycle: Red → Green → Refactor. Benefits: forces clear requirements, prevents over-engineering, provides instant regression coverage. Can be slower initially but reduces debugging time.

[↑ Back to top](#table-of-contents)

### 266. What is the `Error.cause` property (ES2022)?

`throw new Error('message', {cause: originalError})` — chains errors to preserve the original cause. `error.cause` holds the original error. Useful for wrapping low-level errors with higher-level context without losing the original stack trace.

[↑ Back to top](#table-of-contents)

## Performance (Debounce, Throttle, Memoization)

### 267. Describe the hardest production bug you fixed.

**Approach**: Focus on a bug that was elusive, required deep investigation, and had significant impact. Explain your diagnostic process and the fix.

**Example**:
> “We had a memory leak in a single‑page application that caused the browser to crash after about an hour of usage. It was hard to reproduce because it only happened when users navigated through many screens.
>
> **Process**:
> 1. I used Chrome DevTools Memory tab to take heap snapshots before and after navigation. I noticed detached DOM nodes accumulating.
> 2. I traced them to a custom modal component that added a global scroll‑block event listener but never removed it on unmount. The listener kept a reference to the modal’s DOM element.
> 3. I also discovered a `setInterval` in a chart component that wasn’t cleared, holding onto large data arrays.
>
> **Fix**: I added cleanup functions in `useEffect` for both issues. I also introduced a custom ESLint rule to enforce cleanup for all timers and event listeners.
>
> **Result**: The memory leak was eliminated, and the app remained stable for days. The incident taught us to enforce cleanup patterns and use heap snapshots in our testing.”

[↑ Back to top](#table-of-contents)

### 268. How does garbage collection work in V8?

V8 uses a **generational, mark‑and‑sweep** garbage collector.

- **Heap**: Divided into **young generation** (newly allocated objects) and **old generation** (objects that survive multiple collections).
- **Minor GC (Scavenger)**: Runs frequently on the young generation, copying surviving objects to a survivor space. Very fast.
- **Major GC (Mark‑Sweep / Mark‑Compact)**: Runs less often on the old generation. It marks reachable objects, sweeps unreachable ones, and compacts to reduce fragmentation.
- **Incremental marking**: Long pauses are avoided by interleaving marking with JavaScript execution.

[↑ Back to top](#table-of-contents)

### 269. What is a memory leak and what causes them?

Memory that is no longer needed but not released because references still exist. Common causes: forgotten event listeners (not removed), closures holding large objects, global variables accumulating data, DOM references held after nodes are removed, detached DOM nodes, `setInterval` never cleared.

[↑ Back to top](#table-of-contents)

### 270. What is garbage collection in JavaScript?

JS engines automatically free memory that is no longer reachable. The most common algorithm is mark-and-sweep: starting from roots (global, stack), the engine marks all reachable objects and sweeps the rest. Closures can cause unintentional memory retention.

[↑ Back to top](#table-of-contents)

### 271. What is the JavaScript garbage collection impact of closures?

A closure keeps references to all variables in its outer scope alive, even those not explicitly used — in some engines. This can cause large objects to be retained unintentionally. Fix: nullify references when done (`largeData = null`), extract only needed values from outer scope rather than capturing the whole scope, use WeakRef for caches.

[↑ Back to top](#table-of-contents)

## Generators, Iterators & Symbols

### 272. What are iterators and iterables?

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

[↑ Back to top](#table-of-contents)

### 273. What are Proxy and Reflect?

`Proxy` wraps an object and intercepts fundamental operations (get, set, delete, apply, construct) via handler traps. `Reflect` provides the same set of operations as static methods. Used for: validation, reactive systems (Vue 3), logging, access control, mocking.

[↑ Back to top](#table-of-contents)

### 274. What is `Reflect` in JavaScript?

A built-in object with static methods mirroring Proxy handler traps. `Reflect.get(obj, key)`, `Reflect.set(obj, key, val)`, `Reflect.has(obj, key)`, etc. Used inside Proxy handlers to invoke default behavior after custom logic. Also useful as a cleaner alternative to some `Object` methods.

[↑ Back to top](#table-of-contents)

### 275. What is `Symbol.toPrimitive` used for?

Allows an object to define its own coercion to a primitive. The method receives a hint (`'number'`, `'string'`, or `'default'`) and should return the appropriate primitive. Example use: custom value objects (Money, Color) that behave naturally in arithmetic or string contexts.

[↑ Back to top](#table-of-contents)

### 276. What is `Symbol` and why was it introduced?

`Symbol()` creates a unique, immutable primitive. Introduced in ES6 to create non-string property keys that avoid naming collisions — critical for metaprogramming hooks like `Symbol.iterator`, `Symbol.toPrimitive`, `Symbol.hasInstance`.

[↑ Back to top](#table-of-contents)

### 277. What is a generator function?

Declared with `function*`, it returns a generator object that implements the iterator protocol. Uses `yield` to pause execution and return a value. Execution resumes on `.next()`. Useful for lazy sequences, infinite data streams, and implementing async flows (before async/await).

```javascript
function* range(start, end) {
for (let i = start; i <= end; i++) yield i;
}
[...range(1, 5)]; // [1, 2, 3, 4, 5]

```

[↑ Back to top](#table-of-contents)

### 278. What is an iterable?

An object implementing the iterable protocol: a `[Symbol.iterator]()` method that returns an iterator. Arrays, strings, Maps, Sets, and generators are iterable. Custom iterables can be created by implementing this method.

[↑ Back to top](#table-of-contents)

### 279. What is the Proxy object and how is it used?

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

[↑ Back to top](#table-of-contents)

## Regular Expressions & String Manipulation

### 280. How would you implement a publish/subscribe system with topics and wildcards?

Map topic strings to subscriber Sets. For wildcards (`*`), on publish check each subscriber's pattern against the topic using a regex or glob match. Namespace topics with `.` separator for hierarchical subscriptions (`user.*` matches `user.created`, `user.deleted`).

**Q181. Situation: `JSON.stringify` is dropping data — explain why and how to fix it.**

`JSON.stringify` silently omits: `undefined` values in objects (and `undefined` itself), functions, `Symbol` keys and values, and `Infinity`/`NaN` (become `null`). Circular references throw. Fix: use a replacer function as the second argument to handle special values, or use a library like `flatted` for circular refs.

[↑ Back to top](#table-of-contents)

## Modules, Build Tools & Browser APIs

### 281. How do you detect and prevent infinite loops in user-submitted code?

Run in a sandboxed Web Worker. Inject a counter that increments on each iteration and throws after a limit. Use a timer in the host to terminate the Worker after a timeout. Never run untrusted code in the main thread or with `eval` in the host environment.

[↑ Back to top](#table-of-contents)

### 282. What are source maps?

Files that map minified/compiled production code back to the original source. Enable readable stack traces and breakpoints in DevTools despite bundling and transpilation. Generated by bundlers (webpack, Vite) with a configuration option.

[↑ Back to top](#table-of-contents)

### 283. What is a bundler (Webpack, Rollup, Vite)?

A tool that takes JavaScript modules (and other assets) and combines them into optimized files for deployment. Handles dependency resolution, code splitting, tree shaking, minification, and asset processing. Webpack: powerful, configurable, most popular. Rollup: great for libraries (clean ESM output). Vite: fast dev server with native ESM + Rollup for production.

[↑ Back to top](#table-of-contents)

### 284. What is Jest?

The most popular JavaScript testing framework. Zero-config by default, built-in mocking, code coverage, snapshot testing, and assertion library. Works with Node.js and browser environments (via jsdom). Supports TypeScript via Babel or ts-jest.

[↑ Back to top](#table-of-contents)

### 285. What is the difference between `dependencies` and `devDependencies`?

`dependencies`: packages needed to run the app in production (Express, React, Lodash). `devDependencies`: packages needed only during development (Jest, ESLint, Babel, TypeScript). Distinguishing them matters for keeping production `node_modules` lean. `npm install --production` skips devDependencies.

[↑ Back to top](#table-of-contents)

### 286. What is the Fetch API vs XMLHttpRequest?

`fetch` is Promise-based, cleaner syntax, supports streams, no built-in timeout/progress. `XMLHttpRequest` is callback-based, supports progress events and synchronous calls (avoid sync). `fetch` does not reject on HTTP errors (only on network failure) — always check `response.ok`.

[↑ Back to top](#table-of-contents)

### 287. What is the JavaScript pipeline operator proposal?

The `|>` operator (Stage 2) allows `value |> fn1(%) |> fn2(%)`, making pipelines readable without nesting or composition helpers. `%` is the placeholder for the piped value. Still in proposal — use Babel plugin for early access. Competing with the Hack-style (with %) and F#-style (without) proposals.

[↑ Back to top](#table-of-contents)

### 288. What is the TC39 proposal process and how do you track upcoming JavaScript features?

Proposals go through 5 stages: Stage 0 (idea), Stage 1 (proposal), Stage 2 (draft spec), Stage 3 (candidate — implementations begin), Stage 4 (finished — included in next ES spec). Track at the tc39/proposals GitHub repo. Stage 3 proposals are generally safe to use with Babel/TypeScript. Stage 4 proposals ship in the next ECMAScript edition.

[↑ Back to top](#table-of-contents)

### 289. What is the Web Worker API?

Runs JavaScript in a background thread, separate from the main thread. Communicates via `postMessage`/`onmessage`. No DOM access. Used for CPU-intensive tasks (image processing, data parsing, encryption) to avoid blocking the main thread.

[↑ Back to top](#table-of-contents)

### 290. What is transpilation and what does Babel do?

Transpilation converts modern JS (ES2022+) to older JS (ES5) so it runs in older browsers. Babel: a popular transpiler with plugin/preset system. Transforms JSX, TypeScript, and modern syntax. In Vite projects, esbuild handles basic transpilation faster; Babel needed only for advanced transforms.

[↑ Back to top](#table-of-contents)

## General / Miscellaneous JavaScript Concepts

### 291. Compare WebSockets, SSE, and WebRTC for real‑time features.

| Feature | WebSockets | SSE (Server‑Sent Events) | WebRTC |
|--------|-----------|------------------------|--------|
| **Direction** | Bidirectional | Server → client only | Peer‑to‑peer (with signaling) |
| **Protocol** | ws / wss | HTTP/2 (text/event‑stream) | UDP‑based (with ICE) |
| **Use cases** | Chat, gaming, collaborative editing | Live feeds, notifications, stock tickers | Video/audio calls, peer‑to‑peer data |
| **Overhead** | Moderate | Low (HTTP) | Higher |
| **Reconnection** | Manual | Built‑in (EventSource) | Handled by ICE |
| **Browser support** | Excellent | Excellent (except IE) | Good (requires HTTPS) |

**Choice**:
- Use **WebSockets** for full‑duplex, low‑latency communication.
- Use **SSE** when only server needs to push data (simpler, uses HTTP).
- Use **WebRTC** for media streaming or large file transfers between clients.

[↑ Back to top](#table-of-contents)

### 292. CPU vs memory bottlenecks – how to identify and fix?

**CPU bottlenecks** – JavaScript execution causing long tasks, jank, high CPU usage.
- **Identify**: Chrome DevTools Performance tab; look for long “Script” tasks.
- **Fix**: Code splitting, Web Workers for heavy computations, throttle/debounce event handlers, use `useTransition` to prioritize UI updates, avoid expensive renders.

**Memory bottlenecks** – Leaks causing growing memory consumption, eventual slowdown or crash.
- **Identify**: Memory tab, take heap snapshots; compare after user actions to see retained objects.
- **Fix**: Clean up event listeners, intervals, WebSocket connections; avoid retaining large data in closures; use weak references (`WeakMap`, `WeakSet`) for caching; unmount components properly; use `useEffect` cleanup.

[↑ Back to top](#table-of-contents)

### 293. Explain the difference between eager and lazy evaluation in JavaScript.

Eager: values are computed immediately when defined. Lazy: values are computed only when needed. Generators implement lazy sequences. `&&` and `||` are lazy (short-circuit). Proxies enable lazy object initialization. Lazy evaluation avoids unnecessary computation and enables infinite sequences.

[↑ Back to top](#table-of-contents)

### 294. Explain the difference between localStorage, sessionStorage, and cookies.

| Feature | localStorage | sessionStorage | cookies |
|---------|--------------|----------------|--------|
| **Capacity** | ~5‑10 MB | ~5‑10 MB | ~4 KB |
| **Lifetime** | Persistent until manually cleared | Tab/window lifetime; cleared on close | Can be set with expiration; can be session‑only |
| **Scope** | Same origin | Same origin, per tab | Same origin; path can be scoped |
| **Sent to server** | No | No | Yes (with every HTTP request) |
| **API** | Simple (`setItem`, `getItem`) | Simple | More complex (document.cookie) |
| **Use case** | Client‑side data, offline storage | Temporary session data | Authentication, tracking, server‑side needs |

[↑ Back to top](#table-of-contents)

### 295. Explain the IntersectionObserver API and its use cases (lazy loading, infinite scroll).

`IntersectionObserver` watches elements and triggers a callback when they enter/exit the viewport (or a specified root element). It is asynchronous and efficient, avoiding scroll listeners.

**Use cases**:
- Lazy loading images: observe images, set `src` when visible.
- Infinite scroll: load more content when a sentinel element appears.
- Analytics: track when an element is viewed.
- Animation: trigger entrance animations.

[↑ Back to top](#table-of-contents)

### 296. How do you avoid layout thrashing?

**Layout thrashing** occurs when you repeatedly read layout properties (e.g., `offsetHeight`) and then write styles in a loop, forcing the browser to recalculate layout multiple times.

**Avoidance**:
- Batch reads before writes. For example, read all necessary dimensions first, then apply style changes.
- Use `requestAnimationFrame` to schedule changes.
- Prefer CSS transforms (`translate`, `scale`) for animations instead of properties that trigger layout (`top`, `left`, `width`).
- Use `will-change` for elements that will be animated.
- Use `ResizeObserver` instead of listening to `resize` with synchronous layout reads.

[↑ Back to top](#table-of-contents)

### 297. How do you balance performance vs feature delivery?

**Approach**: Show that you prioritize based on impact, data, and business goals. You don’t over‑optimize prematurely but make performance a non‑negotiable for critical user flows.

**Example**:
> “I treat performance as a feature, not an afterthought. I balance by:
> - **Setting performance budgets** early (e.g., bundle size, Time to Interactive). If a new feature threatens to exceed the budget, we discuss trade‑offs.
> - **Using data** – I check Lighthouse scores and Core Web Vitals. If a feature is critical for conversion (e.g., checkout), I allocate extra time for optimization.
> - **Deferring non‑critical optimizations** – for internal tools, we may accept slightly slower load times if it accelerates delivery, but we always track regressions.
> - **Iterative improvement** – we release a feature, monitor real‑user metrics, and then optimize if needed. This prevents over‑engineering while maintaining a fast baseline.”

[↑ Back to top](#table-of-contents)

### 298. How do you build PWAs with service workers, manifest files, and offline‑first experiences?

**Steps**:

[↑ Back to top](#table-of-contents)

### 299. How do you check if a property exists in an object?

A:
- `'prop' in obj` – checks own and inherited properties.
- `obj.hasOwnProperty('prop')` – checks own properties only.
- `Object.hasOwn(obj, 'prop')` – modern alternative.

[↑ Back to top](#table-of-contents)

### 300. How do you check page load behavior using browser developer tools? What metrics do you look at?

In Chrome DevTools **Network** tab:
- **Waterfall** – see resource loading order, identify slow requests.
- **DOMContentLoaded**, **Load** events – time to interactive.
- **Main thread activity** – long tasks that block rendering.

In **Performance** tab:
- Record page load; look for **Layout Shift** events, **Long Tasks**, and **FPS** during scroll.
- **Core Web Vitals** are shown in the **Timings** section.

**Metrics**:
- **TTFB** (Time to First Byte) – server response time.
- **FCP** (First Contentful Paint) – first text/image painted.
- **LCP** (Largest Contentful Paint) – main content loaded.
- **CLS** – layout shifts score.
- **INP** – interaction responsiveness.

[↑ Back to top](#table-of-contents)

### 301. How do you ensure accessibility beyond ARIA labels?

**Accessibility** goes beyond ARIA:
- **Semantic HTML**: Use correct elements (`<button>`, `<nav>`, `<header>`, etc.) rather than divs with roles.
- **Keyboard navigation**: Ensure all interactive elements are reachable with Tab, have visible focus indicators, and support Enter/Space for activation.
- **Screen reader announcements**: Use `aria-live` regions for dynamic updates. Provide alt text for images.
- **Color contrast**: Follow WCAG 2.1 AA standards for text and interactive elements.
- **Touch targets**: Ensure interactive elements are large enough (min 44×44px).
- **Testing**: Use automated tools (axe, Lighthouse) and manual testing with screen readers (NVDA, VoiceOver).
- **Focus management**: Manage focus after navigation or modal open/close.
- **Skip links**: Provide skip‑to‑content links for keyboard users.

[↑ Back to top](#table-of-contents)

### 302. How do you ensure code quality with testing? (unit, integration, e2e)

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

[↑ Back to top](#table-of-contents)

### 303. How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)

**Defense in depth**:

- **XSS (Cross‑Site Scripting)** – Use libraries that auto‑escape (React by default escapes content). Avoid `dangerouslySetInnerHTML`; if necessary, sanitize with DOMPurify. Set `Content-Security-Policy` (CSP) to restrict script sources.
- **CSP** – Implement strict CSP headers (e.g., `default-src 'self'`, `script-src 'self'`). Use nonces for inline scripts. Test with report‑only mode first.
- **CSRF (Cross‑Site Request Forgery)** – Use `SameSite=Lax` cookies, anti‑CSRF tokens, or double‑submit cookies. In SPAs, store tokens in memory (not localStorage) and use them in custom headers.
- **Token leakage** – Avoid storing access tokens in `localStorage` (vulnerable to XSS). Prefer httpOnly cookies with `Secure` and `SameSite=Strict`. If using JWT in memory, ensure it’s not exposed in URLs or logs.
- **Sensitive data in URLs** – Never put tokens or PII in URLs (they appear in server logs, referrer headers).
- **Third‑party scripts** – Carefully vet them; use Subresource Integrity (SRI) to ensure they aren’t tampered with.
- **Audit tools** – Use Lighthouse Security audits, OWASP ZAP, or npm packages like `helmet` for Express.

**Example**:
> “We migrated from storing JWT in localStorage to httpOnly cookies with SameSite=Lax, which eliminated XSS‑based token theft. We implemented a strict CSP with `script-src 'self'` and used nonces for dynamically injected scripts. For forms, we included CSRF tokens and validated them on the server. We also ran regular security scans using Snyk and automated OWASP ZAP in CI.”

[↑ Back to top](#table-of-contents)

### 304. How do you extract spacing, font sizes, and colors from Figma designs?

- **Spacing**: Use Figma’s inspect panel to get `margin`, `padding` values. I convert them to `rem` or CSS custom properties based on a design token system.
- **Font sizes**: Note the `px` values, convert to `rem` (with a base of 16px). Define type scale as variables (`--font-size-sm`, `--font-size-md`).
- **Colors**: Copy hex/rgba values; define as CSS variables (`--color-primary`, `--color-neutral-50`). Use opacity for shadows, overlays.
- **Design tokens**: Extract all into a `tokens.json` file and generate CSS variables via tooling (Style Dictionary). This ensures consistency across components.

[↑ Back to top](#table-of-contents)

### 305. How do you implement scalable code review workflows (linters, pre‑commit hooks, pair programming)?

**Goal**: Maintain code quality while keeping reviews efficient and collaborative.

**Layers**:

[↑ Back to top](#table-of-contents)

### 306. How do you manage shared libraries and dependencies in a monorepo?

**Goal**: Maximize code reuse while maintaining independent versioning and avoiding dependency hell.

**Approaches**:
- **Monorepo tools** – Use Nx, Turborepo, or pnpm workspaces. These provide dependency graph awareness, build caching, and affected‑only testing.
- **Structure** – Organize packages into `apps/` (applications) and `libs/` (shared code). Each library has its own `package.json`.
- **Versioning** – Decide between fixed versioning (all packages share a version) and independent versioning. Independent versioning allows teams to release only changed libraries, reducing coupling.
- **Dependency management** – Use `pnpm` to avoid duplication; it enforces strict dependency resolution. Use `npm audit` or `snyk` for vulnerability scanning.
- **Upgrades** – Automate dependency updates with Renovate or Dependabot. Test across all affected packages using CI.

**Key considerations**:
- **Avoid circular dependencies** – Enforce with tools like `madge` or ESLint rules.
- **Build caching** – Use Nx or Turborepo to skip rebuilding unchanged libraries.
- **Publishing** – Use changesets to manage versioning and generate changelogs. Publish packages to a registry (private or public).

**Example**:
> “We migrated to an Nx monorepo with 3 applications and 12 shared libraries. We used independent versioning and changesets to manage releases. Developers could run `nx affected:test` to test only changed packages, reducing CI time by 60%. We set up Renovate to keep dependencies updated, with automated PRs that triggered full CI.”

[↑ Back to top](#table-of-contents)

### 307. How do you mentor juniors through code walkthroughs, tech spikes, and 1:1s?

**Approach**: Describe specific mentoring practices that help juniors grow.

**Example**:
> “I believe in building confidence and ownership. For **code walkthroughs**, I ask juniors to explain their solution first, then I ask open‑ended questions like ‘What edge cases did you consider?’ or ‘How could we make this more testable?’ rather than simply pointing out issues. I also do live pair programming on complex tasks.
>
> **Tech spikes**: I assign small spikes (e.g., ‘evaluate React Query for data fetching’) with a clear goal and timebox. After the spike, we do a knowledge‑sharing session where they present findings. This builds research skills and ownership.
>
> **1:1s**: I keep them focused on career goals, blockers, and growth areas. I also encourage juniors to lead small features with my support, gradually increasing responsibility. I always celebrate their wins publicly to build confidence.”

[↑ Back to top](#table-of-contents)

### 308. How do you optimize images and fonts?

**Images**:
- Use `<img loading="lazy">` for off‑screen images.
- Serve WebP/AVIF with `<picture>` fallbacks.
- Set explicit `width` and `height` to avoid CLS.
- Use `srcset` and `sizes` for responsive images.
- Consider using a CDN that optimizes on‑the‑fly.

**Fonts**:
- Use `font-display: swap` in `@font-face`.
- Preload critical fonts: `<link rel="preload" as="font" href="/font.woff2" crossorigin>`
- Subset fonts to only needed characters.
- Use system fonts as fallback to avoid FOUT.

[↑ Back to top](#table-of-contents)

### 309. How do you profile and optimize a JavaScript animation that's dropping frames?

Use Chrome DevTools Performance tab to record frames. Look for long tasks (red bars) on the main thread. Move expensive calculations to a Worker. Avoid layout thrash — read all properties before writing. Use `transform` and `opacity` for GPU-accelerated animations. Use `requestAnimationFrame` for timing. Reduce paint area with `will-change: transform`.

[↑ Back to top](#table-of-contents)

### 310. How do you profile JavaScript performance?

Browser DevTools Performance panel: record, then analyze flame chart for long tasks, scripting time, rendering. Memory panel: take heap snapshots to find leaks. `console.time()` / `console.timeEnd()` for rough timing. `performance.mark()` / `performance.measure()` for precise custom measurements via Performance API.

[↑ Back to top](#table-of-contents)

### 311. How do you write JavaScript that works in both browser and Node.js?

Avoid environment-specific globals (`window`, `document`, `process`, `require`). Use feature detection. Use bundlers (Vite, Rollup) with appropriate targets. Write code against standard APIs (Fetch, Web Streams — now available in Node 18+). Publish CJS/ESM dual packages for library code.

[↑ Back to top](#table-of-contents)

### 312. How does JavaScript handle implicit coercion in arithmetic?

A: The `+` operator prefers string concatenation if either operand is a string; other arithmetic operators (`-`, `*`, `/`) coerce to numbers. Example: `'5' + 3` → `'53'`, `'5' - 3` → `2`.

[↑ Back to top](#table-of-contents)

### 313. How does JavaScript handle integer overflow?

JavaScript's `Number` type is a 64-bit IEEE 754 float. Safe integer range is `-(2^53 - 1)` to `2^53 - 1` (`Number.MAX_SAFE_INTEGER`). Beyond this, integers lose precision (no overflow/crash, just wrong values). Use `BigInt` for arbitrary-precision integers.

[↑ Back to top](#table-of-contents)

### 314. How does strict mode affect scoping and variable declaration?

A: Strict mode (`"use strict"`) prevents accidental globals, disallows duplicate parameter names, and changes the behavior of `this` in functions (defaults to `undefined` instead of `window`).

[↑ Back to top](#table-of-contents)

### 315. How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)

The browser rendering pipeline typically involves these steps (per frame):

[↑ Back to top](#table-of-contents)

### 316. How does the history API work for routing?

The History API (`window.history`) allows manipulation of the browser session history without reloading the page. Key methods:

- `history.pushState(state, title, url)` – adds a new entry.
- `history.replaceState(state, title, url)` – replaces current entry.
- `popstate` event – fires when the user navigates with back/forward.

Modern SPAs use this to implement client‑side routing: listening to `popstate`, updating the view, and using `pushState` for navigation.

[↑ Back to top](#table-of-contents)

### 317. How It Works (Follow the Link)

When you run `obj instanceof Constructor`, JavaScript plays a game of **"Follow the Link"**:

1. It looks at the object's hidden link (`__proto__`).
2. It follows that link up to the next blueprint, and the next, walking up the chain.
3. At each step, it asks: *"Is this blueprint the exact same as `Constructor.prototype`?"*
4. If it finds a match anywhere in the chain, it returns **`true`**. If it runs out of links and hits the end of the line (`null`), it returns **`false`**.

[↑ Back to top](#table-of-contents)

### 318. How JavaScript keeps track of multiple functions?

Think of the **Call Stack** as a stack of plates at a buffet.

JavaScript is a "single-threaded" language, which simply means it can only do **one thing at a time**. It only has one chef. Because it can only cook one recipe at a time, it needs a system to keep track of where it is in the process, especially when one function tells it to go run another function.

The Call Stack is that tracking system. It operates on a rule called **LIFO** (Last In, First Out). If you put a plate on top of a stack, that top plate is the very first one you have to take off.

Here is how JavaScript builds and dismantles this stack:

[↑ Back to top](#table-of-contents)

### 319. How to center an element horizontally? Vertically? Both?

**Horizontally**:
- Inline/inline‑block: `text-align: center` on parent.
- Block with fixed width: `margin: 0 auto`.
- Flexbox: `display: flex; justify-content: center` on parent.
- Grid: `display: grid; place-items: center` (centers both axes).

**Vertically**:
- Flexbox: `display: flex; align-items: center` on parent.
- Grid: `display: grid; align-items: center` (or `place-items: center` for both).
- Absolute positioning with transform:

```css
position: relative; /* on parent */
.child {
position: absolute;
top: 50%;
transform: translateY(-50%);
}
```

- For single line of text: `line-height` equal to container height.

**Both axes**:
- Flexbox: `display: flex; justify-content: center; align-items: center`.
- Grid: `display: grid; place-items: center`.
- Absolute + transform:

```css
.parent { position: relative; }
.child {
position: absolute;
top: 50%; left: 50%;
transform: translate(-50%, -50%);
}

```

[↑ Back to top](#table-of-contents)

### 320. How would you check cumulative layout shifts (CLS) on a page?

- **DevTools** – Open **Lighthouse**; run performance audit; CLS score appears under “Core Web Vitals”.
- **Performance tab** – Record page load, then look for “Layout Shift” events in the summary. Click to see which elements shifted.
- **Web Vitals library** – add `web-vitals` to your app and send CLS data to analytics.
- **Manual inspection** – resize viewport, throttle network to see if images or ads cause shifts.

**Mitigation**: Set explicit dimensions on images, reserve space for dynamic content, and avoid inserting content above existing UI.

[↑ Back to top](#table-of-contents)

### 321. How would you create a responsive layout with CSS Grid?

CSS Grid is a two‑dimensional system. For responsiveness:
- Use `grid-template-columns` with `repeat(auto-fit, minmax(min, max))`.
- Example: `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));` – creates as many columns as possible, each at least 250px wide, growing equally.
- Combine with media queries to adjust grid structure at different breakpoints.
- Use `fr` units for flexible sizing.

[↑ Back to top](#table-of-contents)

### 322. How would you improve Web Vitals (LCP, CLS, INP)?

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

[↑ Back to top](#table-of-contents)

### 323. Is JavaScript compiled or interpreted?

Technically both. Modern JS engines (V8, SpiderMonkey) use JIT (Just-In-Time) compilation. Code is first parsed into an AST, then compiled to bytecode, then hot paths are compiled to optimized machine code at runtime. JavaScript starts running your code immediately without making you wait (like an interpreter). But as it runs, it secretly figures out which parts of your code are used the most and fully translates them into lightning-fast machine code in the background (like a compiler).

[↑ Back to top](#table-of-contents)

### 324. Peak Traffic Failure: A critical UI feature fails during peak traffic – how do you mitigate?

**Immediate actions**:
- **Rollback** the recent deployment if it correlates with the failure.
- **Scale up** server resources (if backend) or enable more CDN edge nodes.
- **Feature flag** – disable the failing feature remotely to restore core functionality.
- **Switch to a fallback UI** – show a degraded experience (e.g., static placeholder) until the issue is resolved.

**Long‑term**:
- **Load testing** – simulate high traffic before release (tools: k6, Artillery).
- **Implement caching** at multiple layers (CDN, browser, server).
- **Use circuit breakers** for external API calls to prevent cascading failures.
- **Ensure the frontend can degrade gracefully** – e.g., show skeleton loaders, retry mechanisms.
- **Monitor** key metrics (error rates, latency) and set up alerts.

[↑ Back to top](#table-of-contents)

### 325. Style with CSS modules / styled‑components?

– ensure styles are encapsulated and themable.

[↑ Back to top](#table-of-contents)

### 326. UI Glitches: Users report intermittent UI glitches in different browsers – how do you troubleshoot?

**Process**:

[↑ Back to top](#table-of-contents)

### 327. What are `AbortController` and `AbortSignal`?

`AbortController` creates a controller with an associated `AbortSignal`. Passing the signal to `fetch` allows cancelling the request by calling `controller.abort()`. The signal can also be passed to any API that supports abort signals for consistent cancellation.

[↑ Back to top](#table-of-contents)

### 328. What are `Map` and `Set`?

`Map`: key-value pairs where keys can be any type (objects, functions). Ordered by insertion. Has `size`, `get`, `set`, `has`, `delete`, `forEach`. `Set`: collection of unique values of any type. Used for deduplication and membership tests. Both are iterable.

[↑ Back to top](#table-of-contents)

### 329. What are container queries?

Container queries allow styling of an element based on the size of its **parent container**, not the viewport. They enable true component‑level responsiveness.

Syntax:

```css
.component {
container-type: inline-size;
}
@container (min-width: 400px) {
.component .child {
display: flex;
}
}
```

This makes components reusable in different contexts.

[↑ Back to top](#table-of-contents)

### 330. What are CORS and SOP (Same-Origin Policy)?

SOP: browsers block JS from accessing resources from a different origin (protocol + domain + port). CORS: server opts in to cross-origin access via `Access-Control-Allow-Origin` headers. Preflight `OPTIONS` requests check permissions for non-simple requests.

[↑ Back to top](#table-of-contents)

### 331. What are CSS custom properties (variables)?

CSS custom properties (aka CSS variables) allow you to store values for reuse. They are defined with `--` prefix and accessed with `var()`.

Example:

```css
:root {
--primary-color: #3498db;
}
.button {
background-color: var(--primary-color);
}
```

They are dynamic and can be updated via JavaScript or media queries, making them powerful for theming.

[↑ Back to top](#table-of-contents)

### 332. What are flaky test detection strategies?

Flaky tests are those that sometimes pass and sometimes fail without code changes. Detection strategies:

- **Retry mechanism**: Run tests multiple times (e.g., 3–5) in CI; if they fail at least once but also pass, mark as flaky.
- **Statistical analysis**: Collect test run history; use tools like `flaky` (Python) or built‑in CI features (GitHub Actions, CircleCI) to flag tests with high variance.
- **Isolation**: Run tests in different orders, with random seed values (e.g., Jest’s `--randomize`), or with environment variations to reveal flakiness.
- **Screenshot diffs**: For visual tests, flaky may come from timing or non‑deterministic rendering. Use tools like Percy or Chromatic that handle baseline comparisons.
- **Quarantine**: Move flaky tests to a separate suite that doesn’t block deployments until fixed. Track them with a flaky test dashboard.

**Prevention**: Avoid hardcoded timers; use `waitFor` utilities; ensure mocks are properly reset; avoid relying on network state; use deterministic data.

[↑ Back to top](#table-of-contents)

### 333. What are generics in TypeScript?

A way to write reusable code that works with multiple types. `function identity<T>(arg: T): T { return arg; }`. The type parameter `T` is a placeholder filled in at usage. Used in containers, utilities, and APIs to maintain type safety without losing flexibility.

[↑ Back to top](#table-of-contents)

### 334. What are Node.js streams?

`Readable`, `Writable`, `Duplex`, `Transform` streams handle data in chunks rather than loading everything into memory. Pipe-able: `readStream.pipe(transformStream).pipe(writeStream)`. Essential for large file processing, HTTP responses, and real-time data.

[↑ Back to top](#table-of-contents)

### 335. What are preload, prefetch, and priority hints?

- **`<link rel="preload">`** – tells the browser to download a resource as soon as possible, for resources needed **now** (e.g., LCP image, critical font). It does not execute the resource.
- **`<link rel="prefetch">`** – downloads a resource for a future navigation (e.g., next page). Low priority; may be cached.
- **`<link rel="preconnect">`** – opens a connection to an origin (DNS, TCP, TLS) to reduce latency for future requests.
- **`<link rel="dns-prefetch">`** – resolves DNS only.
- **`fetchpriority` attribute** (experimental) – hints the browser about priority: `high` / `low` / `auto`. Can be used on images, iframes, etc.

[↑ Back to top](#table-of-contents)

### 336. What are property descriptors?

Each property has hidden attributes: `value`, `writable` (can be changed), `enumerable` (appears in loops), `configurable` (can be deleted/reconfigured). Access via `Object.getOwnPropertyDescriptor(obj, 'key')`. Set via `Object.defineProperty(obj, 'key', descriptor)`. Getters/setters replace `value` and `writable` with `get` and `set`.

[↑ Back to top](#table-of-contents)

### 337. What are semantic tags in HTML? Give examples.

Semantic tags clearly describe their meaning to both the browser and the developer. They improve accessibility, SEO, and code maintainability.

**Examples**:
- `<header>` – introductory content or navigation links.
- `<nav>` – navigation links.
- `<main>` – the dominant content of the `<body>`.
- `<article>` – self‑contained composition (blog post, news story).
- `<section>` – thematic grouping of content.
- `<aside>` – tangentially related content (sidebar).
- `<footer>` – footer for a section or page.
- `<figure>` and `<figcaption>` – illustrations with captions.
- `<mark>` – highlighted text.
- `<time>` – machine‑readable date/time.

[↑ Back to top](#table-of-contents)

### 338. What are snapshot tests?

`expect(value).toMatchSnapshot()` serializes the value and saves it to a file on first run. Subsequent runs compare against the snapshot. Fast to write but prone to false positives — only use for stable, simple outputs. Prefer explicit assertions for complex behavior.

[↑ Back to top](#table-of-contents)

### 339. What are symbols used for?

A: Symbols are unique and immutable primitives used as object property keys to avoid name collisions. They are not enumerable in `for...in` loops, but can be accessed via `Object.getOwnPropertySymbols()`.

[↑ Back to top](#table-of-contents)

### 340. What are the built-in error types?

`Error` (base), `TypeError` (wrong type), `ReferenceError` (variable not found), `SyntaxError` (invalid syntax, usually parse-time), `RangeError` (value out of range, e.g., stack overflow), `URIError` (malformed URI), `EvalError` (eval-related, rare). Each is a constructor — check with `err instanceof TypeError`.

[↑ Back to top](#table-of-contents)

### 341. What are the core principles of functional programming?

Pure functions, immutability, function composition, avoiding shared state and side effects, declarative style. FP makes code more predictable and testable. JavaScript is multi-paradigm — FP can be applied selectively.

[↑ Back to top](#table-of-contents)

### 342. What are the different ways to handle forms in JavaScript?

- **Traditional submit**: Listen to `submit` event on form, call `preventDefault`, collect values via `FormData` or accessing inputs by id.
- **FormData API**: `new FormData(formElement)` to get key‑value pairs.
- **Controlled components** (in React): state holds values.
- **Uncontrolled**: Access values via refs when needed.

[↑ Back to top](#table-of-contents)

### 343. What are the types of errors in JavaScript?

`SyntaxError` (code cannot be parsed), `ReferenceError` (undefined variable), `TypeError` (wrong type, null access), `RangeError` (value out of range), `URIError`, `EvalError`. All extend `Error`. Custom errors extend `Error` with a name property.

[↑ Back to top](#table-of-contents)

### 344. What are transducers?

Composable algorithmic transformations that are independent of the input source. Combine multiple `map`/`filter` operations into one pass over a collection, eliminating intermediate arrays. Used in performance-sensitive functional pipelines.

[↑ Back to top](#table-of-contents)

### 345. What are Web Vitals and why do they matter?

Core Web Vitals are a set of user‑centric metrics for web performance:

- **LCP (Largest Contentful Paint)** – loading performance; should be ≤2.5s.
- **CLS (Cumulative Layout Shift)** – visual stability; should be ≤0.1.
- **INP (Interaction to Next Paint)** – responsiveness; should be ≤200ms (replaces FID).

They matter because Google uses them as ranking signals, and they directly impact user experience, bounce rates, and conversions. Optimizing them improves overall site quality.

[↑ Back to top](#table-of-contents)

### 346. What does `bind` return?

`bind` returns a new function with `this` permanently bound to the specified value. The original function is unchanged. The bound function can also have arguments pre-filled (partial application). Calling `bind` multiple times only applies the first binding.

[↑ Back to top](#table-of-contents)

### 347. What is `any` vs `unknown` in TypeScript?

`any`: disables type checking entirely — you can do anything with it. Unsafe. `unknown`: type-safe alternative to `any`. You can't perform operations on `unknown` without first narrowing its type (type guard, assertion). Prefer `unknown` over `any` when type is truly unknown.

[↑ Back to top](#table-of-contents)

### 348. What is `BigInt` and when do you use it?

A numeric type for integers of arbitrary size: `9007199254740993n`. Append `n` to a literal or use `BigInt(value)`. Cannot be mixed with regular `Number` in operations. Use when: working with IDs from languages that use 64-bit integers, cryptography, precise large integer arithmetic, or any value exceeding `Number.MAX_SAFE_INTEGER`.

[↑ Back to top](#table-of-contents)

### 349. What is `Buffer` in Node.js?

A fixed-size allocation of raw binary data (a subclass of `Uint8Array`). Used when dealing with file I/O, network protocols, or binary data. `Buffer.from('hello', 'utf8')`, `buf.toString('hex')`. Distinct from ArrayBuffer/TypedArrays in the browser.

[↑ Back to top](#table-of-contents)

### 350. What is `console.table`, `console.group`, and `console.time`?

`console.table(arr)`: renders arrays/objects as a formatted table. `console.group(label)` / `console.groupEnd()`: collapses related logs. `console.time(label)` / `console.timeEnd(label)`: measures time between calls. `console.trace()`: prints current call stack.

[↑ Back to top](#table-of-contents)

### 351. What is `event.stopPropagation()` vs `event.preventDefault()`?

`stopPropagation()`: stops the event from bubbling up (or capturing down) to parent elements. `preventDefault()`: prevents the browser's default action (form submission, link navigation, checkbox toggle). They are independent — you can call one, both, or neither. `stopImmediatePropagation()` also prevents other listeners on the same element.

[↑ Back to top](#table-of-contents)

### 352. What is `globalThis`?

A standard way to access the global object regardless of environment. `window` in browsers, `global` in Node.js, `self` in Web Workers. `globalThis` normalizes these across environments for portable code.

[↑ Back to top](#table-of-contents)

### 353. What is `IntersectionObserver`?

Observes when an element enters or leaves the viewport (or a container). Callbacks fire when the intersection ratio crosses thresholds. Used for: lazy loading images, infinite scroll, triggering animations on scroll, analytics (view tracking).

[↑ Back to top](#table-of-contents)

### 354. What is `Object.freeze()` vs `Object.seal()`?

`Object.freeze(obj)`: prevents adding, deleting, or modifying any properties. Shallow — nested objects can still be mutated. `Object.seal(obj)`: prevents adding or deleting properties, but allows modifying existing ones. Use freeze for truly immutable objects; use seal when shape must be fixed but values can change.

[↑ Back to top](#table-of-contents)

### 355. What is `ResizeObserver`?

Watches when an element's size changes and fires a callback. Better than `window.resize` (which fires for the whole window). Used for responsive components that need to react to their own size — container queries in JS.

[↑ Back to top](#table-of-contents)

### 356. What is a functor?

An object with a `map` method that applies a function to the value inside it and returns the same type. Arrays are functors. Promises are almost functors (`.then`). Functors allow you to transform values inside containers without extracting them — a key FP concept.

[↑ Back to top](#table-of-contents)

### 357. What is a timing attack and how does it relate to JavaScript?

Inferring secret information from the time it takes to perform operations. String comparison with `===` short-circuits on the first mismatch — timing varies by how much matches. Use constant-time comparison for sensitive values (HMAC verification). `crypto.timingSafeEqual` in Node.js.

[↑ Back to top](#table-of-contents)

### 358. What is a union type vs intersection type?

Union (`A | B`): the value can be type A OR type B. Use with type guards to narrow. Intersection (`A & B`): the value must satisfy BOTH type A AND type B — combines all properties. Union is OR; intersection is AND.

[↑ Back to top](#table-of-contents)

### 359. What is atomic design methodology?

Atomic design is a methodology for creating design systems with five levels:

- **Atoms** – basic HTML elements (button, input, label) with styles.
- **Molecules** – groups of atoms functioning together (search bar: input + button).
- **Organisms** – distinct, complex UI sections (header, product card).
- **Templates** – page‑level structures without real content.
- **Pages** – templates with actual content.

It promotes reusability, consistency, and a clear hierarchy. In code, atoms become base components, molecules compose them, etc.

[↑ Back to top](#table-of-contents)

### 360. What is chaos engineering for frontend?

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

[↑ Back to top](#table-of-contents)

### 361. What is clickjacking and how do you prevent it?

An attack where a transparent iframe overlays a legitimate site, tricking users into clicking on hidden elements. Prevention: `X-Frame-Options: DENY` or `SAMEORIGIN` HTTP header, or CSP `frame-ancestors 'none'` directive.

[↑ Back to top](#table-of-contents)

### 362. What is code coverage and what metrics matter?

Percentage of code executed during tests: line, branch, function, statement coverage. Branch coverage is most meaningful — tests every code path. 100% coverage doesn't guarantee bug-free code; it only shows what was executed, not what was asserted correctly.

[↑ Back to top](#table-of-contents)

### 363. What is code coverage?

A metric showing what percentage of your code is executed by tests. Types: line coverage, branch coverage (if/else paths), function coverage, statement coverage. Run with `jest --coverage`. 100% coverage doesn't mean bug-free — focus on meaningful tests, not chasing numbers.

[↑ Back to top](#table-of-contents)

### 364. What is Content Security Policy (CSP)?

An HTTP header that tells browsers which sources of content are allowed (scripts, styles, images, fonts). Mitigates XSS by blocking inline scripts and unauthorized external scripts. `Content-Security-Policy: script-src 'self' https://trusted.com`. Use `nonce` or `hash` for necessary inline scripts.

[↑ Back to top](#table-of-contents)

### 365. What is CORS?

Cross-Origin Resource Sharing — a browser security mechanism that restricts cross-origin HTTP requests. Servers must send `Access-Control-Allow-Origin` headers to allow cross-origin access. Simple requests (GET, POST with certain content-types) go through; complex requests trigger a preflight `OPTIONS` request. CORS is a browser restriction — it doesn't apply to server-to-server requests.

[↑ Back to top](#table-of-contents)

### 366. What is CSRF (Cross-Site Request Forgery)?

Tricks authenticated users into making unintended requests to a site they're logged into. Prevention: CSRF tokens (unique per session, validated server-side), `SameSite=Strict` or `SameSite=Lax` cookies, check `Origin`/`Referer` headers, avoid side effects from GET requests.

[↑ Back to top](#table-of-contents)

### 367. What is debouncing?

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

[↑ Back to top](#table-of-contents)

### 368. What is Flexbox? Explain main concepts.

Flexbox is a one‑dimensional layout model that arranges items in rows or columns with powerful alignment and distribution capabilities.

**Main concepts**:
- **Container** with `display: flex`.
- **Main axis** – defined by `flex-direction` (row or column).
- **Cross axis** – perpendicular to the main axis.
- **Properties on container**:
- `flex-direction`: row | row-reverse | column | column-reverse.
- `justify-content`: alignment along main axis (flex-start, center, space-between, etc.).
- `align-items`: alignment along cross axis (stretch, center, baseline, etc.).
- `flex-wrap`: wrap items to multiple lines.
- `gap`: space between items.
- **Properties on items**:
- `flex-grow`: how much an item can grow.
- `flex-shrink`: how much it can shrink.
- `flex-basis`: initial size.
- `align-self`: override container’s `align-items`.

[↑ Back to top](#table-of-contents)

### 369. What is function composition vs piping?

Both combine functions. **Composition** (`compose`): right-to-left — `compose(f, g)(x)` = `f(g(x))`. **Piping** (`pipe`): left-to-right — `pipe(g, f)(x)` = `f(g(x))`. Pipe is more readable for most developers (data flows left to right). Both create new functions from combining existing ones.

[↑ Back to top](#table-of-contents)

### 370. What is functional programming?

A programming paradigm treating computation as evaluation of mathematical functions. Key principles: pure functions, immutability, no side effects, function composition, declarative style. JavaScript supports both OOP and FP — you can mix them. Libraries: Ramda, Lodash/fp.

[↑ Back to top](#table-of-contents)

### 371. What is immutability and how do you achieve it in JavaScript?

Never mutating data — always creating new values. Use spread/`Object.assign` for objects, `map`/`filter`/`slice` for arrays. Libraries: Immer (mutable-looking updates that produce immutable results). `Object.freeze` for shallow freezing.

[↑ Back to top](#table-of-contents)

### 372. What is JavaScript and where can it run?

JavaScript is a high-level, dynamic, interpreted programming language originally designed for browser scripting. Today it runs in browsers (via JS engines like V8 in Chrome), on servers (Node.js), in mobile apps (React Native), desktop apps (Electron), and IoT devices – anywhere a JS runtime is embedded.

[↑ Back to top](#table-of-contents)

### 373. What is Jest and what does it provide?

A zero-config testing framework: test runner, assertion library (`expect`), mocking (`jest.fn()`, `jest.mock()`), snapshot testing, code coverage. Works for both browser and Node.js code. The most popular JS testing solution.

[↑ Back to top](#table-of-contents)

### 374. What is method chaining?

Returning `this` from methods to allow calling multiple methods on the same object in sequence: `builder.setName('x').setAge(5).build()`. Common in jQuery, Lodash, query builders, and the Builder pattern. Makes code more fluent and readable.

[↑ Back to top](#table-of-contents)

### 375. What is npm and what is `package.json`?

npm (Node Package Manager): the default package manager for Node.js. Manages project dependencies, scripts, and publishing. `package.json`: manifest file containing project metadata, dependencies, devDependencies, scripts (`start`, `test`, `build`), version, and configuration for tools.

[↑ Back to top](#table-of-contents)

### 376. What is property descriptor?

A: An object that describes attributes of a property: `value`, `writable`, `enumerable`, `configurable`. Can be retrieved with `Object.getOwnPropertyDescriptor(obj, prop)`.

[↑ Back to top](#table-of-contents)

### 377. What is property-based testing?

Instead of specific inputs, you define properties that should hold for any input. A library (fast-check, JSVerify) generates hundreds of random test cases. Excellent for finding edge cases you wouldn't think to write manually. Useful for pure functions and data transformation logic.

[↑ Back to top](#table-of-contents)

### 378. What is strict mode?

`'use strict'` at the top of a file or function enables strict mode. It prevents use of undeclared variables, disables `with`, makes `this` undefined in regular functions (not `window`), disallows duplicate parameter names, and throws on otherwise-silent errors.

[↑ Back to top](#table-of-contents)

### 379. What is the `Atomics` API and when do you need it?

`Atomics` provides atomic operations on `SharedArrayBuffer` for safe inter-thread communication in Worker threads. Without atomics, concurrent writes cause data races. `Atomics.wait`, `Atomics.notify` implement mutex-like synchronization. Rarely needed — only for low-level concurrent algorithms in Workers.

[↑ Back to top](#table-of-contents)

### 380. What is the `Error` object?

Has properties: `name` (type of error, e.g., `'TypeError'`), `message` (description), `stack` (stack trace string, non-standard but universally supported), `cause` (ES2022 — error that caused this one, for chaining). Create with `new Error('message')`.

[↑ Back to top](#table-of-contents)

### 381. What is the Command pattern?

Encapsulates a request as an object, enabling undo/redo, queuing, logging, and parameterization of operations. In JS: `{ execute: fn, undo: fn }`. Used in text editors, Redux (actions are commands), and task queues.

[↑ Back to top](#table-of-contents)

### 382. What is the Decorator pattern?

Wraps an object or function to extend its behavior without modifying the original. In JS: higher-order functions (`withLogging(fn)`), ES decorators (TC39 proposal, used in TypeScript/Angular), or manually wrapping objects. Used for logging, caching, authentication, validation.

[↑ Back to top](#table-of-contents)

### 383. What is the difference between `innerHTML`, `textContent`, and `innerText`?

`innerHTML`: gets/sets HTML content (parses HTML — XSS risk with user input). `textContent`: gets/sets text content of an element and all descendants (no HTML parsing — safe, fast, includes hidden elements). `innerText`: like `textContent` but respects CSS (doesn't include hidden elements, triggers layout). Use `textContent` for safety and performance.

[↑ Back to top](#table-of-contents)

### 384. What is the difference between `interface` and `type`?

`interface`: can be merged (declaration merging), better for object shapes and OOP. `type`: more flexible — can represent primitives, unions, intersections, tuples, mapped types. Both can extend each other (`interface extends type` and vice versa). For objects, either works; prefer `interface` for public APIs, `type` for complex type math.

[↑ Back to top](#table-of-contents)

### 385. What is the difference between `Object.assign()` and spread?

Both create shallow copies/merges. Differences: `Object.assign` invokes setters on the target; spread doesn't. `Object.assign` mutates the target; spread always creates a new object. `Object.assign` copies inherited enumerable properties from the source if they're own properties; spread copies own enumerable properties. For most cases, they're interchangeable.

[↑ Back to top](#table-of-contents)

### 386. What is the difference between `reduce` and `reduceRight`?

A: Both accumulate values; `reduce` goes left-to-right, `reduceRight` goes right-to-left.

[↑ Back to top](#table-of-contents)

### 387. What is the difference between `require` resolution and ESM resolution in Node.js?

`require` looks for `.js`, then `index.js`, then checks `package.json main`. ESM requires explicit file extensions and respects the `exports` field. ESM cannot `require()` synchronously. Mixing both requires careful package configuration.

[↑ Back to top](#table-of-contents)

### 388. What is the difference between a statement and an expression?

An expression produces a value (`2 + 2`, `fn()`, `x ? a : b`). A statement performs an action (`if`, `for`, `return`, `throw`). Some constructs can be either — function declarations are statements; function expressions are expressions.

[↑ Back to top](#table-of-contents)

### 389. What is the difference between CSR, SSR, SSG, and ISR?

- **CSR (Client‑Side Rendering)**: JavaScript runs in the browser to render the UI. Initial HTML is minimal. Good for dynamic, interactive apps but can hurt SEO and initial load.
- **SSR (Server‑Side Rendering)**: Renders HTML on the server per request. Fast initial paint, better SEO. Used in Next.js `getServerSideProps`.
- **SSG (Static Site Generation)**: Pre‑renders HTML at build time. Very fast, ideal for content that doesn’t change often (blogs, marketing pages). Next.js `getStaticProps`.
- **ISR (Incremental Static Regeneration)**: Builds static pages but can regenerate them in the background after deployment. Combines benefits of SSG and SSR. Next.js `revalidate` option.

[↑ Back to top](#table-of-contents)

### 390. What is the difference between debounce and throttle?

Debounce: waits for a pause in calls — only fires once after the activity stops. Good for: search input, form validation on type. Throttle: fires at regular intervals during continuous activity — guarantees execution frequency. Good for: scroll position tracking, drag events, game loops.

[↑ Back to top](#table-of-contents)

### 391. What is the difference between named and namespace imports?

Named: `import {foo, bar} from './mod'` — imports specific exports. Namespace: `import * as mod from './mod'` — imports all exports as properties of a single object. Namespace imports prevent tree shaking of unused exports.

[↑ Back to top](#table-of-contents)

### 392. What is the difference between pass-by-value and pass-by-reference?

Primitives are passed by value — a copy is made. Objects (including arrays) are passed by reference — both the caller and the function reference the same object in memory. However, reassigning the parameter doesn't affect the original; only mutations do.

[↑ Back to top](#table-of-contents)

### 393. What is the History API?

`history.pushState(state, title, url)` — adds an entry to the browser's history stack and changes the URL without a page reload. `history.replaceState()` — replaces current entry. `window.onpopstate` — fires when user navigates back/forward. Foundation of client-side routing in SPAs.

[↑ Back to top](#table-of-contents)

### 394. What is the JavaScript engine and how does it work?

A JavaScript engine is like a smart translator and office manager for your code. It does three main things:

Translates & Runs: It reads your text code, converts it into a quick shorthand (bytecode) the computer understands, and runs it immediately.

Speeds Up (JIT): It watches your code as it runs. If it sees a specific action you repeat constantly, it instantly upgrades that part into ultra-fast machine code.

Cleans Up (Garbage Collection): It holds onto the data you are currently using, and automatically throws away old data you no longer need so your computer doesn't slow down or crash.

[↑ Back to top](#table-of-contents)

### 395. What is the purpose of the meta tags?

`<meta>` tags provide metadata about the HTML document. Common uses:

- Character set: `<meta charset="UTF-8">`
- Viewport for responsive design: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Description for SEO: `<meta name="description" content="...">`
- Author: `<meta name="author" content="...">`
- Refresh/redirect: `<meta http-equiv="refresh" content="5;url=https://...">`

[↑ Back to top](#table-of-contents)

### 396. What is the ResizeObserver?

`ResizeObserver` reports changes to the dimensions of an element. It is useful for responsive components that need to react to size changes (e.g., charts, adaptive layouts). Unlike `window.resize` events, it targets specific elements and works cross‑browser.

[↑ Back to top](#table-of-contents)

### 397. What is the Strategy pattern?

Defines a family of algorithms, encapsulates each, and makes them interchangeable. In JS, pass different functions to the same interface: `sort(arr, ascendingStrategy)` vs `sort(arr, descendingStrategy)`. Eliminates complex if/else chains, follows Open/Closed Principle.

[↑ Back to top](#table-of-contents)

### 398. What is the testing pyramid for JavaScript?

Unit tests (fast, many): individual functions, modules. Integration tests (medium): interactions between units, API calls. E2E tests (slow, few): full browser flows. Focus the most effort on integration tests — they give the best coverage-to-cost ratio for most JS apps.

[↑ Back to top](#table-of-contents)

### 399. What is TypeScript and how does it relate to JavaScript?

TypeScript is a superset of JavaScript — all valid JS is valid TypeScript. It adds static type annotations that are removed at compile time (transpiled to plain JS). Provides compile-time type checking, better IDE support, and self-documenting code. Maintained by Microsoft.

[↑ Back to top](#table-of-contents)

### 400. What is unit testing?

Testing individual functions or modules in isolation. Fast, focused, no external dependencies (use mocks/stubs). Verifies that a unit of code produces the correct output for a given input. Foundation of the testing pyramid. Tools: Jest, Vitest, Mocha.

[↑ Back to top](#table-of-contents)

### 401. What is visual regression testing? How would you implement it?

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

[↑ Back to top](#table-of-contents)

### 402. What is XSS (Cross-Site Scripting) and how do you prevent it?

Injecting malicious scripts into pages viewed by other users. Prevention: never insert user-controlled HTML via `innerHTML` — use `textContent`. Use Content Security Policy (CSP) headers. Sanitize with DOMPurify when HTML is required. Escape output server-side.

[↑ Back to top](#table-of-contents)

### 403. What is your approach to multi‑tenant frontend applications?

**Multi‑tenancy**: Single codebase serving multiple tenants (organizations) with custom branding, configuration, and sometimes data isolation.

**Approach**:
- **Theming**: Use CSS variables or dynamic theme loading based on tenant identifier.
- **Configuration**: Fetch tenant config at runtime (e.g., `/api/tenant/config`) and store in context. Adjust UI elements (logos, feature flags).
- **Routing**: Use subdomains (tenant.myapp.com) or paths (`/tenant/:id`) to determine tenant.
- **Data isolation**: Ensure all API requests include tenant ID (e.g., in headers). Use authentication that scopes data.
- **Build**: Single build serving all tenants. Avoid per‑tenant builds for scalability.

[↑ Back to top](#table-of-contents)

### 404. What is your framework for identifying, prioritizing, and reducing technical debt?

**Goal**: Balance short‑term delivery with long‑term maintainability.

**Framework**:

[↑ Back to top](#table-of-contents)

### 405. What is your strategy for fluid responsive design using CSS Grid, Flexbox, and container queries?

- **Flexbox** – for one‑dimensional layouts (navigation bars, card rows). Use `flex-wrap`, `gap`, and `align-items`.
- **CSS Grid** – for two‑dimensional layouts (page grids, complex components). Use `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` for responsive cards.
- **Container queries** – when a component’s layout should change based on its own container size, not the viewport. Useful for reusable components. Example: `@container (min-width: 400px) { .card { flex-direction: row; } }`.
- **Fluid typography** – use `clamp()` with viewport units (e.g., `font-size: clamp(1rem, 2vw, 2rem)`).
- **Responsive images** – use `<picture>` and `srcset` with `sizes`.

**Approach**: Design for mobile first, then use media queries to enhance larger screens. Use relative units (rem, %, vw). Test on real devices.

[↑ Back to top](#table-of-contents)

### 406. What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)

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

[↑ Back to top](#table-of-contents)

### 407. What tools and practices do you use for frontend observability, error tracking, and performance monitoring?

**Observability**:
- **Logging** – Use structured logging (e.g., `console.log` with `winston` or `pino` in Node). In browsers, send logs to a service like Datadog or LogRocket.
- **Distributed tracing** – If backend uses tracing, propagate trace IDs to frontend to correlate requests.

**Error tracking**:
- **Sentry** – Captures JavaScript errors, breadcrumbs, user context. Integrates with React to show component stack traces.
- **Source maps** – Upload to Sentry during build to get readable stack traces.

**Performance monitoring**:
- **Real User Monitoring (RUM)** – Use tools like Datadog RUM, New Relic Browser, or Google Analytics 4 (with Core Web Vitals). Track Core Web Vitals (LCP, CLS, INP) and custom metrics (e.g., time to interactive).
- **Lighthouse CI** – Run in CI to catch regressions before deployment.
- **Web Vitals library** – Use `web-vitals` to send metrics to your analytics backend.

**Alerts**:
- Set up alerts for error rate spikes, high LCP, or increased bundle size. Use tools like Sentry’s alert rules or Datadog monitors.

**Example**:
> “We integrated Sentry for error tracking, uploading source maps in CI. We used Datadog RUM to track Core Web Vitals and custom business timings (e.g., time to checkout). We created dashboards for each team and set up alerts for 5xx errors and when LCP exceeded 2.5 seconds for more than 5% of sessions. This helped us catch a major performance regression within minutes of deployment.”

[↑ Back to top](#table-of-contents)

### 408. What tools do you use for frontend performance analysis? (Lighthouse, WebPageTest, Chrome DevTools)

- **Lighthouse** – quick audits for performance, accessibility, SEO. Integrated in Chrome DevTools and CI.
- **WebPageTest** – deep analysis from multiple locations, filmstrip view, first‑view/repeat‑view comparisons. Great for advanced diagnostics.
- **Chrome DevTools** – Performance tab for detailed runtime analysis, Network tab for resource loading, Memory tab for heap snapshots.
- **Real User Monitoring (RUM)** – Datadog RUM, New Relic Browser, or custom instrumentation with Web Vitals library.
- **Bundle analysis** – webpack‑bundle‑analyzer, Next.js bundle analyzer to identify large chunks.
- **Lighthouse CI** – run Lighthouse in GitHub Actions to catch regressions before deployment.

**Workflow**: Use local DevTools during development, Lighthouse CI on every PR, and RUM in production to monitor real user experience.

Below are the questions with detailed, practical answers covering Node.js, React, and Redux. These reflect real‑world debugging and optimization approaches used in production.

[↑ Back to top](#table-of-contents)

### 409. When NOT to use JavaScript: CPU-heavy tasks, long-running blocking logic – use backend or workers.

**Scenarios**:
- **Large data processing** (sorting, filtering, complex calculations) – offload to Web Workers or the backend.
- **Image/video processing** – use backend services or Canvas + WebGL with off‑thread rendering.
- **Intensive animations** – use CSS animations/transitions instead of JS, or requestAnimationFrame with careful batching.
- **Real‑time ML inference** – consider WebAssembly or backend.

[↑ Back to top](#table-of-contents)

### 410. When NOT to use JavaScript?

CPU-heavy tasks, long-running blocking logic – use backend or workers.

[↑ Back to top](#table-of-contents)

### 411. When to use?

- Content changes frequently (e.g., social media feed, e‑commerce product page with dynamic data).
- SEO is critical and content is user‑specific.

**SSG (Static Site Generation)**:
- Build‑time generation of HTML files.
- Fastest performance, ideal for content that rarely changes (e.g., blog, documentation).

**ISR (Incremental Static Regeneration)**:
- Combines SSG and SSR: static pages can be updated after deployment without a full rebuild.
- Good for sites with large number of pages that need occasional updates (e.g., e‑commerce product pages).

[↑ Back to top](#table-of-contents)
