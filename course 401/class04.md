# Classes And Objects

- Objects are an encapsulation of variables and functions into a single entity. 
- Objects are created using classes. The class describes what the object will be, but is separate from the object itself.
- Classes are created using the keyword class and an indented block, which contains class methods. Example :

`class MyClass:`

    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
### Accessing Object Variables

simply you can access a variable from an object by invoke the object.variable, example:

`class MyClass:`

    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

`myobjectx = MyClass()`

`myobjectx.variable`

and `myobjectx.function()` for accessing a function

## Thinking recursively in Python

a recursion is simply a function that repeats itself until we reach a base case that the function stops repeating. So you can think of it as santa clause using his elves to deliver presents as : 

![elves](https://files.realpython.com/media/elves_7.8d1af1cd85c8.png)

so every elf delivers to less houses than the previous one, and that exactly what a recursion in programming could be like, some of the recursive functions are :
1. Factorial:

   `def factorial(n):`

        if n == 1:
            return 1
        else: 
            return n * factorial(n-1)

the factorial function repeats it self until it reaches to the base case that is if n == 1, the answer is one, so 3!=3*2! and so on 

2. Fibonacci: 

`def fibonacci(n):`
	
	if n <= 1:
		return n
	else:
		return (fibonacci(n-1) + fibonacci(n-2))

same as the factorial, the fibonacci function repeats it self until we reach the base case which is if n<=1 return n

3. Lucas sequence:

`def Lucas(n):`
	
	if n = 1:
		return 1
    if n = 0:
		return 2    
	else:
		return (Lucas(n-1) + Lucas(n-2))

the Lucas sequence has the same formula as fibonacci but the base cases are different since the Lucas sequence starts with 2 not 0 as in fibonacci

## Python Testing with pytest

### Fixtures

Fixtures are functions, which will run before each test function to which it is applied. Fixtures are used to feed some data to the tests such as database connections, URLs to test and some sort of input data. Syntax: `@pytest.fixture`

so a fixture in pytest example will be like this : 

`@pytest.fixture`

`def simple_file():`

    return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time. You can do this by passing the scope parameter to the @pytest.fixture decorator:

`@pytest.fixture(scope='module')`

`def simple_file():`

       return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

### Coverage

Coverage in python is a tool for measuring code coverage of Python programs. It monitors your program, noting which parts of the code have been executed, then analyzes the source to identify code that could have been executed but was not.



