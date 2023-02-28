## Conditionals and Loops

Comparison operators:
```python
x = 63 < 73
x = 63.5 > 73.2
x = 50 <= 60

x = 'Sample' == 'sample' #checks at ascci level
x = 'Sample' != 'sample' # not equal.

# python is case sensitive. To solve this you can use this
x = 'Sample'
x.lower() == 'sample'

# for a condition to work, the value has to of the same datatype
x = ((22,33,45 < 22,33,45,66))
```

Multiple conditions:
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
```python
bool(False)  
bool(None)  
bool(0)  
bool("")  
bool(())  
bool([])  
bool({})
```

Conditional statements:
```python
# oneliner
gender = 'm'
salution = 'sir' if gender.lower() == 'm' else 'madam'
# output = sir
```

if else:
```python
number = 40
if number % 3 == 0:
	print('can be divided by 3')
else:
	print("can't be divided by 3") 
```

elif:
```python
num = 40
if num % 3 == 0:
	print('te delen door 3')
elif num % 4 == 0:
	print('te delen door 4')
else:
	print('kan niet door 3 en 4 gedeeld worden')
```

True or False:
```python
numbers = []
if numbers: # checks condition is True or False
	for num in numbers
		print(num)
else:
	print('the list is empty')
```
[^1]: The else block can be omitted. This makes sure that your code runs only under the correct conditions.
[^2]: If only one block needs to run, use if, elif, else. If multiple blocks of code needs to run, use a series of if statements.

For loop:
```python
x = [32,64,128]
sample = 0
for val in x: # where val is the variabele and x is the list
	sample = sample + val
print(sample)
```
[1]: It is best practice to use a single item for the variabele that represents the items in the list. Example for cat in cats.

While loop:
```python
y = 0  
z = 1  
x = int(input('nummer: '))  # use int to accept numerical input
while z <= x:  
    y += z  
    z += 1  
print('De som van de nummers 1 tot ', x, ' is ', y)

# move from one list to another
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

How to quit a loop:
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

Break and continue statements:
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
    i += 1

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

Match case:
```python
# new match conditional statement
gender = 'm'
match gender:
	case 'm':
		print('man')
	case 'f' | 'v':
		print('woman')
	case _:
		print('other')
```

---