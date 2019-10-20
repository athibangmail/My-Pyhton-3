## Inheritance
####  Inheritance are the concept of access the super class attributes and methods
-  What is Inheritance?
    - Inheritance is acquire all the attributes and methods from it super class
    - names of parent class -> base class, super class and ancestor class 
    - names of child class -> derived class and  sub class

- Syntax of Inheritance:
    ````
    class DerivedClassName(BaseClassName):
        pass

    ````
- Simple Inheritance:
    ````
    class Robot(object):
        
        def __init__(self, name):
            self.name  = name
        
        def say_hi(self):
            print("Hi This is {}".format(self.name))
    

    class PhysicianRobot(Robot):

        pass

    marvin = PhysicianRobot("Marvin")
    marvin.say_hi()
    "Hi This is Marvin"
    ````
    - in the above example the `name` and `say_hi` attributes are inherited
    from the Robot class

- Difference Between isinstance and type functions
    - Type function will return the class object
    - isinstance will True is if the isinstance belongs to parent class
    ````
    x = Robot("Marvin")
    y = PhysicianRobot("James")
    print(isinstance(x, Robot), isinstance(y, PhysicianRobot))
    print(isinstance(x, PhysicianRobot))
    print(type(y) == Robot , type(y) == PhysicianRobot)
     
    True True
    False
    False True
    ````
- Overriding, Ovewritten and Overloading
    - Overriding is the same method is written in sub class
    and also executed the parent class method
    ````
    class Vehicles(object):
        self.acce = 0.5

        def __init__(self, name):
            self.name = name
        
        def accelerator(self, value)
            self.acce = self.acce + value

    class Bike(Vehicles):
        def accelerator(self, value)
            super().accelerator(value)
            return self.acce
    
    bike = Bike("Hero")
    print(bike.accelerator(20)
    20.5
    ````
- Ovewritten is over write the exiting method, its only execute the sub class function
- OverLoading is not accomplish for python, but still we can do it other way,
it is like same method name with different function
````
def f(x):
    return x+10

def f(x,y):
    return x+y

````
    - above code is error in python instead of added condition in same method
    ````
    def f(x, y=10)
        return x+y
    ````