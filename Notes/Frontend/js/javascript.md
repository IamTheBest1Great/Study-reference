# JavaScript – Comprehensive Interview Question Bank

**225+ Questions across 18 sections**

*Fundamentals · Types · Functions · Async · OOP · Patterns · Performance · Runtime · Senior Scenarios*

---

## Section 1: Fundamentals & Language Basics

*Core concepts every JavaScript developer must know cold.*

**Q1. What is JavaScript and where does it run?**

JavaScript is a high-level, interpreted, single-threaded, dynamically typed programming language originally designed for web browsers. It now runs in many environments (Node.js, Deno, Bun, embedded systems) thanks to standalone JS engines like V8, SpiderMonkey, and JavaScriptCore.

**Q2. What is the ECMAScript specification?**

ECMAScript (ES) is the standardized specification that JavaScript implements, maintained by TC39. Versions like ES5, ES6/ES2015, ES2020, ES2022 added major features. New proposals move through a 5-stage process (Stage 0–4) before being incorporated into the spec.

**Q3. What is the difference between JavaScript and TypeScript?**

TypeScript is a statically typed superset of JavaScript that compiles down to plain JS. TypeScript adds interfaces, generics, enums, and type annotations. These are erased at compile time – runtime behavior is identical to JS.

**Q4. What are the primitive types in JavaScript?**

`string`, `number`, `bigint`, `boolean`, `undefined`, `null`, `symbol`. Primitives are immutable and stored by value. Everything else (objects, arrays, functions) is an object stored by reference.

**Q5. What is `typeof` and what are its quirks?**

`typeof` returns a string indicating the type. Notable quirks: `typeof null === 'object'` (historical bug), `typeof function(){}  === 'function'` (special case), `typeof undeclaredVar === 'undefined'` (safe without ReferenceError).

**Q6. What is the difference between `==` and `===`?**

`===` (strict equality) checks value and type with no coercion. `==` (loose equality) performs type coercion before comparing. Prefer `===` always; `==` produces surprising results like `0 == ''` being `true`.

**Q7. What is type coercion?**

JavaScript automatically converts a value from one type to another when an operator or context requires it. E.g., `'5' - 2 === 3` (string coerced to number), `'5' + 2 === '52'` (number coerced to string). Implicit coercion is a common source of bugs.

**Q8. What are truthy and falsy values?**

Falsy: `false`, `0`, `-0`, `0n`, `''`, `null`, `undefined`, `NaN`. Everything else is truthy, including `[]`, `{}`, `'0'`, and `'false'`. Used in boolean contexts like `if` conditions and logical operators.

**Q9. What is `NaN` and how do you check for it?**

`NaN` (Not a Number) is a numeric value indicating a failed numeric operation. It is the only value in JS not equal to itself (`NaN !== NaN`). Use `Number.isNaN(val)` for reliable checking — unlike the global `isNaN()`, it does not coerce first.

**Q10. What is the difference between `null` and `undefined`?**

`undefined` means a variable has been declared but not assigned. `null` is an explicit assignment representing intentional absence of value. `typeof undefined === 'undefined'`; `typeof null === 'object'`. Both are falsy but `null == undefined` is true while `null === undefined` is false.

**Q11. What is variable hoisting?**

Declarations (not initializations) are moved to the top of their scope during compilation. `var` declarations are hoisted and initialized to `undefined`. `let` and `const` are hoisted but not initialized — accessing them before declaration throws a ReferenceError (Temporal Dead Zone).

**Q12. What is the Temporal Dead Zone (TDZ)?**

The period between entering a block scope and the declaration of a `let` or `const` variable. Accessing the variable in the TDZ throws a `ReferenceError`. This is why `let`/`const` feel like they're "not hoisted" even though they technically are.

**Q13. What are the differences between `var`, `let`, and `const`?**

`var`: function-scoped, hoisted, can be re-declared, no block scoping. `let`: block-scoped, not hoisted usably (TDZ), cannot be re-declared. `const`: block-scoped, must be initialized, cannot be reassigned (though object contents can be mutated). Prefer `const` by default, `let` when reassignment is needed, avoid `var`.

**Q14. What is strict mode?**

`'use strict'` at the top of a file or function enables strict mode. It prevents use of undeclared variables, disables `with`, makes `this` undefined in regular functions (not `window`), disallows duplicate parameter names, and throws on otherwise-silent errors.

**Q15. What is the difference between a statement and an expression?**

An expression produces a value (`2 + 2`, `fn()`, `x ? a : b`). A statement performs an action (`if`, `for`, `return`, `throw`). Some constructs can be either — function declarations are statements; function expressions are expressions.

---

## Section 2: Scope, Closures & the Execution Context

*Understanding how JavaScript finds and stores variables.*

**Q16. What is scope in JavaScript?**

Scope defines where variables are accessible. JavaScript has global scope, function scope, and block scope (ES6+). The scope chain is the hierarchy of scopes searched when resolving a variable name, from innermost outward.

**Q17. What is lexical scoping?**

Lexical scoping means a function's scope is determined by where it is defined in the source code, not where it is called. Inner functions have access to the variables of their outer functions at the time of definition.

**Q18. What is a closure?**

A closure is a function that retains access to its lexical scope even after the outer function has returned. The inner function "closes over" the variables of the outer function. Used for data privacy, partial application, memoization, and module patterns.

**Q19. Give a practical use case for closures.**

A counter factory: `function makeCounter() { let count = 0; return () => ++count; }`. Each call to `makeCounter()` creates an independent counter with private state. The inner function closes over `count` and it cannot be accessed or modified externally.

**Q20. What is the execution context?**

An abstract concept representing the environment in which JavaScript code runs. Each context has a Variable Environment (scope), a `this` binding, and an Outer Environment reference. The Global Execution Context is created first; function calls create new ones pushed onto the Call Stack.

**Q21. What is the Call Stack?**

A LIFO (Last In, First Out) data structure tracking function calls. When a function is invoked, a new frame is pushed; when it returns, it's popped. Stack overflow occurs when recursion is too deep or a function never returns.

**Q22. What is scope chain resolution?**

When a variable is referenced, JS searches the current scope first, then each outer scope up to global. If not found, a `ReferenceError` is thrown. This chain is established at function definition time (lexical scoping).

**Q23. What is the module scope?**

In ES modules (`.mjs` or `<script type="module">`), the top-level is module scope — not global. Variables declared at the top are not on `window`. Modules also enforce strict mode by default.

**Q24. What is IIFE (Immediately Invoked Function Expression) and why was it used?**

`(function() { /* code */ })()` — a function defined and immediately called. Used pre-ES6 to create a local scope and avoid polluting the global namespace. With `let`/`const` and ES modules, IIFEs are rarely needed today.

**Q25. What is a common closure bug in loops?**

Using `var` in a `for` loop with async callbacks — all callbacks close over the same `var i`. Fix: use `let` (creates a new binding per iteration), or wrap in an IIFE to capture the current value. This is a classic interview trap.

**Q26. What is variable shadowing?**

Declaring a variable in an inner scope with the same name as one in an outer scope. The inner declaration shadows the outer one within its scope. The outer variable is unchanged and becomes accessible again outside the inner scope.

**Q27. What is the difference between pass-by-value and pass-by-reference?**

Primitives are passed by value — a copy is made. Objects (including arrays) are passed by reference — both the caller and the function reference the same object in memory. However, reassigning the parameter doesn't affect the original; only mutations do.

**Q28. What is garbage collection in JavaScript?**

JS engines automatically free memory that is no longer reachable. The most common algorithm is mark-and-sweep: starting from roots (global, stack), the engine marks all reachable objects and sweeps the rest. Closures can cause unintentional memory retention.

---

## Section 3: Functions

*Functions are first-class citizens in JavaScript.*

**Q29. What does "first-class functions" mean?**

Functions can be assigned to variables, passed as arguments, returned from other functions, and stored in data structures — just like any other value. This enables higher-order functions, callbacks, currying, and functional programming patterns.

**Q30. What is the difference between a function declaration and a function expression?**

Declaration: `function foo() {}` — hoisted in its entirety, can be called before definition. Expression: `const foo = function() {}` — not hoisted; calling before initialization throws a `ReferenceError` (or `TypeError` for `var`).

**Q31. What are arrow functions and how do they differ from regular functions?**

Arrow functions (`const fn = () => {}`) have shorter syntax, no own `this` binding (they inherit `this` from the enclosing scope), no `arguments` object, no `prototype`, and cannot be used as constructors. They cannot be used as methods when `this` is needed.

**Q32. What is `this` in JavaScript?**

`this` refers to the execution context's subject — the object a method belongs to when called. Its value depends on how the function is called: method call → the object; regular function call → `undefined` (strict) or `global`; arrow function → inherited from enclosing scope; `new` → the new instance.

**Q33. How do `call`, `apply`, and `bind` work?**

`fn.call(thisArg, a, b)` — invokes `fn` with `this` set to `thisArg`, args listed individually. `fn.apply(thisArg, [a, b])` — same but args as an array. `fn.bind(thisArg, a)` — returns a new function permanently bound to `thisArg` with optional pre-filled args (partial application).

**Q34. What is a higher-order function?**

A function that takes another function as an argument and/or returns a function. Examples: `Array.prototype.map`, `filter`, `reduce`, `setTimeout`. They enable functional programming patterns and code reuse.

**Q35. What is currying?**

Transforming a function that takes multiple arguments into a chain of functions each taking one argument: `f(a, b, c)` becomes `f(a)(b)(c)`. Enables partial application and composition. Libraries like Lodash provide `_.curry`.

**Q36. What is partial application?**

Pre-filling some arguments of a function, returning a new function waiting for the rest. Implemented with `bind`: `const double = multiply.bind(null, 2)`. Different from currying — partial application fills multiple args at once.

**Q37. What is function composition?**

Combining multiple functions such that the output of one becomes the input of the next: `compose(f, g)(x) === f(g(x))`. Enables building complex transformations from simple, testable pieces.

**Q38. What is the `arguments` object?**

An array-like object available inside regular functions containing all passed arguments. Not available in arrow functions. Prefer rest parameters (`...args`) which give a real array and work in arrow functions.

**Q39. What are rest parameters and the spread operator?**

Rest (`...args`): collects remaining arguments into an array inside a function definition. Spread (`...arr`): expands an iterable into individual elements at a call site or in an array/object literal. Same syntax, opposite directions.

**Q40. What is memoization?**

Caching the result of a function call based on its inputs. On repeated calls with the same arguments, the cached result is returned instead of recomputing. Implemented with a Map or plain object. Effective for pure, expensive functions.

**Q41. What is a pure function?**

A function that (1) always returns the same output for the same input and (2) has no side effects (no mutation of external state, no I/O, no random values). Pure functions are predictable, testable, and composable.

**Q42. What is a generator function?**

A function declared with `function*` that can pause execution with `yield` and resume later. Returns an iterator. Used for lazy sequences, infinite data streams, async flow control (pre-async/await), and implementing custom iterators.

**Q43. What is a recursive function and what is tail call optimization?**

A function that calls itself. Each call adds a frame to the call stack. Tail call optimization (TCO) — when the recursive call is the last operation — allows the engine to reuse the current stack frame. TCO is specified in ES6 but only Safari implements it reliably.

---

## Section 4: Arrays & Objects

*Mastering JavaScript's primary data structures.*

**Q44. What are the most important array methods?**

`map` (transform), `filter` (select), `reduce` (accumulate), `find`/`findIndex` (search), `some`/`every` (boolean tests), `forEach` (iterate with side effects), `flat`/`flatMap` (nested arrays), `sort`, `splice`, `slice`, `includes`, `indexOf`, `Array.from`, `Array.isArray`.

**Q45. What is the difference between `map` and `forEach`?**

`map` returns a new array of transformed values — it's a pure transformation. `forEach` returns `undefined` and is used purely for side effects (logging, mutations). Prefer `map` when you need the results; `forEach` only for side effects.

**Q46. How does `reduce` work?**

`array.reduce((accumulator, currentValue, index, array) => newAccumulator, initialValue)`. Iterates the array, passing the accumulated result to each callback. Can replace `map`, `filter`, and many other operations. Always provide an initial value to avoid bugs on empty arrays.

**Q47. What is the difference between `slice` and `splice`?**

`slice(start, end)`: non-mutating, returns a shallow copy of a portion. `splice(start, deleteCount, ...items)`: mutates the original array, removes and/or inserts elements in-place, returns removed elements.

**Q48. How do you remove duplicates from an array?**

`[...new Set(arr)]` — fastest, works for primitives. `arr.filter((v, i, a) => a.indexOf(v) === i)` — works without Set. For objects (by key), use `reduce` with a lookup object. `Set` uses value equality for primitives.

**Q49. What is array destructuring?**

`const [a, b, ...rest] = arr` — extracts array elements into named variables by position. Default values: `const [a = 0] = []`. Swap variables: `[a, b] = [b, a]`. Skip elements: `const [, second] = arr`.

**Q50. What is object destructuring?**

`const {name, age: years = 0} = obj` — extracts properties by name into variables, with optional renaming and defaults. Nested: `const {address: {city}} = obj`. In function params: `function fn({name, age}) {}`.

**Q51. What is the spread operator for objects?**

`{...obj1, ...obj2}` creates a shallow merge. Later keys override earlier ones. Used to create modified copies without mutation: `const updated = {...user, age: 31}`. Only copies own enumerable properties.

**Q52. What is object shorthand property syntax?**

`const name = 'Alice'; const obj = {name}` is shorthand for `{name: name}`. Method shorthand: `{greet() {}}` instead of `{greet: function() {}}`. Computed property names: `{[dynamicKey]: value}`.

**Q53. What is optional chaining (`?.`)?**

`obj?.prop?.nested?.method()` — short-circuits and returns `undefined` if any intermediate value is `null` or `undefined`, instead of throwing a `TypeError`. Works with bracket notation (`obj?.[key]`) and function calls (`fn?.()`).

**Q54. What is nullish coalescing (`??`)?**

`value ?? 'default'` — returns the right side only when the left side is `null` or `undefined`. Unlike `||`, it does not short-circuit on `0`, `''`, or `false`. Use `??` when `0` and `''` are valid values.

**Q55. What is `Object.freeze` vs `Object.seal`?**

`freeze`: no adding, removing, or modifying properties — object is fully immutable (shallow). `seal`: no adding or removing properties, but existing properties can still be modified. Both are shallow — nested objects are still mutable.

**Q56. What are property descriptors?**

Every object property has a descriptor: `value`, `writable`, `enumerable`, `configurable`. `Object.defineProperty(obj, 'key', {value: 1, writable: false})` controls these. `Object.getOwnPropertyDescriptor` reads them.

**Q57. What is the difference between `for...in` and `for...of`?**

`for...in`: iterates over all enumerable string property keys of an object (including inherited ones — use `hasOwnProperty` to filter). `for...of`: iterates over values of any iterable (array, string, Map, Set, generator). Prefer `for...of` for arrays.

**Q58. How do you deep clone an object in JavaScript?**

`structuredClone(obj)` — the modern standard, handles most types (Map, Set, Date, circular refs) but not functions or class instances. `JSON.parse(JSON.stringify(obj))` — only handles JSON-safe types. Lodash `_.cloneDeep` handles edge cases. Manual recursive clone for custom needs.

---

## Section 5: Prototypes & Object-Oriented JavaScript

*How JavaScript's inheritance model actually works.*

**Q59. What is the prototype chain?**

Every object has an internal `[[Prototype]]` link to another object (or `null`). When a property is not found on an object, JS searches up the prototype chain until it's found or the chain ends. This is JavaScript's inheritance mechanism.

**Q60. What is `Object.create`?**

`Object.create(proto)` creates a new object with `proto` as its `[[Prototype]]`. Useful for manual prototype-based inheritance without constructors. `Object.create(null)` creates an object with no prototype — a pure dictionary.

**Q61. What is a constructor function?**

A regular function called with `new`. The `new` keyword: (1) creates a new object, (2) sets its `[[Prototype]]` to the constructor's `.prototype`, (3) sets `this` to the new object, (4) returns `this` implicitly (unless an object is explicitly returned).

**Q62. What is the `prototype` property on functions?**

Every function has a `.prototype` object. When the function is used as a constructor with `new`, the created instance's `[[Prototype]]` points to this object. Methods placed on `.prototype` are shared among all instances.

**Q63. What are ES6 classes?**

Syntactic sugar over prototype-based inheritance. `class Foo extends Bar { constructor() { super(); } method() {} }` compiles to constructor functions and prototype assignments. Classes enforce `new` (cannot be called without it), are not hoisted usably, and run in strict mode.

**Q64. What does `super` do in a class?**

In a constructor, `super()` calls the parent class constructor — required in subclass constructors before accessing `this`. In a method, `super.method()` calls the parent class's version of that method.

**Q65. What is the difference between static and instance methods?**

Instance methods are defined on the class body and accessible on instances. Static methods are defined with `static` and accessible on the class itself (not instances). Used for factory methods, utility helpers, or methods that don't need `this`.

**Q66. What are mixins and how do you implement them in JavaScript?**

A mixin adds methods from one object to another without inheritance: `Object.assign(Target.prototype, MixinA, MixinB)`. Since JS only has single inheritance (via prototype chain), mixins allow composing multiple behaviors. Higher-order class mixins are more composable: `const Serializable = (Base) => class extends Base { serialize() {} }`.

**Q67. What is the difference between `__proto__` and `prototype`?**

`__proto__` is the instance's actual prototype link (accessor for `[[Prototype]]`). `prototype` is the property on constructor functions used to set the prototype of instances. Prefer `Object.getPrototypeOf(obj)` over accessing `__proto__` directly.

**Q68. What is prototypal delegation vs classical inheritance?**

Classical inheritance copies behavior from parent to child at class definition time. Prototypal delegation links objects at runtime — the child delegates to the parent when a property isn't found. JS uses delegation; classes are a syntactic layer over it.

---

## Section 6: Asynchronous JavaScript

*Managing time and I/O in a single-threaded language.*

**Q69. What is the Event Loop?**

The mechanism that allows JavaScript to perform non-blocking I/O despite being single-threaded. The event loop checks the Call Stack; when empty, it dequeues tasks from the Task Queue (macrotasks) and Microtask Queue and pushes them onto the stack.

**Q70. What is the difference between the Microtask Queue and the Macrotask Queue?**

Microtasks (Promise `.then`, `queueMicrotask`, `MutationObserver`) run after every task before the next task and before rendering. Macrotasks (`setTimeout`, `setInterval`, I/O, `setImmediate`) run one per event loop iteration. Microtasks always drain completely before the next macrotask.

**Q71. What are callbacks and what problems do they have?**

A function passed as an argument to be called when an async operation completes. Problems: callback hell (deeply nested, hard to read), difficult error handling, no return values, inversion of control. Solved by Promises and async/await.

**Q72. What is a Promise?**

An object representing an eventual value. States: `pending`, `fulfilled`, `rejected`. Created with `new Promise((resolve, reject) => {...})`. Consumed with `.then(onFulfilled, onRejected)` and `.catch(onRejected)`. Returned promises chain automatically.

**Q73. How does Promise chaining work?**

Each `.then()` returns a new Promise. If the handler returns a value, the next `.then` receives it. If it returns a Promise, the next `.then` waits for it to settle. This flattening eliminates nested callbacks. Errors propagate down the chain to the nearest `.catch`.

**Q74. What is `Promise.all`?**

Takes an array of Promises and returns a Promise that resolves with an array of all results when all input Promises fulfill. If any rejects, the result Promise rejects immediately with that reason. Use for parallel independent operations.

**Q75. What are `Promise.allSettled`, `Promise.race`, and `Promise.any`?**

`allSettled`: waits for all, resolves with array of `{status, value/reason}` — never rejects. `race`: settles with the first Promise to settle (fulfill or reject). `any`: fulfills with the first fulfillment; rejects with `AggregateError` only if all reject.

**Q76. What is `async/await`?**

Syntactic sugar over Promises. An `async` function always returns a Promise. `await` pauses execution of the async function until the awaited Promise settles, then returns its value. Makes async code read like synchronous code.

**Q77. How do you handle errors with `async/await`?**

Wrap `await` calls in `try/catch/finally`. Or attach `.catch()` to the returned Promise. Each `await` can be individually wrapped, or one `try/catch` can guard multiple awaits. Unhandled rejections in async functions should always be caught.

**Q78. What happens if you `await` a non-Promise value?**

`await` wraps the value in `Promise.resolve()`. So `await 42` is valid and evaluates to `42`. The function still suspends briefly, yielding to the microtask queue.

**Q79. How do you run async operations in parallel vs sequentially?**

Sequential: `await a(); await b()` — total time = a + b. Parallel: `const [r1, r2] = await Promise.all([a(), b()])` — total time = max(a, b). A common mistake is `await` inside `for...of` when operations are independent — use `Promise.all` instead.

**Q80. What is the difference between `setTimeout(fn, 0)` and `Promise.resolve().then(fn)`?**

Both defer execution, but Promise callbacks (microtasks) run before setTimeout callbacks (macrotasks). `setTimeout(fn, 0)` adds to the macrotask queue; `Promise.resolve().then(fn)` adds to the microtask queue, which drains before the next macrotask.

**Q81. What are `AbortController` and `AbortSignal`?**

`AbortController` creates a controller with an associated `AbortSignal`. Passing the signal to `fetch` allows cancelling the request by calling `controller.abort()`. The signal can also be passed to any API that supports abort signals for consistent cancellation.

**Q82. What are async generators and when would you use them?**

Declared with `async function*`, they combine async and generator behavior. Each `yield` can produce a value asynchronously. Consumed with `for await...of`. Useful for paginated APIs, streaming data, or any async sequence.

**Q83. What is the danger of floating Promises?**

A Promise that is not awaited and has no `.catch()`. If it rejects, the error is silently swallowed or triggers `unhandledRejection`. Always `await` or `.catch()` every Promise. ESLint rules like `no-floating-promises` (from TypeScript-eslint) catch this statically.

---

## Section 7: Iterators, Generators & Symbols

*Advanced language features powering modern JavaScript.*

**Q84. What is an iterable?**

An object implementing the iterable protocol: a `[Symbol.iterator]()` method that returns an iterator. Arrays, strings, Maps, Sets, and generators are iterable. Custom iterables can be created by implementing this method.

**Q85. What is an iterator?**

An object with a `next()` method that returns `{value, done}`. `done: true` signals exhaustion. `for...of`, spread, destructuring, and `Array.from` all consume iterators automatically.

**Q86. How do generators implement iterators?**

`function*` creates a generator function returning a generator object that is both an iterable and an iterator. `yield` pauses execution and provides the next value. `yield*` delegates to another iterable. Generator's `next()` resumes from the last `yield`.

**Q87. What is `Symbol` and why was it introduced?**

`Symbol()` creates a unique, immutable primitive. Introduced in ES6 to create non-string property keys that avoid naming collisions — critical for metaprogramming hooks like `Symbol.iterator`, `Symbol.toPrimitive`, `Symbol.hasInstance`.

**Q88. What are well-known Symbols?**

Built-in Symbols used to customize JS behavior: `Symbol.iterator` (makes object iterable), `Symbol.toPrimitive` (custom type coercion), `Symbol.hasInstance` (customizes `instanceof`), `Symbol.species` (customizes derived instances), `Symbol.toStringTag` (customizes `Object.prototype.toString`).

**Q89. What is `Symbol.toPrimitive` used for?**

Allows an object to define its own coercion to a primitive. The method receives a hint (`'number'`, `'string'`, or `'default'`) and should return the appropriate primitive. Example use: custom value objects (Money, Color) that behave naturally in arithmetic or string contexts.

**Q90. What is a WeakMap and when would you use it?**

A `Map` with weakly-held keys — keys must be objects, and if the object is garbage collected, the entry is automatically removed. No size property, no iteration. Use for attaching private data to DOM nodes or objects without preventing their GC.

**Q91. What is a WeakSet?**

Like `WeakMap` but only stores objects (no key-value pairs), and only for membership testing. Objects are weakly referenced. Use for tracking objects (e.g., "visited nodes" in a graph traversal) without preventing garbage collection.

---

## Section 8: ES6+ Modern Features

*Features that define modern JavaScript style.*

**Q92. What are template literals?**

Backtick strings (`` ` ``) supporting multi-line text and embedded expressions via `${}`. Tagged templates allow a function to process the template string. Used for HTML strings, SQL queries, styled-components, and i18n.

**Q93. What are tagged template literals?**

A function call where the function receives the template parts and interpolated values as separate arguments: `` tag`Hello ${name}` `` calls `tag(['Hello ', ''], name)`. Used by styled-components, graphql-tag, Lit HTML.

**Q94. What is the `for...of` loop?**

Iterates over values of any iterable. Unlike `for...in` (which gives keys), `for...of` gives values. Works with arrays, strings, Maps, Sets, generators, and any custom iterable. Combined with `entries()`, `keys()`, or `values()` for indexed access.

**Q95. What are `Map` and `Set`?**

`Map`: key-value pairs where keys can be any type (objects, functions). Ordered by insertion. Has `size`, `get`, `set`, `has`, `delete`, `forEach`. `Set`: collection of unique values of any type. Used for deduplication and membership tests. Both are iterable.

**Q96. What are the differences between `Map` and a plain object?**

`Map`: any key type, ordered by insertion, `size` property, iterable directly, no prototype pollution. Object: only string/Symbol keys, not reliably ordered (though modern engines maintain insertion order for string keys), must use `hasOwnProperty`. Use `Map` for dictionaries with non-string keys or when key order matters.

**Q97. What are Proxy and Reflect?**

`Proxy` wraps an object and intercepts fundamental operations (get, set, delete, apply, construct) via handler traps. `Reflect` provides the same set of operations as static methods. Used for: validation, reactive systems (Vue 3), logging, access control, mocking.

**Q98. What are named exports vs default exports in ES modules?**

Named: `export const foo = 1` — imported as `import {foo} from './mod'`. Default: `export default function(){}` — imported as `import anything from './mod'`. A module can have many named exports but only one default. Named exports are generally preferred for tree-shaking and explicitness.

**Q99. What is dynamic `import()`?**

`import('./module.js')` returns a Promise that resolves to the module's namespace object. Enables lazy loading and code splitting — load code on demand rather than upfront. Unlike static `import`, it can be inside conditions or functions.

**Q100. What is `globalThis`?**

A standard way to access the global object regardless of environment. `window` in browsers, `global` in Node.js, `self` in Web Workers. `globalThis` normalizes these across environments for portable code.

---

## Section 9: `this`, Call Context & Binding

*One of JavaScript's most misunderstood features.*

**Q101. What are the four rules that determine `this`?**

1. Default binding: standalone function call → `undefined` (strict) or `global`. 2. Implicit binding: method call `obj.fn()` → `this = obj`. 3. Explicit binding: `fn.call(obj)` / `fn.apply(obj)` / `fn.bind(obj)`. 4. `new` binding: `new Fn()` → `this` is the new instance. Arrow functions ignore all rules and inherit `this` lexically.

**Q102. Why does `this` lose context in callbacks?**

When a method is passed as a callback, it becomes a standalone function reference. The implicit binding (to the original object) is lost. Fix: `fn.bind(this)`, arrow function wrapper, or store `const self = this` (old pattern).

**Q103. What does `new` do step by step?**

1. Creates a new empty object. 2. Sets its `[[Prototype]]` to `Constructor.prototype`. 3. Calls the constructor with `this` set to the new object. 4. If the constructor explicitly returns an object, that object is returned; otherwise, the new object created in step 1 is returned.

**Q104. How do arrow functions differ from regular functions regarding `this`?**

Arrow functions have no own `this`. They inherit `this` from the enclosing lexical scope at the time of definition. This makes them ideal for callbacks and event handlers where you want `this` to refer to the surrounding context, not the caller.

**Q105. What is hard binding and when do you use it?**

`fn.bind(thisArg, ...args)` returns a new function permanently bound to `thisArg`. The binding cannot be overridden even with `call`, `apply`, or `new`. Used when passing methods as callbacks and when partially applying arguments.

**Q106. Situation: `this` is `undefined` inside a class method used as a callback — how do you fix it?**

Three options: (1) bind in the constructor: `this.method = this.method.bind(this)`. (2) Use a class field arrow function: `method = () => {}` (most common in React). (3) Use an arrow function at the call site: `element.addEventListener('click', () => this.method())`.

---

## Section 10: Error Handling & Debugging

*Writing resilient JavaScript.*

**Q107. What are the types of errors in JavaScript?**

`SyntaxError` (code cannot be parsed), `ReferenceError` (undefined variable), `TypeError` (wrong type, null access), `RangeError` (value out of range), `URIError`, `EvalError`. All extend `Error`. Custom errors extend `Error` with a name property.

**Q108. How do you create custom error types?**

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

**Q109. What is `try/catch/finally` and how does `finally` behave?**

`try` runs code that might throw. `catch(e)` handles thrown errors. `finally` runs no matter what — even if `try` returns or `catch` throws. If `finally` returns a value, it overrides the `try`/`catch` return — a subtle behavior to be aware of.

**Q110. How do you handle errors in Promises vs async/await?**

Promises: `.catch(handler)` at the end of the chain. Async/await: `try/catch` block, or `.catch()` on the returned Promise. Unhandled rejections: listen to `process.on('unhandledRejection')` (Node) or `window.addEventListener('unhandledrejection')` (browser).

**Q111. What is the `Error.cause` property (ES2022)?**

`throw new Error('message', {cause: originalError})` — chains errors to preserve the original cause. `error.cause` holds the original error. Useful for wrapping low-level errors with higher-level context without losing the original stack trace.

**Q112. What are source maps?**

Files that map minified/compiled production code back to the original source. Enable readable stack traces and breakpoints in DevTools despite bundling and transpilation. Generated by bundlers (webpack, Vite) with a configuration option.

**Q113. How do you debug JavaScript effectively?**

`debugger` statement (pauses in DevTools), `console.log/table/trace/time`, breakpoints in DevTools, conditional breakpoints, watch expressions, the Call Stack panel (for async), and network panel for API calls. For production: error monitoring (Sentry), structured logging.

**Q114. What is `console.table`, `console.group`, and `console.time`?**

`console.table(arr)`: renders arrays/objects as a formatted table. `console.group(label)` / `console.groupEnd()`: collapses related logs. `console.time(label)` / `console.timeEnd(label)`: measures time between calls. `console.trace()`: prints current call stack.

---

## Section 11: The DOM & Browser APIs

*Interfacing with the browser environment.*

**Q115. What is the DOM?**

The Document Object Model — a tree representation of an HTML document. Each tag is a node. JavaScript can read and manipulate the DOM to dynamically update content, structure, and styles without page reloads.

**Q116. What is event bubbling and capturing?**

Events propagate in three phases: capture (from window down to target), target (at the element), bubble (from target back up to window). `addEventListener(event, handler, true)` for capture phase, `false`/omitted for bubble. `stopPropagation()` halts further propagation.

**Q117. What is event delegation?**

Attaching a single listener to a parent instead of many listeners on children. Uses bubbling — the parent receives the event and checks `event.target` to determine which child triggered it. Efficient for dynamic lists where children are added/removed.

**Q118. What is the difference between `innerHTML`, `textContent`, and `innerText`?**

`innerHTML`: gets/sets raw HTML markup — XSS risk with user input. `textContent`: gets/sets plain text, ignores HTML tags, not affected by CSS (fastest). `innerText`: like `textContent` but respects CSS visibility (causes reflow — avoid in performance-sensitive code).

**Q119. What is `MutationObserver`?**

Watches for DOM changes (child additions, attribute changes, text modifications) and fires a callback asynchronously with a list of `MutationRecord` objects. More efficient than polling. Used in libraries for tracking DOM changes without reflow.

**Q120. What is `IntersectionObserver`?**

Observes when an element enters or leaves the viewport (or a container). Callbacks fire when the intersection ratio crosses thresholds. Used for: lazy loading images, infinite scroll, triggering animations on scroll, analytics (view tracking).

**Q121. What is `ResizeObserver`?**

Watches when an element's size changes and fires a callback. Better than `window.resize` (which fires for the whole window). Used for responsive components that need to react to their own size — container queries in JS.

**Q122. What is the difference between `localStorage`, `sessionStorage`, and cookies?**

`localStorage`: key-value, persists across sessions, same-origin, up to ~5MB. `sessionStorage`: same-origin, cleared when tab closes. Cookies: sent with every HTTP request (server access), can have expiry, `HttpOnly` flag prevents JS access. Use cookies for auth tokens, `localStorage` for non-sensitive client-only data.

**Q123. What is the History API?**

`history.pushState(state, title, url)` adds a history entry without reload. `history.replaceState` modifies the current entry. `window.popstate` fires on back/forward. The foundation of client-side routing in SPAs.

**Q124. What is the Fetch API vs XMLHttpRequest?**

`fetch` is Promise-based, cleaner syntax, supports streams, no built-in timeout/progress. `XMLHttpRequest` is callback-based, supports progress events and synchronous calls (avoid sync). `fetch` does not reject on HTTP errors (only on network failure) — always check `response.ok`.

**Q125. What is the Web Worker API?**

Runs JavaScript in a background thread, separate from the main thread. Communicates via `postMessage`/`onmessage`. No DOM access. Used for CPU-intensive tasks (image processing, data parsing, encryption) to avoid blocking the main thread.

---

## Section 12: Performance & Memory

*Writing fast, efficient JavaScript.*

**Q126. What is the difference between debounce and throttle?**

Debounce: delays execution until after N milliseconds of inactivity — fires once after the user stops. Throttle: limits execution to at most once per N milliseconds — fires regularly during activity. Use debounce for search inputs; throttle for scroll/resize handlers.

**Q127. What is `requestAnimationFrame`?**

Schedules a callback before the next browser repaint. Runs at the display refresh rate (~60fps). Better than `setTimeout` for animations — synchronized with the browser's paint cycle, paused in background tabs, and not subject to throttling.

**Q128. What are memory leaks in JavaScript and what causes them?**

Memory that is allocated but never freed because references still exist. Common causes: event listeners not removed, closures holding references, global variables, detached DOM nodes still referenced in JS, interval/timeout callbacks holding references.

**Q129. What is reflow and repaint?**

Reflow (layout): recalculates positions/sizes of elements — triggered by DOM/style changes affecting layout. Repaint: redraws pixels without layout changes (color, visibility). Reflow is expensive. Batch DOM reads then writes. Use `requestAnimationFrame`. Avoid forced synchronous layout (reading layout after writing).

**Q130. What is lazy loading?**

Deferring resource loading until it's actually needed. Native: `<img loading="lazy">`, dynamic `import()`. For images: `IntersectionObserver`. For code: `React.lazy`, route-level code splitting. Reduces initial load time and data usage.

**Q131. What is the difference between `==` comparisons and `Object.is`?**

`Object.is(a, b)` is like `===` but handles two edge cases: `Object.is(NaN, NaN) === true` and `Object.is(+0, -0) === false`. Used internally by React and Redux for comparison logic. Regular `===` treats `NaN !== NaN` and `+0 === -0`.

**Q132. How does V8 optimize JavaScript?**

JIT (Just-In-Time) compilation: interprets first, then compiles hot code to machine code. Hidden classes: V8 creates internal type shapes for objects — keep object property order consistent. Inline caching: caches property lookup results. Avoid deoptimization triggers: type changes, `arguments`, `eval`, `try/catch` in hot loops.

**Q133. What is tree shaking and how does it relate to ES modules?**

Tree shaking removes unused exports from the final bundle using static analysis. Only works with ES module syntax (`import`/`export`) — not CommonJS (`require`). Write named exports, avoid side-effectful imports, mark packages as `"sideEffects": false` in `package.json`.

---

## Section 13: Functional Programming in JavaScript

*FP patterns that lead to cleaner, more testable code.*

**Q134. What are the core principles of functional programming?**

Pure functions, immutability, function composition, avoiding shared state and side effects, declarative style. FP makes code more predictable and testable. JavaScript is multi-paradigm — FP can be applied selectively.

**Q135. What is immutability and how do you achieve it in JavaScript?**

Never mutating data — always creating new values. Use spread/`Object.assign` for objects, `map`/`filter`/`slice` for arrays. Libraries: Immer (mutable-looking updates that produce immutable results). `Object.freeze` for shallow freezing.

**Q136. What is a functor?**

A value in a context that can be mapped over — i.e., it implements a `map` method. Arrays are the canonical JavaScript functor. Promises have `then` (similar but not strictly a functor). Functors preserve structure while transforming values.

**Q137. What is a monad (in practical JS terms)?**

A pattern for sequencing operations with context — essentially anything with a `flatMap`/`chain` method that flattens one level. Promises behave monadically (`.then` flattens nested promises). Used in libraries like fp-ts. Understanding monads enables cleaner async and nullable handling.

**Q138. What is point-free style?**

Writing functions without explicitly mentioning their arguments: `const double = map(x => x * 2)` vs `arr => arr.map(x => x * 2)`. Enabled by partial application and currying. Improves composability but can harm readability if overused.

**Q139. What are transducers?**

Composable algorithmic transformations that are independent of the input source. Combine multiple `map`/`filter` operations into one pass over a collection, eliminating intermediate arrays. Used in performance-sensitive functional pipelines.

---

## Section 14: Modules & Project Structure

*Organizing JavaScript at scale.*

**Q140. What is the CommonJS module system?**

Node.js's original module system: `require()` to import, `module.exports` or `exports.foo` to export. Synchronous, evaluated at load time. Still widely used in Node.js server code and older packages. Being gradually replaced by ESM.

**Q141. What are ES Modules (ESM)?**

The standard JS module system: `import`/`export`. Static — imports are resolved at parse time, enabling tree shaking. Asynchronous loading in browsers. `"type": "module"` in `package.json` enables ESM in Node.js. `.mjs` extension also works.

**Q142. What is the difference between named and namespace imports?**

Named: `import {foo, bar} from './mod'` — imports specific exports. Namespace: `import * as mod from './mod'` — imports all exports as properties of a single object. Namespace imports prevent tree shaking of unused exports.

**Q143. What is circular dependency and how do you handle it?**

Module A imports B, and B imports A. Both module systems handle it but the imported value may be `undefined` at evaluation time. Fix: restructure to extract shared code to a third module C, or use lazy imports (dynamic `import()`).

**Q144. What is module federation?**

A Webpack 5 feature (and now broader concept) allowing multiple independently deployed applications to share code at runtime. Module A can dynamically load components from Module B's deployed bundle. Used in micro-frontend architectures.

**Q145. What are package.json `exports` and `main` fields?**

`main`: entry point for CommonJS/legacy resolvers. `exports`: modern conditional exports — specify different entry points for ESM, CJS, browser, Node, types. `exports` takes precedence over `main` in modern tooling. Enables dual CJS/ESM packages.

---

## Section 15: Node.js & Server-Side JavaScript

*JavaScript beyond the browser.*

**Q146. What is the Node.js event loop and how does it differ from the browser's?**

Node.js uses libuv for I/O and has additional phases: timers (`setTimeout`/`setInterval`), pending callbacks, idle, poll (I/O), check (`setImmediate`), close callbacks. `setImmediate` runs after I/O in the check phase — before a `setTimeout(fn, 0)` in I/O context.

**Q147. What is `process.nextTick`?**

Schedules a callback to run at the end of the current operation, before the event loop continues — even before Promise microtasks in older Node versions. Now runs in the microtask queue. Overusing it can starve I/O callbacks.

**Q148. What are Node.js streams?**

`Readable`, `Writable`, `Duplex`, `Transform` streams handle data in chunks rather than loading everything into memory. Pipe-able: `readStream.pipe(transformStream).pipe(writeStream)`. Essential for large file processing, HTTP responses, and real-time data.

**Q149. What is the `cluster` module?**

Allows spawning multiple Node.js processes sharing the same port. Master process forks workers (one per CPU core). Distributes incoming connections across workers. Used to take advantage of multi-core CPUs since Node.js is single-threaded.

**Q150. What is `Buffer` in Node.js?**

A fixed-size allocation of raw binary data (a subclass of `Uint8Array`). Used when dealing with file I/O, network protocols, or binary data. `Buffer.from('hello', 'utf8')`, `buf.toString('hex')`. Distinct from ArrayBuffer/TypedArrays in the browser.

**Q151. What are Worker Threads in Node.js?**

`worker_threads` module runs JS in parallel threads within the same process. Unlike `cluster` (separate processes), workers share memory via `SharedArrayBuffer`. Used for CPU-intensive tasks — image resizing, compression, parsing.

**Q152. What is the difference between `require` resolution and ESM resolution in Node.js?**

`require` looks for `.js`, then `index.js`, then checks `package.json main`. ESM requires explicit file extensions and respects the `exports` field. ESM cannot `require()` synchronously. Mixing both requires careful package configuration.

---

## Section 16: Security in JavaScript

*Common vulnerabilities and defenses.*

**Q153. What is XSS (Cross-Site Scripting) and how do you prevent it?**

Injecting malicious scripts into pages viewed by other users. Prevention: never insert user-controlled HTML via `innerHTML` — use `textContent`. Use Content Security Policy (CSP) headers. Sanitize with DOMPurify when HTML is required. Escape output server-side.

**Q154. What is prototype pollution?**

Modifying `Object.prototype` through user-controlled input like `obj['__proto__']['admin'] = true`. This affects all objects. Prevention: use `Object.create(null)` for dictionaries, validate input keys, use `Map` instead of objects for dynamic keys, and use libraries with built-in protections.

**Q155. What is a timing attack and how does it relate to JavaScript?**

Inferring secret information from the time it takes to perform operations. String comparison with `===` short-circuits on the first mismatch — timing varies by how much matches. Use constant-time comparison for sensitive values (HMAC verification). `crypto.timingSafeEqual` in Node.js.

**Q156. What is Content Security Policy (CSP)?**

An HTTP header that restricts what resources a page can load and execute. `script-src 'self'` prevents inline scripts and scripts from external origins. Mitigates XSS. Can also report violations without enforcing with `Content-Security-Policy-Report-Only`.

**Q157. What is `eval()` and why is it dangerous?**

Executes a string as JavaScript code. Security risk: if the string contains user input, it enables code injection. Performance risk: prevents V8 optimization of the surrounding scope. Almost never necessary — use `JSON.parse`, `Function` constructor only if unavoidable, never with untrusted input.

**Q158. What are CORS and SOP (Same-Origin Policy)?**

SOP: browsers block JS from accessing resources from a different origin (protocol + domain + port). CORS: server opts in to cross-origin access via `Access-Control-Allow-Origin` headers. Preflight `OPTIONS` requests check permissions for non-simple requests.

---

## Section 17: Testing JavaScript

*Writing confident, maintainable tests.*

**Q159. What is the testing pyramid for JavaScript?**

Unit tests (fast, many): individual functions, modules. Integration tests (medium): interactions between units, API calls. E2E tests (slow, few): full browser flows. Focus the most effort on integration tests — they give the best coverage-to-cost ratio for most JS apps.

**Q160. What is Jest and what does it provide?**

A zero-config testing framework: test runner, assertion library (`expect`), mocking (`jest.fn()`, `jest.mock()`), snapshot testing, code coverage. Works for both browser and Node.js code. The most popular JS testing solution.

**Q161. What is the difference between `jest.fn()`, `jest.spyOn()`, and `jest.mock()`?**

`jest.fn()`: creates a standalone mock function. `jest.spyOn(obj, 'method')`: replaces `obj.method` with a spy, preserving the original implementation by default. `jest.mock('./module')`: replaces an entire module with auto-mocked versions. Use `mockImplementation` or `mockReturnValue` to control behavior.

**Q162. What are snapshot tests?**

`expect(value).toMatchSnapshot()` serializes the value and saves it to a file on first run. Subsequent runs compare against the snapshot. Fast to write but prone to false positives — only use for stable, simple outputs. Prefer explicit assertions for complex behavior.

**Q163. What is test-driven development (TDD)?**

Red-Green-Refactor cycle: (1) write a failing test, (2) write the minimum code to pass, (3) refactor. TDD produces high test coverage, drives better API design, and reduces over-engineering. Can be slower initially but pays off in fewer bugs and confident refactoring.

**Q164. How do you test asynchronous code in Jest?**

Return a Promise from the test, or use `async/await`. `done` callback (old style). Use `expect.assertions(n)` to ensure async assertions actually run. Mock timers with `jest.useFakeTimers()` and `jest.runAllTimers()` for `setTimeout`/`setInterval` logic.

**Q165. What is code coverage and what metrics matter?**

Percentage of code executed during tests: line, branch, function, statement coverage. Branch coverage is most meaningful — tests every code path. 100% coverage doesn't guarantee bug-free code; it only shows what was executed, not what was asserted correctly.

**Q166. What is property-based testing?**

Instead of specific inputs, you define properties that should hold for any input. A library (fast-check, JSVerify) generates hundreds of random test cases. Excellent for finding edge cases you wouldn't think to write manually. Useful for pure functions and data transformation logic.

---

## Section 18: Senior-Level Scenario Questions

*Open-ended design and debugging scenarios for experienced developers.*

**Q167. Design a rate limiter function in JavaScript.**

Track call timestamps in a sliding window or token bucket. `function rateLimit(fn, limit, window) { let calls = []; return (...args) => { const now = Date.now(); calls = calls.filter(t => now - t < window); if (calls.length >= limit) throw new Error('Rate limited'); calls.push(now); return fn(...args); }; }`. For async queuing instead of throwing, use a Promise queue with delay.

**Q168. How would you implement a deep equality function?**

Handle primitives with `===`. Handle `null` explicitly. Check same type and same constructor. For arrays, check length then recurse over indices. For objects, check same keys then recurse over values. Handle `Date`, `RegExp`, `Map`, `Set`, and circular references. `Object.is` for NaN/+0/-0 edge cases.

**Q169. Situation: A Node.js server is leaking memory — how do you diagnose it?**

Take heap snapshots with `node --inspect` and Chrome DevTools. Use `clinic.js` or `0x`. Look for growing retained size in heap snapshots. Common culprits: global caches without eviction, event listeners not removed, closures capturing large objects, `setInterval` not cleared. Take multiple snapshots over time and diff them.

**Q170. How would you implement an event emitter from scratch?**

Store handlers in a `Map<string, Set<Function>>`. `on(event, handler)`: add handler to the Set. `off(event, handler)`: remove it. `emit(event, ...args)`: iterate the Set and call each handler. `once(event, handler)`: wrap handler to call `off` after first invocation.

**Q171. How do you implement `Promise.all` from scratch?**

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

**Q172. How would you design a client-side caching layer?**

LRU (Least Recently Used) cache: doubly linked list + Map for O(1) get/set. `get(key)`: move node to front. `set(key, val)`: add to front, evict tail if over capacity. Add TTL: store expiry timestamp, check on `get`. Add stale-while-revalidate: return stale value while background-fetching fresh data.

**Q173. Explain how you would implement virtual scrolling in vanilla JavaScript.**

Calculate item height. Determine total scroll height. Render only visible items + buffer. On scroll, update the range of visible indices. Translate the rendered container with `transform: translateY` instead of `top` (avoids reflow). Recycle DOM nodes instead of creating/destroying them.

**Q174. How would you architect a state management system in vanilla JavaScript?**

A central `Store` class holding state object. `dispatch(action)` runs the reducer to produce new state (immutably). `subscribe(listener)` adds observers; `unsubscribe` removes them. `getState()` returns current state. Middleware support: wrap `dispatch` with a chain of middleware functions. Notify subscribers after each dispatch.

**Q175. Situation: A `for` loop with `var` and `setTimeout` doesn't behave as expected — explain and fix.**

`for (var i = 0; i < 5; i++) setTimeout(() => console.log(i), 0)` prints `5` five times. `var` is function-scoped — all callbacks close over the same `i`. Fix 1: `let` in the loop (block-scoped, new binding per iteration). Fix 2: IIFE `(function(i) { setTimeout(...) })(i)`. Fix 3: `setTimeout(console.log, 0, i)`.

**Q176. How would you implement debounce and throttle from scratch?**

Debounce: `function debounce(fn, delay) { let timer; return (...args) => { clearTimeout(timer); timer = setTimeout(() => fn(...args), delay); }; }`. Throttle (leading): track `lastCall`. If `Date.now() - lastCall >= delay`, call `fn` and update `lastCall`. Trailing throttle: use `setTimeout` and cancel if called again within the window.

**Q177. How do you detect and prevent infinite loops in user-submitted code?**

Run in a sandboxed Web Worker. Inject a counter that increments on each iteration and throws after a limit. Use a timer in the host to terminate the Worker after a timeout. Never run untrusted code in the main thread or with `eval` in the host environment.

**Q178. Design a pipeline function (like `|>` operator) in JavaScript.**

```javascript
const pipe = (...fns) => x => fns.reduce((acc, fn) => fn(acc), x);
const process = pipe(trim, toLowerCase, removeSpecialChars, truncate(50));
process(input);
```
For async pipelines: `const pipeAsync = (...fns) => x => fns.reduce(async (acc, fn) => fn(await acc), x)`.

**Q179. How would you implement memoization with a complex cache key?**

For single-argument functions, a `Map` is sufficient. For multiple arguments, serialize args: `JSON.stringify(args)` (fast but fails for functions, undefined, circular refs). For robust solution: use a WeakMap for object args (prevents memory leaks) with a trie-like structure for multiple args (as in libraries like `memoize-one`).

**Q180. How would you implement a publish/subscribe system with topics and wildcards?**

Map topic strings to subscriber Sets. For wildcards (`*`), on publish check each subscriber's pattern against the topic using a regex or glob match. Namespace topics with `.` separator for hierarchical subscriptions (`user.*` matches `user.created`, `user.deleted`).

**Q181. Situation: `JSON.stringify` is dropping data — explain why and how to fix it.**

`JSON.stringify` silently omits: `undefined` values in objects (and `undefined` itself), functions, `Symbol` keys and values, and `Infinity`/`NaN` (become `null`). Circular references throw. Fix: use a replacer function as the second argument to handle special values, or use a library like `flatted` for circular refs.

**Q182. How do you handle JavaScript errors in a production application end-to-end?**

Error boundaries (React) for UI crashes. `window.onerror` and `window.onunhandledrejection` for unhandled errors. Integrate Sentry/Datadog with breadcrumbs and user context. Source maps for readable stack traces. Alert on error rate spikes. `try/catch` for expected failures with user-facing messages. Structured logging for server-side.

**Q183. How would you build an undo/redo system?**

Maintain two stacks: undo stack and redo stack. On action: push current state to undo, clear redo. On undo: pop from undo → apply → push to redo. On redo: pop from redo → apply → push to undo. For commands (not full state snapshots), store `do`/`undo` function pairs to avoid cloning large state objects.

**Q184. Explain the JavaScript module resolution algorithm.**

For bare specifiers (`import 'lodash'`): check `node_modules`, resolve `package.json exports`/`main`. For relative paths (`./util`): try exact, then `.js`, `.mjs`, `.cjs`, `/index.js`. For browsers: relies on import maps or bundlers (no `node_modules` resolution natively). TypeScript adds path aliases and `baseUrl` on top.

**Q185. How would you implement a simple reactive system (like Vue's reactivity)?**

Track the currently executing effect in a global variable. `reactive(obj)`: wrap with `Proxy`. On `get`, if an effect is running, add it to that property's subscriber Set (track). On `set`, call all subscribers (trigger). Effects run their function, which accesses reactive properties, automatically subscribing. This is Vue 3's reactivity core.

**Q186. Situation: An async function is silently failing — how do you debug it?**

Check for missing `await` (the Promise is returned but not awaited). Check for caught errors that are swallowed silently in `.catch(() => {})`. Add `process.on('unhandledRejection')`. Use `Promise.all` carefully — a rejection can be missed if the result isn't awaited. Enable the `no-floating-promises` ESLint rule.

**Q187. How would you compile a simple expression language to JavaScript?**

Lexer: tokenize the input string into tokens (numbers, operators, identifiers, parentheses). Parser: build an Abstract Syntax Tree (AST) using recursive descent. Code generator: walk the AST and emit JavaScript (or evaluate directly from the AST). Libraries: Acorn (JS parser), Chevrotain (parser toolkit).

**Q188. How do you ensure JavaScript is accessible?**

Manage focus after dynamic content changes. Announce dynamic updates via `aria-live` regions. Don't rely solely on color or hover states. Ensure all interactive elements are keyboard operable (Enter/Space, arrow keys per ARIA patterns). Test with screen readers (NVDA, VoiceOver). Use eslint-plugin-jsx-a11y for automated linting.

**Q189. How would you architect a real-time collaborative editing feature?**

Operational Transformation (OT) or CRDT (Conflict-free Replicated Data Type) algorithms to handle concurrent edits. WebSocket for real-time transport. Server applies and broadcasts operations. Yjs and Automerge are production-ready CRDT libraries. Awareness protocol for cursor/presence sharing.

**Q190. Situation: Your third-party script is blocking the main thread — how do you fix it?**

Load with `defer` (executes after HTML parse, in order) or `async` (executes immediately when downloaded). Move to a Web Worker for CPU work. Use dynamic `import()` to load only when needed. Evaluate if the script is necessary at all — audit with Lighthouse third-party audit. Use `scheduler.postTask` (Chrome) to yield control.

**Q191. How do you safely handle `JSON.parse` with unknown input?**

Always wrap in `try/catch`. Validate the parsed structure — don't assume it matches your expected schema. Use a validation library (Zod, Yup) to parse and validate in one step: `const result = MySchema.safeParse(JSON.parse(input))`. Never trust server or external data structure without validation.

**Q192. Design a retry mechanism with exponential backoff for API calls.**

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

**Q193. How would you implement a JavaScript interpreter in JavaScript?**

Tokenize input into a stream of tokens (lexer). Parse tokens into an AST (parser — use recursive descent for simplicity). Evaluate the AST recursively (interpreter): for literals, return the value; for binary expressions, evaluate both sides; for identifiers, look up in an environment object; for function calls, evaluate the function and arguments then apply. This is the basis of js-interpreter and Babel plugins.

**Q194. What is the `Atomics` API and when do you need it?**

`Atomics` provides atomic operations on `SharedArrayBuffer` for safe inter-thread communication in Worker threads. Without atomics, concurrent writes cause data races. `Atomics.wait`, `Atomics.notify` implement mutex-like synchronization. Rarely needed — only for low-level concurrent algorithms in Workers.

**Q195. How would you implement feature detection in JavaScript?**

Check for the feature's existence before using it: `if ('IntersectionObserver' in window)`. For methods: `if (typeof arr.flat === 'function')`. For CSS: `CSS.supports('display', 'grid')`. Prefer feature detection over user-agent sniffing (unreliable). Use polyfills for missing features rather than forking code.

**Q196. Explain the difference between eager and lazy evaluation in JavaScript.**

Eager: values are computed immediately when defined. Lazy: values are computed only when needed. Generators implement lazy sequences. `&&` and `||` are lazy (short-circuit). Proxies enable lazy object initialization. Lazy evaluation avoids unnecessary computation and enables infinite sequences.

**Q197. How would you handle large JSON files in Node.js?**

Don't load the entire file into memory with `JSON.parse`. Use streaming JSON parsers: `JSONStream`, `oboe`, or `stream-json`. Read the file as a Readable stream and pipe through the parser. Process records one at a time. For extremely large files, consider a line-delimited JSON format (NDJSON) which is easier to stream.

**Q198. Situation: You need to run 100 API calls but limit concurrency to 5 — how?**

Implement a concurrency limiter: maintain a running count and a queue. When running < limit, start a task. When a task completes, start the next queued one. Or use `p-limit` (npm). Alternatively, chunk the array into groups of 5 and `await Promise.all(chunk)` per group — less dynamic but simple for batch processing.

**Q199. How would you implement a simple dependency injection container?**

A container maps tokens (strings, Symbols, or classes) to factories. `register(token, factory)`: store the factory. `resolve(token)`: call the factory, injecting dependencies by calling `resolve` for each declared dependency. Handle circular dependencies by detecting cycles. Supports singletons by caching resolved instances.

**Q200. What would you look for when reviewing a junior developer's JavaScript PR?**

Missing `await` or unhandled Promises. Mutable data where immutable patterns were intended. `var` instead of `let`/`const`. Callback-style code where Promises/async-await are cleaner. Missing error handling. Potential XSS with `innerHTML`. Performance issues: loops inside loops, DOM queries in loops, missing debounce on event handlers. Missing tests for edge cases.

**Q201. How do you write JavaScript that works in both browser and Node.js?**

Avoid environment-specific globals (`window`, `document`, `process`, `require`). Use feature detection. Use bundlers (Vite, Rollup) with appropriate targets. Write code against standard APIs (Fetch, Web Streams — now available in Node 18+). Publish CJS/ESM dual packages for library code.

**Q202. Design a simple virtual DOM diffing algorithm.**

Represent nodes as `{type, props, children}` objects. Diff function: if types differ, replace entirely. If same type, diff props — apply changed/removed/added props to the real DOM node. Recurse into children: use keys for stable matching; add/remove/patch as needed. Apply all changes in the commit phase after the full diff.

**Q203. What is the JavaScript pipeline operator proposal?**

The `|>` operator (Stage 2) allows `value |> fn1(%) |> fn2(%)`, making pipelines readable without nesting or composition helpers. `%` is the placeholder for the piped value. Still in proposal — use Babel plugin for early access. Competing with the Hack-style (with %) and F#-style (without) proposals.

**Q204. How would you implement a persistent undo history that survives page reload?**

Store the action history (not full state snapshots) in `localStorage` or `IndexedDB`. On load, replay the action log to reconstruct state. For large histories, use snapshots at intervals: store the base snapshot plus a delta log since the last snapshot. Limit history length to control storage size.

**Q205. Situation: Users report your web app crashes their browser tab — what do you investigate?**

Check for infinite loops (missing loop exit condition, infinite recursion). Check memory usage in Task Manager / DevTools Memory tab — look for heap growth. Check for WebSocket or polling connections sending enormous payloads. Look for `setInterval` without `clearInterval`. Check for canvas or WebGL without proper cleanup. Use `performance.memory` API and heap snapshots to narrow down.

**Q206. How does `structuredClone` differ from `JSON.parse(JSON.stringify())`?**

`structuredClone`: handles `Date`, `Map`, `Set`, `ArrayBuffer`, `RegExp`, circular references, `undefined`, `Infinity`, `NaN`. Does not clone functions or class instances (throws). `JSON.parse(JSON.stringify())`: drops `undefined`, functions, Symbols; converts `Date` to string; throws on circular refs; converts `Infinity`/`NaN` to `null`. Use `structuredClone` for general-purpose deep cloning.

**Q207. How do you approach writing JavaScript for low-powered devices?**

Minimize main thread work — offload to Workers. Avoid long tasks (> 50ms). Use passive event listeners. Reduce layout thrash — batch reads and writes. Minimize repaints. Prefer CSS animations over JS animations. Code split aggressively. Avoid large dependency bundles. Test on real low-end devices with CPU throttling in DevTools. Use the `scheduler` API (when available) to yield to the browser.

**Q208. What is the TC39 proposal process and how do you track upcoming JavaScript features?**

Proposals go through 5 stages: Stage 0 (idea), Stage 1 (proposal), Stage 2 (draft spec), Stage 3 (candidate — implementations begin), Stage 4 (finished — included in next ES spec). Track at the tc39/proposals GitHub repo. Stage 3 proposals are generally safe to use with Babel/TypeScript. Stage 4 proposals ship in the next ECMAScript edition.

**Q209. How would you build a JavaScript SDK for a REST API?**

A class or factory accepting `baseURL` and auth credentials. Each resource (users, posts) gets methods (`getAll`, `getById`, `create`, `update`, `delete`). Central `request` method handles: setting auth headers, base URL, error parsing, retry logic, and type coercion. Generate TypeScript types from OpenAPI spec. Version the SDK with semantic versioning.

**Q210. Situation: `this` is `undefined` in a class method — what are the possible causes?**

The method was destructured from the instance (`const {method} = instance`). It was passed as a callback without binding. It's a static method being called on an instance. It's an async method and `this` was lost in a callback inside it. Fixes: bind in the constructor, use class field arrow functions, or use `fn.bind(instance)` at the call site.

**Q211. How would you implement a simple template engine?**

Replace `{{variable}}` placeholders with values from a context object: `str.replace(/\{\{(\w+)\}\}/g, (_, key) => context[key] ?? '')`. For loops and conditionals, parse into an AST and evaluate. For production use: Handlebars, Mustache, or Nunjucks. For type safety: tagged template literals with TypeScript.

**Q212. How do you make a JavaScript library tree-shakeable?**

Use named exports (not a single default export object). Avoid side effects at module load time. Mark the package as `"sideEffects": false` in `package.json` (or list files that do have side effects). Use ES module format. Avoid importing one large utility that pulls in everything — provide granular per-function imports.

**Q213. What are the trade-offs between using `class` and factory functions in JavaScript?**

Classes: familiar syntax, `instanceof` works, better performance for many instances (shared prototype methods), native `private` fields (ES2022). Factory functions: no `new` required, naturally encapsulated private data via closure, easy mixins, more flexible, no prototype chain confusion. Factory functions are preferred in functional codebases; classes in OOP-heavy codebases.

**Q214. How would you implement server-sent events (SSE) on the client side?**

`const source = new EventSource('/events')`. `source.onmessage = e => handle(e.data)`. `source.addEventListener('customEvent', handler)`. `source.onerror` for reconnection logic. SSE auto-reconnects on disconnect. One-way server-to-client only. Use `source.close()` to stop. Better than polling; simpler than WebSockets for push-only scenarios.

**Q215. Explain how JavaScript handles concurrency with the event loop, Workers, and SharedArrayBuffer.**

The event loop handles concurrency at the application level — non-blocking I/O via callbacks, interleaved on the single main thread. Web Workers provide true parallelism — separate threads with no shared memory (communicate via `postMessage`). `SharedArrayBuffer` allows workers to share memory for performance-critical scenarios, requiring `Atomics` for synchronization. These three layers allow JavaScript to scale from simple async to multi-threaded parallelism.

**Q216. How would you design JavaScript error handling for a large team?**

Establish error taxonomy — `ValidationError`, `NetworkError`, `NotFoundError` all extending `AppError` with codes. Central `handleError` function that: logs structured data, triggers monitoring, maps to user messages. Lint rules for no floating promises, no empty catch blocks. Document error contracts for every public function. Integration tests for error paths.

**Q217. What is `WeakRef` and `FinalizationRegistry`?**

`WeakRef` holds a weak reference to an object — if the object is GC'd, `ref.deref()` returns `undefined`. `FinalizationRegistry` registers a callback to run after an object is collected. Used for: caches that shouldn't prevent GC, tracking live instances for debugging. The GC timing is non-deterministic — don't rely on these for critical logic.

**Q218. How do you handle JavaScript in a security-sensitive context (e.g., fintech)?**

Subresource Integrity (SRI) on external scripts. Strict CSP. No `eval`, `new Function`, `innerHTML` with user data. Sanitize all inputs. HTTPS everywhere. `HttpOnly`/`Secure` cookies. Dependency auditing (`npm audit`). Regular penetration testing. Runtime Application Self-Protection (RASP). Code review for timing attacks and prototype pollution.

**Q219. What is the JavaScript garbage collection impact of closures?**

A closure keeps references to all variables in its outer scope alive, even those not explicitly used — in some engines. This can cause large objects to be retained unintentionally. Fix: nullify references when done (`largeData = null`), extract only needed values from outer scope rather than capturing the whole scope, use WeakRef for caches.

**Q220. How would you build an offline-first JavaScript web app?**

Service Worker for caching assets and API responses (Cache API). Background sync for deferring requests when offline. IndexedDB for structured client-side storage. Optimistic UI updates that sync when connection restores. Conflict resolution strategy (last-write-wins or CRDT). Workbox simplifies service worker caching strategies.

**Q221. Explain how you'd port a callback-based API to use Promises.**

`function promisify(fn) { return (...args) => new Promise((resolve, reject) => { fn(...args, (err, result) => err ? reject(err) : resolve(result)); }); }`. Node.js provides `util.promisify` for Node-style (error-first) callbacks. For event-based APIs: wrap in a Promise that resolves on the success event and rejects on the error event.

**Q222. How do you profile and optimize a JavaScript animation that's dropping frames?**

Use Chrome DevTools Performance tab to record frames. Look for long tasks (red bars) on the main thread. Move expensive calculations to a Worker. Avoid layout thrash — read all properties before writing. Use `transform` and `opacity` for GPU-accelerated animations. Use `requestAnimationFrame` for timing. Reduce paint area with `will-change: transform`.

**Q223. Design a JavaScript plugin system.**

A `PluginManager` class with `register(plugin)` and `run(hook, context)`. Plugins are objects with hook names as keys: `{beforeSave: async (ctx) => {...}}`. Manager maintains a `Map<hookName, Plugin[]>`. On `run`, iterate plugins for that hook in registration order. Support async hooks with sequential `await` or parallel `Promise.all`. Provide `context` object for plugins to share state.

**Q224. What is the difference between `Object.keys`, `Object.values`, `Object.entries`, and `Object.fromEntries`?**

`Object.keys(obj)`: own enumerable string key names. `Object.values(obj)`: own enumerable values. `Object.entries(obj)`: own enumerable `[key, value]` pairs. `Object.fromEntries(iterable)`: creates an object from key-value pairs (inverse of `entries`). Together, these enable functional transformations: `Object.fromEntries(Object.entries(obj).map(([k, v]) => [k, transform(v)]))`.

**Q225. How would you implement structured concurrency in JavaScript?**

Group async operations so all are cancelled/resolved together. Model with an `AbortController` shared among tasks. Pattern: `async function withTimeout(fn, ms) { const ac = new AbortController(); const timer = setTimeout(() => ac.abort(), ms); try { return await fn(ac.signal); } finally { clearTimeout(timer); } }`. The TC39 `Async Context` proposal and `AbortSignal.any()` improve this further. Libraries like `effect-ts` provide structured concurrency primitives.
