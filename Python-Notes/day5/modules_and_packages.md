# Day 5: Modules and Packages

## Title: Modules and Packages

### Topics Covered
- Importing Modules
- Creating Modules
- Using Packages

## Detailed Explanations

### Definition
- **Modules**: Files containing Python code that can be imported and used in other Python programs. They help in organizing code and reusing functionality across different projects.
- **Packages**: Collections of modules organized in directories. They include an `__init__.py` file and one or more module files. Packages allow for better organization and management of related modules.

### Why it is Required
Modules and packages promote code reuse, organization, and modularity. They enable developers to modularize their code, making it easier to manage large codebases and share code across different projects.

### How to Implement
- **Creating a Module**: Write Python code in a file with a `.py` extension. For example, `my_module.py`.
- **Creating a Package**: Organize modules into directories with an `__init__.py` file. The `__init__.py` file makes the directory a package and can include initialization code.

### Where to Use
Modules and packages are used to:
- Organize code into manageable sections.
- Import and use libraries and functionalities in your projects.
- Share reusable code across multiple projects.

## Diagrams

### Module Import Diagram & Package Structure Diagram
![image](https://github.com/karthikputtoju/Mastering-Python-in-21-Days/assets/37204779/5e085072-f56f-450b-a595-649cd1674b53)

## Syntax
```python
# Importing a module
import module_name

# Importing specific functions from a module
from module_name import function_name

# Creating a module
# my_module.py
def my_function():
    return "Hello, World!"

# Creating a package
# my_package/
#   __init__.py
#   module1.py
#   module2.py
```

## Example Code
```python
# Importing a module
import math
print(math.sqrt(16))  # Output: 4.0

# Importing specific functions from a module
from math import pi
print(pi)  # Output: 3.141592653589793


# Creating and using a custom module
# my_module.py
def greet(name):
    return f"Hello, {name}!"

# main.py
import my_module
print(my_module.greet("Alice"))  # Output: Hello, Alice!


# Creating and using a package
# my_package/__init__.py
# my_package/module1.py
def add(a, b):
    return a + b

# main.py
from my_package.module1 import add
print(add(5, 3))  # Output: 8
```

## Explanation Code Step by Step
1. Importing a Module:

	- import math imports the math module, allowing access to its functions.
	- print(math.sqrt(16)) calls the sqrt function from the math module to compute the square root of 16.

2. Importing Specific Functions:

	- from math import pi imports the pi constant from the math module.
	- print(pi) prints the value of pi.

3. Creating and Using a Custom Module:

	- def greet(name): defines a function in my_module.py.
	- import my_module imports this module into main.py.
	- print(my_module.greet("Alice")) calls the greet function from my_module.

4. Creating and Using a Package:

	- The add function is defined in my_package/module1.py.
	- from my_package.module1 import add imports the add function into main.py.
	- print(add(5, 3)) calls the add function from module1.

## Key Points to Remember
1. Modules: Single files containing Python code that can be imported.
2. Packages: Directories containing multiple modules and an __init__.py file.
3. Use import to include modules and packages in your code.
4. The __init__.py file initializes a package and can include initialization code.

## Quick Summary
Modules and packages help in organizing and reusing code. Modules are individual files, while packages are directories containing multiple modules. Importing allows you to use external and custom code in your programs.

## Quiz
1. How do you create a module in Python?
2. What is the purpose of the __init__.py file in a package?
3. How do you import a specific function from a module?
4. What are the advantages of using packages in Python?

## Labs
1. Lab 5.1: Factorial Module
	Objective: Create a module with a function that calculates the factorial of a number and use it in another script.

	Instructions:

	Define a function named factorial in a file named math_utils.py.
	Write a script named main.py that imports this function and uses it to calculate the factorial of a given number.
	```python
	# math_utils.py
	def factorial(n):
	    if n == 0:
	        return 1
	    else:
	        return n * factorial(n-1)
	
	# main.py
	from math_utils import factorial
	
	print(factorial(5))  # Output: 120
	```
2. Lab 5.2: Math Operations Package
	Objective: Create a package with two modules: one for basic math operations and one for advanced math operations. Use these modules in a script.

	Instructions:

	Create a directory named my_math_package with an __init__.py file.
	Create two modules: basic.py and advanced.py inside my_math_package/.
	Write a script named main.py that imports and uses functions from these modules.
	```python
	# my_math_package/basic.py
	def add(a, b):
	    return a + b
	
	def subtract(a, b):
	    return a - b
	
	# my_math_package/advanced.py
	def multiply(a, b):
	    return a * b
	
	def divide(a, b):
	    return a / b
	
	# main.py
	from my_math_package.basic import add, subtract
	from my_math_package.advanced import multiply, divide
	
	print(add(5, 3))      # Output: 8
	print(subtract(5, 3)) # Output: 2
	print(multiply(5, 3)) # Output: 15
	print(divide(5, 3))   # Output: 1.6666666666666667
	```
