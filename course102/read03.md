### what is wireframing?
*Wireframing is a practice used by UX designers which allows them to define and plan the information hierarchy of their design for a website, app, or product.*

**wireframe creation:**
- Wireframes drawn with paper and a pencil, or at a whiteboard, have the advantage of looking and being very easy to change, which can help tremendously in early conversations about your website or product.
- With the help of paper-prototypes, you can test with end users at every stage of ideation and design. Changes at these stages are much easier—and therefore cheaper—than changes deemed necessary after coding is under way.
- Switching later to software (after initially hand-drawing your wireframe) allows you to keep track of more detailed decisions.

Wireframes from CareerFoundry student Samuel Adaramola:
![wireframes](https://d33wubrfki0l68.cloudfront.net/dbb80f2f6a5dafa25f702ad00bc429057fb59cec/52716/en/blog/uploads/versions/samuel-student-wireframe---x----972-715x---.png
)
## HTML Basics
 **HTML:** *HTML is a markup language that defines the structure of your content.*
  **Paragraph syntax in HTML:** 
  
  `<p>text</p>`

  **Anatomy of an HTML element** 
  ![HTML elements](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png
  )
  
  **The main parts of our element are as follows:**
- The opening tag: This consists of the name of the element (in this case, p), wrapped in opening and closing angle brackets. This states where the element begins or starts to take effect — in this case where the paragraph begins.
- The closing tag: This is the same as the opening tag, except that it includes a forward slash before the element name. This states where the element ends — in this case where the paragraph ends. Failing to add a closing tag is one of the standard beginner errors and can lead to strange results.
- The content: This is the content of the element, which in this case, is just text.
- The element: The opening tag, the closing tag, and the content together comprise the element.

**Anatomy of an HTML document**
*That wraps up the basics of individual HTML elements, but they aren't handy on their own. Now we'll look at how individual elements are combined to form an entire HTML page.*
example of HTML document:

`<!DOCTYPE html>
<html>

  <head>

    <meta charset="utf-8">

    <title>My test page</title>

  </head>

  <body>

    <img src="images/firefox-icon.png" alt="My test image">
  
  </body>

</html>`
 
 **Image syntax:**

 `<img src="images/firefox-icon.png" alt="My test image">`

 *We have also included an alt (alternative) attribute. In this attribute, you specify descriptive text for users who cannot see the image, possibly because of the following reasons:*

- They are visually impaired. Users with significant visual impairments often use tools called screen readers to read out the alt text to them.
- Something has gone wrong causing the image not to display. For example, try deliberately changing the path inside your src attribute to make it incorrect.

### semantics in HTML

In HTML, for example, the <h1> element is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."

`<h1>This is a top level heading</h1>`

By default, most browser's user agent stylesheet will style an <h1> with a large font size to make it look like a heading (although you could style it to look like anything you wanted).

On the other hand, you could make any element look like a top level heading. Consider the following:

`<span style="font-size: 32px; margin: 21px 0;">Is this a top level heading?</span>`

