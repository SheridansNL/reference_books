## Object oriented Programming

Bijna alles is een object. Een string is een object, een integer is een object.
Een class is een soort blauwdruk waarin methoden of objecten worden vastgelegd en gemakkelijk benaderd kunnen worden met een dot notation.
Een class word gebruikt als je iets vaker opnieuw wil gebruiken.

Soorten objecten in classes:
```python
x = 1
print(type(x))
#uitkomst is class 'int'
print(type("hello"))
#uitkomst is class 'str' waarbij de string hello een object is uit de class str.

def hello():
	print("hoi")

print(type(hello))
#uitkomst is class 'function'
```

Wat is een method:
```python
string = "hello"
print(string.upper())
#upper is hierbij de methode
```

Class creation:
```python
class Dog: #class name in CameCase. example: DogTail

	#The __init__ this method is called every time when the 
	#instance Dog() is called.
	
	#self is a target opject and becomes the object 'd'
	def __init__(self, name, age):
	
	# create instance attribute class Dog
	self._name = name.title() # underscore makes it private
	self.age = age
	
	#creating a function or Method in the class.
	def bark(self):
		print("bark")
	# one blank line between methods!
	def add_one(self, x):
		return x + 1

	def get_name(self):
		return self._name
	
	def get_age(self):
		return self.age
	# creeren van een method om de age te wijzigen.
	def set_age(self, age):
		self.age = age
		
d = Dog("Tim", 25) #variabele d van het class type dog
d.bark() # de method aanroepen
print(d.add_one(5)) #uitkomst is 6
print(type(d)) # uitkomst <class '__main__.Dog'> oftwel main module

print(d.name) #rechtstreeks aanroepen van de attribute
d.set_age(22) #wijzigen van attribute age 25 naar 22
print(d.get_age()) #aanroepen van de method
```

Class horizontal inheritence - example 1:
```python
class Student:
	def __init__(self, name, grade):
		self.name = name
		self.grade = grade

	def get_grade(self):
		return self.grade

class Course:
	def __init__(self, name, max_students):
		self.name = name
		self.max_students = max_students
		self.students = [] #empty list 

	def add_student(self, student):
		if len(self.students) < self.max_students:
			self.students.append(student) 
			return True
		return False

	def get_average_grade(self):
		value = 0
		for student in self.students:
			value += student.get_grade()
		return value / len(self.students)

s1 = Student("tim", 9)
s2 = Student("bill", 7)
s3 = Student("theo", 5)

c1 = Course("Science", 2)
c1.add_student(s1)
c1.add_student(s2)
print(c1.add_student(s3)) #returns a False

print(c1.students[0].name) #call index 0
print(c1.get_average_grade())
```

Class horizontal inheritence - example 2:
```python
#person.py
from car import Car
class Person:
    def __init__(self, name):
        self.name = name

    def drive(self, car):
        car.start()
        print(f"{self.name} is driving a {car.make} {car.model}")
        car.stop()

#car.py
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def start(self):
        print(f"Starting the {self.make} {self.model}")

    def stop(self):
        print(f"Stopping the {self.make} {self.model}")

car1 = Car("Honda", "Civic")
person = Person("Alice")
person.drive(car1)

```

Inheritance:
>Werkt met een parrent en child classes die algemene methods kunnen gebruiken van de parrent. Dit zorgt dat je dezelfde code niet opnieuw hoeft te schrijven, maar kunt lenen van de parrent.
```python
class Pet:
	def __init__(self, name, age):
		self.name = name
		self.age = age

	def show(self):
		# de f statement, ook wel format
		print(f"I am {self.name} and I am {self.age} years old")

class Toys:
	def __init__(self, toys='bal'):
		self.toys = toys

	def show_toy(self):
		print(f'Look at my {self.toys}')
		
class Cat(Pet): #aanspreken van de parent class Pet
	def speak(self):
		print("meow")

class Dog(Pet):
	def __init__(self, name, age, color):
		""" aanroepen van method en arguments uit de 
		parent class Pet."""
		super().__init__(name, age) #call method from parent
		self.toys = Toys() # create instace and assign to attribute
		self.color = color #extra attribute

	def speak(self):
		print("Bark")

	def show(self):
		print(
			f"I am {self.name} and I am {self.age} years old"
			f" and I am {self.color}"
		)

p = Pet("tim", 19)
p.show()

c = Cat("Billy", 12)
c.show() #inherits the show method from class Pet
d = Dog("Theo", 15, "brown")
d.speak() #output is Bark
d.show() #spreekt hier de show method aan in de class Dog
d.toys.show_toy()
```

Class attributes:
>Een class attribute word vastgesteld voor de hele class. Het gebruikt geen self. Het is niet gedefinieerd in een method en heeft geen toegang tot een instance van de class.
```python
class Person:
	#class attribute
	number_of_people = 0

	def __init__(self, name):
		self.name = name

p1 = Person("tim")
p2 = Person("jill")

print(Person.number_of_people) #output = 0
Person.number_of_people = 8
print(Person.number_of_people) #output = 8
print(p1.number_of_people) #output = 8

#Usage:

class Person:
	#class attribute
	number_of_people = 0

	def __init__(self, name):
		self.name = name
		Person.number_of_people += 1

p1 = Person("tim")
print(p1.number_of_people) #output = 1
p2 = Person("jill")
print(p1.number_of_people) #output = 2
```

Class methods:
>werkt op de class zelf en hebben geen toegang tot een instance
```python
class Person:
	#class attribute
	number_of_people = 0

	def __init__(self, name):
		self.name = name
		Person.add_person() #use the classmethod to add a person

	#decorator om aan te geven dat dit een classmethod is.
	@classmethod
	def total_people(cls): #cls = class New class
		return cls.number_of_people()

	@classmethod
	def add_person(cls):
		cls.number_of_people += 1

p1 = Person("tim")
p2 = Person("jill")
print(Person.total_people())
```

Static methods:
>Gebruik je om gelijkwaardige functions samen te groeperen in een class, zodat het overzichtelijk en gestructureerd blijft. Je kan ze gemakkelijk verplaatsen naar een andere module om te blijven gebruiken. 
>Gebruikt geen self of cls. Blijven hetzelfde.
```python
class Math:
	@staticmethod
	def add5(x):
		return x + 5
	@staticmethod
	def add10(x):
		return x + 10

	@staticmethod
	def pr():
		print("run")

print(Math.add5(5)) #output = 10
Math.pr()
```

Oproepen class module:
>Je kan je eigen gecreerde classes opslaan als module in dezelfde map.
>Je noemt hem dan bijvoorbeerld rekenen.py.
```python
#Module rekenen.py
class Math:

	@staticmethod
	def add5(x):
		return x + 5

	@staticmethod
	def add10(x):
		return x + 10

# explicite function
def pr():
	print("run")

---
# In een ander bestand.
# De module aanroepen
import rekenen

# Created a class object
object = rekenen.Math()

# Calling and printing class methods
print(object.add5(15))
print(object.add10(15))

# Calling the function
rekenen.pr()

---
#of je kan een specifieke functie / method importeren
from rekenen import pr

# Calling the function
pr()
```

---