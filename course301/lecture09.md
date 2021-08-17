# FUNCTIONAL PROGRAMMING

## What is functional programming ?

*Functional programming is a programming paradigm  a style of building the structure and elements of computer programs that treats computation as the evaluation of mathematical functions and avoids changingstate and mutable data*

## Pure Functions 

**how do we know if a function is pure or not?**

Here is a very strict definition of purity:
- It returns the same result if given the same arguments (it is also referred as deterministic)
- It does not cause any observable side effects

### Pure functions benefits

*The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:*
- Given a parameter A → expect the function to return value B
- Given a parameter C → expect the function to return value D

*A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.*

`let list = [1, 2, 3, 4, 5];`

`const incrementNumbers = (list) => list.map(number => number + 1);`

## Immutability

*Unchanging over time or unable to be changed.*

**In Javascript we commonly use the for loop. This next for statement has some mutable variables.**

`var values = [1, 2, 3, 4, 5];`

`var sumOfValues = 0;`

`for (var i = 0; i < values.length; i++) {`
  
  `sumOfValues += values[i];`

`}`


`sumOfValues // 15`

For each iteration, we are changing the i and the sumOfValue state. But how do we handle mutability in iteration? Recursion!

`let list = [1, 2, 3, 4, 5];`

`let accumulator = 0;`

`function sum(list, accumulator) {`
  
  `if (list.length == 0) {`
    
    return accumulator;
  
  `}`

  `return sum(list.slice(1), accumulator + list[0]);`

`}`

`sum(list, accumulator); // 15`

`list; // [1, 2, 3, 4, 5]`

`accumulator; // 0`

 **Recursion**  means defining a problem in terms of itself". This can be a very powerful tool in writing algorithms.

 **Parts of a Recursive Algorithm**

- All recursive algorithms must have the following:

- Base Case (i.e., when to stop)

- Work toward Base Case

- Recursive Call (i.e., call ourselves)

## Functions as first-class entities

*The idea of functions as first-class entities is that functions are also treated as values and used as data.*

Functions as first-class entities can:

- refer to it from constants and variables
- pass it as a parameter to other functions
- return it as result from other functions

The idea is to treat functions as values and pass functions like data. 
### Higher-order functions

When we talk about higher-order functions, we mean a function that either:
- takes one or more functions as arguments
- returns a function as its result

## Filter

Given a collection, we want to filter by an attribute. The filter function expects a true or false value to determine if the element should or should not be included in the result collection.
 Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not.

*A simple example is when we have a collection of integers and we want only the even numbers.*

**Imperative approach**

An imperative way to do it with Javascript is to:

- create an empty array evenNumbers
- iterate over the numbers array
- push the even numbers to the evenNumbers array

`var numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];`

`var evenNumbers = [];`

`for (var i = 0; i < numbers.length; i++) {`

  `if (numbers[i] % 2 == 0) {`
    
    evenNumbers.push(numbers[i]);
  
  `}`

`}`

`console.log(evenNumbers); // (6) [0, 2, 4, 6, 8, 10]`

We can also use the filter higher order function to receive the even function, and return a list of even numbers:

`const even = n => n % 2 == 0;`

`const listOfNumbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];`

`listOfNumbers.filter(even); // [0, 2, 4, 6, 8, 10]`






