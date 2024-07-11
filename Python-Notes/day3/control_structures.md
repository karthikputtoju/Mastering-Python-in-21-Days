# Day 3: Control Structures

## Title: Control Structures

### Topics Covered
- Conditional Statements
- Loops
- Control Flow

## Detailed Explanations

### Definition
Control structures manage the flow of execution in a program. They allow you to control the sequence of execution based on conditions and repetitions. The primary control structures in Python are:
- **Conditional Statements**: Used to execute code blocks based on conditions. Keywords include `if`, `elif`, and `else`.
- **Loops**: Used to execute code repeatedly. Keywords include `for` and `while`.

### Why it is Required
Control structures are essential for making programs dynamic and responsive to different conditions and scenarios. They allow for decision-making and handling repetitive tasks, making programs more efficient and versatile.

### How to Implement
1. **Conditional Statements**: Use `if`, `elif`, and `else` keywords to execute different code blocks based on conditions.
2. **Loops**: Use `for` to iterate over sequences and `while` to repeat code as long as a condition is true.

### Where to Use
Control structures are used in nearly every program to handle decision-making processes and iterative operations. They are fundamental for creating logical flow and managing program execution.

## Diagrams

### Flowchart of Conditional Statements
![image](https://github.com/karthikputtoju/Mastering-Python-in-21-Days/assets/37204779/2be0e4aa-96c5-426f-8986-fc1a6815baf9)


### Loop Structure Diagram
![Loop Structure Diagram](images/loop_structure_diagram.png)

## Syntax
```python
# Conditional statement
if condition:
    # Code block
elif another_condition:
    # Code block
else:
    # Code block

# For loop
for item in iterable:
    # Code block

# While loop
while condition:
    # Code block
```

## Example Code
```python
# Control structure examples
x = 10

# Conditional statement
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")

# For loop
for i in range(5):
    print(i)

# While loop
count = 0
while count < 5:
    print(count)
    count += 1
```

## Explanation Code Step by Step
1. Conditional Statement:
	- if x > 5: checks if x is greater than 5. If true, it prints "x is greater than 5".
	- elif x == 5: checks if x is equal to 5. If true, it prints "x is equal to 5".
	- else: covers all other cases where x is less than 5, printing "x is less than 5".
2. For Loop:
	- for i in range(5): iterates over a range of numbers from 0 to 4 (inclusive). Each number is printed in turn.
3. While Loop:
	- while count < 5: continues to execute as long as count is less than 5. It prints the value of count and increments count by 1 in each iteration.

## Key Points to Remember
1. Conditional Statements: Use if to test conditions, elif for additional conditions, and else for the default case.
2. For Loops: Useful for iterating over sequences like lists, tuples, or ranges.
3. While Loops: Useful for repeating code as long as a condition is true. Ensure that the condition eventually becomes false to avoid infinite loops.

## Quick Summary
Control structures direct the flow of execution in a program. Conditional statements enable decision-making, while loops handle repetitive tasks. Use if, elif, and else for conditionals, and for and while for loops.

## Quiz
1. What is the purpose of control structures in a program?
2. How do you write a for loop in Python?
3. What is the difference between if and elif in conditional statements?
4. What does a while loop do?

## Labs
1. Lab 3.1: Conditional Statements
   Objective: Write a program that uses conditional statements to check if a number is positive, negative, or zero.

   Instructions:

   Prompt the user to enter a number.
   Use conditional statements to check if the number is positive, negative, or zero.
   Print the result.
	```python
	# Lab 3.1 Code
	number = float(input("Enter a number: "))
	
	if number > 0:
	    print("The number is positive.")
	elif number < 0:
	    print("The number is negative.")
	else:
	    print("The number is zero.")
	```
2. Lab 3.2: Looping Through Numbers
   Objective: Write a program that prints all even numbers between 1 and 20 using a loop.

   Instructions:

   Use a for loop to iterate through numbers from 1 to 20.
   Print the even numbers.
	```python
	# Lab 3.2 Code
	for num in range(1, 21):
	    if num % 2 == 0:
	        print(num)
	```

