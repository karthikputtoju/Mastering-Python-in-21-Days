# Day 6: File Handling

## Title: File Handling

### Topics Covered
- Reading Files
- Writing Files
- File Methods
- Context Managers

## Detailed Explanations

### Definition
File handling refers to the process of performing operations such as reading from and writing to files. This allows programs to store and retrieve data, interact with external data sources, and persist data between program executions.

### Why it is Required
File handling is crucial for:
- **Data Persistence**: Saving data between program runs.
- **Data Interaction**: Reading from or writing to external data sources such as logs, configuration files, and data files.

### How to Implement
- **Opening Files**: Use the `open()` function with a mode ('r', 'w', 'a') to open a file.
- **Reading/Writing**: Use methods like `read()`, `write()`, and `close()` to manipulate file content.
- **Context Managers**: Use the `with` statement to ensure proper resource management and automatic file closure.

### Where to Use
File handling is used in:
- **Logging**: Recording events and errors.
- **Configuration Management**: Storing settings.
- **Data Analysis**: Reading data files for analysis.

## Diagrams

### File Handling Process Diagram
![File Handling Process Diagram](images/file_handling_process_diagram.png)

### Context Manager Workflow Diagram
![Context Manager Workflow Diagram](images/context_manager_workflow_diagram.png)

## Syntax
```python
# Opening a file
file = open('filename.txt', 'mode')

# Reading from a file
content = file.read()

# Writing to a file
file.write('Hello, World!')

# Closing a file
file.close()

# Using a context manager
with open('filename.txt', 'mode') as file:
    # Code block
```

## Example Code
```python
# Reading from a file
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# Writing to a file
with open('example.txt', 'w') as file:
    file.write('Hello, World!')

# Appending to a file
with open('example.txt', 'a') as file:
    file.write('\nAppend this line.')

# Reading line by line
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

## Explanation Code Step by Step
1. Reading from a File:

	- with open('example.txt', 'r') as file: opens the file in read mode.
	- content = file.read() reads the entire content of the file.
	- print(content) prints the content to the console.
2. Writing to a File:

	- with open('example.txt', 'w') as file: opens the file in write mode.
	- file.write('Hello, World!') writes the string to the file.
3. Appending to a File:

	- with open('example.txt', 'a') as file: opens the file in append mode.
	- file.write('\nAppend this line.') appends a new line to the file.
4. Reading Line by Line:

	- for line in file: iterates through each line in the file.
	- print(line.strip()) prints each line after stripping leading/trailing whitespace.

## Key Points to Remember
1. File Modes:
	- 'r' for reading.
	- 'w' for writing (overwrites the file).
	- 'a' for appending (adds to the file).
2. Context Managers: Use the with statement to handle file operations, ensuring that files are properly closed after their suite finishes.

## Quick Summary
File handling involves opening, reading from, writing to, and closing files. The open() function is used to access files, and context managers (with statement) help in managing resources efficiently. Understanding file methods and modes is key to effective file manipulation.

## Quiz
1. How do you open a file in read mode?
2. What is the purpose of a context manager in file handling?
3. Name three methods for reading from a file.

## Labs
1. Lab 6.1: Read File Content
	Objective: Write a program that reads a text file and prints its content.
	
	Instructions:
	
	Create a text file named sample.txt with some content.
	Write a Python script that reads and prints the content of sample.txt.
	```python
	# read_file.py
	with open('sample.txt', 'r') as file:
	    content = file.read()
	    print(content)
	```

2. Lab 6.2: Write and Read User Input
	Objective: Write a program that writes user input to a file and then reads and displays the content.
	
	Instructions:
	
	Write a Python script that prompts the user for input and writes it to a file named user_input.txt.
	After writing the input, the script should read the file and display its content.
	```python
	# write_and_read_user_input.py
	user_input = input("Enter some text: ")
	
	# Writing to file
	with open('user_input.txt', 'w') as file:
	    file.write(user_input)
	
	# Reading from file
	with open('user_input.txt', 'r') as file:
	    content = file.read()
	    print("File content:", content)
	```
