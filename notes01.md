# object orientate programming notes 1

I think OPP is awesome!

```python 
# Example

class Person:
    def__init__(self,name):
        self.name = name
        
    def__str__(self):
        return f"Person Object called: (self.name)"
       
    def__repr__(self):
       return self.__str__()
       

```(Tilda button)

## Definitions
-Encapsulation
-Polymorphism
-Override
OOP 1 slideshow notes

# Class: An abstract description of all objects that can be made from this set class where an object can be instantiated from.
# Attributes of the class are the objects accesible tools (What an object could be)
# Feilds: Variables that belong ot an object or a class
# Type 1: It belongs to the instance of the class 
# Type 2: it belongs to the class itself
# methods are functions that the object can call
# remember to Capitilize classname, unlike variables
# after defining the class, add its attributes, then assighn a variable with an instantion of the class to interact with it
# use paranthesis when calling the class name
'''
Example
class Person:
    # block code
# end of the person class
student1 = Person() # student1 is now a person object


'''
# My own class
class Person:
    def __init__(self, name, last, age, height):
        self.name = name
        self.last = last
        self.age = age
        self.height = height
    
    def setbirth(self, birth):
        self.birth = birth
        
          
        
    def setage(self):
        return self.age

person1 = Person('phill', 'shapiro', '17', "6'1")
# person1(me) is now an object
print(person1.setage())
# Calling method
person1.setbirth(2005)
# calling method aswell as setting parameter
print(person1.birth)
print(person1)
# Another class of myself (practice)
class Mee:
    def __init__(self, name, last, height, birth):
        self.first = name
        self.last = last
        self.height = height
        self.birth = birth

person1 = Mee('phillip', 'shapiro', 62, 2005)
print(person1.birth)
# self is now person 1, so person1.first is the same as self.first

OOP2

    
