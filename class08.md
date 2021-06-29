# CSS Layout
## Positioning Elements in CSS

*You can specify the positioning scheme using the **position property** in CSS. You can also float elements using the float property.*

- **Normal flow** : Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. 
- **Relative Positioning** :This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. 
- **Absolute Positioning** :This positions the element in relation to its containing element.

### Position Property:

*The position property specifies the type of positioning method used for an element.*

**There are five different position values:**

    1. static
    2. relative
    3. fixed
    4. absolute
    5. sticky

    
The static position:


- HTML elements are positioned static by default.

- Static positioned elements are not affected by the top, bottom, left, and right properties.

- An element with position: static; is not positioned in any special way; it is always positioned according to the normal flow of the page.

The relative position:

- An element with position: relative; is positioned relative to its normal position.

- Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element.

The fixed position :
- An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.

- A fixed element does not leave a gap in the page where it would normally have been located.

The absolute position:

- An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).

- However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.

to help differentiating between these properties, you can see the picture below:

![poosition](https://miro.medium.com/max/1200/1*3nHXvVEEbQziTats5DlZOA.png)

### Floating Elements

- float property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible.
- Anything else that sits inside the containing element will flow around the element that is floated.


**Clearing Floats**

*The clear property allows you to say that no element (within the same containing element) should touch the left or right-hand sides of a box. It can take the following values:*

- left: The left-hand side of the box should not touch any other elements appearing in the same containing element.-right: The right-hand side of the box will not touch elements appearing in the same containing element.
- both: Neither the left nor right-hand sides of the box will touch elements appearing in the same containing element.- none: Elements can touch either side

**Screen Sizing:** Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.

### Fixed Width layout

- To create a fixed width layout, the width of the main boxes on a page will usually be specified in pixels (and sometimes their height, too).
- The fixed width layout will stay the same width no matter what size the browser window is, whereas the liquid layout will stretch (or shrink) to fill the screen

![width](https://i.stack.imgur.com/OSIdf.png)


### Liquid Layout

The liquid layout uses percentages to specify the width of each box so that the design will stretch to fit the size of the screen.

### Grid Layout 

*The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.*

![grids](https://cdn.codecoda.com/themes/user/site/default/asset/img/blog/CSS-layout-1.png)

**grid element**

`<div class="grid-container">`

   `<div class="grid-item">1</div>`

   `<div class="grid-item">2</div>`

   `<div class="grid-item">3</div>`

`</div>`

you can display them in CSS as :

`.grid-container {`

`display: grid;`

`}`



### CSS frameworks
*CSS frameworks aim to make your life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. You can include the CSS framework code in your projects rather than writing the CSS from scratch.*

## Multiple Style sheets

- Some web page authors split up their CSS style rules into separate style sheets. For example, they might use one style sheet to control the layout and another to control fonts, colors and so on.
- Some authors take an even more modular approach to stylesheets, creating separate stylesheets to control typography, layout, forms, tables, even different styles for each sub-section of a site.
- There are two ways to add multiple style sheets to a page:
1. Your HTML page can link to one style sheet and that stylesheet can use the @importrule to import other style sheets.2. In the HTML you can use a separate `<link>` element for each style sheet.

