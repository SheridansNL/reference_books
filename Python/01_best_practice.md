## Best practice

- Work in alphabetical order
- Import standard library modules first, followed by a blank line and then the modules you wrote.
- A function should always return an value or None.
- Class attributes need to be private. Use underscore. self.\_name

>Python has `_` that you should use for variables you intend to throw away.
```python
for _ in range(5): # underscore 
	numbers_thrown.append(randint(1, 6))
```

>When a variable needs to stay a constant in the program, write the name in all caps.
```python
MAX_AGE = 65
```

>If you specify a default value for a parameter, no spaces should be used on either side of the equal sign. Same goes for keyword arguments.
```python
def function_name(parameter_0, parameter_1='default value'):

#calling the function
function_name(value_0, parameter_1='value')

# if the parameters are longer than 79 chars on a line
def function_name(
		parameter_0, parameter_1, parameter_2): # double tab
	# function body
```

Write clear input prompts:
```python
# Make sure the lines in the code don't exceed 79 chars.
prompt = 'if the prompt is getting to long'
prompt += 'you can use multiple lines to write clear prompts: '
answer = input(prompt)
```

Code hygene:
```python
# At the top import packages
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
 x = x + y
 MAX = 3
# two lines of whitespace
# finally the main function block
if __name__ == '__main__':

```

>When the interpreter runs a module, the `__name__` variable will be set as  `__main__` if the module that is being run is the main program. 
>But if the code is importing the module from another module, then the `__name__`  variable will be set to that module’s name.
```python
# File_one
# Python module to execute
import file_two

print("File one __name__ is set to: {}" .format(__name__))

if __name__ == "__main__":
   print("File one executed when ran directly")
else:
   print("File one executed when imported")

# ==========================================================
# File_two
# Python module to import

print("File two __name__ is set to: {}" .format(__name__))

if __name__ == "__main__":
   print("File two executed when ran directly")
else:
   print("File two executed when imported")


# If run from file_one (the main file) the output should look like this:
# File two __name__ is set to: file_two
# File two executed when imported
# File one __name__ is set to: __main__
# File one executed when ran directly.
```

---