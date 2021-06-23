# HTML, CSS and JavaScript
## Images in HTML
**Adding Images:**
- The HTML `<img>` tag is used to embed an image in a web page.

- Images are not technically inserted into a web page; images are linked to web pages. The `<img>` tag creates a holding space for the referenced image.

- The `<img>` tag is empty, it contains attributes only, and does not have a closing tag.

- The `<img>` tag has two required attributes:
   1. src - Specifies the path to the image
   2. alt - Specifies an alternate text for the image.

   syntax: `<img src="url" alt="alternatetext">`

- You will also often see an `<img>`
element use two other attributes
that specify its size:
1. height:
This specifies the height of the
image in pixels.
2. width:
This specifies the width of the
image in pixels.

**There are three rules to remember when you
are creating images for your website which are
summarized below:**
1. Save images in
the right format
Websites mainly use images in
jpeg, gif, or png format.
2.  Save images at
the right size
You should save the image at
the same width and height it will
appear on the website.
3. Use the correct resolution
Computer screens are made up
of dots known as pixels. Images
used on the web are also made
up of tiny dots.

**note that Photographs are best saved as JPEGs; illustrations or logos that use flat colors are better saved as GIFs.**

## Colors in CSS
### CSS Text Color
in css we have:
1. text color, attribute: color
2. background color, attribute: background-color
3. borders color, attribute: border-color

**There are three different ways to specify colors in CSS:**
1. Color Keywords:
The first and easiest way to specify a color is using one of the 17 predefined color keywords.
for example: `color:red;`
2. RGB Color Values: RGB values are specified for each of the key colors (red, green, blue), using a value between 0 and 255 or a percentage value. A higher value means more of that color. for example : `color: rgb(128, 80, 200);` the result is purple
3. Hexadecimal Color Values: The most common way to specify colors in CSS is to use their hexadecimal (or hex) values. Hex values are actually just a different way to represent RGB values. Instead of using three numbers between 0 and 255, you use six hexadecimal numbers. Hex numbers can be 0-9 and A-F. Hex values are always prefixed with a # symbol. for example : `color: #8050c8;` result: purple

![colors](https://cdn.educba.com/academy/wp-content/uploads/2020/03/CSS-Color-Codes.jpg)

- CSS3 has introduced an extra value for RGB colors to
indicate opacity. It is known as RGBA.
- CSS3 also allows you to specify colors as HSL values,
with an optional opacity value. It is known as HSLA.

## text in CSS
**text alignment**
- The text-align property is used to set the horizontal alignment of a text.

- A text can be left or right aligned, centered, or justified.

**Vertical Alignment**
The vertical-align property sets the vertical alignment of an element.

**Text Decoration**
- The text-decoration property is used to set or remove decorations from text.

- The value text-decoration: none; is often used to remove underlines from links

**Text Transformation**
- The text-transform property is used to specify uppercase and lowercase letters in a text.

- It can be used to turn everything into uppercase or lowercase letters, or capitalize the first letter of each word:

`p.uppercase {`

  `text-transform: uppercase;`
`}`

`p.lowercase {`
  `text-transform: lowercase;`
`}`

`p.capitalize {`
  `text-transform: capitalize;`
`}`

**You can control the space between lines of text,
individual letters, and words. Text can also be aligned to the left, right, center, or justified. It can also be indented.**

 ### Text Indentation
The text-indent property is used to specify the indentation of the first line of a text: `text-indent: 50px;`

**Letter Spacing:**
The letter-spacing property is used to specify the space between the characters in a text.
for example :`letter-spacing: 3px;`

**Line Height**
The line-height property is used to specify the space between lines: `line-height: 0.8;`

**Word Spacing**
The word-spacing property is used to specify the space between the words in a text.
for example : `word-spacing: 10px;`

**White Space**
The white-space property specifies how white-space inside an element is handled.
for example: `white-space: nowrap;`
