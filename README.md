# Pythonisms

## Author: Joseph Hangarter

### What I have learned with Python Iterators, Generators, Dunder Methods, and Decorators

* `__iter__` and `__next__` are very useful if you would like to iterate through an object. Objects that support the `__iter__` and `__next__` dunder methods automatically work with for-in loops.

* Here is an example of using an iterator with a linked list:
```
class LinkedList:

    def __init__(self):
        self.head = None


    def __len__(self):
      return len(list(iter(self)))

    def __iter__(self):

      def generator_func():

        current = self.head

        while current:
          yield current.value
          current = current.next

      return generator_func()
``` 
* Generators are iterators, a kind of iterable you can only iterate over once. Generators do not store all the values in memory, they generate the values on the fly

* `yield` is a keyword that is used like return, except the function will return a generator.
    * when you call the function, the code you have written in the function body does not run. The function only returns the generator object
    * code will continue from where it left off each time for uses the generator
    * The first time the `for` calls the generator object created from the function, it will run the code in your function from the beginning until it hits yield, then it'll return the first value of the loop. Then, each other call will run the loop in the function one more time, and return the next value until there is no value to return.


### References:
* [Iterators](https://dbader.org/blog/python-iterators)
* [Generators](https://dbader.org/blog/python-generators)
* [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
* [Decorators](https://realpython.com/primer-on-python-decorators/)
* [yield] (https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do)
