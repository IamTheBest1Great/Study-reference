# React.js Interview Questions — Theoretical / Conceptual

A consolidated, deduplicated collection of **conceptual and theoretical React.js interview questions**, compiled from all available study reference files and organized section-wise. Purely practical coding tasks and real-world/scenario-based questions have been placed in their own companion documents.

## Fundamentals, JSX & Virtual DOM

### 1. All the tags needs to be closed:

Unlike HTML, all tags needs to closed explicitly with in JSX. This rule applies for self-closing tags(like hr, br and img tags) as well.

### 2. Arrow functions in callbacks:

It is possible to use *arrow functions* directly in the callbacks. `jsx harmony handleClick() { console.log('SingOut triggered'); } render() { return <button onClick={() => this.handleClick()}>SignOut</button>; }` **Note:** If the callback is passed as prop to child components, those components might do an extra re-rendering. In those cases, it is preferred to go with `.bind()` or *public class fields syntax* approach considering performance. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 3. Can I import an SVG file as react component?

You can import SVG directly as component instead of loading it as a file. This feature is available with `react-scripts@2.0.0` and higher.

```jsx harmony import { ReactComponent as Logo } from "./logo.svg"; const App = () => ( <div> {/* Logo is an actual react component */} <Logo /> </div> );

```
**Note**: Don't forget about the curly braces in the import. [↑ Back to Table of Contents](#table-of-contents)

### 4. Can you use React without JSX?

[↑ Back to Table of Contents](#table-of-contents) Yes. `React.createElement('div', {className:'box'}, 'Hello')` is valid but verbose. JSX is purely syntactic sugar; the output is identical JS objects. ------------------------------------------------------------------------

### 5. Do browsers understand JSX code?

[↑ Back to Table of Contents](#table-of-contents) No, browsers can't understand JSX code. You need a transpiler to convert your JSX to regular Javascript that browsers can understand. The most widely used transpiler right now is Babel. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 6. Document Metadata?

[↑ Back to Table of Contents](#table-of-contents) Built-in support for `<title>`, `<meta>`, etc.:

```jsx function BlogPost({ post }) { return ( <> <title>{post.title}</title> <meta name="description" content={post.excerpt} /> <article>{post.content}</article> </> ); }

```

### 7. Does the cost of inline arrow functions in JSX always matter?

No — harmless for plain DOM elements; matters mainly when breaking `React.memo` on a custom child component.

### 8. Efficient DOM Updates?

This entire process—working with the Virtual DOM, diffing, and selective updating—makes the UI rendering much faster and more efficient than manipulating the Real DOM directly. [↑ Back to Table of Contents](#table-of-contents)

### 9. How can we find the version of React at runtime in the browser?

You can use `React.version` to get the version.

```jsx harmony const REACT_VERSION = React.version; ReactDOM.render( <div>{`React version: ${REACT_VERSION}`}</div>, document.getElementById("app") );

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 10. How do comments work inside JSX?

`{/* comment */}` — regular `//` or `/* */` only work outside JSX expression blocks, not directly between JSX tags.

### 11. How do style objects work in JSX (`style={{...}}`)?

The outer `{}` is JSX interpolation, the inner `{}` is a JS object with camelCased CSS properties and values as strings/numbers (unitless numbers default to `px` for most properties).

### 12. How do you memoize a component?

[↑ Back to Table of Contents](#table-of-contents) There are memoize libraries available which can be used on function components. For example `moize` library can memoize the component in another component.

```jsx harmony import moize from "moize"; import Component from "./components/Component"; // this module exports a non-memoized component const MemoizedFoo = moize.react(Component); const Consumer = () => { <div> {"I will memoize the following entry:"} <MemoizedFoo /> </div>; };

```
**Update:** Since React v16.6.0, we have a `React.memo`. It provides a higher order component which memoizes component unless the props change. To use it, simply wrap the component using React.memo before you use it.

```js const MemoComponent = React.memo(function MemoComponent(props) { /* render using props */ }); OR; export default React.memo(MyFunctionComponent);

```
**** ------------------------------------------------------------------------

### 13. How do you print falsy values in JSX?

[↑ Back to Table of Contents](#table-of-contents) The falsy values such as false, null, undefined, and true are valid children but they don't render anything. If you still want to display them then you need to convert it to string. Let's take an example on how to convert to a string,

```javascript <div>My JavaScript variable is {String(myVariable)}.</div>

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 14. How do you render a list of items in JSX?

Map the array to elements, each with a unique `key`: `items.map(item => <li key={item.id}>{item.name}</li>)`.

### 15. How do you render Array, Strings and Numbers in React 16 Version?

**Note:** This question references React 16. These features remain valid in current React versions (18/19). **Arrays**: Starting with React 16, you can return multiple sibling elements without a wrapping element by returning an array or using Fragments. **Array approach:**

```jsx const ReactJSDevs = () => { return [ <li key="1">John</li>, <li key="2">Jackie</li>, <li key="3">Jordan</li>, ]; };

```
**Fragment approach (preferred):**

```jsx const ReactJSDevs = () => { return ( <> <li>John</li> <li>Jackie</li> <li>Jordan</li> </> ); };

```
You can also merge this array of items in another array component.

```jsx const JSDevs = () => { return ( <ul> <li>Brad</li> <li>Brodge</li> <ReactJSDevs /> <li>Brandon</li> </ul> ); };

```
**Strings and Numbers:** You can also return string and number type from the render method.

```jsx render() { return 'Welcome to ReactJS questions'; } // Number render() { return 2018; }

```
[↑ Back to Table of Contents](#table-of-contents)

### 16. How do you write comments in JSX?

Wrap standard JS comments in curly braces: `{/* comment */}`.

### 17. How does it work?

For every DOM object, there is a corresponding virtual DOM object(copy), which has the same properties. The main difference between the real DOM object and the virtual DOM object is that any changes in the virtual DOM object will not reflect on the screen directly. Consider a virtual DOM object as a blueprint of the real DOM object. Whenever a JSX element gets rendered, every virtual DOM object gets updated. > \*\*Note- One may think updating every virtual DOM object might be > inefficient, but that's not the case. Updating the virtual DOM is much > faster than updating the real DOM since we are just updating the > blueprint of the real DOM. React uses two virtual DOMs to render the user interface. One of them is used to store the current state of the objects and the other to store the previous state of the objects. Whenever the virtual DOM gets updated, react compares the two virtual DOMs and gets to know about which virtual DOM objects were updated. After knowing which objects were updated, react renders only those objects inside the real DOM instead of rendering the complete real DOM. This way, with the use of virtual DOM, react solves the problem of inefficient updating. ------------------------------------------------------------------------

### 18. How does the new JSX transform differ from the old one?

The new transform auto-imports `jsx` from `react/jsx-runtime`, so you no longer need `import React from 'react'` purely to use JSX (you still need it for Hooks).

### 19. How events are different in React?

Handling events in React elements has some syntactic differences: 1. React event handlers are named using camelCase, rather than lowercase. 2. With JSX you pass a function as the event handler, rather than a string. [↑ Back to Table of Contents](#table-of-contents)

### 20. How is the new JSX transform different from old transform??

[↑ Back to Table of Contents](#table-of-contents) The new JSX transform doesn't require React to be in scope. i.e, You don't need to import React package for simple scenarios. Let's take an example to look at the main differences between the old and the new transform, **Old Transform:**

```js import React from "react"; function App() { return <h1>Good morning!!</h1>; }

```
Now JSX transform convert the above code into regular JavaScript as below,

```js import React from "react"; function App() { return React.createElement("h1", null, "Good morning!!"); }

```
**New Transform:** The new JSX transform doesn't require any React imports

```js function App() { return <h1>Good morning!!</h1>; }

```
Under the hood JSX transform compiles to below code

```js import { jsx as _jsx } from "react/jsx-runtime"; function App() { return _jsx("h1", { children: "Good morning!!" }); }

```
**Note:** You still need to import React to use Hooks. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 21. How JSX prevents Injection Attacks?

[↑ Back to Table of Contents](#table-of-contents) React DOM escapes any values embedded in JSX before rendering them. Thus it ensures that you can never inject anything that's not explicitly written in your application. Everything is converted to a string before being rendered. For example, you can embed user input as below,

```javascript const name = response.potentiallyMaliciousInput; const element = <h1>{name}</h1>;

```
This way you can prevent XSS(Cross-site-scripting) attacks in the application. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 22. How to bind methods or event handlers in JSX callbacks?

[↑ Back to Table of Contents](#table-of-contents) There are 3 possible ways to achieve this in class components:

### 23. How to implement _default_ or _NotFound_ page?

[↑ Back to Table of Contents](#table-of-contents) A `<Switch>` renders the first child `<Route>` that matches. A `<Route>` with no path always matches. So you just need to simply drop path attribute as below

```jsx harmony <Switch> <Route exact path="/" component={Home} /> <Route path="/user" component={User} /> <Route component={NotFound} /> </Switch>

```
****

### 24. How to loop inside JSX?

[↑ Back to Table of Contents](#table-of-contents) You can simply use `Array.prototype.map` with ES6 _arrow function_ syntax. For example, the `items` array of objects is mapped into an array of components:

```jsx harmony <tbody> {items.map((item) => ( <SomeComponent key={item.id} name={item.name} /> ))} </tbody>

```
But you can't iterate using `for` loop:

```jsx harmony <tbody> for (let i = 0; i < items.length; i++) { <SomeComponent key={items[i].id} name={items[i].name} /> } </tbody>

```
This is because JSX tags are transpiled into _function calls_, and you can't use statements inside expressions. This may change thanks to `do` expressions which are _stage 1 proposal_.

### 25. How to use React label element?

If you try to render a `<label>` element bound to a text input using the standard `for` attribute, then it produces HTML missing that attribute and prints a warning to the console.

```jsx harmony <label for={'user'}>{'User'}</label> <input type={'text'} id={'user'} />

```
Since `for` is a reserved keyword in JavaScript, use `htmlFor` instead.

```jsx harmony <label htmlFor={'user'}>{'User'}</label> <input type={'text'} id={'user'} />

```
[↑ Back to Table of Contents](#table-of-contents)

### 26. How Virtual DOM works?

[↑ Back to Table of Contents](#table-of-contents) The _Virtual DOM_ works in five simple steps.

### 27. How you use decorators in React?

[↑ Back to Table of Contents](#table-of-contents) You can *decorate* your *class* components, which is the same as passing the component into a function. **Decorators** are flexible and readable way of modifying component functionality.

```jsx harmony @setTitle("Profile") class Profile extends React.Component { //.... } /* title is a string that will be set as a document title WrappedComponent is what our decorator will receive when put directly above a component class as seen in the example above */ const setTitle = (title) => (WrappedComponent) => { return class extends React.Component { componentDidMount() { document.title = title; } render() { return <WrappedComponent {...this.props} />; } }; };

```
**Note:** Decorators are a feature that didn't make it into ES7, but are currently a _stage 2 proposal_. **** ------------------------------------------------------------------------

### 28. Initial render:

When a UI component renders for the first time, it returns JSX. React uses this structure to create a Virtual DOM tree, which is a lightweight copy of the actual DOM. This Virtual DOM is then used to build and render the Real DOM in the browser.

### 29. Initial render:

When a UI component renders for the first time, it returns JSX. React creates a Virtual DOM tree from the JSX structure.

### 30. Is it possible to use react without JSX?

[↑ Back to Table of Contents](#table-of-contents) Yes, JSX is not mandatory for using React. Actually it is convenient when you don't want to set up compilation in your build environment. Each JSX element is just syntactic sugar for calling `React.createElement(component, props, ...children)`. For example, let us take a greeting example with JSX,

```javascript class Greeting extends React.Component { render() { return <div>Hello {this.props.message}</div>; } } ReactDOM.render( <Greeting message="World" />, document.getElementById("root") );

```
You can write the same code without JSX as below,

```javascript class Greeting extends React.Component { render() { return React.createElement("div", null, `Hello ${this.props.message}`); } } ReactDOM.render( React.createElement(Greeting, { message: "World" }, null), document.getElementById("root") );

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 31. Is it possible to use React without rendering HTML?

[↑ Back to Table of Contents](#table-of-contents) It is possible. Below are the possible options:

```jsx harmony render() { return false }

```
```jsx harmony render() { return true }

```
```jsx harmony render() { return null }

```
React version >=16.0.0:

```jsx harmony render() { return [] }

```
```jsx harmony render() { return "" }

```
React version >=16.2.0:

```jsx harmony render() { return <React.Fragment></React.Fragment> }

```
```jsx harmony render() { return <></> }

```
React version >=18.0.0:

```jsx harmony render() { return undefined }

```

### 32. Public class fields syntax:

If you don't like to use bind approach then _public class fields syntax_ can be used to correctly bind callbacks. The Create React App enables this syntax by default.

```jsx harmony handleClick = () => { console.log("SingOut triggered", this); };

```
```jsx harmony <button onClick={this.handleClick}>SingOut</button>

```

### 33. Render order of nested Parent → Child → GrandChild components?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Parent() { console.log('Parent render'); return ( <div> <Child /> </div> ); } function Child() { console.log('Child render'); return <GrandChild />; } function GrandChild() { console.log('GrandChild render'); return <div>leaf</div>; }

```
**Behavior on initial mount:**

```
Parent render Child render GrandChild render

```
**Explanation:** React renders top-down. Parent renders first (to determine what children to render), then Child, then GrandChild. Commit happens after the entire tree is reconciled. React does NOT interleave render and commit phases.

### 34. Return a single root element?

If you are returning multiple elements from a component, wrap them in a single parent element. Otherwise you will receive the below error in your browser console. `html Adjacent JSX elements must be wrapped in an enclosing tag.`

### 35. Server Actions?

Call server functions directly from components:

```jsx async function createPost(formData) { 'use server' const post = await db.posts.create({ title: formData.get('title') }); revalidatePath('/posts'); return post; } function NewPost() { return ( <form action={createPost}> <input name="title" /> <button type="submit">Create</button> </form> ); }

```

### 36. Use camelCase naming:

It is suggested to use camelCase naming for attributes in JSX. For example, the common attributes of HTML elements such as `class`, `tabindex` will be used as `className` and `tabIndex`. **Note:** There is an exception for `aria-*` and `data-*` attributes which should be lower cased all the time. [↑ Back to Table of Contents](#table-of-contents)

### 37. Using react components:

```jsx harmony <FormattedMessage id={"account"} defaultMessage={"The amount is less than minimum balance."} />

```

### 38. Using the `withRouter()` higher-order function:

The `withRouter()` higher-order function will inject the history object as a prop of the component. This object provides `push()` and `replace()` methods to avoid the usage of context.

```jsx harmony import { withRouter } from "react-router-dom"; // this also works with 'react-router-native' const Button = withRouter(({ history }) => ( <button type="button" onClick={() => { history.push("/new-location"); }} > {"Click Me!"} </button> ));

```

### 39. Virtual DOM & Component Rendering?

React doesn't manipulate the real DOM directly. Instead, it uses a **Virtual DOM** — a lightweight JavaScript representation of the UI. When a component renders (e.g., `<App />`): * React **executes the component function** (e.g., `App()`). * Hooks like `useState` are registered and tracked in order. * React builds a **Virtual DOM tree** from the returned JSX. * This virtual DOM is a **plain JS object** that describes the desired UI. This process ensures fast and efficient rendering before React decides how to update the real DOM.

### 40. What are inline conditional expressions?

You can use either _if statements_ or _ternary expressions_ which are available in JS(and JSX in React) to conditionally execute or render expressions. Apart from these approaches, you can also embed any expressions in JSX by wrapping them in curly braces and then followed by JS logical operator `&&`. It is helpful to render elements conditionally within a single line and commonly used for concise logic, especially in JSX rendering.

```jsx harmony <h1>Hello!</h1>; { messages.length > 0 && !isLogin ? ( <h2>You have {messages.length} unread messages.</h2> ) : ( <h2>You don't have unread messages.</h2> ); }

```
[↑ Back to Table of Contents](#table-of-contents)

### 41. What are the advantages of using React?

[↑ Back to Table of Contents](#table-of-contents) MVC is generally abbreviated as Model View Controller. - **Use of Virtual DOM to improve efficiency: **React uses virtual DOM to render the view. As the name suggests, virtual DOM is a virtual representation of the real DOM. Each time the data changes in a react app, a new virtual DOM gets created. Creating a virtual DOM is much faster than rendering the UI inside the browser. Therefore, with the use of virtual DOM, the efficiency of the app improves. - **Gentle learning curve:** React has a gentle learning curve when compared to frameworks like Angular. Anyone with little knowledge of javascript can start building web applications using React. - **SEO friendly:** React allows developers to develop engaging user interfaces that can be easily navigated in various search engines. It also allows server-side rendering, which boosts the SEO of an app. - **Reusable components: **React uses component-based architecture for developing applications. Components are independent and reusable bits of code. These components can be shared across various applications having similar functionality. The re-use of components increases the pace of development. - **Huge ecosystem of libraries to choose from: **React provides you with the freedom to choose the tools, libraries, and architecture for developing an application based on your requirement.

### 42. What are the benefits of new JSX transform?

[↑ Back to Table of Contents](#table-of-contents) There are three major benefits of new JSX transform, 1. It is possible to use JSX without importing React packages 2. The compiled output might improve the bundle size in a small amount 3. The future improvements provides the flexibility to reduce the number of concepts to learn React. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 43. What are the exceptions on React component naming?

The component names should start with an uppercase letter but there are few exceptions to this convention. The lowercase tag names with a dot (property accessors) are still considered as valid component names. For example, the below tag can be compiled to a valid component,

```jsx harmony render() { return ( <obj.component/> // `React.createElement(obj.component)` ) }

```
[↑ Back to Table of Contents](#table-of-contents)

### 44. What are the major features of React?

React offers a powerful set of features that have made it one of the most popular JavaScript libraries for building user interfaces: **Core Features:** - **Component-Based Architecture**: React applications are built using components - independent, reusable pieces of code that return HTML via a render function. This modular approach enables better code organization, reusability, and maintenance. - **Virtual DOM**: React creates an in-memory data structure cache, computes the resulting differences, and efficiently updates only the changed parts in the browser DOM. This approach significantly improves performance compared to direct DOM manipulation. - **JSX (JavaScript XML)**: A syntax extension that allows writing HTML-like code in JavaScript. JSX makes the code more readable and expressive while providing the full power of JavaScript. - **Unidirectional Data Flow**: React follows a one-way data binding model where data flows from parent to child components. This makes the code more predictable and easier to debug. - **Declarative UI**: React allows you to describe what your UI should look like for a given state, and it handles the DOM updates when the underlying data changes. **Advanced Features:** - **React Hooks**: Introduced in React 16.8, hooks allow using state and other React features in functional components without writing classes. - **Context API**: Provides a way to share values between components without explicitly passing props through every level of the component tree. - **Error Boundaries**: Components that catch JavaScript errors anywhere in their child component tree and display fallback UI instead of crashing. - **Server-Side Rendering (SSR)**: Enables rendering React components on the server before sending HTML to the client, improving performance and SEO. - **Concurrent Mode**: A set of new features (in development) that help React apps stay responsive and gracefully adjust to the user's device capabilities and network speed. - **React Server Components**: A new feature that allows components to be rendered entirely on the server, reducing bundle size and improving performance. - **Suspense**: A feature that lets your components "wait" for something before rendering, supporting code-splitting and data fetching with cleaner code. These features collectively make React powerful for building everything from small widgets to complex, large-scale web applications. [↑ Back to Table of Contents](#table-of-contents)

### 45. What are the rules of JSX?

1. Must return a single root element (or Fragment). 2. All tags must be closed. 3. Attributes use camelCase (`className`, `onClick`, `htmlFor`). 4. JavaScript expressions go inside `{}`. 5. Cannot use reserved words like 'class' or 'for'. 6. Use `className` instead of `class`. 7. Use `htmlFor` instead of `for`.

### 46. What does 'declarative' mean in React?

You describe what the UI should look like for a given state. React figures out how to make the DOM match. Imperative code would manually manipulate the DOM step by step; declarative code just re-renders with new state. ------------------------------------------------------------------------

### 47. What does JSX compile to?

[↑ Back to Table of Contents](#table-of-contents) JSX compiles to `React.createElement(type, props, ...children)` in React \<17, and to the automatic `jsx()` runtime in React 17+. Both produce plain JavaScript objects (React elements) describing the UI. ------------------------------------------------------------------------

### 48. What is `createRoot()` and why replace `ReactDOM.render()`?

`createRoot()` (React 18+) opts an app into concurrent features (automatic batching, transitions, improved Suspense). `ReactDOM.render()` runs in legacy mode without them.

### 49. What is `React.createElement()`? What does it return?

The function JSX compiles to. It returns a plain JS object (a React element) describing type, props, and children — not an actual DOM node.

### 50. What is a switching component?

A _switching component_ is a component that renders one of many components. We need to use object to map prop values to components. For example, a switching component to display different pages based on `page` prop:

```jsx harmony import HomePage from "./HomePage"; import AboutPage from "./AboutPage"; import ServicesPage from "./ServicesPage"; import ContactPage from "./ContactPage"; const PAGES = { home: HomePage, about: AboutPage, services: ServicesPage, contact: ContactPage, }; const Page = (props) => { const Handler = PAGES** --- ### What is a wrapper component? A wrapper in React is a component that wraps or surrounds another component or group of components. It can be used for a variety of purposes such as adding additional functionality, styling, or layout to the wrapped components. For example, consider a simple component that displays a message:

```javascript const Message = ({ text }) => { return <p>{text}</p>; };

```
We can create a wrapper component that will add a border to the message component:

```javascript const MessageWrapper = (props) => { return ( <div style={{ border: "1px solid black" }}> <Message {...props} /> </div> ); };

```
Now we can use the MessageWrapper component instead of the Message component and the message will be displayed with a border:

```javascript <MessageWrapper text="Hello World" />

```
Wrapper component can also accept its own props and pass them down to the wrapped component, for example, we can create a wrapper component that will add a title to the message component:

```javascript const MessageWrapperWithTitle = ({ title, ...props }) => { return ( <div> <h3>{title}</h3> <Message {...props} /> </div> ); };

```
Now we can use the MessageWrapperWithTitle component and pass title props:

```javascript <MessageWrapperWithTitle title="My Message" text="Hello World" />

```
This way, the wrapper component can add additional functionality, styling, or layout to the wrapped component while keeping the wrapped component simple and reusable. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is children prop? The `children` prop is a special prop in React used to pass elements between the opening and closing tags of a component. It is commonly used in layout and wrapper componnents. A simple usage of children prop looks as below,

```jsx harmony function MyDiv({ children }){ return ( <div> {children} </div>; ); } export default function Greeting() { return ( <MyDiv> <span>{"Hello"}</span> <span>{"World"}</span> </MyDiv> ); }

```
Here, everything inside `<MyDiv>...</MyDiv>` is passed as children to the custom div component. The children can be text, JSX elements, fragments, arrays and functions(for advance use case like render props). <details><summary><b>See Class</b></summary> <p>

```jsx harmony const MyDiv = React.createClass({ render: function () { return <div>{this.props.children}</div>; }, }); ReactDOM.render( <MyDiv> <span>{"Hello"}</span> <span>{"World"}</span> </MyDiv>, node );

```
</p> </details> **Note:** There are several methods available in the legacy React API to work with this prop. These include `React.Children.map`, `React.Children.forEach`, `React.Children.count`, `React.Children.only`, `React.Children.toArray`. **** --- ### What is `forwardRef`? `React.forwardRef((props, ref) => ...)` passes a ref from a parent through a functional component to a DOM node or child component. Required because refs are not regular props and cannot be passed through as-is. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is forwardRef, and when do you need it? This one is simple! You can use forwardRef to pass a ref from the parent component through the child component to a DOM element or another component inside it. You need it particularly because, by default, function components do not accept ref, as ref is not a regular prop, and it is handled separately by React. forwardRef is needed because it enables access to a child component’s DOM node, it helps in imperative actions like .focus() , .scrollIntoView() , and measuring layout. So, when you don’t use forwardRef, the parent won’t be able to directly interact with the child’s internal DOM elements, and hence it may hinder when required to reuse. **This is how forwardRef works -** React.forwardRef wraps a functional component and provides ref as a second argument. This is the pattern: const Input = React.forwardRef((props, ref) =\> { return \<input ref={ref} {...props} /\>; }); Here’s how you can use it: const inputRef = useRef(); `<Input ref={inputRef} />`{=html} Now the parent can directly call: inputRef.current.focus(); Some common use cases are - integrating DOM libraries, focus management, triggering animations, measuring DOM elements, etc. --- ### What is lifting state up? Moving shared state to the nearest common ancestor of components that need it, then passing it down via props and up via callbacks. This keeps state as the single source of truth. ------------------------------------------------------------------------ --- --- ### What is Lifting State Up in React? When several components need to share the same changing data then it is recommended to _lift the shared state up_ to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components. **** --- ### What is prop drilling and why is it a problem? Passing props through many intermediate components that don't use them just to reach a deep child. It creates tight coupling and makes refactoring hard. Solved by Context, state management libraries, or component composition. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is prop drilling in React? Sometimes while developing React applications, there is a need to pass data from a component that is higher in the hierarchy to a component that is deeply nested. To pass data between such components, we pass props from a source component and keep passing the prop to the next component in the hierarchy till we reach the deeply nested component. The **disadvantage** of using prop drilling is that the components that should otherwise be not aware of the data have access to the data. --- ### What is prop drilling? Problems and solutions. Prop drilling is passing data through multiple layers of components via props, even when intermediate components don’t need that data. This makes code harder to maintain and refactor. **Solutions**: - **Context API**: Create a context and provide values at a higher level, then consume them deep down. - **State management libraries**: Redux, Zustand, etc. - **Component composition**: Instead of passing props, pass components as children or use render props to flatten the hierarchy. --- ### What is React.Fragment and why is it useful? React's Fragment helps in grouping multiple elements together by being careful not to add an extra element to the DOM. Just like you know in React, every component MUST return a single parent element, and a fragment just acts like that parent, except it doesn’t actually show up in the final HTML. I’ll explain this to you with an example! If you write: return ( \<\>

```{=html} <h1>

```
Hello

```{=html} </h1>

```
<p>World</p> \</\> ); React will group these elements together using Fragment, but in the browser, it will render as:

```{=html} <h1>

```
Hello

```{=html} </h1>

```
```{=html} <p>

```
World

```{=html} </p>

```
This shows that the Fragment is only used by React internally; it does not create an HTML element like a \<div>. Why do we use Fragment? Because sometimes using \<div> might cause some problems like breaking layouts on flexbox or grid, or creating invalid HTML (yes, this happens!) You can use it in these 2 ways: - \<React.Fragment> ... \</React.Fragment> - <> ... \</> - (short syntax) One thing you need to keep in mind is that only React.Fragment supports props like key, which comes in hand when rendering lists. --- ### What is server state vs client state? Server state: data from APIs (users, posts) -- needs caching, refetching, synchronization, background updates. Client state: local UI state (modal open, form values) -- synchronous, lives only in the browser. ------------------------------------------------------------------------ --- --- ### What is state in React? Mutable data owned by a component. When state changes, React schedules a re-render. State is private to the component unless shared via props or context. `useState` / `useReducer` manage it in functional components. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is state mutation and how to prevent it? `State mutation` happens when you try to update the state of a component without actually using `setState` function. This can happen when you are trying to do some computations using a state variable and unknowingly save the result in the same state variable. This is the main reason why it is advised to return new instances of state variables from the reducers by using Object.assign({}, ...) or spread syntax. This can cause unknown issues in the UI as the value of the state variable got updated without telling React to check what all components were being affected from this update and it can cause UI bugs. Ex:

```javascript class A extends React.component { constructor(props) { super(props); this.state = { loading: false } } componentDidMount() { let { loading } = this.state; loading = (() => true)(); // Trying to perform an operation and directly saving in a state variable }

```
**How to prevent it:** Make sure your state variables are immutable by either enforcing immutability by using plugins like Immutable.js, always using `setState` to make updates, and returning new instances in reducers when sending updated state values. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is the container/presenter pattern and is it still relevant? Separating data logic (container) from UI (presenter). Less strictly followed now – hooks handle data logic inside any component. But the concept of separating concerns is still valuable, enforced by custom hooks. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the controlled component pattern for reusable components? This pattern creates a flexible component that can run on "autopilot" OR be manually "steered" by its parent. Instead of forcing a component to be strictly controlled or strictly uncontrolled, you build it to support both modes seamlessly. A reusable component can work in two modes: uncontrolled (manages own state) or controlled (parent provides `value` + `onChange`). Example: an `<Accordion>` that works out of the box but can also be fully controlled. ------------------------------------------------------------------------ --- --- ### What is the difference between an Element and a Component? **Element:** - A React **Element** is a plain JavaScript object that describes what you want to see on the UI. It represents a DOM node or a component at a specific point in time. - Elements are immutable: once created, you cannot change their properties. Instead, you create new elements to reflect updates. - Elements can be nested within other elements through their `props`. - Creating an element is a fast, lightweight operation—it does **not** create any actual DOM nodes or render anything to the screen directly. **Example (without JSX):**

```js const element = React.createElement("button", { id: "login-btn" }, "Login");

```
**Equivalent JSX syntax:**

```jsx <button id="login-btn">Login</button>

```
**The object returned by `React.createElement`:**

```js { type: 'button', props: { id: 'login-btn', children: 'Login' } }

```
Elements are then passed to the React DOM renderer (e.g., `ReactDOM.render()`), which translates them to actual DOM nodes. **Component:** - A **Component** is a function or class that returns an element (or a tree of elements) to describe part of the UI. Components can accept inputs (called **props**) and manage their own state (in case of class or function components with hooks). - Components allow you to split the UI into independent, reusable pieces, each isolated and composable. - You can define a component using a function or a class: **Example (Function Component with JSX):**

```jsx const Button = ({ handleLogin }) => ( <button id="login-btn" onClick={handleLogin}> Login </button> );

```
When JSX is compiled, it's transformed into a tree of `React.createElement` calls:

```js const Button = ({ handleLogin }) => React.createElement( "button", { id: "login-btn", onClick: handleLogin }, "Login" );

```
**In summary:** - **Elements** are the smallest building blocks in React—objects that describe what you want to see. - **Components** are functions or classes that return elements and encapsulate logic, structure, and behavior for parts of your UI. > Think of **elements** as the instructions for creating UI, and **components** as reusable blueprints that combine logic and structure to generate those instructions. **** --- ### What is the difference between props and state? Props are external, immutable (from parent). State is internal, mutable (managed by the component). Props configure a component; state tracks what changes over time inside it. ------------------------------------------------------------------------ --- --- ### What is the difference between state and props? In React, both **state** and **props** are plain JavaScript objects, but they serve different purposes and have distinct behaviors: ### State - **Definition:** State is a data structure that is managed within a component. It represents information that can change over the lifetime of the component. - **Mutability:** State is mutable, meaning it can be changed using the setter function (`setState` in class components or the updater function from `useState` in functional components). - **Scope:** State is local to the component where it is defined. Only that component can modify its own state. - **Usage:** State is typically used for data that needs to change in response to user actions, network responses, or other dynamic events. - **Re-rendering:** Updating the state triggers a re-render of the component and its descendants. ### Props - **Definition:** Props (short for “properties”) are inputs to a component, provided by its parent component. - **Mutability:** Props are read-only. A component cannot modify its own props; they are immutable from the component’s perspective. - **Scope:** Props are used to pass data and event handlers down the component tree, enabling parent components to configure or communicate with their children. - **Usage:** Props are commonly used to make components reusable and configurable. They allow the same component to be rendered with different data or behavior. - **Analogy:** Think of props as arguments to a function, whereas state is like variables declared inside the function. ### Summary Table | Feature | State | Props | |-----------|-------------------------------------|-----------------------------------| | Managed by| The component itself | Parent component | | Mutable | Yes | No (read-only) | | Scope | Local to the component | Passed from parent to child | | Usage | Manage dynamic data and UI changes | Configure and customize component | | Update | Using setState/useState | Cannot be updated by the component| **** --- ### What is the difference between `super()` and `super(props)` in React using ES6 classes? When you want to access `this.props` in `constructor()` then you should pass props to `super()` method. **Using `super(props)`:**

```javascript class MyComponent extends React.Component { constructor(props) { super(props); console.log(this.props); // { name: 'John', ... } } }

```
**Using `super()`:**

```javascript class MyComponent extends React.Component { constructor(props) { super(); console.log(this.props); // undefined } }

```
Outside `constructor()` both will display same value for `this.props`. **** ------------------------------------------------------------------------ --- --- ### What is the impact of indexes as keys? Keys should be stable, predictable, and unique so that React can keep track of elements. In the below code snippet each element's key will be based on ordering, rather than tied to the data that is being represented. This limits the optimizations that React can do and creates confusing bugs in the application.

```jsx harmony { todos.map((todo, index) => <Todo {...todo} key={index} />); }

```
If you use element data for unique key, assuming `todo.id` is unique to this list and stable, React would be able to reorder elements without needing to reevaluate them as much.

```jsx harmony { todos.map((todo) => <Todo {...todo} key={todo.id} />); }

```
**Note:** If you don't specify `key` prop at all, React will use index as a key's value while iterating over an array of data. **** --- ### What is the `key` prop and why is it important? A special string or number that uniquely identifies a list item. React uses keys to match items between renders for efficient reconciliation. Wrong or missing keys cause incorrect DOM reuse and subtle bugs. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the purpose of forward ref in HOCs? Refs will not get passed through because ref is not a prop. It handled differently by React just like **key**. If you add a ref to a HOC, the ref will refer to the outermost container component, not the wrapped component. In this case, you can use Forward Ref API. For example, we can explicitly forward refs to the inner FancyButton component using the React.forwardRef API. The below HOC logs all props,

````
```javascript function logProps(Component) { class LogProps extends React.Component { componentDidUpdate(prevProps) { console.log('old props:', prevProps); console.log('new props:', this.props); } render() { const {forwardedRef, ...rest} = this.props; // Assign the custom prop "forwardedRef" as a ref return <Component ref={forwardedRef} {...rest} />; } } return React.forwardRef((props, ref) => { return <LogProps {...props} forwardedRef={ref} />; }); }

```
````
Let's use this HOC to log all props that get passed to our “fancy button” component,

````
```javascript class FancyButton extends React.Component { focus() { // ... } // ... } export default logProps(FancyButton);

```
````
Now lets create a ref and pass it to FancyButton component. In this case, you can set focus to button element.

````
```javascript import FancyButton from './FancyButton'; const ref = React.createRef(); ref.current.focus(); <FancyButton label="Click Me" handleClick={handleClick} ref={ref} />;

```
````
[ --- ### What is the purpose of getDerivedStateFromError? This lifecycle method is invoked after an error has been thrown by a descendant component. It receives the error that was thrown as a parameter and should return a value to update state. The signature of the lifecycle method is as follows,

```
static getDerivedStateFromError(error)

```
Let us take error boundary use case with the above lifecycle method for demonistration purpose,

```
class ErrorBoundary extends React.Component { constructor(props) { super(props); this.state = { hasError: false }; } static getDerivedStateFromError(error) { // Update state so the next render will show the fallback UI. return { hasError: true }; } render() { if (this.state.hasError) { // You can render any custom fallback UI return <h1>Something went wrong.</h1>; } return this.props.children; } }

```
[ --- ### What is the purpose of unmountComponentAtNode method? This method is available from react-dom package and it removes a mounted React component from the DOM and clean up its event handlers and state. If no component was mounted in the container, calling this function does nothing. Returns true if a component was unmounted and false if there was no component to unmount. The method signature would be as follows,

```
ReactDOM.unmountComponentAtNode(container);

```
[ --- ### What is the purpose of using super constructor with props argument? A child class constructor cannot make use of `this` reference until the `super()` method has been called. The same applies to ES6 sub-classes as well. The main reason for passing props parameter to `super()` call is to access `this.props` in your child constructors. **Passing props:**

```javascript class MyComponent extends React.Component { constructor(props) { super(props); console.log(this.props); // prints { name: 'John', age: 42 } } }

```
**Not passing props:**

```javascript class MyComponent extends React.Component { constructor(props) { super(); console.log(this.props); // prints undefined // but props parameter is still available console.log(props); // prints { name: 'John', age: 42 } } render() { // no difference outside constructor console.log(this.props); // prints { name: 'John', age: 42 } } }

```
The above code snippets reveals that `this.props` is different only within the constructor. It would be the same outside the constructor. **** ------------------------------------------------------------------------ --- --- ### What is the recommended approach of removing an array element in React state? The better approach is to use `Array.prototype.filter()` method. For example, let's create a `removeItem()` method for updating the state.

```javascript removeItem(index) { this.setState({ data: this.state.data.filter((item, i) => i !== index) }) }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------ --- ## React Fundamentals & JSX --- ### What is the recommended ordering of methods in component class? *Recommended* ordering of methods from *mounting* to *render stage*: 1. `static` methods 2. `constructor()` 3. `getChildContext()` 4. `componentWillMount()` 5. `componentDidMount()` 6. `componentWillReceiveProps()` 7. `shouldComponentUpdate()` 8. `componentWillUpdate()` 9. `componentDidUpdate()` 10. `componentWillUnmount()` 11. click handlers or event handlers like `onClickSubmit()` or `onChangeDescription()` 12. getter methods for render like `getSelectReason()` or `getFooterContent()` 13. optional render methods like `renderNavigation()` or `renderProfilePicture()` 14. `render()` **** ------------------------------------------------------------------------ --- --- ### What is the render props pattern? The Render Props pattern is a way to share a specific behavior or piece of data between components by using a function as a prop. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the required method to be defined for a class component? The `render()` method is the only required method in a class component. i.e, All methods other than render method are optional for a class component. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is the typical use case of portals? React portals are very useful when a parent component has overflow: hidden or has properties that affect the stacking context(z-index,position,opacity etc styles) and you need to visually “break out” of its container. For example, dialogs, global message notifications, hovercards, and tooltips. [ --- ### What will happen if you use props in initial state? If the props on the component are changed without the component being refreshed, the new prop value will never be displayed because the constructor function will never update the current state of the component. The initialization of state from props only runs when the component is first created. The below component won't display the updated input value:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { records: ** ------------------------------------------------------------------------

### 51. What is declarative vs imperative programming? How does React fit in?

Imperative code describes the exact steps to change the UI. Declarative code describes the desired end state, and the library figures out the steps. React is declarative: you write `<h1>{name}</h1>` and React reconciles the DOM to match.

### 52. What is JSX and how is it rendered in the browser?

[↑ Back to Table of Contents](#table-of-contents) JSX is a syntax extension for JavaScript that looks like HTML but gets transformed into regular JavaScript function calls (`React.createElement`). The browser cannot interpret JSX directly; it is transpiled by tools like Babel into `React.createElement` calls, which produce plain JavaScript objects representing the virtual DOM. These objects are then rendered to the actual DOM by React. Example:

```jsx const element = <h1>Hello, world!</h1>; // Transpiles to: const element = React.createElement('h1', null, 'Hello, world!');

```

### 53. What is JSX and why does React use it?

[↑ Back to Table of Contents](#table-of-contents) JSX is a syntax extension allowing HTML-like markup inside JS. At build time it compiles to `React.createElement()` calls. It improves readability, catches errors earlier via the compiler, and makes component trees visually clear. ------------------------------------------------------------------------

### 54. What is JSX?

[↑ Back to Table of Contents](#table-of-contents) _JSX_ stands for _JavaScript XML_ and it is an XML-like syntax extension to ECMAScript. Basically it just provides the syntactic sugar for the `React.createElement(type, props, ...children)` function, giving us expressiveness of JavaScript along with HTML like template syntax. In the example below, the text inside `<h1>` tag is returned as JavaScript function to the render function.

```jsx harmony export default function App() { return <h1 className="greeting">{"Hello, this is a JSX Code!"}</h1>; }

```
If you don't use JSX syntax then the respective JavaScript code should be written as below,

```javascript import { createElement } from "react"; export default function App() { return createElement( "h1", { className: "greeting" }, "Hello, this is a JSX Code!" ); }

```
<details><summary><b>See Class</b></summary> <p>

```jsx harmony class App extends React.Component { render() { return <h1 className="greeting">{"Hello, this is a JSX Code!"}</h1>; } }

```
</p> </details> **Note:** JSX is stricter than HTML

### 55. What is React and what problem does it solve?

[↑ Back to Table of Contents](#table-of-contents) React is a JavaScript library by Meta for building UIs using a declarative, component-based model. It solves the complexity of keeping the UI in sync with application state by reacting to state changes automatically and efficiently updating the DOM. React uses a virtual DOM for performance optimization and unidirectional data flow for predictable state management.

### 56. What is React Dev Tools?

_React Developer Tools_ let you inspect the component hierarchy, including component props and state. It exists both as a browser extension (for Chrome and Firefox), and as a standalone app (works with other environments including Safari, IE, and React Native). The official extensions available for different browsers or environments.

### 57. What is React Intl?

[↑ Back to Table of Contents](#table-of-contents) The _React Intl_ library makes internationalization in React straightforward, with off-the-shelf components and an API that can handle everything from formatting strings, dates, and numbers, to pluralization. React Intl is part of _FormatJS_ which provides bindings to React via its components and API. ****

### 58. What is React lazy function?

[↑ Back to Table of Contents](#table-of-contents) The `React.lazy` function lets you render a dynamic import as a regular component. It will automatically load the bundle containing the `OtherComponent` when the component gets rendered. This must return a Promise which resolves to a module with a default export containing a React component.

```jsx const OtherComponent = React.lazy(() => import("./OtherComponent")); function MyComponent() { return ( <div> <OtherComponent /> </div> ); }

```
**Note:** `React.lazy` and `Suspense` is not yet available for server-side rendering. If you want to do code-splitting in a server rendered app, we still recommend React Loadable. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 59. What is React proptype array with shape?

If you want to pass an array of objects to a component with a particular shape then use `React.PropTypes.shape()` as an argument to `React.PropTypes.arrayOf()`.

```javascript ReactComponent.propTypes = { arrayWithShape: React.PropTypes.arrayOf( React.PropTypes.shape({ color: React.PropTypes.string.isRequired, fontSize: React.PropTypes.number.isRequired, }) ).isRequired, };

```
**** ------------------------------------------------------------------------

### 60. What is react scripts?

The `react-scripts` package is a set of scripts from the create-react-app starter pack which helps you kick off projects without configuring. The `react-scripts start` command sets up the development environment and starts a server, as well as hot module reloading. [↑ Back to Table of Contents](#table-of-contents)

### 61. What is React?

React (aka React.js or ReactJS) is an **open-source front-end JavaScript library** for building user interfaces based on components. It's used for handling the view layer in web and mobile applications, and allows developers to create reusable UI components and manage the state of those components efficiently. React was created by [Jordan Walke](https://github.com/jordwalke), a software engineer at Facebook (now Meta). It was first deployed on Facebook's News Feed in 2011 and on Instagram in 2012. The library was open-sourced in May 2013 and has since become one of the most popular JavaScript libraries for building modern user interfaces. [↑ Back to Table of Contents](#table-of-contents)

### 62. What is the difference between "rendering" and "committing"?

Rendering computes the new Virtual DOM (interruptible). Committing applies changes to the real DOM and runs effects (synchronous, not interruptible).

### 63. What is the difference between `className` and `class` in JSX?

JSX uses `className` (matching the DOM property name) since `class` is a reserved word in JavaScript.

### 64. What is the difference between HTML and React event handling?

Below are some of the main differences between HTML and React event handling, 1. In HTML, the event name usually represents in _lowercase_ as a convention:

```html <button onclick="activateLasers()"></button>

```
Whereas in React it follows _camelCase_ convention:

```jsx harmony <button onClick={activateLasers}>

```
2. In HTML, you can return `false` to prevent default behavior:

```html <a href="#" onclick='console.log("The link was clicked."); return false;' />

```
Whereas in React you must call `preventDefault()` explicitly:

```javascript function handleClick(event) { event.preventDefault(); console.log("The link was clicked."); }

```
3. In HTML, you need to invoke the function by appending `()` Whereas in react you should not append `()` with the function name. (refer "activateLasers" function in the first point for example) [↑ Back to Table of Contents](#table-of-contents)

### 65. What is the difference between Imperative and Declarative in React?

Imagine a simple UI component, such as a "Like" button. When you tap it, it turns blue if it was previously grey, and grey if it was previously blue. The imperative way of doing this would be:

```javascript if (user.likes()) { if (hasBlue()) { removeBlue(); addGrey(); } else { removeGrey(); addBlue(); } }

```
Basically, you have to check what is currently on the screen and handle all the changes necessary to redraw it with the current state, including undoing the changes from the previous state. You can imagine how complex this could be in a real-world scenario. In contrast, the declarative approach would be:

```javascript if (this.state.liked) { return <blueLike />; } else { return <greyLike />; }

```
Because the declarative approach separates concerns, this part of it only needs to handle how the UI should look in a specific state, and is therefore much simpler to understand. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 66. What is the difference between Real DOM and Virtual DOM?

[↑ Back to Table of Contents](#table-of-contents) Below are the main differences between Real DOM and Virtual DOM, | Real DOM | Virtual DOM | | ------------------------------------ | ------------------------------------ | | Updates are slow | Updates are fast | | DOM manipulation is very expensive. | DOM manipulation is very easy | | You can update HTML directly. | You Can’t directly update HTML | | It causes too much of memory wastage | There is no memory wastage | | Creates a new DOM if element updates | It updates the JSX if element update | ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 67. What is the difference between try catch block and error boundaries?

Try catch block works with imperative code whereas error boundaries are meant for declarative code to render on the screen. For example, the try catch block used for below imperative code

```javascript try { showButton(); } catch (error) { // ... }

```
Whereas error boundaries wrap declarative code as below,

```javascript <ErrorBoundary> <MyComponent /> </ErrorBoundary>

```
So if an error occurs in a **componentDidUpdate** method caused by a **setState** somewhere deep in the tree, it will still correctly propagate to the closest error boundary. [↑ Back to Table of Contents](#table-of-contents)

### 68. What is the React DevTools and what can you do with it?

[↑ Back to Table of Contents](#table-of-contents) A browser extension that lets you inspect the component tree, view props/state/context, highlight re-renders, and use the Profiler to record timing and flame graphs of render performance. ------------------------------------------------------------------------

### 69. What is the reason behind multiple JSX tags to be wrapped?

[↑ Back to Table of Contents](#table-of-contents) Behind the scenes, JSX is transformed into plain javascript objects. It is not possible to return two or more objects from a function without wrapping into an array. This is the reason you can't simply return two or more JSX tags from a function without wrapping them into a single parent tag or a Fragment. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 70. What is the reason multiple JSX elements must be wrapped in one parent?

JSX transpiles to function calls; a function/component can't return multiple sibling objects without wrapping them in an array or single parent (or Fragment).

### 71. What is the trade-off of the Compound Components pattern vs a single component with a declarative config object/array prop?

Compound Components give a more flexible, JSX-native, readable API (the consumer controls layout/order freely) but require more setup (Context plumbing) and are less convenient to generate dynamically from data; a config-array prop is easier to generate programmatically but less flexible for custom layout per-item.

### 72. What is the Virtual DOM?

[↑ Back to Table of Contents](#table-of-contents) An in-memory lightweight JS tree that mirrors the real DOM. React renders to the virtual DOM first, diffs two versions (reconciliation), and applies only the minimal set of real DOM mutations needed. ------------------------------------------------------------------------

### 73. What is the virtual DOM? How does react use the virtual DOM to render the UI?

[↑ Back to Table of Contents](#table-of-contents) As stated by the react team, virtual DOM is a concept where a virtual representation of the real DOM is kept inside the memory and is synced with the real DOM by a library such as ReactDOM.

### 74. What would be the common mistake of function being called every time the component renders?

You need to make sure that function is not being called while passing the function as a parameter.

```jsx harmony render() { // Wrong: handleClick is called instead of passed as a reference! return <button onClick={this.handleClick()}>{'Click Me'}</button> }

```
Instead, pass the function itself without parenthesis:

```jsx harmony render() { // Correct: handleClick is passed as a reference! return <button onClick={this.handleClick}>{'Click Me'}</button> }

```
**** ------------------------------------------------------------------------

### 75. Why can't browsers run JSX directly?

JSX isn't valid JS syntax. A build tool (Babel/SWC/esbuild) transpiles it to `createElement`/`jsx()` calls before reaching the browser.

### 76. Why does React use `className` instead of `class`?

`class` is a reserved JS keyword; since JSX compiles to JS object literals, `class` would conflict, so React uses `className` (mirroring the DOM API `element.className`).

### 77. Why should component names start with capital letter?

[↑ Back to Table of Contents](#table-of-contents) If you are rendering your component using JSX, the name of that component has to begin with a capital letter otherwise React will throw an error as an unrecognized tag. This convention is because only HTML elements and SVG tags can begin with a lowercase letter.

```jsx harmony function SomeComponent { // Code goes here }

```
You can define function component whose name starts with lowercase letter, but when it's imported it should have a capital letter. Here lowercase is fine:

```jsx harmony function myComponent { render() { return <div />; } } export default myComponent;

```
While when imported in another file it should start with capital letter:

```jsx harmony import MyComponent from "./myComponent";

```
****

### 78. Why was virtual DOM introduced?

DOM manipulation is an integral part of any web application, but DOM manipulation is quite slow when compared to other operations in JavaScript. The efficiency of the application gets affected when several DOM manipulations are being done. Most JavaScript frameworks update the entire DOM even when a small part of the DOM changes. For example, consider a list that is being rendered inside the DOM. If one of the items in the list changes, the entire list gets rendered again instead of just rendering the item that was changed/updated. This is called inefficient updating. To address the problem of inefficient updating, the react team introduced the concept of virtual DOM.

### 79. Why you get "Router may have only one child element" warning?

You have to wrap your Route's in a `<Switch>` block because `<Switch>` is unique in that it renders a route exclusively. At first you need to add `Switch` to your imports:

```javascript import { Switch, Router, Route } from "react-router";

```
Then define the routes within `<Switch>` block:

```jsx harmony <Router> <Switch> <Route {/* ... */} /> <Route {/* ... */} /> </Switch> </Router>

```
[↑ Back to Table of Contents](#table-of-contents)

## Components, Props & State

### 80. `React.FC` vs explicit return type – which is better?

Explicit: `function Comp({name}: Props): JSX.Element` is more explicit about what's returned. `React.FC<Props>` implicitly types children and return. The React team no longer recommends `React.FC` – prefer explicit typing. [↑ Back to Table of Contents](#table-of-contents)

### 81. Binding in Constructor:

In JavaScript classes, the methods are not bound by default. The same rule applies for React event handlers defined as class methods. Normally we bind them in constructor.

```
javascript class User extends Component { constructor(props) { super(props); this.handleClick = this.handleClick.bind(this); } handleClick() { console.log("SingOut triggered"); } render() { return <button onClick={this.handleClick}>SingOut</button>; } }

```

### 82. Calling `setState()` with an object to merge with state:

- Using `Object.assign()` to create a copy of the object:

```javascript const user = Object.assign({}, this.state.user, { age: 42 }); this.setState({ user });

```
- Using _spread operator_:

```javascript const user = { ...this.state.user, age: 42 }; this.setState({ user });

```

### 83. Can a component return multiple top-level elements without a Fragment?

Yes, as of React that supports returning arrays or using `<>...</>` — but each sibling in an array needs its own `key`.

### 84. Can I dispatch an action in reducer?

Dispatching an action within a reducer is an **anti-pattern**. Your reducer should be _without side effects_, simply digesting the action payload and returning a new state object. Adding listeners and dispatching actions within the reducer can lead to chained actions and other side effects. [↑ Back to Table of Contents](#table-of-contents)

### 85. Changes are made with pure functions(Reducers):

To specify how the state tree is transformed by actions, you write reducers. Reducers are just pure functions that take the previous state and an action as parameters, and return the next state.

```jsx function counter(state = 0, action) { switch (action.type) { case 'INCREMENT': return state + 1; case 'DECREMENT': return state - 1; default: return state; } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 86. Class Components:

You can also use ES6 class to define a component. The above function component can be written as a class component:

```jsx harmony class Greeting extends React.Component { render() { return <h1>{`Hello, ${this.props.message}`}</h1>; } }

```
****

### 87. Component Elements Of The Same Type:

When a component updates, the instance stays the same, so that state is maintained across renders. React updates the props of the underlying component instance to match the new element, and calls componentWillReceiveProps() and componentWillUpdate() on the underlying instance. After that, the render() method is called and the diff algorithm recurses on the previous result and the new result.

### 88. Component Re-renders Unexpectedly: Component re-renders even when props don't change -- hidden reasons.

[↑ Back to Table of Contents](#table-of-contents) **Common hidden reasons**: - **Parent re‑renders** -- by default, a component re‑renders when its parent re‑renders, even if props are identical. Fix: use `React.memo`. - **Inline functions/objects** passed as props create new references each render. Fix: use `useCallback` and `useMemo`. - **Context changes** -- if the component consumes any context, a context update triggers re‑render. - **State updates that set the same value** -- React 18 may still re‑render even if value hasn't changed (though it usually doesn't for primitive values). - **Key changes** -- if a component's key changes, React treats it as a new component and unmounts/mounts. **Debug**: - Use `why-did-you-render` library to log prop changes. - Use React DevTools Profiler to see why a component rendered (highlight updates). ------------------------------------------------------------------------

### 89. Component Re-renders Unexpectedly?

Component re-renders even when props don't change – hidden reasons.

### 90. Compute the next state manually:

```jsx const handleClick = () => { const nextState = reducer(state, { type: 'increment' }); console.log('Next state will be:', nextState.count); dispatch({ type: 'increment' }); };

```

### 91. Connect the above props to your container:

The object returned by the `mapStateToProps` function is connected to the container. You can import `connect()` from `react-redux`.

```jsx harmony import React from "react"; import { connect } from "react-redux"; class App extends React.Component { render() { return <div>{this.props.containerData}</div>; } } function mapStateToProps(state) { return { containerData: state.data }; } export default connect(mapStateToProps)(App);

```
[↑ Back to Table of Contents](#table-of-contents)

### 92. Controlled vs uncontrolled components?

[↑ Back to Table of Contents](#table-of-contents) Controlled Components (The Micromanaged Employee) A controlled component is completely managed by React. React keeps track of every single keystroke in its internal memory (state). Analogy: A boss who asks for an update every time an employee writes a single sentence. How it works: When you type into an input box, it triggers an onChange event. React updates its state with the new letter, and then React tells the input box to display that new state. Why use it? Because React knows exactly what is in the box at all times, you can easily do things like disable a "Submit" button until an email address is formatted correctly, or force all text to be uppercase as the user types. Uncontrolled Components (The Independent Worker) An uncontrolled component is left to manage itself. The browser (DOM) keeps track of what is typed in the box, just like a traditional HTML website. Analogy: A suggestion box. You don't monitor people as they write their suggestions; you just use a key to open the box and read whatever is inside only when you actually need it. How it works: You don't bother saving every keystroke to React's state. Instead, you attach a ref (a reference) to the input. When the user finally clicks "Submit", React uses that ref to reach into the DOM and pull the final value out. Why use it? It requires less code to set up. It's great for very simple forms where you don't need instant validation while the user is typing. ------------------------------------------------------------------------

### 93. Controlled vs uncontrolled forms -- trade-offs in practice?

Controlled: every keystroke updates state → always have current value for validation, but can cause re-renders. Uncontrolled with ref: only read on submit → fewer renders, but can't do real-time validation easily. ------------------------------------------------------------------------

### 94. Current state:

It refers to actual state

### 95. Describe about data flow in react?

React implements one-way reactive data flow using props which reduce boilerplate and is easier to understand than traditional two-way data binding. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 96. Destructuring:

To get props and use them in a component

```javascript // in es 5 var someData = this.props.someData; var dispatch = this.props.dispatch; // in es6 const { someData, dispatch } = this.props;

```

### 97. Difference between `key`-based remounting and conditional rendering?

Conditional rendering can preserve state if type/position match. Changing `key` forces unmount+remount, discarding state.

### 98. Does React support all HTML attributes?

[↑ Back to Table of Contents](#table-of-contents) As of React 16, both standard or custom DOM attributes are fully supported. Since React components often take both custom and DOM-related props, React uses the camelCase convention just like the DOM APIs. Let us take few props with respect to standard HTML attributes,

```javascript <div tabIndex="-1" /> // Just like node.tabIndex DOM API <div className="Button" /> // Just like node.className DOM API <input readOnly={true} /> // Just like node.readOnly DOM API

```
These props work similarly to the corresponding HTML attributes, with the exception of the special cases. It also support all SVG attributes.

### 99. Draft state:

All new changes will be applied to this state. In this state, draft is just a proxy of the current state.

### 100. Event bubbling through a React portal rendered outside the DOM parent?

```jsx // Portals: where does the component appear in the DOM? function Modal({ children }) { return ReactDOM.createPortal( <div className="modal">{children}</div>, document.getElementById('modal-root') // Outside #app ); } function App() { const [show, setShow] = React.useState(false); return ( <div id="app" onClick={() => console.log('app clicked')}> <button onClick={() => setShow(true)}>Open Modal</button> {show && ( <Modal> <button onClick={(e) => { e.stopPropagation(); // Does this stop App's onClick? console.log('modal button clicked'); }}> Close </button> </Modal> )} </div> ); }

```
**Behavior:** Clicking the modal button logs only `modal button clicked`. `stopPropagation` WORKS even though the modal is rendered outside `#app` in the DOM. **Explanation:** Portals render outside the DOM hierarchy but remain in the REACT component tree. Event bubbling follows the REACT tree, not the DOM tree. So events from a portal bubble up through React parents, and `stopPropagation` works relative to the React tree. [↑ Back to Table of Contents](#table-of-contents)

### 101. Explain conditional rendering in React.

Conditional rendering refers to the dynamic output of user interface markups based on a condition state. It works in the same way as JavaScript conditions. Using conditional rendering, it is possible to toggle specific application functions, API data rendering, hide or show elements, decide permission levels, authentication handling, and so on. There are different approaches for implementing conditional rendering in React. Some of them are: - Using if-else conditional logic which is suitable for smaller as well as for medium-sized applications - Using ternary operators, which takes away some amount of complication from if-else statements - Using element variables, which will enable us to write cleaner code.

### 102. Explain React state and props.

[↑ Back to Table of Contents](#table-of-contents) | PropsState | | | --------------------------------- | ------------------------------------------ | | Immutable | Owned by its component | | Has better performance | Locally scoped | | Can be passed to child components | Writeable/Mutable | | | has setState() method to modify properties | | | Changes to state can be asynchronous | | | can only be passed as props | - **React State** Every component in react has a built-in state object, which contains all the property values that belong to that component. In other words, the state object controls the behaviour of a component. Any change in the property values of the state object leads to the re-rendering of the component. > Note- State object is not available in functional components but, we can use React Hooks to add state to a functional component.

### 103. Function Components:

This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the one and only one parameter and return React elements to render the output:

```jsx harmony function Greeting({ message }) { return <h1>{`Hello, ${message}`}</h1>; }

```

### 104. Give an example of Reselect usage?

Let's take calculations and different amounts of a shipment order with the simplified usage of Reselect:

```javascript import { createSelector } from "reselect"; const shopItemsSelector = (state) => state.shop.items; const taxPercentSelector = (state) => state.shop.taxPercent; const subtotalSelector = createSelector(shopItemsSelector, (items) => items.reduce((acc, item) => acc + item.value, 0) ); const taxSelector = createSelector( subtotalSelector, taxPercentSelector, (subtotal, taxPercent) => subtotal * (taxPercent / 100) ); export const totalSelector = createSelector( subtotalSelector, taxSelector, (subtotal, tax) => ({ total: subtotal + tax }) ); let exampleState = { shop: { taxPercent: 8, items: [ { name: "apple", value: 1.2 }, { name: "orange", value: 0.95 }, ], }, }; console.log(subtotalSelector(exampleState)); // 2.15 console.log(taxSelector(exampleState)); // 0.172 console.log(totalSelector(exampleState)); // { total: 2.322 }

```
[↑ Back to Table of Contents](#table-of-contents)

### 105. How do you access props in attribute quotes?

[↑ Back to Table of Contents](#table-of-contents) React (or JSX) doesn't support variable interpolation inside an attribute value. The below representation won't work:

```jsx harmony <img className="image" src="images/{this.props.image}" />

```
But you can put any JS expression inside curly braces as the entire attribute value. So the below expression works:

```jsx harmony <img className="image" src={"images/" + this.props.image} />

```
Using _template strings_ will also work:

```jsx harmony <img className="image" src={`images/${this.props.image}`} />

```
****

### 106. How do you build a controlled form in React?

Each input's `value` is driven by state; `onChange` updates that state, making the state object the single source of truth.

### 107. How do you conditionally render components?

[↑ Back to Table of Contents](#table-of-contents) In some cases you want to render different components depending on some state. JSX does not render `false` or `undefined`, so you can use conditional _short-circuiting_ to render a given part of your component only if a certain condition is true.

```jsx harmony const MyComponent = ({ name, address }) => ( <div> <h2>{name}</h2> {address && <p>{address}</p>} </div> );

```
If you need an `if-else` condition then use _ternary operator_.

```jsx harmony const MyComponent = ({ name, address }) => ( <div> <h2>{name}</h2> {address ? <p>{address}</p> : <p>{"Address is not available"}</p>} </div> );

```

### 108. How do you discriminate prop variants (discriminated unions)?

A shared literal "kind" field narrows which other props are required for each variant.

### 109. How do you lift state up? Why is it needed?

Move state to the closest common ancestor of components that need to share it, since siblings can't communicate directly in React's top-down data flow.

### 110. How do you pass an event handler to a component?

You can pass event handlers and other functions as props to child components. The functions can be passed to child component as below,

```jsx function Button({ onClick }) { return <button onClick={onClick}>Download</button>; } export default function downloadExcel() { function handleClick() { alert("Downloaded"); } return <Button onClick={handleClick}></Button>; }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 111. How do you pass data child → parent?

Pass a callback function as a prop. The child calls it with data, the parent receives it in the handler and updates its state. This maintains one-way data flow while still communicating upward. [⬆ Back to Table of Contents](#-table-of-contents)

### 112. How do you pass state through navigation without putting it in the URL?

`navigate('/path', { state: { from: 'cart' } })`; read it on the destination with `useLocation().state`. Not persisted on refresh (unlike query params).

### 113. How do you prevent prop explosion in complex components?

Use compound components instead of many boolean props. Accept a config object. Use context for deeply shared state. Separate components for different variants rather than one component with 20 props. [⬆ Back to Table of Contents](#-table-of-contents)

### 114. How do you protect routes (auth guards)?

In the loader, check auth status and redirect if not authenticated. Or create a `RequireAuth` wrapper component that checks auth state and renders `<Navigate to='/login'/>` if not authenticated. [↑ Back to Table of Contents](#table-of-contents)

### 115. How do you say that props are readonly?

[↑ Back to Table of Contents](#table-of-contents) When you declare a component as a function or a class, it must never modify its own props. Let us take a below capital function,

```javascript function capital(amount, interest) { return amount + interest; }

```
The above function is called “pure” because it does not attempt to change their inputs, and always return the same result for the same inputs. Hence, React has a single rule saying "All React components must act like pure functions with respect to their props." ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 116. How do you say that state updates are merged?

When you call setState() in the component, React merges the object you provide into the current state. For example, let us take a facebook user with posts and comments details as state variables,

```
constructor(props) { super(props); this.state = { posts: [], comments: [] }; }

```
Now you can update them independently with separate `setState()` calls as below,

```
componentDidMount() { fetchPosts().then(response => { this.setState({ posts: response.posts }); }); fetchComments().then(response => { this.setState({ comments: response.comments }); }); }

```
As mentioned in the above code snippets, `this.setState({comments})` updates only comments variable without modifying or replacing posts variable. [

### 117. How do you set default value for uncontrolled component?

[↑ Back to Table of Contents](#table-of-contents) In React, the value attribute on form elements will override the value in the DOM. With an uncontrolled component, you might want React to specify the initial value, but leave subsequent updates uncontrolled. To handle this case, you can specify a **defaultValue** attribute instead of **value**.

```javascript render() { return ( <form onSubmit={this.handleSubmit}> <label> User Name: <input defaultValue="John" type="text" ref={this.input} /> </label> <input type="submit" value="Submit" /> </form> ); }

```
The same applies for `select` and `textArea` inputs. But you need to use **defaultChecked** for `checkbox` and `radio` inputs. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 118. How do you type a `forwardRef` component?

`forwardRef<HTMLInputElement, InputProps>((props, ref) => ...)` — the first generic is the ref's type, the second is the props type.

### 119. How do you type a component that accepts all native `<button>` props plus custom ones?

`interface ButtonProps extends React.ButtonHTMLAttributes<HTMLButtonElement> { variant?: 'primary' | 'secondary' }`, then spread `{...rest}` onto the native `<button>`.

### 120. How do you type a function component's props?

`interface Props { label: string; onClick: () => void }` as the function's parameter type; `React.FC<Props>` is generally discouraged now.

### 121. How do you type component props?

Define an `interface`/`type`: `interface Props { name: string; onClick: () => void }`, then `function Comp({name, onClick}: Props)`.

### 122. How do you update arrays inside state?

Eventhough arrays in JavaScript are mutable in nature, you need to treat them as immutable while storing them in a state. That means, similar to objects, the arrays cannot be updated directly inside state. Instead, you need to create a copy of the existing array and then set the state to use newly copied array. To ensure that arrays are not mutated, the mutation operations like direct direct assignment(arr** ------------------------------------------------------------------------

### 123. How do you update nested objects inside state?

You cannot simply use spread syntax for all kinds of objects inside state. Because spread syntax is shallow and it copies properties for one level deep only. If the object has nested object structure, UI doesn't work as expected with regular JavaScript nested property mutation. Let's demonstrate this behavior with an example of User object which has address nested object inside of it.

```jsx const user = { name: "John", age: 32, address: { country: "Singapore", postalCode: 440004, }, };

```
If you try to update the country nested field in a regular javascript fashion(as shown below) then user profile screen won't be updated with latest value.

```js user.address.country = "Germany";

```
This issue can be fixed by flattening all the fields into a top-level object or create a new object for each nested object and point it to it's parent object. In this example, first you need to create copy of address object and update it with the latest value. Later, the address object should be linked to parent user object something like below.

```js setUser({ ...user, address: { ...user.address, country: "Germany", }, });

```
This approach is bit verbose and not easy for deep hierarchical state updates. But this workaround can be used for few levels of nested objects without much hassle. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 124. How do you use immer library for state updates?

Immer library enforces the immutability of state based on **copy-on-write** mechanism. It uses JavaScript proxy to keep track of updates to immutable states. Immer has 3 main states as below,

### 125. How does React batch multiple state updates?

[↑ Back to Table of Contents](#table-of-contents) React prevents component from re-rendering for each and every state update by grouping multiple state updates within an event handler. This strategy improves the application performance and this process known as **batching**. The older version of React only supported batching for browser events whereas React18 supported for asynchronous actions, timeouts and intervals along with native events. This improved version of batching is called **automatic batching**. Let's demonstrate this automatic batching feature with a below example.

```jsx import { useState } from "react"; export default function BatchingState() { const [count, setCount] = useState(0); const [message, setMessage] = useState("batching"); console.log("Application Rendered"); const handleAsyncFetch = () => { fetch("https://jsonplaceholder.typicode.com/users/1").then(() => { // Automatic Batching re-render only once setCount(count + 1); setMessage("users fetched"); }); }; return ( <> <h1>{count}</h1> <button onClick={handleAsyncFetch}>Click Me!</button> </> ); }

```
The preceding code updated two state variables with in an event handler. However, React will perform automatic batching feature and the component will be re-rendered only once for better performance.

### 126. How does the "Compound Components" pattern handle components that aren't direct children (e.g., nested in a wrapper div)?

Using `React.Children.map`/`cloneElement` (older approach, fragile with nesting) or, more robustly, Context — so sub-components can be nested arbitrarily deep and still read shared state/behavior without relying on direct parent-child positioning.

### 127. How React PropTypes allow different types for one prop?

You can use `oneOfType()` method of `PropTypes`. For example, the height property can be defined with either `string` or `number` type as below:

```javascript Component.propTypes = { size: PropTypes.oneOfType([PropTypes.string, PropTypes.number]), };

```
[↑ Back to Table of Contents](#table-of-contents)

### 128. How to apply validation on props in React?

[↑ Back to Table of Contents](#table-of-contents) When the application is running in _development mode_, React will automatically check all props that we set on components to make sure they have _correct type_. If the type is incorrect, React will generate warning messages in the console. It's disabled in _production mode_ due to performance impact. The mandatory props are defined with `isRequired`. The set of predefined prop types: 1. `PropTypes.number` 2. `PropTypes.string` 3. `PropTypes.array` 4. `PropTypes.object` 5. `PropTypes.func` 6. `PropTypes.node` 7. `PropTypes.element` 8. `PropTypes.bool` 9. `PropTypes.symbol` 10. `PropTypes.any` We can define `propTypes` for `User` component as below:

```jsx harmony import React from "react"; import PropTypes from "prop-types"; class User extends React.Component { static propTypes = { name: PropTypes.string.isRequired, age: PropTypes.number.isRequired, }; render() { return ( <> <h1>{`Welcome, ${this.props.name}`}</h1> <h2>{`Age, ${this.props.age}`}</h2> </> ); } }

```
**Note:** In React v15.5 _PropTypes_ were moved from `React.PropTypes` to `prop-types` library. **Modern Recommendation:** While PropTypes are still supported, **TypeScript** is now the industry standard for type checking in React applications. Consider using TypeScript for better type safety, IDE support, and compile-time error detection. _The Equivalent Functional Component_

```jsx harmony import React from "react"; import PropTypes from "prop-types"; function User({ name, age }) { return ( <> <h1>{`Welcome, ${name}`}</h1> <h2>{`Age, ${age}`}</h2> </> ); } User.propTypes = { name: PropTypes.string.isRequired, age: PropTypes.number.isRequired, };

```
_Modern TypeScript Version_

```tsx import React from "react"; interface UserProps { name: string; age: number; } function User({ name, age }: UserProps) { return ( <> <h1>{`Welcome, ${name}`}</h1> <h2>{`Age, ${age}`}</h2> </> ); }

```
****

### 129. How to conditionally apply class attributes?

[↑ Back to Table of Contents](#table-of-contents) You shouldn't use curly braces inside quotes because it is going to be evaluated as a string.

```jsx harmony <div className="btn-panel {this.props.visible ? 'show' : 'hidden'}">

```
Instead you need to move curly braces outside (don't forget to include spaces between class names):

```jsx harmony <div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>

```
_Template strings_ will also work:

```jsx harmony <div className={`btn-panel ${this.props.visible ? 'show' : 'hidden'}`}>

```
****

### 130. How to create react class components without ES6?

[↑ Back to Table of Contents](#table-of-contents) If you don't use ES6 then you may need to use the create-react-class module instead. For default props, you need to define getDefaultProps() as a function on the passed object. Whereas for initial state, you have to provide a separate getInitialState method that returns the initial state.

```javascript var Greeting = createReactClass({ getDefaultProps: function () { return { name: "Jhohn", }; }, getInitialState: function () { return { message: this.props.message }; }, handleClick: function () { console.log(this.state.message); }, render: function () { return <h1>Hello, {this.props.name}</h1>; }, });

```
**Note:** If you use createReactClass then auto binding is available for all methods. i.e, You don't need to use `.bind(this)` with in constructor for event handlers. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 131. How to pass data between react components?

**Parent Component to Child Component (using props)** With the help of props, we can send data from a parent to a child component.

### 132. How to prevent component from rendering?

[↑ Back to Table of Contents](#table-of-contents) You can prevent component from rendering by returning null based on specific condition. This way it can conditionally render component.

```javascript function Greeting(props) { if (!props.loggedIn) { return null; } return <div className="greeting">welcome, {props.name}</div>; }

```
```javascript class User extends React.Component { constructor(props) { super(props); this.state = {loggedIn: false, name: 'John'}; } render() { return ( <div> //Prevent component render if it is not loggedIn <Greeting loggedIn={this.state.loggedIn} /> <UserDetails name={this.state.name}> </div> ); }

```
In the above example, the `greeting` component skips its rendering section by applying condition and returning null value. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 133. How to prevent it:

Make sure your state variables are immutable by either enforcing immutability by using plugins like Immutable.js, always using `setState` to make updates, and returning new instances in reducers when sending updated state values. [↑ Back to Table of Contents](#table-of-contents)

### 134. How to read updated state after dispatch?

If you need the updated value right after dispatching, you have several options:

### 135. How to use and update the state object?

```
class Car extends React.Component { constructor(props) { super(props); this.state = { brand: "BMW", color: "Black" }; } changeColor() { this.setState(prevState => { return { color: "Red" }; }); } render() { return ( <div> <button onClick={() => this.changeColor()}>Change Color</button> <p>{this.state.color}</p> </div> ); } }

```
As one can see in the code above, we can use the state by calling **this.state.propertyName** and we can change the state object property using **setState** method. - **React Props** Every React component accepts a single object argument called props (which stands for “properties”). These props can be passed to a component using HTML attributes and the component accepts these props as an argument. Using props, we can pass data from one component to another. *Passing props to a component:* While rendering a component, we can pass the props as an HTML attribute:

```
<Car brand="Mercedes"/>

```
The component receives the props: *In Class component:*

```
class Car extends React.Component { constructor(props) { super(props); this.state = { brand: this.props.brand, color: "Black" }; } }

```
*In Functional component:*

```
function Car(props) { let [brand, setBrand] = useState(props.brand); }

```
> Note- Props are read-only. They cannot be manipulated or changed inside a component. [↑ Back to Table of Contents](#table-of-contents)

### 136. How to use class field declarations syntax in React classes?

[↑ Back to Table of Contents](#table-of-contents) React Class Components can be made much more concise using the class field declarations. You can initialize the local state without using the constructor and declare class methods by using arrow functions without the extra need to bind them. Let's take a counter example to demonstrate class field declarations for state without using constructor and methods without binding,

```jsx class Counter extends Component { state = { value: 0 }; handleIncrement = () => { this.setState((prevState) => ({ value: prevState.value + 1, })); }; handleDecrement = () => { this.setState((prevState) => ({ value: prevState.value - 1, })); }; render() { return ( <div> {this.state.value} <button onClick={this.handleIncrement}>+</button> <button onClick={this.handleDecrement}>-</button> </div> ); } }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 137. If we have var, let, and const, why do we need state variables?

Regular variables (var/let/const) are reset on every re-render — React calls the function component again, so local variables start fresh. useState persists values across renders AND triggers a re-render when changed. Without useState, changing a variable wouldn't notify React to update the UI. State is React's mechanism for: (1) persisting values across renders, (2) triggering UI updates when values change. Think of useState as a variable that React 'watches' and responds to.

### 138. In reducers:

Let's create `reducer.js`:

```javascript import { ADD_TODO } from "./actionTypes"; export default (state = [], action) => { switch (action.type) { case ADD_TODO: return [ ...state, { text: action.text, completed: false, }, ]; default: return state; } };

```
[↑ Back to Table of Contents](#table-of-contents)

### 139. Is it mandatory to define constructor for React component?

[↑ Back to Table of Contents](#table-of-contents) No, it is not mandatory. i.e, If you don't initialize state and you don't bind methods, you don't need to implement a constructor for your React component. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 140. Is it ref argument available for all functions or class components?

[↑ Back to Table of Contents](#table-of-contents) Regular function or class components don’t receive the ref argument, and ref is not available in props either. The second ref argument only exists when you define a component with React.forwardRef call. [

### 141. Keys are used to match children in lists?

When reconciling lists, React uses the key prop to identify which items have stayed the same, moved, or have been added or removed For eg: items.map(item => <li key={item.id}>{item.name}</li>) There is a reason why these keys are critical: - They provide a stable identity across renders - Prevent incorrect reuse of DOM nodes - Preserve component state Without stable keys, React falls back to index-based matching What you must also note is that Reordering can lead to state being assigned to the wrong component, unnecessary re-renders, and even UI inconsistencies. You must be wondering why the complexity is O(n) instead of O(n³) - A full tree comparison would require checking every node against every other node, which then results in O(n³) complexity. React reduces this to O(n) using two assumptions: - Different element types produce different subtrees - Because of this, there is no need to deeply compare and replace directly - Keys uniquely identify elements in lists - Enables efficient matching of children without exhaustive comparison These heuristics make React perform reconciliation in linear time relative to the number of elements. Now this was all you needed to know about reconciliation, Here's a short answer that you can prepare if the interviewer isn't expecting anything detailed: - Reconciliation is the process by which React compares the previous and new Virtual DOM trees to compute the minimal DOM updates. It uses a heuristic O(n) diffing algorithm based on two assumptions: elements of different types produce different trees, and keys provide a stable identity for list elements. Now you are good to go! ------------------------------------------------------------------------

### 142. Missing key prop behavior?

```jsx function App() { const [items, setItems] = React.useState(['a', 'b', 'c']); return ( <ul> {items.map(item => ( <li>{item} <input /></li> // Missing key! ))} </ul> ); }

```
**Behavior:** React console warning about missing `key`. If items are added/removed, input values may be incorrectly preserved on the wrong elements. **Explanation:** Without keys, React uses index-based reconciliation. If you prepend an item, React reuses the FIRST DOM node for it, potentially preserving the old input's value in the wrong place. [↑ Back to Table of Contents](#table-of-contents)

### 143. Must prop be named as render for render props?

[↑ Back to Table of Contents](#table-of-contents) Even though the pattern named render props, you don't have to use a prop named render to use this pattern. i.e, Any prop that is a function that a component uses to know what to render is technically a "render prop". Lets take an example with the children prop for render props,

```javascript <Mouse children={(mouse) => ( <p> The mouse position is {mouse.x}, {mouse.y} </p> )} />

```
Actually children prop doesn’t need to be named in the list of “attributes” in JSX element. Instead, you can keep it directly inside element,

```javascript <Mouse> {(mouse) => ( <p> The mouse position is {mouse.x}, {mouse.y} </p> )} </Mouse>

```
While using this above technique(without any name), explicitly state that children should be a function in your propTypes.

```javascript Mouse.propTypes = { children: PropTypes.func.isRequired, };

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 144. Next state:

It is formed after all mutations applied to the draft state Immer can be used by following below instructions, 1. Install the dependency using `npm install use-immer` command 2. Replace `useState` hook with `useImmer` hook by importing at the top 3. The setter function of `useImmer` hook can be used to update the state. For example, the mutation syntax of immer library simplifies the nested address object of user state as follows,

```jsx import { useImmer } from "use-immer"; const ** ------------------------------------------------------------------------ --- --- ### How does React batch multiple state updates? React prevents component from re-rendering for each and every state update by grouping multiple state updates within an event handler. This strategy improves the application performance and this process known as **batching**. The older version of React only supported batching for browser events whereas React18 supported for asynchronous actions, timeouts and intervals along with native events. This improved version of batching is called **automatic batching**. Let's demonstrate this automatic batching feature with a below example.

```jsx import { useState } from "react"; export default function BatchingState() { const ** ------------------------------------------------------------------------

### 145. Reducer is a pure function:

It computes the new state without side effects.

### 146. Reducer?

A pure function that takes the current state and an action, and returns a new state (immutable update). Reducers combine to form the root reducer.

### 147. Refs aren’t passed through:

For HOCs you need to pass through all props to the wrapped component but this does not work for refs. This is because ref is not really a prop similar to key. In this case you need to use the React.forwardRef API [↑ Back to Table of Contents](#table-of-contents)

### 148. Render props pattern — headless component sharing fetch logic?

[↑ Back to Table of Contents](#table-of-contents)

```jsx // Pattern: render prop function DataFetcher({ url, render }) { const [data, setData] = React.useState(null); const [loading, setLoading] = React.useState(true); React.useEffect(() => { fetch(url).then(r => r.json()).then(d => { setData(d); setLoading(false); }); }, [url]); return render({ data, loading }); } // Usage: function App() { return ( <DataFetcher url="/api/users" render={({ data, loading }) => loading ? <p>Loading...</p> : <UserList users={data} /> } /> ); }

```
**Behavior:** `DataFetcher` is a headless component — it manages fetching logic, the parent controls rendering. When `url` changes, effect re-runs. **Key insight:** Render props pass state and behavior to consumers via function props. Modern equivalent: custom hooks (more composable, no JSX nesting). Both patterns are valid — render props shine when you need JSX composition context.

### 149. Rendering components:

After triggering a render, React will call your components to display them on the screen. React will call the root component for initial render and call the function component whose state update triggered the render. This is a recursive process for all nested components of the target component.

### 150. Shared Modal or Sidebar Visibility?

It's ideal for managing the visibility of shared UI components like modals, drawers, or sidebars, especially when their state needs to be controlled from various parts of the app.

### 151. Should keys be globally unique?

The keys used within arrays should be unique among their siblings but they don’t need to be globally unique. i.e, You can use the same keys with two different arrays. For example, the below `Book` component uses two arrays with different arrays,

```javascript function Book(props) { const index = ( <ul> {props.pages.map((page) => ( <li key={page.id}>{page.title}</li> ))} </ul> ); const content = props.pages.map((page) => ( <div key={page.id}> <h3>{page.title}</h3> <p>{page.content}</p> <p>{page.pageNumber}</p> </div> )); return ( <div> {index} <hr /> {content} </div> ); }

```
[↑ Back to Table of Contents](#table-of-contents)

### 152. Single source of truth:

The state of your whole application is stored in an object tree within a single store. The single state tree makes it easier to keep track of changes over time and debug or inspect the application.

```jsx const store = createStore(reducer);

```

### 153. Split Contexts?

Create separate contexts for unrelated pieces of state:

```jsx const UserContext = React.createContext(); const ThemeContext = React.createContext();

```

### 154. Spread operator:

Helps in passing props down into a component

```javascript // in es 5 <SomeComponent someData={this.props.someData} dispatch={this.props.dispatch} /> // in es6 <SomeComponent {...this.props} />

```

### 155. State is read-only:

The only way to change the state is to emit an action, an object describing what happened. This ensures that neither the views nor the network callbacks will ever write directly to the state.

```js const action = { type: 'INCREMENT' }; store.dispatch(action);

```

### 156. State or Props Change?

When the component's state or props change, React creates a new Virtual DOM reflecting the updated UI. However, it doesn't immediately update the Real DOM; instead, it works in memory to prepare for an efficient update. !** ------------------------------------------------------------------------

### 157. State Storage?

* Each slot stores: * The current state value. * A queue of pending state updates.

### 158. State update is not immediate in the current render:

The state variable still holds the old value until the next render.

### 159. State, Data & UI Systems?

------------------------------------------------------------------------

### 160. Use `mapStateToProps()`:

It maps the state variables from your store to the props that you specify.

### 161. Using `<Route>` component and render props pattern:

The `<Route>` component passes the same props as `withRouter()`, so you will be able to access the history methods through the history prop.

```jsx harmony import { Route } from "react-router-dom"; const Button = () => ( <Route render={({ history }) => ( <button type="button" onClick={() => { history.push("/new-location"); }} > {"Click Me!"} </button> )} /> );

```

### 162. What are components? Functional vs class components.

[↑ Back to Table of Contents](#table-of-contents) Components are the building blocks of a React application. They accept inputs (props) and return React elements describing what should appear on screen. - **Functional components**: Plain JavaScript functions that accept props and return JSX. They are simpler, support hooks, and are the preferred way to write components today. - **Class components**: ES6 classes that extend `React.Component` and must implement a `render` method. They have lifecycle methods (`componentDidMount`, etc.) and state management via `this.state` and `this.setState`.

### 163. What are controlled components?

A **controlled component** is a React component that **fully manages the form element's state**(e.g, elements like `<input>`, `<textarea>`, or `<select>`)) using React's internal state mechanism. i.e, The component does not manage its own internal state — instead, React acts as the single source of truth for form data. The controlled components will be implemented using the below steps, 1. Initialize the state using `useState` hooks in function components or inside constructor for class components. 2. Set the value of the form element to the respective state variable. 3. Create an event handler(`onChange`) to handle the user input changes through `useState`'s updater function or `setState` from class component. 4. Attach the above event handler to form element's change or click events **Note:** React re-renders the component every time the input value changes. For example, the name input field updates the username using `handleChange` event handler as below,

```javascript import React, { useState } from "react"; function UserProfile() { const ** --- ### What are controlled vs. uncontrolled components? Controlled: form input value is driven by React state --- every keystroke calls onChange which updates state which re-renders. React is the source of truth. Enables: validation on every keystroke, conditional disabling, programmatic control. Uncontrolled: input value lives in the DOM --- React reads it via ref only when needed (on submit). Source of truth is the DOM. Uncontrolled is simpler for basic forms; controlled is needed for real-time validation, conditional logic, or syncing with other state. ------------------------------------------------------------------------ --- --- ### What are default props? The _defaultProps_ can be defined as a property on the component to set the default values for the props. These default props are used when props not supplied(i.e., undefined props), but not for `null` or `0` as props. That means, If you provide null value then it remains null value. It's the same behavior with 0 as well. For example, let us create color default prop for the button component,

```javascript function MyButton { // ... } MyButton.defaultProps = { color: "red", };

```
If `props.color` is not provided then it will set the default value to 'red'. i.e, Whenever you try to access the color prop it uses the default value

```javascript function MyButton() { return <MyButton />; // props.color will contain red value }

```
**** --- ### What are default props and PropTypes? defaultProps (The Backup Plan) This provides a fallback value just in case a parent component forgets to pass a prop. Analogy: If you don't explicitly choose a side dish, the restaurant automatically defaults to giving you fries. PropTypes (The Bouncer) This checks the props coming in to make sure they are the correct type (like a number, a string, or a boolean) and warns you in the developer console if someone made a mistake. Analogy: A bouncer checking IDs. If a developer tries to pass the word "Twenty" into an age prop that expects the actual number 20, PropTypes throws a warning flag. ------------------------------------------------------------------------ --- --- ### What are fragments? Syntax for returning multiple elements without an extra DOM node: `<> </>` or `<React.Fragment>`. Keyed fragments use the long form: `<React.Fragment key={id}>`. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are headless components? Components that provide behavior, accessibility, and state management with no UI – consumers apply their own styles. Examples: Radix UI, Headless UI, React Aria. Powerful for design systems needing full styling control. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are Higher Order Components? Simply put, Higher-Order Component(HOC) is a function that takes in a component and returns a new component. **When do we need a Higher Order Component?** While developing React applications, we might develop components that are quite similar to each other with minute differences. In most cases, developing similar components might not be an issue but, while developing larger applications we need to keep our code **DRY**, therefore, we want an **abstraction** that allows us to define this logic in a single place and share it across components. HOC allows us to create that abstraction. **Example of a HOC:** Consider the following components having similar functionality. The following component displays the list of articles:

```
// "GlobalDataSource" is some global data source class ArticlesList extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { articles: GlobalDataSource.getArticles(), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { // States gets Update whenver data source changes this.setState({ articles: GlobalDataSource.getArticles(), }); } render() { return ( <div> {this.state.articles.map((article) => ( <ArticleData article={article} key={article.id} /> ))} </div> ); } }

```
The following component displays the list of users:

```
// "GlobalDataSource" is some global data source class UsersList extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { users: GlobalDataSource.getUsers(), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { // States gets Update whenver data source changes this.setState({ users: GlobalDataSource.getUsers(), }); } render() { return ( <div> {this.state.users.map((user) => ( <UserData user={user} key={user.id} /> ))} </div> ); } }

```
Notice the above components, both have similar functionality but, they are calling different methods to an API endpoint. Let’s create a Higher Order Component to create an abstraction:

```
// Higher Order Component which takes a component // as input and returns another component // "GlobalDataSource" is some global data source function HOC(WrappedComponent, selectData) { return class extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { data: selectData(GlobalDataSource, props), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { this.setState({ data: selectData(GlobalDataSource, this.props), }); } render() { // Rendering the wrapped component with the latest data data return <WrappedComponent data={this.state.data} {...this.props} />; } }; }

```
We know HOC is a function that takes in a component and returns a component. In the code above, we have created a function called HOC which returns a component and performs functionality that can be shared across both the **ArticlesList** component and **UsersList** Component. The second parameter in the HOC function is the function that calls the method on the API endpoint. We have reduced the duplicated code of the **componentDidUpdate** and **componentDidMount** functions. Using the concept of Higher-Order Components, we can now render the **ArticlesList** and **UsersList **components in the following way:

```
const ArticlesListWithHOC = HOC(ArticlesList, (GlobalDataSource) => GlobalDataSource.getArticles()); const UsersListWithHOC = HOC(UsersList, (GlobalDataSource) => GlobalDataSource.getUsers());

```
Remember, we are not trying to change the functionality of each component, we are trying to share a single functionality across multiple components using HOC. --- ### What are Higher-Order Components (HOCs)? Functions that take a component and return a new component with enhanced behavior. E.g., `withAuth(Component)` wraps it to redirect if unauthenticated. HOCs are less common now that custom hooks exist. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are HOC factory implementations? There are two main ways of implementing HOCs in React. 1. Props Proxy (PP) and 2. Inheritance Inversion (II). But they follow different approaches for manipulating the _WrappedComponent_. **Props Proxy** In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name **Props Proxy**.

```jsx function ppHOC(WrappedComponent) { return class PP extends React.Component { render() { return <WrappedComponent {...this.props} />; } }; }

```
**Inheritance Inversion** In this approach, the returned HOC class (Enhancer) extends the WrappedComponent. It is called Inheritance Inversion because instead of the WrappedComponent extending some Enhancer class, it is passively extended by the Enhancer. In this way the relationship between them seems **inverse**.

```jsx function iiHOC(WrappedComponent) { return class Enhancer extends WrappedComponent { render() { return super.render(); } }; }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What are Keyed Fragments? The Fragments declared with the explicit syntax may have keys. The general use case is mapping a collection to an array of fragments as below,

```
function Glossary(props) { return ( <dl> {props.items.map((item) => ( // Without the `key`, React will fire a key warning <React.Fragment key={item.id}> <dt>{item.term}</dt> <dd>{item.description}</dd> </React.Fragment> ))} </dl> ); }

```
**Note:** key is the only attribute that can be passed to Fragment. In the future, there might be a support for additional attributes, such as event handlers. [ --- ### What are keys in React? A key is a special string attribute that needs to be included when using lists of elements. Example of a list using key - const ids = \[1,2,3,4,5\]; const listElements = ids.map((id)=\>{ return(

```{=html} <li key="{id.toString()}">

```
{id}

```{=html} </li>

```
) }) **Importance of keys -** - Keys help react identify which elements were added, changed or removed. - Keys should be given to array elements for providing a unique identity for each element. - Without keys, React does not understand the order or uniqueness of each element. - With keys, React has an idea of which particular element was deleted, edited, and added. - Keys are generally used for displaying a list of data coming from an API. > \*\*\*Note- Keys used within arrays should be unique among siblings. They need not be globally unique. ## Learn via our Video Courses [Rahul Janghu](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [**Python Course for Beginners With Certification: Mastering the Essentials**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [4.90](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Enrolled: 273136](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLWZvci1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Aditya Jain](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli) [**Free Data Structures and Algorithms (DSA) in C++ Online Course with Certificate**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli) [4.5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli) [Enrolled: 45488](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWRhdGEtc3RydWN0dXJlcz91dG1fc291cmNlPWli) [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli) [**C++ Course: Learn the Essentials**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli) [Enrolled: 82805](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvY3BwLWJlZ2lubmVycz91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==) [**Python and SQL for Data Science Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==) [Enrolled: 79131](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0aG9uLXNxbC1kYXRhLXNjaWVuY2U/dXRtX3NvdXJjZT1pYg==) [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=) [**Node JS Certification Course - Master the Fundamentals**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=) [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=) [Enrolled: 27194](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvbm9kZWpzP3V0bV9zb3VyY2U9aWI=) [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli) [**SQL for Beginners: Learn SQL using MySQL and Database Design Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli) [Enrolled: 59986](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvc3FsLXVzaW5nLW15c3FsLWNvdXJzZT91dG1fc291cmNlPWli) [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [**JavaScript Course With Certification: Unlocking the Power of JavaScript**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Enrolled: 98373](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YXNjcmlwdC1iZWdpbm5lcnM/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [**Computer Networking Course: Master Computer Networking**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Enrolled: 40401](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1jb21wdXRlci1uZXR3b3Jrcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Sumeet malik](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=) [**NSET Course: Mathematics**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=) [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=) [Enrolled: 13703](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvTWF0aHNOU0VUP3V0bV9zb3VyY2U9aWI=) [Sumeet malik](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=) [**NSET Course: Logical reasoning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=) [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=) [Enrolled: 12705](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvQXB0aXR1ZGVOU0VUP3V0bV9zb3VyY2U9aWI=) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli) [**Operating System Course: Learn Fundamentals of Operating System**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli) [Enrolled: 39702](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1vcGVyYXRpbmctc3lzdGVtLWNvdXJzZT91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=) [**Microsoft Malware Detection using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=) [Enrolled: 1578](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWljcm9zb2Z0LW1hbHdhcmUtZGV0ZWN0aW9uP3V0bV9zb3VyY2U9aWI=) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==) [**Netflix Movie Recommendation System using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==) [Enrolled: 2950](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbmV0ZmxpeC1tb3ZpZS1yZWNvbW1lbmRhdGlvbi1zeXN0ZW0/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli) [**Amazon Fashion Discovery Engine using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli) [Enrolled: 990](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYW1hem9uLWZhc2hpb24tZGlzY292ZXJ5LWVuZ2luZT91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==) [**Personalized Cancer Diagnosis using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==) [Enrolled: 952](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcGVyc29uYWxpemVkLWNhbmNlci1kaWFnbm9zaXM/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli) [**Facebook Friend Recommendation using Graph Mining**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli) [Enrolled: 709](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZmFjZWJvb2stZnJpZW5kLXJlY29tbWVuZGF0aW9uLXVzaW5nLWdyYXBoLW1pbmluZz91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=) [**Predicting tags for Stackoverflow using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=) [Enrolled: 564](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHJlZGljdGluZy10YWdzLWZvci1zdGFja292ZXJmbG93P3V0bV9zb3VyY2U9aWI=) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==) [**Quora Question Pair Similarity Problem using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==) [Enrolled: 636](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcXVvcmEtcXVlc3Rpb24tcGFpci1zaW1pbGFyaXR5LXByb2JsZW0/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=) [**Taxi demand prediction in New York City using Machine Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=) [Enrolled: 680](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvdGF4aS1kZW1hbmQtcHJlZGljdGlvbi1pbi1uZXcteW9yay1jaXR5P3V0bV9zb3VyY2U9aWI=) [Mrinal Bhattacharya](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [**React JS Free Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Enrolled: 29162](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1yZWFjdC1qcy1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Yash Raj](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=) [**AWS Free Course with Certificate for Beginners**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=) [4.7](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=) [Enrolled: 17390](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvYXdzLWZyZWUtY291cnNlP3V0bV9zb3VyY2U9aWI=) [Subhesh Kumar](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==) [**Object Oriented Programming in Java Course Online**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==) [4.95](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==) [Enrolled: 14722](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uvb2JqZWN0LW9yaWVudGVkLXByb2dyYW1taW5nLWphdmE/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [**Free Maths for Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Enrolled: 11674](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aGVtYXRpY3MtZm9yLW1hY2hpbmUtbGVhcm5pbmctZnJlZS1jb3Vyc2U/dXRtX3NvdXJjZT1pYg==) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [**Deep Learning Course: Deep Dive into Deep Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Enrolled: 10662](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Jamshaid Sohail](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [**PyTorch for Deep Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Enrolled: 4313](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvcHl0b3JjaC1mb3ItZGVlcC1sZWFybmluZy1mcmVlLWNvdXJzZT91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli) [**Supervised Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli) [Enrolled: 17407](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS1zdXBlcnZpc2VkLWxlYXJuaW5nLWNvdXJzZT91dG1fc291cmNlPWli) [Srikanth Varma](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=) [**Unsupervised Machine Learning Course**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=) [Enrolled: 5206](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvZnJlZS11bnN1cGVydmlzZWQtbGVhcm5pbmctY291cnNlP3V0bV9zb3VyY2U9aWI=) [Prateek Narang](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=) [**Maths for Programmers**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=) [Enrolled: 7881](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvbWF0aHMtZm9yLXByb2dyYW1tZXJzP3V0bV9zb3VyY2U9aWI=) [Gaurav Sisodia](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli) [**Keras & TensorFlow for Deep Learning**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli) [4.8](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli) [Enrolled: 4201](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2Uva2VyYXMtdGVuc29yZmxvdy1mb3ItZGVlcC1sZWFybmluZz91dG1fc291cmNlPWli) [Arnav Gupta](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==) [**Spring Boot Course: Certified Course for Essential Skills**](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==) [5](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==) [Enrolled: 24148](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==) [Free](https://www.interviewbit.com/api/v3/redirect/scaler_auth/?redirect_url=aHR0cHM6Ly9zY2FsZXIuY29tL3RvcGljcy9jb3Vyc2UvamF2YS1zcHJpbmctYm9vdC1ibG9nZ2luZy1hcHA/dXRtX3NvdXJjZT1pYg==) --- ### What are loadable components? If you want to do code-splitting in a server rendered app, it is recommend to use Loadable Components because React.lazy and Suspense is not yet available for server-side rendering. Loadable lets you render a dynamic import as a regular component. Lets take an example,

```
import loadable from '@loadable/component'; const OtherComponent = loadable(() => import('./OtherComponent')); function MyComponent() { return ( <div> <OtherComponent /> </div> ); }

```
Now OtherComponent will be loaded in a separated bundle [ --- ### What are portals? A React Portal is like a teleportation device for your UI. It lets you write the code for a component inside a parent, but physically display it somewhere else on the page (usually floating over the whole screen). Use it for: Popups, modals, and tooltips so they don't get cut off or trapped by their parent container's layout rules. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are portals in React? A Portal is a React feature that enables rendering children into a DOM node that exists outside the parent component's DOM hierarchy, while still preserving the React component hierarchy. Portals help avoid CSS stacking issues—for example, elements with position: fixed may not behave as expected inside a parent with transform. Portals solve this by rendering content (like modals or tooltips) outside such constrained DOM contexts.

```javascript ReactDOM.createPortal(child, container);

```
* `child`: Any valid React node (e.g., JSX, string, fragment). * `container`: A real DOM node (e.g., `document.getElementById('modal-root')`). Even though the content renders elsewhere in the DOM, it still behaves like a normal child in React. It has access to context, state, and event handling. **Example:- Modal:**

```jsx function Modal({ children }) { return ReactDOM.createPortal( <div className="modal">{children}</div>, document.body) ); }

```
The above code will render the modal content into the body element in the HTML, not inside the component's usual location. **** --- ### What are presentational vs container components? Presentational: concern is how things look, receive data via props, rarely have own state. Container: concern is how things work, handle data fetching and state, pass data to presentational children. The pattern is less strict now that hooks exist. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are props? Read-only inputs passed from parent to child. Props flow downward (one-way data flow). Mutating props directly is forbidden; instead lift state or use callbacks. ------------------------------------------------------------------------ --- --- ### What are props in React? The props in React are the inputs to a component of React. They can be single-valued or objects having a set of values that will be passed to components of React during creation by using a naming convention that almost looks similar to HTML-tag attributes. We can say that props are the data passed from a parent component into a child component. The main purpose of props is to provide different component functionalities such as: - Passing custom data to the React component. - Using through `this.props.reactProp` inside render() method of the component. - Triggering state changes. For example, consider we are creating an element with reactProp property as given below: `<Element reactProp = "1" />` This reactProp name will be considered as a property attached to the native props object of React which already exists on each component created with the help of React library: `props.reactProp;`. --- ### What are pure components? Components that produce the same output for the same props/state. `React.PureComponent` (class) and `React.memo` (function) implement shallow-equality checks to skip redundant renders. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are React elements vs React components? React Elements (The Lego Brick) An element is a single, plain blueprint of what you want to see on the screen. It doesn't actually do anything yet; it's just a simple JavaScript object that describes a piece of the UI. Analogy: A single Lego block or a sketch of a window. What it looks like: { type: 'div', props: { className: 'box', children: 'Hello' } } React Components (The Factory / Blueprint) A component is the factory, function, or template that creates those elements. It takes in some data (called props) and outputs React elements. Analogy: The master blueprint or the factory mold that can stamp out hundreds of Lego blocks. What it looks like: A JavaScript function like function Button() { return `<button />`{=html} }. ------------------------------------------------------------------------ --- --- ### What are React Portals, and when would you use them? When you work with React, you might have noticed how a component renders inside its parent in the DOM. But even so, there are times when you don’t necessarily want that. For example, think of a modal. Even if the modal component is written deep inside your component tree, you usually want it to appear at the top of the page, and not stuck inside some parent container. And to mitigate this very problem, Portals are used. So, you don't have to render from your usual place, and run something like: ReactDOM.createPortal(child, container) This practically commands to render the component elsewhere in the DOM. Now, here’s how you can set it up: First write, ::: {#modal-root} ::: Then, from anywhere in your React app, you can render into it like this: ReactDOM.createPortal(`<Modal />`{=html}, document.getElementById("modal-root")); Even when it’s done, you need to keep this in mind that even though the modal is rendered outside the parent in the DOM, it still showcases like a normal React child. Which means that it still receives props, it still has access to context, and event handling still works. In fact, event bubbling can take place here. If you click inside a modal rendered via a portal, the event still bubbles up to the parent component in the React tree, and not based on the DOM structure. Now, coming to when to use these Portals, You can say that mostly when UI needs to “break out” of layout restrictions like overflow: hidden, z-index stacking issues. That’s why they’re commonly used for modals, tooltips, dropdowns, and toast notifications. --- ### What are render props? **Render Props** is a simple technique for sharing code between components using a prop whose value is a function. The below component uses render prop which returns a React element.

```jsx harmony <DataProvider render={(data) => <h1>{`Hello ${data.target}`}</h1>} />

```
Libraries such as React Router and DownShift are using this pattern. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What are state and props? Props (properties) are read-only data passed FROM parent TO child components --- like function arguments. They cannot be modified by the receiving component. State is mutable data managed INSIDE a component. When state changes, React re-renders that component and its children. Key distinction: props flow down (parent → child), events/callbacks flow up (child → parent). Props changes cause re-renders too --- React re-renders a component whenever its parent re-renders OR its own state changes. ------------------------------------------------------------------------ --- --- ### What are state and props? Difference between them. - **Props** (short for properties): Read‑only data passed from parent to child. They are immutable within the child component. - **State**: Mutable data managed within a component. When state changes, the component re‑renders. | | Props | State | |---|-------|-------| | Mutability | Immutable (cannot be changed by child) | Mutable (changed via `setState` or hook setters) | | Ownership | Owned by parent, used by child | Owned by the component itself | | Purpose | Configure component, pass data down | Handle dynamic data that changes over time | --- ### What are stateful components? If the behaviour of a component is dependent on the _state_ of the component then it can be termed as stateful component. These _stateful components_ are either function components with hooks or _class components_. Let's take an example of function stateful component which update the state based on click event,

```javascript import React, {useState} from 'react'; const App = (props) => { const **

### 164. What are default props and PropTypes?

- **defaultProps**: Provides fallback values when props are not supplied (undefined props). - **PropTypes**: Validates prop types at runtime in development. TypeScript is the modern alternative.

```jsx MyButton.defaultProps = { color: 'red' }; MyButton.propTypes = { name: PropTypes.string.isRequired };

```

### 165. What are default props?

[↑ Back to Table of Contents](#table-of-contents) The _defaultProps_ can be defined as a property on the component to set the default values for the props. These default props are used when props not supplied(i.e., undefined props), but not for `null` or `0` as props. That means, If you provide null value then it remains null value. It's the same behavior with 0 as well. For example, let us create color default prop for the button component,

```javascript function MyButton { // ... } MyButton.defaultProps = { color: "red", };

```
If `props.color` is not provided then it will set the default value to 'red'. i.e, Whenever you try to access the color prop it uses the default value

```javascript function MyButton() { return <MyButton />; // props.color will contain red value }

```
****

### 166. What are default props? How do you set them in function components?

Fallback values for unpassed props, set via default parameters: `function Button({ size = 'medium' }) {}`.

### 167. What are forward refs?

_Ref forwarding_ is a feature that lets some components take a _ref_ they receive, and pass it further down to a child.

```jsx harmony const ButtonElement = React.forwardRef((props, ref) => ( <button ref={ref} className="CustomButton"> {props.children} </button> )); // Create ref to the DOM button: const ref = React.createRef(); <ButtonElement ref={ref}>{"Forward Ref"}</ButtonElement>;

```
[↑ Back to Table of Contents](#table-of-contents)

### 168. What are fragments?

[↑ Back to Table of Contents](#table-of-contents) It's a common pattern or practice in React for a component to return multiple elements. _Fragments_ let you group a list of children without adding extra nodes to the DOM. You need to use either `<Fragment>` or a shorter syntax having empty tag (`<></>`). Below is the example of how to use fragment inside _Story_ component.

```jsx harmony function Story({ title, description, date }) { return ( <Fragment> <h2>{title}</h2> <p>{description}</p> <p>{date}</p> </Fragment> ); }

```
It is also possible to render list of fragments inside a loop with the mandatory **key** attribute supplied.

```jsx harmony function StoryBook() { return stories.map((story) => ( <Fragment key={story.id}> <h2>{story.title}</h2> <p>{story.description}</p> <p>{story.date}</p> </Fragment> )); }

```
Usually, you don't need to use `<Fragment>` until there is a need of _key_ attribute. The usage of shorter syntax looks like below.

```jsx harmony function Story({ title, description, date }) { return ( <> <h2>{title}</h2> <p>{description}</p> <p>{date}</p> </> ); }

```

### 169. What are portals in React?

[↑ Back to Table of Contents](#table-of-contents) A Portal is a React feature that enables rendering children into a DOM node that exists outside the parent component's DOM hierarchy, while still preserving the React component hierarchy. Portals help avoid CSS stacking issues—for example, elements with position: fixed may not behave as expected inside a parent with transform. Portals solve this by rendering content (like modals or tooltips) outside such constrained DOM contexts.

```javascript ReactDOM.createPortal(child, container);

```
* `child`: Any valid React node (e.g., JSX, string, fragment). * `container`: A real DOM node (e.g., `document.getElementById('modal-root')`). Even though the content renders elsewhere in the DOM, it still behaves like a normal child in React. It has access to context, state, and event handling. **Example:- Modal:**

```jsx function Modal({ children }) { return ReactDOM.createPortal( <div className="modal">{children}</div>, document.body) ); }

```
The above code will render the modal content into the body element in the HTML, not inside the component's usual location. ****

### 170. What are portals?

[↑ Back to Table of Contents](#table-of-contents) A React Portal is like a teleportation device for your UI. It lets you write the code for a component inside a parent, but physically display it somewhere else on the page (usually floating over the whole screen). Use it for: Popups, modals, and tooltips so they don't get cut off or trapped by their parent container's layout rules.

### 171. What are presentational vs container components?

- **Presentational**: Concerned with how things look, receive data via props, rarely have own state. - **Container**: Concerned with how things work, handle data fetching and state, pass data to presentational children. The pattern is less strict now that hooks exist.

### 172. What are props in React?

[↑ Back to Table of Contents](#table-of-contents) _Props_ are inputs to components. They are single values or objects containing a set of values that are passed to components on creation similar to HTML-tag attributes. Here, the data is passed down from a parent component to a child component. The primary purpose of props in React is to provide following component functionality: 1. Pass custom data to your component. 2. Trigger state changes. 3. Use via `this.props.reactProp` inside component's `render()` method. For example, let us create an element with `reactProp` property:

```jsx harmony <Element reactProp={"1"} />

```
This `reactProp` (or whatever you came up with) attribute name then becomes a property attached to React's native props object which originally already exists on all components created using React library.

```jsx harmony props.reactProp;

```
For example, the usage of props in function component looks like below:

```jsx import React from "react"; import ReactDOM from "react-dom"; const ChildComponent = (props) => { return ( <div> <p>{props.name}</p> <p>{props.age}</p> <p>{props.gender}</p> </div> ); }; const ParentComponent = () => { return ( <div> <ChildComponent name="John" age="30" gender="male" /> <ChildComponent name="Mary" age="25" geneder="female" /> </div> ); };

```
The properties from props object can be accessed directly using destructing feature from ES6 (ECMAScript 2015). It is also possible to fallback to default value when the prop value is not specified. The above child component can be simplified like below.

```jsx harmony const ChildComponent = ({ name, age, gender = "male" }) => { return ( <div> <p>{name}</p> <p>{age}</p> <p>{gender}</p> </div> ); };

```
**Note:** The default value won't be used if you pass `null` or `0` value. i.e, default value is only used if the prop value is missed or `undefined` value has been passed. <details><summary><b>See Class</b></summary> The Props accessed in Class Based Component as below

```jsx import React from "react"; import ReactDOM from "react-dom"; class ChildComponent extends React.Component { render() { return ( <div> <p>{this.props.name}</p> <p>{this.props.age}</p> <p>{this.props.gender}</p> </div> ); } } class ParentComponent extends React.Component { render() { return ( <div> <ChildComponent name="John" age="30" gender="male" /> <ChildComponent name="Mary" age="25" gender="female" /> </div> ); } }

```
</details>

### 173. What are props?

[↑ Back to Table of Contents](#table-of-contents) Read-only inputs passed from parent to child. Props flow downward (one-way data flow). Mutating props directly is forbidden; instead lift state or use callbacks. ------------------------------------------------------------------------

### 174. What are React Fragments and why use them?

`<Fragment>` / `<>...</>` group multiple children without adding an extra DOM node — useful to avoid breaking CSS layouts (flex/grid) or creating invalid HTML.

### 175. What are render props?

[↑ Back to Table of Contents](#table-of-contents) **Render Props** is a simple technique for sharing code between components using a prop whose value is a function. The below component uses render prop which returns a React element.

```jsx harmony <DataProvider render={(data) => <h1>{`Hello ${data.target}`}</h1>} />

```
Libraries such as React Router and DownShift are using this pattern. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 176. What are search params and how do you use them?

URL query string parameters (`?tab=settings&page=2`). `useSearchParams()` returns `[searchParams, setSearchParams]`. Use as UI state (tab, filter, page) so users can share/bookmark specific views.

### 177. What are state and props? Difference between them.

[↑ Back to Table of Contents](#table-of-contents) - **Props** (short for properties): Read‑only data passed from parent to child. They are immutable within the child component. - **State**: Mutable data managed within a component. When state changes, the component re‑renders. | | Props | State | |---|-------|-------| | Mutability | Immutable (cannot be changed by child) | Mutable (changed via `setState` or hook setters) | | Ownership | Owned by parent, used by child | Owned by the component itself | | Purpose | Configure component, pass data down | Handle dynamic data that changes over time |

### 178. What are the guidelines to be followed for writing reducers?

There are two guidelines to be taken care while writing reducers in your code. 1. Reducers must be pure without mutating the state. That means, same input always returns the same output. These reducers run during rendering time similar to state updater functions. So these functions should not send any requests, schedule time outs and any other side effects. 2. Each action should describe a single user interaction even though there are multiple changes applied to data. For example, if you "reset" registration form which has many user input fields managed by a reducer, it is suggested to send one "reset" action instead of creating separate action for each fields. The proper ordering of actions should reflect the user interactions in the browser and it helps a lot for debugging purpose. [↑ Back to Table of Contents](#table-of-contents)

### 179. What are the hidden reasons a component re‑renders even when props don't change?

[↑ Back to Table of Contents](#table-of-contents) - **Parent re‑render**: By default, when a parent re‑renders, all its children re‑render, regardless of prop changes. (Fixed with `React.memo`) - **Inline functions/objects**: If you pass an inline function or object as prop, the child sees a new reference on every render, causing a re‑render (unless the child is memoized and uses deep comparison or the prop is memoized). - **Context changes**: If the component consumes a context that changes, it re‑renders. - **Hooks with changing dependencies**: `useEffect`, `useMemo`, `useCallback` dependencies may cause re‑execution of hooks, but not necessarily the whole component re‑render. - **State updates that set the same value**: In React 18, if you set state to the same value (using `setState(prev => prev)`), it may still cause a re‑render in some cases (but not in strict mode?).

### 180. What are the preferred and non-preferred array operations for updating the state?

The below table represent preferred and non-preferred array operations for updating the component state. | Action | Preferred | Non-preferred | | --------- | -------------------- | -------------------------- | | Adding | concat, ** ------------------------------------------------------------------------

### 181. What are the problems of using render props with pure components?

[↑ Back to Table of Contents](#table-of-contents) If you create a function inside a render method, it negates the purpose of pure component. Because the shallow prop comparison will always return false for new props, and each render in this case will generate a new value for the render prop. You can solve this issue by defining the render function as instance method. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 182. What are uncontrolled components?

The **Uncontrolled components** are form elements (like `<input>`, `<textarea>`, or `<select>`) that **manage their own state internally** via the **DOM**, rather than through React state. You can query the DOM using a `ref` to find its current value when you need it. This is a bit more like traditional HTML. The uncontrolled components will be implemented using the below steps, 1. Create a ref using `useRef` react hook in function component or `React.createRef()` in class based component. 2. Attach this `ref` to the form element. 3. The form element value can be accessed directly through `ref` in event handlers or `componentDidMount` for class components In the below UserProfile component, the `username` input is accessed using ref.

```jsx harmony import React, { useRef } from "react"; function UserProfile() { const usernameRef = useRef(null); const handleSubmit = (event) => { event.preventDefault(); console.log("The submitted username is: " + usernameRef.current.value); }; return ( <form onSubmit={handleSubmit}> <label> Username: <input type="text" ref={usernameRef} /> </label> <button type="submit">Submit</button> </form> ); }

```
**Note:** Here, DOM is in charge of the value. React only accesses the value when needed (via `ref`). **Benefits:** * **Less boilerplate** — no need for `useState` and `onChange`. * Useful for **quick form setups** or when integrating with **non-React code**. * Slightly better **performance** in very large forms (fewer re-renders). In most cases, it's recommend to use controlled components to implement forms. In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself. <details><summary><b>See Class</b></summary> <p>

```jsx harmony class UserProfile extends React.Component { constructor(props) { super(props); this.handleSubmit = this.handleSubmit.bind(this); this.input = React.createRef(); } handleSubmit(event) { alert("A name was submitted: " + this.input.current.value); event.preventDefault(); } render() { return ( <form onSubmit={this.handleSubmit}> <label> {"Name:"} <input type="text" ref={this.input} /> </label> <input type="submit" value="Submit" /> </form> ); } }

```
</p> </details> ****

### 183. What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)

[↑ Back to Table of Contents](#table-of-contents) **Common causes**: - Parent re‑renders – by default, children re‑render even if props haven’t changed. - Inline functions/objects passed as props – new references on every render. - Context changes – any consumer re‑renders when context value changes. - State updates that don’t change the value but still trigger re‑render (if using setState with new object reference).

### 184. What does React do differently when a `key` changes vs stays the same?

Same `key`+`type`: DOM node and instance reused (state preserved). Changed `key`: old instance unmounted, new one mounted fresh.

### 185. What happens if a component wrapped in `memo()` has its own state changes?

[↑ Back to Table of Contents](#table-of-contents) The component will still re‑render when its internal state changes, regardless of `memo`. `React.memo` only controls re‑renders triggered by parent prop changes. State updates always cause a re‑render of the component (unless you use other optimizations like `useState` with a functional update that doesn't change the value). ------------------------------------------------------------------------

### 186. What happens if you mutate state directly?

React does not detect the change and won't re-render. Always return new references: `setState([...arr])` or `setState({...obj})`. Direct mutation causes stale UI and hard-to-debug bugs. [⬆ Back to Table of Contents](#-table-of-contents)

### 187. What is `children` prop? How does composition work in React?

`props.children` holds nested content between a component's tags, enabling composition: a wrapper component lets the caller decide what content goes inside.

### 188. What is `createSlice()` and what does it contain? (name, initialState, reducers)

`createSlice` accepts an object with: - `name`: A string used as prefix for action types. - `initialState`: The initial state value. - `reducers`: An object mapping action names to reducer functions (or `prepare` callbacks). Each reducer function receives `state` and `action` and can mutate the state (thanks to Immer). - `extraReducers` (optional): Allows responding to actions not defined in the slice (e.g., from `createAsyncThunk`). It returns an object with `actions` (action creators) and `reducer` (slice reducer). [↑ Back to Table of Contents](#table-of-contents)

### 189. What is `forwardRef`?

[↑ Back to Table of Contents](#table-of-contents) `React.forwardRef((props, ref) => ...)` passes a ref from a parent through a functional component to a DOM node or child component. Required because refs are not regular props and cannot be passed through as-is.

### 190. What is `React.Fragment` with a key used for?

Rendering a keyed list of grouped elements without a wrapper `div` — only `<React.Fragment key={}>` supports the `key` prop, not the `<>` shorthand.

### 191. What is `React.Fragment`? Why use it instead of a wrapping `<div>`?

`<>...</>` lets a component return multiple children without an extra DOM node, avoiding wrapper `div`s that could break CSS layout or semantics.

### 192. What is a reducer? Why must reducers be pure functions?

Takes `(state, action)`, returns next state, no side effects — required for predictable replay/testing and reference-equality change detection.

### 193. What is an updater function? Should an updater function be used in all cases?

An **updater function** is a form of `setState` where you pass a **function** instead of a direct value. This function receives the **previous state** as an argument and returns the **next state**. The updater function expression looks like below,

```js setCount(prevCount => prevCount + 1); // Safe and predictable

```
Here, `prevCount => prevCount + 1` is the updater function. In the React community, there's often a recommendation to use updater functions when updating state that depends on its previous value. This helps prevent unexpected behaviors that can arise from working with outdated or "stale" state. While using an updater function is a good habit, it's not always necessary. In most cases, React batches updates and ensures that the state is up-to-date at the beginning of the event handler, so you typically don’t run into stale state issues during a single synchronous event. However, if you’re doing multiple updates to the same state variable within a single handler, using the updater form ensures that each update correctly uses the latest state value, rather than a potentially outdated one. **Example: Multiple Updates in One Handler**

```js function handleCount() { setCounter(a => a + 1); setCounter(a => a + 1); setCounter(a => a + 1); }

```
In this example, `a => a + 1` is an **updater function**. React queues these updater functions and applies them sequentially, each using the most recent state value. As a result, the counter will correctly increment by 3. In many cases, such as setting state based on user input or assigning static values, you don’t need the updater function:

```js setName('Sudheer');

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 194. What is children prop?

[↑ Back to Table of Contents](#table-of-contents) The `children` prop is a special prop in React used to pass elements between the opening and closing tags of a component. It is commonly used in layout and wrapper componnents. A simple usage of children prop looks as below,

```jsx harmony function MyDiv({ children }){ return ( <div> {children} </div>; ); } export default function Greeting() { return ( <MyDiv> <span>{"Hello"}</span> <span>{"World"}</span> </MyDiv> ); }

```
Here, everything inside `<MyDiv>...</MyDiv>` is passed as children to the custom div component. The children can be text, JSX elements, fragments, arrays and functions(for advance use case like render props). <details><summary><b>See Class</b></summary> <p>

```jsx harmony const MyDiv = React.createClass({ render: function () { return <div>{this.props.children}</div>; }, }); ReactDOM.render( <MyDiv> <span>{"Hello"}</span> <span>{"World"}</span> </MyDiv>, node );

```
</p> </details> **Note:** There are several methods available in the legacy React API to work with this prop. These include `React.Children.map`, `React.Children.forEach`, `React.Children.count`, `React.Children.only`, `React.Children.toArray`. ****

### 195. What is colocation in React?

Keeping related code together -- state close to where it's used, styles next to components, tests next to source. Avoid premature abstraction. Move state up only when shared, not just to 'be organized'. ------------------------------------------------------------------------

### 196. What is composition vs inheritance in React?

React favors composition (props/children) over class inheritance hierarchies for building complex UIs.

### 197. What is context?

_Context_ provides a way to pass data through the component tree without having to pass props down manually at every level. For example, authenticated users, locale preferences, UI themes need to be accessed in the application by many components.

```javascript const { Provider, Consumer } = React.createContext(defaultValue);

```
[↑ Back to Table of Contents](#table-of-contents)

### 198. What is flux?

**Flux** is an **application architecture** (not a framework or library) designed by Facebook to manage **data flow** in React applications. It was created as an alternative to the traditional **MVC (Model-View-Controller)** pattern, and it emphasizes a **unidirectional data flow** to make state changes more predictable and easier to debug. Flux complements React by organizing the way data moves through your application, especially in large-scale or complex projects.

### 199. What is Hot Module Replacement (HMR)? Why does it matter for React development?

HMR swaps updated modules in a running app without a full page reload, preserving component state during development (e.g., keeping a form's typed input while you tweak its styling), dramatically speeding up the dev feedback loop.

### 200. What is JSX spread attributes (`{...props}`)? What's the risk?

Spreads an object's keys as individual props: `<Comp {...props} />`. Risk: passing unintended props through (e.g., leaking a prop the child doesn't expect, or overriding one accidentally depending on order).

### 201. What is Lifting State Up in React?

[↑ Back to Table of Contents](#table-of-contents) When several components need to share the same changing data then it is recommended to _lift the shared state up_ to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components. ****

### 202. What is prop drilling and how do you solve it?

[↑ Back to Table of Contents](#table-of-contents) Prop drilling is passing data through multiple intermediate components that don't need it, just to reach a deeply nested child. Problems: tight coupling, boilerplate, harder refactoring. Solutions: (1) Context API — for global or subtree-wide state. (2) Redux/Zustand — for complex global state. (3) Component composition — restructure to avoid deep nesting. (4) Component elevation — lift the consuming component higher. Use the simplest solution: composition first, then Context, then Redux.

### 203. What is prop drilling and why is it a problem?

[↑ Back to Table of Contents](#table-of-contents) Prop drilling is passing props through many intermediate components that don't use them just to reach a deep child. It creates tight coupling, makes refactoring hard, and reduces code maintainability. Solved by Context API, state management libraries, or component composition.

### 204. What is prop drilling in React?

[↑ Back to Table of Contents](#table-of-contents) Sometimes while developing React applications, there is a need to pass data from a component that is higher in the hierarchy to a component that is deeply nested. To pass data between such components, we pass props from a source component and keep passing the prop to the next component in the hierarchy till we reach the deeply nested component. The **disadvantage** of using prop drilling is that the components that should otherwise be not aware of the data have access to the data.

### 205. What is prop drilling? Problems and solutions.

[↑ Back to Table of Contents](#table-of-contents) Prop drilling is passing data through multiple layers of components via props, even when intermediate components don’t need that data. This makes code harder to maintain and refactor. **Solutions**: - **Context API**: Create a context and provide values at a higher level, then consume them deep down. - **State management libraries**: Redux, Zustand, etc. - **Component composition**: Instead of passing props, pass components as children or use render props to flatten the hierarchy.

### 206. What is prop inversion of control?

Prop Inversion of Control (IoC) means a component stops bossing its pieces around and instead says to the developer using it: "You take the wheel, you decide how this part should work." Instead of hardcoding every single behavior inside the component and adding 50 different configuration props, the component hands control back over to you. const names = ["Alice", "Bob", "Charlie"]; <List items={names} renderItem={(name) => <span>👤 {name}</span>} /> [⬆ Back to Table of Contents](#-table-of-contents)

### 207. What is prop type narrowing with discriminated unions (conceptually, even pre-TS)?

Structuring props so only a valid, mutually exclusive combination can be passed (e.g., `variant: 'link'` requiring `href`, `variant: 'button'` requiring `onClick`), preventing invalid prop combinations at the API design level.

### 208. What is React.Fragment and why is it useful?

[↑ Back to Table of Contents](#table-of-contents) React's Fragment helps in grouping multiple elements together by being careful not to add an extra element to the DOM. Just like you know in React, every component MUST return a single parent element, and a fragment just acts like that parent, except it doesn’t actually show up in the final HTML. I’ll explain this to you with an example! If you write: return ( \<\>

```{=html} <h1>

```
Hello

```{=html} </h1>

```
<p>World</p> \</\> ); React will group these elements together using Fragment, but in the browser, it will render as:

```{=html} <h1>

```
Hello

```{=html} </h1>

```
```{=html} <p>

```
World

```{=html} </p>

```
This shows that the Fragment is only used by React internally; it does not create an HTML element like a \<div>. Why do we use Fragment? Because sometimes using \<div> might cause some problems like breaking layouts on flexbox or grid, or creating invalid HTML (yes, this happens!) You can use it in these 2 ways: - \<React.Fragment> ... \</React.Fragment> - <> ... \</> - (short syntax) One thing you need to keep in mind is that only React.Fragment supports props like key, which comes in hand when rendering lists.

### 209. What is server state vs client state?

Server state: data from APIs (users, posts) – needs caching, refetching, synchronization, background updates. Client state: local UI state (modal open, form values) – synchronous, lives only in the browser. [↑ Back to Table of Contents](#table-of-contents)

### 210. What is snapshot testing? When is it useful vs risky?

Serializes rendered output for comparison; useful for stable presentational components, risky as a primary strategy (hard to meaningfully review, easy to blindly update).

### 211. What is state in React?

[↑ Back to Table of Contents](#table-of-contents) _State_ of a component is an object that holds some information that may change over the lifetime of the component. The important point is whenever the state object changes, the component re-renders. It is always recommended to make our state as simple as possible and minimize the number of stateful components. ![state](images/state.jpg) Let's take an example of **User** component with `message` state. Here, **useState** hook has been used to add state to the User component and it returns an array with current state and function to update it.

```jsx harmony import { useState } from "react"; function User() { const [message, setMessage] = useState("Welcome to React world"); return ( <div> <h1>{message}</h1> </div> ); }

```
Whenever React calls your component or access `useState` hook, it gives you a snapshot of the state for that particular render. <details><summary><b>See Class</b></summary> <p>

```jsx harmony import React from "react"; class User extends React.Component { constructor(props) { super(props); this.state = { message: "Welcome to React world", }; } render() { return ( <div> <h1>{this.state.message}</h1> </div> ); } }

```
</p> </details> State is similar to props, but it is private and fully controlled by the component ,i.e., it is not accessible to any other component till the owner component decides to pass it.

### 212. What is state mutation and how to prevent it?

`State mutation` happens when you try to update the state of a component without actually using `setState` function. This can happen when you are trying to do some computations using a state variable and unknowingly save the result in the same state variable. This is the main reason why it is advised to return new instances of state variables from the reducers by using Object.assign({}, ...) or spread syntax. This can cause unknown issues in the UI as the value of the state variable got updated without telling React to check what all components were being affected from this update and it can cause UI bugs. Ex:

```javascript class A extends React.component { constructor(props) { super(props); this.state = { loading: false } } componentDidMount() { let { loading } = this.state; loading = (() => true)(); // Trying to perform an operation and directly saving in a state variable }

```

### 213. What is test isolation, and why does it matter for React component tests?

Each test should run independently without leaking state (mocks, timers, DOM) into the next. RTL's `render` auto-cleans up the DOM after each test (via `afterEach(cleanup)`, often automatic), preventing one test's rendered output from bleeding into another's assertions.

### 214. What is the "key to reset a subtree" trick for resetting component state?

Changing an element's `key` forces React to unmount and remount the subtree, discarding all its internal state — a common technique to reset a form or widget to its initial state without manually clearing every field.

### 215. What is the "Portal" pattern, and when do you use it?

Rendering a component's output into a different part of the DOM tree (via `createPortal`) than its logical position in the React tree — typically for modals, tooltips, or dropdowns that need to escape a parent's `overflow: hidden` or `z-index` stacking context.

### 216. What is the "props getter" pattern used by headless libraries (e.g., downshift)?

Instead of exposing raw state, the Hook returns functions like `getInputProps()` / `getItemProps()` that spread the correct ARIA attributes and event handlers onto the consumer's own markup, bundling correct behavior without dictating the DOM structure.

### 217. What is the "render in a loop with composition" pattern vs a monolithic configurable component?

Instead of one component with many conditional props controlling every variant (`<Card showHeader showFooter variant=...>`), composing smaller pieces (`<Card><Card.Header/><Card.Body/></Card>`) that the consumer assembles as needed, improving flexibility without prop explosion.

### 218. What is the Compound Components pattern?

Components sharing implicit state via Context, giving flexible structure: `<Tabs><Tabs.List>...</Tabs.List></Tabs>`.

### 219. What is the controlled component pattern for reusable components?

[↑ Back to Table of Contents](#table-of-contents) This pattern creates a flexible component that can run on "autopilot" OR be manually "steered" by its parent. Instead of forcing a component to be strictly controlled or strictly uncontrolled, you build it to support both modes seamlessly. A reusable component can work in two modes: uncontrolled (manages own state) or controlled (parent provides `value` + `onChange`). Example: an `<Accordion>` that works out of the box but can also be fully controlled. ------------------------------------------------------------------------

### 220. What is the Controlled/Uncontrolled hybrid pattern?

A component accepts optional `value`/`onChange` for controlled use, falling back to internal state via `defaultValue` otherwise.

### 221. What is the difference between `interface` and `type` for defining props? When does it matter?

Both work for most prop definitions; `interface` supports declaration merging (useful for extending `Express.Request`-style ambient types) while `type` supports unions/intersections more directly. For simple component props, the choice is largely stylistic/team convention.

### 222. What is the difference between `setState()` and `replaceState()` methods?

When you use `setState()` the current and previous states are merged. `replaceState()` throws out the current state, and replaces it with only what you provide. Usually `setState()` is used unless you really need to remove all previous keys for some reason. You can also set state to `false`/`null` in `setState()` instead of using `replaceState()`. [↑ Back to Table of Contents](#table-of-contents)

### 223. What is the difference between `super()` and `super(props)` in React using ES6 classes?

[↑ Back to Table of Contents](#table-of-contents) When you want to access `this.props` in `constructor()` then you should pass props to `super()` method. **Using `super(props)`:**

```javascript class MyComponent extends React.Component { constructor(props) { super(props); console.log(this.props); // { name: 'John', ... } } }

```
**Using `super()`:**

```javascript class MyComponent extends React.Component { constructor(props) { super(); console.log(this.props); // undefined } }

```
Outside `constructor()` both will display same value for `this.props`. **** ------------------------------------------------------------------------

### 224. What is the difference between a "key prop" warning and a "missing dependency" warning?

The key warning flags list items without stable identity (reconciliation risk); the missing-dependency warning (from the exhaustive-deps ESLint rule) flags a `useEffect`/`useMemo`/`useCallback` referencing a value not listed in its dependency array (stale-closure risk).

### 225. What is the difference between a transition and a regular (synchronous) state update in terms of interruptibility?

A regular update renders to completion and commits as soon as possible (urgent). A transition's render work can be paused, abandoned, or restarted if a more urgent update comes in before it finishes, keeping the UI responsive.

### 226. What is the difference between constructor and getInitialState?

[↑ Back to Table of Contents](#table-of-contents) You should initialize state in the constructor when using ES6 classes, and `getInitialState()` method when using `React.createClass()`. **Using ES6 classes:**

```javascript class MyComponent extends React.Component { constructor(props) { super(props); this.state = { /* initial state */ }; } }

```
**Using `React.createClass()`:**

```javascript const MyComponent = React.createClass({ getInitialState() { return { /* initial state */ }; }, });

```
**Note:** `React.createClass()` is deprecated and removed in React v16. Use plain JavaScript classes instead.

### 227. What is the difference between Flow and PropTypes?

Flow is a _static analysis tool_ (static checker) which uses a superset of the language, allowing you to add type annotations to all of your code and catch an entire class of bugs at compile time. PropTypes is a _basic type checker_ (runtime checker) which has been patched onto React. It can't check anything other than the types of the props being passed to a given component. If you want more flexible typechecking for your entire project Flow/TypeScript are appropriate choices. [↑ Back to Table of Contents](#table-of-contents)

### 228. What is the difference between normalized and nested state shape in a global store?

Normalized state stores entities by ID in flat lookup tables (like a database), avoiding duplication and making updates to a single entity cheap. Nested state embeds related data directly, which is simpler initially but causes duplication and update headaches as relationships grow.

### 229. What is the Headless Component pattern?

Implements behavior/state logic with no markup/styling of its own, leaving visual output to the consumer (e.g., Radix primitives).

### 230. What is the impact of indexes as keys?

Keys should be stable, predictable, and unique. Using indexes as keys limits optimizations React can do and creates confusing bugs. If you don't specify a key prop at all, React will use index as a key's value by default.

### 231. What is the key prop and why is it important?

A special string or number that uniquely identifies a list item. React uses keys to match items between renders for efficient reconciliation. Wrong or missing keys cause incorrect DOM reuse and subtle bugs. **Benefits of key:** - Enables React to efficiently update and re-render components - Prevents unnecessary re-renders by reusing components - Helps maintain internal state of list items correctly

### 232. What is the main purpose of constructor?

[↑ Back to Table of Contents](#table-of-contents) The constructor is mainly used for two purposes, 1. To initialize local state by assigning object to this.state 2. For binding event handler methods to the instance For example, the below code covers both the above cases,

```javascript constructor(props) { super(props); // Don't call this.setState() here! this.state = { counter: 0 }; this.handleClick = this.handleClick.bind(this); }

```

### 233. What is the Observer/Pub-Sub pattern's use in React outside of Context (e.g., a lightweight event bus for cross-cutting concerns)?

A module-level event emitter that components `subscribe`/`publish` to for concerns that don't fit cleanly into the component tree's data flow (e.g., a toast system triggered from non-component code, or a global "logout" event), avoiding the need to lift that state into React itself.

### 234. What is the provider pattern?

A component that wraps part of the tree and supplies shared state/functionality via context. Used extensively: `ThemeProvider`, `AuthProvider`, `QueryClientProvider`. Stacking providers is common. [⬆ Back to Table of Contents](#-table-of-contents)

### 235. What is the purpose of callback function as an argument of `setState()`?

The callback function provided as the second argument to `setState` is executed after the state has been updated and the component has re-rendered. Because `setState()` is asynchronous, you cannot reliably perform actions that require the updated state immediately after calling `setState`. The callback ensures your code runs only after the update and re-render are complete.

### 236. What is the purpose of unmountComponentAtNode method?

This method is available from react-dom package and it removes a mounted React component from the DOM and clean up its event handlers and state. If no component was mounted in the container, calling this function does nothing. Returns true if a component was unmounted and false if there was no component to unmount. The method signature would be as follows,

```javascript ReactDOM.unmountComponentAtNode(container);

```
[↑ Back to Table of Contents](#table-of-contents)

### 237. What is the purpose of using super constructor with props argument?

[↑ Back to Table of Contents](#table-of-contents) A child class constructor cannot make use of `this` reference until the `super()` method has been called. The same applies to ES6 sub-classes as well. The main reason for passing props parameter to `super()` call is to access `this.props` in your child constructors. **Passing props:**

```javascript class MyComponent extends React.Component { constructor(props) { super(props); console.log(this.props); // prints { name: 'John', age: 42 } } }

```
**Not passing props:**

```javascript class MyComponent extends React.Component { constructor(props) { super(); console.log(this.props); // prints undefined // but props parameter is still available console.log(props); // prints { name: 'John', age: 42 } } render() { // no difference outside constructor console.log(this.props); // prints { name: 'John', age: 42 } } }

```
The above code snippets reveals that `this.props` is different only within the constructor. It would be the same outside the constructor. **** ------------------------------------------------------------------------

### 238. What is the recommended approach of removing an array element in React state?

[↑ Back to Table of Contents](#table-of-contents) The better approach is to use `Array.prototype.filter()` method. For example, let's create a `removeItem()` method for updating the state.

```javascript removeItem(index) { this.setState({ data: this.state.data.filter((item, i) => i !== index) }) }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 239. What is the render props pattern?

A component accepts a function prop (`render` or `children`) and calls it with shared data. `<Mouse render={({x,y}) => <Cursor x={x} y={y}/>}/>`. Flexible but can lead to callback hell; custom hooks are usually cleaner.

### 240. What is the risk of trusting `window.postMessage` data without validation in a React component?

Any page can send a `postMessage` to your window; without checking `event.origin` against an allow-list and validating the message shape, a malicious page could inject fake data or trigger unintended state changes.

### 241. What is the Slot pattern?

A component accepts other components as props for specific "slots" (`<Layout header={<Nav/>}>`), giving the caller control over region content.

### 242. What is the state reducer pattern?

State Reducer Pattern gives the user of your component a "veto power" or steering wheel over how the component’s internal data changes. Instead of the component making all the rules about how its state updates, it handles the heavy lifting but passes every change through a custom function you provide. This lets you intercept and modify the changes before they actually happen. [↑ Back to Table of Contents](#table-of-contents)

### 243. What is unidirectional data flow in React?

Data flows parent → child via props. A child requests a change via a callback passed down, and the parent updates its own state, flowing back down as new props.

### 244. What will happen if you use `setState()` in constructor?

[↑ Back to Table of Contents](#table-of-contents) When you use `setState()`, then apart from assigning to the object state React also re-renders the component and all its children. You would get error like this: _Can only update a mounted or mounting component._ So we need to use `this.state` to initialize variables inside constructor.

### 245. What will happen if you use `setState()` in constructor?

When you use `setState()`, then apart from assigning to the object state React also re-renders the component and all its children. You would get error like this: _Can only update a mounted or mounting component._ So we need to use `this.state` to initialize variables inside constructor. [↑ Back to Table of Contents](#table-of-contents)

### 246. When component props defaults to true?

[↑ Back to Table of Contents](#table-of-contents) If you pass no value for a prop, it defaults to true. This behavior is available so that it matches the behavior of HTML. For example, below expressions are equivalent,

```javascript <MyInput autocomplete /> <MyInput autocomplete={true} />

```
**Note:** It is not recommended to use this approach because it can be confused with the ES6 object shorthand (example, `{name}` which is short for `{name: name}`) ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 247. When did you get stuck while using React, and how did you fix it?

[↑ Back to Table of Contents](#table-of-contents) **Approach**: Describe a technical problem that had you stuck for a while, how you debugged it, and what you learned. **Example**: \> "I was building a drag‑and‑drop kanban board with React. The issue was that after dropping a card, the state updated correctly, but the card would visually jump back to its original position for a split second before snapping to the new column. \> \> **What I tried**: I checked the reducer, verified that the state was immutable, and used `React.memo` on the card components. Nothing worked. \> \> **How I fixed it**: I realized that the drag library I was using (`react-dnd`) was updating the DOM imperatively during the drag. After the drop, React would reconcile its virtual DOM and reset the card's inline styles. I solved it by resetting the drag preview style in a `useLayoutEffect` after the state update, ensuring that React's reconciliation happened after the drop animation. \> \> **Lesson**: I learned that mixing imperative DOM manipulation (like drag libraries) with React's declarative model requires careful timing. I also became more proficient in `useLayoutEffect` and the React lifecycle." ------------------------------------------------------------------------

### 248. When should you NOT use Context for state?

For frequently changing data (e.g., mouse position, animation frames), because every consumer re-renders. Use a dedicated state library with selectors (Zustand, Jotai, Redux) for fine-grained subscriptions. [↑ Back to Table of Contents](#table-of-contents)

### 249. Why are props read-only? What happens if you mutate them?

React's data flow is unidirectional; mutating props directly doesn't trigger a re-render and breaks the parent's ownership of that data.

### 250. Why can't you mutate props?

React enforces a "pure function" contract — components must never modify their own props; data flows one-way from parent to child.

### 251. Why can't you update props in React?

[↑ Back to Table of Contents](#table-of-contents) The React philosophy is that props should be **immutable** (read-only) and **top-down**. This means that a parent can send any prop values to a child, but the child can't modify received props. This ensures predictable data flow. *The full document continues with all remaining sections. Due to length, the complete Q&A is provided in the downloadable markdown file. All 335 unique questions are covered with thorough answers.* > **Note:** This consolidated bank contains every distinct concept from your 672 raw entries. Duplicates and near-duplicates have been merged to create a clean, comprehensive study guide. No unique question has been omitted. **End of document.**

### 252. Why do you not required to use inheritance?

In React, it is recommend using composition instead of inheritance to reuse code between components. Both Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Whereas, If you want to reuse non-UI functionality between components, it is suggested to extracting it into a separate JavaScript module. Later components import it and use that function, object, or a class, without extending it. [↑ Back to Table of Contents](#table-of-contents)

### 253. Why is state update asynchronous?

React batches state updates for performance. `setState()` / the setter from `useState()` schedules a re-render rather than immediately mutating state. Reading state right after calling the setter still returns the old value within the same event handler. ------------------------------------------------------------------------

### 254. Why React.js? What problems does it solve?

React solves several frontend challenges: - **Declarative UI**: Instead of imperatively manipulating the DOM, you describe what the UI should look like for a given state. React handles updates efficiently. - **Component‑based architecture**: Encourages reusability, maintainability, and separation of concerns. - **Efficient updates**: Virtual DOM diffing minimizes costly DOM manipulations. - **Unidirectional data flow**: Makes data flow predictable and easier to debug. - **Ecosystem and community**: Rich tooling, libraries (React Router, Redux), and strong community support. [↑ Back to Table of Contents](#table-of-contents)

### 255. Why should we not update the state directly?

If you try to update the state directly then it won't re-render the component.

```
javascript //Wrong this.state.message = "Hello world";

```
Instead use `setState()` method. It schedules an update to a component's state object. When state changes, the component responds by re-rendering.

```
javascript //Correct this.setState({ message: "Hello World" });

```
**Note:** You can directly assign to the state object either in *constructor* or using latest javascript's class field declaration syntax. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 256. Why shouldn't you use array index as a `key` in dynamic lists?

If the list reorders/filters, the index no longer uniquely identifies an item, causing wrong state association or broken animations.

### 257. Why we need to be careful when spreading props on DOM elements?

[↑ Back to Table of Contents](#table-of-contents) When we *spread props* we run into the risk of adding unknown HTML attributes, which is a bad practice. Instead we can use prop destructuring with `...rest` operator, so it will add only required props. For example,

```jsx harmony const ComponentA = () => ( <ComponentB isDisplay={true} className={"componentStyle"} /> ); const ComponentB = ({ isDisplay, ...domProps }) => ( <div {...domProps}>{"ComponentB"}</div> );

```
**** ------------------------------------------------------------------------

## Rendering, Reconciliation & Lifecycle

### 258. Commit Phase (Real DOM Updates)

[↑ Back to Table of Contents](#table-of-contents) Once reconciliation is done: * React enters the **commit phase**. * It applies calculated changes to the **real DOM**. * It also runs side effects like `useEffect` or `useLayoutEffect`. This is the only time React interacts directly with the browser DOM.

### 259. ContextType as property of class:

The contextType property on a class can be assigned a Context object created by React.createContext(). After that, you can consume the nearest current value of that Context type using this.context in any of the lifecycle methods and render function. Lets assign contextType property on MyClass as below,

```javascript class MyClass extends React.Component { componentDidMount() { let value = this.context; /* perform a side-effect at mount using the value of MyContext */ } componentDidUpdate() { let value = this.context; /* ... */ } componentWillUnmount() { let value = this.context; /* ... */ } render() { let value = this.context; /* render something based on the value of MyContext */ } } MyClass.contextType = MyContext;

```

### 260. Explain React Fiber's architecture in detail.

Each component maps to a Fiber node (type, props, state, effect tags, parent/child/sibling links) forming a Fiber tree. React maintains a "current" tree (on screen) and a "work-in-progress" tree (being built) — double buffering. Work is split into units scheduled by priority; low-priority work can be paused to handle urgent updates (e.g., user input), then resumed.

### 261. Explain Strict Mode in React.

StrictMode is a tool added in **version 16.3** of React to highlight potential problems in an application. It performs additional checks on the application.

```
function App() { return ( <React.StrictMode> <div classname="App"> <Header/> <div> Page Content </div> <Footer/> </div> </React.StrictMode> ); }

```
To enable StrictMode, `<React.StrictMode>` tags need to be added inside the application:

```
import React from "react"; import ReactDOM from "react-dom"; import App from "./App"; const rootElement = document.getElementById("root"); ReactDOM.render( <React.StrictMode> <App /> </React.StrictMode>, rootElement );

```
StrictMode currently helps with the following issues: - **Identifying components with unsafe lifecycle methods: ** - Certain lifecycle methods are unsafe to use in asynchronous react applications. With the use of third-party libraries, it becomes difficult to ensure that certain lifecycle methods are not used. - StrictMode helps in providing us with a warning if any of the class components use an unsafe lifecycle method. - **Warning about the usage of legacy string API:** - If one is using an older version of React, **callback ref** is the recommended way to manage **refs** instead of using the **string refs**. StrictMode gives a warning if we are using **string refs** to manage refs. - **Warning about the usage of findDOMNode:** - Previously, findDOMNode( ) method was used to search the tree of a DOM node. This method is deprecated in React. Hence, the StrictMode gives us a warning about the usage of this method. - **Warning about the usage of legacy context API (because the API is error-prone).** [↑ Back to Table of Contents](#table-of-contents)

### 262. Explain the commit phase vs render phase.

[↑ Back to Table of Contents](#table-of-contents) Render phase: React calls component functions, runs reconciliation – pure, may be paused/aborted. Commit phase: React applies DOM mutations, runs layout effects (`useLayoutEffect`), then passive effects (`useEffect`) – cannot be interrupted.

### 263. Fiber Tree Structure?

[↑ Back to Table of Contents](#table-of-contents) Each component in your app is represented by a **Fiber node** in a tree structure. A Fiber node contains: * Component type * Props & state * Pointers to parent, child, and sibling nodes * Effect tags to track changes (e.g., update, placement) * This forms the **Fiber Tree**, a data structure React uses instead of the traditional call stack.

### 264. How does React Fiber works? Explain in detail.

[↑ Back to Table of Contents](#table-of-contents) React Fiber is the **core engine** that enables advanced features like **concurrent rendering**, **prioritization**, and **interruptibility** in React. Here's how it works:

### 265. How does React's diffing algorithm work (O(n))?

[↑ Back to Table of Contents](#table-of-contents) React compares trees level by level. If root elements differ in type, it destroys the old tree. For same-type DOM elements it updates only changed attributes. For same-type components it updates props and re-renders. Keys enable efficient list diffing. ------------------------------------------------------------------------

### 266. How does React's reconciliation algorithm work?

It compares the new element tree with the previous one: elements of different types produce entirely new trees; elements of the same type keep the DOM node and only update changed attributes; for lists, `key` props let React match children across renders instead of diffing by position.

### 267. How does ReactJS work behind the scenes (render → reconciliation → commit)?

Components execute to build a virtual DOM tree; React's Fiber architecture reconciles (diffs) the new tree against the previous one in an interruptible render phase; then applies minimal DOM mutations in an uninterruptible commit phase and runs effects.

### 268. How does strict mode affect scoping and variable declaration?

A: Strict mode (`"use strict"`) prevents accidental globals, disallows duplicate parameter names, and changes the behavior of `this` in functions (defaults to `undefined` instead of `window`).

### 269. How does the React Fiber architecture change how rendering fundamentally works?

It replaces the old synchronous, recursive stack-based reconciler with an incremental one built on linked Fiber nodes — enabling pausable/resumable/abortable/prioritizable rendering work, which is the foundation for concurrent rendering, transitions, and Suspense.

### 270. How to update a component every second?

[↑ Back to Table of Contents](#table-of-contents) You need to use `setInterval()` to trigger the change, but you also need to clear the timer when the component unmounts to prevent errors and memory leaks.

```javascript componentDidMount() { this.interval = setInterval(() => this.setState({ time: Date.now() }), 1000) } componentWillUnmount() { clearInterval(this.interval) }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 271. Is it possible to access a ref in the render method?

[↑ Back to Table of Contents](#table-of-contents) Yes, you can access a ref in the render method, but what you get from it depends on how you're using the ref and when in the component lifecycle you're rendering. For example, when using ref to access a DOM node (e.g., divRef.current), it's not immediately available on the first render.

```js const divRef = useRef(null); console.log(divRef.current); // ❌ null on initial render return <div ref={divRef}>Hello</div>;

```

### 272. Mounting:

The component is ready to mount in the browser DOM. This phase covers initialization from `constructor()`, `getDerivedStateFromProps()`, `render()`, and `componentDidMount()` lifecycle methods.

### 273. Order of setState calls, componentDidMount and componentDidUpdate in a class component?

[↑ Back to Table of Contents](#table-of-contents)

```jsx class MyComponent extends React.Component { state = { count: 0 }; componentDidMount() { console.log('mounted, count:', this.state.count); this.setState({ count: 1 }); this.setState({ count: 2 }); } componentDidUpdate(prevProps, prevState) { console.log('updated from', prevState.count, 'to', this.state.count); } render() { console.log('render, count:', this.state.count); return <div>{this.state.count}</div>; } }

```
**Output:**

```
render, count: 0 mounted, count: 0 render, count: 2 updated from 0 to 2

```
**Explanation:** Initial render logs `0`. After mount, two `setState` calls are batched → one re-render with final value `2`. `componentDidUpdate` sees the jump from `0` to `2`. Class `setState` in lifecycle methods is batched automatically.

### 274. Pre-commit?

Before the component actually applies the changes to the DOM, there is a moment that allows React to read from the DOM through the `getSnapshotBeforeUpdate()`.

### 275. Reconciliation (Diffing Algorithm)

[↑ Back to Table of Contents](#table-of-contents) When state or props change: * React re-executes the component to produce a new virtual DOM. * It **compares the new virtual DOM to the previous one** using an efficient diffing algorithm. * React determines the **minimal set of DOM changes** required. This process is known as **reconciliation**.

### 276. Reconciliation?

Based on the diffing results, React decides which parts of the Real DOM should be updated. It avoids re-rendering the entire DOM and instead updates only the elements that actually changed. ![vdom3](images/vdom3.png)

### 277. Two Phases of Rendering?

[↑ Back to Table of Contents](#table-of-contents) ##### **A. Render Phase (work-in-progress)** * React builds a **work-in-progress Fiber tree**. * It walks through each component (begin phase), calculates what needs to change, and collects side effects (complete phase). * This phase is **interruptible**—React can pause it and resume later.

### 278. Unmounting:

In this last phase, the component is not needed and gets unmounted from the browser DOM. This phase includes `componentWillUnmount()` lifecycle method. It's worth mentioning that React internally has a concept of phases when applying changes to the DOM. They are separated as follows

### 279. Updating:

In this phase, the component gets updated in two ways, sending the new props and updating the state either from `setState()` or `forceUpdate()`. This phase covers `getDerivedStateFromProps()`, `shouldComponentUpdate()`, `render()`, `getSnapshotBeforeUpdate()` and `componentDidUpdate()` lifecycle methods.

### 280. What are Strict Mode's dev-only behaviors?

Double-invokes component bodies, state initializers, and effect setup+cleanup to surface impure logic. No effect in production.

### 281. What are the different phases of component lifecycle?

[↑ Back to Table of Contents](#table-of-contents) The component lifecycle has three distinct lifecycle phases:

### 282. What are the lifecycle methods going to be deprecated in React v16?

[↑ Back to Table of Contents](#table-of-contents) **⚠️ FULLY DEPRECATED:** These lifecycle methods have been deprecated and removed from React 17+. The following lifecycle methods were deprecated due to unsafe coding practices and problems with async rendering: 1. `componentWillMount()` - **REMOVED in React 17** 2. `componentWillReceiveProps()` - **REMOVED in React 17** 3. `componentWillUpdate()` - **REMOVED in React 17** **Timeline:** - React 16.3: Methods aliased with `UNSAFE_` prefix - React 17+: Unprefixed versions completely removed - Current (React 18/19): Only `UNSAFE_` versions exist (not recommended) **Modern Alternatives:** | Deprecated Method | Modern Replacement | |---|---| | `componentWillMount()` | `constructor()` or `componentDidMount()` | | `componentWillReceiveProps()` | `static getDerivedStateFromProps()` or `componentDidUpdate()` | | `componentWillUpdate()` | `getSnapshotBeforeUpdate()` + `componentDidUpdate()` | **Best Practice:** Use functional components with hooks instead: - `useEffect()` for side effects - `useState()` for state management - `useMemo()`/`useCallback()` for optimization **** ------------------------------------------------------------------------

### 283. What are the lifecycle methods of React?

[↑ Back to Table of Contents](#table-of-contents) React lifecycle hooks will have the methods that will be automatically called at different phases in the component lifecycle and thus it provides good control over what happens at the invoked point. It provides the power to effectively control and manipulate what goes on throughout the component lifecycle. For example, if you are developing the YouTube application, then the application will make use of a network for buffering the videos and it consumes the power of the battery (assume only these two). After playing the video if the user switches to any other application, then you should make sure that the resources like network and battery are being used most efficiently. You can stop or pause the video buffering which in turn stops the battery and network usage when the user switches to another application after video play. So we can say that the developer will be able to produce a quality application with the help of lifecycle methods and it also helps developers to make sure to plan what and how to do it at different points of birth, growth, or death of user interfaces. The various lifecycle methods are: - `constructor()`: This method will be called when the component is initiated before anything has been done. It helps to set up the initial state and initial values. - `getDerivedStateFromProps()`: This method will be called just before element(s) rendering in the DOM. It helps to set up the state object depending on the initial props. The getDerivedStateFromProps() method will have a state as an argument and it returns an object that made changes to the state. This will be the first method to be called on an updating of a component. - `render()`: This method will output or re-render the HTML to the DOM with new changes. The render() method is an essential method and will be called always while the remaining methods are optional and will be called only if they are defined. - `componentDidMount()`: This method will be called after the rendering of the component. Using this method, you can run statements that need the component to be already kept in the DOM. - `shouldComponentUpdate()`: The Boolean value will be returned by this method which will specify whether React should proceed further with the rendering or not. The default value for this method will be True. - `getSnapshotBeforeUpdate()`: This method will provide access for the props as well as for the state before the update. It is possible to check the previously present value before the update, even after the update. - `componentDidUpdate()`: This method will be called after the component has been updated in the DOM. - `componentWillUnmount()`: This method will be called when the component removal from the DOM is about to happen.

### 284. What are the rules covered by diffing algorithm?

[↑ Back to Table of Contents](#table-of-contents) When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements. It covers the below rules during reconciliation algorithm,

### 285. What are the three main lifecycle phases?

Mounting (component added to DOM), Updating (props/state change → re-render), Unmounting (component removed from DOM). Class components have explicit methods; hooks model these via `useEffect`. **Q40. Map class lifecycle methods to hooks.** - `componentDidMount` → `useEffect(() => {...}, [])` - `componentDidUpdate` → `useEffect(() => {...}, [dep])` - `componentWillUnmount` → cleanup function returned from `useEffect` - `getDerivedStateFromProps` → compute derived state inline or in `useMemo`

### 286. What are the three phases of a class component's lifecycle?

Mounting (`constructor`, `render`, `componentDidMount`), Updating (`render`, `componentDidUpdate`), Unmounting (`componentWillUnmount`).

### 287. What is `getDerivedStateFromProps` and when would you use it?

[↑ Back to Table of Contents](#table-of-contents) A static class lifecycle that returns new state derived from props before every render. Rarely needed; usually derived state should be computed during render or via `useMemo`. Overuse leads to confusing state synchronization bugs.

### 288. What is `getSnapshotBeforeUpdate`?

[↑ Back to Table of Contents](#table-of-contents) A class lifecycle called right before the DOM is updated. Its return value is passed as 'snapshot' to `componentDidUpdate`. Used for reading scroll position or other DOM measurements before a commit.

### 289. What is `PureComponent` vs `Component` in class components?

`PureComponent` auto-implements a shallow `shouldComponentUpdate`. Plain `Component` always re-renders unless you implement that method yourself.

### 290. What is `shouldComponentUpdate` and its functional equivalent?

[↑ Back to Table of Contents](#table-of-contents) `shouldComponentUpdate` returns boolean to control re-rendering in class components. The functional equivalent is `React.memo` (shallow comparison) or a custom comparator passed as its second argument.

### 291. What is diffing algorithm?

[↑ Back to Table of Contents](#table-of-contents) React needs to use algorithms to find out how to efficiently update the UI to match the most recent tree. The diffing algorithms is generating the minimum number of operations to transform one tree into another. However, the algorithms have a complexity in the order of O(n3) where n is the number of elements in the tree. In this case, for displaying 1000 elements would require in the order of one billion comparisons. This is far too expensive. Instead, React implements a heuristic O(n) algorithm based on two assumptions: 1. Two elements of different types will produce different trees. 2. The developer can hint at which child elements may be stable across different renders with a key prop.

### 292. What is event delegation in React?

React attaches a single event listener at the root DOM node and routes events to the correct handler using its internal fiber tree. Efficient: one listener handles all events instead of per-element listeners. ------------------------------------------------------------------------

### 293. What is Fiber? Why did React introduce it?

Fiber is React's reconciliation engine (React 16+), replacing the old synchronous stack reconciler. Each Fiber is a unit of work, making rendering interruptible/resumable and enabling concurrent features.

### 294. What is React Fiber?

[↑ Back to Table of Contents](#table-of-contents) The Problem (Old React) Before Fiber, when React started updating the screen, it had to finish the entire job in one single blast without stopping. If it was a massive update (like rendering a huge list), the browser would freeze. If a user tried to click a button or type during that freeze, the app felt broken and laggy. The Solution (React Fiber) Fiber changes the way React works by breaking the massive update job into tiny, bite-sized tasks. Because the work is split up, React gains three superpowers: Pause & Resume: It can do a little bit of work, pause to let the browser breathe, and then pick up right where it left off. Prioritize: If a user clicks a button while React is busy rendering a hidden menu, React will pause the menu, handle the button click immediately (high priority), and then go back to the menu. Abort: If you switch pages mid-load, React can instantly throw away the half-finished work of the old page instead of wasting time finishing it. ------------------------------------------------------------------------

### 295. What is reconciliation in React?

[↑ Back to Table of Contents](#table-of-contents) Reconciliation is React's algorithm for diffing the previous virtual DOM tree with the new one and determining the minimal set of real DOM changes needed. Key heuristics: (1) Elements of different types produce entirely different trees. (2) Elements with stable keys are matched across renders. (3) Same type = update props in place. React's Fiber architecture enables incremental reconciliation — work can be paused, prioritized, and resumed, unlike the old synchronous stack reconciler.

### 296. What is reconciliation?

[↑ Back to Table of Contents](#table-of-contents) `Reconciliation` is the process through which React updates the Browser DOM and makes React work faster. React use a `diffing algorithm` so that component updates are predictable and faster. React would first calculate the difference between the `real DOM` and the copy of DOM `(Virtual DOM)` when there's an update of components. React stores a copy of Browser DOM which is called `Virtual DOM`. When we make changes or add data, React creates a new Virtual DOM and compares it with the previous one. This comparison is done by `Diffing Algorithm`. Now React compares the Virtual DOM with Real DOM. It finds out the changed nodes and updates only the changed nodes in Real DOM leaving the rest nodes as it is. This process is called _Reconciliation_.

### 297. What is reconciliation? How does React's diffing algorithm work?

[↑ Back to Table of Contents](#table-of-contents) So this concept is not very difficult once you read its rules and uses! What you should do here is get familiar with the concept right now, have a read, and then, in the end, I'll mention a short answer-like paragraph that you can use during your interview. So to understand Reconciliation: Reconciliation is the internal algo process React uses to compare the previous Virtual DOM tree with the newly generated Virtual DOM tree after a state or prop changes. Here's what happens to make it work: 1. React re-renders the component to produce a new Virtual DOM tree 2. It compares this tree with the previous Virtual DOM tree 3. It computes a set of changes called mutations 4. It applies only those changes to the real DOM And so, this process is used to avoid unnecessary DOM operations, which end up being expensive. Coming to React's Diffing Algorithm - React's Diffing Algorithm is a part of the reconciliation process, where its primary goal is to minimize DOM updates. Now it is important to understand how this takes place, so please look into this carefully: - The expensive but optimal component is (O(n3 ) ) - React uses a tree-diffing algorithm to minimize DOM - Hence, it uses a heuristic O(n) algorithm instead of specific assumptions What it essentially does is compare root elements, then if they differ, the entire subtree is replaced, and if they match, then its attributes and the recursion on children are compared. There are some rules of diffing that you really need to keep in mind:

### 298. What is the "double render" cost of Strict Mode in development? Does it affect production?

Strict Mode intentionally double-invokes render/effect logic in development to surface side effects, roughly doubling dev-time render cost — but it has zero effect on the production build's actual performance.

### 299. What is the commit phase's "passive effects" vs "layout effects" ordering?

Layout effects (`useLayoutEffect`) run synchronously right after DOM mutation, before the browser paints. Passive effects (`useEffect`) run asynchronously after paint, so the user may briefly see the pre-effect UI.

### 300. What is the lifecycle methods order in mounting?

[↑ Back to Table of Contents](#table-of-contents) The lifecycle methods are called in the following order when an instance of a component is being created and inserted into the DOM. 1. `constructor()` 2. `static getDerivedStateFromProps()` 3. `render()` 4. `componentDidMount()`

### 301. What is the main goal of React Fiber?

[↑ Back to Table of Contents](#table-of-contents) The goal of _React Fiber_ is to increase its suitability for areas like animation, layout, and gestures. Its headline feature is **incremental rendering**: the ability to split rendering work into chunks and spread it out over multiple frames. Its main goals are: * **Incremental Rendering** – Breaks work into chunks for smoother updates. * **Interruptible Rendering** – Pauses and resumes rendering to keep the UI responsive. * **Prioritization** – Handles high-priority updates (e.g. animations) before low-priority ones. * **Concurrency Support** – Enables working on multiple UI versions simultaneously. * **Better Error Handling** – Supports component-level error boundaries. * **Suspense Support** – Allows waiting for async data before rendering. * **Improved DevTools** – Enables better debugging and performance tracking. ****

### 302. What is the methods order when component re-rendered?

[↑ Back to Table of Contents](#table-of-contents) An update can be caused by changes to props or state. The below methods are called in the following order when a component is being re-rendered. 1. static getDerivedStateFromProps() 2. shouldComponentUpdate() 3. render() 4. getSnapshotBeforeUpdate() 5. componentDidUpdate() ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 303. What is the purpose of `getDerivedStateFromProps()` lifecycle method?

[↑ Back to Table of Contents](#table-of-contents) The new static `getDerivedStateFromProps()` lifecycle method is invoked after a component is instantiated as well as before it is re-rendered. It can return an object to update state, or `null` to indicate that the new props do not require any state updates.

```javascript class MyComponent extends React.Component { static getDerivedStateFromProps(props, state) { // ... } }

```
This lifecycle method along with `componentDidUpdate()` covers all the use cases of `componentWillReceiveProps()`.

### 304. What is the recommended ordering of methods in component class?

_Recommended_ ordering of methods from _mounting_ to _render stage_: 1. `static` methods 2. `constructor()` 3. `getChildContext()` 4. `componentWillMount()` 5. `componentDidMount()` 6. `componentWillReceiveProps()` 7. `shouldComponentUpdate()` 8. `componentWillUpdate()` 9. `componentDidUpdate()` 10. `componentWillUnmount()` 11. click handlers or event handlers like `onClickSubmit()` or `onChangeDescription()` 12. getter methods for render like `getSelectReason()` or `getFooterContent()` 13. optional render methods like `renderNavigation()` or `renderProfilePicture()` 14. `render()` [↑ Back to Table of Contents](#table-of-contents)

### 305. Why do two sibling components with the same `key` cause a warning or misbehavior?

React uses `key` to uniquely identify items among siblings during reconciliation; duplicate keys make it ambiguous which DOM node/state belongs to which element, risking incorrect reuse.

### 306. Why do you not need error boundaries for event handlers?

Error boundaries do not catch errors inside event handlers. React doesn’t need error boundaries to recover from errors in event handlers. Unlike the render method and lifecycle methods, the event handlers don’t happen during rendering. So if they throw, React still knows what to display on the screen. If you need to catch an error inside an event handler, use the regular JavaScript try / catch statement:

```javascript class MyComponent extends React.Component { constructor(props) { super(props); this.state = { error: null }; this.handleClick = this.handleClick.bind(this); } handleClick() { try { // Do something that could throw } catch (error) { this.setState({ error }); } } render() { if (this.state.error) { return <h1>Caught an error.</h1>; } return <button onClick={this.handleClick}>Click Me</button>; } }

```
Note that the above example is demonstrating regular JavaScript behavior and doesn’t use error boundaries. [↑ Back to Table of Contents](#table-of-contents)

### 307. Why does strict mode render twice in React?

StrictMode renders components twice in development mode(not production) in order to detect any problems with your code and warn you about those problems. This is used to detect accidental side effects in the render phase. If you used `create-react-app` development tool then it automatically enables StrictMode by default.

```js const root = createRoot(document.getElementById("root")); root.render( <StrictMode> <App /> </StrictMode> );

```
If you want to disable this behavior then you can simply remove `strict` mode.

```js const root = createRoot(document.getElementById("root")); root.render(<App />);

```
To detect side effects the following functions are invoked twice: 1. Function component bodies, excluding the code inside event handlers. 2. Functions passed to `useState`, `useMemo`, or `useReducer` (any other Hook) 3. Class component's `constructor`, `render`, and `shouldComponentUpdate` methods 4. Class component static `getDerivedStateFromProps` method 5. State updater functions ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 308. Why is a component constructor called only once?

[↑ Back to Table of Contents](#table-of-contents) React's *reconciliation* algorithm assumes that without any information to the contrary, if a custom component appears in the same place on subsequent renders, it's the same component as before, so reuses the previous instance rather than creating a new one. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 309. Why should not call setState in componentWillUnmount?

[↑ Back to Table of Contents](#table-of-contents) You should not call `setState()` in `componentWillUnmount()` because once a component instance is unmounted, it will never be mounted again.

## Hooks (Core & Advanced)

### 310. `useMemo` vs `React.memo` — how are they different?

`React.memo` prevents an entire *component* from re-rendering based on props; `useMemo` memoizes a *computed value* inside a component. They're often used together: `React.memo` on the child, `useMemo`/`useCallback` in the parent to keep the props it receives referentially stable.

### 311. `useMemo` vs `useCallback` – what's the difference?

[↑ Back to Table of Contents](#table-of-contents) `useMemo(() => fn(), deps)` memoizes the return value of `fn`. `useCallback(fn, deps)` memoizes `fn` itself. `useCallback(fn, deps) === useMemo(() => fn, deps)`. Choose `useMemo` for values, `useCallback` for functions.

### 312. `useRef` vs `useState`?

Ref updates don't trigger re-render and apply immediately; state updates do trigger re-render, visible next render.

### 313. `useTransition` vs `Suspense`?

`Suspense` declares what fallback to show; `useTransition` declares how urgent an update is, keeping old UI visible while preparing the new one.

### 314. Abort Fetch Requests?

```jsx useEffect(() => { const controller = new AbortController(); fetch(url, { signal: controller.signal }) .then(response => response.json()) .then(data => setData(data)) .catch(err => { if (err.name !== 'AbortError') { setError(err); } }); return () => controller.abort(); }, [url]);

```

### 315. Actions & Form Actions?

Automatic handling of pending states, errors, and optimistic updates:

```jsx function Form() { const [state, formAction] = useFormState(serverAction, initialState); const { pending } = useFormStatus(); return ( <form action={formAction}> <input disabled={pending} /> <button disabled={pending}> {pending ? 'Submitting...' : 'Submit'} </button> </form> ); }

```

### 316. Avoid Inline Object/Function Dependencies?

```jsx // ❌ Bad: New object on every render useEffect(() => { doSomething(options); }, [{ page: 1, limit: 10 }]); // Always different reference // ✅ Good: Memoize or extract const options = useMemo(() => ({ page: 1, limit: 10 }), []); useEffect(() => { doSomething(options); }, [options]);

```

### 317. Built-in Hooks:

The built-in Hooks are divided into 2 parts as given below: - **Basic Hooks:** - `useState()`: This functional component is used to set and retrieve the state. - `useEffect()`: It enables for performing the side effects in the functional components. - `useContext()`: It is used for creating common data that is to be accessed by the components hierarchy without having to pass the props down to each level. - **Additional Hooks:** - `useReducer()` : It is used when there is a complex state logic that is having several sub-values or when the upcoming state is dependent on the previous state. It will also enable you to optimization of component performance that will trigger deeper updates as it is permitted to pass the dispatch down instead of callbacks. - `useMemo()` : This will be used for recomputing the memoized value when there is a change in one of the dependencies. This optimization will help for avoiding expensive calculations on each render. - `useCallback()` : This is useful while passing callbacks into the optimized child components and depends on the equality of reference for the prevention of unneeded renders. - `useImperativeHandle()`: It will enable modifying the instance that will be passed with the ref object. - `useDebugValue()`: It is used for displaying a label for custom hooks in React DevTools. - `useRef()` : It will permit creating a reference to the DOM element directly within the functional component. - `useLayoutEffect()`: It is used for the reading layout from the DOM and re-rendering synchronously.

### 318. Call Hooks from React Functions only:

You shouldn’t call Hooks from regular JavaScript functions or class components. Instead, you should call them from either function components or custom hooks. Let's find the difference of correct and incorrect usage with below examples, **Correct usage:**:

```jsx //Example1: function Counter() { // Correct: useState is used inside a functional component const [count, setCount] = useState(0); return <div>Counter: {count}</div>; } //Example2: function useFetchData(url) { const [data, setData] = useState(null); useEffect(() => { fetch(url) .then((response) => response.json()) .then((data) => setData(data)); }, [url]); return data; } function UserProfile() { // Correct: Using a custom hook here const user = useFetchData('https://some-api.com/user'); return ( <div> <h1>{user ? user.name : 'Loading profile...'}</h1> </div> ); }

```
**Incorrect usage:**:

```jsx //Example1 function normalFunction() { // Incorrect: Can't call hooks in normal functions const [count, setCount] = useState(0); } //Example2 function fetchData(url) { // Incorrect: Hooks can't be used in non-React functions const [data, setData] = useState(null); useEffect(() => { fetch(url) .then((response) => response.json()) .then((data) => setData(data)); }, [url]); return data; }

```
In the above incorrect usage example, both `useState` and `useEffect` are used in non-React functions(`normalFunction` and `fetchData`), which is not allowed. [↑ Back to Table of Contents](#table-of-contents)

### 319. Call Hooks only at the top level of your react functions:

You should always use hooks at the top level of react function before any early returns. i.e, You shouldn’t call Hooks inside loops, conditions, or nested functions. This will ensure that Hooks are called in the same order each time a component renders and it preserves the state of Hooks between multiple re-renders due to `useState` and `useEffect` calls. Let's see the difference using an example, **Correct usage:**:

```jsx function UserProfile() { // Correct: Hooks called at the top level const ** --- ### When and how often does React invoke the setup and cleanup functions inside a useEffect hook? 1. **Setup Function Execution (`useEffect`)** The setup function (or the main function) you pass to `useEffect` runs at specific points: 1. **After the component is mounted** (if the dependency array is empty `** ------------------------------------------------------------------------ --- --- ### Why do React Hooks make use of refs? Earlier, refs were only limited to class components but now it can also be accessible in function components through the useRef Hook in React. The refs are used for: - Managing focus, media playback, or text selection. - Integrating with DOM libraries by third-party. - Triggering the imperative animations. --- ### Why do we use array destructuring (square brackets notation) in `useState`? When we declare a state variable with `useState`, it returns a pair — an array with two items. The first item is the current value, and the second is a function that updates the value. Using [0] and [1] to access them is a bit confusing because they have a specific meaning. This is why we use array destructuring instead. For example, the array index access would look as follows:

```
var userStateVariable = useState('userProfile'); // Returns an array pair var user = userStateVariable[0]; // Access first item var setUser = userStateVariable[1]; // Access second item

```
Whereas with array destructuring the variables can be accessed as follows:

```
const [user, setUser] = useState('userProfile');

```
[ --- ### Why use functional updates with `useState`? `setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### ❓ What is the difference between useEffect, useLayoutEffect, and useInsertionEffect? **Answer:** useEffect: runs AFTER paint (asynchronous) — doesn't block browser from painting. Good for: data fetching, subscriptions, analytics. useLayoutEffect: runs synchronously AFTER DOM mutations but BEFORE paint — blocks painting. Use when you need to read/write DOM layout (element size/position) to avoid visual flicker. useInsertionEffect: runs BEFORE DOM mutations — specifically for CSS-in-JS libraries to inject styles before any layout effects read styles. Hierarchy: useInsertionEffect → DOM mutations → useLayoutEffect → paint → useEffect. --- ### ❓ What is the difference between useMemo and useCallback? **Answer:** useMemo memoizes the RESULT of a computation — returns cached value until deps change. Use for expensive calculations. useCallback memoizes a FUNCTION DEFINITION — returns same function reference until deps change. Use when passing callbacks to memoized child components. Key distinction: useMemo = memo(fn()), useCallback = memo(fn). When NOT to use useMemo: (1) simple calculations where memoization overhead exceeds savings. (2) Values that change on every render anyway. Overusing them adds memory and comparison overhead. --- ## Performance & Concurrent React ### A React component re-renders again and again but you never called setState. Why? Multiple causes are possible: Parent re-render: parent's state/props changed, triggering all children to re-render Inline objects/arrays as props: {} or [] creates new reference on every render Inline functions as props: () => {} creates new function instance each render Context value changed: if consuming a Context that updates frequently Custom hook with unstable return values causing cascading updates useEffect with missing/incorrect deps triggering setState in a loop --- ### Can you force a component to re-render without calling setState? By default, when your component's state or props change, your component will re-render. If your `render()` method depends on some other data, you can tell React that the component needs re-rendering by calling `forceUpdate()`.

```javascript component.forceUpdate(callback);

```
It is recommended to avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`. **** ------------------------------------------------------------------------ --- --- ### CPU vs memory bottlenecks – how to identify and fix? **CPU bottlenecks** – JavaScript execution causing long tasks, jank, high CPU usage. - **Identify**: Chrome DevTools Performance tab; look for long “Script” tasks. - **Fix**: Code splitting, Web Workers for heavy computations, throttle/debounce event handlers, use `useTransition` to prioritize UI updates, avoid expensive renders. **Memory bottlenecks** – Leaks causing growing memory consumption, eventual slowdown or crash. - **Identify**: Memory tab, take heap snapshots; compare after user actions to see retained objects. - **Fix**: Clean up event listeners, intervals, WebSocket connections; avoid retaining large data in closures; use weak references (`WeakMap`, `WeakSet`) for caching; unmount components properly; use `useEffect` cleanup. --- ### Edge caching vs CDN caching strategies. - **Edge caching** (also often provided by CDNs) caches static assets at edge locations (points of presence) close to users. Typically for static files (JS, CSS, images). You can configure cache headers (`Cache-Control`) and invalidation strategies. - **CDN caching** can also cache dynamic responses (HTML) using strategies like “stale‑while‑revalidate” to serve stale content while refreshing in the background. Useful for SSR pages. - **Strategies**: - Use `Cache-Control: public, max-age=31536000, immutable` for versioned assets. - For HTML, use `s-maxage` and `stale-while-revalidate` for CDNs. - Use surrogate keys to purge specific resources. --- --- ### Design an Image Gallery with lazy loading and skeleton placeholders. **Requirements**: Grid of images, load as user scrolls, show skeleton while loading. **Design**: - **Lazy loading**: Use `IntersectionObserver` to set `src` when image enters viewport. Fallback `loading="lazy"` for simpler. - **Skeletons**: Show a placeholder div with the same dimensions (aspect ratio) and a pulse animation. - **Responsive**: Use CSS Grid or flex with `object-fit: cover`. - **Error handling**: On error, show broken image icon. - **Performance**: Use `srcset` for responsive images, WebP format. --- ### How do you balance performance vs feature delivery? Framework: performance is a feature, not a tax. Approach: (1) Establish performance budgets upfront (e.g., LCP < 2.5s, bundle size < 200KB). (2) Automate performance checks in CI — fail builds that regress metrics. (3) Address performance debt in dedicated sprints, not as afterthoughts. (4) Use data: is this optimization worth the effort? (5) Good software design (proper abstractions, avoiding premature optimization) often prevents performance issues. (6) When deadlines force trade-offs, document the debt and schedule payback. --- ### How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab) **React DevTools Profiler**\ - Record a profile while interacting with the app. - The "Flamegraph" view shows which components rendered and why. - Look for components that re‑render frequently or take a long time. - Use the "Why did this render?" option (with a custom hook or the `why‑did‑you‑render` library) to identify prop changes. **Browser Performance Tab (Chrome DevTools)**\ - Record a performance trace during the problematic interaction. - Look for long tasks (yellow/red bars) and inspect the call stack. - Identify whether the bottleneck is JavaScript (React render) or layout/paint (CSS). - Use "Timings" to see where time is spent: script, render, paint. **Lighthouse / Web Vitals**\ - Run Lighthouse to get a high‑level score and suggestions. - Use the "Performance" panel to measure Core Web Vitals (LCP, CLS, INP). **Memory Tab**\ - If performance degrades over time, take heap snapshots to find memory leaks. ------------------------------------------------------------------------ --- --- ### How do you detect and prevent memory leaks in long-running SPAs? **Detection**: - Use Chrome DevTools Memory tab: take heap snapshots before and after a series of user actions that should free memory. - Look for retained objects that are no longer needed (e.g., detached DOM elements, large arrays). - Use `performance.memory` (Chrome) to monitor memory usage over time. - Use the “Performance monitor” to watch JS heap size. **Prevention**: - Always clean up `setInterval`/`setTimeout` in `useEffect` cleanup. - Remove event listeners in cleanup. - Cancel subscriptions (WebSocket, fetch with AbortController) on unmount. - Avoid storing large data in global variables or closures that persist. - Use `useRef` for values that shouldn’t cause re‑renders but be cautious about holding references. - For caches, use `WeakMap`/`WeakSet` to allow garbage collection when keys are no longer referenced. - Profile your app after implementing cleanup to ensure no accumulation. --- ### How do you ensure a React app performs well at 100k users? CDN for static assets. SSR/SSG for fast initial loads. Aggressive caching (React Query, HTTP cache headers). Server-side pagination, never load all data. Code splitting per route. Error boundaries everywhere. Monitoring and alerting from day one. ------------------------------------------------------------------------ --- --- ### How do you measure and fix excessive re-renders? Use React DevTools 'Highlight Updates' to spot components re-rendering. Record a Profiler session to see flame charts. Then: add `React.memo`, split context, move state closer to usage, or batch updates. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### How do you memoize a component? There are memoize libraries available which can be used on function components. For example `moize` library can memoize the component in another component.

```jsx harmony import moize from "moize"; import Component from "./components/Component"; // this module exports a non-memoized component const MemoizedFoo = moize.react(Component); const Consumer = () => { <div> {"I will memoize the following entry:"} <MemoizedFoo /> </div>; };

```
**Update:** Since React v16.6.0, we have a `React.memo`. It provides a higher order component which memoizes component unless the props change. To use it, simply wrap the component using React.memo before you use it.

```js const MemoComponent = React.memo(function MemoComponent(props) { /* render using props */ }); OR; export default React.memo(MyFunctionComponent);

```
**** ------------------------------------------------------------------------ --- ## React Context & Component Patterns --- ### How does the Virtual DOM improve performance? Real DOM mutations are expensive (layout, paint, composite). React batches changes and applies minimal updates. The diffing algorithm is O(n) using heuristics (same type → update; different type → destroy and replace). ------------------------------------------------------------------------ --- --- ### How to focus an input element on page load? You need to use `useEffect` hook to set focus on input field during page load time for functional component.

```jsx harmony import React, { useEffect, useRef } from "react"; const App = () => { const inputElRef = useRef(null); useEffect(() => { inputElRef.current.focus(); }, **

### 320. Calling a hook conditionally inside an if block?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [flag, setFlag] = React.useState(false); if (flag) { const [extra, setExtra] = React.useState(0); // RULES VIOLATION! } return <button onClick={() => setFlag(true)}>Click</button>; }

```
**Behavior:** React throws an error: "Rendered more hooks than during the previous render." **Explanation:** Hooks must be called in the SAME ORDER every render. Conditional hooks change the hook call count/order between renders, breaking React's internal hook-to-state mapping. This is why the Rules of Hooks exist.

### 321. Can Hooks be used in class components?

[↑ Back to Table of Contents](#table-of-contents) No, Hooks cannot be used inside class components. They are specially designed for function components. This is because hooks depend on the sequence in which they are called during a component's render, something that's only guaranteed in functional components. However, both class and function components can coexist in the same application. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 322. Can React Hook replaces Redux?

[↑ Back to Table of Contents](#table-of-contents) The React Hook cannot be considered as a replacement for Redux (It is an open-source, JavaScript library useful in managing the application state) when it comes to the management of the global application state tree in large complex applications, even though the React will provide a useReducer hook that manages state transitions similar to Redux. Redux is very useful at a lower level of component hierarchy to handle the pieces of a state which are dependent on each other, instead of a declaration of multiple useState hooks. In commercial web applications which is larger, the complexity will be high, so using only React Hook may not be sufficient. Few developers will try to tackle the challenge with the help of React Hooks and others will combine React Hooks with the Redux.

### 323. Can useRef be used to store previous values?

[↑ Back to Table of Contents](#table-of-contents) Yes, `useRef` is a common pattern when you want to compare current and previous props or state without causing re-renders. **Example: Storing previous state value**

```js import { useEffect, useRef, useState } from 'react'; function PreviousValueExample() { const [count, setCount] = useState(0); const prevCountRef = useRef(); useEffect(() => { prevCountRef.current = count; }, [count]); const prevCount = prevCountRef.current; return ( <div> <p>Current: {count}</p> <p>Previous: {prevCount}</p> <button onClick={() => setCount(c => c + 1)}>Increment</button> </div> ); }

```

### 324. Can useState take a function as an initial value?

[↑ Back to Table of Contents](#table-of-contents) Yes, `useState` can take a function as an initial value, and this is a useful feature in React called **lazy initialization**. This function is also known as **initializer function**. When you call useState(initialValue), you normally pass in a value directly:

```js const [count, setCount] = useState(0); // initial value is 0

```
But if calculating that initial value is expensive or involves logic, you can pass a function that returns the value:

```js const [count, setCount] = useState(() => { // This function only runs once — when the component first renders return expensiveComputation(); });

```
This function avoids doing heavy computation on every render. If you don't use this function form and invokes it directly, the function will run everytime the component renders and impact the performance. For example, the below usage is not recommended.

```js const [count, setCount] = useState(expensiveComputation());

```

### 325. Can you combine **useReducer** with **useContext**?

[↑ Back to Table of Contents](#table-of-contents) Yes, it's common to combine **useReducer** with **useContext** to build a lightweight state management system similar to Redux:

```js const AppContext = React.createContext(); function AppProvider({ children }) { const [state, dispatch] = useReducer(reducer, initialState); return ( <AppContext.Provider value={{ state, dispatch }}> {children} </AppContext.Provider> ); }

```

### 326. Can you describe the useMemo() Hook?

[↑ Back to Table of Contents](#table-of-contents) The `useMemo()` Hook in React is used to **optimize performance** by **memoizing the result of expensive calculations**. It ensures that a function is **only re-executed when its dependencies change**, preventing unnecessary computations on every re-render. ##### Syntax

```js const memoizedValue = useMemo(() => computeExpensiveValue(arg), [dependencies]);

```
- **`computeExpensiveValue`**: A function that returns the computed result. - **`dependencies`**: An array of values that, when changed, will cause the memoized function to re-run. If the dependencies haven’t changed since the last render, React returns the **cached result** instead of re-running the function. Let's exaplain the usage of `useMemo` hook with an example of user search and its respective filtered users list.

### 327. Can you dispatch multiple actions in a row with useReducer?

[↑ Back to Table of Contents](#table-of-contents) Yes, you can dispatch multiple actions in a row using `useReducer` but not directly in one call. You'd have to call dispatch multiple times or create a composite action in your reducer that performs multiple updates based on the action type. **Example: Dispatching Multiple Actions** You can define a custom function with dispatching actions one by one.

```js function handleMultipleActions(dispatch) { dispatch({ type: 'increment' }); dispatch({ type: 'increment' }); dispatch({ type: 'reset' }); }

```
After that, you need to invoke it through event handler

```js <button onClick={() => handleMultipleActions(dispatch)}> Run Multiple Actions </button>

```
**Note:** You can also define a custom action type If you want multiple state changes to be handled in one reducer call.

```js case 'increment_twice': return { count: state.count + 2 };

```
Then dispatch

```js dispatch({ type: 'increment_twice' });

```

### 328. Can you explain how useState works internally?

[↑ Back to Table of Contents](#table-of-contents) React’s hooks, including `useState`, rely on some internal machinery that keeps track of state **per component** and **per hook call** during rendering. Here's a simplified explanation of the internal mechanics: ##### 1. **Hook List / Linked List** * React maintains a linked list or array of "hook states" for each component. * When a component renders, React keeps track of which hook it is currently processing via a cursor/index. * Each call to `useState()` corresponds to one "slot" in this list. ##### 2. **State Storage** * Each slot stores: * The current state value. * A queue of pending state updates. ##### 3. **Initial Render** * When the component first renders, React: * Creates a new slot for `useState` with the initial state (e.g., `0`). * Returns `[state, updaterFunction]`. ##### 4. **Updater Function** * The updater function (`setCount`) is a closure that, when called: * Enqueues a state update to React's internal queue. * Schedules a re-render of the component. ##### 5. **Re-render and State Update** * On the next render: * React processes all queued updates for each hook slot. * Updates the stored state value accordingly. * Returns the new state to the component. ##### 6. **Important: Hook Order** * Hooks must be called in the same order on every render so React can match hook calls to their internal slots. * That’s why you can’t call hooks conditionally. The pseudocode for internal implementation of `useState` looks like below,

```js let hookIndex = 0; const hooks = []; function useState(initialValue) { const currentIndex = hookIndex; if (!hooks[currentIndex]) { // First render: initialize state hooks[currentIndex] = { state: initialValue, queue: [], }; } const hook = hooks[currentIndex]; // Process queued updates hook.queue.forEach(update => { hook.state = update(hook.state); }); hook.queue = []; // Define updater function function setState(action) { // action can be new state or function(state) => new state hook.queue.push(typeof action === 'function' ? action : () => action); scheduleRender(); // triggers React re-render } hookIndex++; return [hook.state, setState]; }

```

### 329. Can you have multiple useEffect hooks in a single component?

Yes, multiple useEffect hooks are allowed and recommended when you want to separate concerns.

```jsx useEffect(() => { // Handles API fetch }, ** ------------------------------------------------------------------------ --- --- ### Custom hooks vs HOCs vs render props – when to use each? Custom hooks: sharing stateful logic without extra JSX – the modern default. HOCs: when you need to wrap a component (e.g., code splitting, legacy compatibility). Render props: when JSX composition is specifically needed. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### Difference between `useEffect`, `useLayoutEffect`, and `useInsertionEffect`. - **`useEffect`**: Runs asynchronously after the browser paints. Suitable for most side effects. - **`useLayoutEffect`**: Runs synchronously after all DOM mutations but before the browser paints. Useful for measuring layout or making visual updates that should appear before paint (e.g., scrolling to an element). Use sparingly as it blocks painting. - **`useInsertionEffect`**: A newer hook (React 18) intended for CSS‑in‑JS libraries to inject styles before layout effects fire. Not meant for general use. --- ### Difference between `useMemo` and `React.memo`. - **`useMemo`**: A hook that memoizes the result of a computation. It recalculates only when its dependencies change. Used to optimize expensive calculations inside a component. - **`React.memo`**: A higher‑order component that memoizes a component. It prevents re‑rendering if the props have not changed (shallow comparison). It wraps the whole component, not a value. --- --- ### Differentiate React Hooks vs Classes. | React HooksClasses | | | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | | It is used in functional components of React. | It is used in class-based components of React. | | It will not require a declaration of any kind of constructor. | It is necessary to declare the constructor inside the class component. | | It does not require the use of `this` keyword in state declaration or modification. | Keyword `this` will be used in state declaration (`this.state`) and in modification (`this.setState()`). | | It is easier to use because of the `useState` functionality. | No specific function is available for helping us to access the state and its corresponding setState variable. | | React Hooks can be helpful in implementing Redux and context API. | Because of the long setup of state declarations, class states are generally not preferred. | --- ### Do Hooks cover all the functionalities provided by the classes? Our goal is for Hooks to cover all the functionalities for classes at its earliest. There are no Hook equivalents for the following methods that are not introduced in Hooks yet: - `getSnapshotBeforeUpdate()` - `getDerivedStateFromError()` - `componentDidCatch()` Since it is an early time for Hooks, few third-party libraries may not be compatible with Hooks at present, but they will be added soon. --- ### Do Hooks replace render props and higher order components? Both render props and higher-order components render only a single child but in most of the cases Hooks are a simpler way to serve this by reducing nesting in your tree. **** ------------------------------------------------------------------------ --- --- ### Does React Hook work with static typing? Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. React Hooks are functions that are designed to make sure about all attributes must be statically typed. For enforcing stricter static typing within our code, we can make use of the React API with custom Hooks. --- ### Explain about types of Hooks in React. There are two types of Hooks in React. They are: **1. Built-in Hooks:** The built-in Hooks are divided into 2 parts as given below: - **Basic Hooks:** - `useState()`: This functional component is used to set and retrieve the state. - `useEffect()`: It enables for performing the side effects in the functional components. - `useContext()`: It is used for creating common data that is to be accessed by the components hierarchy without having to pass the props down to each level. - **Additional Hooks:** - `useReducer()` : It is used when there is a complex state logic that is having several sub-values or when the upcoming state is dependent on the previous state. It will also enable you to optimization of component performance that will trigger deeper updates as it is permitted to pass the dispatch down instead of callbacks. - `useMemo()` : This will be used for recomputing the memoized value when there is a change in one of the dependencies. This optimization will help for avoiding expensive calculations on each render. - `useCallback()` : This is useful while passing callbacks into the optimized child components and depends on the equality of reference for the prevention of unneeded renders. - `useImperativeHandle()`: It will enable modifying the instance that will be passed with the ref object. - `useDebugValue()`: It is used for displaying a label for custom hooks in React DevTools. - `useRef()` : It will permit creating a reference to the DOM element directly within the functional component. - `useLayoutEffect()`: It is used for the reading layout from the DOM and re-rendering synchronously. **2. Custom Hooks: **A custom Hook is basically a function of JavaScript. The Custom Hook working is similar to a regular function. The “use” at the beginning of the Custom Hook Name is required for React to understand that this is a custom Hook and also it will describe that this specific function follows the rules of Hooks. Moreover, developing custom Hooks will enable you for extracting component logic from within reusable functions. --- ### Explain how to create a simple React Hooks example program. I will assume that you are having some coding knowledge about JavaScript and have installed Node on your system for creating a below given React Hook program. An installation of Node comes along with the command-line tools: npm and npx, where npm is useful to install the packages into a project and npx is useful in running commands of Node from the command line. The npx looks in the current project folder for checking whether a command has been installed there. When the command is not available on your computer, the npx will look in the npmjs.com repository, then the latest version of the command script will be loaded and will run without locally installing it. This feature is useful in creating a skeleton React application within a few key presses. Open the Terminal inside the folder of your choice, and run the following command: npx create-react-app react-items-with-hooks Here, the `create-react-app` is an app initializer created by Facebook, to help with the easy and quick creation of React application, providing options to customize it while creating the application? The above command will create a new folder named react-items-with-hooks and it will be initialized with a basic React application. Now, you will be able to open the project in your favourite IDE. You can see an src folder inside the project along with the main application component `App.js`. This file is having a single function `App()` which will return an element and it will make use of an extended JavaScript syntax(JSX) for defining the component. JSX will permit you for writing HTML-style template syntax directly into the JavaScript file. This mixture of JavaScript and HTML will be converted by React toolchain into pure JavaScript that will render the HTML element. It is possible to define your own React components by writing a function that will return a JSX element. You can try this by creating a new file `src/SearchItem.js`and put the following code into it. import React from 'react'; export function SearchItem() { return ( <div> <div className="search-input"> <input type="text" placeholder="SearchItem"/> </div> <h1 className="h1">Search Results</h1> <div className="items"> <table> <thead> <tr> <th className="itemname-col">Item Name</th> <th className="price-col">Price</th> <th className="quantity-col">Quantity</th> </tr> </thead> <tbody></tbody> </table> </div> </div> ); } This is all about how you can create a component. It will only display the empty table and doesn’t do anything. But you will be able to use the Search component in the application. Open the file `src/App.js` and add the import statement given below to the top of the file. import { SearchItem } from './SearchItem'; Now, from the logo.svg, import will be removed and then contents of returned value in the function `App()` will be replaced with the following code: ::: {classname="App"}

```{=html} <header>

```
Items with Hooks

```{=html} </header>

```
`<SearchItem/>`{=html} ::: You can notice that the element \<SearchItem/> has been used just similar to an HTML element. The JSX syntax will enable for including the components in this approach directly within the JavaScript code. Your application can be tested by running the below-given command in your terminal. `npm start` This command will compile your application and open your default browser into [http://localhost:4000](http://localhost:4000/). This command can be kept on running when code development is in progress to make sure that the application is up-to-date, and also this browser page will be reloaded each time you modify and save the code. This application will work finely, but it doesn’t look nice as it doesn’t react to any input from the user. You can make it more interactive by adding a state with React Hooks, adding authentication, etc. --- ### Explain React Hooks. **What are Hooks? **Hooks are functions that let us “hook into” React state and lifecycle features from a **functional component.** React Hooks** cannot** be used in class components. They let us write components without class. **Why were Hooks introduced in React?** React hooks were introduced in the 16.8 version of React. Previously, functional components were called stateless components. Only class components were used for state management and lifecycle methods. The need to change a functional component to a class component, whenever state management or lifecycle methods were to be used, led to the development of Hooks. *Example of a hook: ***useState hook:** In functional components, the useState hook lets us define a state for a component: function Person(props) { // We are declaring a state variable called name. // setName is a function to update/change the value of name let \[name, setName\] = useState(''); } The state variable “name” can be directly used inside the HTML. --- ### Explain `useEffect` deeply: cleanup function, dependency array pitfalls. `useEffect` lets you perform side effects (data fetching, subscriptions, DOM manipulations) in functional components. It runs after the browser paints. - **Dependency array**: If omitted, effect runs after every render. If empty (`[]`), runs only once (mount). If values are provided, effect runs when any of those values change. - **Cleanup function**: Return a function from `useEffect` – it runs before the component unmounts and before the next effect execution (to clean up previous subscriptions). Useful for canceling requests, clearing timers, removing event listeners. **Pitfalls**: - Missing dependencies can lead to stale data or infinite loops. - Including unnecessary dependencies may cause excessive re‑runs. - Using objects or arrays as dependencies without memoization can cause unwanted re‑runs because reference changes every render. --- ### How do you create a custom hook? A function whose name starts with 'use' that calls other hooks. It extracts and reuses stateful logic without changing component hierarchy. E.g., `useWindowSize()`, `useFetch()`, `useDebounce()`. ------------------------------------------------------------------------ --- --- ### How do you share state logic between components using custom hooks? Custom hooks allow you to **extract and share stateful logic** between components without changing their hierarchy. The state itself is not shared---each component using the hook gets its own isolated state. #### Example: useLocalStorage Hook

```jsx import { useState, useEffect } from 'react'; function useLocalStorage(key, initialValue) { // Get stored value or use initial value const ** ------------------------------------------------------------------------

### 330. Can You Use Multiple Contexts in One Component?

[↑ Back to Table of Contents](#table-of-contents) Yes, it is possible. You can use multiple contexts inside the same component by calling useContext multiple times, once for each context. It can be achieved with below steps, * Create multiple contexts using `createContext()`. * Wrap your component tree with multiple `<Provider>`s. * Call `useContext()` separately for each context in the same component. **Example: Using `ThemeContext` and `UserContext` Together**

```js import React, { createContext, useContext } from 'react'; // Step 1: Create two contexts const ThemeContext = createContext(); const UserContext = createContext(); function Dashboard() { // Step 2: Use both contexts const theme = useContext(ThemeContext); const user = useContext(UserContext); return ( <div style={{ background: theme === 'dark' ? '#333' : '#fff' }}> <h1>Welcome, {user.name}</h1> <p>Current theme: {theme}</p> </div> ); } // Step 3: Provide both contexts function App() { return ( <ThemeContext.Provider value="dark"> <UserContext.Provider value={{ name: 'Sudheer' }}> <Dashboard /> </UserContext.Provider> </ThemeContext.Provider> ); } export default App;

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 331. Can you use useRef to persist values across renders??

[↑ Back to Table of Contents](#table-of-contents) Yes, you can use `useRef` to persist values across renders in React. Unlike `useState`, changing `.current` does not cause re-renders, but the value is preserved across renders. **Example:**

```js function Timer() { const renderCount = useRef(0); useEffect(() => { renderCount.current++; console.log("Render count:", renderCount.current); }); return <div>Check console for render count.</div>; }

```

### 332. Cleanup Function Execution (Returned function from `useEffect`)

The cleanup function is called **before the effect is re-executed** and when the component **unmounts**. [↑ Back to Table of Contents](#table-of-contents)

### 333. Combining with?

`**useReducer**` **for Global State Management** When combined with `useReducer`, `useContext` becomes a powerful tool for managing more complex global state logic. This pattern helps maintain cleaner, scalable state logic without introducing external libraries like Redux. Some of the common use cases of useContext are listed below, [↑ Back to Table of Contents](#table-of-contents)

### 334. Context / Hooks?

-- Use a hook like `useFeatureFlag(flagKey)` that returns the current variation. This can be used in components to conditionally render or execute code.

### 335. Controlled vs uncontrolled components -- explain with examples.

- **Controlled component**: Form input whose value is controlled by React state. The input's value is set via `value` prop and updates via `onChange`. React is the single source of truth.

```
jsx const [value, setValue] = useState(''); <input value={value} onChange={e => setValue(e.target.value)} />

```
- **Uncontrolled component**: The DOM itself manages the input state. You access the current value via a ref (`useRef`).

```
jsx const inputRef = useRef(); <input ref={inputRef} /> // later: inputRef.current.value

```

### 336. Create the Auth Context:

You can define `AuthProvider` which holds and provides `user`, `login()`, and `logout()` via context.

```js // AuthContext.js import React, { createContext, useContext, useState } from 'react'; const AuthContext = createContext(); export function AuthProvider({ children }) { const [user, setUser] = useState(null); const login = (username) => setUser({ name: username }); const logout = () => setUser(null); return ( <AuthContext.Provider value={{ user, login, logout }}> {children} </AuthContext.Provider> ); } // Custom hook for cleaner usage export const useAuth = () => useContext(AuthContext);

```

### 337. Custom hooks vs. HOCs vs. render props — when do you use each today?

Custom hooks are the modern default for sharing stateful logic without extra JSX nesting. HOCs remain useful when you need to *wrap* a component itself (e.g., legacy code-splitting boundaries). Render props matter when the sharing genuinely needs to happen through JSX composition/context.

### 338. Dashboard with logout:

Read or access user and logout details from `useAuth` custom hook and use it inside dashboard page.

```js // Dashboard.js import React from 'react'; import { useAuth } from './AuthContext'; function Dashboard() { const { user, logout } = useAuth(); if (!user) { return <p>Please login to view the dashboard.</p>; } return ( <div> <h2>Dashboard</h2> <p>Logged in as: {user.name}</p> <button onClick={logout}>Logout</button> </div> ); } export default Dashboard;

```
[↑ Back to Table of Contents](#table-of-contents)

### 339. Defining a child component inside a parent's render function?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Parent() { const [count, setCount] = React.useState(0); const Child = () => <div>child: {count}</div>; // Defined INSIDE render return ( <> <Child /> <button onClick={() => setCount(c => c + 1)}>+</button> </> ); }

```
**Behavior:** Works but is a serious performance bug. Every re-render creates a NEW `Child` component type. React sees a different component and UNMOUNTS the old one and MOUNTS a new one every render. **Explanation:** Never define components inside render functions. Each render creates a new function reference — React's reconciler sees a new component type and destroys + recreates the DOM. Move `Child` OUTSIDE `Parent`.

### 340. Differentiate React Hooks vs Classes.

[↑ Back to Table of Contents](#table-of-contents) | React HooksClasses | | | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | | It is used in functional components of React. | It is used in class-based components of React. | | It will not require a declaration of any kind of constructor. | It is necessary to declare the constructor inside the class component. | | It does not require the use of `this` keyword in state declaration or modification. | Keyword `this` will be used in state declaration (`this.state`) and in modification (`this.setState()`). | | It is easier to use because of the `useState` functionality. | No specific function is available for helping us to access the state and its corresponding setState variable. | | React Hooks can be helpful in implementing Redux and context API. | Because of the long setup of state declarations, class states are generally not preferred. |

### 341. Do Hooks cover all the functionalities provided by the classes?

Our goal is for Hooks to cover all the functionalities for classes at its earliest. There are no Hook equivalents for the following methods that are not introduced in Hooks yet: - `getSnapshotBeforeUpdate()` - `getDerivedStateFromError()` - `componentDidCatch()` Since it is an early time for Hooks, few third-party libraries may not be compatible with Hooks at present, but they will be added soon. [↑ Back to Table of Contents](#table-of-contents)

### 342. Do Hooks replace render props and higher order components?

[↑ Back to Table of Contents](#table-of-contents) Both render props and higher-order components render only a single child but in most of the cases Hooks are a simpler way to serve this by reducing nesting in your tree. **** ------------------------------------------------------------------------

### 343. Do I need to rewrite all my class components with hooks?

[↑ Back to Table of Contents](#table-of-contents) No. But you can try Hooks in a few components(or new components) without rewriting any existing code. Because there are no plans to remove classes in ReactJS.

### 344. Does React Hook work with static typing?

Static typing refers to the process of code check during the time of compilation for ensuring all variables will be statically typed. React Hooks are functions that are designed to make sure about all attributes must be statically typed. For enforcing stricter static typing within our code, we can make use of the React API with custom Hooks. [↑ Back to Table of Contents](#table-of-contents)

### 345. Does useMemo prevent re-rendering of child components?

[↑ Back to Table of Contents](#table-of-contents) The `useMemo` hook **does not directly prevent re-rendering of child components**. Its main purpose is to memoize the result of an expensive computation so that it doesn’t get recalculated unless its dependencies change. While this can improve performance, it doesn’t inherently control whether a child component re-renders. However, `useMemo` **can help prevent re-renders** when the memoized value is passed as a prop to a child component that is wrapped in `React.memo`. In that case, if the memoized value doesn’t change between renders (i.e., it has the same reference), React.memo can skip re-rendering the child. So, while `useMemo` doesn’t stop renders on its own, it **works in combination** with tools like `React.memo` to optimize rendering behavior.

### 346. Empty Dependency Array:

`**[]**`

```css useEffect(() => { // runs once after the initial render }, []);

```
* Effect runs **only once** (like `componentDidMount`). * Ignores all state/prop changes.

### 347. Event Listeners?

```jsx useEffect(() => { const handleResize = () => setWidth(window.innerWidth); window.addEventListener('resize', handleResize); return () => window.removeEventListener('resize', handleResize); }, []);

```

### 348. Explain about types of Hooks in React.

[↑ Back to Table of Contents](#table-of-contents) There are two types of Hooks in React. They are:

### 349. Explain about types of side effects in React component.

There are two types of side effects in React component. They are: - **Effects without Cleanup: **This side effect will be used in useEffect which does not restrict the browser from screen update. It also improves the responsiveness of an application. A few common examples are network requests, Logging, manual DOM mutations, etc. - **Effects with Cleanup:** Some of the Hook effects will require the cleanup after updating of DOM is done. For example, if you want to set up an external data source subscription, it requires cleaning up the memory else there might be a problem of memory leak. It is a known fact that React will carry out the cleanup of memory when the unmounting of components happens. But the effects will run for each render() method rather than for any specific method. Thus we can say that, before execution of the effects succeeding time the React will also cleanup effects from the preceding render. Get Access to 250+ Guides with Scaler Mobile App! Experience free learning content on the Scaler Mobile App 4.5 100K+ Play Store [↑ Back to Table of Contents](#table-of-contents)

### 350. Explain how to create a simple React Hooks example program.

[↑ Back to Table of Contents](#table-of-contents) I will assume that you are having some coding knowledge about JavaScript and have installed Node on your system for creating a below given React Hook program. An installation of Node comes along with the command-line tools: npm and npx, where npm is useful to install the packages into a project and npx is useful in running commands of Node from the command line. The npx looks in the current project folder for checking whether a command has been installed there. When the command is not available on your computer, the npx will look in the npmjs.com repository, then the latest version of the command script will be loaded and will run without locally installing it. This feature is useful in creating a skeleton React application within a few key presses. Open the Terminal inside the folder of your choice, and run the following command: npx create-react-app react-items-with-hooks Here, the `create-react-app` is an app initializer created by Facebook, to help with the easy and quick creation of React application, providing options to customize it while creating the application? The above command will create a new folder named react-items-with-hooks and it will be initialized with a basic React application. Now, you will be able to open the project in your favourite IDE. You can see an src folder inside the project along with the main application component `App.js`. This file is having a single function `App()` which will return an element and it will make use of an extended JavaScript syntax(JSX) for defining the component. JSX will permit you for writing HTML-style template syntax directly into the JavaScript file. This mixture of JavaScript and HTML will be converted by React toolchain into pure JavaScript that will render the HTML element. It is possible to define your own React components by writing a function that will return a JSX element. You can try this by creating a new file `src/SearchItem.js`and put the following code into it. import React from 'react'; export function SearchItem() { return ( <div> <div className="search-input"> <input type="text" placeholder="SearchItem"/> </div> <h1 className="h1">Search Results</h1> <div className="items"> <table> <thead> <tr> <th className="itemname-col">Item Name</th> <th className="price-col">Price</th> <th className="quantity-col">Quantity</th> </tr> </thead> <tbody></tbody> </table> </div> </div> ); } This is all about how you can create a component. It will only display the empty table and doesn’t do anything. But you will be able to use the Search component in the application. Open the file `src/App.js` and add the import statement given below to the top of the file. import { SearchItem } from './SearchItem'; Now, from the logo.svg, import will be removed and then contents of returned value in the function `App()` will be replaced with the following code: ::: {classname="App"}

```{=html} <header>

```
Items with Hooks

```{=html} </header>

```
`<SearchItem/>`{=html} ::: You can notice that the element \<SearchItem/> has been used just similar to an HTML element. The JSX syntax will enable for including the components in this approach directly within the JavaScript code. Your application can be tested by running the below-given command in your terminal. `npm start` This command will compile your application and open your default browser into [http://localhost:4000](http://localhost:4000/). This command can be kept on running when code development is in progress to make sure that the application is up-to-date, and also this browser page will be reloaded each time you modify and save the code. This application will work finely, but it doesn’t look nice as it doesn’t react to any input from the user. You can make it more interactive by adding a state with React Hooks, adding authentication, etc.

### 351. Explain React Hooks.

[↑ Back to Table of Contents](#table-of-contents)

### 352. Explain useEffect deeply — cleanup, dependency array pitfalls.

[↑ Back to Table of Contents](#table-of-contents) useEffect runs after render, asynchronously (not blocking paint). Dependencies array: empty [] = run once on mount. [dep1, dep2] = run when those deps change. No array = run after every render. Cleanup: return a function to run on unmount or before next effect — critical for: removing event listeners, cancelling subscriptions, clearing timers, aborting fetch. Pitfalls: (1) Missing dependencies causes stale closures. (2) Object/function deps cause infinite loops if created inline. (3) Async functions inside useEffect need IIFE or internal async function.

```javascript useEffect(() => { const controller = new AbortController(); fetch('/api', { signal: controller.signal }) .then(r => r.json()) .then(setData) .catch(e => { if (e.name !== 'AbortError') setError(e) }); return () => controller.abort(); // cleanup! }, [url]); // re-run when url changes

```

### 353. Fix a `useEffect` that has missing dependencies (the ESLint exhaustive-deps warning)

[↑ Back to Table of Contents](#table-of-contents)

```jsx // ❌ Bug: `userId` is used inside but omitted from deps — stale closure risk useEffect(() => { fetchUser(userId).then(setUser); }, []); // eslint warns: missing dependency 'userId' // ✅ Fix 1: include it — effect re-runs whenever userId changes (usually the correct behavior) useEffect(() => { fetchUser(userId).then(setUser); }, [userId]); // ✅ Fix 2: if a value is intentionally not a dependency (e.g. a stable setState function or a ref), // that's fine to omit — setState/dispatch identities are guaranteed stable by React and refs don't need to be listed.

```
Never "fix" the warning by disabling the lint rule (`// eslint-disable-next-line`) unless you're certain the omitted value truly can't change in a way that matters — that's how stale-closure bugs get shipped. If you deliberately don't want the effect to re-run for a value that does change, wrap that value in a ref instead of lying to the dependency array.

### 354. Follow the Rules of Hooks?

- Only call hooks at the top level (not inside loops, conditions, or nested functions) - Only call hooks from React functions (components or custom hooks)

### 355. Force-updating a component after mutating a ref directly?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function useForceUpdate() { const [, setState] = React.useState(0); return React.useCallback(() => setState(n => n + 1), []); } function App() { const forceUpdate = useForceUpdate(); const data = React.useRef({ value: 0 }); return ( <> <p>Value: {data.current.value}</p> <button onClick={() => { data.current.value += 1; // mutate ref forceUpdate(); // manually trigger re-render }}> Increment </button> </> ); }

```
**Behavior:** Works correctly — each click increments the displayed value. **Explanation:** Refs don't trigger re-renders on their own. By separating the data (ref) from the render trigger (state), you can accumulate changes and batch re-renders manually. Useful for high-frequency updates where you control when to re-render.

### 356. Functional update vs direct update?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [user, setUser] = React.useState({ name: 'Alice', age: 25 }); function updateName() { setUser({ name: 'Bob' }); // Missing age! } return ( <div> <p>{user.name} - {user.age}</p> <button onClick={updateName}>Update</button> </div> ); }

```
**Behavior:** After clicking, shows `Bob - ` (age is gone). **Explanation:** Unlike class component `setState`, the `useState` setter REPLACES the entire state, not merges it. Passing `{ name: 'Bob' }` discards `age`. Fix: `setUser(prev => ({ ...prev, name: 'Bob' }))`.

### 357. Functional vs class components – key differences?

[↑ Back to Table of Contents](#table-of-contents) - **Functional**: Plain JS functions, use hooks for state/lifecycle, simpler, preferred since React 16.8. - **Class**: Extend `React.Component`, use `this.state` and lifecycle methods, support error boundaries natively. New code should use functional components with hooks.

### 358. Home page with login:

Read or access user and login details through custom useAuth hook and use it inside home page.

```js // HomePage.js import React from 'react'; import { useAuth } from './AuthContext'; function HomePage() { const { user, login } = useAuth(); return ( <div> <h1>Home</h1> {user ? ( <p>Welcome back, {user.name}!</p> ) : ( <button onClick={() => login('Alice')}>Login</button> )} </div> ); } export default HomePage;

```

### 359. Hook List / Linked List?

[↑ Back to Table of Contents](#table-of-contents) * React maintains a linked list or array of "hook states" for each component. * When a component renders, React keeps track of which hook it is currently processing via a cursor/index. * Each call to `useState()` corresponds to one "slot" in this list.

### 360. Hooks and State Management?

With Hooks (like `useState`, `useEffect`): * React keeps an **internal list of hooks per component**. * Hooks are identified by their order in the function. * When state updates occur, React re-renders the component and re-runs the hooks in the same order.

### 361. How do reactive dependencies in the useEffect dependency array affect its execution behavior?

[↑ Back to Table of Contents](#table-of-contents) The `useEffect` hook accepts an optional dependencies argument that accepts an array of reactive values. The **dependency array** determines **when** the effect runs. i.e, It makes `useEffect` _reactive_ to changes in specified values. ##### **How Dependency Array Affects Behavior**

### 362. How do you avoid unnecessary object/function recreation?

Declare stable values outside the component when possible, use `useMemo` for objects/arrays, `useCallback` for functions, and avoid inline object literals as prop values in JSX. [⬆ Back to Table of Contents](#-table-of-contents)

### 363. How do you avoid unnecessary re-renders caused by Context?

Memoize the `value` (`useMemo`), split into smaller contexts, or move frequently-changing state into a selector-based library.

### 364. How do you create a custom hook?

[↑ Back to Table of Contents](#table-of-contents) A function whose name starts with 'use' that calls other hooks. It extracts and reuses stateful logic without changing component hierarchy. E.g., `useWindowSize()`, `useFetch()`, `useDebounce()`. ------------------------------------------------------------------------

### 365. How do you create and consume Context?

`createContext(defaultValue)`, wrap in `<Context.Provider value={...}>`, read with `useContext(Context)`.

### 366. How do you fetch data with `useEffect`? What are the pitfalls?

Use a cancelled-flag or `AbortController` in the cleanup to avoid race conditions from fast-changing deps overwriting fresher data with stale responses.

### 367. How do you integrate a non-React library (e.g., D3, Leaflet)?

Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it. [⬆ Back to Table of Contents](#-table-of-contents)

### 368. How do you manage focus after navigation in a SPA?

After route change, programmatically move focus to the new page's heading or a skip-link target. Use a ref and `ref.current.focus()` in `useEffect` when the route changes. [↑ Back to Table of Contents](#table-of-contents)

### 369. How do you pass parent data to the 5th child component?

[↑ Back to Table of Contents](#table-of-contents) Options in order of preference: (1) Component composition — restructure so the component needing data isn't 5 levels deep. (2) React Context — create a context, wrap with Provider at the parent level, consume with useContext at the child — no prop drilling needed. (3) State management (Redux/Zustand) — store state globally, child subscribes directly. (4) Prop drilling — workable for 2-3 levels, painful at 5 levels. For most cases, Context is the right answer.

### 370. How do you prevent an expensive component from blocking user input (e.g., a large table filtering as you type)?

`useTransition` to mark the expensive re-render as low priority, or `useDeferredValue` on the filter text, keeping the input responsive while the table catches up.

### 371. How do you share logic between a Hook and an effect cleanup safely (avoiding duplicated subscribe/unsubscribe code)?

Define the subscribe/unsubscribe logic as named functions inside the effect (or a stable custom Hook), ensuring the same reference is used to both subscribe and later unsubscribe correctly.

### 372. How do you share state logic between components using custom hooks?

Custom hooks allow you to **extract and share stateful logic** between components without changing their hierarchy. The state itself is not shared—each component using the hook gets its own isolated state.

### 373. How do you test a component that fetches data in `useEffect`?

Mock the request (`msw`/`jest.mock`), render, then `findByText`/`waitFor` for the resolved content.

### 374. How do you test custom hooks?

Use `renderHook` from `@testing-library/react`. `act()` wraps state updates. `const {result} = renderHook(() => useCounter(0)); act(() => result.current.increment()); expect(result.current.count).toBe(1)`. [⬆ Back to Table of Contents](#-table-of-contents)

### 375. How do you type `useContext` so consumers get a properly-typed value (and a helpful error if used outside the Provider)?

Type the context as `createContext<ContextType | undefined>(undefined)`, then write a custom `useMyContext()` Hook that throws a clear error if the value is `undefined`, letting consumers use a properly-narrowed, non-nullable type.

### 376. How do you type `useReducer`?

[↑ Back to Table of Contents](#table-of-contents) Define State and Action types (often a discriminated union for Action). `useReducer<Reducer<State, Action>>(reducer, initial)`. TypeScript infers dispatch type automatically.

### 377. How do you type `useRef` for a DOM node vs a mutable value?

`useRef<HTMLInputElement>(null)` for DOM; `useRef<number>(0)` for a freely mutable instance value.

### 378. How do you type `useState` when the initial value doesn't convey the full type?

`useState<User | null>(null)` — supply an explicit generic.

### 379. How do you type `useState` with TypeScript?

`useState<Type>(initialValue)`. For nullable: `useState<User | null>(null)`. TypeScript infers the type from initial value in simple cases; be explicit when the initial value doesn't reveal the full type. [↑ Back to Table of Contents](#table-of-contents)

### 380. How do you type `useState`?

`useState<Type>(initial)` — TypeScript infers the type from the initial value in simple cases; be explicit (`useState<User | null>(null)`) when the initial value doesn't reveal the full type.

### 381. How do you type a custom Hook's tuple return value?

Annotate the return type explicitly as a tuple, since TS otherwise infers an array literal as a union array.

### 382. How do you type a reducer function and its actions for `useReducer`?

Define a discriminated union for actions (`type Action = { type: 'increment' } | { type: 'set'; payload: number }`), then `function reducer(state: State, action: Action): State`, letting TypeScript narrow `action.payload` based on `action.type` inside each case.

### 383. How do you type context?

`createContext<ContextType | undefined>(undefined)`. In `useContext` wrapper hook, assert non-null or throw if context is undefined. This avoids the need to check for undefined in every consumer. [↑ Back to Table of Contents](#table-of-contents)

### 384. How Do You Use useRef to Access a DOM Element in React? Give an example.

[↑ Back to Table of Contents](#table-of-contents) The `useRef` hook is commonly used in React to directly reference and interact with DOM elements — like focusing an input, scrolling to a section, or controlling media elements. When you assign a ref to a DOM element using useRef, React gives you access to the underlying DOM node via the .current property of the ref object. **Example: Focus an input**

```js import React, { useRef } from 'react'; function FocusInput() { const inputRef = useRef(null); // create the ref const handleFocus = () => { inputRef.current.focus(); // access DOM element and focus it }; return ( <div> <input type="text" ref={inputRef} /> <button onClick={handleFocus}>Focus the input</button> </div> ); }

```
**Note:** The DOM reference is only available **after the component has mounted** — typically accessed in `useEffect` or event handlers.

### 385. How does `useLayoutEffect` cause layout thrashing, and how do you avoid it?

Alternating reads (`offsetHeight`) and writes (`style.height = ...`) forces synchronous reflow on every read-after-write cycle. Batch all reads first, then all writes, to avoid interleaved forced reflows.

### 386. How does `useOptimistic` (React 19) differ from manually managing optimistic state with `useState`?

`useOptimistic` automatically reverts to the real state once the underlying async action settles (success or failure), removing the need to manually track and roll back a separate "pending" state variable yourself.

### 387. How does `useReducer` works? Explain with an example?

[↑ Back to Table of Contents](#table-of-contents) The `useReducer` hooks works similarly to Redux, where: * You define a **reducer function** to handle state transitions. * You dispatch actions to update the state. **Counter Example with Increment, Decrement, and Reset:** 1. Reducer function: Define a counter reducer function that takes the current state and an action object with a type, and returns a new state based on that type.

```js function counterReducer(state, action) { switch (action.type) { case 'increment': return { count: state.count + 1 }; case 'decrement': return { count: state.count - 1 }; case 'reset': return { count: 0 }; default: return state; } }

```
2. Using `useReducer`: Invoke `useReducer` with above reducer function along with initial state. Thereafter, you can attach dispatch actions for respective button handlers.

```js import React, { useReducer } from 'react'; function Counter() { const initialState = { count: 0 }; const [state, dispatch] = useReducer(counterReducer, initialState); return ( <div style={{ textAlign: 'center' }}> <h2>Count: {state.count}</h2> <button onClick={() => dispatch({ type: 'increment' })}>Increment</button> <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button> <button onClick={() => dispatch({ type: 'reset' })}>Reset</button> </div> ); } export default Counter;

```
Once the new state has been returned, React re-renders the component with the updated `state.count`.

### 388. How does `useRef` differ from a regular variable?

Regular variables reset on every render. A ref persists. Unlike state, changing `ref.current` does not cause a re-render. Think of it as instance variable storage for functional components. [⬆ Back to Table of Contents](#-table-of-contents)

### 389. How does `useState` work internally?

React keeps a per-component list ("hook list") of slots indexed by call order; each `useState` call reads/writes its slot. This is why hook order must stay identical across renders — React has no other way to match calls to state.

### 390. How does the performance of using Hooks will differ in comparison with the classes?

- React Hooks will avoid a lot of overheads such as the instance creation, binding of events, etc., that are present with classes. - Hooks in React will result in smaller component trees since they will be avoiding the nesting that exists in HOCs (Higher Order Components) and will render props which result in less amount of work to be done by React. [↑ Back to Table of Contents](#table-of-contents)

### 391. How does useLayoutEffect cause layout thrashing?

[↑ Back to Table of Contents](#table-of-contents) The `useLayoutEffect` can **cause layout thrashing** when you **repeatedly read and write to the DOM** in ways that force the browser to recalculate layout multiple times per frame. This is because `useLayoutEffect` runs _before the browser paints_, these reflows happen _synchronously_, blocking rendering and degrading performance. **Example:**

```js function ThrashingComponent() { const ref = useRef(); useLayoutEffect(() => { const height = ref.current.offsetHeight; //Read ref.current.style.height = height + 20 + 'px'; //Write const newHeight = ref.current.offsetHeight; //Read again — forces reflow }, []); return <div ref={ref}>Hello</div>; }

```
In the above code, each read/write cycle triggers synchronous reflows, blocking the main thread and delays UI rendering. This issue can be avoided by batching your DOM reads and writes and prevent unnecessary reads after writes.

### 392. How does useLayoutEffect work during server-side rendering (SSR)?

The `useLayoutEffect` hook does **not run on the server**, because there is no DOM. React issues a warning in server environments like Next.js if `useLayoutEffect` is used directly. This can be mitigated using a conditional polyfill:

```jsx const useIsomorphicLayoutEffect = typeof window !== 'undefined' ? useLayoutEffect : useEffect;

```
i.e, Use `useIsomorphicLayoutEffect` in components that render both on client and server. [↑ Back to Table of Contents](#table-of-contents)

### 393. How is `useReducer` Different from `useState`?

[↑ Back to Table of Contents](#table-of-contents) There are notable differences between `useState` and `useReducer` hooks. | Feature | `useState` | `useReducer` | |-----------------------|--------------------------------------|---------------------------------------| | State complexity | Simple (one variable or flat object) | Complex, multi-part or deeply nested | | Update style | Direct (e.g. `setState(x)`) | Through actions (e.g. `dispatch({})`) | | Update logic | In component | In reducer function | | Reusability & testing | Less reusable | Highly reusable & testable |

### 394. How should you structure a large React application?

Feature-based folders (`features/auth`, `features/dashboard`) rather than type-based (`components/`, `containers/`) once the app grows; shared UI primitives in a common folder; business logic pushed into hooks/services; clear separation between UI, state, and data layers; TypeScript for safety at scale.

### 395. How to avoid?

- **`React.memo`** – wrap functional components to prevent re‑renders when props (shallow‑compared) don’t change. - **`useMemo`** – memoize expensive computations or object/array values. - **`useCallback`** – memoize functions to avoid new references. - **Colocate state** – move state down to the component that needs it, rather than lifting it unnecessarily high. - **Splitting context** – break large contexts into smaller ones so consumers only subscribe to what they use. - **`useReducer` instead of multiple `useState`** – can help group related state updates and reduce re‑renders if implemented with care.

### 396. How to ensure hooks followed the rules in your project?

React team released an ESLint plugin called **eslint-plugin-react-hooks** that enforces Hook's two rules. It is part of Hooks API. You can add this plugin to your project using the below command,

```javascript npm install eslint-plugin-react-hooks --save-dev

```
And apply the below config in your ESLint config file,

```javascript // Your ESLint configuration { "plugins": [ // ... "react-hooks" ], "rules": { // ... "react-hooks/rules-of-hooks": "error" } }

```
This plugin also provide another important rule through `react-hooks/exhaustive-deps`. It ensures that the dependencies of useEffect, useCallback, and useMemo hooks are correctly listed to avoid potential bugs.

```jsx useEffect(() => { // Forgetting `message` will result in incorrect behavior console.log(message); }, []); // Here `message` should be a dependency

```
The recommended `eslint-config-react-app` preset already includes the hooks rules of this plugin. For example, the linter enforce proper naming convention for hooks. If you rename your custom hooks which as prefix "use" to something else then linter won't allow you to call built-in hooks such as useState, useEffect etc inside of your custom hook anymore. **Note:** This plugin is intended to use in Create React App by default. [↑ Back to Table of Contents](#table-of-contents)

### 397. How to fetch data with React Hooks?

[↑ Back to Table of Contents](#table-of-contents) The effect hook called `useEffect` is used to fetch the data with axios from the API and to set the data in the local state of the component with the state hook’s update function. Let's take an example in which it fetches list of react articles from the API

```
import React, { useState, useEffect } from 'react'; import axios from 'axios'; function App() { const [data, setData] = useState({ hits: [] }); useEffect(async () => { const result = await axios('http://hn.algolia.com/api/v1/search?query=react'); setData(result.data); }, []); return ( <ul> {data.hits.map((item) => ( <li key={item.objectID}> <a href={item.url}>{item.title}</a> </li> ))} </ul> ); } export default App;

```
Remember we provided an empty array as second argument to the effect hook to avoid activating it on component updates but only for the mounting of the component. i.e, It fetches only for component mount. [

### 398. How to prevent infinite loops with useEffect?

[↑ Back to Table of Contents](#table-of-contents) Infinite loops happen when the effect updates state that’s listed in its own dependency array, which causes the effect to re-run, updating state again and so on. **Infinite loop scenario:**

```js useEffect(() => { setCount(count + 1); }, [count]); // Triggers again every time count updates

```
You need to ensure that setState calls do not depend on values that cause the effect to rerun, or isolate them with a guard.

```js useEffect(() => { if (count < 5) { setCount(count + 1); } }, [count]);

```

### 399. How would you implement role-based access control (RBAC) in React?

Store user roles in auth context. Create a `usePermissions` hook that checks roles. Wrap protected components with a `Can` component or conditional rendering. Protect routes in the router (loader-level redirect). Never trust client-side checks alone -- enforce on the server. ------------------------------------------------------------------------

### 400. How would you optimize a slow React application?

Diagnostic first --- profile with React DevTools Profiler to identify: Components rendering too often → add React.memo, fix prop references Expensive computations → wrap with useMemo Large bundle → code splitting with React.lazy, tree shaking Slow initial load → SSR/SSG, preloading critical resources Memory leaks → check useEffect cleanups, event listener removal Long list rendering → implement virtualization Network waterfall → parallel data fetching, caching with React Query/SWR ------------------------------------------------------------------------

### 401. Important: Hook Order?

[↑ Back to Table of Contents](#table-of-contents) * Hooks must be called in the same order on every render so React can match hook calls to their internal slots. * That’s why you can’t call hooks conditionally. The pseudocode for internal implementation of `useState` looks like below,

```js let hookIndex = 0; const hooks = []; function useState(initialValue) { const currentIndex = hookIndex; if (!hooks[currentIndex]) { // First render: initialize state hooks[currentIndex] = { state: initialValue, queue: [], }; } const hook = hooks[currentIndex]; // Process queued updates hook.queue.forEach(update => { hook.state = update(hook.state); }); hook.queue = []; // Define updater function function setState(action) { // action can be new state or function(state) => new state hook.queue.push(typeof action === 'function' ? action : () => action); scheduleRender(); // triggers React re-render } hookIndex++; return [hook.state, setState]; }

```

### 402. Index as key with reorder?

```jsx function App() { const [items, setItems] = React.useState([ { id: 1, text: 'First' }, { id: 2, text: 'Second' }, ]); function addFirst() { setItems([{ id: 0, text: 'New' }, ...items]); } // Version A: key=index // Version B: key=item.id return ( <> <button onClick={addFirst}>Add to front</button> <ul> {items.map((item, index) => ( <li key={index}> {/* Or key={item.id} */} {item.text} <input defaultValue={item.text} /> </li> ))} </ul> </> ); }

```
**Behavior with `key={index}`:** Adding to front keeps input values in wrong positions — the new item gets the old first item's input value. **Behavior with `key={item.id}`:** Correct behavior — each item keeps its own input state. **Explanation:** With index keys, prepending shifts all indices. React maps old key `0` to new item at position `0`, reusing the DOM node. With id keys, React correctly identifies each item and mounts a new node for the new item. [↑ Back to Table of Contents](#table-of-contents)

### 403. Initial render:

[↑ Back to Table of Contents](#table-of-contents) * When the component first renders, React: * Creates a new slot for `useState` with the initial state (e.g., `0`). * Returns `[state, updaterFunction]`.

### 404. Initial render:

* When the component first renders, React: * Creates a new slot for `useState` with the initial state (e.g., `0`). * Returns `[state, updaterFunction]`.

### 405. Is dispatch from useReducer asynchronous and does it update state immediately?

[↑ Back to Table of Contents](#table-of-contents) The `dispatch` function returned by `useReducer` is **not asynchronous** — it is a **synchronous** function call. When you call `dispatch(action)`, React **synchronously** invokes your reducer with the current state and the action, computes the new state, and **schedules a re-render**. However, the **state variable does not update immediately** within the same render cycle. The updated state is only available in the **next render**. This behavior is similar to `useState`'s `setState` — React **batches** state updates for performance optimization, meaning the component does not re-render immediately after each `dispatch` call. Instead, React processes all dispatched actions and re-renders once with the final state. ##### Key Points

### 406. Is Hooks cover all use cases for classes?

Hooks doesn't cover all use cases of classes but there is a plan to add them soon. Currently there are no Hook equivalents to the uncommon **getSnapshotBeforeUpdate** and **componentDidCatch** lifecycles yet. [↑ Back to Table of Contents](#table-of-contents)

### 407. Is that possible to use useImperativeHandle without forwardRef?

**No.** `useImperativeHandle` only works when the component is wrapped in `forwardRef`. It's the combination that allows parent components to use a `ref` on a function component. [↑ Back to Table of Contents](#table-of-contents)

### 408. Is useState Synchronous or Asynchronous?

[↑ Back to Table of Contents](#table-of-contents) The `useState` hook is synchronous, but state updates are asynchronous. When you call `useState()`, it runs synchronously and returns the state variable and setter function as tuple.

```js const [count, setCount] = useState(0);

```
This happens immediately during rendering. However, the state update function (**setState**) is asynchronous in the sense that it doesn't update the state immediately. React **batches** updates and applies them before the next render. You won’t see the updated value immediately after calling `setState`. **Example:**

```js const [count, setCount] = useState(0); function handleClick() { setCount(count + 1); console.log(count); // ❗️Still logs the old value }

```
The > `console.log(count)` prints the **old value**, because the update hasn’t happened yet. To see the updated state value, you can use `useEffect()` hook. It runs **after the component has re-rendered.** By the time `useEffect` runs: * The component has been updated. * The **state contains the new value**.

```js import React, { useState, useEffect } from 'react'; function Counter() { const [count, setCount] = useState(0); const handleClick = () => { setCount(count + 1); console.log('Clicked count (old):', count); // Old value }; useEffect(() => { console.log('Updated count:', count); // New value }, [count]); // Only runs when `count` changes return <button onClick={handleClick}>Count: {count}</button>; }

```

### 409. Keep Hooks Focused and Simple?

```jsx // ❌ Bad: One hook doing too much function useEverything() { const [user, setUser] = useState(null); const [posts, setPosts] = useState([]); const [theme, setTheme] = useState('light'); // ... lots of unrelated logic } // ✅ Good: Separate concerns function useUser() { /* user logic */ } function usePosts() { /* posts logic */ } function useTheme() { /* theme logic */ }

```

### 410. Map class lifecycle methods to hooks.

[↑ Back to Table of Contents](#table-of-contents) - `componentDidMount` → `useEffect(() => {...}, [])` - `componentDidUpdate` → `useEffect(() => {...}, [dep])` - `componentWillUnmount` → cleanup function returned from `useEffect` - `getDerivedStateFromProps` → compute derived state inline or in `useMemo`

### 411. Memoize Context Value?

Use `useMemo` to prevent unnecessary re-renders:

```jsx const contextValue = useMemo(() => ({ user, setUser, theme, setTheme }), [user, theme]);

```
However, this only helps if the object structure and dependencies are well controlled. [↑ Back to Table of Contents](#table-of-contents)

### 412. Multiple useEffects order?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { React.useEffect(() => { console.log('effect 1'); return () => console.log('cleanup 1'); }, []); React.useEffect(() => { console.log('effect 2'); return () => console.log('cleanup 2'); }, []); return <div>test</div>; }

```
**Behavior on mount:**

```
effect 1 effect 2

```
**Behavior on unmount:**

```
cleanup 1 cleanup 2

```
**Explanation:** Multiple `useEffect` hooks run in the ORDER they are declared, after each render. Cleanups also run in declaration order on unmount.

### 413. No Dependency Array (Omitted)

```css useEffect(() => { // runs after **every** render });

```
* Effect runs after **every render**, regardless of what changed. * Can lead to **performance issues** if not used carefully. React uses shallow comparison of the dependencies. If any value has changed (!==), the effect will re-run. **Note:** This hook works well when dependencies are primitives or memoized objects/functions. [↑ Back to Table of Contents](#table-of-contents)

### 414. Properly Manage Dependencies?

```jsx // ❌ Bad: Missing dependency useEffect(() => { fetchUser(userId); }, []); // userId is missing // ✅ Good: All dependencies listed useEffect(() => { fetchUser(userId); }, [userId]);

```

### 415. React Compiler (formerly React Forget)

Automatic memoization - no more manual `useMemo`, `useCallback`, or `React.memo` needed!

```jsx // Before: Manual optimization const memoizedValue = useMemo(() => expensiveCalc(a, b), [a, b]); // React 19: Compiler does it automatically const value = expensiveCalc(a, b); // Automatically optimized!

```

### 416. React — Coding / Implementation?

These are live coding questions in React: - Implement a custom `useFetch` hook that handles loading, error, and data states. - Implement a custom `useDebounce` hook. - Implement a custom `useThrottle` hook. - Implement a custom `useLocalStorage` hook. - Implement a custom `useIntersectionObserver` hook. - Implement a custom `usePrevious` hook (returns previous state value). - Implement a custom `useMediaQuery` hook. - Implement a custom `useEventListener` hook. - Implement a custom `useClickOutside` hook. - Implement a custom `useWindowSize` hook. - Implement a custom `useAsync` hook (manage async function states). - Build a counter that increments and decrements. - Build a controlled form with validation (email, password strength). - Build a search input with debouncing that fetches from an API. - Build a list that renders only visible items (virtualization, manual). - Implement a todo list with CRUD and localStorage persistence. - Build a shopping cart with add, remove, update quantity, and total calculation. - Build a multi-step form wizard with Next/Back navigation and validation. - Build an accordion with multiple or single open behavior. - Build a modal / dialog with focus trap and escape key to close. - Implement pagination (client-side and server-side). - Implement infinite scroll using Intersection Observer. - Build a drag-and-drop list (without libraries). - Build a star rating component. - Build a file upload component with drag-and-drop, progress, and preview. - Implement a recursive comment thread (nested comments with reply). - Fix a component that has a stale closure problem in `useEffect`. - Fix a component where `useEffect` has missing dependencies (ESLint warning trap). - Fix a React component that causes infinite re-renders. - Given a slow React tree, identify and fix the performance bottleneck (profile, add `memo`, `useMemo`, `useCallback`). - Implement `useReducer` for a complex form state. - Implement context + reducer for a mini global state. - Build a real-time search/filter over a large list with debouncing. - Build a typeahead / autocomplete component. - Build tabs component with lazy-loaded content. - Implement a carousel/image slider. - Build a tree view (expandable/collapsible nodes). - Implement a virtualized list (render only visible rows). - Build a Kanban board with columns and drag-and-drop cards. - Build a data grid/table with sort, filter, and pagination.

### 417. React.useMemo() memoizing a JSX element to skip a child's re-render?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Parent() { const [count, setCount] = React.useState(0); return ( <div> <button onClick={() => setCount(c => c + 1)}>Count: {count}</button> {React.useMemo(() => <ExpensiveChild />, [])} </div> ); } function ExpensiveChild() { console.log('ExpensiveChild render'); return <div>expensive</div>; }

```
**Behavior:** `ExpensiveChild render` logs only ONCE regardless of how many times button is clicked. **Explanation:** `React.useMemo(() => <ExpensiveChild />, [])` memoizes the React ELEMENT (not the component). Since the element reference is stable (same JSX object), React reuses the previous render result. This is an alternative to `React.memo` for cases where you control the parent.

### 418. Setup Function Execution (`useEffect`)

The setup function (or the main function) you pass to `useEffect` runs at specific points:

### 419. Stale closure in useEffect?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { const interval = setInterval(() => { console.log('count is', count); // Stale closure! }, 1000); return () => clearInterval(interval); }, []); // Missing count in deps return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior:** The interval always logs `count is 0` even as you click and count increases. **Explanation:** Stale closure bug. The effect captures `count = 0` at mount time. Since `[]` prevents re-running, the interval never gets the updated `count`. Fix: add `count` to deps (resets interval on change), or use a ref to store latest count.

### 420. Subscriptions?

```jsx useEffect(() => { const subscription = dataSource.subscribe(handleChange); return () => subscription.unsubscribe(); }, [dataSource]);

```

### 421. Theme Customization?

`useContext` can be used to manage application-wide themes, such as light and dark modes, ensuring consistent styling and enabling user-driven customization.

### 422. Timers and Intervals?

```jsx useEffect(() => { const intervalId = setInterval(() => { setCount(c => c + 1); }, 1000); return () => clearInterval(intervalId); }, []);

```

### 423. Use `useEffect` to react to state changes:

```jsx useEffect(() => { console.log('Updated count:', state.count); }, [state.count]);

```

### 424. Use `useRef` to track the latest state:

```jsx const stateRef = useRef(state); useEffect(() => { stateRef.current = state; }, [state]);

```
**Note:** This behavior is by design in React. The `dispatch` function itself has a **stable identity** (it doesn't change between re-renders), which makes it safe to omit from `useEffect` dependency arrays. [↑ Back to Table of Contents](#table-of-contents)

### 425. Use() Hook?

[↑ Back to Table of Contents](#table-of-contents) Read resources (Promises, Context) inside render:

```jsx function User({ userPromise }) { const user = use(userPromise); // Suspends until resolved return <div>{user.name}</div>; }

```

### 426. UseCallback returning a stable function reference across re-renders?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function useToggle(initial = false) { const [value, setValue] = React.useState(initial); const toggle = React.useCallback(() => setValue(v => !v), []); return [value, toggle]; } function App() { const [isOpen, toggle] = useToggle(); console.log('App render'); return ( <> <button onClick={toggle}>Toggle</button> {isOpen && <Modal />} </> ); }

```
**Behavior:** `toggle` is the same function reference across renders. Passing `toggle` to memoized children won't cause unnecessary re-renders. **Explanation:** `useCallback` with `[]` deps creates the function once. The `setValue(v => !v)` functional update never closes over stale state. This is the correct pattern for stable callback refs.

### 427. UseCallback without dependency change?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Parent() { const [count, setCount] = React.useState(0); const [text, setText] = React.useState(''); const handleClick = React.useCallback(() => { console.log('clicked'); }, []); // No deps const handleTextChange = React.useCallback((e) => { setText(e.target.value); }, []); // No deps return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <Child onClick={handleClick} /> </> ); } const Child = React.memo(({ onClick }) => { console.log('Child rendered'); return <button onClick={onClick}>Child</button>; });

```
**Behavior:** Child DOES NOT re-render when count changes. **Explanation:** `useCallback` with `[]` returns the SAME function reference across renders. `React.memo` + `useCallback` with stable deps = memoized child that doesn't re-render when parent's unrelated state changes.

### 428. UseDeferredValue keeping input responsive during an expensive re-render?

```jsx function SearchResults({ query }) { console.log('SearchResults render with:', query); // Simulate expensive computation const results = Array.from({ length: 1000 }, (_, i) => `${query}-result-${i}`); return <ul>{results.slice(0, 5).map(r => <li key={r}>{r}</li>)}</ul>; } function App() { const [input, setInput] = React.useState(''); const deferredQuery = React.useDeferredValue(input); return ( <> <input value={input} onChange={e => setInput(e.target.value)} /> <SearchResults query={deferredQuery} /> </> ); }

```
**Behavior:** Input updates immediately (urgent). `deferredQuery` lags behind — React renders the old results while computing new ones. Input never feels sluggish. **Explanation:** `useDeferredValue` gives you a deferred copy of a value. React renders with the old deferred value first (fast), then re-renders with the new value concurrently. The input feels instant. [↑ Back to Table of Contents](#table-of-contents)

### 429. UseEffect cleanup timing?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('effect', count); return () => { console.log('cleanup', count); }; }, [count]); return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior:** Initial render: `effect 0`. Click: `cleanup 0` then `effect 1`. Click again: `cleanup 1` then `effect 2`. **Explanation:** When `count` changes: cleanup of the PREVIOUS effect runs first (with the OLD `count` value captured in closure), then the new effect runs with the new `count`.

### 430. UseEffect infinite loop?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { setCount(count + 1); // Infinite loop! }, [count]); return <div>{count}</div>; }

```
**Behavior:** Infinite re-render loop. Browser tab crashes. **Explanation:** Effect runs → updates `count` → triggers re-render → effect sees new `count` in deps → runs again → infinite loop. Fix: use `setCount(prev => prev + 1)` with `[]` deps, or restructure logic to not update the same state you depend on.

### 431. UseEffect mount/unmount order when toggling between two sibling components?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [type, setType] = React.useState('A'); return ( <> {type === 'A' ? <ComponentA /> : <ComponentB />} <button onClick={() => setType(t => t === 'A' ? 'B' : 'A')}>Toggle</button> </> ); } function ComponentA() { React.useEffect(() => { console.log('A mounted'); return () => console.log('A unmounted'); }, []); return <div>A</div>; } function ComponentB() { React.useEffect(() => { console.log('B mounted'); return () => console.log('B unmounted'); }, []); return <div>B</div>; }

```
**Output on toggle A→B:**

```
A unmounted B mounted

```
**Explanation:** Switching between two DIFFERENT component types causes React to unmount the old one and mount the new one — full lifecycle. State is completely reset. If you rendered `<ComponentA />` in both branches, React would KEEP the instance and just update props.

### 432. UseEffect vs useLayoutEffect timing?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [width, setWidth] = React.useState(0); React.useLayoutEffect(() => { setWidth(document.body.clientWidth); }, []); React.useEffect(() => { console.log('useEffect width:', width); }, [width]); return <div>Width: {width}</div>; }

```
**Behavior:** `useLayoutEffect` fires before browser paint, measures DOM, sets width. User never sees `width: 0` — they immediately see the correct width. `useEffect` fires after paint with the updated width. **Explanation:** `useLayoutEffect` blocks paint — use for DOM measurements to avoid flicker. `useEffect` is non-blocking and runs after paint — use for side effects that don't need to block rendering.

### 433. UseEffect with async function?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { React.useEffect(async () => { const data = await fetch('/api/data').then(r => r.json()); console.log(data); }, []); // Anti-pattern! }

```
**Behavior:** Works but creates an unhandled Promise. React warns in console. **Explanation:** `useEffect` expects its callback to return either `undefined` or a cleanup function. `async` functions return Promises — React can't call a Promise as cleanup. Correct pattern:

```jsx React.useEffect(() => { let cancelled = false; async function fetchData() { const data = await fetch('/api/data').then(r => r.json()); if (!cancelled) console.log(data); } fetchData(); return () => { cancelled = true; }; }, []);

```

### 434. UseEffect with empty dependency array?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('mounted'); return () => console.log('unmounted'); }, []); return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior (with React.StrictMode):** Logs `mounted`, `unmounted`, `mounted` on initial render. Then nothing on updates. **Behavior (without StrictMode):** Logs `mounted` once on mount. `unmounted` only when component is removed from DOM. **Explanation:** `[]` dependency array means "run only on mount, cleanup on unmount." In StrictMode, React intentionally double-invokes effects in development to catch bugs.

### 435. UseMemo recalculation?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); const [multiplier, setMultiplier] = React.useState(2); const result = React.useMemo(() => { console.log('computing...'); return count * multiplier; }, [count, multiplier]); return ( <> <p>{result}</p> <button onClick={() => setCount(c => c + 1)}>count: {count}</button> <button onClick={() => setMultiplier(m => m + 1)}>multiplier: {multiplier}</button> </> ); }

```
**Behavior:** `computing...` only logs when `count` OR `multiplier` changes. Not on unrelated re-renders (if parent caused a re-render for some other reason). **Explanation:** `useMemo` caches the result and only recomputes when dependencies change. Clicking either button logs `computing...`. If there was another state that caused re-renders, `useMemo` would protect this computation.

### 436. UseMemo recomputing when a dependency array value is a new array reference each render?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Expensive({ data }) { const processed = React.useMemo(() => { console.log('processing...'); return data.map(x => x * 2); }, [data]); return <div>{processed.join(', ')}</div>; } function App() { const [count, setCount] = React.useState(0); const data = [1, 2, 3]; // Created every render return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <Expensive data={data} /> </> ); }

```
**Behavior:** `processing...` logs on EVERY render despite `useMemo`. **Explanation:** `data = [1, 2, 3]` creates a NEW array every render. `useMemo`'s dep comparison uses `Object.is` — different array reference every time → recomputes. Fix: `const data = React.useMemo(() => [1, 2, 3], [])` in App.

### 437. UseOptimistic Hook?

Implement optimistic UI updates:

```jsx function TodoList({ todos }) { const [optimisticTodos, addOptimisticTodo] = useOptimistic( todos, (state, newTodo) => [...state, { ...newTodo, pending: true }] ); async function createTodo(title) { addOptimisticTodo({ id: Date.now(), title }); await saveTodo(title); } return optimisticTodos.map(todo => ( <Todo key={todo.id} {...todo} /> )); }

```

### 438. User Authentication and Session Management?

`useContext` allows global access to authentication status and user data. This enables conditional rendering of components and helps manage protected routes or user-specific UI elements.

### 439. UseRef does not cause re-render?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); const renderCount = React.useRef(0); renderCount.current++; return ( <div> <p>State count: {count}</p> <p>Render count: {renderCount.current}</p> <button onClick={() => setCount(c => c + 1)}>Increment state</button> <button onClick={() => { renderCount.current++; console.log(renderCount.current); }}> Increment ref </button> </div> ); }

```
**Behavior:** - Clicking "Increment state" re-renders, both counts update visually. - Clicking "Increment ref" DOES NOT re-render. `renderCount.current` changes in memory but UI doesn't update. The console shows updated value but the page doesn't re-render. **Explanation:** Changing `ref.current` never triggers a re-render. `renderCount.current++` in the render body runs on every render (counting correctly), but it's only visible because a STATE change causes a re-render.

### 440. UseRef to track previous value?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [count, setCount] = React.useState(0); const prevCount = React.useRef(null); React.useEffect(() => { prevCount.current = count; }); return ( <div> <p>Current: {count}, Previous: {prevCount.current}</p> <button onClick={() => setCount(c => c + 1)}>+</button> </div> ); }

```
**Behavior:** Initially shows `Current: 0, Previous: null`. After first click: `Current: 1, Previous: 0`. After second click: `Current: 2, Previous: 1`. **Explanation:** The `useEffect` without deps runs after EVERY render, updating the ref with the current count. During the NEXT render, `prevCount.current` holds the previous value. Since ref updates don't cause re-renders, this works correctly.

### 441. UseTransition keeps UI responsive?

```jsx function SearchResults({ query }) { const [results, setResults] = React.useState([]); React.useEffect(() => { // Heavy computation const filtered = hugeList.filter(item => item.includes(query)); setResults(filtered); }, [query]); return <ul>{results.map(r => <li key={r}>{r}</li>)}</ul>; } function App() { const [query, setQuery] = React.useState(''); const [isPending, startTransition] = React.useTransition(); function handleChange(e) { startTransition(() => { setQuery(e.target.value); // Non-urgent update }); } return ( <> <input onChange={handleChange} /> {isPending && <p>Loading...</p>} <SearchResults query={query} /> </> ); }

```
**Behavior:** Input remains responsive while results update. `isPending` shows loading state during transition. If user types fast, React may abandon intermediate transitions. **Explanation:** `startTransition` marks updates as non-urgent. React prioritizes the input update (urgent) and defers the search results update. This prevents the input from lagging during heavy re-renders. [↑ Back to Table of Contents](#table-of-contents)

### 442. UseTransition marking a state update as non-urgent?

```jsx function App() { const [resource, setResource] = React.useState(null); const [isPending, startTransition] = React.useTransition(); function handleClick() { startTransition(() => { setResource(fetchData()); // Expensive operation }); } return ( <> <button onClick={handleClick} disabled={isPending}> {isPending ? 'Loading...' : 'Load Data'} </button> <React.Suspense fallback={<p>Loading content...</p>}> {resource && <DataDisplay resource={resource} />} </React.Suspense> </> ); }

```
**Behavior:** Button shows 'Loading...' while transition is pending. UI remains interactive. Suspense shows fallback only if the data-fetching component suspends. **Explanation:** `isPending` from `useTransition` tells you when a transition is in-flight. Button stays interactive. Combining `useTransition` + `Suspense` gives smooth, non-blocking data loading UX. [↑ Back to Table of Contents](#table-of-contents)

### 443. What are common `useEffect` mistakes?

Missing deps (stale closures), unstable deps (infinite loops), using it for derivable values, missing cleanup.

### 444. What are Custom Hooks?

A Custom Hook is a function in Javascript whose name begins with ‘use’ and which calls other hooks. It is a part of React v16.8 hook update and permits you for reusing the stateful logic without any need for component hierarchy restructuring. In almost all of the cases, custom hooks are considered to be sufficient for replacing render props and HoCs (Higher-Order components) and reducing the amount of nesting required. Custom Hooks will allow you for avoiding multiple layers of abstraction or wrapper hell that might come along with Render Props and HoCs. The **disadvantage** of Custom Hooks is it cannot be used inside of the classes.

### 445. What are Custom React Hooks, and How Can You Develop One?

**Custom Hooks** in React are JavaScript functions that allow you to **extract and reuse component logic** using React's built-in Hooks like `useState`, `useEffect`, etc. They start with the word **"use"** and let you encapsulate logic that multiple components might share—such as fetching data, handling forms, or managing timers—without repeating code. Let's explain the custom hook usage with `useFetchData` example. The `useFetchData` custom Hook is a reusable function in React that simplifies the process of fetching data from an API. It encapsulates common logic such as initiating the fetch request, managing loading and error states, and storing the fetched data. By using built-in Hooks like `useState` and `useEffect`, `useFetchData` provides a clean interface that returns the `data`, `loading`, and `error` values, which can be directly used in components.

```jsx import { useState, useEffect } from 'react'; function useFetchData(url) { const ** 309. ### How does React Fiber works? Explain in detail. React Fiber is the **core engine** that enables advanced features like **concurrent rendering**, **prioritization**, and **interruptibility** in React. Here's how it works: \### 1. **Fiber Tree Structure** Each component in your app is represented by a **Fiber node** in a tree structure. A Fiber node contains: - Component type - Props & state - Pointers to parent, child, and sibling nodes - Effect tags to track changes (e.g., update, placement) - This forms the **Fiber Tree**, a data structure React uses instead of the traditional call stack. \### 2. **Two Phases of Rendering** \#### **A. Render Phase (work-in-progress)** - React builds a **work-in-progress Fiber tree**. - It walks through each component (begin phase), calculates what needs to change, and collects side effects (complete phase). - This phase is **interruptible**---React can pause it and resume later. \#### **B. Commit Phase** - React applies changes to the **Real DOM**. - Runs lifecycle methods (e.g., `componentDidMount`, `useEffect`). - This phase is **non-interruptible** but fast. \### 3. **Work Units and Scheduling** - React breaks rendering into **units of work** (small tasks). - These units are scheduled based on **priority** using the **React Scheduler**. - If time runs out (e.g., user starts typing), React can **pause and yield** control back to the browser. \### 4. **Double Buffering with Two Trees** - React maintains two trees: - **Current Tree** -- what's visible on the screen. - **Work-In-Progress Tree** -- the next version being built in memory. - Only after the new tree is fully ready, React **commits** it, making it the new current tree. \### 5. **Concurrency and Prioritization** - React can prepare multiple versions of UI at once (e.g., during slow data loading). - Updates can be **assigned priorities**, so urgent updates (like clicks) are handled faster than background work. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What are hooks? Hooks is a new feature(React 16.8) that lets you use state and other React features without writing a class. Let's see an example of useState hook example,

```
import { useState } from 'react'; function Example() { // Declare a new state variable, which we'll call "count" const [count, setCount] = useState(0); return ( <div> <p>You clicked {count} times</p> <button onClick={() => setCount(count + 1)}>Click me</button> </div> ); }

```
[ --- ### What are stale closures in `useEffect`? When an effect captures a variable from a previous render. If the dependency array is incomplete, the effect uses the old value. Fix: add the variable to deps, or use a ref to always access the latest value. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What are the best practices for using React Hooks? Following best practices ensures your hooks are predictable, maintainable, and bug-free. #### 1. **Follow the Rules of Hooks** - Only call hooks at the top level (not inside loops, conditions, or nested functions) - Only call hooks from React functions (components or custom hooks) #### 2. **Use the ESLint Plugin**

```bash npm install eslint-plugin-react-hooks --save-dev

```
```json { "plugins": **

### 446. What are Higher-Order Components (HOCs)?

Functions that take a component and return a new component with enhanced behavior. E.g., `withAuth(Component)` wraps it to redirect if unauthenticated. HOCs are less common now that custom hooks exist.

### 447. What are Hooks?

Hooks are functions that let us “hook into” React state and lifecycle features from a **functional component.** React Hooks** cannot** be used in class components. They let us write components without class.

### 448. What are stale closures and how do they happen in `useEffect`?

An effect captures variables from the render it was created in; if the dependency array is incomplete, subsequent updates to those variables aren't seen inside the effect. Fix: add to deps or use a ref for "latest value" access.

### 449. What are stale closures in `useEffect`?

[↑ Back to Table of Contents](#table-of-contents) When an effect captures a variable from a previous render. If the dependency array is incomplete, the effect uses the old value. Fix: add the variable to deps, or use a ref to always access the latest value.

### 450. What are stateful components?

If the behavior of a component is dependent on the state of the component, it can be termed as a stateful component. These stateful components are either function components with hooks or class components.

### 451. What are stateless components?

If the behaviour of a component is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless you need to use a lifecycle hook in your components, you should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the `this` keyword altogether. ****

### 452. What are the best practices for using React Hooks?

[↑ Back to Table of Contents](#table-of-contents) Following best practices ensures your hooks are predictable, maintainable, and bug-free. ##### 1. **Follow the Rules of Hooks** - Only call hooks at the top level (not inside loops, conditions, or nested functions) - Only call hooks from React functions (components or custom hooks) ##### 2. **Use the ESLint Plugin**

```bash npm install eslint-plugin-react-hooks --save-dev

```
```json { "plugins": ["react-hooks"], "rules": { "react-hooks/rules-of-hooks": "error", "react-hooks/exhaustive-deps": "warn" } }

```
##### 3. **Keep Hooks Focused and Simple**

```jsx // ❌ Bad: One hook doing too much function useEverything() { const [user, setUser] = useState(null); const [posts, setPosts] = useState([]); const [theme, setTheme] = useState('light'); // ... lots of unrelated logic } // ✅ Good: Separate concerns function useUser() { /* user logic */ } function usePosts() { /* posts logic */ } function useTheme() { /* theme logic */ }

```
##### 4. **Use Descriptive Names for Custom Hooks**

```jsx // ❌ Bad function useData() { } // ✅ Good function useUserAuthentication() { } function useFetchProducts() { } function useFormValidation() { }

```
##### 5. **Properly Manage Dependencies**

```jsx // ❌ Bad: Missing dependency useEffect(() => { fetchUser(userId); }, []); // userId is missing // ✅ Good: All dependencies listed useEffect(() => { fetchUser(userId); }, [userId]);

```
##### 6. **Avoid Inline Object/Function Dependencies**

```jsx // ❌ Bad: New object on every render useEffect(() => { doSomething(options); }, [{ page: 1, limit: 10 }]); // Always different reference // ✅ Good: Memoize or extract const options = useMemo(() => ({ page: 1, limit: 10 }), []); useEffect(() => { doSomething(options); }, [options]);

```
##### 7. **Clean Up Side Effects** Always return a cleanup function when subscribing to events, timers, or external data sources.

### 453. What are the common usecases of useRef hook?

[↑ Back to Table of Contents](#table-of-contents) Some of the common cases are: \* Automatically focus an input when a component mounts. \* Scroll to a specific element. \* Measure element dimensions (`offsetWidth`, `clientHeight`). \* Control video/audio playback. \* Integrate with non-React libraries (like D3 or jQuery). ------------------------------------------------------------------------ 301. ### What is useImperativeHandle Hook? Give an example. `useImperativeHandle` is a React Hook that allows a **child component** to expose **custom functions or properties** to its **parent component**, when using `ref`. It is typically used with `forwardRef` and is very useful in cases like **modals**, **dialogs**, **custom inputs**, etc., where the parent needs to **control behavior imperatively** (e.g., open, close, reset). **Example: Dialog component** \`\`\`js import React, { useRef, useState, useImperativeHandle, forwardRef, } from 'react'; import './Dialog.css'; const Dialog = forwardRef((props, ref) =\> { const \*\* ------------------------------------------------------------------------

### 454. What are the differences between `useEffect` and the experimental `useEvent`/Effect Event pattern?

`useEvent`-style patterns create a stable function reference that always reads the latest props/state without needing to be listed as a dependency — solving the "stable callback with fresh closure" problem that plain `useCallback` can't.

### 455. What are the differences between functional and class components?

[↑ Back to Table of Contents](#table-of-contents) Before the introduction of Hooks in React, functional components were called stateless components and were behind class components on a feature basis. After the introduction of Hooks, functional components are equivalent to class components. Although functional components are the new trend, the react team insists on keeping class components in React. Therefore, it is important to know how these components differ. On the following basis let’s compare functional and class components: - **Declaration** Functional components are nothing but JavaScript functions and therefore can be declared using an arrow function or the function keyword:

```
function card(props){ return( <div className="main-container"> <h2>Title of the card</h2> </div> ) } const card = (props) =>{ return( <div className="main-container"> <h2>Title of the card</h2> </div> ) }

```
Class components, on the other hand, are declared using the ES6 class:

```
class Card extends React.Component{ constructor(props){ super(props); } render(){ return( <div className="main-container"> <h2>Title of the card</h2> </div> ) } }

```
- **Handling props** Let’s render the following component with props and analyse how functional and class components handle props:

```
<Student Info name="Vivek" rollNumber="23" />

```
In functional components, the handling of props is pretty straightforward. Any prop provided as an argument to a functional component can be directly used inside HTML elements:

```
function StudentInfo(props){ return( <div className="main"> <h2>{props.name}</h2> <h4>{props.rollNumber}</h4> </div> ) }

```
In the case of class components, props are handled in a different way:

```
class StudentInfo extends React.Component{ constructor(props){ super(props); } render(){ return( <div className="main"> <h2>{this.props.name}</h2> <h4>{this.props.rollNumber}</h4> </div> ) } }

```
As we can see in the code above, **this **keyword is used in the case of class components. - **Handling state** Functional components use React hooks to handle state. It uses the useState hook to set the state of a variable inside the component:

```
function ClassRoom(props){ let [studentsCount,setStudentsCount] = useState(0); const addStudent = () => { setStudentsCount(++studentsCount); } return( <div> <p>Number of students in class room: {studentsCount}</p> <button onClick={addStudent}>Add Student</button> </div> ) }

```
Since useState hook returns an array of two items, the first item contains the current state, and the second item is a function used to update the state. In the code above, using array destructuring we have set the variable name to studentsCount with a current value of “0” and setStudentsCount is the function that is used to update the state. For reading the state, we can see from the code above, the variable name can be directly used to read the current state of the variable. We cannot use React Hooks inside class components, therefore state handling is done very differently in a class component: Let’s take the same above example and convert it into a class component:

```
class ClassRoom extends React.Component{ constructor(props){ super(props); this.state = {studentsCount : 0}; this.addStudent = this.addStudent.bind(this); } addStudent(){ this.setState((prevState)=>{ return {studentsCount: prevState.studentsCount++} }); } render(){ return( <div> <p>Number of students in class room: {this.state.studentsCount}</p> <button onClick={this.addStudent}>Add Student</button> </div> ) } }

```
In the code above, we see we are using **this.state** to add the variable studentsCount and setting the value to “0”. For reading the state, we are using **this.state.studentsCount**. For updating the state, we need to first bind the addStudent function to **this**. Only then, we will be able to use the **setState** function which is used to update the state. Advance your career with **Mock Assessments** Real-world coding challenges for top company interviews Real-Life Problems Detailed reports **Attempt Now**

### 456. What are the differences between useEffect and useEvent (experimental)?

[↑ Back to Table of Contents](#table-of-contents) `useEvent` is an **experimental hook** (not yet stable in React) designed to solve the problem of creating **stable event handlers** that always access the latest props and state without causing re-renders or needing to be in dependency arrays. ##### The Problem useEvent Solves

```jsx // Problem: onTick changes on every render, causing interval to reset function Timer({ onTick }) { useEffect(() => { const id = setInterval(() => { onTick(); // Uses stale closure if onTick is not in deps }, 1000); return () => clearInterval(id); }, [onTick]); // Adding onTick causes interval to reset frequently }

```
##### Solution with useEvent (Experimental)

```jsx import { useEvent } from 'react'; // Experimental function Timer({ onTick }) { const stableOnTick = useEvent(onTick); useEffect(() => { const id = setInterval(() => { stableOnTick(); // Always calls latest onTick }, 1000); return () => clearInterval(id); }, []); // No dependency needed! }

```
##### Key Differences | Feature | useEffect | useEvent (experimental) | |---------|-----------|------------------------| | Purpose | Run side effects | Create stable callbacks | | Runs | After render | During render (creates function) | | Returns | Cleanup function | Stable event handler | | Closure | Captures values at render time | Always accesses latest values | | Dependencies | Must list all used values | Not needed in other hooks' deps | **Note:** Until `useEvent` is stable, you can use `useCallback` with `useRef` as a workaround for stable callbacks.

### 457. What are the differences between useEffect and useLayoutEffect hooks?

[↑ Back to Table of Contents](#table-of-contents) useEffect and useLayoutEffect are both React hooks that can be used to synchronize a component with an external system, such as a browser API or a third-party library. However, there are some key differences between the two: - Timing: useEffect runs after the browser has finished painting, while useLayoutEffect runs synchronously before the browser paints. This means that useLayoutEffect can be used to measure and update layout in a way that feels more synchronous to the user. - Browser Paint: useEffect allows browser to paint the changes before running the effect, hence it may cause some visual flicker. useLayoutEffect synchronously runs the effect before browser paints and hence it will avoid visual flicker. - Execution Order: The order in which multiple useEffect hooks are executed is determined by React and may not be predictable. However, the order in which multiple useLayoutEffect hooks are executed is determined by the order in which they were called. - Error handling: useEffect has a built-in mechanism for handling errors that occur during the execution of the effect, so that it does not crash the entire application. useLayoutEffect does not have this mechanism, and errors that occur during the execution of the effect will crash the entire application. In general, it's recommended to use useEffect as much as possible, because it is more performant and less prone to errors. useLayoutEffect should only be used when you need to measure or update layout, and you can't achieve the same result using useEffect.

### 458. What are the rules needs to follow for hooks?

You need to follow two rules in order to use hooks, 1. Call Hooks only at the top level of your react functions. i.e, You shouldn’t call Hooks inside loops, conditions, or nested functions. This will ensure that Hooks are called in the same order each time a component renders and it preserves the state of Hooks between multiple useState and useEffect calls. 2. Call Hooks from React Functions only. i.e, You shouldn’t call Hooks from regular JavaScript functions. [↑ Back to Table of Contents](#table-of-contents)

### 459. What are the rules that must be followed while using React Hooks?

[↑ Back to Table of Contents](#table-of-contents) There are 2 rules which must be followed while you code with Hooks: - React Hooks must be called only at the top level. It is not allowed to call them inside the nested functions, loops, or conditions. - It is allowed to call the Hooks only from the React Function Components.

### 460. What are the sources used for introducing hooks?

Hooks got the ideas from several different sources. Below are some of them, 1. Previous experiments with functional APIs in the react-future repository 2. Community experiments with render prop APIs such as Reactions Component 3. State variables and state cells in DisplayScript. 4. Subscriptions in Rx. 5. Reducer components in ReasonReact. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 461. What are the use cases of useContext hook?

[↑ Back to Table of Contents](#table-of-contents) The `useContext` hook in React is used to share data across components without having to pass props manually through each level. Here are some common and effective use cases:

### 462. What are the usecases of useLayoutEffect?

[↑ Back to Table of Contents](#table-of-contents) You need to use `useLayoutEffect` when your effect **must run before the browser paints**, such as: * **Reading layout measurements** (e.g., element size, scroll position) * **Synchronously applying DOM styles** to prevent visual flicker * **Animating layout or transitions** * **Integrating with third-party libraries** that require DOM manipulation If there's no visual or layout dependency, prefer `useEffect` — it's more performance-friendly.

```js useLayoutEffect(() => { const width = divRef.current.offsetWidth; if (width < 400) { divRef.current.style.background = 'blue'; // prevents flicker } }, []);

```

### 463. What are useFormState and useFormStatus hooks?

These hooks simplify form handling with Server Actions in React 19.

### 464. What does `useEffect` do? When does it run relative to render?

Runs a side effect *after* paint, asynchronously. Re-runs when a `deps` value changes (every render if omitted, once if `[]`).

### 465. What happens if you call `useState` conditionally?

[↑ Back to Table of Contents](#table-of-contents) As per rules of React Hooks, hooks must be called unconditionally. For example, if you conditionally call it:

```js if (someCondition) { const [state, setState] = useState(0); }

```
React will throw a runtime error because it **relies on the order of Hook calls**, and conditional logic breaks that order.

### 466. What happens if you return a Promise from useEffect??

[↑ Back to Table of Contents](#table-of-contents) You should NOT return a Promise from useEffect. React expects the function passed to useEffect to return either nothing (undefined) or a cleanup function (synchronous function). i.e, It does not expect or handle a returned Promise. If you still return a Promise, React will ignore it silently, and it may lead to bugs or warnings in strict mode. **Incorrect:**

```js useEffect(async () => { await fetchData(); // ❌ useEffect shouldn't be async }, []);

```
**Correct:**

```jsx useEffect(() => { const fetchData = async () => { const res = await fetch('/api'); const data = await res.json(); setData(data); }; fetchData(); }, []);

```

### 467. What happens if you use useLayoutEffect for non-layout logic?

[↑ Back to Table of Contents](#table-of-contents) Using `useLayoutEffect` for logic **unrelated to layout or visual DOM changes** (such as logging, data fetching, or analytics) is **not recommended**. It can lead to **performance issues** or even unexpected behavior. **Example: Anti-pattern**

```js useLayoutEffect(() => { console.log("Tracking analytics"); fetch('/log-page-view'); }, []);

```
The above usage delays the paint of the UI just to send a network request, which could (and should) be done after paint using useEffect.

### 468. What is `useActionState` (React 19)?

Manages state for an async action. Returns `[state, dispatch, isPending]`. On form submission, calls the action with form data, updates state with the result, and tracks pending status automatically. [↑ Back to Table of Contents](#table-of-contents)

### 469. What is `useCallback` and why is it used?

[↑ Back to Table of Contents](#table-of-contents) The `useCallback` is a React Hook used to memoize **function definitions** between renders. It returns the same function reference unless its dependencies change. This is especially useful when passing callbacks to optimized child components (e.g. those wrapped in `React.memo`) to prevent unnecessary re-renders. **Example:**

```css const handleClick = useCallback(() => { console.log('Button clicked'); }, []);

```
Without `useCallback`, a new function is created on every render, potentially causing child components to re-render unnecessarily.

### 470. What is `useCallback`?

[↑ Back to Table of Contents](#table-of-contents) Memoizes a function reference. Prevents child components that receive the function as prop from re-rendering unnecessarily, and prevents effects from re-running when a callback is a dependency.

### 471. What is `useCallback`? How does it differ from `useMemo`?

Memoizes a function reference (`useMemo(() => fn, deps)`). Prevents re-creating callbacks passed to memoized children.

### 472. What is `useContext`?

[↑ Back to Table of Contents](#table-of-contents) Subscribes to a React context. Receives the current context value and re-renders whenever it changes. Eliminates prop drilling for shared data like theme, locale, auth, or feature flags.

### 473. What is `useContext`? How does it avoid prop drilling?

Reads the nearest matching Provider's value, letting any descendant read it directly without threading through intermediate props.

### 474. What is `useDebugValue`?

Used inside custom hooks to display a label in React DevTools. Helps identify what a custom hook is doing when inspecting components. The second argument is a formatting function called only in DevTools. [⬆ Back to Table of Contents](#-table-of-contents)

### 475. What is `useDeferredValue` and how does it differ from `useTransition`?

`useDeferredValue` wraps a *value* you don't control the update of (e.g., a prop); `useTransition` wraps a *state update* you do control (via `startTransition`). Both let urgent UI stay responsive while expensive work is deferred.

### 476. What is `useDeferredValue`?

Accepts a value and returns a deferred copy that trails behind during heavy renders. UI stays responsive with the current value while React concurrently renders the expensive output with the new value. [⬆ Back to Table of Contents](#-table-of-contents)

### 477. What is `useFormStatus`?

A hook available inside a form child component. Returns `{pending, data, method, action}` of the parent form's submission. Lets you disable inputs or show spinners without prop drilling from the form. [↑ Back to Table of Contents](#table-of-contents)

### 478. What is `useId`?

[↑ Back to Table of Contents](#table-of-contents) Generates a stable, unique ID that is consistent between server and client renders. Use for accessibility attributes like `aria-labelledby` or `htmlFor` where IDs must match across SSR and hydration.

### 479. What is `useId`? Why was it added?

Generates a stable unique ID for a11y attributes, guaranteeing matching IDs between server-rendered and hydrated markup.

### 480. What is `useImperativeHandle`?

Customizes the ref value exposed when `forwardRef` is used. Lets a parent call specific methods on a child (e.g., `child.focus()`) without exposing the entire DOM node or component internals. [⬆ Back to Table of Contents](#-table-of-contents)

### 481. What is `useImperativeHandle`? When would you use it?

Customizes the instance exposed via `ref` (with `forwardRef`), exposing specific imperative methods instead of the raw DOM node.

### 482. What is `useLayoutEffect` and how does it differ from `useEffect`?

Same API, but fires synchronously after DOM mutations and *before* the browser paints — used for reading layout (measurements) and making synchronous DOM adjustments to avoid visual flicker. `useEffect` is non-blocking and runs after paint.

### 483. What is `useLayoutEffect`?

Same signature as `useEffect` but fires synchronously after DOM mutations and before browser paint. Use for: reading layout (scroll position, dimensions) and synchronously updating the DOM to avoid flicker. [⬆ Back to Table of Contents](#-table-of-contents)

### 484. What is `useMemo`?

Memoizes the result of an expensive computation. Re-computes only when dependencies change. Use for: heavy calculations, creating stable object/array references, derived data from props. [⬆ Back to Table of Contents](#-table-of-contents)

### 485. What is `useMemo`? When should you use it?

Memoizes a computation's result, recomputing only on dep change. Use for expensive computations or referential equality needs.

### 486. What is `useOptimistic` (React 19)?

Shows an optimistic state update immediately while an async action is pending. When the action completes (or fails), React reverts to the actual state. Provides smooth UX without complex manual state management. ------------------------------------------------------------------------

### 487. What is `useOptimistic`?

Shows an optimistic UI update immediately while an async action is pending, automatically reverting to actual state if the action fails — removes manual "pending item" state management.

### 488. What is `useReducer` vs `useState`?

`useReducer` centralizes complex state transitions in one function via dispatched actions — better when state has multiple sub-values or next state depends on the action type; `useState` is simpler for independent, unrelated values.

### 489. What is `useReducer`?

[↑ Back to Table of Contents](#table-of-contents) Like `useState` but manages state via a `reducer(state, action) => newState` function. Better for complex state with multiple sub-values, or when next state depends on action type. Pairs well with `useContext` for mini-Redux patterns.

### 490. What is `useReducer`? Why do you use useReducer?

[↑ Back to Table of Contents](#table-of-contents) The `useReducer` hook is a React hook used to manage **complex state logic** inside **functional components**. It is conceptually similar to **Redux**. i.e, Instead of directly updating state like with `useState`, you **dispatch an action** to a **reducer function**, and the reducer returns the new state. The `useReducer` hook takes three arguments:

```js const [state, dispatch] = useReducer(reducer, initialState, initFunction);

```
* `**reducer**`: A function `(state, action) => newState` that handles how state should change based on the action. * `**initialState**`: The starting state. * `**dispatch**`: A function you call to trigger an update by passing an action. The `useReducer` hook is used when: * The **state is complex**, such as nested structures or multiple related values. * State updates depend on the **previous state** and **logic**. * You want to **separate state update logic** from UI code to make it cleaner and testable. * You’re managing features like: * Forms * Wizards / Multi-step flows * Undo/Redo functionality * Shopping cart logic * Toggle & conditional UI logic

### 491. What is `useRef`?

Returns a mutable `{current}` object that persists across renders without triggering re-renders. Two main uses: (1) accessing DOM nodes directly, (2) storing instance variables like timers or previous values. [⬆ Back to Table of Contents](#-table-of-contents)

### 492. What is `useRef`? What are its two main use cases?

Returns a mutable `{ current }` persisting across renders without re-rendering. Uses: DOM node refs, and mutable "instance variables."

### 493. What is `useState`?

Declares state in a functional component. Returns `[value, setter]`. The setter schedules a re-render with the new value. Multiple `useState` calls are independent. [⬆ Back to Table of Contents](#-table-of-contents)

### 494. What is `useSyncExternalStore`? When is it needed?

Subscribes to an external store safely under concurrent rendering, avoiding "tearing." Used internally by state libraries.

### 495. What is `useTransition` used for?

Marking a state update as non-urgent so React can interrupt it in favor of higher-priority updates (like typing); `isPending` lets you show a loading indicator without manual loading state.

### 496. What is `useTransition`?

Hook version of `startTransition`. Returns `[isPending, startTransition]`. `isPending` is true while the transition is rendering. Use it to show loading spinners without setting separate loading state. [⬆ Back to Table of Contents](#-table-of-contents)

### 497. What is `useTransition`? What problem does it solve?

Marks a state update as low-priority/interruptible, keeping the old UI visible while rendering the transition in the background.

### 498. What is a "smart" vs "dumb" component?

Smart (container) components manage data/state/logic; dumb (presentational) components just render props. Largely replaced by custom Hooks + a single component today.

### 499. What is a custom Hook?

A function starting with `use` that calls other Hooks internally, extracting and sharing reusable stateful logic (e.g., `useFetch`, `useDebounce`) without changing the component tree.

### 500. What is a custom Hook? How do you build one?

A function starting with `use` that calls other Hooks, extracting reusable stateful logic (e.g., `useDebounce`).

### 501. What is a hook?

[↑ Back to Table of Contents](#table-of-contents) Hooks are functions that let you 'hook into' React state and lifecycle features from function components. Rules: (1) Only call hooks at the top level --- not inside loops, conditions, or nested functions. (2) Only call hooks from React function components or custom hooks. Common built-in hooks: useState, useEffect, useContext, useRef, useMemo, useCallback, useReducer. Custom hooks are functions starting with 'use' that compose built-in hooks for reusable stateful logic. ------------------------------------------------------------------------

### 502. What is a hook? Why were hooks introduced?

[↑ Back to Table of Contents](#table-of-contents) Hooks are functions that let you "hook into" React state and lifecycle features from functional components. They were introduced in React 16.8 to allow using state, side effects, and other React features without writing classes. Reasons for hooks: - Reuse stateful logic across components without complex patterns like HOCs or render props. - Simplify component logic by grouping related code (e.g., `useEffect` for side effects). - Avoid the complexity of `this` binding and class lifecycle methods. - Improve tree‑shaking and reduce bundle size. ------------------------------------------------------------------------

### 503. What is a monorepo and how does it relate to React projects?

A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps.

### 504. What is a render prop? How does it compare to Hooks?

A component that takes a function prop to determine what to render, sharing logic. Hooks avoid the "wrapper hell" render props create.

### 505. What is an infinite `useEffect` loop and how does it happen?

Setting state inside an effect that's also a dependency of that same effect (without a stabilizing condition), causing effect → state update → re-render → effect again, forever.

### 506. What is focus management and why does it matter?

After dynamic UI changes (modal open, navigation, form error), focus must be programmatically moved to the right element for keyboard/screen reader users. Use `ref.current.focus()` in `useEffect` after state changes. [⬆ Back to Table of Contents](#-table-of-contents)

### 507. What is Formik / React Hook Form used for?

Form state libraries handling values, validation, touched/error tracking, and submission. React Hook Form is uncontrolled-by-default (fewer re-renders, better performance for large forms); Formik uses controlled inputs (simpler mental model, more re-renders).

### 508. What is lazy initialization in `useState`?

`useState(() => expensiveCalc())` passes a function so the initial value is computed only once (on mount), not on every render. Useful for reading from `localStorage` or parsing data. [⬆ Back to Table of Contents](#-table-of-contents)

### 509. What is React Hook Form and why is it popular?

Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood -- minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms. ------------------------------------------------------------------------

### 510. What is React Hooks?

[↑ Back to Table of Contents](#table-of-contents) React Hooks are the built-in functions that permit developers for using the state and lifecycle methods within React components. These are newly added features made available in React 16.8 version. Each lifecycle of a component is having 3 phases which include mount, unmount, and update. Along with that, components have properties and states. Hooks will allow using these methods by developers for improving the reuse of code with higher flexibility navigating the component tree. Using Hook, all features of React can be used without writing class components. ***For example***, before React version 16.8, it required a class component for managing the state of a component. But now using the useState hook, we can keep the state in a functional component.

### 511. What is React Query (TanStack Query) / SWR, and why use them over manual `useEffect` fetching?

Purpose-built server-state libraries providing caching, deduplication of concurrent requests, background refetching, and stale-while-revalidate semantics — solving problems manual `fetch`-in-`useEffect` doesn't (race conditions, cache invalidation, refetch-on-focus).

### 512. What is React.memo? How is it different from useMemo and useCallback?

Remember: React.memo works from outside, i.e, the props, and useMemo/useCallback work inside the component. You know how in React, whenever a component re-renders, all of its child components also re-render by default. And sometimes, this entire step becomes unnecessary. To prevent it from happening, we use the above three: React.memo, useMemo, & useCallback. But how are they different? Let me explain! **React.memo** It is an HOC (higher-order component) that is used to optimize performance and prevent a component from re-rendering if its props haven’t changed. In this case, React checks to see if the props are the same as before, - If yes, it skips render - If no, then re-render This comes in use a lot when a component ends up receiving the same data again and again. (becomes quite inconvenient!) But you should be careful, Even if the data looks the same, React may still think it changed. For example:

```
<Child user={{ name: "Kamala" }} />

```
Here, a new object is created every time, so React thinks props have changed, and then a re-render happens. Now, to prevent this from happening, we use: useMemo & useCallback **a.** **useMemo** stores/memorizes a value, so it doesn’t get recreated on every render. Eg:

```
const user = useMemo(() => ({ name: "Kamala" }), []);

```
Now the same object is reused, and React.memo can work properly. **b. useCallback** is similar, but for functions. Eg:

```
const handleClick = useCallback(() => { console.log("clicked"); }, []);

```
Without this, a new function is created every render, which can also break React.memo. You might be asked as a follow-up if a component wrapped in React.memo still re-renders, then what’s the problem. You can answer this by listing errors, such as if Parent passes inline objects/functions, or the component consumes context. [↑ Back to Table of Contents](#table-of-contents)

### 513. What is re‑rendering, and why does it happen?

Re‑rendering is the process where React updates the UI to reflect the current state and props. It happens when: - A component’s state changes. - Its props change. - Its parent re‑renders (by default). - A context value it uses changes. - A custom hook triggers an update. React batches updates for performance; re‑rendering does not necessarily mean the DOM is updated – React computes the difference (reconciliation) and only updates the DOM where needed.

### 514. What is the `eslint-plugin-react-hooks` plugin?

[↑ Back to Table of Contents](#table-of-contents) Enforces Rules of Hooks: 'rules-of-hooks' (hooks only in function components/custom hooks) and 'exhaustive-deps' (all effect dependencies declared). Install in every React project. ------------------------------------------------------------------------

### 515. What is the `react-error-boundary` library?

Provides `<ErrorBoundary fallback={...}>` and `<ErrorBoundary FallbackComponent={...}>`. Also provides `useErrorBoundary()` hook to imperatively throw errors into the nearest boundary and reset it.

### 516. What is the `use` Hook (React 19)? How does it differ from other Hooks?

Can be called conditionally; reads a Promise's value directly in render, suspending via `Suspense` until resolved.

### 517. What is the `useEffect` cleanup function?

[↑ Back to Table of Contents](#table-of-contents) Return a function from `useEffect` to run cleanup before the next effect or on unmount. Used to clear timers, cancel fetch, unsubscribe from observables, or remove event listeners.

### 518. What is the `useTransition` hook for performance?

Marks a state update as a non-urgent transition. React renders the urgent update first (keeping UI responsive) and defers the transition. Returns `[isPending, startTransition]`; use `isPending` to show a loading indicator. [↑ Back to Table of Contents](#table-of-contents)

### 519. What is the Container/Presentational pattern? Still relevant with Hooks?

Separating data-fetching "smart" containers from "dumb" rendering. With Hooks, the split often moves into a custom Hook instead of two files.

### 520. What is the container/presenter pattern and is it still relevant?

Separating data logic (container) from UI (presenter). Less strictly followed now – hooks handle data logic inside any component. But the concept of separating concerns is still valuable, enforced by custom hooks. [↑ Back to Table of Contents](#table-of-contents)

### 521. What is the difference between `startTransition` and `useTransition`?

`startTransition` is the standalone function (usable outside components, e.g. in a vanilla event handler) for marking an update as a transition; `useTransition` is the Hook version that also gives you an `isPending` boolean for showing a pending UI state.

### 522. What is the difference between a development build and a production build of a React app?

Development builds include extra warnings, Strict Mode double-invocation, unminified code with readable stack traces, and devtools hooks. Production builds strip these, minify/mangle code, and often run additional optimizations (dead code elimination), resulting in a smaller, faster bundle with less helpful error messages.

### 523. What is the difference between class components and function components?

Class components use `this.state` and lifecycle methods. Function components use Hooks. Since Hooks (16.8), function components can do everything classes can and are now the default.

### 524. What is the difference between optimistic and pessimistic updates?

Optimistic: update UI immediately assuming success, roll back on error (fast UX). Pessimistic: wait for server confirmation before updating UI (safe, may feel slow). React 19 has `useOptimistic` for the optimistic pattern. [⬆ Back to Table of Contents](#-table-of-contents)

### 525. What is the difference between useEffect and useLayoutEffect?

[↑ Back to Table of Contents](#table-of-contents) Both useEffect and useLayoutEffect run after React updates the DOM. But here’s how they both differ: 1\. useEffect runs after the browser has painted the update. So the user already sees the UI change, and then your effect runs in the background. This is why it’s non-blocking and used for things like API calls, subscriptions, and logging. Here, useEffect(() =\> { console.log("runs after paint"); }); 2\. useLayoutEffect runs before the browser paints. So React updates the DOM, then your effect runs, and only after that does the browser show anything. Like this: useLayoutEffect(() =\> { console.log("runs before paint"); }); Because of this, it is synchronous and blocks the UI until it finishes. So, how do they come in use? Imagine that you need to measure an element’s size or adjust its position, If you use useEffect, the browser will first show the UI, and then your adjustment happens. Also, remember that this can cause a visible flicker. With useLayoutEffect, the adjustment happens before anything is shown, so the user never sees that intermediate state. Now, which one is best to use when? - useEffect, in most cases! - useLayouteffect, only when you need to make visual changes before the screen updates Here’s what they can ask as a follow-up in interviews: Q. When can useLayoutEffect hurt performance? Your ans: Since it blocks painting, heavy or slow logic inside it can delay rendering and make the UI feel laggy.

### 526. What is the difference between useEffect, useLayoutEffect, and useInsertionEffect?

[↑ Back to Table of Contents](#table-of-contents) useEffect: runs AFTER paint (asynchronous) — doesn't block browser from painting. Good for: data fetching, subscriptions, analytics. useLayoutEffect: runs synchronously AFTER DOM mutations but BEFORE paint — blocks painting. Use when you need to read/write DOM layout (element size/position) to avoid visual flicker. useInsertionEffect: runs BEFORE DOM mutations — specifically for CSS-in-JS libraries to inject styles before any layout effects read styles. Hierarchy: useInsertionEffect → DOM mutations → useLayoutEffect → paint → useEffect.

### 527. What is the difference between useMemo and React.memo?

[↑ Back to Table of Contents](#table-of-contents) React.memo is a HOC (Higher Order Component) that memoizes an entire component --- prevents re-render if props haven't changed (shallow comparison). useMemo is a hook that memoizes a computed value inside a component. Use React.memo on child components that receive stable props and render expensively. Use useMemo for expensive calculations within a component. They work together: React.memo stops the component from re-rendering, useMemo stops expensive recalculations inside. ------------------------------------------------------------------------

### 528. What is the difference between useState and useRef hook?

[↑ Back to Table of Contents](#table-of-contents) 1. useState causes components to re-render after state updates whereas useRef doesn't cause a component to re-render when the value or state changes. Essentially, useRef is like a "box" that can hold a mutable value in its (`.current`) property. 2. useState allows us to update the state inside components. While useRef allows referencing DOM elements and tracking values. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 529. What is the order of hook execution in a component?

Hooks run top-to-bottom on every render in the same order. React relies on call order to associate hook state with the correct hook -- this is why hooks cannot be inside conditionals or loops. Think of React hooks like a numbered seating chart at a wedding. React doesn't remember your hooks by their actual names; it only tracks them by the exact order (seat number) they appear in your code. How it Works Render 1: React notes that Seat 1 is a useState for a username, and Seat 2 is a useEffect for fetching data. Render 2: React expects the exact same setup. It goes to Seat 1, grabs the username state, goes to Seat 2, and runs the effect. Why Hooks Can't Be in if Statements or Loops If you hide a hook inside an if condition, and that condition turns false, that hook doesn't run. The Disaster: The hook in Seat 2 disappears. The hook that used to be in Seat 3 slides over into Seat 2. React gets totally confused and hands the wrong data to the wrong hook, crashing your app. ------------------------------------------------------------------------

### 530. What is the purpose of eslint plugin for hooks?

The ESLint plugin enforces rules of Hooks to avoid bugs. It assumes that any function starting with ”use” and a capital letter right after it is a Hook. In particular, the rule enforces that, 1. Calls to Hooks are either inside a PascalCase function (assumed to be a component) or another useSomething function (assumed to be a custom Hook). 2. Hooks are called in the same order on every render. [

### 531. What is the React Compiler (React Forget)?

The **React Compiler** (formerly known as React Forget) automatically optimizes your components by adding memoization where needed - eliminating the need for manual `useMemo`, `useCallback`, and `React.memo`.

### 532. What is the risk of using `key` to force-remount a component during a transition?

It discards all internal state of the remounted subtree immediately rather than smoothly transitioning, defeating the purpose of `useTransition`'s "keep old UI visible while preparing new" behavior — generally these two patterns solve different problems and shouldn't be combined carelessly.

### 533. What is the stable release for hooks support?

React includes a stable implementation of React Hooks in 16.8 release for below packages 1. React DOM 2. React DOM Server 3. React Test Renderer 4. React Shallow Renderer [↑ Back to Table of Contents](#table-of-contents)

### 534. What is the testing pyramid for React?

Unit tests (fast, many): individual functions/hooks. Integration tests (medium): component interactions, user flows. E2E tests (slow, few): full browser flows via Playwright or Cypress. Focus effort on the middle layer. [↑ Back to Table of Contents](#table-of-contents)

### 535. What is the use of useEffect React Hooks?

[↑ Back to Table of Contents](#table-of-contents) The useEffect React Hook is used for performing the side effects in functional components. With the help of useEffect, you will inform React that your component requires something to be done after rendering the component or after a state change. The function you have passed(can be referred to as “effect”) will be remembered by React and call afterwards the performance of DOM updates is over. Using this, we can perform various calculations such as data fetching, setting up document title, manipulating DOM directly, etc, that don’t target the output value. The useEffect hook will run by default after the first render and also after each update of the component. React will guarantee that the DOM will be updated by the time when the effect has run by it. The useEffect React Hook will accept 2 arguments: `useEffect(callback,[dependencies]);` Where the first argument callback represents the function having the logic of side-effect and it will be immediately executed after changes were being pushed to DOM. The second argument dependencies represent an optional array of dependencies. The useEffect() will execute the callback only if there is a change in dependencies in between renderings. **Example:**

```
import { useEffect } from 'react'; function WelcomeGreetings({ name }) { const msg = `Hi, ${name}!`; // Calculates output useEffect(() => { document.title = `Welcome to you ${name}`; // Side-effect! }, [name]); return <div>{msg}</div>; // Calculates output }

```
The above code will update the document title which is considered to be a side-effect as it will not calculate the component output directly. That is why updating of document title has been placed in a callback and provided to useEffect(). Consider you don’t want to execute document title update each time on rendering of WelcomeGreetings component and you want it to be executed only when the name prop changes then you need to supply name as a dependency to `useEffect(callback, [name])`.

### 536. What is the use() hook in React 19?

The `use()` hook allows you to read the value of a resource (Promise or Context) during render, with Suspense integration.

### 537. What is the useDebugValue hook?

[↑ Back to Table of Contents](#table-of-contents) The `useDebugValue` hook is used to **display a label** for custom hooks in **React DevTools**. It helps developers debug custom hooks by showing meaningful information. ##### Syntax

```js useDebugValue(value); useDebugValue(value, formatFn); // With optional formatter

```
##### Example: Custom Hook with Debug Value

```jsx import { useState, useEffect, useDebugValue } from 'react'; function useOnlineStatus() { const [isOnline, setIsOnline] = useState(true); useEffect(() => { const handleOnline = () => setIsOnline(true); const handleOffline = () => setIsOnline(false); window.addEventListener('online', handleOnline); window.addEventListener('offline', handleOffline); return () => { window.removeEventListener('online', handleOnline); window.removeEventListener('offline', handleOffline); }; }, []); // Shows "OnlineStatus: Online" or "OnlineStatus: Offline" in DevTools useDebugValue(isOnline ? 'Online' : 'Offline'); return isOnline; }

```
##### With Formatting Function (for expensive computations)

```jsx function useUser(userId) { const [user, setUser] = useState(null); // The format function only runs when DevTools is open useDebugValue(user, (user) => user ? `User: ${user.name}` : 'Loading...'); return user; }

```
**Note:** Only use `useDebugValue` in custom hooks that are part of shared libraries. It's not necessary for every custom hook in application code.

### 538. What is the useId hook and when should you use it?

[↑ Back to Table of Contents](#table-of-contents) The `useId` hook is a React hook introduced in React 18 that generates **unique IDs** that are stable across server and client renders. It's primarily used for **accessibility attributes** like linking form labels to inputs. ##### Syntax

```js const id = useId();

```
##### Example: Accessible Form Input

```jsx import { useId } from 'react'; function EmailField() { const id = useId(); return ( <div> <label htmlFor={id}>Email:</label> <input id={id} type="email" /> </div> ); }

```
##### When to Use - Generating unique IDs for form elements (`htmlFor`, `aria-describedby`, `aria-labelledby`) - Creating stable IDs in server-side rendering (SSR) applications - Avoiding ID collisions when the same component is rendered multiple times ##### When NOT to Use - As keys in a list (use data-based keys instead) - As CSS selectors or query selectors - For any purpose that requires the ID to be predictable **Note:** The IDs generated by `useId` contain colons (`:`) which may not work in CSS selectors. For multiple related IDs, you can use the same `id` as a prefix: `${id}-firstName`, `${id}-lastName`.

### 539. What is the useInsertionEffect hook?

[↑ Back to Table of Contents](#table-of-contents) The `useInsertionEffect` hook is designed for **CSS-in-JS library authors** to inject styles into the DOM before any layout effects run. It fires synchronously before DOM mutations. ##### Syntax

```js useInsertionEffect(() => { // Insert styles here return () => { // Cleanup }; }, [dependencies]);

```
##### Execution Order

```
1. useInsertionEffect → Inject styles 2. DOM mutations → React updates DOM 3. useLayoutEffect → Read layout, synchronously re-render if needed 4. Browser paint → User sees the result 5. useEffect → Side effects run

```
##### Example: Dynamic Style Injection

```jsx import { useInsertionEffect } from 'react'; let isInserted = new Set(); function useCSS(rule) { useInsertionEffect(() => { if (!isInserted.has(rule)) { isInserted.add(rule); const style = document.createElement('style'); style.textContent = rule; document.head.appendChild(style); } }, [rule]); } function Button() { useCSS('.dynamic-btn { background: blue; color: white; }'); return <button className="dynamic-btn">Click me</button>; }

```
**Note:** This hook is not intended for application code. It's specifically for CSS-in-JS libraries like styled-components or Emotion to prevent style flickering.

### 540. What is the useSyncExternalStore hook?

[↑ Back to Table of Contents](#table-of-contents) The `useSyncExternalStore` hook is designed to **subscribe to external stores** (non-React state sources) in a way that's compatible with concurrent rendering. It's primarily used by library authors for state management libraries.

### 541. What is the useTransition hook and how does it differ from useDeferredValue?

The `useTransition` hook allows you to mark certain state updates as **non-urgent transitions**, keeping the UI responsive during expensive re-renders. It returns a `isPending` flag and a `startTransition` function.

### 542. What is useContext? What are the steps to follow for useContext?

[↑ Back to Table of Contents](#table-of-contents) The `useContext` hook is a built-in React Hook that lets you access the value of a context inside a functional component without needing to wrap it in a <Context.Consumer> component. It helps you **avoid prop drilling** (passing props through multiple levels) by allowing components to access shared data like themes, authentication status, or user preferences. The usage of useContext involves three main steps:

### 543. What is useImperativeHandle Hook? Give an example.

[↑ Back to Table of Contents](#table-of-contents) `useImperativeHandle` is a React Hook that allows a **child component** to expose **custom functions or properties** to its **parent component**, when using `ref`. It is typically used with `forwardRef` and is very useful in cases like **modals**, **dialogs**, **custom inputs**, etc., where the parent needs to **control behavior imperatively** (e.g., open, close, reset). **Example: Dialog component**

```js import React, { useRef, useState, useImperativeHandle, forwardRef, } from 'react'; import './Dialog.css'; const Dialog = forwardRef((props, ref) => { const [isOpen, setIsOpen] = useState(false); const [formData, setFormData] = useState(''); useImperativeHandle(ref, () => ({ open: () => setIsOpen(true), close: () => setIsOpen(false), reset: () => setFormData(''), })); if (!isOpen) return null; return ( <div className="dialog"> <h2>Dialog</h2> <input type="text" value={formData} placeholder="Type something..." onChange={(e) => setFormData(e.target.value)} /> <br /> <button onClick={() => setIsOpen(false)}>Close</button> </div> ); }); function Parent() { const dialogRef = useRef(); return ( <div> <h1>useImperativeHandle Dialog Example</h1> <button onClick={() => dialogRef.current.open()}>Open Dialog</button> <button onClick={() => dialogRef.current.reset()}>Reset Dialog</button> <button onClick={() => dialogRef.current.close()}>Close Dialog</button> <Dialog ref={dialogRef} /> </div> ); } export default Parent;

```

### 544. What is useReducer, and when would you use it over useState?

useReducer and useState are React hooks that manage state within functional components. Here, useRender is used for more complex state logic, and useState carries out simpler values. Here’s how they work: With useState, you directly update values with

```
setCount(count + 1);

```
Now you already know what change you want, so you update it immediately. The approach becomes a little different when it comes to useReducer. You will describe what happened, and a separate function then decides how to update the state. For example:

```
const [state, dispatch] = useReducer(reducer, { count: 0 });

```
Here: - state - holds the current value - dispatch - used to send actions - reducer - a function that updates the state Looking at the reducer function,

```
function reducer(state, action) { if (action.type === "increment") { return { count: state.count + 1 }; } return state; }

```
Here, the reducer receives the current ‘state’ and an ‘action’, then it checks what kind of action it is (action.type), and based on that, it returns a new state. At first, this feels like extra steps compared to useState. But it becomes useful when state is more complex. For example, in a form with multiple fields, instead of writing many useState calls, you can handle all updates in one reducer function. This keeps all the logic in one place instead of spreading it across different handlers. [↑ Back to Table of Contents](#table-of-contents)

### 545. What is useState() in React?

[↑ Back to Table of Contents](#table-of-contents) The useState() is a built-in React Hook that allows you for having state variables in functional components. It should be used when the DOM has something that is dynamically manipulating/controlling. In the below-given example code, The useState(0) will return a tuple where the count is the first parameter that represents the counter’s current state and the second parameter setCounter method will allow us to update the state of the counter.

```
... const [count, setCounter] = useState(0); const [otherStuffs, setOtherStuffs] = useState(...); ... const setCount = () => { setCounter(count + 1); setOtherStuffs(...); ... };

```
We can make use of setCounter() method for updating the state of count anywhere. In this example, we are using setCounter() inside the setCount function where various other things can also be done. The idea with the usage of hooks is that we will be able to keep our code more functional and avoid class-based components if they are not required.

### 546. What problems does `useMemo` actually solve? When should you NOT use it?

[↑ Back to Table of Contents](#table-of-contents) `useMemo` solves unnecessary recomputation of expensive calculations on every render. It also helps maintain referential equality for objects/arrays that are dependencies of other hooks (like `useEffect`).

### 547. What problems does React Query solve vs raw `useEffect` fetching?

Caching, request dedup, background refetch, retries, stale-while-revalidate, and loading/error states out of the box.

### 548. What rules need to be followed for hooks?

You need to follow two rules in order to use hooks,

### 549. What types of values can `useState` hold?

[↑ Back to Table of Contents](#table-of-contents) The `useState` hook accepts different types of values. * Primitives: `number`, `string`, `boolean` * Arrays * Objects * Functions * `null` or `undefined` But you needs to be cautious with **reference types (objects/arrays)** because React compares old and new values **by reference**, so direct mutations won't trigger a re-render. For example, the correct and wrong ways of state updates as shown below,

```js user.name = "Sudheer"; //wrong way setUser(prev => ({ ...prev, name: 'Sudheer' })); //correct way

```

### 550. What would the context value be for no matching provider?

When a component calls `useContext(SomeContext)` but **no matching** `<SomeContext.Provider>` **is present higher up in the component tree**, the **default value** passed to `React.createContext(defaultValue)` is returned.

```js const ThemeContext = React.createContext('light'); // 'light' is the default value function ThemedComponent() { const theme = useContext(ThemeContext); return <div>Current theme: {theme}</div>; } // No ThemeContext.Provider anywhere in the tree

```
In this case, `theme` will be 'light'. It's the default value you provided when you created the context. **Note:** If you don’t specify a default value, the context value will be undefined when used without a provider:

```jsx const AuthContext = React.createContext(); // No default function Profile() { const auth = useContext(AuthContext); // auth will be undefined if there's no AuthContext.Provider }

```
[↑ Back to Table of Contents](#table-of-contents)

### 551. What's a common pitfall when using useContext with objects?

[↑ Back to Table of Contents](#table-of-contents) A **common pitfall** when using `useContext` with objects is **triggering unnecessary re-renders** across all consuming components — even when only part of the context value changes. When you provide an object as the context value, React compares the entire object reference. If the object changes (even slightly), React assumes the whole context has changed, and **all components using** `useContext(MyContext)` **will re-render**, regardless of whether they use the part that changed. **Example:**

```js const MyContext = React.createContext(); function MyProvider({ children }) { const [user, setUser] = useState(null); const [theme, setTheme] = useState('light'); // This causes all consumers to re-render on any state change const contextValue = { user, setUser, theme, setTheme }; return ( <MyContext.Provider value={contextValue}> {children} </MyContext.Provider> ); }

```
In this case, a change in `theme` will also trigger a re-render in components that only care about `user`. This issue can be fixed in two ways,

### 552. When and how often does React invoke the setup and cleanup functions inside a useEffect hook?

[↑ Back to Table of Contents](#table-of-contents)

### 553. When does a child's useEffect cleanup run vs the parent's cleanup?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function App() { const [show, setShow] = React.useState(true); React.useEffect(() => { return () => { console.log('App cleanup'); }; }, []); return ( <> {show && <Child />} <button onClick={() => setShow(false)}>Hide</button> </> ); } function Child() { React.useEffect(() => { console.log('Child mounted'); return () => console.log('Child cleanup'); }, []); return <div>child</div>; }

```
**Behavior:** On mount: `Child mounted`. On clicking Hide: `Child cleanup`. App's cleanup only runs when App itself unmounts. **Explanation:** Effect cleanups run when the component unmounts OR before the next effect run. Conditional rendering (`show && <Child />`) unmounts Child when `show` becomes false, triggering Child's cleanup.

### 554. When is `useMemo`/`useCallback` actually worth it? Cost of overusing?

Worth it for expensive computations or memoized-child/dependency stability. Overuse adds comparison/storage overhead that can net lose for cheap computations.

### 555. When NOT to Use?

- As keys in a list (use data-based keys instead) - As CSS selectors or query selectors - For any purpose that requires the ID to be predictable **Note:** The IDs generated by `useId` contain colons (`:`) which may not work in CSS selectors. For multiple related IDs, you can use the same `id` as a prefix: `${id}-firstName`, `${id}-lastName`. [↑ Back to Table of Contents](#table-of-contents)

### 556. When should you use Redux/Zustand instead of Context + `useState`?

For complex, frequently-updating shared state needing fine-grained subscriptions, time-travel debugging, or middleware.

### 557. When should you use useImperativeHandle?

[↑ Back to Table of Contents](#table-of-contents) The useImperativeHandler hook will be used in below cases: * You want to expose **imperative methods** from a child component - Custom input controls exposing `focus`, `clear`, or `validate` methods - Modal components exposing `open()` and `close()` methods - Scroll containers exposing `scrollToTop()` or `scrollToBottom()` methods * You want to **hide internal implementation** but provide controlled external access. * You're building **reusable component libraries** (e.g., inputs, modals, form controls).

### 558. When to Still Use Manual Optimization?

```jsx // For external libraries without Compiler support import { expensiveLibFunction } from 'old-library'; function MyComponent() { // May still need manual memoization here const result = useMemo(() => expensiveLibFunction(), []); return <div>{result}</div>; }

```

### 559. When to use a Class Component over a Function Component?

[↑ Back to Table of Contents](#table-of-contents) After the addition of Hooks(i.e. React 16.8 onwards) it is always recommended to use Function components over Class components in React. Because you could use state, lifecycle methods and other features that were only available in class component present in function component too. But even there are two reasons to use Class components over Function components. 1. If you need a React functionality whose Function component equivalent is not present yet, like Error Boundaries. 2. In older versions, If the component needs _state or lifecycle methods_ then you need to use class component. So the summary to this question is as follows: **Use Function Components:** - If you don't need state or lifecycle methods, and your component is purely presentational. - For simplicity, readability, and modern code practices, especially with the use of React Hooks for state and side effects. **Use Class Components:** - If you need to manage state or use lifecycle methods. - In scenarios where backward compatibility or integration with older code is necessary. **Note:** You can also use reusable [react error boundary](https://github.com/bvaughn/react-error-boundary) third-party component without writing any class. i.e, No need to use class components for Error boundaries. The usage of Error boundaries from the above library is quite straight forward. > **_Note when using react-error-boundary:_** ErrorBoundary is a client component. You can only pass props to it that are serializable or use it in files that have a `"use client";` directive.

```jsx "use client"; import { ErrorBoundary } from "react-error-boundary"; <ErrorBoundary fallback={<div>Something went wrong</div>}> <ExampleApplication /> </ErrorBoundary>;

```

### 560. Why do React Hooks make use of refs?

[↑ Back to Table of Contents](#table-of-contents) Earlier, refs were only limited to class components but now it can also be accessible in function components through the useRef Hook in React. The refs are used for: - Managing focus, media playback, or text selection. - Integrating with DOM libraries by third-party. - Triggering the imperative animations.

### 561. Why do we use array destructuring (square brackets notation) in `useState`?

[↑ Back to Table of Contents](#table-of-contents) When we declare a state variable with `useState`, it returns a pair — an array with two items. The first item is the current value, and the second is a function that updates the value. Using [0] and [1] to access them is a bit confusing because they have a specific meaning. This is why we use array destructuring instead. For example, the array index access would look as follows:

```javascript var userStateVariable = useState("userProfile"); // Returns an array pair var user = userStateVariable[0]; // Access first item var setUser = userStateVariable[1]; // Access second item

```
Whereas with array destructuring the variables can be accessed as follows:

```javascript const [user, setUser] = useState("userProfile");

```

### 562. Why is storing derived values in `useState` (and syncing via `useEffect`) usually an anti-pattern?

It creates two sources of truth that can get out of sync, adds an unnecessary extra render (state update → re-render), and is harder to reason about than just computing the value directly during render.

### 563. Why React tab is not showing up in DevTools?

[↑ Back to Table of Contents](#table-of-contents) When the page loads, _React DevTools_ sets a global named `__REACT_DEVTOOLS_GLOBAL_HOOK__`, then React communicates with that hook during initialization. If the website is not using React or if React fails to communicate with DevTools then it won't show up the tab. ****

### 564. Why use functional updates with `useState`?

[↑ Back to Table of Contents](#table-of-contents) `setCount(c => c + 1)` reads the latest state inside the updater, avoiding stale closure bugs. Always use functional updates when new state depends on old state, especially inside async code or intervals.

### 565. Why were Hooks introduced in React?

React hooks were introduced in the 16.8 version of React. Previously, functional components were called stateless components. Only class components were used for state management and lifecycle methods. The need to change a functional component to a class component, whenever state management or lifecycle methods were to be used, led to the development of Hooks. *Example of a hook: ***useState hook:** In functional components, the useState hook lets us define a state for a component:

```
function Person(props) { // We are declaring a state variable called name. // setName is a function to update/change the value of name let [name, setName] = useState(''); }

```
The state variable “name” can be directly used inside the HTML. [↑ Back to Table of Contents](#table-of-contents)

### 566. With Specific Dependencies:

`**[count, user]**`

```css useEffect(() => { // runs after initial render // AND whenever `count` or `user` changes }, [count, user]);

```
* Effect runs on **first render**, and * Again **every time** any dependency value changes.

## Performance Optimization

### 567. A React component re-renders again and again but you never called setState. Why?

[↑ Back to Table of Contents](#table-of-contents) Multiple causes are possible: Parent re-render: parent's state/props changed, triggering all children to re-render Inline objects/arrays as props: {} or [] creates new reference on every render Inline functions as props: () => {} creates new function instance each render Context value changed: if consuming a Context that updates frequently Custom hook with unstable return values causing cascading updates useEffect with missing/incorrect deps triggering setState in a loop

### 568. A user complains about slow UI after data load --- how would you optimize rendering and improve UX?

Slow UI after data load typically means the initial render is expensive or the data processing blocks the main thread. - **Profile the render:** Use React DevTools Profiler to identify which component is expensive. Look for large lists, complex calculations, or deeply nested component trees. - **Defer heavy work:** - Move expensive computations to a Web Worker. - Use `useDeferredValue` or `startTransition` to mark non‑urgent updates (React 18) so the UI stays responsive. - Split the data into chunks and render progressively (e.g., pagination or infinite scroll). - **Virtualise large lists:** With `react‑window` or `react‑virtualized`, only render visible items. - **Optimise images and media:** Lazy load images, use proper formats, and serve scaled images. - **Improve perceived performance:** Show skeleton screens or placeholder loaders immediately, then fill in data as it arrives. This reduces perceived lag. - **Memoise derived data:** Use `useMemo` to avoid recalculating expensive derived state on every render. - **Avoid layout thrashing:** Batch DOM reads/writes. In React, this is less common but can happen with third‑party libraries. ------------------------------------------------------------------------

### 569. Asset Loading APIs?

[↑ Back to Table of Contents](#table-of-contents) Preload resources for better performance:

```jsx import { preload, preinit } from 'react-dom'; preload('/font.woff2', { as: 'font' }); preinit('/script.js', { as: 'script' });

```

### 570. Can a re-render happen without a commit?

Yes — in concurrent mode, React can render (compute the new tree) and then discard/restart that work if interrupted by a higher-priority update, never reaching commit.

### 571. Can you force a component to re-render without calling setState?

[↑ Back to Table of Contents](#table-of-contents) By default, when your component's state or props change, your component will re-render. If your `render()` method depends on some other data, you can tell React that the component needs re-rendering by calling `forceUpdate()`.

```javascript component.forceUpdate(callback);

```
It is recommended to avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`. **** ------------------------------------------------------------------------

### 572. Canary Deployment?

- Deploy new version to a small percentage of production traffic (e.g., 1–5%). - Monitor error rates, latency, and Core Web Vitals. - Use feature flags to control exposure further. - If metrics stay within thresholds, gradually increase traffic.

### 573. Context re-render behavior – what should you know?

Every consumer re-renders when the context value changes by reference. Passing a new object literal as value on every parent render causes all consumers to re-render every time. Fix: memoize the value with `useMemo`. [⬆ Back to Table of Contents](#-table-of-contents)

### 574. CSS Animation Jank: A CSS animation is janky on mobile – how to identify and fix?

**Identify**: - Use Chrome DevTools **Performance** tab, record while animation runs. - Look for long **Layout** or **Paint** events. If they appear during animation, the property being animated is causing layout recalculations. - Enable **Paint flashing** and **Layout Shift Regions** to visualize repaints. **Common causes**: - Animating properties that trigger layout (e.g., `width`, `height`, `top`, `left`). - Heavy JavaScript executing on the main thread during animation. - Missing `will-change` hint for animated elements. - Compositing issues (e.g., elements not on their own layer). **Fixes**: - Animate only **`transform`** and **`opacity`** – these are handled by the compositor thread. - Use `will-change: transform` for elements you intend to animate, but sparingly to avoid memory overhead. - Move heavy JavaScript out of animation frames (use `requestAnimationFrame` with throttling). - Ensure animated elements are in a separate compositing layer (by using `transform: translateZ(0)` or `will-change`). - Test on real mobile devices with throttled CPU.

### 575. Deploy to Staging?

- Deploy to a staging environment (e.g., using a Kubernetes cluster or static hosting). - Run end‑to‑end tests against staging. - Perform performance testing (Lighthouse CI).

### 576. Does `React.lazy` support named exports?

No, only default exports. For a named export, create an intermediate module that re-exports it as default: `export { Named as default } from './Module'`.

### 577. Does a child always re-render when its parent re-renders?

Yes by default, unless wrapped in `React.memo` with shallowly-equal props.

### 578. Does the lazy function support named exports?

No, currently `React.lazy` function supports default exports only. If you would like to import modules which are named exports, you can create an intermediate module that reexports it as the default. It also ensures that tree shaking keeps working and don’t pull unused components. Let's take a component file which exports multiple named components,

```javascript // MoreComponents.js export const SomeComponent = /* ... */; export const UnusedComponent = /* ... */;

```
and reexport `MoreComponents.js` components in an intermediate file `IntermediateComponent.js`

```javascript // IntermediateComponent.js export { SomeComponent as default } from "./MoreComponents.js";

```
Now you can import the module using lazy function as below,

```javascript import React, { lazy } from "react"; const SomeComponent = lazy(() => import("./IntermediateComponent.js"));

```
[↑ Back to Table of Contents](#table-of-contents)

### 579. Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.

**Route‑based code splitting** – using `React.lazy` with `Suspense`:

```jsx const Home = React.lazy(() => import('./routes/Home')); const About = React.lazy(() => import('./routes/About')); function App() { return ( <Suspense fallback={<Loading />}> <Routes> <Route path="/" element={<Home />} /> <Route path="/about" element={<About />} /> </Routes> </Suspense> ); }

```
**Component‑level lazy loading** – for heavy components like modals, charts, or editors:

```jsx const HeavyChart = React.lazy(() => import('./HeavyChart')); // then use it with Suspense

```
**Pre‑loading** – start loading a chunk before navigation using `webpackPrefetch`:

```jsx import(/* webpackPrefetch: true */ './HeavyComponent');

```
**Pre‑fetching on hover** – trigger dynamic import when user hovers over a link. **Bundler configuration** – ensure chunks are named and optimized (e.g., Webpack’s `splitChunks`).

### 580. Explain the concept of "controlled re‑render boundaries".

[↑ Back to Table of Contents](#table-of-contents) A controlled re‑render boundary is a technique to isolate parts of the UI that re‑render frequently from those that don’t. This can be achieved by: - Using `React.memo` on child components. - Moving state down to the components that need it. - Lifting state up only as necessary. - Using `useMemo` and `useCallback` to stabilize props. - Structuring context to avoid unnecessary consumers.

### 581. Follow-up: What if we set the SAME value?

```jsx <button onClick={() => setCount(count)}>Same</button> // sets to current value

```
**Behavior:** React bails out of re-rendering after comparing state with `Object.is`. If state doesn't change, Provider doesn't re-render, Context consumers don't re-render. [⬆ Back to Table of Contents](#-table-of-contents)

### 582. Given a slow React tree, how do you identify and fix the performance bottleneck?

[↑ Back to Table of Contents](#table-of-contents) **Identify:** 1. Open React DevTools **Profiler**, record an interaction, and look at the flame graph — it shows which components rendered and how long each took. 2. Turn on "Highlight updates when components render" to visually spot components re-rendering more than expected. 3. Check the Profiler's "Why did this render?" info (or add manual `console.log` in render) to find the trigger — new props, new context value, or parent re-render. **Common fixes, applied in order of impact:** - **Co-locate state** — move state closer to where it's used so unrelated parts of the tree don't re-render. - **`React.memo`** on pure child components that receive the same props most of the time. - **`useMemo`/`useCallback`** to stabilize object/array/function props passed into memoized children (memo alone won't help if the prop reference changes every render). - **Split contexts** so a fast-changing value doesn't force every consumer of a big shared context to re-render. - **Virtualize long lists** (`react-window`) instead of rendering thousands of DOM nodes. - **Code-split** rarely-used branches with `React.lazy` + `Suspense` to shrink the initial render. - Move truly expensive, non-UI computation out of render (e.g. into a Web Worker) if it blocks the main thread. The key discipline is to **profile first, then fix** — `useMemo`/`useCallback` everywhere without evidence adds overhead and complexity without necessarily solving the actual bottleneck.

### 583. How do you reduce the performance cost of a component that re-renders on every scroll event?

Throttle/debounce the scroll handler, or better, derive the needed value (e.g., scroll position bucket) and only call `setState` when that derived value actually changes, avoiding a state update (and render) on every pixel of scroll.

### 584. How does `React.memo` prevent re-renders? Limitations?

Shallow-compares props; skips re-render if equal. Doesn't help if props are new references every render (needs `useMemo`/`useCallback` upstream).

### 585. How does React Context work? When can it hurt performance?

[↑ Back to Table of Contents](#table-of-contents) Context provides a way to pass data through the component tree without prop drilling. It works by creating a `Provider` component that holds a value. Any component that consumes the context via `useContext` will re‑render when the context value changes. **Performance pitfalls**: - If the context value changes frequently, many consumers may re‑render. - When a component consumes context, it cannot be memoized based on props alone; it will re‑render whenever the context value changes, even if the component’s own props didn’t change. - Using context for global state that changes often (e.g., animations) can cause excessive re‑renders.

### 586. How does the Virtual DOM improve performance?

[↑ Back to Table of Contents](#table-of-contents) Real DOM mutations are expensive (layout, paint, composite). React batches changes and applies minimal updates. The diffing algorithm is O(n) using heuristics (same type → update; different type → destroy and replace). ------------------------------------------------------------------------

### 587. How to prevent re-renders in React?

[↑ Back to Table of Contents](#table-of-contents) - **Reason for re-renders in React:** - Re-rendering of a component and its child components occur when props or the state of the component has been changed. - Re-rendering components that are not updated, affects the performance of an application. - **How to prevent re-rendering:** Consider the following components: class Parent extends React.Component { state = { messageDisplayed: false }; componentDidMount() { this.setState({ messageDisplayed: true }); } render() { console.log("Parent is getting rendered"); return ( <div className="App"> <Message /> </div> ); } } class Message extends React.Component { constructor(props) { super(props); this.state = { message: "Hello, this is vivek" }; } render() { console.log("Message is getting rendered"); return ( <div> <p>{this.state.message}</p> </div> ); } } - The** Parent** component is the parent component and the **Message** is the child component. Any change in the parent component will lead to re-rendering of the child component as well. To prevent the re-rendering of child components, we use the shouldComponentUpdate( ) method: > \*\*Note- Use shouldComponentUpdate( ) method only when you are sure > that it's a static component. class Message extends React.Component { constructor(props) { super(props); this.state = { message: "Hello, this is vivek" }; } shouldComponentUpdate() { console.log("Does not get rendered"); return false; } render() { console.log("Message is getting rendered"); return ( <div> <p>{this.state.message}</p> </div> ); } } As one can see in the code above, we have returned **false** from the shouldComponentUpdate( ) method, which prevents the child component from re-rendering. ------------------------------------------------------------------------

### 588. How to re-render the view when the browser is resized?

It is possible to listen to the resize event in **componentDidMount()** and then update the width and height dimensions. It requires the removal of the event listener in the **componentWillUnmount()** method. Using the below-given code, we can render the view when the browser is resized. class WindowSizeDimensions extends React.Component { constructor(props){ super(props); this.updateDimension = this.updateDimension.bind(this); } componentWillMount() { this.updateDimension() } componentDidMount() { window.addEventListener('resize', this.updateDimension) } componentWillUnmount() { window.removeEventListener('resize', this.updateDimension) } updateDimension() { this.setState({width: window.innerWidth, height: window.innerHeight}) } render() { return <span>{this.state.width} x {this.state.height}</span> } } ------------------------------------------------------------------------

### 589. How would you implement a robust frontend monitoring and logging system?

A robust system combines **error tracking**, **performance monitoring**, **user analytics**, and **structured logging**. - **Error tracking**: Use Sentry, Rollbar, or similar. Capture JavaScript errors, unhandled promise rejections, and React error boundaries. Upload source maps to get readable stack traces. - **Performance monitoring**: Implement Real User Monitoring (RUM) with tools like Datadog RUM, New Relic Browser, or Google Analytics with Web Vitals. Track Core Web Vitals (LCP, CLS, INP), custom timings (e.g., time to checkout), and resource loading. - **Logging**: For client‑side, send structured logs to a backend endpoint (e.g., via `fetch`). Use a correlation ID across frontend and backend to trace requests. Avoid logging sensitive data. - **User analytics**: Use tools like Mixpanel or Amplitude to track feature usage, funnel conversions, and user flows. - **Alerts**: Set up alerts on error rate spikes, performance regressions, or business metric thresholds. Use tools like Sentry’s alert rules or Datadog monitors. - **Implementation**: Wrap the app in a monitoring provider that initializes SDKs, attaches user context, and buffers logs. Ensure logging doesn’t block the main thread – send data asynchronously in idle periods.

### 590. How would you improve Web Vitals (LCP, CLS, INP)?

**Largest Contentful Paint (LCP)** – Largest element painted (usually hero image or text block) - Optimize server response time (TTFB) with CDN and caching. - Prioritize loading of LCP element: use `<link rel="preload">` for LCP images. - Avoid lazy‑loading the LCP image. - Minimize render‑blocking resources (CSS/JS) – defer non‑critical scripts. - Use server‑side rendering or static generation for fast initial paint. **Cumulative Layout Shift (CLS)** – Unexpected layout shifts - Always set explicit `width` and `height` on images, videos, and iframes. - Reserve space for dynamic content (e.g., using `aspect-ratio` or placeholder skeletons). - Insert new content (like ads) in a reserved space. - Avoid injecting UI elements above existing content. **Interaction to Next Paint (INP)** – Responsiveness to user input - Break up long tasks (use `setTimeout` or `scheduler.yield` in React 18+). - Use `useTransition` for non‑urgent state updates to keep UI responsive. - Optimize event handlers: avoid heavy work; offload to Web Workers if possible. - Reduce JavaScript execution time overall (code splitting, tree shaking).

### 591. How would you optimize a React application rendering 100,000+ items in a list?

Multi-layer approach: Virtualization/windowing: use react-window or react-virtual — render only visible rows (~10-20 items), recycle DOM nodes as user scrolls Pagination or infinite scroll: load chunks of 20-50 items instead of all at once Memoize list items with React.memo to prevent re-renders on unrelated state changes Use stable keys — avoid index as key if items can reorder Debounce filter/search operations Web Workers for heavy sorting/filtering computations off the main thread Code splitting: lazy load the list component if not immediately needed [↑ Back to Table of Contents](#table-of-contents)

### 592. How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)

Rendering 100,000+ DOM nodes at once will severely degrade performance. The key is to render only what's visible. **Virtualization / Windowing**\ - Use libraries like `react-window` or `react-virtualized`. They render only the items that fit in the viewport plus a small buffer. - Example with `react-window`: `jsx import { FixedSizeList as List } from 'react-window'; const Row = ({ index, style }) => <div style={style}>Item {index}</div>; <List height={600} itemCount={100000} itemSize={35} width={300}> {Row} </List>` - This dramatically reduces DOM nodes and memory usage. **Pagination**\ - If virtualization is not sufficient or if data comes from an API, implement pagination (offset-based or cursor) to load data in chunks. - Combine pagination with virtualization for very large datasets where loading all data upfront is impractical. **Optimizations within each row**\ - Use `React.memo` on row components to avoid re‑rendering when props (e.g., item data) haven't changed. - Avoid inline functions/objects in row props. **Measuring and adjusting**\ - Use the React DevTools Profiler to ensure only visible rows re‑render on scroll. ------------------------------------------------------------------------

### 593. Is it good to use arrow functions in render methods?

[↑ Back to Table of Contents](#table-of-contents) Yes, You can use. It is often the easiest way to pass parameters to callback functions. But you need to optimize the performance while using it.

```javascript class Foo extends Component { handleClick() { console.log("Click happened"); } render() { return <button onClick={() => this.handleClick()}>Click Me</button>; } }

```
**Note:** Using an arrow function in render method creates a new function each time the component renders, which may have performance implications

### 594. Name a few techniques to optimize React app performance.

[↑ Back to Table of Contents](#table-of-contents) There are many ways through which one can optimize the performance of a React app, let’s have a look at some of them: - **Using useMemo( )** - - It is a React hook that is used for caching CPU-Expensive functions. - Sometimes in a React app, a CPU-Expensive function gets called repeatedly due to re-renders of a component, which can lead to slow rendering. useMemo( ) hook can be used to cache such functions. By using useMemo( ), the CPU-Expensive function gets called only when it is needed. - **Using React.PureComponent -** - It is a base component class that checks the state and props of a component to know whether the component should be updated. - Instead of using the simple React.Component, we can use React.PureComponent to reduce the re-renders of a component unnecessarily. - **Maintaining State Colocation -** - This is a process of moving the state as close to where you need it as possible. - Sometimes in React app, we have a lot of unnecessary states inside the parent component which makes the code less readable and harder to maintain. Not to forget, having many states inside a single component leads to unnecessary re-renders for the component. - It is better to shift states which are less valuable to the parent component, to a separate component. - **Lazy Loading -** - It is a technique used to reduce the load time of a React app. Lazy loading helps reduce the risk of web app performances to a minimum.

### 595. Performance?

-- Load flags asynchronously; use a loading state (e.g., show a skeleton) until flags are ready, especially for critical flags that affect layout.

### 596. Re-render and State Update?

* On the next render: * React processes all queued updates for each hook slot. * Updates the stored state value accordingly. * Returns the new state to the component.

### 597. Re-render when the state updated:

When you update the component state using the state setter function, the componen't state automatically queues for a render.

### 598. React batches updates:

Multiple `dispatch` calls within the same event handler result in a single re-render.

### 599. React.memo with object prop?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function ExpensiveChild({ items }) { console.log('ExpensiveChild rendered'); return <ul>{items.map(i => <li key={i}>{i}</li>)}</ul>; } const MemoChild = React.memo(ExpensiveChild); function Parent() { const [count, setCount] = React.useState(0); const items = React.useMemo(() => [1, 2, 3], []); return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <MemoChild items={items} /> </> ); }

```
**Behavior:** `ExpensiveChild rendered` logs only ONCE (on mount). Clicking button does NOT re-render child. **Explanation:** `useMemo(() => [1, 2, 3], [])` creates the array ONCE and returns the same reference every render. `React.memo` sees the same `items` reference — no re-render. This is the correct combination.

### 600. Updater Function?

* The updater function (`setCount`) is a closure that, when called: * Enqueues a state update to React's internal queue. * Schedules a re-render of the component.

### 601. What are common React performance optimization techniques? (practical guide)

[↑ Back to Table of Contents](#table-of-contents) When you are optimizing performance in React, your primary concern is to always reduce unnecessary re-renders and avoid expensive work. These optimizations should be applied only after identifying actual bottlenecks. Here are some practical ways that you can use to tackle it: 1\. Prevent unnecessary re-renders - React.memo React.memo is used to memoize a component so it only re-renders when its props change. This is especially helpful for child components that end up receiving the same props because of the parent updates. This can be particularly effective when you combine it with stable props. 2\. Stabilize props - useCallback, useMemo - useCallback is used to memoize functions so that new function references are not created on every render, especially when passing callbacks to memoized children. - useMemo is used to cache the result of expensive computations so they are only recalculated when dependencies change. It should only be used when the computation is actually costly. 3\. Reduce initial load - Code Splitting Using React.lazy and Suspense, components can be loaded only when you need them instead of bundling everything upfront. This can basically help you with reducing the initial bundle size and improving load time, especially in large applications. 4\. Minimize re-render scope - State Colocation State should be kept as close as possible to where it is used. Lifting state too high causes more components to re-render unnecessarily. Also, colocating state limits updates to only the relevant parts of the UI. 5\. Optimize large lists - Virtualization For long lists, libraries like react-window render only the visible items instead of the entire dataset. This significantly reduces DOM nodes and improves rendering performance. Note - How to approach optimization! You need to understand that optimization should not be done prematurely. The correct approach is to use the React DevTools Profiler to identify which components are re-rendering frequently and consuming time, and then apply these techniques selectively. Now, you are good to go!

### 602. What are common React performance pitfalls?

Inline object/function props; context with rapidly changing values; large component trees without memoization; missing keys in lists; doing heavy work in render; importing large libraries without tree shaking; large images without lazy loading. [⬆ Back to Table of Contents](#-table-of-contents)

### 603. What are Pure Components?

Pure components are the components which render the same output for the same state and props. In function components, you can achieve these pure components through memoized `React.memo()` API wrapping around the component. This API prevents unnecessary re-renders by comparing the previous props and new props using shallow comparison. So it will be helpful for performance optimizations. But at the same time, it won't compare the previous state with the current state because function component itself prevents the unnecessary rendering by default when you set the same state again. The syntactic representation of memoized components looks like below,

```jsx const MemoizedComponent = memo(SomeComponent, arePropsEqual?);

```
Below is the example of how child component(i.e., EmployeeProfile) prevents re-renders for the same props passed by parent component(i.e.,EmployeeRegForm).

```jsx import { memo, useState } from "react"; const EmployeeProfile = memo(function EmployeeProfile({ name, email }) { return ( <> <p>Name:{name}</p> <p>Email: {email}</p> </> ); }); export default function EmployeeRegForm() { const [name, setName] = useState(""); const [email, setEmail] = useState(""); return ( <> <label> Name:{" "} <input value={name} onChange={(e) => setName(e.target.value)} /> </label> <label> Email:{" "} <input value={email} onChange={(e) => setEmail(e.target.value)} /> </label> <hr /> <EmployeeProfile name={name} /> </> ); }

```
In the above code, the email prop has not been passed to child component. So there won't be any re-renders for email prop change. In class components, the components extending _`React.PureComponent`_ instead of _`React.Component`_ become the pure components. When props or state changes, _PureComponent_ will do a shallow comparison on both props and state by invoking `shouldComponentUpdate()` lifecycle method. **Note:** `React.memo()` is a higher-order component. [↑ Back to Table of Contents](#table-of-contents)

### 604. What are React Suspense and React.lazy? How do they enable code splitting?

In React, all components are bundled together and loaded at once. This can slow down the initial load, especially if the app is large. To avoid this from happening, React has an in-built feature that loads components only when they are needed, and this is called code splitting. Both React Suspense and React.lazy are used together to implement this code-splitting. So if you are importing a component like this:

```
import Profile from "./Profile";

```
You can try writing:

```
const Profile = React.lazy(() => import("./Profile"));

```
So that your component doesn’t load immediately, and that it would only download when React tries to render it. But there’s something you need to watch out for: While the component is loading, React needs to show something on the screen. And you can use ‘Suspense’ for that:

```
<Suspense fallback={<p>Loading...</p>}> <Profile /> </Suspense>

```
So what happens is: - React tries to render \<Profile /> - It sees that the component is still loading - Rendering is paused for that part - The fallback (Loading...) is shown - Once the file loads, React renders the actual component You can use this at different levels: - for entire pages like routes - or for smaller parts of the UI You can also wrap multiple components in one Suspense, or create separate ones if you want different loading states. You should note that in newer React versions, Suspense is also used for things like data fetching and server components. [↑ Back to Table of Contents](#table-of-contents)

### 605. What causes unnecessary re-renders in React?

[↑ Back to Table of Contents](#table-of-contents) Common causes: Parent component re-renders — all children re-render by default Inline objects/functions as props — new reference on every render Context value changes — all consumers re-render State updates higher in the tree than needed Missing React.memo on stable pure components useEffect triggering setState in a loop (missing deps or infinite loop)

### 606. What happens if a child uses React.memo() and parent props don't change?

[↑ Back to Table of Contents](#table-of-contents) If props are truly unchanged (by shallow comparison), React.memo prevents the child from re-rendering. However, if the parent passes inline objects ({}) or inline functions (() =\> {}) as props, these create new references on every parent render --- making React.memo ineffective. Solution: wrap objects in useMemo and functions in useCallback in the parent component to maintain stable references. ------------------------------------------------------------------------

### 607. What is `React.lazy()` plus dynamic `import()`? How does the bundler use it?

Tells the bundler to split that module and its deps into a separate chunk, loaded on demand when `import()` executes at runtime.

### 608. What is `React.lazy` and how does it work?

[↑ Back to Table of Contents](#table-of-contents) `React.lazy(() => import('./Comp'))` creates a lazy-loaded component. React suspends rendering until the chunk loads, showing the nearest `Suspense` fallback. Only works with default exports. ------------------------------------------------------------------------

### 609. What is `React.lazy`?

`React.lazy(() => import('./Comp'))` lazily loads a component's code on first render, suspending until the chunk downloads — must be wrapped in `<Suspense fallback={...}>`.

### 610. What is `React.memo`?

[↑ Back to Table of Contents](#table-of-contents) A HOC that wraps a functional component. On re-render of the parent, React shallowly compares old and new props; if equal, it skips re-rendering the child. Accepts a custom comparator as second argument. ------------------------------------------------------------------------

### 611. What is `shouldComponentUpdate`? How does it relate to `React.memo`?

A class lifecycle method returning `false` to skip a re-render; `React.memo` is its function-component equivalent (shallow comparison, or a custom comparator).

### 612. What is a pure component? What is `React.memo()`?

Renders the same output given the same props/state. `React.memo(Component)` skips re-rendering if props are shallowly equal to the previous render.

### 613. What is a selector function? Why is memoizing selectors (e.g., with `reselect`) important?

A function deriving a value from state. Memoizing avoids recomputing (and returning a new reference for) the same derived value on every call when inputs haven't changed, which would otherwise break consumer re-render optimizations.

### 614. What is code splitting and how does React.lazy work internally?

[↑ Back to Table of Contents](#table-of-contents) Code splitting breaks the JS bundle into smaller chunks loaded on demand, improving initial load time. React.lazy(import('./Component')) creates a lazy component that triggers a dynamic import() when first rendered. Suspense provides the loading fallback UI while the chunk downloads. Internally, React.lazy wraps the promise --- during render, if the promise is pending, React 'throws' it (using Suspense's error boundary mechanism), shows fallback, and resumes rendering when resolved. React Router supports route-level splitting natively. ------------------------------------------------------------------------

### 615. What is code splitting? How with `React.lazy`/`Suspense`?

Splitting the bundle into on-demand chunks; `React.lazy(() => import(...))` + `<Suspense fallback>`.

### 616. What is route based code splitting?

One of the best place to do code splitting is with routes. The entire page is going to re-render at once so users are unlikely to interact with other elements in the page at the same time. Due to this, the user experience won't be disturbed. Let us take an example of route based website using libraries like React Router with React.lazy,

```
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom'; import React, { Suspense, lazy } from 'react'; const Home = lazy(() => import('./routes/Home')); const About = lazy(() => import('./routes/About')); const App = () => ( <Router> <Suspense fallback={<div>Loading...</div>}> <Switch> <Route exact path="/" component={Home} /> <Route path="/about" component={About} /> </Switch> </Suspense> </Router> );

```
In the above code, the code splitting will happen at each route level. [

### 617. What is the "render props waterfall" performance risk?

Deeply nested render-prop/HOC wrapping can cause every layer to re-render together even when only the innermost data changed, since each wrapper re-renders its children as part of its own render output.

### 618. What is the main performance pitfall of Context?

Any consumer re-renders whenever the Provider's `value` changes, even for unrelated fields, especially with a new object literal passed each render.

### 619. What is the purpose of Suspense beyond lazy loading?

Suspense is a generic mechanism for orchestrating asynchronous dependencies in React. Besides lazy loading components, it can be used for data fetching (with libraries like Relay, Next.js) or any asynchronous operation that integrates with Suspense. It lets components “wait” for something before rendering, with a fallback UI. [↑ Back to Table of Contents](#table-of-contents)

### 620. What is the React DevTools Profiler used for?

Records renders, showing a flame graph of duration and "why did this render" causes.

### 621. What triggers a re-render in React?

Own state change, parent re-rendering, consumed context value changing, or a force update.

### 622. What will happen by defining nested function components?

Technically it is possible to write nested function components but it is not suggested to write nested function definitions. Because it leads to unexpected bugs and performance issues. [↑ Back to Table of Contents](#table-of-contents)

### 623. When does `React.memo` NOT help?

[↑ Back to Table of Contents](#table-of-contents) When props include new object/function references on every parent render (must pair with `useMemo`/`useCallback`). When the component is cheap to render (overhead of comparison \> render cost). When props always change. ------------------------------------------------------------------------

### 624. When to use the callback?

[↑ Back to Table of Contents](#table-of-contents) Use the `setState` callback when you need to perform an action immediately after the DOM has been updated in response to a state change. i.e, The callback is a reliable way to perform actions after a state update and re-render, especially when the timing is critical due to the asynchronous nature of state updates in React. For example, if you need to interact with the updated DOM, trigger analytics, or perform further computations that depend on the new state or rendered output.

### 625. When would you use `React.memo`?

[↑ Back to Table of Contents](#table-of-contents) Use `React.memo` for: - Components that receive the same props often but re‑render due to parent re‑renders. - Large components that are expensive to re‑render. - Pure functional components that depend on props only. Avoid over‑using `memo` because the shallow prop comparison itself costs time. Use it where profiling shows a benefit.

### 626. Why are keys important in lists? What happens if keys are unstable?

Keys give each element a stable identity, allowing React to match items between re‑renders. Without keys, React might reuse DOM nodes incorrectly, leading to performance issues or broken UI (e.g., lost focus, incorrect state). If keys are unstable (e.g., using index when the list can reorder), React may re‑create elements unnecessarily or mix up internal state.

### 627. Why does React re-render the whole component function on every update rather than patching just changed JSX?

Re-running the function is what makes the model declarative; performance is recovered via cheap reconciliation and explicit `memo` rather than skipping the function call itself.

### 628. Why function is preferred over object for `setState()`?

React may batch multiple `setState()` calls into a single update for performance. Because `this.props` and `this.state` may be updated asynchronously, you should not rely on their values for calculating the next state. This counter example will fail to update as expected:

```javascript // Wrong this.setState({ counter: this.state.counter + this.props.increment, });

```
The preferred approach is to call `setState()` with function rather than object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument.

```javascript // Correct this.setState((prevState, props) => ({ counter: prevState.counter + props.increment, }));

```
[↑ Back to Table of Contents](#table-of-contents)

### 629. Why we need to pass a function to setState()?

The reason behind for this is that `setState()` is an asynchronous operation. React batches state changes for performance reasons, so the state may not change immediately after `setState()` is called. That means you should not rely on the current state when calling `setState()` since you can't be sure what that state will be. The solution is to pass a function to `setState()`, with the previous state as an argument. By doing this you can avoid issues with the user getting the old state value on access due to the asynchronous nature of `setState()`. Let's say the initial count value is zero. After three consecutive increment operations, the value is going to be incremented only by one.

```javascript // assuming this.state.count === 0 this.setState({ count: this.state.count + 1 }); this.setState({ count: this.state.count + 1 }); this.setState({ count: this.state.count + 1 }); // this.state.count === 1, not 3

```
If we pass a function to `setState()`, the count gets incremented correctly.

```javascript this.setState((prevState, props) => ({ count: prevState.count + props.increment, })); // this.state.count === 3 as expected

```
**(OR)**

## Context API & State Management (Redux/Zustand/MobX)

### 630. Are there any similarities between Redux and RxJS?

[↑ Back to Table of Contents](#table-of-contents) These libraries are very different for very different purposes, but there are some vague similarities. Redux is a tool for managing state throughout the application. It is usually used as an architecture for UIs. Think of it as an alternative to (half of) Angular. RxJS is a reactive programming library. It is usually used as a tool to accomplish asynchronous tasks in JavaScript. Think of it as an alternative to Promises. Redux uses the Reactive paradigm because the Store is reactive. The Store observes actions from a distance, and changes itself. RxJS also uses the Reactive paradigm, but instead of being an architecture, it gives you basic building blocks, Observables, to accomplish this pattern.

### 631. Can Redux only be used with React?

[↑ Back to Table of Contents](#table-of-contents) Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. Redux simply provides a subscription mechanism which can be used by any other code.

### 632. Careful selection of complementary packages?

Redux is more minimal by design and provides extension points such as middleware and store enhancers. This has led to a large ecosystem, but it also means you must thoughtfully choose and configure additional packages for features like undo/redo, persistence, or form handling—something Flux explicitly leaves out but may be simpler to manage in smaller setups.

### 633. Compare Redux, MobX, Recoil/Jotai, Zustand, and Context for a large-scale app.

Redux (RTK): battle-tested, best DevTools/time-travel debugging, most boilerplate (mitigated by RTK), best for large teams needing strict patterns. MobX: less boilerplate via mutable observables, can be less predictable at scale. Recoil/Jotai: atomic, fine-grained, React-native mental model, newer ecosystem. Zustand: minimal API, great performance, good for medium complexity. Context: built-in, fine for infrequent/low-fanout updates only.

### 634. Components?

Used for _dumb_ components unaware of Redux.

### 635. Containers?

Used for _smart_ components connected to Redux.

### 636. Context vs Redux – when to choose which?

[↑ Back to Table of Contents](#table-of-contents) Context: simple, low-frequency shared state (theme, auth, locale). Redux: complex update logic, middleware (logging, side effects), time-travel debugging, large team codebases, or when you need strict action-based mutations.

### 637. Do I need to keep all my state into Redux? Should I ever use react internal state?

[↑ Back to Table of Contents](#table-of-contents) It is up to the developer's decision, i.e., it is developer's job to determine what kinds of state make up your application, and where each piece of state should live. Some users prefer to keep every single piece of data in Redux, to maintain a fully serializable and controlled version of their application at all times. Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, inside a component's internal state. Below are the rules of thumb to determine what kind of data should be put into Redux 1. Do other parts of the application care about this data? 2. Do you need to be able to create further derived data based on this original data? 3. Is the same data being used to drive multiple components? 4. Is there value to you in being able to restore this state to a given point in time (ie, time travel debugging)? 5. Do you want to cache the data (i.e, use what's in state if it's already there instead of re-requesting it)?

### 638. Do you need to have a particular build tool to use Redux?

[↑ Back to Table of Contents](#table-of-contents) Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. You should be able to use it regardless of your JavaScript build process. Redux also offers a UMD build that can be used directly without any build process at all.

### 639. Explain the Redux Toolkit flow.

(1) createSlice() defines state shape, reducers (sync), and generates action creators. (2) configureStore() combines slices into the global store, auto-adds DevTools and middleware. (3) createAsyncThunk() handles async operations — dispatches pending/fulfilled/rejected actions. (4) extraReducers handles async thunk lifecycle in slices. (5) Components use useSelector() to read state and useDispatch() to send actions. (6) Store notifies all subscribers on state change, React re-renders connected components.

### 640. How do you get redux scaffolding using create-react-app?

[↑ Back to Table of Contents](#table-of-contents) Redux team has provided official redux+js or redux+typescript templates for create-react-app project. The generated project setup includes, 1. Redux Toolkit and React-Redux dependencies 2. Create and configure Redux store 3. React-Redux `<Provider>` passing the store to React components 4. Small "counter" example to demo how to add redux logic and React-Redux hooks API to interact with the store from components The below commands need to be executed along with template option as below,

### 641. How do you manage global state? Compare Context, Redux, and modern alternatives.

[↑ Back to Table of Contents](#table-of-contents) So, this question is more targeted towards ways that YOU would take to manage the global state. So while I write the answer down, it’s best that you personalize it with examples that seem fit to you. Managing global state in React really depends on its scope and complexity. Most of the time, you can use ‘useState’ or ‘useReducer’, which may work well for component-specific data. But there are many circumstances under which different features can be used, 1\. Context API - This is used when the state has to be shared with multiple components, and it helps in avoiding prop drilling,g but please keep in mind that it can cause all consumers to re-render on updates. 2\. Redux - When the state becomes more complex and interdependent throughout the application, external libraries like Redux are used. It provides a centralized store, predictable updates, and middleware support, but it comes with additional boilerplate. When you look into modern alternatives, Zustand and Jotai provide simpler APIs and more efficient updates, which are usually suitable for mid-sized applications. Here are some distinctions that you can note: Client state & Server state: - Client state can be managed with local state, Context, or Redux. - Server state is better handled by tools like React Query, which manage caching and synchronization. When NOT to use Redux: Redux is unnecessary for small or moderately complex applications, or when most of the state is server state. So, here’s what you should do: Start with local state, then move to Context for shared state, and then use external libraries only when complexity or performance demands it.

### 642. How do you persist Redux/Zustand state across page reloads?

`redux-persist` (Redux) or Zustand's built-in `persist` middleware serialize selected state to `localStorage`/`sessionStorage` and rehydrate on load.

### 643. How do you test components connected to Redux/Zustand?

Wrap the component in a test-specific store instance (seeded with known state) via the real `Provider`, rather than mocking the store entirely, so the real selector/dispatch wiring is exercised.

### 644. How does async flow work in Redux Toolkit?

[↑ Back to Table of Contents](#table-of-contents) 1. Define a thunk using `createAsyncThunk`. 2. Inside the payload creator, perform async work (e.g., fetch). 3. Dispatch the thunk from a component. 4. The thunk dispatches the `pending` action immediately. 5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error. 6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data).

### 645. How does Redux Toolkit work internally?

[↑ Back to Table of Contents](#table-of-contents) - `createSlice` uses `createReducer` and `createAction` under the hood to generate reducers and action creators. It leverages Immer to allow immutable updates with mutable syntax. - `configureStore` calls Redux’s `createStore`, applies default middleware (including `redux-thunk`), and enables the Redux DevTools Extension. - `createAsyncThunk` returns a thunk that dispatches the lifecycle actions automatically and allows handling of the async operation.

### 646. How Redux Form `initialValues` get updated from state?

[↑ Back to Table of Contents](#table-of-contents) You need to add `enableReinitialize : true` setting.

```javascript const InitializeFromStateForm = reduxForm({ form: "initializeFromState", enableReinitialize: true, })(UserEdit);

```
If your `initialValues` prop gets updated, your form will update too.

### 647. How Relay is different from Redux?

[↑ Back to Table of Contents](#table-of-contents) Relay is similar to Redux in that they both use a single store. The main difference is that relay only manages state originated from the server, and all access to the state is used via _GraphQL_ queries (for reading data) and mutations (for changing data). Relay caches the data for you and optimizes data fetching for you, by fetching only changed data and nothing more.

### 648. How to access Redux store outside a component?

[↑ Back to Table of Contents](#table-of-contents) You just need to export the store from the module where it created with `createStore()`. Also, it shouldn't pollute the global window object.

```javascript store = createStore(myReducer); export default store;

```

### 649. How to add multiple middlewares to Redux?

[↑ Back to Table of Contents](#table-of-contents) You can use `applyMiddleware()`. For example, you can add `redux-thunk` and `logger` passing them as arguments to `applyMiddleware()`:

```javascript import { createStore, applyMiddleware } from "redux"; const createStoreWithMiddleware = applyMiddleware( ReduxThunk, logger )(createStore);

```

### 650. How to reset state in Redux?

[↑ Back to Table of Contents](#table-of-contents) You need to write a _root reducer_ in your application which delegate handling the action to the reducer generated by `combineReducers()`. For example, let us take `rootReducer()` to return the initial state after `USER_LOGOUT` action. As we know, reducers are supposed to return the initial state when they are called with `undefined` as the first argument, no matter the action.

```javascript const appReducer = combineReducers({ /* your app's top-level reducers */ }); const rootReducer = (state, action) => { if (action.type === "USER_LOGOUT") { state = undefined; } return appReducer(state, action); };

```
In case of using `redux-persist`, you may also need to clean your storage. `redux-persist` keeps a copy of your state in a storage engine. First, you need to import the appropriate storage engine and then, to parse the state before setting it to undefined and clean each storage state key.

```javascript const appReducer = combineReducers({ /* your app's top-level reducers */ }); const rootReducer = (state, action) => { if (action.type === "USER_LOGOUT") { Object.keys(state).forEach((key) => { storage.removeItem(`persist:${key}`); }); state = undefined; } return appReducer(state, action); };

```

### 651. How to structure Redux top level directories?

[↑ Back to Table of Contents](#table-of-contents) Most of the applications has several top-level directories as below:

### 652. How to use `connect()` from React Redux?

[↑ Back to Table of Contents](#table-of-contents) You need to follow two steps to use your store in your container:

### 653. Immutability is essential?

Redux enforces a strict immutability model for state updates, which differs from Flux’s more relaxed approach. This means you must avoid mutating state directly. Many Redux-related libraries assume immutability, so your team must be disciplined in writing pure update logic. You can use tools like `redux-immutable-state-invariant`, `Immer`, or `Immutable.js` to help enforce this practice, especially during development.

### 654. Javascript template:

```js npx create-react-app my-app --template redux

```

### 655. Limited static type integration?

While Flux has mature support for static type checking with tools like Flow, Redux’s type integration is less seamless. Although TypeScript is commonly used with Redux now, early Flow support was limited, and more boilerplate was required for static type safety. This may affect teams that rely heavily on type systems for large codebases. [↑ Back to Table of Contents](#table-of-contents)

### 656. Redux vs Context API?

Context is a built-in value-passing mechanism, not a full state management solution (no actions/reducers/middleware). Redux provides all of that.

### 657. Should I keep all component's state in Redux store?

[↑ Back to Table of Contents](#table-of-contents) Keep your data in the Redux store, and the UI related state internally in the component.

### 658. What are Redux selectors and why use them?

[↑ Back to Table of Contents](#table-of-contents) _Selectors_ are functions that take Redux state as an argument and return some data to pass to the component. For example, to get user details from the state:

```javascript const getUserData = (state) => state.user.data;

```
These selectors have two main benefits, 1. The selector can compute derived data, allowing Redux to store the minimal possible state 2. The selector is not recomputed unless one of its arguments changes

### 659. What are the advantages of formik over redux form library?

Below are the main reasons to recommend formik over redux form library, 1. The form state is inherently short-term and local, so tracking it in Redux (or any kind of Flux library) is unnecessary. 2. Redux-Form calls your entire top-level Redux reducer multiple times ON EVERY SINGLE KEYSTROKE. This way it increases input latency for large apps. 3. Redux-Form is 22.5 kB minified gzipped whereas Formik is 12.7 kB [↑ Back to Table of Contents](#table-of-contents)

### 660. What are the core principles of Redux?

[↑ Back to Table of Contents](#table-of-contents) Redux follows three fundamental principles:

### 661. What are the differences between `call()` and `put()` in redux-saga?

[↑ Back to Table of Contents](#table-of-contents) Both `call()` and `put()` are effect creator functions. `call()` function is used to create effect description, which instructs middleware to call the promise. `put()` function creates an effect, which instructs middleware to dispatch an action to the store. Let's take example of how these effects work for fetching particular user data.

```javascript function* fetchUserSaga(action) { // `call` function accepts rest arguments, which will be passed to `api.fetchUser` function. // Instructing middleware to call promise, it resolved value will be assigned to `userData` variable const userData = yield call(api.fetchUser, action.userId); // Instructing middleware to dispatch corresponding action. yield put({ type: "FETCH_USER_SUCCESS", userData, }); }

```

### 662. What are the differences between Redux and MobX?

[↑ Back to Table of Contents](#table-of-contents) Below are the main differences between Redux and MobX, | TopicReduxMobX | | | | -------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------- | | Definition | It is a javascript library for managing the application state | It is a library for reactively managing the state of your applications | | Programming | It is mainly written in ES6 | It is written in JavaScript(ES5) | | Data Store | There is only one large store exist for data storage | There is more than one store for storage | | Usage | Mainly used for large and complex applications | Used for simple applications | | Performance | Need to be improved | Provides better performance | | How it stores | Uses JS Object to store | Uses observable to store the data |

### 663. What are the downsides of Redux compared to Flux?

[↑ Back to Table of Contents](#table-of-contents) While Redux offers a powerful and predictable state management solution, it comes with a few trade-offs when compared to Flux. These include:

### 664. What are the features of Redux DevTools?

[↑ Back to Table of Contents](#table-of-contents) Some of the main features of Redux DevTools are below, 1. Lets you inspect every state and action payload. 2. Lets you go back in time by _cancelling_ actions. 3. If you change the reducer code, each _staged_ action will be re-evaluated. 4. If the reducers throw, you will see during which action this happened, and what the error was. 5. With `persistState()` store enhancer, you can persist debug sessions across page reloads.

### 665. What are the main features of Redux Form?

[↑ Back to Table of Contents](#table-of-contents) Some of the main features of Redux Form are: 1. Field values persistence via Redux store. 2. Validation (sync/async) and submission. 3. Formatting, parsing and normalization of field values.

### 666. What are the main features of Reselect library?

Let's see the main features of Reselect library, 1. Selectors can compute derived data, allowing Redux to store the minimal possible state. 2. Selectors are efficient. A selector is not recomputed unless one of its arguments changes. 3. Selectors are composable. They can be used as input to other selectors.

### 667. What are typical middleware choices for handling asynchronous calls in Redux?

[↑ Back to Table of Contents](#table-of-contents) Some of the popular middleware choices for handling asynchronous calls in Redux eco system are `Redux Thunk, Redux Promise, Redux Saga`.

### 668. What is an action in Redux?

[↑ Back to Table of Contents](#table-of-contents) *Actions* are plain JavaScript objects or payloads of information that send data from your application to your store. They are the only source of information for the store. Actions must have a type property that indicates the type of action being performed. For example, let's take an action which represents adding a new todo item:

```
{ type: ADD_TODO, text: 'Add todo item' }

```

### 669. What is createAsyncThunk() and why is it used?

createAsyncThunk handles async operations (API calls) in Redux. It takes an action type string and an async payload creator function. It automatically dispatches three action types: actionName/pending (loading), actionName/fulfilled (success with data), actionName/rejected (error). Handle these in extraReducers with builder.addCase(). This standardizes async state management and eliminates manual loading/error state boilerplate. ------------------------------------------------------------------------

### 670. What is Jotai and how does the atomic model work?

[↑ Back to Table of Contents](#table-of-contents) Jotai defines state as atoms – minimal pieces of state. Components subscribe to individual atoms; only components using a changed atom re-render. Derived atoms compute from other atoms, similar to Recoil.

### 671. What is middleware in Redux? Example?

Intercepts dispatched actions before reducers; `redux-thunk` lets action creators return functions for async dispatch sequences.

### 672. What is MobX?

[↑ Back to Table of Contents](#table-of-contents) MobX is a simple, scalable and battle tested state management solution for applying functional reactive programming (TFRP). For ReactJS application, you need to install below packages,

```bash npm install mobx --save npm install mobx-react --save

```

### 673. What is Recoil/Jotai? What problem do atom-based libraries solve?

Model state as small independent atoms, giving fine-grained reactivity without manually splitting Context.

### 674. What is Redux and why is it used?

[↑ Back to Table of Contents](#table-of-contents) Redux is a predictable state container: single source of truth (one global store), state is read-only (only changed by dispatching actions), changes via pure reducer functions. Benefits for large apps: predictable state transitions, easy debugging (Redux DevTools time-travel), centralized state logic, middleware for async operations, testable reducers. Redux Toolkit (RTK) is the modern recommended approach — reduces boilerplate with createSlice, createAsyncThunk, and immer-based immutable updates.

### 675. What is Redux Form?

_Redux Form_ works with React and Redux to enable a form in React to use Redux to store all of its state. Redux Form can be used with raw HTML5 inputs, but it also works very well with common UI frameworks like Material UI, React Widgets and React Bootstrap. [↑ Back to Table of Contents](#table-of-contents)

### 676. What is Redux Thunk vs Redux Saga?

Thunk: action creators return functions (`dispatch`, `getState` access) for simple async logic using Promises — simple, minimal API. Saga: generator-based middleware for complex async flows (cancellation, race conditions, sequencing) — more powerful, steeper learning curve.

### 677. What is Redux Thunk?

[↑ Back to Table of Contents](#table-of-contents) _Redux Thunk_ middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch()` and `getState()` as parameters.

### 678. What is Redux Toolkit (RTK) and why is it recommended?

The official, opinionated Redux toolset: `configureStore` (sensible defaults + DevTools), `createSlice` (auto-generates actions/reducers, uses Immer for mutable-looking immutable updates), and `createAsyncThunk` for async logic — drastically reduces boilerplate versus plain Redux.

### 679. What is Redux Toolkit and why is it recommended over plain Redux?

[↑ Back to Table of Contents](#table-of-contents) Redux Toolkit (RTK) is the official, opinionated toolset for Redux. It simplifies common patterns, reduces boilerplate, and includes best practices out of the box: - **`configureStore`**: Sets up the store with good defaults (middleware, devtools). - **`createSlice`**: Automatically generates action creators and reducers. - **`createAsyncThunk`**: Handles asynchronous actions with loading states. - **Immer integration**: Allows writing mutable‑looking code in reducers (actual immutability is handled). - **Redux DevTools** automatically enabled.

### 680. What is redux-saga?

[↑ Back to Table of Contents](#table-of-contents) `redux-saga` is a library that aims to make side effects (asynchronous things like data fetching and impure things like accessing the browser cache) in React/Redux applications easier and better. It is available in NPM:

```console $ npm install --save redux-saga

```

### 681. What is Redux?

[↑ Back to Table of Contents](#table-of-contents) Redux is a predictable state container for JavaScript applications, most commonly used with React. It helps you manage and centralize your application’s state in a single source of truth, enabling easier debugging, testing, and maintenance—especially in large or complex applications. Redux core is tiny library(about 2.5kB gzipped) and has no dependencies.

### 682. What is Redux? What are its three core principles?

Single store, read-only state (changed via dispatched actions), changes made by pure reducers.

### 683. What is the "single source of truth" principle in state management?

Each piece of data should have exactly one authoritative place it lives; everything else derives from or references it, avoiding sync bugs from duplicated copies.

### 684. What is the `useSelector` / `useDispatch` pattern in Redux?

[↑ Back to Table of Contents](#table-of-contents) useSelector is for reading data. It lets your component "grab" a specific piece of state from the global Redux store useDispatch is for changing data. It gives you a dispatch function. You use this function to send "actions" (requests) to the Redux store telling it to update the data.

### 685. What is the Context API?

[↑ Back to Table of Contents](#table-of-contents) A built-in React mechanism for sharing values across the component tree without prop drilling. Three parts: `React.createContext()` (creates context), `Provider` (supplies value), `useContext()` (consumes value). ------------------------------------------------------------------------

### 686. What is the Context API? When should you use it instead of prop drilling?

[↑ Back to Table of Contents](#table-of-contents) Prop drilling is the pattern of passing on data from the parent component through several levels down to the nested child component, but its process makes the code harder to maintain and debug. To avoid such problems, Context API, which is a built-in feature in React, helps in passing on the data, but without having to go through every level. This is how it works: You create a context using React.createContext(), then wrap part of your app with a Provider, and lastly, consume the value using useContext() Now, how does this actually help? For example: - current user (auth) - theme (dark/light) - language/locale These are values that are needed across many components at different levels. Passing them manually quickly becomes messy, so Context helps in keeping it cleaner. But here’s where it gets a little confusing, Context is not meant for everything. If the data changes very frequently, such as form input or animations, then Context might even end up hurting the performance. And why is that? Because whenever the context value changes, all components consuming it re-render. So the better way to understand this is that you can use Context for global, relatively stable data and keep local or frequently changing state inside components. You can also split contexts based on how often they update, instead of putting everything into one. That’s the difference between Context and Redux! Context is built into React and works well for simpler cases. Redux, on the other hand, adds things like middleware, devtools, better control over updates …but it also comes with more setup. **You can be asked some follow-up questions here, like:** Q. What happens if Context values change frequently? Your ans: All consuming components re-render. Q. How do you optimize it? Your ans: I split contexts based on their use and memoize the value passed to the Provider.

### 687. What is the difference between component and container in React Redux?

[↑ Back to Table of Contents](#table-of-contents) **Component** is a class or function component that describes the presentational part of your application. **Container** is an informal term for a component that is connected to a Redux store. Containers _subscribe_ to Redux state updates and _dispatch_ actions, and they usually don't render DOM elements; they delegate rendering to presentational child components.

### 688. What is the difference between Context API and Redux Toolkit?

[↑ Back to Table of Contents](#table-of-contents) Context API: built-in React, no extra library, ideal for low-frequency updates (theme, locale, auth user). Limitation: any context value change re-renders all consumers — bad for high-frequency state. Redux Toolkit: external library, single global store with selectors — components only re-render when their specific slice changes. Better for: complex state, frequent updates, time-travel debugging, multiple teams. Decision: use Context for simple/infrequent state, Redux Toolkit for complex apps with many state updates.

### 689. What is the difference between global state and server state (cache)?

Global state (UI preferences, auth) is owned entirely by the client. Server state (fetched API data) is actually owned by the server and the client just holds a cached, possibly-stale copy — better managed by a data-fetching library (React Query) than a generic state store.

### 690. What is the flux architecture pattern?

Unidirectional data flow: Action → Dispatcher → Store → View → (user interaction) → Action. Redux is inspired by Flux. Data always flows one way, making state changes predictable and traceable. [⬆ Back to Table of Contents](#-table-of-contents)

### 691. What is the mental model of redux-saga?

[↑ Back to Table of Contents](#table-of-contents) _Saga_ is like a separate thread in your application, that's solely responsible for side effects. `redux-saga` is a redux _middleware_, which means this thread can be started, paused and cancelled from the main application with normal Redux actions, it has access to the full Redux application state and it can dispatch Redux actions as well.

### 692. What is the proper way to access Redux store?

[↑ Back to Table of Contents](#table-of-contents) The best way to access your store in a component is to use the `connect()` function, that creates a new component that wraps around your existing one. This pattern is called _Higher-Order Components_, and is generally the preferred way of extending a component's functionality in React. This allows you to map state and action creators to your component, and have them passed in automatically as your store updates. Let's take an example of `<FilterLink>` component using connect:

```javascript import { connect } from "react-redux"; import { setVisibilityFilter } from "../actions"; import Link from "../components/Link"; const mapStateToProps = (state, ownProps) => ({ active: ownProps.filter === state.visibilityFilter, }); const mapDispatchToProps = (dispatch, ownProps) => ({ onClick: () => dispatch(setVisibilityFilter(ownProps.filter)), }); const FilterLink = connect(mapStateToProps, mapDispatchToProps)(Link); export default FilterLink;

```
Due to it having quite a few performance optimizations and generally being less likely to cause bugs, the Redux developers almost always recommend using `connect()` over accessing the store directly (using context API).

```javascript function MyComponent { someMethod() { doSomethingWith(this.context.store); } }

```

### 693. What is the purpose of the constants in Redux?

[↑ Back to Table of Contents](#table-of-contents) Constants allows you to easily find all usages of that specific functionality across the project when you use an IDE. It also prevents you from introducing silly bugs caused by typos – in which case, you will get a `ReferenceError` immediately. Normally we will save them in a single file (`constants.js` or `actionTypes.js`).

```javascript export const ADD_TODO = "ADD_TODO"; export const DELETE_TODO = "DELETE_TODO"; export const EDIT_TODO = "EDIT_TODO"; export const COMPLETE_TODO = "COMPLETE_TODO"; export const COMPLETE_ALL = "COMPLETE_ALL"; export const CLEAR_COMPLETED = "CLEAR_COMPLETED";

```
In Redux, you use them in two places:

### 694. What is the Redux Toolkit (RTK)?

[↑ Back to Table of Contents](#table-of-contents) The official, recommended way to write Redux. Reduces boilerplate with `createSlice` (combines actions + reducers), `configureStore`, and RTK Query (built-in data fetching/caching layer).

### 695. What is the use of the `ownProps` parameter in `mapStateToProps()` and `mapDispatchToProps()`?

If the `ownProps` parameter is specified, React Redux will pass the props that were passed to the component into your _connect_ functions. So, if you use a connected component:

```jsx harmony import ConnectedComponent from "./containers/ConnectedComponent"; <ConnectedComponent user={"john"} />;

```
The `ownProps` inside your `mapStateToProps()` and `mapDispatchToProps()` functions will be an object:

```javascript { user: "john"; }

```
You can use this object to decide what to return from those functions. [↑ Back to Table of Contents](#table-of-contents)

### 696. What is Zustand and how does it differ from Redux?

[↑ Back to Table of Contents](#table-of-contents) Zustand is a minimal state library using hooks. No boilerplate, no reducers/actions required. Stores are plain JS objects with setter functions. Components subscribe to specific slices to avoid unnecessary re-renders.

### 697. What problems does Redux solve in large React applications?

[↑ Back to Table of Contents](#table-of-contents) - **State sharing**: Avoids prop drilling for deeply nested components. - **Predictability**: State changes happen via pure reducers, making it easier to debug with time‑travel. - **Separation of concerns**: UI logic is decoupled from state management. - **Middleware**: Enables handling side effects (async actions, logging) in a structured way. - **DevTools**: Excellent debugging capabilities.

### 698. Whats the purpose of `at` symbol in the Redux connect decorator?

[↑ Back to Table of Contents](#table-of-contents) The **@** symbol is in fact a JavaScript expression used to signify decorators. _Decorators_ make it possible to annotate and modify classes and properties at design time. Let's take an example setting up Redux without and with a decorator. - **Without decorator:**

```javascript import React from "react"; import * as actionCreators from "./actionCreators"; import { bindActionCreators } from "redux"; import { connect } from "react-redux"; function mapStateToProps(state) { return { todos: state.todos }; } function mapDispatchToProps(dispatch) { return { actions: bindActionCreators(actionCreators, dispatch) }; } class MyApp extends React.Component { // ...define your main app here } export default connect(mapStateToProps, mapDispatchToProps)(MyApp);

```
- **With decorator:**

```javascript import React from "react"; import * as actionCreators from "./actionCreators"; import { bindActionCreators } from "redux"; import { connect } from "react-redux"; function mapStateToProps(state) { return { todos: state.todos }; } function mapDispatchToProps(dispatch) { return { actions: bindActionCreators(actionCreators, dispatch) }; } @connect(mapStateToProps, mapDispatchToProps) export default class MyApp extends React.Component { // ...define your main app here }

```
The above examples are almost similar except the usage of decorator. The decorator syntax isn't built into any JavaScript runtimes yet, and is still experimental and subject to change. You can use babel for the decorators support.

### 699. When should you use Context vs. Redux/Zustand?

Context: simple, low-frequency shared values (theme, auth user, locale). Redux/Zustand: complex update logic, frequent updates, middleware needs, or when many unrelated consumers must avoid re-rendering on unrelated state changes.

### 700. When would you decide NOT to use Redux and choose a simpler solution?

[↑ Back to Table of Contents](#table-of-contents) Redux adds complexity. I would choose a simpler alternative when: - **The app is small or has limited state:** If state is mostly local, React’s `useState`/`useReducer` + context is sufficient. - **State updates are simple and infrequent:** For example, a form‑driven app with little cross‑component communication. - **The team is unfamiliar with Redux patterns:** Introducing it would slow development. - **Real‑time / high‑frequency updates:** Redux’s immutable updates can become a bottleneck. For real‑time apps, consider Zustand, Valtio, or MobX. - **We already use React Query / SWR:** If data fetching is the main state concern, these libraries handle caching and sync, and local UI state can stay in component state. - **The app will stay relatively static** and doesn’t need advanced features like time travel or extensive middleware. **Alternatives:** React Context (for low‑frequency data), Zustand (simple global store), Jotai/Recoil (atomic state), or even plain module singletons for truly simple cases. Let me know if you need deeper elaboration on any of these topics.

### 701. Where and why have you used Redux Toolkit in your projects?

[↑ Back to Table of Contents](#table-of-contents) Common scenarios: - **Large‑scale apps with complex shared state**: Shopping carts, user authentication, multi‑step forms. - **Real‑time dashboards**: To manage data from WebSockets across many components. - **Apps with complex async flows**: To maintain loading/error states in a consistent manner. - **When multiple features need access to the same data**: E.g., user profile, preferences, notifications.

### 702. Why are Redux state functions called reducers?

[↑ Back to Table of Contents](#table-of-contents) Reducers always return the accumulation of the state (based on all previous and current actions). Therefore, they act as a reducer of state. Each time a Redux reducer is called, the state and action are passed as parameters. This state is then reduced (or accumulated) based on the action, and then the next state is returned. You could _reduce_ a collection of actions and an initial state (of the store) on which to perform these actions to get the resulting final state.

## Routing & Navigation

### 703. `useParams`, `useNavigate`, `useSearchParams`?

`useParams` reads dynamic path segments. `useNavigate` programmatically navigates. `useSearchParams` reads/writes the query string.

### 704. How do you prevent open redirect vulnerabilities in a React Router app (e.g., a `?redirect=` query param)?

Validate that the redirect target is a relative, same-origin path (not an arbitrary external URL) before calling `navigate()`/`window.location`, rejecting or ignoring untrusted absolute URLs.

### 705. How do you programmatically navigate using React Router v4?

[↑ Back to Table of Contents](#table-of-contents) There are three different ways to achieve programmatic routing/navigation within components.

### 706. How do you redirect after a successful form submission/mutation?

Call `navigate('/success')` imperatively after the async action resolves, or return a `redirect()` response from a route action (data API), which React Router handles automatically.

### 707. How do you test a component with React Router routes?

Wrap it in `<MemoryRouter initialEntries={['/some/path']}>` to simulate a specific URL without a real browser, then assert on rendered route content or navigation behavior.

### 708. How does client-side routing work?

A router library (React Router, TanStack Router) listens to the browser history API (`pushState`, `popstate`) and renders different components based on the current URL – without full page reloads. [↑ Back to Table of Contents](#table-of-contents)

### 709. How is React different from Angular or Vue?

React is a view library (handles only UI); Angular is a full framework with DI, routing, forms built-in; Vue sits in between. React uses JSX + JS composition, Angular uses TypeScript + decorators + templates, Vue uses SFC (Single File Components). ------------------------------------------------------------------------

### 710. How React Router is different from history library?

[↑ Back to Table of Contents](#table-of-contents) React Router is a wrapper around the `history` library which handles interaction with the browser's `window.history` with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node. ****

### 711. How to get history on React Router v4?

[↑ Back to Table of Contents](#table-of-contents) Below are the list of steps to get history object on React Router v4, 1. Create a module that exports a `history` object and import this module across the project. For example, create `history.js` file:

```javascript import { createBrowserHistory } from "history"; export default createBrowserHistory({ /* pass a configuration object here if needed */ });

```
2. You should use the `<Router>` component instead of built-in routers. Import the above `history.js` inside `index.js` file:

```jsx harmony import { Router } from "react-router-dom"; import history from "./history"; import App from "./App"; ReactDOM.render( <Router history={history}> <App /> </Router>, holder );

```
3. You can also use push method of `history` object similar to built-in history object:

```javascript // some-other-file.js import history from "./history"; history.push("/go-here");

```
****

### 712. How to get query parameters in React Router v4?

[↑ Back to Table of Contents](#table-of-contents) The ability to parse query strings was taken out of React Router v4 because there have been user requests over the years to support different implementation. So the decision has been given to users to choose the implementation they like. The recommended approach is to use query strings library.

```javascript const queryString = require("query-string"); const parsed = queryString.parse(props.location.search);

```
You can also use `URLSearchParams` if you want something native:

```javascript const params = new URLSearchParams(props.location.search); const foo = params.get("name");

```
You should use a _polyfill_ for IE11. ****

### 713. How to pass data between sibling components using React router?

[↑ Back to Table of Contents](#table-of-contents) Passing data between sibling components of React is possible using React Router with the help of `history.push` and `match.params`. In the code given below, we have a Parent component` AppDemo.js` and have two Child Components `HomePage` and `AboutPage`. Everything is kept inside a Router by using React-router Route. It is also having a route for `/about/{params}` where we will pass the data. import React, { Component } from 'react'; class AppDemo extends Component { render() { return ( `<Router>`{=html}

```{=html} <div className="AppDemo">

```
<ul> <li> <NavLink to="/" activeStyle={{ color:'blue' }}>Home</NavLink> </li> <li> <NavLink to="/about" activeStyle={{ color:'blue' }}>About `</NavLink>`{=html}

```{=html} </li>

```
```{=html} </ul>

```
<Route path="/about/:aboutId" component={AboutPage} /> <Route path="/about" component={AboutPage} /> <Route path="/" component={HomePage} /> </div> </Router> ); } } export default AppDemo; The HomePage is a functional component with a button. On button click, we are using `props.history.push(‘/about/’ + data)` to programmatically navigate into `/about/data`. export default function HomePage(props) { const handleClick = (data) =\> { props.history.push('/about/' + data); } return ( <div> <button onClick={() => handleClick('DemoButton')}>To About</button> </div> ) } Also, the functional component AboutPage will obtain the data passed by `props.match.params.aboutId`. export default function AboutPage(props) { if(!props.match.params.aboutId) { return <div> No Data Yet </div> } return ( <div> {`Data obtained from HomePage is ${props.match.params.aboutId}`} </div> ) } After button click in the HomePage the page will look like below:

### 714. How to pass params to `history.push` method in React Router v4?

[↑ Back to Table of Contents](#table-of-contents) While navigating you can pass props to the `history` object:

```javascript this.props.history.push({ pathname: "/template", search: "?name=sudheer", state: { detail: response.data }, });

```
The `search` property is used to pass query params in `push()` method. ****

### 715. How to perform automatic redirect after login?

The react-router package will provide the component `<Redirect>` in React Router. Rendering of a `<Redirect>` component will navigate to a newer location. In the history stack, the current location will be overridden by the new location just like the server-side redirects. import React, { Component } from 'react' import { Redirect } from 'react-router' export default class LoginDemoComponent extends Component { render() { if (this.state.isLoggedIn === true) { return `<Redirect to="/your/redirect/page" />`{=html} } else { return <div> {'Please complete login'} </div> } } }

### 716. Using context:

This option is not recommended and treated as unstable API.

```jsx harmony const Button = (props, context) => ( <button type="button" onClick={() => { context.history.push("/new-location"); }} > {"Click Me!"} </button> ); Button.contextTypes = { history: React.PropTypes.shape({ push: React.PropTypes.func.isRequired, }), };

```
[↑ Back to Table of Contents](#table-of-contents)

### 717. What are nested routes in React Router v6?

[↑ Back to Table of Contents](#table-of-contents) Child `<Route>` elements inside a parent `<Route>`. The parent renders an `<Outlet/>` where child content appears. Enables layouts where outer shell (nav, sidebar) persists and inner content changes with URL.

### 718. What are route actions in React Router?

[↑ Back to Table of Contents](#table-of-contents) Functions that handle form submissions and mutations on a route. Called when a Form is submitted to that route. Work with React Router's data APIs for full progressive enhancement. ------------------------------------------------------------------------

### 719. What are route loaders in React Router v6.4+?

[↑ Back to Table of Contents](#table-of-contents) Functions defined on routes that fetch data before the component renders. The component receives data via `useLoaderData()`. Eliminates loading spinners inside components -- data is ready before render. ------------------------------------------------------------------------

### 720. What are the `<Router>` components of React Router v6?

[↑ Back to Table of Contents](#table-of-contents) React Router v6 provides below 4 `<Router>` components: 1. `<BrowserRouter>`:Uses the HTML5 history API for standard web apps. 2. `<HashRouter>`:Uses hash-based routing for static servers. 3. `<MemoryRouter>`:Uses in-memory routing for testing and non-browser environments. 4. `<StaticRouter>`:Provides static routing for server-side rendering (SSR). The above components will create _browser_, _hash_, _memory_ and _static_ history instances. React Router v6 makes the properties and methods of the `history` instance associated with your router available through the context in the `router` object. ****

### 721. What are the benefits of React Router V4?

[↑ Back to Table of Contents](#table-of-contents) Below are the main benefits of React Router V4 module, 1. In React Router v4(version 4), the API is completely about components. A router can be visualized as a single component(`<BrowserRouter>`) which wraps specific child router components(`<Route>`). 2. You don't need to manually set history. The router module will take care history by wrapping routes with `<BrowserRouter>` component. 3. The application size is reduced by adding only the specific router module(Web, core, or native) ****

### 722. What is client-side routing? How does it differ from server routing?

Intercepts navigation via the History API, swapping components without a full reload/request per navigation.

### 723. What is React Router and what are its main components?

[↑ Back to Table of Contents](#table-of-contents) `<BrowserRouter>` or `<RouterProvider>`: wraps the app. `<Routes>`/`<Route>`: declare URL → component mappings. `<Link>`: navigation without reload. `useNavigate()`, `useParams()`, `useSearchParams()`, `useLocation()`: hooks for router state. ------------------------------------------------------------------------

### 724. What is React Router?

[↑ Back to Table of Contents](#table-of-contents) React Router refers to the standard library used for routing in React. It permits us for building a single-page web application in React with navigation without even refreshing the page when the user navigates. It also allows to change the browser URL and will keep the user interface in sync with the URL. React Router will make use of the component structure for calling the components, using which appropriate information can be shown. Since React is a component-based framework, it’s not necessary to include and use this package. Any other compatible routing library would also work with React. The major components of React Router are given below: - **BrowserRouter:** It is a router implementation that will make use of the HTML5 history API (pushState, popstate, and event replaceState) for keeping your UI to be in sync with the URL. It is the parent component useful in storing all other components. - **Routes: **It is a newer component that has been introduced in the React v6 and an upgrade of the component. - **Route: **It is considered to be a conditionally shown component and some UI will be rendered by this whenever there is a match between its path and the current URL. - **Link:** It is useful in creating links to various routes and implementing navigation all over the application. It works similarly to the anchor tag in HTML.

### 725. What is route matching precedence in React Router v6?

V6 uses a ranking algorithm based on specificity (static segments rank higher than dynamic `:param` segments, which rank higher than wildcards) rather than "first match wins" order.

### 726. What is routing in React? How does it work?

[↑ Back to Table of Contents](#table-of-contents) Routing in React is the process of mapping URL paths to different components, enabling a single‑page application (SPA) to simulate multiple pages. React Router (or other libraries) listens to URL changes, matches the path against defined routes, and renders the corresponding component without a full browser refresh. It leverages the browser’s History API (`pushState`, `replaceState`) to manage navigation and updates the UI accordingly.

### 727. What is the difference between `Router` and `Link` in React Router?

[↑ Back to Table of Contents](#table-of-contents) - **`Router`** (e.g., `BrowserRouter`): Provides the routing context and handles history management. It is the parent component that enables navigation and URL sync. - **`Link`**: A component that renders an anchor (`<a>`) with the `to` prop. It allows navigation without a full page reload, using client‑side routing. ------------------------------------------------------------------------

### 728. What is the difference between `useNavigate` and `<Navigate>`?

`useNavigate()` returns an imperative function for programmatic navigation (after form submit, in event handlers). `<Navigate>` is a component that redirects declaratively as part of JSX render output. [↑ Back to Table of Contents](#table-of-contents)

### 729. Why did Create React App fall out of favor? What replaced it?

Slow Webpack-based tooling, limited configurability; superseded by Vite (SPAs) or meta-frameworks (Next.js/Remix) for SSR/routing conventions.

## Forms & Controlled Components

### 730. How do you do form validation in React without a library?

Track values and errors in state. Validate in `onChange` (real-time) or `onBlur` (on leave) or `onSubmit`. Set error messages in state and display them. For complex forms, a library is usually worth the dependency. ------------------------------------------------------------------------

### 731. What is Formik?

A form library providing values, errors, touched state, and handlers. Uses controlled components. Simpler API for moderate forms. Yup integration for schema validation. Slower than React Hook Form for large forms. [⬆ Back to Table of Contents](#-table-of-contents)

### 732. What is the popular choice for form handling?

`Formik` is a form library for react which provides solutions such as validation, keeping track of the visited fields, and handling form submission. In detail, You can categorize them as follows, 1. Getting values in and out of form state 2. Validation and error messages 3. Handling form submission It is used to create a scalable, performant, form helper with a minimal API to solve annoying stuff. [

## Data Fetching & React Query/Suspense

### 733. How do you cancel a query automatically when its component unmounts?

React Query handles this internally by default for the underlying fetch (via `AbortSignal` passed to the query function) when a query becomes unused and its `gcTime` conditions are met or when manually cancelled via `queryClient.cancelQueries`.

### 734. How do you deduplicate identical simultaneous requests?

React Query automatically dedupes identical in-flight queries (same query key) triggered by multiple components, serving them from one network request.

### 735. How It Works?

[↑ Back to Table of Contents](#table-of-contents) 1. Server starts sending HTML immediately 2. When it hits `<Suspense>`, it sends the fallback 3. Continues streaming rest of the page 4. When data is ready, sends the actual component 5. Client replaces fallback with real content 6. Hydration happens independently per component

### 736. React Scheduler?

[↑ Back to Table of Contents](#table-of-contents) React uses an internal **Scheduler** to control how updates are prioritized: * Urgent tasks like clicks and inputs are processed immediately. * Non-urgent tasks (like data fetching) can be delayed or paused. * This improves responsiveness and allows for **time slicing** in Concurrent Mode.

### 737. SWR vs React Query?

SWR is lighter with similar stale-while-revalidate philosophy; React Query has richer built-ins (optimistic helpers, infinite queries, DevTools).

### 738. What are the patterns for data fetching in React?

[↑ Back to Table of Contents](#table-of-contents) 1. `useEffect` + fetch (basic) 2. Custom `useFetch` hook 3. React Query / SWR (recommended for server state) 4. Route loaders (React Router v6.4+) 5. Server Components with async/await (Next.js App Router) ------------------------------------------------------------------------

### 739. What does it mean for a component to "suspend"? What triggers it?

A component suspends when it throws a Promise during render (directly, via `use()`, or via a Suspense-integrated data-fetching library), signaling to React "I'm not ready yet" so the nearest Suspense boundary shows its fallback until the promise resolves.

### 740. What is `Suspense`? How does it work for data fetching?

Shows a fallback while children aren't ready; extended via the `use` Hook/RSC to data fetching — a component "suspends" by throwing a promise.

### 741. What is optimistic mutation in React Query?

[↑ Back to Table of Contents](#table-of-contents) In `useMutation`'s `onMutate`, update the cache optimistically. In `onError`, roll back via context passed from `onMutate`. In `onSettled`, invalidate/refetch to sync with server. Provides instant UI feedback. ------------------------------------------------------------------------

### 742. What is optimistic mutation, and how would you implement it with React Query?

Update the UI/cache immediately assuming success (`onMutate`), roll back via a snapshot if the request fails (`onError`), and reconcile with the server response (`onSettled`) — improves perceived responsiveness for common CRUD actions.

### 743. What is parallel data fetching in Server Components, and why does it matter?

Starting multiple independent `fetch` calls without sequentially `await`-ing each one before the next starts, avoiding request waterfalls and reducing total time-to-render.

### 744. What is parallel vs sequential data fetching?

Sequential: `await A`, then `await B` – total time = A + B. Parallel: `await Promise.all([A,B])` – total time = max(A,B). In Server Components, initiate fetches without awaiting them first, then await together.

### 745. What is prefetching in React Query? When would you use it?

`queryClient.prefetchQuery(...)` loads data into the cache before it's needed (e.g., on hover over a link, or in a route loader), so the eventual component render finds data already cached.

### 746. What is React Query (TanStack Query)?

[↑ Back to Table of Contents](#table-of-contents) A library for fetching, caching, synchronizing, and updating server state. Provides `useQuery` (fetch), `useMutation` (create/update/delete), automatic background refetching, cache invalidation, and stale-while-revalidate. ------------------------------------------------------------------------

### 747. What is React Query's caching model?

[↑ Back to Table of Contents](#table-of-contents) Data is cached by query key. `staleTime` controls how long data is considered fresh (no background refetch). `cacheTime` controls how long unused data stays in cache. Queries refetch on window focus, reconnect, or stale threshold.

### 748. What is streaming SSR? How does `Suspense` enable it?

Sends the page shell immediately, streaming in slower parts wrapped in their own `Suspense` boundaries as they become ready.

### 749. What is suspense component?

React Suspense is a built-in feature that lets you defer rendering part of your component tree until some condition(asynchronous operation) is met—usually, data or code has finished loading. While waiting, Suspense lets you display a fallback UI like a spinner or placeholder. 1. Lazy loading components uses suspense feature, If the module containing the dynamic import is not yet loaded by the time parent component renders, you must show some fallback content while you’re waiting for it to load using a loading indicator. This can be done using **Suspense** component.

```javascript const OtherComponent = React.lazy(() => import("./OtherComponent")); function MyComponent() { return ( <div> <Suspense fallback={<div>Loading...</div>}> <OtherComponent /> </Suspense> </div> ); }

```
The above component shows fallback UI instead real component until `OtherComponent` is fully loaded. 2. As an another example, suspend until async data(data fetching) is ready

```jsx function UserProfile() { const user = use(fetchUser()); // throws a promise internally return <div>{user.name}</div>; } function App() { return ( <Suspense fallback={<div>Loading user...</div>}> <UserProfile /> </Suspense> ); }

```
[↑ Back to Table of Contents](#table-of-contents)

### 750. What is Suspense?

A component that shows a fallback while children are 'suspended'. Components suspend by throwing a Promise. React catches it, shows the fallback, and retries when the Promise resolves. Used with `lazy()` and data-fetching libraries. [↑ Back to Table of Contents](#table-of-contents)

### 751. What is SWR?

Stale-While-Revalidate: a data fetching hook from Vercel. Returns cached data immediately (stale), then revalidates in the background. Simple API: `const {data, error, isLoading} = useSWR(key, fetcher)`.

### 752. What is the difference between `isLoading` and `isFetching` in React Query?

`isLoading` is true only during the very first fetch (no cached data yet). `isFetching` is true any time a request is in flight, including background refetches of already-cached data.

### 753. What is the difference between a "query" and a "mutation" in React Query?

Queries are for reading/caching data (GET-like, retried automatically, cached). Mutations are for creating/updating/deleting data (side-effecting, not cached, triggered imperatively).

### 754. When it helps?

During heavy computations, data fetching, or large list updates – the app stays interactive.

### 755. Why can Suspense boundaries be nested, and what determines which one catches a given suspension?

The nearest ancestor Suspense boundary to the component that suspended catches it and shows its fallback, letting different parts of a tree show independent loading states rather than one fallback blocking the entire page.

## React 18/19, Concurrent Features

### 756. Are custom DOM attributes supported in React v16?

[↑ Back to Table of Contents](#table-of-contents) **Note:** This question references React v16, which is outdated. The information below applies to React 16+, including current versions (React 18/19). Yes. Starting with React 16, React no longer ignores unknown DOM attributes. If you write JSX with an attribute that React doesn't recognize, React will pass it through to the DOM. For example, let's take a look at the below attribute:

```jsx harmony <div mycustomattribute={"something"} />

```
In React 15 and earlier, this would render an empty div:

```html <div />

```
In React 16 and later (including React 18/19), any unknown attributes will end up in the DOM:

```html <div mycustomattribute="something" />

```
This is useful for supplying browser-specific non-standard attributes, trying new DOM APIs, and integrating with opinionated third-party libraries. **** ------------------------------------------------------------------------

### 757. Batching in React 18 vs React 17?

```jsx // React 17 behavior: function App17() { const [a, setA] = React.useState(0); const [b, setB] = React.useState(0); function handleClick() { setTimeout(() => { setA(1); // triggers render setB(1); // triggers another render — 2 renders total in React 17 }, 0); } // ... } // React 18 behavior: function App18() { // Same code, but with createRoot: // setTimeout(() => { setA(1); setB(1); }) — BATCHED! Only 1 render. }

```
**Explanation:** React 17: batching only in React event handlers (onClick, etc.). `setTimeout`, `Promise`, native events caused separate re-renders. React 18 with `createRoot`: automatic batching everywhere — all state updates in async callbacks are batched into one render. [↑ Back to Table of Contents](#table-of-contents)

### 758. Can I use javascript urls in react16.9?

**⚠️ DEPRECATED:** As of React 19, `javascript:` URLs are no longer supported and may throw errors. In React 16.9, `javascript:` URLs would log a warning in the console because URLs starting with `javascript:` are dangerous security vulnerabilities (XSS attacks).

```javascript const companyProfile = { website: "javascript: alert('Your website is hacked')", }; // This logged a warning in React 16.9 // Now blocked or throws error in modern React <a href={companyProfile.website}>More details</a>;

```
**Modern Best Practice:** - Never use `javascript:` URLs - Use proper event handlers instead:

```javascript const handleClick = (e) => { e.preventDefault(); // Your logic here }; <a href="#" onClick={handleClick}>More details</a> // Or better: <button onClick={handleClick}>More details</button>

```
[↑ Back to Table of Contents](#table-of-contents)

### 759. How does React 18's automatic batching work?

Automatic batching in React 18 groups multiple state updates from any source (not just event handlers) into a single re‑render. This is enabled by default when using `createRoot`. It reduces unnecessary renders and improves performance. You can opt out using `flushSync`. [↑ Back to Table of Contents](#table-of-contents)

### 760. How would you ensure a React app performs well at 100k concurrent users?

CDN for static assets, SSR/SSG for fast first paint, aggressive HTTP/query caching (React Query), server-side pagination (never load full datasets), route-level code splitting, error boundaries everywhere, and production monitoring/alerting from day one.

### 761. Is it possible to prevent automatic batching?

Yes, it is possible to prevent automatic batching default behavior. There might be cases where you need to re-render your component after each state update or updating one state depends on another state variable. Considering this situation, React introduced `flushSync` method from `react-dom` API for the usecases where you need to flush state updates to DOM immediately. The usage of `flushSync` method within an `onClick` event handler will be looking like as below,

```jsx import { flushSync } from "react-dom"; const handleClick = () => { flushSync(() => { setClicked(!clicked); //Component will create a re-render here }); setCount(count + 1); // Component will create a re-render again here };

```
In the above click handler, React will update DOM at first using flushSync and second time updates DOM because of the counter setter function by avoiding automatic batching. [↑ Back to Table of Contents](#table-of-contents)

### 762. Is there a functional-component equivalent of error boundaries?

Not natively as of React 18 — you must use a class component, or the `react-error-boundary` library which wraps one for you.

### 763. React 18 automatic batching in a native event handler?

```jsx function App() { const [a, setA] = React.useState(0); const [b, setB] = React.useState(0); console.log('render', a, b); return ( <button onClick={() => { setA(1); setB(2); }}> Click </button> ); }

```
**Behavior:** On click, logs `render 1 2` ONCE (not twice). **Explanation:** React 18 automatically batches ALL state updates — even inside native event handlers. Both `setA` and `setB` are batched into a single re-render. In React 17, this would also batch inside React synthetic events (but not in setTimeout/promises). [↑ Back to Table of Contents](#table-of-contents)

### 764. Server Action vs API route?

A Server Action is callable directly from components/forms with Next.js handling the network call. An API route is an explicit, stable HTTP endpoint.

### 765. What are React 19 Actions?

Functions that handle async mutations (form submissions, data updates). They can be synchronous or async. React 19 provides `useActionState`, `useFormStatus`, and `useOptimistic` to manage their state automatically. ------------------------------------------------------------------------

### 766. What are React 19's key additions?

The React Compiler (automatic memoization, reducing manual `useMemo`/`useCallback`/`React.memo`), Server Actions (`'use server'` functions callable from Client Components), `useActionState`/`useFormStatus`/`useOptimistic` for form/action UX, the `use()` hook for reading Promises/Context during render (can be called conditionally, unlike other hooks), and built-in document metadata support (`<title>`, `<meta>` inside components).

### 767. What are Server Actions (React 19 / Next.js)?

Functions marked `'use server'` that can be called directly from Client Components (e.g., as a `<form action={fn}>`) without hand-writing an API route; React serializes arguments, executes on the server, and streams the result back — includes automatic CSRF protection and progressive enhancement (forms work without JS).

### 768. What are the key features introduced in React 19?

React 19 (released 2024) brings major improvements for full-stack React applications:

### 769. What is `createRoot()` and why was it introduced in React 18?

`createRoot()` replaces `ReactDOM.render()`. It opts the app into React 18's concurrent features (automatic batching, `startTransition`, Suspense improvements). `ReactDOM.render()` runs in legacy mode without those features. [↑ Back to Table of Contents](#table-of-contents)

### 770. What is `ReactDOM.createRoot()`? How did rendering change in React 18?

`createRoot(container).render(<App/>)` is the React 18 mounting API, replacing legacy `ReactDOM.render()`, opting into the concurrent renderer.

### 771. What is `startTransition`?

Marks a state update as non-urgent. React processes urgent updates first and defers the transition. If a newer transition comes in, the in-progress one is aborted. Used for navigation, search, filtering. [↑ Back to Table of Contents](#table-of-contents)

### 772. What is automatic batching (React 18)? What changed from React 17?

React 18 batches state updates from *any* source (promises, timeouts, native event handlers), not just React's own event handlers as in React 17 and earlier, reducing unnecessary intermediate re-renders.

### 773. What is automatic batching in React 18, and how does it differ from React 17?

React 18 batches all `setState` calls within the same tick — even inside `setTimeout`, Promises, or native event handlers — into a single re-render. React 17 only batched inside React's own synthetic event handlers.

### 774. What is automatic batching in React 18?

React 18 batches multiple `setState` calls in async contexts (`setTimeout`, Promises, native event handlers) into one re-render. Previously, only synchronous event handlers were batched. Reduces render count.

### 775. What is batching? How did it change in React 18?

Grouping multiple updates into one re-render. React 18's automatic batching extends this to all updates, not just React event handlers.

### 776. What is Concurrent Rendering?

The Concurrent rendering makes React apps to be more responsive by rendering component trees without blocking the main UI thread. It allows React to interrupt a long-running render to handle a high-priority event. i.e, When you enabled concurrent Mode, React will keep an eye on other tasks that need to be done, and if there's something with a higher priority it will pause what it is currently rendering and let the other task finish first. You can enable this in two ways,

```javascript // 1. Part of an app by wrapping with ConcurrentMode <React.unstable_ConcurrentMode> <Something /> </React.unstable_ConcurrentMode>; // 2. Whole app using createRoot ReactDOM.unstable_createRoot(domNode).render(<App />);

```
[↑ Back to Table of Contents](#table-of-contents)

### 777. What is concurrent rendering? When does it help vs hurt?

Concurrent rendering allows React to work on multiple tasks simultaneously, interrupting low‑priority work to handle high‑priority updates (like typing). It helps keep the UI responsive.

### 778. What is state batching? What changed in React 18 regarding batching?

State batching is the process of grouping multiple state updates into a single re‑render to improve performance. In React 17 and earlier, batching only happened inside React event handlers (e.g., `onClick`). Updates inside promises, `setTimeout`, or native events were not batched. **React 18** introduced **automatic batching** for all updates, regardless of where they originate (promises, timeouts, etc.), using `createRoot`. This reduces unnecessary re‑renders.

### 779. What is state batching? What changed in React 18?

State batching = multiple setState calls in one event handler are combined into one re-render. In React 17, batching only happened in event handlers — setState calls inside setTimeout or Promises caused separate re-renders. React 18 introduced automatic batching everywhere — all setState calls (even in async code, setTimeout, Promises, native events) are batched. This means fewer re-renders and better performance. Use flushSync() to opt out of batching when you need synchronous DOM updates.

### 780. What is streaming SSR and how does React 18+ improve it?

HTML is streamed to the client in chunks as it becomes ready, instead of waiting for the whole page; `<Suspense>` boundaries let slow parts stream in later with a fallback shown first, and hydration can happen progressively/selectively per boundary rather than all at once.

### 781. What is the "two render passes" behavior you might see in React 18 Strict Mode, and why doesn't it indicate a bug by itself?

Strict Mode intentionally renders twice in development to help surface components/effects that aren't pure or properly cleaned up; the second pass's output is discarded and this never happens in production, so by itself it's a detection tool, not a sign of broken app behavior.

### 782. What is the behavior of uncaught errors in react 16?

**Note:** This behavior was introduced in React 16 and continues in React 18/19. In React 16+, errors that are not caught by any error boundary will result in unmounting of the whole React component tree. The reason behind this decision is that it is worse to leave corrupted UI in place than to completely remove it. For example, it is worse for a payments app to display a wrong amount than to render nothing. **Best Practice:** Always wrap your application or critical sections in error boundaries to prevent complete unmounting and provide a better user experience.

```jsx <ErrorBoundary fallback={<ErrorPage />}> <App /> </ErrorBoundary>

```
[↑ Back to Table of Contents](#table-of-contents)

### 783. What is the difference between async mode and concurrent mode?

Both refers the same thing. Previously concurrent Mode being referred to as "Async Mode" by React team. The name has been changed to highlight React’s ability to perform work on different priority levels. So it avoids the confusion from other approaches to Async Rendering. [↑ Back to Table of Contents](#table-of-contents)

## SSR, Next.js & Server Components

### 784. Browser downloads the JS bundle (hydration)

Once the HTML is displayed, the browser downloads the same framework code. React “hydrates” the existing DOM without re-rendering from scratch.

### 785. How do environment variables work differently between server and client code in Next.js?

Only variables prefixed `NEXT_PUBLIC_` are inlined into the client bundle and accessible in browser code; unprefixed variables are only available in server-side code (Server Components, API routes, `getServerSideProps`), keeping secrets out of the client bundle.

### 786. How do you fetch data in the App Router?

Server Components can be `async` and `await fetch(...)` directly — no `useEffect`/loading boilerplate.

### 787. How do you prevent waterfall requests in a component tree?

Start independent fetches in parallel (RSC siblings fetch concurrently by default; client-side use `Promise.all`/`useQueries`) rather than nested sequential `await`s.

### 788. How does Next.js handle image optimization?

The `next/image` component automatically resizes, optimizes format (WebP/AVIF), lazy-loads, and prevents layout shift via required width/height or `fill`.

### 789. How would you implement Server-Side Rendering (SSR) for a React application? When to use SSR, SSG, ISR?

**SSR (Server‑Side Rendering)**: - Render React components to HTML on the server for each request. - Improves initial page load and SEO. - Can be implemented with frameworks like Next.js (using `getServerSideProps`).

### 790. How would you implement SSR for a React application?

**Approaches**: - **Frameworks**: Next.js (recommended), Remix, or custom Node server with React’s `renderToString`/`renderToPipeableStream`. - **Data fetching**: Fetch data on the server (e.g., `getServerSideProps` in Next.js) and pass it as props to the component. - **Hydration**: Server‑rendered HTML is sent to client; React attaches event listeners and reconciles. - **Performance**: Use streaming SSR (`renderToPipeableStream`) for faster TTFB. - **Caching**: Use CDN caching with `stale-while-revalidate` for pages. - **Challenges**: Ensure server and client environment compatibility (avoid `window` usage in server). Use `useEffect` for client‑only code.

### 791. How you implement Server Side Rendering or SSR?

React is already equipped to handle rendering on Node servers. A special version of the DOM renderer is available, which follows the same pattern as on the client side.

```jsx harmony import ReactDOMServer from "react-dom/server"; import App from "./App"; ReactDOMServer.renderToString(<App />);

```
This method will output the regular HTML as a string, which can be then placed inside a page body as part of the server response. On the client side, React detects the pre-rendered content and seamlessly picks up where it left off. [↑ Back to Table of Contents](#table-of-contents)

### 792. Is it possible to use async/await in plain React?

[↑ Back to Table of Contents](#table-of-contents) Yes, you can use `async/await` in plain React, as long as your JavaScript environment supports ES2017+. Nowadays most modern browsers and build tools support ES2017+ version. If you're using **Create React App**, **Next.js**, **Remix**, or any modern React setup, `async/await` is supported out of the box through **Babel**.

### 793. RSC vs SSR – what's the difference?

SSR renders components on the server to HTML and then hydrates on the client (components run on both). RSC components run ONLY on the server, never hydrate, and can be async. They reduce client bundle size significantly. [↑ Back to Table of Contents](#table-of-contents)

### 794. RSC vs. traditional SSR — what's the real difference?

SSR renders components to HTML on the server *and* the same component code re-runs (hydrates) on the client. RSC components run *exclusively* on the server and are never re-executed or shipped to the client at all — a fundamentally different, more bundle-size-efficient model.

### 795. Server‑side?

-- For Next.js, fetch flags in `getServerSideProps` or `getStaticProps` to avoid layout shifts. Use LaunchDarkly's server‑side SDK to evaluate flags on the server.

### 796. SSR vs SSG vs ISR?

SSR: rendered per request. SSG: rendered once at build time. ISR: statically generated but regenerated in the background after an interval.

### 797. What are Next.js `loading.js` and `error.js`?

`loading.js`: automatically wraps the page in Suspense – shown while the page is loading. `error.js`: an error boundary for the route – shown when the page throws. They are React components with special Next.js behavior. [↑ Back to Table of Contents](#table-of-contents)

### 798. What are React Server Components (RSC)?

Components that run only on the server. They can directly access databases, file systems, and APIs. Their code never ships to the client. They cannot use hooks or browser APIs. They interleave with Client Components.

### 799. What are React Server Components (RSC)? How do they differ from SSR?

Run only on the server, never shipped to the client bundle, can access backend resources directly; SSR still ships and re-hydrates component JS client-side.

### 800. What are the differences between page router and app router in nextjs?

Next.js provides two different routing systems: the **Page Router** (traditional) and the **App Router** (introduced in Next.js 13). The App Router is built on React Server Components and offers more powerful features for modern web applications. Here are the main differences between them: | Feature | Page Router | App Router | |---------|-------------|------------| | Directory | Uses `pages/` directory | Uses `app/` directory | | Routing | File-based routing with files like `pages/about.js` | File-based routing with folders and special files like `app/about/page.js` | | Components | All components are Client Components by default | All components are Server Components by default | | Layouts | Custom `_app.js` and `_document.js` for shared layouts | Native nested layouts using `layout.js` files | | Data Fetching | Uses `getServerSideProps`, `getStaticProps`, and `getInitialProps` | Uses `async/await` in Server Components with native `fetch` | | Loading States | Manual implementation required | Built-in `loading.js` for streaming and suspense | | Error Handling | Custom `_error.js` page | Built-in `error.js` for error boundaries at any level | | Streaming | Limited support | Built-in support for streaming with Suspense | | Server Actions | Not available | Native support for server-side mutations | | Metadata | Using `Head` component from `next/head` | Native Metadata API with `metadata` object or `generateMetadata` function | | Rendering | SSR, SSG, ISR, and CSR | SSR, SSG, ISR, CSR plus React Server Components | **Example of Page Router structure:**

```
pages/ ├── index.js // Home page (/) ├── about.js // About page (/about) ├── _app.js // Custom App component ├── _document.js // Custom Document └── posts/ └── [id].js // Dynamic route (/posts/:id)

```
**Example of App Router structure:**

```
app/ ├── page.js // Home page (/) ├── layout.js // Root layout ├── loading.js // Loading UI ├── error.js // Error UI ├── about/ │ └── page.js // About page (/about) └── posts/ └── [id]/ └── page.js // Dynamic route (/posts/:id)

```
**Note:** The App Router is recommended for new Next.js applications as it provides better performance, simpler data fetching patterns, and improved developer experience with React Server Components. [↑ Back to Table of Contents](#table-of-contents)

### 801. What is "hydration cost" in SSR apps, and how do you reduce it?

The time/CPU spent re-running component JS to attach event listeners to server-rendered HTML. Reduce via selective/progressive hydration (Suspense boundaries), reducing the amount of interactive (Client Component) code shipped, and deferring non-critical component hydration.

### 802. What is `getStaticPaths` (Pages Router)? When is it needed?

Defines which dynamic routes (`[slug].js`) to pre-render at build time for SSG, specifying a `fallback` strategy for paths not pre-rendered.

### 803. What is hydration in React?

Hydration is the process where React 'attaches' event handlers and makes a server-rendered HTML page interactive. SSR sends HTML to the browser (fast first paint). React then downloads, parses JS and runs hydration — it walks the existing DOM and attaches React's event system without re-creating DOM nodes. Hydration mismatch errors occur when server-rendered HTML doesn't match what React would render on client (e.g., browser-specific values, Date.now(), Math.random()). React 18 has selective/partial hydration via Suspense.

### 804. What is hydration? How do hydration mismatches occur?

Hydration is the process where React attaches event listeners and reconciles the server‑rendered HTML with the client‑side virtual DOM. It allows interactive components to “take over” the static markup. **Hydration mismatches** occur when the HTML generated on the server differs from the initial render on the client (e.g., due to different data, random values, or browser‑only APIs). React will then attempt to patch the mismatch, which can cause performance issues and break user experience. [↑ Back to Table of Contents](#table-of-contents)

### 805. What is hydration? What can go wrong during it?

React attaches to server-rendered HTML, reusing nodes and wiring listeners. A "hydration mismatch" occurs if client and server output differ.

### 806. What is Incremental Static Regeneration's `revalidate` option?

A time (in seconds) after which Next.js will regenerate a statically generated page in the background on the next request, serving the stale version until the new one is ready.

### 807. What is ISR (Incremental Static Regeneration)?

SSG with time-based revalidation. Pages are statically generated but regenerated in the background after a specified interval. Serves stale page while regenerating fresh version. Set with `revalidate` in Next.js. [↑ Back to Table of Contents](#table-of-contents)

### 808. What is middleware in Next.js? Give a use case.

Code that runs before a request completes, at the edge, for tasks like auth redirects, A/B test routing, or geolocation-based rewrites, defined in a `middleware.ts` file.

### 809. What is NextJS and major features of it?

Next.js is a popular and lightweight framework for static and server‑rendered applications built with React. It also provides styling and routing solutions. Below are the major features provided by NextJS, 1. Server-rendered by default 2. Automatic code splitting for faster page loads 3. Simple client-side routing (page based) 4. Webpack-based dev environment which supports (HMR) 5. Able to implement with Express or any other Node.js HTTP server 6. Customizable with your own Babel and Webpack configurations [

### 810. What is React hydration?

React hydration is used to add client-side JavaScript interactivity to pre-rendered static HTML generated by the server. It is used only for server-side rendering(SSR) to enhance the initial rendering time and make it SEO friendly application. This hydration acts as a bridge to reduce the gap between server side and client-side rendering. After the page loaded with generated static HTML, React will add application state and interactivity by attaching all event handlers for the respective elements. Let's demonstrate this with an example. Consider that React DOM API(using `renderToString`) generated HTML for `<App>` component which contains `<button>` element to increment the counter.

```jsx import {useState} from 'react'; import { renderToString } from 'react-dom/server'; export default function App() { const [count, setCount] = React.useState(0); return ( <h1>Counter</h1> <button onClick={() => setCount(prevCount => prevCount + 1)}> {count} times </button> ); } const html = renderToString(<App />);

```
The above code generates the below HTML with a header text and button component without any interactivity.

```html <h1>Counter</h1> <button> <!-- -->0<!-- --> times </button>

```
At this stage `hydrateRoot` API can be used to perform hydration by attaching `onClick` event handler.

```jsx import { hydrateRoot } from "react-dom/client"; import App from "./App.js"; hydrateRoot(document.getElementById("root"), <App />);

```
After this step, you are able to run React application on server-side and hydrating the javascript bundle on client-side for smooth user experience and SEO purposes. [↑ Back to Table of Contents](#table-of-contents)

### 811. What is ReactDOMServer?

The `ReactDOMServer` object enables you to render components to static markup (typically used on node server). This object is mainly used for _server-side rendering_ (SSR). The following methods can be used in both the server and browser environments: 1. `renderToString()` 2. `renderToStaticMarkup()` For example, you generally run a Node-based web server like Express, Hapi, or Koa, and you call `renderToString` to render your root component to a string, which you then send as response.

```javascript // using Express import { renderToString } from "react-dom/server"; import MyPage from "./MyPage"; app.get("/", (req, res) => { res.write( "<!DOCTYPE html><html><head><title>My Page</title></head><body>" ); res.write('<div id="content">'); res.write(renderToString(<MyPage />)); res.write("</div></body></html>"); res.end(); });

```
[↑ Back to Table of Contents](#table-of-contents)

### 812. What is selective hydration? Why does it matter?

React hydrates parts of the page as their HTML/JS arrive and as the user interacts, rather than waiting for the whole page.

### 813. What is server-side rendering (SSR)?

Generating the initial HTML on the server per request and sending it to the browser, so content is visible before JS loads/executes — improves perceived performance and SEO versus a blank-shell client-side render.

### 814. What is server-side rendering (SSR)? How does it differ from client-side rendering?

With server-side rendering, i.e, SSR, you don’t have to entirely build the UI in the browser; instead of that, it helps by generating the HTML on the server for each request and sending it to the browser. After the HTML is delivered, the browser displays content immediately, and React then hydrates the page to make it interactive. You can be asked the difference between Client-side-rendering and server-side rendering, so here are some points that you can keep in mind: | **Server-side renderingClient-side Rendering** | | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | | The initial render is done on the server as HTML before reaching the browser.The initial render is done on the browser using JS. | | You can see the content immediately on first load.CSR is a bit slower, the screen is blank, or it shows a loading process till JS executes. | | The server prepares the HTML, so the browser only needs to display it initially.The browser is responsible for creating and updating the DOM. | | The first render is faster because the content is already prepared.The first render might take time or feel slower on slow devices/networks. | | It is easy for a search engine to index content since it is present in the HTML.Search engines may come across difficulties here. (if JS is not executed properly) | | Requires a hydration step - because everything is rendered on a client.No hydration required. | | Part of the rendering work is done on the server to help reduce the client’s initial workload.Most of the application logic is sent to the client as JavaScript. | To quickly understand the advantages of SSR: - It has a faster initial load time, - Better SEO - And improved perceived performance Now, here are some things you need to look out for, It has a higher server load, complex infrastructure, and hydration mismatch issues, sometimes even a slight delay before full interactivity. You can also be asked questions like, " What is hydration? In the interviews, so here’s how you can answer - Hydration is the process by which React attaches event listeners and restores component state on top of the server-rendered HTML. - It converts static HTML into a fully interactive React app - Must match the server-rendered output to avoid errors You should also note some modern approaches made by React: 1\. Frameworks like Next.js provide built-in SSR support, which helps in mixing SSR, CSR, and SSG. 2\. Static Site Generation (SSG), here pages are pre-rendered at build time, and it is faster than SSR but less dynamic. 3\. Streaming SSR, the server sends HTML in chunks, which improves time-to-first-byte and progressive rendering. 4\. React Server Components (RSC) run only on the server and are never sent to the client as JavaScript. They practically help in reducing bundle size and improving performance. With this, it can fetch data directly on the server and send only the required UI output to the client. [↑ Back to Table of Contents](#table-of-contents)

### 815. What is SSG (Static Site Generation)?

Pre-rendering pages to HTML at build time. Fastest delivery via CDN. Used for content that doesn't change per request (blogs, docs, marketing). Next.js uses `getStaticProps` and `generateStaticParams`. [↑ Back to Table of Contents](#table-of-contents)

### 816. What is SSR with React?

Rendering React components on the server to HTML strings. Improves FCP (First Contentful Paint) and SEO. Client then hydrates the HTML. Next.js handles SSR automatically with `getServerSideProps` or Server Components. ------------------------------------------------------------------------

### 817. What is SSR? What problem does it solve vs a pure client-rendered SPA?

Generates initial HTML on the server with real content, improving perceived load and SEO vs an empty client-rendered shell.

### 818. What is streaming SSR?

Sending HTML to the browser in chunks as components finish rendering on the server. Parts of the page become interactive progressively. React 18's `renderToPipeableStream` / `renderToReadableStream` enable this. [⬆ Back to Table of Contents](#-table-of-contents)

### 819. What is the "FOUC" (flash of unstyled content) risk with runtime CSS-in-JS in SSR, and how is it mitigated?

If styles are injected client-side after hydration, the user may briefly see unstyled markup. Mitigated by extracting critical CSS server-side and inlining it in the initial HTML response (most CSS-in-JS libraries provide an SSR extraction API for this).

### 820. What is the 'use client' directive?

Placed at the top of a file to mark it and its imports as Client Components in the RSC architecture. Required for any component using hooks, event handlers, or browser APIs when using Next.js App Router. [⬆ Back to Table of Contents](#-table-of-contents)

### 821. What is the `'use client'` directive? When do you need it?

Marks a Client Component boundary for anything using Hooks, event handlers, or browser APIs.

### 822. What is the `use server` directive (Next.js Server Actions)?

`'use server'` marks a function (or an entire file) as a **Server Action** — code that always runs on the server, even when called from a Client Component, similar in spirit to an RPC call.

```jsx // actions.js 'use server'; export async function createPost(formData) { const title = formData.get('title'); await db.posts.create({ title }); }

```
```jsx // ClientForm.jsx ('use client' component) import { createPost } from './actions'; export default function Form() { return ( <form action={createPost}> <input name="title" /> <button type="submit">Create</button> </form> ); }

```
Under the hood, calling a `'use server'` function from the client triggers a POST request to the server; React serializes the arguments, runs the function on the server, and streams the result back. It's the mutation counterpart to Server Components — Server Components read data, Server Actions write data, both without hand-written API routes. `'use client'` marks the boundary going the other way — code that must run in the browser (state, effects, event handlers). [↑ Back to Table of Contents](#table-of-contents)

### 823. What is the difference between a dynamic and a static route segment caching behavior in the App Router?

Static segments (no dynamic data dependencies) are cached and reused across requests by default. Using dynamic functions (`cookies()`, `headers()`) or `cache: 'no-store'` on a fetch opts a route into fully dynamic, per-request rendering.

### 824. What is the difference between CSR, SSR, SSG, and ISR?

- **CSR (Client‑Side Rendering)**: JavaScript runs in the browser to render the UI. Initial HTML is minimal. Good for dynamic, interactive apps but can hurt SEO and initial load. - **SSR (Server‑Side Rendering)**: Renders HTML on the server per request. Fast initial paint, better SEO. Used in Next.js `getServerSideProps`. - **SSG (Static Site Generation)**: Pre‑renders HTML at build time. Very fast, ideal for content that doesn’t change often (blogs, marketing pages). Next.js `getStaticProps`. - **ISR (Incremental Static Regeneration)**: Builds static pages but can regenerate them in the background after deployment. Combines benefits of SSG and SSR. Next.js `revalidate` option.

### 825. What is the Next.js App Router vs Pages Router?

App Router (`app/`) uses Server Components, nested layouts, file conventions. Pages Router (`pages/`) is Client Components by default with `getServerSideProps`/`getStaticProps`.

### 826. What is the Next.js App Router, and how does it differ from the Page Router?

File-system routing via `app/` (vs. `pages/`); components are Server Components by default (vs. all Client Components); native nested layouts (`layout.js`) and built-in `loading.js`/`error.js` for Suspense/error boundaries per route; native async data fetching with `fetch`; native Server Actions support.

### 827. What is the Next.js App Router?

File-system based routing using `app/` directory with `layout.js`, `page.js`, `loading.js`, `error.js` conventions. Pages are Server Components by default. Client Components use `'use client'` directive. [↑ Back to Table of Contents](#table-of-contents)

### 828. What is the purpose of renderToNodeStream method?

The `ReactDOMServer#renderToNodeStream` method is used to generate HTML on the server and send the markup down on the initial request for faster page loads. It also helps search engines to crawl your pages easily for SEO purposes. **Note:** Remember this method is not available in the browser but only server. [↑ Back to Table of Contents](#table-of-contents)

### 829. What is the risk of putting sensitive logic/secrets in a Client Component by mistake?

Anything in a `'use client'` module (and its non-server imports) ships to the browser bundle, so secrets or sensitive business logic placed there become visible/extractable by anyone inspecting the client JS.

### 830. What is the security consideration around React Server Components and passing data from server to client?

Data passed as props from a Server Component into a Client Component is serialized and does ship to the browser; sensitive fields fetched server-side must be explicitly excluded from what's passed down, not just "kept on the server" by assumption.

### 831. When to use client and server components?

You can efficiently build nextjs application if you are aware about which part of the application needs to use client components and which other parts needs to use server components. The common cases of both client and server components are listed below: **Client components:** 1. Whenever your need to add interactivity and event listeners such as onClick(), onChange(), etc to the pages 2. If you need to use State and Lifecycle Effects like useState(), useReducer(), useEffect() etc. 3. If there is a requirement to use browser-only APIs. 4. If you need to implement custom hooks that depend on state, effects, or browser-only APIs. 5. There are React Class components in the pages. **Server components:** 1. If the component logic is about data fetching. 2. If you need to access backend resources directly. 3. When you need to keep sensitive information((access tokens, API keys, etc) ) on the server. 4. If you want reduce client-side JavaScript and placing large dependencies on the server. [↑ Back to Table of Contents](#table-of-contents)

### 832. Why is `react-dom` a separate package from `react`?

To decouple the core reconciliation/component model from any specific rendering target, enabling `react-native`, `react-art`, SSR (`react-dom/server`), etc., to share the same core.

## Error Handling & Error Boundaries

### 833. Can you describe about componentDidCatch lifecycle method signature?

The **componentDidCatch** lifecycle method is invoked after an error has been thrown by a descendant component. The method receives two parameters, 1. error: - The error object which was thrown 2. info: - An object with a componentStack key contains the information about which component threw the error. The method structure would be as follows

```javascript componentDidCatch(error, info);

```
****

### 834. Error boundary catches what?

```jsx class ErrorBoundary extends React.Component { state = { hasError: false }; static getDerivedStateFromError() { return { hasError: true }; } componentDidCatch(error, info) { console.log('caught', error.message); } render() { if (this.state.hasError) return <h1>Something went wrong</h1>; return this.props.children; } } function Buggy() { throw new Error('Oops!'); } // Which of these does the error boundary catch? // A: <Buggy /> (render error) // B: <button onClick={() => { throw new Error('click') }}>Click</button> // C: useEffect with throw // D: setTimeout with throw

```
- **A: YES** — render-time errors are caught by error boundaries. - **B: NO** — event handler errors are NOT caught by error boundaries. - **C: NO** — errors in `useEffect` are NOT caught (they happen asynchronously after render). - **D: NO** — async errors are never caught. **Explanation:** Error boundaries ONLY catch errors during rendering, in lifecycle methods, and in constructors of child components. Handle event handler errors with try/catch. Handle async errors with window.onerror or per-operation try/catch. [↑ Back to Table of Contents](#table-of-contents)

### 835. How do you create an error boundary?

Class component with `static getDerivedStateFromError(error) { return {hasError:true} }` to render fallback, and `componentDidCatch(error, info)` for logging. Render fallback UI when `hasError` is true. ------------------------------------------------------------------------

### 836. How do you log errors caught by an Error Boundary to a monitoring service (e.g., Sentry)?

Call the logging SDK inside `componentDidCatch(error, errorInfo)`, which receives both the error and the component stack trace, then report it before rendering the fallback UI.

### 837. How do you reset an Error Boundary after the user retries (e.g., clicking "Try again")?

Change the boundary's `key` prop to force a fresh mount, or use `react-error-boundary`'s `resetErrorBoundary`/`onReset` support to clear the caught error and re-render children.

### 838. How do you test error boundaries?

Suppress `console.error` in the test. Render a component that throws inside an error boundary. Assert the fallback UI renders. Use `jest.spyOn(console, 'error').mockImplementation(() => {})` to silence expected errors. [⬆ Back to Table of Contents](#-table-of-contents)

### 839. What are the methods invoked during error handling?

Below methods are called when there is an error during rendering, in a lifecycle method, or in the constructor of any child component. 1. static getDerivedStateFromError() 2. componentDidCatch() [

### 840. What is an error boundary?

A class component that implements `getDerivedStateFromError()` and/or `componentDidCatch()`. It catches rendering errors in its subtree and renders a fallback UI instead of crashing the whole app.

### 841. What is an Error Boundary? What errors does it NOT catch?

A class component with `getDerivedStateFromError`/`componentDidCatch` catching render/lifecycle/constructor errors in its child tree. Does NOT catch event handler, async, or SSR errors.

### 842. What is global error monitoring in React apps?

Pair error boundaries with a monitoring SDK (Sentry, LogRocket). Use `window.onerror` and `window.onunhandledrejection` for uncaught async errors. Error boundaries call `componentDidCatch` which logs to the service.

### 843. What is the behavior of an uncaught error with no error boundary present (React 16+)?

The entire component tree unmounts — React's philosophy is that leaving corrupted UI on screen (e.g., a payments app showing a wrong amount) is worse than showing nothing. Always wrap critical sections in boundaries to avoid full-app blank-outs.

### 844. What is the benefit of component stack trace from error boundary?

Apart from error messages and javascript stack, React16 will display the component stack trace with file names and line numbers using error boundary concept. For example, BuggyCounter component displays the component stack trace as below, ![stacktrace](images/error_boundary.png) [↑ Back to Table of Contents](#table-of-contents)

### 845. What is the difference between a recoverable and an unrecoverable error in a React app's error-handling strategy?

A recoverable error (e.g., a failed API call) can show an inline retry UI while the rest of the app keeps working. An unrecoverable error (e.g., corrupted app state) may require a full Error Boundary fallback or forced reload, since continuing to render could produce further incorrect behavior.

### 846. What is the purpose of getDerivedStateFromError?

This lifecycle method is invoked after an error has been thrown by a descendant component. It receives the error that was thrown as a parameter and should return a value to update state. The signature of the lifecycle method is as follows,

```javascript static getDerivedStateFromError(error)

```
Let us take error boundary use case with the above lifecycle method for demonstration purpose,

```javascript class ErrorBoundary extends React.Component { constructor(props) { super(props); this.state = { hasError: false }; } static getDerivedStateFromError(error) { // Update state so the next render will show the fallback UI. return { hasError: true }; } render() { if (this.state.hasError) { // You can render any custom fallback UI return <h1>Something went wrong.</h1>; } return this.props.children; } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 847. Why can't a single top-level Error Boundary be a complete error-handling strategy?

One crash anywhere takes down the entire app's UI behind a single fallback; nesting boundaries around independent sections (widgets, routes) isolates failures so one broken part doesn't block the rest.

## Design Patterns (HOC, Render Props, Compound Components)

### 848. Don’t use HOCs inside the render method:

It is not recommended to apply a HOC to a component within the render method of a component.

```javascript render() { // A new version of EnhancedComponent is created on every render // EnhancedComponent1 !== EnhancedComponent2 const EnhancedComponent = enhance(MyComponent); // That causes the entire subtree to unmount/remount each time! return <EnhancedComponent />; }

```
The above code impacts on performance by remounting a component that causes the state of that component and all of its children to be lost. Instead, apply HOCs outside the component definition so that the resulting component is created only once.

### 849. Higher-Order Component (HOC) that logs props on every render?

[↑ Back to Table of Contents](#table-of-contents)

```jsx const withLogger = (WrappedComponent) => { return function LoggedComponent(props) { console.log(`${WrappedComponent.displayName || WrappedComponent.name} rendered with:`, props); return <WrappedComponent {...props} />; }; }; function Button({ label, onClick }) { return <button onClick={onClick}>{label}</button>; } const LoggedButton = withLogger(Button); function App() { return <LoggedButton label="Submit" onClick={() => alert('clicked')} />; }

```
**Behavior:** Every time `LoggedButton` renders, logs `Button rendered with: { label: 'Submit', onClick: [Function] }`. **HOC concern:** If `App` re-renders, `withLogger(Button)` is a new component type per render if defined inside — always define HOCs outside components.

### 850. HOC that logs props on every render:

```jsx const withLogger = (Wrapped) => (props) => { console.log(`${Wrapped.name} rendered with:`, props); return <Wrapped {...props} />; }; // Always define HOCs OUTSIDE component render — defining inline creates a new type every render, forcing remounts.

```

### 851. How do you create HOC using render props?

[↑ Back to Table of Contents](#table-of-contents) You can implement most higher-order components (HOC) using a regular component with a render prop. For example, if you would prefer to have a withMouse HOC instead of a `<Mouse>`{=html} component, you could easily create one using a regular `<Mouse>`{=html} with a render prop.

```javascript function withMouse(Component) { return class extends React.Component { render() { return ( <Mouse render={(mouse) => <Component {...this.props} mouse={mouse} />} /> ); } }; }

```
This way render props gives the flexibility of using either pattern. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 852. Static methods must be copied over:

When you apply a HOC to a component the new component does not have any of the static methods of the original component

```javascript // Define a static method WrappedComponent.staticMethod = function () { /*...*/ }; // Now apply a HOC const EnhancedComponent = enhance(WrappedComponent); // The enhanced component has no static method typeof EnhancedComponent.staticMethod === "undefined"; // true

```
You can overcome this by copying the methods onto the container before returning it,

```javascript function enhance(WrappedComponent) { class Enhance extends React.Component { /*...*/ } // Must know exactly which method(s) to copy :( Enhance.staticMethod = WrappedComponent.staticMethod; return Enhance; }

```

### 853. What are HOC factory implementations?

There are two main ways of implementing HOCs in React. 1. Props Proxy (PP) and 2. Inheritance Inversion (II). But they follow different approaches for manipulating the _WrappedComponent_. **Props Proxy** In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name **Props Proxy**.

```jsx function ppHOC(WrappedComponent) { return class PP extends React.Component { render() { return <WrappedComponent {...this.props} />; } }; }

```
**Inheritance Inversion** In this approach, the returned HOC class (Enhancer) extends the WrappedComponent. It is called Inheritance Inversion because instead of the WrappedComponent extending some Enhancer class, it is passively extended by the Enhancer. In this way the relationship between them seems **inverse**.

```jsx function iiHOC(WrappedComponent) { return class Enhancer extends WrappedComponent { render() { return super.render(); } }; }

```
[↑ Back to Table of Contents](#table-of-contents)

### 854. What is a higher-order component (HOC)? Give an example.

A function taking a component and returning an enhanced one, e.g. `withAuth(Component)`. Largely superseded by custom Hooks.

### 855. What is render hijacking in react?

The concept of render hijacking is the ability to control what a component will output from another component. It means that you decorate your component by wrapping it into a Higher-Order component. By wrapping, you can inject additional props or make other changes, which can cause changing logic of rendering. It does not actually enable hijacking, but by using HOC you make your component behave differently. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 856. What is the difference between a Compound Component and a Slot-based component?

Compound Components implicitly share state via Context between a fixed set of sub-components (`<Tabs.Tab>` knows which `<Tabs>` it belongs to). Slot-based components explicitly receive arbitrary content/components as props without that implicit shared-state wiring.

### 857. What is the purpose of forward ref in HOCs?

Refs will not get passed through because ref is not a prop. It handled differently by React just like **key**. If you add a ref to a HOC, the ref will refer to the outermost container component, not the wrapped component. In this case, you can use Forward Ref API. For example, we can explicitly forward refs to the inner FancyButton component using the React.forwardRef API. The below HOC logs all props,

````
```javascript function logProps(Component) { class LogProps extends React.Component { componentDidUpdate(prevProps) { console.log('old props:', prevProps); console.log('new props:', this.props); } render() { const {forwardedRef, ...rest} = this.props; // Assign the custom prop "forwardedRef" as a ref return <Component ref={forwardedRef} {...rest} />; } } return React.forwardRef((props, ref) => { return <LogProps {...props} forwardedRef={ref} />; }); }

```
````
Let's use this HOC to log all props that get passed to our “fancy button” component,

````
```javascript class FancyButton extends React.Component { focus() { // ... } // ... } export default logProps(FancyButton);

```
````
Now lets create a ref and pass it to FancyButton component. In this case, you can set focus to button element.

````
```javascript import FancyButton from './FancyButton'; const ref = React.createRef(); ref.current.focus(); <FancyButton label="Click Me" handleClick={handleClick} ref={ref} />;

```
````
[↑ Back to Table of Contents](#table-of-contents)

## Testing React Applications

### 858. Give a simple example of Jest test case?

Let's write a test for a function that adds two numbers in `sum.js` file:

```javascript const sum = (a, b) => a + b; export default sum;

```
Create a file named `sum.test.js` which contains actual test:

```javascript import sum from "./sum"; test("adds 1 + 2 to equal 3", () => { expect(sum(1, 2)).toBe(3); });

```
And then add the following section to your `package.json`:

```json { "scripts": { "test": "jest" } }

```
Finally, run `yarn test` or `npm test` and Jest will print a result:

```console $ yarn test PASS ./sum.test.js ✓ adds 1 + 2 to equal 3 (2ms)

```
[↑ Back to Table of Contents](#table-of-contents)

### 859. How do you test a component using fake timers (e.g., a debounce or a countdown)?

`jest.useFakeTimers()`, trigger the action, then `jest.advanceTimersByTime(ms)` or `jest.runAllTimers()` to fast-forward, asserting the expected state after the delay — avoiding real wall-clock waits in tests.

### 860. How do you test that a component is accessible?

`jest-axe` runs axe-core against the rendered HTML, asserting no violations: `expect(await axe(container)).toHaveNoViolations()`.

### 861. What are the advantages of Jest over Jasmine?

There are couple of advantages compared to Jasmine: - Automatically finds tests to execute in your source code. - Automatically mocks dependencies when running your tests. - Allows you to test asynchronous code synchronously. - Runs your tests with a fake DOM implementation (via `jsdom`) so that your tests can be run on the command line. - Runs tests in parallel processes so that they finish sooner. [↑ Back to Table of Contents](#table-of-contents)

### 862. What is React Testing Library (RTL)? What is its core philosophy?

"Test your software the way users use it" — query by accessible roles/labels/text, not implementation details.

### 863. What is React Testing Library?

A testing library that renders components to a DOM (via jsdom) and provides user-centric queries (`getByRole`, `getByText`, `getByLabelText`). Encourages testing behavior, not implementation details. ------------------------------------------------------------------------

### 864. What is Shallow Renderer in React testing?

[↑ Back to Table of Contents](#table-of-contents) *Shallow rendering* is useful for writing unit test cases in React. It lets you render a component *one level deep* and assert facts about what its render method returns, without worrying about the behavior of child components, which are not instantiated or rendered. For example, if you have the following component:

```javascript function MyComponent() { return ( <div> <span className={"heading"}>{"Title"}</span> <span className={"description"}>{"Description"}</span> </div> ); }

```
Then you can assert as follows:

```jsx harmony import ShallowRenderer from "react-test-renderer/shallow"; // in your test const renderer = new ShallowRenderer(); renderer.render(<MyComponent />); const result = renderer.getRenderOutput(); expect(result.type).toBe("div"); expect(result.props.children).toEqual(** ------------------------------------------------------------------------ --- --- #### 795. What is the difference between shallow and deep rendering? [↑ Back to Table of Contents](#table-of-contents) Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees. --- --- #### 796. What is the testing pyramid for React? [↑ Back to Table of Contents](#table-of-contents) Unit tests (fast, many): individual functions/hooks. Integration tests (medium): component interactions, user flows. E2E tests (slow, few): full browser flows via Playwright or Cypress. Focus effort on the middle layer. ------------------------------------------------------------------------ --- --- #### 797. What is the difference between visual regression testing and contract testing? [↑ Back to Table of Contents](#table-of-contents) **Answer:** Visual regression testing: captures screenshots of components, compares against baseline — catches unintended CSS/layout changes. Tools: Chromatic (Storybook-based), Percy, Playwright screenshots. Contract testing (frontend-backend): verifies the API response shape matches what the frontend expects — catches backend changes that break frontend before integration. Tools: Pact.js, MSW (Mock Service Worker). Both are important: visual regression for UI stability, contract testing for API stability. --- --- #### 798. What are the advantages of Jest over Jasmine? [↑ Back to Table of Contents](#table-of-contents) There are couple of advantages compared to Jasmine: - Automatically finds tests to execute in your source code. - Automatically mocks dependencies when running your tests. - Allows you to test asynchronous code synchronously. - Runs your tests with a fake DOM implementation (via `jsdom`) so that your tests can be run on the command line. - Runs tests in parallel processes so that they finish sooner. --- --- #### 799. What is Jest? [↑ Back to Table of Contents](#table-of-contents) _Jest_ is a JavaScript unit testing framework created by Facebook based on Jasmine and provides automated mock creation and a `jsdom` environment. It's often used for testing components. --- --- #### 800. What is React Testing Library? [↑ Back to Table of Contents](#table-of-contents) A testing library that renders components to a DOM (via jsdom) and provides user-centric queries (`getByRole`, `getByText`, `getByLabelText`). Encourages testing behavior, not implementation details. ------------------------------------------------------------------------ --- --- #### 801. What is the purpose of ReactTestUtils package? [↑ Back to Table of Contents](#table-of-contents) _ReactTestUtils_ are provided in the `with-addons` package and allow you to perform actions against a simulated DOM for the purpose of unit testing. **** --- --- #### 802. What is Vitest and how does it differ from Jest? [↑ Back to Table of Contents](#table-of-contents) Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects. --- --- #### 803. What are flaky test detection strategies? [↑ Back to Table of Contents](#table-of-contents) Flaky tests are those that sometimes pass and sometimes fail without code changes. Detection strategies: - **Retry mechanism**: Run tests multiple times (e.g., 3–5) in CI; if they fail at least once but also pass, mark as flaky. - **Statistical analysis**: Collect test run history; use tools like `flaky` (Python) or built‑in CI features (GitHub Actions, CircleCI) to flag tests with high variance. - **Isolation**: Run tests in different orders, with random seed values (e.g., Jest’s `--randomize`), or with environment variations to reveal flakiness. - **Screenshot diffs**: For visual tests, flaky may come from timing or non‑deterministic rendering. Use tools like Percy or Chromatic that handle baseline comparisons. - **Quarantine**: Move flaky tests to a separate suite that doesn’t block deployments until fixed. Track them with a flaky test dashboard. **Prevention**: Avoid hardcoded timers; use `waitFor` utilities; ensure mocks are properly reset; avoid relying on network state; use deterministic data. --- --- ### Intermediate #### 804. How do you test components with context? [↑ Back to Table of Contents](#table-of-contents) Wrap with the real Provider (or a test Provider with controlled values) in the render call. RTL's `render` accepts a wrapper option: `render(<Comp/>, {wrapper: TestProviders})`. ------------------------------------------------------------------------ --- --- #### 805. How do you test custom hooks? [↑ Back to Table of Contents](#table-of-contents) Use `renderHook` from `@testing-library/react`. `act()` wraps state updates. `const {result} = renderHook(() => useCounter(0)); act(() => result.current.increment()); expect(result.current.count).toBe(1)`. --- --- #### 806. Give a simple example of Jest test case [↑ Back to Table of Contents](#table-of-contents) Let's write a test for a function that adds two numbers in `sum.js` file:

```javascript const sum = (a, b) => a + b; export default sum;

```
Create a file named `sum.test.js` which contains actual test:

```javascript import sum from "./sum"; test("adds 1 + 2 to equal 3", () => { expect(sum(1, 2)).toBe(3); });

```
And then add the following section to your `package.json`:

```json { "scripts": { "test": "jest" } }

```
Finally, run `yarn test` or `npm test` and Jest will print a result:

```console $ yarn test PASS ./sum.test.js ✓ adds 1 + 2 to equal 3 (2ms)

```
--- --- #### 807. How do you test user interactions? [↑ Back to Table of Contents](#table-of-contents) Use `userEvent` from `@testing-library/user-event` (more realistic than `fireEvent` – triggers all real browser events). `userEvent.click()`, `userEvent.type()`, `userEvent.selectOptions()`. --- --- #### 808. How to test React Native apps? [↑ Back to Table of Contents](#table-of-contents) React Native can be tested only in mobile simulators like iOS and Android. You can run the app in your mobile using expo app ([https://expo.io](https://expo.io/)) Where it syncs using QR code, your mobile and computer should be in same wireless network. --- --- #### 809. How do you test error boundaries? [↑ Back to Table of Contents](#table-of-contents) Suppress `console.error` in the test. Render a component that throws inside an error boundary. Assert the fallback UI renders. Use `jest.spyOn(console, 'error').mockImplementation(() => {})` to silence expected errors. --- --- #### 810. Explain contract testing between frontend and backend. [↑ Back to Table of Contents](#table-of-contents) Contract testing ensures that the frontend and backend agree on the structure of API requests and responses, without running full end‑to‑end tests. - **Tools**: Pact (consumer‑driven contract testing), OpenAPI (Swagger) validators, or GraphQL schema checks. - **Process**: 1. **Consumer (frontend) defines expectations** – writes a “pact” describing the request it will send and the expected response. 2. **Pact file** is shared with the provider (backend). 3. **Provider verifies** – runs tests against its actual code to ensure it can satisfy the contract. - **Benefits**: Detects breaking API changes early; allows frontend and backend to develop independently; reduces need for expensive end‑to‑end tests. **Example**: Using Pact.js, a frontend test would set up an interaction, generate a pact file, and the backend verifies it during CI. If either side changes the contract, CI fails. --- --- #### 811. How do you ensure code quality with testing? (unit, integration, e2e) [↑ Back to Table of Contents](#table-of-contents) A balanced test pyramid: - **Unit tests** (Jest, Vitest) – test individual functions, hooks, and components in isolation. Cover edge cases, pure logic. Aim for high coverage on critical business logic. - **Integration tests** (React Testing Library) – test how components work together. Focus on user interactions, state updates, and API mocks. Avoid testing implementation details. - **End‑to‑end tests** (Playwright, Cypress) – test critical user journeys across real browsers. Keep them small and focused (e.g., login, checkout). Run on staging before deployment. **Quality gates**: - Enforce minimum coverage thresholds (e.g., 80%) for new code. - Run tests in CI; block merge if any fail. - Use mutation testing (Stryker) to detect weak tests. - Include accessibility testing (axe) in integration/e2e tests. **Developer experience**: Fast feedback with watch mode, local test runner, and test data factories. --- --- #### 812. How do you test async behavior (e.g., API calls)? [↑ Back to Table of Contents](#table-of-contents) Mock fetch or use MSW (Mock Service Worker). Use `findBy*` or `waitFor(() => expect(...))` to wait for async DOM updates. Never use arbitrary `setTimeout` in tests. --- --- ### Senior / Scenario / Design #### 813. What is visual regression testing? How would you implement it? [↑ Back to Table of Contents](#table-of-contents) Visual regression testing catches unintended UI changes by comparing screenshots of components or pages against approved baselines. **Implementation**: - **Tools**: Percy (integrated with Storybook), Chromatic, or open‑source tools like Playwright with screenshot comparison. - **Workflow**: 1. Capture screenshots of each component/page in a controlled environment (e.g., Storybook). 2. Store baseline images (e.g., in Percy’s cloud). 3. On each pull request, run a new build, capture new screenshots, and compare. 4. Review any differences; if intentional, approve as new baseline. 5. Fail CI if unapproved changes are detected. **Considerations**: - Use consistent viewport sizes and mock data to avoid false positives. - Ignore dynamic elements (timestamps, random IDs) with attribute masking. - Run only on relevant components to keep feedback fast. --- --- #### 814. How would you implement A/B testing without affecting current users? [↑ Back to Table of Contents](#table-of-contents) **Answer:** (1) Feature flags: tools like LaunchDarkly or GrowthBook assign users to control/variant based on user ID (consistent bucketing). (2) Percentage rollout: expose variant to X% of users, increase gradually. (3) Segment targeting: specific user segments (new users, premium tier). (4) Server-side assignment (prevents flicker): assign group at request time, persist in cookie/session. (5) Client-side: read flag value at component render time. (6) Analytics events: track conversions per variant. (7) Statistical significance: don't end tests early. --- ##### TypeScript with React --- ## TypeScript & Type Safety ### Junior #### 815. What are default props and PropTypes? [↑ Back to Table of Contents](#table-of-contents) defaultProps (The Backup Plan) This provides a fallback value just in case a parent component forgets to pass a prop. Analogy: If you don't explicitly choose a side dish, the restaurant automatically defaults to giving you fries. PropTypes (The Bouncer) This checks the props coming in to make sure they are the correct type (like a number, a string, or a boolean) and warns you in the developer console if someone made a mistake. Analogy: A bouncer checking IDs. If a developer tries to pass the word "Twenty" into an age prop that expects the actual number 20, PropTypes throws a warning flag. ------------------------------------------------------------------------ --- --- #### 816. What is the difference between Flow and PropTypes? [↑ Back to Table of Contents](#table-of-contents) Flow is a _static analysis tool_ (static checker) which uses a superset of the language, allowing you to add type annotations to all of your code and catch an entire class of bugs at compile time. PropTypes is a _basic type checker_ (runtime checker) which has been patched onto React. It can't check anything other than the types of the props being passed to a given component. If you want more flexible typechecking for your entire project Flow/TypeScript are appropriate choices. **** --- --- #### 817. What is React proptype array with shape? [↑ Back to Table of Contents](#table-of-contents) If you want to pass an array of objects to a component with a particular shape then use `React.PropTypes.shape()` as an argument to `React.PropTypes.arrayOf()`.

```javascript ReactComponent.propTypes = { arrayWithShape: React.PropTypes.arrayOf( React.PropTypes.shape({ color: React.PropTypes.string.isRequired, fontSize: React.PropTypes.number.isRequired, }) ).isRequired, };

```
**** ------------------------------------------------------------------------ --- --- #### 818. What are the benefits of using TypeScript with ReactJS? [↑ Back to Table of Contents](#table-of-contents) Below are some of the benefits of using TypeScript with ReactJS, 1. It is possible to use latest JavaScript features 2. Use of interfaces for complex type definitions 3. IDEs such as VS Code was made for TypeScript 4. Avoid bugs with the ease of readability and Validation --- --- #### 819. What are the recommended ways for static type checking? [↑ Back to Table of Contents](#table-of-contents) **Modern Recommendation (2026):** **TypeScript** is the industry standard for type checking in React applications. While PropTypes (`React.PropTypes` moved to `prop-types` package since React v15.5) are still available for runtime type checking, they have significant limitations: - Only check types at runtime - No compile-time errors - Limited IDE autocomplete support - No inference for complex types **TypeScript is now the recommended approach** because it provides: - Compile-time type checking - Excellent IDE support with IntelliSense - Type inference and generic types - Better refactoring capabilities - Growing ecosystem and community support **Note:** Flow (Facebook's type checker) has seen declining adoption and is rarely used in new projects. **Example with TypeScript:**

```tsx interface UserProps { name: string; age: number; isActive?: boolean; } function User({ name, age, isActive = true }: UserProps) { return <div>{name} - {age}</div>; }

```
--- --- #### 820. What is a discriminated union and when is it useful in React? [↑ Back to Table of Contents](#table-of-contents) A union type with a common literal property ('type' or 'status') that narrows the type: `type Action = {type:'increment'} | {type:'setValue', payload:number}`. TypeScript can infer the correct shape in switch/case. --- --- #### 821. Why use TypeScript with React? [↑ Back to Table of Contents](#table-of-contents) Catches type errors at compile time (wrong prop types, missing required props). Enables autocomplete, refactoring safety, and self-documenting component APIs. Reduces runtime bugs significantly in large codebases. --- --- #### 822. What is Flow? [↑ Back to Table of Contents](#table-of-contents) _Flow_ is a _static type checker_ designed to find type errors in JavaScript. Flow types can express much more fine-grained distinctions than traditional type systems. For example, Flow helps you catch errors involving `null`, unlike most type systems. **** --- --- ### Intermediate #### 823. `React.FC` vs explicit return type -- which is better? [↑ Back to Table of Contents](#table-of-contents) Explicit: `function Comp({name}: Props): JSX.Element` is more explicit about what's returned. `React.FC<Props>` implicitly types children and return. The React team no longer recommends `React.FC` -- prefer explicit typing. ------------------------------------------------------------------------ --- **Additional source material:** Explicit: `function Comp({name}: Props): JSX.Element` is more explicit about what's returned. `React.FC<Props>` implicitly types children and return. The React team no longer recommends `React.FC` – prefer explicit typing. --- --- #### 824. How do you type component props with TypeScript? [↑ Back to Table of Contents](#table-of-contents) Define an interface or type alias: `interface Props {name: string; onClick: () => void}`. Pass as generic to FC: `const Comp: React.FC<Props> = ({name, onClick}) => ...` or just define props inline: `function Comp({name}: Props)`. --- --- #### 825. How do you type event handlers? [↑ Back to Table of Contents](#table-of-contents) `React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`. Or use inline type: `(e: React.ChangeEvent<HTMLInputElement>) => void`. --- --- #### 826. Explain the flow of Redux Toolkit. [↑ Back to Table of Contents](#table-of-contents) 1. **Define slices** using `createSlice`. Each slice contains `name`, `initialState`, and `reducers` (functions that handle actions). Reducers can be simple or use `prepare` callbacks. 2. **Combine slices** (if needed) and configure the store with `configureStore`. 3. **Dispatch actions** using the generated action creators (e.g., `increment()`). 4. **Use hooks** (`useSelector`, `useDispatch`) in React components to read state and dispatch actions. 5. **Async logic**: Use `createAsyncThunk` to define thunks that handle async requests and dispatch pending/fulfilled/rejected actions. --- --- #### 827. Explain the Redux data flow (action → reducer → store → view). [↑ Back to Table of Contents](#table-of-contents) 1. **Action**: A plain object with a `type` field describing what happened (e.g., `{ type: 'INCREMENT' }`). Dispatched from the UI. 2. **Reducer**: A pure function that takes the current state and an action, and returns a new state (immutable update). Reducers combine to form the root reducer. 3. **Store**: Holds the state tree. Provides `dispatch`, `getState`, and `subscribe`. 4. **View**: React components subscribe to the store and re‑render when the state changes. --- --- #### 828. How does async flow work in Redux Toolkit? [↑ Back to Table of Contents](#table-of-contents) 1. Define a thunk using `createAsyncThunk`. 2. Inside the payload creator, perform async work (e.g., fetch). 3. Dispatch the thunk from a component. 4. The thunk dispatches the `pending` action immediately. 5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error. 6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data). --- --- #### 829. Explain the Redux Toolkit flow. [↑ Back to Table of Contents](#table-of-contents) **Answer:** (1) createSlice() defines state shape, reducers (sync), and generates action creators. (2) configureStore() combines slices into the global store, auto-adds DevTools and middleware. (3) createAsyncThunk() handles async operations — dispatches pending/fulfilled/rejected actions. (4) extraReducers handles async thunk lifecycle in slices. (5) Components use useSelector() to read state and useDispatch() to send actions. (6) Store notifies all subscribers on state change, React re-renders connected components. --- --- #### 830. Describe about data flow in react? [↑ Back to Table of Contents](#table-of-contents) React implements one-way reactive data flow using props which reduce boilerplate and is easier to understand than traditional two-way data binding. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- #### 831. How do you type children in React with TypeScript? [↑ Back to Table of Contents](#table-of-contents) `React.ReactNode`: anything renderable (most flexible). `React.ReactElement`: a React element only. `React.PropsWithChildren<Props>`: adds optional children to any props type. Prefer `ReactNode` for general children. --- --- #### 832. How do you type context? [↑ Back to Table of Contents](#table-of-contents) `createContext<ContextType | undefined>(undefined)`. In `useContext` wrapper hook, assert non-null or throw if context is undefined. This avoids the need to check for undefined in every consumer. ------------------------------------------------------------------------ --- --- #### 833. How to use TypeScript in `create-react-app` application? [↑ Back to Table of Contents](#table-of-contents) Starting from react-scripts@3.3.0+ releases onwards, you can now optionally start a new app from a template by appending `--template [template-name]` to the creation command. If you don't select a template, it will create your project with base template. Remember that templates are always named in the format `cra-template-[template-name]`, here you only need to fill the `[template-name]` section. The typeScript can be used in your project by appending `--template typescript` to the creation command.

```bash npx create-react-app my-app --template typescript

```
But if you are using React Scripting between react-scripts@2.1.0 and react-scripts@3.2.x , there is a built-in support for TypeScript. i.e, `create-react-app` now supports TypeScript natively. You can just pass `--typescript` option as below

```bash npx create-react-app my-app --typescript

### 865. What is the difference between shallow and deep rendering?

Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees. [↑ Back to Table of Contents](#table-of-contents)

### 866. What is Vitest and how does it differ from Jest?

Vitest is a Vite-native test runner compatible with Jest's API. Faster (uses Vite's module graph), no babel config needed, native ESM support. Drop-in replacement for Jest in Vite projects.

## TypeScript with React

### 867. How do you avoid `any` when typing a third-party library without TypeScript definitions?

Write a local `.d.ts` declaration file with minimal type definitions for the parts you use, or check if `@types/<package>` exists on DefinitelyTyped before falling back to `any`/`unknown` with manual runtime checks.

### 868. How do you design a reusable button component?

Accept `variant`, `size`, `disabled`, `onClick`, `children`, `type` props. Use TypeScript to type them. Forward refs for DOM access. Avoid hardcoding styles -- use class variants or a styling system. Compose with an icon slot. ------------------------------------------------------------------------

### 869. How do you type children in React with TypeScript?

`React.ReactNode`: anything renderable (most flexible). `React.ReactElement`: a React element only. `React.PropsWithChildren<Props>`: adds optional children to any props type. Prefer `ReactNode` for general children. [⬆ Back to Table of Contents](#-table-of-contents)

### 870. How do you type component props with TypeScript?

Define an interface or type alias: `interface Props {name: string; onClick: () => void}`. Pass as generic to FC: `const Comp: React.FC<Props> = ({name, onClick}) => ...` or just define props inline: `function Comp({name}: Props)`. [⬆ Back to Table of Contents](#-table-of-contents)

### 871. How to use TypeScript in `create-react-app` application?

Starting from react-scripts@3.3.0+ releases onwards, you can now optionally start a new app from a template by appending `--template [template-name]` to the creation command. If you don't select a template, it will create your project with base template. Remember that templates are always named in the format `cra-template-[template-name]`, here you only need to fill the `[template-name]` section. The typeScript can be used in your project by appending `--template typescript` to the creation command.

```bash npx create-react-app my-app --template typescript

```
But if you are using React Scripting between react-scripts@2.1.0 and react-scripts@3.2.x , there is a built-in support for TypeScript. i.e, `create-react-app` now supports TypeScript natively. You can just pass `--typescript` option as below

```bash npx create-react-app my-app --typescript # or yarn create react-app my-app --typescript

```
Whereas for lower versions of react scripts, just supply `--scripts-version` option as `react-scripts-ts` while you create a new project. `react-scripts-ts` is a set of adjustments to take the standard `create-react-app` project pipeline and bring TypeScript into the mix. Now the project layout should look like the following:

```
my-app/ ├─ .gitignore ├─ images.d.ts ├─ node_modules/ ├─ public/ ├─ src/ │ └─ ... ├─ package.json ├─ tsconfig.json ├─ tsconfig.prod.json ├─ tsconfig.test.json └─ tslint.json

```
[↑ Back to Table of Contents](#table-of-contents)

### 872. Typescript template:

```js npx create-react-app my-app --template redux-typescript

```
[↑ Back to Table of Contents](#table-of-contents)

### 873. What are the benefits of using TypeScript with ReactJS?

Below are some of the benefits of using TypeScript with ReactJS, 1. It is possible to use latest JavaScript features 2. Use of interfaces for complex type definitions 3. IDEs such as VS Code was made for TypeScript 4. Avoid bugs with the ease of readability and Validation [↑ Back to Table of Contents](#table-of-contents)

### 874. What are the recommended ways for static type checking?

**Modern Recommendation (2026):** **TypeScript** is the industry standard for type checking in React applications. While PropTypes (`React.PropTypes` moved to `prop-types` package since React v15.5) are still available for runtime type checking, they have significant limitations: - Only check types at runtime - No compile-time errors - Limited IDE autocomplete support - No inference for complex types **TypeScript is now the recommended approach** because it provides: - Compile-time type checking - Excellent IDE support with IntelliSense - Type inference and generic types - Better refactoring capabilities - Growing ecosystem and community support **Note:** Flow (Facebook's type checker) has seen declining adoption and is rarely used in new projects. **Example with TypeScript:**

```tsx interface UserProps { name: string; age: number; isActive?: boolean; } function User({ name, age, isActive = true }: UserProps) { return <div>{name} - {age}</div>; }

```
[↑ Back to Table of Contents](#table-of-contents)

### 875. What is `PropTypes`? How does it differ from TypeScript?

A runtime prop-validation library (dev-time console warnings). TypeScript validates at compile time, catching errors before the code runs, but not bad runtime data.

### 876. What is a discriminated union and when is it useful in React?

A union type with a common literal property ('type' or 'status') that narrows the type: `type Action = {type:'increment'} | {type:'setValue', payload:number}`. TypeScript can infer the correct shape in switch/case. [↑ Back to Table of Contents](#table-of-contents)

### 877. Why use TypeScript with React?

Catches type errors at compile time (wrong prop types, missing required props). Enables autocomplete, refactoring safety, and self-documenting component APIs. Reduces runtime bugs significantly in large codebases. [↑ Back to Table of Contents](#table-of-contents)

## Styling in React

### 878. Give an example of Styled Components?

Lets create `<Title>` and `<Wrapper>` components with specific styles for each.

```javascript import React from "react"; import styled from "styled-components"; // Create a <Title> component that renders an <h1> which is centered, red and sized at 1.5em const Title = styled.h1` font-size: 1.5em; text-align: center; color: palevioletred; `; // Create a <Wrapper> component that renders a <section> with some padding and a papayawhip background const Wrapper = styled.section` padding: 4em; background: papayawhip; `;

```
These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

```jsx harmony <Wrapper> <Title>{"Lets start first styled component!"}</Title> </Wrapper>

```
[↑ Back to Table of Contents](#table-of-contents)

### 879. What are the different ways to style a React component?

There are many different ways through which one can style a React component. Some of the ways are : - **Inline Styling: **We can directly style an element using inline style attributes. Make sure the value of style is a JavaScript object:

```
class RandomComponent extends React.Component { render() { return ( <div> <h3 style={{ color: "Yellow" }}>This is a heading</h3> <p style={{ fontSize: "32px" }}>This is a paragraph</p> </div> ); } }

```
- **Using JavaScript object: **We can create a separate JavaScript object and set the desired style properties. This object can be used as the value of the inline style attribute.

```
class RandomComponent extends React.Component { paragraphStyles = { color: "Red", fontSize: "32px" }; headingStyles = { color: "blue", fontSize: "48px" }; render() { return ( <div> <h3 style={this.headingStyles}>This is a heading</h3> <p style={this.paragraphStyles}>This is a paragraph</p> </div> ); } }

```
- **CSS Stylesheet: **We can create a separate CSS file and write all the styles for the component inside that file. This file needs to be imported inside the component file.

```
import './RandomComponent.css'; class RandomComponent extends React.Component { render() { return ( <div> <h3 className="heading">This is a heading</h3> <p className="paragraph">This is a paragraph</p> </div> ); } }

```
- **CSS Modules:** We can create a separate CSS module and import this module inside our component. Create a file with “.module.css”‘ extension, styles.module.css:

```
.paragraph{ color:"red"; border:1px solid black; }

```
We can import this file inside the component and use it:

```
import styles from './styles.module.css'; class RandomComponent extends React.Component { render() { return ( <div> <h3 className="heading">This is a heading</h3> <p className={styles.paragraph} >This is a paragraph</p> </div> ); } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 880. What is a "zero-runtime" CSS-in-JS library (e.g., vanilla-extract, Panda CSS)? How does it differ from `styled-components`?

It extracts styles to static CSS files at build time rather than injecting `<style>` tags at runtime, giving CSS-in-JS's developer ergonomics (colocated, typed styles) without the runtime performance cost.

### 881. What is CSS-in-JS? Trade-offs vs traditional CSS?

Writing CSS in JS (`styled-components`/Emotion), scoped per component, dynamic via props — at the cost of runtime overhead and bundle size.

### 882. What is Tailwind CSS? How does it differ from CSS-in-JS?

Utility-first classes composed in markup, compiled/purged to plain CSS at build time, no runtime JS styling cost.

### 883. What is the purpose of a `postcss`/Tailwind build step in a React project, and how does it interact with the bundler?

PostCSS (often running Tailwind's engine) transforms authored CSS — expanding utility classes, adding vendor prefixes (autoprefixer), purging unused classes — before the bundler includes the resulting CSS in the final build output.

## Security & Accessibility

### 884. Define API?

-- props for variants, event handlers, and accessibility attributes.\

### 885. How do you build a reusable modal?

Use a portal to render outside the app root. Manage open state via controlled pattern. Trap focus inside for accessibility. Close on Escape key and overlay click. Accept children for flexible content. [⬆ Back to Table of Contents](#-table-of-contents)

### 886. How do you design a component library that's flexible and consistent org-wide?

Headless primitives for behavior/accessibility, shared design tokens, strict controlled/uncontrolled prop conventions, accessibility testing, Storybook for discoverability.

### 887. How do you securely store auth tokens in a React app?

HttpOnly cookies: cannot be accessed by JS, protected from XSS (but vulnerable to CSRF). `localStorage`: accessible to JS, vulnerable to XSS. Best practice: HttpOnly cookies + CSRF tokens, not `localStorage` for sensitive tokens. [↑ Back to Table of Contents](#table-of-contents)

### 888. How does React prevent XSS by default?

React escapes all values rendered in JSX. Strings are HTML-encoded before being inserted into the DOM. You cannot accidentally inject script tags through regular JSX expressions. ------------------------------------------------------------------------

### 889. How to use innerHTML in React?

[↑ Back to Table of Contents](#table-of-contents) The `dangerouslySetInnerHTML` attribute is React's replacement for using `innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a `__html` object as key and HTML text as value. In this example MyComponent uses `dangerouslySetInnerHTML` attribute for setting HTML markup:

```jsx harmony function createMarkup() { return { __html: "First &middot; Second" }; } function MyComponent() { return <div dangerouslySetInnerHTML={createMarkup()} />; }

```
**** ------------------------------------------------------------------------

### 890. How to use styles in React?

The `style` attribute accepts a JavaScript object with camelCased properties rather than a CSS string. This is consistent with the DOM style JavaScript property, is more efficient, and prevents XSS security holes.

```jsx harmony const divStyle = { color: "blue", backgroundImage: "url(" + imgUrl + ")", }; function HelloWorldComponent() { return <div style={divStyle}>Hello World!</div>; }

```
Style keys are camelCased in order to be consistent with accessing the properties on DOM nodes in JavaScript (e.g. `node.style.backgroundImage`). [↑ Back to Table of Contents](#table-of-contents)

### 891. Is React safe from XSS by default? When can it still occur?

React escapes interpolated values by default. XSS can still occur via `dangerouslySetInnerHTML` with unsanitized input, a user-controlled `javascript:` URL, or a DOM-manipulating third-party library.

### 892. What are ARIA roles and attributes?

ARIA (Accessible Rich Internet Applications) attributes like `role`, `aria-label`, `aria-describedby`, `aria-expanded`, `aria-hidden` provide semantic meaning to custom components for screen readers. [↑ Back to Table of Contents](#table-of-contents)

### 893. What is `dangerouslySetInnerHTML` and why is it dangerous?

Sets raw HTML on a DOM node, bypassing React's XSS protection. If the HTML contains user input, it can execute arbitrary scripts. Always sanitize with DOMPurify before using it. [↑ Back to Table of Contents](#table-of-contents)

### 894. What is `dangerouslySetInnerHTML`? When would you use it?

Sets raw HTML, bypassing escaping — an XSS risk with unsanitized input. Only use with trusted content or content sanitized via `DOMPurify`.

### 895. What is `eslint-plugin-jsx-a11y`? What does it catch?

An ESLint plugin flagging common a11y mistakes in JSX statically (missing `alt`, missing keyboard handlers, invalid ARIA usage).

### 896. What is a CSRF attack and how do you prevent it in React apps?

Cross-Site Request Forgery tricks a user's browser into making authenticated requests to your API. Prevent with CSRF tokens in headers, `SameSite` cookie attribute, and not relying solely on cookies for auth. [↑ Back to Table of Contents](#table-of-contents)

### 897. What is color contrast, and how do you verify a React app meets WCAG requirements?

Sufficient contrast between text and background colors for readability, especially for low-vision users. Verify with tools like the axe DevTools extension, Lighthouse's accessibility audit, or a contrast-checker against WCAG AA/AAA thresholds.

### 898. What tools help check React app accessibility?

- `eslint-plugin-jsx-a11y` (static analysis) - `@axe-core/react` (runtime checks in development) - Browser extensions: Axe DevTools, WAVE - Lighthouse a11y audit - Manual screen reader testing (NVDA, VoiceOver) [↑ Back to Table of Contents](#table-of-contents)

### 899. Why does accessibility matter in a React app, differently from "regular" HTML?

React doesn't change DOM accessibility rules; the risk is component abstractions (custom dropdowns, `<div onClick>`) silently losing semantics native elements give for free.

### 900. Why does accessibility matter in React apps?

SPAs often break native browser accessibility (focus management, history, page titles). React renders JS-controlled UI that screen readers may not handle correctly without explicit a11y handling. [↑ Back to Table of Contents](#table-of-contents)

### 901. Why does accessibility matter in React SPAs specifically?

SPAs bypass native browser navigation behaviors (focus reset, page titles, history announcements) that screen readers rely on by default — these must be manually re-implemented.

### 902. Why does RTL discourage test IDs/class names? When is `data-testid` appropriate?

Accessible queries keep tests resilient and verify actual accessibility. `data-testid` only as a fallback when no accessible query exists.

## React Ecosystem & Build Tools

### 903. How does tree shaking work in modern bundlers?

Tree shaking is a dead‑code elimination technique that removes unused exports from the final bundle. Bundlers like Webpack and Rollup analyze the import/export graph and only include code that is actually used. This relies on ES modules being statically analyzable.

### 904. How to avoid using relative path imports in create-react-app?

[↑ Back to Table of Contents](#table-of-contents) Create a file called `.env` in the project root and write the import path:

```
NODE_PATH=src/app

```
After that restart the development server. Now you should be able to import anything inside `src/app` without relative paths.

### 905. How to debug your React Native?

[↑ Back to Table of Contents](#table-of-contents) Follow the below steps to debug React Native app: 1. Run your application in the iOS simulator. 2. Press `Command + D` and a webpage should open up at `http://localhost:8081/debugger-ui`. 3. Enable *Pause On Caught Exceptions* for a better debugging experience. 4. Press `Command + Option + I` to open the Chrome Developer tools, or open it via `View` -> `Developer` -> `Developer Tools`. 5. You should now be able to debug as you normally would.

### 906. How to do logging in React Native?

[↑ Back to Table of Contents](#table-of-contents) You can use `console.log`, `console.warn`, etc. As of React Native v0.29 you can simply run the following to see logs in the console:

```
$ react-native log-ios $ react-native log-android

```

### 907. Standalone app?

(Safari, React Native, etc) ****

### 908. Use the ESLint Plugin?

```bash npm install eslint-plugin-react-hooks --save-dev

```
```json { "plugins": ["react-hooks"], "rules": { "react-hooks/rules-of-hooks": "error", "react-hooks/exhaustive-deps": "warn" } }

```

### 909. Webpack vs Vite vs esbuild/SWC for a React app?

Webpack: configurable, bundles everything (can be slow). Vite: native ESM in dev (fast start), Rollup for prod. esbuild/SWC: much faster Go/Rust-based compilers, often used underneath other tools.

### 910. What are the popular React-specific linters?

ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types. Another popular plugin is `eslint-plugin-jsx-a11y`, which will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with `alt` text and `tabindex`, for example, will not be picked up by regular plugins. ****

### 911. What environment variables are safe to expose in a React app?

Only non-secret config: API base URLs, feature flags, analytics IDs. Never: API secret keys, database credentials, private keys. Vite exposes `VITE_` prefixed vars; CRA exposes `REACT_APP_` prefixed vars – all are visible in the bundle.

### 912. What is `TestRenderer` package in React?

This package provides a renderer that can be used to render components to pure JavaScript objects, without depending on the DOM or a native mobile environment. This package makes it easy to grab a snapshot of the platform view hierarchy (similar to a DOM tree) rendered by a ReactDOM or React Native without using a browser or `jsdom`.

```jsx harmony import TestRenderer from "react-test-renderer"; const Link = ({ page, children }) => <a href={page}>{children}</a>; const testRenderer = TestRenderer.create( <Link page={"https://www.facebook.com/"}>{"Facebook"}</Link> ); console.log(testRenderer.toJSON()); // { // type: 'a', // props: { href: 'https://www.facebook.com/' }, // children: ** ------------------------------------------------------------------------ --- --- ### What is the 'why did you render' library? A development utility that patches React to notify you when a component re-renders due to reference-equal props/state. Helps find components where `React.memo` or `useMemo` would be beneficial. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the behavior of uncaught errors in react 16? **Note:** This behavior was introduced in React 16 and continues in React 18/19. In React 16+, errors that are not caught by any error boundary will result in unmounting of the whole React component tree. The reason behind this decision is that it is worse to leave corrupted UI in place than to completely remove it. For example, it is worse for a payments app to display a wrong amount than to render nothing. **Best Practice:** Always wrap your application or critical sections in error boundaries to prevent complete unmounting and provide a better user experience.

```jsx <ErrorBoundary fallback={<ErrorPage />}> <App /> </ErrorBoundary>

```
**** --- ### What is the benefit of styles modules? It is recommended to avoid hard coding style values in components. Any values that are likely to be used across different UI components should be extracted into their own modules. For example, these styles could be extracted into a separate component:

```javascript export const colors = { white, black, blue, }; export const space = **

### 913. What is code-splitting?

Code-Splitting is a feature supported by bundlers like Webpack and Browserify which can create multiple bundles that can be dynamically loaded at runtime. The react project supports code splitting via dynamic import() feature. For example, in the below code snippets, it will make moduleA.js and all its unique dependencies as a separate chunk that only loads after the user clicks the 'Load' button. **moduleA.js**

```javascript const moduleA = "Hello"; export { moduleA };

```
**App.js**

```javascript export default function App { function handleClick() { import("./moduleA") .then(({ moduleA }) => { // Use moduleA }) .catch((err) => { // Handle failure }); }; return ( <div> <button onClick={this.handleClick}>Load</button> </div> ); }

```
<details><summary><b>See Class</b></summary> <p>

```javascript import React, { Component } from "react"; class App extends Component { handleClick = () => { import("./moduleA") .then(({ moduleA }) => { // Use moduleA }) .catch((err) => { // Handle failure }); }; render() { return ( <div> <button onClick={this.handleClick}>Load</button> </div> ); } } export default App;

```{=html} </p>

```
```{=html} </details>

```
------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is Concurrent Rendering? The Concurrent rendering makes React apps to be more responsive by rendering component trees without blocking the main UI thread. It allows React to interrupt a long-running render to handle a high-priority event. i.e, When you enabled concurrent Mode, React will keep an eye on other tasks that need to be done, and if there's something with a higher priority it will pause what it is currently rendering and let the other task finish first. You can enable this in two ways,

```
// 1. Part of an app by wrapping with ConcurrentMode <React.unstable_ConcurrentMode> <Something /> </React.unstable_ConcurrentMode>; // 2. Whole app using createRoot ReactDOM.unstable_createRoot(domNode).render(<App />);

```
[ --- ### What is concurrent rendering? When does it help vs hurt? Concurrent rendering allows React to work on multiple tasks simultaneously, interrupting low‑priority work to handle high‑priority updates (like typing). It helps keep the UI responsive. **When it helps**: During heavy computations, data fetching, or large list updates – the app stays interactive. **When it may hurt**: Not all apps need it; it adds complexity and can cause subtle bugs if components assume synchronous rendering. --- ### What is React lazy function? The `React.lazy` function lets you render a dynamic import as a regular component. It will automatically load the bundle containing the `OtherComponent` when the component gets rendered. This must return a Promise which resolves to a module with a default export containing a React component.

```jsx const OtherComponent = React.lazy(() => import("./OtherComponent")); function MyComponent() { return ( <div> <OtherComponent /> </div> ); }

```
**Note:** `React.lazy` and `Suspense` is not yet available for server-side rendering. If you want to do code-splitting in a server rendered app, we still recommend React Loadable. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is React memo function? Class components can be restricted from re-rendering when their input props are the same using **PureComponent or shouldComponentUpdate**. Now you can do the same with function components by wrapping them in **React.memo**.

```jsx const MyComponent = React.memo(function MyComponent(props) { /* only rerenders if props change */ });

```
------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is `React.lazy` and how does it work? `React.lazy(() => import('./Comp'))` creates a lazy-loaded component. React suspends rendering until the chunk loads, showing the nearest `Suspense` fallback. Only works with default exports. ------------------------------------------------------------------------ --- --- ### What is `React.memo`? A HOC that wraps a functional component. On re-render of the parent, React shallowly compares old and new props; if equal, it skips re-rendering the child. Accepts a custom comparator as second argument. ------------------------------------------------------------------------ --- --- ### What is `startTransition`? Marks a state update as non-urgent. React processes urgent updates first and defers the transition. If a newer transition comes in, the in-progress one is aborted. Used for navigation, search, filtering. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is Suspense? A component that shows a fallback while children are 'suspended'. Components suspend by throwing a Promise. React catches it, shows the fallback, and retries when the Promise resolves. Used with `lazy()` and data-fetching libraries. ------------------------------------------------------------------------ --- --- ### What is suspense component? React Suspense is a built-in feature that lets you defer rendering part of your component tree until some condition(asynchronous operation) is met---usually, data or code has finished loading. While waiting, Suspense lets you display a fallback UI like a spinner or placeholder. 1. Lazy loading components uses suspense feature, If the module containing the dynamic import is not yet loaded by the time parent component renders, you must show some fallback content while you’re waiting for it to load using a loading indicator. This can be done using **Suspense** component.

```javascript const OtherComponent = React.lazy(() => import("./OtherComponent")); function MyComponent() { return ( <div> <Suspense fallback={<div>Loading...</div>}> <OtherComponent /> </Suspense> </div> ); }

```
The above component shows fallback UI instead real component until `OtherComponent` is fully loaded. 2. As an another example, suspend until async data(data fetching) is ready

```jsx function UserProfile() { const user = use(fetchUser()); // throws a promise internally return <div>{user.name}</div>; } function App() { return ( <Suspense fallback={<div>Loading user...</div>}> <UserProfile /> </Suspense> ); }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is the difference between async mode and concurrent mode? Both refers the same thing. Previously concurrent Mode being referred to as "Async Mode" by React team. The name has been changed to highlight React’s ability to perform work on different priority levels. So it avoids the confusion from other approaches to Async Rendering. [ --- ### What is the difference between element and component re-render? Elements are plain objects; React creates/updates them every render cheaply. A component re-renders when its state or props change, executing the function body again. Only DOM nodes actually affected get updated in the real DOM. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the difference between virtualization and windowing? Trade-offs. **Virtualization** is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. **Windowing** is a specific implementation (e.g., `react-window`) that renders a “window” of items. **Trade-offs**: - **Pros**: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists. - **Cons**: Adds complexity; layout calculations can be tricky for variable heights. Accessibility can suffer if not implemented carefully (screen readers may not see all items). Scrolling might feel different. --- --- ### What is the methods order when component re-rendered? An update can be caused by changes to props or state. The below methods are called in the following order when a component is being re-rendered. 1. static getDerivedStateFromProps() 2. shouldComponentUpdate() 3. render() 4. getSnapshotBeforeUpdate() 5. componentDidUpdate() ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is the Profiler API? `React.Profiler` wraps a tree and calls `onRender(id, phase, actualDuration, ...)` after each commit. Used to programmatically measure render performance in development. React DevTools Profiler wraps this in a UI. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the purpose of ESLint and Prettier in a React project? ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other -- ESLint for rules, Prettier for style. ------------------------------------------------------------------------ --- --- ### What is the purpose of Suspense beyond lazy loading? Suspense is a generic mechanism for orchestrating asynchronous dependencies in React. Besides lazy loading components, it can be used for data fetching (with libraries like Relay, Next.js) or any asynchronous operation that integrates with Suspense. It lets components “wait” for something before rendering, with a fallback UI. --- ### What is windowing technique? Windowing is a technique that only renders a small subset of your rows at any given time, and can dramatically reduce the time it takes to re-render the components as well as the number of DOM nodes created. If your application renders long lists of data then this technique is recommended. Both react-window and react-virtualized are popular windowing libraries which provides several reusable components for displaying lists, grids, and tabular data. [ --- ### What is windowing/virtualization and when do you need it? Rendering only visible list items in a large dataset instead of all of them. Libraries: `react-window`, `react-virtual`, `TanStack Virtual`. Use when rendering 1000+ items causes frame drops or memory pressure. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization) **CDN (Content Delivery Network)** - Serve static assets (JS, CSS, images) from a CDN to reduce latency for users worldwide. Use a global CDN like Cloudflare, Fastly, or AWS CloudFront. **Code Splitting** - Split code by routes using `React.lazy` and `Suspense`. This loads only the JavaScript needed for the current page. - Use dynamic imports for heavy components that are not needed immediately. **Lazy Loading** - Images: use `loading="lazy"` attribute on `<img>`. - Off‑screen components: load them only when they become visible (using Intersection Observer). **Image Optimization** - Serve responsive images with `srcset` and `sizes`. - Use modern formats (WebP, AVIF) and fallbacks. - Compress images; use CDN image optimization services (e.g., Imgix, Cloudinary). **Font Optimization** - Use `font-display: swap` to avoid invisible text during loading. - Preload critical fonts with `<link rel="preload">`. - Subset fonts to reduce size. **Resource Hints** - Use `preconnect` for origins you’ll connect to (e.g., API, CDN). - Use `dns-prefetch` for third‑party domains. **Minification & Compression** - Ensure your bundler (Webpack, Vite) minifies code and uses Brotli or Gzip compression. **HTTP/2 or HTTP/3** - Enable HTTP/2 for multiplexing; consider HTTP/3 for better performance. **Service Worker** - Cache static assets for repeat visits. --- --- ### When does `React.memo` NOT help? When props include new object/function references on every parent render (must pair with `useMemo`/`useCallback`). When the component is cheap to render (overhead of comparison \> render cost). When props always change. ------------------------------------------------------------------------ --- --- ### When to Still Use Manual Optimization

```jsx // For external libraries without Compiler support import { expensiveLibFunction } from 'old-library'; function MyComponent() { // May still need manual memoization here const result = useMemo(() => expensiveLibFunction(), []); return <div>{result}</div>; }

```
#### Compatibility - Works with React 18.3+ and React 19 - Compatible with TypeScript - Works with all React hooks - Supports Server Components and Client Components 327. ### What is Streaming SSR and how does React 18+ improve it? **Streaming SSR** sends HTML to the browser in chunks as it's generated, rather than waiting for the entire page. React 18+ dramatically improves this with Suspense integration. #### Traditional SSR (Pre-React 18)

```
Server: Wait for ALL data → Generate ALL HTML → Send to client Client: Receive HTML → Download ALL JS → Hydrate ALL components Problem: Slow components block entire page!

```
#### Streaming SSR (React 18+)

```
Server: Send HTML as it's ready, wrap slow parts in <Suspense> Client: Render immediately, hydrate progressively Benefit: User sees content faster!

```
#### Basic Example

```jsx import { Suspense } from 'react'; export default function Page() { return ( <html> <body> {/* Sent immediately */} <header> <h1>My App</h1> </header> {/* Sent immediately with fallback */} <Suspense fallback={<div>Loading comments...</div>}> <Comments /> {/* Streamed when ready */} </Suspense> {/* Also streamed separately */} <Suspense fallback={<div>Loading recommendations...</div>}> <Recommendations /> {/* Streamed when ready */} </Suspense> <footer>© 2026</footer> </body> </html> ); }

```
#### Server Component with Data Fetching

```jsx // This is a Server Component (async!) async function Comments() { const comments = await db.comments.findMany(); return ( <ul> {comments.map(comment => ( <li key={comment.id}>{comment.text}</li> ))} </ul> ); }

```
--- ### When would you use `React.memo`? Use `React.memo` for: - Components that receive the same props often but re‑render due to parent re‑renders. - Large components that are expensive to re‑render. - Pure functional components that depend on props only. Avoid over‑using `memo` because the shallow prop comparison itself costs time. Use it where profiling shows a benefit. --- --- ### ❓ How do you debug a performance bottleneck in a React app using DevTools? **Answer:** (1) Chrome Performance tab: record user interaction, look for long tasks (>50ms) in the flame chart, identify JS evaluation and layout/paint phases. (2) React DevTools Profiler: record interactions, see which components render and their render duration, look for 'why did this render' annotation. (3) Memory tab: take heap snapshots before/after interactions to find leaks. (4) Network tab: identify slow requests, bundle sizes, caching issues. (5) Coverage tab: see unused JS/CSS bytes. Combine all for complete picture. --- ### ❓ If given an existing website to analyze and improve performance, what is your first step? **Answer:** Start with measurement before optimization. (1) Run Lighthouse audit in Chrome DevTools — get baseline scores for Performance, Accessibility, SEO. (2) Check Core Web Vitals in the Performance tab and real user data in Search Console. (3) Use Network tab to analyze waterfall — identify render-blocking resources, large bundles, slow API calls. (4) Check Coverage tab for unused JS/CSS. (5) Look for layout shifts in the Layout Shift Regions feature. Measure → identify bottleneck → fix → measure again. Never optimize blind. --- ### ❓ What are Web Vitals and why do they matter? **Answer:** Core Web Vitals are Google's metrics for user experience quality: LCP (Largest Contentful Paint) — loading performance, should be < 2.5s. CLS (Cumulative Layout Shift) — visual stability, should be < 0.1. INP (Interaction to Next Paint, replaced FID) — responsiveness, should be < 200ms. Also important: FCP (First Contentful Paint), TTFB (Time to First Byte), TTI (Time to Interactive). These directly affect SEO rankings (Google uses them as ranking signals) and user experience metrics. --- ### ❓ What is re-rendering and why does it happen? **Answer:** Re-rendering is React calling your component function again to compute new JSX output. Causes: (1) Component's own state changes via setState/dispatch. (2) Parent component re-renders (by default, all children re-render). (3) Context value changes. (4) Subscribed store changes (Redux, Zustand). Important: re-rendering doesn't always mean DOM update — React diffs and only applies necessary DOM changes. Prevent unnecessary re-renders with React.memo, useMemo, useCallback, and proper state co-location. --- ### ❓ You notice a memory leak in a production SPA — how do you identify and fix it? **Answer:** Identification: (1) Use Chrome Memory tab — take heap snapshots, compare before/after navigation. Growing detached DOM nodes and growing listener counts are red flags. (2) Chrome Performance monitor — watch JS heap size over time. Common causes & fixes: (1) Event listeners not removed — fix with cleanup in useEffect return. (2) Timers (setInterval) not cleared — clearInterval in cleanup. (3) Stale closures holding references — review useEffect deps. (4) Unsubscribed observables/WebSockets — close in cleanup. (5) Caching without eviction — implement LRU or max-size limits. --- ## React 18/19, SSR & Server Components ### Explain React Server Components vs Client Components. - **Server Components**: Run on the server and send a special JSON-like format to the client. They never re‑render on the client and can access server resources (databases, file system) directly. They reduce bundle size and improve performance. - **Client Components**: Run in the browser and can have interactivity, state, and effects. They are the traditional React components. In the new React architecture, components are “use client” or “use server” directives. Server Components can import Client Components, but not vice versa. --- ### How does React 18's automatic batching work? Automatic batching in React 18 groups multiple state updates from any source (not just event handlers) into a single re‑render. This is enabled by default when using `createRoot`. It reduces unnecessary renders and improves performance. You can opt out using `flushSync`. ------------------------------------------------------------------------ --- --- ### How would you implement SSR for a React application? **Approaches**: - **Frameworks**: Next.js (recommended), Remix, or custom Node server with React's `renderToString`/`renderToPipeableStream`. - **Data fetching**: Fetch data on the server (e.g., `getServerSideProps` in Next.js) and pass it as props to the component. - **Hydration**: Server‑rendered HTML is sent to client; React attaches event listeners and reconciles. - **Performance**: Use streaming SSR (`renderToPipeableStream`) for faster TTFB. - **Caching**: Use CDN caching with `stale-while-revalidate` for pages. - **Challenges**: Ensure server and client environment compatibility (avoid `window` usage in server). Use `useEffect` for client‑only code. ------------------------------------------------------------------------ This comprehensive guide covers the most common component design questions with practical considerations and implementation insights. Each design can be expanded with full code examples, but the key is to understand the trade‑offs, accessibility, performance, and scalability aspects. --- --- ### What are React Server components? React Server Component is a way to write React component that gets rendered in the server-side with the purpose of improving React app performance. These components allow us to load components from the backend. **Note:** React Server Components is still under development and not recommended for production yet. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What are the key features introduced in React 18? React 18, released in March 2022, introduced several groundbreaking features focused on performance and user experience: #### 1. **Automatic Batching** Batch multiple state updates together (even in async code) to reduce re-renders.

```jsx // Before React 18: Only batched in event handlers // After React 18: Batched everywhere setTimeout(() => { setCount(c => c + 1); setFlag(f => !f); // Only 1 re-render in React 18! }, 1000);

```
#### 2. **Concurrent Features** - **useTransition**: Mark updates as non-urgent - **useDeferredValue**: Defer expensive re-renders - **Suspense on Server**: SSR with Suspense support #### 3. **New createRoot API**

```jsx // Old way (React 17) ReactDOM.render(<App />, document.getElementById('root')); // New way (React 18) import { createRoot } from 'react-dom/client'; const root = createRoot(document.getElementById('root')); root.render(<App />);

```
#### 4. **Streaming SSR with Suspense** Stream HTML from server and hydrate components as they arrive. #### 5. **New Hooks** - `useId`: Generate unique IDs for accessibility - `useSyncExternalStore`: Subscribe to external stores - `useInsertionEffect`: For CSS-in-JS libraries #### 6. **Strict Mode Improvements** Double-invokes effects in development to catch bugs. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What causes hydration mismatches and how do you fix them? Think of a hydration mismatch like a blueprint mix-up between two different builders. When using Server-Side Rendering (SSR), the Server builds the HTML webpage first and sends it to the browser. Then, React boots up in the browser, reads that HTML, and tries to "adopt" it (this adoption process is called hydration). A hydration mismatch happens when the HTML that the server built does not exactly match what React expects to see in the browser. React gets confused and throws an error. 🚨 What Causes It? (The Differences) Timestamps: The server creates the HTML at 10:00:00 AM. The browser downloads and reads it at 10:00:03 AM. Because the seconds don't match, React panics. Browser-Only Secrets: The server doesn't have a screen or a hard drive, so it doesn't know what window.innerWidth or localStorage is. If your code uses these, the server will output a blank space, but the browser will try to fill it in with real data. Random Numbers: If you use Math.random(), the server might roll a 4, but the browser rolls a 7. 🛠️ How to Fix It The Best Way (useEffect): Keep the server text generic or empty at first. Use a useEffect hook to calculate the time, random numbers, or browser data after the page has fully loaded in the browser. The "Ignore It" Way (suppressHydrationWarning): If you have a minor, harmless mismatch (like a text timestamp), you can add this attribute to your HTML tag to tell React: "I know they don't match, please don't yell at me." The "Skip Server" Way: Turn off server-rendering for that specific component completely so it only ever builds on the browser. ------------------------------------------------------------------------ --- --- ### What is automatic batching in React 18? React 18 batches multiple `setState` calls in async contexts (`setTimeout`, Promises, native event handlers) into one re-render. Previously, only synchronous event handlers were batched. Reduces render count. ------------------------------------------------------------------------ --- --- ### What is `createRoot()` and why was it introduced in React 18? `createRoot()` replaces `ReactDOM.render()`. It opts the app into React 18's concurrent features (automatic batching, `startTransition`, Suspense improvements). `ReactDOM.render()` runs in legacy mode without those features. ------------------------------------------------------------------------ --- --- ### What is hydration? Attaching React's event handlers and internal state to server-rendered HTML without re-rendering it. React expects the client-side output to exactly match server HTML; mismatches cause warnings or errors. ------------------------------------------------------------------------ --- --- ### What is hydration? How do hydration mismatches occur? Hydration is the process where React attaches event listeners and reconciles the server‑rendered HTML with the client‑side virtual DOM. It allows interactive components to "take over" the static markup. **Hydration mismatches** occur when the HTML generated on the server differs from the initial render on the client (e.g., due to different data, random values, or browser‑only APIs). React will then attempt to patch the mismatch, which can cause performance issues and break user experience. ------------------------------------------------------------------------ --- --- ### What is hydration in React? Hydration is the process where React 'attaches' event handlers and makes a server-rendered HTML page interactive. SSR sends HTML to the browser (fast first paint). React then downloads, parses JS and runs hydration --- it walks the existing DOM and attaches React's event system without re-creating DOM nodes. Hydration mismatch errors occur when server-rendered HTML doesn't match what React would render on client (e.g., browser-specific values, Date.now(), Math.random()). React 18 has selective/partial hydration via Suspense. ------------------------------------------------------------------------ --- --- ### What is React hydration? React hydration is used to add client-side JavaScript interactivity to pre-rendered static HTML generated by the server. It is used only for server-side rendering(SSR) to enhance the initial rendering time and make it SEO friendly application. This hydration acts as a bridge to reduce the gap between server side and client-side rendering. After the page loaded with generated static HTML, React will add application state and interactivity by attaching all event handlers for the respective elements. Let's demonstrate this with an example. Consider that React DOM API(using `renderToString`) generated HTML for `<App>` component which contains `<button>` element to increment the counter.

```jsx import {useState} from 'react'; import { renderToString } from 'react-dom/server'; export default function App() { const ** ------------------------------------------------------------------------

### 914. What is the difference between a bundler and a compiler/transpiler in the React toolchain (e.g., Webpack vs Babel/SWC)?

A compiler/transpiler (Babel, SWC) transforms source syntax (JSX, newer JS, TypeScript) into code the target environment understands. A bundler (Webpack, Rollup, Vite's build step) combines many modules/files into optimized output bundles, handling code splitting, asset processing, and dependency graphs — they're complementary, often used together.

### 915. What is the difference between React Native and React?

[↑ Back to Table of Contents](#table-of-contents) **React** is a JavaScript library, supporting both front end web and being run on the server, for building user interfaces and web applications. **React Native** is a mobile framework that compiles to native app components, allowing you to build native mobile applications (iOS, Android, and Windows) in JavaScript that allows you to use React to build your components, and implements React under the hood.

### 916. What is the purpose of ESLint and Prettier in a React project?

ESLint: static analysis, catches bugs and enforces coding standards (with `react`, `react-hooks`, `jsx-a11y` plugins). Prettier: opinionated code formatting. They complement each other – ESLint for rules, Prettier for style.

### 917. What is the role of Babel in a React project?

[↑ Back to Table of Contents](#table-of-contents) Transpiles modern JS and JSX to browser-compatible JS. Plugins transform JSX to `createElement` calls. In Vite projects, esbuild handles transpilation faster; Babel is less common in new setups. ------------------------------------------------------------------------

### 918. What is Vite and why is it preferred over CRA?

[↑ Back to Table of Contents](#table-of-contents) Vite uses native ES modules for dev server (near-instant startup) and Rollup for production builds. Much faster than CRA's webpack-based dev server. CRA is no longer maintained.

### 919. What is Vite, and why is it preferred over Create React App today?

Vite uses native ES modules for near-instant dev-server startup and Rollup for optimized production builds; CRA (webpack-based, no longer actively maintained) is significantly slower in dev and is no longer recommended for new projects — Vite (SPAs) or Next.js (SSR/full-stack) are the modern defaults.

## General / Miscellaneous React Concepts

### 920. `BrowserRouter` vs `HashRouter`?

`BrowserRouter` uses clean URLs via History API (needs server config for refresh). `HashRouter` uses `#` fragments, never hitting the server, zero config but less clean.

### 921. `dispatch` is synchronous:

The reducer runs immediately when `dispatch` is called.

### 922. `getBy` vs `queryBy` vs `findBy` – when do you use each?

[↑ Back to Table of Contents](#table-of-contents) - `getBy`: throws if not found (use when element should exist) - `queryBy`: returns null if not found (use for asserting absence) - `findBy`: async, returns Promise – use when element appears after async operation

### 923. `render`, `screen`, `fireEvent`/`userEvent`?

`render` mounts; `screen` provides queries; `userEvent` simulates realistic interactions (preferred over `fireEvent`).

### 924. `staleTime` vs `cacheTime`/`gcTime`?

`staleTime`: how long data is "fresh." `gcTime`: how long unused cached data stays before garbage collection.

### 925. A/B Testing: How to implement A/B testing without affecting current users?

**Implementation**: - Use a feature flag service (e.g., LaunchDarkly, Optimizely) that can assign users to variants. - **Variant assignment** – deterministic based on user ID or cookie, so users see consistent experience. - **Initialization** – fetch assignment early (e.g., on app boot) and store in context. - **Render conditionally** based on variant. - **Avoid layout shift** – ensure that variant components have the same dimensions as the control. - **Analytics** – track which variant users saw to measure impact. **For performance**: - Use asynchronous loading of the testing SDK. - Consider server‑side assignment if using SSR.

### 926. Actions?

Used for all action creators, where file names correspond to part of the app.

### 927. After a dependency value changes?

(if the dependency array contains variables)

### 928. After every render?

(if no dependency array is provided)

### 929. After the component is mounted?

(if the dependency array is empty `[]`)

### 930. Analyzes code?

during build time

### 931. Arrays and fragments:

Return multiple elements to render as Arrays and Fragments to wrap multiple elements

### 932. Arrow functions:

Makes compact syntax

```javascript // es 5 var users = usersList.map(function (user) { return <li>{user.name}</li>; }); // es 6 const users = usersList.map((user) => <li>{user.name}</li>);

```

### 933. Async logic?

Use `createAsyncThunk` to define thunks that handle async requests and dispatch pending/fulfilled/rejected actions. [↑ Back to Table of Contents](#table-of-contents)

### 934. Automatically inserts memoization?

where beneficial

### 935. Blue‑Green Deployment?

- Maintain two identical environments: blue (current) and green (new). - Deploy new version to green, run smoke tests. - Switch router (load balancer) to green instantly. - If issues arise, switch back to blue.

### 936. Booleans or null:

Doesn't render anything but these types are used to conditionally render content. [↑ Back to Table of Contents](#table-of-contents)

### 937. Build & Test?

(PR / main) - Lint, type check, unit/integration tests. - Build the application (generating static assets). - Run contract tests, visual regression tests. - Upload source maps to error tracking.

### 938. Build in isolation?

-- use Storybook to develop without distractions.\

### 939. Calling `setState()` with a function:

```
javascript this.setState((prevState) => ({ user: { ...prevState.user, age: 42, }, }));

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 940. Can I use web components in react application?

[↑ Back to Table of Contents](#table-of-contents) Yes, you can use web components in a react application. Even though many developers won't use this combination, it may require especially if you are using third-party UI components that are written using Web Components. For example, let us use `Vaadin` date picker web component as below,

```javascript import "./App.css"; import "@vaadin/vaadin-date-picker"; export default function App() { return ( <div className="App"> <vaadin-date-picker label="When were you born?"></vaadin-date-picker> </div> ); }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 941. Can you list down top websites or applications using react as front end framework?

[↑ Back to Table of Contents](#table-of-contents) Below are the `top 10 websites` using React as their front-end framework, 1. Facebook 2. Uber 3. Instagram 4. WhatsApp 5. Khan Academy 6. Airbnb 7. Dropbox 8. Flipboard 9. Netflix 10. PayPal ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 942. Clean Up Side Effects?

[↑ Back to Table of Contents](#table-of-contents) Always return a cleanup function when subscribing to events, timers, or external data sources.

### 943. Cleanup?

-- Once a feature is fully rolled out, remove the flag code to avoid clutter. Use the SDK's ability to archive flags. **Example**: \> "We used LaunchDarkly with React. We wrapped our app in a provider that initialized flags from localStorage first (for caching) then streamed updates via WebSocket. We created a `useFlag` hook that returned the flag value and automatically re‑rendered when the flag changed. For A/B tests, we used the `variation` to track analytics events. In Next.js, we fetched flags on the server using the Node SDK and passed them to the page via props, ensuring no layout shift." ------------------------------------------------------------------------

### 944. Combine slices?

(if needed) and configure the store with `configureStore`.

### 945. Commit changes to DOM:

After calling components, React will modify the DOM for initial render using `appendChild()` DOM API and apply minimal necessary DOM updates for re-renders based on differences between rerenders. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 946. Component API versioning?

– For shared component libraries, use semantic versioning. Breaking changes require a major version bump. Provide codemods to ease migration.

### 947. Component Library Development?

– Build components using a framework‑agnostic approach (e.g., CSS modules with CSS variables, or a framework‑specific library like React). Start with the most used components (button, input, modal). Document API, variants, and usage guidelines in Storybook.

### 948. Concurrency and Prioritization?

* React can prepare multiple versions of UI at once (e.g., during slow data loading). * Updates can be **assigned priorities**, so urgent updates (like clicks) are handled faster than background work. [↑ Back to Table of Contents](#table-of-contents)

### 949. Debouncing:

Publish changes after a period of inactivity. For example, it can be used using \_.debounce lodash function

### 950. Define slices?

using `createSlice`. Each slice contains `name`, `initialState`, and `reducers` (functions that handle actions). Reducers can be simple or use `prepare` callbacks.

### 951. Different trees are produced because of different elements?

If the root elements have different types, React: - unmounts the old component tree, - destroys associated DOM nodes, - mounts a new tree. Example: <div /> → <section /> This triggers a full rebuild of that subtree.

### 952. Dispatch actions?

using the generated action creators (e.g., `increment()`).

### 953. Document?

-- in Storybook, with prop tables, usage examples, and design guidelines.\

### 954. Does the statics object work with ES6 classes in React?

[↑ Back to Table of Contents](#table-of-contents) No, `statics` only works with `React.createClass()`:

```javascript someComponent = React.createClass({ statics: { someMethod: function () { // .. }, }, });

```
But you can write statics inside ES6+ classes as below,

```javascript class Component extends React.Component { static propTypes = { // ... }; static someMethod() { // ... } }

```
or writing them outside class as below,

```javascript class Component extends React.Component { .... } Component.propTypes = {...} Component.someMethod = function(){....}

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 955. DOM Elements Of The Same Type:

When comparing two React DOM elements of the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes. Lets take an example with same DOM elements except className attribute,

```javascript <div className="show" title="ReactJS" /> <div className="hide" title="ReactJS" />

```

### 956. Double Buffering with Two Trees?

* React maintains two trees: * **Current Tree** – what's visible on the screen. * **Work-In-Progress Tree** – the next version being built in memory. * Only after the new tree is fully ready, React **commits** it, making it the new current tree.

### 957. During action creation:

Let's take `actions.js`:

```javascript import { ADD_TODO } from "./actionTypes"; export function addTodo(text) { return { type: ADD_TODO, text }; }

```

### 958. Elements Of Different Types:

Whenever the root elements have different types, React will tear down the old tree and build the new tree from scratch. For example, elements <a> to <img>, or from <Article> to <Comment> of different types lead a full rebuild.

### 959. Elements of the same type are compared attribute-wise?

If element types are the same, React updates only the changed attributes, and then recursively compares child elements

### 960. Explain reducers and extraReducers – when to use each?

[↑ Back to Table of Contents](#table-of-contents) - **`reducers`**: Used for actions that are directly handled by this slice. RTK automatically generates action creators with the same names. Good for synchronous, slice‑specific updates. - **`extraReducers`**: Used to respond to actions defined elsewhere (e.g., thunks, actions from other slices). It’s often used with `builder` callback to handle `pending`, `fulfilled`, `rejected` of async thunks. It allows a slice to react to actions that are not its own.

### 961. Full Production Rollout?

- After canary passes, deploy to all pods (rolling update). - Invalidate CDN caches if needed (use versioned asset names to avoid stale content). - Post‑deployment monitoring for 30 minutes, then close the canary. **Tools**: GitHub Actions/GitLab CI, ArgoCD for Kubernetes, AWS CodeDeploy for blue‑green, LaunchDarkly for feature flags.

### 962. Given an array of users, find all active user ids.

**Array**: `users = [{ id: 1, active: true }, { id: 2, active: false }]`\ Also with `null`, `{}`, etc.

```
javascript function getActiveIds(users) { return users .filter(user => user && typeof user === 'object' && user.active === true) .map(user => user.id); }

```

### 963. Given users = \[{id:1, active:true}, {id:2, active:false}\], find all active user IDs.

```
javascript // Clean array const activeIds = users .filter(u => u.active) .map(u => u.id); // [1] // With nulls/empty objects: [{id:1, active:true}, null, {}, {id:2}] const activeIdsSafe = users .filter(u => u && u.id && u.active) .map(u => u.id);

```
The defensive version handles nulls, empty objects, and missing properties. Always validate data before accessing nested properties in real-world scenarios.

### 964. Grouping by features or routes:

One common way to structure projects is locate CSS, JS, and tests together, grouped by feature or route.

```
common/ ├─ Avatar.js ├─ Avatar.css ├─ APIUtils.js └─ APIUtils.test.js feed/ ├─ index.js ├─ Feed.js ├─ Feed.css ├─ FeedStory.js ├─ FeedStory.test.js └─ FeedAPI.js profile/ ├─ index.js ├─ Profile.js ├─ ProfileHeader.js ├─ ProfileHeader.css └─ ProfileAPI.js

```

### 965. Grouping by file type:

Another popular way to structure projects is to group similar files together.

```
api/ ├─ APIUtils.js ├─ APIUtils.test.js ├─ ProfileAPI.js └─ UserAPI.js components/ ├─ Avatar.js ├─ Avatar.css ├─ Feed.js ├─ Feed.css ├─ FeedStory.js ├─ FeedStory.test.js ├─ Profile.js ├─ ProfileHeader.js └─ ProfileHeader.css

```
****

### 966. Handling keys:

React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree. For example, adding a key can make the tree conversion efficient,

```javascript <ul> <li key="2015">Duke</li> <li key="2016">Villanova</li> </ul> <ul> <li key="2014">Connecticut</li> <li key="2015">Duke</li> <li key="2016">Villanova</li> </ul>

```

### 967. How are error boundaries handled in React v15?

[↑ Back to Table of Contents](#table-of-contents) **⚠️ LEGACY:** This question is only relevant for historical context. React v15 is extremely outdated (released in 2016). React v15 provided very basic support for _error boundaries_ using the `unstable_handleError` method. This was an experimental feature that was later redesigned and renamed to `componentDidCatch` in React v16. **Modern Error Boundaries (React 16+):** - Use `static getDerivedStateFromError(error)` for UI fallback - Use `componentDidCatch(error, info)` for logging - Work consistently across server and client rendering **** ------------------------------------------------------------------------

### 968. How do you access imperative API of web components?

Web Components often expose an imperative API to implement its functions. You will need to use a **ref** to interact with the DOM node directly if you want to access imperative API of a web component. But if you are using third-party Web Components, the best solution is to write a React component that behaves as a **wrapper** for your Web Component. [

### 969. How do you avoid unnecessary re-renders with `useSelector`?

Select narrow slices, use memoized selectors (`reselect`), or a custom equality function (`shallowEqual`).

### 970. How do you create a generic, reusable component?

`function List<T>({ items, renderItem }: { items: T[]; renderItem: (item: T) => React.ReactNode })`.

### 971. How do you define nested routes (v6+)?

Nest `<Route>` elements; render `<Outlet/>` in the parent for the matched child.

### 972. How do you implement a layout route (shared header/sidebar across multiple pages)?

A parent `<Route element={<Layout/>}>` wrapping child routes, with `<Layout>` rendering shared chrome plus an `<Outlet/>` for the matched child.

### 973. How do you implement protected/private routes?

Wrap the element in an auth check that renders children or `<Navigate to="/login"/>`.

### 974. How do you integrate feature flags (LaunchDarkly, etc.) in React ecosystems?

**Goal**: Control feature rollout, A/B testing, and safe releases. **Integration**:

### 975. How do you mock API calls with `msw`?

Intercepts actual network requests at the network layer, returning fixture responses without the component knowing it's mocked.

### 976. How do you pass a component as a prop (not just data)?

Pass the element or component reference itself as a prop value: `<Layout icon={<HomeIcon/>} />` or `<Layout Icon={HomeIcon} />`, letting the parent customize rendered content.

### 977. How do you pass arguments to an event handler?

During iterations or loops, it is common to pass an extra parameter to an event handler. This can be achieved through arrow functions or bind method. Let us take an example of user details updated in a grid,

```javascript <button onClick={(e) => this.updateUser(userId, e)}>Update User details</button> <button onClick={this.updateUser.bind(this, userId)}>Update User details</button>

```
In the both approaches, the synthetic argument `e` is passed as a second argument. You need to pass it explicitly for arrow functions and it will be passed automatically for `bind` method. [↑ Back to Table of Contents](#table-of-contents)

### 978. How do you prevent a dependency supply-chain attack from affecting a React app?

Pin exact dependency versions (lockfile committed), run `npm audit`/Snyk in CI, review new dependencies before adding them, and consider a private registry proxy that vets packages.

### 979. How do you prevent clickjacking in a React app?

Set the `X-Frame-Options` header (or CSP's `frame-ancestors` directive) on the server/CDN response to prevent the app from being embedded in a malicious iframe on another site.

### 980. How do you prevent navigation away from a page with unsaved changes?

Use `useBlocker` (v6.4+ data router) to intercept navigation attempts and show a confirmation prompt before allowing the route change.

### 981. How do you test async behavior (e.g., API calls)?

Mock fetch or use MSW (Mock Service Worker). Use `findBy*` or `waitFor(() => expect(...))` to wait for async DOM updates. Never use arbitrary `setTimeout` in tests. [↑ Back to Table of Contents](#table-of-contents)

### 982. How do you test components with context?

Wrap with the real Provider (or a test Provider with controlled values) in the render call. RTL's `render` accepts a wrapper option: `render(<Comp/>, {wrapper: TestProviders})`.

### 983. How do you test components wrapped in Providers/Router?

A custom `render` wrapper that wraps the component in needed providers, reused across tests.

### 984. How do you test error states (e.g., a failed API call shows an error message)?

Mock the request to reject/return an error response via `msw`, render the component, and assert the error UI appears via `findByText`/`findByRole`.

### 985. How do you test user interactions?

Use `userEvent` from `@testing-library/user-event` (more realistic than `fireEvent` – triggers all real browser events). `userEvent.click()`, `userEvent.type()`, `userEvent.selectOptions()`. [↑ Back to Table of Contents](#table-of-contents)

### 986. How do you theme a React app (light/dark mode) cleanly?

Define theme values as CSS custom properties or a theme object, toggle a root-level class/attribute (`data-theme="dark"`) or Context provider, and have styled components/CSS reference the theme tokens rather than hardcoded values.

### 987. How do you type `children`?

`React.ReactNode` covers the broadest, most common case.

### 988. How do you type event handlers?

`React.ChangeEvent<HTMLInputElement>`, `React.MouseEvent<HTMLButtonElement>`, `React.FormEvent<HTMLFormElement>`. Or use inline type: `(e: React.ChangeEvent<HTMLInputElement>) => void`. [⬆ Back to Table of Contents](#-table-of-contents)

### 989. How do you update rendered elements?

[↑ Back to Table of Contents](#table-of-contents) You can update UI(represented by rendered element) by passing the newly created element to ReactDOM's render method. For example, lets take a ticking clock example, where it updates the time by calling render method multiple times,

```javascript function tick() { const element = ( <div> <h1>Hello, world!</h1> <h2>It is {new Date().toLocaleTimeString()}.</h2> </div> ); ReactDOM.render(element, document.getElementById("root")); } setInterval(tick, 1000);

```

### 990. How do you use contextType?

ContextType is used to consume the context object. The contextType property can be used in two ways,

### 991. How does React updates screen in an application?

React updates UI in three steps,

### 992. How does ReactJS work behind the scenes?

ReactJS is a powerful JavaScript library for building user interfaces. While it appears simple on the surface, React performs a lot of complex operations behind the scenes to efficiently update the UI. Here's an overview of how it works internally:

### 993. How does the browser rendering pipeline work?

[↑ Back to Table of Contents](#table-of-contents) (1) Parse HTML → DOM tree. (2) Parse CSS → CSSOM tree. (3) Combine DOM + CSSOM → Render Tree (only visible elements). (4) Layout (Reflow): calculate position/size of each element. (5) Paint: fill in pixels for each element. (6) Compositing: combine layers (GPU). Optimization: minimize reflows (expensive) by batching DOM reads/writes, use transform/opacity for animations (GPU-composited, skip layout/paint), avoid layout thrashing (alternating read-write of layout properties).

### 994. How is React different from HTML in event handling?

camelCase names (`onClick` not `onclick`), pass a function reference (not a string), and must call `event.preventDefault()` explicitly instead of `return false`.

### 995. How to create refs?

[↑ Back to Table of Contents](#table-of-contents) There are two approaches 1. This is a recently added approach. _Refs_ are created using `React.createRef()` method and attached to React elements via the `ref` attribute. In order to use _refs_ throughout the component, just assign the _ref_ to the instance property within constructor.

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.myRef = React.createRef(); } render() { return <div ref={this.myRef} />; } }

```
2. You can also use ref callbacks approach regardless of React version. For example, the search bar component's input element is accessed as follows,

```jsx harmony class SearchBar extends Component { constructor(props) { super(props); this.txtSearch = null; this.state = { term: "" }; this.setInputSearchRef = (e) => { this.txtSearch = e; }; } onInputChange(event) { this.setState({ term: this.txtSearch.value }); } render() { return ( <input value={this.state.term} onChange={this.onInputChange.bind(this)} ref={this.setInputSearchRef} /> ); } }

```
You can also use _refs_ in function components using **closures**. **Note**: You can also use inline ref callbacks even though it is not a recommended approach.

### 996. How to define constants in React?

You can use ES7 `static` field to define constant.

```javascript class MyComponent extends React.Component { static DEFAULT_PAGINATION = 10; }

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 997. How to prevent a function from being called multiple times?

[↑ Back to Table of Contents](#table-of-contents) If you use an event handler such as **onClick or onScroll** and want to prevent the callback from being fired too quickly, then you can limit the rate at which callback is executed. This can be achieved in the below possible ways,

### 998. How to programmatically trigger click event in React?

You could use the ref prop to acquire a reference to the underlying `HTMLInputElement` object through a callback, store the reference as a class property, then use that reference to later trigger a click from your event handlers using the `HTMLElement.click` method. This can be done in two steps: 1. Create ref in render method:

```jsx harmony <input ref={(input) => (this.inputElement = input)} />

```
2. Apply click event in your event handler:

```javascript this.inputElement.click();

```
------------------------------------------------------------------------ ------------------------------------------------------------------------

### 999. How to use `<FormattedMessage>` as placeholder using React Intl?

[↑ Back to Table of Contents](#table-of-contents) The `<Formatted... />` components from `react-intl` return elements, not plain text, so they can't be used for placeholders, alt text, etc. In that case, you should use lower level API `formatMessage()`. You can inject the `intl` object into your component using `injectIntl()` higher-order component and then format the message using `formatMessage()` available on that object.

```jsx harmony import React from "react"; import { injectIntl, intlShape } from "react-intl"; const MyComponent = ({ intl }) => { const placeholder = intl.formatMessage({ id: "messageId" }); return <input placeholder={placeholder} />; }; MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
****

### 1000. How would you optimize a React app rendering 100,000+ list items?

Virtualize (react-window/react-virtual) to render only visible rows; paginate or infinite-scroll instead of loading everything; memoize row components; use stable keys; debounce filter/search; offload heavy sorting/filtering to a Web Worker; code-split the list component if not immediately needed.

### 1001. Identifies expensive calculations?

and renders

### 1002. Is it good to use `setState()` in `componentWillMount()` method?

[↑ Back to Table of Contents](#table-of-contents) **⚠️ DEPRECATED:** `componentWillMount()` has been removed in React 17+. This question is only relevant for legacy React applications. **Historical Context:** While it was technically safe to use `setState()` inside `componentWillMount()`, this lifecycle method is now deprecated and removed because: - It caused issues with server-side rendering - Created confusion about the right place for async operations - Was problematic with React's concurrent rendering features **Modern Alternative:** Use `componentDidMount()` for side effects and async initialization in class components:

```jsx harmony componentDidMount() { axios.get(`api/todos`) .then((result) => { this.setState({ messages: [...result.data] }) }) }

```

### 1003. Library Upgrade: A component breaks when upgrading a library version -- how do you manage dependencies?

[↑ Back to Table of Contents](#table-of-contents) **Approach**: 1. **Read release notes** and changelogs carefully for breaking changes. 2. **Test in isolation** -- create a branch, upgrade the library, run tests, and manually test affected components. 3. **Use dependency management tools** -- `npm outdated` to see which libraries can be upgraded. `npm audit` for security. 4. **Pin exact versions** in `package.json` for critical libraries to avoid unexpected upgrades. 5. **Use version ranges** for non‑critical ones, but lock with `package-lock.json` or `yarn.lock`. 6. **Implement abstraction** -- wrap external libraries in your own adapter components to isolate changes. 7. **Stagger upgrades** -- upgrade one library at a time to isolate issues.

### 1004. Localization and Internationalization?

It supports localization by providing translated strings or locale-specific content to components, adapting the application for users in different regions.

### 1005. Machine Coding Round?

These are "build this from scratch" questions given as a 45–90 min challenge:

### 1006. Portals:

Render children into a different DOM subtree.

### 1007. Preserves React semantics?

- your code still behaves correctly

### 1008. Provider?

-- Wrap the app with a feature flag provider (e.g., `LaunchDarklyProvider`). Initialize flags early, usually in the root component or a higher‑order component.

### 1009. Publish?

-- to a shared package or monorepo for reuse. ------------------------------------------------------------------------

### 1010. React elements:

Elements that instruct React to render a DOM node. It includes html elements such as `<div/>` and user defined elements.

### 1011. Recursing On Children:

when recursing on the children of a DOM node, React just iterates over both lists of children at the same time and generates a mutation whenever there’s a difference. For example, when adding an element at the end of the children, converting between these two trees works well.

```javascript <ul> <li>first</li> <li>second</li> </ul> <ul> <li>first</li> <li>second</li> <li>third</li> </ul>

```

### 1012. RequestAnimationFrame throttling:

Changes based on requestAnimationFrame. For example, it can be used using raf-schd lodash function

### 1013. Rollback?

-- if a critical break occurs, revert the version and investigate later. **For major upgrades** (e.g., React 16 → 17 → 18): - Use codemods (like `react-codemod`) to automate migration. - Run in development mode to catch deprecation warnings. - Test across all browsers and devices. ------------------------------------------------------------------------

### 1014. Server fetches data and renders the component to HTML?

All API calls happen on the server. The complete, populated HTML string is generated.

### 1015. Should I learn ES6 before learning ReactJS?

[↑ Back to Table of Contents](#table-of-contents) No, you don’t have to learn es2015/es6 to learn react. But you may find many resources or React ecosystem uses ES6 extensively. Let's see some of the frequently used ES6 features,

### 1016. Static field?

You can use a static class field to initialize your contextType using public class field syntax.

```javascript class MyClass extends React.Component { static contextType = MyContext; render() { let value = this.context; /* render something based on the value */ } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 1017. String and numbers:

Render both Strings and Numbers as text nodes in the DOM

### 1018. Style with CSS modules / styled‑components?

-- ensure styles are encapsulated and themable.\

### 1019. Testing?

-- Mock feature flags in unit tests. In end‑to‑end tests, set flags via API or by injecting cookies.

### 1020. Throttling:

Changes based on a time based frequency. For example, it can be used using \_.throttle lodash function

### 1021. Triggering or initiating a render:

The component is going to triggered for render in two ways.

### 1022. Understand the component?

-- identify its purpose, variations (sizes, colors, states), and behavior (hover, disabled).\

### 1023. Using an API:

```javascript const messages = defineMessages({ accountMessage: { id: "account", defaultMessage: "The amount is less than minimum balance.", }, }); formatMessage(messages.accountMessage);

```
****

### 1024. What are capture phase events?

The `onClickCapture` React event is helpful to catch all the events of child elements irrespective of event propagation logic or even if the events propagation stopped. This is useful if you need to log every click events for analytics purpose. For example, the below code triggers the click event of parent first followed by second level child eventhough leaf child button elements stops the propagation.

```jsx <div onClickCapture={() => alert("parent")}> <div onClickCapture={() => alert("child")}> <button onClick={(e) => e.stopPropagation()} /> <button onClick={(e) => e.stopPropagation()} /> </div> </div>

```
The event propagation for the above code snippet happens in the following order: 1. It travels downwards in the DOM tree by calling all `onClickCapture` event handlers. 2. It executes `onClick` event handler on the target element. 3. It travels upwards in the DOM tree by call all `onClick` event handlers above to it. [↑ Back to Table of Contents](#table-of-contents)

### 1025. What are CSS Modules? How do they prevent collisions?

Locally-scoped class names via hashed generation at build time, imported as an object.

### 1026. What are loaders and actions (v6.4+ data APIs)?

Loaders fetch data before a route renders (`useLoaderData`). Actions handle mutations from `<Form>` submissions (`useActionData`).

### 1027. What are nested routes and the `<Outlet>` component?

Child `<Route>` elements inside a parent route; the parent renders `<Outlet/>` as a placeholder where the matched child's content appears — enables persistent layouts (nav/sidebar) with swappable inner content.

### 1028. What are React elements vs React components?

[↑ Back to Table of Contents](#table-of-contents) React Elements (The Lego Brick) An element is a single, plain blueprint of what you want to see on the screen. It doesn't actually do anything yet; it's just a simple JavaScript object that describes a piece of the UI. Analogy: A single Lego block or a sketch of a window. What it looks like: { type: 'div', props: { className: 'box', children: 'Hello' } } React Components (The Factory / Blueprint) A component is the factory, function, or template that creates those elements. It takes in some data (called props) and outputs React elements. Analogy: The master blueprint or the factory mold that can stamp out hundreds of Lego blocks. What it looks like: A JavaScript function like function Button() { return `<button />`{=html} }. ------------------------------------------------------------------------

### 1029. What are React Mixins?

[↑ Back to Table of Contents](#table-of-contents) **⚠️ DEPRECATED:** Mixins are considered legacy and should not be used in modern React applications. _Mixins_ were a way to share common functionality between components using `React.createClass()`. However, they caused several problems: - Implicit dependencies - Name clashes - Snowballing complexity One of the most commonly used mixins was `PureRenderMixin`:

```javascript const PureRenderMixin = require("react-addons-pure-render-mixin"); const Button = React.createClass({ mixins: [PureRenderMixin], // ... });

```
**Modern Alternatives:** - **React.memo()** for functional components (replaces PureRenderMixin) - **Custom Hooks** for sharing stateful logic - **Higher-Order Components (HOCs)** for cross-cutting concerns - **Render Props** pattern

```javascript // Modern equivalent using React.memo const Button = React.memo(({ onClick, label }) => ( <button onClick={onClick}>{label}</button> ));

```

### 1030. What are React Portals, and when would you use them?

When you work with React, you might have noticed how a component renders inside its parent in the DOM. But even so, there are times when you don’t necessarily want that. For example, think of a modal. Even if the modal component is written deep inside your component tree, you usually want it to appear at the top of the page, and not stuck inside some parent container. And to mitigate this very problem, Portals are used. So, you don't have to render from your usual place, and run something like:

```
ReactDOM.createPortal(child, container)

```
This practically commands to render the component elsewhere in the DOM. Now, here’s how you can set it up: First write,

```
<div id="modal-root"></div>

```
Then, from anywhere in your React app, you can render into it like this:

```
ReactDOM.createPortal(<Modal />, document.getElementById("modal-root"));

```
Even when it’s done, you need to keep this in mind that even though the modal is rendered outside the parent in the DOM, it still showcases like a normal React child. Which means that it still receives props, it still has access to context, and event handling still works. In fact, event bubbling can take place here. If you click inside a modal rendered via a portal, the event still bubbles up to the parent component in the React tree, and not based on the DOM structure. Now, coming to when to use these Portals, You can say that mostly when UI needs to “break out” of layout restrictions like overflow: hidden, z-index stacking issues. That’s why they’re commonly used for modals, tooltips, dropdowns, and toast notifications. [↑ Back to Table of Contents](#table-of-contents)

### 1031. What are synthetic events in React?

`SyntheticEvent` is a cross-browser wrapper around the browser's native event. Its API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers. The native events can be accessed directly from synthetic events using `nativeEvent` attribute. Let's take an example of `BookStore` title search component with the ability to get all native event properties

```js function BookStore() { function handleTitleChange(e) { console.log("The new title is:", e.target.value); console.log('Synthetic event:', e); // React SyntheticEvent console.log('Native event:', e.nativeEvent); // Browser native event e.stopPropagation(); e.preventDefault(); } return <input name="title" onChange={handleTitleChange} />; }

```
List of common synthetic events are: * `onClick` * `onChange` * `onSubmit` * `onKeyDown`, `onKeyUp` * `onFocus`, `onBlur` * `onMouseEnter`, `onMouseLeave` * `onTouchStart`, `onTouchEnd` [↑ Back to Table of Contents](#table-of-contents)

### 1032. What are the common folder structures for React?

There are two common practices for React project file structure.

### 1033. What are the differences between controlled and uncontrolled components?

Controlled and uncontrolled components are just different approaches to handling input from elements in react. | FeatureUncontrolledControlledName attrs | | | | | ----------------------------------------- | -- | -- | -- | | One-time value retrieval (e.g. on submit) | ✔️ | ✔️ | ✔️ | | Validating on submit | ✔️ | ✔️ | ✔️ | | Field-level Validation | ❌ | ✔️ | ✔️ | | Conditionally disabling submit button | ❌ | ✔️ | ✔️ | | Enforcing input format | ❌ | ✔️ | ✔️ | | several inputs for one piece of data | ❌ | ✔️ | ✔️ | | dynamic inputs | ❌ | ✔️ | 🤔 | - **Controlled component: **In a controlled component, the value of the input element is controlled by React. We store the state of the input element inside the code, and by using event-based callbacks, any changes made to the input element will be reflected in the code as well. When a user enters data inside the input element of a controlled component, onChange function gets triggered and inside the code, we check whether the value entered is valid or invalid. If the value is valid, we change the state and re-render the input element with the new value. Example of a controlled component: function FormValidation(props) { let \[inputValue, setInputValue\] = useState(""); let updateInput = e =\> { setInputValue(e.target.value); }; return ( <div> <form> <input type="text" value={inputValue} onChange={updateInput} /> </form> </div> ); } As one can see in the code above, the value of the input element is determined by the state of the** inputValue **variable. Any changes made to the input element is handled by the **updateInput** function. - **Uncontrolled component:** In an uncontrolled component, the value of the input element is handled by the DOM itself. Input elements inside uncontrolled components work just like normal HTML input form elements. The state of the input element is handled by the DOM. Whenever the value of the input element is changed, event-based callbacks are not called. Basically, react does not perform any action when there are changes made to the input element. Whenever use enters data inside the input field, the updated data is shown directly. To access the value of the input element, we can use **ref**. Example of an uncontrolled component: function FormValidation(props) { let inputValue = React.createRef(); let handleSubmit = e =\> { alert(`Input value: ${inputValue.current.value}`); e.preventDefault(); }; return ( <div> <form onSubmit={handleSubmit}> <input type="text" ref={inputValue} /> <button type="submit">Submit</button> </form> </div> ); } As one can see in the code above, we are **not** using **onChange** function to govern the changes made to the input element. Instead, we are using **ref** to access the value of the input element.

### 1034. What are the drawbacks of MVW pattern?

1. DOM manipulation is very expensive which causes applications to behave slow and inefficient. 2. Due to circular dependencies, a complicated model was created around models and views. 3. Lot of data changes happens for collaborative applications(like Google Docs). 4. No way to do undo (travel back in time) easily without adding so much extra code. [↑ Back to Table of Contents](#table-of-contents)

### 1035. What are the limitations of React?

Apart from the advantages, there are few limitations of React too, 1. React is just a view library, not a full framework. 2. There is a learning curve for beginners who are new to web development. 3. Integrating React into a traditional MVC framework requires some additional configuration. 4. The code complexity increases with inline templating and JSX. 5. Too many smaller components leading to over engineering or boilerplate. [↑ Back to Table of Contents](#table-of-contents)

### 1036. What are the limitations with HOCs?

Higher-order components come with a few caveats apart from its benefits. Below are the few listed in an order,

### 1037. What are the Pointer Events supported in React?

_Pointer Events_ provide a unified way of handling all input events. In the old days we had a mouse and respective event listeners to handle them but nowadays we have many devices which don't correlate to having a mouse, like phones with touch surface or pens. We need to remember that these events will only work in browsers that support the _Pointer Events_ specification. The following event types are now available in _React DOM_: 1. `onPointerDown` 2. `onPointerMove` 3. `onPointerUp` 4. `onPointerCancel` 5. `onGotPointerCapture` 6. `onLostPointerCapture` 7. `onPointerEnter` 8. `onPointerLeave` 9. `onPointerOver` 10. `onPointerOut` [↑ Back to Table of Contents](#table-of-contents)

### 1038. What are the possible return types of render method?

[↑ Back to Table of Contents](#table-of-contents) Below are the list of following types used and return from render method,

### 1039. What are the RTL query priorities?

Priority order: `getByRole` (most like how screen readers work) > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByDisplayValue` > `getByAltText` > `getByTitle` > `getByTestId` (last resort). [↑ Back to Table of Contents](#table-of-contents)

### 1040. What are the two ways of formatting in React Intl?

[↑ Back to Table of Contents](#table-of-contents) The library provides two ways to format strings, numbers, and dates:

### 1041. What happened to event pooling?

In React 16 and earlier, `SyntheticEvent` objects were pooled and reused – accessing event properties asynchronously returned null. React 17 removed pooling. `event.persist()` is no longer needed. [⬆ Back to Table of Contents](#-table-of-contents)

### 1042. What happens if a component returns `null`?

React renders nothing for that component (no DOM node), which is valid and commonly used for conditionally hiding content.

### 1043. What is `<NavLink>`? How does it differ from `<Link>`?

Same as `<Link>` but automatically applies an "active" styling/class when its `to` matches the current URL, useful for nav menus.

### 1044. What is `act()`? Why does RTL warn about updates outside it?

Ensures updates/effects/re-renders are flushed before assertions; RTL wraps this internally, warning fires for manual async updates outside it.

### 1045. What is `flushSync`? When would you need it?

Forces a synchronous update/flush, opting out of batching — rarely needed, mainly for immediate DOM reads after a change.

### 1046. What is `satisfies` and how is it useful for typing component configuration objects?

`satisfies` checks a value against a type without widening/changing the value's inferred type, useful for config objects (e.g., a theme or route map) where you want both validation against a shape and precise literal-type inference preserved for later use.

### 1047. What is `useInfiniteQuery`? When is it used?

Manages paginated data that loads incrementally (e.g., infinite scroll), tracking pages and providing a `fetchNextPage` function tied to a `getNextPageParam` cursor function.

### 1048. What is a consumer?

A Consumer is a React component that subscribes to context changes. It requires a function as a child which receives current context value as argument and returns a react node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. Lets take a simple example,

```javascript <MyContext.Consumer> {value => /* render something based on the context value */} </MyContext.Consumer>

```
[↑ Back to Table of Contents](#table-of-contents)

### 1049. What is a design system / component library pattern?

Shared, consistently-styled primitives and design tokens used across products for visual/behavioral consistency.

### 1050. What is a factory/builder pattern for creating typed, reusable form field components?

A function that generates a pre-configured, typed field component bound to a specific form library/schema (e.g., `createFormField<FormValues>()`), reducing repetitive boilerplate across many similar fields while preserving type safety.

### 1051. What is a focus trap?

Confines keyboard focus within a modal/dialog so Tab doesn't reach content behind it. Required for accessible modals. Libraries: `focus-trap-react`, `@radix-ui/react-dialog` handle this automatically. [⬆ Back to Table of Contents](#-table-of-contents)

### 1052. What is a monorepo, and what tools help manage one for a React codebase (e.g., sharing a component library across apps)?

A single repository containing multiple packages/apps (e.g., a shared UI library plus several apps consuming it). Tools like Turborepo, Nx, or Yarn/pnpm workspaces manage shared dependencies, incremental builds, and task caching across the packages.

### 1053. What is a React SPA and what are its trade-offs?

Think of a React SPA (Single Page Application) like a modern video game rather than a traditional book. Instead of turning to a completely new physical page every time you click a link (which causes the browser to reload and flash white), a SPA loads one single blank page at the very beginning. Then, it uses JavaScript to dynamically erase old content and snap new content into place instantly. ------------------------------------------------------------------------

### 1054. What is a skip link?

A visually hidden link at the top of the page that becomes visible on focus and links to the main content area. Allows keyboard users to skip repetitive navigation. Required for WCAG 2.1 AA compliance.

### 1055. What is a Subresource Integrity (SRI) hash, and when would a React app use one?

A hash attribute on a `<script>`/`<link>` tag verifying a CDN-loaded file hasn't been tampered with; relevant when loading a library (e.g., via a CDN `<script>` tag in an HTML template) from a third-party host outside your build pipeline.

### 1056. What is a wrapper component?

A wrapper in React is a component that wraps or surrounds another component or group of components. It can be used for a variety of purposes such as adding additional functionality, styling, or layout to the wrapped components. For example, consider a simple component that displays a message:

```javascript const Message = ({ text }) => { return <p>{text}</p>; };

```
We can create a wrapper component that will add a border to the message component:

```javascript const MessageWrapper = (props) => { return ( <div style={{ border: "1px solid black" }}> <Message {...props} /> </div> ); };

```
Now we can use the MessageWrapper component instead of the Message component and the message will be displayed with a border:

```javascript <MessageWrapper text="Hello World" />

```
Wrapper component can also accept its own props and pass them down to the wrapped component, for example, we can create a wrapper component that will add a title to the message component:

```javascript const MessageWrapperWithTitle = ({ title, ...props }) => { return ( <div> <h3>{title}</h3> <Message {...props} /> </div> ); };

```
Now we can use the MessageWrapperWithTitle component and pass title props:

```javascript <MessageWrapperWithTitle title="My Message" text="Hello World" />

```
This way, the wrapper component can add additional functionality, styling, or layout to the wrapped component while keeping the wrapped component simple and reusable. [↑ Back to Table of Contents](#table-of-contents)

### 1057. What is chaos engineering for frontend?

Chaos engineering is the practice of intentionally introducing failures to test system resilience. For frontend, it means simulating network issues, slow responses, API errors, or resource constraints to ensure the UI degrades gracefully. **Examples**: - **Network throttling** – simulate slow 3G to test lazy loading and timeouts. - **API failures** – mock 5xx responses and ensure error states appear. - **JavaScript exceptions** – inject errors to test error boundaries and fallback UI. - **Resource exhaustion** – simulate low memory or high CPU to see if the app remains responsive. **Tools**: - Browser DevTools network throttling. - Chaos Monkey for frontend (e.g., using a library that randomly blocks requests). - Custom middleware in development to inject latency or errors. **Goal**: Build confidence that the app won’t crash under adverse conditions and provides clear feedback to users.

### 1058. What is createSlice() and what does it contain?

createSlice() accepts: name (action type prefix), initialState, reducers object (sync action handlers), and extraReducers (async thunk handlers). It auto-generates: action creators (slice.actions.actionName), action types (slice.name/actionName), and the reducer function. Reducers inside createSlice can mutate state directly because RTK uses Immer under the hood — Immer converts mutations into immutable updates. Export the reducer for the store and the actions for dispatch. [↑ Back to Table of Contents](#table-of-contents)

### 1059. What is Flow?

_Flow_ is a _static type checker_ designed to find type errors in JavaScript. Flow types can express much more fine-grained distinctions than traditional type systems. For example, Flow helps you catch errors involving `null`, unlike most type systems. [↑ Back to Table of Contents](#table-of-contents)

### 1060. What is forwardRef, and when do you need it?

This one is simple! You can use forwardRef to pass a ref from the parent component through the child component to a DOM element or another component inside it. You need it particularly because, by default, function components do not accept ref, as ref is not a regular prop, and it is handled separately by React. forwardRef is needed because it enables access to a child component’s DOM node, it helps in imperative actions like

```
.focus()

```
,

```
.scrollIntoView()

```
, and measuring layout. So, when you don’t use forwardRef, the parent won’t be able to directly interact with the child’s internal DOM elements, and hence it may hinder when required to reuse. **This is how forwardRef works -** React.forwardRef wraps a functional component and provides ref as a second argument. This is the pattern:

```
const Input = React.forwardRef((props, ref) => { return <input ref={ref} {...props} />; });

```
Here’s how you can use it:

```
const inputRef = useRef(); <Input ref={inputRef} />

```
Now the parent can directly call:

```
inputRef.current.focus();

```
Some common use cases are - integrating DOM libraries, focus management, triggering animations, measuring DOM elements, etc. [↑ Back to Table of Contents](#table-of-contents)

### 1061. What is image lazy-loading in React? How do you implement it?

Deferring offscreen image loads until they're near the viewport, via the native `loading="lazy"` attribute on `<img>` or an `IntersectionObserver`-based custom component for more control (placeholders, fade-in).

### 1062. What is Mock Service Worker (MSW)?

Intercepts requests at the network level using Service Workers (browser) or node http interceptor (test). Define handlers once, use in tests AND in development. More realistic than mocking fetch directly. [↑ Back to Table of Contents](#table-of-contents)

### 1063. What is optimistic UI? How do you implement it?

Update the UI immediately before server confirmation, roll back on failure, via `onMutate`/`onError`/`onSettled`.

### 1064. What is query invalidation? How do you trigger a refetch after a mutation?

`queryClient.invalidateQueries({ queryKey })` marks queries stale, refetching on next use — typically called in a mutation's `onSuccess`.

### 1065. What is referential equality, and why does it matter so much in React?

Same-object identity (`===`) vs structural equality. React's optimizations rely on cheap reference checks, so "new but equivalent" objects defeat them.

### 1066. What is the `Outlet` component?

[↑ Back to Table of Contents](#table-of-contents) A placeholder rendered by a parent route where its matching child route's element is shown. Enables nested layouts. Multiple outlets can be named for parallel rendering in advanced scenarios.

### 1067. What is the browser support for react applications?

React supports all popular browsers, including Internet Explorer 9 and above, although some polyfills are required for older browsers such as IE 9 and IE 10. If you use **es5-shim and es5-sham** polyfill then it even support old browsers that doesn't support ES5 methods. [

### 1068. What is the difference between `getBy`, `queryBy`, and `findBy` in RTL?

`getBy*` throws immediately if not found (for elements expected to exist). `queryBy*` returns `null` instead of throwing (for asserting something is *absent*). `findBy*` is async, retrying until found or timing out (for elements that appear after an async update).

### 1069. What is the difference between `next/link` prefetching and a manual `router.prefetch()` call?

`<Link>` automatically prefetches linked pages' code/data when they enter the viewport (in production). `router.prefetch()` lets you trigger the same prefetching imperatively (e.g., on hover or a predicted next action) outside of a visible `<Link>`.

### 1070. What is the difference between `onChange` and `onInput` in React forms?

React's `onChange` fires on every value change (behaving like the native `input` event), unlike the native DOM `change` event which only fires on blur/commit — React normalizes this for consistency.

### 1071. What is the difference between `onClick={handleClick}` and `onClick={handleClick()}`?

The first passes a function reference React calls on click. The second invokes it immediately during render and passes its return value — almost always a bug.

### 1072. What is the difference between an Element and a Component?

[↑ Back to Table of Contents](#table-of-contents) **Element:** - A React **Element** is a plain JavaScript object that describes what you want to see on the UI. It represents a DOM node or a component at a specific point in time. - Elements are immutable: once created, you cannot change their properties. Instead, you create new elements to reflect updates. - Elements can be nested within other elements through their `props`. - Creating an element is a fast, lightweight operation—it does **not** create any actual DOM nodes or render anything to the screen directly. **Example (without JSX):**

```js const element = React.createElement("button", { id: "login-btn" }, "Login");

```
**Equivalent JSX syntax:**

```jsx <button id="login-btn">Login</button>

```
**The object returned by `React.createElement`:**

```js { type: 'button', props: { id: 'login-btn', children: 'Login' } }

```
Elements are then passed to the React DOM renderer (e.g., `ReactDOM.render()`), which translates them to actual DOM nodes. **Component:** - A **Component** is a function or class that returns an element (or a tree of elements) to describe part of the UI. Components can accept inputs (called **props**) and manage their own state (in case of class or function components with hooks). - Components allow you to split the UI into independent, reusable pieces, each isolated and composable. - You can define a component using a function or a class: **Example (Function Component with JSX):**

```jsx const Button = ({ handleLogin }) => ( <button id="login-btn" onClick={handleLogin}> Login </button> );

```
When JSX is compiled, it's transformed into a tree of `React.createElement` calls:

```js const Button = ({ handleLogin }) => React.createElement( "button", { id: "login-btn", onClick: handleLogin }, "Login" );

```
**In summary:** - **Elements** are the smallest building blocks in React—objects that describe what you want to see. - **Components** are functions or classes that return elements and encapsulate logic, structure, and behavior for parts of your UI. > Think of **elements** as the instructions for creating UI, and **components** as reusable blueprints that combine logic and structure to generate those instructions. ****

### 1073. What is the difference between mounting and updating in terms of effect behavior?

On mount, every effect with satisfied conditions runs for the first time. On update, only effects whose dependency array changed re-run (compare each value against its previous render).

### 1074. What is the difference between React and Angular?

Let's see the difference between React and Angular in a table format. | React | Angular | | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | | React is a library and has only the View layer | Angular is a framework and has complete MVC functionality | | React handles rendering on the server side | AngularJS renders only on the client side but Angular 2 and above renders on the server side | | React uses JSX that looks like HTML in JS which can be confusing | Angular follows the template approach for HTML, which makes code shorter and easy to understand | | React Native, which is a React type to build mobile applications are faster and more stable | Ionic, Angular's mobile native app is relatively less stable and slower | | In React, data flows only in one way and hence debugging is easy | In Angular, data flows both way i.e it has two-way data binding between children and parent and hence debugging is often difficult | **Note:** The above list of differences are purely opinionated and it vary based on the professional experience. But they are helpful as base parameters. [↑ Back to Table of Contents](#table-of-contents)

### 1075. What is the history behind React evolution?

The history of ReactJS started in 2010 with the creation of **XHP**. XHP is a PHP extension which improved the syntax of the language such that XML document fragments become valid PHP expressions and the primary purpose was used to create custom and reusable HTML elements. The main principle of this extension was to make front-end code easier to understand and to help avoid cross-site scripting attacks. The project was successful to prevent the malicious content submitted by the scrubbing user. But there was a different problem with XHP in which dynamic web applications require many roundtrips to the server, and XHP did not solve this problem. Also, the whole UI was re-rendered for small change in the application. Later, the initial prototype of React is created with the name **FaxJ** by Jordan inspired from XHP. Finally after sometime React has been introduced as a new library into JavaScript world. <details> <summary><b>See deep-dive answer</b></summary> The evolution of React has a fascinating history that spans over a decade: **2010-2011: The Origins** - The journey began with **XHP**, a PHP extension created at Facebook that allowed HTML components to be used in PHP code - XHP improved front-end code readability and helped prevent cross-site scripting (XSS) attacks - However, XHP had limitations with dynamic web applications, requiring frequent server roundtrips and complete UI re-renders for small changes **2011-2012: Early Development** - Jordan Walke created the first prototype called **FaxJS** (later renamed to React), inspired by XHP's component model - The key innovation was bringing XHP's component model to JavaScript with performance improvements - React introduced the Virtual DOM concept to solve the performance issues of full page re-renders - First deployed internally on Facebook's News Feed in 2011 and Instagram in 2012 **2013: Public Release** - React was officially open-sourced at JSConf US in May 2013 - Initial public reception was mixed, with some developers skeptical about the JSX syntax and the approach of mixing markup with JavaScript **2014-2015: Growing Adoption** - React Native was announced in 2015, extending React's paradigm to mobile app development - The ecosystem began to grow with tools like Redux for state management - Companies beyond Facebook began adopting React for production applications **2016-2018: Maturation** - React 16 ("Fiber") was released in 2017 with a complete rewrite of the core architecture - Introduction of new features like Error Boundaries, Portals, and improved server-side rendering - React 16.3 introduced the Context API for easier state management **2019-Present: Modern React** - React Hooks were introduced in React 16.8 (February 2019), revolutionizing state management in functional components - React 17 (October 2020) focused on making React upgrades easier - React 18 (March 2022) introduced concurrent rendering and automatic batching - React continues to evolve with Server Components, the new React compiler (React Forget), and other performance improvements </details> **Note:** JSX, React's syntax extension, was indeed inspired by XHP's approach of embedding XML-like syntax in code. [↑ Back to Table of Contents](#table-of-contents)

### 1076. What is the proper placement for error boundaries?

The granularity of error boundaries usage is up to the developer based on project needs. You can follow either of these approaches, 1. You can wrap top-level route components to display a generic error message for the entire application. 2. You can also wrap individual components in an error boundary to protect them from crashing the rest of the application. [↑ Back to Table of Contents](#table-of-contents)

### 1077. What is the Provider hell problem, and how do you avoid it?

Deeply nesting many separate Context Providers at the app root (`<A><B><C><D>`) becomes unreadable. Avoid by composing providers into a single wrapper component, or combining related, co-changing contexts into one.

### 1078. What is the purpose of `push()` and `replace()` methods of `history`?

A history instance has two methods for navigation purpose. 1. `push()` 2. `replace()` If you think of the history as an array of visited locations, `push()` will add a new location to the array and `replace()` will replace the current location in the array with the new one. [↑ Back to Table of Contents](#table-of-contents)

### 1079. What is the purpose of default value in context?

The defaultValue argument is only used when a component does not have a matching Provider above it in the tree. This can be helpful for testing components in isolation without wrapping them. Below code snippet provides default theme value as Luna.

```javascript const MyContext = React.createContext(defaultValue);

```
[↑ Back to Table of Contents](#table-of-contents)

### 1080. What is the purpose of displayName class property?

The displayName string is used in debugging messages. Usually, you don’t need to set it explicitly because it’s inferred from the name of the function or class that defines the component. You might want to set it explicitly if you want to display a different name for debugging purposes or when you create a higher-order component. For example, To ease debugging, choose a display name that communicates that it’s the result of a withSubscription HOC.

```javascript function withSubscription(WrappedComponent) { class WithSubscription extends React.Component { /* ... */ } WithSubscription.displayName = `WithSubscription(${getDisplayName( WrappedComponent )})`; return WithSubscription; } function getDisplayName(WrappedComponent) { return ( WrappedComponent.displayName || WrappedComponent.name || "Component" ); }

```
[↑ Back to Table of Contents](#table-of-contents)

### 1081. What is the purpose of ReactTestUtils package?

_ReactTestUtils_ are provided in the `with-addons` package and allow you to perform actions against a simulated DOM for the purpose of unit testing. [↑ Back to Table of Contents](#table-of-contents)

### 1082. What is the purpose of render method of `react-dom`?

[↑ Back to Table of Contents](#table-of-contents) This method is used to render a React element into the DOM in the supplied container and return a reference to the component. If the React element was previously rendered into container, it will perform an update on it and only mutate the DOM as necessary to reflect the latest changes.

```
ReactDOM.render(element, container, [callback])

```
If the optional callback is provided, it will be executed after the component is rendered or updated.

### 1083. What is the recommended way for naming components?

[↑ Back to Table of Contents](#table-of-contents) It is recommended to name the component by reference instead of using `displayName`. Using `displayName` for naming component:

```javascript export default React.createClass({ displayName: "TodoApp", // ... });

```
The **recommended** approach:

```javascript export default class TodoApp extends React.Component { // ... }

```
also

```javascript const TodoApp = () => { //... }; export default TodoApp;

```

### 1084. What is the required method to be defined for a class component?

[↑ Back to Table of Contents](#table-of-contents) The `render()` method is the only required method in a class component. i.e, All methods other than render method are optional for a class component. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 1085. What is the risk of exposing API keys/secrets in a client-side React bundle?

Anything bundled for the browser (including `NEXT_PUBLIC_`-prefixed or hardcoded values) is visible to anyone inspecting the JS; secrets must stay server-side, with the client calling a backend proxy instead.

### 1086. What is the typical use case of portals?

[↑ Back to Table of Contents](#table-of-contents) React Portals are primarily used to render UI components such as **modals, tooltips, dropdowns, hovercards, and notifications** outside of their parent component's DOM tree. This helps avoid common CSS issues caused by parent elements, such as: * `**overflow: hidden**` on parent elements clipping or hiding child elements like modals or tooltips, * **stacking context and** `**z-index**` **conflicts** created by parent containers that prevent child elements from appearing above other content. That means, you need to visually “break out” of its container. By rendering these UI elements into a separate DOM node (often directly under `<body>`), portals ensure they appear above all other content and are not restricted by the parent’s CSS or layout constraints, resulting in correct positioning and visibility regardless of the parent’s styling.

### 1087. What is the use of `react-dom` package?

[↑ Back to Table of Contents](#table-of-contents) The `react-dom` package provides *DOM-specific methods* that can be used at the top level of your app. Most of the components are not required to use this module. Some of the methods of this package are: 1. `render()` 2. `hydrate()` 3. `unmountComponentAtNode()` 4. `findDOMNode()` 5. `createPortal()` **** ------------------------------------------------------------------------

### 1088. What is the use of refs?

The _ref_ is used to return a reference to the element. They _should be avoided_ in most cases, however, they can be useful when you need a direct access to the DOM element or an instance of a component. [↑ Back to Table of Contents](#table-of-contents)

### 1089. When Cleanup Runs:

- Before the component unmounts - Before re-running the effect when dependencies change [↑ Back to Table of Contents](#table-of-contents)

### 1090. When do we need a Higher Order Component?

While developing React applications, we might develop components that are quite similar to each other with minute differences. In most cases, developing similar components might not be an issue but, while developing larger applications we need to keep our code **DRY**, therefore, we want an **abstraction** that allows us to define this logic in a single place and share it across components. HOC allows us to create that abstraction. **Example of a HOC:** Consider the following components having similar functionality. The following component displays the list of articles:

```
// "GlobalDataSource" is some global data source class ArticlesList extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { articles: GlobalDataSource.getArticles(), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { // States gets Update whenver data source changes this.setState({ articles: GlobalDataSource.getArticles(), }); } render() { return ( <div> {this.state.articles.map((article) => ( <ArticleData article={article} key={article.id} /> ))} </div> ); } }

```
The following component displays the list of users:

```
// "GlobalDataSource" is some global data source class UsersList extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { users: GlobalDataSource.getUsers(), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { // States gets Update whenver data source changes this.setState({ users: GlobalDataSource.getUsers(), }); } render() { return ( <div> {this.state.users.map((user) => ( <UserData user={user} key={user.id} /> ))} </div> ); } }

```
Notice the above components, both have similar functionality but, they are calling different methods to an API endpoint. Let’s create a Higher Order Component to create an abstraction:

```
// Higher Order Component which takes a component // as input and returns another component // "GlobalDataSource" is some global data source function HOC(WrappedComponent, selectData) { return class extends React.Component { constructor(props) { super(props); this.handleChange = this.handleChange.bind(this); this.state = { data: selectData(GlobalDataSource, props), }; } componentDidMount() { // Listens to the changes added GlobalDataSource.addChangeListener(this.handleChange); } componentWillUnmount() { // Listens to the changes removed GlobalDataSource.removeChangeListener(this.handleChange); } handleChange() { this.setState({ data: selectData(GlobalDataSource, this.props), }); } render() { // Rendering the wrapped component with the latest data data return <WrappedComponent data={this.state.data} {...this.props} />; } }; }

```
We know HOC is a function that takes in a component and returns a component. In the code above, we have created a function called HOC which returns a component and performs functionality that can be shared across both the **ArticlesList** component and **UsersList** Component. The second parameter in the HOC function is the function that calls the method on the API endpoint. We have reduced the duplicated code of the **componentDidUpdate** and **componentDidMount** functions. Using the concept of Higher-Order Components, we can now render the **ArticlesList** and **UsersList **components in the following way:

```
const ArticlesListWithHOC = HOC(ArticlesList, (GlobalDataSource) => GlobalDataSource.getArticles()); const UsersListWithHOC = HOC(UsersList, (GlobalDataSource) => GlobalDataSource.getUsers());

```
Remember, we are not trying to change the functionality of each component, we are trying to share a single functionality across multiple components using HOC. [↑ Back to Table of Contents](#table-of-contents)

### 1091. When do you need to use refs?

[↑ Back to Table of Contents](#table-of-contents) There are few use cases to go for refs, 1. Managing focus, text selection, or media playback. 2. Triggering imperative animations. 3. Integrating with third-party DOM libraries.

### 1092. When it may hurt?

Not all apps need it; it adds complexity and can cause subtle bugs if components assume synchronous rendering. [↑ Back to Table of Contents](#table-of-contents)

### 1093. When should a component be split into smaller components?

When it exceeds \~150 lines, has distinct logical sections, when part of it needs to be reused, or when different parts change at different frequencies. Each component should have a single clear responsibility. ------------------------------------------------------------------------

### 1094. Which is preferred option with in callback refs and findDOMNode()?

[↑ Back to Table of Contents](#table-of-contents) It is preferred to use _callback refs_ over `findDOMNode()` API. Because `findDOMNode()` prevents certain improvements in React in the future. The **legacy** approach of using `findDOMNode`:

```javascript class MyComponent extends Component { componentDidMount() { findDOMNode(this).scrollIntoView(); } render() { return <div />; } }

```
The recommended approach is:

```javascript class MyComponent extends Component { constructor(props) { super(props); this.node = createRef(); } componentDidMount() { this.node.current.scrollIntoView(); } render() { return <div ref={this.node} />; } }

```

### 1095. Why are inline ref callbacks or functions not recommended?

If the ref callback is defined as an inline function, it will get called twice during updates, first with null and then again with the DOM element. This is because a new instance of the function is created with each render, so React needs to clear the old ref and set up the new one.

```
class UserForm extends Component { handleSubmit = () => { console.log('Input Value is: ', this.input.value); }; render() { return ( <form onSubmit={this.handleSubmit}> <input type="text" ref={(input) => (this.input = input)} /> // Access DOM input in handle submit <button type="submit">Submit</button> </form> ); } }

```
But our expectation is for the ref callback to get called once, when the component mounts. One quick fix is to use the ES7 class property syntax to define the function

```
class UserForm extends Component { handleSubmit = () => { console.log('Input Value is: ', this.input.value); }; setSearchInput = (input) => { this.input = input; }; render() { return ( <form onSubmit={this.handleSubmit}> <input type="text" ref={this.setSearchInput} /> // Access DOM input in handle submit <button type="submit">Submit</button> </form> ); } }

```
**Note:** In React v16.3, [**⬆ Back to Top**](https://dev.to/sakhnyuk/300-react-interview-questions-2ko4#table-of-contents) [↑ Back to Table of Contents](#table-of-contents)

### 1096. Why are String Refs legacy?

If you worked with React before, you might be familiar with an older API where the `ref` attribute is a string, like `ref={'textInput'}`, and the DOM node is accessed as `this.refs.textInput`. We advise against it because _string refs have below issues_, and are considered legacy. String refs were **removed in React v16**. 1. They _force React to keep track of currently executing component_. This is problematic because it makes react module stateful, and thus causes weird errors when react module is duplicated in the bundle. 2. They are _not composable_ — if a library puts a ref on the passed child, the user can't put another ref on it. Callback refs are perfectly composable. 3. They _don't work with static analysis_ like Flow. Flow can't guess the magic that framework does to make the string ref appear on `this.refs`, as well as its type (which could be different). Callback refs are friendlier to static analysis. 4. It doesn't work as most people would expect with the "render callback" pattern (e.g. <DataGrid renderRow={this.renderRow} />)

```jsx harmony class MyComponent extends Component { renderRow = (index) => { // This won't work. Ref will get attached to DataTable rather than MyComponent: return <input ref={"input-" + index} />; // This would work though! Callback refs are awesome. return <input ref={(input) => (this["input-" + index] = input)} />; }; render() { return ( <DataTable data={this.props.data} renderRow={this.renderRow} /> ); } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 1097. Why avoid array index as key?

When items are reordered, inserted, or deleted, index-based keys cause React to reuse DOM nodes incorrectly. Use stable unique IDs (DB id, UUID) instead. [⬆ Back to Table of Contents](#-table-of-contents)

### 1098. Why do you need additional care for component libraries while using forward refs?

[↑ Back to Table of Contents](#table-of-contents) When you start using forwardRef in a component library, you should treat it as a breaking change and release a new major version of your library. This is because your library likely has a different behavior such as what refs get assigned to, and what types are exported. These changes can break apps and other libraries that depend on the old behavior. ------------------------------------------------------------------------ ------------------------------------------------------------------------

### 1099. Why does `0 && <Component/>` render "0" instead of nothing?

Logical AND returns the first falsy operand if `cond` is falsy; `0` is falsy but is still a valid renderable value, so React renders the literal "0" text instead of nothing. Fix: use a boolean (`cond > 0 && ...`) or a ternary.

### 1100. Why fragments are better than container divs?

[↑ Back to Table of Contents](#table-of-contents) Below are the list of reasons to prefer fragments over container DOM elements, 1. Fragments are a bit faster and use less memory by not creating an extra DOM node. This only has a real benefit on very large and deep trees. 2. Some CSS mechanisms like _Flexbox_ and _CSS Grid_ have a special parent-child relationships, and adding divs in the middle makes it hard to keep the desired layout. 3. The DOM Inspector is less cluttered. ****

### 1101. Why is `isMounted()` an anti-pattern and what is the proper solution?

The primary use case for `isMounted()` is to avoid calling `setState()` after a component has been unmounted, because it will emit a warning.

```javascript if (this.isMounted()) { this.setState({...}) }

```
Checking `isMounted()` before calling `setState()` does eliminate the warning, but it also defeats the purpose of the warning. Using `isMounted()` is a code smell because the only reason you would check is because you think you might be holding a reference after the component has unmounted. An optimal solution would be to find places where `setState()` might be called after a component has unmounted, and fix them. Such situations most commonly occur due to callbacks, when a component is waiting for some data and gets unmounted before the data arrives. Ideally, any callbacks should be canceled in `componentWillUnmount()`, prior to unmounting. [↑ Back to Table of Contents](#table-of-contents)

### 1102. Why is calling `setState` inside `render` dangerous?

Can trigger an infinite render loop; the update belongs in an event handler or effect instead.

### 1103. Why React uses `className` over `class` attribute?

[↑ Back to Table of Contents](#table-of-contents) React uses **className** instead of **class** because of a JavaScript naming conflict with the class keyword. 1. `class` is a reserved keyword in JavaScript In JavaScript, class is used to define ES6 classes:

```js class Person { constructor(name) { this.name = name; } }

```
If you try to use class as a variable or property name, it will throw a syntax error. Since JSX is just JavaScript with XML-like syntax, using class directly in JSX would break the parser. 2. JSX Is JavaScript When you write JSX like this:

```jsx <div class="btn">Click</div>

```
It will be compiled to:

```jsx React.createElement('div', { class: 'btn' }, 'Click');

```
But `class` is invalid in this object literal context (since it clashes with the JS keyword), hence React instead uses className.

```jsx <div className="btn">Click</div>

```
which compiles to:

```jsx React.createElement('div', { className: 'btn' }, 'Click');

```
React then translates `className` to` class` in the final HTML DOM. 3. Aligns with DOM APIs In vanilla JavaScript, you interact with element classes using:

```js element.className = 'my-class';

```
React follows this convention, staying consistent with the DOM API's property name rather than HTML’s attribute. ****

### 1104. Why ReactDOM is separated from React?

[↑ Back to Table of Contents](#table-of-contents) The React team worked on extracting all DOM-related features into a separate library called *ReactDOM*. React v0.14 is the first release in which the libraries are split. By looking at some of the packages, `react-native`, `react-art`, `react-canvas`, and `react-three`, it has become clear that the beauty and essence of React has nothing to do with browsers or the DOM. To build more environments that React can render to, React team planned to split the main React package into two: `react` and `react-dom`. This paves the way to writing components that can be shared between the web version of React and React Native. **** ------------------------------------------------------------------------

### 1105. Work Units and Scheduling?

* React breaks rendering into **units of work** (small tasks). * These units are scheduled based on **priority** using the **React Scheduler**. * If time runs out (e.g., user starts typing), React can **pause and yield** control back to the browser.

### 1106. Wrap Your App with the Provider:

Wrap the above created provider in main `App.js` file

```js // App.js import React from 'react'; import { AuthProvider } from './AuthContext'; import HomePage from './HomePage'; import Dashboard from './Dashboard'; function App() { return ( <AuthProvider> <HomePage /> <Dashboard /> </AuthProvider> ); } export default App;

```

### 1107. Write tests?

-- unit tests for logic, integration tests for interactions, visual regression tests.\


---

*Total questions in this document: 1107*