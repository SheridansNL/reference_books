## Functions & modules

Simple function definition:
```python
def sample(name):                   #function name
	print(f'hello {name}')
sample()
```

Anonymous function:
```python
lambda name: print(f'hello {name}')
```

Paramaters and arguments:
```python
def sample(name): # the variable name is a parameter
	print('Hello' + name)
sample('Mees') # the value mees is an argument

# positional arguments
def sample(name, age):
	print('Hello' + name + 'you are' + age)

sample('Mees', 4)

# keyword arguments
def sample(name, age):
	print('Hello' + name + 'you are' + age)

sample(name = 'Mees', age = 4) # keyword

#Giving default values
def sample(name, age=3): # here age has a default value
	print('Hello' + name + 'you are' + age)
sample('Mees')
# arguments age replaced
sample(name = 'Mees', age=4)

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

Local en global scope:
```python
#local scope
def sample():
	num = 24
	print(num)

sample()
print(num) # gives a NameError: not defined

# global scope
num = 24
def sample():
	print(num)
sample()
print(num) # gives output 24
```
[^1]: A local variabele is not reconized in another function.

Modules importeren:
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

Buildin functions and modules:
```python
print() # output to screen
abs() 
# geeft absolute waarden voor een integer. Input is meestal een negatief getal
round() # rond floating point nummers af
max() # vind het hoogste getal in een groep nummers
min() # laagste getal

def minmax(*numbers): # * = Variadic argument
	low = min(numbers)
	high = max(numbers)
	
return low, high

n = 1, 10, 30, 35, 23, 60, 87, 3
print(minmax(*n)) # Variadic argument

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