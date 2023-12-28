# My_Property

`My_Property` is a simple implementation of a custom property descriptor in Python. It allows you to define custom behavior for attribute access, modification, and deletion in your classes.

## Usage

Here's an example of how you can use `My_Property` in your own classes:

```python
from my_property import My_Property

class Alphabet:
    def __init__(self, value):
        self._value = value
 
    def getting(self):
        print('Getting value')
        return self._value
    
    def setting(self, value):
        print('Setting value to ' + value)
        self._value = value

    def deleting(self):
        print('Deleting value')
        del self._value

    value = My_Property(getting, setting, deleting)

# Create an instance of Alphabet
func = Alphabet("Hello")

# Access the 'value' attribute using the custom property
print(func.value)

# Modify the 'value' attribute
func.value += " World"
print(func.value)

# Delete the 'value' attribute
del func.value
