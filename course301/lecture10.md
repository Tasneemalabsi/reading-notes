# In memory storage

## The call stack 

*The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.* 

**In Asynchronous JavaScript**, we have a callback function, an event loop, and a task queue. The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop.

so now, what is the definition of **call stack**

*call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).*

### LIFO 
When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

**Temporarily store**: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

![callstack](https://cdn-media-1.freecodecamp.org/images/QgR2uIk7tW0YNz0Xm8g0jAPeRFI0e4sCejsv)


## How does the call stack handle function calls?

consider the following code : 

`function firstFunction(){`
  
  `console.log("Hello from firstFunction");`

`}`

`function secondFunction(){`

  `firstFunction();`

  `console.log("The end from secondFunction");`

`}`

`secondFunction();`

**This is what happens when the code is run:**

1. When secondFunction() gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.
2. secondFunction() then calls firstFunction()which is pushed into the stack.
3. firstFunction() returns and prints “Hello from firstFunction” to the console.
4. firstFunction() is pop off the stack.
5. The execution order then move to secondFunction().
6. secondFunction() returns and print “The end from secondFunction” to the console.
7. secondFunction() is pop off the stack, clearing the memory.

## JavaScript error messages && debugging

**Types of error messages:**
- Reference errors: This is as simple as when you try to use a variable that is not yet declared you get this type os errors. example :

`console.log(foo) // Uncaught ReferenceError: foo is not defined`

- **Syntax Error:** this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse. example:

`JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1`

- **Range errors:** Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up. example:

`var foo= []`

`foo.length = foo.length -1 // Uncaught RangeError: Invalid array length`

- **Type errors:** Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable. example:

`var foo = {}`

`foo.bar // undefined`

`foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined`

### Debugging 

To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug, click the line you wanna debug and refresh your page again (F5).

If the line you selected was run you will be able to see what has happened before that point and you can try and evaluate the next lines to check if everything is outputting what you are expecting.

**The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.**







