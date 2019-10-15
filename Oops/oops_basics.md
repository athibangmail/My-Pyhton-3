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

- Counter with class
    ````
    In [1]: # Create a class with below three points

    In [2]: # 1.Counter will count th number of instances

    In [3]: # 2. Increment the count if new instance was created

    In [4]: # 3. decrement the count if any instance deleted

        In [9]: class Counter():
    ...:     counter = 0
    ...:     def __init__(self):
    ...:         type(self).counter += 1
    ...:     def __del__(self):
    ...:         type(self).counter -=1
    ...:

    In [10]: a = Counter()

    In [11]: print("Total No of instance are {}".format(Counter.counter)
        ...: )
    Total No of instance are 1

    In [12]: b= Counter()

    In [13]: print("Total No of instance are {}".format(Counter.counter))
    Total No of instance are 2

    In [14]: c = Counter()

    In [15]: print("Total No of instance are {}".format(Counter.counter))
    Total No of instance are 3

    In [16]: del c

    In [17]: print("Total No of instance are {}".format(Counter.counter))
    Total No of instance are 2

    In [18]: del b

    In [19]: print("Total No of instance are {}".format(Counter.counter))
    Total No of instance are 1

    In [20]: del a

    In [21]: print("Total No of instance are {}".format(Counter.counter))
    Total No of instance are 0
    ````
    - in the above code increment and decrement used type(self)
    it the current class 

- Static Method:
    - Static method's are the instance method which defines inside the class
    we can read the private data's
    ```
        class Robot():
            __counter = 0

            def __init__(self):
                type(self).__counter += 1
            
            def Robotinstances(self):
                return Robot.__counter
    ```
    -  the above class example is a instance method which return the count
    but there are two problem here:
    1. we can't call int instance method before instance was created,
    2. The number of robots nothing to do with a single robots instance

    -  you will get a error if run the below code
    ````
    >>> Robot.Robotinstances()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    TypeError: RobotInstances() takes exactly 1 argument (0 given) 
    ````
    one solution to remove the self parameter in RobotInstances
    ````
    class Robot():
            __counter = 0

            def __init__(self):
                type(self).__counter += 1
            
            def Robotinstances():
                return Robot.__counter
    ````
    -  now we can call the method using class but this will not work 
    through instance call
    ````
    >>> from static_methods2 import Robot
    >>> Robot.RobotInstances()
    0
    >>> x = Robot()
    >>> x.RobotInstances()
    Traceback (most recent call last):

    File "<stdin>", line 1, in <module>
    TypeError: RobotInstances() takes no arguments (1 given)
    >>> 
    ````
    - The call x.RobotInstances() is now passing the instance class as first parameter
    - There is a solution for this problem we can make a instance method as static method
        which allows a both the ways
    ````
    In [31]: class Robot():
    ...:     __counter = 0
    ...:     def __init__(self):
    ...:         type(self).__counter += 1
    ...:
    ...:     @staticmethod
    ...:     def Robotinstance():
    ...:         return Robot.__counter
    ...:
    ...:

    In [32]: Robot.Robotinstance()
    Out[32]: 0

    In [33]: x = Robot()

    In [34]: x.Robotinstance()
    Out[34]: 1
    ````
- Class Method:
   Don't be confused with the class method and static method
   both are bound to the class not instance.the first parameter
   is used for the class method is refer to class instance.

   ````
    In [44]: class Robot():
    ...:     __counter = 0
    ...:     def __init__(self):
    ...:         type(self).__counter += 1
    ...:
    ...:     @classmethod
    ...:     def Robotinstance(cls):
    ...:         return Robot.__counter
    ...:
    ...:
    In [45]: Robot.Robotinstance()
    Out[45]: 0
    
    In [46]: x = Robot()

    In [47]: x.Robotinstance()
    Out[47]: 1
   ````