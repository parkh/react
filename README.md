# React

React is a test project to learn... yeah, the basics of [ReactJS](https://facebook.github.io/react/).
Why? Because I need it for my work. And also it is a great piece of technology.

So, let's go!

## What is ReactJS?

- Open sourse projected, maintained by Facebook
- Can be the "V" in MVC
- Narrow in scope, tightly focused
- Ideal for large-scale, single page application (SPA)
- Uses high-speed virtual DOM
- Uses clean and easy-to-understand JSX syntax

## Why is ReactJS so fast?

- JS objects are faster than DOM objects
- The ReactJS virtual DOM is a JS object
- ReactJS never reads from the “real” DOM
- ReactJS **only writes** to the real DOM if needed
- ReactJS efficiently handles DOM updates

## JSX (JavaScript as XML)

- is optional, XML-styled syntax for use in JS
- is **NOT HTML**, it's **XML**
- transpiled to plain JS by [Babel](https://babeljs.io)
- lower-case for HTML tags, CapitalCase for ReactJS Components, camelCase for HTML attributes
- avoids JS keywords like `class`, uses `className` instead
- style is a JSON object
- transpilers: [HTML->JSX](https://facebook.github.io/react/html-jsx.html), [JSX->JS](http://babeljs.io/repl/)

## Rendering

- Combining data and code to produce HTML, CSS and JS
- **Server-side** = producing complete and parsable HTML, CSS and JS on the server and sending results to the client
- **Client-side** = leaving some of the rendering work to be performed on the client
- `React.render()` renders an element to the DOM. Takes 3 arguments:
  - `ReactElement` - the element to render (simple HTML element)
  - `DOMElement` - the target DOM element to render into
  - `Callback` - an optional callback function

## ReactJS Component 

- Returns ReactElement(s) via `render` method
- Complex and reusable, empower *declarative*, as opposed to *imperative* programming
- Take advantage of JS with **Props**, **State** and **Events**

### Props

- Collection of values associated with a component
- Accessible via `this.props`
- Allows for dynamic rendering of data when re-using components
- Are **IMMUTABLE**, never write to `this.props`

### State

- Is optional
- Representing mutable :) properties that affect final rendered output
- `getInitialState` - set the initial values of component's state
- `setState` - update the state, informing ReactJS to render to the virtual DOM

### Props vs State

|                     --                     |props|state|
|:-------------------------------------------|:---:|:---:|
|Can get initial value from parent Component?|  +  |  +  |
|Can be changed by parent Component?         |  +  |  -  |
|Can set default values inside Component?    |  +  |  +  |
|Can change inside Component?                |  -  |  +  |
|Can set initial value for child Components? |  +  |  +  |
|Can change in child Components?             |  +  |  -  |

### Events

- Simple JSON objects
- Triggering the State change
- Uniform across browsers and consistent with [W3C Spec](https://www.w3.org/TR/DOM-Level-3-Events/), thanks to SyntheticEvent (wrapper for browser's event object passed into event function)
