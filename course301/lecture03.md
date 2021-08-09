# Passing Functions as Props

## Lists and Keys

### Basic List Component

**Usually you would render lists inside a component.**

example of rendering lists inside react component: 

`function NumberList(props) {`

  `const numbers = props.numbers;`

  `const listItems = numbers.map((number) =>`

    `<li>{number}</li>`

  `);`

  `return (`

    `<ul>{listItems}</ul>`

  `);`

`}`

`const numbers = [1, 2, 3, 4, 5];`

`ReactDOM.render(`

  `<NumberList numbers={numbers} />,`

  `document.getElementById('root')`

`);`

Let’s assign a key to our list items inside numbers.map() and fix the missing key issue.

`function NumberList(props) {`

  `const numbers = props.numbers;`

  `const listItems = numbers.map((number) =>`

    <li key={number.toString()}>
      {number}
    </li>
  `);`

  `return (`

    <ul>{listItems}</ul>
  `);`

`}`

`const numbers = [1, 2, 3, 4, 5];`

`ReactDOM.render(`

  `<NumberList numbers={numbers} />,`

  `document.getElementById('root')`

`);`

### Keys

*Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:*

`const numbers = [1, 2, 3, 4, 5];`

`const listItems = numbers.map((number) =>`

  `<li key={number.toString()}>`

    {number}
  `</li>`

`);`

#### Extracting Components with Keys

*Keys only make sense in the context of the surrounding array.*

*For example, if you extract a ListItem component, you should keep the key on the `<ListItem />` elements in the array rather than on the `<li>` element in the ListItem itself.*

### Embedding map() in JSX

`function NumberList(props) {`

  `const numbers = props.numbers;`

  `const listItems = numbers.map((number) =>`

    <ListItem key={number.toString()}
              value={number} />
  `);`

  `return (`

    <ul>
      {listItems}
    </ul>
  `);`

`}`

## Spread Operators

*The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.*

### What is the spread operator?

*spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.*

### What can … do?

*The … spread operator is useful for many different routine tasks in JavaScript, including the following:*

- Copying an array
- Concatenating or combining arrays
- Using Math functions
- Using an array as arguments
- Adding an item to a list
- Adding to state in React
- Combining objects
- Converting NodeList to an array

### Examples of using …

`[...["😋😛😜🤪😝"]] // Array [ "😋😛😜🤪😝" ]`

`[..."🙂🙃😉😊😇🥰😍🤩!"] // Array(9) [ "🙂", "🙃", "😉", "😊", "😇", "🥰", "😍", "🤩", "!" ]`

`const hello = {hello: "😋😛😜🤪😝"}`

`const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}`

`const helloWorld = {...hello,...world}`

`console.log(helloWorld) // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" }`
