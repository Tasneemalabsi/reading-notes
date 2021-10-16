# Game of Greed Reading

## Random Modules in Python
- *Random modules allows you to access many operation, it's used in Python by importing it:*

     `import random`

- *it's used when you want to pick a certain number from a given range* 
- *When making your password database more secure or powering a random page feature of your website.*

### Random Functions:

1. **Randint:** used to get a random number from a given range, it takes two parameters, the high and low values that determine the range. Example:

`import random`

`print random.randint(0, 5)`, the output should be a number from 1 to 5, 0 is not included .

2. **Random:** used for a large range of numbers, Example: 

`import random`

`random.random() * 100` gives a random number from 0 to 100

3. **Choice:** it's used to get a random element from a given list. Example:

`import random`

`random.choice( ['red', 'black', 'green'] ).` the output would be any element from the list .

4. **Shuffle:** shuffles the list elements' order so they would have a random order. Example;

`from random import shuffle`

`x = [[i] for i in range(10)]`

`shuffle(x)`

**Sample output:**

print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]

5. **Randrange:**
Generate a randomly selected element from range, it takes three arguments which are : *(start, stop, step)*.  Example:

`import random`

`for i in range(3):`

    print random.randrange(0, 101, 5)

## Risk Analysis in Software Testing

*Risk Analysis in Software Engineering is the process of analyzing the risks associated with your Testing Project.*

**the possible risks that you developers could encounter:**

- Use of new hardware
- Use of new technology
- Use of new automation tool
- The sequence of code
Availability of test resources for the application

**Risk magnitude indicators:**
- High: when the effect of the risk would be very high and non-tolerable. 

- Medium: it is tolerable. The company may suffer financially but there is a limited risk.

- Low: it is tolerable. There lies little or no external exposure or no financial loss.

**Risk Identification:**

- Business Risks

- Testing Risks

- Premature Release Risk

- Software Risks

### Risk Assessment:

the following graph shows the assessment process 

![risk](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2019/08/Picture1-528x290.png)


### How to perform Risk Analysis?


1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified


## TestCoverage

*Test coverage is a useful tool for finding untested parts of a codebase.*

![test coverage](https://martinfowler.com/bliki/images/testCoverage/sketch.png)

### measure your testcoverage level :
-  The trouble is that high coverage numbers are too easy to reach with low quality testing. At the most absurd level you have **AssertionFreeTesting**.

- TDD is a very useful, but certainly not sufficient, tool to help you get good tests. if you write good and meaningful tests, your tests coverage percentage would be about 80 to 90%

- Certainly low coverage numbers are a sign of trouble. But high numbers don't necessarily mean much, and lead to ignorance-promoting dashboards.

**enough testing will be checked if the two following points is true:**

- You rarely get bugs that escape into production, and
- You are rarely hesitant to change some code for fear it will cause production bugs.





