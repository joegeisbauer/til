# Decorators

Decorators are clsoures in python that take on the function name they wrap in Python. There are three things one needs for a closure in Python:

 * A nested function in an enclosing function.
 * A nonlocal object from the enclosing function that is accessed in the nested function.
 * The enclosing function must return the nested function

 So below is the setup for a decorator that prints "Decorated Function" upon the function is wraps.

 ```python
 def func_decorator(func):

     def inner():
         print("Decorated Function")
         func()
    return inner

def say_hello():
    print("Hello World!\n")

@func_decorator
def say_hello2():
    print("Hello World!\n")

if __name__ == "__main__":

    say_hello()
    print()
    say_hello2()
```

Notice the functions `say_hello` and `say_hello2` are identical except for the decorator in `say_hello2`. In the above example, the eclosing function is `func_decorator` and the nested function is `inner`. The nonlocal object that is referenced is also a function. It is `func` in the definition of the decorator.