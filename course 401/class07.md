# Game of Greed Reading Part 2

it happens when you declare variables inside functions and when you try to access them outside this function, you have an error that these variables are not defined, this thing has to do with **scope**, so what is scope ?

*the scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on.*

mainly, there are two general scopes:
- **Global scope**: The names that you define in this scope are available to all your code.

- **Local scope**: The names that you define in this scope are only available or visible to the code within the scope.

![scopes](https://media.geeksforgeeks.org/wp-content/uploads/types_namespace-1.png)

in the picture above indicates the scope (or namespace, almost) process in python and the allowed access to them, clearly, the built-in methods and variable are accessable anywhere in everyone's code . 
- in early programming language, there was only the global scope, which causes lots of errors and problems in the debugging process

- later, languages developed to use scope for solving these problems, so in this case,there’s no way for you to access all the variables in a program at all locations in that program. 

for more understanding, here is this code:

![scopes](https://www.askpython.com/wp-content/uploads/2019/08/python-namespace-example.png)

## Scope VS namespace:

- Python scopes are implemented as dictionaries that map names to objects. 
- These dictionaries are commonly called **namespaces. **

## Using the LEGB Rule for Python Scope

The letters in LEGB stand for Local, Enclosing, Global, and Built-in:

- Local scope is the code block or body of any Python function or lambda expression.

- Enclosing (or nonlocal) scope is a special scope that only exists for nested functions. 

- Global (or module) scope is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module.
- Built-in scope is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. 

![scopes in python](https://apprize.best/python/learning_1/learning_1.files/image022.jpg)

## Modifying the Behavior of a Python Scope
*Python provides two keywords that allow you to modify the content of global and nonlocal names. These two keywords are:*

- global, example:

`counter = 0  # A global name`
`def update_counter():`
    `global counter  # Declare counter as global`

    counter = counter + 1  # Successfully update the counter

update_counter()
counter
output: 1
- nonlocal, example:

`def func():`

    var = 100  # A nonlocal variable

    def nested():
         nonlocal var  # Declare var as nonlocal
         var += 100
    nested()
     print(var)

 `func()`

output: 200

## Bringing Names to Scope With import

the following code shows for an example of what happens when you import some standard modules and names:

`>>> dir()`

`['__annotations__', '__builtins__',..., '__spec__']`

`>>> import sys`

`>>> dir()`

`['__annotations__', '__builtins__',..., '__spec__', 'sys']`

`>>> import os`

`>>> dir()`

`['__annotations__', '__builtins__',..., '__spec__', 'os', 'sys']`

`>>> from functools import partial`

`>>> dir()`

`['__annotations__', '__builtins__',..., '__spec__', 'os', 'partial', 'sys']`

## Discovering Unusual Python Scopes

- **Comprehensions:** A comprehension is a compact way to process all or part of the elements in a collection or sequence. 
- **Exception blocks:**  The exception variable is a variable that holds a reference to the exception raised by a try statement. 
- **Classes and instances:** Unlike functions, the class local scope isn’t created at call time, but at execution time. Each class object has its own .__dict__ attribute that holds the class scope or namespace where all the class attributes live.

## Using Scope Related Built-In Functions

- globals()
- locals()
- dir()
- vars()
