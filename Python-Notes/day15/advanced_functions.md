# Day 15: Advanced Functions

## Title: Advanced Functions

### Topics Covered
- Lambda Functions
- Map, Filter, Reduce
- List Comprehensions
- Decorators

## Detailed Explanations

### Definition
Advanced functions in Python include lambda functions, higher-order functions like map, filter, and reduce, list comprehensions, and decorators.

### Why it is Required
These advanced function concepts allow for more concise, readable, and efficient code. They enable functional programming paradigms and are powerful tools for data processing and code enhancement.

### How to Implement
- **Lambda Functions**: Anonymous functions defined using the `lambda` keyword.
- **Map, Filter, Reduce**: Higher-order functions part of the `functools` module.
- **List Comprehensions**: A concise way to create lists.
- **Decorators**: Functions that modify or enhance other functions.

### Where to Use
Advanced functions are used in data processing, functional programming, and situations requiring concise and readable code.

## Diagrams

### Lambda Function Workflow Diagram
![Lambda Function Workflow Diagram](images/lambda_function_workflow.png)

### Map, Filter, Reduce Flowchart
![Map, Filter, Reduce Flowchart](images/map_filter_reduce_flowchart.png)

### List Comprehension Diagram
![List Comprehension Diagram](images/list_comprehension_diagram.png)

### Decorator Pattern Diagram
![Decorator Pattern Diagram](images/decorator_pattern_diagram.png)

## Syntax
```python
# Lambda function
lambda arguments: expression

# Map function
map(function, iterable)

# Filter function
filter(function, iterable)

# Reduce function
from functools import reduce
reduce(function, iterable)

# List comprehension
[expression for item in iterable if condition]

# Decorator
def decorator_function(original_function):
    def wrapper_function(*args, **kwargs):
        # Code block
        return original_function(*args, **kwargs)
    return wrapper_function
```

## Example Code
```python
# Lambda function example
square = lambda x: x ** 2
print(square(5))  # Output: 25

# Map function example
numbers = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x ** 2, numbers))
print(squares)  # Output: [1, 4, 9, 16, 25]

# Filter function example
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # Output: [2, 4]

# Reduce function example
from functools import reduce
product = reduce(lambda x, y: x * y, numbers)
print(product)  # Output: 120

# List comprehension example
squares = [x ** 2 for x in numbers]
print(squares)  # Output: [1, 4, 9, 16, 25]

# Decorator example
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Something is happening before the function is called.
# Hello!
# Something is happening after the function is called.
```

## Explanation Code Step by Step
1. Lambda Function:

	- lambda x: x ** 2 defines an anonymous function that squares a number.
2. Map Function:

	- map(lambda x: x ** 2, numbers) applies the lambda function to each element in numbers.
3. Filter Function:

	- filter(lambda x: x % 2 == 0, numbers) filters out odd numbers from numbers.
4. Reduce Function:

	- reduce(lambda x, y: x * y, numbers) multiplies all elements in numbers.
5. List Comprehension:

	- [x ** 2 for x in numbers] creates a list of squares of numbers.
6. Decorator:

	- @my_decorator wraps say_hello() function, adding behavior before and after its execution.

## Key Points to Remember
1. Lambda Functions: Anonymous and defined using the lambda keyword.
2. Map, Filter, Reduce: Higher-order functions for data processing.
3. List Comprehensions: Provide a concise way to create lists.
4. Decorators: Modify or enhance functions using the @ symbol.

## Quick Summary
Advanced functions like lambda functions, map, filter, reduce, list comprehensions, and decorators enable concise, readable, and efficient code. They are powerful tools for data processing and function enhancement.

## Quiz
1. What is a lambda function?
2. How do you use the map function in Python?
3. What is the purpose of a decorator in Python?

## Labs
1. Lab 15.1: Lambda Functions
	Objective: Write a program using lambda functions to sort a list of tuples based on the second element.
	
	Instructions:
	
	Create a list of tuples where each tuple contains a string and a number.
	Use a lambda function to sort the list based on the number.
	```python
	tuples_list = [('a', 2), ('b', 1), ('c', 3)]
	sorted_list = sorted(tuples_list, key=lambda x: x[1])
	print(sorted_list)  # Output: [('b', 1), ('a', 2), ('c', 3)]
	```
2. Lab 15.2: Map Function
	Objective: Use the map function to convert a list of temperatures from Celsius to Fahrenheit.
	
	Instructions:
	
	Create a list of temperatures in Celsius.
	Use map and a lambda function to convert these temperatures to Fahrenheit.
	```python
	celsius = [0, 10, 20, 30, 40]
	fahrenheit = list(map(lambda c: (c * 9/5) + 32, celsius))
	print(fahrenheit)  # Output: [32.0, 50.0, 68.0, 86.0, 104.0]
	```
3. Lab 15.3: List Comprehension
	Objective: Create a list comprehension that generates a list of squares of numbers from 1 to 10.
	
	Instructions:
	
	Use a list comprehension to create a list of squares for numbers from 1 to 10.
	```python
	squares = [x ** 2 for x in range(1, 11)]
	print(squares)  # Output: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
	```
4. Lab 15.4: Decorator
	Objective: Implement a decorator that logs the execution time of a function.
	
	Instructions:
	
	Create a decorator that prints the time it takes for a function to execute.
	Apply this decorator to a function that performs a time-consuming task.
	```python
	import time
	
	def timing_decorator(func):
	    def wrapper(*args, **kwargs):
	        start_time = time.time()
	        result = func(*args, **kwargs)
	        end_time = time.time()
	        print(f"Execution time: {end_time - start_time} seconds")
	        return result
	    return wrapper
	
	@timing_decorator
	def long_running_function():
	    time.sleep(2)
	
	long_running_function()
	# Output: Execution time: 2.000xxx seconds
	```
