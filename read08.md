# Expressions and Loops
## Expressions:
*An expression is any valid unit of code that resolves to a value.*

**JavaScript has the following expression categories:**

- Arithmetic: evaluates to a number, for example 3.14159. (Generally uses arithmetic operators.)
- String: evaluates to a character string, for example, "Fred" or "234". (Generally uses string operators.)
- Logical: evaluates to true or false. (Often involves logical operators.)
- Primary expressions: Basic keywords and general expressions in JavaScript.
- Left-hand-side expressions: Left values are the destination of an assignment.

**Grouping operator**

*The grouping operator ( ) controls the precedence of evaluation in expressions. For example, you can override multiplication and division first, then addition and subtraction to evaluate addition first. ex:*

var a = 1;
var b = 2;
var c = 3;

// default precedence
a + b * c     // 7
// evaluated by default like this
a + (b * c)   // 7

// now overriding precedence
// addition before multiplication
(a + b) * c   // 9

// which is equivalent to
a * c + b * c // 9

**Left-hand-side expressions**

*Left values are the destination of an assignment.*

1. new, ex:

`var objectName = new objectType([param1, param2, ..., paramN]);` 

2. super, ex:

`super([arguments]); // calls the parent constructor.
super.functionOnParent([arguments]);`

## Loops and iteration
*You can think of a loop as a computerized version of the game where you tell someone to take X steps in one direction, then Y steps in another. For example, the idea "Go five steps to the east" could be expressed this way as a loop:*

`for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step');
}`

**The statements for loops provided in JavaScript are:**

- for statement
- do...while statement
- while statement
- labeled statement
- break statement
- continue statement
- for...in statement
- for...of statement

**For statement**

*A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop. Syntax:*

`for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement`

 ** When a for loop executes, the following occurs:**

1.  The initializing expression initialExpression, if any, is executed. This expression usually initializes one or more loop counters, but the syntax allows an expression of any degree of complexity. This expression can also declare variables.
2. The conditionExpression expression is evaluated. If the value of conditionExpression is true, the loop statements execute. If the value of condition is false, the for loop terminates. (If the condition expression is omitted entirely, the condition is assumed to be true.)
3. The statement executes. To execute multiple statements, use a block statement ({ ... }) to group those statements.
4. If present, the update expression incrementExpression is executed.
5. Control returns to Step 2.

**The do while statement**

*The do...while statement repeats until a specified condition evaluates to false.*

A do...while statement looks as follows:

`do
  statement
while (condition);`

**While statement**

*A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:*

`while (condition)
  statement`

**labeled statement**

*A label provides a statement with an identifier that lets you refer to it elsewhere in your program. For example, you can use a label to identify a loop, and then use the break or continue statements to indicate whether a program should interrupt the loop or continue its execution.*

The syntax of the labeled statement looks like the following:

`label :
   statement`

   **break statement**

*Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.*

*When you use break without a label, it terminates the innermost enclosing while, do-while, for, or switch immediately and transfers control to the following statement.*

When you use break with a label, it terminates the specified labeled statement.

The syntax of the break statement looks like this:

`break;
break [label];`

**continue statement**

*The continue statement can be used to restart a while, do-while, for, or label statement.*

- When you use continue without a label, it terminates the current iteration of the innermost enclosing while, do-while, or for statement and continues execution of the loop with the next iteration. In contrast to the break statement, continue does not terminate the execution of the loop entirely. In a while loop, it jumps back to the condition. In a for loop, it jumps to the increment-expression.
- When you use continue with a label, it applies to the looping statement identified with that label.

*The syntax of the continue statement looks like the following:*

`continue [label];`

**for...in statement**

*The for...in statement iterates a specified variable over all the enumerable properties of an object. For each distinct property, JavaScript executes the specified statements.*

 A for...in statement looks as follows:

`for (variable in object)
  statement`

  **for...of statement**

*The for...of statement creates a loop Iterating over iterable objects (including Array, Map, Set, arguments object and so on), invoking a custom iteration hook with statements to be executed for the value of each distinct property.*

`for (variable of object)
  statement`


