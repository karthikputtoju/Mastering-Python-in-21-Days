# Day 19: Advanced pytest Features

## Title: Advanced pytest Features

### Topics Covered
- Fixtures
- Parametrized Tests
- Markers
- Plugins
- Mocking

## Detailed Explanations

### Definition
Advanced features in `pytest` include:
- **Fixtures**: For setup and teardown of test environments.
- **Parametrized Tests**: To run the same test with different inputs.
- **Markers**: To categorize and selectively run tests.
- **Plugins**: To extend `pytest` functionality.
- **Mocking**: To simulate objects and their interactions.

### Why it is Required
These features enhance the flexibility, reusability, and scalability of tests, making it easier to handle complex testing scenarios and customize test behavior.

### How to Implement
- **Fixtures**: Use `@pytest.fixture` to define reusable setup and teardown code.
- **Parametrized Tests**: Use `@pytest.mark.parametrize` to run tests with multiple sets of data.
- **Markers**: Use `@pytest.mark` to label tests for categorization and selective execution.
- **Plugins**: Leverage `pytest` plugins to add extra functionality.
- **Mocking**: Use `unittest.mock.MagicMock` to simulate objects and their behaviors.

### Where to Use
These advanced features are used in larger projects requiring comprehensive testing strategies, such as testing complex applications, libraries, or frameworks.

## Diagrams

### Fixture Workflow Diagram
![Fixture Workflow Diagram](images/fixture_workflow.png)

### Parametrized Test Flowchart
![Parametrized Test Flowchart](images/parametrized_test_flowchart.png)

### Mocking Process Diagram
![Mocking Process Diagram](images/mocking_process.png)

## Syntax
```python
# Using fixtures
import pytest

@pytest.fixture
def setup_data():
    return {"key": "value"}

def test_example(setup_data):
    assert setup_data["key"] == "value"

# Parametrized tests
import pytest

@pytest.mark.parametrize("input,expected", [(1, 2), (3, 4), (5, 6)])
def test_add_one(input, expected):
    assert add_one(input) == expected

# Markers
import pytest

@pytest.mark.slow
def test_slow_function():
    # Slow test
    pass

# Mocking
from unittest.mock import MagicMock

def test_mock():
    mock_obj = MagicMock()
    mock_obj.method.return_value = "mocked!"
    assert mock_obj.method() == "mocked!"
```

## Example Code
```python
# test_example.py
import pytest

@pytest.fixture
def sample_data():
    return [1, 2, 3, 4, 5]

def test_sample_data_length(sample_data):
    assert len(sample_data) == 5

@pytest.mark.parametrize("a,b,expected", [(1, 1, 2), (2, 3, 5), (4, 5, 9)])
def test_add(a, b, expected):
    assert a + b == expected

@pytest.mark.slow
def test_slow_operation():
    import time
    time.sleep(2)  # Simulate slow operation
    assert True

from unittest.mock import MagicMock

def test_mocking():
    mock_obj = MagicMock()
    mock_obj.some_method.return_value = 42
    assert mock_obj.some_method() == 42
```

## Explanation Code Step by Step
1. Fixtures:

	- Define reusable setup code with @pytest.fixture.
	- Use the fixture in test functions to provide setup data or state.
2. Parametrized Tests:

	- Use @pytest.mark.parametrize to define multiple sets of inputs and expected results for a test.
	- The test function runs once for each set of parameters.
3. Markers:

	- Use @pytest.mark to label tests with custom tags (e.g., slow).
	- Allows selective running of tests based on these tags.
4. Mocking:

	- Use unittest.mock.MagicMock to create mock objects.
	- Simulate object behaviors and interactions without relying on real implementations.
## Key Points to Remember
1. Fixtures provide reusable setup and teardown logic.
2. Parametrized tests facilitate testing with different inputs.
3. Markers help in categorizing and selectively running tests.
4. Plugins can extend pytest with additional functionality.
5. Mocking is used to simulate interactions with objects.

## Quick Summary
Advanced pytest features like fixtures, parametrized tests, markers, plugins, and mocking significantly enhance testing capabilities, making it easier to manage complex testing scenarios and customize test behavior.

## Quiz
1. What is the purpose of fixtures in pytest?
2. How do you create parametrized tests in pytest?
3. What is mocking, and why is it used in testing?

## Labs
1. Lab 19.1: Database Fixture
	Objective: Create a fixture that sets up a database connection and write tests using this fixture.
	
	Instructions:
	
	Define a fixture to establish a database connection.
	Write tests that use this fixture to interact with the database.
	```python
	# test_database.py
	import pytest
	import sqlite3
	
	@pytest.fixture
	def db_connection():
	    conn = sqlite3.connect(':memory:')  # In-memory database
	    yield conn
	    conn.close()
	
	def test_database_query(db_connection):
	    cursor = db_connection.cursor()
	    cursor.execute("CREATE TABLE test (id INTEGER, value TEXT)")
	    cursor.execute("INSERT INTO test (id, value) VALUES (1, 'test')")
	    db_connection.commit()
	
	    cursor.execute("SELECT value FROM test WHERE id = 1")
	    result = cursor.fetchone()
	    assert result[0] == 'test'
	```
2. Lab 19.2: Parametrized Factorial Tests
	Objective: Write parametrized tests for a function that calculates the factorial of a number.
	
	Instructions:
	
	Implement a factorial function.
	Use @pytest.mark.parametrize to test the factorial function with various inputs.
	```python
	# test_factorial.py
	import pytest
	from math import factorial
	
	@pytest.mark.parametrize("n,expected", [
	    (0, 1),
	    (1, 1),
	    (5, 120),
	    (7, 5040)
	])
	def test_factorial(n, expected):
	    assert factorial(n) == expected
	```
3. Lab 19.3: Mocking API Response
	Objective: Use mocking to simulate a web API response in a test.
	
	Instructions:
	
	Mock an API call using unittest.mock.
	Write a test that verifies handling of the mock API response.
	```python
	# test_api.py
	import pytest
	from unittest.mock import patch
	import requests
	
	def get_api_data():
	    response = requests.get('https://api.example.com/data')
	    return response.json()
	
	@patch('requests.get')
	def test_api_data(mock_get):
	    mock_get.return_value.json.return_value = {"key": "mocked_value"}
	    data = get_api_data()
	    assert data["key"] == "mocked_value"
	```
