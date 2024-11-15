## ReactJS Course Notes

### Introduction
Welcome to the **React.Js Section !** This page contains comprehensive notes and summaries from the ReactJS course, covering various topics and concepts essential for mastering ReactJS. Whether you are a beginner or an experienced developer, these notes will help you understand and implement ReactJS effectively in your projects. Explore the chapters to learn about React setup, components, JSX, state management, hooks, advanced React concepts, and much more. Happy learning!

### Ch 1 - React Setup, React DOM, Project Structure

### Why React?
- Single page applications as well as multi-page applications

### What is React?
- A component-based JavaScript library for building user interfaces
- React is a declarative, efficient, and flexible JavaScript library for building user interfaces

### What are Components?
- Components are the building blocks of any React application, and a single app usually consists of multiple components
- A component is a self-contained module that renders some output
- Components can be reused and composed together to form complex UIs
- Components can be a set of nested components

### What is React DOM?
- React DOM is a library that is used to render React components in the DOM
- React DOM takes care of updating the DOM to match the React components

### React Project Structure
- `public` folder
    - Contains the static assets and HTML file for the React application
    - `index.html` is the main HTML file that serves as the entry point for the React application
    - `favicon.ico` is the icon that appears in the browser tab for the React application
    - `manifest.json` is a metadata file that provides information about the React application
- `src` folder
    - Contains the source code for the React application
    - `index.js` is the main JavaScript file that renders the React application in the DOM
    - `App.js` is the main component of the React application that serves as the root component
    - `App.css` contains the styles for the `App` component
    - `logo.svg` is an SVG image that is used in the `App` component
- `node_modules` folder
    - Contains the dependencies and packages installed for the React application
- `package.json` file
    - Contains the metadata and configuration for the React application
    - Includes information about the project, dependencies, scripts, and other settings
- `package-lock.json` file
    - Contains the exact version of the dependencies installed for the React application
    - Ensures that the same versions of dependencies are installed across different environments
- `README.md` file
    - Contains information about the React application, including instructions on how to run and use the application
- `.gitignore` file
    - Specifies the files and directories that should be ignored by Git when tracking changes in the project
    - Helps to keep the repository clean and avoid committing unnecessary files
- `vite.config.js` file (if using Vite)
    - Contains the configuration settings for the Vite build tool
    - Allows customization of the build process, configuration of plugins, and setting other options for the project

### What is Node?
- Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine and executes JavaScript code outside a web browser

### What is NPM?
- npm is a package manager for the JavaScript programming language
- It is the default package manager for the JavaScript runtime environment Node.js

### What is a Toolchain?
- A toolchain is a set of programming tools that are used together to perform a complex software development task or to create a software product

### Getting Started with React Project Setup
- Create a new React project using create-react-app
    - `npx create-react-app my-app`
    - This command creates a new directory called `my-app` with a default React project structure
- Navigate into the project directory
    - `cd my-app`
    - This command changes the current working directory to the newly created project directory
- Start the development server
    - `npm start`
    - This command starts the development server and opens the default React application in your web browser. The application will automatically reload if you make changes to the code

### What is Vite?
- Vite is a build tool that aims to provide a faster and more efficient development experience for modern web projects
- Vite focuses on speed and simplicity, leveraging modern JavaScript features like ES modules and native ESM imports to provide a faster development experience

### React Setup with Vite
- Create a new React project using Vite
    - `npm init @vitejs/app my-react-app --template react`
    - This command creates a new directory called `my-react-app` with a default React project structure using Vite
- Navigate into the project directory
    - `cd my-react-app`
    - This command changes the current working directory to the newly created project directory
- Start the development server
    - `npm run dev`
    - This command starts the development server and opens the default React application in your web browser. The application will automatically reload if you make changes to the code

### React DOM Root Element
- `const root = ReactDOM.createRoot(document.getElementById('root'));`
    - This line of code creates a root element to render the React application
    - `ReactDOM.createRoot` is used to create a root container for the React application
    - `document.getElementById('root')` selects the DOM element with the id `root` where the React application will be rendered
    - This root element is where the React component tree will be mounted and managed by React DOM
    - React DOM efficiently updates and synchronizes the real DOM with the virtual DOM created by React components


### Ch 2 - Component, Props, JSX

- what is JSX ? 
    - JSX stands for JavaScript XML.
    - JSX allows you to write HTML elements and components in a syntax that looks similar to HTML.
    - JSX is not a separate templating language, but it is a syntax extension of JavaScript.
    - JSX produces React elements that can be rendered in the DOM.
    - JSX is used to describe what the UI should look like.
    - JSX is transformed into JavaScript using a transpiler like Babel before it is rendered in the browser.
    - JSX elements are treated as JavaScript expressions and can be used in the same way as other JavaScript expressions.
    - JSX elements can contain JavaScript expressions inside curly braces `{}`.
    - JSX elements can be nested and composed together to form complex UIs.
    - JSX elements can have attributes and event handlers similar to HTML elements.
    - JSX elements can be self-closing or have children elements.
    - JSX elements can be used in React components to define the UI structure.
    - JSX elements can be used in conditional rendering, loops, and other JavaScript constructs.
    - JSX elements can be used with React components to create reusable and composable UI components.
    - JSX elements can be used with React hooks and state to create interactive and dynamic UIs.
### Ch 3 - Conditional rendering, maps
- Notes:

### Ch 4 - Events, Event handler, Synthetic Event Object
- Notes:

### Ch 5 - State, useState hook
- Notes:

### Ch 6 - Forms, Event Objects, lifting state up
- Notes:

### Ch 7 - CRUD operations, useEffect hook
- Notes:

### Ch 8 - useReducers for State management
- Notes:

### Ch 9 - Context API, useContext hook
- Notes:

### Ch 10 - Context API with useReducers, Custom hooks
- Notes:

### Ch 11 - useRef hook
- Notes:

### Ch 12 - useEffect hook detailed, API calls
- Notes:

### Ch 13 - useMemo, useCallback, memo
- Notes:

### Ch 14 - Advanced React 1 - forwardRef, useDeferred, useTransition etc
- Notes:

### Ch 15 - Advanced React 2 - Lazy loading, flushSync, createPortal etc
- Notes: