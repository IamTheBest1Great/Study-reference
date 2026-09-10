If you're preparing for a **React developer coding interview**, the coding questions are usually much more practical than DSA-heavy. Interviewers often give you a small UI/problem and ask you to implement it in React.

For **React + JavaScript**, these are the most frequently useful problems to practice.

# 🔥 Most Frequent React Coding Interview Questions

## 1. Counter

**Question:** Create a counter with increment, decrement, and reset.

Tests:

* `useState`
* Event handling
* Functional components

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>+</button>
<button onClick={() => setCount(count - 1)}>-</button>
<button onClick={() => setCount(0)}>Reset</button>
```

**Difficulty:** ⭐

---

## 2. Todo List ⭐⭐⭐

Probably one of the **most common React coding questions**.

Requirements might be:

* Add todo
* Delete todo
* Mark complete
* Edit todo
* Filter completed/pending

Example:

```text
Todo App

[ Learn React        ] [Add]

☐ Learn React       🗑
☑ Learn JavaScript  🗑
☐ Learn Spring Boot 🗑
```

Tests:

* `useState`
* Arrays
* `map()`
* `filter()`
* Controlled inputs
* Component design

---

## 3. Search / Filter List ⭐⭐⭐

Given:

```js
const users = [
  { name: "John" },
  { name: "Alice" },
  { name: "Bob" }
];
```

Create a search box that filters users as the user types.

```text
Search: [ ali       ]

Alice
```

Tests:

* State
* Controlled components
* `filter()`
* Conditional rendering

---

# 4. Fetch API Data ⭐⭐⭐

Very common.

> Fetch users from an API and display them.

You should know:

```jsx
useEffect(() => {
    fetch("/api/users")
        .then(res => res.json())
        .then(data => setUsers(data))
        .catch(error => setError(error));
}, []);
```

But interviewers may add requirements:

```text
Loading...
    ↓
API request
    ↓
Success → Display users

Failure → Show error
```

They may ask you to implement:

* Loading state
* Error state
* Empty state
* Retry
* API call on button click

---

# 5. Debounced Search ⭐⭐⭐

A very good interview problem.

Imagine:

```text
Search GitHub users

[ shubham       ]
```

Don't make an API request on **every keystroke**.

Instead:

```text
s       → wait
sh      → wait
shu     → wait
shub    → wait
shubh   → wait
```

After the user stops typing for, say, 500 ms:

```text
            ↓
       API request
```

Tests:

* `useEffect`
* `setTimeout`
* Cleanup function
* API calls
* Understanding of performance

Example concept:

```jsx
useEffect(() => {
    const timer = setTimeout(() => {
        searchUsers(query);
    }, 500);

    return () => clearTimeout(timer);
}, [query]);
```

**Very worth practicing.**

---

# 6. Pagination ⭐⭐⭐

> Fetch 100 users but display 10 per page.

```text
Users

John
Alice
Bob
...

< Previous   1 2 3 4 5   Next >
```

They may ask you to implement:

* Page number
* Next/Previous
* API pagination
* Disable buttons appropriately

Tests:

* State management
* Array manipulation
* API integration

---

# 7. Modal / Popup ⭐⭐

Create:

```text
        ┌──────────────────────┐
        │       Profile        │
        │                      │
        │   John Doe           │
        │   Developer          │
        │                      │
        │        [ Close ]     │
        └──────────────────────┘
```

Tests:

* Conditional rendering
* State
* Event handling
* Component composition

---

# 8. Accordion ⭐⭐

Example:

```text
What is React?             ▼

What is useState?          ▶

What is useEffect?         ▶

What is Virtual DOM?       ▶
```

Clicking a question expands its answer.

Tests:

* State
* Conditional rendering
* Lists
* Component design

---

# 9. Tabs ⭐⭐

```text
[ Profile ] [ Posts ] [ Settings ]

--------------------------------
Profile information...
```

Clicking tabs changes the displayed content.

Tests:

* State
* Conditional rendering
* Reusable components

---

# 10. Form Validation ⭐⭐⭐

Extremely common.

Example:

```text
Register

Name:
[____________]

Email:
[____________]

Password:
[____________]

        [ Register ]
```

Validate:

```text
❌ Email is required
❌ Invalid email
❌ Password must contain 8 characters
```

Tests:

* Controlled inputs
* Form events
* Validation
* Error handling

---

# 11. Password Show / Hide ⭐

```text
Password: [ ******** ] 👁
```

Click the eye:

```text
Password: [ MyPassword123 ] 👁
```

Simple but frequently used as a warm-up.

---

# 12. Star Rating ⭐⭐

Create:

```text
Rating:

☆ ☆ ☆ ☆ ☆
```

Click:

```text
★ ★ ★ ★ ☆
```

Tests:

* State
* Events
* Rendering lists
* Conditional styling

---

# 13. Shopping Cart ⭐⭐⭐

This is a very good **intermediate React interview problem**.

```text
Products

Laptop       ₹50,000    [Add]
Mouse        ₹1,000     [Add]
Keyboard     ₹2,000     [Add]


Cart

Laptop       1    ₹50,000
Mouse        2    ₹2,000

Total: ₹52,000
```

Requirements:

* Add product
* Remove product
* Increase quantity
* Decrease quantity
* Calculate total

Tests:

* State management
* Array operations
* Derived state
* Component architecture

---

# 14. Like / Favorite Button ⭐

```text
❤️ 123
```

Click:

```text
❤️ 124
```

Click again:

```text
♡ 123
```

Sounds easy, but interviewers can use it to test state handling.

---

# 15. Infinite Scroll ⭐⭐⭐

Display:

```text
Item 1
Item 2
...
Item 20

        ↓ scroll

Item 21
...
Item 40
```

When the user reaches the bottom:

```text
       ↓
Load more
       ↓
API request
       ↓
Append data
```

Tests:

* `useEffect`
* Scroll handling / `IntersectionObserver`
* API calls
* State updates
* Performance

---

# 16. Auto-Suggestion Search ⭐⭐⭐

Example:

```text
Search:
[ jav ]

Suggestions:

Java
JavaScript
Java Spring
JavaFX
```

Tests:

* Controlled input
* Filtering
* Conditional rendering
* Debouncing

---

# 17. Stopwatch / Timer ⭐⭐

```text
00:15:32

[Start] [Pause] [Reset]
```

Tests:

* `useEffect`
* `setInterval`
* Cleanup
* State

Very useful for understanding React's lifecycle.

---

# 18. Countdown Timer ⭐⭐

```text
Enter seconds:

[ 60 ]

[Start]

59
58
57
...
0

Time's up!
```

---

# 19. Theme Switcher ⭐⭐

```text
☀️ Light
🌙 Dark
```

Clicking changes the application's theme.

Could be implemented using:

* State
* Context API
* CSS classes

For senior interviews, they may ask you to implement it using **Context**.

---

# 20. `useLocalStorage` Custom Hook ⭐⭐⭐

They may ask:

> Create a custom hook that stores state in localStorage.

For example:

```jsx
const [theme, setTheme] = useLocalStorage("theme", "dark");
```

When the page refreshes:

```text
theme → dark
```

Tests:

* Custom hooks
* `useState`
* `useEffect`
* Browser APIs

---

# 21. Build Your Own `useDebounce` ⭐⭐⭐

Instead of simply implementing debouncing inside a component:

```jsx
const debouncedValue = useDebounce(search, 500);
```

Then:

```jsx
useEffect(() => {
    searchAPI(debouncedValue);
}, [debouncedValue]);
```

This is a **very good interview question** because it tests whether you understand hooks rather than just copying patterns.

---

# 22. Build Your Own `useFetch` ⭐⭐⭐

Example:

```jsx
const {
    data,
    loading,
    error
} = useFetch("/api/users");
```

Internally:

```text
useFetch
   │
   ├── API request
   ├── loading
   ├── data
   └── error
```

This tests custom hooks and API handling.

---

# 23. Parent → Child → Parent Communication ⭐⭐

Example:

```text
Parent
  │
  ├── sends data ──────→ Child
  │
  ←── callback ───────── Child
```

Question:

> Create a parent component and child component where the child can update the parent's state.

Tests:

* Props
* Callback functions
* State lifting

---

# 24. Reusable Button / Input Component ⭐⭐

They may give you:

```jsx
<Button type="primary" loading={true}>
    Submit
</Button>
```

and ask you to create a reusable component.

Tests:

* Props
* Component composition
* Reusability
* Conditional rendering

---

# 25. Table with Sorting + Filtering ⭐⭐⭐⭐

This is a **very realistic frontend interview task**.

Given:

```text
Users

Search: [__________]

Name          Age       Salary
--------------------------------
Alice         25        50,000
Bob           31        70,000
John          22        40,000
```

Click `Salary`:

```text
Salary ↑
```

Sort ascending/descending.

Add:

* Search
* Sorting
* Pagination
* Loading
* Empty state

This combines many React concepts.

---

# 🔥 What Interviewers Commonly Combine

The real interview usually isn't:

> "Build a counter."

Instead, they may give you something like:

### Example interview task

> Build a user management page.

Requirements:

```text
                 User Management

Search: [_____________]    [Add User]

------------------------------------------------
Name       Email             Role       Actions
------------------------------------------------
John       john@gmail       Admin      Edit
Alice      alice@gmail      User       Edit
Bob        bob@gmail        User       Edit
------------------------------------------------

        < 1 2 3 4 5 >
```

Then progressively add:

### Round 1

Display users.

### Round 2

Add search.

### Round 3

Add sorting.

### Round 4

Add pagination.

### Round 5

Fetch data from API.

### Round 6

Add loading/error states.

### Round 7

Add edit modal.

### Round 8

Ask:

> How would you optimize this if there were 100,000 users?

That's where they start testing **engineering ability**, not just React syntax.

---

# 🎯 If You Have Limited Time

I'd practice these **15 problems in this exact order**:

| #  | Problem                     | Priority |
| -- | --------------------------- | -------- |
| 1  | Counter                     | ⭐        |
| 2  | Todo List                   | 🔥🔥🔥   |
| 3  | Search/Filter               | 🔥🔥🔥   |
| 4  | API Fetch + Loading/Error   | 🔥🔥🔥   |
| 5  | Form Validation             | 🔥🔥🔥   |
| 6  | Debounced Search            | 🔥🔥🔥🔥 |
| 7  | Pagination                  | 🔥🔥🔥   |
| 8  | Modal                       | 🔥🔥     |
| 9  | Tabs                        | 🔥🔥     |
| 10 | Accordion                   | 🔥🔥     |
| 11 | Shopping Cart               | 🔥🔥🔥🔥 |
| 12 | Table + Sorting + Filtering | 🔥🔥🔥🔥 |
| 13 | Infinite Scroll             | 🔥🔥🔥   |
| 14 | Custom `useDebounce`        | 🔥🔥🔥🔥 |
| 15 | Custom `useFetch`           | 🔥🔥🔥🔥 |

### And alongside these, make sure your JavaScript is strong in:

```text
map()
filter()
reduce()
find()
some()
every()
sort()
spread operator
destructuring
closures
Promises
async/await
event loop
debouncing
throttling
```

Because in a React coding interview, **weak JavaScript often becomes the bottleneck even when your React knowledge is good**.

If you're targeting **Java + Spring Boot + React full-stack roles**, I'd prepare these React problems alongside your Java/Spring Boot interview preparation rather than treating React as a separate topic.
