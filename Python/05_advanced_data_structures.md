## Lists

Lists with differtent data types:
```python
sample = []                           # empty list
sample = [25, 35, 45]                 # list with integers
sample = ['Ede', 'Utrecht', 'Stroe']  # list with strings
sample = list(range(10))              # build in function()
print(sample)

import string
letters = list(string.ascii_uppercase)# complete alfabet
```
[1]: The contents of a list are called elements.

Indexes:
```python
# List index
sample = ['Ede', 'Utrecht', 'Stroe']

sample[0] # output Ede
sample[1] # output Utrecht
sample[-1] # output Stroe

print(sample[0] + "is a place")
#print(sample[3] + "is a place") out of list range
#print(sample[1.2] + "is a place") float is not possible
```

Build in functions and lists:
```python
l1 = [1, 2, 3, 4, 5]

len(l1)    # 5
max(l1)    # 5
min(l1)    # 1
sum(l1)    # 15
sorted()   # (iterable, /, *, key=None, reverse=False)
filter()   # filter(function, iterable)
map()      # (func, *iterables)
all()
any()
```

Map() example:
```python
def myfunc(a):
  return len(a)

x = map(myfunc, ['apple', 'banana', 'cherry'])
# convert the map into a list, for readability:
print(list(x))
```

Split and join:
```python
text = 'This is a story about'
words = text.split()      # makes a list of al the words
print(' '.join(words)     # returns the list to a string
```

Range():
```python
numbers = list(range(1, 6)
print(numbers) #output = [1, 2, 3, 4, 5]

# skip with step sizes.			   
even_numbers = list(range(2, 11, 2)
print(numbers) #output = [2, 4, 6, 8, 10]

# very usefull in a loop
for value in range(1, 6):
	print(value)
```

List modification methods:
```python
codes = ['NL','B','L']

codes.append('F')          # ['NL','B','L','F']
codes.extend(['D', 'I'])   # ['NL','B','L','F','D','I']
codes.insert(1, 'ES')      # ['NL','ES',B','L','F','D','I']
code = codes.pop()         # ['NL','ES',B','L','F','D']
codes.remove('L')          # ['NL','ES',B','F','D']
codes.reverse()            # ['L', 'B', 'NL']
del codes[1]               # ['NL',B','F','D']
codes.sort()               # ['B','D','F','NL']
```

A list can contain another list (nesting):
```python
x = [1, 223, 2, 45, 63, 22]
print(x)
# calling the elements in a childlist. 
# The elements outside the range are lost.
print(x[0:3][2]) #output = 2

# list slicing options
print(x[:3]) # [1, 223, 2]
print(x[2:]) # starts with index 2 til end of list
print(x[-3:]) # gives last 3 elementens 
print(x[:]) # complete list
	  
# usefull for copying to a new list.
y = x[:]
```

```python
# output the list length
print(len(x))

# changing a element using the index.
x = [1, 223, 2, 45, 63, 22]
x[2] = 34
print(x)

# changing the value of and element using an existing index value.
x[2] = x[1]

# concatinate to a list
x = [1, 223, 2, 45, 63, 22]
y = [15, 20, 35]
print(x + y)

# list replication
print([2, 4, 6] * 3)

# deleting list elementens
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
```

True or False boolean
```python
x = [1, 223, 2, 45, 63, 22]
print(223 in x)
#of
print('bal' in ['aap', 'noot', 'mies']) #output = False
```

Index, Insert en sorteren
```python
# search for indexnr
x = [1, 223, 2, 45, 63, 22]
print(x.index(45)) #output = 3

# insert element in list
# syntax: insert(index position, 'value')
x.insert(2, '15')

# append to end of the list
x.append('15')

# oplopend of aflopend sorteren van je lijst
x = [1, 223, 2, 45, 63, 22]
x.sort()
print(x)
# aflopend sorteren
x.sort(reverse=True)

# werkt ook voor strings
x = ['aap', 'noot', 'mies']
sort()
print(x)

# temporary sort with sorted()
x = [1, 223, 2, 45, 63, 22]
print(sorted(x))
# or
x.sorted(reverse=True)

# print list in reverse
x = [1, 223, 2, 45, 63, 22]
x.reverse()
print(x)

# unpacking
t = (10, 20, 30, 40)
v1, v2, *rest = t
# output = v1=10, v2=20, rest=[30, 40]
```

List comprehensions:
```python
# in plaats van:
squares = []
for val in range(1, 11):
	square = val ** 2
	squares.append(square)
print(squares)

# list comprehension combines the for loop and the iteration of new elements in a single line and also appends automaticly to the list squares.
squares = [val**2 for val in range(1, 11)]
print(squares)
```

## TUPLES

>A tuple is immutable and uses () instead of []
```python
# a tuple in python
example = ('earth', 'wind', 'fire')
# example[2] = 'water' gives an error
print(example)

# Nesten of tuples into another
A = (10, 20, 30)
B = ('aap', 'noot', 'mies')
C = (A, B)
print(C)

# slicing is possible
x = (1, 223, 2, 45, 63, 22)
print(x [1:3])

# you can delete an entire tuple
x = (1, 223, 2, 45, 63, 22)
del x
print(x)
```

## DICTIONARIES

>A dictionary works with key, value pairs
```python
# multiple values per key nested in a list in one dictionary
steden = {
		  'Gelderland': ['Ede', 'Wageningen', 'Elst'],
		  'Utrecht': ['Maarsen', 'Nijmegen']
		  } # add lists to a key
print(steden)

#extract a value
output = steden['Gelderland']

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

# listen
keys = list(codes.keys())
values = list(codes.values())

# zipping
d = dict(zip(keys, values))

# sort the dictionay
for key in sorted(dict_0.keys()):

# if a dictionary  has a lot of duplicate values you can use set
for value in set(dict_0.values()): #filters duplicates
```
[1]: You can also build a set directly, using braces. You can keep them apart. A dictionary has KeyValue pairs,  where sets only have values.

Set:
>The function set() is used to make a set from other collections
```python
s1 = set()           # empty set
s1.add(5)            # {5}
s1.update({1,7,9})   # {1, 5, 9, 7}
s1.remove(9)         # {1, 5, 7}
s1.discard(9)        # {1, 5, 7}
```

---