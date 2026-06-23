# 🟨 JavaScript – Comprehensive Interview Question Bank

**300+ Questions across 20 sections**

*Fundamentals · Types · Scope · Closures · Async · Prototypes · ES6+ · DOM · Patterns · Performance · Security*

---

## 📋 Table of Contents

### Section 1: JavaScript Fundamentals
| # | Question |
|---|----------|
| Q1 | [What is JavaScript and where can it run?](#q1-what-is-javascript-and-where-can-it-run) |
| Q2 | [What is the difference between JavaScript and ECMAScript?](#q2-what-is-the-difference-between-javascript-and-ecmascript) |
| Q3 | [Is JavaScript compiled or interpreted?](#q3-is-javascript-compiled-or-interpreted) |
| Q4 | [What is the JavaScript engine and how does it work?](#q4-what-is-the-javascript-engine-and-how-does-it-work) |
| Q5 | [What is single-threaded execution in JavaScript?](#q5-what-is-single-threaded-execution-in-javascript) |
| Q6 | [What is the difference between `null` and `undefined`?](#q6-what-is-the-difference-between-null-and-undefined) |
| Q7 | [What are the primitive data types in JavaScript?](#q7-what-are-the-primitive-data-types-in-javascript) |
| Q8 | [What is the difference between `==` and `===`?](#q8-what-is-the-difference-between--and-) |
| Q9 | [What is type coercion?](#q9-what-is-type-coercion) |
| Q10 | [What is `NaN` and how do you check for it?](#q10-what-is-nan-and-how-do-you-check-for-it) |
| Q11 | [What is the `typeof` operator?](#q11-what-is-the-typeof-operator) |
| Q12 | [What are truthy and falsy values?](#q12-what-are-truthy-and-falsy-values) |
| Q13 | [What is the difference between `var`, `let`, and `const`?](#q13-what-is-the-difference-between-var-let-and-const) |
| Q14 | [What is hoisting?](#q14-what-is-hoisting) |
| Q15 | [What is the Temporal Dead Zone (TDZ)?](#q15-what-is-the-temporal-dead-zone-tdz) |

### Section 2: Scope, Closures & Execution Context
| # | Question |
|---|----------|
| Q16 | [What is scope in JavaScript?](#q16-what-is-scope-in-javascript) |
| Q17 | [What is the difference between global, function, and block scope?](#q17-what-is-the-difference-between-global-function-and-block-scope) |
| Q18 | [What is the scope chain?](#q18-what-is-the-scope-chain) |
| Q19 | [What is lexical scope?](#q19-what-is-lexical-scope) |
| Q20 | [What is a closure?](#q20-what-is-a-closure) |
| Q21 | [What are practical uses of closures?](#q21-what-are-practical-uses-of-closures) |
| Q22 | [What is a closure memory leak and how do you avoid it?](#q22-what-is-a-closure-memory-leak-and-how-do-you-avoid-it) |
| Q23 | [What is an execution context?](#q23-what-is-an-execution-context) |
| Q24 | [What is the call stack?](#q24-what-is-the-call-stack) |
| Q25 | [What is the difference between function scope and block scope?](#q25-what-is-the-difference-between-function-scope-and-block-scope) |
| Q26 | [What is an IIFE and why is it used?](#q26-what-is-an-iife-and-why-is-it-used) |
| Q27 | [Situation: Classic loop closure bug – `var` in a for loop.](#q27-situation-classic-loop-closure-bug--var-in-a-for-loop) |
| Q28 | [What is variable shadowing?](#q28-what-is-variable-shadowing) |

### Section 3: Functions
| # | Question |
|---|----------|
| Q29 | [What is the difference between function declaration and function expression?](#q29-what-is-the-difference-between-function-declaration-and-function-expression) |
| Q30 | [What are arrow functions and how do they differ from regular functions?](#q30-what-are-arrow-functions-and-how-do-they-differ-from-regular-functions) |
| Q31 | [What is a first-class function?](#q31-what-is-a-first-class-function) |
| Q32 | [What is a higher-order function?](#q32-what-is-a-higher-order-function) |
| Q33 | [What is a pure function?](#q33-what-is-a-pure-function) |
| Q34 | [What are default parameters?](#q34-what-are-default-parameters) |
| Q35 | [What is the rest parameter (`...args`)?](#q35-what-is-the-rest-parameter-args) |
| Q36 | [What is the `arguments` object?](#q36-what-is-the-arguments-object) |
| Q37 | [What is function currying?](#q37-what-is-function-currying) |
| Q38 | [What is function composition?](#q38-what-is-function-composition) |
| Q39 | [What is memoization?](#q39-what-is-memoization) |
| Q40 | [What is a callback function?](#q40-what-is-a-callback-function) |
| Q41 | [What is the difference between a method and a function?](#q41-what-is-the-difference-between-a-method-and-a-function) |
| Q42 | [What is a generator function?](#q42-what-is-a-generator-function) |

### Section 4: `this` Keyword
| # | Question |
|---|----------|
| Q43 | [What is `this` in JavaScript?](#q43-what-is-this-in-javascript) |
| Q44 | [What are the four rules of `this` binding?](#q44-what-are-the-four-rules-of-this-binding) |
| Q45 | [How does `this` work in arrow functions?](#q45-how-does-this-work-in-arrow-functions) |
| Q46 | [What is explicit binding with `call`, `apply`, and `bind`?](#q46-what-is-explicit-binding-with-call-apply-and-bind) |
| Q47 | [What is the difference between `call` and `apply`?](#q47-what-is-the-difference-between-call-and-apply) |
| Q48 | [What does `bind` return?](#q48-what-does-bind-return) |
| Q49 | [What is `this` in a class?](#q49-what-is-this-in-a-class) |
| Q50 | [Situation: `this` is `undefined` or `window` inside a callback – why?](#q50-situation-this-is-undefined-or-window-inside-a-callback--why) |

### Section 5: Prototypes & Inheritance
| # | Question |
|---|----------|
| Q51 | [What is a prototype in JavaScript?](#q51-what-is-a-prototype-in-javascript) |
| Q52 | [What is the prototype chain?](#q52-what-is-the-prototype-chain) |
| Q53 | [What is the difference between `__proto__` and `prototype`?](#q53-what-is-the-difference-between-__proto__-and-prototype) |
| Q54 | [What is `Object.create()`?](#q54-what-is-objectcreate) |
| Q55 | [What is prototypal inheritance?](#q55-what-is-prototypal-inheritance) |
| Q56 | [What are ES6 classes and how do they relate to prototypes?](#q56-what-are-es6-classes-and-how-do-they-relate-to-prototypes) |
| Q57 | [What is the difference between classical and prototypal inheritance?](#q57-what-is-the-difference-between-classical-and-prototypal-inheritance) |
| Q58 | [What is `instanceof` and how does it work?](#q58-what-is-instanceof-and-how-does-it-work) |
| Q59 | [What is `hasOwnProperty`?](#q59-what-is-hasownproperty) |
| Q60 | [What is `Object.getPrototypeOf()`?](#q60-what-is-objectgetprototypeof) |

### Section 6: Objects & Arrays
| # | Question |
|---|----------|
| Q61 | [What are the ways to create objects in JavaScript?](#q61-what-are-the-ways-to-create-objects-in-javascript) |
| Q62 | [What is destructuring?](#q62-what-is-destructuring) |
| Q63 | [What is the spread operator?](#q63-what-is-the-spread-operator) |
| Q64 | [What is the difference between shallow copy and deep copy?](#q64-what-is-the-difference-between-shallow-copy-and-deep-copy) |
| Q65 | [How do you deep clone an object?](#q65-how-do-you-deep-clone-an-object) |
| Q66 | [What are computed property names?](#q66-what-are-computed-property-names) |
| Q67 | [What is `Object.keys()`, `Object.values()`, `Object.entries()`?](#q67-what-is-objectkeys-objectvalues-objectentries) |
| Q68 | [What is `Object.freeze()` vs `Object.seal()`?](#q68-what-is-objectfreeze-vs-objectseal) |
| Q69 | [What are property descriptors?](#q69-what-are-property-descriptors) |
| Q70 | [What is optional chaining (`?.`)?](#q70-what-is-optional-chaining-) |
| Q71 | [What is the nullish coalescing operator (`??`)?](#q71-what-is-the-nullish-coalescing-operator-) |
| Q72 | [What are the most important array methods?](#q72-what-are-the-most-important-array-methods) |
| Q73 | [What is the difference between `map`, `filter`, and `reduce`?](#q73-what-is-the-difference-between-map-filter-and-reduce) |
| Q74 | [What is the difference between `forEach` and `map`?](#q74-what-is-the-difference-between-foreach-and-map) |
| Q75 | [What is array and object destructuring with defaults?](#q75-what-is-array-and-object-destructuring-with-defaults) |
| Q76 | [How do you remove duplicates from an array?](#q76-how-do-you-remove-duplicates-from-an-array) |
| Q77 | [What is the difference between `find` and `filter`?](#q77-what-is-the-difference-between-find-and-filter) |
| Q78 | [What does `flat()` and `flatMap()` do?](#q78-what-does-flat-and-flatmap-do) |

### Section 7: Asynchronous JavaScript
| # | Question |
|---|----------|
| Q79 | [What is synchronous vs asynchronous code?](#q79-what-is-synchronous-vs-asynchronous-code) |
| Q80 | [What is the Event Loop?](#q80-what-is-the-event-loop) |
| Q81 | [What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?](#q81-what-are-the-call-stack-web-apis-callback-queue-and-microtask-queue) |
| Q82 | [What is the difference between macrotasks and microtasks?](#q82-what-is-the-difference-between-macrotasks-and-microtasks) |
| Q83 | [What is a callback and what is callback hell?](#q83-what-is-a-callback-and-what-is-callback-hell) |
| Q84 | [What is a Promise?](#q84-what-is-a-promise) |
| Q85 | [What are the states of a Promise?](#q85-what-are-the-states-of-a-promise) |
| Q86 | [What is promise chaining?](#q86-what-is-promise-chaining) |
| Q87 | [What is `Promise.all()`?](#q87-what-is-promiseall) |
| Q88 | [What is `Promise.allSettled()`?](#q88-what-is-promiseallsettled) |
| Q89 | [What is `Promise.race()`?](#q89-what-is-promiserace) |
| Q90 | [What is `Promise.any()`?](#q90-what-is-promiseany) |
| Q91 | [What is `async/await`?](#q91-what-is-asyncawait) |
| Q92 | [How do you handle errors with `async/await`?](#q92-how-do-you-handle-errors-with-asyncawait) |
| Q93 | [What happens if you `await` a non-Promise value?](#q93-what-happens-if-you-await-a-non-promise-value) |
| Q94 | [What is the difference between sequential and parallel async execution?](#q94-what-is-the-difference-between-sequential-and-parallel-async-execution) |
| Q95 | [Situation: Output the order of `setTimeout`, Promise, and synchronous code.](#q95-situation-output-the-order-of-settimeout-promise-and-synchronous-code) |
| Q96 | [What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?](#q96-what-is-settimeout-vs-setinterval-vs-requestanimationframe) |

### Section 8: ES6+ Modern JavaScript
| # | Question |
|---|----------|
| Q97 | [What are template literals?](#q97-what-are-template-literals) |
| Q98 | [What are Symbols?](#q98-what-are-symbols) |
| Q99 | [What is a WeakMap and when would you use it?](#q99-what-is-a-weakmap-and-when-would-you-use-it) |
| Q100 | [What is a WeakSet?](#q100-what-is-a-weakset) |
| Q101 | [What is a Map vs a plain object?](#q101-what-is-a-map-vs-a-plain-object) |
| Q102 | [What is a Set?](#q102-what-is-a-set) |
| Q103 | [What are iterators and iterables?](#q103-what-are-iterators-and-iterables) |
| Q104 | [What is the `for...of` loop?](#q104-what-is-the-forof-loop) |
| Q105 | [What is the difference between `for...in` and `for...of`?](#q105-what-is-the-difference-between-forin-and-forof) |
| Q106 | [What are tagged template literals?](#q106-what-are-tagged-template-literals) |
| Q107 | [What are ES2020+ features you should know?](#q107-what-are-es2020-features-you-should-know) |
| Q108 | [What is the logical assignment operators (`&&=`, `||=`, `??=`)?](#q108-what-is-the-logical-assignment-operators---) |
| Q109 | [What are private class fields?](#q109-what-are-private-class-fields) |
| Q110 | [What is `structuredClone()`?](#q110-what-is-structuredclone) |

### Section 9: Classes & Object-Oriented Programming
| # | Question |
|---|----------|
| Q111 | [What is a class in JavaScript?](#q111-what-is-a-class-in-javascript) |
| Q112 | [What is a constructor?](#q112-what-is-a-constructor) |
| Q113 | [What is inheritance with `extends` and `super`?](#q113-what-is-inheritance-with-extends-and-super) |
| Q114 | [What are static methods and properties?](#q114-what-are-static-methods-and-properties) |
| Q115 | [What are getters and setters?](#q115-what-are-getters-and-setters) |
| Q116 | [What is method chaining?](#q116-what-is-method-chaining) |
| Q117 | [What is polymorphism in JavaScript?](#q117-what-is-polymorphism-in-javascript) |
| Q118 | [What is encapsulation and how is it achieved in JS?](#q118-what-is-encapsulation-and-how-is-it-achieved-in-js) |
| Q119 | [What is the difference between composition and inheritance?](#q119-what-is-the-difference-between-composition-and-inheritance) |
| Q120 | [What is a mixin?](#q120-what-is-a-mixin) |

### Section 10: Error Handling
| # | Question |
|---|----------|
| Q121 | [What is a `try/catch/finally` block?](#q121-what-is-a-trycatchfinally-block) |
| Q122 | [What is the `Error` object?](#q122-what-is-the-error-object) |
| Q123 | [What are the built-in error types?](#q123-what-are-the-built-in-error-types) |
| Q124 | [How do you create a custom error?](#q124-how-do-you-create-a-custom-error) |
| Q125 | [How do you handle errors in Promises?](#q125-how-do-you-handle-errors-in-promises) |
| Q126 | [What is an unhandled promise rejection?](#q126-what-is-an-unhandled-promise-rejection) |
| Q127 | [What does `finally` do in a Promise chain?](#q127-what-does-finally-do-in-a-promise-chain) |
| Q128 | [Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?](#q128-situation-error-thrown-inside-settimeout--does-trycatch-catch-it) |

### Section 11: The DOM & Browser APIs
| # | Question |
|---|----------|
| Q129 | [What is the DOM?](#q129-what-is-the-dom) |
| Q130 | [How do you select DOM elements?](#q130-how-do-you-select-dom-elements) |
| Q131 | [What is the difference between `innerHTML`, `textContent`, and `innerText`?](#q131-what-is-the-difference-between-innerhtml-textcontent-and-innertext) |
| Q132 | [How do you create, append, and remove DOM elements?](#q132-how-do-you-create-append-and-remove-dom-elements) |
| Q133 | [What is event bubbling and capturing?](#q133-what-is-event-bubbling-and-capturing) |
| Q134 | [What is `event.stopPropagation()` vs `event.preventDefault()`?](#q134-what-is-eventstopp ropagation-vs-eventpreventdefault) |
| Q135 | [What is event delegation?](#q135-what-is-event-delegation) |
| Q136 | [What is the difference between `addEventListener` and `onclick`?](#q136-what-is-the-difference-between-addeventlistener-and-onclick) |
| Q137 | [What is the `DOMContentLoaded` vs `load` event?](#q137-what-is-the-domcontentloaded-vs-load-event) |
| Q138 | [What is `localStorage` vs `sessionStorage` vs cookies?](#q138-what-is-localstorage-vs-sessionstorage-vs-cookies) |
| Q139 | [What is the `fetch` API?](#q139-what-is-the-fetch-api) |
| Q140 | [What is CORS?](#q140-what-is-cors) |
| Q141 | [What is the Intersection Observer API?](#q141-what-is-the-intersection-observer-api) |
| Q142 | [What is the MutationObserver API?](#q142-what-is-the-mutationobserver-api) |
| Q143 | [What is the History API?](#q143-what-is-the-history-api) |

### Section 12: Memory Management & Performance
| # | Question |
|---|----------|
| Q144 | [How does garbage collection work in JavaScript?](#q144-how-does-garbage-collection-work-in-javascript) |
| Q145 | [What is a memory leak and what causes them?](#q145-what-is-a-memory-leak-and-what-causes-them) |
| Q146 | [What is debouncing?](#q146-what-is-debouncing) |
| Q147 | [What is throttling?](#q147-what-is-throttling) |
| Q148 | [What is the difference between debounce and throttle?](#q148-what-is-the-difference-between-debounce-and-throttle) |
| Q149 | [What is lazy loading?](#q149-what-is-lazy-loading) |
| Q150 | [What are Web Workers?](#q150-what-are-web-workers) |
| Q151 | [What is `requestAnimationFrame` and why use it for animations?](#q151-what-is-requestanimationframe-and-why-use-it-for-animations) |
| Q152 | [What is reflow and repaint?](#q152-what-is-reflow-and-repaint) |
| Q153 | [How do you profile JavaScript performance?](#q153-how-do-you-profile-javascript-performance) |

### Section 13: Design Patterns
| # | Question |
|---|----------|
| Q154 | [What is the Module pattern?](#q154-what-is-the-module-pattern) |
| Q155 | [What is the Singleton pattern?](#q155-what-is-the-singleton-pattern) |
| Q156 | [What is the Observer / Pub-Sub pattern?](#q156-what-is-the-observer--pub-sub-pattern) |
| Q157 | [What is the Factory pattern?](#q157-what-is-the-factory-pattern) |
| Q158 | [What is the Decorator pattern?](#q158-what-is-the-decorator-pattern) |
| Q159 | [What is the Strategy pattern?](#q159-what-is-the-strategy-pattern) |
| Q160 | [What is the Proxy pattern?](#q160-what-is-the-proxy-pattern) |
| Q161 | [What is the Command pattern?](#q161-what-is-the-command-pattern) |
| Q162 | [What is the Revealing Module pattern?](#q162-what-is-the-revealing-module-pattern) |

### Section 14: Modules & Tooling
| # | Question |
|---|----------|
| Q163 | [What are ES Modules (`import`/`export`)?](#q163-what-are-es-modules-importexport) |
| Q164 | [What is the difference between default and named exports?](#q164-what-is-the-difference-between-default-and-named-exports) |
| Q165 | [What is CommonJS (`require`/`module.exports`)?](#q165-what-is-commonjs-requiremoduleexports) |
| Q166 | [What is the difference between CommonJS and ES Modules?](#q166-what-is-the-difference-between-commonjs-and-es-modules) |
| Q167 | [What is tree shaking?](#q167-what-is-tree-shaking) |
| Q168 | [What is a bundler (Webpack, Rollup, Vite)?](#q168-what-is-a-bundler-webpack-rollup-vite) |
| Q169 | [What is transpilation and what does Babel do?](#q169-what-is-transpilation-and-what-does-babel-do) |
| Q170 | [What is source mapping?](#q170-what-is-source-mapping) |

### Section 15: Functional Programming
| # | Question |
|---|----------|
| Q171 | [What is functional programming?](#q171-what-is-functional-programming) |
| Q172 | [What is immutability and why does it matter?](#q172-what-is-immutability-and-why-does-it-matter) |
| Q173 | [What are side effects?](#q173-what-are-side-effects) |
| Q174 | [What is function composition vs piping?](#q174-what-is-function-composition-vs-piping) |
| Q175 | [What is partial application?](#q175-what-is-partial-application) |
| Q176 | [What is a functor?](#q176-what-is-a-functor) |
| Q177 | [What is point-free style?](#q177-what-is-point-free-style) |

### Section 16: JavaScript Security
| # | Question |
|---|----------|
| Q178 | [What is XSS (Cross-Site Scripting)?](#q178-what-is-xss-cross-site-scripting) |
| Q179 | [What is CSRF (Cross-Site Request Forgery)?](#q179-what-is-csrf-cross-site-request-forgery) |
| Q180 | [What is Content Security Policy (CSP)?](#q180-what-is-content-security-policy-csp) |
| Q181 | [Why is `eval()` dangerous?](#q181-why-is-eval-dangerous) |
| Q182 | [What is prototype pollution?](#q182-what-is-prototype-pollution) |
| Q183 | [How do you securely handle user input in JavaScript?](#q183-how-do-you-securely-handle-user-input-in-javascript) |
| Q184 | [What is clickjacking and how do you prevent it?](#q184-what-is-clickjacking-and-how-do-you-prevent-it) |

### Section 17: JavaScript Runtime & Node.js Basics
| # | Question |
|---|----------|
| Q185 | [What is Node.js?](#q185-what-is-nodejs) |
| Q186 | [What is the difference between the browser and Node.js environments?](#q186-what-is-the-difference-between-the-browser-and-nodejs-environments) |
| Q187 | [What is the Node.js event loop vs the browser event loop?](#q187-what-is-the-nodejs-event-loop-vs-the-browser-event-loop) |
| Q188 | [What is `process.nextTick()`?](#q188-what-is-processnexttick) |
| Q189 | [What is npm and what is `package.json`?](#q189-what-is-npm-and-what-is-packagejson) |
| Q190 | [What is the difference between `dependencies` and `devDependencies`?](#q190-what-is-the-difference-between-dependencies-and-devdependencies) |

### Section 18: TypeScript Fundamentals (JS Context)
| # | Question |
|---|----------|
| Q191 | [What is TypeScript and how does it relate to JavaScript?](#q191-what-is-typescript-and-how-does-it-relate-to-javascript) |
| Q192 | [What are the basic types in TypeScript?](#q192-what-are-the-basic-types-in-typescript) |
| Q193 | [What is `any` vs `unknown` in TypeScript?](#q193-what-is-any-vs-unknown-in-typescript) |
| Q194 | [What is a type assertion?](#q194-what-is-a-type-assertion) |
| Q195 | [What is a union type vs intersection type?](#q195-what-is-a-union-type-vs-intersection-type) |
| Q196 | [What are generics in TypeScript?](#q196-what-are-generics-in-typescript) |
| Q197 | [What is the difference between `interface` and `type`?](#q197-what-is-the-difference-between-interface-and-type) |
| Q198 | [What is type narrowing?](#q198-what-is-type-narrowing) |

### Section 19: Testing JavaScript
| # | Question |
|---|----------|
| Q199 | [What is unit testing?](#q199-what-is-unit-testing) |
| Q200 | [What is Jest?](#q200-what-is-jest) |
| Q201 | [What are mocks, stubs, and spies?](#q201-what-are-mocks-stubs-and-spies) |
| Q202 | [What is TDD (Test-Driven Development)?](#q202-what-is-tdd-test-driven-development) |
| Q203 | [How do you test asynchronous code in Jest?](#q203-how-do-you-test-asynchronous-code-in-jest) |
| Q204 | [What is code coverage?](#q204-what-is-code-coverage) |
| Q205 | [What is the difference between unit, integration, and E2E tests?](#q205-what-is-the-difference-between-unit-integration-and-e2e-tests) |

### Section 20: Senior-Level & Tricky Scenario Questions
| # | Question |
|---|----------|
| Q206 | [What is the output of `0.1 + 0.2 === 0.3` and why?](#q206-what-is-the-output-of-01--02--03-and-why) |
| Q207 | [What is the difference between `Object.assign()` and spread?](#q207-what-is-the-difference-between-objectassign-and-spread) |
| Q208 | [Explain how `Array.prototype.reduce` works from scratch.](#q208-explain-how-arrayprototypereduce-works-from-scratch) |
| Q209 | [Implement a deep clone function.](#q209-implement-a-deep-clone-function) |
| Q210 | [Implement a debounce function from scratch.](#q210-implement-a-debounce-function-from-scratch) |
| Q211 | [Implement a throttle function from scratch.](#q211-implement-a-throttle-function-from-scratch) |
| Q212 | [Implement `Promise.all` from scratch.](#q212-implement-promiseall-from-scratch) |
| Q213 | [What is the output: `typeof null`?](#q213-what-is-the-output-typeof-null) |
| Q214 | [What is the output: `[] == ![]`?](#q214-what-is-the-output---) |
| Q215 | [How does JavaScript handle integer overflow?](#q215-how-does-javascript-handle-integer-overflow) |
| Q216 | [What is `BigInt` and when do you use it?](#q216-what-is-bigint-and-when-do-you-use-it) |
| Q217 | [How would you implement an event emitter?](#q217-how-would-you-implement-an-event-emitter) |
| Q218 | [How would you implement `curry` function from scratch?](#q218-how-would-you-implement-curry-function-from-scratch) |
| Q219 | [What is the Proxy object and how is it used?](#q219-what-is-the-proxy-object-and-how-is-it-used) |
| Q220 | [What is `Reflect` in JavaScript?](#q220-what-is-reflect-in-javascript) |
| Q221 | [Situation: Design a retry mechanism for a failed API call.](#q221-situation-design-a-retry-mechanism-for-a-failed-api-call) |
| Q222 | [Situation: How do you cancel a fetch request?](#q222-situation-how-do-you-cancel-a-fetch-request) |
| Q223 | [What is tail call optimization?](#q223-what-is-tail-call-optimization) |
| Q224 | [Explain the difference between `Array.from()` and spread on a NodeList.](#q224-explain-the-difference-between-arrayfrom-and-spread-on-a-nodelist) |
| Q225 | [What is the `void` operator?](#q225-what-is-the-void-operator) |
| Q226 | [What are the tricky parts of `==` type coercion rules?](#q226-what-are-the-tricky-parts-of--type-coercion-rules) |
| Q227 | [How does JavaScript sort arrays by default and what is the gotcha?](#q227-how-does-javascript-sort-arrays-by-default-and-what-is-the-gotcha) |
| Q228 | [Implement `Array.prototype.flat` from scratch.](#q228-implement-arrayprototypeflat-from-scratch) |
| Q229 | [What is the difference between `Object.create(null)` and `{}`?](#q229-what-is-the-difference-between-objectcreatenull-and-) |
| Q230 | [How would you implement infinite scrolling with vanilla JS?](#q230-how-would-you-implement-infinite-scrolling-with-vanilla-js) |

---

## Section 1: JavaScript Fundamentals

*Core concepts every JavaScript developer must know cold.*

---

#### Q1. What is JavaScript and where can it run?

JavaScript is a high-level, dynamic, interpreted programming language originally designed for browser scripting. Today it runs in browsers (via JS engines like V8 in Chrome), on servers (Node.js), in mobile apps (React Native), desktop apps (Electron), and IoT devices – anywhere a JS runtime is embedded.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q2. What is the difference between JavaScript and ECMAScript?

ECMAScript (ES) is the specification/standard. JavaScript is the most popular implementation of that standard. TC39 (a committee) maintains the ECMAScript spec and releases yearly updates (ES2015/ES6, ES2016… ES2024). Browsers and Node.js implement these features over time.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q3. Is JavaScript compiled or interpreted?

Technically both. Modern JS engines (V8, SpiderMonkey) use JIT (Just-In-Time) compilation. Code is first parsed into an AST, then compiled to bytecode, then hot paths are compiled to optimized machine code at runtime. JavaScript starts running your code immediately without making you wait (like an interpreter). But as it runs, it secretly figures out which parts of your code are used the most and fully translates them into lightning-fast machine code in the background (like a compiler).
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q4. What is the JavaScript engine and how does it work?

A JavaScript engine is like a smart translator and office manager for your code. It does three main things:

Translates & Runs: It reads your text code, converts it into a quick shorthand (bytecode) the computer understands, and runs it immediately.

Speeds Up (JIT): It watches your code as it runs. If it sees a specific action you repeat constantly, it instantly upgrades that part into ultra-fast machine code.

Cleans Up (Garbage Collection): It holds onto the data you are currently using, and automatically throws away old data you no longer need so your computer doesn't slow down or crash.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q5. What is single-threaded execution in JavaScript?

JavaScript has one call stack and one thread of execution – it can only do one thing at a time. Long-running tasks block everything else. The event loop enables asynchronous behavior by offloading tasks (timers, network) to Web APIs and processing their callbacks when the stack is empty.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q6. What is the difference between `null` and `undefined`?

`undefined`: a variable has been declared but not assigned a value; also the return value of functions that don't return anything. `null`: an intentional absence of value, explicitly assigned by a developer. `typeof undefined === 'undefined'`; `typeof null === 'object'` (a historic bug in JS).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q7. What are the primitive data types in JavaScript?

There are 7 primitives: `string`, `number`, `boolean`, `undefined`, `null`, `symbol` (ES6), and `bigint` (ES2020). Everything else is an `object` (arrays, functions, dates, etc. are objects). Primitives are immutable and stored by value; objects are stored by reference.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q8. What is the difference between `==` and `===`?

`===` (strict equality): compares value AND type — no coercion. `==` (loose equality): performs type coercion before comparing. `1 == '1'` is `true`; `1 === '1'` is `false`. Always prefer `===` to avoid unexpected coercion bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q9. What is type coercion?

JavaScript automatically converts types when operating on mixed-type values. Example: `'5' - 2 = 3` (string coerced to number), `'5' + 2 = '52'` (number coerced to string for `+`). Implicit coercion can cause bugs; use explicit conversion (`Number()`, `String()`, `Boolean()`) for clarity.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q10. What is `NaN` and how do you check for it?

`NaN` (Not-a-Number) is the result of invalid numeric operations (`'abc' * 2`, `0/0`). Its type is `'number'`. Weirdly, `NaN !== NaN`. Check with `Number.isNaN(value)` (strict – only true for actual NaN) or `isNaN(value)` (coerces first, less reliable).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q11. What is the `typeof` operator?

Returns a string describing the type of a value: `'string'`, `'number'`, `'boolean'`, `'undefined'`, `'object'`, `'function'`, `'symbol'`, `'bigint'`. Known quirks: `typeof null === 'object'` (bug), `typeof function(){} === 'function'` (functions are objects but get their own typeof result).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q12. What are truthy and falsy values?

Falsy: `false`, `0`, `-0`, `0n`, `''` (empty string), `null`, `undefined`, `NaN`. Everything else is truthy, including `'0'`, `[]`, `{}`, and `'false'`. Used in boolean contexts like `if` conditions and `&&`/`||` operators.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q13. What is the difference between `var`, `let`, and `const`?

`var`: function-scoped, hoisted and initialized to `undefined`, can be redeclared. `let`: block-scoped, hoisted but not initialized (TDZ), cannot be redeclared. `const`: block-scoped, must be initialized at declaration, cannot be reassigned (but object contents can be mutated). Always prefer `const` by default, `let` when reassignment is needed, avoid `var`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q14. What is hoisting?

JavaScript's behavior of moving declarations to the top of their scope during the creation phase of the execution context. `var` declarations are hoisted and initialized to `undefined`. Function declarations are fully hoisted (name + body). `let`/`const` are hoisted but not initialized (Temporal Dead Zone). Class declarations are hoisted but not initialized.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q15. What is the Temporal Dead Zone (TDZ)?

The period between the start of a block scope and the `let`/`const` declaration being executed. Accessing the variable in this window throws a `ReferenceError`. It exists because hoisting moves the binding to the top of the block but doesn't initialize it until the declaration line is reached.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 2: Scope, Closures & Execution Context

*Understanding where variables live and how functions remember their environment.*

---

#### Q16. What is scope in JavaScript?

Scope defines the accessibility of variables and functions in different parts of your code. JavaScript has global scope, function scope, and block scope (ES6+). Scope determines where variables can be read or written.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q17. What is the difference between global, function, and block scope?

Global scope: variables declared outside any function/block, accessible everywhere. Function scope: variables declared with `var` inside a function, accessible only within that function. Block scope: variables declared with `let`/`const` inside `{}`, accessible only within that block.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q18. What is the scope chain?

When JS looks up a variable, it starts in the current scope and moves outward to enclosing scopes until it reaches the global scope. This chain of scopes is the scope chain. If not found in global scope, a `ReferenceError` is thrown.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q19. What is lexical scope?

The scope of a variable is determined by its position in the source code at write time, not at runtime. Inner functions have access to variables in their outer (enclosing) functions. This is decided when the code is parsed, not when it runs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q20. What is a closure?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q21. What are practical uses of closures?

Data privacy/encapsulation (module pattern), factory functions, memoization, partial application, event handlers that remember state, maintaining state in async operations, and implementing the module pattern before ES modules existed.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q22. What is a closure memory leak and how do you avoid it?

If a closure holds a reference to a large object or DOM node and is never released, that memory can't be garbage collected. Avoid by: nullifying references when no longer needed, removing event listeners, avoiding closures that capture large objects unnecessarily, and using `WeakMap`/`WeakRef` for holding references that shouldn't prevent GC.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q23. What is an execution context?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q24. What is the call stack?

A stack data structure that tracks function calls. When a function is called, its execution context is pushed onto the stack. When it returns, it's popped off. If the stack overflows (infinite recursion), you get a `RangeError: Maximum call stack size exceeded`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q25. What is the difference between function scope and block scope?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q26. What is an IIFE and why is it used?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q27. Situation: Classic loop closure bug – `var` in a for loop.

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);
}
// Logs: 3, 3, 3 — not 0, 1, 2
```
Because `var` is function-scoped, all callbacks share the same `i`. When they run, the loop has finished and `i` is `3`. Fix: use `let` (block-scoped, creates a new binding per iteration), use `setTimeout` with a closure factory, or use `forEach`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q28. What is variable shadowing?

When a variable declared in an inner scope has the same name as a variable in an outer scope, the inner one "shadows" the outer one within that scope. The outer variable is inaccessible within the inner scope by that name.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 3: Functions

*Functions are first-class citizens in JavaScript — master them deeply.*

---

#### Q29. What is the difference between function declaration and function expression?

Function declaration: `function foo() {}` — hoisted fully, available before its line in code. Function expression: `const foo = function() {}` — not hoisted (the variable is hoisted as `undefined`). Arrow functions are always expressions. Named function expressions are useful for recursion and stack traces.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q30. What are arrow functions and how do they differ from regular functions?

Arrow functions (`() => {}`) are concise and have no own `this`, `arguments`, `super`, or `new.target`. They inherit `this` lexically from the enclosing scope. They cannot be used as constructors (`new` throws), cannot be used as methods with a dynamic `this`, and don't have a `prototype` property.

### **What are Arrow Functions?**

Arrow functions (`() => {}`) are a shorter, modern way to write functions in JavaScript.

```javascript
// Regular Function
function greeting(name) {
  return "Hello " + name;
}

// Arrow Function
const greeting = (name) => "Hello " + name;

```

---

### **The 3 Major Differences**

The differences matter because arrow functions aren't just a visual shortcut; they behave differently under the hood.

#### 1. The `this` Keyword (The Biggest Difference)

* **Regular functions** create their own `this` value depending on *how* and *where* they are called. It can change dynamically.
* **Arrow functions** don't have their own `this`. They inherit `this` from the code surrounding them (lexical scope). They never change their mind about what `this` means.

#### 2. Cannot Be Constructors

* **Regular functions** can be used with the `new` keyword to create new objects (like a blueprint).
* **Arrow functions** will throw an error if you try to use `new` with them. They cannot be used as constructors.

#### 3. No `arguments` Object

* **Regular functions** have a built-in local variable called `arguments` that contains a list of all the values passed into the function.
* **Arrow functions** do not have this. If you need a list of inputs, you must use modern rest parameters instead (like `(...args) => {}`).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q31. What is a first-class function?

Functions are first-class citizens in JavaScript — they can be assigned to variables, passed as arguments to other functions, returned from functions, stored in arrays/objects, and have properties attached to them. This enables functional programming patterns.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q32. What is a higher-order function?

A function that takes one or more functions as arguments, returns a function, or both. Examples: `Array.prototype.map`, `filter`, `reduce`, `setTimeout`. They're the backbone of functional programming in JavaScript.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q33. What is a pure function?

A function that: (1) always returns the same output for the same input, and (2) has no side effects (doesn't modify external state, make network calls, write to DOM, etc.). Pure functions are predictable, testable, and easy to reason about.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q34. What are default parameters?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q35. What is the rest parameter (`...args`)?

Collects all remaining arguments into an array: `function sum(...nums) { return nums.reduce((a,b) => a+b, 0); }`. Must be the last parameter. Unlike `arguments`, rest parameters are real arrays with all array methods.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q36. What is the `arguments` object?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q37. What is function currying?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q38. What is function composition?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q39. What is memoization?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q40. What is a callback function?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q41. What is the difference between a method and a function?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q42. What is a generator function?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 4: `this` Keyword

*One of JavaScript's most misunderstood concepts.*

---

#### Q43. What is `this` in JavaScript?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q44. What are the four rules of `this` binding?

1. **Default binding**: standalone function call → `this` is global object (or `undefined` in strict mode).
2. **Implicit binding**: method call `obj.fn()` → `this` is `obj`.
3. **Explicit binding**: `fn.call(ctx)`, `fn.apply(ctx)`, `fn.bind(ctx)` → `this` is `ctx`.
4. **New binding**: `new Fn()` → `this` is the newly created object.

Arrow functions ignore all these rules and use lexical `this`.
The `this` keyword in JavaScript is like a pronoun (like "he", "she", or "it"). Its meaning changes entirely depending on **how** a function is called.

Here are the 4 simple rules JavaScript uses to figure out what `this` means, ordered from lowest to highest priority:

---

### 1. Default Binding (The Default)

If you call a standalone function all by itself, `this` defaults to the global window/global object. (If you are using strict mode, it will be `undefined`).

```javascript
function show() {
  console.log(this); 
}

show(); // 🌐 Prints: Window object (or undefined)

```

### 2. Implicit Binding (The Object Before the Dot)

When a function is called as a method inside an object, `this` refers to the **object directly to the left of the dot**.

```javascript
const user = {
  name: "Alice",
  greet() { console.log(this.name); }
};

user.greet(); // 📍 Prints: "Alice" (because 'user' is left of the dot)

```

### 3. Explicit Binding (Direct Control)

You can force a function to use a specific object as `this` by using `.call()`, `.apply()`, or `.bind()`. You are explicitly telling JavaScript, "Use *this* object!"

```javascript
function sayName() { console.log(this.name); }
const person = { name: "Bob" };

sayName.call(person); // 🎯 Prints: "Bob" (forced via .call)

```

### 4. `new` Binding (The Constructor)

When you call a function with the `new` keyword, JavaScript creates a brand-new empty object behind the scenes, and `this` points directly to that new object.

```javascript
function Car(color) {
  this.color = color;
}

const myCar = new Car("Red"); // ✨ 'this' becomes the new myCar object

```

---

### The Exception: Arrow Functions

Arrow functions completely ignore these 4 rules. They don't get their own `this` at all. Instead, they look at the code directly surrounding them and **adopt the `this` value of their parent scope**.
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q45. How does `this` work in arrow functions?

Arrow functions have no own `this`. They capture `this` from the enclosing lexical scope at the time they are defined. This makes them ideal for callbacks and methods that need to access the outer `this`, eliminating the need for `const self = this` or `.bind(this)`.
Arrow functions do **not** have their own `this` keyword. Instead, they act like a sponge and **absorb the `this` value from the code directly surrounding them** (their parent scope).

Once an arrow function captures its parent's `this`, it is permanently locked in and can never change.

---

### The Classic Problem and the Arrow Solution

Before arrow functions, passing a function inside a timer (like `setTimeout`) or a callback would cause `this` to break because it would lose its connection to the object.

```javascript
const user = {
  name: "Alice",
  
  greetRegular() {
    setTimeout(function() {
      // ❌ ERROR: Regular functions change 'this' to the global Window
      console.log("Hello " + this.name); 
    }, 1000);
  },

  greetArrow() {
    setTimeout(() => {
      //  Works! The arrow function steals 'this' from greetArrow()
      console.log("Hello " + this.name); 
    }, 1000);
  }
};

user.greetArrow(); // Prints "Hello Alice" after 1 second

```

---

### Why this is useful:

* **No more hacks:** You no longer need to write confusing workarounds like `const self = this;` or tack `.bind(this)` onto the end of every callback function.
* **Predictable behavior:** It makes writing asynchronous code (like fetching data or setting timers) inside objects much cleaner and less prone to bugs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q46. What is explicit binding with `call`, `apply`, and `bind`?

All three methods allow you to explicitly set `this`. `call(thisArg, arg1, arg2)` calls immediately with individual args. `apply(thisArg, [args])` calls immediately with args as array. `bind(thisArg, ...args)` returns a new function with `this` permanently bound — doesn't call immediately.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q47. What is the difference between `call` and `apply`?

Both call a function immediately with a given `this`. The only difference is how additional arguments are passed: `call` takes individual arguments (`fn.call(ctx, a, b, c)`), while `apply` takes an array (`fn.apply(ctx, [a, b, c])`). Use `apply` when you already have args in an array.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q48. What does `bind` return?

`bind` returns a new function with `this` permanently bound to the specified value. The original function is unchanged. The bound function can also have arguments pre-filled (partial application). Calling `bind` multiple times only applies the first binding.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q49. What is `this` in a class?

Inside a class method, `this` refers to the instance of the class. In the constructor, `this` is the newly created object. Static methods have `this` bound to the class itself, not an instance. Arrow function class fields capture `this` at creation time (safe for callbacks).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q50. Situation: `this` is `undefined` or `window` inside a callback – why?

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
[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 5: Prototypes & Inheritance

*Understanding JavaScript's object model at its core.*

---

#### Q51. What is a prototype in JavaScript?

Every JavaScript object has an internal `[[Prototype]]` link pointing to another object (or null). When a property isn't found on an object, JavaScript walks up the prototype chain looking for it. This is how objects inherit properties and methods.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q52. What is the prototype chain?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q53. What is the difference between `__proto__` and `prototype`?

`prototype` is a property on constructor functions. When you use `new`, the created object's `[[Prototype]]` is set to the constructor's `prototype`. `__proto__` is the actual prototype link on every object instance (the accessor for `[[Prototype]]`). Use `Object.getPrototypeOf()` instead of `__proto__` in production code.
To understand the difference, think of a constructor function as a **Factory** and the objects it creates as **Products**.

---

### 1. `prototype` (The Factory's Blueprint)

This property **only** belongs to the Factory (the constructor function). It is the master blueprint where the factory keeps all the shared tools, methods, and features it wants every product to have.

* **Analogy:** The blueprint sitting inside the iPhone factory.

### 2. `__proto__` (The Product's Link)

This property belongs to **every single object instance** (the products). It is a hidden, live link pointing directly back to the factory's master blueprint. If an object is asked to do something it doesn't know how to do, it uses this link to look it up on the blueprint.

* **Analogy:** The "Made in Factory X" barcode stamped on the back of your actual iPhone.

---

### A Quick Code Example

```javascript
// The Factory
function Robot() {}

// Adding a tool to the Factory's master blueprint
Robot.prototype.laser = function() { return "Zap!"; };

// Creating a Product
const wallE = new Robot();

// wallE doesn't have 'laser' on his own body, 
// so he uses __proto__ to find it on the blueprint!
console.log(wallE.laser()); // "Zap!"

console.log(wallE.__proto__ === Robot.prototype); // true

```

---

### The Golden Rule for Production

> ⚠️ **Don't use `__proto__` in real code.** > While `__proto__` works in browsers, it is old, slow, and bad practice to use directly. Instead, modern JavaScript gives you a clean tool to inspect an object's blueprint: **`Object.getPrototypeOf(obj)`**.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q54. What is `Object.create()`?

Creates a new object with the specified object as its prototype. `const child = Object.create(parent)` — `child` inherits from `parent` without needing a constructor. Passing `null` creates an object with no prototype at all (truly empty object, no `toString` etc.).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q55. What is prototypal inheritance?

Objects inherit directly from other objects through the prototype chain. This differs from classical OOP where classes inherit from classes. In JS, inheritance is delegation — if an object doesn't have a property, it delegates the lookup to its prototype.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q56. What are ES6 classes and how do they relate to prototypes?

ES6 classes are syntactic sugar over prototypal inheritance. `class Animal { speak() {} }` creates `Animal.prototype.speak`. `class Dog extends Animal {}` sets `Dog.prototype.__proto__ = Animal.prototype`. Under the hood, it's still prototype-based — no classical inheritance actually occurs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q57. What is the difference between classical and prototypal inheritance?

Classical (Java/C++): Classes are blueprints, objects are instances, inheritance copies behavior from parent class to child class. Prototypal (JS): Objects inherit from objects directly through a live prototype link — delegation, not copying. Changes to the prototype affect all inheriting objects.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q58. What is `instanceof` and how does it work?

`obj instanceof Constructor` walks the prototype chain of `obj` looking for `Constructor.prototype`. Returns `true` if found. Can give unexpected results with multiple frames (different global contexts). Prefer duck typing or `Object.getPrototypeOf()` for robust checks.
### **The Short Version**

`instanceof` is like an **ancestry test** for JavaScript objects. It checks if an object belongs to a specific class or constructor function by looking at its family tree (the prototype chain).

```javascript
object instanceof Constructor

```

---

### **How It Works (Follow the Link)**

When you run `obj instanceof Constructor`, JavaScript plays a game of **"Follow the Link"**:

1. It looks at the object's hidden link (`__proto__`).
2. It follows that link up to the next blueprint, and the next, walking up the chain.
3. At each step, it asks: *"Is this blueprint the exact same as `Constructor.prototype`?"*
4. If it finds a match anywhere in the chain, it returns **`true`**. If it runs out of links and hits the end of the line (`null`), it returns **`false`**.

---

### **A Quick Example**

```javascript
class Animal {}
class Dog extends Animal {}

const myPet = new Dog();

console.log(myPet instanceof Dog);    //  true (Direct parent)
console.log(myPet instanceof Animal); //  true (Grandparent - it walked up the chain!)
console.log(myPet instanceof Array);  // ❌ false (Not in the family tree)

```

---

### **The Main "Gotcha"**

`instanceof` can occasionally lie to you if your web application uses **iframes** or multiple window environments.

Because each iframe has its own separate environment (its own `Window`, `Array`, and `Object` blueprints), an array created inside an iframe will return `false` if you check it with `iframeArray instanceof Array` in your main window. For safe checks (especially with arrays), it is better to use specific tools like **`Array.isArray(obj)`**.
[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q59. What is `hasOwnProperty`?

`obj.hasOwnProperty('key')` returns `true` only if `key` is a direct property of `obj`, not inherited through the prototype chain. Use it when iterating with `for...in` to distinguish own properties from inherited ones. Alternative: `Object.hasOwn(obj, 'key')` (ES2022).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q60. What is `Object.getPrototypeOf()`?

Returns the prototype of an object (`[[Prototype]]`). The standard alternative to `__proto__`. Use `Object.setPrototypeOf()` to change an object's prototype (though this is slow and discouraged — use `Object.create()` at construction time instead).

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 6: Objects & Arrays

*Deep understanding of JavaScript's two most-used data structures.*

---

#### Q61. What are the ways to create objects in JavaScript?

Object literal `{}`, `new Object()`, `Object.create(proto)`, constructor functions with `new`, ES6 classes with `new`, factory functions returning `{}`. Object literals and classes are the most common. Factory functions offer more flexibility and avoid `new`/`this` complexity.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q62. What is destructuring?

Extracting values from arrays or objects into distinct variables. `const {a, b} = obj`, `const [x, y] = arr`. Supports renaming (`{a: localName}`), defaults (`{a = 0}`), nested destructuring, and rest (`{a, ...rest}`). Works in function parameters, variable declarations, and assignments.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q63. What is the spread operator?

`...` spreads an iterable into individual elements. For arrays: `[...arr1, ...arr2]` (concatenate/copy). For objects: `{...obj1, ...obj2}` (merge/clone). In function calls: `fn(...args)`. Creates shallow copies — nested objects are still references.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q64. What is the difference between shallow copy and deep copy?

Shallow copy: copies the top-level properties. Nested objects/arrays are still referenced (not duplicated). Methods: spread `{...obj}`, `Object.assign({}, obj)`, `arr.slice()`. Deep copy: copies all levels recursively — changes in copy don't affect original. Methods: `structuredClone()`, `JSON.parse(JSON.stringify(obj))` (with limitations), or libraries like Lodash `_.cloneDeep`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q65. How do you deep clone an object?

Best method (modern): `structuredClone(obj)` — handles circular references, dates, maps, sets. Legacy: `JSON.parse(JSON.stringify(obj))` — simple but loses functions, `undefined`, `Date` objects become strings, can't handle circular references. For complex needs: Lodash `_.cloneDeep()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q66. What are computed property names?

ES6 syntax to use an expression as a property key: `const key = 'name'; const obj = { [key]: 'Alice' }` — creates `{name: 'Alice'}`. Useful for dynamic property names, especially in reducers or when building objects from variables.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q67. What is `Object.keys()`, `Object.values()`, `Object.entries()`?

`Object.keys(obj)`: returns array of own enumerable property names. `Object.values(obj)`: returns array of own enumerable property values. `Object.entries(obj)`: returns array of `[key, value]` pairs. All iterate only over own enumerable string-keyed properties (not prototype, not symbols).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q68. What is `Object.freeze()` vs `Object.seal()`?

`Object.freeze(obj)`: prevents adding, deleting, or modifying any properties. Shallow — nested objects can still be mutated. `Object.seal(obj)`: prevents adding or deleting properties, but allows modifying existing ones. Use freeze for truly immutable objects; use seal when shape must be fixed but values can change.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q69. What are property descriptors?

Each property has hidden attributes: `value`, `writable` (can be changed), `enumerable` (appears in loops), `configurable` (can be deleted/reconfigured). Access via `Object.getOwnPropertyDescriptor(obj, 'key')`. Set via `Object.defineProperty(obj, 'key', descriptor)`. Getters/setters replace `value` and `writable` with `get` and `set`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q70. What is optional chaining (`?.`)?

Safely accesses deeply nested properties without throwing if an intermediate value is `null`/`undefined`. `obj?.a?.b?.c` returns `undefined` instead of throwing. Works for method calls (`obj.fn?.()`) and array access (`arr?.[0]`). Short-circuits the rest of the expression when it encounters `null`/`undefined`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q71. What is the nullish coalescing operator (`??`)?

Returns the right-hand value when the left-hand value is `null` or `undefined` (not just falsy). `const val = input ?? 'default'` — if `input` is `0` or `''`, those are used (unlike `||` which would fall back to 'default'). Use `??` when `0` or empty string are valid values.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q72. What are the most important array methods?

Mutation: `push`, `pop`, `shift`, `unshift`, `splice`, `sort`, `reverse`. Non-mutating: `map`, `filter`, `reduce`, `find`, `findIndex`, `some`, `every`, `includes`, `indexOf`, `slice`, `flat`, `flatMap`, `concat`. Creation: `Array.from()`, `Array.of()`, `Array.isArray()`. Prefer non-mutating methods for predictability.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q73. What is the difference between `map`, `filter`, and `reduce`?

`map(fn)`: transforms each element, returns new array of same length. `filter(fn)`: returns new array with only elements where `fn` returns truthy. `reduce(fn, initial)`: accumulates all elements into a single value (sum, object, nested array, etc.). All are non-mutating.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q74. What is the difference between `forEach` and `map`?

`forEach` executes a side effect for each element, returns `undefined`. `map` transforms each element and returns a new array. Don't use `map` when you don't need the returned array (use `forEach` for side effects). Can't break out of either — use `for...of` or `some`/`every` for early exit.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q75. What is array and object destructuring with defaults?

```javascript
const { a = 10, b: renamed = 20 } = { a: 5 };
// a = 5, renamed = 20

const [x = 1, y = 2] = [10];
// x = 10, y = 2
```
Defaults apply only when the value is `undefined`, not `null`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q76. How do you remove duplicates from an array?

`[...new Set(arr)]` — most concise for primitives. `Array.from(new Set(arr))` — equivalent. For objects (by property): `arr.filter((v, i, a) => a.findIndex(t => t.id === v.id) === i)`. Set works by value equality for primitives; for objects, it checks reference equality.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q77. What is the difference between `find` and `filter`?

`find(fn)`: returns the first element where `fn` is truthy, or `undefined` if none. Short-circuits. `filter(fn)`: returns a new array of all elements where `fn` is truthy — never short-circuits. Use `find` when you need one result; use `filter` when you need all matches.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q78. What does `flat()` and `flatMap()` do?

`arr.flat(depth)`: flattens nested arrays up to specified depth (default 1). `arr.flat(Infinity)` fully flattens. `arr.flatMap(fn)`: equivalent to `arr.map(fn).flat(1)` but more efficient. Useful for mapping to arrays and then flattening one level.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 7: Asynchronous JavaScript

*The most critical section for modern JS development.*

---

#### Q79. What is synchronous vs asynchronous code?

Synchronous: executes line by line, each line waits for the previous to finish. Asynchronous: initiates an operation and moves on; the result is handled later via callback, promise, or async/await. JS is single-threaded, so async operations are managed by the event loop, not true parallelism.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q80. What is the Event Loop?

The mechanism that allows JavaScript to perform non-blocking async operations despite being single-threaded. It continuously checks if the call stack is empty, then takes tasks from the task queue and pushes them onto the stack. This enables handling timers, network responses, and user events without blocking the main thread.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q81. What are the Call Stack, Web APIs, Callback Queue, and Microtask Queue?

**Call Stack**: where synchronous code executes (LIFO). **Web APIs**: browser-provided async capabilities (setTimeout, fetch, DOM events) — offloaded from JS thread. **Callback Queue (macrotask queue)**: where timer/event callbacks wait. **Microtask Queue**: where Promise callbacks and `queueMicrotask` wait. Microtasks run before the next macrotask.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q82. What is the difference between macrotasks and microtasks?

**Macrotasks** (task queue): `setTimeout`, `setInterval`, `setImmediate`, I/O, UI rendering. One macrotask runs per event loop iteration. **Microtasks**: Promises (`.then`, `.catch`, `.finally`), `queueMicrotask`, `MutationObserver`. ALL microtasks are processed after each macrotask, before the next macrotask runs. Microtasks have priority.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q83. What is a callback and what is callback hell?

A callback is a function passed to another function to be called later. Callback hell: deeply nested callbacks where each async step requires another callback, creating a pyramid of doom. Makes code hard to read, debug, and maintain. Solved by Promises and async/await.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q84. What is a Promise?

An object representing the eventual completion or failure of an async operation. Created with `new Promise((resolve, reject) => {...})`. Provides `.then()` for success, `.catch()` for error, `.finally()` for cleanup. Promises are chainable and avoid callback hell. They're always asynchronous — `.then` callbacks always run after the current synchronous code.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q85. What are the states of a Promise?

**Pending**: initial state, operation in progress. **Fulfilled**: operation completed successfully — `resolve()` was called. **Rejected**: operation failed — `reject()` was called. Once settled (fulfilled or rejected), a Promise is immutable — it can never change state again.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q86. What is promise chaining?

`.then()` returns a new Promise, so you can chain multiple async operations: `fetchUser().then(user => fetchPosts(user.id)).then(posts => render(posts)).catch(handleError)`. Each `.then` receives the resolved value of the previous one. Errors propagate down the chain to the nearest `.catch`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q87. What is `Promise.all()`?

Takes an iterable of Promises, returns a Promise that resolves with an array of all resolved values when ALL promises resolve. Rejects immediately if ANY promise rejects (fail-fast). Use for parallel operations where all results are needed and any failure should abort.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q88. What is `Promise.allSettled()`?

Like `Promise.all()` but never rejects. Waits for ALL promises to settle and returns an array of `{status: 'fulfilled', value}` or `{status: 'rejected', reason}` objects. Use when you need all results regardless of individual failures (e.g., multiple independent API calls).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q89. What is `Promise.race()`?

Returns a Promise that settles (resolves or rejects) as soon as the FIRST promise in the iterable settles. Use for timeouts: `Promise.race([fetch(url), timeout(5000)])`. The other promises continue running but their outcomes are ignored.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q90. What is `Promise.any()`?

Returns a Promise that resolves as soon as ANY promise resolves. Rejects only if ALL promises reject (with an `AggregateError`). Opposite short-circuit behavior from `Promise.all()`. Use when you want the fastest successful result (e.g., trying multiple CDNs).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q91. What is `async/await`?

Syntactic sugar over Promises. `async` functions always return a Promise. `await` pauses execution of the async function until the awaited Promise resolves, then returns the resolved value. Makes async code look and behave more like synchronous code. Under the hood, it's still Promises.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q92. How do you handle errors with `async/await`?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q93. What happens if you `await` a non-Promise value?

`await 42` is valid — it simply returns `42`. The value is wrapped in `Promise.resolve()` first. This means `await` is safe to use even if you're not sure if a function returns a Promise.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q94. What is the difference between sequential and parallel async execution?

Sequential: `await a(); await b();` — B starts only after A finishes. Total time = A + B. Parallel: `await Promise.all([a(), b()])` — both start simultaneously. Total time = max(A, B). Use parallel when operations are independent; sequential when one depends on the other.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q95. Situation: Output the order of `setTimeout`, Promise, and synchronous code.

```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// Output: 1, 4, 3, 2
```
Synchronous code runs first (1, 4). Microtasks (Promises) run before macrotasks (setTimeout). So 3 runs before 2.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q96. What is `setTimeout` vs `setInterval` vs `requestAnimationFrame`?

`setTimeout(fn, delay)`: calls `fn` once after `delay` ms (minimum — actual time may be longer). `setInterval(fn, delay)`: calls `fn` repeatedly every `delay` ms. `requestAnimationFrame(fn)`: calls `fn` before the next browser repaint (~60fps). Use rAF for animations; it's paused when the tab is hidden and syncs with display refresh rate.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 8: ES6+ Modern JavaScript

*Features you must know for any modern JS interview.*

---

#### Q97. What are template literals?

### **The Short Version**

Template literals are a modern, much cleaner way to work with text (strings) in JavaScript. Instead of using single (`'`) or double (`"`) quotes, you wrap your text in **backticks (```)**.

They solve two major headaches of traditional strings: messy string gluing (concatenation) and multi-line formatting.

---

### **The 2 Best Features**

#### 1. Stuffing Variables Inside Text (Interpolation)

Instead of using the plus sign (`+`) to awkwardly glue text and variables together, you can inject variables or math directly into the text using the **`${}`** placeholder. JavaScript will evaluate whatever is inside the brackets on the fly.

* **The Old, Messy Way:** ```javascript
"Hello, " + name + "! You are " + (age + 1) + " next year.";
```

```


* **The New, Clean Way:** ```javascript
`Hello, ${name}! You are ${age + 1} next year.`;
```


```



#### 2. Multi-line Text Made Easy

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q98. What are Symbols?

A unique, immutable primitive value. `Symbol('desc')` creates a Symbol; no two Symbols are equal. Used as unique property keys (avoid naming collisions), to implement well-known behaviors (`Symbol.iterator`, `Symbol.toPrimitive`), and for truly private-ish object properties. Not enumerable in `for...in` or `Object.keys()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q99. What is a WeakMap and when would you use it?

"A WeakMap is a collection of key-value pairs where keys must be objects, and those keys are held weakly."

The "Why" (The Killer Feature)
"Because the keys are held weakly, a WeakMap prevents memory leaks. If an object used as a key is deleted anywhere else in your application, JavaScript automatically wipes out its entry from the WeakMap and frees up that memory."

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q100. What is a WeakSet?

"A WeakSet is a collection of unique objects that are held weakly."

The "Why" (The Killer Feature)
"Because it holds objects weakly, it prevents memory leaks. If an object stored inside a WeakSet has no other active references left in your application, JavaScript's garbage collector will automatically wipe it out of the WeakSet and free up the memory."

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q101. What is a Map vs a plain object?

`Map`: any type as key (including objects), maintains insertion order, has `.size`, iterable directly, better performance for frequent additions/deletions, no prototype pollution risk. Plain object: string/symbol keys only, prototype chain pollution risk, JSON-serializable, simpler syntax. Use `Map` when keys are non-strings or when frequently mutating entries.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q102. What is a Set?

A collection of unique values (no duplicates). Values can be of any type. `Set` has methods: `add`, `has`, `delete`, `clear`, `size`. Iterable. Useful for deduplication, tracking unique items, and set math (union/intersection with spread + filter).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q103. What are iterators and iterables?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q104. What is the `for...of` loop?

Iterates over values of any iterable (arrays, strings, Maps, Sets, generators). `for (const item of arr) {}`. Supports `break`, `continue`, `return`. Unlike `forEach`, works with generators and custom iterables. Unlike `for...in`, iterates values not property names.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q105. What is the difference between `for...in` and `for...of`?

`for...in`: iterates over enumerable property KEYS (including inherited ones) of an object. Avoid on arrays (iterates indices as strings + any added prototype properties). `for...of`: iterates over VALUES of any iterable. Cannot be used on plain objects directly (they aren't iterable by default).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q106. What are tagged template literals?

A function called with a template literal. The function receives the string parts as an array and the interpolated values as separate arguments. Used by libraries like styled-components, GraphQL (`gql\`...\``), and SQL query builders to process template strings safely.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q107. What are ES2020+ features you should know?

Optional chaining `?.`, nullish coalescing `??`, `Promise.allSettled()`, `BigInt`, `globalThis`, dynamic import `import()`, `String.matchAll()`, logical assignment `&&=`/`||=`/`??=` (ES2021), `Array.at()` (ES2022), `Object.hasOwn()` (ES2022), `structuredClone()` (ES2022), top-level `await` (ES2022).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q108. What is the logical assignment operators (`&&=`, `||=`, `??=`)?

Short-circuit assignment operators. `a &&= b` — assign `b` to `a` only if `a` is truthy. `a ||= b` — assign `b` to `a` only if `a` is falsy. `a ??= b` — assign `b` to `a` only if `a` is `null`/`undefined`. More concise than full if-statements for conditional assignment.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q109. What are private class fields?

Declared with `#` prefix: `#privateField`. Accessible only inside the class body — not on instances, not via `Object.keys()`, not from subclasses. Enforced by the runtime (unlike the convention of `_private`). Also supports private methods and private static fields.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q110. What is `structuredClone()`?

A built-in global function for deep cloning objects. Handles circular references, `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`. Does NOT clone functions, DOM nodes, or class instances (their prototype). Available in modern browsers and Node.js 17+. Preferred over `JSON.parse(JSON.stringify())`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 9: Classes & Object-Oriented Programming

*OOP patterns in modern JavaScript.*

---

#### Q111. What is a class in JavaScript?

A template for creating objects, introduced in ES6. Syntactic sugar over constructor functions and prototypes. Defines a constructor, methods (on the prototype), static members (on the class itself), and private fields. Classes are NOT hoisted the same way as function declarations — they're in the TDZ.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q112. What is a constructor?

The special `constructor()` method in a class, called automatically when `new ClassName()` is used. It sets up the initial state of the instance via `this`. If not defined, a default empty constructor is used. In derived classes, `super()` must be called before accessing `this`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q113. What is inheritance with `extends` and `super`?

`extends` sets up the prototype chain between classes. `super()` in a derived constructor calls the parent's constructor. `super.method()` calls a parent's method. A derived class must call `super()` before accessing `this` in the constructor — otherwise `ReferenceError`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q114. What are static methods and properties?

Defined on the class itself, not on instances. Called as `ClassName.method()`. Cannot access instance properties via `this` (though `this` refers to the class). Used for utility functions, factory methods, or class-level constants. `static #private` is also supported.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q115. What are getters and setters?

`get` and `set` keywords create accessor properties. `get` defines a function called when the property is read; `set` defines a function called when it's assigned. Allow computed or validated properties with a simple property-access syntax. Defined in class body or via `Object.defineProperty`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q116. What is method chaining?

Returning `this` from methods to allow calling multiple methods on the same object in sequence: `builder.setName('x').setAge(5).build()`. Common in jQuery, Lodash, query builders, and the Builder pattern. Makes code more fluent and readable.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q117. What is polymorphism in JavaScript?

Different objects responding to the same interface/method call in different ways. In JS, achieved through method overriding in subclasses. Since JS is duck-typed, any object with the right method can be used polymorphically without explicit inheritance.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q118. What is encapsulation and how is it achieved in JS?

Bundling data and methods that operate on that data, restricting direct access to internal state. Achieved via: closures (private state in factory functions), private class fields (`#field`), and conventions like `_private` (not enforced). Forces consumers to use the public API.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q119. What is the difference between composition and inheritance?

Inheritance ("is-a"): extend a base class to reuse behavior — creates tight coupling, fragile base class problem. Composition ("has-a"): combine small, focused objects/functions to build complex behavior — more flexible, loosely coupled. Prefer composition over inheritance for reusability (famous GoF principle).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q120. What is a mixin?

A pattern to add methods from one object to another without inheritance. `Object.assign(TargetClass.prototype, mixin)`. Enables sharing behavior across unrelated class hierarchies. No native mixin support in JS — it's a convention using `Object.assign` or object spread.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 10: Error Handling

*Writing robust, fail-safe JavaScript.*

---

#### Q121. What is a `try/catch/finally` block?

`try`: code that might throw. `catch(err)`: runs if an error is thrown — `err` is the Error object. `finally`: always runs regardless of success or failure — used for cleanup. `throw` can throw any value, but throw Error objects for best debuggability (stack trace).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q122. What is the `Error` object?

Has properties: `name` (type of error, e.g., `'TypeError'`), `message` (description), `stack` (stack trace string, non-standard but universally supported), `cause` (ES2022 — error that caused this one, for chaining). Create with `new Error('message')`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q123. What are the built-in error types?

`Error` (base), `TypeError` (wrong type), `ReferenceError` (variable not found), `SyntaxError` (invalid syntax, usually parse-time), `RangeError` (value out of range, e.g., stack overflow), `URIError` (malformed URI), `EvalError` (eval-related, rare). Each is a constructor — check with `err instanceof TypeError`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q124. How do you create a custom error?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q125. How do you handle errors in Promises?

`.catch(fn)` at the end of a chain handles any rejection in the chain. Can also pass a rejection handler as the second argument to `.then(null, onRejected)`. In `async/await`, use `try/catch`. Always handle promise rejections — unhandled rejections crash Node.js and cause console warnings in browsers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q126. What is an unhandled promise rejection?

A Promise that rejects with no `.catch` handler. In Node.js, unhandled rejections emit a warning and can crash the process. In browsers, they fire `window.onunhandledrejection`. Listen to `process.on('unhandledRejection', handler)` in Node.js for a global safety net.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q127. What does `finally` do in a Promise chain?

`.finally(fn)` runs `fn` regardless of whether the promise resolved or rejected. Useful for cleanup (hiding loading spinners, closing connections). It doesn't receive the resolved value or rejection reason. It passes the original outcome to the next handler in the chain.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q128. Situation: Error thrown inside `setTimeout` – does `try/catch` catch it?

No. The `try/catch` has already exited by the time the `setTimeout` callback runs (it runs in a future event loop iteration). Handle errors inside the callback itself with an inner `try/catch`, or use `window.onerror` / `process.on('uncaughtException')` for a global handler.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 11: The DOM & Browser APIs

*Interacting with the browser environment.*

---

#### Q129. What is the DOM?

The Document Object Model — a tree-structured representation of an HTML document created by the browser. JavaScript uses the DOM API to read and manipulate the page's structure, content, and styles. Each HTML element becomes a Node object with properties and methods.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q130. How do you select DOM elements?

`document.getElementById('id')` — returns single element. `document.querySelector('css-selector')` — returns first match. `document.querySelectorAll('css-selector')` — returns NodeList of all matches. `document.getElementsByClassName('cls')` / `getElementsByTagName('tag')` — live HTMLCollections. Prefer `querySelector`/`querySelectorAll` for flexibility.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q131. What is the difference between `innerHTML`, `textContent`, and `innerText`?

`innerHTML`: gets/sets HTML content (parses HTML — XSS risk with user input). `textContent`: gets/sets text content of an element and all descendants (no HTML parsing — safe, fast, includes hidden elements). `innerText`: like `textContent` but respects CSS (doesn't include hidden elements, triggers layout). Use `textContent` for safety and performance.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q132. How do you create, append, and remove DOM elements?

Create: `document.createElement('div')`. Set content: `el.textContent = 'text'` or `el.setAttribute('class', 'box')`. Append: `parent.appendChild(el)` or `parent.append(el)` (newer, accepts strings). Insert: `parent.insertBefore(el, ref)` or `el.insertAdjacentElement('position', newEl)`. Remove: `el.remove()` or `parent.removeChild(el)`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q133. What is event bubbling and capturing?

Events propagate in three phases: **Capture phase** (top → target), **Target phase** (at element), **Bubble phase** (target → top). By default, event listeners use bubbling. Pass `true` or `{capture: true}` to `addEventListener` to listen during capture phase. Most events bubble; some don't (e.g., `focus`, `blur` — use `focusin`/`focusout`).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q134. What is `event.stopPropagation()` vs `event.preventDefault()`?

`stopPropagation()`: stops the event from bubbling up (or capturing down) to parent elements. `preventDefault()`: prevents the browser's default action (form submission, link navigation, checkbox toggle). They are independent — you can call one, both, or neither. `stopImmediatePropagation()` also prevents other listeners on the same element.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q135. What is event delegation?

Attaching a single event listener to a parent element instead of individual listeners on each child. Uses event bubbling — events from children bubble up to the parent. Check `event.target` to determine which child was clicked. More efficient for dynamic lists; fewer memory-consuming listeners.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q136. What is the difference between `addEventListener` and `onclick`?

`onclick` is an element property — only one handler can be set (later assignment overrides). `addEventListener` allows multiple handlers for the same event on the same element, supports capture phase, and can be removed with `removeEventListener`. Always prefer `addEventListener`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q137. What is the `DOMContentLoaded` vs `load` event?

`DOMContentLoaded`: fires when HTML is fully parsed and DOM is ready — before images/stylesheets finish loading. `load` (on `window`): fires when ALL resources (images, styles, scripts) have loaded. Use `DOMContentLoaded` for DOM manipulation that doesn't depend on images; use `load` when you need images to be loaded.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q138. What is `localStorage` vs `sessionStorage` vs cookies?

`localStorage`: persists until explicitly cleared, ~5MB, origin-scoped, not sent with requests. `sessionStorage`: persists per tab until tab closes, ~5MB, not sent with requests. `cookies`: sent with every HTTP request (for auth), can have expiry, smaller (~4KB), can be HttpOnly (not accessible by JS) — critical for security.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q139. What is the `fetch` API?

A modern Promise-based API for HTTP requests, replacing `XMLHttpRequest`. `fetch(url, options)` returns a Promise of a `Response`. You must call `.json()`, `.text()`, or `.blob()` to read the body (also async). A `fetch` only rejects on network failure — not on 4xx/5xx responses (check `response.ok`).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q140. What is CORS?

Cross-Origin Resource Sharing — a browser security mechanism that restricts cross-origin HTTP requests. Servers must send `Access-Control-Allow-Origin` headers to allow cross-origin access. Simple requests (GET, POST with certain content-types) go through; complex requests trigger a preflight `OPTIONS` request. CORS is a browser restriction — it doesn't apply to server-to-server requests.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q141. What is the Intersection Observer API?

An async API to observe when an element enters or leaves the viewport (or another element). More performant than scroll event listeners. Use for: lazy loading images, infinite scroll, animations on scroll, analytics visibility tracking.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q142. What is the MutationObserver API?

Watches for changes to the DOM tree (child additions/removals, attribute changes, text changes). Fires asynchronously (as a microtask). Use when you need to react to DOM changes made by third-party scripts or when you can't use your own state management.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q143. What is the History API?

`history.pushState(state, title, url)` — adds an entry to the browser's history stack and changes the URL without a page reload. `history.replaceState()` — replaces current entry. `window.onpopstate` — fires when user navigates back/forward. Foundation of client-side routing in SPAs.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 12: Memory Management & Performance

*Writing fast, leak-free JavaScript.*

---

#### Q144. How does garbage collection work in JavaScript?

JS uses automatic GC, primarily via mark-and-sweep: starting from roots (global, stack), mark all reachable objects. Anything unreachable is garbage and its memory is freed. Modern engines use generational GC (young/old generation), incremental GC, and idle-time GC to minimize pauses.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q145. What is a memory leak and what causes them?

Memory that is no longer needed but not released because references still exist. Common causes: forgotten event listeners (not removed), closures holding large objects, global variables accumulating data, DOM references held after nodes are removed, detached DOM nodes, `setInterval` never cleared.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q146. What is debouncing?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q147. What is throttling?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q148. What is the difference between debounce and throttle?

Debounce: waits for a pause in calls — only fires once after the activity stops. Good for: search input, form validation on type. Throttle: fires at regular intervals during continuous activity — guarantees execution frequency. Good for: scroll position tracking, drag events, game loops.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q149. What is lazy loading?

Deferring loading of resources (images, modules, components) until they're actually needed. Reduces initial page load. For images: `<img loading="lazy">` or Intersection Observer. For code: dynamic `import()` — `const mod = await import('./module.js')`. Both reduce time-to-interactive.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q150. What are Web Workers?

Background threads that run JS code without blocking the main thread. No DOM access. Communicate with the main thread via `postMessage`/`onmessage`. Use for CPU-intensive tasks (image processing, crypto, parsing large JSON). Shared Workers can be accessed by multiple tabs. Service Workers intercept network requests.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q151. What is `requestAnimationFrame` and why use it for animations?

Schedules a callback before the browser's next repaint (~60fps). Pauses automatically when tab is hidden (saves battery/CPU). Passes a timestamp for smooth, frame-rate-independent animations. Much better than `setInterval` for visual updates because it syncs with the display refresh cycle.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q152. What is reflow and repaint?

**Reflow (layout)**: browser recalculates positions/dimensions of elements — expensive, cascades. Triggered by: adding/removing elements, changing size/position/font. **Repaint**: browser redraws pixels — less expensive. Triggered by: changing color, visibility, shadow. Minimize by batching DOM changes, using `documentFragment`, CSS transforms (GPU-composited), and avoiding reading layout properties in a loop.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q153. How do you profile JavaScript performance?

Browser DevTools Performance panel: record, then analyze flame chart for long tasks, scripting time, rendering. Memory panel: take heap snapshots to find leaks. `console.time()` / `console.timeEnd()` for rough timing. `performance.mark()` / `performance.measure()` for precise custom measurements via Performance API.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 13: Design Patterns

*Proven solutions to recurring JavaScript design problems.*

---

#### Q154. What is the Module pattern?

Uses an IIFE or ES modules to encapsulate private state and expose a public API. Prevents global namespace pollution. The classic pre-module pattern:
```javascript
const counter = (function() {
  let count = 0;
  return { increment: () => ++count, getCount: () => count };
})();
```

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q155. What is the Singleton pattern?

Ensures only one instance of an object exists. In JS, module-level variables are naturally singletons (module is cached after first import). Classic implementation uses a closure that stores the instance and returns it on all subsequent calls.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q156. What is the Observer / Pub-Sub pattern?

Objects (subscribers) register interest in events. When an event occurs, the publisher notifies all subscribers. EventEmitter in Node.js, `addEventListener` in the browser, Redux's store, and RxJS all implement this pattern. Decouples the event source from event consumers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q157. What is the Factory pattern?

A function that creates and returns objects without using `new` and classes directly. Allows encapsulating creation logic and returning different object types based on input. More flexible than constructors — can return cached instances, different implementations, or augmented objects.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q158. What is the Decorator pattern?

Wraps an object or function to extend its behavior without modifying the original. In JS: higher-order functions (`withLogging(fn)`), ES decorators (TC39 proposal, used in TypeScript/Angular), or manually wrapping objects. Used for logging, caching, authentication, validation.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q159. What is the Strategy pattern?

Defines a family of algorithms, encapsulates each, and makes them interchangeable. In JS, pass different functions to the same interface: `sort(arr, ascendingStrategy)` vs `sort(arr, descendingStrategy)`. Eliminates complex if/else chains, follows Open/Closed Principle.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q160. What is the Proxy pattern?

Wraps an object to intercept and control access to its properties. ES6 `Proxy` enables this natively. Use for: validation, logging, access control, caching, reactive systems (Vue 3 uses Proxy for reactivity), API mocking.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q161. What is the Command pattern?

Encapsulates a request as an object, enabling undo/redo, queuing, logging, and parameterization of operations. In JS: `{ execute: fn, undo: fn }`. Used in text editors, Redux (actions are commands), and task queues.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q162. What is the Revealing Module pattern?

A variation of the Module pattern where all functions/variables are defined privately, and an object literal is returned that reveals only the public members by name. Makes clear what's public and what's private.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 14: Modules & Tooling

*How modern JavaScript is organized and built.*

---

#### Q163. What are ES Modules (`import`/`export`)?

The official standard module system. Static `import`/`export` declarations are analyzed at parse time (enables tree shaking). Modules have their own scope, are strict by default, run once (cached), and support cyclic dependencies. Works in modern browsers (`<script type="module">`) and Node.js (`.mjs` or `"type":"module"` in package.json).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q164. What is the difference between default and named exports?

Named: `export const foo = 1` — imported as `import { foo } from './m'`. Can have many per file. Import name must match (or be aliased with `as`). Default: `export default value` — imported as `import anything from './m'`. Only one per file. Named exports are preferred for tree-shaking and refactoring safety.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q165. What is CommonJS (`require`/`module.exports`)?

Node.js's original module system. `const x = require('./x')` — synchronous, evaluated at runtime. `module.exports = value` to export. Modules are cached after the first load. Can export a function, object, or primitive. Cannot be statically analyzed (limits tree shaking).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q166. What is the difference between CommonJS and ES Modules?

CJS: synchronous `require`, `module.exports`, dynamic (can be conditional), not statically analyzable, default in Node.js. ESM: asynchronous, static `import`/`export`, tree-shakeable, `this` is `undefined` at module level, supported in browsers natively. ESM is the future standard; Node.js supports both.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q167. What is tree shaking?

Dead code elimination based on static analysis of ES module imports/exports. Bundlers (Rollup, Webpack, Vite) detect exported code that's never imported and exclude it from the bundle. Requires: ES modules (not CJS), no side-effectful imports, correct `sideEffects` field in package.json.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q168. What is a bundler (Webpack, Rollup, Vite)?

A tool that takes JavaScript modules (and other assets) and combines them into optimized files for deployment. Handles dependency resolution, code splitting, tree shaking, minification, and asset processing. Webpack: powerful, configurable, most popular. Rollup: great for libraries (clean ESM output). Vite: fast dev server with native ESM + Rollup for production.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q169. What is transpilation and what does Babel do?

Transpilation converts modern JS (ES2022+) to older JS (ES5) so it runs in older browsers. Babel: a popular transpiler with plugin/preset system. Transforms JSX, TypeScript, and modern syntax. In Vite projects, esbuild handles basic transpilation faster; Babel needed only for advanced transforms.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q170. What is source mapping?

A file (`.map`) that maps minified/transpiled code back to the original source. Enables debugging production code with original source in DevTools. Generated by bundlers/transpilers. Should be served in staging, sometimes restricted in production.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 15: Functional Programming

*Writing JS in a functional style.*

---

#### Q171. What is functional programming?

A programming paradigm treating computation as evaluation of mathematical functions. Key principles: pure functions, immutability, no side effects, function composition, declarative style. JavaScript supports both OOP and FP — you can mix them. Libraries: Ramda, Lodash/fp.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q172. What is immutability and why does it matter?

Data that cannot be changed after creation. Instead of mutating, create new data. Benefits: predictability, easier debugging, safe sharing between functions, enables undo/redo, time-travel debugging. In JS: use `const` for bindings, spread for objects/arrays, `Object.freeze()` for true immutability, or libraries like Immer.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q173. What are side effects?

Any interaction with the outside world from within a function: modifying external variables, DOM manipulation, network requests, logging, reading from `Date.now()`. Functions with side effects are harder to test and predict. FP separates pure computation from side effects — push side effects to the edges of your program.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q174. What is function composition vs piping?

Both combine functions. **Composition** (`compose`): right-to-left — `compose(f, g)(x)` = `f(g(x))`. **Piping** (`pipe`): left-to-right — `pipe(g, f)(x)` = `f(g(x))`. Pipe is more readable for most developers (data flows left to right). Both create new functions from combining existing ones.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q175. What is partial application?

Fixing some arguments of a function, producing a function with fewer arguments. Unlike currying (one argument at a time), partial application fixes any number. `const double = multiply.bind(null, 2)`. Useful for creating specialized functions from general ones.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q176. What is a functor?

An object with a `map` method that applies a function to the value inside it and returns the same type. Arrays are functors. Promises are almost functors (`.then`). Functors allow you to transform values inside containers without extracting them — a key FP concept.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q177. What is point-free style?

Writing functions without explicitly mentioning their arguments. `const double = map(x => x * 2)` vs `const double = arr => arr.map(x => x * 2)`. The first is point-free. Achievable through currying and composition. Can improve readability but can also obscure intent if overused.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 16: JavaScript Security

*Writing secure JavaScript.*

---

#### Q178. What is XSS (Cross-Site Scripting)?

An attack where malicious scripts are injected into web pages viewed by other users. Types: Stored (persisted in DB), Reflected (in URL), DOM-based (via client-side JS). Prevention: escape all user output (use `textContent` not `innerHTML`), CSP headers, sanitize with DOMPurify, avoid `eval()`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q179. What is CSRF (Cross-Site Request Forgery)?

Tricks authenticated users into making unintended requests to a site they're logged into. Prevention: CSRF tokens (unique per session, validated server-side), `SameSite=Strict` or `SameSite=Lax` cookies, check `Origin`/`Referer` headers, avoid side effects from GET requests.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q180. What is Content Security Policy (CSP)?

An HTTP header that tells browsers which sources of content are allowed (scripts, styles, images, fonts). Mitigates XSS by blocking inline scripts and unauthorized external scripts. `Content-Security-Policy: script-src 'self' https://trusted.com`. Use `nonce` or `hash` for necessary inline scripts.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q181. Why is `eval()` dangerous?

Executes arbitrary code strings — a major XSS vector if user input reaches it. Bypasses security, slows performance (JIT can't optimize code inside eval), and makes debugging harder. Never use `eval()` with untrusted input. Also avoid `Function()`, `setTimeout('code string')`, `setInterval('code string')`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q182. What is prototype pollution?

An attack where `__proto__`, `constructor`, or `prototype` properties are set on user-supplied objects, affecting all objects in the application. Can be used to override methods on `Object.prototype`. Prevention: validate input keys (reject `__proto__`), use `Object.create(null)` for dictionaries, use `Map` instead of plain objects for user data.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q183. How do you securely handle user input in JavaScript?

Never trust user input. Validate on both client (UX) and server (security). Escape before inserting into DOM (use `textContent`). Sanitize HTML with DOMPurify if HTML is needed. Use parameterized queries for databases. Encode for the output context (HTML, URL, JS).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q184. What is clickjacking and how do you prevent it?

An attack where a transparent iframe overlays a legitimate site, tricking users into clicking on hidden elements. Prevention: `X-Frame-Options: DENY` or `SAMEORIGIN` HTTP header, or CSP `frame-ancestors 'none'` directive.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 17: JavaScript Runtime & Node.js Basics

*Understanding JS outside the browser.*

---

#### Q185. What is Node.js?

A JavaScript runtime built on Chrome's V8 engine. Enables server-side JavaScript. Non-blocking I/O via an event loop (powered by libuv). Single-threaded for JS execution but uses threads internally for I/O. Ideal for I/O-heavy apps (APIs, real-time, streaming); less ideal for CPU-heavy tasks (use Worker Threads).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q186. What is the difference between the browser and Node.js environments?

Browser: has DOM, window, document, browser APIs (fetch, localStorage, alert), sandboxed. Node.js: has no DOM, has `process`, `__dirname`, `__filename`, `require`, built-in modules (`fs`, `http`, `path`, `crypto`, `os`), full file system access, can run servers. Both run the same JS language.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q187. What is the Node.js event loop vs the browser event loop?

Both use the event loop pattern but with different phases. Node.js (libuv): has explicit phases — timers → pending callbacks → idle/prepare → poll (I/O) → check (setImmediate) → close callbacks. Browser event loop is simpler. Key difference: Node has `setImmediate` and `process.nextTick` (runs before everything else in the current iteration).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q188. What is `process.nextTick()`?

Schedules a callback to run at the end of the current iteration of the Node.js event loop, before any I/O events or timers. Runs before Promises (microtasks) in Node.js's implementation. Use sparingly — too many nextTick callbacks can starve the event loop.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q189. What is npm and what is `package.json`?

npm (Node Package Manager): the default package manager for Node.js. Manages project dependencies, scripts, and publishing. `package.json`: manifest file containing project metadata, dependencies, devDependencies, scripts (`start`, `test`, `build`), version, and configuration for tools.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q190. What is the difference between `dependencies` and `devDependencies`?

`dependencies`: packages needed to run the app in production (Express, React, Lodash). `devDependencies`: packages needed only during development (Jest, ESLint, Babel, TypeScript). Distinguishing them matters for keeping production `node_modules` lean. `npm install --production` skips devDependencies.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 18: TypeScript Fundamentals (JS Context)

*TypeScript knowledge expected in most modern JS interviews.*

---

#### Q191. What is TypeScript and how does it relate to JavaScript?

TypeScript is a superset of JavaScript — all valid JS is valid TypeScript. It adds static type annotations that are removed at compile time (transpiled to plain JS). Provides compile-time type checking, better IDE support, and self-documenting code. Maintained by Microsoft.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q192. What are the basic types in TypeScript?

Primitive: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`. Object: `object`, `array` (`number[]` or `Array<number>`), tuple (`[string, number]`), `enum`. Special: `any` (opts out of checking), `unknown` (safe any), `never` (never returns), `void` (no return value).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q193. What is `any` vs `unknown` in TypeScript?

`any`: disables type checking entirely — you can do anything with it. Unsafe. `unknown`: type-safe alternative to `any`. You can't perform operations on `unknown` without first narrowing its type (type guard, assertion). Prefer `unknown` over `any` when type is truly unknown.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q194. What is a type assertion?

Telling TypeScript "trust me, I know the type of this value." `const el = document.getElementById('btn') as HTMLButtonElement`. Doesn't do runtime conversion — purely compile-time. Use when you have more context than the type system. Can use `as Type` or `<Type>value` (JSX incompatible).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q195. What is a union type vs intersection type?

Union (`A | B`): the value can be type A OR type B. Use with type guards to narrow. Intersection (`A & B`): the value must satisfy BOTH type A AND type B — combines all properties. Union is OR; intersection is AND.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q196. What are generics in TypeScript?

A way to write reusable code that works with multiple types. `function identity<T>(arg: T): T { return arg; }`. The type parameter `T` is a placeholder filled in at usage. Used in containers, utilities, and APIs to maintain type safety without losing flexibility.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q197. What is the difference between `interface` and `type`?

`interface`: can be merged (declaration merging), better for object shapes and OOP. `type`: more flexible — can represent primitives, unions, intersections, tuples, mapped types. Both can extend each other (`interface extends type` and vice versa). For objects, either works; prefer `interface` for public APIs, `type` for complex type math.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q198. What is type narrowing?

Reducing a broad type to a more specific type within a code branch using type guards. Methods: `typeof` checks, `instanceof`, `in` operator, truthiness checks, equality checks, discriminated unions, user-defined type predicates (`fn(x): x is Type`). TypeScript understands these patterns and narrows the type automatically.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 19: Testing JavaScript

*Ensuring code quality with automated tests.*

---

#### Q199. What is unit testing?

Testing individual functions or modules in isolation. Fast, focused, no external dependencies (use mocks/stubs). Verifies that a unit of code produces the correct output for a given input. Foundation of the testing pyramid. Tools: Jest, Vitest, Mocha.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q200. What is Jest?

The most popular JavaScript testing framework. Zero-config by default, built-in mocking, code coverage, snapshot testing, and assertion library. Works with Node.js and browser environments (via jsdom). Supports TypeScript via Babel or ts-jest.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q201. What are mocks, stubs, and spies?

**Mock**: replaces an entire module or function with a fake implementation. **Stub**: provides canned responses for specific calls (controls what a dependency returns). **Spy**: wraps real implementation to record calls (what args, how many times). Jest's `jest.fn()` and `jest.spyOn()` cover all these.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q202. What is TDD (Test-Driven Development)?

Write tests first (failing), then write the minimum code to make them pass, then refactor. Cycle: Red → Green → Refactor. Benefits: forces clear requirements, prevents over-engineering, provides instant regression coverage. Can be slower initially but reduces debugging time.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q203. How do you test asynchronous code in Jest?

Return a Promise from the test, or use `async/await`. Use `done` callback for callback-style APIs. Jest's fake timers (`jest.useFakeTimers()`) control `setTimeout`/`setInterval`. Mock `fetch` or use MSW for network calls. `await waitFor(() => expect(...))` for async DOM updates.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q204. What is code coverage?

A metric showing what percentage of your code is executed by tests. Types: line coverage, branch coverage (if/else paths), function coverage, statement coverage. Run with `jest --coverage`. 100% coverage doesn't mean bug-free — focus on meaningful tests, not chasing numbers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q205. What is the difference between unit, integration, and E2E tests?

**Unit**: tests one function/module in isolation — fast, deterministic. **Integration**: tests how multiple units work together — may use real database/service or mocks. **E2E**: tests the full application in a real browser — slowest, most realistic (Playwright, Cypress). Balance: many unit, some integration, few E2E.

[⬆ Back to Table of Contents](#-table-of-contents)

---

## Section 20: Senior-Level & Tricky Scenario Questions

*Separating good developers from great ones.*

---

#### Q206. What is the output of `0.1 + 0.2 === 0.3` and why?

`false`. JavaScript uses IEEE 754 double-precision floating point. `0.1 + 0.2` is `0.30000000000000004`. Binary can't represent 0.1 or 0.2 exactly. Fix: `Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON`, or use `toFixed()` for display, or use integer arithmetic (work in cents not dollars).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q207. What is the difference between `Object.assign()` and spread?

Both create shallow copies/merges. Differences: `Object.assign` invokes setters on the target; spread doesn't. `Object.assign` mutates the target; spread always creates a new object. `Object.assign` copies inherited enumerable properties from the source if they're own properties; spread copies own enumerable properties. For most cases, they're interchangeable.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q208. Explain how `Array.prototype.reduce` works from scratch.

Takes a callback `(accumulator, currentValue, index, array) => newAccumulator` and an optional initial value. If no initial value, uses the first element. Iterates each element, passing the accumulator (starts as initial value or first element) to the callback, using the return value as the next accumulator. Returns the final accumulator.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q209. Implement a deep clone function.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q210. Implement a debounce function from scratch.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q211. Implement a throttle function from scratch.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q212. Implement `Promise.all` from scratch.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q213. What is the output: `typeof null`?

`'object'`. This is a well-known bug in JavaScript that has persisted since its first implementation and cannot be fixed without breaking existing code. The original implementation used low-order bits to tag types, and null's representation had the same bits as object tags.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q214. What is the output: `[] == ![]`?

`true`. Steps: `![]` is `false` (arrays are truthy). `[] == false` → `[] == 0` (false to number). `[] == 0` → `'' == 0` (array to primitive → empty string). `'' == 0` → `0 == 0` → `true`. This is a classic demonstration of why `==` should be avoided.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q215. How does JavaScript handle integer overflow?

JavaScript's `Number` type is a 64-bit IEEE 754 float. Safe integer range is `-(2^53 - 1)` to `2^53 - 1` (`Number.MAX_SAFE_INTEGER`). Beyond this, integers lose precision (no overflow/crash, just wrong values). Use `BigInt` for arbitrary-precision integers.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q216. What is `BigInt` and when do you use it?

A numeric type for integers of arbitrary size: `9007199254740993n`. Append `n` to a literal or use `BigInt(value)`. Cannot be mixed with regular `Number` in operations. Use when: working with IDs from languages that use 64-bit integers, cryptography, precise large integer arithmetic, or any value exceeding `Number.MAX_SAFE_INTEGER`.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q217. How would you implement an event emitter?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q218. How would you implement `curry` function from scratch?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q219. What is the Proxy object and how is it used?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q220. What is `Reflect` in JavaScript?

A built-in object with static methods mirroring Proxy handler traps. `Reflect.get(obj, key)`, `Reflect.set(obj, key, val)`, `Reflect.has(obj, key)`, etc. Used inside Proxy handlers to invoke default behavior after custom logic. Also useful as a cleaner alternative to some `Object` methods.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q221. Situation: Design a retry mechanism for a failed API call.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q222. Situation: How do you cancel a fetch request?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q223. What is tail call optimization?

A JS engine optimization where if a function's last action is calling another function (`return fn()`), the current stack frame can be replaced instead of adding a new one — enabling O(1) stack space for tail-recursive functions. Specified in ES6 strict mode, but only Safari actually implements it. In practice, use loops or trampolining for deep recursion.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q224. Explain the difference between `Array.from()` and spread on a NodeList.

Both convert array-like/iterables to arrays. `Array.from(nodeList)` works on any array-like (has `length` and indexed items — even without `Symbol.iterator`). Spread `[...nodeList]` requires the object to be iterable (`Symbol.iterator`). NodeLists are iterable in modern browsers, so both work there. `Array.from` also accepts a map function as second argument.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q225. What is the `void` operator?

`void expression` evaluates the expression and returns `undefined`. Used in `<a href="void(0)">` to prevent navigation. Also used in arrow functions to explicitly return `undefined` and signal no return value is intended: `const handler = () => void doSomething()`. Rarely needed in modern code.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q226. What are the tricky parts of `==` type coercion rules?

Key rules: if one side is a number, convert the other to number. If one side is a boolean, convert boolean to number first. Objects are converted to primitives via `valueOf()` then `toString()`. `null == undefined` is `true`, but `null == 0` is `false`. `NaN == NaN` is `false`. These inconsistencies are why `===` is always preferred.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q227. How does JavaScript sort arrays by default and what is the gotcha?

`Array.prototype.sort()` converts elements to strings and sorts lexicographically by default. `[10, 9, 2, 1, 100].sort()` gives `[1, 10, 100, 2, 9]`. For numeric sort, always provide a comparator: `arr.sort((a, b) => a - b)` for ascending. `.sort()` mutates the original array.

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q228. Implement `Array.prototype.flat` from scratch.

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q229. What is the difference between `Object.create(null)` and `{}`?

`{}` creates an object with `Object.prototype` in its prototype chain — it has `toString`, `hasOwnProperty`, `valueOf`, etc. `Object.create(null)` creates a truly empty object with NO prototype — no inherited methods. Useful as a pure hash map (no risk of key collisions with prototype properties like `'toString'` or `'constructor'`).

[⬆ Back to Table of Contents](#-table-of-contents)

---

#### Q230. How would you implement infinite scrolling with vanilla JS?

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

[⬆ Back to Table of Contents](#-table-of-contents)

---

*300 questions across 20 sections. Master these and crack 95% of JavaScript interviews! 🟨*
