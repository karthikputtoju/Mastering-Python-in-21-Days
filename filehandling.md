# Python File Handling and Error Handling

| Topic                                    | Description                                                                   | Example                                               |
|------------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Opening and Closing Files**             | Managing file operations using `open()` and `close()` methods.                 | ```python file = open('file.txt', 'r') file.close() ``` |
| **Reading and Writing Text Files**        | Performing read and write operations on text files using file objects.         | ```python with open('file.txt', 'w') as file: file.write('Hello, World!') ``` |
| **Working with File Paths and Directories** | Manipulating file paths and directories using `os` module.                    | ```python import os os.mkdir('directory') ```        |
| **Error Handling and Exceptions**         | Handling potential errors and exceptions during file operations.               | ```python try: file = open('file.txt', 'r') except FileNotFoundError: print('File not found') ``` |
| **Context Managers and the `with` Statement** | Managing resources and ensuring proper cleanup with `with` statement.         | ```python with open('file.txt', 'r') as file: data = file.read() ``` |

## Opening and Closing Files
```python
# Opening a file in read mode
file = open('file.txt', 'r')

# Closing the file
file.close()
```
## Reading and Writing Text Files
```python
# Writing to a file
with open('file.txt', 'w') as file:
    file.write('Hello, World!')

# Reading from a file
with open('file.txt', 'r') as file:
    content = file.read()
    print(content)  # Output: Hello, World!
```
## Working with File Paths and Directories
```python
# Creating a directory
import os
os.mkdir('directory')

# Listing files in a directory
files = os.listdir('directory')
print(files)
```
## Error Handling and Exceptions
```python
# Handling file not found exception
try:
    file = open('file.txt', 'r')
except FileNotFoundError:
    print('File not found')
```
## Context Managers and the with Statement
```python
# Using with statement for file handling
with open('file.txt', 'r') as file:
    data = file.read()
    print(data)
```
This table provides an overview of file handling, error handling, and the use of context managers in Python, including descriptions, examples, and operations for each topic.
