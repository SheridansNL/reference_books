## Print()

```python
>>> print("Hello world")
Hello world
>>> print(10)
10

# print can take multiple arguments
>>> print("The result is", 10)
The result is 10
```

---

## Input()

```python
# string with user input > output string
sample = input('Give a number? ')     # output type = string
sample = int(input('Give a number? ') # output type = integer

print(f'You chose the number: {sample}.')
```

---

## Reserved keywords

```python
and        as          assert    break
class      continue    def       del
elif       else        except    finally
for        from        global    if
import     in          is        lambda
nonlocal   not         or        pass
raise      return      try       while
with       yield
```

## Build-in functions

```python
abs()          dict()       help()   min()       setattr()
all()          dir()        hex()    next()      slice()
any()          divmod()     id()     object()    sorted()
ascii()        enumerate()  input()  oct()       staticmethod()
bin()          eval()       int()    open()      str()
bool()         bytearray()  exec()   filter()    isinstance()
issubclass()   ord()        pow()    sum()       super()
bytes()        float()      iter()   print()     tuple()
callable()     format()     len()    property()  type()
chr()          frozenset()  list()   range()     vars()
classmethod()  getattr()    locals() repr()      zip()
compile()      globals()    map()    reversed()  __import__()
complex()      hasattr()    max()    round()     delattr()
hash()         memoryview() set()
```

---

## Operators

Normal operators:
```python
=
+
-
*
** (exponent)
/
```

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

## Variables

Rules for setting variables:
* Only letters, numbers and underscore
* A variable may not begin with a number
* Reserved words may not be used in a variable
* Use simple and clear designations

```python
# Retrieving the memory address of a variable with id()
sample = 64
print(id(sample))
```

Local variables:
```python
def sample():
	example = 'This is a locale variable'
	print(example)
sample()
```

Global variables:
```python
#Global variable
example = 'This is a global variable that can be used more often'

def sample_1():
	print(example)

# to use a global variable inside a function or to set a local variable to be used global.
def sample_2():
		global example # keyword global
	print(example)

	# nonlocal is used in nested functions
	def sample_3():
		nonlocal example # keyword nonlocal
		example = 'hello'
```

---

## Data types

Concept:
```python
x = 34
# x is a variable
# = is an operator
# 34 is a literal

y = "This is a string"
# You can also use 'single quotes'
# You can also use ```three single quotes```
# For multiple lines """ three double quotes """

print(type(x)) # type is very usefull function!
print(type(y))
```

Integers:
```python
# integer numbers
x = 25
y = -25

# multiple assignment
x, y, z = 10, 20, 30

# floating point numbers for decimals
x = 25.1234

# conversion from float to hex
x = float.hex(25.1234)

# boolean data type. (True or False)
A = 32
B = 40
print(A > B)
# output = False

# underscore in numbers
universe_age = 14_000_000_000
print(universe_age) # output 14000000000

```

String formatting:
```python
# prefered using an f-string. (f = format)
output = f'{name} is {age} years old'
print(output)

#or 
print( f'{name} is {age} years old' )
print( name + ' is ' + str(age) + ' years old' )
# String : %s and Digit : %d
print( '%s is %d years old ' % (name, age) ) 
print( '{} is {} years old'.format(name, age) )
```

String manipulation:
```python
example = "My name is " + "Monty Python" # concatinate
example = "Gas " * 3

# concatinate by using +=
example = "It's a good day " 
example += "for a drive"
print(example)

# Print number of characters in a variable
print(len(example))

# Searching a string. 
# It outputs the index number of the first iteration
example = "Some text"
sample = example.find("te")
print(sample)

# Changing a text to all upper() or lower() case.
# Other options are capitalize() and title()
sample = input("Which country do you belong to?")
print(sample.upper())
```

Special characters in a string:
| character | discription |
| --- | --- |
| \n | newline |
| \t | horizontal tab |
| \r | carriage return | 
| \b | backspace |
| \f | form feed |
| \' | single quote |
| \" | double quote |
| \\ | backslash |
| \v | vertical tab |
| \N | N is the number for Unicode character |
| \NNN | NNN is digits for Octal value |
| \xNN | NN is a hex value; \x is used to denote following is a hex value. |
| \a | bell sound, actually default chime |
| \u0263 | To input unicode |
[List of unicode characters](https://en.wikipedia.org/wiki/List_of_Unicode_characters)

Indexing and slicing:
```python
# Indexing characters in a sting.
first = "This is a string"
print("First character = ", first[0])
# Negative indexing
print("Last character = ",first[-1])
# Multiple characters (index 0 and 1)
print("Multiple characters = ", first[0:2]) # output: Th

print("Reverse characters = ", first[::-1])
```

Stripping whitespace:
```python
# Extra whitespace can be stripped with the stripping method.
# This can be usefull to clean up user input before storing.
txt = ' python '
txt.rstrip() # output ' python'
txt.lstrip() # output 'python '
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