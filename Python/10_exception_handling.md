## Exception Handling

**Types of errors:**
There are a ton of system errors in the python documentation. Here is a small selection:

>Value errors: Bijvoorbeeld wanneer je een ander argument geeft aan een function, dan wat deze accepteerd, zoals het uploaden van een \*.txt in plaats van een \*.jpg

>Import error: Niet kunnen importeren van een module in de programmacode, door bijvoorbeeld het ontbreken van een internetverbinding.

>OS error:  When the program is incompattible with the operating system.

> Type error: The value of the datatype isnt supported

> Name error: The called value isnt defined in the program

> Index error: The provided index number is higher than the list created.

Simple try except statement in function:
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

Adding the else and finally statement:
```python
def divide(x, y):
	try:
		result = x // y
	except ZeroDivisionError:
		print("Sorry ! You are dividing by zero ")
	else:
		print("Yeah ! Your answer is :", result)

#Python provides a keyword finally, which is always executed after the try and except blocks. The final block always executes after normal termination of try block or after try block terminates due to some exceptions.
	finally:
		print('This is always executed')
	    # this block is always executed` 
	    # regardless of exception generation.`
	    
divide(3, 0)
```

---