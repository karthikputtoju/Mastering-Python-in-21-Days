# Day 17: Working with APIs

## Title: Working with APIs

### Topics Covered
- Consuming APIs
- Authenticating API Requests
- Rate Limiting
- Error Handling in API Requests

## Detailed Explanations

### Definition
Working with APIs involves making requests to external services and handling the responses. This process includes managing authentication, respecting rate limits, and dealing with errors effectively.

### Why it is Required
Consuming APIs allows applications to integrate functionality and data from external sources, such as web services or third-party platforms. Proper handling of authentication, rate limits, and errors ensures secure and reliable communication with APIs.

### How to Implement
- **Authentication**: Use headers to include an access token or API key in your requests.
- **Rate Limiting**: Handle rate limits by checking HTTP status codes and implementing retries with appropriate delays.
- **Error Handling**: Use try-except blocks to catch and manage errors that occur during API requests.

### Where to Use
API consumption is crucial in web development, mobile apps, data integration, and any application requiring interaction with external services or data sources.

## Diagrams

### API Request-Response Cycle with Authentication Diagram
![API Request-Response Cycle with Authentication](images/api_request_response_cycle_authentication.png)

### Rate Limiting Flowchart
![Rate Limiting Flowchart](images/rate_limiting_flowchart.png)

### Error Handling in API Requests Diagram
![Error Handling in API Requests](images/error_handling_api_requests.png)

## Syntax
```python
# Making authenticated API requests
import requests

api_url = "https://api.example.com/data"
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
}

response = requests.get(api_url, headers=headers)
data = response.json()

# Handling rate limits
import time

while True:
    response = requests.get(api_url, headers=headers)
    if response.status_code == 429:  # Too Many Requests
        retry_after = int(response.headers.get('Retry-After', 1))
        time.sleep(retry_after)
    else:
        break

# Error handling
try:
    response = requests.get(api_url, headers=headers)
    response.raise_for_status()
    data = response.json()
except requests.exceptions.HTTPError as err:
    print(f"HTTP error occurred: {err}")
except Exception as err:
    print(f"Other error occurred: {err}")
```

## Example Code
```python
# Authenticated API request example
import requests

api_url = "https://api.github.com/user"
headers = {
    'Authorization': 'token YOUR_GITHUB_TOKEN'
}

response = requests.get(api_url, headers=headers)
if response.status_code == 200:
    data = response.json()
    print(data)  # Output: JSON response from GitHub API
else:
    print(f"Failed to fetch data: {response.status_code}")

# Handling rate limits example
import time

api_url = "https://api.github.com/rate_limit"
headers = {
    'Authorization': 'token YOUR_GITHUB_TOKEN'
}

while True:
    response = requests.get(api_url, headers=headers)
    if response.status_code == 429:  # Too Many Requests
        retry_after = int(response.headers.get('Retry-After', 1))
        print(f"Rate limit exceeded. Retrying after {retry_after} seconds.")
        time.sleep(retry_after)
    else:
        data = response.json()
        print(data)  # Output: Rate limit information
        break

# Error handling example
try:
    response = requests.get(api_url, headers=headers)
    response.raise_for_status()
    data = response.json()
    print(data)  # Output: JSON response from API
except requests.exceptions.HTTPError as err:
    print(f"HTTP error occurred: {err}")
except Exception as err:
    print(f"Other error occurred: {err}")
```

## Explanation Code Step by Step
1. Authenticated API Request:

	- Include an Authorization header with the access token to authenticate requests. The server validates the token and returns the response.
2. Handling Rate Limits:

	- Continuously make requests and check for HTTP status code 429 (Too Many Requests). If encountered, retrieve the Retry-After header and wait before retrying.
3. Error Handling:

	- Use try-except blocks to catch and handle errors such as HTTPError for HTTP-specific issues and generic exceptions for other errors.

## Key Points to Remember
1. Authentication: Use the Authorization header for access tokens or API keys.
2. Rate Limits: Check for HTTP status code 429 and handle rate limits by implementing retry logic with delays.
3. Error Handling: Use try-except blocks to handle various types of errors in API requests.
4. Library: The requests library simplifies managing API interactions in Python.

## Quick Summary
Working with APIs involves making requests, handling authentication, managing rate limits, and dealing with errors effectively. Proper handling ensures secure and reliable communication with external services. The requests library is a powerful tool for these tasks in Python.

## Quiz
1. What is the purpose of authentication in API requests?
2. How do you handle rate limits when making API requests?
3. What is the significance of error handling in API requests?

## Labs
1. Lab 17.1: Authenticated API Request
	Objective: Write a program that makes an authenticated API request to a public API that requires a token.
	
	Instructions:
	
	Choose a public API that requires authentication.
	Implement a script to make an authenticated request and print the response.
	```python
	import requests
	
	api_url = "https://api.example.com/data"
	headers = {
	    'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
	}
	
	response = requests.get(api_url, headers=headers)
	if response.status_code == 200:
	    print(response.json())
	else:
	    print(f"Failed to fetch data: {response.status_code}")
	```
2. Lab 17.2: Handling Rate Limits
	Objective: Create a program that handles rate limits when making requests to an API.
	
	Instructions:
	
	Select an API that imposes rate limits.
	Implement a script to manage rate limits by checking the status code and implementing retries with delays.
	```python
	import time
	import requests
	
	api_url = "https://api.example.com/rate_limit"
	headers = {
	    'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
	}
	
	while True:
	    response = requests.get(api_url, headers=headers)
	    if response.status_code == 429:
	        retry_after = int(response.headers.get('Retry-After', 1))
	        print(f"Rate limit exceeded. Retrying after {retry_after} seconds.")
	        time.sleep(retry_after)
	    else:
	        print(response.json())
	        break
3. Lab 17.3: Error Handling in API Requests
	Objective: Develop a program that includes error handling for API requests, printing specific error messages for HTTP and other errors.
	
	Instructions:

	Implement a script that makes an API request.
	Use try-except blocks to handle and print specific error messages for different types of errors.
	```python
	import requests
	
	api_url = "https://api.example.com/data"
	headers = {
	    'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
	}
	
	try:
	    response = requests.get(api_url, headers=headers)
	    response.raise_for_status()
	    print(response.json())
	except requests.exceptions.HTTPError as err:
	    print(f"HTTP error occurred: {err}")
	except Exception as err:
	    print(f"Other error occurred: {err}")
	```
