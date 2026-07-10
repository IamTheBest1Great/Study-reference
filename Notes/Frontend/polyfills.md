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

# Complete Polyfills for Array Methods (Most Asked)

Here are the **complete code implementations** for all 6 most asked array polyfills:

***

## 1️⃣ **Array.map()** - Transform Array Elements

### **What it does:**
Creates a new array by applying a function to each element.

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **new array** (doesn't modify original)
- ✅ Callback receives: `value`, `index`, `array`
- ✅ Length of result = length of original array [dev](https://dev.to/pawan16123/javascript-most-asked-polyfills-25e3)

***

## 2️⃣ **Array.filter()** - Filter Array Elements

### **What it does:**
Creates a new array with elements that pass a test (return true).

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **new array** with only matching elements
- ✅ Callback must return `true` to include element
- ✅ Result length can be less than original [medium](https://medium.com/@aniketbkangane9637/javascript-polyfills-for-map-filter-and-reduce-most-asked-interview-questions-edc20d9ae937)

***

## 3️⃣ **Array.reduce()** - Accumulate Array Values

### **What it does:**
Reduces array to a single value by accumulating.

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **single value** (not array)
- ✅ Takes `initialValue` (optional)
- ✅ Callback receives: `accumulator`, `currentValue`, `index`, `array`
- ✅ If no initialValue, starts with `arr[0]` [medium](https://medium.com/@imPradhyumn/polyfills-for-map-filter-and-reduce-in-7914ea26bf37)

***

## 4️⃣ **Array.forEach()** - Iterate Array

### **What it does:**
Executes callback for each element (no return value).

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **undefined** (no new array)
- ✅ Just executes callback for side effects
- ✅ Callback receives: `value`, `index`, `array` [dev](https://dev.to/umerjaved178/polyfills-for-foreach-map-filter-reduce-in-javascript-1h13)

***

## 5️⃣ **Array.flat()** - Flatten Nested Arrays

### **What it does:**
Flattens nested arrays into a single-level array.

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **new flattened array**
- ✅ `depth` parameter (default = 1)
- ✅ Uses recursion for nested arrays
- ✅ `myFlat(Infinity)` flattens all levels [medium](https://medium.com/@mynkmishra/polyfills-in-javascript-1-3-17d4927ebd49)

***

## 6️⃣ **Array.includes()** - Check Element Exists

### **What it does:**
Checks if array contains a specific element.

### **Polyfill:**
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

### **Key Points:**
- ✅ Returns **boolean** (`true`/`false`)
- ✅ `fromIndex` parameter (default = 0)
- ✅ Handles `NaN` correctly (uses SameValueZero)
- ✅ Negative `fromIndex` works correctly [github](https://github.com/siddhigate/js-polyfills)

***

## 📊 **Comparison Table**

| Method | Returns | Modifies Original | Callback Params |
|--------|---------|-------------------|-----------------|
| `map()` | New Array | ❌ No | `value, index, array` |
| `filter()` | New Array | ❌ No | `value, index, array` |
| `reduce()` | Single Value | ❌ No | `acc, value, index, array` |
| `forEach()` | `undefined` | ❌ No | `value, index, array` |
| `flat()` | New Array | ❌ No | None (uses recursion) |
| `includes()` | `boolean` | ❌ No | None (uses loop) |

***



### **Key Differences to Remember:**

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

## ✅ **Complete Test Suite**

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

# Complete Polyfills: Function, Promise & Advanced Methods

Here are the **complete code implementations** for Function methods, Promise methods, and Advanced utility functions:

***

## 📚 **2. Function Methods Polyfills**

### **2.1 Function.call()** - Invoke Function with Context

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

### **2.2 Function.apply()** - Invoke Function with Array Args

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

### **2.3 Function.bind()** - Create Function with Context

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

### **2.4 compare: call vs apply vs bind**

| Method | Executes? | Args Format | Returns |
|--------|-----------|-------------|---------|
| `call()` | ✅ Immediately | Comma-separated | Result |
| `apply()` | ✅ Immediately | Array | Result |
| `bind()` | ❌ Returns function | Comma-separated | Function |

 [rahuulmiishra.medium](https://rahuulmiishra.medium.com/interviewer-write-the-polyfill-of-call-apply-and-bind-in-2-different-ways-844156550be9)

***

## 📚 **3. Promise Methods Polyfills**

### **3.1 Promise.all()** - Wait for All Promises

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

### **3.2 Promise.allSettled()** - Wait for All (Success/Error)

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

### **3.3 Promise.any()** - First Successful Promise

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

### **3.4 Promise.race()** - First Resolved Promise

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

### **3.5 compare: Promise Methods**

| Method | Resolves When | Rejects When |
|--------|---------------|--------------|
| `all()` | All succeed | Any fails |
| `allSettled()` | All settle | Never (always resolves) |
| `any()` | First succeeds | All fail |
| `race()` | First completes | First rejects |

 [dev](https://dev.to/mandy8055/which-promise-method-do-you-need-da9)

***

## 📚 **4. Advanced Utility Polyfills**

### **4.1 debounce()** - Delay Execution Until Gap

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

### **4.2 throttle()** - Limit Execution Frequency

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

### **4.3 deepCopy()** - Clone Object Recursively

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

### **4.4 deepMerge()** - Merge Objects Recursively

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

### **4.5 flatten()** - Flatten Nested Arrays (Alternative)

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

### **4.6 useEffect()** - React Hook Polyfill (Simplified)

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

## 🎯 **Interview Priority**

### **Must Know:**
1. ✅ `call()` / `apply()` / `bind()`
2. ✅ `Promise.all()`
3. ✅ `debounce()` / `throttle()`

### **Should Know:**
4. ✅ `Promise.allSettled()` / `any()` / `race()`
5. ✅ `deepCopy()`

### **Nice to Know:**
6. ✅ `deepMerge()` / `flatten()`

***
