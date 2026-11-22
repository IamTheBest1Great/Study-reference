# JavaScript Interview Questions — Coding / Implementation

A consolidated, deduplicated collection of **hands-on coding, implementation, polyfill, and output-based JavaScript interview questions** — write-a-function tasks, polyfills to implement, and predict-the-output code snippets — organized section-wise.

**Total unique questions: 183**

## Table of Contents

- [Closures, Scope & Hoisting](#closures-scope-hoisting) (8)
  - [1. What is the output of the following code? `console.log(foo()); console.log(bar()); function foo() { return "foo";...`?](#1-what-is-the-output-of-the-following-code-consolelogfoo-consolelogbar-function-foo-return-foo)
  - [2. What is the output of the following code? `function outer() { console.log(x); if (false) { var x = 10; } console....`?](#2-what-is-the-output-of-the-following-code-function-outer-consolelogx-if-false-var-x-10-console)
  - [3. What is the output of the following code? `function outer() { var x = 10; var inner = function() { console.log(x)...`?](#3-what-is-the-output-of-the-following-code-function-outer-var-x-10-var-inner-function-consolelogx)
  - [4. What is the output of the following code? `var a = 1; (function() { console.log(a); var a = 2; console.log(a); })...`?](#4-what-is-the-output-of-the-following-code-var-a-1-function-consoleloga-var-a-2-consoleloga)
  - [5. What is the output of the following code? `var a = 1; function a() {} console.log(a); function b() {} var b = 2; ...`?](#5-what-is-the-output-of-the-following-code-var-a-1-function-a-consoleloga-function-b-var-b-2)
  - [6. What is the output of the following code? `var fns = []; for (var i = 0; i < 3; i++) { fns.push((function(j) { re...`?](#6-what-is-the-output-of-the-following-code-var-fns-for-var-i-0-i-3-i-fnspushfunctionj-re)
  - [7. What is the output of the following code? `var x = 10; function foo() { return x; var x = 20; } console.log(foo()...`?](#7-what-is-the-output-of-the-following-code-var-x-10-function-foo-return-x-var-x-20-consolelogfoo)
  - [8. What is the output of the following code? `var x = 1; function test() { console.log(x); var x = 2; console.log(x)...`?](#8-what-is-the-output-of-the-following-code-var-x-1-function-test-consolelogx-var-x-2-consolelogx)
- [`this`, call/apply/bind & Functions](#this-callapplybind-functions) (6)
  - [9. How would you implement `curry` function from scratch?](#9-how-would-you-implement-curry-function-from-scratch)
  - [10. Implement: `once` — function that can only be called once.](#10-implement-once-function-that-can-only-be-called-once)
  - [11. What is the output of the following code? `(function(x, y) { console.log(x + y); })(3, 4); console.log( (function...`?](#11-what-is-the-output-of-the-following-code-functionx-y-consolelogx-y-3-4-consolelog-function)
  - [12. What is the output of the following code? `function curry(fn) { return function curried(...args) { if (args.lengt...`?](#12-what-is-the-output-of-the-following-code-function-curryfn-return-function-curriedargs-if-argslengt)
  - [13. What is the output of the following code? `function greet(greeting, punctuation) { return `${greeting}, ${this.na...`?](#13-what-is-the-output-of-the-following-code-function-greetgreeting-punctuation-return-greeting-thisna)
  - [14. What is the output of the following code? `var result = (function(a) { return (function(b) { return a + b; })(2);...`?](#14-what-is-the-output-of-the-following-code-var-result-functiona-return-functionb-return-a-b-2)
- [Prototypes, Classes & OOP](#prototypes-classes-oop) (20)
  - [15. How to place 5 divs in a row without using flex, margin, or padding? (Hint: display: inline-block)](#15-how-to-place-5-divs-in-a-row-without-using-flex-margin-or-padding-hint-display-inline-block)
  - [16. How would you implement an event emitter?](#16-how-would-you-implement-an-event-emitter)
  - [17. What is the output of the following code? `class Animal { constructor(name) { this.name = name; this.type = this....`?](#17-what-is-the-output-of-the-following-code-class-animal-constructorname-thisname-name-thistype-this)
  - [18. What is the output of the following code? `class Animal { constructor(name) { this.name = name; } speak() { retur...`?](#18-what-is-the-output-of-the-following-code-class-animal-constructorname-thisname-name-speak-retur)
  - [19. What is the output of the following code? `class Base { constructor() { console.log(new.target.name); } } class C...`?](#19-what-is-the-output-of-the-following-code-class-base-constructor-consolelognewtargetname-class-c)
  - [20. What is the output of the following code? `class Base { static create() { return new this(); } describe() { retur...`?](#20-what-is-the-output-of-the-following-code-class-base-static-create-return-new-this-describe-retur)
  - [21. What is the output of the following code? `class Button { constructor(label) { this.label = label; } click() { co...`?](#21-what-is-the-output-of-the-following-code-class-button-constructorlabel-thislabel-label-click-co)
  - [22. What is the output of the following code? `class Counter { count = 0; increment = () => { this.count++; console.l...`?](#22-what-is-the-output-of-the-following-code-class-counter-count-0-increment-thiscount-consolel)
  - [23. What is the output of the following code? `class Counter { static count = 0; constructor() { Counter.count++; thi...`?](#23-what-is-the-output-of-the-following-code-class-counter-static-count-0-constructor-countercount-thi)
  - [24. What is the output of the following code? `class EventEmitter { #handlers = {}; on(event, fn) { (this.#handlers[e...`?](#24-what-is-the-output-of-the-following-code-class-eventemitter-handlers-onevent-fn-thishandlerse)
  - [25. What is the output of the following code? `class MyArray extends Array { sum() { return this.reduce((a, b) => a +...`?](#25-what-is-the-output-of-the-following-code-class-myarray-extends-array-sum-return-thisreducea-b-a)
  - [26. What is the output of the following code? `class MyClass { #secret = 42; getSecret() { return this.#secret; } } c...`?](#26-what-is-the-output-of-the-following-code-class-myclass-secret-42-getsecret-return-thissecret-c)
  - [27. What is the output of the following code? `class MyClass { name = 'class'; regularMethod() { return this.name; } ...`?](#27-what-is-the-output-of-the-following-code-class-myclass-name-class-regularmethod-return-thisname)
  - [28. What is the output of the following code? `const obj = new MyClass(); class MyClass { greet() { return "hello"; }...`?](#28-what-is-the-output-of-the-following-code-const-obj-new-myclass-class-myclass-greet-return-hello)
  - [29. What is the output of the following code? `const parent = { a: 1 }; const child = Object.create(parent); child.b ...`?](#29-what-is-the-output-of-the-following-code-const-parent-a-1-const-child-objectcreateparent-childb)
  - [30. What is the output of the following code? `function Animal(name) { this.name = name; } Animal.prototype.speak = f...`?](#30-what-is-the-output-of-the-following-code-function-animalname-thisname-name-animalprototypespeak-f)
  - [31. What is the output of the following code? `function Foo() {} const f = new Foo(); Foo.prototype = {}; const g = n...`?](#31-what-is-the-output-of-the-following-code-function-foo-const-f-new-foo-fooprototype-const-g-n)
  - [32. What is the output of the following code? `function Person(name) { this.name = name; } Person.prototype.greet = f...`?](#32-what-is-the-output-of-the-following-code-function-personname-thisname-name-personprototypegreet-f)
  - [33. What is the output of the following code? `function Vehicle() {} Vehicle.prototype.type = 'vehicle'; function Car...`?](#33-what-is-the-output-of-the-following-code-function-vehicle-vehicleprototypetype-vehicle-function-car)
  - [34. Write a polyfill for `call`, `apply`, and `bind`.](#34-write-a-polyfill-for-call-apply-and-bind)
- [ES6+ Features (Destructuring, Spread/Rest, Modules)](#es6-features-destructuring-spreadrest-modules) (62)
  - [35. Implement: `compose` vs `pipe` — output prediction.](#35-implement-compose-vs-pipe-output-prediction)
  - [36. Implement: Check if a string is a palindrome (ignoring spaces/punctuation).](#36-implement-check-if-a-string-is-a-palindrome-ignoring-spacespunctuation)
  - [37. Implement: Deep merge two objects.](#37-implement-deep-merge-two-objects)
  - [38. Implement: Given a string, find the first non-repeating character.](#38-implement-given-a-string-find-the-first-non-repeating-character)
  - [39. What is the output of the following code? `// Chained optional chaining + nullish coalescing: const user = { prof...`?](#39-what-is-the-output-of-the-following-code-chained-optional-chaining-nullish-coalescing-const-user-prof)
  - [40. What is the output of the following code? `// Map iteration order vs Object: const map = new Map(); map.set('b', ...`?](#40-what-is-the-output-of-the-following-code-map-iteration-order-vs-object-const-map-new-map-mapsetb)
  - [41. What is the output of the following code? `// Tricky destructuring: const { a: { b } } = { a: { b: 42 } }; consol...`?](#41-what-is-the-output-of-the-following-code-tricky-destructuring-const-a-b-a-b-42-consol)
  - [42. What is the output of the following code? `// Tricky: what does this print? const arr = [1, 2, 3]; // forEach wit...`?](#42-what-is-the-output-of-the-following-code-tricky-what-does-this-print-const-arr-1-2-3-foreach-wit)
  - [43. What is the output of the following code? `console.log(a); let a = 5;...`?](#43-what-is-the-output-of-the-following-code-consoleloga-let-a-5)
  - [44. What is the output of the following code? `console.log(true ? 'yes' : 'no'); console.log(false ? 'yes' : 'no'); /...`?](#44-what-is-the-output-of-the-following-code-consolelogtrue-yes-no-consolelogfalse-yes-no)
  - [45. What is the output of the following code? `const [a, , b, ...rest] = [1, 2, 3, 4, 5]; console.log(a, b, rest); co...`?](#45-what-is-the-output-of-the-following-code-const-a-b-rest-1-2-3-4-5-consoleloga-b-rest-co)
  - [46. What is the output of the following code? `const a = [1, 2, 3]; const b = [1, 2, 3]; const c = a; console.log(a =...`?](#46-what-is-the-output-of-the-following-code-const-a-1-2-3-const-b-1-2-3-const-c-a-consoleloga)
  - [47. What is the output of the following code? `const a = { toString() { return 'A'; } }; const b = { toString() { ret...`?](#47-what-is-the-output-of-the-following-code-const-a-tostring-return-a-const-b-tostring-ret)
  - [48. What is the output of the following code? `const a = { val: 1 }; const b = a; b.val = 2; console.log(a.val); cons...`?](#48-what-is-the-output-of-the-following-code-const-a-val-1-const-b-a-bval-2-consolelogaval-cons)
  - [49. What is the output of the following code? `const arr = [1, 2, 3, 4, 5]; delete arr[2]; console.log(arr); console....`?](#49-what-is-the-output-of-the-following-code-const-arr-1-2-3-4-5-delete-arr2-consolelogarr-console)
  - [50. What is the output of the following code? `const arr = [1, 2, 3]; arr.extra = 'surprise'; for (let val of arr) { ...`?](#50-what-is-the-output-of-the-following-code-const-arr-1-2-3-arrextra-surprise-for-let-val-of-arr)
  - [51. What is the output of the following code? `const arr = [1, 2, 3]; arr[10] = 11; console.log(arr.length); console....`?](#51-what-is-the-output-of-the-following-code-const-arr-1-2-3-arr10-11-consolelogarrlength-console)
  - [52. What is the output of the following code? `const cache = new WeakMap(); function process(obj) { if (cache.has(obj...`?](#52-what-is-the-output-of-the-following-code-const-cache-new-weakmap-function-processobj-if-cachehasobj)
  - [53. What is the output of the following code? `const factorial = function fact(n) { if (n <= 1) return 1; return n * ...`?](#53-what-is-the-output-of-the-following-code-const-factorial-function-factn-if-n-1-return-1-return-n)
  - [54. What is the output of the following code? `const gen = (function*() { let id = 0; while (true) { yield ++id; } })...`?](#54-what-is-the-output-of-the-following-code-const-gen-function-let-id-0-while-true-yield-id)
  - [55. What is the output of the following code? `const handler = { get(target, prop) { return prop in target ? target[p...`?](#55-what-is-the-output-of-the-following-code-const-handler-gettarget-prop-return-prop-in-target-targetp)
  - [56. What is the output of the following code? `const handler = { get(target, prop, receiver) { console.log(`get: ${pr...`?](#56-what-is-the-output-of-the-following-code-const-handler-gettarget-prop-receiver-consolelogget-pr)
  - [57. What is the output of the following code? `const key = 'name'; const obj = { [key]: 'Alice', ['age']: 30, [1 + 2]...`?](#57-what-is-the-output-of-the-following-code-const-key-name-const-obj-key-alice-age-30-1-2)
  - [58. What is the output of the following code? `const map = new Map(); map.set('1', 'string key'); map.set(1, 'number ...`?](#58-what-is-the-output-of-the-following-code-const-map-new-map-mapset1-string-key-mapset1-number)
  - [59. What is the output of the following code? `const obj = Object.freeze({ a: 1, nested: { b: 2 } }); obj.a = 99; obj...`?](#59-what-is-the-output-of-the-following-code-const-obj-objectfreeze-a-1-nested-b-2-obja-99-obj)
  - [60. What is the output of the following code? `const obj = { a: 1, b: function() { return this.a; }, c: () => this?.a...`?](#60-what-is-the-output-of-the-following-code-const-obj-a-1-b-function-return-thisa-c-thisa)
  - [61. What is the output of the following code? `const obj = { a: { b: { c: 42 } } }; console.log(obj?.a?.b?.c); consol...`?](#61-what-is-the-output-of-the-following-code-const-obj-a-b-c-42-consolelogobjabc-consol)
  - [62. What is the output of the following code? `const obj = { data: [1, 2, 3], double() { return this.data.map(functio...`?](#62-what-is-the-output-of-the-following-code-const-obj-data-1-2-3-double-return-thisdatamapfunctio)
  - [63. What is the output of the following code? `const obj = { name: 'Alice', greet: () => { console.log(this.name); } ...`?](#63-what-is-the-output-of-the-following-code-const-obj-name-alice-greet-consolelogthisname)
  - [64. What is the output of the following code? `const obj = { name: 'Alice', greet: function() { console.log(this.name...`?](#64-what-is-the-output-of-the-following-code-const-obj-name-alice-greet-function-consolelogthisname)
  - [65. What is the output of the following code? `const obj = { x: 1, getX: function() { return function() { return this...`?](#65-what-is-the-output-of-the-following-code-const-obj-x-1-getx-function-return-function-return-this)
  - [66. What is the output of the following code? `const obj = {}; obj[true] = 'bool'; obj[1] = 'number'; obj['1'] = 'str...`?](#66-what-is-the-output-of-the-following-code-const-obj-objtrue-bool-obj1-number-obj1-str)
  - [67. What is the output of the following code? `const original = { a: 1, b: { c: 2 } }; // Attempt 1: JSON roundtrip c...`?](#67-what-is-the-output-of-the-following-code-const-original-a-1-b-c-2-attempt-1-json-roundtrip-c)
  - [68. What is the output of the following code? `const original = { a: 1, nested: { b: 2 } }; const copy = { ...origina...`?](#68-what-is-the-output-of-the-following-code-const-original-a-1-nested-b-2-const-copy-origina)
  - [69. What is the output of the following code? `const person = { firstName: 'John', lastName: 'Doe', get fullName() { ...`?](#69-what-is-the-output-of-the-following-code-const-person-firstname-john-lastname-doe-get-fullname)
  - [70. What is the output of the following code? `const proto = { greet() { return `Hello, ${this.name}`; } }; const obj...`?](#70-what-is-the-output-of-the-following-code-const-proto-greet-return-hello-thisname-const-obj)
  - [71. What is the output of the following code? `const result = (1, 2, 3); console.log(result); for (let i = 0, j = 10;...`?](#71-what-is-the-output-of-the-following-code-const-result-1-2-3-consolelogresult-for-let-i-0-j-10)
  - [72. What is the output of the following code? `const sym1 = Symbol('key'); const sym2 = Symbol('key'); console.log(sy...`?](#72-what-is-the-output-of-the-following-code-const-sym1-symbolkey-const-sym2-symbolkey-consolelogsy)
  - [73. What is the output of the following code? `const { a: x = 10, b: y = 20, c: z = 30 } = { a: 1, b: undefined }; co...`?](#73-what-is-the-output-of-the-following-code-const-a-x-10-b-y-20-c-z-30-a-1-b-undefined-co)
  - [74. What is the output of the following code? `function createCounter() { let count = 0; return { increment() { count...`?](#74-what-is-the-output-of-the-following-code-function-createcounter-let-count-0-return-increment-count)
  - [75. What is the output of the following code? `function foo() { return this.x; } const bound1 = foo.bind({ x: 1 }); c...`?](#75-what-is-the-output-of-the-following-code-function-foo-return-thisx-const-bound1-foobind-x-1-c)
  - [76. What is the output of the following code? `function Foo() { this.x = 1; return { x: 2 }; // Returns an object! } ...`?](#76-what-is-the-output-of-the-following-code-function-foo-thisx-1-return-x-2-returns-an-object)
  - [77. What is the output of the following code? `function greet() { return `Hi, ${this.name}`; } const alice = { name: ...`?](#77-what-is-the-output-of-the-following-code-function-greet-return-hi-thisname-const-alice-name)
  - [78. What is the output of the following code? `function makeAdder(x) { return function(y) { return x + y; }; } const ...`?](#78-what-is-the-output-of-the-following-code-function-makeadderx-return-functiony-return-x-y-const)
  - [79. What is the output of the following code? `function makeMultiplier(x) { return (y) => x * y; } const double = mak...`?](#79-what-is-the-output-of-the-following-code-function-makemultiplierx-return-y-x-y-const-double-mak)
  - [80. What is the output of the following code? `function noDefault(a, b, c) {} function withDefault(a, b = 2, c) {} fu...`?](#80-what-is-the-output-of-the-following-code-function-nodefaulta-b-c-function-withdefaulta-b-2-c-fu)
  - [81. What is the output of the following code? `function outer() { let x = 10; function middle() { let y = 20; functio...`?](#81-what-is-the-output-of-the-following-code-function-outer-let-x-10-function-middle-let-y-20-functio)
  - [82. What is the output of the following code? `function Person(name) { this.name = name; console.log(this); } const p...`?](#82-what-is-the-output-of-the-following-code-function-personname-thisname-name-consolelogthis-const-p)
  - [83. What is the output of the following code? `function sum() { return arguments[0] + arguments[1]; } const arrowSum ...`?](#83-what-is-the-output-of-the-following-code-function-sum-return-arguments0-arguments1-const-arrowsum)
  - [84. What is the output of the following code? `function tag(strings, ...values) { console.log(strings); console.log(v...`?](#84-what-is-the-output-of-the-following-code-function-tagstrings-values-consolelogstrings-consolelogv)
  - [85. What is the output of the following code? `function test() { console.log(arguments[0]); console.log(arguments.len...`?](#85-what-is-the-output-of-the-following-code-function-test-consolelogarguments0-consolelogargumentslen)
  - [86. What is the output of the following code? `function test(...args) { console.log(args); } const arr = [1, 2, 3]; t...`?](#86-what-is-the-output-of-the-following-code-function-testargs-consolelogargs-const-arr-1-2-3-t)
  - [87. What is the output of the following code? `function* gen() { console.log('start'); yield 1; console.log('middle')...`?](#87-what-is-the-output-of-the-following-code-function-gen-consolelogstart-yield-1-consolelogmiddle)
  - [88. What is the output of the following code? `function* gen() { yield 1; yield 2; return 3; yield 4; } const g = gen...`?](#88-what-is-the-output-of-the-following-code-function-gen-yield-1-yield-2-return-3-yield-4-const-g-gen)
  - [89. What is the output of the following code? `function* infinite() { let i = 0; while (true) yield i++; } const gen ...`?](#89-what-is-the-output-of-the-following-code-function-infinite-let-i-0-while-true-yield-i-const-gen)
  - [90. What is the output of the following code? `let a = 5; console.log(a++); console.log(a); console.log(++a); console...`?](#90-what-is-the-output-of-the-following-code-let-a-5-consoleloga-consoleloga-consoleloga-console)
  - [91. What is the output of the following code? `let counter = 0; function getDefault() { return ++counter; } function ...`?](#91-what-is-the-output-of-the-following-code-let-counter-0-function-getdefault-return-counter-function)
  - [92. What is the output of the following code? `let i = 0; const obj = { next() { return i < 3 ? { value: i++, done: f...`?](#92-what-is-the-output-of-the-following-code-let-i-0-const-obj-next-return-i-3-value-i-done-f)
  - [93. What is the output of the following code? `let obj = { val: 1, [Symbol.toPrimitive](hint) { console.log('hint:', ...`?](#93-what-is-the-output-of-the-following-code-let-obj-val-1-symboltoprimitivehint-consoleloghint)
  - [94. What is the output of the following code? `let x = 'global'; function outer() { let x = 'outer'; function inner()...`?](#94-what-is-the-output-of-the-following-code-let-x-global-function-outer-let-x-outer-function-inner)
  - [95. What is the output of the following code? `let x = 1; { let x = 2; { let x = 3; console.log(x); } console.log(x);...`?](#95-what-is-the-output-of-the-following-code-let-x-1-let-x-2-let-x-3-consolelogx-consolelogx)
  - [96. What is the output or behavior?](#96-what-is-the-output-or-behavior)
- [Arrays, Objects & Data Structures](#arrays-objects-data-structures) (8)
  - [97. Design a notification/toast system with queueing, auto-dismiss, and priority handling.](#97-design-a-notificationtoast-system-with-queueing-auto-dismiss-and-priority-handling)
  - [98. Design a Progress Bar / Stepper with configurable steps and validation logic.](#98-design-a-progress-bar-stepper-with-configurable-steps-and-validation-logic)
  - [99. Design a Todo List application with add, edit, delete, and mark‑as‑complete.](#99-design-a-todo-list-application-with-add-edit-delete-and-markascomplete)
  - [100. Implement: `chunk(array, size)` — split array into chunks.](#100-implement-chunkarray-size-split-array-into-chunks)
  - [101. Implement: Flatten array to any depth.](#101-implement-flatten-array-to-any-depth)
  - [102. What is the output of the following code? `console.log([] == ![]);...`?](#102-what-is-the-output-of-the-following-code-consolelog)
  - [103. What is the output?](#103-what-is-the-output)
  - [104. What is the output?](#104-what-is-the-output)
- [Type Coercion, Equality & Data Types](#type-coercion-equality-data-types) (12)
  - [105. What is the output of the following code? `console.log("B" + "a" + + "a" + "a");...`?](#105-what-is-the-output-of-the-following-code-consolelogb-a-a-a)
  - [106. What is the output of the following code? `console.log(+true); console.log(+false); console.log(+null); console.l...`?](#106-what-is-the-output-of-the-following-code-consolelogtrue-consolelogfalse-consolelognull-consolel)
  - [107. What is the output of the following code? `console.log(false || 'default'); console.log('' || 'default'); console...`?](#107-what-is-the-output-of-the-following-code-consolelogfalse-default-consolelog-default-console)
  - [108. What is the output of the following code? `console.log(NaN === NaN); console.log(NaN == NaN); console.log(isNaN("...`?](#108-what-is-the-output-of-the-following-code-consolelognan-nan-consolelognan-nan-consolelogisnan)
  - [109. What is the output of the following code? `console.log(null + 1); console.log(undefined + 1); console.log(null + ...`?](#109-what-is-the-output-of-the-following-code-consolelognull-1-consolelogundefined-1-consolelognull)
  - [110. What is the output of the following code? `console.log(typeof foo); console.log(typeof bar); var foo = function()...`?](#110-what-is-the-output-of-the-following-code-consolelogtypeof-foo-consolelogtypeof-bar-var-foo-function)
  - [111. What is the output of the following code? `console.log(typeof null); console.log(typeof undefined); console.log(t...`?](#111-what-is-the-output-of-the-following-code-consolelogtypeof-null-consolelogtypeof-undefined-consolelogt)
  - [112. What is the output of the following code? `console.log(typeof typeof 1); console.log(typeof typeof 'hello'); cons...`?](#112-what-is-the-output-of-the-following-code-consolelogtypeof-typeof-1-consolelogtypeof-typeof-hello-cons)
  - [113. What is the output of the following code? `function processData(data) { if (typeof data !== 'string') { throw new...`?](#113-what-is-the-output-of-the-following-code-function-processdatadata-if-typeof-data-string-throw-new)
  - [114. What is the output of the following code? `function test() { console.log(typeof x); console.log(typeof y); var x ...`?](#114-what-is-the-output-of-the-following-code-function-test-consolelogtypeof-x-consolelogtypeof-y-var-x)
  - [115. What is the output of the following code? `var NULL = undefined; console.log(typeof undefined == typeof NULL);...`?](#115-what-is-the-output-of-the-following-code-var-null-undefined-consolelogtypeof-undefined-typeof-null)
  - [116. What is the output: `typeof null`?](#116-what-is-the-output-typeof-null)
- [Asynchronous JavaScript (Promises, async/await, Event Loop)](#asynchronous-javascript-promises-asyncawait-event-loop) (31)
  - [117. Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.](#117-design-a-search-with-autocomplete-typeahead-debouncing-caching-race-conditions)
  - [118. Design a state management solution for a complex app.](#118-design-a-state-management-solution-for-a-complex-app)
  - [119. Design an autocomplete search with debouncing, caching, and race condition handling.](#119-design-an-autocomplete-search-with-debouncing-caching-and-race-condition-handling)
  - [120. Implement: `pipe` with error handling and async support.](#120-implement-pipe-with-error-handling-and-async-support)
  - [121. What is the output of the following code? `async function a() { console.log('a start'); await b(); console.log('a...`?](#121-what-is-the-output-of-the-following-code-async-function-a-consoleloga-start-await-b-consoleloga)
  - [122. What is the output of the following code? `async function fail() { throw new Error('async error'); } async functi...`?](#122-what-is-the-output-of-the-following-code-async-function-fail-throw-new-errorasync-error-async-functi)
  - [123. What is the output of the following code? `async function fails() { throw new Error('async fail'); } // Will this...`?](#123-what-is-the-output-of-the-following-code-async-function-fails-throw-new-errorasync-fail-will-this)
  - [124. What is the output of the following code? `async function fetchData() { return 42; } const result = fetchData(); ...`?](#124-what-is-the-output-of-the-following-code-async-function-fetchdata-return-42-const-result-fetchdata)
  - [125. What is the output of the following code? `async function main() { console.log('A'); await Promise.resolve(); con...`?](#125-what-is-the-output-of-the-following-code-async-function-main-consoleloga-await-promiseresolve-con)
  - [126. What is the output of the following code? `async function one() { return 1; } async function two() { const a = aw...`?](#126-what-is-the-output-of-the-following-code-async-function-one-return-1-async-function-two-const-a-aw)
  - [127. What is the output of the following code? `async function test() { console.log(1); await null; console.log(2); aw...`?](#127-what-is-the-output-of-the-following-code-async-function-test-consolelog1-await-null-consolelog2-aw)
  - [128. What is the output of the following code? `async function test() { const result = await Promise.all([ Promise.res...`?](#128-what-is-the-output-of-the-following-code-async-function-test-const-result-await-promiseall-promiseres)
  - [129. What is the output of the following code? `console.log('1'); setTimeout(() => console.log('2'), 0); Promise.resol...`?](#129-what-is-the-output-of-the-following-code-consolelog1-settimeout-consolelog2-0-promiseresol)
  - [130. What is the output of the following code? `console.log('A'); setTimeout(() => console.log('B'), 0); console.log('...`?](#130-what-is-the-output-of-the-following-code-consoleloga-settimeout-consolelogb-0-consolelog)
  - [131. What is the output of the following code? `console.log('before'); new Promise((resolve) => { console.log('inside ...`?](#131-what-is-the-output-of-the-following-code-consolelogbefore-new-promiseresolve-consoleloginside)
  - [132. What is the output of the following code? `const p = new Promise((resolve) => { resolve(1); resolve(2); resolve(3...`?](#132-what-is-the-output-of-the-following-code-const-p-new-promiseresolve-resolve1-resolve2-resolve3)
  - [133. What is the output of the following code? `const p1 = new Promise((resolve) => setTimeout(() => resolve('P1'), 30...`?](#133-what-is-the-output-of-the-following-code-const-p1-new-promiseresolve-settimeout-resolvep1-30)
  - [134. What is the output of the following code? `const promise1 = Promise.resolve(1); const promise2 = Promise.resolve(...`?](#134-what-is-the-output-of-the-following-code-const-promise1-promiseresolve1-const-promise2-promiseresolve)
  - [135. What is the output of the following code? `for (let i = 0; i < 3; i++) { setTimeout(function() { console.log(i); ...`?](#135-what-is-the-output-of-the-following-code-for-let-i-0-i-3-i-settimeoutfunction-consolelogi)
  - [136. What is the output of the following code? `for (var i = 0; i < 3; i++) { setTimeout(function() { console.log(i); ...`?](#136-what-is-the-output-of-the-following-code-for-var-i-0-i-3-i-settimeoutfunction-consolelogi)
  - [137. What is the output of the following code? `function Timer() { this.seconds = 0; setInterval(function() { this.sec...`?](#137-what-is-the-output-of-the-following-code-function-timer-thisseconds-0-setintervalfunction-thissec)
  - [138. What is the output of the following code? `let resolve; const p = new Promise(r => { resolve = r; }); p.then(v =>...`?](#138-what-is-the-output-of-the-following-code-let-resolve-const-p-new-promiser-resolve-r-pthenv)
  - [139. What is the output of the following code? `Promise.resolve('start') .then(val => { console.log(val); return 'seco...`?](#139-what-is-the-output-of-the-following-code-promiseresolvestart-thenval-consolelogval-return-seco)
  - [140. What is the output of the following code? `Promise.resolve() .then(() => { throw new Error('oops'); }) .then(() =...`?](#140-what-is-the-output-of-the-following-code-promiseresolve-then-throw-new-erroroops-then)
  - [141. What is the output of the following code? `Promise.resolve().then(() => console.log('Promise 1')); queueMicrotask...`?](#141-what-is-the-output-of-the-following-code-promiseresolvethen-consolelogpromise-1-queuemicrotask)
  - [142. What is the output of the following code? `Promise.resolve(1) .then(v => { console.log(v); return Promise.resolve...`?](#142-what-is-the-output-of-the-following-code-promiseresolve1-thenv-consolelogv-return-promiseresolve)
  - [143. What is the output of the following code? `Promise.resolve(1) .then(x => { console.log(x); return x + 1; }) .then...`?](#143-what-is-the-output-of-the-following-code-promiseresolve1-thenx-consolelogx-return-x-1-then)
  - [144. What is the output of the following code? `setTimeout(() => console.log('A'), 0); setTimeout(() => { console.log(...`?](#144-what-is-the-output-of-the-following-code-settimeout-consoleloga-0-settimeout-consolelog)
  - [145. What is the output? (Most asked JS output question)](#145-what-is-the-output-most-asked-js-output-question)
  - [146. What is the output? (Node.js)](#146-what-is-the-output-nodejs)
  - [147. What is the output? (Ultimate async challenge)](#147-what-is-the-output-ultimate-async-challenge)
- [Error Handling & Debugging](#error-handling-debugging) (1)
  - [148. How do you create a custom error?](#148-how-do-you-create-a-custom-error)
- [General / Miscellaneous JavaScript Concepts](#general-miscellaneous-javascript-concepts) (35)
  - [149. Design a carousel that can handle 1000+ images efficiently.](#149-design-a-carousel-that-can-handle-1000-images-efficiently)
  - [150. Design a config-driven form renderer using a JSON schema.](#150-design-a-config-driven-form-renderer-using-a-json-schema)
  - [151. Design a data table with sorting, filtering, pagination, and performance trade-offs.](#151-design-a-data-table-with-sorting-filtering-pagination-and-performance-trade-offs)
  - [152. Design a drag-and-drop interface (e.g., kanban board).](#152-design-a-drag-and-drop-interface-eg-kanban-board)
  - [153. Design a multi-step form with validation.](#153-design-a-multi-step-form-with-validation)
  - [154. Design a Posts with Comments system – how do you manage deeply nested data?](#154-design-a-posts-with-comments-system-how-do-you-manage-deeply-nested-data)
  - [155. Design a real-time dashboard with multiple data sources.](#155-design-a-real-time-dashboard-with-multiple-data-sources)
  - [156. Design a search with typeahead/autocomplete.](#156-design-a-search-with-typeaheadautocomplete)
  - [157. Design a state management solution for a complex analytics/dashboard app.](#157-design-a-state-management-solution-for-a-complex-analyticsdashboard-app)
  - [158. Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.](#158-design-an-e-commerce-frontend-with-filters-price-category-rating-and-scalable-state-updates)
  - [159. Design an image gallery with lazy loading and skeleton placeholders.](#159-design-an-image-gallery-with-lazy-loading-and-skeleton-placeholders)
  - [160. Design an infinite scrolling feed (virtualization, pagination, loading states).](#160-design-an-infinite-scrolling-feed-virtualization-pagination-loading-states)
  - [161. How do you create a form with validation?](#161-how-do-you-create-a-form-with-validation)
  - [162. How do you implement drag and drop using native APIs?](#162-how-do-you-implement-drag-and-drop-using-native-apis)
  - [163. Implement abstraction?](#163-implement-abstraction)
  - [164. Implement accessibility?](#164-implement-accessibility)
  - [165. What is the output of `0.1 + 0.2 === 0.3` and why?](#165-what-is-the-output-of-01-02-03-and-why)
  - [166. What is the output of the following code? `// As a STATEMENT (in console or at top level): {} + [] // As an EXPRE...`?](#166-what-is-the-output-of-the-following-code-as-a-statement-in-console-or-at-top-level-as-an-expre)
  - [167. What is the output of the following code? `console.log("" == false); console.log("" === false); console.log(0 == ...`?](#167-what-is-the-output-of-the-following-code-consolelog-false-consolelog-false-consolelog0)
  - [168. What is the output of the following code? `console.log("5" - 3); console.log("5" + 3); console.log("5" - "3"); co...`?](#168-what-is-the-output-of-the-following-code-consolelog5-3-consolelog5-3-consolelog5-3-co)
  - [169. What is the output of the following code? `console.log(0 || 'default'); console.log(0 ?? 'default'); console.log(...`?](#169-what-is-the-output-of-the-following-code-consolelog0-default-consolelog0-default-consolelog)
  - [170. What is the output of the following code? `console.log(0.1 + 0.2 === 0.3); console.log(0.1 + 0.2);...`?](#170-what-is-the-output-of-the-following-code-consolelog01-02-03-consolelog01-02)
  - [171. What is the output of the following code? `console.log(1 < 2 < 3); console.log(3 > 2 > 1);...`?](#171-what-is-the-output-of-the-following-code-consolelog1-2-3-consolelog3-2-1)
  - [172. What is the output of the following code? `console.log(1 == '1'); console.log(1 === '1'); console.log(1 == true);...`?](#172-what-is-the-output-of-the-following-code-consolelog1-1-consolelog1-1-consolelog1-true)
  - [173. What is the output of the following code? `console.log(5 & 3); console.log(5 | 3); console.log(5 ^ 3); console.lo...`?](#173-what-is-the-output-of-the-following-code-consolelog5-3-consolelog5-3-consolelog5-3-consolelo)
  - [174. What is the output of the following code? `console.log([10, 9, 2, 1, 100].sort()); console.log([10, 9, 2, 1, 100]...`?](#174-what-is-the-output-of-the-following-code-consolelog10-9-2-1-100sort-consolelog10-9-2-1-100)
  - [175. What is the output of the following code? `console.log([] + []); console.log([] + {}); console.log({} + []); // a...`?](#175-what-is-the-output-of-the-following-code-consolelog-consolelog-consolelog-a)
  - [176. What is the output of the following code? `console.log([] + []); console.log([] + {}); console.log({} + []); cons...`?](#176-what-is-the-output-of-the-following-code-consolelog-consolelog-consolelog-cons)
  - [177. What is the output of the following code? `console.log(null == undefined); console.log(null === undefined); conso...`?](#177-what-is-the-output-of-the-following-code-consolelognull-undefined-consolelognull-undefined-conso)
  - [178. What is the output of the following code? `console.log(true + false); console.log(true + true); console.log(false...`?](#178-what-is-the-output-of-the-following-code-consolelogtrue-false-consolelogtrue-true-consolelogfalse)
  - [179. What is the output of the following code? `console.log(void 0); console.log(void 'hello'); console.log(void (1 + ...`?](#179-what-is-the-output-of-the-following-code-consolelogvoid-0-consolelogvoid-hello-consolelogvoid-1)
  - [180. What is the output of the following code? `function createFunctions() { var result = []; for (var i = 0; i < 3; i...`?](#180-what-is-the-output-of-the-following-code-function-createfunctions-var-result-for-var-i-0-i-3-i)
  - [181. What is the output of the following code? `function test(a, b, c) { console.log(a, b, c); } test(1, ...[], 2); te...`?](#181-what-is-the-output-of-the-following-code-function-testa-b-c-consoleloga-b-c-test1-2-te)
  - [182. What is the output of the following code? `try { null.property; } catch (e) { console.log(e instanceof TypeError)...`?](#182-what-is-the-output-of-the-following-code-try-nullproperty-catch-e-consoleloge-instanceof-typeerror)
  - [183. What is the output of the following code? `var obj = { x: 1 }; console.log(delete obj.x); console.log(obj.x); var...`?](#183-what-is-the-output-of-the-following-code-var-obj-x-1-consolelogdelete-objx-consolelogobjx-var)

---

## Closures, Scope & Hoisting

### 1. What is the output of the following code? `console.log(foo()); console.log(bar()); function foo() { return "foo";...`?

```javascript
console.log(foo());
console.log(bar());

function foo() { return "foo"; }
var bar = function() { return "bar"; };
```

**Output:**
```

"foo"
TypeError: bar is not a function
```

**Explanation:** `foo` is a function declaration — fully hoisted with its body. `bar` is a variable declaration — hoisted as `undefined`, so calling `bar()` when it's `undefined` throws a TypeError.

[↑ Back to top](#table-of-contents)

### 2. What is the output of the following code? `function outer() { console.log(x); if (false) { var x = 10; } console....`?

```javascript
function outer() {
console.log(x);
if (false) {
var x = 10;
}
console.log(x);
}
outer();
```

**Output:**
```

undefined
undefined
```

**Explanation:** `var x` inside the `if` block (even a never-executed one) is hoisted to the top of `outer()`. The `if (false)` never runs, so `x` is always `undefined`. Hoisting doesn't care about dead code branches.

[↑ Back to top](#table-of-contents)

### 3. What is the output of the following code? `function outer() { var x = 10; var inner = function() { console.log(x)...`?

```javascript
function outer() {
var x = 10;
var inner = function() {
console.log(x);
};
x = 20;
return inner;
}
var fn = outer();
fn();
```

**Output:**
```

20
```

**Explanation:** The closure captures the VARIABLE `x`, not its VALUE at the time the function was created. When `fn()` is called, `x` has been updated to `20`. Closures close over the binding (reference), not the value.

[↑ Back to top](#table-of-contents)

### 4. What is the output of the following code? `var a = 1; (function() { console.log(a); var a = 2; console.log(a); })...`?

```javascript
var a = 1;
(function() {
console.log(a);
var a = 2;
console.log(a);
})();
console.log(a);
```

**Output:**
```

undefined
2
1
```

**Explanation:** Inside the IIFE, `var a` is hoisted to the top of the function scope. The outer `a = 1` is shadowed. First log sees hoisted (undefined) inner `a`. After assignment, second log sees `2`. Outer `a` is unchanged.

[↑ Back to top](#table-of-contents)

### 5. What is the output of the following code? `var a = 1; function a() {} console.log(a); function b() {} var b = 2; ...`?

```javascript
var a = 1;
function a() {}
console.log(a);

function b() {}
var b = 2;
console.log(b);
```

**Output:**
```

1
2
```

**Explanation:** Function declarations are hoisted before `var`. After hoisting: `a` is the function. But then `var a = 1` assigns `1` to `a`. So `console.log(a)` = `1`. Same for `b`: function `b` is hoisted, then `b = 2` overwrites it.

[↑ Back to top](#table-of-contents)

### 6. What is the output of the following code? `var fns = []; for (var i = 0; i < 3; i++) { fns.push((function(j) { re...`?

```javascript
var fns = [];
for (var i = 0; i < 3; i++) {
fns.push((function(j) {
return function() { console.log(j); };
})(i));
}
fns[0]();
fns[1]();
fns[2]();
```

**Output:**
```

0
1
2
```

**Explanation:** IIFE solution to the classic closure bug. Each IIFE immediately captures the current value of `i` as parameter `j`. Each returned function closes over its own `j`.

[↑ Back to top](#table-of-contents)

### 7. What is the output of the following code? `var x = 10; function foo() { return x; var x = 20; } console.log(foo()...`?

```javascript
var x = 10;
function foo() {
return x;
var x = 20;
}
console.log(foo());
```

**Output:**
```

undefined
```

**Explanation:** `var x = 20` inside `foo` is hoisted to the top. The function becomes: `var x; return x; x = 20;`. `x` is returned before assignment, so `undefined`.

[↑ Back to top](#table-of-contents)

### 8. What is the output of the following code? `var x = 1; function test() { console.log(x); var x = 2; console.log(x)...`?

```javascript
var x = 1;
function test() {
console.log(x);
var x = 2;
console.log(x);
}
test();
console.log(x);
```

**Output:**
```

undefined
2
1
```

**Explanation:** Inside `test()`, `var x` is hoisted to the top of the function but not initialized. So the first `console.log(x)` sees the hoisted `var x` (value `undefined`), not the outer `x = 1`. After assignment, `x = 2`. The outer `x` is unchanged.

[↑ Back to top](#table-of-contents)

## `this`, call/apply/bind & Functions

### 9. How would you implement `curry` function from scratch?

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

[↑ Back to top](#table-of-contents)

### 10. Implement: `once` — function that can only be called once.

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

[↑ Back to top](#table-of-contents)

### 11. What is the output of the following code? `(function(x, y) { console.log(x + y); })(3, 4); console.log( (function...`?

```javascript
(function(x, y) {
console.log(x + y);
})(3, 4);

console.log(
(function(a) {
return a * a;
})(5)
);
```

**Output:**
```

7
25
```

**Explanation:** IIFE (Immediately Invoked Function Expression) is called right away. First IIFE logs `3 + 4 = 7`. Second IIFE returns `5 * 5 = 25` which is passed to `console.log`.

[↑ Back to top](#table-of-contents)

### 12. What is the output of the following code? `function curry(fn) { return function curried(...args) { if (args.lengt...`?

```javascript
function curry(fn) {
return function curried(...args) {
if (args.length >= fn.length) return fn(...args);
return (...more) => curried(...args, ...more);
};
}
const add = curry((a, b, c) => a + b + c);
console.log(add(1)(2)(3));
console.log(add(1, 2)(3));
console.log(add(1)(2, 3));
console.log(add(1, 2, 3));
```

**Output:**
```

6
6
6
6
```

**Explanation:** The curry function checks if enough args have been accumulated (`>= fn.length`). All four call styles eventually provide all 3 arguments and call the original function.

[↑ Back to top](#table-of-contents)

### 13. What is the output of the following code? `function greet(greeting, punctuation) { return `${greeting}, ${this.na...`?

```javascript
function greet(greeting, punctuation) {
return `${greeting}, ${this.name}${punctuation}`;
}
const person = { name: 'Alice' };
console.log(greet.call(person, 'Hello', '!'));
console.log(greet.apply(person, ['Hi', '?']));
```

**Output:**
```

Hello, Alice!
Hi, Alice?
```

**Explanation:** `call` sets `this = person` and passes args individually. `apply` sets `this = person` and passes args as an array. Both explicitly bind `this`.

[↑ Back to top](#table-of-contents)

### 14. What is the output of the following code? `var result = (function(a) { return (function(b) { return a + b; })(2);...`?

```javascript
var result = (function(a) {
return (function(b) {
return a + b;
})(2);
})(1);
console.log(result);
```

**Output:**
```

3
```

**Explanation:** Outer IIFE is called with `a = 1`. It returns an inner IIFE called with `b = 2`. The inner function returns `a + b` = `1 + 2` = `3`. The inner closure accesses `a` from the outer scope.

[↑ Back to top](#table-of-contents)

## Prototypes, Classes & OOP

### 15. How to place 5 divs in a row without using flex, margin, or padding? (Hint: display: inline-block)

Using `display: inline-block`:

```html
<style>
.box {
display: inline-block;
width: 100px;
height: 100px;
background: red;
}
</style>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
```

Note: Inline‑block elements respect whitespace between them in HTML, which creates a small gap. To remove gap, set parent `font-size: 0` and reset font‑size on children.

[↑ Back to top](#table-of-contents)

### 16. How would you implement an event emitter?

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

[↑ Back to top](#table-of-contents)

### 17. What is the output of the following code? `class Animal { constructor(name) { this.name = name; this.type = this....`?

```javascript
class Animal {
constructor(name) {
this.name = name;
this.type = this.constructor.name;
}
}
class Dog extends Animal {}
class Cat extends Animal {}

const d = new Dog('Rex');
const c = new Cat('Whiskers');
console.log(d.type);
console.log(c.type);
console.log(d instanceof Animal);
console.log(d.constructor === Dog);
```

**Output:**
```

Dog
Cat
true
true
```

**Explanation:** `this.constructor.name` gives the actual class name, not `Animal`. In the constructor, `this.constructor` refers to the ACTUAL class used with `new`. So Dog instances get `type = 'Dog'`.

[↑ Back to top](#table-of-contents)

### 18. What is the output of the following code? `class Animal { constructor(name) { this.name = name; } speak() { retur...`?

```javascript
class Animal {
constructor(name) {
this.name = name;
}
speak() {
return `${this.name} makes a sound`;
}
}
class Dog extends Animal {
speak() {
return `${super.speak()} — specifically barking`;
}
}
const d = new Dog('Rex');
console.log(d.speak());
console.log(d instanceof Dog);
console.log(d instanceof Animal);
```

**Output:**
```

Rex makes a sound — specifically barking
true
true
```

**Explanation:** `super.speak()` calls `Animal.prototype.speak` with `this = d`. `d instanceof Animal` is `true` because `Animal.prototype` is in `d`'s prototype chain via inheritance.

[↑ Back to top](#table-of-contents)

### 19. What is the output of the following code? `class Base { constructor() { console.log(new.target.name); } } class C...`?

```javascript
class Base {
constructor() {
console.log(new.target.name);
}
}
class Child extends Base {
constructor() {
super();
}
}
new Base();
new Child();
```

**Output:**
```

Base
Child
```

**Explanation:** `new.target` inside a constructor refers to the function/class that was called with `new`. Even when `super()` calls Base's constructor, `new.target` is still `Child` — it tracks the originally-invoked constructor.

[↑ Back to top](#table-of-contents)

### 20. What is the output of the following code? `class Base { static create() { return new this(); } describe() { retur...`?

```javascript
class Base {
static create() {
return new this();
}
describe() {
return 'Base';
}
}
class Child extends Base {
describe() {
return 'Child';
}
}
const b = Base.create();
const c = Child.create();
console.log(b.describe());
console.log(c.describe());
```

**Output:**
```

Base
Child
```

**Explanation:** Static methods are inherited. `Child.create()` calls `new this()` where `this` is `Child` (the class itself in a static context), so it creates a `Child` instance. `c.describe()` calls `Child.prototype.describe`.

[↑ Back to top](#table-of-contents)

### 21. What is the output of the following code? `class Button { constructor(label) { this.label = label; } click() { co...`?

```javascript
class Button {
constructor(label) {
this.label = label;
}
click() {
console.log(`${this.label} clicked`);
}
}
const btn = new Button('Submit');
btn.click();

const handler = btn.click;
handler(); // What happens?
```

**Output:**
```

Submit clicked
TypeError: Cannot read properties of undefined (reading 'label')
```

**Explanation:** `btn.click()` has implicit binding — `this = btn`. When `handler = btn.click` extracts the method and calls it standalone, `this` is `undefined` (class bodies are in strict mode). Fix: `const handler = btn.click.bind(btn)` or use arrow class field.

[↑ Back to top](#table-of-contents)

### 22. What is the output of the following code? `class Counter { count = 0; increment = () => { this.count++; console.l...`?

```javascript
class Counter {
count = 0;
increment = () => {
this.count++;
console.log(this.count);
}
}
const c = new Counter();
const inc = c.increment;
inc();
inc();
```

**Output:**
```

1
2
```

**Explanation:** Arrow class fields capture `this` at creation time (in the constructor). Each instance gets its own arrow function with `this` permanently bound to the instance. Extracting `inc = c.increment` doesn't break `this`.

[↑ Back to top](#table-of-contents)

### 23. What is the output of the following code? `class Counter { static count = 0; constructor() { Counter.count++; thi...`?

```javascript
class Counter {
static count = 0;
constructor() {
Counter.count++;
this.id = Counter.count;
}
static getCount() {
return Counter.count;
}
}
const a = new Counter();
const b = new Counter();
const c = new Counter();
console.log(Counter.getCount());
console.log(a.id, b.id, c.id);
console.log(a.count);
```

**Output:**
```

3
1 2 3
undefined
```

**Explanation:** `static count` belongs to the `Counter` class, not instances. Instances don't have a `count` property — `a.count` is `undefined`. Each instance gets a unique `id` from the shared counter.

[↑ Back to top](#table-of-contents)

### 24. What is the output of the following code? `class EventEmitter { #handlers = {}; on(event, fn) { (this.#handlers[e...`?

```javascript
class EventEmitter {
#handlers = {};
on(event, fn) { (this.#handlers[event] ??= []).push(fn); return this; }
emit(event, data) { this.#handlers[event]?.forEach(fn => fn(data)); return this; }
}

const emitter = new EventEmitter();

emitter
.on('data', x => console.log('handler 1:', x))
.on('data', x => console.log('handler 2:', x * 2))
.emit('data', 5)
.emit('data', 10);
```

**Output:**
```

handler 1: 5
handler 2: 10
handler 1: 10
handler 2: 20
```

**Explanation:** Method chaining works because `on` and `emit` return `this`. Multiple handlers for the same event all fire. Second `emit(10)` fires all `'data'` handlers again with value `10`.

[↑ Back to top](#table-of-contents)

### 25. What is the output of the following code? `class MyArray extends Array { sum() { return this.reduce((a, b) => a +...`?

```javascript
class MyArray extends Array {
sum() {
return this.reduce((a, b) => a + b, 0);
}
}
const arr = new MyArray(1, 2, 3, 4, 5);
console.log(arr.sum());
console.log(arr instanceof Array);
console.log(arr instanceof MyArray);
const filtered = arr.filter(x => x > 2);
console.log(filtered instanceof MyArray);
```

**Output:**
```

15
true
true
true
```

**Explanation:** Classes can extend built-ins. `MyArray` inherits all Array methods. `filter` on a subclass returns an instance of the subclass (not plain Array) — this is the `Symbol.species` behavior in modern JS.

[↑ Back to top](#table-of-contents)

### 26. What is the output of the following code? `class MyClass { #secret = 42; getSecret() { return this.#secret; } } c...`?

```javascript
class MyClass {
#secret = 42;
getSecret() { return this.#secret; }
}
const obj = new MyClass();
console.log(obj.getSecret());
console.log(obj.#secret);
console.log('#secret' in obj);
```

**Output:**
```

42
SyntaxError: Private field '#secret' must be declared in an enclosing class
false
```

**Explanation:** Private fields (`#`) are enforced at the syntax level — accessing from outside the class is a SyntaxError, not just `undefined`. The `in` operator can check private fields but only inside the class.

[↑ Back to top](#table-of-contents)

### 27. What is the output of the following code? `class MyClass { name = 'class'; regularMethod() { return this.name; } ...`?

```javascript
class MyClass {
name = 'class';

regularMethod() {
return this.name;
}
arrowMethod = () => {
return this.name;
}
}
const obj = new MyClass();
const reg = obj.regularMethod;
const arr = obj.arrowMethod;

console.log(obj.regularMethod());
console.log(obj.arrowMethod());
console.log(reg());
console.log(arr());
```

**Output:**
```

class
class
undefined (or TypeError in strict mode)
class
```

**Explanation:** Regular methods use dynamic `this` — extracting and calling standalone loses the `this` binding. Arrow class fields capture `this` at construction time — safe to extract and pass as callbacks.

[↑ Back to top](#table-of-contents)

### 28. What is the output of the following code? `const obj = new MyClass(); class MyClass { greet() { return "hello"; }...`?

```javascript
const obj = new MyClass();
class MyClass {
greet() { return "hello"; }
}
```

**Output:**
```

ReferenceError: Cannot access 'MyClass' before initialization
```

**Explanation:** Classes are hoisted but remain in the TDZ until the declaration is evaluated. They are NOT hoisted the way function declarations are. Always define classes before using them.

[↑ Back to top](#table-of-contents)

### 29. What is the output of the following code? `const parent = { a: 1 }; const child = Object.create(parent); child.b ...`?

```javascript
const parent = { a: 1 };
const child = Object.create(parent);
child.b = 2;

console.log(child.a);
console.log(child.b);
console.log(child.hasOwnProperty('a'));
console.log(child.hasOwnProperty('b'));

for (let key in child) {
console.log(key);
}
for (let key in child) {
if (child.hasOwnProperty(key)) console.log('own:', key);
}
```

**Output:**
```

1
2
false
true
b
a
own: b
```

**Explanation:** `child.a` is found via prototype chain. `b` is own. `for...in` iterates ALL enumerable properties including inherited ones (`a` and `b`). Filter with `hasOwnProperty` to get only own properties.

[↑ Back to top](#table-of-contents)

### 30. What is the output of the following code? `function Animal(name) { this.name = name; } Animal.prototype.speak = f...`?

```javascript
function Animal(name) {
this.name = name;
}
Animal.prototype.speak = function() {
return `${this.name} speaks`;
};

const dog = new Animal('Rex');
console.log(dog.speak());
console.log(dog.hasOwnProperty('name'));
console.log(dog.hasOwnProperty('speak'));
console.log('speak' in dog);
```

**Output:**
```

Rex speaks
true
false
true
```

**Explanation:** `name` is an own property set in the constructor. `speak` is on `Animal.prototype`, not on `dog` directly. `in` operator checks the entire prototype chain, so `'speak' in dog` is `true`.

[↑ Back to top](#table-of-contents)

### 31. What is the output of the following code? `function Foo() {} const f = new Foo(); Foo.prototype = {}; const g = n...`?

```javascript
function Foo() {}
const f = new Foo();
Foo.prototype = {};
const g = new Foo();

console.log(f instanceof Foo);
console.log(g instanceof Foo);
```

**Output:**
```

false
true
```

**Explanation:** `instanceof` checks if `Foo.prototype` (current value) is in the prototype chain. `f` was created with the OLD `Foo.prototype`. After reassignment, `f`'s chain no longer contains the new `Foo.prototype`. `g` was created with the NEW `Foo.prototype`, so `g instanceof Foo` is `true`.

[↑ Back to top](#table-of-contents)

### 32. What is the output of the following code? `function Person(name) { this.name = name; } Person.prototype.greet = f...`?

```javascript
function Person(name) {
this.name = name;
}
Person.prototype.greet = function() {
return `Hi, I'm ${this.name}`;
};

const alice = new Person('Alice');
const bob = Object.create(alice);
bob.name = 'Bob';

console.log(alice.greet());
console.log(bob.greet());
console.log(bob.__proto__ === alice);
console.log(bob instanceof Person);
```

**Output:**
```

Hi, I'm Alice
Hi, I'm Bob
true
true
```

**Explanation:** `bob`'s prototype is `alice` (a Person instance). `bob.greet()` finds `greet` via chain: `bob` → `alice` → `Person.prototype`. `bob instanceof Person` is `true` because `Person.prototype` is in the chain. `bob.name` shadows `alice.name`.

[↑ Back to top](#table-of-contents)

### 33. What is the output of the following code? `function Vehicle() {} Vehicle.prototype.type = 'vehicle'; function Car...`?

```javascript
function Vehicle() {}
Vehicle.prototype.type = 'vehicle';

function Car() {}
Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.type = 'car';

const v = new Vehicle();
const c = new Car();

console.log(v.type);
console.log(c.type);
console.log(Object.getPrototypeOf(c) === Car.prototype);
console.log(Object.getPrototypeOf(Car.prototype) === Vehicle.prototype);
```

**Output:**
```

vehicle
car
true
true
```

**Explanation:** `Car.prototype.type = 'car'` shadows `Vehicle.prototype.type`. The prototype chain for `c` is: `c` → `Car.prototype` → `Vehicle.prototype` → `Object.prototype`.

[↑ Back to top](#table-of-contents)

### 34. Write a polyfill for `call`, `apply`, and `bind`.

**`call` polyfill** (already provided earlier, but here is a clean version):

```javascript
Function.prototype.myCall = function(context, ...args) {
context = context ?? globalThis;
const fnSymbol = Symbol();
context[fnSymbol] = this;
const result = context[fnSymbol](...args);
delete context[fnSymbol];
return result;
};
```

**`apply` polyfill**:

```javascript
Function.prototype.myApply = function(context, argsArray) {
context = context ?? globalThis;
const fnSymbol = Symbol();
context[fnSymbol] = this;
const result = context[fnSymbol](...argsArray);
delete context[fnSymbol];
return result;
};
```

**`bind` polyfill**:

```javascript
Function.prototype.myBind = function(context, ...boundArgs) {
const fn = this;
return function(...args) {
return fn.apply(context, boundArgs.concat(args));
};
};

```

[↑ Back to top](#table-of-contents)

## ES6+ Features (Destructuring, Spread/Rest, Modules)

### 35. Implement: `compose` vs `pipe` — output prediction.

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

[↑ Back to top](#table-of-contents)

### 36. Implement: Check if a string is a palindrome (ignoring spaces/punctuation).

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

[↑ Back to top](#table-of-contents)

### 37. Implement: Deep merge two objects.

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

[↑ Back to top](#table-of-contents)

### 38. Implement: Given a string, find the first non-repeating character.

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

[↑ Back to top](#table-of-contents)

### 39. What is the output of the following code? `// Chained optional chaining + nullish coalescing: const user = { prof...`?

```javascript
// Chained optional chaining + nullish coalescing:
const user = {
profile: null,
settings: {
theme: undefined,
notifications: {
email: true
}
}
};

console.log(user?.profile?.avatar ?? 'default-avatar');
console.log(user?.settings?.theme ?? 'light');
console.log(user?.settings?.notifications?.email ?? false);
console.log(user?.missing?.deep?.property ?? 'fallback');
console.log(user?.profile?.name ?? user?.settings?.theme ?? 'unknown');
```

**Output:**
```

default-avatar   // profile is null, short-circuits to undefined, ?? gives default
light            // theme is undefined, ?? gives 'light'
true             // email is true, ?? not needed
fallback         // missing chain → undefined → ?? gives fallback
unknown          // profile is null (undefined), theme is undefined → unknown
```

[↑ Back to top](#table-of-contents)

### 40. What is the output of the following code? `// Map iteration order vs Object: const map = new Map(); map.set('b', ...`?

```javascript
// Map iteration order vs Object:
const map = new Map();
map.set('b', 2);
map.set('a', 1);
map.set('c', 3);

const obj = { b: 2, a: 1, c: 3 };

console.log([...map.keys()]);
console.log(Object.keys(obj));

const map2 = new Map();
map2.set(3, 'three');
map2.set(1, 'one');
map2.set(2, 'two');
console.log([...map2.keys()]);

const obj2 = { 3: 'three', 1: 'one', 2: 'two' };
console.log(Object.keys(obj2));
```

**Output:**
```

['b', 'a', 'c']    // Map: insertion order always
['b', 'a', 'c']    // Object string keys: insertion order (modern JS)
[3, 1, 2]          // Map: insertion order for number keys too
['1', '2', '3']    // Object: numeric keys sorted numerically first!
```

**Explanation:** `Map` ALWAYS preserves insertion order for all key types. Objects have a special rule: integer-like string keys (`'1'`, `'2'`, `'3'`) are sorted numerically before other string keys.

[↑ Back to top](#table-of-contents)

### 41. What is the output of the following code? `// Tricky destructuring: const { a: { b } } = { a: { b: 42 } }; consol...`?

```javascript
// Tricky destructuring:
const { a: { b } } = { a: { b: 42 } };
console.log(b);
console.log(typeof a); // Is 'a' defined?

const [, second, , fourth = 'default'] = [1, 2, 3];
console.log(second, fourth);

// Swap without temp variable:
let x = 1, y = 2;
[x, y] = [y, x];
console.log(x, y);
```

**Output:**
```

42
undefined   // 'a' is NOT declared — nested destructuring renames, doesn't create 'a'
2 default   // second=2, fourth is undefined → uses default
2 1         // x and y swapped
```

[↑ Back to top](#table-of-contents)

### 42. What is the output of the following code? `// Tricky: what does this print? const arr = [1, 2, 3]; // forEach wit...`?

```javascript
// Tricky: what does this print?
const arr = [1, 2, 3];

// forEach with async — does it wait?
async function processAll() {
console.log('start');
arr.forEach(async (n) => {
await new Promise(r => setTimeout(r, n * 100));
console.log(n);
});
console.log('end'); // Prints before forEach items?
}
processAll();
```

**Output:**
```

start
end
1
2
3
```

**Explanation:** `forEach` does NOT await async callbacks. It fires all three async functions and immediately moves to `console.log('end')`. Each async callback runs independently. Use `for...of` with `await` for sequential async iteration, or `Promise.all` for parallel with await.

[↑ Back to top](#table-of-contents)

### 43. What is the output of the following code? `console.log(a); let a = 5;...`?

```javascript
console.log(a);
let a = 5;
```

**Output:**
```

ReferenceError: Cannot access 'a' before initialization
```

**Explanation:** `let` is hoisted but NOT initialized. Accessing it before its declaration line is in the Temporal Dead Zone (TDZ) — a `ReferenceError` is thrown. Unlike `var` which would give `undefined`.

[↑ Back to top](#table-of-contents)

### 44. What is the output of the following code? `console.log(true ? 'yes' : 'no'); console.log(false ? 'yes' : 'no'); /...`?

```javascript
console.log(true ? 'yes' : 'no');
console.log(false ? 'yes' : 'no');
// Nested ternary:
const score = 75;
const grade = score >= 90 ? 'A' : score >= 80 ? 'B' : score >= 70 ? 'C' : 'F';
console.log(grade);
// Tricky associativity:
console.log(true ? true : false ? 'yes' : 'no');
```

**Output:**
```

yes
no
C
true
```

**Explanation:** Ternary is right-associative. `true ? true : (false ? 'yes' : 'no')` — the first condition is `true`, so `true` is returned immediately. The right side is never evaluated.

[↑ Back to top](#table-of-contents)

### 45. What is the output of the following code? `const [a, , b, ...rest] = [1, 2, 3, 4, 5]; console.log(a, b, rest); co...`?

```javascript
const [a, , b, ...rest] = [1, 2, 3, 4, 5];
console.log(a, b, rest);

const { x, y, ...remaining } = { x: 1, y: 2, z: 3, w: 4 };
console.log(x, y, remaining);
```

**Output:**
```

1 3 [4, 5]
1 2 { z: 3, w: 4 }
```

**Explanation:** Array destructuring skips elements with empty slots (`,`). Rest collects remaining elements/properties into a new array/object.

[↑ Back to top](#table-of-contents)

### 46. What is the output of the following code? `const a = [1, 2, 3]; const b = [1, 2, 3]; const c = a; console.log(a =...`?

```javascript
const a = [1, 2, 3];
const b = [1, 2, 3];
const c = a;

console.log(a == b);
console.log(a === b);
console.log(a == c);
console.log(a === c);

console.log(JSON.stringify(a) === JSON.stringify(b));
```

**Output:**
```

false   // Different references
false
true    // Same reference (c = a)
true
true    // String comparison of serialized arrays
```

**Explanation:** Arrays (objects) are compared by REFERENCE, not value. `a == b` compares object references — `a` and `b` are different arrays. `a === c` is `true` because `c` points to the same array as `a`. Use `JSON.stringify` or deep-equal for value comparison.

[↑ Back to top](#table-of-contents)

### 47. What is the output of the following code? `const a = { toString() { return 'A'; } }; const b = { toString() { ret...`?

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

[↑ Back to top](#table-of-contents)

### 48. What is the output of the following code? `const a = { val: 1 }; const b = a; b.val = 2; console.log(a.val); cons...`?

```javascript
const a = { val: 1 };
const b = a;
b.val = 2;
console.log(a.val);

const c = { val: 1 };
const d = { ...c };
d.val = 3;
console.log(c.val);
```

**Output:**
```

2
1
```

**Explanation:** `b = a` copies the reference. Both point to the same object — mutating via `b` affects `a`. Spread `{...c}` creates a shallow copy — a new object. Mutating `d` doesn't affect `c`.

[↑ Back to top](#table-of-contents)

### 49. What is the output of the following code? `const arr = [1, 2, 3, 4, 5]; delete arr[2]; console.log(arr); console....`?

```javascript
const arr = [1, 2, 3, 4, 5];
delete arr[2];
console.log(arr);
console.log(arr.length);
console.log(arr[2]);
```

**Output:**
```

[1, 2, empty, 4, 5]
5
undefined
```

**Explanation:** `delete` on an array element removes the value but leaves a "hole" — the index still exists, `length` is unchanged. `arr[2]` returns `undefined`. Use `splice` to actually remove an element and update length.

[↑ Back to top](#table-of-contents)

### 50. What is the output of the following code? `const arr = [1, 2, 3]; arr.extra = 'surprise'; for (let val of arr) { ...`?

```javascript
const arr = [1, 2, 3];
arr.extra = 'surprise';

for (let val of arr) {
console.log(val);
}
for (let key in arr) {
console.log(key);
}
```

**Output:**
```

// for...of:
1
2
3
// for...in:
0
1
2
extra
```

**Explanation:** `for...of` iterates array VALUES (uses the iterator). `for...in` iterates all enumerable KEYS including non-index properties like `'extra'`. Never use `for...in` on arrays.

[↑ Back to top](#table-of-contents)

### 51. What is the output of the following code? `const arr = [1, 2, 3]; arr[10] = 11; console.log(arr.length); console....`?

```javascript
const arr = [1, 2, 3];
arr[10] = 11;
console.log(arr.length);
console.log(arr[5]);
arr.forEach((val, i) => console.log(i, val));
```

**Output:**
```

11
undefined
0 1
1 2
2 3
10 11
```

**Explanation:** Setting index 10 creates a sparse array with `length = 11`. Indices 3–9 are "holes" (empty slots), returning `undefined` when accessed. `forEach` SKIPS holes — only logs indices 0, 1, 2, and 10.

[↑ Back to top](#table-of-contents)

### 52. What is the output of the following code? `const cache = new WeakMap(); function process(obj) { if (cache.has(obj...`?

```javascript
const cache = new WeakMap();

function process(obj) {
if (cache.has(obj)) {
console.log('cache hit');
return cache.get(obj);
}
const result = JSON.stringify(obj);
cache.set(obj, result);
console.log('computed');
return result;
}

let obj = { name: 'Alice' };
process(obj); // computed
process(obj); // cache hit
obj = null;   // obj is eligible for GC; WeakMap entry disappears automatically
```

**Output:**
```

computed
cache hit
```

**Explanation:** `WeakMap` holds keys weakly — when `obj` is nulled and no other references exist, the key and its value are garbage collected without any manual cleanup. Perfect for caching without memory leaks.

[↑ Back to top](#table-of-contents)

### 53. What is the output of the following code? `const factorial = function fact(n) { if (n <= 1) return 1; return n * ...`?

```javascript
const factorial = function fact(n) {
if (n <= 1) return 1;
return n * fact(n - 1);
};
console.log(factorial(5));
console.log(typeof fact);
```

**Output:**
```

120
undefined
```

**Explanation:** Named function expressions allow the function to reference itself by name internally (`fact`). But the name `fact` is only available INSIDE the function — it's not visible in the outer scope. `typeof fact` is `undefined` (or throws ReferenceError in strict).

[↑ Back to top](#table-of-contents)

### 54. What is the output of the following code? `const gen = (function*() { let id = 0; while (true) { yield ++id; } })...`?

```javascript
const gen = (function*() {
let id = 0;
while (true) {
yield ++id;
}
})();

console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
```

**Output:**
```

1
2
3
```

**Explanation:** An infinite generator — yields an incrementing ID each time `.next()` is called. Because generators are lazy, this doesn't cause an infinite loop. It only runs when `.next()` is called.

[↑ Back to top](#table-of-contents)

### 55. What is the output of the following code? `const handler = { get(target, prop) { return prop in target ? target[p...`?

```javascript
const handler = {
get(target, prop) {
return prop in target ? target[prop] : `Property "${prop}" not found`;
}
};
const proxy = new Proxy({ name: 'Alice', age: 30 }, handler);
console.log(proxy.name);
console.log(proxy.age);
console.log(proxy.email);
```

**Output:**
```

Alice
30
Property "email" not found
```

**Explanation:** The Proxy `get` trap intercepts all property accesses. Instead of returning `undefined` for missing properties, it returns a custom message.

[↑ Back to top](#table-of-contents)

### 56. What is the output of the following code? `const handler = { get(target, prop, receiver) { console.log(`get: ${pr...`?

```javascript
const handler = {
get(target, prop, receiver) {
console.log(`get: ${prop}`);
return Reflect.get(target, prop, receiver);
},
set(target, prop, value, receiver) {
console.log(`set: ${prop} = ${value}`);
return Reflect.set(target, prop, value, receiver);
}
};
const proxy = new Proxy({}, handler);
proxy.name = 'Alice';
console.log(proxy.name);
```

**Output:**
```

set: name = Alice
get: name
Alice
```

**Explanation:** The Proxy intercepts both `set` and `get` operations. `Reflect.set`/`Reflect.get` perform the default behavior. This pattern is used for logging, validation, and reactivity systems (Vue 3).

[↑ Back to top](#table-of-contents)

### 57. What is the output of the following code? `const key = 'name'; const obj = { [key]: 'Alice', ['age']: 30, [1 + 2]...`?

```javascript
const key = 'name';
const obj = {
[key]: 'Alice',
['age']: 30,
[1 + 2]: 'three',
};
console.log(obj.name);
console.log(obj.age);
console.log(obj[3]);
console.log(Object.keys(obj));
```

**Output:**
```

Alice
30
three
['name', 'age', '3']
```

**Explanation:** Computed property names evaluate the expression in `[]`. `[1 + 2]` = `[3]` = key `'3'` (numbers are coerced to strings as object keys). `Object.keys` shows all keys as strings.

[↑ Back to top](#table-of-contents)

### 58. What is the output of the following code? `const map = new Map(); map.set('1', 'string key'); map.set(1, 'number ...`?

```javascript
const map = new Map();
map.set('1', 'string key');
map.set(1, 'number key');
map.set(true, 'bool key');

console.log(map.get('1'));
console.log(map.get(1));
console.log(map.size);

const obj = {};
obj['1'] = 'string key';
obj[1] = 'number key';
console.log(obj['1']);
console.log(Object.keys(obj).length);
```

**Output:**
```

string key
number key
3
number key   // obj[1] overwrites obj['1'] — both coerce to same key '1'
1
```

**Explanation:** `Map` keeps keys strictly typed — `'1'` and `1` are different keys. Plain objects coerce all keys to strings — `obj[1]` becomes `obj['1']`, overwriting the previous value.

[↑ Back to top](#table-of-contents)

### 59. What is the output of the following code? `const obj = Object.freeze({ a: 1, nested: { b: 2 } }); obj.a = 99; obj...`?

```javascript
const obj = Object.freeze({ a: 1, nested: { b: 2 } });
obj.a = 99;
obj.c = 3;
obj.nested.b = 99;
console.log(obj.a);
console.log(obj.c);
console.log(obj.nested.b);
```

**Output:**
```

1
undefined
99
```

**Explanation:** `Object.freeze` is SHALLOW. Top-level properties cannot be added or modified. But `nested` is an object reference — freeze doesn't deep-freeze it. `obj.nested.b = 99` works because `nested` itself wasn't frozen.

[↑ Back to top](#table-of-contents)

### 60. What is the output of the following code? `const obj = { a: 1, b: function() { return this.a; }, c: () => this?.a...`?

```javascript
const obj = {
a: 1,
b: function() { return this.a; },
c: () => this?.a,
};
console.log(obj.b());
console.log(obj.c());
const { b, c } = obj;
console.log(b.call({ a: 99 }));
console.log(c.call({ a: 99 }));
```

**Output:**
```

1         // obj.b() — this is obj
undefined // obj.c() — arrow, this is global (no .a)
99        // b.call({a:99}) — this overridden
undefined // c.call({a:99}) — arrows ignore call/apply/bind
```

[↑ Back to top](#table-of-contents)

### 61. What is the output of the following code? `const obj = { a: { b: { c: 42 } } }; console.log(obj?.a?.b?.c); consol...`?

```javascript
const obj = {
a: {
b: {
c: 42
}
}
};
console.log(obj?.a?.b?.c);
console.log(obj?.x?.y?.z);
console.log(obj?.a?.b?.c?.toFixed(2));

const arr = [1, 2, 3];
console.log(arr?.[0]);
console.log(arr?.[10]);

const fn = null;
console.log(fn?.());
```

**Output:**
```

42
undefined
'42.00'
1
undefined
undefined
```

**Explanation:** `?.` short-circuits to `undefined` if any part of the chain is `null`/`undefined`. Does not throw. Works on property access, array indexing (`?.[index]`), and function calls (`?.()`).

[↑ Back to top](#table-of-contents)

### 62. What is the output of the following code? `const obj = { data: [1, 2, 3], double() { return this.data.map(functio...`?

```javascript
const obj = {
data: [1, 2, 3],
double() {
return this.data.map(function(x) {
return x * this.factor; // What is this here?
});
},
doubleArrow() {
return this.data.map((x) => x * this.factor);
},
factor: 2
};
console.log(obj.double());
console.log(obj.doubleArrow());
```

**Output:**
```

[NaN, NaN, NaN]   // this.factor is undefined (this = global in callback)
[2, 4, 6]         // arrow captures this = obj
```

**Explanation:** Regular function in `map` callback loses `obj` context. `this` is global/undefined. `this.factor` is `undefined`. `x * undefined = NaN`. Arrow function lexically inherits `this` from `doubleArrow`, which is `obj`.

[↑ Back to top](#table-of-contents)

### 63. What is the output of the following code? `const obj = { name: 'Alice', greet: () => { console.log(this.name); } ...`?

```javascript
const obj = {
name: 'Alice',
greet: () => {
console.log(this.name);
}
};
obj.greet();
```

**Output:**
```

undefined
```

**Explanation:** Arrow functions do NOT have their own `this`. They capture `this` from the enclosing scope at definition time. `obj` is defined in the global scope, so `this` in the arrow function refers to the global object (or `undefined` in strict mode), which doesn't have a `name` property.

[↑ Back to top](#table-of-contents)

### 64. What is the output of the following code? `const obj = { name: 'Alice', greet: function() { console.log(this.name...`?

```javascript
const obj = {
name: 'Alice',
greet: function() {
console.log(this.name);
}
};
obj.greet();
const greet = obj.greet;
greet();
```

**Output:**
```

Alice
undefined (or TypeError in strict mode)
```

**Explanation:** `obj.greet()` — implicit binding, `this = obj`, `this.name = 'Alice'`. `const greet = obj.greet` — method is extracted. `greet()` — default binding, `this = window` (or `undefined` in strict mode), no `name` property.

[↑ Back to top](#table-of-contents)

### 65. What is the output of the following code? `const obj = { x: 1, getX: function() { return function() { return this...`?

```javascript
const obj = {
x: 1,
getX: function() {
return function() {
return this.x;
};
}
};
console.log(obj.getX()());

const obj2 = {
x: 1,
getX: function() {
return () => this.x;
}
};
console.log(obj2.getX()());
```

**Output:**
```

undefined
1
```

**Explanation:** `obj.getX()()` — `getX()` returns a regular function. When called standalone (not as method), `this` is global/undefined. `undefined.x` → `undefined`. Arrow function in `obj2.getX()` captures `this` lexically from `getX`'s context (the `obj2` method call), so `this.x = 1`.

[↑ Back to top](#table-of-contents)

### 66. What is the output of the following code? `const obj = {}; obj[true] = 'bool'; obj[1] = 'number'; obj['1'] = 'str...`?

```javascript
const obj = {};
obj[true] = 'bool';
obj[1] = 'number';
obj['1'] = 'string';
console.log(Object.keys(obj));
console.log(obj[true]);
console.log(obj[1]);
console.log(obj['1']);
```

**Output:**
```

['1']
string
string
string
```

**Explanation:** Object keys are always strings (or Symbols). `true` → `'true'`? No! `true` coerces to `'true'`... wait. Actually: `true` → `'true'`, `1` → `'1'`, `'1'` → `'1'`. So `1` and `'1'` collide, but `true` → `'true'` is a different key. Let me re-check:

**Corrected Output:**
```

['true', '1']
string    // obj[true] = obj['true'] = 'bool'... but wait
```

Actually `obj[true]` → `obj['true']` = `'bool'`. `obj[1]` = `obj['1']` = `'string'` (overwritten by `obj['1'] = 'string'`).

**Actual Correct Output:**
```

['true', '1']
bool
string
string
```

**Explanation:** `true` coerces to string `'true'` as object key. `1` and `'1'` both become key `'1'` — the last assignment wins (`'string'`). Always be explicit with key types; use `Map` when you need typed keys.

[↑ Back to top](#table-of-contents)

### 67. What is the output of the following code? `const original = { a: 1, b: { c: 2 } }; // Attempt 1: JSON roundtrip c...`?

```javascript
const original = { a: 1, b: { c: 2 } };

// Attempt 1: JSON roundtrip
const clone1 = JSON.parse(JSON.stringify(original));
clone1.b.c = 99;
console.log(original.b.c); // ?

// Attempt 2: structuredClone
const clone2 = structuredClone(original);
clone2.b.c = 88;
console.log(original.b.c); // ?

// Attempt 3: spread
const clone3 = { ...original };
clone3.b.c = 77;
console.log(original.b.c); // ?
```

**Output:**
```

2    // JSON roundtrip — true deep clone, b.c unchanged
2    // structuredClone — true deep clone, b.c unchanged
77   // spread — shallow clone, nested b is still shared reference
```

**Explanation:** Only DEEP clone methods protect nested objects. Spread only copies the top level. Both `JSON.parse(JSON.stringify())` and `structuredClone` produce true deep copies. Use `structuredClone` — it handles more types and circular references.

[↑ Back to top](#table-of-contents)

### 68. What is the output of the following code? `const original = { a: 1, nested: { b: 2 } }; const copy = { ...origina...`?

```javascript
const original = { a: 1, nested: { b: 2 } };
const copy = { ...original };
copy.a = 99;
copy.nested.b = 99;
console.log(original.a);
console.log(original.nested.b);
```

**Output:**
```

1
99
```

**Explanation:** Spread creates a SHALLOW copy. Top-level `a` is a primitive — changing `copy.a` doesn't affect `original.a`. But `nested` is an object — both `original.nested` and `copy.nested` point to the SAME object. Mutating `copy.nested.b` affects the original.

[↑ Back to top](#table-of-contents)

### 69. What is the output of the following code? `const person = { firstName: 'John', lastName: 'Doe', get fullName() { ...`?

```javascript
const person = {
firstName: 'John',
lastName: 'Doe',
get fullName() {
return `${this.firstName} ${this.lastName}`;
},
set fullName(name) {
[this.firstName, this.lastName] = name.split(' ');
}
};
console.log(person.fullName);
person.fullName = 'Jane Smith';
console.log(person.firstName);
console.log(person.lastName);
```

**Output:**
```

John Doe
Jane
Smith
```

**Explanation:** Getters/setters look like properties but run functions. Getting `fullName` computes from `firstName` and `lastName`. Setting it splits the string and assigns back. This is encapsulation via computed properties.

[↑ Back to top](#table-of-contents)

### 70. What is the output of the following code? `const proto = { greet() { return `Hello, ${this.name}`; } }; const obj...`?

```javascript
const proto = {
greet() { return `Hello, ${this.name}`; }
};
const obj = Object.create(proto);
obj.name = 'World';
console.log(obj.greet());
console.log(Object.getPrototypeOf(obj) === proto);
console.log(obj.hasOwnProperty('greet'));
console.log(obj.hasOwnProperty('name'));
```

**Output:**
```

Hello, World
true
false
true
```

**Explanation:** `Object.create(proto)` sets `proto` as `obj`'s prototype. `greet` is found via prototype chain. `name` is an own property.

[↑ Back to top](#table-of-contents)

### 71. What is the output of the following code? `const result = (1, 2, 3); console.log(result); for (let i = 0, j = 10;...`?

```javascript
const result = (1, 2, 3);
console.log(result);

for (let i = 0, j = 10; i < 3; i++, j--) {
console.log(i, j);
}
```

**Output:**
```

3
0 10
1 9
2 8
```

**Explanation:** The comma operator evaluates each operand left-to-right and returns the value of the LAST one. `(1, 2, 3)` = `3`. In `for` loops, comma separates multiple initializers and updaters.

[↑ Back to top](#table-of-contents)

### 72. What is the output of the following code? `const sym1 = Symbol('key'); const sym2 = Symbol('key'); console.log(sy...`?

```javascript
const sym1 = Symbol('key');
const sym2 = Symbol('key');
console.log(sym1 === sym2);
console.log(sym1.toString());
console.log(typeof sym1);

const obj = {};
obj[sym1] = 'symbol value';
console.log(obj[sym1]);
console.log(obj[sym2]);
console.log(Object.keys(obj));
```

**Output:**
```

false
Symbol(key)
symbol
symbol value
undefined
[]
```

**Explanation:** Every `Symbol()` creates a UNIQUE value. `sym1 !== sym2` even with same description. Symbol keys are NOT included in `Object.keys()`, `Object.values()`, or `for...in`. Use `Object.getOwnPropertySymbols()` to access them.

[↑ Back to top](#table-of-contents)

### 73. What is the output of the following code? `const { a: x = 10, b: y = 20, c: z = 30 } = { a: 1, b: undefined }; co...`?

```javascript
const { a: x = 10, b: y = 20, c: z = 30 } = { a: 1, b: undefined };
console.log(x, y, z);

const [p = 5, q = 6, r = 7] = [1, null, undefined];
console.log(p, q, r);
```

**Output:**
```

1 20 30
1 null 7
```

**Explanation:** Object destructuring with rename (`a: x`) and default. Default only applies if value is `undefined`, NOT `null`. `b: undefined` triggers default → `y = 20`. `c` is absent → `z = 30`. Array: `null` is NOT `undefined`, so `q = null`. `undefined` triggers default → `r = 7`.

[↑ Back to top](#table-of-contents)

### 74. What is the output of the following code? `function createCounter() { let count = 0; return { increment() { count...`?

```javascript
function createCounter() {
let count = 0;
return {
increment() { count++; },
decrement() { count--; },
getCount() { return count; }
};
}
const counter = createCounter();
counter.increment();
counter.increment();
counter.increment();
counter.decrement();
console.log(counter.getCount());
```

**Output:**
```

2
```

**Explanation:** All three methods share the same closure over `count`. Each `increment` adds 1, each `decrement` subtracts 1. `3 - 1 = 2`. This is the module pattern using closures for private state.

[↑ Back to top](#table-of-contents)

### 75. What is the output of the following code? `function foo() { return this.x; } const bound1 = foo.bind({ x: 1 }); c...`?

```javascript
function foo() {
return this.x;
}
const bound1 = foo.bind({ x: 1 });
const bound2 = bound1.bind({ x: 2 });
console.log(bound1());
console.log(bound2());
```

**Output:**
```

1
1
```

**Explanation:** Once a function is bound with `bind`, subsequent `bind` calls cannot change `this`. `bound2` tries to rebind to `{x:2}` but the original binding to `{x:1}` persists. Only the FIRST `bind` wins.

[↑ Back to top](#table-of-contents)

### 76. What is the output of the following code? `function Foo() { this.x = 1; return { x: 2 }; // Returns an object! } ...`?

```javascript
function Foo() {
this.x = 1;
return { x: 2 }; // Returns an object!
}
function Bar() {
this.x = 1;
return 42; // Returns a primitive
}
const foo = new Foo();
const bar = new Bar();
console.log(foo.x);
console.log(bar.x);
```

**Output:**
```

2
1
```

**Explanation:** If a constructor returns an OBJECT, `new` returns that object instead of `this`. If a constructor returns a PRIMITIVE (or nothing), `new` returns `this`. `Foo` returns `{x: 2}` so `foo.x = 2`. `Bar` returns `42` (primitive) so `bar` is the `this` object with `x = 1`.

[↑ Back to top](#table-of-contents)

### 77. What is the output of the following code? `function greet() { return `Hi, ${this.name}`; } const alice = { name: ...`?

```javascript
function greet() {
return `Hi, ${this.name}`;
}
const alice = { name: 'Alice' };
const bob = { name: 'Bob' };
const greetAlice = greet.bind(alice);
console.log(greetAlice());
console.log(greetAlice.call(bob));
```

**Output:**
```

Hi, Alice
Hi, Alice
```

**Explanation:** `bind` creates a new function with `this` permanently set to `alice`. Even calling `.call(bob)` on the bound function cannot override the binding. Bound `this` cannot be changed.

[↑ Back to top](#table-of-contents)

### 78. What is the output of the following code? `function makeAdder(x) { return function(y) { return x + y; }; } const ...`?

```javascript
function makeAdder(x) {
return function(y) {
return x + y;
};
}
const add5 = makeAdder(5);
const add10 = makeAdder(10);
console.log(add5(3));
console.log(add10(3));
console.log(add5(add10(1)));
```

**Output:**
```

8
13
16
```

**Explanation:** `makeAdder(5)` closes over `x = 5`. `add5(3)` = `5 + 3 = 8`. `add10(3)` = `10 + 3 = 13`. `add10(1)` = `11`, then `add5(11)` = `5 + 11 = 16`.

[↑ Back to top](#table-of-contents)

### 79. What is the output of the following code? `function makeMultiplier(x) { return (y) => x * y; } const double = mak...`?

```javascript
function makeMultiplier(x) {
return (y) => x * y;
}

const double = makeMultiplier(2);
const triple = makeMultiplier(3);

console.log([1, 2, 3, 4, 5].map(double));
console.log([1, 2, 3, 4, 5].map(triple));

// Point-free composition:
const compose = (...fns) => x => fns.reduceRight((v, f) => f(v), x);
const doubleThenTriple = compose(triple, double);
console.log([1, 2, 3].map(doubleThenTriple));
```

**Output:**
```

[2, 4, 6, 8, 10]
[3, 6, 9, 12, 15]
[6, 12, 18]
```

**Explanation:** `double` and `triple` are partially applied via closure. They can be passed directly to `map`. `doubleThenTriple`: first doubles (x→2x), then triples (2x→6x). Composition in point-free style.

[↑ Back to top](#table-of-contents)

### 80. What is the output of the following code? `function noDefault(a, b, c) {} function withDefault(a, b = 2, c) {} fu...`?

```javascript
function noDefault(a, b, c) {}
function withDefault(a, b = 2, c) {}
function withRest(a, ...rest) {}
const arrow = (a, b, c) => {};

console.log(noDefault.length);
console.log(withDefault.length);
console.log(withRest.length);
console.log(arrow.length);
```

**Output:**
```

3
1
1
3
```

**Explanation:** `Function.length` counts parameters BEFORE the first default or rest parameter. `withDefault` has `a` before the default `b`, so `length = 1`. `withRest` has `a` before rest, so `length = 1`.

[↑ Back to top](#table-of-contents)

### 81. What is the output of the following code? `function outer() { let x = 10; function middle() { let y = 20; functio...`?

```javascript
function outer() {
let x = 10;
function middle() {
let y = 20;
function inner() {
console.log(x + y);
}
inner();
}
middle();
}
outer();
```

**Output:**
```

30
```

**Explanation:** `inner()` has access to `y` from `middle()`'s scope and `x` from `outer()`'s scope through the closure chain. `x + y = 10 + 20 = 30`.

[↑ Back to top](#table-of-contents)

### 82. What is the output of the following code? `function Person(name) { this.name = name; console.log(this); } const p...`?

```javascript
function Person(name) {
this.name = name;
console.log(this);
}
const p1 = new Person('Alice');
const p2 = Person('Bob');
console.log(p2);
```

**Output:**
```

Person { name: 'Alice' }  // logged by constructor
undefined                  // p2 = undefined (no return value)
// 'Bob' is set on global object (window.name = 'Bob') in non-strict mode
```

**Explanation:** With `new`, a fresh object is created and `this` refers to it. Without `new`, `this` is the global object — `Person('Bob')` sets `global.name = 'Bob'`. The function returns `undefined` (no return), so `p2 = undefined`.

[↑ Back to top](#table-of-contents)

### 83. What is the output of the following code? `function sum() { return arguments[0] + arguments[1]; } const arrowSum ...`?

```javascript
function sum() {
return arguments[0] + arguments[1];
}
const arrowSum = (...args) => args[0] + args[1];

console.log(sum(1, 2));
console.log(arrowSum(1, 2));

const obj = {
value: 10,
add: function(n) { return this.value + n; },
addArrow: (n) => 10 + n, // can't use this.value here
};
console.log(obj.add(5));
console.log(obj.addArrow(5));
```

**Output:**
```

3
3
15
15
```

**Explanation:** Both work but for different reasons. Arrow `addArrow` can't use `this.value` (arrow captures outer `this` which isn't `obj`), so it hardcodes `10`. `obj.add(5)` uses `this.value = 10` correctly.

[↑ Back to top](#table-of-contents)

### 84. What is the output of the following code? `function tag(strings, ...values) { console.log(strings); console.log(v...`?

```javascript
function tag(strings, ...values) {
console.log(strings);
console.log(values);
return strings.reduce((acc, str, i) =>
acc + str + (values[i] !== undefined ? `[${values[i]}]` : ''), '');
}
const name = 'Alice';
const age = 30;
const result = tag`Hello ${name}, you are ${age} years old`;
console.log(result);
```

**Output:**
```

['Hello ', ', you are ', ' years old']
['Alice', 30]
Hello [Alice], you are [30] years old
```

**Explanation:** Tagged templates receive: `strings` (array of static string parts), `...values` (evaluated expressions). This enables custom template processing (used in styled-components, SQL, GraphQL).

[↑ Back to top](#table-of-contents)

### 85. What is the output of the following code? `function test() { console.log(arguments[0]); console.log(arguments.len...`?

```javascript
function test() {
console.log(arguments[0]);
console.log(arguments.length);
console.log(Array.isArray(arguments));
}
test(1, 2, 3);

const arrow = (...args) => {
console.log(args);
console.log(Array.isArray(args));
};
arrow(1, 2, 3);
```

**Output:**
```

1
3
false
[1, 2, 3]
true
```

**Explanation:** `arguments` is array-like but NOT an actual array. Arrow functions have NO `arguments` object — use rest params instead. Rest params `...args` is a real array.

[↑ Back to top](#table-of-contents)

### 86. What is the output of the following code? `function test(...args) { console.log(args); } const arr = [1, 2, 3]; t...`?

```javascript
function test(...args) {
console.log(args);
}
const arr = [1, 2, 3];
test(...arr);
test.apply(null, arr);

const str = 'hello';
console.log([...str]);
console.log(Array.from(str));
```

**Output:**
```

[1, 2, 3]
[1, 2, 3]
['h', 'e', 'l', 'l', 'o']
['h', 'e', 'l', 'l', 'o']
```

**Explanation:** Spread works on any iterable. Strings are iterable, so spreading or `Array.from` converts each character to an array element.

[↑ Back to top](#table-of-contents)

### 87. What is the output of the following code? `function* gen() { console.log('start'); yield 1; console.log('middle')...`?

```javascript
function* gen() {
console.log('start');
yield 1;
console.log('middle');
yield 2;
console.log('end');
return 3;
}
const g = gen();
console.log(g.next());
console.log(g.next());
console.log(g.next());
console.log(g.next());
```

**Output:**
```

start
{ value: 1, done: false }
middle
{ value: 2, done: false }
end
{ value: 3, done: true }
{ value: undefined, done: true }
```

**Explanation:** Generators are lazy. Each `next()` runs until the next `yield` (or `return`). After `return 3`, the generator is exhausted. Subsequent `next()` calls return `{ value: undefined, done: true }`.

[↑ Back to top](#table-of-contents)

### 88. What is the output of the following code? `function* gen() { yield 1; yield 2; return 3; yield 4; } const g = gen...`?

```javascript
function* gen() {
yield 1;
yield 2;
return 3;
yield 4;
}
const g = gen();
console.log([...g]);
```

**Output:**
```

[1, 2]
```

**Explanation:** Spread and `for...of` iterate until `done: true`. A `return` in a generator sets `done: true` with the returned value, but the returned value is NOT included in spread/for...of results. `yield 4` is never reached (dead code after `return`).

[↑ Back to top](#table-of-contents)

### 89. What is the output of the following code? `function* infinite() { let i = 0; while (true) yield i++; } const gen ...`?

```javascript
function* infinite() {
let i = 0;
while (true) yield i++;
}

const gen = infinite();
const first5 = Array.from({ length: 5 }, () => gen.next().value);
console.log(first5);

// Take utility:
function take(gen, n) {
const result = [];
for (const val of gen) {
result.push(val);
if (result.length >= n) break;
}
return result;
}
console.log(take(infinite(), 5));
```

**Output:**
```

[0, 1, 2, 3, 4]
[0, 1, 2, 3, 4]
```

**Explanation:** Infinite generators are safe — they only compute the next value when `.next()` is called. `break` in `for...of` calls the generator's `return()` method, cleanly stopping it.

[↑ Back to top](#table-of-contents)

### 90. What is the output of the following code? `let a = 5; console.log(a++); console.log(a); console.log(++a); console...`?

```javascript
let a = 5;
console.log(a++);
console.log(a);
console.log(++a);
console.log(a);

let b = 5;
let c = b++ + ++b;
console.log(c);
console.log(b);
```

**Output:**
```

5    // postfix returns current value THEN increments
6
7    // prefix increments THEN returns new value
7
13   // b++ returns 5 (b becomes 6), ++b increments to 7 and returns 7, 5+7=12... wait
7
```

**Wait, let's trace `b++ + ++b` carefully:**
- `b = 5`
- `b++` → returns `5`, b is now `6`
- `++b` → b becomes `7`, returns `7`
- `5 + 7 = 12`, `b = 7`

**Actual Output for c:**
```

12
7
```

**Explanation:** Postfix `++` returns the value BEFORE incrementing. Prefix `++` increments first and returns the new value.

[↑ Back to top](#table-of-contents)

### 91. What is the output of the following code? `let counter = 0; function getDefault() { return ++counter; } function ...`?

```javascript
let counter = 0;
function getDefault() {
return ++counter;
}
function test(a = getDefault()) {
console.log(a);
}
test();
test();
test(99);
console.log(counter);
```

**Output:**
```

1
2
99
2
```

**Explanation:** Default parameters are evaluated each time the function is called with `undefined`. `getDefault()` is called twice (for the first two `test()` calls). `test(99)` passes `99`, so default is not evaluated. `counter` = `2`.

[↑ Back to top](#table-of-contents)

### 92. What is the output of the following code? `let i = 0; const obj = { next() { return i < 3 ? { value: i++, done: f...`?

```javascript
let i = 0;
const obj = {
next() {
return i < 3 ? { value: i++, done: false } : { value: undefined, done: true };
},
[Symbol.iterator]() { return this; }
};
for (const val of obj) {
console.log(val);
}
console.log([...obj]);
```

**Output:**
```

0
1
2
[]     ← iterator is exhausted after for...of
```

**Explanation:** `for...of` consumes the iterator (i goes 0→1→2→3). After the loop, `i = 3` and the iterator is done. Spreading `obj` again finds the iterator already exhausted. Stateful iterators can only be iterated once — use a generator factory to reset.

[↑ Back to top](#table-of-contents)

### 93. What is the output of the following code? `let obj = { val: 1, [Symbol.toPrimitive](hint) { console.log('hint:', ...`?

```javascript
let obj = {
val: 1,
[Symbol.toPrimitive](hint) {
console.log('hint:', hint);
if (hint === 'number') return this.val;
if (hint === 'string') return `obj(${this.val})`;
return true; // default
}
};

console.log(+obj);
console.log(`${obj}`);
console.log(obj + '');
console.log(obj == 1);
```

**Output:**
```

hint: number
1
hint: string
obj(1)
hint: default
true (string concat with default hint)
hint: default
true
```

**Explanation:** `Symbol.toPrimitive` is called when an object is coerced. The `hint` argument tells you the expected type: `'number'` for arithmetic, `'string'` for template literals, `'default'` for `+` with string and `==`.

[↑ Back to top](#table-of-contents)

### 94. What is the output of the following code? `let x = 'global'; function outer() { let x = 'outer'; function inner()...`?

```javascript
let x = 'global';
function outer() {
let x = 'outer';
function inner() {
let x = 'inner';
console.log(x);
}
inner();
console.log(x);
}
outer();
console.log(x);
```

**Output:**
```

inner
outer
global
```

**Explanation:** Each scope has its own `x`. `inner()` logs its own `x = 'inner'`. After `inner()` returns, `outer()` logs its own `x = 'outer'`. Global logs `'global'`. Variable shadowing at each level.

[↑ Back to top](#table-of-contents)

### 95. What is the output of the following code? `let x = 1; { let x = 2; { let x = 3; console.log(x); } console.log(x);...`?

```javascript
let x = 1;
{
let x = 2;
{
let x = 3;
console.log(x);
}
console.log(x);
}
console.log(x);
```

**Output:**
```

3
2
1
```

**Explanation:** Each block creates a separate `let x` binding. Each scope's `x` is independent. `let` is block-scoped — inner blocks shadow outer ones without affecting them.

[↑ Back to top](#table-of-contents)

### 96. What is the output or behavior?

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

[↑ Back to top](#table-of-contents)

## Arrays, Objects & Data Structures

### 97. Design a notification/toast system with queueing, auto-dismiss, and priority handling.

**Requirements**:
- Display toast notifications with auto‑dismiss.
- Queue multiple notifications if many appear at once.
- Support priorities (e.g., error stays longer or requires manual close).
- Configurable position, animations.

**Design**:
- **Global store**: Maintain an array of notifications, each with id, message, type, priority, autoDismissTimeout, etc.
- **Queue management**: When a new notification is added, if the limit is reached (e.g., max 3 visible), add to a queue. When a notification is removed, show the next from queue.
- **Auto‑dismiss**: Use `setTimeout` per notification; clear timeout on manual close or when notification is removed.
- **Priority handling**: Sort or prioritize showing high‑priority notifications (e.g., errors) over lower ones; maybe replace a low‑priority notification if a high‑priority arrives.
- **UI**: Use a portal to render toasts in a fixed container. Animate in/out.
- **API**: Provide `notify.success()`, `notify.error()` etc., with options.

[↑ Back to top](#table-of-contents)

### 98. Design a Progress Bar / Stepper with configurable steps and validation logic.

**Requirements**: Show a multi‑step process (e.g., form steps). Each step can have validation before proceeding. Visual indication of completed/active/pending steps.

**Design**:
- **Props**: `steps` array (each with label, component), `validateStep` function per step, `onComplete`.
- **State**: `currentStep`, `stepData` (collected data).
- **Behavior**: When user clicks “Next”, run validation; if passes, move to next step. When “Previous”, go back. On last step, call `onComplete`.
- **Styling**: Use CSS classes for step indicators (completed, active, pending). Use `flex` or `grid`.

**Implementation**:

```jsx
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

[↑ Back to top](#table-of-contents)

### 99. Design a Todo List application with add, edit, delete, and mark‑as‑complete.

**Requirements**: Manage a list of todos; each todo has an id, text, and completed flag. Support adding, editing, deleting, and toggling completion.

**Design considerations**:
- **State**: Use `useState` (or `useReducer` for complex updates) to store todos array.
- **Edit mode**: Track which todo is being edited (or use a separate edit field).
- **Accessibility**: Keyboard navigation, focus management.
- **Persistence**: Optionally store in `localStorage`.
- **Performance**: Use `useCallback` for handlers, `React.memo` for each todo item to avoid unnecessary re‑renders.

**Implementation skeleton**:

```jsx
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

[↑ Back to top](#table-of-contents)

### 100. Implement: `chunk(array, size)` — split array into chunks.

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

[↑ Back to top](#table-of-contents)

### 101. Implement: Flatten array to any depth.

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

[↑ Back to top](#table-of-contents)

### 102. What is the output of the following code? `console.log([] == ![]);...`?

```javascript
console.log([] == ![]);
```

**Output:**
```

true
```

**Explanation:** Step by step:
1. `![]` → `false` (arrays are truthy, so negation gives false)
2. `[] == false` → `[] == 0` (boolean converts to number)
3. `[] == 0` → `'' == 0` (array.toString() = empty string)
4. `'' == 0` → `0 == 0` (empty string converts to 0)
5. `0 == 0` → `true`

[↑ Back to top](#table-of-contents)

### 103. What is the output?

`true`. Steps: `![]` is `false` (arrays are truthy). `[] == false` → `[] == 0` (false to number). `[] == 0` → `'' == 0` (array to primitive → empty string). `'' == 0` → `0 == 0` → `true`. This is a classic demonstration of why `==` should be avoided.

[↑ Back to top](#table-of-contents)

### 104. What is the output?

`true`. Steps: `![]` is `false` (arrays are truthy). `[] == false` → `[] == 0` (false to number). `[] == 0` → `'' == 0` (array to primitive → empty string). `'' == 0` → `0 == 0` → `true`. This is a classic demonstration of why `==` should be avoided.

[↑ Back to top](#table-of-contents)

## Type Coercion, Equality & Data Types

### 105. What is the output of the following code? `console.log("B" + "a" + + "a" + "a");...`?

```javascript
console.log("B" + "a" + + "a" + "a");
```

**Output:**
```

BaNaNa
```

**Explanation:** `+"a"` is unary plus on `"a"` = `NaN`. So: `"B" + "a"` = `"Ba"`, then `"Ba" + NaN` = `"BaNaN"` (NaN converts to string "NaN"), then `"BaNaN" + "a"` = `"BaNaNa"`. Classic.

[↑ Back to top](#table-of-contents)

### 106. What is the output of the following code? `console.log(+true); console.log(+false); console.log(+null); console.l...`?

```javascript
console.log(+true);
console.log(+false);
console.log(+null);
console.log(+undefined);
console.log(+[]);
console.log(+[1]);
console.log(+[1,2]);
console.log(+{});
console.log(+"");
console.log(+"5");
```

**Output:**
```

1
0
0
NaN
0
1
NaN
NaN
0
5
```

**Explanation:** Unary `+` converts to number. `+[]` → `+""` (array to string = "") → `0`. `+[1]` → `+"1"` → `1`. `+[1,2]` → `+"1,2"` → `NaN`. `+{}` → `+"[object Object]"` → `NaN`. `+""` → `0`. `+"5"` → `5`.

[↑ Back to top](#table-of-contents)

### 107. What is the output of the following code? `console.log(false || 'default'); console.log('' || 'default'); console...`?

```javascript
console.log(false || 'default');
console.log('' || 'default');
console.log(0 || 'default');
console.log(null || 'default');
console.log('value' || 'default');

console.log(false && 'value');
console.log('truthy' && 'value');
console.log('truthy' && false);
```

**Output:**
```

default
default
default
default
value
false
value
false
```

**Explanation:** `||` returns the first TRUTHY value or the last value. `&&` returns the first FALSY value or the last value. They return actual values, not booleans. This is short-circuit evaluation.

[↑ Back to top](#table-of-contents)

### 108. What is the output of the following code? `console.log(NaN === NaN); console.log(NaN == NaN); console.log(isNaN("...`?

```javascript
console.log(NaN === NaN);
console.log(NaN == NaN);
console.log(isNaN("hello"));
console.log(Number.isNaN("hello"));
console.log(Number.isNaN(NaN));
```

**Output:**
```

false
false
true
false
true
```

**Explanation:** `NaN` is the only value not equal to itself. `isNaN()` coerces the argument first (`"hello"` → `NaN`), so it returns `true`. `Number.isNaN()` does NOT coerce — `"hello"` is not `NaN` (it's a string), so `false`. Only actual `NaN` returns `true` from `Number.isNaN`.

[↑ Back to top](#table-of-contents)

### 109. What is the output of the following code? `console.log(null + 1); console.log(undefined + 1); console.log(null + ...`?

```javascript
console.log(null + 1);
console.log(undefined + 1);
console.log(null + undefined);
console.log(null + null);
```

**Output:**
```

1
NaN
NaN
0
```

**Explanation:** `null` converts to `0` in arithmetic. `undefined` converts to `NaN`. `null + 1` = `0 + 1` = `1`. `undefined + 1` = `NaN + 1` = `NaN`. `null + undefined` = `0 + NaN` = `NaN`. `null + null` = `0 + 0` = `0`.

[↑ Back to top](#table-of-contents)

### 110. What is the output of the following code? `console.log(typeof foo); console.log(typeof bar); var foo = function()...`?

```javascript
console.log(typeof foo);
console.log(typeof bar);
var foo = function() {};
function bar() {}
```

**Output:**
```

undefined
function
```

**Explanation:** `foo` is a `var` declaration hoisted as `undefined`. `bar` is a function declaration hoisted completely. `typeof` never throws, returns a string.

[↑ Back to top](#table-of-contents)

### 111. What is the output of the following code? `console.log(typeof null); console.log(typeof undefined); console.log(t...`?

```javascript
console.log(typeof null);
console.log(typeof undefined);
console.log(typeof NaN);
console.log(typeof function(){});
console.log(typeof class{});
console.log(typeof []);
```

**Output:**
```

object
undefined
number
function
function
object
```

**Explanation:** `typeof null === 'object'` is a historic bug. `NaN` is of type `number`. Functions and classes have type `function`. Arrays are objects. Use `Array.isArray()` to detect arrays.

[↑ Back to top](#table-of-contents)

### 112. What is the output of the following code? `console.log(typeof typeof 1); console.log(typeof typeof 'hello'); cons...`?

```javascript
console.log(typeof typeof 1);
console.log(typeof typeof 'hello');
console.log(typeof typeof undefined);
console.log(typeof typeof typeof 1);
```

**Output:**
```

string
string
string
string
```

**Explanation:** `typeof 1` = `'number'` (string). `typeof 'number'` = `'string'`. `typeof` always returns a string, so `typeof typeof anything` is always `'string'`. This chains indefinitely — it's always `'string'`.

[↑ Back to top](#table-of-contents)

### 113. What is the output of the following code? `function processData(data) { if (typeof data !== 'string') { throw new...`?

```javascript
function processData(data) {
if (typeof data !== 'string') {
throw new TypeError(`Expected string, got ${typeof data}`);
}
return data.toUpperCase();
}

const results = [
[processData, 'hello'],
[processData, 42],
[processData, 'world'],
].map(([fn, arg]) => {
try {
return { ok: true, value: fn(arg) };
} catch (e) {
return { ok: false, error: e.message };
}
});

console.log(results);
```

**Output:**
```

[
{ ok: true, value: 'HELLO' },
{ ok: false, error: 'Expected string, got number' },
{ ok: true, value: 'WORLD' }
]
```

**Explanation:** This is the Result pattern (common in functional programming). Wrapping each call in try/catch produces a consistent structure whether it succeeds or fails. Allows processing all items without one error stopping the rest.

[↑ Back to top](#table-of-contents)

### 114. What is the output of the following code? `function test() { console.log(typeof x); console.log(typeof y); var x ...`?

```javascript
function test() {
console.log(typeof x);
console.log(typeof y);
var x = 1;
}
test();
```

**Output:**
```

undefined
undefined
```

**Explanation:** `var x` is hoisted — `typeof x` = `'undefined'` (the string "undefined"). `y` was never declared anywhere. `typeof` on an undeclared variable returns the string `'undefined'` without throwing (unlike accessing it directly which would throw ReferenceError).

[↑ Back to top](#table-of-contents)

### 115. What is the output of the following code? `var NULL = undefined; console.log(typeof undefined == typeof NULL);...`?

```javascript
var NULL = undefined;
console.log(typeof undefined == typeof NULL);
```

**Output:**
```

true
```

**Explanation:** `typeof undefined` is `'undefined'`. `NULL` is a variable holding `undefined`, so `typeof NULL` is also `'undefined'`. Both strings are equal with `==`.

[↑ Back to top](#table-of-contents)

### 116. What is the output: `typeof null`?

`'object'`. This is a well-known bug in JavaScript that has persisted since its first implementation and cannot be fixed without breaking existing code. The original implementation used low-order bits to tag types, and null's representation had the same bits as object tags.

[↑ Back to top](#table-of-contents)

## Asynchronous JavaScript (Promises, async/await, Event Loop)

### 117. Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.

**Requirements**: Input with suggestions, async fetching, prevent out‑of‑order responses.

**Design**:
- **Debouncing**: 300ms delay; cancel previous timer.
- **Caching**: Map (key = query) to suggestions; check cache before fetch.
- **Race condition**: Use request ID or `AbortController`. Each new request aborts previous.
- **Accessibility**: ARIA combobox, listbox, option. Keyboard navigation.
- **Highlighting**: Use `dangerouslySetInnerHTML` or regex replace to highlight matched text.

[↑ Back to top](#table-of-contents)

### 118. Design a state management solution for a complex app.

**Requirements**:
- Handle asynchronous data, caching, optimistic updates.
- Manage shared state across many features.
- Ensure performance.

**Design**:
- **Global state**: Use Redux Toolkit with slices per feature. Use `createEntityAdapter` for normalized data.
- **Async logic**: `createAsyncThunk` for API calls; handle loading/error states.
- **Caching**: Implement a cache layer with expiration; use selectors to retrieve cached data.
- **Optimistic updates**: Update the store optimistically on user actions; if the request fails, rollback using the previous state snapshot.
- **Derived state**: Use `createSelector` (Reselect) for memoized derived data.
- **Cross‑slice communication**: Use `extraReducers` to listen to actions from other slices.
- **Performance**: Use selectors that compute only when needed. Use `React.memo` and `useCallback` to avoid re‑renders.

[↑ Back to top](#table-of-contents)

### 119. Design an autocomplete search with debouncing, caching, and race condition handling.

**Requirements**:
- As user types, fetch suggestions from an API.
- Debounce input to avoid excessive requests.
- Cache results to avoid repeated network calls.
- Handle race conditions: ensure that responses arrive in the correct order.

**Design**:
- **Debouncing**: Use a `setTimeout` that delays the API call until after a pause (e.g., 300ms). Clear previous timer on new input.
- **Caching**: Use a `Map` with the search query as key and the fetched results as value. Check cache before making a request.
- **Race condition handling**: Store the latest request’s identifier (e.g., timestamp or request ID). When a response arrives, compare its ID with the stored latest; if it doesn’t match, ignore it.
- **Implementation**: Use `useState` for input value, `useRef` for cache, debounce timer, and current request ID. Consider using `AbortController` to cancel previous in‑flight requests.

[↑ Back to top](#table-of-contents)

### 120. Implement: `pipe` with error handling and async support.

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

[↑ Back to top](#table-of-contents)

### 121. What is the output of the following code? `async function a() { console.log('a start'); await b(); console.log('a...`?

```javascript
async function a() {
console.log('a start');
await b();
console.log('a end');
}
async function b() {
console.log('b start');
await c();
console.log('b end');
}
async function c() {
console.log('c');
}
console.log('start');
a();
console.log('end');
```

**Output:**
```

start
a start
b start
c
end
b end
a end
```

**Explanation:** Each `await` yields control. `a()` starts, calls `b()`, which calls `c()`. `c()` logs and returns. Back to sync: `end` logs. Then microtasks resume: `b end`, then `a end`.

[↑ Back to top](#table-of-contents)

### 122. What is the output of the following code? `async function fail() { throw new Error('async error'); } async functi...`?

```javascript
async function fail() {
throw new Error('async error');
}
async function main() {
try {
await fail();
console.log('this never runs');
} catch(e) {
console.log('caught:', e.message);
}
console.log('continues after catch');
}
main();
```

**Output:**
```

caught: async error
continues after catch
```

**Explanation:** `throw` inside an `async` function causes the returned Promise to reject. `await fail()` rethrows the rejection as a synchronous error inside `main`, caught by `try/catch`. Execution continues normally after the catch block.

[↑ Back to top](#table-of-contents)

### 123. What is the output of the following code? `async function fails() { throw new Error('async fail'); } // Will this...`?

```javascript
async function fails() {
throw new Error('async fail');
}

// Will this catch it?
try {
fails(); // Not awaited!
} catch (e) {
console.log('caught:', e.message);
}

// What about this?
fails().catch(e => console.log('promise caught:', e.message));
```

**Output:**
```

promise caught: async fail
```

(And a console warning about unhandled rejection from the first `fails()` call)

**Explanation:** `fails()` without `await` returns a rejected Promise. A synchronous `try/catch` cannot catch a rejected Promise. You MUST either `await` inside an async context or use `.catch()`. The first call is an unhandled rejection.

[↑ Back to top](#table-of-contents)

### 124. What is the output of the following code? `async function fetchData() { return 42; } const result = fetchData(); ...`?

```javascript
async function fetchData() {
return 42;
}
const result = fetchData();
console.log(result);
result.then(v => console.log(v));
```

**Output:**
```

Promise { 42 }
42
```

**Explanation:** `async` functions ALWAYS return a Promise. `fetchData()` returns `Promise.resolve(42)`. The `console.log(result)` shows the Promise object. `.then` receives the resolved value `42`.

[↑ Back to top](#table-of-contents)

### 125. What is the output of the following code? `async function main() { console.log('A'); await Promise.resolve(); con...`?

```javascript
async function main() {
console.log('A');
await Promise.resolve();
console.log('B');
await Promise.resolve();
console.log('C');
}
console.log('Start');
main();
console.log('End');
```

**Output:**
```

Start
A
End
B
C
```

**Explanation:** `main()` is called, logs `A`, then `await` pauses it and yields control back. The sync code `End` logs. Then microtasks resume: `B` logs, another await, then `C`.

[↑ Back to top](#table-of-contents)

### 126. What is the output of the following code? `async function one() { return 1; } async function two() { const a = aw...`?

```javascript
async function one() {
return 1;
}
async function two() {
const a = await one();
const b = await one();
return a + b;
}
two().then(console.log);
```

**Output:**
```

2
```

**Explanation:** `one()` resolves to `1`. `await one()` gives `1`. Both `a` and `b` are `1`. `a + b = 2`. The result is a Promise resolving to `2`, and `.then(console.log)` logs it.

[↑ Back to top](#table-of-contents)

### 127. What is the output of the following code? `async function test() { console.log(1); await null; console.log(2); aw...`?

```javascript
async function test() {
console.log(1);
await null;
console.log(2);
await null;
console.log(3);
}
console.log(4);
test();
console.log(5);
```

**Output:**
```

4
1
5
2
3
```

**Explanation:** Sync: `4`, then `test()` starts, logs `1`, hits `await`, pauses. Sync continues: `5`. Microtask resumes `test`: `2`, another await, then `3`.

[↑ Back to top](#table-of-contents)

### 128. What is the output of the following code? `async function test() { const result = await Promise.all([ Promise.res...`?

```javascript
async function test() {
const result = await Promise.all([
Promise.resolve('a'),
new Promise(resolve => setTimeout(() => resolve('b'), 100)),
Promise.resolve('c'),
]);
console.log(result);
}
test();
console.log('sync after test()');
```

**Output:**
```

sync after test()
['a', 'b', 'c']   // after ~100ms
```

**Explanation:** `test()` is async — it returns a Promise immediately and the sync code after continues. `Promise.all` waits for the slowest (100ms setTimeout), then resolves with all three values in ORDER (not resolution order).

[↑ Back to top](#table-of-contents)

### 129. What is the output of the following code? `console.log('1'); setTimeout(() => console.log('2'), 0); Promise.resol...`?

```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
Promise.resolve().then(() => {
console.log('4');
setTimeout(() => console.log('5'), 0);
});
console.log('6');
```

**Output:**
```

1
6
3
4
2
5
```

**Explanation:**
- Sync: `1`, `6`
- Microtask queue runs (ALL microtasks before next macrotask): `3`, `4` (the `.then` for 4 also schedules `setTimeout(5)`)
- Macrotask queue: `2`, then `5`

[↑ Back to top](#table-of-contents)

### 130. What is the output of the following code? `console.log('A'); setTimeout(() => console.log('B'), 0); console.log('...`?

```javascript
console.log('A');
setTimeout(() => console.log('B'), 0);
console.log('C');
```

**Output:**
```

A
C
B
```

**Explanation:** Synchronous code runs first: `A`, then `C`. `setTimeout` with delay `0` puts the callback in the macrotask queue. It runs after the current synchronous code completes.

[↑ Back to top](#table-of-contents)

### 131. What is the output of the following code? `console.log('before'); new Promise((resolve) => { console.log('inside ...`?

```javascript
console.log('before');
new Promise((resolve) => {
console.log('inside executor');
resolve('done');
console.log('after resolve');
}).then(val => console.log(val));
console.log('after promise');
```

**Output:**
```

before
inside executor
after resolve
after promise
done
```

**Explanation:** The Promise executor function runs SYNCHRONOUSLY. `resolve()` marks the promise as fulfilled but the `.then` callback is scheduled as a microtask. So `after resolve` and `after promise` run before `done`.

[↑ Back to top](#table-of-contents)

### 132. What is the output of the following code? `const p = new Promise((resolve) => { resolve(1); resolve(2); resolve(3...`?

```javascript
const p = new Promise((resolve) => {
resolve(1);
resolve(2);
resolve(3);
});
p.then(v => console.log(v));
```

**Output:**
```

1
```

**Explanation:** A Promise can only settle ONCE. The first `resolve(1)` settles the promise as fulfilled with value `1`. Subsequent `resolve(2)` and `resolve(3)` calls are silently ignored.

[↑ Back to top](#table-of-contents)

### 133. What is the output of the following code? `const p1 = new Promise((resolve) => setTimeout(() => resolve('P1'), 30...`?

```javascript
const p1 = new Promise((resolve) => setTimeout(() => resolve('P1'), 300));
const p2 = new Promise((resolve) => setTimeout(() => resolve('P2'), 100));
const p3 = new Promise((_, reject) => setTimeout(() => reject('P3'), 200));

Promise.all([p1, p2, p3])
.then(console.log)
.catch(e => console.log('all caught:', e));

Promise.race([p1, p2, p3])
.then(v => console.log('race:', v))
.catch(e => console.log('race caught:', e));
```

**Output:**
```

race: P2         (after ~100ms — P2 wins the race)
all caught: P3   (after ~200ms — P3 rejects, Promise.all fails)
```

**Explanation:** `Promise.race` settles when the first promise settles — P2 resolves at 100ms. `Promise.all` fails when any promise rejects — P3 rejects at 200ms.

[↑ Back to top](#table-of-contents)

### 134. What is the output of the following code? `const promise1 = Promise.resolve(1); const promise2 = Promise.resolve(...`?

```javascript
const promise1 = Promise.resolve(1);
const promise2 = Promise.resolve(2);
const promise3 = Promise.reject(new Error('fail'));

Promise.allSettled([promise1, promise2, promise3])
.then(results => {
results.forEach(result => {
if (result.status === 'fulfilled') {
console.log('value:', result.value);
} else {
console.log('reason:', result.reason.message);
}
});
});
```

**Output:**
```

value: 1
value: 2
reason: fail
```

**Explanation:** `Promise.allSettled` never rejects. It waits for ALL promises and gives you each result with a `status` field. Essential when you need all results regardless of failures.

[↑ Back to top](#table-of-contents)

### 135. What is the output of the following code? `for (let i = 0; i < 3; i++) { setTimeout(function() { console.log(i); ...`?

```javascript
for (let i = 0; i < 3; i++) {
setTimeout(function() {
console.log(i);
}, 1000);
}
```

**Output:**
```

0
1
2
```

**Explanation:** `let` is block-scoped. Each loop iteration creates a NEW binding of `i`. Each callback closes over its own distinct `i`. This is the fix for the classic `var` closure bug.

[↑ Back to top](#table-of-contents)

### 136. What is the output of the following code? `for (var i = 0; i < 3; i++) { setTimeout(function() { console.log(i); ...`?

```javascript
for (var i = 0; i < 3; i++) {
setTimeout(function() {
console.log(i);
}, 1000);
}
```

**Output:**
```

3
3
3
```

**Explanation:** `var` is function-scoped (not block-scoped). All three callbacks share the same `i`. By the time they run (after 1 second), the loop has finished and `i === 3`. All three log `3`.

[↑ Back to top](#table-of-contents)

### 137. What is the output of the following code? `function Timer() { this.seconds = 0; setInterval(function() { this.sec...`?

```javascript
function Timer() {
this.seconds = 0;
setInterval(function() {
this.seconds++;
console.log(this.seconds);
}, 1000);
}
const t = new Timer();
```

**Output:**
```

NaN (every second)
```

**Explanation:** The regular function inside `setInterval` has its own `this`. When called by the timer, `this` is the global object (or `undefined` in strict mode). `undefined.seconds++` = `NaN`. Fix: use arrow function, or `const self = this`, or `.bind(this)`.

[↑ Back to top](#table-of-contents)

### 138. What is the output of the following code? `let resolve; const p = new Promise(r => { resolve = r; }); p.then(v =>...`?

```javascript
let resolve;
const p = new Promise(r => { resolve = r; });

p.then(v => console.log('then1:', v));
p.then(v => console.log('then2:', v));

console.log('before resolve');
resolve(42);
console.log('after resolve');
```

**Output:**
```

before resolve
after resolve
then1: 42
then2: 42
```

**Explanation:** Multiple `.then` on the same Promise both get the resolved value. The executor runs synchronously (so we can capture `resolve`). Calling `resolve` synchronously queues the `.then` callbacks as microtasks. They run after the sync code.

[↑ Back to top](#table-of-contents)

### 139. What is the output of the following code? `Promise.resolve('start') .then(val => { console.log(val); return 'seco...`?

```javascript
Promise.resolve('start')
.then(val => {
console.log(val);
return 'second';
})
.then(val => {
console.log(val);
return Promise.resolve('third');
})
.then(val => {
console.log(val);
})
.then(val => {
console.log(val); // What prints here?
});
```

**Output:**
```

start
second
third
undefined
```

**Explanation:** The last `.then` receives `undefined` because the previous `.then` had no return statement. A `.then` callback that doesn't return anything implicitly returns `undefined`, which resolves the next promise to `undefined`.

[↑ Back to top](#table-of-contents)

### 140. What is the output of the following code? `Promise.resolve() .then(() => { throw new Error('oops'); }) .then(() =...`?

```javascript
Promise.resolve()
.then(() => { throw new Error('oops'); })
.then(() => console.log('then'))
.catch(e => console.log('caught:', e.message))
.then(() => console.log('after catch'));
```

**Output:**
```

caught: oops
after catch
```

**Explanation:** The first `.then` throws, skipping subsequent `.then`s until the `.catch`. After `.catch` handles the error and returns normally (no throw), the next `.then` runs. The chain continues normally after a `.catch`.

[↑ Back to top](#table-of-contents)

### 141. What is the output of the following code? `Promise.resolve().then(() => console.log('Promise 1')); queueMicrotask...`?

```javascript
Promise.resolve().then(() => console.log('Promise 1'));
queueMicrotask(() => console.log('queueMicrotask'));
Promise.resolve().then(() => console.log('Promise 2'));
setTimeout(() => console.log('setTimeout'), 0);
```

**Output:**
```

Promise 1
queueMicrotask
Promise 2
setTimeout
```

**Explanation:** All three microtasks (two Promise callbacks and `queueMicrotask`) run before the macrotask (`setTimeout`). They run in the order they were queued.

[↑ Back to top](#table-of-contents)

### 142. What is the output of the following code? `Promise.resolve(1) .then(v => { console.log(v); return Promise.resolve...`?

```javascript
Promise.resolve(1)
.then(v => {
console.log(v);
return Promise.resolve(2);
})
.then(v => {
console.log(v);
throw new Error('oops');
})
.catch(e => {
console.log(e.message);
return 3;
})
.then(v => console.log(v))
.finally(() => console.log('done'));
```

**Output:**
```

1
2
oops
3
done
```

**Explanation:** Chain flows: resolve(1)→then logs 1→resolve(2)→then logs 2→throw→catch logs 'oops' and returns 3→then logs 3→finally logs 'done'. `finally` always runs and passes the value through.

[↑ Back to top](#table-of-contents)

### 143. What is the output of the following code? `Promise.resolve(1) .then(x => { console.log(x); return x + 1; }) .then...`?

```javascript
Promise.resolve(1)
.then(x => {
console.log(x);
return x + 1;
})
.then(x => {
console.log(x);
return Promise.resolve(x + 1);
})
.then(x => console.log(x));
```

**Output:**
```

1
2
3
```

**Explanation:** Each `.then` receives the resolved value of the previous. Returning a value wraps it in a resolved Promise. Returning a Promise unwraps it before passing to the next `.then`.

[↑ Back to top](#table-of-contents)

### 144. What is the output of the following code? `setTimeout(() => console.log('A'), 0); setTimeout(() => { console.log(...`?

```javascript
setTimeout(() => console.log('A'), 0);
setTimeout(() => {
console.log('B');
Promise.resolve().then(() => console.log('C'));
}, 0);
setTimeout(() => console.log('D'), 0);
```

**Output:**
```

A
B
C
D
```

**Explanation:** `A`, `B`, `D` are all macrotasks queued in order. After `B` runs, `C` is added as a microtask. Microtasks run before the next macrotask, so `C` runs before `D`.

[↑ Back to top](#table-of-contents)

### 145. What is the output? (Most asked JS output question)

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

[↑ Back to top](#table-of-contents)

### 146. What is the output? (Node.js)

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

[↑ Back to top](#table-of-contents)

### 147. What is the output? (Ultimate async challenge)

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

[↑ Back to top](#table-of-contents)

## Error Handling & Debugging

### 148. How do you create a custom error?

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

[↑ Back to top](#table-of-contents)

## General / Miscellaneous JavaScript Concepts

### 149. Design a carousel that can handle 1000+ images efficiently.

**Requirements**:
- Display one image at a time (or a few) with navigation.
- Smooth transitions.
- Efficient memory usage with 1000+ images.

**Design**:
- **Virtualization**: Only render images that are currently visible plus a buffer (e.g., previous/next slide). Use `IntersectionObserver` to load images on demand.
- **Lazy loading**: Load image `src` only when the slide is about to become visible.
- **State**: Track current index; use `transform: translateX` with CSS transitions for sliding.
- **Performance**: Preload next image(s) for smoother navigation. Avoid rendering all images at once; reuse DOM elements (e.g., only 3–5 slides in the DOM at any time).
- **Memory**: Unload images that are far away by removing their `src` and freeing memory. However, modern browsers handle this; but for extreme cases, you can manage manually.
- **Accessibility**: Keyboard navigation, ARIA roles (`listbox`, `option`), focus management.

[↑ Back to top](#table-of-contents)

### 150. Design a config-driven form renderer using a JSON schema.

**Requirements**:
- Render forms based on a JSON schema defining fields, validations, layouts.
- Support dynamic field visibility, dependencies.

**Design**:
- **Schema**: Define fields: type (text, number, select, date), label, placeholder, validations (required, pattern, min/max), conditional display (showIf based on other field values).
- **Parser**: Recursively render components based on field type using a registry (e.g., `FieldComponent` map).
- **State**: Use `react-hook-form` or similar to manage form state, validation, and error messages.
- **Dynamic visibility**: Use `useWatch` to watch other fields and conditionally render.
- **Layout**: Support groups, sections, columns via schema properties.
- **Validation**: Integrate with Zod or Yup schemas derived from the JSON.
- **Extensibility**: Allow custom component registration for custom field types.

[↑ Back to top](#table-of-contents)

### 151. Design a data table with sorting, filtering, pagination, and performance trade-offs.

**Requirements**:
- Display large datasets with client‑side or server‑side operations.
- Sorting by columns, filtering by text or dropdown, pagination.

**Design**:
- **Data fetching**: Decide between client‑side (all data loaded) or server‑side (pagination and filtering done on server). For large datasets, server‑side is preferred.
- **State**: Store current page, page size, sort column and direction, filter values. Use URL query parameters for shareability.
- **Rendering**: Use virtualization (e.g., `react‑virtual`) if many rows are shown. Use `React.memo` for rows.
- **Sorting**: On column header click, toggle sort direction; re‑fetch data (server‑side) or sort client‑side.
- **Filtering**: Input fields for each column; debounce before sending request.
- **Pagination**: Show page numbers or “Load more”. Use offset/limit.
- **Performance trade‑offs**: Server‑side reduces client memory but increases network requests. Client‑side is faster for filtering/sorting but only suitable for moderate data size. Use virtualization for client‑side tables with many rows.

[↑ Back to top](#table-of-contents)

### 152. Design a drag-and-drop interface (e.g., kanban board).

**Requirements**:
- Reorder items within a column.
- Move items between columns.
- Touch and mouse support.

**Design**:
- **HTML5 Drag-and-Drop** is limited; use libraries like `react‑dnd`, `dnd‑kit`, or `@dnd‑kit/sortable` for better control.
- **State**: Store columns and cards in a normalized structure. On drag end, update order/column mapping.
- **Accessibility**: Ensure keyboard accessibility (e.g., using arrow keys to move focus, Enter to pick up, arrow to move, Enter to drop).
- **Performance**: Use memoization for column and card components; avoid re‑renders during drag.
- **Visual feedback**: Show placeholder, highlight drop zones.

[↑ Back to top](#table-of-contents)

### 153. Design a multi-step form with validation.

**Requirements**:
- Several steps (e.g., personal info, address, confirmation).
- Client‑side validation per step.
- Keep data across steps; allow go back and edit.
- Submit at the end.

**Design**:
- **State**: Use `useReducer` or context to store form data across steps. Each step's data can be local state but synced to global context.
- **Navigation**: Maintain current step index; on “Next”, validate current step; if valid, proceed.
- **Validation**: Use schema validation (e.g., Zod) per step. Show inline errors.
- **Persistence**: Optionally store draft in `localStorage` to recover on refresh.
- **Submission**: On final step, collect all data and send to API.
- **UI**: Show progress indicator; allow step clicks to navigate.

[↑ Back to top](#table-of-contents)

### 154. Design a Posts with Comments system – how do you manage deeply nested data?

**Requirements**: Display posts, each with comments, comments may have nested replies.

**Design**:
- **Data structure**: Use normalized state (e.g., entities for posts, users, comments). Store comments as map with parent references. Build tree on demand.
- **State management**: Redux Toolkit with `createEntityAdapter` for normalized data. Or use React Query for server state and local state for UI.
- **Rendering**: Recursive component for comment tree. Use memoization to avoid re‑renders on deep trees.
- **Optimistic updates**: When adding comment, update local state immediately, then sync with server.
- **Performance**: Use virtual scrolling for long comment threads.

[↑ Back to top](#table-of-contents)

### 155. Design a real-time dashboard with multiple data sources.

**Requirements**:
- Display widgets with live updates from WebSocket, SSE, or polling.
- Handle multiple data sources simultaneously.
- Ensure performance and scalability.

**Design**:
- **Data fetching strategy**: Use WebSockets for low‑latency updates; for less critical data, use Server‑Sent Events or long polling.
- **State management**: Centralize dashboard state (e.g., Redux) with slices for each widget. Use `createAsyncThunk` for initial data load and WebSocket middleware to dispatch updates.
- **Subscription management**: Use a custom hook that subscribes to the data source on component mount and cleans up on unmount. For multiple sources, use a central manager or a pub/sub pattern.
- **Caching & reconciliation**: Cache incoming data to avoid flickering; merge updates with existing state.
- **Performance**: Use memoized selectors, `React.memo` for widgets, and virtualize if needed. Throttle high‑frequency updates.
- **Error resilience**: Reconnection logic with exponential backoff; display error states per widget.

[↑ Back to top](#table-of-contents)

### 156. Design a search with typeahead/autocomplete.

(Similar to autocomplete design above, but can add highlighting, keyboard navigation.)

**Design**:
- **Input**: Controlled component.
- **Debouncing**: 300ms delay.
- **Source**: Fetch suggestions from API; may also include recent searches.
- **Caching**: In‑memory cache with TTL.
- **Race condition**: Use AbortController or request ID.
- **Accessibility**: ARIA roles (`combobox`, `listbox`, `option`); keyboard navigation (arrow keys, Enter, Esc).
- **Highlighting**: Highlight matching substring in results.
- **Fallback**: Show “no results” when empty.

[↑ Back to top](#table-of-contents)

### 157. Design a state management solution for a complex analytics/dashboard app.

**Requirements**: Real‑time data, multiple widgets, filters that affect many components.

**Design**:
- **Store**: Redux Toolkit with slices for:
- Filters (global time range, date picker)
- Widget data (each widget’s data, loading, error)
- User preferences
- **Normalization**: Use `createEntityAdapter` for time‑series data.
- **Async**: `createAsyncThunk` for API calls; caching with `selectors` that return memoized data.
- **WebSocket integration**: Middleware that dispatches actions on incoming messages.
- **Performance**: Use `useSelector` with shallow equality or memoized selectors. Use `React.memo` for widgets.
- **Derived data**: Use Reselect to compute aggregated metrics only when raw data changes.

[↑ Back to top](#table-of-contents)

### 158. Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.

**Requirements**:
- Multiple filter facets that update the product list.
- Efficient state updates without causing excessive re‑renders.
- Pagination or infinite scroll.

**Design**:
- **State**: Use a global store (Redux or Zustand) for filters and product list. Filters: price range, category (multi‑select), rating, etc.
- **Filter logic**: Combine filters into a query object; on filter change, update the query and fetch new products. Debounce price slider input.
- **Caching**: Cache product pages based on filter query to avoid redundant requests.
- **UI performance**: Use `React.memo` for product cards; use `useSelector` with memoized selectors (Reselect) to derive filtered products only when relevant filters change.
- **Pagination**: Implement either offset‑based pagination or cursor‑based; load more on scroll or via “Load More” button.
- **URL synchronization**: Keep filters in URL query parameters for shareability and persistence on refresh.

[↑ Back to top](#table-of-contents)

### 159. Design an image gallery with lazy loading and skeleton placeholders.

**Requirements**:
- Load images as user scrolls.
- Show placeholder skeletons until images load.
- Support responsive layouts (grid, masonry).

**Design**:
- **Lazy loading**: Use `IntersectionObserver` to detect when an image enters the viewport. Set the `src` attribute only when visible. Fallback for older browsers using `loading="lazy"` attribute.
- **Skeletons**: Render a placeholder component with the same dimensions (e.g., a gray box with pulse animation) while `img` is loading. On load, replace with image.
- **Responsive**: Use CSS Grid with `minmax` for responsive columns. For masonry, use a library or CSS columns.
- **Performance**: Use thumbnails; serve responsive images with `srcset` and `sizes`.
- **Error handling**: Show broken image icon on load error.

[↑ Back to top](#table-of-contents)

### 160. Design an infinite scrolling feed (virtualization, pagination, loading states).

**Requirements**:
- Load more items as user scrolls near the bottom.
- Use pagination (cursor or offset).
- Virtualization to render only visible items.
- Manage loading and error states.

**Design**:
- **Pagination**: Use offset‑based (page, limit) or cursor‑based (next token). Store a list of items.
- **Scroll detection**: Attach scroll listener to the container; check if scroll position is near bottom (e.g., `scrollHeight - scrollTop <= clientHeight + threshold`). Use throttling for performance.
- **Loading state**: Show a loading spinner when fetching. Prevent duplicate requests.
- **Virtualization**: Use a library like `react-window` or `react-virtualized` to render only the items in viewport. This is crucial for large lists to maintain performance.
- **Error handling**: Display error message and optionally retry button.
- **Edge cases**: When no more items, hide loading indicator; handle empty state.

[↑ Back to top](#table-of-contents)

### 161. How do you create a form with validation?

Use `<form>` with input fields and submit button. Validation can be:

- **HTML5 built‑in**: `required`, `pattern`, `type="email"`, `min`, `max`, etc. Browser provides basic validation and error messages.
- **JavaScript validation**: Listen to `submit` event, prevent default, and check values manually. Show custom error messages.

Example:

```html
<form id="myForm">
<input type="text" id="name" required pattern="[A-Za-z]{3,}">
<input type="email" id="email" required>
<button type="submit">Submit</button>
</form>
<script>
document.getElementById('myForm').addEventListener('submit', (e) => {
if (!document.getElementById('name').checkValidity()) {
e.preventDefault();
alert('Name must be at least 3 letters');
}
});
</script>

```

[↑ Back to top](#table-of-contents)

### 162. How do you implement drag and drop using native APIs?

Native HTML5 drag‑and‑drop uses `dragstart`, `dragend`, `dragover`, `drop` events. You need to set `draggable="true"` on draggable elements, and call `preventDefault` on `dragover` to enable drop.

Example:

```html
<div draggable="true" ondragstart="dragStart(event)">Drag me</div>
<div ondrop="drop(event)" ondragover="allowDrop(event)">Drop here</div>
<script>
function dragStart(e) { e.dataTransfer.setData('text/plain', e.target.id); }
function allowDrop(e) { e.preventDefault(); }
function drop(e) {
e.preventDefault();
const data = e.dataTransfer.getData('text/plain');
const dragged = document.getElementById(data);
e.target.appendChild(dragged);
}
</script>
```

For more complex drag‑and‑drop, consider libraries like `react-dnd` or `dnd-kit`.

[↑ Back to top](#table-of-contents)

### 163. Implement abstraction?

– wrap external libraries in your own adapter components to isolate changes.

[↑ Back to top](#table-of-contents)

### 164. Implement accessibility?

– proper ARIA roles, keyboard navigation, focus management.

[↑ Back to top](#table-of-contents)

### 165. What is the output of `0.1 + 0.2 === 0.3` and why?

`false`. JavaScript uses IEEE 754 double-precision floating point. `0.1 + 0.2` is `0.30000000000000004`. Binary can't represent 0.1 or 0.2 exactly. Fix: `Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON`, or use `toFixed()` for display, or use integer arithmetic (work in cents not dollars).

[↑ Back to top](#table-of-contents)

### 166. What is the output of the following code? `// As a STATEMENT (in console or at top level): {} + [] // As an EXPRE...`?

```javascript
// As a STATEMENT (in console or at top level):
{} + []
// As an EXPRESSION:
console.log({} + []);
```

**Output:**
```

0           // as statement — {} is a block, + [] is unary plus on [] = 0
"[object Object]"  // as expression inside console.log
```

**Explanation:** When `{}` appears at the START of a statement, JS parses it as an empty block, not an object literal. So `{} + []` becomes `+([] )` which is `+""` = `0`. Inside an expression context (like `console.log`), `{}` is an object.

[↑ Back to top](#table-of-contents)

### 167. What is the output of the following code? `console.log("" == false); console.log("" === false); console.log(0 == ...`?

```javascript
console.log("" == false);
console.log("" === false);
console.log(0 == false);
console.log("0" == false);
console.log("" == 0);
```

**Output:**
```

true
false
true
true
true
```

**Explanation:** `"" == false` → `"" == 0` (boolean to number) → `0 == 0` → `true`. `"0" == false` → `"0" == 0` → `0 == 0` → `true`. The `===` check fails because types differ.

[↑ Back to top](#table-of-contents)

### 168. What is the output of the following code? `console.log("5" - 3); console.log("5" + 3); console.log("5" - "3"); co...`?

```javascript
console.log("5" - 3);
console.log("5" + 3);
console.log("5" - "3");
console.log("5" * "3");
console.log(5 + "3");
console.log(5 - "3");
```

**Output:**
```

2
53
2
15
53
2
```

**Explanation:** `-`, `*`, `/` always convert to numbers. `+` is special: if either operand is a string, it concatenates. `"5" + 3` = `"53"` (string wins), but `5 + "3"` = `"53"` too. `-` forces numeric conversion so `"5" - 3 = 2`.

[↑ Back to top](#table-of-contents)

### 169. What is the output of the following code? `console.log(0 || 'default'); console.log(0 ?? 'default'); console.log(...`?

```javascript
console.log(0 || 'default');
console.log(0 ?? 'default');
console.log('' || 'default');
console.log('' ?? 'default');
console.log(null || 'default');
console.log(null ?? 'default');
console.log(false || 'default');
console.log(false ?? 'default');
```

**Output:**
```

default     // || treats 0 as falsy
0           // ?? only checks for null/undefined
default     // || treats '' as falsy
''          // ?? only checks for null/undefined
default
default
default
false       // ?? only checks for null/undefined
```

**Explanation:** `??` (nullish coalescing) only falls back when the left side is `null` or `undefined`. `0`, `''`, and `false` are valid values for `??`. `||` treats all falsy values as triggers for the fallback.

[↑ Back to top](#table-of-contents)

### 170. What is the output of the following code? `console.log(0.1 + 0.2 === 0.3); console.log(0.1 + 0.2);...`?

```javascript
console.log(0.1 + 0.2 === 0.3);
console.log(0.1 + 0.2);
```

**Output:**
```

false
0.30000000000000004
```

**Explanation:** JavaScript uses IEEE 754 double-precision floating-point. Neither `0.1` nor `0.2` can be represented exactly in binary. Their sum has a rounding error. Fix: `Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON`.

[↑ Back to top](#table-of-contents)

### 171. What is the output of the following code? `console.log(1 < 2 < 3); console.log(3 > 2 > 1);...`?

```javascript
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

**Output:**
```

true
false
```

**Explanation:** Left-to-right evaluation. `1 < 2` = `true`, then `true < 3` → `1 < 3` = `true`. For second: `3 > 2` = `true`, then `true > 1` → `1 > 1` = `false`. Common interview trick — JS doesn't support chained comparisons like Python.

[↑ Back to top](#table-of-contents)

### 172. What is the output of the following code? `console.log(1 == '1'); console.log(1 === '1'); console.log(1 == true);...`?

```javascript
console.log(1 == '1');
console.log(1 === '1');
console.log(1 == true);
console.log(1 === true);
console.log(0 == false);
console.log(0 === false);
console.log('' == false);
console.log('' === false);
console.log(null == false);
console.log(null == 0);
console.log(null == undefined);
console.log(null === undefined);
```

**Output:**
```

true   false
true   false
true   false
true   false
false  false  ← null is special
false
true   false
```

**Detailed output:**
```

true, false, true, false, true, false, true, false, false, false, true, false
```

**Explanation:** `==` coercion rules: number vs string → convert string to number. boolean → convert to number. null/undefined only equal each other (and nothing else) with `==`.

[↑ Back to top](#table-of-contents)

### 173. What is the output of the following code? `console.log(5 & 3); console.log(5 | 3); console.log(5 ^ 3); console.lo...`?

```javascript
console.log(5 & 3);
console.log(5 | 3);
console.log(5 ^ 3);
console.log(~5);
console.log(5 << 1);
console.log(20 >> 2);
```

**Output:**
```

1    // 101 & 011 = 001
7    // 101 | 011 = 111
6    // 101 ^ 011 = 110
-6   // ~5 = -(5+1)
10   // shift left by 1 = multiply by 2
5    // shift right by 2 = divide by 4
```

**Explanation:** Bitwise AND, OR, XOR on binary representations. `~n` = `-(n+1)` (bitwise NOT). `<< n` multiplies by `2^n`. `>> n` divides by `2^n` (integer division). Often used for performance tricks and flags.

[↑ Back to top](#table-of-contents)

### 174. What is the output of the following code? `console.log([10, 9, 2, 1, 100].sort()); console.log([10, 9, 2, 1, 100]...`?

```javascript
console.log([10, 9, 2, 1, 100].sort());
console.log([10, 9, 2, 1, 100].sort((a, b) => a - b));
console.log(['banana', 'apple', 'cherry'].sort());
```

**Output:**
```

[1, 10, 100, 2, 9]
[1, 2, 9, 10, 100]
['apple', 'banana', 'cherry']
```

**Explanation:** Default `sort()` converts to strings and sorts lexicographically. `"10"` comes before `"2"` because `"1" < "2"`. Always provide a comparator for numeric sorting.

[↑ Back to top](#table-of-contents)

### 175. What is the output of the following code? `console.log([] + []); console.log([] + {}); console.log({} + []); // a...`?

```javascript
console.log([] + []);
console.log([] + {});
console.log({} + []);   // as expression
```

**Output:**
```

""
"[object Object]"
"[object Object]"
```

**Explanation:** Arrays convert to `""` (empty string) via `toString()`. Objects convert to `"[object Object]"`. `[] + []` = `"" + ""` = `""`. `[] + {}` = `"" + "[object Object]"` = `"[object Object]"`. As an expression, `{} + []` treats `{}` as an empty object (not a block), so same result. (As a statement, see Q9.)

[↑ Back to top](#table-of-contents)

### 176. What is the output of the following code? `console.log([] + []); console.log([] + {}); console.log({} + []); cons...`?

```javascript
console.log([] + []);
console.log([] + {});
console.log({} + []);
console.log(+[]);
console.log(+{});
console.log(+null);
console.log(+undefined);
console.log(+'');
console.log(+' ');
console.log(+true);
console.log(+false);
```

**Output:**
```

""               // [] → "" + [] → "" = ""
"[object Object]" // [] → "" + {} → "[object Object]"
"[object Object]" // as expression: {} is object, not block
0                // +[] → +"" → 0
NaN              // +{} → +"[object Object]" → NaN
0                // +null → 0
NaN              // +undefined → NaN
0                // +"" → 0
0                // +" " → 0 (whitespace string trims to empty)
1                // +true → 1
0                // +false → 0
```

[↑ Back to top](#table-of-contents)

### 177. What is the output of the following code? `console.log(null == undefined); console.log(null === undefined); conso...`?

```javascript
console.log(null == undefined);
console.log(null === undefined);
console.log(null == 0);
console.log(null == false);
console.log(undefined == false);
```

**Output:**
```

true
false
false
false
false
```

**Explanation:** `null == undefined` is `true` by spec — it's a special case. `null` and `undefined` only loosely equal each other, nothing else. `null` does NOT coerce to `0` or `false` in `==` comparisons. `undefined` similarly does not coerce.

[↑ Back to top](#table-of-contents)

### 178. What is the output of the following code? `console.log(true + false); console.log(true + true); console.log(false...`?

```javascript
console.log(true + false);
console.log(true + true);
console.log(false + false);
console.log(true + 1);
console.log(false + 1);
```

**Output:**
```

1
2
0
2
1
```

**Explanation:** Booleans coerce to numbers in arithmetic: `true = 1`, `false = 0`. This is why `true + false = 1 + 0 = 1`.

[↑ Back to top](#table-of-contents)

### 179. What is the output of the following code? `console.log(void 0); console.log(void 'hello'); console.log(void (1 + ...`?

```javascript
console.log(void 0);
console.log(void 'hello');
console.log(void (1 + 2));
console.log(undefined === void 0);
```

**Output:**
```

undefined
undefined
undefined
true
```

**Explanation:** `void` always returns `undefined` regardless of the expression. `void 0` is a reliable way to get `undefined` (in old JS where `undefined` could be overwritten). `void 0 === undefined` is always `true`.

[↑ Back to top](#table-of-contents)

### 180. What is the output of the following code? `function createFunctions() { var result = []; for (var i = 0; i < 3; i...`?

```javascript
function createFunctions() {
var result = [];
for (var i = 0; i < 3; i++) {
result.push(function() { return i; });
}
return result;
}
var fns = createFunctions();
console.log(fns[0]());
console.log(fns[1]());
console.log(fns[2]());
```

**Output:**
```

3
3
3
```

**Explanation:** All functions share the same `var i` from `createFunctions`. After the loop, `i = 3`. All three functions return the same `i`. Fix with `let` or IIFE.

[↑ Back to top](#table-of-contents)

### 181. What is the output of the following code? `function test(a, b, c) { console.log(a, b, c); } test(1, ...[], 2); te...`?

```javascript
function test(a, b, c) {
console.log(a, b, c);
}

test(1, ...[], 2);
test(...[1, 2], 3);
test(...[1, 2, 3, 4]); // Extra args
test(1, ...[2, 3]);
```

**Output:**
```

1 undefined 2   // ...[] spreads nothing, b is undefined
1 2 3
1 2 3           // Extra arg 4 ignored (not in params, goes to arguments)
1 2 3
```

**Explanation:** Spread in function calls inlines the array elements as arguments. `...[]` spreads nothing (empty). Extra arguments beyond params are silently ignored (accessible via `arguments`).

[↑ Back to top](#table-of-contents)

### 182. What is the output of the following code? `try { null.property; } catch (e) { console.log(e instanceof TypeError)...`?

```javascript
try {
null.property;
} catch (e) {
console.log(e instanceof TypeError);
console.log(e.name);
console.log(e.message.includes('null'));
}

try {
undeclaredVar;
} catch (e) {
console.log(e instanceof ReferenceError);
console.log(e.name);
}
```

**Output:**
```

true
TypeError
true
true
ReferenceError
```

**Explanation:** Accessing a property on `null` throws `TypeError`. Referencing an undeclared variable throws `ReferenceError`. Knowing error types helps write targeted error handling.

[↑ Back to top](#table-of-contents)

### 183. What is the output of the following code? `var obj = { x: 1 }; console.log(delete obj.x); console.log(obj.x); var...`?

```javascript
var obj = { x: 1 };
console.log(delete obj.x);
console.log(obj.x);

var y = 5;
console.log(delete y);
console.log(y);

function foo() {}
console.log(delete foo);
```

**Output:**
```

true
undefined
false
5
false
```

**Explanation:** `delete` on object properties works and returns `true`. `delete` on variables declared with `var` returns `false` and doesn't delete them. `delete` on function declarations also returns `false`.

[↑ Back to top](#table-of-contents)
