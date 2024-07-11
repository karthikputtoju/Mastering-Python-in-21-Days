# Day 20: API Testing with pytest

## Title: API Testing with pytest

### Topics Covered
- Writing API Tests
- Using pytest Fixtures for Setup
- Validating API Responses
- Mocking API Requests

## Detailed Explanations

### Definition
API testing with `pytest` involves creating tests that interact with APIs to ensure they are functioning correctly. This includes validating responses, using fixtures for setup, and mocking API requests to simulate various scenarios.

### Why it is Required
Testing APIs ensures that they work as expected, handle edge cases, and return the correct data. Using `pytest` for API testing provides a structured approach to automate and manage these tests effectively.

### How to Implement
- **Writing API Tests**: Use the `requests` library to make API calls and validate the responses.
- **Using pytest Fixtures**: Define fixtures to set up test environments and share common data or configurations.
- **Mocking API Requests**: Use `unittest.mock` to simulate API responses for isolated and controlled testing.

### Where to Use
API testing is applicable in web development, microservices, and any system that provides or consumes APIs, ensuring their reliability and performance.

## Diagrams

### API Testing Workflow Diagram
![API Testing Workflow Diagram](images/api_testing_workflow.png)

### Fixture Setup and Teardown Flowchart
![Fixture Setup and Teardown Flowchart](images/fixture_setup_teardown.png)

### Mocking API Requests Diagram
![Mocking API Requests Diagram](images/mocking_api_requests.png)

## Syntax
```python
# Writing API tests
import requests
import pytest

@pytest.fixture
def api_url():
    return "https://api.example.com/data"

def test_api_response(api_url):
    response = requests.get(api_url)
    assert response.status_code == 200
    assert "data" in response.json()

# Mocking API requests
from unittest.mock import patch

@patch('requests.get')
def test_mocked_api_response(mock_get):
    mock_get.return_value.status_code = 200
    mock_get.return_value.json.return_value = {"data": "value"}
    
    response = requests.get("https://api.example.com/data")
    assert response.status_code == 200
    assert response.json() == {"data": "value"}
```

## Example Code
```python
# test_api.py
import requests
import pytest
from unittest.mock import patch

@pytest.fixture
def api_url():
    return "https://api.github.com/users/octocat"

def test_github_api(api_url):
    response = requests.get(api_url)
    assert response.status_code == 200
    data = response.json()
    assert "login" in data
    assert data["login"] == "octocat"

@patch('requests.get')
def test_mocked_github_api(mock_get):
    mock_get.return_value.status_code = 200
    mock_get.return_value.json.return_value = {
        "login": "octocat",
        "id": 583231
    }
    
    response = requests.get("https://api.github.com/users/octocat")
    assert response.status_code == 200
    data = response.json()
    assert data["login"] == "octocat"
    assert data["id"] == 583231
```

## Explanation Code Step by Step
1. API Test with Requests:

	- Use requests.get(api_url) to make an API call.
	- Check the response status code and validate the JSON data.
2. Mocking API Requests:

	- Use @patch('requests.get') to replace the requests.get call with a mock object.
	- Define the mock response and validate it to simulate different scenarios.

## Key Points to Remember
1. Use the requests library to make API calls in tests.
2. Utilize pytest fixtures for setting up and tearing down test data.
3. Apply unittest.mock to mock API requests and simulate various responses.
4. Validate API responses by checking both status codes and response data.

## Quick Summary
API testing with pytest involves writing tests to make API calls, validating responses, and using fixtures and mocking to ensure APIs function correctly. This approach helps ensure APIs handle various scenarios properly and consistently.

## Quiz
1. How do you make API calls in pytest tests?
2. What is the purpose of mocking in API testing?
3. How do you use pytest fixtures for setting up API test data?

## Labs
1. Lab 20.1: Writing API Tests
	Objective: Write a test that makes an API call to a public API and validates the response data.
	
	Instructions:
	
	Choose a public API (e.g., a weather API).
	Write a test function that calls the API and checks the response status and data.
	```python
	# test_weather_api.py
	import requests
	import pytest
	
	@pytest.fixture
	def weather_api_url():
	    return "https://api.open-meteo.com/v1/forecast?latitude=35.6895&longitude=139.6917&hourly=temperature_2m"
	
	def test_weather_api(weather_api_url):
	    response = requests.get(weather_api_url)
	    assert response.status_code == 200
	    data = response.json()
	    assert "hourly" in data
	    assert "temperature_2m" in data["hourly"]
	```
2. Lab 20.2: API Base URL Fixture
	Objective: Create a fixture that sets up an API base URL and use it in multiple tests.
	
	Instructions:
	
	Define a fixture that returns the base URL for an API.
	Use this fixture in multiple test functions to construct complete API endpoints.
	```python
	# test_base_url.py
	import requests
	import pytest
	
	@pytest.fixture
	def base_url():
	    return "https://api.example.com"
	
	def test_get_endpoint(base_url):
	    url = f"{base_url}/data"
	    response = requests.get(url)
	    assert response.status_code == 200
	
	def test_post_endpoint(base_url):
	    url = f"{base_url}/submit"
	    response = requests.post(url, json={"key": "value"})
	    assert response.status_code == 201
	```
3. Lab 20.3: Mocking API Responses
	Objective: Use mocking to simulate different API responses and write tests to validate the behavior.
	
	Instructions:
	
	Use unittest.mock to create mock responses for different scenarios.
	Write tests that check how your code handles these mock responses.
	```python
	# test_mocked_responses.py
	import pytest
	from unittest.mock import patch
	import requests
	
	@patch('requests.get')
	def test_mocked_success_response(mock_get):
	    mock_get.return_value.status_code = 200
	    mock_get.return_value.json.return_value = {"key": "value"}
	    response = requests.get("https://api.example.com/data")
	    assert response.status_code == 200
	    assert response.json() == {"key": "value"}
	
	@patch('requests.get')
	def test_mocked_error_response(mock_get):
	    mock_get.return_value.status_code = 404
	    response = requests.get("https://api.example.com/data")
	    assert response.status_code == 404
	```
