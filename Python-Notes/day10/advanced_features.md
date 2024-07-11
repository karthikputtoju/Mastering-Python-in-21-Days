# Day 10: Advanced Python Features

## Title: Advanced Python Features

### Topics Covered
- Iterators
- Generators
- Decorators
- Context Managers

## Detailed Explanations

### Definition
- **Iterators**: Objects that allow you to traverse through all the elements of a collection, one at a time.
- **Generators**: Functions that yield values one at a time and maintain their state between calls.
- **Decorators**: Functions that modify the behavior of other functions or methods.
- **Context Managers**: Objects that manage the setup and teardown of resources, ensuring proper acquisition and release.

### Why it is Required
These features provide powerful tools for:
- **Efficient Data Handling**: Iterators and generators help in processing data efficiently, especially with large datasets.
- **Code Reuse and Enhancement**: Decorators enable the addition of functionality to existing code in a reusable way.
- **Resource Management**: Context managers ensure that resources like files and network connections are properly managed.

### How to Implement
- **Iterators**: Implement `__iter__()` and `__next__()` methods in a class.
- **Generators**: Use the `yield` keyword in a function.
- **Decorators**: Use the `@` symbol to wrap functions with another function.
- **Context Managers**: Implement `__enter__()` and `__exit__()` methods or use the `with` statement.

### Where to Use
- **Iterators and Generators**: Used for efficient data iteration and processing.
- **Decorators**: Used to enhance or modify the behavior of functions or methods.
- **Context Managers**: Used to manage resources like file operations, database connections, and network communications.

## Diagrams

### Iterator Workflow Diagram
![Iterator Workflow Diagram](images/iterator_workflow_diagram.png)

### Generator State Diagram
![Generator State Diagram](images/generator_state_diagram.png)

### Decorator Pattern Diagram
![Decorator Pattern Diagram](images/decorator_pattern_diagram.png)

### Context Manager Flow Diagram
![Context Manager Flow Diagram](images/context_manager_flow_diagram.png)

## Syntax
```python
# Iterator
class MyIterator:
    def __iter__(self):
        return self

    def __next__(self):
        # Code block

# Generator
def generator_function():
    yield value

# Decorator
def decorator_function(original_function):
    def wrapper_function(*args, **kwargs):
        # Code block
        return original_function(*args, **kwargs)
    return wrapper_function

# Context Manager
class MyContextManager:
    def __enter__(self):
        # Code block

    def __exit__(self, exc_type, exc_val, exc_tb):
        # Code block
```

## Example Code
```python
# Iterator example
class MyNumbers:
    def __init__(self):
        self.a = 1

    def __iter__(self):
        return self

    def __next__(self):
        if self.a <= 5:
            x = self.a
            self.a += 1
            return x
        else:
            raise StopIteration

numbers = MyNumbers()
for num in numbers:
    print(num)  # Output: 1 2 3 4 5

# Generator example
def my_generator():
    for i in range(1, 6):
        yield i

for value in my_generator():
    print(value)  # Output: 1 2 3 4 5

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

# Context Manager example
class MyResource:
    def __enter__(self):
        print("Resource acquired")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Resource released")

with MyResource():
    print("Using resource")
# Output:
# Resource acquired
# Using resource
# Resource released
```

## Explanation Code Step by Step
1. Iterator:

	- __iter__() returns the iterator object.
	- __next__() returns the next value until a StopIteration exception is raised.
2. Generator:

	- yield generates values one at a time, resuming where it left off on subsequent calls.
3. Decorator:

	- @my_decorator wraps the say_hello() function, modifying its behavior by adding pre- and post-function calls.
4. Context Manager:

	- __enter__() acquires a resource.
	- __exit__() releases the resource, ensuring proper resource management.

## Key Points to Remember
1. Iterators: Implement __iter__() and __next__() methods.
2. Generators: Use yield to produce values lazily.
3. Decorators: Enhance or modify functions using the @ symbol.
4. Context Managers: Ensure proper resource management using __enter__() and __exit__() methods.

## Quick Summary
Advanced Python features like iterators, generators, decorators, and context managers provide powerful tools for efficient data handling, code enhancement, and resource management. These features enable cleaner, more maintainable, and efficient code.

## Quiz
1. What is the purpose of the yield keyword in Python?
2. How do you define a decorator in Python?
3. What methods are used to implement a context manager?

## Labs
1. Lab 10.1: Create an Iterator
	Objective: Create an iterator that generates squares of numbers from 1 to 5.
	
	Instructions:
	
	Define a class SquareIterator with an __iter__() and __next__() method.
	```python
	class SquareIterator:
	    def __init__(self):
	        self.num = 1
	
	    def __iter__(self):
	        return self
	
	    def __next__(self):
	        if self.num <= 5:
	            result = self.num ** 2
	            self.num += 1
	            return result
	        else:
	            raise StopIteration
	
	squares = SquareIterator()
	for square in squares:
	    print(square)  # Output: 1 4 9 16 25
	```
2. Lab 10.2: Write a Generator
	Objective: Write a generator that produces Fibonacci numbers up to a specified limit.
	
	Instructions:
	
	Define a function fibonacci_generator() that uses yield to produce Fibonacci numbers.
	```python
	def fibonacci_generator(limit):
	    a, b = 0, 1
	    while a < limit:
	        yield a
	        a, b = b, a + b
	
	for number in fibonacci_generator(10):
	    print(number)  # Output: 0 1 1 2 3 5 8
	```
3. Lab 10.3: Implement a Decorator
	Objective: Implement a decorator that logs the execution time of a function.
	
	Instructions:
	
	Define a decorator time_logger that logs the start and end time of the decorated function.
	```python
	import time
	
	def time_logger(func):
	    def wrapper(*args, **kwargs):
	        start_time = time.time()
	        result = func(*args, **kwargs)
	        end_time = time.time()
	        print(f"Execution time: {end_time - start_time} seconds")
	        return result
	    return wrapper
	
	@time_logger
	def sample_function():
	    time.sleep(2)
	    print("Function executed")
	
	sample_function()
	# Output:
	# Function executed
	# Execution time: 2.00... seconds
	```
4. Lab 10.4: Create a Context Manager
	Objective: Create a context manager to manage a database connection.
	
	Instructions:
	
	Define a class DatabaseConnection with __enter__() and __exit__() methods.
	```python
	class DatabaseConnection:
	    def __enter__(self):
	        print("Connecting to the database")
	        # Code to connect to the database
	        return self
	
	    def __exit__(self, exc_type, exc_val, exc_tb):
	        print("Disconnecting from the database")
	        # Code to disconnect from the database
	
	with DatabaseConnection():
	    print("Performing database operations")
	# Output:
	# Connecting to the database
	# Performing database operations
	# Disconnecting from the database
	```
