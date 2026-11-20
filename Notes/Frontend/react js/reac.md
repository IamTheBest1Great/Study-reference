# React.js Interview Questions — Coding / Implementation

A consolidated, deduplicated collection of **hands-on coding, implementation, and output-based React.js interview questions** (build-a-component tasks, custom hooks to implement, predict-the-output snippets), compiled from all available study reference files and organized section-wise.

## Fundamentals, JSX & Virtual DOM

### 1. How do you apply vendor prefixes to inline styles in React?

React _does not_ apply _vendor prefixes_ automatically. You need to add vendor prefixes manually.

```jsx harmony <div style={{ transform: "rotate(90deg)", WebkitTransform: "rotate(90deg)", // note the capital 'W' here msTransform: "rotate(90deg)", // 'ms' is the only lowercase vendor prefix }} />

```
[↑ Back to Table of Contents](#table-of-contents)

### 2. How to access current locale with React Intl?

[↑ Back to Table of Contents](#table-of-contents) You can get the current locale in any component of your application using `injectIntl()`:

```jsx harmony import { injectIntl, intlShape } from "react-intl"; const MyComponent = ({ intl }) => ( <div>{`The current locale is ${intl.locale}`}</div> ); MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
****

### 3. How to import and export components using React and ES6?

You should use default for exporting the components

```jsx harmony import User from "user"; export default function MyProfile { return <User type="customer">//...</User>; }

```
<details><summary><b>See Class</b></summary> <p>

```jsx harmony import React from "react"; import User from "user"; export default class MyProfile extends React.Component { render() { return <User type="customer">//...</User>; } }

```
</p> </details> With the export specifier, the MyProfile is going to be the member and exported to this module and the same can be imported without mentioning the name in other components.

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 695. How to test React Native apps? React Native can be tested only in mobile simulators like iOS and Android. You can run the app in your mobile using expo app ([https://expo.io](https://expo.io/)) Where it syncs using QR code, your mobile and computer should be in same wireless network. [↑ Back to Table of Contents](#table-of-contents) --- ### 696. What environment variables are safe to expose in a React app? Only non-secret config: API base URLs, feature flags, analytics IDs. Never: API secret keys, database credentials, private keys. Vite exposes `VITE_` prefixed vars; CRA exposes `REACT_APP_` prefixed vars – all are visible in the bundle. ## Section 17: Build, Tooling & Ecosystem *The infrastructure around a React application.* [↑ Back to Table of Contents](#table-of-contents) --- ### 697. What is the difference between React Native and React? **React** is a JavaScript library, supporting both front end web and being run on the server, for building user interfaces and web applications. **React Native** is a mobile framework that compiles to native app components, allowing you to build native mobile applications (iOS, Android, and Windows) in JavaScript that allows you to use React to build your components, and implements React under the hood. [↑ Back to Table of Contents](#table-of-contents) --- ## React Ecosystem, Libraries & Internationalization ### 698. Can I use web components in react application? Yes, you can use web components in a react application. Even though many developers won't use this combination, it may require especially if you are using third-party UI components that are written using Web Components. For example, let us use `Vaadin` date picker web component as below,

```
import React, { Component } from 'react'; import './App.css'; import '@vaadin/vaadin-date-picker'; class App extends Component { render() { return ( <div className="App"> <vaadin-date-picker label="When were you born?"></vaadin-date-picker> </div> ); } } export default App;

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 699. How do you access imperative API of web components? Web Components often expose an imperative API to implement its functions. You will need to use a **ref** to interact with the DOM node directly if you want to access imperative API of a web component. But if you are using third-party Web Components, the best solution is to write a React component that behaves as a **wrapper** for your Web Component. [↑ Back to Table of Contents](#table-of-contents) --- ### 700. How do you integrate a non-React library (e.g., D3, Leaflet)? Create a ref for the container DOM node. In `useEffect` (`deps=[]`), initialize the library with the `ref.current` node. Return cleanup to destroy the instance on unmount. Let the library own its DOM; don't let React re-render inside it. [↑ Back to Table of Contents](#table-of-contents) --- ### 701. How to access current locale with React Intl? You can get the current locale in any component of your application using `injectIntl()`:

```jsx harmony import { injectIntl, intlShape } from "react-intl"; const MyComponent = ({ intl }) => ( <div>{`The current locale is ${intl.locale}`}</div> ); MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 702. How to add Bootstrap to a react application? Bootstrap can be added to your React app in a three possible ways, 1. Using the Bootstrap CDN: This is the easiest way to add bootstrap. Add both bootstrap CSS and JS resources in a head tag. 2. Bootstrap as Dependency: If you are using a build tool or a module bundler such as Webpack, then this is the preferred option for adding Bootstrap to your React application

```javascript npm install bootstrap

```
3. React Bootstrap Package: In this case, you can add Bootstrap to our React app is by using a package that has rebuilt Bootstrap components to work particularly as React components. Below packages are popular in this category, 1. react-bootstrap 2. reactstrap [↑ Back to Table of Contents](#table-of-contents) --- ### 703. How to format date using React Intl? The `injectIntl()` higher-order component will give you access to the `formatDate()` method via the props in your component. The method is used internally by instances of `FormattedDate` and it returns the string representation of the formatted date.

```jsx harmony import { injectIntl, intlShape } from "react-intl"; const stringDate = this.props.intl.formatDate(date, { year: "numeric", month: "numeric", day: "numeric", }); const MyComponent = ({ intl }) => ( <div>{`The formatted date is ${stringDate}`}</div> ); MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 704. How to use `<FormattedMessage>` as placeholder using React Intl? The `<Formatted... />` components from `react-intl` return elements, not plain text, so they can't be used for placeholders, alt text, etc. In that case, you should use lower level API `formatMessage()`. You can inject the `intl` object into your component using `injectIntl()` higher-order component and then format the message using `formatMessage()` available on that object.

```jsx harmony import React from "react"; import { injectIntl, intlShape } from "react-intl"; const MyComponent = ({ intl }) => { const placeholder = intl.formatMessage({ id: "messageId" }); return <input placeholder={placeholder} />; }; MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 705. How to use Font Awesome icons in React? The below steps followed to include Font Awesome in React: 1. Install `font-awesome`:

```console $ npm install --save font-awesome

```
2. Import `font-awesome` in your `index.js` file:

```javascript import "font-awesome/css/font-awesome.min.css";

```
3. Add Font Awesome classes in `className`:

```javascript function MyComponent { return <div><i className={'fa fa-spinner'} /></div> }

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 706. How to use Polymer in React? You need to follow below steps to use Polymer in React, 1. Create a Polymer element:

```
<link rel="import" href="../../bower_components/polymer/polymer.html" />; Polymer({ is: 'calender-element', ready: function () { this.textContent = 'I am a calender'; }, });

```
1. Create the Polymer component HTML tag by importing it in a HTML document, e.g. import it in the `index.html` of your React application:

```
<link rel="import" href="./src/polymer-components/calender-element.html" />

```
1. Use that element in the JSX file:

```
import React from 'react'; class MyComponent extends React.Component { render() { return <calender-element />; } } export default MyComponent;

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 707. How would you implement internationalization (i18n) in React? `react-intl` or `react-i18next`. Extract all strings to message catalogs. `useIntl()` hook for formatting. Support RTL layouts (`dir='rtl'`, CSS logical properties). Format dates, numbers, currencies via Intl API. Lazy load language bundles. [↑ Back to Table of Contents](#table-of-contents) --- ### 708. Is it recommended to use CSS In JS technique in React? React does not have any opinion about how styles are defined but if you are a beginner then good starting point is to define your styles in a separate \*.css file as usual and refer to them using className. This functionality is not part of React but came from third-party libraries. But If you want to try a different approach(CSS-In-JS) then styled-components library is a good option. [↑ Back to Table of Contents](#table-of-contents) --- ### 709. What are the approaches to include polyfills in your `create-react-app`? There are approaches to include polyfills in create-react-app, 1. **Manual import from `core-js`:** Create a file called (something like) `polyfills.js` and import it into root `index.js` file. Run `npm install core-js` or `yarn add core-js` and import your specific required features.

```javascript import "core-js/fn/array/find"; import "core-js/fn/array/includes"; import "core-js/fn/number/is-nan";

```
2. **Using Polyfill service:** Use the polyfill.io CDN to retrieve custom, browser-specific polyfills by adding this line to `index.html`:

```html <script src="https://cdn.polyfill.io/v2/polyfill.min.js?features=default,Array.prototype.includes"></script>

```
In the above script we had to explicitly request the `Array.prototype.includes` feature as it is not included in the default feature set. [↑ Back to Table of Contents](#table-of-contents) --- ### 710. What are the main features of React Intl? Below are the main features of React Intl, 1. Display numbers with separators. 2. Display dates and times correctly. 3. Display dates relative to "now". 4. Pluralize labels in strings. 5. Support for 150+ languages. 6. Runs in the browser and Node. 7. Built on standards. [↑ Back to Table of Contents](#table-of-contents) --- ### 711. What are the popular packages for animation? _React Transition Group_ and _React Motion_ are popular animation packages in React ecosystem. [↑ Back to Table of Contents](#table-of-contents) --- ### 712. What are the two ways of formatting in React Intl? The library provides two ways to format strings, numbers, and dates: 1. **Using react components:**

```jsx harmony <FormattedMessage id={"account"} defaultMessage={"The amount is less than minimum balance."} />

```
2. **Using an API:**

```javascript const messages = defineMessages({ accountMessage: { id: "account", defaultMessage: "The amount is less than minimum balance.", }, }); formatMessage(messages.accountMessage);

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 713. What is Formik? A form library providing values, errors, touched state, and handlers. Uses controlled components. Simpler API for moderate forms. Yup integration for schema validation. Slower than React Hook Form for large forms. [↑ Back to Table of Contents](#table-of-contents) --- ### 714. What is React Hook Form and why is it popular? Register inputs with `register()`, validation via resolver (Yup, Zod). Uncontrolled under the hood – minimal re-renders (only on submit or validated field change). Better performance than Formik for large forms. [↑ Back to Table of Contents](#table-of-contents) --- ### 715. What is React Intl? The _React Intl_ library makes internationalization in React straightforward, with off-the-shelf components and an API that can handle everything from formatting strings, dates, and numbers, to pluralization. React Intl is part of _FormatJS_ which provides bindings to React via its components and API. [↑ Back to Table of Contents](#table-of-contents) --- ### 716. What is Storybook? A development environment for building, documenting, and testing UI components in isolation. Write stories for different component states. Used for design systems, component libraries, and visual regression testing. [↑ Back to Table of Contents](#table-of-contents) --- ### 717. What is the benefit of styles modules? It is recommended to avoid hard coding style values in components. Any values that are likely to be used across different UI components should be extracted into their own modules. For example, these styles could be extracted into a separate component:

```javascript export const colors = { white, black, blue, }; export const space = [0, 8, 16, 32, 64];

```
And then imported individually in other components:

```javascript import { space, colors } from "./styles";

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 718. What is the popular choice for form handling? `Formik` is a form library for react which provides solutions such as validation, keeping track of the visited fields, and handling form submission. In detail, You can categorize them as follows, 1. Getting values in and out of form state 2. Validation and error messages 3. Handling form submission It is used to create a scalable, performant, form helper with a minimal API to solve annoying stuff. [↑ Back to Table of Contents](#table-of-contents) --- ## Build Tools & Developer Experience ### 719. How does tree shaking work in modern bundlers? Tree shaking is a dead‑code elimination technique that removes unused exports from the final bundle. Bundlers like Webpack and Rollup analyze the import/export graph and only include code that is actually used. This relies on ES modules being statically analyzable. [↑ Back to Table of Contents](#table-of-contents) --- ### 720. How to avoid using relative path imports in create-react-app? Create a file called `.env` in the project root and write the import path:

```
NODE_PATH=src/app

```
After that restart the development server. Now you should be able to import anything inside `src/app` without relative paths. [↑ Back to Table of Contents](#table-of-contents) --- ### 721. How to debug forwardRefs in DevTools? **React.forwardRef** accepts a render function as parameter and DevTools uses this function to determine what to display for the ref forwarding component. For example, If you don't name the render function or not using displayName property then it will appear as ”ForwardRef” in the DevTools,

```javascript const WrappedComponent = React.forwardRef((props, ref) => { return <LogProps {...props} forwardedRef={ref} />; });

```
But If you name the render function then it will appear as **”ForwardRef(myFunction)”**

```javascript const WrappedComponent = React.forwardRef(function myFunction(props, ref) { return <LogProps {...props} forwardedRef={ref} />; });

```
As an alternative, You can also set displayName property for forwardRef function,

```javascript function logProps(Component) { class LogProps extends React.Component { // ... } function forwardRef(props, ref) { return <LogProps {...props} forwardedRef={ref} />; } // Give this component a more helpful display name in DevTools. // e.g. "ForwardRef(logProps(MyComponent))" const name = Component.displayName || Component.name; forwardRef.displayName = `logProps(${name})`; return React.forwardRef(forwardRef); }

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 722. How to enable production mode in React? You should use Webpack's `DefinePlugin` method to set `NODE_ENV` to `production`, by which it strip out things like propType validation and extra warnings. Apart from this, if you minify the code, for example, Uglify's dead-code elimination to strip out development only code and comments, it will drastically reduce the size of your bundle. [↑ Back to Table of Contents](#table-of-contents) --- ### 723. How to use class field declarations syntax in React classes? React Class Components can be made much more concise using the class field declarations. You can initialize the local state without using the constructor and declare class methods by using arrow functions without the extra need to bind them. Let's take a counter example to demonstrate class field declarations for state without using constructor and methods without binding,

```jsx class Counter extends Component { state = { value: 0 }; handleIncrement = () => { this.setState((prevState) => ({ value: prevState.value + 1, })); }; handleDecrement = () => { this.setState((prevState) => ({ value: prevState.value - 1, })); }; render() { return ( <div> {this.state.value} <button onClick={this.handleIncrement}>+</button> <button onClick={this.handleDecrement}>-</button> </div> ); } }

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 724. How to use https instead of http in create-react-app? You just need to use `HTTPS=true` configuration. You can edit your `package.json` scripts section:

```json "scripts": { "start": "set HTTPS=true && react-scripts start" }

```
or just run `set HTTPS=true && npm start` [↑ Back to Table of Contents](#table-of-contents) --- ### 725. How you use decorators in React? You can _decorate_ your _class_ components, which is the same as passing the component into a function. **Decorators** are flexible and readable way of modifying component functionality.

```jsx harmony @setTitle("Profile") class Profile extends React.Component { //.... } /* title is a string that will be set as a document title WrappedComponent is what our decorator will receive when put directly above a component class as seen in the example above */ const setTitle = (title) => (WrappedComponent) => { return class extends React.Component { componentDidMount() { document.title = title; } render() { return <WrappedComponent {...this.props} />; } }; };

```
**Note:** Decorators are a feature that didn't make it into ES7, but are currently a _stage 2 proposal_. [↑ Back to Table of Contents](#table-of-contents) --- ### 726. Should I learn ES6 before learning ReactJS? No, you don’t have to learn es2015/es6 to learn react. But you may find many resources or React ecosystem uses ES6 extensively. Let's see some of the frequently used ES6 features, 1. **Destructuring:** To get props and use them in a component

```javascript // in es 5 var someData = this.props.someData; var dispatch = this.props.dispatch; // in es6 const { someData, dispatch } = this.props;

```
2. **Spread operator:** Helps in passing props down into a component

```javascript // in es 5 <SomeComponent someData={this.props.someData} dispatch={this.props.dispatch} /> // in es6 <SomeComponent {...this.props} />

```
3. **Arrow functions:** Makes compact syntax

```javascript // es 5 var users = usersList.map(function (user) { return <li>{user.name}</li>; }); // es 6 const users = usersList.map((user) => <li>{user.name}</li>);

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 727. What are the common folder structures for React? There are two common practices for React project file structure. 1. **Grouping by features or routes:** One common way to structure projects is locate CSS, JS, and tests together, grouped by feature or route.

```
common/ ├─ Avatar.js ├─ Avatar.css ├─ APIUtils.js └─ APIUtils.test.js feed/ ├─ index.js ├─ Feed.js ├─ Feed.css ├─ FeedStory.js ├─ FeedStory.test.js └─ FeedAPI.js profile/ ├─ index.js ├─ Profile.js ├─ ProfileHeader.js ├─ ProfileHeader.css └─ ProfileAPI.js

```
2. **Grouping by file type:** Another popular way to structure projects is to group similar files together.

```
api/ ├─ APIUtils.js ├─ APIUtils.test.js ├─ ProfileAPI.js └─ UserAPI.js components/ ├─ Avatar.js ├─ Avatar.css ├─ Feed.js ├─ Feed.css ├─ FeedStory.js ├─ FeedStory.test.js ├─ Profile.js ├─ ProfileHeader.js └─ ProfileHeader.css

```
[↑ Back to Table of Contents](#table-of-contents) --- ### 728. What are the features of create react app? Below are the list of some of the features provided by create react app. 1. React, JSX, ES6, Typescript and Flow syntax support. 2. Autoprefixed CSS 3. CSS Reset/Normalize 4. A live development server 5. A fast interactive unit test runner with built-in support for coverage reporting 6. A build script to bundle JS, CSS, and images for production, with hashes and sourcemaps 7. An offline-first service worker and a web app manifest, meeting all the Progressive Web App criteria. [↑ Back to Table of Contents](#table-of-contents) --- ### 729. What are the popular React-specific linters? ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types. Another popular plugin is `eslint-plugin-jsx-a11y`, which will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with `alt` text and `tabindex`, for example, will not be picked up by regular plugins. [↑ Back to Table of Contents](#table-of-contents) --- ### 730. What is a monorepo and how does it relate to React projects? A single repo containing multiple packages (apps, libraries). Tools: Nx, Turborepo, pnpm workspaces. Useful for sharing component libraries, utility hooks, or a design system across multiple React apps. [↑ Back to Table of Contents](#table-of-contents) --- ### 731. What is CRA and its benefits? **⚠️ OUTDATED:** Create React App (CRA) is no longer actively maintained and is not recommended for new projects as of 2024+. **Modern Alternatives:** Use **Vite** (for SPAs) or **Next.js** (for full-stack/SSR) instead. See recommended setup commands at the end of this answer. **Historical Context:** The `create-react-app` CLI tool allows you to quickly create & run React applications with no configuration step. Let's create Todo App using _CRA_:

```console

### 4. How to pretty print JSON with React?

We can use `<pre>` tag so that the formatting of the `JSON.stringify()` is retained:

```jsx harmony const data = { name: "John", age: 42 }; function User { return <pre>{JSON.stringify(data, null, 2)}</pre>; } const container = createRoot(document.getElementById("container")); container.render(<User />);

```
<details><summary><b>See Class</b></summary> <p>

```jsx harmony const data = { name: "John", age: 42 }; class User extends React.Component { render() { return <pre>{JSON.stringify(data, null, 2)}</pre>; } } React.render(<User />, document.getElementById("container"));

```
</p> </details> [↑ Back to Table of Contents](#table-of-contents)

### 5. How to use Polymer in React?

[↑ Back to Table of Contents](#table-of-contents) You need to follow below steps to use Polymer in React, 1. Create a Polymer element:

```jsx harmony <link rel="import" href="../../bower_components/polymer/polymer.html" />; Polymer({ is: "calendar-element", ready: function () { this.textContent = "I am a calendar"; }, });

```
2. Create the Polymer component HTML tag by importing it in a HTML document, e.g. import it in the `index.html` of your React application:

```html <link rel="import" href="./src/polymer-components/calendar-element.html" />

```
3. Use that element in the JSX file:

```javascript export default function MyComponent { return <calendar-element />; }

```
****

### 6. How to write comments in React?

[↑ Back to Table of Contents](#table-of-contents) The comments in React/JSX are similar to JavaScript Multiline comments but are wrapped in curly braces. **Single-line comments:**

```jsx harmony <div> {/* Single-line comments(In vanilla JavaScript, the single-line comments are represented by double slash(//)) */} {`Welcome ${user}, let's play React`} </div>

```
**Multi-line comments:**

```jsx harmony <div> {/* Multi-line comments for more than one line */} {`Welcome ${user}, let's play React`} </div>

```
You can use `//` and `/* */` in JS logic, hooks, and functions. ****

### 7. What is the output of the following code? `function Parent() { console.log('Parent render'); return ( <div> <Chil...`?

```jsx function Parent() { console.log('Parent render'); return ( <div> <Child /> </div> ); } function Child() { console.log('Child render'); return <GrandChild />; } function GrandChild() { console.log('GrandChild render'); return <div>leaf</div>; }

```
**Behavior on initial mount:**

```
Parent render Child render GrandChild render

```
**Explanation:** React renders top-down. Parent renders first (to determine what children to render), then Child, then GrandChild. Commit happens after the entire tree is reconciled. React does NOT interleave render and commit phases. [⬆ Back to Table of Contents](#-table-of-contents)

### 8. What is the output of the following code? `function SearchResults({ query }) { console.log('SearchResults render ...`?

```jsx function SearchResults({ query }) { console.log('SearchResults render with:', query); // Simulate expensive computation const results = Array.from({ length: 1000 }, (_, i) => `${query}-result-${i}`); return <ul>{results.slice(0, 5).map(r => <li key={r}>{r}</li>)}</ul>; } function App() { const [input, setInput] = React.useState(''); const deferredQuery = React.useDeferredValue(input); return ( <> <input value={input} onChange={e => setInput(e.target.value)} /> <SearchResults query={deferredQuery} /> </> ); }

```
**Behavior:** Input updates immediately (urgent). `deferredQuery` lags behind — React renders the old results while computing new ones. Input never feels sluggish. **Explanation:** `useDeferredValue` gives you a deferred copy of a value. React renders with the old deferred value first (fast), then re-renders with the new value concurrently. The input feels instant. [⬆ Back to Table of Contents](#-table-of-contents)

### 9. What is the output of the following code? `import { createRoot } from "react-dom/client"; const root = createRoot...`?

When the app starts, you can trigger the initial render by calling `creatRoot` with the target DOM node followed by invoking component's `render` method. For example, the following code snippet renders `App` component on root DOM node.

```jsx import { createRoot } from "react-dom/client"; const root = createRoot(document.getElementById("root")); root.render(<App />);

```

## Components, Props & State

### 10. Design a file upload component with progress, retry, and cancel support.

Use `XMLHttpRequest` or `fetch` with a readable stream (for progress events, since plain `fetch` lacks upload progress natively), track per-file state (pending/uploading/done/error) in state, expose a cancel via `AbortController`, and support retry by re-triggering the same upload function for a failed file.

### 11. Design a Notification / Toast system with queueing, auto-dismiss, and priority.

**Requirements**: Manage multiple toasts; auto‑dismiss after timeout; queue when limit reached; support priorities (error stays longer, etc.) **Design**: - **Store**: Use a state array of notifications, each with id, message, type, priority, timeout. - **Queue**: When adding, if current visible count >= max, push to queue. On dismiss, show next from queue. - **Auto‑dismiss**: `setTimeout` per notification; clear on manual close. Higher priority = longer duration. - **Positioning**: Use portal to render fixed container. - **API**: `toast.success()`, `toast.error()`, etc., returning dismiss function.

```jsx const ToastContainer = () => { const [notifications, setNotifications] = useState([]); const addToast = (toast) => { /* manage queue */ }; const removeToast = (id) => { /* remove from array and trigger next */ }; // render list of Toasts };

```

### 12. Design a Progress Bar / Stepper with configurable steps and validation logic.

**Requirements**: Show a multi‑step process (e.g., form steps). Each step can have validation before proceeding. Visual indication of completed/active/pending steps. **Design**: - **Props**: `steps` array (each with label, component), `validateStep` function per step, `onComplete`. - **State**: `currentStep`, `stepData` (collected data). - **Behavior**: When user clicks "Next", run validation; if passes, move to next step. When "Previous", go back. On last step, call `onComplete`. - **Styling**: Use CSS classes for step indicators (completed, active, pending). Use `flex` or `grid`. **Implementation**:

```
jsx const Stepper = ({ steps, onComplete }) => { const [current, setCurrent] = useState(0); const [data, setData] = useState({}); const handleNext = async () => { const isValid = await steps[current].validate?.(data); if (isValid !== false) { if (current === steps.length - 1) onComplete(data); else setCurrent(prev => prev + 1); } }; // render step content and navigation };

```

### 13. Design a reusable, accessible `<Modal>`/`<Dialog>` component.

Headless core (focus trap, Escape, scroll lock, `role="dialog"`) separated from styling; render via portal; return focus on close; support nested modal stacking.

### 14. Design a Star Rating component – how would you support half or partial ratings?

**Requirements**: Display a star rating (1‑5). Support whole, half, or custom fractional values. **Design**: - **Props**: `value` (number), `onChange` (for interactive), `precision` (0.5 or 0.1), `size`, `readOnly`. - **Implementation**: Render 5 stars, each star can be partially filled using a technique like: - Two overlapping elements (a full star and a half star) with clip‑path or width percentage. - SVG with gradient or mask. - **Interaction**: On click, determine mouse position within the star to compute fractional value. - **Accessibility**: Use `role="slider"` with `aria-valuenow`, keyboard support (arrow keys). **Example approach**:

```jsx const Star = ({ filled, fraction, onClick }) => { // fraction: 0 (empty), 0.5 (half), 1 (full) // Use background image or SVG with linear gradient };

```

### 15. Design a Tabs component that supports dynamic content loading and async data.

**Requirements**: Tabs should be able to load content dynamically (e.g., each tab's content may be fetched from an API when selected). Support async loading states. **Design**: - **Props**: `tabs` array (each with label, content load function or component). - **State**: `activeTab` index, `loading` per tab, `content` cache per tab. - **Behavior**: When a tab becomes active, if its content hasn't been loaded, trigger async load and show loading spinner. - **Accessibility**: Use ARIA roles (`tablist`, `tab`, `tabpanel`). Handle keyboard navigation (arrow keys). - **Performance**: Cache loaded content to avoid re‑fetching. **Implementation**:

```
jsx const Tabs = ({ tabs }) => { const [active, setActive] = useState(0); const [contentCache, setContentCache] = useState({}); const [loading, setLoading] = useState(false); useEffect(() => { if (!contentCache[active] && tabs[active].load) { setLoading(true); tabs[active].load().then(data => { setContentCache(prev => ({ ...prev, [active]: data })); setLoading(false); }); } }, [active, contentCache, tabs]); const activeContent = contentCache[active] ?? (tabs[active].content || <div>No content</div>); return ( /* JSX with tab buttons and panel */ ); };

```
------------------------------------------------------------------------

### 16. Design an Accordion component -- should it allow single or multiple panels open? Why?

**Requirements**: Accordion collapses/expands sections. Decide on behavior (single open at a time vs. multiple open). **Design**: - **Props**: `allowMultiple` boolean, `children` (array of panel items), optionally `defaultOpen` indices. - **State**: Store `openIndices` (array if multiple, single index if single). - **Why choose single vs multiple?** - **Single** (default) is simpler and keeps UI tidy; useful for limited vertical space or step‑by‑step flows. - **Multiple** gives user flexibility; good for settings panels where users may want to see several sections at once. **Implementation**:

```
jsx const Accordion = ({ allowMultiple = false, children }) => { const [open, setOpen] = useState([]); // array of indices const toggle = (index) => { if (allowMultiple) { setOpen(prev => prev.includes(index) ? prev.filter(i => i !== index) : [...prev, index]); } else { setOpen(prev => prev[0] === index ? [] : [index]); } }; return ( /* render children with open state */ ); };

```
------------------------------------------------------------------------

### 17. Design an E-commerce Filter system (price, category, rating) with scalable state updates.

**Requirements**: Multiple filter facets that update product list. Efficient updates and URL sync. **Design**: - **State**: Store filter values in a global store (Redux/Zustand) or React context. Use `useReducer` for complex filter logic. - **Debouncing**: For price slider, debounce updates to avoid excessive API calls. - **URL sync**: Use `useEffect` to sync filters to URL query params; on page load, parse query to set initial filters. - **Performance**: Use memoized selectors (Reselect) to compute filtered products; cache API results per filter combination. - **Scalability**: For large product sets, move filtering to backend; send filter parameters to API.

### 18. Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.

**Requirements**: - Multiple filter facets that update the product list. - Efficient state updates without causing excessive re‑renders. - Pagination or infinite scroll. **Design**: - **State**: Use a global store (Redux or Zustand) for filters and product list. Filters: price range, category (multi‑select), rating, etc. - **Filter logic**: Combine filters into a query object; on filter change, update the query and fetch new products. Debounce price slider input. - **Caching**: Cache product pages based on filter query to avoid redundant requests. - **UI performance**: Use `React.memo` for product cards; use `useSelector` with memoized selectors (Reselect) to derive filtered products only when relevant filters change. - **Pagination**: Implement either offset‑based pagination or cursor‑based; load more on scroll or via "Load More" button. - **URL synchronization**: Keep filters in URL query parameters for shareability and persistence on refresh.

### 19. Event bubbling through a Portal:

A `stopPropagation()` call inside a portal-rendered modal still stops the click from reaching a React-tree ancestor's `onClick`, even though the portal's DOM node lives outside that ancestor — because React bubbles events along the **React tree**, not the DOM tree.

### 20. How to declare a state object?

*Example: *

```
class Car extends React.Component{ constructor(props){ super(props); this.state = { brand: "BMW", color: "black" } } }

```

### 21. How to pass numbers to React component?

We can pass `numbers` as `props` to React component using curly braces `{}` where as `strings` in double quotes `""` or single quotes `''`

```jsx import React from "react"; const ChildComponent = ({ name, age }) => { return ( <> My Name is {name} and Age is {age} </> ); }; const ParentComponent = () => { return ( <> <ChildComponent name="Chetan" age={30} /> </> ); }; export default ParentComponent;

```
[↑ Back to Table of Contents](#table-of-contents)

### 22. What is the output of the following code? `class ErrorBoundary extends React.Component { state = { hasError: fals...`?

```jsx class ErrorBoundary extends React.Component { state = { hasError: false }; static getDerivedStateFromError() { return { hasError: true }; } componentDidCatch(error, info) { console.log('caught', error.message); } render() { if (this.state.hasError) return <h1>Something went wrong</h1>; return this.props.children; } } function Buggy() { throw new Error('Oops!'); } // Which of these does the error boundary catch? // A: <Buggy /> (render error) // B: <button onClick={() => { throw new Error('click') }}>Click</button> // C: useEffect with throw // D: setTimeout with throw

```
- **A: YES** — render-time errors are caught by error boundaries. - **B: NO** — event handler errors are NOT caught by error boundaries. - **C: NO** — errors in `useEffect` are NOT caught (they happen asynchronously after render). - **D: NO** — async errors are never caught. **Explanation:** Error boundaries ONLY catch errors during rendering, in lifecycle methods, and in constructors of child components. Handle event handler errors with try/catch. Handle async errors with window.onerror or per-operation try/catch. [⬆ Back to Table of Contents](#-table-of-contents)

### 23. What is the output of the following code? `class MyComponent extends React.Component { state = { count: 0 }; comp...`?

```jsx class MyComponent extends React.Component { state = { count: 0 }; componentDidMount() { console.log('mounted, count:', this.state.count); this.setState({ count: 1 }); this.setState({ count: 2 }); } componentDidUpdate(prevProps, prevState) { console.log('updated from', prevState.count, 'to', this.state.count); } render() { console.log('render, count:', this.state.count); return <div>{this.state.count}</div>; } }

```
**Output:**

```
render, count: 0 mounted, count: 0 render, count: 2 updated from 0 to 2

```
**Explanation:** Initial render logs `0`. After mount, two `setState` calls are batched → one re-render with final value `2`. `componentDidUpdate` sees the jump from `0` to `2`. Class `setState` in lifecycle methods is batched automatically. [⬆ Back to Table of Contents](#-table-of-contents)

### 24. What is the output of the following code? `const withLogger = (WrappedComponent) => { return function LoggedCompo...`?

```jsx const withLogger = (WrappedComponent) => { return function LoggedComponent(props) { console.log(`${WrappedComponent.displayName || WrappedComponent.name} rendered with:`, props); return <WrappedComponent {...props} />; }; }; function Button({ label, onClick }) { return <button onClick={onClick}>{label}</button>; } const LoggedButton = withLogger(Button); function App() { return <LoggedButton label="Submit" onClick={() => alert('clicked')} />; }

```
**Behavior:** Every time `LoggedButton` renders, logs `Button rendered with: { label: 'Submit', onClick: [Function] }`. **HOC concern:** If `App` re-renders, `withLogger(Button)` is a new component type per render if defined inside — always define HOCs outside components. [⬆ Back to Table of Contents](#-table-of-contents)

### 25. What is the output of the following code? `function reducer(state, action) { switch(action.type) { case 'incremen...`?

```jsx function reducer(state, action) { switch(action.type) { case 'increment': return { ...state, count: state.count + 1 }; case 'decrement': return { ...state, count: state.count - 1 }; case 'reset': return { count: 0, step: state.step }; default: return state; } } function App() { const [state, dispatch] = React.useReducer(reducer, { count: 0, step: 2 }); return ( <> <p>{state.count}</p> <button onClick={() => dispatch({ type: 'increment' })}>+</button> <button onClick={() => dispatch({ type: 'decrement' })}>-</button> <button onClick={() => dispatch({ type: 'reset' })}>reset</button> </> ); }

```
**Behavior:** Works as a predictable state machine. `reset` resets count to `0` but preserves `step`. Each action is declarative and traceable. **Explanation:** `useReducer` is preferred over multiple `useState` when: state has multiple sub-values that update together, next state depends on action type, or you want predictable, testable state transitions. [⬆ Back to Table of Contents](#-table-of-contents)

### 26. What is the output of the following code? `harmony class MyComponent extends React.Component { constructor(props)...`?

[↑ Back to Table of Contents](#table-of-contents) If the props on the component are changed without the component being refreshed, the new prop value will never be displayed because the constructor function will never update the current state of the component. The initialization of state from props only runs when the component is first created. The below component won't display the updated input value:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { records: [], inputValue: this.props.inputValue, }; } render() { return <div>{this.state.inputValue}</div>; } }

```
Using props inside render method will update the value:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { record: [], }; } render() { return <div>{this.props.inputValue}</div>; } }

```

### 27. What is the output of the following code? `harmony class MyComponent extends React.Component { constructor(props)...`?

If the props on the component are changed without the component being refreshed, the new prop value will never be displayed because the constructor function will never update the current state of the component. The initialization of state from props only runs when the component is first created. The below component won't display the updated input value:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { records: [], inputValue: this.props.inputValue, }; } render() { return <div>{this.state.inputValue}</div>; } }

```
Using props inside render method will update the value:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { record: [], }; } render() { return <div>{this.props.inputValue}</div>; } }

```
[↑ Back to Table of Contents](#table-of-contents)

## Rendering, Reconciliation & Lifecycle

### 28. How to dispatch an action on load?

[↑ Back to Table of Contents](#table-of-contents) You can dispatch an action in `componentDidMount()` method and in `render()` method you can verify the data.

```javascript class App extends Component { componentDidMount() { this.props.fetchData(); } render() { return this.props.isLoaded ? ( <div>{"Loaded"}</div> ) : ( <div>{"Not Loaded"}</div> ); } } const mapStateToProps = (state) => ({ isLoaded: state.isLoaded, }); const mapDispatchToProps = { fetchData }; export default connect(mapStateToProps, mapDispatchToProps)(App);

```

### 29. How to make AJAX call and in which component lifecycle methods should I make an AJAX call?

You can use AJAX libraries such as Axios, jQuery AJAX, and the browser built-in `fetch`. You should fetch data in the `componentDidMount()` lifecycle method. This is so you can use `setState()` to update your component when the data is retrieved. For example, the employees list fetched from API and set local state:

```jsx harmony class MyComponent extends React.Component { constructor(props) { super(props); this.state = { employees: ** ------------------------------------------------------------------------ --- ### 114. 21. Explain conditional rendering in React. Conditional rendering refers to the dynamic output of user interface markups based on a condition state. It works in the same way as JavaScript conditions. Using conditional rendering, it is possible to toggle specific application functions, API data rendering, hide or show elements, decide permission levels, authentication handling, and so on. There are different approaches for implementing conditional rendering in React. Some of them are: - Using if-else conditional logic which is suitable for smaller as well as for medium-sized applications - Using ternary operators, which takes away some amount of complication from if-else statements - Using element variables, which will enable us to write cleaner code. --- --- ### How to prevent component from rendering? You can prevent component from rendering by returning null based on specific condition. This way it can conditionally render component.

```javascript function Greeting(props) { if (!props.loggedIn) { return null; } return <div className="greeting">welcome, {props.name}</div>; }

```
```javascript class User extends React.Component { constructor(props) { super(props); this.state = {loggedIn: false, name: 'John'}; } render() { return ( <div> //Prevent component render if it is not loggedIn <Greeting loggedIn={this.state.loggedIn} /> <UserDetails name={this.state.name}> </div> ); }

```
In the above example, the `greeting` component skips its rendering section by applying condition and returning null value. ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### Is it good to use arrow functions in render methods? Yes, You can use. It is often the easiest way to pass parameters to callback functions. But you need to optimize the performance while using it.

```
class Foo extends Component { handleClick() { console.log('Click happened'); } render() { return <button onClick={() => this.handleClick()}>Click Me</button>; } }

```
**Note:** Using an arrow function in render method creates a new function each time the component renders, which may have performance implications [ --- ### What are error boundaries? Introduced in version 16 of React, Error boundaries provide a way for us to catch errors that occur in the render phase. - **What is an error boundary?** Any component which uses one of the following lifecycle methods is considered an error boundary. In what places can an error boundary detect an error? 1. Render phase 2. Inside a lifecycle method 3. Inside the constructor **Without using error boundaries:** class CounterComponent extends React.Component{ constructor(props){ super(props); this.state = { counterValue: 0 } this.incrementCounter = this.incrementCounter.bind(this); } incrementCounter(){ this.setState(prevState =\> counterValue = prevState+1); } render(){ if(this.state.counter === 2){ throw new Error('Crashed'); } return(

```{=html} <div>

```
<button onClick={this.incrementCounter}>Increment Value</button> <p>Value of counter: {this.state.counterValue}</p> </div> ) } } In the code above, when the counterValue equals 2, we throw an error inside the render method. When we are not using the error boundary, instead of seeing an error, we see a blank page. Since any error inside the render method leads to unmounting of the component. To display an error that occurs inside the render method, we use error boundaries. **With error boundaries: **As mentioned above, error boundary is a component using one or both of the following methods: **static getDerivedStateFromError and componentDidCatch.** Let’s create an error boundary to handle errors in the render phase: class ErrorBoundary extends React.Component { constructor(props) { super(props); this.state = { hasError: false }; } static getDerivedStateFromError(error) {\ return { hasError: true }; } componentDidCatch(error, errorInfo) {\ logErrorToMyService(error, errorInfo); } render() { if (this.state.hasError) {\ return

```{=html} <h4>

```
Something went wrong

```{=html} </h4>

```
} return this.props.children; } } In the code above, **getDerivedStateFromError** function renders the fallback UI interface when the render method has an error. **componentDidCatch** logs the error information to an error tracking service. Now with the error boundary, we can render the CounterComponent in the following way: `<ErrorBoundary>`{=html} `<CounterComponent/>`{=html} `</ErrorBoundary>`{=html} --- ### What are error boundaries in React v16? **Note:** Error boundaries were introduced in React 16 and remain valid in current React versions (18/19). _Error boundaries_ are components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed. A class component becomes an error boundary if it defines these lifecycle methods: - `static getDerivedStateFromError(error)` - for rendering fallback UI - `componentDidCatch(error, info)` - for logging error information

```jsx harmony class ErrorBoundary extends React.Component { constructor(props) { super(props); this.state = { hasError: false }; } static getDerivedStateFromError(error) { // Update state so the next render will show the fallback UI return { hasError: true }; } componentDidCatch(error, info) { // Log error to an error reporting service console.error('Error caught by boundary:', error, info); logErrorToMyService(error, info); } render() { if (this.state.hasError) { // Render custom fallback UI return <h1>Something went wrong.</h1>; } return this.props.children; } }

```
Usage:

```jsx harmony <ErrorBoundary> <MyWidget /> </ErrorBoundary>

```
**Note:** Error boundaries currently only work with class components. There is no hook equivalent yet, though `use()` hook in React 19 provides some error handling capabilities. **** ------------------------------------------------------------------------ --- --- ### What are the different phases of component lifecycle? The component lifecycle has three distinct lifecycle phases: 1. **Mounting:** The component is ready to mount in the browser DOM. This phase covers initialization from `constructor()`, `getDerivedStateFromProps()`, `render()`, and `componentDidMount()` lifecycle methods. 2. **Updating:** In this phase, the component gets updated in two ways, sending the new props and updating the state either from `setState()` or `forceUpdate()`. This phase covers `getDerivedStateFromProps()`, `shouldComponentUpdate()`, `render()`, `getSnapshotBeforeUpdate()` and `componentDidUpdate()` lifecycle methods. 3. **Unmounting:** In this last phase, the component is not needed and gets unmounted from the browser DOM. This phase includes `componentWillUnmount()` lifecycle method. It's worth mentioning that React internally has a concept of phases when applying changes to the DOM. They are separated as follows 4. **Render** The component will render without any side effects. This applies to Pure components and in this phase, React can pause, abort, or restart the render. 5. **Pre-commit** Before the component actually applies the changes to the DOM, there is a moment that allows React to read from the DOM through the `getSnapshotBeforeUpdate()`. 6. **Commit** React works with the DOM and executes the final lifecycles respectively `componentDidMount()` for mounting, `componentDidUpdate()` for updating, and `componentWillUnmount()` for unmounting. React 16.3+ Phases (or an ** --- ### What are the lifecycle methods going to be deprecated in React v16? **⚠️ FULLY DEPRECATED:** These lifecycle methods have been deprecated and removed from React 17+. The following lifecycle methods were deprecated due to unsafe coding practices and problems with async rendering: 1. `componentWillMount()` - **REMOVED in React 17** 2. `componentWillReceiveProps()` - **REMOVED in React 17** 3. `componentWillUpdate()` - **REMOVED in React 17** **Timeline:** - React 16.3: Methods aliased with `UNSAFE_` prefix - React 17+: Unprefixed versions completely removed - Current (React 18/19): Only `UNSAFE_` versions exist (not recommended) **Modern Alternatives:** | Deprecated Method | Modern Replacement | |---|---| | `componentWillMount()` | `constructor()` or `componentDidMount()` | | `componentWillReceiveProps()` | `static getDerivedStateFromProps()` or `componentDidUpdate()` | | `componentWillUpdate()` | `getSnapshotBeforeUpdate()` + `componentDidUpdate()` | **Best Practice:** Use functional components with hooks instead: - `useEffect()` for side effects - `useState()` for state management - `useMemo()`/`useCallback()` for optimization **** ------------------------------------------------------------------------ --- --- ### What are the lifecycle methods of React? React lifecycle hooks will have the methods that will be automatically called at different phases in the component lifecycle and thus it provides good control over what happens at the invoked point. It provides the power to effectively control and manipulate what goes on throughout the component lifecycle. For example, if you are developing the YouTube application, then the application will make use of a network for buffering the videos and it consumes the power of the battery (assume only these two). After playing the video if the user switches to any other application, then you should make sure that the resources like network and battery are being used most efficiently. You can stop or pause the video buffering which in turn stops the battery and network usage when the user switches to another application after video play. So we can say that the developer will be able to produce a quality application with the help of lifecycle methods and it also helps developers to make sure to plan what and how to do it at different points of birth, growth, or death of user interfaces. The various lifecycle methods are: - `constructor()`: This method will be called when the component is initiated before anything has been done. It helps to set up the initial state and initial values. - `getDerivedStateFromProps()`: This method will be called just before element(s) rendering in the DOM. It helps to set up the state object depending on the initial props. The getDerivedStateFromProps() method will have a state as an argument and it returns an object that made changes to the state. This will be the first method to be called on an updating of a component. - `render()`: This method will output or re-render the HTML to the DOM with new changes. The render() method is an essential method and will be called always while the remaining methods are optional and will be called only if they are defined. - `componentDidMount()`: This method will be called after the rendering of the component. Using this method, you can run statements that need the component to be already kept in the DOM. - `shouldComponentUpdate()`: The Boolean value will be returned by this method which will specify whether React should proceed further with the rendering or not. The default value for this method will be True. - `getSnapshotBeforeUpdate()`: This method will provide access for the props as well as for the state before the update. It is possible to check the previously present value before the update, even after the update. - `componentDidUpdate()`: This method will be called after the component has been updated in the DOM. - `componentWillUnmount()`: This method will be called when the component removal from the DOM is about to happen. --- ### What are the possible return types of render method? Below are the list of following types used and return from render method, 1. **React elements:** Elements that instruct React to render a DOM node. It includes html elements such as `<div/>` and user defined elements. 2. **Arrays and fragments:** Return multiple elements to render as Arrays and Fragments to wrap multiple elements 3. **Portals:** Render children into a different DOM subtree. 4. **String and numbers:** Render both Strings and Numbers as text nodes in the DOM 5. **Booleans or null:** Doesn't render anything but these types are used to conditionally render content. [ --- ### What are the rules covered by diffing algorithm? When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements. It covers the below rules during reconciliation algorithm, 1. **Elements Of Different Types:** Whenever the root elements have different types, React will tear down the old tree and build the new tree from scratch. For example, elements to, or from to of different types lead a full rebuild. 2. **DOM Elements Of The Same Type:** When comparing two React DOM elements of the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes. Lets take an example with same DOM elements except className attribute,

```
<div className="show" title="ReactJS" /> <div className="hide" title="ReactJS" />

```
1. **Component Elements Of The Same Type:** When a component updates, the instance stays the same, so that state is maintained across renders. React updates the props of the underlying component instance to match the new element, and calls componentWillReceiveProps() and componentWillUpdate() on the underlying instance. After that, the render() method is called and the diff algorithm recurses on the previous result and the new result. 2. **Recursing On Children:** when recursing on the children of a DOM node, React just iterates over both lists of children at the same time and generates a mutation whenever there’s a difference. For example, when adding an element at the end of the children, converting between these two trees works well.

```
<ul> <li>first</li> <li>second</li> </ul> <ul> <li>first</li> <li>second</li> <li>third</li> </ul>

```
1. **Handling keys:** React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree. For example, adding a key can make the tree conversion efficient,

```
<ul> <li key="2015">Duke</li> <li key="2016">Villanova</li> </ul> <ul> <li key="2014">Connecticut</li> <li key="2015">Duke</li> <li key="2016">Villanova</li> </ul>

```
[ --- ### What is an error boundary? A class component that implements `getDerivedStateFromError()` and/or `componentDidCatch()`. It catches rendering errors in its subtree and renders a fallback UI instead of crashing the whole app. ------------------------------------------------------------------------ --- --- ### What is diffing algorithm? React needs to use algorithms to find out how to efficiently update the UI to match the most recent tree. The diffing algorithms is generating the minimum number of operations to transform one tree into another. However, the algorithms have a complexity in the order of O(n3) where n is the number of elements in the tree. In this case, for displaying 1000 elements would require in the order of one billion comparisons. This is far too expensive. Instead, React implements a heuristic O(n) algorithm based on two assumptions: 1. Two elements of different types will produce different trees. 2. The developer can hint at which child elements may be stable across different renders with a key prop. [ --- ### What is React Fiber? The Problem (Old React) Before Fiber, when React started updating the screen, it had to finish the entire job in one single blast without stopping. If it was a massive update (like rendering a huge list), the browser would freeze. If a user tried to click a button or type during that freeze, the app felt broken and laggy. The Solution (React Fiber) Fiber changes the way React works by breaking the massive update job into tiny, bite-sized tasks. Because the work is split up, React gains three superpowers: Pause & Resume: It can do a little bit of work, pause to let the browser breathe, and then pick up right where it left off. Prioritize: If a user clicks a button while React is busy rendering a hidden menu, React will pause the menu, handle the button click immediately (high priority), and then go back to the menu. Abort: If you switch pages mid-load, React can instantly throw away the half-finished work of the old page instead of wasting time finishing it. ------------------------------------------------------------------------ --- --- ### What is reconciliation? The process of diffing the new React element tree against the previous one to compute minimal DOM mutations. React uses two heuristics: same type → update props; different type → unmount old, mount new. Keys help reconcile lists. ------------------------------------------------------------------------ --- --- ### What is reconciliation? How does React's diffing algorithm work? So this concept is not very difficult once you read its rules and uses! What you should do here is get familiar with the concept right now, have a read, and then, in the end, I'll mention a short answer-like paragraph that you can use during your interview. So to understand Reconciliation: Reconciliation is the internal algo process React uses to compare the previous Virtual DOM tree with the newly generated Virtual DOM tree after a state or prop changes. Here's what happens to make it work: 1. React re-renders the component to produce a new Virtual DOM tree 2. It compares this tree with the previous Virtual DOM tree 3. It computes a set of changes called mutations 4. It applies only those changes to the real DOM And so, this process is used to avoid unnecessary DOM operations, which end up being expensive. Coming to React's Diffing Algorithm - React's Diffing Algorithm is a part of the reconciliation process, where its primary goal is to minimize DOM updates. Now it is important to understand how this takes place, so please look into this carefully: - The expensive but optimal component is (O(n3 ) ) - React uses a tree-diffing algorithm to minimize DOM - Hence, it uses a heuristic O(n) algorithm instead of specific assumptions What it essentially does is compare root elements, then if they differ, the entire subtree is replaced, and if they match, then its attributes and the recursion on children are compared. There are some rules of diffing that you really need to keep in mind: **1. Different trees are produced because of different elements** If the root elements have different types, React: - unmounts the old component tree, - destroys associated DOM nodes, - mounts a new tree. Example: <div /> → <section /> This triggers a full rebuild of that subtree. **2. Elements of the same type are compared attribute-wise** If element types are the same, React updates only the changed attributes, and then recursively compares child elements **3. Keys are used to match children in lists** When reconciling lists, React uses the key prop to identify which items have stayed the same, moved, or have been added or removed For eg: items.map(item => <li key={item.id}>{item.name}</li>) There is a reason why these keys are critical: - They provide a stable identity across renders - Prevent incorrect reuse of DOM nodes - Preserve component state Without stable keys, React falls back to index-based matching What you must also note is that Reordering can lead to state being assigned to the wrong component, unnecessary re-renders, and even UI inconsistencies. You must be wondering why the complexity is O(n) instead of O(n³) - A full tree comparison would require checking every node against every other node, which then results in O(n³) complexity. React reduces this to O(n) using two assumptions: - Different element types produce different subtrees - Because of this, there is no need to deeply compare and replace directly - Keys uniquely identify elements in lists - Enables efficient matching of children without exhaustive comparison These heuristics make React perform reconciliation in linear time relative to the number of elements. Now this was all you needed to know about reconciliation, Here's a short answer that you can prepare if the interviewer isn't expecting anything detailed: - Reconciliation is the process by which React compares the previous and new Virtual DOM trees to compute the minimal DOM updates. It uses a heuristic O(n) diffing algorithm based on two assumptions: elements of different types produce different trees, and keys provide a stable identity for list elements. Now you are good to go! ------------------------------------------------------------------------ --- --- ### What is reconciliation in React? How does the diffing algorithm work? Reconciliation is React's algorithm for determining which parts of the DOM need to be updated when state or props change. It uses a **virtual DOM** (a lightweight representation) and compares it with the previous version. **Diffing algorithm (simplified)**: - **Elements of different types**: The whole subtree is torn down and rebuilt. - **Elements of the same type**: React keeps the same DOM node and only updates changed attributes (e.g., `className`). Then it recursively diffs children. - **List children with keys**: Keys help identify which items have changed, been added, or removed. Without stable keys, the algorithm may re‑render more than necessary. ------------------------------------------------------------------------ --- --- ### What is re‑rendering, and why does it happen? Re‑rendering is the process where React updates the UI to reflect the current state and props. It happens when: - A component’s state changes. - Its props change. - Its parent re‑renders (by default). - A context value it uses changes. - A custom hook triggers an update. React batches updates for performance; re‑rendering does not necessarily mean the DOM is updated – React computes the difference (reconciliation) and only updates the DOM where needed. --- ### What is Strict Mode? Think of React Strict Mode like a stress tester or a spellcheck for your code. It is a special wrapper tool (\<React.StrictMode\>) you place around your app. It doesn't show anything on the screen itself, but it activates extra checks behind the scenes. The Secret Weapon: The "Double Run" In development, Strict Mode will deliberately run your components, state updates, and useEffect hooks twice every time they load. Why does it do this? Good React code should be predictable. Running a component twice should produce the exact same result. If running your code a second time suddenly breaks a feature, causes a visual glitch, or leaves a background timer running, Strict Mode has successfully exposed a hidden bug (called a "side effect") before it reaches your users. Warning System: It also watches your code and prints warning messages in the browser console if you are using old, outdated React features that will break in future updates. ⚠️ The Golden Rule Strict Mode only works in development. When you publish your app to the live internet (production), React automatically turns off all the double-running and warnings so your live website runs at 100% full speed. ------------------------------------------------------------------------ --- --- ### What is strict mode in React? `React.StrictMode` is a useful component for highlighting potential problems in an application. Just like `<Fragment>`, `<StrictMode>` does not render any extra DOM elements. It activates additional checks and warnings for its descendants. These checks apply for *development mode* only.

```jsx harmony import { StrictMode } from "react"; function App() { return ( <div> <Header /> <StrictMode> <div> <ComponentOne /> <ComponentTwo /> </div> </StrictMode> <Header /> </div> ); }

```
In the example above, the _strict mode_ checks apply to `<ComponentOne>` and `<ComponentTwo>` components only. i.e., Part of the application only. **Note:** Frameworks such as NextJS has this flag enabled by default. **** ------------------------------------------------------------------------ --- --- ### What is the benefit of component stack trace from error boundary? Apart from error messages and javascript stack, React16 will display the component stack trace with file names and line numbers using error boundary concept. For example, BuggyCounter component displays the component stack trace as below, !** ------------------------------------------------------------------------ --- ## React Rendering, Reconciliation & Lifecycle --- ### What is the benefit of strict mode? The `<StrictMode>`{=html} will be helpful in the below cases, 1. To find the bugs caused by impure rendering where the components will re-render twice. 2. To find the bugs caused by missing cleanup of effects where the components will re-run effects one more extra time. 3. Identifying components with **unsafe lifecycle methods**. 4. Warning about **legacy string ref** API usage. 5. Detecting unexpected **side effects**. 6. Detecting **legacy context** API. 7. Warning about deprecated **findDOMNode** usage ------------------------------------------------------------------------ ------------------------------------------------------------------------ --- --- ### What is the difference between shallow and deep rendering? Shallow rendering (Enzyme): renders one level deep, doesn't mount children. Deep/full rendering (RTL): renders the full tree to DOM. RTL's approach is preferred – it tests what the user actually sees. [⬆ Back to Table of Contents](#-table-of-contents) --- --- ### What is the difference between try catch block and error boundaries? Try catch block works with imperative code whereas error boundaries are meant for declarative code to render on the screen. For example, the try catch block used for below imperative code

```
try { showButton(); } catch (error) { // ... }

```
Whereas error boundaries wrap declarative code as below,

```
<ErrorBoundary> <MyComponent /> </ErrorBoundary>

```
So if an error occurs in a **componentDidUpdate** method caused by a **setState** somewhere deep in the tree, it will still correctly propagate to the closest error boundary. [ --- ### What is the main goal of React Fiber? The goal of _React Fiber_ is to increase its suitability for areas like animation, layout, and gestures. Its headline feature is **incremental rendering**: the ability to split rendering work into chunks and spread it out over multiple frames. Its main goals are: * **Incremental Rendering** – Breaks work into chunks for smoother updates. * **Interruptible Rendering** – Pauses and resumes rendering to keep the UI responsive. * **Prioritization** – Handles high-priority updates (e.g. animations) before low-priority ones. * **Concurrency Support** – Enables working on multiple UI versions simultaneously. * **Better Error Handling** – Supports component-level error boundaries. * **Suspense Support** – Allows waiting for async data before rendering. * **Improved DevTools** – Enables better debugging and performance tracking. **** --- ### What is the purpose of render method of `react-dom`? This method is used to render a React element into the DOM in the supplied container and return a reference to the component. If the React element was previously rendered into container, it will perform an update on it and only mutate the DOM as necessary to reflect the latest changes.

```
ReactDOM.render(element, container, ** ------------------------------------------------------------------------

## Hooks (Core & Advanced)

### 30. `React.memo` + stable `useMemo` array — correctly skips re-render:

```jsx const items = useMemo(() => [1, 2, 3], []); // same reference every render <MemoChild items={items} /> // Child renders ONCE regardless of parent re-renders — correct pairing.

```

### 31. `useDeferredValue` keeping an input responsive:

The input updates immediately on every keystroke (urgent); the deferred value (and anything computed from it, like search results) lags behind and updates once React has spare capacity — so typing never feels sluggish even with expensive downstream rendering.

### 32. `useEffect` vs `useLayoutEffect` paint timing:

`useLayoutEffect` runs and can update the DOM *before* the browser paints (no flicker, but blocks rendering); `useEffect` runs *after* paint (non-blocking, possible one-frame flicker if it mutates the DOM).

### 33. `useMemo` recomputing despite unrelated state changes:

```jsx const result = useMemo(() => count * multiplier, [count, multiplier]); // Only recomputes when count OR multiplier change — clicking an unrelated button does NOT trigger recomputation.

```

### 34. `useMemo` still recomputing due to a fresh dependency array reference:

```jsx function App() { const data = [1, 2, 3]; // new array every render! return <Expensive data={data} />; // useMemo inside Expensive keyed on `data` recomputes every render // Fix: const data = useMemo(() => [1,2,3], []) in App. }

```

### 35. `useRef` never triggers a re-render:

Incrementing `ref.current` doesn't cause the component to re-render — the updated value only becomes visible on screen the next time something *else* triggers a render.

### 36. Build a counter that increments and decrements?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Counter({ step = 1 }) { const [count, setCount] = useState(0); return ( <div> <button onClick={() => setCount(c => c - step)}>-</button> <span>{count}</span> <button onClick={() => setCount(c => c + step)}>+</button> <button onClick={() => setCount(0)}>Reset</button> </div> ); }

```
Uses the functional updater form (`c => c + step`) so rapid clicks don't read a stale `count` from a batched render.

### 37. Build a custom hook like `useDebounce` or `useFetch`.

[↑ Back to Table of Contents](#table-of-contents) **`useDebounce`** (example):

```
javascript import { useState, useEffect } from 'react'; function useDebounce(value, delay) { const [debouncedValue, setDebouncedValue] = useState(value); useEffect(() => { const handler = setTimeout(() => setDebouncedValue(value), delay); return () => clearTimeout(handler); }, [value, delay]); return debouncedValue; }

```
**`useFetch`** (example):

```
javascript function useFetch(url, options = {}) { const [data, setData] = useState(null); const [loading, setLoading] = useState(true); const [error, setError] = useState(null); useEffect(() => { const abortController = new AbortController(); const fetchData = async () => { try { const res = await fetch(url, { ...options, signal: abortController.signal }); if (!res.ok) throw new Error('Network error'); const json = await res.json(); setData(json); setLoading(false); } catch (err) { if (err.name !== 'AbortError') { setError(err); setLoading(false); } } }; fetchData(); return () => abortController.abort(); }, [url, ...Object.values(options)]); // caution: options can cause infinite loops return { data, loading, error }; }

```
------------------------------------------------------------------------

### 38. Build a file upload component with drag-and-drop, progress, and preview?

```jsx function FileUpload({ onUpload }) { const [file, setFile] = useState(null); const [preview, setPreview] = useState(null); const [progress, setProgress] = useState(0); const [dragging, setDragging] = useState(false); function handleFile(f) { setFile(f); setPreview(URL.createObjectURL(f)); uploadWithProgress(f); } function uploadWithProgress(f) { const xhr = new XMLHttpRequest(); xhr.upload.onprogress = (e) => { if (e.lengthComputable) setProgress(Math.round((e.loaded / e.total) * 100)); }; xhr.onload = () => onUpload?.(xhr.response); xhr.open('POST', '/api/upload'); const formData = new FormData(); formData.append('file', f); xhr.send(formData); } return ( <div onDragOver={e => { e.preventDefault(); setDragging(true); }} onDragLeave={() => setDragging(false)} onDrop={e => { e.preventDefault(); setDragging(false); handleFile(e.dataTransfer.files[0]); }} style={{ border: dragging ? '2px dashed blue' : '2px dashed gray' }} > <input type="file" onChange={e => handleFile(e.target.files[0])} /> {preview && <img src={preview} width={100} />} {file && <progress value={progress} max={100} />} </div> ); }

```
`XMLHttpRequest` (not `fetch`) is used because it's currently the standard way to get granular upload-progress events in the browser; `URL.createObjectURL` gives an instant local preview before the upload completes. Remember to `URL.revokeObjectURL(preview)` when the component unmounts or the file changes, to avoid a memory leak. [↑ Back to Table of Contents](#table-of-contents)

### 39. Build a Star Rating component?

```jsx function StarRating({ value, onChange, max = 5 }) { const [hovered, setHovered] = useState(0); return ( <div onMouseLeave={() => setHovered(0)}> {Array.from({ length: max }, (_, i) => i + 1).map(star => ( <span key={star} onClick={() => onChange(star)} onMouseEnter={() => setHovered(star)} style={{ color: star <= (hovered || value) ? 'gold' : 'gray', cursor: 'pointer' }} > ★ </span> ))} </div> ); }

```
`hovered` (local, transient UI state) previews the rating on hover without touching the committed `value`, which is only updated on click — a controlled component pattern where the parent owns the actual rating. [↑ Back to Table of Contents](#table-of-contents)

### 40. Build a typeahead / autocomplete component with keyboard navigation?

```jsx function Autocomplete({ fetchSuggestions }) { const [query, setQuery] = useState(''); const [suggestions, setSuggestions] = useState([]); const [activeIndex, setActiveIndex] = useState(-1); const debouncedQuery = useDebounce(query, 300); useEffect(() => { if (!debouncedQuery) { setSuggestions([]); return; } fetchSuggestions(debouncedQuery).then(setSuggestions); }, [debouncedQuery, fetchSuggestions]); function handleKeyDown(e) { if (e.key === 'ArrowDown') setActiveIndex(i => Math.min(i + 1, suggestions.length - 1)); if (e.key === 'ArrowUp') setActiveIndex(i => Math.max(i - 1, 0)); if (e.key === 'Enter' && activeIndex >= 0) select(suggestions[activeIndex]); if (e.key === 'Escape') setSuggestions([]); } function select(item) { setQuery(item.label); setSuggestions([]); setActiveIndex(-1); } return ( <div> <input value={query} onChange={e => setQuery(e.target.value)} onKeyDown={handleKeyDown} role="combobox" aria-expanded={suggestions.length > 0} /> <ul role="listbox"> {suggestions.map((s, i) => ( <li key={s.id} role="option" aria-selected={i === activeIndex} style={{ background: i === activeIndex ? '#eee' : 'transparent' }} onMouseDown={() => select(s)}> {s.label} </li> ))} </ul> </div> ); }

```
`onMouseDown` (not `onClick`) is used for selecting a suggestion because `onClick` fires after `onBlur`, which would have already closed the suggestion list; debouncing avoids firing a network request on every keystroke. [↑ Back to Table of Contents](#table-of-contents)

### 41. Calling a hook conditionally:

```jsx if (flag) { const [extra, setExtra] = useState(0); // Rules of Hooks violation! } // React throws: "Rendered more hooks than during the previous render."

```

### 42. Design a component that renders differently based on viewport size (responsive layout) without layout thrashing.

Prefer CSS media queries/container queries for purely visual changes (no JS needed, no re-render). Only use a `useMediaQuery`/`ResizeObserver`-based Hook when the *structure* of what renders must actually change (not just styling), and debounce/throttle resize-driven state updates.

### 43. Design a form wizard with multiple steps in React.

Store step index in state. Store all step data in a reducer or React Hook Form with a persistent form context. Each step validates before proceeding. Preserve data when navigating back. Consider URL-based step state for shareable links.

### 44. Design a Search with Autocomplete, debouncing, caching, and race condition handling.

```javascript function useAutocomplete(query) { const [results, setResults] = useState([]); const cache = useRef(new Map()); useEffect(() => { if (!query || query.length < 2) return; if (cache.current.has(query)) { setResults(cache.current.get(query)); return; } const controller = new AbortController(); fetch(`/api/search?q=${query}`, { signal: controller.signal }) .then(r => r.json()) .then(data => { cache.current.set(query, data); setResults(data); }) .catch(e => { if (e.name !== 'AbortError') console.error(e); }); return () => controller.abort(); // cancel on new query }, [query]); return results; } // Debounce query in parent before passing to hook

```
Three-layer defense: debounce (reduces requests), cache (avoids redundant requests), AbortController (handles race conditions). Minimum 2-char threshold prevents wasteful very-short queries.

### 45. Design a Stopwatch with Start, Stop, Reset and live timer display.

```javascript function Stopwatch() { const [time, setTime] = useState(0); const [running, setRunning] = useState(false); const intervalRef = useRef(null); const start = () => { if (running) return; setRunning(true); intervalRef.current = setInterval(() => setTime(t => t + 10), 10); }; const stop = () => { setRunning(false); clearInterval(intervalRef.current); }; const reset = () => { stop(); setTime(0); }; useEffect(() => () => clearInterval(intervalRef.current), []); const format = ms => { const s = Math.floor(ms / 1000) % 60; const m = Math.floor(ms / 60000); const cs = Math.floor((ms % 1000) / 10); return `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}.${String(cs).padStart(2,'0')}`; }; }

```
Key points: useRef for interval ID (not state — changing it shouldn't cause re-render). Cleanup in useEffect return. Use functional update setTime(t => t + 10) to avoid stale closure issues.

### 46. Design a Todo List application with add, edit, delete, and mark‑as‑complete.

**Requirements**: Manage a list of todos; each todo has an id, text, and completed flag. Support adding, editing, deleting, and toggling completion. **Design considerations**: - **State**: Use `useState` (or `useReducer` for complex updates) to store todos array. - **Edit mode**: Track which todo is being edited (or use a separate edit field). - **Accessibility**: Keyboard navigation, focus management. - **Persistence**: Optionally store in `localStorage`. - **Performance**: Use `useCallback` for handlers, `React.memo` for each todo item to avoid unnecessary re‑renders. **Implementation skeleton**:

```
jsx const TodoApp = () => { const [todos, setTodos] = useState([]); const [newTodo, setNewTodo] = useState(''); const [editId, setEditId] = useState(null); const [editText, setEditText] = useState(''); const addTodo = () => { /* add new todo */ }; const toggleTodo = (id) => { /* toggle completed */ }; const deleteTodo = (id) => { /* delete todo */ }; const startEdit = (todo) => { /* set editId, editText */ }; const saveEdit = () => { /* update todo text */ }; return ( /* JSX with input, list of TodoItem components */ ); };

```

### 47. Design a Toggle / Switch component -- controlled vs uncontrolled patterns.

**Requirements**: A switch that can be controlled (value passed from parent) or uncontrolled (internal state). Support `onChange` callback. **Design**: - **Uncontrolled**: Internal `useState`, initial value from `defaultChecked`. - **Controlled**: Parent manages value via `checked` prop; component becomes read‑only to parent updates. - **Both patterns**: Check if `checked` prop is defined; if yes, use controlled; otherwise use internal state. - **Accessibility**: `role="switch"`, `aria-checked`, keyboard support (Space/Enter). - **Styling**: Use CSS pseudo‑elements for slider effect.

```
jsx const Toggle = ({ checked: controlledChecked, defaultChecked = false, onChange }) => { const [internalChecked, setInternalChecked] = useState(defaultChecked); const isControlled = controlledChecked !== undefined; const current = isControlled ? controlledChecked : internalChecked; const handleToggle = () => { const newValue = !current; if (!isControlled) setInternalChecked(newValue); onChange?.(newValue); }; return <button role="switch" aria-checked={current} onClick={handleToggle} />; };

```

### 48. How to focus an input element on page load?

You need to use `useEffect` hook to set focus on input field during page load time for functional component.

```jsx harmony import React, { useEffect, useRef } from "react"; const App = () => { const inputElRef = useRef(null); useEffect(() => { inputElRef.current.focus(); }, []); return ( <div> <input defaultValue={"Won't focus"} /> <input ref={inputElRef} defaultValue={"Will focus"} /> </div> ); }; ReactDOM.render(<App />, document.getElementById("app"));

```
<details><summary><b>See Class</b></summary> <p> You can do it by creating _ref_ for `input` element and using it in `componentDidMount()`:

```jsx harmony class App extends React.Component { componentDidMount() { this.nameInput.focus(); } render() { return ( <div> <input defaultValue={"Won't focus"} /> <input ref={(input) => (this.nameInput = input)} defaultValue={"Will focus"} /> </div> ); } } ReactDOM.render(<App />, document.getElementById("app"));

```
</p> </details> [↑ Back to Table of Contents](#table-of-contents)

### 49. Implement a carousel/image slider?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Carousel({ images, interval = 3000 }) { const [index, setIndex] = useState(0); useEffect(() => { const timer = setInterval(() => { setIndex(i => (i + 1) % images.length); }, interval); return () => clearInterval(timer); }, [images.length, interval]); return ( <div className="carousel"> <button onClick={() => setIndex(i => (i - 1 + images.length) % images.length)}>‹</button> <img src={images[index]} /> <button onClick={() => setIndex(i => (i + 1) % images.length)}>›</button> <div> {images.map((_, i) => ( <span key={i} onClick={() => setIndex(i)} style={{ fontWeight: i === index ? 'bold' : 'normal' }}>●</span> ))} </div> </div> ); }

```
Modulo arithmetic (`(i + 1) % length`) makes the index wrap around seamlessly at both ends; the `useEffect` auto-advance timer is cleared and restarted whenever `images` or `interval` changes, and on unmount.

### 50. Implement a custom `useAsync` hook (manage async function states)

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useCallback, useEffect } from 'react'; function useAsync(asyncFn, immediate = true) { const [status, setStatus] = useState('idle'); // idle | pending | success | error const [value, setValue] = useState(null); const [error, setError] = useState(null); const execute = useCallback((...args) => { setStatus('pending'); setValue(null); setError(null); return asyncFn(...args) .then(response => { setValue(response); setStatus('success'); }) .catch(err => { setError(err); setStatus('error'); }); }, [asyncFn]); useEffect(() => { if (immediate) execute(); }, [execute, immediate]); return { execute, status, value, error }; }

```

### 51. Implement a custom `useClickOutside` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useEffect, useRef } from 'react'; function useClickOutside(callback) { const ref = useRef(null); useEffect(() => { function handleClick(event) { if (ref.current && !ref.current.contains(event.target)) { callback(event); } } document.addEventListener('mousedown', handleClick); return () => document.removeEventListener('mousedown', handleClick); }, [callback]); return ref; } // Usage — close a dropdown/modal when clicking outside function Dropdown({ onClose }) { const ref = useClickOutside(onClose); return <div ref={ref} className="dropdown">...</div>; }

```

### 52. Implement a custom `useDebounce` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useEffect } from 'react'; function useDebounce(value, delay = 300) { const [debounced, setDebounced] = useState(value); useEffect(() => { const timer = setTimeout(() => setDebounced(value), delay); return () => clearTimeout(timer); // cancel if value changes before delay elapses }, [value, delay]); return debounced; } // Usage function Search() { const [query, setQuery] = useState(''); const debouncedQuery = useDebounce(query, 400); useEffect(() => { if (debouncedQuery) fetchResults(debouncedQuery); }, [debouncedQuery]); return <input value={query} onChange={e => setQuery(e.target.value)} />; }

```
The hook only "commits" the latest value after the user has stopped typing for `delay` ms — every keystroke resets the timer via the cleanup function, so the API call fires once, not on every character.

### 53. Implement a custom `useEventListener` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useRef, useEffect } from 'react'; function useEventListener(eventName, handler, element = window) { const savedHandler = useRef(handler); useEffect(() => { savedHandler.current = handler; // always call the latest handler, no stale closures }, [handler]); useEffect(() => { const target = element?.current ?? element; if (!target?.addEventListener) return; const listener = (event) => savedHandler.current(event); target.addEventListener(eventName, listener); return () => target.removeEventListener(eventName, listener); }, [eventName, element]); } // Usage useEventListener('resize', () => console.log(window.innerWidth));

```

### 54. Implement a custom `useFetch` hook (loading/error/data states)

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useEffect } from 'react'; function useFetch(url, options) { const [state, setState] = useState({ data: null, loading: true, error: null }); useEffect(() => { const controller = new AbortController(); setState({ data: null, loading: true, error: null }); fetch(url, { ...options, signal: controller.signal }) .then(res => { if (!res.ok) throw new Error(`HTTP ${res.status}`); return res.json(); }) .then(data => setState({ data, loading: false, error: null })) .catch(err => { if (err.name !== 'AbortError') { setState({ data: null, loading: false, error: err }); } }); return () => controller.abort(); }, [url]); return state; // { data, loading, error } }

```
Key points: `AbortController` cancels the in-flight request on unmount or when `url` changes (prevents setting state on an unmounted component / race conditions between overlapping requests), and the object is reset to a loading state at the start of every new fetch.

### 55. Implement a custom `useIntersectionObserver` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useEffect, useRef } from 'react'; function useIntersectionObserver(options = { threshold: 0.1 }) { const ref = useRef(null); const [isIntersecting, setIsIntersecting] = useState(false); useEffect(() => { const node = ref.current; if (!node) return; const observer = new IntersectionObserver(([entry]) => { setIsIntersecting(entry.isIntersecting); }, options); observer.observe(node); return () => observer.disconnect(); }, [options.threshold, options.root, options.rootMargin]); return [ref, isIntersecting]; } // Usage — lazy-load an image or trigger infinite scroll function LazyImage({ src }) { const [ref, visible] = useIntersectionObserver(); return <img ref={ref} src={visible ? src : undefined} />; }

```

### 56. Implement a custom `useLocalStorage` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useEffect, useCallback } from 'react'; function useLocalStorage(key, initialValue) { const [value, setValue] = useState(() => { try { const item = window.localStorage.getItem(key); return item ? JSON.parse(item) : initialValue; } catch { return initialValue; } }); const setStoredValue = useCallback((newValue) => { setValue(prev => { const resolved = newValue instanceof Function ? newValue(prev) : newValue; try { window.localStorage.setItem(key, JSON.stringify(resolved)); } catch (e) { console.error('localStorage write failed', e); } return resolved; }); }, [key]); // keep in sync across browser tabs useEffect(() => { const onStorage = (e) => { if (e.key === key && e.newValue) setValue(JSON.parse(e.newValue)); }; window.addEventListener('storage', onStorage); return () => window.removeEventListener('storage', onStorage); }, [key]); return [value, setStoredValue]; }

```

### 57. Implement a custom `useMediaQuery` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useEffect } from 'react'; function useMediaQuery(query) { const [matches, setMatches] = useState(() => window.matchMedia(query).matches); useEffect(() => { const mql = window.matchMedia(query); const handler = (e) => setMatches(e.matches); mql.addEventListener('change', handler); setMatches(mql.matches); return () => mql.removeEventListener('change', handler); }, [query]); return matches; } // Usage const isMobile = useMediaQuery('(max-width: 600px)');

```

### 58. Implement a custom `usePrevious` hook (returns previous state value)

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useRef, useEffect } from 'react'; function usePrevious(value) { const ref = useRef(); useEffect(() => { ref.current = value; // runs AFTER render, so ref still holds the OLD value during this render }, [value]); return ref.current; } // Usage function Counter({ count }) { const prevCount = usePrevious(count); return <p>Now: {count}, before: {prevCount}</p>; }

```
This works because `useEffect` runs after the render commits — so on any given render, `ref.current` still holds the value from the *previous* render until the effect updates it.

### 59. Implement a custom `useThrottle` hook?

[↑ Back to Table of Contents](#table-of-contents)

```jsx import { useState, useRef, useEffect } from 'react'; function useThrottle(value, limit = 300) { const [throttled, setThrottled] = useState(value); const lastRan = useRef(Date.now()); useEffect(() => { const timer = setTimeout(() => { if (Date.now() - lastRan.current >= limit) { setThrottled(value); lastRan.current = Date.now(); } }, limit - (Date.now() - lastRan.current)); return () => clearTimeout(timer); }, [value, limit]); return throttled; }

```
Unlike debounce (which waits for a pause), throttle guarantees the value updates **at most once every `limit` ms**, even during continuous activity — useful for scroll/resize handlers where you want steady, periodic updates rather than a single update after the activity stops.

### 60. Implement a custom hook like `useDebounce` or `useFetch` (React).

[↑ Back to Table of Contents](#table-of-contents) **`useDebounce`**:

```
javascript import { useState, useEffect } from 'react'; function useDebounce(value, delay) { const [debouncedValue, setDebouncedValue] = useState(value); useEffect(() => { const handler = setTimeout(() => setDebouncedValue(value), delay); return () => clearTimeout(handler); }, [value, delay]); return debouncedValue; }

```
**`useFetch`**:

```
javascript function useFetch(url, options = {}) { const [data, setData] = useState(null); const [loading, setLoading] = useState(true); const [error, setError] = useState(null); useEffect(() => { const abortController = new AbortController(); const signal = abortController.signal; fetch(url, { ...options, signal }) .then(res => { if (!res.ok) throw new Error('Network response was not ok'); return res.json(); }) .then(data => { setData(data); setLoading(false); }) .catch(err => { if (err.name !== 'AbortError') { setError(err); setLoading(false); } }); return () => abortController.abort(); }, [url]); return { data, loading, error }; }

```
------------------------------------------------------------------------

### 61. Implement a recursive comment thread (nested comments with reply)

[↑ Back to Table of Contents](#table-of-contents)

```jsx function Comment({ comment, onReply }) { const [replying, setReplying] = useState(false); const [text, setText] = useState(''); return ( <div style={{ marginLeft: 20 }}> <p>{comment.author}: {comment.text}</p> <button onClick={() => setReplying(r => !r)}>Reply</button> {replying && ( <form onSubmit={e => { e.preventDefault(); onReply(comment.id, text); setText(''); setReplying(false); }}> <input value={text} onChange={e => setText(e.target.value)} /> <button type="submit">Post</button> </form> )} {comment.children?.map(child => ( <Comment key={child.id} comment={child} onReply={onReply} /> ))} </div> ); } function CommentThread({ comments, onReply }) { return comments.map(c => <Comment key={c.id} comment={c} onReply={onReply} />); }

```
The component calls itself for `comment.children`, so each level of nesting just increases the indentation — the recursion terminates naturally when a comment has no children. `onReply` is passed down unchanged so any nested comment can add a child to the tree, typically by updating a normalized state object or array in the parent that owns the whole tree.

### 62. Implement Debouncing and Throttling in a search or scroll-heavy component.

[↑ Back to Table of Contents](#table-of-contents) **Debouncing** (search input):

```jsx const debouncedSearch = useCallback( debounce((query) => { /* fetch */ }, 300), [] ); const handleChange = (e) => debouncedSearch(e.target.value);

```
**Throttling** (scroll event):

```jsx const throttledScroll = useCallback( throttle(() => { /* handle scroll */ }, 200), [] ); useEffect(() => { window.addEventListener('scroll', throttledScroll); return () => window.removeEventListener('scroll', throttledScroll); }, []);

```

### 63. Returning a Promise from `useEffect`:

```jsx useEffect(async () => { await fetchData(); }, []); // anti-pattern // React expects undefined or a cleanup function, not a Promise — warns in console. Wrap the async logic in an inner function instead.

```

### 64. Stale closure in a `setInterval` inside `useEffect`:

```jsx useEffect(() => { const id = setInterval(() => console.log('count is', count), 1000); return () => clearInterval(id); }, []); // missing `count` dependency // Always logs the count from mount time (e.g. 0), never updates.

```

### 65. Two components using the same custom hook — do they share state?

[↑ Back to Table of Contents](#table-of-contents)

```jsx function useCustomHook() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('hook effect:', count); }, [count]); return [count, setCount]; } function ComponentA() { const [count, setCount] = useCustomHook(); return <button onClick={() => setCount(c => c + 1)}>A: {count}</button>; } function ComponentB() { const [count, setCount] = useCustomHook(); return <button onClick={() => setCount(c => c + 1)}>B: {count}</button>; }

```
**Behavior:** A and B have COMPLETELY INDEPENDENT state. Clicking A only affects A's count. Clicking B only affects B's. **Explanation:** Custom hooks share LOGIC, not STATE. Each component that calls `useCustomHook` gets its own isolated `useState` and `useEffect` instances. This is why hooks are more flexible than HOCs for sharing behavior.

### 66. Use Descriptive Names for Custom Hooks?

```jsx // ❌ Bad function useData() { } // ✅ Good function useUserAuthentication() { } function useFetchProducts() { } function useFormValidation() { }

```

### 67. What is the output of the following code? `// Portals: where does the component appear in the DOM? function Modal...`?

```jsx // Portals: where does the component appear in the DOM? function Modal({ children }) { return ReactDOM.createPortal( <div className="modal">{children}</div>, document.getElementById('modal-root') // Outside #app ); } function App() { const [show, setShow] = React.useState(false); return ( <div id="app" onClick={() => console.log('app clicked')}> <button onClick={() => setShow(true)}>Open Modal</button> {show && ( <Modal> <button onClick={(e) => { e.stopPropagation(); // Does this stop App's onClick? console.log('modal button clicked'); }}> Close </button> </Modal> )} </div> ); }

```
**Behavior:** Clicking the modal button logs only `modal button clicked`. `stopPropagation` WORKS even though the modal is rendered outside `#app` in the DOM. **Explanation:** Portals render outside the DOM hierarchy but remain in the REACT component tree. Event bubbling follows the REACT tree, not the DOM tree. So events from a portal bubble up through React parents, and `stopPropagation` works relative to the React tree. [⬆ Back to Table of Contents](#-table-of-contents)

### 68. What is the output of the following code? `// React 17 behavior: function App17() { const [a, setA] = React.useSt...`?

```jsx // React 17 behavior: function App17() { const [a, setA] = React.useState(0); const [b, setB] = React.useState(0); function handleClick() { setTimeout(() => { setA(1); // triggers render setB(1); // triggers another render — 2 renders total in React 17 }, 0); } // ... } // React 18 behavior: function App18() { // Same code, but with createRoot: // setTimeout(() => { setA(1); setB(1); }) — BATCHED! Only 1 render. }

```
**Explanation:** React 17: batching only in React event handlers (onClick, etc.). `setTimeout`, `Promise`, native events caused separate re-renders. React 18 with `createRoot`: automatic batching everywhere — all state updates in async callbacks are batched into one render. [⬆ Back to Table of Contents](#-table-of-contents)

### 69. What is the output of the following code? `const MyContext = React.createContext(0); function Child() { const val...`?

```jsx const MyContext = React.createContext(0); function Child() { const value = React.useContext(MyContext); console.log('Child render:', value); return <div>{value}</div>; } function App() { const [count, setCount] = React.useState(0); return ( <MyContext.Provider value={count}> <Child /> <button onClick={() => setCount(c => c + 1)}>+</button> </MyContext.Provider> ); }

```
**Behavior:** Child re-renders on every count increment, logging the new value.

### 70. What is the output of the following code? `const ThemeContext = React.createContext(); function App() { const [th...`?

```jsx const ThemeContext = React.createContext(); function App() { const [theme, setTheme] = React.useState({ color: 'blue' }); return ( <ThemeContext.Provider value={theme}> <Child /> <button onClick={() => setTheme({ color: 'red' })}>Change</button> </ThemeContext.Provider> ); } function Child() { const theme = React.useContext(ThemeContext); console.log('Child rendered'); return <div style={{ color: theme.color }}>Hello</div>; }

```
**Behavior:** Every time `setTheme` is called with a new object (even `{ color: 'blue' }` again), ALL consumers re-render. **Explanation:** Context re-renders all consumers when the value changes by REFERENCE. Every `setTheme(...)` creates a new object, triggering all consumers. Fix: memoize the value with `useMemo`, or split contexts. [⬆ Back to Table of Contents](#-table-of-contents)

### 71. What is the output of the following code? `function App() { const [a, setA] = React.useState(0); const [b, setB] ...`?

```jsx function App() { const [a, setA] = React.useState(0); const [b, setB] = React.useState(0); console.log('render', a, b); return ( <button onClick={() => { setA(1); setB(2); }}> Click </button> ); }

```
**Behavior:** On click, logs `render 1 2` ONCE (not twice). **Explanation:** React 18 automatically batches ALL state updates — even inside native event handlers. Both `setA` and `setB` are batched into a single re-render. In React 17, this would also batch inside React synthetic events (but not in setTimeout/promises). [⬆ Back to Table of Contents](#-table-of-contents)

### 72. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); const [m...`?

```jsx function App() { const [count, setCount] = React.useState(0); const [multiplier, setMultiplier] = React.useState(2); const result = React.useMemo(() => { console.log('computing...'); return count * multiplier; }, [count, multiplier]); return ( <> <p>{result}</p> <button onClick={() => setCount(c => c + 1)}>count: {count}</button> <button onClick={() => setMultiplier(m => m + 1)}>multiplier: {multiplier}</button> </> ); }

```
**Behavior:** `computing...` only logs when `count` OR `multiplier` changes. Not on unrelated re-renders (if parent caused a re-render for some other reason). **Explanation:** `useMemo` caches the result and only recomputes when dependencies change. Clicking either button logs `computing...`. If there was another state that caused re-renders, `useMemo` would protect this computation. [⬆ Back to Table of Contents](#-table-of-contents)

### 73. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); const pr...`?

```jsx function App() { const [count, setCount] = React.useState(0); const prevCount = React.useRef(null); React.useEffect(() => { prevCount.current = count; }); return ( <div> <p>Current: {count}, Previous: {prevCount.current}</p> <button onClick={() => setCount(c => c + 1)}>+</button> </div> ); }

```
**Behavior:** Initially shows `Current: 0, Previous: null`. After first click: `Current: 1, Previous: 0`. After second click: `Current: 2, Previous: 1`. **Explanation:** The `useEffect` without deps runs after EVERY render, updating the ref with the current count. During the NEXT render, `prevCount.current` holds the previous value. Since ref updates don't cause re-renders, this works correctly. [⬆ Back to Table of Contents](#-table-of-contents)

### 74. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); const re...`?

```jsx function App() { const [count, setCount] = React.useState(0); const renderCount = React.useRef(0); renderCount.current++; return ( <div> <p>State count: {count}</p> <p>Render count: {renderCount.current}</p> <button onClick={() => setCount(c => c + 1)}>Increment state</button> <button onClick={() => { renderCount.current++; console.log(renderCount.current); }}> Increment ref </button> </div> ); }

```
**Behavior:** - Clicking "Increment state" re-renders, both counts update visually. - Clicking "Increment ref" DOES NOT re-render. `renderCount.current` changes in memory but UI doesn't update. The console shows updated value but the page doesn't re-render. **Explanation:** Changing `ref.current` never triggers a re-render. `renderCount.current++` in the render body runs on every render (counting correctly), but it's only visible because a STATE change causes a re-render. [⬆ Back to Table of Contents](#-table-of-contents)

### 75. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); function...`?

```jsx function App() { const [count, setCount] = React.useState(0); function handleClick() { setCount(5); setCount(5); setCount(5); } // How many times does the component re-render? }

```
**Behavior:** The component re-renders ONCE (not three times). **Explanation:** React batches the state updates. Since all three calls set the same value `5`, React also applies the "bail-out" optimization — if the new state is the same as the current state (using `Object.is`), React may not re-render at all (if already at 5). [⬆ Back to Table of Contents](#-table-of-contents)

### 76. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); React.us...`?

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('effect ran, count:', count); }); return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior:** Effect logs on EVERY render (mount + every update). **Explanation:** `useEffect` with NO dependency array runs after every render. On mount: effect runs. On every state/prop change → re-render → effect runs again. [⬆ Back to Table of Contents](#-table-of-contents)

### 77. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); React.us...`?

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('mounted'); return () => console.log('unmounted'); }, []); return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior (with React.StrictMode):** Logs `mounted`, `unmounted`, `mounted` on initial render. Then nothing on updates. **Behavior (without StrictMode):** Logs `mounted` once on mount. `unmounted` only when component is removed from DOM. **Explanation:** `[]` dependency array means "run only on mount, cleanup on unmount." In StrictMode, React intentionally double-invokes effects in development to catch bugs. [⬆ Back to Table of Contents](#-table-of-contents)

### 78. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); React.us...`?

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('effect', count); return () => { console.log('cleanup', count); }; }, [count]); return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior:** Initial render: `effect 0`. Click: `cleanup 0` then `effect 1`. Click again: `cleanup 1` then `effect 2`. **Explanation:** When `count` changes: cleanup of the PREVIOUS effect runs first (with the OLD `count` value captured in closure), then the new effect runs with the new `count`. [⬆ Back to Table of Contents](#-table-of-contents)

### 79. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); React.us...`?

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { setCount(count + 1); // Infinite loop! }, [count]); return <div>{count}</div>; }

```
**Behavior:** Infinite re-render loop. Browser tab crashes. **Explanation:** Effect runs → updates `count` → triggers re-render → effect sees new `count` in deps → runs again → infinite loop. Fix: use `setCount(prev => prev + 1)` with `[]` deps, or restructure logic to not update the same state you depend on. [⬆ Back to Table of Contents](#-table-of-contents)

### 80. What is the output of the following code? `function App() { const [count, setCount] = React.useState(0); React.us...`?

```jsx function App() { const [count, setCount] = React.useState(0); React.useEffect(() => { const interval = setInterval(() => { console.log('count is', count); // Stale closure! }, 1000); return () => clearInterval(interval); }, []); // Missing count in deps return <button onClick={() => setCount(c => c + 1)}>{count}</button>; }

```
**Behavior:** The interval always logs `count is 0` even as you click and count increases. **Explanation:** Stale closure bug. The effect captures `count = 0` at mount time. Since `[]` prevents re-running, the interval never gets the updated `count`. Fix: add `count` to deps (resets interval on change), or use a ref to store latest count. [⬆ Back to Table of Contents](#-table-of-contents)

### 81. What is the output of the following code? `function App() { const [flag, setFlag] = React.useState(false); if (fl...`?

```jsx function App() { const [flag, setFlag] = React.useState(false); if (flag) { const [extra, setExtra] = React.useState(0); // RULES VIOLATION! } return <button onClick={() => setFlag(true)}>Click</button>; }

```
**Behavior:** React throws an error: "Rendered more hooks than during the previous render." **Explanation:** Hooks must be called in the SAME ORDER every render. Conditional hooks change the hook call count/order between renders, breaking React's internal hook-to-state mapping. This is why the Rules of Hooks exist. [⬆ Back to Table of Contents](#-table-of-contents)

### 82. What is the output of the following code? `function App() { const [isLoggedIn, setIsLoggedIn] = React.useState(fa...`?

```jsx function App() { const [isLoggedIn, setIsLoggedIn] = React.useState(false); return ( <div> {isLoggedIn && <Dashboard />} {isLoggedIn ? <UserMenu /> : <LoginButton />} {isLoggedIn || <GuestBanner />} </div> ); }

```
**Behavior when `isLoggedIn = false`:** Shows only `<GuestBanner />`. **Behavior when `isLoggedIn = true`:** Shows `<Dashboard />`, `<UserMenu />`. `<GuestBanner />` is hidden. **Explanation:** `{condition && <Component />}` — renders nothing when false (React ignores `false`). `{condition || <Component />}` — renders component when condition is falsy. Note: `{0 && <Comp />}` renders `0` — use `{!!count && <Comp />}` or ternary. [⬆ Back to Table of Contents](#-table-of-contents)

### 83. What is the output of the following code? `function App() { const [items, setItems] = React.useState([ { id: 1, t...`?

```jsx function App() { const [items, setItems] = React.useState([ { id: 1, text: 'First' }, { id: 2, text: 'Second' }, ]); function addFirst() { setItems([{ id: 0, text: 'New' }, ...items]); } // Version A: key=index // Version B: key=item.id return ( <> <button onClick={addFirst}>Add to front</button> <ul> {items.map((item, index) => ( <li key={index}> {/* Or key={item.id} */} {item.text} <input defaultValue={item.text} /> </li> ))} </ul> </> ); }

```
**Behavior with `key={index}`:** Adding to front keeps input values in wrong positions — the new item gets the old first item's input value. **Behavior with `key={item.id}`:** Correct behavior — each item keeps its own input state. **Explanation:** With index keys, prepending shifts all indices. React maps old key `0` to new item at position `0`, reusing the DOM node. With id keys, React correctly identifies each item and mounts a new node for the new item. [⬆ Back to Table of Contents](#-table-of-contents)

### 84. What is the output of the following code? `function App() { const [items, setItems] = React.useState(['a', 'b', '...`?

```jsx function App() { const [items, setItems] = React.useState(['a', 'b', 'c']); return ( <ul> {items.map(item => ( <li>{item} <input /></li> // Missing key! ))} </ul> ); }

```
**Behavior:** React console warning about missing `key`. If items are added/removed, input values may be incorrectly preserved on the wrong elements. **Explanation:** Without keys, React uses index-based reconciliation. If you prepend an item, React reuses the FIRST DOM node for it, potentially preserving the old input's value in the wrong place. [⬆ Back to Table of Contents](#-table-of-contents)

### 85. What is the output of the following code? `function App() { const [items, setItems] = React.useState([1, 2, 3]); ...`?

```jsx function App() { const [items, setItems] = React.useState([1, 2, 3]); function addItem() { items.push(4); // Direct mutation! setItems(items); } return ( <div> {items.map(i => <span key={i}>{i}</span>)} <button onClick={addItem}>Add</button> </div> ); }

```
**Behavior:** Clicking "Add" may NOT re-render. The item may or may not appear. **Explanation:** `items.push(4)` mutates the array directly. `setItems(items)` passes the SAME array reference. React's shallow comparison sees the same reference and may bail out of re-rendering. Fix: `setItems([...items, 4])` — new reference triggers re-render. [⬆ Back to Table of Contents](#-table-of-contents)

### 86. What is the output of the following code? `function App() { const [items, setItems] = React.useState([1, 2, 3]); ...`?

```jsx function App() { const [items, setItems] = React.useState([1, 2, 3]); return ( <ul> {items.map((item) => ( <li key={item}> {item} <input defaultValue={item} /> </li> ))} </ul> ); } // User types in the first input, then the list order is reversed. // What happens to the typed value?

```
**Behavior with stable keys (`key={item}`):** Input values follow their item correctly — the typed value stays with the right item. **Behavior with index keys (`key={index}`):** Typed value stays with the POSITION, not the item. After reversal, the value is in the wrong input. **Explanation:** Keys tell React which DOM nodes belong to which items. Stable (unique) keys allow React to correctly reorder DOM nodes with their state. Index keys cause DOM confusion on reorder/insert/delete. [⬆ Back to Table of Contents](#-table-of-contents)

### 87. What is the output of the following code? `function App() { const [resource, setResource] = React.useState(null);...`?

```jsx function App() { const [resource, setResource] = React.useState(null); const [isPending, startTransition] = React.useTransition(); function handleClick() { startTransition(() => { setResource(fetchData()); // Expensive operation }); } return ( <> <button onClick={handleClick} disabled={isPending}> {isPending ? 'Loading...' : 'Load Data'} </button> <React.Suspense fallback={<p>Loading content...</p>}> {resource && <DataDisplay resource={resource} />} </React.Suspense> </> ); }

```
**Behavior:** Button shows 'Loading...' while transition is pending. UI remains interactive. Suspense shows fallback only if the data-fetching component suspends. **Explanation:** `isPending` from `useTransition` tells you when a transition is in-flight. Button stays interactive. Combining `useTransition` + `Suspense` gives smooth, non-blocking data loading UX. [⬆ Back to Table of Contents](#-table-of-contents)

### 88. What is the output of the following code? `function App() { const [show, setShow] = React.useState(true); React.u...`?

```jsx function App() { const [show, setShow] = React.useState(true); React.useEffect(() => { return () => { console.log('App cleanup'); }; }, []); return ( <> {show && <Child />} <button onClick={() => setShow(false)}>Hide</button> </> ); } function Child() { React.useEffect(() => { console.log('Child mounted'); return () => console.log('Child cleanup'); }, []); return <div>child</div>; }

```
**Behavior:** On mount: `Child mounted`. On clicking Hide: `Child cleanup`. App's cleanup only runs when App itself unmounts. **Explanation:** Effect cleanups run when the component unmounts OR before the next effect run. Conditional rendering (`show && <Child />`) unmounts Child when `show` becomes false, triggering Child's cleanup. [⬆ Back to Table of Contents](#-table-of-contents)

### 89. What is the output of the following code? `function App() { const [type, setType] = React.useState('A'); return (...`?

```jsx function App() { const [type, setType] = React.useState('A'); return ( <> {type === 'A' ? <ComponentA /> : <ComponentB />} <button onClick={() => setType(t => t === 'A' ? 'B' : 'A')}>Toggle</button> </> ); } function ComponentA() { React.useEffect(() => { console.log('A mounted'); return () => console.log('A unmounted'); }, []); return <div>A</div>; } function ComponentB() { React.useEffect(() => { console.log('B mounted'); return () => console.log('B unmounted'); }, []); return <div>B</div>; }

```
**Output on toggle A→B:**

```
A unmounted B mounted

```
**Explanation:** Switching between two DIFFERENT component types causes React to unmount the old one and mount the new one — full lifecycle. State is completely reset. If you rendered `<ComponentA />` in both branches, React would KEEP the instance and just update props. [⬆ Back to Table of Contents](#-table-of-contents)

### 90. What is the output of the following code? `function App() { const [user, setUser] = React.useState({ name: 'Alice...`?

```jsx function App() { const [user, setUser] = React.useState({ name: 'Alice', age: 25 }); function updateName() { setUser({ name: 'Bob' }); // Missing age! } return ( <div> <p>{user.name} - {user.age}</p> <button onClick={updateName}>Update</button> </div> ); }

```
**Behavior:** After clicking, shows `Bob - ` (age is gone). **Explanation:** Unlike class component `setState`, the `useState` setter REPLACES the entire state, not merges it. Passing `{ name: 'Bob' }` discards `age`. Fix: `setUser(prev => ({ ...prev, name: 'Bob' }))`. [⬆ Back to Table of Contents](#-table-of-contents)

### 91. What is the output of the following code? `function App() { const [width, setWidth] = React.useState(0); React.us...`?

```jsx function App() { const [width, setWidth] = React.useState(0); React.useLayoutEffect(() => { setWidth(document.body.clientWidth); }, []); React.useEffect(() => { console.log('useEffect width:', width); }, [width]); return <div>Width: {width}</div>; }

```
**Behavior:** `useLayoutEffect` fires before browser paint, measures DOM, sets width. User never sees `width: 0` — they immediately see the correct width. `useEffect` fires after paint with the updated width. **Explanation:** `useLayoutEffect` blocks paint — use for DOM measurements to avoid flicker. `useEffect` is non-blocking and runs after paint — use for side effects that don't need to block rendering. [⬆ Back to Table of Contents](#-table-of-contents)

### 92. What is the output of the following code? `function App() { React.useEffect(() => { console.log('effect 1'); retu...`?

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
**Explanation:** Multiple `useEffect` hooks run in the ORDER they are declared, after each render. Cleanups also run in declaration order on unmount. [⬆ Back to Table of Contents](#-table-of-contents)

### 93. What is the output of the following code? `function App() { React.useEffect(async () => { const data = await fetc...`?

```jsx function App() { React.useEffect(async () => { const data = await fetch('/api/data').then(r => r.json()); console.log(data); }, []); // Anti-pattern! }

```
**Behavior:** Works but creates an unhandled Promise. React warns in console. **Explanation:** `useEffect` expects its callback to return either `undefined` or a cleanup function. `async` functions return Promises — React can't call a Promise as cleanup. Correct pattern:

```jsx React.useEffect(() => { let cancelled = false; async function fetchData() { const data = await fetch('/api/data').then(r => r.json()); if (!cancelled) console.log(data); } fetchData(); return () => { cancelled = true; }; }, []);

```
[⬆ Back to Table of Contents](#-table-of-contents)

### 94. What is the output of the following code? `function Child({ onClick }) { console.log('Child rendered'); return <b...`?

```jsx function Child({ onClick }) { console.log('Child rendered'); return <button onClick={onClick}>Click</button>; } const MemoChild = React.memo(Child); function Parent() { const [count, setCount] = React.useState(0); const handleClick = () => setCount(c => c + 1); return ( <> <p>{count}</p> <MemoChild onClick={handleClick} /> </> ); }

```
**Behavior:** `Child rendered` logs on EVERY parent re-render despite `React.memo`. **Explanation:** `React.memo` does shallow prop comparison. `handleClick` is a NEW function reference on every render (arrow function defined inline). The prop reference changes every time, so `memo` sees different props and re-renders. Fix: wrap `handleClick` in `useCallback`. [⬆ Back to Table of Contents](#-table-of-contents)

### 95. What is the output of the following code? `function Counter() { const [count, setCount] = React.useState(0); func...`?

```jsx function Counter() { const [count, setCount] = React.useState(0); function handleClick() { setCount(count + 1); setCount(count + 1); setCount(count + 1); console.log(count); } return <button onClick={handleClick}>{count}</button>; }

```
**Behavior:** Clicking the button logs `0` and the count shows `1` (not `3`). **Explanation:** State updates are batched. All three `setCount(count + 1)` calls capture the SAME `count` value (stale closure). They all schedule a re-render with `0 + 1 = 1`. The component re-renders once with `count = 1`. Fix: use functional updates `setCount(prev => prev + 1)`. [⬆ Back to Table of Contents](#-table-of-contents)

### 96. What is the output of the following code? `function Counter() { const [count, setCount] = React.useState(0); func...`?

```jsx function Counter() { const [count, setCount] = React.useState(0); function handleClick() { setCount(prev => prev + 1); setCount(prev => prev + 1); setCount(prev => prev + 1); } return <button onClick={handleClick}>{count}</button>; }

```
**Behavior:** Clicking the button increments count by 3 each click. **Explanation:** Functional updates always receive the LATEST state as `prev`. Even though batched, React processes them in order: `0→1→2→3`. Each updater receives the result of the previous one. [⬆ Back to Table of Contents](#-table-of-contents)

### 97. What is the output of the following code? `function Expensive({ data }) { const processed = React.useMemo(() => {...`?

```jsx function Expensive({ data }) { const processed = React.useMemo(() => { console.log('processing...'); return data.map(x => x * 2); }, [data]); return <div>{processed.join(', ')}</div>; } function App() { const [count, setCount] = React.useState(0); const data = [1, 2, 3]; // Created every render return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <Expensive data={data} /> </> ); }

```
**Behavior:** `processing...` logs on EVERY render despite `useMemo`. **Explanation:** `data = [1, 2, 3]` creates a NEW array every render. `useMemo`'s dep comparison uses `Object.is` — different array reference every time → recomputes. Fix: `const data = React.useMemo(() => [1, 2, 3], [])` in App. [⬆ Back to Table of Contents](#-table-of-contents)

### 98. What is the output of the following code? `function ExpensiveChild({ items }) { console.log('ExpensiveChild rende...`?

```jsx function ExpensiveChild({ items }) { console.log('ExpensiveChild rendered'); return <ul>{items.map(i => <li key={i}>{i}</li>)}</ul>; } const MemoChild = React.memo(ExpensiveChild); function Parent() { const [count, setCount] = React.useState(0); const items = React.useMemo(() => [1, 2, 3], []); return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <MemoChild items={items} /> </> ); }

```
**Behavior:** `ExpensiveChild rendered` logs only ONCE (on mount). Clicking button does NOT re-render child. **Explanation:** `useMemo(() => [1, 2, 3], [])` creates the array ONCE and returns the same reference every render. `React.memo` sees the same `items` reference — no re-render. This is the correct combination. [⬆ Back to Table of Contents](#-table-of-contents)

### 99. What is the output of the following code? `function InputWithState() { const [value, setValue] = React.useState('...`?

```jsx function InputWithState() { const [value, setValue] = React.useState(''); return <input value={value} onChange={e => setValue(e.target.value)} />; } function App() { const [show, setShow] = React.useState(true); return ( <> {show ? <InputWithState key="a" /> : <InputWithState key="b" />} <button onClick={() => setShow(s => !s)}>Toggle</button> </> ); }

```
**Behavior:** Each toggle RESETS the input to empty. **Explanation:** When the `key` changes from `"a"` to `"b"`, React treats it as a completely different component, unmounts the old one and mounts a new one. State is lost. This is a useful trick to force a component to reset state — change its key. [⬆ Back to Table of Contents](#-table-of-contents)

### 100. What is the output of the following code? `function Parent() { const [count, setCount] = React.useState(0); const...`?

```jsx function Parent() { const [count, setCount] = React.useState(0); const [text, setText] = React.useState(''); const handleClick = React.useCallback(() => { console.log('clicked'); }, []); // No deps const handleTextChange = React.useCallback((e) => { setText(e.target.value); }, []); // No deps return ( <> <button onClick={() => setCount(c => c + 1)}>{count}</button> <Child onClick={handleClick} /> </> ); } const Child = React.memo(({ onClick }) => { console.log('Child rendered'); return <button onClick={onClick}>Child</button>; });

```
**Behavior:** Child DOES NOT re-render when count changes. **Explanation:** `useCallback` with `[]` returns the SAME function reference across renders. `React.memo` + `useCallback` with stable deps = memoized child that doesn't re-render when parent's unrelated state changes. [⬆ Back to Table of Contents](#-table-of-contents)

### 101. What is the output of the following code? `function Parent() { const [count, setCount] = React.useState(0); const...`?

```jsx function Parent() { const [count, setCount] = React.useState(0); const Child = () => <div>child: {count}</div>; // Defined INSIDE render return ( <> <Child /> <button onClick={() => setCount(c => c + 1)}>+</button> </> ); }

```
**Behavior:** Works but is a serious performance bug. Every re-render creates a NEW `Child` component type. React sees a different component and UNMOUNTS the old one and MOUNTS a new one every render. **Explanation:** Never define components inside render functions. Each render creates a new function reference — React's reconciler sees a new component type and destroys + recreates the DOM. Move `Child` OUTSIDE `Parent`. [⬆ Back to Table of Contents](#-table-of-contents)

### 102. What is the output of the following code? `function Parent() { const [count, setCount] = React.useState(0); retur...`?

```jsx function Parent() { const [count, setCount] = React.useState(0); return ( <div> <button onClick={() => setCount(c => c + 1)}>Count: {count}</button> {React.useMemo(() => <ExpensiveChild />, [])} </div> ); } function ExpensiveChild() { console.log('ExpensiveChild render'); return <div>expensive</div>; }

```
**Behavior:** `ExpensiveChild render` logs only ONCE regardless of how many times button is clicked. **Explanation:** `React.useMemo(() => <ExpensiveChild />, [])` memoizes the React ELEMENT (not the component). Since the element reference is stable (same JSX object), React reuses the previous render result. This is an alternative to `React.memo` for cases where you control the parent. [⬆ Back to Table of Contents](#-table-of-contents)

### 103. What is the output of the following code? `function SearchResults({ query }) { const [results, setResults] = Reac...`?

```jsx function SearchResults({ query }) { const [results, setResults] = React.useState([]); React.useEffect(() => { // Heavy computation const filtered = hugeList.filter(item => item.includes(query)); setResults(filtered); }, [query]); return <ul>{results.map(r => <li key={r}>{r}</li>)}</ul>; } function App() { const [query, setQuery] = React.useState(''); const [isPending, startTransition] = React.useTransition(); function handleChange(e) { startTransition(() => { setQuery(e.target.value); // Non-urgent update }); } return ( <> <input onChange={handleChange} /> {isPending && <p>Loading...</p>} <SearchResults query={query} /> </> ); }

```
**Behavior:** Input remains responsive while results update. `isPending` shows loading state during transition. If user types fast, React may abandon intermediate transitions. **Explanation:** `startTransition` marks updates as non-urgent. React prioritizes the input update (urgent) and defers the search results update. This prevents the input from lagging during heavy re-renders. [⬆ Back to Table of Contents](#-table-of-contents)

### 104. What is the output of the following code? `function useCustomHook() { const [count, setCount] = React.useState(0)...`?

```jsx function useCustomHook() { const [count, setCount] = React.useState(0); React.useEffect(() => { console.log('hook effect:', count); }, [count]); return [count, setCount]; } function ComponentA() { const [count, setCount] = useCustomHook(); return <button onClick={() => setCount(c => c + 1)}>A: {count}</button>; } function ComponentB() { const [count, setCount] = useCustomHook(); return <button onClick={() => setCount(c => c + 1)}>B: {count}</button>; }

```
**Behavior:** A and B have COMPLETELY INDEPENDENT state. Clicking A only affects A's count. Clicking B only affects B's. **Explanation:** Custom hooks share LOGIC, not STATE. Each component that calls `useCustomHook` gets its own isolated `useState` and `useEffect` instances. This is why hooks are more flexible than HOCs for sharing behavior. [⬆ Back to Table of Contents](#-table-of-contents)

### 105. What is the output of the following code? `function useForceUpdate() { const [, setState] = React.useState(0); re...`?

```jsx function useForceUpdate() { const [, setState] = React.useState(0); return React.useCallback(() => setState(n => n + 1), []); } function App() { const forceUpdate = useForceUpdate(); const data = React.useRef({ value: 0 }); return ( <> <p>Value: {data.current.value}</p> <button onClick={() => { data.current.value += 1; // mutate ref forceUpdate(); // manually trigger re-render }}> Increment </button> </> ); }

```
**Behavior:** Works correctly — each click increments the displayed value. **Explanation:** Refs don't trigger re-renders on their own. By separating the data (ref) from the render trigger (state), you can accumulate changes and batch re-renders manually. Useful for high-frequency updates where you control when to re-render. [⬆ Back to Table of Contents](#-table-of-contents)

### 106. What is the output of the following code? `function useToggle(initial = false) { const [value, setValue] = React....`?

```jsx function useToggle(initial = false) { const [value, setValue] = React.useState(initial); const toggle = React.useCallback(() => setValue(v => !v), []); return [value, toggle]; } function App() { const [isOpen, toggle] = useToggle(); console.log('App render'); return ( <> <button onClick={toggle}>Toggle</button> {isOpen && <Modal />} </> ); }

```
**Behavior:** `toggle` is the same function reference across renders. Passing `toggle` to memoized children won't cause unnecessary re-renders. **Explanation:** `useCallback` with `[]` deps creates the function once. The `setValue(v => !v)` functional update never closes over stale state. This is the correct pattern for stable callback refs. [⬆ Back to Table of Contents](#-table-of-contents)

### 107. What is useEffect hook? How to fetch data with React Hooks?

The `useEffect` hook is a React Hook that lets you perform **side effects** in function components. Side effects are operations that interact with the outside world or system and aren't directly related to rendering UI --- such as fetching data, setting up subscriptions, timers, manually manipulating the DOM, etc. In function components, useEffect replaces the class component lifecycle methods(`componentDidMount`, `componentDidUpdate` and `componentWillUnmount`) with a single, unified API. **Syntax**

```js useEffect(() => { // Side effect logic here return () => { // Cleanup logic (optional) }; }, ** ------------------------------------------------------------------------ --- --- ## Context & State Management ### Can I dispatch an action in reducer? Dispatching an action within a reducer is an **anti-pattern**. Your reducer should be _without side effects_, simply digesting the action payload and returning a new state object. Adding listeners and dispatching actions within the reducer can lead to chained actions and other side effects. **** --- ### Can React Hook replaces Redux? The React Hook cannot be considered as a replacement for Redux (It is an open-source, JavaScript library useful in managing the application state) when it comes to the management of the global application state tree in large complex applications, even though the React will provide a useReducer hook that manages state transitions similar to Redux. Redux is very useful at a lower level of component hierarchy to handle the pieces of a state which are dependent on each other, instead of a declaration of multiple useState hooks. In commercial web applications which is larger, the complexity will be high, so using only React Hook may not be sufficient. Few developers will try to tackle the challenge with the help of React Hooks and others will combine React Hooks with the Redux. --- ### Can Redux only be used with React? Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. Redux simply provides a subscription mechanism which can be used by any other code. [ --- ### Can useRef be used to store previous values? Yes, `useRef` is a common pattern when you want to compare current and previous props or state without causing re-renders. **Example: Storing previous state value**

```js import { useEffect, useRef, useState } from 'react'; function PreviousValueExample() { const ** ------------------------------------------------------------------------

## Performance Optimization

### 108. `React.memo` with an inline function prop still re-renders:

```jsx const MemoChild = React.memo(Child); function Parent() { const [count, setCount] = useState(0); return <MemoChild onClick={() => setCount(c => c+1)} />; // New function reference every render → React.memo's shallow comparison fails → Child re-renders every time. // Fix: wrap the handler in useCallback. }

```

### 109. Design a Carousel that can handle 1000+ images efficiently.

**Requirements**: Smooth sliding, load images on demand, avoid memory bloat. **Design**: - **Virtualization**: Only render current, previous, next slide (buffer). Use `transform: translateX` for sliding. - **Lazy loading**: Use `IntersectionObserver` or `loading="lazy"` on images. Preload next image. - **DOM nodes**: Maintain only a few slide elements; reuse them as index changes. - **Memory**: Unload images that are far away by removing `src` and letting GC collect. - **Accessibility**: Keyboard arrows, ARIA roles.

### 110. Design a Data Table with sorting, filtering, pagination, and performance trade-offs.

**Requirements**: Table with large datasets, support sorting on columns, filtering, pagination. **Design**: - **Data fetching**: Choose client‑side (if dataset manageable) or server‑side (if huge). Server‑side reduces memory but increases network calls. - **State**: Store current page, page size, sort column/direction, filters. - **Rendering**: Virtualize rows if many visible at once. Use `React.memo` for rows. - **Sorting**: On column click, update state; if server‑side, fetch new data; if client‑side, sort array (memoize). - **Filtering**: Text inputs with debounce; if client‑side, filter array. - **Trade‑offs**: Client‑side allows instant filtering/sorting but limits data size. Server‑side more scalable but adds latency.

### 111. Design an Image Gallery with lazy loading and skeleton placeholders.

**Requirements**: Grid of images, load as user scrolls, show skeleton while loading. **Design**: - **Lazy loading**: Use `IntersectionObserver` to set `src` when image enters viewport. Fallback `loading="lazy"` for simpler. - **Skeletons**: Show a placeholder div with the same dimensions (aspect ratio) and a pulse animation. - **Responsive**: Use CSS Grid or flex with `object-fit: cover`. - **Error handling**: On error, show broken image icon. - **Performance**: Use `srcset` for responsive images, WebP format.

### 112. What happens when a parent re-renders?

All child components re-render by default unless wrapped in `React.memo` or the subtree is stable. Re-rendering means the function runs again; it does not mean the DOM changes – React still diffs before touching the DOM. [↑ Back to Table of Contents](#table-of-contents)

### 113. What is the output of the following code? `const Child = React.memo(function Child({ value }) { console.log('Chil...`?

```jsx const Child = React.memo(function Child({ value }) { console.log('Child rendered'); return <div>{value}</div>; }); function Parent() { const [count, setCount] = React.useState(0); const [text, setText] = React.useState(''); const config = { threshold: 100 }; return ( <> <Child value={text} config={config} /> <button onClick={() => setCount(c => c + 1)}>+{count}</button> </> ); }

```
**Behavior:** `Child rendered` logs on every Parent re-render despite `React.memo`. **Explanation:** `config = { threshold: 100 }` creates a NEW object on every render. `React.memo` sees a new `config` reference and re-renders. Fix: move `config` outside the component, or use `useMemo`. [⬆ Back to Table of Contents](#-table-of-contents)

## Context API & State Management (Redux/Zustand/MobX)

### 114. Design a state management solution for a complex app.

**Requirements**: - Handle asynchronous data, caching, optimistic updates. - Manage shared state across many features. - Ensure performance. **Design**: - **Global state**: Use Redux Toolkit with slices per feature. Use `createEntityAdapter` for normalized data. - **Async logic**: `createAsyncThunk` for API calls; handle loading/error states. - **Caching**: Implement a cache layer with expiration; use selectors to retrieve cached data. - **Optimistic updates**: Update the store optimistically on user actions; if the request fails, rollback using the previous state snapshot. - **Derived state**: Use `createSelector` (Reselect) for memoized derived data. - **Cross‑slice communication**: Use `extraReducers` to listen to actions from other slices. - **Performance**: Use selectors that compute only when needed. Use `React.memo` and `useCallback` to avoid re‑renders. ------------------------------------------------------------------------

### 115. How do you make sure that user remains authenticated on page refresh while using Context API State Management?

[↑ Back to Table of Contents](#table-of-contents) When a user logs in and reload, to persist the state generally we add the load user action in the useEffect hooks in the main App.js. While using Redux, loadUser action can be easily accessed. **App.js**

```
import { loadUser } from '../actions/auth'; store.dispatch(loadUser());

```
- But while using **Context API**, to access context in App.js, wrap the AuthState in index.js so that App.js can access the auth context. Now whenever the page reloads, no matter what route you are on, the user will be authenticated as **loadUser** action will be triggered on each re-render. **index.js**

```
import React from 'react'; import ReactDOM from 'react-dom'; import App from './App'; import AuthState from './context/auth/AuthState'; ReactDOM.render( <React.StrictMode> <AuthState> <App /> </AuthState> </React.StrictMode>, document.getElementById('root'), );

```
**App.js**

```
const authContext = useContext(AuthContext); const { loadUser } = authContext; useEffect(() => { loadUser(); }, []);

```
**loadUser**

```
const loadUser = async () => { const token = sessionStorage.getItem('token'); if (!token) { dispatch({ type: ERROR, }); } setAuthToken(token); try { const res = await axios('/api/auth'); dispatch({ type: USER_LOADED, payload: res.data.data, }); } catch (err) { console.error(err); } };

```

### 116. How to make AJAX request in Redux?

[↑ Back to Table of Contents](#table-of-contents) You can use `redux-thunk` middleware which allows you to define async actions. Let's take an example of fetching specific account as an AJAX call using _fetch API_:

```javascript export function fetchAccount(id) { return (dispatch) => { dispatch(setLoadingAccountState()); // Show a loading spinner fetch(`/account/${id}`, (response) => { dispatch(doneFetchingAccount()); // Hide loading spinner if (response.status === 200) { dispatch(setAccount(response.json)); // Use a normal function to set the received state } else { dispatch(someError); } }); }; } function setAccount(data) { return { type: "SET_Account", data: data }; }

```

### 117. How to set initial state in Redux?

[↑ Back to Table of Contents](#table-of-contents) You need to pass initial state as second argument to createStore:

```javascript const rootReducer = combineReducers({ todos: todos, visibilityFilter: visibilityFilter, }); const initialState = { todos: [{ id: 123, name: "example", completed: false }], }; const store = createStore(rootReducer, initialState);

```

## Routing & Navigation

### 118. How to add Google Analytics for React Router?

[↑ Back to Table of Contents](#table-of-contents) Add a listener on the `history` object to record each page view:

```javascript history.listen(function (location) { window.ga("set", "page", location.pathname + location.search); window.ga("send", "pageview", location.pathname + location.search); });

```
****

## React 18/19, Concurrent Features

### 119. Automatic batching inside a native event handler (React 18):

```jsx <button onClick={() => { setA(1); setB(2); }}>Click</button> // Logs ONE render, not two — React 18 batches automatically everywhere, including native handlers.

```

## Error Handling & Error Boundaries

### 120. Design a React app's error-reporting pipeline (client errors reaching an engineering dashboard).

Global Error Boundaries reporting to a monitoring SDK (e.g., Sentry) in `componentDidCatch`, a global `window.onerror`/`unhandledrejection` listener for errors outside React's tree, source maps uploaded for readable stack traces, and user/session context attached to each report for reproduction.

## Design Patterns (HOC, Render Props, Compound Components)

### 121. How to create props proxy for HOC component?

[↑ Back to Table of Contents](#table-of-contents) You can add/edit props passed to the component using *props proxy* pattern like this:

```jsx harmony function HOC(WrappedComponent) { return class Test extends Component { render() { const newProps = { title: "New Header", footer: false, showFeatureX: false, showFeatureY: true, }; return <WrappedComponent {...this.props} {...newProps} />; } }; }

```
**** ------------------------------------------------------------------------

### 122. How to format date using React Intl?

[↑ Back to Table of Contents](#table-of-contents) The `injectIntl()` higher-order component will give you access to the `formatDate()` method via the props in your component. The method is used internally by instances of `FormattedDate` and it returns the string representation of the formatted date.

```jsx harmony import { injectIntl, intlShape } from "react-intl"; const stringDate = this.props.intl.formatDate(date, { year: "numeric", month: "numeric", day: "numeric", }); const MyComponent = ({ intl }) => ( <div>{`The formatted date is ${stringDate}`}</div> ); MyComponent.propTypes = { intl: intlShape.isRequired, }; export default injectIntl(MyComponent);

```
****

### 123. What is the output of the following code? `// Pattern: render prop function DataFetcher({ url, render }) { const ...`?

```jsx // Pattern: render prop function DataFetcher({ url, render }) { const [data, setData] = React.useState(null); const [loading, setLoading] = React.useState(true); React.useEffect(() => { fetch(url).then(r => r.json()).then(d => { setData(d); setLoading(false); }); }, [url]); return render({ data, loading }); } // Usage: function App() { return ( <DataFetcher url="/api/users" render={({ data, loading }) => loading ? <p>Loading...</p> : <UserList users={data} /> } /> ); }

```
**Behavior:** `DataFetcher` is a headless component — it manages fetching logic, the parent controls rendering. When `url` changes, effect re-runs. **Key insight:** Render props pass state and behavior to consumers via function props. Modern equivalent: custom hooks (more composable, no JSX nesting). Both patterns are valid — render props shine when you need JSX composition context. [⬆ Back to Table of Contents](#-table-of-contents)

## Security & Accessibility

### 124. Design a Dropdown / Select component with keyboard navigation and accessibility.

**Requirements**: Custom dropdown that supports selection, keyboard navigation (arrow keys, Enter, Esc), and ARIA attributes. **Design**: - **Structure**: Button (trigger) + popup list. Use `role="combobox"`, `aria-expanded`, `aria-haspopup="listbox"`. - **Keyboard**: - Arrow down/up: move focus through options, update `aria-activedescendant`. - Enter/Space: select focused option. - Esc: close without selection. - **Focus management**: Keep focus on the trigger; manage active descendant. - **Virtualization** if many options. - **Outside click**: Use `useRef` and event listener to close when clicking outside. - **Portal** for popup to avoid overflow clipping. **Implementation**:

```
jsx const Dropdown = ({ options, value, onChange }) => { const [isOpen, setIsOpen] = useState(false); const [highlightedIndex, setHighlightedIndex] = useState(-1); // handle keyboard events // render button and list with aria attributes };

```
------------------------------------------------------------------------

### 125. Design a Modal/Dialog component -- focus trapping, accessibility, backdrop behavior.

**Requirements**: Modal that traps focus, is keyboard accessible (ESC to close), has backdrop, and is accessible. **Design**: - **Props**: `isOpen`, `onClose`, `title`, `children`, `closeOnBackdropClick`, `closeOnEsc`. - **Focus trapping**: Use `useEffect` to move focus to the first focusable element inside modal on open, and restore focus to the trigger on close. Use a ref to track focusable elements. - **Accessibility**: Set `role="dialog"`, `aria-modal="true"`, `aria-labelledby` referencing title. Ensure backdrop is inert to screen readers. - **Backdrop**: Render a semi‑transparent overlay; on click, call `onClose` if `closeOnBackdropClick`. - **Portal**: Render modal at the end of the `body` using `ReactDOM.createPortal` to avoid stacking issues. **Implementation**:

```
jsx const Modal = ({ isOpen, onClose, children }) => { useEffect(() => { const handleEsc = (e) => { if (e.key === 'Escape') onClose(); }; if (isOpen) { document.addEventListener('keydown', handleEsc); // trap focus logic } return () => document.removeEventListener('keydown', handleEsc); }, [isOpen, onClose]); if (!isOpen) return null; return ReactDOM.createPortal(/* modal JSX */, document.body); };

```

### 126. Design a Modal/Dialog component with focus trapping and accessibility.

Key requirements: (1) Focus trap: when modal opens, focus moves inside; Tab cycles only within modal; Escape closes. (2) aria-modal='true', role='dialog', aria-labelledby pointing to title. (3) Return focus to trigger element on close. (4) Backdrop click to close (optional). (5) Render in portal (ReactDOM.createPortal) to avoid z-index and overflow issues. (6) Lock body scroll while open. Implementation: useEffect to handle keyboard events and focus management, ref on modal container for focus trap logic.

### 127. Implement accessibility?

-- proper ARIA roles, keyboard navigation, focus management.\

## General / Miscellaneous React Concepts

### 128. Create a free personalised study plan?

Get into your dream companies with expert guidance Real-Life Problems Prep for Target Roles Custom Plan Duration [**Create My Plan**](https://www.interviewbit.com/interview-preparation-kit/)

### 129. Design a Config-Driven Form Renderer using a JSON schema.

**Requirements**: Render forms from a JSON definition, with validation, conditional fields, and custom components. **Design**: - **Schema structure**: `{ fields: [{ name, type, label, validation, conditions, options }] }`. - **Renderer**: Iterate over fields; map `type` to a React component (text input, select, date picker). Use a component registry. - **Validation**: Integrate with Zod or Yup; generate validation schema dynamically. - **Conditional fields**: Use `useWatch` (React Hook Form) to listen to values and filter fields based on conditions. - **State management**: Use `react-hook-form` for form state and validation. - **Extensibility**: Allow consumers to pass custom field components.

### 130. Design a file upload component with progress tracking and chunked uploads.

**Requirements**: - Upload large files in chunks. - Show progress per chunk and overall. - Support pause/resume, retry, and cancellation. **Design**: - **Chunking**: Split file into chunks of size (e.g., 1MB). Maintain a chunk queue. - **Upload logic**: Use `fetch` with `PUT` or `POST` and `Range` headers, or a custom API endpoint that accepts chunks. For each chunk, send a request with chunk index and total chunks. - **Progress**: Track per‑chunk status (pending, uploading, completed). Calculate overall progress (uploaded bytes / total bytes). Use `XMLHttpRequest` or `fetch` with `upload.onprogress`. - **Resume**: Store upload state (uploaded chunks) in `localStorage` or IndexedDB; resume by sending only missing chunks. - **Error handling**: Retry failed chunks with exponential backoff. - **Abort**: Use `AbortController` to cancel ongoing requests. - **UI**: Display progress bar, list of files, cancel/pause buttons.

### 131. Design a theme-able, extensible component library.

**Requirements**: - Support light/dark themes, custom brand colors. - Allow consumers to override styles. - Be extensible with new components. **Design**: - **Styling approach**: Use CSS‑in‑JS (emotion, styled‑components) with theming via `ThemeProvider` or use CSS variables for dynamic theming. - **Base styles**: Provide a set of design tokens (colors, spacing, typography) as CSS custom properties. - **Theme object**: Define theme object with `colors`, `spacing`, etc. Use React Context to pass theme. - **Component API**: Use polymorphic `as` prop to allow rendering as different elements. Provide variant props (`variant="primary"`). - **Extensibility**: Allow consumers to pass custom class names and `style` props. Use composition over inheritance. - **Documentation**: Provide Storybook for interactive documentation. - **Tree shaking**: Use barrel exports but ensure proper configuration for bundlers to only include used components.

### 132. Design a typeahead/autocomplete search component.

Debounced controlled input; cancel in-flight requests with `AbortController`; cache recent results; keyboard navigation with `role="combobox"`; loading/no-results states.

### 133. Design a Virtualized/Windowed list for very large datasets.

Core concept: only render visible rows + overscan buffer (~3 rows above/below viewport). Track scrollTop to determine which rows are visible. Row height can be fixed (simple) or dynamic (requires measurement with ResizeObserver). Container has total height (itemCount * rowHeight) for correct scrollbar. Visible items are absolutely positioned with top = index * rowHeight. Libraries: react-window (fixed), react-virtual (dynamic heights). Custom implementation: useRef for container, useState for scrollTop, useEffect for scroll listener with cleanup.

### 134. Give an example on How to use context?

**Context** is designed to share data that can be considered **global** for a tree of React components. For example, in the code below lets manually thread through a “theme” prop in order to style the Button component.

```javascript //Lets create a context with a default theme value "luna" const ThemeContext = React.createContext("luna"); // Create App component where it uses provider to pass theme value in the tree class App extends React.Component { render() { return ( <ThemeContext.Provider value="nova"> <Toolbar /> </ThemeContext.Provider> ); } } // A middle component where you don't need to pass theme prop anymore function Toolbar(props) { return ( <div> <ThemedButton /> </div> ); } // Lets read theme value in the button component to use class ThemedButton extends React.Component { static contextType = ThemeContext; render() { return <Button theme={this.context} />; } }

```
[↑ Back to Table of Contents](#table-of-contents)

### 135. How to create a switching component for displaying different pages?

A switching component refers to a component that will render one of the multiple components. We should use an object for mapping prop values to components. A below-given example will show you how to display different pages based on page prop using switching component:

```
import HomePage from './HomePage' import AboutPage from './AboutPage' import FacilitiesPage from './FacilitiesPage' import ContactPage from './ContactPage' import HelpPage from './HelpPage' const PAGES = { home: HomePage, about: AboutPage, facilitiess: FacilitiesPage, contact: ContactPage help: HelpPage } const Page = (props) => { const Handler = PAGES[props.page] || HelpPage return <Handler {...props} /> } // The PAGES object keys can be used in the prop types for catching errors during dev-time. Page.propTypes = { page: PropTypes.oneOf(Object.keys(PAGES)).isRequired }

```
[↑ Back to Table of Contents](#table-of-contents)

### 136. How to debug forwardRefs in DevTools?

[↑ Back to Table of Contents](#table-of-contents) **React.forwardRef** accepts a render function as parameter and DevTools uses this function to determine what to display for the ref forwarding component. For example, If you don't name the render function or not using displayName property then it will appear as ”ForwardRef” in the DevTools,

```javascript const WrappedComponent = React.forwardRef((props, ref) => { return <LogProps {...props} forwardedRef={ref} />; });

```
But If you name the render function then it will appear as **”ForwardRef(myFunction)”**

```javascript const WrappedComponent = React.forwardRef(function myFunction(props, ref) { return <LogProps {...props} forwardedRef={ref} />; });

```
As an alternative, You can also set displayName property for forwardRef function,

```javascript function logProps(Component) { class LogProps extends React.Component { // ... } function forwardRef(props, ref) { return <LogProps {...props} forwardedRef={ref} />; } // Give this component a more helpful display name in DevTools. // e.g. "ForwardRef(logProps(MyComponent))" const name = Component.displayName || Component.name; forwardRef.displayName = `logProps(${name})`; return React.forwardRef(forwardRef); }

```

### 137. What are the different ways to write `mapDispatchToProps()`?

There are a few ways of binding _action creators_ to `dispatch()` in `mapDispatchToProps()`. Below are the possible options:

```javascript const mapDispatchToProps = (dispatch) => ({ action: () => dispatch(action()), });

```
```javascript const mapDispatchToProps = (dispatch) => ({ action: bindActionCreators(action, dispatch), });

```
```javascript const mapDispatchToProps = { action };

```
The third option is just a shorthand for the first one. [↑ Back to Table of Contents](#table-of-contents)

### 138. What happens with `<div mycustomattribute="x" />` in modern React?

Since React 16, unknown DOM attributes pass through to the rendered DOM instead of being stripped.


---

*Total questions in this document: 138*
