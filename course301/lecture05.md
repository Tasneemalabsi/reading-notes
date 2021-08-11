# React 

*React is the premier way to build big, fast Web apps with JavaScript.*

** the process of building a searchable product data table using React:**

## Start With A Mock
*Imagine that we already have a JSON API and a mock from our designer. The mock looks like this:*

![mock](https://reactjs.org/static/1071fbcc9eed01fddc115b41e193ec11/d4770/thinking-in-react-mock.png)

Our JSON API returns some data that looks like this:

`[
  {category: "Sporting Goods", price: "$49.99", stocked: true, name: "Football"},
  {category: "Sporting Goods", price: "$9.99", stocked: true, name: "Baseball"},
  {category: "Sporting Goods", price: "$29.99", stocked: false, name: "Basketball"},
  {category: "Electronics", price: "$99.99", stocked: true, name: "iPod Touch"},
  {category: "Electronics", price: "$399.99", stocked: false, name: "iPhone 5"},
  {category: "Electronics", price: "$199.99", stocked: true, name: "Nexus 7"}
];`

### Step 1: Break The UI Into A Component Hierarchy

*The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names.*

### Step 2: Build A Static Version in React

*Now that you have your component hierarchy, it’s time to implement your app. The easiest way is to build a version that takes your data model and renders the UI but has no interactivity. *

### Step 3: Identify The Minimal (but complete) Representation Of UI State
*To make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with state.*

*To build your app correctly, you first need to think of the minimal set of mutable state that your app needs.*

### Step 4: Identify Where Your State Should Live
*React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. This is often the most challenging part for newcomers to understand, so follow these steps to figure it out:*

**For each piece of state in your application:**

- Identify every component that renders something based on that state.
- Find a common owner component (a single component above all the components that need the state in the hierarchy).
- Either the common owner or another component higher up in the hierarchy should own the state.
- If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

### Step 5: Add Inverse Data Flow

*So far, we’ve built an app that renders correctly as a function of props and state flowing down the hierarchy. Now it’s time to support data flowing the other way: the form components deep in the hierarchy need to update the state in **FilterableProductTable**.*
