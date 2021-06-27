# HTML and JavaScript
## Tables in HTML
### how to create a table in HTML ?
- The `<table>` tag defines an HTML table.

- Each table row is defined with a `<tr>` tag. Each table header is defined with a `<th>` tag. Each table data/cell is defined with a `<td>` tag.

- By default, the text in `<th>` elements are bold and centered.

- By default, the text in `<td>` elements are regular and left-aligned.

for example :
 `<table>`

  `<tr>`
    
    `<th>`  Firstname `</th>`

    `<th>`Lastname`</th>`

    `<th>Age</th>`

  `</tr>`

  `<tr>`

    `<td>Jill</td>`

    `<td>Smith</td>`

    `<td>50</td>`

  `</tr>`
  
  **the output will be:**
   <table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
</table> 

- To add a border to a table, use the CSS border property, for example:

`table, th, td {`
  
  `border: 1px solid black;`

`}`
  
- To make a cell span more than one column, use the colspan attribute, for example:

`<th colspan="2">Telephone</th>`

- To make a cell span more than one row, use the rowspan attribute:

`<th rowspan="2">Telephone:</th>`

- For long tables you can split the table into a X`<thead>`, `<tbody>`, and `<tfoot>`.

## Objects in JavaScript
*How to create an object in JavaScript ?*

You define (and create) a JavaScript object with an object literal,for example:

`const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};`

### Object Types (Blueprints) (Classes)

The previous examples is limited. it only creates single objects.

- Sometimes we need a "blueprint" for creating many objects of the same "type".

- The way to create an "object type", is to use an object constructor function.

- In the example below, function Person() is an object constructor function.

`function Person(first, last, age, eye) {`

  `this.firstName = first;`

  `this.lastName = last;`

  `this.age = age;`

  `this.eyeColor = eye;`

`}`

- Objects of the same type are created by calling the constructor function with the new keyword:

`const myFather = new Person("John", "Doe", 50, "blue");`

`const myMother = new Person("Sally", "Rally", 48, "green");`

**Adding a Property to an Object**

Adding a new property to an existing object is easy: 

`myFather.nationality = "English";`

**The this Keyword**

- In JavaScript, the thing called this is the object that "owns" the code.

- The value of this, when used in an object, is the object itself.

- In a constructor function this does not have a value. It is a substitute for the new object. The value of this will become the new object when a new object is created.

**Arrays can be objects**

*arrays are special type of objects, they hold a special set of property-value pair.

**Arrays of objects**

we can create arrays of objects easily, for example:

`let cars = [`

  `{`
    "color": "purple",`
    
    `"type": "minivan",`

    `"registration": new Date('2017-01-03'),`

    `"capacity": 7`
  },`

  `{`
    "color": "red",`

    `"type": "station wagon",`

    `"registration": new Date('2018-03-03'),`

   `"capacity": 5`
  `},`
  
  Arrays of objects don't stay the same all the time. We almost always need to manipulate them. So let's take a look at how we can add objects to an already existing array.

  **Built in objects in JavaScript**

  ![objects](https://lh3.googleusercontent.com/proxy/dpXUV6G3EDkprvLDSJlmoccET8QWf1L2mAfrSSV45NL9whyAcq8mYA5dw3zQRewF58W7qC79a1B-1BcT70L0_bzb-KxVB9k9LTSp4FGbfz9ouBcjOmed6xphuCw)

  ### Window Object
  - The window object represents an open window in a browser.

- If a document contain frames (`<iframe>`  tags), the browser creates one window object for the HTML document, and one additional window object for each frame.

- Note: There is no public standard that applies to the Window object, but all major browsers support it.

the following image shows some of window object properties:

![window](https://i.imgur.com/0SlQsZz.png)

### Domain Modeling
*domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.*

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

**Model epic fails videos**

- Imagine you've been tasked to build a program that models the popularity of epic fail videos. After months of painstaking research, you've determined that the two essential metrics for gauging popularity are an epic rating and whether or not the video has animals.

- Since you'll be modeling the popularity of many types of videos—parkour epic fails, corgi epic fails, etc.—you'll want to build self-contained objects with the same attributes and behaviors. That way, when you need to change the algorithm for determining popularity, the changes will be small and targeted.

- As you read this article, type out and run all code samples you come across. Do not copy and paste. Writing out and testing your code will help you remember how to implement domain models in JavaScript later.














