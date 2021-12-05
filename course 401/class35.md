# Pythonisms

## Dunder Methods

Magic methods in Python are the special methods that start and end with the double underscores. They are also called dunder methods. Magic methods are not meant to be invoked directly by you, but the invocation happens internally from the class on a certain action. For example, when you add two numbers using the + operator, internally, the `__add__()` method will be called.

### Enriching a Simple Account Class

*Some dunder methods to unlock the following language features:*

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)

### Object Initialization: __init__

**Example:**

```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []

```

### Object Representation: __str__, __repr__

**There are two ways to do this using dunder methods:**

1. `__repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

2. `__str__`: The “informal” or nicely printable string representation of an object. This is for the enduser.

```
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
```

### Iteration: __len__, __getitem__, __reversed__

In order to iterate over our account object I need to add some transactions. 

```
def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)
```

### Operator Overloading for Comparing Accounts: __eq__, __lt__

*The object type `__eq__` method, compares two objects for equality, by comparing their id, which is their memory address.*

When we use objectOne == ObjectTwo, and if objectOne is an ancestor of ObjectTwo, then ObjectTwo `__eq__` method is called, otherwise objectOne `__eq__` method is called.

```
class Implements_Eq:
    def __eq__( self , other):
        return True
```

When performing x < y, or x > y, or x <= y, or x >= y in python, this amounts to calling y `__gt__`, `__lt__`, `__ge__`, and `__le__` methods

```
class Implements_Lt:
    def __lt__( self, other):
        return True
```

### Operator Overloading for Merging Accounts: __add__

Let’s implement `__add__` to be able to merge two accounts. The expected behavior would be to merge all attributes together: the owner name, as well as starting amounts and transactions. 

```
def __add__(self, other):
    owner = '{}&{}'.format(self.owner, other.owner)
    start_amount = self.amount + other.amount
    acc = Account(owner, start_amount)
    for t in list(self) + list(other):
        acc.add_transaction(t)
    return acc
```

### Callable Python Objects: __call__

*You can make an object callable like a regular function by adding the `__call__` dunder method.*

```
class Account:
    # ... (see above)

    def __call__(self):
        print('Start amount: {}'.format(self.amount))
        print('Transactions: ')
        for transaction in self:
            print(transaction)
        print('\nBalance: {}'.format(self.balance))
```

### Context Manager Support and the With Statement: __enter__, __exit__

We can leverage the Pythonic with statement by adding two more dunder methods. I’m also adding some print calls to make the example clearer when we demo it:

```
class Account:
    # ... (see above)

    def __enter__(self):
        print('ENTER WITH: Making backup of transactions for rollback')
        self._copy_transactions = list(self._transactions)
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('EXIT WITH:', end=' ')
        if exc_type:
            self._transactions = self._copy_transactions
            print('Rolling back to previous transactions')
            print('Transaction resulted in {} ({})'.format(
                exc_type.__name__, exc_val))
        else:
            print('Transaction OK')
```           

## Iterators

*Python Iterators That Iterate Forever*

We’ll begin by writing a class that demonstrates the bare-bones iterator protocol in Python. 

```
repeater = Repeater('Hello')
for item in repeater:
    print(item)
```

*To start with the implementation we’ll define and flesh out the Repeater class first:*

```
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self)
```

RepeaterIterator looks like a straightforward Python class, but you might want to take note of the following two things:

- In the `__init__` method we link each RepeaterIterator instance to the Repeater object that created it. That way we can hold on to the “source” object that’s being iterated over.

- In RepeaterIterator.`__next__`, we reach back into the “source” Repeater instance and return the value associated with it.

### How do for-in loops work in Python?

To dispel some of that “magic” we can expand this loop into a slightly longer code snippet that gives the same result:

```
repeater = Repeater('Hello')
iterator = repeater.__iter__()
while True:
    item = iterator.__next__()
    print(item)
```    

the for-in was just syntactic sugar for a simple while loop:

- It first prepared the repeater object for iteration by calling its `__iter__` method. This returned the actual iterator object.
- After that, the loop repeatedly calls the iterator object’s `__next__` method to retrieve values from it.

### A Simpler Iterator Class

That way we could get rid of RepeaterIterator altogether and implement an iterable object with a single Python class. Let’s try it out! Our new and simplified iterator example looks as follows:

```
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value
```        

### Python 2.x Compatible Iterators

- In Python 3, the method that retrieves the next value from an iterator is called `__next__`.
- In Python 2, the same method is called next (no underscores).

```
class InfiniteRepeater(object):
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value

    # Python 2 compatibility:
    def next(self):
        return self.__next__()

```

### Iterators Summary

- Iterators provide a sequence interface to Python objects that’s memory efficient and considered Pythonic. Behold the beauty of the for-in loop!
- To support iteration an object needs to implement the iterator protocol by providing the `__iter__` and `__next__` dunder methods.
- Class-based iterators are only one way to write iterable objects in Python. Also consider generators and generator expressions.

## Generators

Python provides a generator to create your own iterator function. A generator is a special type of function which does not return a single value, instead, it returns an iterator object with a sequence of values. In a generator function, a yield statement is used rather than a return statement. 

```
def mygenerator():
    print('First item')
    yield 10

    print('Second item')
    yield 20

    print('Last item')
    yield 30
```

In the above example, the mygenerator() function is a generator function. It uses yield instead of return keyword. So, this will return the value against the yield keyword each time it is called. However, you need to create an iterator for this function, as shown below.

Example: next() 

```
>>> gen = mygenerator() 
>>> next(gen) 
First item 
10                      
>>> next(gen) 
Second item 
20                      
>>> next(gen) 
Last item 
30 
```


### Using for Loop with Generator Function
The generator function can also use the for loop.

**Example**

```
def get_sequence_upto(x):
    for i in range(x):
        yield i
```

As you can see above, the get_sequence_upto function uses the yield keyword. The generator is called just like a normal function. However, its execution is paused on encountering the yield keyword. 

### Generator Expression

Python also provides a generator expression, which is a shorter way of defining simple generator functions. The generator expression is an anonymous generator function. The following is a generator expression for the square_of_sequence() function.

Example: 

`squres = (x*x for x in range(5))`