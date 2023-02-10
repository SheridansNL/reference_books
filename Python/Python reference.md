## Best practice

- Work in alphabetical order
- Import standard library modules first, followed by a blanc line and then the modules you wrote.
- A function should always return an value or None.

>When a variable needs to stay a constant in the program, write the name in all caps.
```python
MAX_AGE = 65
```

>If you specify a default value for a parameter, no spaces should be used on either side of the equal singn. Same goes for keyword arguments.
```python
def function_name(parameter_0, parameter_1='default value'):

#calling the function
function_name(value_0, parameter_1='value')

# if the parameters are longer than 79 chars on a line
def function_name(
		parameter_0, parameter_1, parameter_2): # double tab
	# function body
```

Write clear input promts:
```python
# Make sure the lines in the code dont exceed 79 chars.
prompt = 'if the prompt is getting to long'
prompt += 'you can use multiple lines to write clear prompts: '
answer = input(prompt)
```

Code hygene:
```python
# at the top import packages
from lxml import etree
# 2 lines of whitespace
# Second import modules
import os # modules in lower_case with underscores between words
# two lines of whitespace
# third define functions
def get_ip():
	"""
	Discribe what the function does with a docstring
	immediatly after the defining the function.
	Python looks for this string when generating documentation 
	for the functions in the program
	""" 
	pass
# two lines of whitespace
# then class definitions
class ScannerInfo: # write classes in CamelCase. No unnderscores
	""" A class should have a docstring!"""
# two lines of whitespace
# global variables
 x = x +y
 MAX = 3
# two lines of whitespace
# finally the main function block
if __name__ == '__main__':

```

>When the interpreter runs a module, the `__name__` variable will be set as  `__main__` if the module that is being run is the main program. But if the code is importing the module from another module, then the `__name__`  variable will be set to that module’s name.
```python
# File_one
# Python module to execute
import file_two

print("File one __name__ is set to: {}" .format(__name__))

if __name__ == "__main__":
   print("File one executed when ran directly")
else:
   print("File one executed when imported")

# File_two
# Python module to import

print("File two __name__ is set to: {}" .format(__name__))

if __name__ == "__main__":
   print("File two executed when ran directly")
else:
   print("File two executed when imported")

"""
If run from file_one (the main file) the output should look like this:
File two __name__ is set to: file_two
File two executed when imported
File one __name__ is set to: __main__
File one executed when ran directly.
"""
```

---

## Input()

```python
# string with user input > output string
sample = input('Wat is je geluksgetal? ')
print(f'{sample} is je geluksgetal')
```

String letters:
>\\n = nieuwe regel
>\\t = tab
>\\b =   
>\\d =

Stripping whitespace:
```python
# Extra whitespace can be stripped with the stripping method.
# This can be usefull to clean up user input before storing.
txt = ' python '
txt.rstrip() # output ' python'
txt.lstrip() #output 'python '
txt.strip() # output 'python'
```

Removing prefixes or suffix:
```python
url = 'https://example.com'
url.removeprefix('https://')
# output = example.com

# remove suffix
file = 'sample_file.txt'
file.removesuffix('.txt')
```

---

## Reserved words

and
as
assert
break
class
continue
def
del
elif
else
except
finally
for
from
global
if
import
in
is
lambda
nonlocal
not
or
pass
raise
return
try
while
with
yield

---

## Operators

Normal operators:
>=
>+
>-
>*
>** (exponentiation)
>/

% (modulus): 
```python
# Divides one number by the other and returns the remainder.
>>> 4 % 3 #output = 1
>>> 6 % 3 #output = 0
```

// (floor devision):
```python
# the floor division // rounds the result down to the nearest whole number
x = 15
y = 2

print(x // y)
```

Bitwise Operators:
>Bitwise operators are used to compare (binary) numbers:

| Operator | Name | Description |
|---|---|---|
| & | AND | Sets each bit to 1 if both bits are 1 |
| | OR | Sets each bit to 1 if one of two bits is 1 |
| ^ | XOR | Sets each bit to 1 if only one of two bits is 1 |
| ~ | NOT | Inverts all the bits |
| << | Zero fill left shift | Shift left by pushing zeros in from the right and let the leftmost bits fall off |
| >> | Signed right shift | Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off |
[Python operators reference](https://www.w3schools.com/python/python_operators.asp)

---

## Variabelen

Regels:
* Alleen letters, cijfers en underscore
* Een variabele mag niet beginnen met een cijfer
* Gereserveerde woorden mogen niet gebruikt worden in een variabele
* Gebruik simpele en duidelijke benamingen

```python
# Het geheugenadres van een variabele opvragen
sample = 64
memaddr = id(sample)
print(memaddr)

# manier 2
print(id(sample))
```

Lokale variabelen
```python
def sample():
	example = 'Dit is een lokale variabele'
	print(example)

sample()
```

Globale variabelen
```python
#Globale variabele
example = 'Dit is een globale variabele die vaker te gebruiken is'


def sample():
	print(example)

def secondsample():
	print(example)

sample()
secondsample()
```

---

## Data types

```python
x = 34
# x is een variabele
# = is een operator
# 34 is een literal

y = "Dit is een string"
# De tekst tussen de "dubbele quotes" is een string
# Je kan ook ```drie enkele gebruiken ```
# Je kan ook """ op meerdere regels """ gebruiken
```

```python
# Om karakters in een string te gebruiken kan je gebruik maken van index nummers.

first = "Dit is een string"
print("Eerste karakter = ", first[0])
# Negatief indexen
print("Laatste karakter = ",first[-1])
# Meerdere karakters (van index 0 tot 1)
print("Meerdere karakters = ", first[0:2]

```

```python
#  De modulus (%) operator staat bekend als string formatting operator
print("Ik heb vanacht %d keer geneukt" %20)
# output: Ik heb vannacht 20 keer geneukt.
```

```python
#String manipulatie
example = "Knip en " + "plakwerk"
example = "Gas " * 3

#Sting tekst toevoegen aan variabele
example = "Vandaag is het mooi weer "
example += "of toch niet"
print(example)

#Karakter lengte printen
print(len(example))

#Delen van een string zoeken. De output geeft het indexnummer van de eerste keer dat de input gevonden is.
example = "Dit is een mooi stukje tekst"
sample = example.find("st")
print(sample)
#Als de interpreter niks vind dat is de output -1

#Om een sting naar hoofd of kleine letters te veranderen kan gebruikt worden gemaakt van upper of lower. Camel case kan met title.
sample = input("Which country do you belong to?")
print (sample.upper() + " is a great country!")
# je kan ook lower() of title() gebruiken
```

```python
# using an f-string. (f = format)
sample = input('Wat is je geluksgetal? ')
output = f"{sample} is je geluksgetal"
print(output)

#or
print(f"{sample} is je geluksgetal")
```

```python
#integer nummers
x = 25
y = -25

# multiple assignment
x, y, z = 10, 20, 30

#floating point nummers voor decimalen
x = 25.1234

#conversie van een floating point naar hex
x = float.hex(25.1234)

#Boolean data type. (True or False)
A = 32
B = 40
print(A > B)
#output = False

# underscore in numbers
universe_age = 14_000_000_000
print(universe_age) # output 14000000000

```

----

## Advanced Data structures

Lijsten hebben dezelfde eigenschappen die variabelen bevatten.
De inhoud van een lijst noemt men elementen.

Lists:
```python
#lege lijst
sample = []
#lijst met integers
sample = [25, 35, 45]
#lijst met string type
sample = ['Ede', 'Utrecht', 'Stroe']
print(sample)
```

Indexes:
```python
# Indexering in lijsten
sample = ['Ede', 'Utrecht', 'Stroe']

sample[0] #output Ede
sample[1] #output Utrecht
sample[2] #output Stroe

print(sample[0] + "is de beste")
#print(sample[3] + "is de beste") out of list range
#print(sample[1.2] + "is de beste") floating-point kan niet
```

Range()
```python
numbers = list(range(1, 6)
print(numbers) #output = [1, 2, 3, 4, 5]

# skip with step sizes.			   
even_numbers = list(range(2, 11, 2)
print(numbers) #output = [2, 4, 6, 8, 10]
# loop
for value in range(1, 6):
	print(value)
```

Een lijst kan een andere lijst als element bevatten
```python
x = [1, 223, 2, 45, 63, 22]
print(x)
#oproepen van de elementen in een childlist. met onderstaande verlies je de rest van de lijst inhoud.
print(x[0:3][2]) #output = 2
#list slicing mogelijkheden
print(x[:3]) #Begint bij index 0 [1, 223, 2]
print(x[2:]) #start bij index 2 tot einde lijst
print(x[-3:] # geeft laatste 3 elementen in lijst weer
print(x[:]) #complete lijst word weergegeven.
# handig met kopieren van een lijst om een nieuwe lijst te maken.
y = x[:]
```

```python
#werken met negatieve indexing
print(x[-1])

#lijst lengte opvragen
print(len(x))

#waarden van elementen wijzigen
x = [1, 223, 2, 45, 63, 22]
x[2] = 34
print(x)

#waarden van elementen wijzigen met een bestaande waarde
x[2] = x[1]

#toevoegen aan lijst
x = [1, 223, 2, 45, 63, 22]
y = [15, 20, 35]
print(x + y)

#lijst replicatie
print([2, 4, 6] * 3)

#lijst elementen verwijderen
x = [1, 223, 2, 45, 63, 22]
del(x[2])
print(x)

# remove using pop()
# it removes the last element in the list  and lets u use the value after removing
x = [1, 223, 2, 45, 63, 22]
popped_x = x.pop()
print(x) # output = [1, 223, 2, 45, 63]
print(popped_x) # output = 22

# you can use the indexnr in pop to remove an element in any position
popped_x = x.pop(0)

# remove an element by its value
x.remove('223')

#aanwezig of niet aanwezig in lijst (true or false boolean)
x = [1, 223, 2, 45, 63, 22]
print(223 in x)
#of
print('bal' in ['aap', 'noot', 'mies']) #output = false
```

Index, Insert en sorteren
```python
#indexnr zoeken
x = [1, 223, 2, 45, 63, 22]
print(x.index(45)) #output = 3

#insert element in lijst
#syntax: insert(index positie, 'waarde')
x.insert(2, '15')

# append to end of the list
x.append('15')

#oplopend of aflopend sorteren van je lijst
x = [1, 223, 2, 45, 63, 22]
x.sort()
print(x)
#aflopend sorteren
x.sort(reverse=True)

#werkt ook voor strings
x = ['aap', 'noot', 'mies']
sort()
print(x)

# tijdelijk de lijst sorteren met sorted()
x = [1, 223, 2, 45, 63, 22]
print(sorted(x))
# or
x.sorted(reverse=True)

# print list in reverse
x = [1, 223, 2, 45, 63, 22]
x.reverse()
print(x)
```

List comprehensions:
```python
# in plaats van:
squares = []
for val in range(1, 11):
	square = val ** 2
	squares.append(square)
print(squares)

# kan je deze code in een enkele lijn combineren
# de list comprehension combineert de for loop en het genereren van nieuwe elementen in een enkele regel en append automatisch aan de lijst.
squares = [val**2 for val in range(1, 11)]
print(squares)
```

**TUPLES:**
Een tuple word anders weergegeven dan een lijst. Met () ipv []
Lijsten zijn makkelijk bewerkwaar, waar een tuple niet bewerkbaar is. De ingezette elementen kunnen niet gewijzigd worden.
```python
#een tuple in python
example = ('earth', 'wind', 'fire')
#example[2] = 'poep' geeft een foutmelding
print(example)

sample1 = (10, 20, 30)
sample2 = (40, 50, 60)

print(sample1 + sample2)
#of vermenigvuldigen
print(sample1 * 3)

#Nesten van tuples in een andere
A = (10, 20, 30)
B = ('aap', 'noot', 'mies')
C = (A, B)
print(C)

#slicing van een tuple is mogelijk
x = (1, 223, 2, 45, 63, 22)
print(x [1:3])

#een specifiek element in een tuple verwijderen kan niet, maar je kan wel de volledige tuple verwijderen
x = (1, 223, 2, 45, 63, 22)
del x
print(x)
```

**DICTIONARIES**
Het voordeel van een dictionary is het opslaan van values in paren ipv enkele values.
```python
# multiple values per key nested in a list in one dictionary
steden = {
		  'Gelderland': ['Ede', 'Wageningen', 'Elst'],
		  'Utrecht': ['Maarsen', 'Nijmegen']
		  } # add lists to a key
print(steden)

# add multiple dictionary's in one list
dict_0 = {'key': 'val'}
dict_1 = {'key': 'val'}
dict_2 = {'key': 'val'}

dict_total = [dict_0, dict_1, dict_2]
print(dict_total)

# with loop
aliens = []

for num in range(30):
	new_alien = {'points': '15'}
	aliens.append(new_alien)

for alien in aliens[:5]:
	print(alien)

print(f'Total num of aliens: {len(aliens)}')

# dictionay in a dictionary
dict_total = {
			'dict_0': { 
				'key': 'val'
				},
			'dict_1': {
				'key_1': 'val',
				'key_2': 'val'
				}
				
# add a key or to modify
steden['Zeeland'] = 'naam_stad'

# delete a key
del steden['Gelderland'] # remove key

# using the get method in a dictionary
# it prevents getting an error if the key doensnt exist.
Z = steden.get('Zeeland', 'Staat niet op de kaart.')
print(Z)

# using loops
for key, value in dict_0.items(): #items returns key + value)
for key in dict_0.keys(): # only pulls the keys
for value in dict_0.values(): # only pulls the values

# sort the dictionay
for key in sorted(dict_0.keys()):

# if a dictionary  has a lot of duplicate values you can use set
for value in set(dict_0.values()): #filters duplicates
```
>Note: You can also build a set directly, using braces. You can keep them apart. A dictionary has KeyValue pairs,  where sets only have values.
>steden = {'Ede', 'Elst', 'Nijmegen', 'Maarsen'}

----

## Conditionals and Loops

Comparison operators
```python
x = 63 < 73
x = 63.5 > 73.2
x = 50 <= 60
x = 'Sample' == 'sample' #controle op ascci niveau
x = 'Sample' != 'sample' # niet gelijk aan.

# python is case sensitive. To solve this you can use this
x = 'Sample'
x.lower() == 'sample'

#voorwaarde dat de elementen in de tuple van hetzelfde datatype zijn
x = ((22,33,45 < 22,33,45,66))
```

Multiple conditions
```python
age = 38
gender = 'female'

# Both conditions have to pass
>>> age >= 25 and gender == 'male' # False

# Only fails if both conditions are False
>>> age >= 25 or gender == 'male' # True

# Check value in a list with in
list = [5, 10, 15, 20]
>>> 5 in list # True
>>> 6 in list # False

# Check if value is not in a list
>>> 6 not in list # True

# Boolean expression is either True or False
game_active = True
can_edit = False
```

Almost all booleans are True except the following:
>bool(False)  
>bool(None)  
>bool(0)  
>bool("")  
>bool(())  
>bool([])  
>bool({})

Conditional statements
```python
number = 40
if number % 3 == 0:
	print('kan wel'
else:
	print('kan niet')

#meerde condities 
num = 40
if num % 3 == 0:
	print('te delen door 3')
elif num % 4 == 0:
	print('te delen door 4')
else:
	print('kan niet door 3 en 4 gedeeld worden')

# True or False
numbers = []
if numbers: # checks condition is True or False
	for num in numbers
		print(num)
else:
	print('the list is empty')
```
[^1]: The else block can be omitted. This makes sure that your code runs only under the correct conditions.
[^2]: If only one block needs to run, use if, elif, else. If multiple blocks of code needs to run, use a series of if statements.

Loop statements
```python
# for loop
x = [32,64,128]
sample = 0
for val in x: # where val is the variabele and x is the list
	sample = sample + val
print(sample)

# it is best practice to use a single item for the variabele that represents the items in the list. Example for cat in cats.

#while loop
y = 0  
z = 1  
x = int(input('nummer: '))  #use int to accept numerical input
while z <= x:  
    y += z  
    z += 1  
print('De som van de nummers 1 tot ', x, ' is ', y)

#move from one list to another
unconfirmed = []
confirmed = []
unconfirmed_name = 'Give us your name: '

while True:
	answer = input(unconfirmed_name)
	if answer == 'no':
		break
	else:
		unconfirmed.append(answer)

print(f'Unconfirmed names: {unconfirmed}')

# move form one list to another
while unconfirmed:
	current_name = unconfirmed.pop()
	confirmed.append(current_name)

print(f'Unconfirmed names: {unconfirmed}')

for name in confirmed:
	print(f'Confirmed name: {name}')

# move from dictionary to a list
unconfirmed = {}
confirmed = []
name = 1
unconfirmed_name = 'Give us your name: '

while True:
	answer = input(unconfirmed_name)
	if answer == 'no':
		break
	else:
		unconfirmed[name] = answer
		name += 1
  
print(f'Unconfirmed names: {unconfirmed.items()}')

# it is importend to use copy() to prevent a iteration error.
for name, current_name in unconfirmed.copy().items():
	confirmed.append(current_name)
	del unconfirmed[name]

print(f'{current_name} deleted')
print(f'Unconfirmed names: {unconfirmed}')

for name in confirmed:
	print(f'Confirmed name: {name}')
```

How to quit a loop
```python
# give a value
message = ""
while message != 'quit': # not equal to
	message = input('Tell me something: ')
	
	if message != 'quit':
		print(message)

# using a flag
active = True 
while active:
	message = input('Tell me something: ')
	
	if message == 'quit':
		active = False
	else:
		print(message)
```

Break and continue statements
```python
# while loop with break statement
# breaks immediately, without running remaining code in loop
while True:
	message = input('Tell me something: ')
	
	if message == 'quit':
		break 
	else:
		print(message)
		
n = 6  
i = 1  
while i <= n:  
    if i % 2 == 0:  
        print(i, 'deelbaar door 2')  
    if i % 3 == 0:  
        print(i, 'deelbaar door 3')  
        break  # breaks out of loop
    i = i + 1

#for loop with continue statement
for var in 'computer':  
    if var == 'm':  
        continue # starts at top of loop 
    print(var)

num = 0
while num < 10:
	num += 1
	if num % 2 == 0:
		continue # starts at top of loop again
	print(num) #outputs only the odd numbers.
```

---

## Functions & modules

Een function moet je definieren in de code
```python
def sample():
	print('hello world')
sample()
```

Parameters toevoegen aan een function
```python
def sample(name): # the variable name is a parameter
	print('Hello' + name)
sample('Mees') # the value mees is an argument

#positional arguments
def sample(name, age):
	print('Hello' + name + 'you are' + age)
sample('Mees', 4)

#keyword arguments
def sample(name, age):
	print('Hello' + name + 'you are' + age)
sample(name = 'Mees', age = 4) # keyword

#Giving default values
def sample(name, age = 3): # here age has a default value
	print('Hello' + name + 'you are' + age)
sample('Mees')
#arguments gets  replaced is defined again
sample(name = 'Mees', age = 4)

#Passing a list
def print_name(name):
	print(f'Your name is {name}')

names_list = ['piet', 'jan', 'klaas']
print_name(names_list)
# passing a copy of a list
print_name(names_list[:]) 

#passing an arbitray number of arguments
def pizza(*toppings): # place last when mixing with multiple arguments
""" By adding the asterix before the parameter name tells python to make a tuple containing all the values this function receives"""
	print(toppings)

pizza('cheeze')
pizza('cheeze', 'ham', 'olives')

def pizza(size, **extras):
"""Adding double asterix adds key,value pairs to a dictionay"""
	pizza['size'] = size
	return pizza

#adding extra key, value pairs
build_pizza = pizza('32cm', toppings='cheeze', crust='thin')
print(build_pizza)
```

Local en global scope
```python
#local scope
def sample():
	num = 24
	print(num)
sample()
print(num) #gives a NameError: not defined

#global scope
num = 24
def sample():
	print(num)
sample()
print(num) #gives output 24
```
[^1]: Een local variabele word niet herekend in een ander gedefinieerde function.

Modules importeren
```python
# entire module
import time
time.gmtime()
# specific functions from
from time import gmtime, get_clock_info
gmtime()
# give a function an alias
from time import gmtime as gmt
# give a module an alis
import time as clock
# import every function in a module
from time import *
```

>Een module bestaat uit een opsomming van meerdere funcions.
>Een module is dus ook zelf te creeren.

```python
# filename samplemodule.py
""" A module starts with a docstring discription"""
def product(x, y):
	z = x * y
	return z
	# the return will be printed as output

import samplemodule
output = samplemodule.product(3, 6) # the return has assignd to a variable.
print(output)# output = 18
```

Ingebouwde functies en modules
```python
print()
# output to screen
abs() 
# geeft absolute waarden voor een integer. Input is meestal een negatief getal
round()
# rond floating point nummers af
max() # vind het hoogste getal in een groep nummers
min() # laagste getal
sorted() # sorteerd de items, oplopend of aflopend, in een lijst 
sum() # telt alle integers in een lijst op
len() # geeft info over het aantal elementen in een lijst
type() # geeft info over het soort data type

# String methoden
strip() # verwijderd alle instances van het gegeven argument
x = 'Welcome'
print(x.strip('me')) #output = welco

replace() # vervangt een deel van de string door wat anders
word = 'niet goed'
print(word.replace('niet', 'wel'))

split() #to split up a string
text = 'There is a planet'
print(text.split('re')) #output = ['The', 'is a planet']

join() # lets you add a separator in a list
x = ['ede', 'utrecht', 'elst']
sample = ' ~ '
sample = sample.join(x)
print(sample) #output ede ~ utrecht ~ elst
```

---

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

Class creation
```python
class Dog: #class naam met hoofdletters, bijv DogTail

	#Door __init__ word deze methode elke keer aangeroepen 
	#wanneer de instance Dog() word aangeroepen.
	def __init__(self, name, age):
	# create instance attribute van de class Dog
	self.name = name
	self.age = age
	
	# creeren van een function oftwel een Method in de class.
	def bark(self):
		print("bark")
	# one blanc line between methods!
	def add_one(self, x):
		return x + 1

	def get_name(self):
		return self.name
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

Meerdere classes gebruiken:
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
		self.students = [] #lege lijst 

	def add_student(self, student):
		if len(self.students) < self.max_students:
			self.students.append(student) 
			return True
		return False
		# als de lengte van de lijst kleiner is dan max studenten,
		# dan toevoegen aan de lijst

	def get_average_grade(self):
		value = 0
		for student in self.students:
			value += student.get_grade()
		return value / len(self.students)

s1 = Student("tim", 9)
s2 = Student("bill", 7)
s3 = Student("theo", 5)

course = Course("Science", 2)
course.add_student(s1)
course.add_student(s2)
print(course.students[0].name) #aanroepen naam in lijst op index 0
print(course.get_average_grade())

print(course.add_student(s3)) #geeft een False terug omdat max_students 2 is.
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
>
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
print(p2.number_of_people) #output = 2
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

	@classmethod #decorator om aan te geven dat dit een classmethod is.
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

## Files in Python

Create/open a file, write or append, read and close.
```python
from pathlib import Path 
"""is a library that makes it easier to work with files and directories, no matter the operatingsystem"""

path = Path('file_txt')
contents = path.read_text().rstrip() #method chaining
print(contents)

# Nameing the file
file_name = input("Geef een filename: ")

f = open(file_name + ".txt", "w") # open the file in write mode. use "A" for append.
f.write("Your text") # Write your text
f.close() # close the file

# Opening to display content on screen
f = open(file_name + ".txt", "r") # open the file in read only mode
print(f.read()) # print the readout.
f.close()

#or

print(f.readlines()) # outputs the content in  a list with \n
```

Copy files from one location to another
```python
# importing shutil module
import shutil

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents/file.txt"

# Copy the content of
# source to destination

try:
	shutil.copy(source, destination)
	print("File copied successfully.")

# If source and destination are same
except shutil.SameFileError:
	print("Source and destination represents the same file.")

# If there is any permission issue
except PermissionError:
	print("Permission denied.")

# For other errors
except:
	print("Error occurred while copying file.")
	
```

Move or rename
```python
import shutil

source = "/home/User1/Documents/F1le.txt"
destination = "/home/User2/Documents"

#moving the file
shutil.move(source, destination)

#or for renaming the file
destination = "/home/User2/Documents/NewName.txt"
```

Delete files and folders
```python
#Delete file provided in path
import os
import shutil

file = "/home/User2/Documents/NewName.txt"
os.unlink(file)

# Delete folder in path
path = "/home/User2/Documents/Python"
os.rmdir(path)

# Delete all files and folders present in tree
path = "/home/User2"
shutil.rmtree(path) #Del all present in Directory User2.
```

OS module special methods
```python
import os

print(os.getcwd()) # get current working directory

# Adding back or forward slashes 
print(os.path.join('D:', 'first', 'second')) # output D:\first\second
```

Create a directory with makedirs()
```python
import os

# Leaf directory
directory = "testdir"

# Parent Directories, or set a path
parent_dir = os.getcwd()

# Setting the path
path = os.path.join(parent_dir, directory)

# Create the directory
os.makedirs(path)

print("Directory '%s' created" % directory)
```

---

## Exception Handling

**Types of errors:**
There are a ton of system errors in the python documentation. Here is a small selection:

>Value errors: Bijvoorbeeld wanneer je een ander argument geeft aan een function, dan wat deze accepteerd, zoals het uploaden van een \*.txt in plaats van een \*.jpg

>Import error: Niet kunnen importeren van een module in de programmacode, door bijvoorbeeld het ontbreken van een internetverbinding.

>OS error:  When the program is incompattible with the operating system.

> Type error: The value of the datatype isnt supported

> Name error: The called value isnt defined in the program

> Index error: The provided index number is higher than the list created.

Simple try except statement in function
```python
# working of try()
def divide(x, y):
	try:
		# Floor Division : Gives only Fractional Part as Answer
		result = x // y
		print("Yeah ! Your answer is :", result)
	except ZeroDivisionError:
		print("Sorry ! You are dividing by zero ")
	# multiple excepts are possible
	# ending with an except for all other errors
	except:
		print("Unknown error")

	# you can also fail silently by useing pass
	except:
		pass
divide(3, 0)
```

Adding the else statement
```python
def divide(x, y):
	try:
		result = x // y
	except ZeroDivisionError:
		print("Sorry ! You are dividing by zero ")
	else:
		print("Yeah ! Your answer is :", result)

divide(3, 0)
```

>Python provides a keyword finally, which is always executed after the try and except blocks. The final block always executes after normal termination of try block or after try block terminates due to some exceptions.
>`finally:`
    `# this block is always executed` 
    `# regardless of exception generation.`
    `print('This is always executed')`

---

## Virtual enviroment

Setting up a virtual enviroment:
```bash
$ pip install virtualenv
#or
$ sudo apt-get install python3-venv

# creating directory for venv
$ virtualenv "directoryname"
#or
$ mkdir "directoryname"
$ cd "directoryname"
/dir$ python3 -m venv "enviromentname" #creating virtual enviroment

# activating virtual enviroment
$ source "directoryname"/bin/activate
#deactivating virtual machine
("directoryname")$ deactivate
```

Conda:
```bash
# Conda works across multiple platforms and languages.
# Perfect in the data science space

$ conda create –n new_environment
$ conda activate new_environment
$ conda deactivate
```

---

## Testing

```python
# updating pip and installing pytest
python -m install --upgrade pip
python -m pip install --user pytest # for current user
```

The file that contains the test function has to begin with test_filename.py to be picked up by pytest.
In this file you import the module / function. of your program.

```python
from module import function_name

# test functions need to start with test_
def test_function():
	"""comments"""
	call_function = function_name('argument')
	assert call_function == 'expected output'
```

Open a terminal, navigate to the folder containing the test_filename.py
Enter the command pytest.

| Assertion | Claim|
| --- | ---|
| assert a == b | equal |
| assert a != B | not equal |
| assert a | True |
| assert not a | False |
| assert element in list | element in list |
| assert element not in list | not in list |

Using fixtures
```python
from module_name import class_name

# We need to import pytest because were using a decorator defined in pytest
import pytest

# We apply this decorator to the new function
@pytest.fixture
def global():
	"""comments"""
	question = 'Who am I? '
	call_class = class_name(question)
	return call_class

# the function now has a paramater call_class
def test_number1(call_class)
```

----

## Version control

Install and configure git
```bash
$ sudo apt install git

#Configuring git
$ git config --global user.name "login name computer"
$ git config --global user.email "email"

# setting default name for main branch in a project
$ git config --global init.defaultBranch main
```

Ignoring files
```python
# To avoid git keeping track of unneccary files.
# Make a file called .gitignore
# add directorys such as __pycache__/
__pychache__/
```

Initialize repository
```bash
# navigate to the project directory
project_name$ git init

#checking status
project_name$ git status

# adding all the projectfiles to the repo
project_name$ git add .

# Making a commit / snapshot
project_name$ git commit -m "snapshot name"

# checking the log
project_name$ git log
# or
project_name$ git log --pretty=oneline #simple version

# second commit -a flag tells git to add modified files 
project_name$ git commit -am "New snapshot"

# go back to last commit / snapshot
project_name$ git restore . # all files
project_name$ git restore *filename*
```

Checking out previous commits
```bash
# revisit any commit in the log
$ git log --pretty=oneline
0eb4735c72478c885cf9373bb288a7580ae1ccb9 (HEAD -> main) Ver 1.0
8c95b3b493e675b9ffd07ec30145adb9e74d5acd Started on project

#checkout to previous commit
$ git checkout 8c95b3 # first six characters of ID

# to undo and get back to latest commit
$ git switch -

# reset project to a previous commit from main branch
$ git reset --hard 8c95b3 # commit we want to go back to
```

Deleting the repository
```bash
# either delete the .git directory in a filebrowser (hidden)

# from cli
$ rm -rf .git/
```

---

## Usefull / Popular libraries

Using pip manager:
```bash
$ pip -V #version
$ pip install "librariename"
$ pip show "librariename"
$ pip uninstall "librariename"
$ pip search "librariename"
$ pip list
```

> virtualenv:
> installing the virutal enviroment

> scrapy:
> data extraction from web or mobile pages

>tensor flow:
>popular machine learning

>sci-kit learn:
>alternative to tensorflow

>pandas:
>data analysis

>pygame:
>for creating games. Has also good components related to sound, mouse and accelerometer.

>beautifulsoup:
>scraper for extracting HTML and XML data

>pillow:
>image manipulation

>matplotlib:
>for high leven mathematical functions (works alongside with SciPy and must be installed)

>twisted:
>for web related applications. supports multiple networking protocols.
