# Day 14: API Responses

## Title: API Responses

### Topics Covered
- Understanding API Responses
- Handling JSON, XML, and HTML Responses
- Error Handling in API Responses

## Detailed Explanations

### Definition
API responses are the data sent by a server in response to a client's request. These responses can be in various formats such as JSON, XML, or HTML.

### Why it is Required
Understanding how to handle different types of API responses is crucial for developing applications that communicate with web services. Proper handling ensures the application can process and utilize the data efficiently.

### How to Implement
- Use libraries like `requests` to handle API responses.
- Parse JSON with `json`.
- Parse XML with `xml.etree.ElementTree`.
- Parse HTML with `BeautifulSoup`.

### Where to Use
API responses are used in web applications, mobile apps, data integration, and any system that consumes external data via APIs.

## Diagrams

### API Response Handling Diagram
![API Response Handling Diagram](images/api_response_handling.png)

### JSON Parsing Flowchart
![JSON Parsing Flowchart](images/json_parsing_flowchart.png)

### XML Parsing Diagram
![XML Parsing Diagram](images/xml_parsing_diagram.png)

## Syntax
```python
# Handling JSON response
import requests

response = requests.get('https://api.example.com/data')
data = response.json()

# Handling XML response
import requests
import xml.etree.ElementTree as ET

response = requests.get('https://api.example.com/data.xml')
root = ET.fromstring(response.content)

# Handling HTML response
import requests
from bs4 import BeautifulSoup

response = requests.get('https://example.com')
soup = BeautifulSoup(response.content, 'html.parser')
```

## Example Code
```python
# JSON response example
import requests

response = requests.get('https://api.github.com')
if response.status_code == 200:
    data = response.json()
    print(data)  # Output: JSON response from GitHub API

# XML response example
import requests
import xml.etree.ElementTree as ET

response = requests.get('https://www.w3schools.com/xml/note.xml')
if response.status_code == 200:
    root = ET.fromstring(response.content)
    for child in root:
        print(child.tag, child.text)  # Output: Elements and text from XML

# HTML response example
import requests
from bs4 import BeautifulSoup

response = requests.get('https://example.com')
if response.status_code == 200:
    soup = BeautifulSoup(response.content, 'html.parser')
    print(soup.title.text)  # Output: Title of the HTML page
```

## Explanation Code Step by Step
1. Handling JSON Response:

	- response.json() parses the JSON data from the response.
2. Handling XML Response:

	- ET.fromstring(response.content) parses the XML content.
	- Iterating through root prints each element and its text.
3. Handling HTML Response:

	- BeautifulSoup(response.content, 'html.parser') parses the HTML content.
	- soup.title.text retrieves the page title.

## Key Points to Remember
1. API responses can be in JSON, XML, or HTML format.
2. Use requests library to fetch API responses.
3. Parse JSON with response.json().
4. Parse XML with xml.etree.ElementTree.
5. Parse HTML with BeautifulSoup.

## Quick Summary
API responses come in various formats such as JSON, XML, and HTML. Proper handling and parsing of these responses are essential for using the data in applications. Libraries like requests, json, xml.etree.ElementTree, and BeautifulSoup facilitate easy handling of these formats.

## Quiz
1. What are the common formats of API responses?
2. How do you parse a JSON response in Python?
3. Which library is used for parsing HTML in Python?

## Labs
1. Lab 14.1: JSON Response Handling
	Objective: Write a program that fetches a JSON response from a public API and prints specific fields.
	
	Instructions:
	
	Use the requests library to make a GET request to a public API that returns JSON.
	Extract and print specific fields from the JSON response.
	```python
	import requests
	
	response = requests.get('https://api.github.com')
	if response.status_code == 200:
	    data = response.json()
	    print(f"API URL: {data['current_user_url']}")  # Example field
	```
2. Lab 14.2: XML Response Handling
	Objective: Create a program that fetches an XML response from a public API and extracts and prints specific elements.
	
	Instructions:
	
	Use the requests library to make a GET request to a public API that returns XML.
	Extract and print specific elements from the XML response.
	```python
	import requests
	import xml.etree.ElementTree as ET
	
	response = requests.get('https://www.w3schools.com/xml/note.xml')
	if response.status_code == 200:
	    root = ET.fromstring(response.content)
	    print(f"To: {root.find('to').text}")
	    print(f"From: {root.find('from').text}")
3. Lab 14.3: HTML Response Handling
	Objective: Develop a program that fetches an HTML page and prints the content of all paragraph tags.
	
	Instructions:
	
	Use the requests library to make a GET request to a web page.
	Use BeautifulSoup to parse the HTML and print the content of all paragraph tags.
	```python
	import requests
	from bs4 import BeautifulSoup
	
	response = requests.get('https://example.com')
	if response.status_code == 200:
	    soup = BeautifulSoup(response.content, 'html.parser')
	    for p in soup.find_all('p'):
	        print(p.text)
	```
