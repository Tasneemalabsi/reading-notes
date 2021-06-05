# Programming with JavaScript
## Control flow
The control flow is the order in which the computer executes statements in a script.

*Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.*

*Example:*

`if (field==empty) {
promptUser();
} else {
    submitForm();
}`

For example, the above excerpt might be inside a function that runs when the user clicks the Submit button for the form. The function could also include a loop, which iterates through all of the fields in the form, checking each one in turn. Looking back at the code in the if and else sections, the lines promptUser and submitForm could also be calls to other functions in the script. As you can see, control structures can dictate complex flows of processing even with only a few lines of code.

* So Control flow means that when you read a script, you must not only read from start to finish but also look at program structure and how it affects order of execution.*

## JavaScript functions
A JavaScript function is a block of code designed to perform a particular task.

A JavaScript function is executed when "something" invokes it (calls it).

*Example*

`function myFunction(p1, p2) {
  return p1 * p2;  
}`

**This function returns the product of p1 and p2 (you can add this as a comment inside the function by using //**
### JavaScript Function Synta:
`function name(parameter1, parameter2, parameter3) {
  // code to be executed
}`

 *Function parameters are listed inside the parentheses () in the function definition.*

*Function arguments are the values received by the function when it is invoked.*

*Inside the function, the arguments (the parameters) behave as local variables.*

### Function Invocation
The code inside the function will execute when "something" invokes (calls) the function:

- When an event occurs (when a user clicks a button)
- When it is invoked (called) from JavaScript code
- Automatically (self invoked)

### Function return:
*When JavaScript reaches a return statement, the function will stop executing.*

*Functions often compute a return value. The return value is "returned" back to the "caller":*

var x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}

** Functions Used as Variable Values**

*Functions can be used the same way as you use variables, in all types of formulas, assignments, and calculations.*
 for example, you can this function

 `var text = "The temperature is " + toCelsius(77) + " Celsius";`

  Instead of using variables to store the return of the function:

  `var x = toCelsius(77);
var text = "The temperature is " + x + " Celsius";`

### Local Variable:
*Variables declared within a JavaScript function, become LOCAL to the function.*

*Local variables can only be accessed from within the function. Example:*

`function myFunction() {
  var carName = "Volvo";
  // code here CAN use carName
}`

Outside this specific code, you cannot use the variable carName with its value that is defined inside the function myFunction.
#### JavaScript Operators
1. JavaScript Arithmetic Operators

Operator	Description:

- (+) for Addition
- (-) for	Subtraction
- (*) for	Multiplication
- (**) 	Exponentiation (ES2016)
- (/) for	Division
- (%)	for Modulus (Division Remainder)
- (++) for Increment
- (--) for	Decrement
2. JavaScript Assignment Operators:

| Operator     |Example |Example | 
| ----------- | ----------- |
| =    | x=y     | x=y     |
| +=  | 	x += y     |	x = x + y|
| -=  | 		x -= y   |x = x - y
| *=   |	x *= y|	x = x * y   |
| /=|	x /= y|	x = x / y|
|%=	|x %= y|	x = x % y
|**=	|x **= y|	x = x ** y    |

3. JavaScript String Operators

*The + operator can also be used to add (concatenate) strings. Example:*

var txt1 = "John";

var txt2 = "Doe";

var txt3 = txt1 + " " + txt2;

**The result will be John Doe**

4. JavaScript Comparison Operators

|operator     | Description |
| ----------- | ----------- |
| ==	|equal to     |
| ===	|equal value and equal type       |
| !=	|not equal       |
| !==	|not equal value or not equal type        |
|     >|	greater than       |
|<|	less than       |
| >=|	greater than or equal to        |
|    <=	|less than or equal to       |
|?	|ternary operator       |

4. JavaScript logical operator

| operator      | Description |
| ----------- | ----------- |
| &&|	logical and       |
| ll (acatually it's the vertical bar not the letter l but I coudn't write them because of the table structure|	logical or       |
| !	|logical not       |

5. JavaScript Type Operators

| Operator   | Description |
| ----------- | ----------- |
| typeof|	Returns the type of a variable       |
| instanceof	Returns true if an object is an instance of an object type        |


