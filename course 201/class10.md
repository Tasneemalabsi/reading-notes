# JavaScript Debugging
Every Developer would make errors while typing codes, in JavaScript you can handle and there are debuggers for these errors
## Order Of Execution
- To find the source of an error, it helps to know how scripts are processed.
The order in which statements are executed can be complex; some tasks
cannot complete until another statement or function has been run.
- You might think that the order of execution (the
order in which statements are processed) would be
as numbered: one through to four. However, it is a
little more complicated. 
 ### Code Debugging
- Programming code might contain syntax errors, or logical errors.

- Many of these errors are difficult to diagnose.

- Often, when programming code contains errors, nothing will happen. There are no error messages, and you will get no indications where to search for errors.

- Searching for (and fixing) errors in programming code is called code debugging.

### Execution context
The JavaScript interpreter uses the concept of execution contexts.
There is one global execution context; plus, each function creates a new
new execution context. They correspond to variable scope. 

### Execution context and Hoisting
**Each time a script enters a new execution context, there are two phases of activity:**
1. PREPARE
- The new scope is created
- Variables, functions, and arguments are created
- The value of the this keyword is determined

2. EXECUTE
- Now it can assign values to variables
- Reference functions and run their code
- Execute statements

## Understanding Errors

*If a JavaScript statement generates an error, then it throws an exception.*
*At that point, the interpreter stops and looks for exception-handl ing code.*

If you are anticipating that something in your code
may cause an error, you can use a set of statements
to handle the error (you meet them on p480).
This is important because if the error is not handled,
the script will just stop processing and the user will
not know why. So exception-handling code should
inform users when there is a problem.

### Error objects

*Error objects can help you find where your mistakes are and browsers have tools to help you read them.*

the error object can hold these properties:

![errors](img/errors.png)

there are 7 types of Error objects

![objects](img/errors2.png)

types of errors in JavaScript:

1. Syntax Errors:
Syntax errors are the most common type of error that occurs in any programming language. As the name suggests, something incorrect in the syntax of the program body raises this error. Syntax errors are also known as parsing errors. In JavaScript, they occur at the interpretation time.
consider this example:
`<script type=''text/javascript''>`
    `window.show(;`
  `</script>`

This program will raise an error as the closing bracket of the show function is missing.

2. Runtime Error

These type of error occurs during the runtime of the program, after it is interpreted by the compiler.

Consider this code segment:

  `<script type=''text/javascript''>`
    `window.show();`
  `</script>`

Notice that there is no show function defined. This program will raise an error at runtime as the function which is not present is called, although the syntax is correct.

3. Logical Errors:
These type of errors are the most difficult to find. Consider a statement: `''John is playing guitar.''` This statement is logically correct and its syntax is also correct. Now consider another statement: ''Guitar is playing John.'' This statement is correct with respect to its syntax but is logically incorrect. These types of errors cause a serious problem as they change the whole path of how your program will work.

## Handling and Debugging errors

- Debugging is not easy. But fortunately, all modern browsers have a built-in JavaScript debugger.

- Built-in debuggers can be turned on and off, forcing errors to be reported to the user.

- With a debugger, you can also set breakpoints (places where code execution can be stopped), and examine variables while the code is executing.

- Normally, otherwise follow the steps at the bottom of this page, you activate debugging in your browser with the F12 key, and select "Console" in the debugger menu.

**The console.log() Method**

If your browser supports debugging, you can use console.log() to display JavaScript values in the debugger window

**Setting Breakpoints**
- In the debugger window, you can set breakpoints in the JavaScript code.

- At each breakpoint, JavaScript will stop executing, and let you examine JavaScript values.

- After examining values, you can resume the execution of code (typically with a play button).

**The debugger Keyword**
- The debugger keyword stops the execution of JavaScript, and calls (if available) the debugging function.

- This has the same function as setting a breakpoint in the debugger.

- If no debugging is available, the debugger statement has no effect.

- With the debugger turned on, this code will stop executing before it executes the third line.

Example:

`let x = 15 * 5;`
`debugger;`
`document.getElementById("demo").innerHTML = x;`

## Major Browser Debugging Tools

*Normally, you activate debugging in your browser with F12, and select "Console" in the debugger menu.*

*Otherwise follow these steps:*

**Chrome**
- Open the browser.
- From the menu, select "More tools".
- From tools, choose "Developer tools".
- Finally, select Console.

**Firefox**
- Open the browser.
- From the menu, select "Web Developer".
- Finally, select "Web Console".

**Edge**
- Open the browser.
- From the menu, select "Developer Tools".
- Finally, select "Console".

**Opera**
- Open the browser.
- From the menu, select "Developer".
- From "Developer", select "Developer tools".
- Finally, select "Console".

**Safari**
- Go to Safari, Preferences, Advanced in the main menu.
- Check "Enable Show Develop menu in menu bar".
- When the new option "Develop" appears in the menu:
- Choose "Show Error Console".