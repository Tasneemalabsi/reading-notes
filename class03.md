# HTML, CSS and JavaScript
## Lists in HTML
Usually in websites, articles and papers, you will see lists to write down some instruction, notes or count things. And of course, there are easy ways to write lists in HTML, in HTML there are 3 types of lists :
1. *ordered lists : ordered lists have numbers of each item, you can create an ordered list in HTML by using the tag `<ol>` and for each item you have to use the tag `<li>`, for example :*

`<ol>`

`<li>Chop potatoes into quarters</li>`

`<li>Simmer in salted water for 15-20
 minutes until tender</li>`

`<li>Heat milk, butter and nutmeg</li>`

`<li>Drain potatoes and mash</li>`

`<li>Mix in the milk mixture</li>`

`</ol>`

the results will be :
<ol>
<li>Chop potatoes into quarters</li>
<li>Simmer in salted water for 15-20
 minutes until tender</li>
<li>Heat milk, butter and nutmeg</li>
<li>Drain potatoes and mash</li>
<li>Mix in the milk mixture</li>
</ol>

2. *unordered lists : unordered lists are used with bullets, there is no order in this type of lists. you can create unordered lists by using the tag `<ul>`, for example :*

`<ul>`

`<li>1kg King Edward potatoes</li>`

`<li>100ml milk</li>`

`<li>50g salted butter</li>`

`<li>Freshly grated nutmeg</li>`

`<li>Salt and pepper to taste</li>`

`</ul>`

the results will be :
<ul>
<li>1kg King Edward potatoes</li>
<li>100ml milk</li>
<li>50g salted butter</li>
<li>Freshly grated nutmeg</li>
<li>Salt and pepper to taste</li>
</ul>

3. *Definition Lists: The definition list is created with
the `<dl>` element and usually
consists of a series of terms and
their definitions. for example :*

`<dl>`

`<dt>Sashimi</dt>`

`<dd>Sliced raw fish that is served with
 condiments such as shredded daikon radish or
 ginger root, wasabi and soy sauce</dd>`

`<dt>Scale</dt>`

`<dd>A device used to accurately measure the
 weight of ingredients</dd>`

`<dd>A technique by which the scales are removed
 from the skin of a fish</dd>`

`<dt>Scamorze</dt>`

`<dt>Scamorzo</dt>`

`<dd>An Italian cheese usually made from whole
 cow's milk (although it was traditionally made
 from buffalo milk)</dd>`

`</dl>`
the results will be :

<dl>
<dt>Sashimi</dt>
<dd>Sliced raw fish that is served with
 condiments such as shredded daikon radish or
 ginger root, wasabi and soy sauce</dd>
<dt>Scale</dt>
<dd>A device used to accurately measure the
 weight of ingredients</dd>
<dd>A technique by which the scales are removed
 from the skin of a fish</dd>
<dt>Scamorze</dt>
<dt>Scamorzo</dt>
<dd>An Italian cheese usually made from whole
 cow's milk (although it was traditionally made
 from buffalo milk)</dd>
</dl>

**note that:**
- `<dt>`: 
This is used to contain the term
being defined (the definition
term).
- `<dd>`: 
This is used to contain the
definition.

*If you wanna insert a list in another one, you can use nested lists, for example:*

`<ul>`

`<li>Mousses</li>`

`<li>Pastries<li>`

 `<ul>`
 
 `<li>Croissant</li>`
 
 `<li>Mille-feuille</li>`
 
 `<li>Palmier</li>`
 
 `<li>Profiterole</li>`
 
 `</ul>`

`</li>`

`<li>Tarts</li>`

`</ul>`

**you can use abbreviations to create lists easily, for example (unordered list): `ul>li*(number of list items you want to add)`**

## Boxes in CSS
### Box dimensions (width, height)
- By default a box is sized just big
enough to hold its contents. To
set your own dimensions for a
box you can use the height and
width properties.
- there are multiple ways to determine the dimensions of a box :
1.  specify the size of a box are to use pixels, this is the most popular method because they allow designers to accurately control their size. for example:

`div.box {`

`height: 300px;`

`width: 300px;
}`

2. using percentages: in this method the size of the box is relative to
the size of the browser window. for example :

`p {`

`height: 75%;`

`width: 75%;
}`

3. using ems: in this method, the size
of the box is based on the size
of text within it.

**Overflowing content:** The overflow property tells the
browser what to do if the content
contained within a box is larger
than the box itself. It can have
one of two values:
 1. hidden:
This property simply hides any
extra content that does not fit in
the box.
2. scroll:
This property adds a scrollbar to
the box so that users can scroll
to see the missing content.

For example:

 `p.one {`

`overflow: hidden;}`

`p.two {`

`overflow: scroll;}`

### Border, Margin & Padding in CSS
*Every box has three available properties that
can be adjusted to control its appearance:*
1. Border
Every box has a border (even if
it is not visible or is specified to
be 0 pixels wide). The border
separates the edge of one box
from another.
2. Margin
Margins sit outside the edge
of the border. You can set the
width of a margin to create a
gap between the borders of two
adjacent boxes.
3. Padding
Padding is the space between
the border of a box and any
content contained within it.
Adding padding can increase the
readability of its contents.

**About borders:**
- There is a property called border width which
is used to control the width
of a border. The value of this
property can either be given
in pixels or using one of the
following values: thin, medium, thick
- another property for borders is border style, this property controls the style of borders, they might be solid, dotted, dashed,...
- you can control the color of a border using the border-color property.
- The border property allows you
to specify the width, style and
color of a border in one property
(and the values should be coded
in that specific order). for example :

`p {`

`width: 250px;`

`border: 3px dotted #0088dd;}`

**About alignments and display:**

-  you can center or move your box to left and right using text-align property, for example:

`body {
text-align: center;}` this command will center the body element

- The display property allows
you to turn an inline element
into a block-level element or vice
versa, and can also be used to
hide an element from the page.
The values this property can
take are:
1. inline
This causes a block-level
element to act like an inline
element.
2. block
This causes an inline element to
act like a block-level element.
3. inline-block
This causes a block-level
element to flow like an inline
element, while retaining other
features of a block-level element.
4. none
This hides an element from the
page. 

**more notes about boxes:**

- Hiding boxes: The visibility property allows
you to hide boxes from users
but It leaves a space where the
element would have been.
- Image borders: The border-image property
applies an image to the border of
any box. It takes a background
image and slices it into nine
pieces. 
- box shadows: The box-shadow property
allows you to add a drop shadow
around a box.
- eliptical shapes: To create more complex shapes, you can specify different distances for the horizontal and the vertical parts of the rounded corners. For example, this will create a radius that is wider than it is tall:

`border-radius: 80px 50px;`

## Arrays in JavaScript:

*An array is a special type of variable. It doesn't just store one value; it stores a list of values.*

- You should consider using an
array whenever you are working
with a list or a set of values that
are related to each other.
- Arrays are especially helpful
when you do not know how
many items a list will contain
because, when you create the
array, you do not need to specify
how many values it will hold. 
- You can create an array and give it
a name just like you would any
other variable (using the var
keyword followed by the name of
the array).
- The values are assigned to the
array inside a pair of square
brackets, and each value is
separated by a comma.
- The values in the array do not need
to be the same data type, so you
can store a string, a number and
a Boolean all in the same array. 

example for arrays : 

`var colors;`

`colors ['white', 'black', ' custom'];`

- Values in an array are accessed as if they are in
a numbered list. It is important to know that the
numbering of this list starts at zero (not one). 

- To access a value from an array,
after the array name you specify
the index number for that value
inside square brackets. 

## Switch statement in JavaScript:

*you can use the switch statement to select one of many code blocks to be executed.*

**Syntax:**

`switch (level) {`

`case 'One ':`

`title= 'Level 1 ' ;`

`break;`

`case 'Two':`

`title = ' Level 2 ' ;`

`break;`

`case ' Three' :`

`title = 'Level 3' ;`

`break ;`

`default :`

`title= 'Test';`

`break;}` 

- The switch expression is evaluated once.
- The value of the expression is compared with the values of each case.
- If there is a match, the associated block of code is executed.
- If there is no match, the default code block is executed.

## TYPE COERCION & WEAK TYPING in JavaScript
*If you use a data type JavaScript did not expect,
it tries to make sense of the operation rather
than report an error.*

| data type   | purpose |
| ----------- | ----------- |
|  string    |    Text|
|  number | number     |
| boolean| true or false     |
| null| empty values    |

- JavaScript can convert data
types behind the scenes to
complete an operation. This is
known as type coercion. For
example, a string 'l ' could be
converted to a number 1 in the
following expression:(' 1' > 0).
As a result, the above expression
would evaluate to true.
- JavaScript is said to use weak
typing because the data type
for a value can change. Some
other languages require that you
specify what data type
each variable will be. They are
said to use strong typing. 

### Truthy and Falsy values in JS

- Falsy values are treated as if they
are fa 1 se. The table to the left
shows a hi ghScore variable with
a series of values, all of which
are falsy. falsy value is treated as the number 0
- Truthy values are treated as if
they are true. Almost everything
that is not in the falsy table can
be treated as if it were true. Truthy values can also be treated as the number 1. 

## Loops in JavaScript
- for loop : A for loop repeats until a specified condition evaluates to false. Syntax:

`for ([initialExpression]; [conditionExpression]; [incrementExpression])`
  
  `{statement}`

  - do...while statement: The do...while statement repeats until a specified condition evaluates to false. syntax:

  `do`

  `{statement}`

`while (condition);`

- while statement: A while statement executes its statements as long as a specified condition evaluates to true. syntax

`while (condition)` 
  
  `{statement}`
