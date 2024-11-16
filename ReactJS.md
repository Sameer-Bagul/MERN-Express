## ReactJS Course Notes

### Introduction
Welcome to the **ReactJS Section!** This page contains comprehensive notes and summaries from the ReactJS course, covering various topics and concepts essential for mastering ReactJS. Whether you are a beginner or an experienced developer, these notes will help you understand and implement ReactJS effectively in your projects. Explore the chapters to learn about React setup, components, JSX, state management, hooks, advanced React concepts, and much more. Happy learning!


<!-- !=============================================================================== -->


### Ch 1 - React Setup, React DOM, Project Structure

#### Why React?
- Suitable for both single-page and multi-page applications.

#### What is React?
- A component-based JavaScript library for building user interfaces.
- React is declarative, efficient, and flexible.

#### What are Components?
- Building blocks of any React application.
- Self-contained modules that render some output.
- Reusable and composable to form complex UIs.
- Can be nested within other components.

#### What is React DOM?
- A library used to render React components in the DOM.
- Manages updating the DOM to match React components.

#### React Project Structure
- `public` folder
    - Contains static assets and the main HTML file (`index.html`).
    - Includes `favicon.ico`, `manifest.json`.
- `src` folder
    - Contains the source code.
    - `index.js` renders the React application.
    - `App.js` is the root component.
    - `App.css` contains styles for `App`.
    - `logo.svg` is used in `App`.
- `node_modules` folder
    - Contains dependencies and packages.
- `package.json` file
    - Metadata and configuration for the project.
    - Includes project info, dependencies, scripts.
- `package-lock.json` file
    - Ensures consistent dependency versions.
- `README.md` file
    - Instructions on running and using the application.
- `.gitignore` file
    - Specifies files/directories to ignore in Git.
- `vite.config.js` file (if using Vite)
    - Configuration settings for Vite.

#### What is Node?
- An open-source, cross-platform, back-end JavaScript runtime environment.

#### What is NPM?
- A package manager for JavaScript, default for Node.js.

#### What is a Toolchain?
- A set of programming tools used together for software development.

#### Getting Started with React Project Setup
- Create a new React project using create-react-app:
    - `npx create-react-app my-app`
- Navigate into the project directory:
    - `cd my-app`
- Start the development server:
    - `npm start`

#### What is Vite?
- A build tool for faster and more efficient development.
- Leverages modern JavaScript features for speed.

#### React Setup with Vite
- Create a new React project using Vite:
    - `npm init @vitejs/app my-react-app --template react`
- Navigate into the project directory:
    - `cd my-react-app`
- Start the development server:
    - `npm run dev`

#### React DOM Root Element
- `const root = ReactDOM.createRoot(document.getElementById('root'));`
    - Creates a root element to render the React application.
    - Manages the React component tree.

<!-- !=============================================================================== -->
### Ch 2 - Component, Props, JSX

#### What is a Component?
- Self-contained module that renders output.
- Can be functional or class-based.
- Reusable and composable.
- Can have props and state.
- Supports lifecycle methods and event handlers.
- Can be styled and optimized for performance.

#### What are Props?
- Short for properties, used to pass data from parent to child components.
- Read-only and cannot be modified by child components.
- Passed as attributes in JSX.
- Can be of any data type.
- Used to customize behavior and appearance.
- Supports event handlers, callbacks, and dynamic data.
- Enables reusable and composable components.
- Can use default values, type checking, and destructuring.
- Supports children props for nested components.

**Example of Props**

```jsx
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
    const message = "Hello from Parent Component!";
    return (
        <div>
            <h1>Parent Component</h1>
            <ChildComponent message={message} />
        </div>
    );
}

export default ParentComponent;
```

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent({ message }) {
    return (
        <div>
            <h2>Child Component</h2>
            <p>{message}</p>
        </div>
    );
}

export default ChildComponent;
```

In this example:
- `ParentComponent` passes a `message` prop to `ChildComponent`.
- `ChildComponent` receives the `message` prop and displays it inside a paragraph element.

#### What is JSX?
- JSX stands for JavaScript XML.
- Allows writing HTML-like syntax in JavaScript.
- Transformed into JavaScript using Babel.
- Used to describe UI structure.
- Can contain JavaScript expressions inside `{}`.
- Supports attributes, event handlers, and nesting.

#### What is a Fragment?
- Allows grouping multiple elements without adding extra nodes to the DOM.
- Helps avoid unnecessary wrapper elements.
- Example usage: `<></>` or `<React.Fragment></React.Fragment>`.
- Can accept a `key` attribute when rendering lists of items.
- Improves performance by reducing the number of DOM nodes.

```jsx
return (
    <>
        <ChildComponent />
        <AnotherChildComponent />
    </>
);
```

<!-- !=============================================================================== -->

### Ch 3 - Conditional Rendering, Lists and Keys

#### Conditional Rendering
- Render different components or elements based on conditions.
- Use JavaScript conditional statements like `if`, `else`, and ternary operators.
- Common techniques:
    - Using `if` statements.
    - Using ternary operators.
    - Using logical `&&` operator.

**Example of Conditional Rendering**

```jsx
function Greeting({ isLoggedIn }) {
    if (isLoggedIn) {
        return <h1>Welcome back!</h1>;
    } else {
        return <h1>Please sign up.</h1>;
    }
}
```

```jsx
function App() {
    const isLoggedIn = true;
    return (
        <div>
            <Greeting isLoggedIn={isLoggedIn} />
        </div>
    );
}
```
#### Ternary Operators for Conditional Rendering
- Ternary operators provide a concise way to perform conditional rendering in React.
- Syntax: `condition ? trueExpression : falseExpression`
- Useful for inline conditional rendering within JSX.

**Example of Ternary Operator for Conditional Rendering**

```jsx
function UserGreeting({ isLoggedIn }) {
    return (
        <div>
            {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please sign up.</h1>}
        </div>
    );
}

function App() {
    const isLoggedIn = true;
    return (
        <div>
            <UserGreeting isLoggedIn={isLoggedIn} />
        </div>
    );
}
```

- In this example, the `UserGreeting` component uses a ternary operator to render different messages based on the `isLoggedIn` prop.
- If `isLoggedIn` is `true`, it displays "Welcome back!"; otherwise, it displays "Please sign up."
- Ternary operators help keep the code concise and readable.

#### Lists and Keys
- Use the `map()` function to iterate over an array and return a list of elements.
- Each element should have a unique `key` prop.

**Example of Mapping Array Data**

```jsx
function NumberList({ numbers }) {
    const listItems = numbers.map((number) =>
        <li key={number.toString()}>{number}</li>
    );
    return (
        <ul>{listItems}</ul>
    );
}
```

```jsx
function App() {
    const numbers = [1, 2, 3, 4, 5];
    return (
        <div>
            <NumberList numbers={numbers} />
        </div>
    );
}
```

#### Keys
- Help React identify which items in the list are changed, added, or removed.
- Should be given to elements inside the array for stable identity.
- Best to use a unique string identifier.

**Example of Using Keys**

```jsx
const todoItems = todos.map((todo) =>
    <li key={todo.id}>
        {todo.text}
    </li>
);
```

- Avoid using indexes as keys if the order of items may change.

#### Example of Conditional Rendering with Lists

```jsx
function TodoList({ todos }) {
    return (
        <ul>
            {todos.length > 0 ? (
                todos.map((todo) => <li key={todo.id}>{todo.text}</li>)
            ) : (
                <li>No todos left</li>
            )}
        </ul>
    );
}
```

```jsx
function App() {
    const todos = [
        { id: 1, text: 'Learn React' },
        { id: 2, text: 'Build a project' },
        { id: 3, text: 'Deploy the app' }
    ];
    return (
        <div>
            <TodoList todos={todos} />
        </div>
    );
}
```

- This example demonstrates how to conditionally render a list of todos or a message if there are no todos left.

<!-- !=============================================================================== -->

### Ch 4 - Events, Event Handler, Synthetic Event Object

#### What are Events?
- Actions that occur in the browser, such as clicks, keypresses, form submissions, and mouse movements.
- Events are used to trigger specific functionality in response to user interactions.

#### What is an Event Handler?
- A function that is executed in response to an event.
- Event handlers are used to define what should happen when an event occurs.
- Can be defined inline or as separate functions.

#### What is a Synthetic Event Object?
- A cross-browser wrapper around the native event.
- Provides consistent properties and methods across different browsers.
- Synthetic events are used by React to ensure compatibility and performance.

#### Handling Events in React
- Use camelCase event names like `onClick`, `onSubmit`, `onChange`.
- Pass event handlers as props to components.
- Access event properties like `target`, `value`, `checked`.

**Example of Handling Events**

```jsx
function Button() {
    function handleClick() {
        alert('Button clicked!');
    }

    return (
        <button onClick={handleClick}>Click me</button>
    );
}
```

#### Common Event Types and Handlers
- `onClick`: Triggered when an element is clicked.
- `onChange`: Triggered when the value of an input element changes.
- `onSubmit`: Triggered when a form is submitted.
- `onKeyPress`: Triggered when a key is pressed.
- `onMouseOver`: Triggered when the mouse pointer is over an element.
- `onFocus`: Triggered when an element gains focus.
- `onBlur`: Triggered when an element loses focus.

**Example of Multiple Event Handlers**

```jsx
function Form() {
    function handleSubmit(event) {
        event.preventDefault();
        alert('Form submitted!');
    }

    function handleChange(event) {
        console.log('Input value:', event.target.value);
    }

    return (
        <form onSubmit={handleSubmit}>
            <input type="text" onChange={handleChange} />
            <button type="submit">Submit</button>
        </form>
    );
}
```

#### Advanced Event Handling
- Use event delegation to handle events efficiently.
- Use `event.persist()` to retain the event object in asynchronous code.
- Combine multiple event handlers for complex interactions.

**Example of Advanced Event Handling**

```jsx
function App() {
    function handleClick(event) {
        console.log('Button clicked:', event.target);
    }

    function handleMouseOver(event) {
        console.log('Mouse over:', event.target);
    }

    return (
        <div>
            <button onClick={handleClick} onMouseOver={handleMouseOver}>
                Hover and Click me
            </button>
        </div>
    );
}
```

#### Synthetic Event Object Properties
- `event.target`: The element that triggered the event.
- `event.type`: The type of event (e.g., 'click', 'submit').
- `event.preventDefault()`: Prevents the default action of the event.
- `event.stopPropagation()`: Stops the event from propagating to parent elements.

**Example of Using Synthetic Event Object**

```jsx
function InputField() {
    function handleFocus(event) {
        console.log('Input focused:', event.target);
    }

    function handleBlur(event) {
        console.log('Input blurred:', event.target);
    }

    return (
        <input type="text" onFocus={handleFocus} onBlur={handleBlur} />
    );
}
```

#### Event Handling Best Practices
- Keep event handlers small and focused.
- Use descriptive names for event handler functions.
- Avoid inline event handlers for better readability and maintainability.
- Use `event.persist()` when working with asynchronous code to avoid losing the event object.

**Example of Best Practices**

```jsx
function App() {
    function handleButtonClick(event) {
        event.persist();
        setTimeout(() => {
            console.log('Button clicked:', event.target);
        }, 1000);
    }

    return (
        <div>
            <button onClick={handleButtonClick}>Click me</button>
        </div>
    );
}
```

- This example demonstrates how to persist the event object for use in asynchronous code.


<!-- !=============================================================================== -->
### Ch 5 - State, useState hook

#### What is State?
- State is a built-in object in React that allows components to store and manage data.
- State is mutable and can change over time, triggering re-renders of the component.
- Each component can have its own state, managed using the `useState` hook in functional components or `this.state` in class components.

**Example of State in a Functional Component**

```jsx
import React, { useState } from 'react';

function Counter() {
    const [count, setCount] = useState(0);

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
    );
}

export default Counter;
```

#### What are Hooks?
- Hooks are functions that let you use state and other React features in functional components.
- Introduced in React 16.8 to allow stateful logic in functional components.
- Common hooks include `useState`, `useEffect`, `useContext`, `useReducer`, and more.

**Example of Using Hooks**

```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
    const [seconds, setSeconds] = useState(0);

    useEffect(() => {
        const interval = setInterval(() => {
            setSeconds(prevSeconds => prevSeconds + 1);
        }, 1000);

        return () => clearInterval(interval);
    }, []);

    return <div>Seconds: {seconds}</div>;
}

export default Timer;
```

#### What is useState?
- `useState` is a hook that allows you to add state to functional components.
- It returns an array with two elements: the current state value and a function to update it.
- The initial state value is passed as an argument to `useState`.

**Example of useState Hook**

```jsx
import React, { useState } from 'react';

function Toggle() {
    const [isOn, setIsOn] = useState(false);

    return (
        <div>
            <p>{isOn ? 'ON' : 'OFF'}</p>
            <button onClick={() => setIsOn(!isOn)}>Toggle</button>
        </div>
    );
}

export default Toggle;
```

#### What is State Management?
- State management refers to the practice of managing the state of an application.
- In React, state management can be done using local component state, context API, or state management libraries like Redux, MobX, or Zustand.
- Effective state management ensures that the application state is predictable, maintainable, and scalable.

**Example of State Management with Context API**

```jsx
import React, { createContext, useState, useContext } from 'react';

const ThemeContext = createContext();

function ThemeProvider({ children }) {
    const [theme, setTheme] = useState('light');

    return (
        <ThemeContext.Provider value={{ theme, setTheme }}>
            {children}
        </ThemeContext.Provider>
    );
}

function ThemedComponent() {
    const { theme, setTheme } = useContext(ThemeContext);

    return (
        <div style={{ background: theme === 'light' ? '#fff' : '#333', color: theme === 'light' ? '#000' : '#fff' }}>
            <p>Current Theme: {theme}</p>
            <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>Toggle Theme</button>
        </div>
    );
}

function App() {
    return (
        <ThemeProvider>
            <ThemedComponent />
        </ThemeProvider>
    );
}

export default App;
```



<!-- !=============================================================================== -->
### Ch 6 - Forms, Event Objects, lifting state up
- Notes:

<!-- !=============================================================================== -->
### Ch 7 - CRUD operations, useEffect hook
- Notes:

<!-- !=============================================================================== -->
### Ch 8 - useReducers for State management
- Notes:

<!-- !=============================================================================== -->

### Ch 9 - Context API, useContext hook
- Notes:
<!-- !=============================================================================== -->

### Ch 10 - Context API with useReducers, Custom hooks
- Notes:

<!-- !=============================================================================== -->
### Ch 11 - useRef hook

- Notes:

<!-- !=============================================================================== -->### Ch 12 - useEffect hook detailed, API calls

### Ch 12 - useEffect hook detailed, API calls
- Notes:


<!-- !=============================================================================== -->### Ch 12 - useEffect hook detailed, API calls

### Ch 13 - useMemo, useCallback, memo
- Notes:
<!-- !=============================================================================== -->### Ch 12 - useEffect hook detailed, API calls

### Ch 14 - Advanced React 1 - forwardRef, useDeferred, useTransition etc
- Notes:
<!-- !=============================================================================== -->### Ch 12 - useEffect hook detailed, API calls

### Ch 15 - Advanced React 2 - Lazy loading, flushSync, createPortal etc
- Notes:
<!-- !=============================================================================== -->### Ch 12 - useEffect hook detailed, API calls
