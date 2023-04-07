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

OOP 1 SLIDESHOW NOTES

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

# Slideshow 2
# Encapsulation: information hiding, restricting acces to certain variables.
# we can restrict certain methods to be callable
# Example
'''
class Student:
    
    def __init__(self, first, last, num):
        self.first = first
        self.last = last
        self.__num = num
    def getStudentNumber(self):
        return self.__num
s1 = Student('Mr', 'Park', 10)
print(s1.last)
s1.last = 'hello'
print(s1.last)
'''
'''
class Student:
  def __init__(self,nameF, nameL, num):
    self.__firstName = nameF
    self.__lastName = nameL
    self.__studentNumber = num
  
  def setFirstName(self, newName):
    self.__firstName = newName
# sets new name 
  def getFirstName(self):
    return self.__firstName
# prints new name
# need to set new name first

s1 = Student('phill', 'shapiro', 10)

s1.setFirstName('crill')
print(s1.getFirstName())
# Is this overriding?
'''
# Overriding is when two methods with the same method name and parameters
# OVerloading is when two methods in one class that have the sam method name, but different parameters
# One method is in the parent class (lesson 3)
# One method is in the child class (lesson 3)
# Overriding allows the child class to provide specific implementation for a method that exists in the parent class
# You can also override built-in magic-methods. OR Base-functions
# there is no overloading in pyhthon 3
# Polymorphism is a method that can be used across different classes and object that is dependent on parameters
# poly - many
# morphism - forms
# Different Classes (non-inherited) can have the same named methods (Simple) → Polymorphism Within a set of inherited classes have the same methods
# Example
class Bear:
    def sound(self):
        print("Groarrr")
 
class Dog:
    def sound(self):
        print("Woof woof!")
 
def makeSound(animalType):
    animalType.sound()
bearobj = Bear
dogobj = Dog
print(makeSound(bearobj))
makeSound(dogobj)
# Giving two different classes same method

# WHY DOES THE CODE NOT WORK?

# Polymorphism is a method that can be used across 

# Two different classes have the same attributes and methods
# For example a child of parent have an override method where the child would utilize the method differently 
# these are the two fundamnetal concepts of overriding and polymorphism in pytin 
class Dog:
	def __init__(self,name):
        # the __ is an example of e
		self.__name = name
	
	def __str__(self): # allows us to convert our object into a string
		return “Woof, I’m %s.” % self.__name

corgi = Dog(“Tobasco”)
print(corgi) → “Woof, I’m Tobasco.”
# important because we can use this concept to complete mathematical operations on custom objects, we can also compare between custom objects
# __repr__() returns a string that contains a printable version of our object, basicly allows us to print our object.
# __str__ = allows us to convert our object to a string

CLASS DOG

class Dog:
    ''' Dog conceptualizes possible attributes and methods that a Dog can have to represent an idea of a Dog through programming

    Attributes:
        name: the name for the Dog
        breed: the breed for the Dog
        age: positive integer age for the Dog
        
    '''

    def __init__(self, given_name, breed, age):
        ''' Initializes the dog by providing its name, breed and age

        Arg:
            name: the name for the Dog
            breed: the breed for the Dog
            age: positive integer age for the Dog
        '''
        self.name = given_name
        self.breed = breed
        self.age = age

    def bark(self):
        ''' This gives Dogs an ability to bark: will output Woof! '''
        print('Woof!')

    def eat(self, food):
        print(f'{self.name} is eating {food}')

    def __str__(self):
        ''' This is a __str__() base override to give our Dog Objects a string equivalent value. This allows our Dogs to type casted to strings.'''
        return f'A {self.breed} named {self.name} with an age of: {self.age}.'

    def __repr__(self):
        ''' Making our Dog Objects being representable in other objects. This is done by overriding __repr__()'''
        return self.__str__()
 MAIN DOG
# Using Dog Class in our code

# import our dog.py to access our Dog Class
from dog import Dog

# Create an instance of a Dog Object
dog1 = Dog('Marshall', 'Westie', 3)
dog2 = Dog('Freya', 'Samoyed', 3)
dog3 = Dog('Goji', 'Mutt', 2)

# Dog Class provides a .bark() method
dog1.bark()
dog2.bark()
dog3.bark()

# Since the Dog Class had __str__() and __repr__() overrides, they are printable
print(dog1)
print(dog2)
print(dog3)
CLASS CAT
from random import choice # importing a choice method from the random module

class ScratchPost:
    def __init__(self):
        self.hp = 10

    def use(self):
        if self.hp <= 0:
            return False
        else:
            self.hp = self.hp - 1 # self.hp -= 1
            return True

    def __str__(self):
        return f'A Scratch Post. HP: {self.hp}.'

    def __repr__(self):
        return self.__str__()

class Cat:
    def __init__(self, name, breed, colour):
        self.name = name
        self.breed = breed
        self.colour = colour
        self.is_hungry = choice([True, False])
        self.want_to_scratch = choice([True, False])

    def eat(self, food_name):
        if self.is_hungry:
            print(f'{self.name} ate {food_name}.')
            self.is_hungry = False
        else:
            print(f'{self.name} is not hungry.')

    def scratch(self, post):
        if self.want_to_scratch:
            if post.use():
                self.want_to_scratch = False
                print(f'{self.name} scratched {post}.')
            else:
                print(f'{post} is dead.')
        else:
            print(f'{self.name} does not need to scratch.')

    def __str__(self):
        return f'A {self.breed} cat named {self.name}.'

    def __repr__(self):
        return self.__str__()
MAIN CLASS CAT
from cat import Cat # Cat class from cat.py
from cat import ScratchPost # ScratchPost class from cat.py

post = ScratchPost() # a scratchpost object (class instance)
cat1 = Cat('Cheetos', 'Tabby', 'Orange') # a cat object

# cat data
print(cat1)

# post data
print(post)

# is cat1 hungry?
print(cat1.is_hungry) # accessing an attribute: .is_hungry
cat1.eat('tuna')

# does cat1 need to scratch?
print(cat1.wants_to_scratch) # accessing an attribute ._wants_to_scratch
cat1.scratch(post) # cat object interacting with a post object

# rechecking post data
print(post)

OOP 3

# inheritance
# when I see a bird that walks like a duck and swims like a duck that bird is a duck to me
# Inheritance is when an object or class is based on another class; where its features are from a parent class
# types of inheritance:
# single inheritance:  a subclass inheriting the features of a single superclass.
# multple  inheritance: a subclass inheriting the features of a multiple parent class.
# multi level: inheriiting from an inheritad class A - B - C
# can have a hirechy
# what does is it do? child gets attributes from parent, we can than enhance those attrinutes with new ones, and new methods.
#child can override attributes and methods for their own liking
# the child class does not need new __init__ function, unless it requires new attributes
'''
example of single inheritnace
class ParentClassName:
	“”” Define Parent Class “””
	.
	.
	.

class InheritanceClass(ParentClassName):
	“”” Define Inherited Class “””

	def __init__(self, param, param2):
		ParentClassName.__init__(self, param)
		self.param2 = param2
'''
# what is super() = is a built in function to refer their paren class. It prevents us fromdoing ParentClass.method(self)
# Inheritance extended 
# multi generational : grand - parent - Child
# multiparent = PA and Pb = Child
# is a mixture of A and B essentially 

# polymorphism is method that can be used across differnt classes and object that is dependent on the parameters

    
