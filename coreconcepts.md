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

| Category            | Operators              | Description                                                     | Example                    |
|---------------------|------------------------|-----------------------------------------------------------------|----------------------------|
| **Arithmetic**      | `+`, `-`, `*`, `/`, `%`, `//`, `**` | Perform basic mathematical operations                          | `5 + 3` (Result: `8`)       |
| **Comparison**      | `==`, `!=`, `>`, `<`, `>=`, `<=` | Compare values and return Boolean (True or False)               | `10 > 5` (Result: `True`)   |
| **Logical**         | `and`, `or`, `not`     | Combine Boolean expressions and negate values                   | `True and False` (Result: `False`) |
| **Assignment**      | `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=` | Assign values to variables                                     | `x += 1` (Equivalent to `x = x + 1`) |
| **Bitwise**         | `&`, `|`, `^`, `~`, `<<`, `>>` | Manipulate bits of integers                                    | `5 & 3` (Result: `1`)       |
| **Identity**        | `is`, `is not`         | Compare memory location of objects                              | `x is y` (True if `x` and `y` refer to the same object) |
| **Membership**      | `in`, `not in`         | Check if a value exists within a sequence                       | `'a' in ['a', 'b', 'c']` (Result: `True`) |

## Examples

### Arithmetic Operators

- **Addition**: `5 + 3` (Result: `8`)
- **Subtraction**: `10 - 4` (Result: `6`)
- **Multiplication**: `2 * 6` (Result: `12`)
- **Division**: `10 / 3` (Result: `3.3333`)
- **Modulus**: `10 % 3` (Result: `1`)
- **Floor Division**: `10 // 3` (Result: `3`)
- **Exponentiation**: `2 ** 3` (Result: `8`)

### Comparison Operators

- **Equal to**: `5 == 5` (Result: `True`)
- **Not equal to**: `10 != 5` (Result: `True`)
- **Greater than**: `10 > 5` (Result: `True`)
- **Less than or equal to**: `3 <= 3` (Result: `True`)

### Logical Operators

- **AND**: `True and False` (Result: `False`)
- **OR**: `True or False` (Result: `True`)
- **NOT**: `not True` (Result: `False`)

### Assignment Operators

- **Assignment**: `x = 10`
- **Increment**: `x += 1` (Equivalent to `x = x + 1`)
- **Decrement**: `x -= 1` (Equivalent to `x = x - 1`)

### Bitwise Operators

- **AND**: `5 & 3` (Result: `1`)
- **OR**: `5 | 3` (Result: `7`)
- **XOR**: `5 ^ 3` (Result: `6`)
- **NOT**: `~5` (Result: `-6`)
- **Left Shift**: `5 << 1` (Result: `10`)
- **Right Shift**: `5 >> 1` (Result: `2`)

### Identity Operators

- **is**: `x is y` (True if `x` and `y` refer to the same object)
- **is not**: `x is not y` (True if `x` and `y` do not refer to the same object)

### Membership Operators

- **in**: `'a' in ['a', 'b', 'c']` (Result: `True`)
- **not in**: `'d' not in ['a', 'b', 'c']` (Result: `True`)


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

## Python Data Structures and Comprehensions

| Data Structure            | Description                                                                                   | Example                                 |
|---------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------|
| **Lists**                 | Ordered collection of elements. Mutable (can be changed after creation).                      | `[1, 2, 3, 4, 5]`                        |
| **Tuples**                | Ordered collection of elements. Immutable (cannot be changed after creation).                 | `(1, 2, 3)`                              |
| **Dictionaries**          | Unordered collection of key-value pairs. Mutable and indexed by keys (unique).                | `{'name': 'Alice', 'age': 30}`           |
| **Sets**                  | Unordered collection of unique elements. Mutable and does not allow duplicate elements.       | `{1, 2, 3, 4, 5}`                        |
| **Comprehensions**        | Concise way to create lists, dictionaries, or sets based on existing iterables.               | `[x**2 for x in range(1, 6)]`            |

### Lists
Lists are ordered collections that can hold elements of different data types. They are mutable, meaning their elements can be changed after creation.
- **Creating a List**: `my_list = [1, 2, 3, 4, 5]`
- **Accessing Elements**: `first_element = my_list[0]` (Result: `1`)
- **List Methods**: `my_list.append(6)` (Adds `6` to `my_list`)
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
### Tuples
Tuples are ordered collections that are immutable, meaning their elements cannot be changed after creation.
- **Creating a Tuple**: `my_tuple = (1, 2, 3)`
- **Accessing Elements**: `second_element = my_tuple[1]` (Result: `2`)
- **Tuple Methods**: Few methods due to immutability, e.g., `len(my_tuple)` (Length of tuple)
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
### Dictionaries
Dictionaries are unordered collections of key-value pairs. They are mutable and can hold elements of different data types.
- **Creating a Dictionary**: `person = {'name': 'Alice', 'age': 30}`
- **Accessing Elements**: `person_name = person['name']` (Result: `'Alice'`)
- **Dictionary Methods**: `person['city'] = 'New York'` (Adds key-value pair)
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
### Sets
Sets are unordered collections of unique elements. They are mutable but do not allow duplicate elements.
- **Creating a Set**: `my_set = {1, 2, 3, 4, 5}`
- **Set Operations**: `my_set.add(6)` (Adds `6` to `my_set`)
- **Set Methods**: `my_set.remove(3)` (Removes `3` from `my_set`)

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
### Comprehensions
- **List Comprehension**: `[x**2 for x in range(1, 6)]` (Result: `[1, 4, 9, 16, 25]`)
- **Set Comprehension**: `{x for x in range(10) if x % 2 == 0}` (Result: `{0, 2, 4, 6, 8}`)
- **Dictionary Comprehension**: `{fruit: len(fruit) for fruit in ['apple', 'banana', 'cherry']}`
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
