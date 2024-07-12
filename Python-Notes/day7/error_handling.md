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
![image](https://github.com/karthikputtoju/Mastering-Python-in-21-Days/assets/37204779/f1d994b2-3775-4190-ab44-901564b02c7c)


### Custom Exception Hierarchy Diagram
![image](https://github.com/user-attachments/assets/d76b2dfa-1274-4f8b-b829-8a0429141024)

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
```
## Example Code
```python
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
```

## Explanation Code Step by Step
1. Try-Except Block:
   - try: starts a block of code that might raise an exception.
   - except ZeroDivisionError: catches the ZeroDivisionError and handles it by printing an error message.
   - finally: executes code that runs regardless of whether an exception occurred (e.g., cleanup code).
2. Custom Exception:
   - class MyError(Exception): defines a custom exception class inheriting from Exception.
   - raise MyError("This is a custom error") raises the custom exception.
   - except MyError as e: catches the custom exception and prints the error message.

## Key Points to Remember
1. Try-Except Blocks: Use try to run code that might fail and except to handle specific exceptions.
2. Finally Block: Ensures code executes no matter what, useful for cleanup tasks.
3. Custom Exceptions: Created by subclassing the Exception class, allowing specific error handling.

## Quick Summary
Error handling in Python is managed through exceptions and try-except blocks, with the optional use of the finally block for cleanup. Custom exceptions can be created for specific error cases, improving code clarity and control.

## Quiz
1. What is the purpose of the try-except block?
2. How do you create a custom exception in Python?
3. What is the use of the finally block in error handling?

## Labs
1. Lab 7.1: Handle Division by Zero
   Objective: Write a program that handles division by zero using a try-except block.

   Instructions:

   Write a Python script that performs division and handles any ZeroDivisionError that may occur.
   ```python
    # division_by_zero.py
    try:
        numerator = int(input("Enter numerator: "))
        denominator = int(input("Enter denominator: "))
        result = numerator / denominator
        print(f"Result: {result}")
    except ZeroDivisionError:
        print("Cannot divide by zero!")
   ```
2. Lab 7.2: Custom Exception for Invalid Input
   Objective: Create a custom exception for invalid user input and handle it in a program.

   Instructions:

   Define a custom exception for invalid input.
   Write a Python script that uses this custom exception to handle invalid user input.
   ```python
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
    ```
