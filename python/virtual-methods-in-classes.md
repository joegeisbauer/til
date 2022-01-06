# Virtual Methods in Classes

In C++, one can define a virtual method in a parent class as a placeholder for a method that needs to be defined in the child class. It turns out it is really easy to do this in Python as well. You can do this as follows.

```python
class Parent(object):

    def __init__(self):
        print("The parent class is instantiated.")

    def virtual_method(self):
        raise NotImplementedError


class Child(Parent):

    def __init__(self):
        super().__init__()
        print("The child class is instantiated".)

    def virtual_method(self):
        print("The child class defined this method!")
```

That is it. You can run this code in an `ipython3` environment or from a script, and see how things work as well as the order things are run. If you want to see what happens when the `virtual_method` is not defined in the child class, then you can comment out the method definition in the child class and run the script.