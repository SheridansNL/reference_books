## Files in Python

Create/open a file, write or append, read and close:
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

#best practice. f.close is not needed.
with open(file, 'a') as f:
	f.write('regel5, Merel, 234, C\n') #needs newline
	print('regel6, Piet, 574, A', file = f) #file key
```

Copy files from one location to another:
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

Move or rename:
```python
import shutil

source = "/home/User1/Documents/F1le.txt"
destination = "/home/User2/Documents"

#moving the file
shutil.move(source, destination)

#or for renaming the file
destination = "/home/User2/Documents/NewName.txt"
```

Delete files and folders:
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

OS module special methods:
```python
import os

print(os.getcwd()) # get current working directory

# Adding back or forward slashes 
print(os.path.join('D:', 'first', 'second')) # output D:\first\second
```

Create a directory with makedirs():
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