# HTML and JavaScript 
websites are created using html to build the structure of the site; the headings, pararagraphs and images are created by HTML and even if we want to link other pages, we can use it. CSS is used to design what was created by HTML, you can style your pages using it. For the dynamics of the websites you have to use more advanced technologies and programming languages.
## HTML
*HTML pages are considered (like as we know in Microsoft Word pages) text documents.*

**Now, what about the structure that builds the HTML file.**

HTML consists of characters that live inside angles brackets, these characters are called elements. these 
elements describes the type of content that is put inside the file.

elements are **usually** made up of two tags: opening and closing tags. so tags are like containers to whats written or linked between them.

for example, the following HTML code holds all the necessary tags that must exist in it:

`<!DOCTYPE html>`

` <html>`

`<head>`

`<title>the title of the webpage</title>`

`</head>`

`<body>`

`<p> text </p>`

`</body>`

`</html>`

of course there are more tags that can be put inside the body tag like `<h1>main heading </h1>` and `<h2> sub-heading </h2>` 

*you can also add more info about the content inside the tag, these information are held inside what's called **Attributes** *

**Attributes provide additional info, for example:**

`<p lang="eng-us">text in english</p>`

in the previous example; the attribute name is lang which describes the language of the text, and the attribute value is eng-us which should be written inside quotations 

*the majority of attributes  can be used in certain elements, although a few attributes -such as lang- can appear on any element.*

### VERSIONS OF HTML

** There are different versions of HTML such as: HTML 5, HTML 4, strict XHTML 1.0 and more! so to know which version of HTML you're going to write with, we use a specific and necessary tag which as doctype, each version has a different way to write this tag in the beginning of the code. the following table contains some versions and the doctype tag attached to them:**

| HTML VERSION   | tag |
| ----------- | ----------- |
|HTML 5     | `<!DOCTYPE html> `    |
| HTML 4  | `<!DOCTYPE html PUBLIC"-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">` |
|XML Declaration  | `<?xml version="1.0" ?>`      |
| Strict XHTML 1.0  |` <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/ xhtml1-strict.dtd">`
       |
|Transitional XHTML 1.0 | `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/ xhtml1-transitional.dtd">`

### COMMENTS IN HTML
*sometimes when you are writing your code, there might be some stuff you do that you want to explain how or why you did it to other developers or even to yourself when come back to the code later, you can do that using what's called **comments** in HTML, comments are a reminder to you and other developers that are invisible to the users - unless someone wants to inspect the web page- the comments can be written by the following tag:*

`<!-- comment -->`

### ID and class attributes
*If you want to identify a specific element in an HTML file, you can add an attribute called **id attribute** to identify it specifically, for example:*

`<p id="desciption ">text</p>`

*If you want to identify several elements in the file rather than uniquely identify just one element, you can use the class attribute, for example:*

`<p class="desciption">text</p>`

**the class and id attributes will help you when you want to design your page bu CSS, since you can use their values to specify some contents that you want to add the same type of styling to them**

### div and span elements
if you wanna group a set of elements together so that it would be easier for you to use styling and dynamics in them, and make your code easier to read you can use the tag div, for example:

`<div>`
`<img src="link"/>`

`<ul>`

 `<li>sth</a></li>`

 `<li>sth</a></li>`

 `<li>sth</li>`
 
`</ul>`

`</div>`

you can also use the span tag to group a set of inline elements together, for example:

`<p>text<span class="desciption">sthe</span> text.</p>`

### Iframes
you can notice in Google maps that its shown to you as a part of page but when you open it you can see a whole other page, to do that you can use the iframe tage (abbreviation of inline frame), example:

<iframe
width="number"
height="number"
src="link">
</iframe>

 ### meta tag
 *meta elements add information about the page, they exist only in the head element, they don't have closing tags, they use attributes to carry the information, for example:*

 `<head>`

  `<meta charset="UTF-8">`

  `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  
`</head>`

### escape characters

*There are some characters that are used in
and reserved by HTML code. (For example, the
left and right angled brackets.)*

escape characters are special characters like currency signs and punctuation marks that have specific abbreviations used in HTML., these styles can be added by CS

## styling and CSS
*after creating the HTML page, you can add some styling to make it easier to be read by the users, these styles can be added by CSS*

- before using CSS, if you want to design your page, it's easier for you to have a **wireframe**, wireframes are a sample of the web page that you want to create and how you want it to look like.
- CSS helps you defferntiate between your elements by the size, color and style (such as margins, float-where do you want this element to locate- and borders)
- it's easier to add a separate CSS file to write the CSS codes in it -external CSS-, although you can use inline and internal CSS the can be included in the same HTML file 
- grouping tags and identifications attributes make it easier for you to write the commands in CSS and style your elements or the set of grouped elements
- you can link the CSS file to the HTML file to make it readable by the browser by using the link tag, as written below (considering the css file is called style.css):

`<link rel="stylesheet" href="style.css">`




## JavaScript
*JavaScript is used to improve the interactions and add dynamics to the websites that are created by HTML and designed by CSS, it's a programming language that uses logic to make the web page more interactive, such as making slide-show and filtering data.*

If we want to learn JavaScript we have to know first the meaning of **script**

- A script is a series of instructions that a
computer can follow to achieve a goal. 

- a browser may use different parts of the script depending on how the user interacts with the web page 

- scripts can run different sections of the code in response to the situation around them

now if you want to deal with the computer, you have to use a language that can be understood by the computer, you have to use some words that the computer understands that are put in a specific way that's called the syntax, the programming languages differ slightly in whats called syntax

### how computers deal with the world around them

- as mentioned before, computers don't understant the language of humans so programmers interact with them using data.
- you can refer to anything in life as **objects** in the computer, these objects have **properties** that describe them, the properties are written in name-value pairs to add information about the objects.
- in real life, you can use some commands to make things move in a certain way, in a computer, programmers choose which **events** they should respond to if a specific thing or event happens.
- in life, people mightuse some interactions to deal with things, in a computer, programmers use **methods** to interact with objects, so they can include some instructions to the code to make the computer perform a certain tasks following these instructions.
- any web browser on the computer is mere program that uses objects, you can see objects such as window object that contains the properties about what tab are using the control of the web page, there also document objects that show the contents of the web page, when you press on it it will show you the title used between the <title></title> tags.
- the document object represents the output of the HTML file that developers create.

### how to write a script inside a web page
as I mentioned in the beginning of this class, there are 3 layers to build a web page:

1. HTML only: only shows the structure of the page without any formatting or interactions.
2. HTML+CSS: the structure with designs and coloring that make it easier to read by the users
3. HTML+CSS+JS: styled web pages with dynamics and interactions added by a programming language.

 *to include a JS file inside an HTML file, you can add the script tag so the JavaScript codes can be read by the browser, as written below(considering the css file is called script.js):*

 `<script src="script.js"></script> `

- **it would be better to include the script tag at the end of the HTML code so it will be excuted after reading the whole HTML code, its also better to separate the JS codes in a different file than the HTML even that it could be included in the same file, but separating them makes it easier to red and deal with pages**
- **if you want something from the script code to appear on the HTML page you can use documnt.write(the content that you want to be shown)**










      |











