# Testing and Modules
## Recursion
 *recursion is an important method in programming, sometimes it could be confusing, the main concept of it is that the function is calling itself everytime, until it reaches a base-case which should be determined .*

 examples of recursions :

 1. **calculating the factorial**

 `def factorial(n):`

    if x == 1:
        return 1
    else: 
        return n * factorial(n-1)

`print(factorial(4))`

in the example above we are calculating the factorial of 4 for example which is 4! = 4*3!, 3! = 3 * 2!, and so on. Generally, n! = n * (n-1)!.

the **base case** here is 1!=1 .

2. **fibonacci sequence**

`def fibonacci(n):`
	
	if n <= 1:
		return n
	else:
		return (fibonacci(n-1) + fibonacci(n-2))

the fibonacci sequence is the sequence where each number is the sum of the two numbers that precede it. it could be much more complicated to be solved by loops and arrays (I tried it and it wasn't that simple !) but it could be solved easily with recursions .

## __name__="__main__"

- the __name__="__main__" in python refers to how the file is imported
- if __name__ has the value "__main__", it means that it's running that specific module as the source program, but if we want to import from another file, __name__ is set to that module's name
- 

## In Tests We Trust — TDD with Python

sometimes the application that we created work well, but to make sure that everything is perfect and complete, you should create tests, you can test your code by the creating another file for testing, it has the extension .py so it's a normal python code, like if we want to create a program that returns "female" for a certain name you can create it as this in the test file: 

`def test_should_return_female_when_the_name_is_from_female_gender():`

    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’

*you can memorise the AAA structure that helps yoy to write a test python code, which is:*

- **Arrange**: organise the data that you want to test 
- **Act**: the actual code that will test these data
- **Assert**: check if the results = the output



