# React and Forms

## Controlled Components

*In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().*

**For example, if we want to make the previous example log the name when it is submitted, we can write the form as a controlled component:**

`class NameForm extends React.Component {`

  `constructor(props) {`

    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  `}`

  `handleChange(event) {`

    `this.setState({value: event.target.value});`

  `}`

  `handleSubmit(event) {`

    alert('A name was submitted: ' + this.state.value);

   `event.preventDefault();`

  `}`

  `render() {`

    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    
    `);
  `}`
`}`

### the text area tag

*In HTML, a `<textarea>` element defines its text by its children*


*In React, a `<textarea>` uses a value attribute instead. This way, a form using a `<textarea>` can be written very similarly to a form that uses a single-line input*

### the select tag

*In HTML, `<select>` creates a drop-down list. For example, this HTML creates a drop-down list of flavors*

*React, instead of using this selected attribute, uses a value attribute on the root select tag. This is more convenient in a controlled component because you only need to update it in one place.*

### The file input Tag

*In HTML, an `<input type="file">` lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript via the File API.*

*Because its value is read-only, it is an uncontrolled component in React. It is discussed together with other uncontrolled components later in the documentation.*

## The Conditional (Ternary) Operator

consider this code :

`if ( condition ) {`

  `value if true;`

`}` 

`else {`
  
  `value if false;`

`}`

using the Ternary Operator, the code will be refactores as :

`condition ? value if true : value if false`

**Here’s what you need to know:**

1. The condition is what you’re actually testing. The result of your condition should be true or false or at least coerce to either boolean value.
2. A ? separates our conditional from our true value. Anything between the ? and the : is what is executed if the condition evaluates to true.
3. Finally a : colon. If your condition evaluates to false, any code after the colon is executed.