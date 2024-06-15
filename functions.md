# Python Functions and Built-in Functions

| Topic                               | Description                                                                   | Example                                               |
|-------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Defining Functions with `def`**   | Creating reusable blocks of code with a name and optional parameters.         | ```python def greet(name): print(f"Hello, {name}!") ```|
| **Function Parameters and Arguments** | Passing data to functions through parameters and arguments.                  | ```python def add(a, b): return a + b ```             |
| **Return Statements and Returning Values** | Returning values from functions back to the caller.                          | ```python def square(x): return x ** 2 ```           |
| **Scope and Lifetime of Variables** | Understanding where variables can be accessed and how long they exist.       | ```python def my_function(): x = 10 print(x) ```     |
| **Lambda Functions**                 | Inline functions defined using the `lambda` keyword for simple tasks.        | ```python square = lambda x: x ** 2 ```              |
| **Anonymous Functions**             | Functions without a name, often used with higher-order functions like `map()`. | ```python list(map(lambda x: x ** 2, [1, 2, 3])) ``` |

### Defining Functions with `def`

```python
# Function to greet a person
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```
### Function Parameters and Arguments
```python
# Function to add two numbers
def add(a, b):
    return a + b

result = add(5, 3)  # Output: 8
```
### Return Statements and Returning Values
```python
Copy code
# Function to square a number and return the result
def square(x):
    return x ** 2

result = square(4)  # Output: 16
```
### Scope and Lifetime of Variables
```python
# Example demonstrating scope and lifetime of variables
def my_function():
    x = 10
    print(x)  # Output: 10

my_function()
# print(x)  # Raises NameError: name 'x' is not defined
```
### Lambda Functions
```python
# Lambda function to square a number
square = lambda x: x ** 2
print(square(5))  # Output: 25
```
### Anonymous Functions
```python
# Example of using an anonymous function with map()
squared_numbers = list(map(lambda x: x ** 2, [1, 2, 3]))
print(squared_numbers)  # Output: [1, 4, 9]
```
