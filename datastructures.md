# Python Data Structures: Lists, Tuples, Dictionaries, Sets, and Comprehensions

| Topic                               | Description                                                                   | Example                                               |
|-------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Lists**                           | Ordered collection of items, mutable (changeable) using indices.              | ```python numbers = [1, 2, 3, 4, 5] ```               |
| **Tuples**                          | Ordered collection of items, immutable (unchangeable) using indices.          | ```python coordinates = (10, 20) ```                  |
| **Dictionaries**                    | Unordered collection of key-value pairs, mutable and accessed by keys.         | ```python person = {'name': 'Alice', 'age': 30} ```   |
| **Sets**                            | Unordered collection of unique items, mutable, and supports set operations.    | ```python unique_numbers = {1, 2, 3, 4, 5} ```        |
| **List Comprehensions**             | Concise way to create lists based on existing lists.                           | ```python squares = [x**2 for x in range(1, 6)] ```   |
| **Dictionary Comprehensions**       | Create dictionaries from iterables using a concise syntax.                      | ```python squares_dict = {x: x**2 for x in range(1, 6)} ``` |
| **Set Comprehensions**              | Create sets using a concise syntax from iterables.                              | ```python squares_set = {x**2 for x in range(1, 6)} ``` |
## Lists

### Creating Lists
```python
# Creating a list
numbers = [1, 2, 3, 4, 5]
```
### Accessing Elements and Slicing
```python
# Accessing elements
first_element = numbers[0]   # Accessing first element (1)
last_element = numbers[-1]   # Accessing last element (5)

# Slicing
subset = numbers[2:4]        # Slicing from index 2 to 3 ([3, 4])
```
## Tuples

### Creating Tuples
```python
# Creating a tuple
coordinates = (10, 20)
```
### Accessing Elements
```python
# Accessing elements
x_coord = coordinates[0]   # Accessing first element (10)
y_coord = coordinates[1]   # Accessing second element (20)
```
### Immutability
```python
# Trying to modify a tuple (raises TypeError)
# coordinates[0] = 5
```

## Dictionaries

### Creating Dictionaries
```python
# Creating a dictionary
person = {'name': 'Alice', 'age': 30}
```
### Accessing Elements and Iterating
```python
# Accessing elements
name = person['name']      # Accessing value by key ('Alice')

# Iterating through keys and values
for key, value in person.items():
    print(f"{key}: {value}")
```
## Sets

### Creating Sets and Modifying
```python
# Creating a set
unique_numbers = {1, 2, 3, 4, 5}

# Adding elements
unique_numbers.add(6)      # Adding element to set
unique_numbers.remove(3)   # Removing element from set
```
### Set Operations
```python
# Set operations
set1 = {1, 2, 3}
set2 = {3, 4, 5}

union = set1 | set2        # Union of two sets ({1, 2, 3, 4, 5})
intersection = set1 & set2 # Intersection of two sets ({3})
```
## Comprehensions
### List Comprehensions
```python
# List comprehension to generate squares of numbers from 1 to 5
squares = [x**2 for x in range(1, 6)]
```
### Dictionary Comprehensions
```python
# Dictionary comprehension to create a dictionary of squares
squares_dict = {x: x**2 for x in range(1, 6)}
```
### Set Comprehensions
```python
# Set comprehension to create a set of squares
squares_set = {x**2 for x in range(1, 6)}
```
