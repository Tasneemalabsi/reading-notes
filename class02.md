# HTML, CSS and JavaScript
## Text in HTML
- there are six headings in HTML, starting with h1 which is the main heading of the page that can only be used one time, then h2, h3, h4, h5 and h6 which are the sub headings from the most to the least important that can be used more than one time in the same page. the tags structure is as the following:

`<h1>This is a Main Heading</h1>`

`<h2>This is a Level 2 Heading</h2>`

`<h3>This is a Level 3 Heading</h3>`

`<h4>This is a Level 4 Heading</h4>`

`<h5>This is a Level 5 Heading</h5>`

`<h6>This is a Level 6 Heading</h6> `
- Paragraphs are written in HTML by using the `<p>` tag and by default, a browser will show
each paragraph on a new line, the structure is as the following:    `<p>text</p>`
- to make the text bold in HTML you can use: `<p>This is how we make a word appear <b>`bold.`</b>`
 `</p>`
 
 and to make italic you can use: `<p>This is how we make a word appear <i>italic</i>.
 `</p>`

 - As you have already seen, the browser will automatically show each new paragraph or heading on a new line. But if you wanted to add a line break inside the middle of a paragraph you can use the line break tag `<br />` **note that break is a self closing tag that there is no opening and closing tag breaks**
- To create a break between
themes — such as a change of
topic in a book or a new scene
in a play — you can add a
horizontal rule between sections
using the `<hr />` tag.
- in HTML there are what's called strong tags which shows that this text is important, by default the result will be a bold text: 
`<p><strong>Beware:</strong> Pickpockets operate in
 this area.</p>`
- there is also the emphasis tag which indicates
emphasis that subtly changes
the meaning of a sentence. by default the result will be italic :
`<p>I <em>think</em> Ivy was the first.</p>
`
- If you use an abbreviation or
an acronym, then the `<abbr>`
element can be used. A title
attribute on the opening tag is
used to specify the full term:
`<p><abbr title="Professor">Prof</abbr> Stephen
 Hawking is a theoretical physicist and
 cosmologist.</p>`
 - When you are referencing a
piece of work such as a book,
film or research paper, the
`<cite>` element can be used
to indicate where the citation is
from, example:

`<p><cite>A Brief History of Time</cite> by Stephen
 Hawking has sold over ten million copies
 worldwide.</p>`
  - The` <ins>` element can be used
to show content that has been
inserted into a document, while
the `<del>` element can show text
that has been deleted from it. example :

`<p>It was the <del>worst</del> <ins>best</ins> idea
 she had ever had.</p>`
 the results will be : <p>It was the <del>worst</del> <ins>best</ins> idea
 she had ever had.</p>

 - The` <s>` element indicates
something that is no longer
accurate or relevant (but that
should not be deleted). Example:

`<p>Laptop computer:</p>`

`<p><s>Was $995</s></p>`

`<p>Now only $375</p>`

the results will be 
<p>Laptop computer:</p>
<p><s>Was $995</s></p>
<p>Now only $375</p>

## Introducing CSS 
 *HTML is only to build the structure of the page, it has nothing to do with adding styles to it, if you want to style your web page, you have to link it to CSS.*

 **The key to understanding how CSS works is to
imagine that there is an invisible box around
every HTML element.**

*CSS works by associating rules with HTML elements. These rules govern
how the content of specified elements should be displayed. A CSS rule
contains two parts: a selector and a declaration. so as the following:*

![css](https://miro.medium.com/max/1274/1*3KzGtKSCCfYAc-Qc45AvAQ.png)

*CSS declarations sit inside curly brackets and each is made up of two
parts: a property and a value, separated by a colon. You can specify
several properties in one declaration, each separated by a semi-colon. in the previous example, the property was font-family and the value was Arial.*

### CSS in HTML 
there are 3 ways to link a CSS file to an HTML file:
1. External CSS: in this way you have to put a link to the external CSS file in the HTML file (usually in the head) the tag has to be as the following (considering the name of the CSS file is style.css) : `<link rel="stylesheet" href="style.css">`
this tag has to be written in the HTML file and then all the commands that are put in the CSS file will affect the web page, as said before you can refer to the element you want to style with selectors, **these selectors could be ID selectors, element selectors, class selectors or universal selectors.**
2. Internal CSS : in this way, you put the selector and the properties in the head of the HTML file with no need to create a separate CSS file but with adding the style tag, foe example: 

`<style>`

 `body {
 font-family: arial;
 background-color: rgb(185,179,175);}
 h1 {
 color: rgb(255,255,255);}`

 `</style>`

3. inline CSS: in this way you will use the style as an atribute next to the element you want to add the styles to : 

`<p style= "color:blue;">text</p>`, the result will be then : <p style= "color:blue;">text</p>

**note that it's usually better and safer to use the external css method**

## Basic JavaScript Instructions

*Javascript is a programming language that is used to make web page interactive and adding dynamic to it.*

- there is a familiar concept in Javascript which is called **variables** . A script will have to temporarily
store the bits of information it
needs to do its job. It can store this
data in **variables**. 

variables store different data types , to know more about the data types, take a look at the following table :
|data type      | Description |
| ----------- | ----------- |
|number   | any number without additions (1, 2 ,3,...), declaration: `var number = 3`  |
| string  | anything put between quotations (for example: "Tasneem")  declaration: `var name = "Tasneem"`      |
| boolean  | value that is true or false (used in logical comparisons to return true or false as results)    declaration: `var value = true`  |

There are 6 rules for naming a variable :
1. The name must begin with
a letter, dollar sign ($),or an
underscore (_). It must not start
with a number. 
2. The name can contain letters,
numbers, dollar sign ($), or an
underscore (_). Note that you
must not use a dash(-) or a
period (.) in a variable name. 
3. You cannot use keywords or
reserved words. Keywords
are special words that tell the
interpreter to do something. For
example, var is a keyword used
to declare a variable. Reserved
words are ones that may be used
in a future version of JavaScript. 
4. All variables are case sensitive,
so score and Score would be
different variable names, but
it is bad practice to create two
variables that have the same
name using different cases. 
5. Use a name that describes the
kind of information that the
variable stores. For example,
fi rstName might be used to
store a person's first name,
l astNarne for their last name,
and age for their age.
6. If your variable name is made
up of more than one word, use a
capital letter for the first letter of
every word after the first word. 

### Arrays
*An array is a special type of variable. It doesn't
just store one value; it stores a list of values.*

You create an array and give it
a name just like you would any
other variable (using the var
keyword followed by the name of
the array),for example:
var colors;

`colors ['white', 'black', ' custom'];` 

**Values in an array are accessed as if they are in
a numbered list. It is important to know that the
numbering of this list starts at zero (not one).**

- The first lines of code on the left
create an array containing a list
of three colors. (The values can
be added on the same line or on
separate lines as shown here.) 
- Having created the array, the
third item on the list is changed
from 'custom' to 'beige'. 
- To access a value from an array,
after the array name you specify
the index number for that value
inside square brackets. for a better understanding, look at the following example:

`// Create the array`

`var colors = ['white',`

`'black' ,`

`'custom'];`


`// Update the third item in the array`

`colors[2] = 'beige ' ;`

`// Get the element with an id of col ors`

`var el = document .getElementByid(' colors') ;`

`//Replace with third item from the array`

`el .textContent = colors[2];`

**Expressions:** An expression evaluates into (results in) a single value. Broadly speaking
there are two types of expressions:
1. EXPRESSIONS THAT JUST ASSIGN A
VALUE TO A VARIABLE, ex :
`var color = 'beige'; `
2. EXPRESSIONS THAT USE TWO OR
MORE VALUES TO RETURN A
SINGLE VALUE, ex:

`var area = 3 * 2; `

### Arethmetic operators:

*JavaScript contains the following mathematical
operators, which you can use with numbers.
You may remember some from math class.*

![arethmetic operators](https://cdn-images-1.medium.com/max/1600/1*m46uTShBwfUIWC5txxL5Lw.jpeg)

**To link a JavaScript file to an HTML file you can use the following tag, it's better to use it at the end of the HTML code after the closing body tag so it will execute at the end of the web page (considering the JS file is called script.js):**

`<script src="script.js"></script> `

### conditional statement:

*Conditional statements are used to perform different actions based on different conditions.*

**In JavaScript we have the following conditional statements:**

- Use if to specify a block of code to be executed, if a specified condition is true
- Use else to specify a block of code to be executed, if the same condition is false
- Use else if to specify a new condition to test, if the first condition is false

example for the if statemnt :

`if (hour < 18) {
  greeting = "Good day";
}`

example for the else statement:

`if (hour < 18) {
  greeting = "Good day";
} `

`else {
  greeting = "Good evening";
}`

 example for the else if statemnt :

 `if (time < 10) {
  greeting = "Good morning";
}`

 `else if (time < 20) {
  greeting = "Good day";
}`

`else {
  greeting = "Good evening";
}`