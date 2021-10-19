# Game of Greed Reading Part 4

## Dunder Methods

*dunder methods are predefined methods that are included in classes, they start whith double under_score*

### Enriching a Simple Account Class

Dunder methods in classes can unlock these features:

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)

Dunder methods examples:

### init
The init method is used to create an instance of the class. Example:

`def __init__(self,names):`

     if names:
        self.names = names.copy()
        for name in names:
            self.versions[name] = 1

  ### str 

  The str method is useful when we want to use instances of our class in a print statement. As discussed earlier, it usually returns a memory object. Example:

  `def __str__(self):`

    s ="The current softwares and their versions are listed below: \n"
    for key,value in self.versions.items():
        s+= f"{key} : v{value} \n"
    return s

### setitem

We can give instances of our class a similar feature with the help of the setitem method. Example:

`def __setitem__(self,name,version):`

    if name in self.versions:
        self.versions[name] = version

### len
In a dictionary, the len method returns the number of elements in a list or the number of key-value pairs in a dictionary.

`def __len__(self):`

      return len(self.names)

The len method for this class returns the number of softwares.  

### getitem

The getitem method is like the setitem method, the major difference being that the getitem method is called when we use the [] operator of a dictionary.

### contains

The contains method is used when using the in operator. The return value has to be a boolean.

`def __contains__(self,name):`

    if name in self.versions:
        return True
    else:
        return False

### add 
The add method is called when using the + operator. We can define a custom add method for our class.

`def __add__(self,p2):`

    x = self.x + p2.x
    y = self.y + p2.y
    return point(x,y)

### iadd

The iadd method is like the add method. It is invoked when using the += operator


### call
When invoking a function like func(), we are invoking the call method.

If we put in place a call method for our class, we can do the following:

`p1()`

`p2()`

Below is an example call method:

`def __call__(self):`

    print(f"Called Point {self.x},{self.y}")

### repr
repr is a built-in function to compute the “official” string representation of an object. If at all possible, this should look like a valid Python expression that could be used to recreate an object with the same value.

#### more dunder methods:

![table](https://miro.medium.com/max/1400/1*7eglYMfJEwMo4qbil2O28g.png)

## Probability in Python

 *that probability theory is mainly concerned with predicting the likelihood of future events, while statistics analyzes the frequency of past events.*

 ### From statistics to probability

he code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed

`import random`

`def coin_trial():`

`heads = 0`

`for i in range(100):`

`if random.random() <= 0.5:`

`heads +=1`

`return headsdef simulate(n):`

`trials = [] for i in range(n):`

`trials.append(coin_trial())`

`return(sum(trials)/n)`

`simulate(10)`

`>>> 5.4`

`simulate(100)`

`>>> 4.83`

`simulate(1000)`

`>>> 5.055`

`simulate(1000000)`

`>>> 4.999781`

### The data and the distribution

The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics. The normal distribution looks like this:

![normal dist](https://i.imgur.com/3vDS2Au.png)

**code example**

`# Extract the Tokaji scores`

`tokaji = []`

`non_tokaji = []`

`for wine in wines:`

`if points != '':`

`points = wine[4]`

`if wine[9] == "Tokaji":`

`tokaji.append(float(points))`

`else:`

`non_tokaji.append(points)`

`# Extract the Lambrusco scores`

`lambrusco = []`

`non_lambrusco = []`

`for wine in wines:`

`if points != '':`

`points = wine[4]`

`if wine[9] == "Lambrusco":`

`lambrusco.append(float(points))`

`else:`

`non_lambrusco.append(float(points))`

### Three Sigma Rule

*The Three Sigma rule, also known as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean.*

![sigma](https://i.imgur.com/Mt3RyE0.png)

### the z-scores
The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?” The equation below is the Z-score equation.

![z-score](https://i.imgur.com/3TuDF4G.jpg)

