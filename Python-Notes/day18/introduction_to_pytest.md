# Day 18: Introduction to pytest

## Title: Introduction to pytest

### Topics Covered
- Overview of pytest
- Writing Test Cases
- Running Tests
- Asserting Results

## Detailed Explanations

### Definition
`pytest` is a testing framework for Python that facilitates writing simple and scalable test cases. It provides robust features to streamline the process of testing code.

### Why it is Required
Testing is essential for maintaining code quality and reliability. `pytest` makes it easier to write and execute tests with its straightforward syntax and powerful capabilities.

### How to Implement
1. **Install pytest**: Use pip to install the framework.
2. **Write Test Cases**: Create test functions in Python files named `test_*.py`. Use `assert` statements to compare actual results with expected outcomes.
3. **Run Tests**: Execute tests by running the `pytest` command in the terminal.

### Where to Use
`pytest` is used for various types of testing, including unit testing, functional testing, and integration testing in Python projects.

## Diagrams

### pytest Workflow Diagram
![image](https://github.com/user-attachments/assets/5ab3eb7f-2de6-4c84-bc7c-3776a5969829)

### Test Case Structure Diagram
![image](https://github.com/user-attachments/assets/68170b09-33fd-4431-9ce3-4eeafa4a36f3)

### Assertion Flowchart
![image](https://github.com/user-attachments/assets/280fe618-f10f-4a4d-987e-d78726468a50)

## Syntax
```python
# Installing pytest
pip install pytest

# Writing a test case
def test_function():
    assert some_function() == expected_result

# Running tests
pytest

# Test case with setup and teardown
import pytest

def setup_function():
    # Code to run before each test
    pass

def teardown_function():
    # Code to run after each test
    pass

def test_example():
    setup_function()
    assert some_function() == expected_result
    teardown_function()
```

## Example Code
```python
# test_example.py
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5  # Test passes
    assert add(-1, 1) == 0  # Test passes
    assert add(0, 0) == 0  # Test passes

# Running tests
# Run the command `pytest` in the terminal
```

## Explanation Code Step by Step
1. Install pytest:

	- Use pip install pytest to install the framework.
2. Write Test Case:

	- Define test functions with names starting with test_.
	- Use assert statements to compare the output of functions with expected results.
3. Run Tests:

	- Execute tests by running the pytest command in the terminal.

## Key Points to Remember
1. pytest is a powerful and popular testing framework for Python.
2. Test functions should start with test_ for pytest to recognize them.
3. Use assert statements to validate test outcomes.
4. Run tests using the pytest command.

## Quick Summary
pytest is a widely-used framework that simplifies writing and running tests in Python. Its straightforward syntax for defining test functions and assertions helps ensure code quality and reliability.

## Quiz
1. What is pytest?
2. How do you write a test case in pytest?
3. What command is used to run tests in pytest?

## Labs
1. Lab 18.1: Simple Test Case
	Objective: Write a simple test case using pytest for a function that adds two numbers.
	
	Instructions:
	
	Create a Python file named test_addition.py.
	Define a function add() that returns the sum of two numbers.
	Write a test function test_add() to test this function with different inputs.
	```python
	# test_addition.py
	def add(a, b):
	    return a + b
	
	def test_add():
	    assert add(2, 3) == 5
	    assert add(-1, 1) == 0
	    assert add(0, 0) == 0
	```
2. Lab 18.2: Multiple Conditions
	Objective: Create a test case that checks multiple conditions using assert statements.
	
	Instructions:
	
	Define a function that performs different operations (e.g., multiplication, division).
	Write a test function with multiple assert statements to verify each operation.
	```python
	# test_operations.py
	def multiply(a, b):
	    return a * b
	
	def divide(a, b):
	    return a / b
	
	def test_operations():
	    assert multiply(2, 3) == 6
	    assert divide(6, 2) == 3
	    assert divide(5, 0) == 'division by zero'  # Custom handling
	```
3. Lab 18.3: Test Suite with Setup and Teardown
	Objective: Develop a test suite for a small module, including setup and teardown functions.
	
	Instructions:
	
	Create a Python module with functions to test.
	Write a test file that includes setup_function() and teardown_function() for preparation and cleanup.
	```python
	# test_suite.py
	import pytest
	
	def setup_function():
	    print("Setup for test")
	
	def teardown_function():
	    print("Teardown for test")
	
	def test_example():
	    setup_function()
	    assert 1 + 1 == 2
	    teardown_function()
	```
