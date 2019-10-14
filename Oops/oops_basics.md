## Object Oriented Programming
------------------------------
#### Object oriented programming concepts are below
- Encapsulation
- Inheritance
- Data Abstraction
- Polymorphism

#### what is oops?
- Imagine biggest library in the world, example new york library at new york,
there are two way to access the books for users
open shelves and closed shelves, closed shelves are user can not access the books
directly, the staff only can access the books they only give to the people,
here the access is restricted for the users, open shelves are open access 
for every one, so any one can access it, This access like C programming any one can freely 
add the data, here we may see many problems in long runs, But closed access is a object oriented concept
it products the data, it can only access through functions.the shell is called 
"Encapsulation"

- ### First-Class-Everything:
    - in python everything is a class int float, list, dict and so on
    ````
    >>> x = 42
    >>> type(x)
    <class 'int'>
    >>> y = 4.34
    >>> type(y)
    <class 'float'>
    >>> def f(x):
    ...     return x + 1
    ... 
    >>> type(f)
    <class 'function'>
    >>> import math
    >>> type(math)
    <class 'module'>
    >>> 
    ````

- Difference between `__str__` and `__repr__`
    - `__str__` will return the string we can not evaluate as object again
    but `__repr__` we can evaluate to class again.
    - example with only `__repr__` function.
    ````
    >>> class my_class():
    >>>     def __init__(self):
    >>>         self.name = "Robot"
    >>>     def __repr__(self):
    >>>         print ("My Name is "+str(self.name))
    >>>

    >>> cls = my_class()
    >>> cls_s = str(cls)
    'My Name is Robot'
    >>>cls_e = eval(cls_s)
     <class '__main__.my_class'>

    ````
    - example with only `__str__` function
    ````
    >>> class my_class():
    >>>     def __init__(self):
    >>>         self.name = "Robot"
    >>>     def __str__(self):
    >>>         print ("My Name is "+str(self.name))
    >>>

    >>> cls = my_class()
    >>> cls_s = str(cls)
    'My Name is Robot'
    >>>cls_e = eval(cls_s)
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    File "<string>", line 1
        My Name is Robot
            ^
    SyntaxError: invalid token
    ```` 
