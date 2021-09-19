> # Pythonisms

# Dunder Methods

## What Are Dunder Methods?

***In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores***

***These “dunders” or “special methods” in Python are also sometimes called “magic methods.”***

    class LenSupport:
        def __len__(self):
            return 42

    >>> obj = LenSupport()
    >>> len(obj)
    42

## Special Methods and the Python Data Model

***This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.***

***Python’s data model as a powerful API you can interface with by implementing one or more dunder methods.***

## Enriching a Simple Account Class

***enrich a simple Python class with various dunder methods to unlock the following language features:***

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)

### Object Initialization:

*Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor:*

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

### Object Representation:

*It’s common practice in Python to provide a string representation of your object for the consumer of your class. There are two ways to do this using dunder methods:*

* __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

* __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

        class Account:
            # ... (see above)

        def __repr__(self):
            return 'Account({!r}, {!r})'.format(self.owner, self.amount)

        def __str__(self):
            return 'Account of {} with starting amount: {}'.format(
                self.owner, self.amount)

### Iteration: 

*In order to iterate over our account object I need to add some transactions.*

    class Account:
        # ... (see above)

        def __len__(self):
            return len(self._transactions)

        def __getitem__(self, position):
            return self._transactions[position]

*To iterate over transactions in reversed order you can implement the __reversed__ special method:*

    def __reversed__(self):
        return self[::-1]

    >>> list(reversed(acc))
    [30, -20, 50, -10, 20]

### Operator Overloading for Comparing Accounts:

    from functools import total_ordering

    @total_ordering
    class Account:
        # ... (see above)

        def __eq__(self, other):
            return self.balance == other.balance

        def __lt__(self, other):
            return self.balance < other.balance

### Operator Overloading for Merging Accounts: 

    def __add__(self, other):
        owner = self.owner + other.owner
        start_amount = self.balance + other.balance
        return Account(owner, start_amount)

### Callable Python Objects:

*can make an object callable like a regular function by adding the __call__ dunder method.*

    class Account:
        # ... (see above)

        def __call__(self):
            print('Start amount: {}'.format(self.amount))
            print('Transactions: ')
            for transaction in self:
                print(transaction)
            print('\nBalance: {}'.format(self.balance))

### Context Manager Support and the With Statement: 

*can leverage the Pythonic with statement by adding two more dunder methods.*

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

# Iterators

## Python Iterators That Iterate Forever

***Over the next few paragraphs we’re going to implement a class called Repeater that can be iterated over with a for-in loop, like so:***

    repeater = Repeater('Hello')
    for item in repeater:
        print(item)

***To start with the implementation we’ll define and flesh out the Repeater class first:***

    class Repeater:
        def __init__(self, value):
            self.value = value

        def __iter__(self):
            return RepeaterIterator(self)

***What’s the RepeaterIterator object we’re creating and returning from __iter__? It’s a helper class we also need to define for our for-in iteration example to work:***

    class RepeaterIterator:
        def __init__(self, source):
            self.source = source

        def __next__(self):
            return self.source.value

## How do for-in loops work in Python?

***To dispel some of that “magic” we can expand this loop into a slightly longer code snippet that gives the same result:***

    repeater = Repeater('Hello')
    iterator = repeater.__iter__()
    while True:
        item = iterator.__next__()
        print(item)

***the for-in was just syntactic sugar for a simple while loop:***

* It first prepared the repeater object for iteration by calling its __iter__ method. This returned the actual iterator object.
* After that, the loop repeatedly calls the iterator object’s __next__ method to retrieve values from it.

## A Simpler Iterator Class

***First setting up and retrieving the iterator object with an iter() call, and then repeatedly fetching values from it via next().***

***Remember why we needed the RepeaterIterator class again? We needed it to host the __next__ method for fetching new values from the iterator. But it doesn’t really matter where __next__ is defined. In the iterator protocol, all that matters is that __iter__ returns any object with a __next__ method on it.***

***That way we could get rid of RepeaterIterator altogether and implement an iterable object with a single Python class. Let’s try it out! Our new and simplified iterator example looks as follows:***

    class Repeater:
        def __init__(self, value):
            self.value = value

        def __iter__(self):
            return self

        def __next__(self):
            return self.value

## Python 2.x Compatible Iterators

***There’s a small but important difference between Python 2 and 3 when it comes to implementing class-based iterators:***

* In Python 3, the method that retrieves the next value from an iterator is called __next__.
* In Python 2, the same method is called next (no underscores).

# Generators

## Python Generators 101 – The Basics

***It implemented a class-based iterator cycling through an infinite sequence of values.***

**This is what the class looked like in its second (simplified) version:**

    class Repeater:
        def __init__(self, value):
            self.value = value

        def __iter__(self):
            return self

        def __next__(self):
            return self.value

***This is where Python’s generators enter the scene.***

    def repeater(value):
        while True:
            yield value

## Python Generators That Stop Generating

***in our class-based iterator we were able to signal the end of iteration by manually raising a StopIteration exception. Because generators are fully compatible with class-based iterators, that’s still what happens behind the scenes.***

***Generators stop generating values as soon as control flow returns from the generator function by any means other than a yield statement.***

    def repeat_three_times(value):
        yield value
        yield value
        yield value

## Python Generators – A Quick Summary

***Generator functions are syntactic sugar for writing objects that support the iterator protocol. Generators abstract away much of the boilerplate code needed when writing class-based iterators.***
    
***The yield statement allows you to temporarily suspend execution of a generator function and to pass back values from it.***
    
***Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.***