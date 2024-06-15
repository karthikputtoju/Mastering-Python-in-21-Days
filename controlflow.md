# Python Conditional Statements and Loops

| Topic                                   | Description                                                                                       |
|-----------------------------------------|---------------------------------------------------------------------------------------------------|
| **If Statements**                      | Executes a block of code if a condition is true.                                                   | 
| **Elif and Else Statements**           | Provides additional conditions to check if the previous conditions are not met.                    | 
| **For Loops**                          | Iterates over a sequence (such as lists, tuples, or strings) or other iterable objects.            | 
| **While Loops**                        | Executes a block of code as long as a specified condition is true.                                 | 
| **Loop Control Statements**            | Change the flow of a loop: `break` terminates the loop, `continue` skips the current iteration.    | 
| **Nested Loops**                       | Contains one or more loops inside another loop.                                                    | 
| **Loop Else Clauses**                  | Executes a block of code when the loop condition becomes false.                                    | 

## If Statements

```python
# Example of if statement
x = 10
if x > 5:
    print("x is greater than 5")
```
## If-elif-else Statements

```python
# Example of if-elif-else statement
grade = 85
if grade >= 90:
    print("A")
elif grade >= 80:
    print("B")
else:
    print("C")
```
## For Loops

```python
# Example of for loop
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```
## While Loop

```python
# Example of while loop
count = 0
while count < 5:
    print(count)
    count += 1
```

## Loop Control Statement - Break and Continue
```python
# Example of break statement
for letter in 'python':
    if letter == 'h':
        break
    print('Current Letter :', letter)

# Example of continue statement
for letter in 'python':
    if letter == 'h':
        continue
    print('Current Letter :', letter)
```
## Nested Loop Statement
```python
# Example of nested loops
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} * {j} = {i * j}")
```
## Loop Else Clauses

```python
# Example of loop else clause
numbers = [1, 2, 3, 4, 5]
for number in numbers:
    if number > 5:
        break
else:
    print("All numbers are less than or equal to 5")
```
