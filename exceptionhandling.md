# Python Error and Exception Handling

| Topic                                    | Description                                                                   | Example                                               |
|------------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Types of Exceptions and Error Handling** | Understanding different types of exceptions and how to handle them.            | ```python try: x = 1 / 0 except ZeroDivisionError: print("Cannot divide by zero!") ``` |
| **try, except, else, and finally Blocks** | Using different blocks to manage exceptions and cleanup actions.               | ```python try: file = open('file.txt', 'r') except FileNotFoundError: print('File not found') else: data = file.read() finally: file.close() ``` |
| **Raising Exceptions and Custom Exceptions** | Explicitly raising exceptions and defining custom exception classes.           | ```python raise ValueError("Invalid value") ```       |
| **Handling Specific Exceptions**          | Catching specific exceptions to handle different error conditions.             | ```python try: x = int('foo') except ValueError: print('Invalid input') ``` |
| **Exception Chaining and Traceback Information** | Understanding exception chaining and retrieving traceback details.             | ```python try: raise ValueError("Error occurred") except ValueError as e: raise RuntimeError("Runtime error") from e ``` |

## Types of Exceptions and Error Handling
```python
# Handling ZeroDivisionError
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
```
## try, except, else, and finally Blocks
```python
# Using try, except, else, and finally blocks
try:
    file = open('file.txt', 'r')
except FileNotFoundError:
    print('File not found')
else:
    data = file.read()
    print(data)
finally:
    file.close()
```
## Raising Exceptions and Custom Exceptions
```python
# Raising an exception
raise ValueError("Invalid value")

# Defining and raising a custom exception
class CustomError(Exception):
    pass

raise CustomError("This is a custom error")
```
## Handling Specific Exceptions
```python
# Handling specific exception (ValueError)
try:
    x = int('foo')
except ValueError:
    print('Invalid input')
```
## Exception Chaining and Traceback Information
```python
# Exception chaining example
try:
    raise ValueError("Error occurred")
except ValueError as e:
    raise RuntimeError("Runtime error") from e
```
