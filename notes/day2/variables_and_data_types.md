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
- **Why it is Required**: Understanding data types is crucial for performing operations and ensuring that data is handled correctly. Different data types support different operations.
- **How to Implement**: Data types are automatically assigned based on the value assigned to the variable. You can check the type of a variable using the `type()` function.
- **Common Data Types**:
  - **Integer (`int`)**: Whole numbers, e.g., `5`, `-3`.
  - **Float (`float`)**: Decimal numbers, e.g., `3.14`, `-0.001`.
  - **String (`str`)**: Text, e.g., `"Hello"`, `"Python"`.
  - **Boolean (`bool`)**: True or False values.

### Type Conversion
- **Definition**: Type conversion refers to changing the data type of a variable. This can be done implicitly by Python or explicitly using conversion functions.
- **Why it is Required**: Type conversion is useful when you need to perform operations between different data types or when converting data for specific purposes.
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

