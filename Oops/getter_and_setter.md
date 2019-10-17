# Python Getter and Setter methods
- Getter function will use to get the attribute value
 and Setter used to set the value into the attribute.

- simple example with getter and setter:
    ````
    class P(object):
        def __init__(self, x):
            self.__x = x
        
        def get_x(self):
            return self.__x

        def set_x(self, x):
            self.__x = x
    p = P(10)
    p.get_x()             
    10                    
    p.set_x(20)           
    p.get_x()             
    20                    
    c = P(30)             
    p.get_x() + c.get_x() 
    50                    
    ````
- the above class is fine but it is look ugly
we can do that with simple class itself
````
    class P(object):
        def __init__(self, x):
            return self.x = x
    p = P(20)
    c = P(30)
    p.x + c.x
````
- Okay!, But there is no data **Encapsulation**,
to access the private attributes python have a 
special decorators
````
 class P():                  
     def __init__(self, x):  
         self.set_x(x)       

     def get_x(self):        
         return self.__x     

     def set_x(self, x):     
         if x < 0 :          
             self.__x = 0    
         elif x > 1000:      
             self.__x = 1000 
         else:               
             self.__x = x    

 c = P(20000)                
 c.get_x()                   
 1000                        
 c.set_x(-29)                
 c.get_x()                   
 0                           
````
- in the above example the x variable no longer available
````
 class P(object):             
                              
     def __init__(self, x):   
         self.x = x           

     @property                
     def x(self):             
         return self.__x     

     @x.setter                
     def x(self, x):          
         if x < 0 :           
             self.__x = 0     
         elif x > 1000:       
             self.__x = 1000  
         else:                
             self.__x = x     
                              
 c = P(303030303)             
 c.x                          
 1000                         
````
-  Any attribute we can add decorators property to change as inside class function
so that we can apply some transformation on the data
````
class Robot:

    def __init__(self, name, build_year, lk = 0.5, lp = 0.5 ):
        self.name = name
        self.build_year = build_year
        self.__potential_physical = lk
        self.__potential_psychic = lp

    @property
    def condition(self):
        s = self.__potential_physical + self.__potential_psychic
        if s <= -1:
           return "I feel miserable!"
        elif s <= 0:
           return "I feel bad!"
        elif s <= 0.5:
           return "Could be worse!"
        elif s <= 1:
           return "Seems to be okay!"
        else:
           return "Great!" 
  
if __name__ == "__main__":
    x = Robot("Marvin", 1979, 0.2, 0.4 )
    y = Robot("Caliban", 1993, -0.4, 0.3)
    print(x.condition)
    print(y.condition)
````