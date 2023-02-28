## Testing

```python
# updating pip and installing pytest
python -m install --upgrade pip
python -m pip install --user pytest # for current user
```

>The file that contains the test function has to begin with test_filename.py to be picked up by pytest.
>In this file you import the module / function. of your program.
```python
from module import function_name

# test functions need to start with test_
def test_function():
	"""comments"""
	call_function = function_name('argument')
	assert call_function == 'expected output'
```
[1]: Open a terminal, navigate to the folder containing the test_filename.py. 
[ ]: Enter the command pytest.

| Assertion | Claim|
| --- | ---|
| assert a == b | equal |
| assert a != B | not equal |
| assert a | True |
| assert not a | False |
| assert element in list | element in list |
| assert element not in list | not in list |

Using fixtures:
```python
from module_name import Class_name

# We need to import pytest because were using a decorator defined in pytest
import pytest

# We apply this decorator to the new function
@pytest.fixture
def global():
	"""comments"""
	question = 'Who am I? '
	call_class = Class_name(question)
	return call_class

# the function now has a paramater call_class
def test_number1(call_class)
```

----
