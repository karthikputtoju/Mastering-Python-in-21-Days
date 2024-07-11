# Day 2: Variables and Data Types

## Title: Variables and Data Types

### Topics Covered
- Variables
- Data Types
- Type Conversion
- Constants

## Detailed Explanations

### Variables
- **Definition**: Variables are containers for storing data values. In Python, variables are created by assigning a value to them.
- **Why it is Required**: Variables are essential for managing and manipulating data within a program. They allow you to store information and perform operations on it.
- **How to Implement**: To create a variable, use the `=` operator to assign a value to it. For example, `x = 5` creates a variable `x` with the value `5`.

### Data Types
- **Definition**: Data types specify the type of data a variable holds. Common data types in Python include integers, floats, strings, and booleans.
- **Why it is Required**: Understanding data types is crucial for performing operations and ensuring that data is handled correctly. Different data types support various operations.
- **How to Implement**: Data types are automatically assigned based on the value assigned to the variable. You can check the type of a variable using the `type()` function.
- **Common Data Types**:
  - **Integer (`int`)**: Whole numbers, e.g., `5`, `-3`.
  - **Float (`float`)**: Decimal numbers, e.g., `3.14`, `-0.001`.
  - **String (`str`)**: Text, e.g., `"Hello"`, `"Python"`.
  - **Boolean (`bool`)**: True or False values.

### Type Conversion
- **Definition**: Type conversion refers to changing the data type of a variable. This can be done implicitly by Python or explicitly using conversion functions.
- **Why it is Required**: Type conversion is useful when performing operations between different data types or converting data for specific purposes.
- **How to Implement**: Use built-in functions like `int()`, `float()`, and `str()` to convert between types.
- **Examples**:
  - Convert a float to an integer: `int(3.14)` results in `3`.
  - Convert an integer to a string: `str(10)` results in `"10"`.
  - Convert a string to a float: `float("3.14")` results in `3.14`.

### Constants
- **Definition**: Constants are variables whose values should not change during the execution of a program. While Python does not have built-in constants, naming conventions (e.g., using uppercase) are used to indicate constants.
- **Why it is Required**: Constants are used to represent fixed values that should not be altered, such as mathematical constants or configuration settings.
- **How to Implement**: Define constants using uppercase variable names. For example, `PI = 3.14159` represents the mathematical constant π.

## Diagrams

### Variable Assignment Diagram
![Variable Assignment Diagram](images/variable_assignment_diagram.png)

### Data Type Classification Diagram
![Data Type Classification Diagram](images/data_type_classification_diagram.png)

## Syntax
```python
# Variable assignment
x = 5        # Integer
y = 3.14     # Float
name = "Alice"  # String
is_student = True  # Boolean

# Type Conversion
float_value = 10.99
int_value = int(float_value)  # Convert float to int
print(int_value)

int_value = 100
str_value = str(int_value)    # Convert int to string
print(str_value)

str_value = "123.45"
float_value = float(str_value)  # Convert string to float
print(float_value)

# Constant
PI = 3.14159
```

## Example Code
```python
# Variables and Data Types Example
x = 10
y = 3.14
name = "Alice"
is_student = True

print("x:", x, "Type:", type(x))          # <class 'int'>
print("y:", y, "Type:", type(y))          # <class 'float'>
print("name:", name, "Type:", type(name)) # <class 'str'>
print("is_student:", is_student, "Type:", type(is_student)) # <class 'bool'>

# Type Conversion
float_value = 10.99
int_value = int(float_value)
print("Converted int:", int_value)

int_value = 100
str_value = str(int_value)
print("Converted string:", str_value)

str_value = "123.45"
float_value = float(str_value)
print("Converted float:", float_value)

# Constant
print("PI:", PI)
```

## Explanation Code Step by Step
- **Variable Assignment**:
  - x = 10, y = 3.14, name = "Alice", and is_student = True assign values to variables of different data types.
- **Type Checking**:
  - print(type(x)) shows <class 'int'>, indicating that x is an integer.
  - print(type(y)) shows <class 'float'>, indicating that y is a float.
  - print(type(name)) shows <class 'str'>, indicating that name is a string.
  - print(type(is_student)) shows <class 'bool'>, indicating that is_student is a boolean.
- **Type Conversion**:
  - int(float_value) converts the float 10.99 to an integer 10.
  - str(int_value) converts the integer 100 to the string "100".
  - float(str_value) converts the string "123.45" to the float 123.45.
- **Constants**:
  - PI is defined as a constant with the value 3.14159 and used in the program.

## Key Points to Remember
1. Variables are created by assignment and do not need explicit declaration.
2. Python supports various data types, including int, float, str, and bool.
3. Use the type() function to check the data type of a variable.
4. Type conversion can be performed using functions like int(), float(), and str().
5. Constants are typically represented using uppercase names.

## Quick Summary
1. Variables store data values, and data types define the kind of data stored.
2. Python automatically assigns data types based on the value assigned to a variable.
3. Type conversion allows you to change data types when necessary, and constants are used for fixed values.

## Quiz
1. How do you declare a variable in Python?
2. Name four basic data types in Python.
3. How can you check the data type of a variable?
4. How do you perform type conversion in Python?
5. What is a constant, and how is it typically represented in Python?

## Labs
1. Lab 2.1: Create Variables
   Objective: Create variables of different data types and print their values and types.

   Instructions:

   Create variables for an integer, a float, a string, and a boolean.
   Print the values and types of these variables.

    ```python
    # Lab 2.1 Code
    age = 25
    height = 5.9
    city = "New York"
    is_employee = True
    
    print("Age:", age, "Type:", type(age))
    print("Height:", height, "Type:", type(height))
    print("City:", city, "Type:", type(city))
    print("Is Employee:", is_employee, "Type:", type(is_employee))
    ```

2. Lab 2.2: Type Conversion
   Objective: Perform type conversion between different data types and observe the results.

   Instructions:

   Convert a float to an integer and print the result.
   Convert an integer to a string and print the result.
   Convert a string to a float and print the result.

    ```python
    # Lab 2.2 Code
    float_value = 10.99
    int_value = int(float_value)  # Convert float to int
    print("Converted int:", int_value)
    
    int_value = 100
    str_value = str(int_value)    # Convert int to string
    print("Converted string:", str_value)
    
    str_value = "123.45"
    float_value = float(str_value)  # Convert string to float
    print("Converted float:", float_value)
    ```
