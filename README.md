# ReactJS Interview Questions & Answers

ReactJS Interview Questions is a guide for both interviewers and candidates to prepare for ReactJS interviews. It features a curated list of questions covering basic to advanced concepts, helping evaluate understanding and skills in ReactJS development. Ideal for interview preparation or enhancing ReactJS knowledge.

⭐ If you find this guide helpful, please star the repository to show your support and help others discover it.

---

| 1.  | What is React? |
| --- | :------------- |

React is a front-end and open-source JavaScript library which is useful in developing user interfaces specifically for applications with a single page.

<br />

| 2.  | What are the advantages of using React? |
| --- | :-------------------------------------- |

- Uses JSX syntax
- Use of Virtual DOM instead of Real DOM to improve efficiency
- Reusable components
- Follows Unidirectional or one-way data flow or data binding
- Huge ecosystem of libraries to choose from

<br />

| 3.  | What are the limitations of React? |
| --- | :--------------------------------- |

- React is just a library, not a full-blown framework
- JSX Complexity
- SEO Limitations

<br />

| 4.  | What is JSX? |
| --- | :----------- |

JSX stands for JavaScript XML and It allows us to write HTML inside JavaScript.

In the example below, the text inside `<h1>` tag is returned as JavaScript function to the render function.

```jsx
export default function App() {
  return <h1 className="container">Hello, this is a JSX Code!</h1>;
}
```

If you don't use JSX syntax then the respective JavaScript code should be written as below,

```javascript
import { createElement } from "react";

export default function App() {
  return createElement(
    "h1",
    { className: "greeting" },
    "Hello, this is a JSX Code!"
  );
}
```

<br />

| 5.  | What are components and their type in React? |
| --- | :------------------------------------------- |

Components are independent and reusable bits of code. it's return HTML.
we mainly have two types of components:

- Functional Components
- Class Components

<br />

| 6.  | What are the differences between functional and class components? |
| --- | :---------------------------------------------------------------- |

|     | **Functional Components**                                                                 | **Class Components**                                                                               |
| --- | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| 1.  | Functional components are written as a JavaScript function.                               | Class components are written as a JavaScript class.                                                |
| 2.  | There is no render method used in functional components.                                  | It must have the render() method returning JSX                                                     |
| 3.  | known as Stateless components as they simply accept data and display.                     | known as Stateful components because they implement logic and state.                               |
| 4.  | React lifecycle methods (ex., componentDidMount) cannot be used in functional components. | React lifecycle methods can be used inside class components (ex., componentDidMount).              |
| 5.  | Functional components do not use `this` at all.                                           | Class components use the `this` keyword is used to refer to the current instance of the component. |

<br />

| 7.  | What is the virtual DOM? How does virtual DOM actually make things faster? |
| --- | :------------------------------------------------------------------------- |

- virtual DOM is a virtual representation of the DOM.
- Manipulating DOM is slow, but manipulating Virtual DOM is fast.
- Each time there is a change in the state of our application, the virtual DOM gets updated first instead of the real DOM.

The _Virtual DOM_ works in three simple steps.

1.  Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
    ![virtualDom1](images/virtualDom1.png)

2.  Then the difference between the previous DOM representation and the new one is calculated.
    ![virtualDom2](images/virtualDom2.png)

3.  Once the calculations are done, the real DOM will be updated with only the things that have actually changed.
    ![virtualDom3](images/virtualDom3.png)

**What is the difference between Shadow DOM and Virtual DOM?**
The Shadow DOM is a browser technology designed primarily for scoping variables and CSS in web components.
The Virtual DOM is a concept implemented by libraries in JavaScript on top of browser APIs.

<br />

| 8.  | How does virtual DOM actually make things faster? / How does react use the virtual DOM to render the UI? |
| --- | :------------------------------------------------------------------------------------------------------- |

When anything new is added to the application, a virtual DOM is created and it is represented as a tree. So, whenever there is a change in the state of any element, a new Virtual DOM tree is created. This new Virtual DOM tree is compared with the previous Virtual DOM tree and make a note of the changes. After this, it finds the best possible ways to make these changes to the real DOM. Now only the updated elements will get rendered on the page again.

<br />

| 9.  | Explain the lifecycle methods of React components? |
| --- | :------------------------------------------------- |

- `componentWillMount()` : Executed just before rendering takes place both on the client as well as server-side.
- `componentDidMount()` : Executed on the client side only after the first render.
- `componentWillReceiveProps()` : Invoked as soon as the props are received from the parent class and before another render is called.
- `shouldComponentUpdate()` : If you want your component to update, return true else return false. By default, it returns false.
- `componentWillUpdate()` : Called just before rendering takes place in the DOM.
- `componentDidUpdate()` : Called immediately after rendering takes place.
- `componentWillUnmount()` : Called after the component is unmounted from the DOM. It is used to clear up the memory spaces.

<br />

| 10. | What are the differences between controlled and uncontrolled components? |
| --- | :----------------------------------------------------------------------- |

|     | **Controlled Components**                                | **Uncontrolled Components**              |
| --- | -------------------------------------------------------- | ---------------------------------------- |
| 1.  | They do not maintain their own state.                    | They maintain their own state.           |
| 2.  | Controlled by the parent component.                      | Controlled by the DOM itself.            |
| 3.  | The component is under control of the component’s state. | Components are under the control of DOM. |

<br />

| 11. | What are Higher Order Components(HOC)? When do we need a Higher Order Component? |
| --- | :------------------------------------------------------------------------------- |

Higher-Order Component(HOC) is a function that takes in a component and returns a new component.

In larger React applications, to avoid redundancy and keep code DRY, we need an abstraction to share similar logic across components. Higher Order Components (HOCs) enable us to define this shared logic in one place and apply it to multiple components.

HOC can be used for many use cases:

1. Code reuse, logic and bootstrap abstraction.
2. Render hijacking.
3. State abstraction and manipulation.
4. Props manipulation.

<br />

| 12. | What are Hooks? Listout Hooks. |
| --- | :----------------------------- |

Hooks in React are special functions that allow you to use State and other React features, like lifecycle methods, in functional components. It is eliminating the need for class components.

1. `useState`

useState allows you to add state to functional components. It returns a state variable and a function to update it.

```javascript
const [count, setCount] = useState(0);
```

2. `useEffect`

useEffect lets you perform side effects in functional components, such as data fetching or subscriptions. It can run after every render, only once, or on specific state/prop changes.

```javascript
useEffect(() => {
  // side effect logic
}, [dependency]);
```

3. `useContext`

useContext provides a way to pass data through the component tree without manually passing props. It uses React’s Context API.

```javascript
const value = useContext(MyContext);
```

4. `useReducer`

The useReducer hook is a React hook used to manage complex state logic inside functional components. It is conceptually similar to Redux. i.e, Instead of directly updating state like with useState, you dispatch an action to a reducer function, and the reducer returns the new state.

The useReducer hook takes three arguments:

```javascript
const [state, dispatch] = useReducer(reducer, initialState, initFunction);
```
*   `**reducer**`: A function `(state, action) => newState` that handles how state should change based on the action.
*   `**initialState**`: The starting state.
*   `**dispatch**`: A function you call to trigger an update by passing an action.

The `useReducer` hook is used when:

*   The **state is complex**, such as nested structures or multiple related values.
*   State updates depend on the **previous state** and **logic**.
*   You want to **separate state update logic** from UI code to make it cleaner and testable.
*   You’re managing features like:
    *   Forms
    *   Wizards / Multi-step flows
    *   Undo/Redo functionality
    *   Shopping cart logic
    *   Toggle & conditional UI logic

```javascript
function reducer(state, action) {
  if (action.type === "incremented_age") {
    return {
      age: state.age + 1,
    };
  }
  throw Error("Unknown action.");
}
export default function Age() {
  const [state, dispatch] = useReducer(reducer, { age: 42 });

  function handleClick() {
    dispatch({ type: "incremented_age" });
    // ...
  }
}
```

5. `useCallback`

useCallback returns a memoized callback function, which is useful to prevent unnecessary re-renders when passing callbacks to optimized child components.

```javascript
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

6. `useMemo`

useMemo returns a memoized value, which optimizes performance by memoizing expensive calculations.

```javascript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

7. `useRef`

useRef provides a way to persist mutable values across renders and can be used to access DOM elements directly.

```javascript
const inputRef = useRef(null);
```

8. `Custom Hooks`

Custom Hooks are JavaScript functions starting with ‘use’ containing reusable logic.

```javascript

useFetch.js:

import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);

  return [data];
};

export default useFetch;

index.js

import ReactDOM from "react-dom/client";
import useFetch from "./useFetch";

const Home = () => {
  const [data] = useFetch("YOUR_API_URL");

  return (
    <>
      {data &&
        data.map((item) => {
          return <p key={item.id}>{item.title}</p>;
        })}
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Home />);
```

`RULES :`

1. It is allowed to call the Hooks only from the React Function Components.
2. React Hooks must be called only at the top level. It is not allowed to call them inside the nested functions, loops, or conditions.

 <br />

| 13. | What are Pure Components? |
| --- | :------------------------ |

Pure Components in React are components that only re-render when their props or state change, helping to optimize performance by avoiding unnecessary updates.

```javascript
import React, { PureComponent } from "react";

class MyPureComponent extends PureComponent {
  render() {
    console.log("Rendering MyPureComponent");
    return <div>{this.props.name}</div>;
  }
}

// Usage
class App extends React.Component {
  state = {
    name: "John",
  };

  render() {
    return (
      <div>
        <MyPureComponent name={this.state.name} />
        <button onClick={() => this.setState({ name: "John" })}>
          Update Name
        </button>
      </div>
    );
  }
}

export default App;

In this example, MyPureComponent only re-renders if the name prop changes. When clicking the "Update Name" button without changing the name value, MyPureComponent does not re-render, showcasing its optimization.
```

<br />

| 14. | What is state in React? |
| --- | :---------------------- |

State of a component is an object that holds some information that may change over the lifetime of the component. The important point is whenever the state object changes, the component re-renders. It is always recommended to make our state as simple as possible and minimize the number of stateful components.

```javascript
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "BMW",
      color: "Black",
    };
  }
  changeColor() {
    this.setState((prevState) => {
      return { color: "Red" };
    });
  }
  render() {
    return (
      <div>
        <button onClick={() => this.changeColor()}>Change Color</button>
        <p>{this.state.color}</p>
      </div>
    );
  }
}
```

> `Note` : State object is not available in functional components but, we can use React Hooks to add state to a functional component.

<br />

| 15. | What is props in React? |
| --- | :---------------------- |

Props are inputs to components. They are single values or objects containing a set of values that are passed to components on creation similar to HTML-tag attributes. Here, the data is passed down from a parent component to a child component.

```javascript
import React from "react";

const ChildComponent = (props) => {
  return (
    <div>
      <p>{props.name}</p>
      <p>{props.age}</p>
      <p>{props.gender}</p>
    </div>
  );
};

const ParentComponent = () => {
  return (
    <div>
      <ChildComponent name="John" age="30" gender="male" />
      <ChildComponent name="Mary" age="25" geneder="female" />
    </div>
  );
};
```

<br />

| 16. | What is the difference between state and props? |
| --- | :---------------------------------------------- |

|               | **state**                                                                | **props**                                                |
| ------------- | ------------------------------------------------------------------------ | -------------------------------------------------------- |
| Definition    | Managed within the component                                             | Passed to the component by its parent                    |
| Mutability    | Mutable (can be changed).                                                | Immutable (cannot be changed by the receiving component) |
| Usage         | For data that changes over time and affects rendering                    | For data that the component needs from its parent        |
| Setting Value | `useState` in functional components or this.setState in class components | Passed as attributes in JSX                              |
| Example       | `const [count, setCount] = useState(0);`                                 | `<ChildComponent count={this.state.count} /> `           |

<br />

| 17. | What is prop drilling in React? What is solution of it? |
| --- | :------------------------------------------------------ |

Sometimes, when developing React applications, you need to pass data from a top-level component to a deeply nested component.

The **disadvantage of prop drilling** is that intermediate components need to handle data they don't need, making the code messy and harder to manage.

```
App
 └── Parent (passes user)
      └── Child (passes user)
           └── Grandchild (uses user)
```

```javascript
function App() {
  const user = { name: "John" };
  return <Parent user={user} />;
}

function Parent({ user }) {
  return <Child user={user} />;
}

function Child({ user }) {
  return <Grandchild user={user} />;
}

function Grandchild({ user }) {
  return <div>{user.name}</div>;
}
```

`**Solution**`: Context API

Using the Context API, you can avoid passing props through every level. You can make the data available to any component in the tree.

```
App
 ├── UserContext.Provider (provides user)
 └── Parent
      └── Child
           └── Grandchild (uses user from context)
```

```javascript
import React, { createContext, useContext } from "react";

const UserContext = createContext();

function App() {
  const user = { name: "John" };
  return (
    <UserContext.Provider value={user}>
      <Parent />
    </UserContext.Provider>
  );
}

function Parent() {
  return <Child />;
}

function Child() {
  return <Grandchild />;
}

function Grandchild() {
  const user = useContext(UserContext);
  return <div>{user.name}</div>;
}
```

<br />

| 18. | What are synthetic events in React? |
| --- | :---------------------------------- |

SyntheticEvent is a cross-browser wrapper around the browser's native event.

```javascript
function BookStore() {
  function handleTitleChange(e) {
    console.log("The Book title is:", e.target.value);
    // 'e' represents synthetic event
    const nativeEvent = e.nativeEvent;
    console.log(nativeEvent);
    e.stopPropagation();
    e.preventDefault();
  }

  return <input name="title" onChange={handleTitleChange} />;
}
```

<br />

| 19. | What is "key" prop and what is the benefit of using it? |
| --- | :------------------------------------------------------ |

A `key` is a special attribute which helps React identify which items have changed, are added, or are removed.

When you have stable IDs for rendered items, you may use the item IDs:

```javascript
const todoItems = todos.map((todo) => <li key={todo.id}>{todo.text}</li>);
```

When you don't have stable IDs for rendered items, you may use the item index as a key as a last resort:

```javascript
const todoItems = todos.map((todo, index) => <li key={index}>{todo.text}</li>);
```

**Note**:

1. Using indexes for keys is **not recommended** if the order of items may change. This can negatively impact performance and may cause issues with component state.
2. There will be a warning message in the console if the key prop is not present on list items.
3. The key attribute accepts either string or number and internally convert it as string type.
4. Don't generate the key on the fly something like key={Math.random()}. Because the keys will never match up between re-renders and DOM created everytime.

<br />

| 20. | What are fragments? |
| --- | :------------------ |

Fragments let you group a list of children without adding extra nodes to the DOM. You need to use either or a shorter syntax having empty tag (<></>).

```javascript
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

<br />

| 21. | What are portals in React? |
| --- | :------------------------- |

Portals in React provide a way to render children into a DOM node that exists outside the hierarchy of the parent component. They are useful for scenarios like **modals, tooltips, or any overlay**

```javascript
ReactDOM.createPortal(child, container);
```

```javascript
App.js;

import PortalExample from "./PortalExample";

export default function App() {
  return (
    <>
      <div className="clipping-container">
        <NoPortalExample />
      </div>
      <div className="clipping-container">
        <PortalExample />
      </div>
    </>
  );
}

PortalExample.js

import { useState } from 'react';
import { createPortal } from 'react-dom';
import ModalContent from './ModalContent.js';

export default function PortalExample() {
  const [showModal, setShowModal] = useState(false);
  return (
    <>
      <button onClick={() => setShowModal(true)}>
        Show modal using a portal
      </button>
      {showModal && createPortal(
        <ModalContent onClose={() => setShowModal(false)} />,
        document.body
      )}
    </>
  );
}

ModalContent.js

export default function ModalContent({ onClose }) {
  return (
    <div className="modal">
      <div>I'm a modal dialog</div>
      <button onClick={onClose}>Close</button>
    </div>
  );
}
```

<br />

| 22. | What is Lifting State Up in React? |
| --- | :--------------------------------- |

When several components need to share the same changing data then it is recommended to lift the shared state up to their closest common ancestor.That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

<br />

| 23. | How to use innerHTML in React? |
| --- | :----------------------------- |

The `dangerouslySetInnerHTML` attribute is React's replacement for using `innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a `__html` object as key and HTML text as value.

```javascript
function createMarkup() {
  return { __html: "First &middot; Second" };
}

function MyComponent() {
  return <div dangerouslySetInnerHTML={createMarkup()} />;
}
```

<br />

| 24. | How you implement Server Side Rendering or SSR? |
| --- | :---------------------------------------------- |

React is already equipped to handle rendering on Node servers. A special version of the DOM renderer is available, which follows the same pattern as on the client side.

```javascript
import ReactDOMServer from "react-dom/server";
import App from "./App";

ReactDOMServer.renderToString(<App />);
```

<br />

| 25. | How do you memoize a component? |
| --- | :------------------------------ |

There are memoize libraries available which can be used on function components.

For example moize library can memoize the component in another component.

```javascript
import moize from "moize";
import Component from "./components/Component"; // this module exports a non-memoized component

const MemoizedFoo = moize.react(Component);

const Consumer = () => {
  <div>
    {"I will memoize the following entry:"}
    <MemoizedFoo />
  </div>;
};
```

Update: Since React v16.6.0, we have a React.memo. It provides a higher order component which memoizes component unless the props change. To use it, simply wrap the component using React.memo before you use it.

```javascript
const MemoComponent = React.memo(function MemoComponent(props) {
  /* render using props */
});
OR;
export default React.memo(MyFunctionComponent);
```

<br />

| 26. | What are React Mixins? |
| --- | :--------------------- |

Mixins are a way to totally separate components to have a common functionality. Mixins should not be used and can be replaced with higher-order components or decorators.

One of the most commonly used mixins is `PureRenderMixin`. You might be using it in some components to prevent unnecessary re-renders when the props and state are shallowly equal to the previous props and state:

```javascript
const PureRenderMixin = require("react-addons-pure-render-mixin");

const Button = React.createClass({
  mixins: [PureRenderMixin],
  // ...
});
```

<br />

| 27. | Why should component names start with capital letter? |
| --- | :---------------------------------------------------- |

If you are rendering your component using JSX, the name of that component has to begin with a capital letter otherwise React will throw an error as an unrecognized tag. This convention is because only HTML elements and SVG tags can begin with a lowercase letter.s

```javascript
function SomeComponent {
  // Code goes here
}
```

You can define function component whose name starts with lowercase letter, but when it's imported it should have a capital letter. Here lowercase is fine:

```javascript
function myComponent {
  render() {
    return <div />;
  }
}

export default myComponent;
```

While when imported in another file it should start with capital letter:

```javascript
import MyComponent from "./myComponent";
```

<br />

| 28. | Are custom DOM attributes supported in React v16? |
| --- | :------------------------------------------------ |

Yes. In the past, React used to ignore unknown DOM attributes. If you wrote JSX with an attribute that React doesn't recognize, React would just skip it.

For example, let's take a look at the below attribute:

```javascript
<div mycustomattribute={"something"} />
```

<br />

| 29. | How to loop inside JSX? |
| --- | :---------------------- |

You can simply use `Array.prototype.map` with ES6 arrow function syntax.

For example, the `items` array of objects is mapped into an array of components:

```javascript
<tbody>
  {items.map((item) => (
    <SomeComponent key={item.id} name={item.name} />
  ))}
</tbody>
```

But you can't iterate using for loop:

```javascript
<tbody>
  for (let i = 0; i < items.length; i++) {
    <SomeComponent key={items[i].id} name={items[i].name} />
  }
</tbody>
```

<br />

| 30. | How to loop inside JSX? |
| --- | :---------------------- |

```javascript
<div className="btn-panel {this.props.visible ? 'show' : 'hidden'}">
```

```javascript
<div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>
```

```javascript
<div className={`btn-panel ${this.props.visible ? 'show' : 'hidden'}`}>
```

<br />

| 31. | What is the difference between React and ReactDOM? |
| --- | :------------------------------------------------- |

The `react` package contains `React.createElement()`, `React.Component`, `React.Children`, and other helpers related to elements and component classes. You can think of these as `universal helpers` that you need to build components. The `react-dom` package contains `ReactDOM.render()`, and in `react-dom/server` we have server-side rendering support with `ReactDOMServer.renderToString()` and `ReactDOMServer.renderToStaticMarkup()`.

<br />

| 32. | How to focus an input element on page load? |
| --- | :------------------------------------------ |

```javascript
import React, { useEffect, useRef } from "react";

const App = () => {
  const inputElRef = useRef(null);

  useEffect(() => {
    inputElRef.current.focus();
  }, []);

  return (
    <div>
      <input defaultValue={"Won't focus"} />
      <input ref={inputElRef} defaultValue={"Will focus"} />
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById("app"));
```

For Class

```javascript
class App extends React.Component {
  componentDidMount() {
    this.nameInput.focus();
  }

  render() {
    return (
      <div>
        <input defaultValue={"Won't focus"} />
        <input
          ref={(input) => (this.nameInput = input)}
          defaultValue={"Will focus"}
        />
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById("app"));
```

<br />

| 33. | How can we find the version of React at runtime in the browser? |
| --- | :-------------------------------------------------------------- |

You can use `React.version` to get the version.

```javascript
const REACT_VERSION = React.version;

ReactDOM.render(
  <div>{`React version: ${REACT_VERSION}`}</div>,
  document.getElementById("app")
);
```

<br />

| 34. | How can we find the version of React at runtime in the browser? |
| --- | :-------------------------------------------------------------- |

Add a listener on the `history` object to record each page view:

```javascript
history.listen(function (location) {
  window.ga("set", "page", location.pathname + location.search);
  window.ga("send", "pageview", location.pathname + location.search);
});
```

## React Router

| 35. | What is React Router? |
| --- | :-------------------- |

React Router is a powerful routing library that helps you add new screens and flows to your application incredibly quickly, all while keeping the URL in sync with what's being displayed on the page.

<br />

| 36. | What are the <Router> components of React Router v6? |
| --- | :--------------------------------------------------- |

React Router v6 provides below 4 `<Router>` components:

1. <BrowserRouter>:Uses the HTML5 history API for standard web apps.
2. <HashRouter>:Uses hash-based routing for static servers.
3. <MemoryRouter>:Uses in-memory routing for testing and non-browser environments.
4. <StaticRouter>:Provides static routing for server-side rendering (SSR).

<br />

| 37. | What is the purpose of push() and replace() methods of history? |
| --- | :-------------------------------------------------------------- |

If you think of the history as an array of visited locations, push() will add a new location to the array and replace() will replace the current location in the array with the new one.

## React Redux

![Redux](images/redux.png)

| 38. | What is Redux? |
| --- | :------------- |

Redux is a state management library for JavaScript applications, commonly used with React but also compatible with other libraries

<br />

| 39. | What are Redux three core principles? |
| --- | :------------------------------------ |

1. **Single Source of Truth**: The state of the whole application is stored in a single object.
2. **State is Read-Only**: The only way to change the state is to emit an action, an object describing what happened.
3. **Changes are Made with Pure Functions**: Reducers are pure functions that return the next state based on the previous state and the action.

<br />

| 40. | How to access Redux store outside a component? |
| --- | :--------------------------------------------- |

```javascript
store = createStore(myReducer);
export default store;
```

<br />

| 41. | How to structure Redux top level directories? |
| --- | :-------------------------------------------- |

1. Components: Used for dumb components unaware of Redux.
2. Containers: Used for smart components connected to Redux.
3. Actions: Used for all action creators, where file names correspond to part of the app.
4. Reducers: Used for all reducers, where files name correspond to state key.
5. Store: Used for store initialization.

<br />

| 42. | What is redux-saga? |
| --- | :------------------ |

Redux-Saga is a middleware library for managing side effects in Redux applications. It uses generator functions to handle asynchronous operations, making it easier to manage complex workflows like data fetching and API calls in a more declarative and maintainable way.

<br />

| 43. | What is Redux Thunk? |
| --- | :------------------- |

Redux Thunk is a middleware for Redux that allows you to write action creators that return a function instead of an action. This function can perform asynchronous operations, like fetching data from an API, and dispatch actions based on the results of those operations.

<br />

| 44. | What are the differences between `redux-saga` and `redux-thunk`? |
| --- | :--------------------------------------------------------------- |

|     | **Redux Thunk**                                             | **Redux Saga**                                                       |
| --- | ----------------------------------------------------------- | -------------------------------------------------------------------- |
|     | Uses functions as action creators that return functions     | Uses generator functions for managing side effects                   |
|     | Suitable for simpler use cases and smaller applications     | Suitable for complex asynchronous flows, provides better scalability |
|     | May require more effort for testing due to nested functions | Easier testing due to the use of generator functions                 |

<br />

| 45. | What are the features of Redux DevTools? |
| --- | :--------------------------------------- |

1. Lets you inspect every state and action payload.
2. Lets you go back in time by cancelling actions.
3. If you change the reducer code, each staged action will be re-evaluated.
4. If the reducers throw, you will see during which action this happened, and what the error was.
5. With persistState() store enhancer, you can persist debug sessions across page reloads.

<br />

| 46. | What are Redux selectors and why use them? |
| --- | :----------------------------------------- |

Redux selectors are functions used to extract specific pieces of data from the Redux store state

<br />

| 47. | How to add multiple middlewares to Redux? |
| --- | :---------------------------------------- |

You can use `applyMiddleware()`.

For example, you can add `redux-thunk` and `logger` passing them as arguments to `applyMiddleware()`:

```javascript
import { createStore, applyMiddleware } from "redux";
const createStoreWithMiddleware = applyMiddleware(
  ReduxThunk,
  logger
)(createStore);
```

<br />

| 48. | How to set initial state in Redux? |
| --- | :--------------------------------- |

```javascript
const rootReducer = combineReducers({
  todos: todos,
  visibilityFilter: visibilityFilter,
});

const initialState = {
  todos: [{ id: 123, name: "example", completed: false }],
};

const store = createStore(rootReducer, initialState);
```

<br />

| 49. | What is an action in Redux? |
| --- | :-------------------------- |

Actions are plain JavaScript objects or payloads of information that send data from your application to your store.

<br />

| 50. | What is suspense component? |
| --- | :-------------------------- |

If the module containing the dynamic import is not yet loaded by the time parent component renders, you must show some fallback content while you’re waiting for it to load using a loading indicator. This can be done using Suspense component.

```javascript
const OtherComponent = React.lazy(() => import("./OtherComponent"));

function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <OtherComponent />
      </Suspense>
    </div>
  );
}
```

<br />

| 51. | Can you list down top websites or applications using react as front end framework? |
| --- | :--------------------------------------------------------------------------------- |

1. Facebook
2. Uber
3. Instagram
4. WhatsApp
5. Khan Academy
6. Airbnb
7. Dropbox
8. Flipboard
9. Netflix
10. PayPal

---

# Disclaimer

The questions provided in this repository are the summary of frequently asked questions across numerous companies.
-— do not get discouraged if you don't know the answer to all of them ⁠— that is ok!

Good luck with your interview 😊
