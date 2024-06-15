# Python Functions and Built-in Functions

| Topic                               | Description                                                                   | Example                                               |
|-------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Defining Functions with `def`**   | Creating reusable blocks of code with a name and optional parameters.         | ```python def greet(name): print(f"Hello, {name}!") ```|
| **Function Parameters and Arguments** | Passing data to functions through parameters and arguments.                  | ```python def add(a, b): return a + b ```             |
| **Return Statements and Returning Values** | Returning values from functions back to the caller.                          | ```python def square(x): return x ** 2 ```           |
| **Scope and Lifetime of Variables** | Understanding where variables can be accessed and how long they exist.       | ```python def my_function(): x = 10 print(x) ```     |
| **Lambda Functions**                 | Inline functions defined using the `lambda` keyword for simple tasks.        | ```python square = lambda x: x ** 2 ```              |
| **Anonymous Functions**             | Functions without a name, often used with higher-order functions like `map()`. | ```python list(map(lambda x: x ** 2, [1, 2, 3])) ``` |

### Defining Functions with `def`

```python
# Function to greet a person
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```
