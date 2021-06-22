# HTML, CSS and JavaScript
## Links in HTML
*HTML enables you to navigate to other web pages by using the `<a>` tag, syntax:*

`<a href="url">link text</a>`
- the href part is an attribute that indicates link's destination.
- The link text is the part that will be visible to the user .
-  To write good link text, you can
think of words people might
use when searching for the
page that you are linking to. 
- When you are linking to other pages within the same site, you do not need to specify the domain name in the URL. You can use a shorthand known as a relative URL. for example

`<li><a href="index.html">Home</a></li>`

**Relative URLS:** Relative URLs can be used when linking to pages within your own
website. They provide a shorthand way of telling the browser where to
find your files.

**Email Links:** To create a link that starts up
the user's email program and addresses an email to a specified email address, you use the `<a>` element. Synatx:

`<a href="mailto:jon@example.org">Email Jon</a>`

 **The target Attribute:** By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link. The target attribute specifies where to open the linked document. The target attribute can have one of the following values:

- self: Default. Opens the document in the same window/tab as it was clicked
 - blank: Opens the document in a new window or tab
- parent: Opens the document in the parent frame
- top: Opens the document in the full body of the window
 for example: 

 `<a href="https://github.com//" target="_blank">Visit github!</a>`

 *so in summary: You can use the id attribute to target elements within a page that can be linked to.*

 ## Layout in HTML and CSS
 *CSS treats each HTML element as if it is in its
own box. This box will either be a block-level
box or an inline box.*

 **Block-level elements:**
 - A block-level element always starts on a new line.
- A block-level element always takes up the full width available (stretches out to the left and right as far as it can).
- A block level element has a top and a bottom margin, whereas an inline element does not.

**Inline elements:**
- An inline element does not start on a new line.
- An inline element only takes up as much width as necessary.

to understand the difference, you can see the following image :

![block and inline](https://lh3.googleusercontent.com/proxy/1irO1ykI901OHQZYny3JsRtSTHQput9OqicE-wu9SuF1xKYmrBgsPum4WALuef8qzD6lE9H10kcNUxTlkb587A0FFAR3JIkXmOtLwXCFCH0coCGGgaUzpVWbCD6Kz8pFbATsGO5l7u7z9shrYc9le6ihZopT )

**Controlling the Position of Elements** 

CSS has the following positioning schemes that allow you to control
the layout of a page: normal flow, relative positioning, and absolute
positioning. You specify the positioning scheme using the position
property in CSS. You can also float elements using the float property
- Normal flow: Every block-level element
appears on a new line, causing
each item to appear lower down
the page than the previous one.
- Relative Positioning:
This moves an element from the
position it would be in normal
flow, shifting it to the top, right,
bottom, or left of where it
would have been placed.
- Absolute positioning
This positions the element
in relation to its containing
element. It is taken out of
normal flow, meaning that it
does not affect the position
of any surrounding elements
(as they simply ignore the
space it would have taken up).

**Position property:** The position is a property that sets how an element is positioned in a document. The top, right, bottom, and left properties determine the final location of positioned elements.

**values of this property:**
1. static: The element is positioned according to the normal flow of the document.
2. relative: The element is positioned according to the normal flow of the document, and then offset relative to itself based on the values of top, right, bottom, and left. 
3. absolute: The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to its closest positioned ancestor, if any; otherwise, it is placed relative to the initial containing block. 
4. fixed: The element is removed from the normal document flow, and no space is created for the element in the page layout. 

**Overlapping elements:** When you use relative, fixed, or absolute positioning, boxes can
overlap. If boxes do overlap, the
elements that appear later in the
HTML code sit on top of those
that are earlier in the page. 

*If you want to control which element sits on top, you can use the z-index property. Its value is a number, and the higher the number the closer that element is to the front. For example, an element with a z-index of 10 will appear over the top of one with a z-index of 5.*

**Floating elements:**

- The float property allows you
to take an element in normal
flow and place it as far to the
left or right of the containing
element as possible.
- Anything else that sits inside
the containing element will
flow around the element that is
floated.
- When you use the float
property, you should also use the
width property to indicate how
wide the floated element should
be. If you do not, results can be
inconsistent but the box is likely
to take up the full width of the
containing element (just like it
would in normal flow).

**Using float to place elements side by side:**
- A lot of layouts place boxes
next to each other. The float
property is commonly used to
achieve this.
- When elements are floated, the
height of the boxes can affect
where the following elements sit.

**Clearing Floats:**
- The clear property allows you
to say that no element (within
the same containing element)
should touch the left or righthand sides of a box. It can take
the following values:
1. left: The left-hand side of the box
should not touch any other
elements appearing in the same
containing element.
2. right: The right-hand side of the
box will not touch elements
appearing in the same containing
element.
3. both: Neither the left nor right-hand
sides of the box will touch
elements appearing in the same
containing element.
4. none: Elements can touch either side.

### Layouts:
**Fixed Width Layout:**

To create a fixed width layout,
the width of the main boxes on
a page will usually be specified
in pixels (and sometimes their
height, too).

**Liquid Layout:** The liquid layout uses
percentages to specify the width
of each box so that the design
will stretch to fit the size of the
screen.

**Grid Layout:**
- Grid Layout excels at dividing a page into major regions or defining the relationship in terms of size, position, and layer, between parts of a control built from HTML primitives.
- Like tables, grid layout enables an author to align elements into columns and rows. However, many more layouts are either possible or easier with CSS grid than they were with tables. For example, a grid container's child elements could position themselves so they actually overlap and layer, similar to CSS positioned elements.

**CSS framework:**

CSS frameworks aim to make your life easier by providing the code for
common tasks, such as creating layout grids, styling forms, creating
printer-friendly versions of pages and so on. You can include the CSS
framework code in your projects rather than writing the CSS from scratch.

**Multiple style sheets:**
- Some web page authors split
up their CSS style rules into
separate style sheets. For
example, they might use one
style sheet to control the layout
and another to control fonts,
colors and so on.
- Some authors take an even
more modular approach
to stylesheets, creating
separate stylesheets to control
typography, layout, forms,
tables, even different styles for
each sub-section of a site.
- There are two ways to add
multiple style sheets to a page:
1. Your HTML page can link
to one style sheet and that
stylesheet can use the @import
rule to import other style sheets. for example :

`@import url("tables.css");`

`@import url("typography.css");`

2. In the HTML you can use a
separate `<link>` element for
each style sheet.

## Functions in JavaScript
*A JavaScript function is a block of code designed to perform a particular task. It is executed when "something" invokes it (calls it). Syntax:*

`function name (parameter1, parameter2, parameter3) {`

  `// code to be executed`
`}`

- Function parameters are listed inside the parentheses () in the function definition.

- Function arguments are the values received by the function when it is invoked.

- Inside the function, the arguments (the parameters) behave as local variables.

**Function Invocation:**

*The code inside the function will execute when "something" invokes (calls) the function:*

- When an event occurs (when a user clicks a button)
- When it is invoked (called) from JavaScript code
- Automatically (self invoked)

**Variable Scope**

*The location where you declare a variable will affect where it can be used
within your code. If you declare it within a function, it can only be used
within that function. This is known as the variable's scope.*

**Local and global variables**
- Local Variable:
When you use JavaScript, local variables are variables that are defined within functions. They have local scope, which means that they can only be used within the functions that define them.

- Global Variable:
In contrast, global variables are variables that are defined outside of functions. These variables have global scope, so they can be used by any function without passing them to the function as parameters.

## Pair Programming

*How does pair programming work?*

pair programming involves two roles: **the Driver** and **the Navigator**. The Driver is the programmer who is typing and the only one whose hands are on the keyboard. while The Navigator uses their words to guide the Driver but does not provide any direct input to the computer. The Navigator thinks about the big picture, what comes next, how an algorithm might be converted in to code, while scanning for typos or bugs. 

*Why pair programming?*

there are four fundamental skills that help anyone learn a new language: 
1. Listening: hearing and interpreting the vocabulary 
2. Speaking: using the correct words to communicate an idea 
3. Reading: understanding what written language intends to convey 
4. Writing: producing from scratch a meaningful

*Pair programming touches on all four skills:*

 developers explain out loud what the code should do, listen to others’ guidance, read code that others have written, and write code themselves.

 **The results of pair programming are:**
 1. Greater efficiency: It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.
  2. Engaged collaboration:
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone.
3. Learning from fellow students:
Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of.
4. Social skills: Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities.
5. Job interview readiness:
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen.
6. Work environment readiness:
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product.






