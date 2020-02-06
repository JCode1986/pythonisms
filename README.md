# Pythonisms

## Author: Joseph Hangarter

### What I have learned with Python Iterators, Generators, Dunder Methods, and Decorators

### Iterators
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

### References:
* [Iterators](https://dbader.org/blog/python-iterators)
* [Generators](https://dbader.org/blog/python-generators)
* [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
* [Decorators](https://realpython.com/primer-on-python-decorators/)
