# Python Basics: Data Types, Variables, Operators, and Basic Syntax

## Data Types

Python supports several built-in data types:

- **Numeric Types**: `int`, `float`, `complex`
- **Boolean Type**: `bool`
- **Sequence Types**: `str` (string), `list`, `tuple`, `range`
- **Mapping Type**: `dict` (dictionary)
- **Set Types**: `set`, `frozenset`
- **None Type**: `NoneType`

```python
# Numeric types
age = 25         # int
height = 1.75    # float
balance = 1000j  # complex

# Boolean type
is_student = True

# Sequence types
name = "Alice"       # str
my_list = [1, 2, 3]  # list
my_tuple = (4, 5, 6) # tuple
my_range = range(5)  # range

# Mapping type
person = {'name': 'Bob', 'age': 30}  # dict

# Set types
my_set = {1, 2, 3}       # set
frozen_set = frozenset({'apple', 'banana', 'cherry'})  # frozenset

# None type
value = None
```

## Variables and Constants

### Variables

Variables in Python are dynamically typed and do not need explicit declaration:

```python
message = "Hello, World!"
count = 10
```
### Constants

Python doesn't have built-in constant types, but naming conventions (UPPER_CASE) are used to denote constants:

```python
PI = 3.14159
MAX_SIZE = 100
```

## Operators

Python supports various operators:

<img width="750" alt="image" src="https://github.com/karthikputtoju/Python_Tutorial/assets/37204779/91362dbb-bbbb-47d1-af04-8d7b92f7a32b">

```python
#Arithmetic Operators:
x = 10
y = 3
print(x + y)   # Output: 13
print(x * y)   # Output: 30

#Comparison Operators:
a = 5
b = 3
print(a > b)   # Output: True
print(a == b)  # Output: False

#Logical Operators:
p = True
q = False
print(p and q)   # Output: False
print(not p)     # Output: False

#Assignment Operators:
num = 10
num += 5        # Equivalent to: num = num + 5
print(num)      # Output: 15

#Bitwise Operators:
x = 5
y = 3
print(x & y)    # Output: 1
print(x | y)    # Output: 7

#Identity Operators:
list1 = [1, 2, 3]
list2 = [1, 2, 3]
print(list1 is list2)    # Output: False

#Membership Operators:
fruits = ['apple', 'banana', 'cherry']
print('banana' in fruits)   # Output: True
```

## Strings and String Manipulation

Strings in Python are sequences of characters enclosed within quotes (either single `'` or double `"` quotes). They are immutable, meaning once defined, their values cannot be changed.
Strings in Python are immutable sequences of characters:

```python
#Creating strings
message = "Hello, World!"

#String concatenation
full_name = "John" + " " + "Doe"

# String slicing and indexing
first_name = full_name[:4]  # 'John'
last_name = full_name[5:]   # 'Doe'

# String methods
uppercase_name = full_name.upper()
```

## Lists, Tuples, Dictionaries, Sets, and Comprehensions

## Lists
Lists are ordered collections that can hold elements of different data types. They are mutable, meaning their elements can be changed after creation.

#### Creating Lists

```python
# Creating lists
my_list = [1, 2, 3, 4, 5]
names = ["Alice", "Bob", "Charlie"]
mixed_list = [1, "Alice", True, 3.14]
```

#### Accessing elements

Elements in a list are accessed using indexing (starting from 0):

```python
# Accessing elements
first_element = my_list[0]    # 1
last_element = my_list[-1]    # 5
```
#### List Methods

Python provides built-in methods to manipulate lists:

```python
# Adding elements
my_list.append(6)       # [1, 2, 3, 4, 5, 6]
my_list.insert(2, 2.5)  # [1, 2, 2.5, 3, 4, 5, 6]

# Removing elements
my_list.pop()           # Removes and returns the last element
my_list.remove(3)       # Removes the first occurrence of 3

# Other operations
len(my_list)            # Length of the list
sorted_list = sorted(my_list)  # Returns a sorted copy of the list
```

#### List Comprehensions

List comprehensions provide a concise way to create lists:

```python
# List comprehension
squares = [x**2 for x in range(1, 6)]  # [1, 4, 9, 16, 25]

# Conditional list comprehension
even_numbers = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

## Tuples
Tuples are ordered collections that are immutable, meaning their elements cannot be changed after creation.

#### Creating Tuples
```python
# Creating tuples
my_tuple = (1, 2, 3)
coordinates = (4.5, 6.7)
```

#### Accessing Elements
Elements in a tuple are accessed using indexing:

```python
# Accessing elements
first_element = my_tuple[0]    # 1
second_element = my_tuple[1]   # 2
```

##### Tuple Methods
Tuples have fewer methods compared to lists due to their immutability:

```python
# Tuple length
len(my_tuple)           # Length of the tuple

# Tuple unpacking
x, y, z = my_tuple      # Unpacks elements into variables
```

## Dictionaries
Dictionaries are unordered collections of key-value pairs. They are mutable and can hold elements of different data types.

#### Creating dictionaries
```python
person = {'name': 'Alice', 'age': 30, 'city': 'New York'}
```

#### Accessing Elements
Elements in a dictionary are accessed using keys:

```python
# Accessing elements
person_name = person['name']    # 'Alice'
person_age = person.get('age')  # 30
```

#### Dictionary Methods
Python provides built-in methods to manipulate dictionaries:

```python
# Adding or updating elements
person['email'] = 'alice@example.com'

# Removing elements
removed_age = person.pop('age')   # Removes and returns the 'age' value

# Other operations
len(person)             # Number of items in the dictionary
keys = person.keys()    # Returns a view object of dictionary keys
values = person.values()  # Returns a view object of dictionary values
```

## Sets
Sets are unordered collections of unique elements. They are mutable but do not allow duplicate elements.

#### Creating Sets
```python
# Creating sets
my_set = {1, 2, 3, 4, 5}
unique_characters = set('hello')
```

#### Set Operations
Python sets support various operations:

```python
# Adding elements
my_set.add(6)           # {1, 2, 3, 4, 5, 6}

# Removing elements
my_set.remove(3)        # {1, 2, 4, 5}

# Set operations
union_set = my_set.union({4, 5, 6})   # {1, 2, 4, 5, 6}
intersection_set = my_set.intersection({2, 3, 4})  # {2, 4}
```

## Comprehensions
Comprehensions provide a concise way to create lists, dictionaries, and sets:

```python
# List comprehension
squares = [x**2 for x in range(10)]

# Dictionary comprehension
square_dict = {x: x**2 for x in range(5)}

# Set comprehension
square_set = {x**2 for x in range(10)}
```

This note provides an overview of fundamental concepts in Python programming, including data types, variables, operators, and basic syntax.
