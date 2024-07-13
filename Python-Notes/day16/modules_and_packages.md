# Day 16: Modules and Packages

## Title: Modules and Packages

### Topics Covered
- Creating Modules
- Using Packages
- Importing Modules
- Namespaces

## Detailed Explanations

### Definition
- **Modules**: Python files (`.py`) containing definitions (functions, classes) and statements. They help organize code by grouping related functionality.
- **Packages**: Directories containing multiple modules and an `__init__.py` file. Packages allow for a hierarchical organization of modules.

### Why it is Required
Modules and packages promote code reuse, organization, and maintainability. They enable modular programming by encapsulating related functionality, making code easier to manage and scale.

### How to Implement
- **Creating a Module**: Save functions and classes in a Python file. Example: `mymodule.py`.
- **Creating a Package**: Organize related modules into a directory with an `__init__.py` file. Example structure: `mypackage/`.

### Where to Use
Modules and packages are used to organize code in larger projects, libraries, and frameworks, facilitating better structure and reusability.

## Diagrams

### Module Import Diagram
![image](https://github.com/user-attachments/assets/10bd3464-7967-44ef-b48a-df226fb80308)

### Package Structure Diagram
![image](https://github.com/user-attachments/assets/bfe35589-84ec-4571-a7eb-25c2060a357e)

### Namespace Diagram
![image](https://github.com/user-attachments/assets/17b0155a-8104-4da8-9e76-22b578e3341a)

## Syntax
```python
# Creating a module (mymodule.py)
def greet(name):
    return f"Hello, {name}!"

# Creating a package
# mypackage/
# ├── __init__.py
# ├── module1.py
# └── module2.py

# Importing a module
import mymodule

# Importing a package
from mypackage import module1, module2
```

## Example Code
```python
# mymodule.py
def greet(name):
    return f"Hello, {name}!"

# main.py
import mymodule

print(mymodule.greet('Alice'))  # Output: Hello, Alice!

# mypackage/module1.py
def add(a, b):
    return a + b

# mypackage/module2.py
def subtract(a, b):
    return a - b

# main.py
from mypackage import module1, module2

print(module1.add(5, 3))  # Output: 8
print(module2.subtract(5, 3))  # Output: 2
```

## Explanation Code Step by Step
1. Creating a Module:

	- Save functions and classes in a Python file (e.g., mymodule.py).
2. Creating a Package:

	- Organize related modules into a directory structure.
	- Include an __init__.py file in the directory to make it a package.
3. Importing a Module:

	- Use import mymodule to import the module and access its functions and classes.
4. Importing a Package:

	- Use from mypackage import module1, module2 to import specific modules from a package.

## Key Points to Remember
1. Modules: Individual Python files containing code.
2. Packages: Directories containing multiple modules and an __init__.py file.
3. Importing: Use import to include modules and packages in your code.
4. Code Organization: Modules and packages help in organizing code for better maintainability and reusability.

## Quick Summary
Modules and packages help organize and structure Python code. Modules are individual files, while packages are directories containing multiple modules. They enable modular programming and promote code reuse and maintainability.

## Quiz
1. What is a module in Python?
2. How do you create a package in Python?
3. How do you import a module from a package?

## Labs
1. Lab 16.1: Create a Module
	Objective: Create a module with a function that returns the factorial of a number and use it in another script.
	
	Instructions:
	
	Create a module math_utils.py with a factorial function.
	Write a script main.py to import and use this function.
	```python
	# math_utils.py
	def factorial(n):
	    if n == 0:
	        return 1
	    return n * factorial(n - 1)
	
	# main.py
	from math_utils import factorial
	
	print(factorial(5))  # Output: 120
	```
2. Lab 16.2: Organize Modules into a Package
	Objective: Organize multiple modules into a package and write a script to use functions from these modules.
	
	Instructions:
	
	Create a package mypackage/ with module1.py and module2.py.
	Write a script main.py to import and use functions from these modules.
	```python
	# mypackage/module1.py
	def greet(name):
	    return f"Hello, {name}!"
	
	# mypackage/module2.py
	def farewell(name):
	    return f"Goodbye, {name}!"
	
	# main.py
	from mypackage import module1, module2
	
	print(module1.greet('Alice'))  # Output: Hello, Alice!
	print(module2.farewell('Alice'))  # Output: Goodbye, Alice!
	```
3. Lab 16.3: Create a Package with Sub-Packages
	Objective: Create a package with sub-packages and modules, and write a script to demonstrate their usage.
	
	Instructions:
	
	Create a package main_package/ with sub-packages sub_package1/ and sub_package2/.
	Each sub-package should have a module with a simple function.
	Write a script to import and use functions from these sub-packages.
	```python
	# main_package/sub_package1/module1.py
	def hello():
	    return "Hello from sub_package1!"
	
	# main_package/sub_package2/module2.py
	def hello():
	    return "Hello from sub_package2!"
	
	# main.py
	from main_package.sub_package1 import module1
	from main_package.sub_package2 import module2
	
	print(module1.hello())  # Output: Hello from sub_package1!
	print(module2.hello())  # Output: Hello from sub_package2!
	```
