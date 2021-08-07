# JavaScript
## Understanding Problem Domain
*why problem domains are hard?*

let's make a problem domain analogy with solving puzzles, normally when you put together a jigsaw puzzle you follow steps that might look something like this:
1. Figure out what the major components of the picture are
2. Sort the pieces by color or component
3. Put together all the border pieces
4. Put together each component of the picture from the piles you created

The big issue is that many problem domains are like a puzzle with a blurry picture or no picture at all.

**As programmers, we also are often not given complete information about the problem domain, so we don’t even have the information we need to understand it.**

**Just try and read the famous [Domain Driven Design  book ](https://www.grammarly.com/?utm_source=gdn&utm_medium=cpc&utm_campaign=F2&utm_phase=student&utm_content=bmd121)and you’ll quickly see how complicated and difficult problem domains can be.  (Great book by the way, although you may have to read it twice or three times—I certainly did.)**

*What can you do about it?*

If understanding the problem domain is the hardest part of programming and you want to make programming easier, you can do one of two things:

1. Make the problem domain easier
2. Get better at understanding the problem domain

What meant by this is that it is often beneficial to take a part of the problem and fully understand that part before expanding the problem domain.

## Objects

*In JavaScript, almost "everything" is an object.*

- Booleans can be objects (if defined with the new keyword)
- Numbers can be objects (if defined with the new keyword)
- Strings can be objects (if defined with the new keyword)
- Dates are always objects
- Maths are always objects
- Regular expressions are always objects
- Arrays are always objects
- Functions are always objects
- Objects are always objects

**All JavaScript values, except primitives, are objects.**

**JavaScript Primitives**

- A primitive value is a value that has no properties or methods.

- A primitive data type is data that has a primitive value.

**Objects are Variables**

JavaScript variables can contain single values:

for example
`let person = "John Doe";`

*A JavaScript object is a collection of named values*

**Object Properties**

*The named values, in JavaScript objects, are called properties.*

consider this example : `let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};`

| property   | value |
| ----------- | ----------- |
| firstName   | John        |
| secondName  | Doe         |
| age         | 50          |
| eyeColor    | blue        |


### Creating a JavaScript Object
*With JavaScript, you can define and create your own objects.*

There are different ways to create new objects:

- Create a single object, using an object literal.
- Create a single object, with the keyword new.
- Define an object constructor, and then create objects of the constructed type.
- Create an object using Object.create().

**Using an Object Literal**

- This is the easiest way to create a JavaScript Object.

- Using an object literal, you both define and create an object in one statement.

- An object literal is a list of name:value pairs (like age:50) inside curly braces {}.

yoy can access an object using dot notations or curly brackets.

## Document Object Model

*The Document Object Model (DOM) specifies
how browsers should create a model of an HTML
page and how JavaScript can access and update the
contents of a web page while it is in the browser window.*

**With the object model, JavaScript gets all the power it needs to create dynamic HTML:**

- JavaScript can change all the HTML elements in the page
- JavaScript can change all the HTML attributes in the page
- JavaScript can change all the CSS styles in the page
- JavaScript can remove existing HTML elements and attributes
- JavaScript can add new HTML elements and attributes
- JavaScript can react to all existing HTML events in the page
- JavaScript can create new HTML events in the page

*What is the HTML DOM?*

The HTML DOM is a standard object model and programming interface for HTML. It defines:

- The HTML elements as objects
- The properties of all HTML elements
- The methods to access all HTML elements
- The events for all HTML elements

### The DOM Programming Interface
*The HTML DOM can be accessed with JavaScript (and with other programming languages).*

- In the DOM, all HTML elements are defined as objects.

- The programming interface is the properties and methods of each object.

- A property is a value that you can get or set (like changing the content of an HTML element).

- A method is an action you can do (like add or deleting an HTML element).

The following example changes the content (the innerHTML) of the <p> element with id="demo":

`<html>`

`<body>`

`<p id="demo"></p>`

`<script>`

`document.getElementById("demo").innerHTML = "Hello World!";`

`</script>`

`</body>`

`</html>`

**The `getElementById` Method** 

- The most common way to access an HTML element is to use the id of the element.

- In the example above the getElementById method used id="demo" to find the element.

**The `innerHTML` Property**

- The easiest way to get the content of an element is by using the innerHTML property.

- The innerHTML property is useful for getting or replacing the content of HTML elements.



