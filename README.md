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

## Component Lifecycle

Lifecycle methods firing top down before render and bottom up after.

- Mounting
  - `componentWillMount`
    - invoked once, both on the client and server
    - immediatly before rendering
    - `this.setState()` not triggering additional render
  - `componentDidMount`
    - invoked once, only on the client
    - immediatly after rendering
    - integrating with other JS frameworks, setting timers using `setTimeout` or `setInterval`, or sending AJAX requests meant to be done here
- Updating
  - `componentWillReceiveProps` _(nextProps)_
    - invoked every time when a component is receiving new props
    - is not called for the initial render
    - an opportunity to react to a prop transition before `render()` is called by updating the state using `this.setState()`
    - `this.props` - old props
    - `this.setState()` not triggering additional render
  - `shouldComponentUpdate` _(nextProps, nextState)_
    - be default always returns `true`
    - returning `false` will skip the render
    - used to speed up the app
  - `componentWillUpdate` _(nextProps, nextState)_
    - invoked immediately before rendering when new props or state are being received
    - is not called for the initial render
    - an opportunity to perform preparation before an update occurs
    - `this.setState()` cannot be used here
  - `componentDidUpdate` _(nextProps, nextState)_
    - invoked immediately after the component's updates are flushed to the DOM
    - is not called for the initial render
    - an opportunity to operate on the DOM when the component has been updated
  - `componentWillUnmount`
    - invoked immediately before a component is unmounted from the DOM
    - any necessary cleanup in this method, such as invalidating timers or cleaning up any DOM elements that were created in `componentDidMount` meant to be done here
