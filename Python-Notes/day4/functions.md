# Day 4: Functions

## Title: Functions

### Topics Covered
- Function Definition
- Arguments
- Return Values
- Scope
- Lambda Functions

## Detailed Explanations

### Definition
Functions are reusable blocks of code that perform a specific task. They allow you to break down complex problems into smaller, manageable parts. Functions help in organizing code, promoting reuse, and maintaining modularity.

### Why it is Required
Functions promote code reuse and organization. They make programs easier to read, debug, and maintain by encapsulating functionality into discrete units.

### How to Implement
- **Function Definition**: Use the `def` keyword followed by the function name and parentheses to define a function. Parameters can be specified within the parentheses.
- **Arguments**: Values passed to functions when calling them.
- **Return Values**: Values returned from a function using the `return` keyword.

### Where to Use
Functions are used in all aspects of programming, from performing basic operations to implementing complex algorithms and systems.

## Diagrams

### Function Definition and Call Diagram & Scope of Variables Diagram
![image](https://github.com/karthikputtoju/Mastering-Python-in-21-Days/assets/37204779/23f200ed-da08-4dbb-8696-44e50fe1a5ac)

## Syntax
```python
# Function definition
def function_name(parameters):
    # Code block
    return value

# Lambda function
lambda parameters: expression
```

## Example Code
```python
# Function example
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # Output: 8

# Lambda function example
multiply = lambda x, y: x * y
print(multiply(2, 3))  # Output: 6
```

## Explanation Code Step by Step
1. Function Definition:
	- def add(a, b): defines a function named add that takes two parameters, a and b.
	- The function returns the sum of a and b using return a + b.
2. Function Call:
	- result = add(5, 3) calls the add function with arguments 5 and 3, and stores the result in the variable result.
	- print(result) outputs 8.
3. Lambda Function:
	- multiply = lambda x, y: x * y defines a lambda function that multiplies two numbers.
	- print(multiply(2, 3)) calls the lambda function with arguments 2 and 3, and outputs 6.

## Key Points to Remember
1. Functions are defined using the def keyword.
2. Arguments are values passed to functions.
3. The return keyword is used to return a value from a function.
4. Lambda functions are anonymous functions defined using the lambda keyword for concise function definitions.

## Quick Summary
Functions are crucial for code reuse and organization. They are defined with the def keyword, can accept arguments, and return values. Lambda functions offer a shorthand way to define simple functions.

## Quiz
1. How do you define a function in Python?
2. What is the purpose of the return keyword in a function?
3. How do you define a lambda function in Python?
4. What are the benefits of using functions in programming?

## Labs
1. Lab 4.1: Average of a List
	Objective: Write a function that takes a list of numbers and returns the average.

	Instructions:

	Define a function named average that takes a list of numbers as an argument.
	Calculate the average of the numbers and return it.
	Test the function with a sample list.
	```python
	# Lab 4.1 Code
	def average(numbers):
	    return sum(numbers) / len(numbers)
	
	numbers_list = [10, 20, 30, 40, 50]
	avg = average(numbers_list)
	print("Average:", avg)
 	```
2. Lab 4.2: Check Even Number
	Objective: Write a lambda function that checks if a number is even.

	Instructions:

	Define a lambda function named is_even that takes a number and returns True if it is even, False otherwise.
	Test the lambda function with different numbers.
	```python
	# Lab 4.2 Code
	is_even = lambda x: x % 2 == 0
	
	print(is_even(4))  # Output: True
	print(is_even(7))  # Output: False
	```
