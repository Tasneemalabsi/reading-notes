# React
## what is React ?
*React is a declarative, efficient, and flexible JavaScript library for building user interfaces. It lets you compose complex UIs from small and isolated pieces of code called “components”.*

**The smallest React example looks like this:**

`ReactDOM.render(`

  `<h1>Hello, world!</h1>,`

  `document.getElementById('root')`

`);`

## Introducing JSX
`const element = <h1>Hello, world!</h1>;`

the expression above is not considered string nor html element, it's called **JSX** 

**JSX  is a syntax extension to JavaScript.It also produces React “elements”.**

### Why JSX ?
*Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both. We will come back to components in a further section, but if you’re not yet comfortable putting markup in JS, this talk might convince you otherwise.*

### Embedding Expressions in JSX
`const name = 'Josh Perez';`

`const element = <h1>Hello, {name}</h1>;`

`ReactDOM.render(`
  
  `element,`

  `document.getElementById('root')`

`);`

**You can put any valid JavaScript expression inside the curly braces in JSX. For example, 2 + 2, user.firstName, or formatName(user) are all valid JavaScript expressions.**

### Specifying Attributes with JSX

*You may use quotes to specify string literals as attributes:*

`const element = <div tabIndex="0"></div>;`

*You may also use curly braces to embed a JavaScript expression in an attribute:*

`const element = <img src={user.avatarUrl}></img>;`

**NOTE:Since JSX is closer to JavaScript than to HTML, React DOM uses camelCase property naming convention instead of HTML attribute names.**

**For example, class becomes className in JSX, and tabindex becomes tabIndex.**


## Rendering Elements

*Elements are the smallest building blocks of React apps.*

### Rendering an Element into the DOM

Let’s say there is a <div> somewhere in your HTML file:

`<div id="root"></div>`

**We call this a “root” DOM node because everything inside it will be managed by React DOM.**

*To render a React element into a root DOM node, pass both to ReactDOM.render():*

`const element = <h1>Hello, world</h1>;`

`ReactDOM.render(element, document.getElementById('root'));`

### Updating the Rendered Element
*React elements are immutable. Once you create an element, you can’t change its children or attributes.*

**Example**

`function tick() {`

  `const element = (`

    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  
  `);`

  `ReactDOM.render(element, document.getElementById('root'));`

`}`

`setInterval(tick, 1000);`

**It calls ReactDOM.render() every second from a setInterval() callback.**

## Function and Class Components

consider the following function :

`function Welcome(props) {`

  `return <h1>Hello, {props.name}</h1>;`

`}`

*This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.*

you can refactor the functions to classes like : 

`class Welcome extends React.Component {`

  `render() {`

    `return <h1>Hello, {this.props.name}</h1>;`

  `}`

`}`

### Composing components

*Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail.*

For example:

`function Welcome(props) {`

  `return <h1>Hello, {props.name}</h1>;`

`}`

`function App() {`

  `return (`

    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  `);`

`}`

`ReactDOM.render(`

  `<App />,`

  `document.getElementById('root')`

`);`

### Extracting components:

consider this Comment component:

![component](img/component.png)

*It accepts author (an object), text (a string), and date (a date) as props, and describes a comment on a social media website.*

*This component can be tricky to change because of all the nesting, and it is also hard to reuse individual parts of it.*



