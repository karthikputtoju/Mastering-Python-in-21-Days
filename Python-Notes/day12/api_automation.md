# Day 12: Introduction and Working with APIs

## Title: Introduction and Working with APIs

### Topics Covered
- RESTful APIs
- Making API Requests
- Parsing API Responses

## Detailed Explanations

### Definition
- **API (Application Programming Interface)**: Allows different software systems to communicate with each other.
- **RESTful APIs**: Follow the principles of Representational State Transfer and use standard HTTP methods for communication.

### Why it is Required
APIs enable the integration of different systems and services, allowing them to work together and share data. They are essential for building modern web and mobile applications.

### How to Implement
- Use libraries like `requests` to make HTTP requests to APIs.
- Parse JSON responses using the `json` module.

### Where to Use
APIs are used in web development, mobile apps, data integration, and various other applications requiring inter-system communication.

## Diagrams

### API Request-Response Cycle Diagram
![image](https://github.com/user-attachments/assets/0ca9895b-54f0-45cb-b7f2-21c9c77fbcb8)

### JSON Parsing Diagram
![image](https://github.com/user-attachments/assets/b66bd84d-b4a6-497c-8e9f-ba601986d83d)

## Syntax
```python
# Making a GET request
import requests

response = requests.get('https://api.example.com/data')
data = response.json()

# Making a POST request
response = requests.post('https://api.example.com/data', json={'key': 'value'})

# Parsing JSON response
import json

json_data = '{"name": "Alice", "age": 30}'
data = json.loads(json_data)
```
## Example Code
```python
# GET request example
import requests

response = requests.get('https://api.github.com')
print(response.status_code)  # Output: 200
print(response.json())  # Output: JSON response from GitHub API

# POST request example
response = requests.post('https://httpbin.org/post', json={'name': 'Alice'})
print(response.status_code)  # Output: 200
print(response.json())  # Output: JSON response from httpbin

# Parsing JSON response example
import json

json_data = '{"name": "Alice", "age": 30}'
data = json.loads(json_data)
print(data['name'])  # Output: Alice
print(data['age'])  # Output: 30
Explanation Code Step by Step
GET Request:

requests.get('https://api.github.com') makes an HTTP GET request to the GitHub API.
response.json() parses the JSON response.
POST Request:

requests.post('https://httpbin.org/post', json={'name': 'Alice'}) makes an HTTP POST request with JSON data.
Parsing JSON Response:

json.loads(json_data) parses the JSON string into a Python dictionary.
```

## Key Points to Remember
1. RESTful APIs use standard HTTP methods for communication.
2. Use requests library to make API requests.
3. Parse JSON responses using the json module.
4. APIs enable integration and data sharing between different systems.

## Quick Summary
Working with APIs involves making HTTP requests and parsing JSON responses. The requests library simplifies API interactions, while the json module helps in parsing JSON data. APIs are crucial for system integration and data exchange.

## Quiz
1. What is an API?
2. How do you make a GET request in Python?
3. How do you parse a JSON response in Python?

## Labs
1. Lab 12.1: Make a GET Request
	Objective: Write a program that makes a GET request to a public API and prints the response.
	
	Instructions:
	
	Import the requests library.
	Use requests.get() to make a GET request to a public API.
	Print the response.
	```python
	import requests
	
	response = requests.get('https://api.github.com')
	print(response.status_code)
	print(response.json())
	# Output: Status code and JSON response from GitHub API
	```
2. Lab 12.2: Make a POST Request
	Objective: Create a program that makes a POST request to a public API with JSON data and prints the response.
	
	Instructions:
	
	Import the requests library.
	Use requests.post() to make a POST request to a public API with JSON data.
	Print the response.
	```python
	import requests
	
	response = requests.post('https://httpbin.org/post', json={'name': 'Alice'})
	print(response.status_code)
	print(response.json())
	# Output: Status code and JSON response from httpbin
	```
