# Day 7: Error Handling

## Title: Error Handling

### Topics Covered
- Exceptions
- Try-Except Blocks
- Finally Block
- Custom Exceptions

## Detailed Explanations

### Definition
Error handling is the process of responding to and managing errors that occur during program execution. Python uses exceptions to handle errors, allowing programs to react to error conditions and continue running or terminate gracefully.

### Why it is Required
Error handling is essential for:
- **Robustness**: Preventing programs from crashing due to unexpected errors.
- **User Experience**: Providing informative error messages and handling errors gracefully.
- **Maintenance**: Improving code reliability and debugging capabilities.

### How to Implement
- **Try-Except Blocks**: Use `try` to wrap code that might raise an exception and `except` to handle the exception.
- **Finally Block**: Use `finally` to specify code that runs regardless of whether an exception occurred.
- **Custom Exceptions**: Create custom exceptions by subclassing the `Exception` class.

### Where to Use
Error handling is used in:
- **Runtime Error Management**: Handling unexpected conditions during execution.
- **File Operations**: Managing errors during file reading/writing.
- **User Input**: Validating and handling incorrect input.

## Diagrams

### Exception Handling Flow Diagram
![Exception Handling Flow Diagram](images/exception_handling_flow_diagram.png)

### Custom Exception Hierarchy Diagram
![Custom Exception Hierarchy Diagram](images/custom_exception_hierarchy_diagram.png)

## Syntax
```python
# Try-except block
try:
    # Code block
except ExceptionType:
    # Code block

# Finally block
finally:
    # Code block

# Raising an exception
raise ExceptionType("Error message")

# Custom exception
class CustomError(Exception):
    pass

Example Code
python
Copy code
# Exception handling example
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Execution completed.")

# Custom exception example
class MyError(Exception):
    def __init__(self, message):
        self.message = message

try:
    raise MyError("This is a custom error")
except MyError as e:
    print(e.message)
Explanation Code Step by Step
Try-Except Block:

try: starts a block of code that might raise an exception.
except ZeroDivisionError: catches the ZeroDivisionError and handles it by printing an error message.
finally: executes code that runs regardless of whether an exception occurred (e.g., cleanup code).
Custom Exception:

class MyError(Exception): defines a custom exception class inheriting from Exception.
raise MyError("This is a custom error") raises the custom exception.
except MyError as e: catches the custom exception and prints the error message.
Key Points to Remember
Try-Except Blocks: Use try to run code that might fail and except to handle specific exceptions.
Finally Block: Ensures code executes no matter what, useful for cleanup tasks.
Custom Exceptions: Created by subclassing the Exception class, allowing specific error handling.
Quick Summary
Error handling in Python is managed through exceptions and try-except blocks, with optional use of the finally block for cleanup. Custom exceptions can be created for specific error cases, improving code clarity and control.

Quiz
What is the purpose of the try-except block?
How do you create a custom exception in Python?
What is the use of the finally block in error handling?
Labs
Lab 7.1: Handle Division by Zero
Objective: Write a program that handles division by zero using a try-except block.

Instructions:

Write a Python script that performs division and handles any ZeroDivisionError that may occur.
python
Copy code
# division_by_zero.py
try:
    numerator = int(input("Enter numerator: "))
    denominator = int(input("Enter denominator: "))
    result = numerator / denominator
    print(f"Result: {result}")
except ZeroDivisionError:
    print("Cannot divide by zero!")
Lab 7.2: Custom Exception for Invalid Input
Objective: Create a custom exception for invalid user input and handle it in a program.

Instructions:

Define a custom exception for invalid input.
Write a Python script that uses this custom exception to handle invalid user input.
python
Copy code
# custom_exception_input.py
class InvalidInputError(Exception):
    def __init__(self, message):
        self.message = message

def get_positive_number():
    number = int(input("Enter a positive number: "))
    if number <= 0:
        raise InvalidInputError("The number must be positive.")
    return number

try:
    positive_number = get_positive_number()
    print(f"You entered: {positive_number}")
except InvalidInputError as e:
    print(e.message)

