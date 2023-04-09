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








DOG CLASS

# class dog
class Dog:
    def __init__(self, name, age, breed):
        self.name = name
        self.age = age
        self.breed = breed
    def speak(self):
        print('woof')
    def eat(self, food):
        print(f'{self.name} is eating {food}')
    def __str__(self):
    # is a base override that represent the class object as a string.
        return f'a {self.breed} named {self.name} with an age of {self.age}'
    
    def __repr__(self):
        # returns the official representation of the object.
        return self.__str__()

MAIN DOG

from dog import Dog

d1 = Dog('tim', 19, 'golden')
print(d1)






CAT CLASS

from random import choice
class Scratch_post:
    def __init__(self):
        self.hp = 10
    def use(self):
        if self.hp > 0:
            self.hp -= 1
            return True
        else:
            return False
    def __str__(self):
        return f' scratches left {self.hp}'
    def __repr__(self):
        return self.__str__()
class Cat:
    def __init__(self, name, breed, color):
        self.name = name
        self.breed = breed
        self.color = color
        self.is_hungry = choice([True, False])
        self.want_to_scratch = choice([True, False])
    def eat(self, food):
        if self.is_hungry == True:
            print(f'{self.name} is eating {food}')
        else:
            print(f'{self.name} is not hungry')
    def scratch(self, p):
        # p is a object from the Scratch_post class.
        if self.want_to_scratch == True:
            p.use()
            self.want_to_scratch == False
            print(f'{self.name} scratched the post')
        else:
            print(f'{self.name} does not want to scratch')
    def __str__(self):
        return f'a {self.breed} cat named {self.name}'
    def __repr__(self):
        return self.__str__()
 
CAT CLASS MAIN

from cat import Cat
from cat import Scratch_post
c = Cat('jill', 'golden', 'brown')
p = Scratch_post()


c.eat('tuna')
c.scratch(p)
# printing the p object after the method is used to check the hp.
print(p)
print(c)







ENCAPSULATION

# Encapsulation is restricting the access to the classes/objects certain attributes and methods. We use (__) to do this.

class Student:
    def __init__(self, name, last, num):
        self.name = name
        self.last = last
        
        self.__StudentNumber = num
        # self.__StudentNumber is an ecapsulated attribute
    def __getStudentNUmber(self):
        # __getStudentNUmber is an encapsulated method
        return self.__StudentNumber

s1 = Student('mr', 'park', 10)

print(s1.name)

s1.name = "ms"

print(s1.name)
# will now print 'ms' as we mutated the variable.

print(s1.__getStudentNUmber()) # Causes an error because the method '__getstudentNumber' has encapsulation. if it did not have __, then the number would print.

print(s1.__StudentNUmber) # causes error because the attribute is private.

# HOW TO ACCESS ENCAPSULATED ATTRIBUTES
class Person:
    def __init__(self, name):
        self.__name = name
    def set_name(self, newname):
        self.__name = newname
    def getname(self):
        print(self.__name)

# The getter and setter method will allow us to access encapuslated attributes.
    

p1 = Person('jimmy')
p1.set_name('candy')
p1.getname()









OVERRIDING

# Overloading: is two methods in one class that have the same method name, but differernt parameters.

# Overriding: two methods with the same method name and parameter.abs

'''
-One method is in the parent class (lesson 3)
-One method is in the child class (lesson 3)
-Overriding allows the child class to provide specific implementation for a method that exists in the parent class
-You can also override built-in magic-methods. OR Base-functions
NOTE: There are NO OVERLOADING IN Python 3.
'''

class Animal:
    def eat(self):
        print('this animal is eating')

# rabbit inehrates from the Animal class, therefore it is the child class

# because of inehatince the rabbit class has access to the .eat() method in the animal class.
class Rabbit(Animal):
    def eat(self):
        print('the rabbit is eating carrots')
        # this is ovverriding the .eat() method in the parent class and then providing a more specific implementation.

r = Rabbit()
r.eat()
# will print out the .eat() method in the Rabbit class which is the more specific implementation of the method.








BASE OVERRIDES

# Base Overrides

# two different classes can have the same attributes and methods.

# a child class and parent class have an overrided method, where the child class utilizes the parent method differntly (Example in Overriding.py)

# EXAMPLE

class Dog:
    def __init__(self, name):
        self.__name = name
    def __str__(self):
        return f'woof I am {self.__name}'
    # dont have to call the __str__ function. It is a base override in python that makes our object readable.
d = Dog('jimmy')
print(d)

# __repr__(object) returns a strong containing a printable represntation of an object.

# __str__() allows us to convert out object to a string.

# __repr__() allows us to present a printable version of our object.









POLYMORPHISM

# Polymorphism: is a method that can be used across different classes and objects that is dependent on the parameters.

# - Different Classes (non-inherited) can have the same named methods (Simple) → Polymorphism
# - Within a set of inherited classes have the same methods

# EXAMPLE

class Bear:
    def sound(self):
        print('groar')
class Dog:
    def sound(self):
        print('woof woof')
def makesound(animalType):
    animalType.sound()

b = Bear()
d = Dog()
makesound(b)
makesound(d)
# in conclusion we gave two differnt classes same methods, hence polymorphism.

# Overriding is also an example of Polymorphism

class Person:
    def __init__(self, name, age):
        self.__name = name
        self.__age = age
    def show(self):
        return self.__name
    def show(self, num):
        return f'{self.__name}, {self.__age}'

# the show method is presented twice in one class and has different parameters hence overloading.
  
  
  
  





INHERITANCE

# Inheritance is when an object or class is based another class; where its features are from a parent class

'''
Types:

- Single Inheritance: a subclass inheriting the features of a single superclass/parent class.
- Multiple inheritnace: a subclass inheriting the features of a multiple parent class
- Multilevel inheritnace: a subclass inheriting from another subclass A - B - C.
'''

# What can we do with inheritance: a child will recieve all attributes and methods of the parent.

# the child can than enhance itself with new attributes and methods. The child can also OVERRIDE attributes and methods for their own liking.

# if a child class inherits the parent class: the child does not need a new __init__() unless it requires new attributes.

# the child does not need to reinstate the parents methods unless you override them.

#EXAMPLE
class Parent:
    def __init__(self, name):
         self.__name = name
    def getname(self):
        return self.__name

# Child class
class Child(Parent):
    def __init__(self, name, num):
        Parent.__init__(self, name)
        self.__num = num
    def getChildname(self):
        return f'{self.__num}, {self.getname()}'
        # using the method 'self.getname()' from the parent class.
p = Parent('jill')
c = Child('hello' ,19)
print(c.getChildname())  
print(p.getname())
print(c.getname())

# What is super(): is a built in method for classes to refer to their parent class.

class Parent:
    def __init__(self, name):
         self.__name = name
    def getname(self):
        return self.__name

# Child class
class Child(Parent):
    def __init__(self, name, num):
        super().__init__(name)
        #
        self.__num = num
    def getChildname(self):
        return f'{self.__num}, {self.getname()}'
        # using the method 'self.getname()' from the parent class.
p = Parent('jill')
c = Child('hello' ,19)
print(c.getChildname())  
print(p.getname())
print(c.getname())
# using method from parent class for our child object (another class).



# inheritance video
class Dog:
    def __init__(self, name, age, friendliness):
        self.name = name
        self.age = age
        self.friendliness = friendliness
    
    def like_walks(self):
        return True
# "class Samoyed(Dog)" this means that samoyed is a child class of the class Dog.
class Samoyed(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
        # what this means is that it calls the initlization (__init__) from the superclass.

         
    
    

class Poodle(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
         # because of super we dont need to reset attributes
            # Ex: self.name = name
    def shedding_amount(self):
        return 0
        


        

class Golden(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
    def fetch_ability(self):
        if self.age < 2:
            return 8
        elif self.age < 10:
            return 10
        else:
            return 7 


d = Samoyed('sammy', 2, 10)
print(d.name, d.age, d.friendliness)
print(d.like_walks())



# MULTIPLE INHERITANCE: where there is more than one superclass

class GoldenDoodle(Poodle, Golden):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)


goldie = GoldenDoodle('goldie', 1, 10)
print(goldie.name, goldie.age, goldie.friendliness)
print(goldie.like_walks())
print(goldie.shedding_amount())
print(goldie.fetch_ability())
# we have the same __init__ method 3 times.
# alot of code repetition.

# POLYMORPHISM

# Inheritance Video
class Dog:
    def __init__(self, name, age, friendliness):
        self.name = name
        self.age = age
        self.friendliness = friendliness
    
    def like_walks(self):
        return True
    def barks(self):
        return 'woof'
# "class Samoyed(Dog)" this means that samoyed is a child class of the class Dog.
class Samoyed(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
        # what this means is that it calls the initlization (__init__) from the superclass.

         
    
    

class Poodle(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
         # because of super we dont need to reset attributes
            # Ex: self.name = name
    def shedding_amount(self):
        return 0
        


        

class Golden(Dog):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
    def fetch_ability(self):
        if self.age < 2:
            return 8
        elif self.age < 10:
            return 10
        else:
            return 7 


d = Samoyed('sammy', 2, 10)
print(d.name, d.age, d.friendliness)
print(d.like_walks())



# MULTIPLE INHERITANCE: where there is more than one superclass

class GoldenDoodle(Poodle, Golden):
    def __init__(self, name, age, friendliness):
        super().__init__(name, age, friendliness)
    def barks(self):
        return 'no'


goldie = GoldenDoodle('goldie', 1, 10)
print(goldie.name, goldie.age, goldie.friendliness)
print(goldie.like_walks())
print(goldie.barks())
print(goldie.shedding_amount())


OOP VIDEO NOTES

# Object Orientated Programming in Python

# WHAT IS AN OBJECT


def hello():
    print('hello')

x = 1 

# Type prints out the type of the data the argument is (Example '1' is a int).

print(type(hello))

# When u create something in python u are creating an object which is an instance of a specific class, and that class defines the way an object interacts with other things in our program.

x = 1

y = 'hello'

print(x + y)

# Because the objects are different typeso data they cannot interact with one another. 


# METHODS

string = 'hello'
print(string.upper())

# .upper() is a method acting on object type string stored in variable called string. It converts the string into uppercase letters.

# CREATING A CLASS

class Dog:
    def add_one(self, x):
        return x + 1
    def bark(self):
        print('bark')

# created a class called Dog

# method called bark and called add_one.
d = Dog()
# d is an object of the class 'Dog'
d.bark()
# calling our method 'bark' on our dog object.
print(d.add_one(2))
# This is calling the method 'add_one' on our dog object.



# INIT METHOD

class Cat:

    # __init__ intillizes the cat object.

    def __init__(self, name, age):
        self.name = name
        print(name)

      # self.name = name is an attribute of the class cat.


    def get_name(self):
        return self.name

    # need to add self so python knows which obj we are looking at.

       # 'self' allows us to accesss attributes specific to each cat object.

  

c = Cat('Marel', 13)
print(c.name)

c2 = Cat('bill', 18)
print(c2.name)

c.get_name()
# return name of obj c.
c2.get_name()
# returns name of obj c2. (different from c.get_name)


# MODIFYING ATTRIBUTES

class Cat:

    def __init__(self, name, age):
        self.name = name
        self.age = age
        

    
    def set_newage(self, age):
        # this method modifies the self.age atrribute by changing its value.
        self.age = age
        print(age)

c = Cat('time', 13)
c.set_newage(15)
c2 = Cat('heloo', 17)
c2.set_newage(89)


# MULTIPLE CLASSES (Classes interacting with another)

class Student:
    def __init__(self, name, age, grade):
        # each student will have these attributes
        self.name = name
        self.age = age 
        self.grade = grade # 0 - 100

    def get_grade(self):
        # method that gets students grade.
        return self.grade

class Course:
    # add students to course
    def __init__(self, name, max_students):
        self.name = name
        self.max_students = max_students
        # made an attribute that is not in parameter
        self.students = []
        

    def add_students(self, student):
        # this 'student' is an instance of student object from the class Student
        if len(self.students) < self.max_students:
            self.students.append(student)
            return True
        return False

    def get_average_grade(self):
        value = 0
        for student in self.students:
            value += student.get_grade()
            # use method just incase we change attribute.
        return value / len(self.students)
        
        
s1 = Student('tim', 19, 95)
s2 = Student('bill', 19, 75)
s3 = Student('tim', 19, 65)
s4 = Student('tim', 14, 55)

course = Course('Math', 2)
# by calling the add_student method we are adding students to the course
course.add_students(s1)
course.add_students(s2)
print(course.students[0].name)
# at this point both code is telling us that both things in our list are student objects.
print(course.get_average_grade())


# INHERITANCE

# Generilization
class Pet:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def show(self):
        print (f'I am {self.name} and I am {self.age} years old')
        
    def speak(self):
        print('i dont know what i say')

class Cat(Pet):
     # inheriting class Pet
    def __init__(self, name, age, color):
        super().__init__(name, age)
        #.__init__ defines the method that we want to call, and name and age are the arguments we want to pass. its gonna redifine age and name, and then we can add color.
        # super stands for reference the super class (Pet class (class we inheritad from))
        self.color = color
        
    def speak(self):
        print('meow')

    def show(self):
        print (f'I am {self.name} and I am {self.age} years old and i am {self.color}')


class Dog(Pet):
  
        
    def speak(self):
        print('bark')
    
    

class Fish(Pet):
    pass

p = Pet('tim', 19)
p.show()
p.speak()
c = Cat('bill', 34, 'green')
c.show()

# Even though there is no method called show in class cat. the method still works for object of the Cat class. This is because of inheritance.
c.speak()
d = Dog('jill', 25,)
d.show()
d.speak()

# soeak method is different for the dog class, than the cat class.

# if there is method of the same name in the child class and parent class, the child class will override the parent class method.

f = Fish('bubbles', 19)
f.speak()

# beacause fish does not have speak method. speak from the parent class is used.

# overall when we have classes that are very similar, we should create a parent class to be used for both classes that are very similar to each other.

# CLASS ATTRIBUTES
# class attributes are attributes specific to a class, and not an object.

class Person:
    # this is a class attribute because not defined in __init__ method. (not gonna change). 
    number_of_people = 0
    def __init__(self, name):
        self.name = name
p1 = Person('tim')
p2 = Person('jill')

Person.number_of_people = 8

print(p2.number_of_people)




ENCAPSULATION PRACTICE

# Encapsulation Practice

class User:
    def __init__(self, username, level):
        '''
            all attributes are encapsulated with __ in the front
            two attributes are set by the initialization arguments: username, level
            logged_in attribute is set to False automatically
            pwd attribute will be controlled by a setter method: set_pwd()
        '''
        self.__username = username
        self.__level = str(level).lower().capitalize()
        self.__pwd = self.__set_pwd()
        self.__logged_in = False

    def __set_pwd(self):
        # a setter method to set our password
        # this code can be improved upon to create stronger password requirements
        get_pwd = input("Enter a password: ")
        return get_pwd

    # override example
    def isalpha(self):
        # example of override. String has an .isalpha() as well while our class has one too
        # their behaviour is different but they are a SAME NAMED method; therefore, it is an example of overriding
        return self.__level == 'Alpha'

    def login(self, pwd):
        # a very basic login method
        if pwd == self.__pwd:
            self.__logged_in = True
            print(f'{self.__username} has now logged in')
           
       
        else:
            print('Wrong Password.')
            

    def logout(self):
        # a very basic logout method
        if self.__logged_in == True:
            
            print(f'{self.__username} has logged out.')
            
        else:
            print('Already Logged Out or has not logged in yet.')
            

    def __str__(self):
        # Base override of the string built-method
        return f'User: {self.__username}'

    def __repr__(self):
        return self.__str__()
# end of user

# NEED MORE HELP TO UNDERSTAND


ENCAPSULATION MAIN

# Encapsulation Practice
from encap import User

'''
User needs two attributes arguments: Username and User Status (Alpha, Beta)
Methods:
    login()
    logout()
'''
test = User('POOPOO', 'Alpha') # Creating an Alpha level user with username: POOPOO
test.login('qwerty') # logging in with a wrong password
 # logging in with a right password
test.logout() # logging out
 # logging out again when we already logged out
print('is test alpha?', test.isalpha()) # checking to see if .isalpha() is working







POINT CLASS

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __mul__(self, num):
        # this is the multiplication operator override
        return Point(self.x * num, self.y * num)
        # WHY DO WE NEED THIS?
        
    def distance(self, other_point):
        # we assume other_point is a Point() object
        diff_x = (self.x - other_point.x) ** 2
        diff_y = (self.y - other_point.y) ** 2
        result = (diff_x + diff_y) ** 0.5
        return result

    def __str__(self):
        return f"Point Object ({self.x}, {self.y})"

    def __repr__(self):
        return self.__str__()


POINT MAIN


from point import Point

test1 = Point(2,6)
test2 = Point(-1,5)
origin = Point(0,0)
test3 = Point(5,0)

print(test1)
print(test2)
print(origin)
print("Distance from origin to (5,0)", origin.distance(test3))

test4 = test1 * 3
print(test4)










 
