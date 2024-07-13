# Day 11: Libraries and Frameworks

## Title: Libraries and Frameworks

### Topics Covered
- Standard Library Modules
- Popular Python Libraries
- Frameworks

## Detailed Explanations

### Definition
- **Libraries**: Collections of pre-written code that can be used to perform common tasks.
- **Frameworks**: Larger structures that provide a foundation for developing applications.

### Why it is Required
Libraries and frameworks save time and effort by providing reusable code for common tasks, allowing developers to focus on application logic rather than low-level details.

### How to Implement
- **Libraries**: Imported using the `import` statement.
- **Frameworks**: Provide a structure and guidelines for developing applications.

### Where to Use
Libraries and frameworks are used in every aspect of software development, from web development to data analysis and machine learning.

## Diagrams

### Library Import Diagram
![image](https://github.com/user-attachments/assets/24f98485-8baf-4ebc-a0ea-80636661da49)

### Framework Architecture Diagram
![image](https://github.com/user-attachments/assets/13d2dbf5-822f-4347-9c91-5ce295d5ecd7)

## Syntax
```python
# Importing a standard library module
import math

# Importing a popular library
import requests

# Using a framework (example: Flask)
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```

## Example Code
```python
# Standard library example
import datetime

now = datetime.datetime.now()
print(now)  # Output: Current date and time

# Popular library example
import requests

response = requests.get('https://api.github.com')
print(response.status_code)  # Output: 200

# Framework example (Flask)
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run()
```

## Explanation Code Step by Step
1. Standard Library:

	- import datetime imports the datetime module.
	- datetime.datetime.now() gets the current date and time.
2. Popular Library:

	- import requests imports the requests library.
	- requests.get('https://api.github.com') makes an HTTP GET request.
3. Framework:

	- from flask import Flask imports the Flask class.
	- app = Flask(__name__) creates a Flask application instance.
	- @app.route('/') defines a route for the web application.

## Key Points to Remember
1. Libraries provide reusable code for common tasks.
2. Frameworks offer a foundation for application development.
3. Use import to include libraries and frameworks in your code.
4. Libraries and frameworks save time and effort, allowing developers to focus on higher-level tasks.

## Quick Summary
Libraries and frameworks are essential tools in software development, providing reusable code and a foundation for building applications. They enhance productivity and allow developers to focus on application logic.

## Quiz
1. What is the purpose of the import statement in Python?
2. Name two popular Python libraries.
3. How do you create a simple web application using Flask?

## Labs
1. Lab 11.1: Use the Math Library
	Objective: Write a program that uses the math library to calculate the square root of a number.
	
	Instructions:
	
	Import the math library.
	Use the math.sqrt() function to calculate the square root of a given number.
	```python
	import math
	
	number = 16
	square_root = math.sqrt(number)
	print(f"The square root of {number} is {square_root}")
	# Output: The square root of 16 is 4.0
	```
2. Lab 11.2: Create a Simple Web Application
	Objective: Create a simple web application using the Flask framework that returns "Hello, World!" when accessed.
	
	Instructions:
	
	Install Flask using pip if not already installed: pip install Flask.
	Create a Python script that imports Flask and sets up a basic web application.
	```python
	
	from flask import Flask
	
	app = Flask(__name__)
	
	@app.route('/')
	def hello_world():
	    return 'Hello, World!'

	if __name__ == '__main__':
	    app.run()
	# When run, this will start a local web server and display "Hello, World!" at http://127.0.0.1:5000/
	```
