# Day 9: More on OOP

## Title: More on OOP

### Topics Covered
- Encapsulation
- Abstraction
- Overriding
- Class and Static Methods

## Detailed Explanations

### Definition
- **Encapsulation**: The bundling of data and methods within a class. It restricts direct access to some of the object's components.
- **Abstraction**: The process of hiding the implementation details from the user and providing only the functionality.
- **Overriding**: Allows a subclass to provide a specific implementation of a method defined in its superclass.
- **Class and Static Methods**: Methods that belong to the class rather than an instance. Class methods are defined using `@classmethod`, and static methods using `@staticmethod`.

### Why it is Required
These concepts promote:
- **Data Hiding**: Encapsulation protects the internal state of an object from unintended modifications.
- **Modularity**: Abstraction helps in reducing complexity by hiding unnecessary details.
- **Flexibility**: Overriding allows a subclass to implement its own version of a method.
- **Utility**: Class and static methods can be used for operations that are related to the class, but not dependent on the instance state.

### How to Implement
- **Encapsulation**: Use access modifiers (`_` and `__`) to restrict access to class variables.
- **Abstraction**: Implement abstract classes and methods using the `abc` module.
- **Overriding**: Redefine a method in the subclass that is already defined in the parent class.
- **Class and Static Methods**: Use the `@classmethod` and `@staticmethod` decorators.

### Where to Use
- **Encapsulation and Abstraction**: Used to protect data and provide a clear interface.
- **Overriding**: Used in inheritance hierarchies to allow specific implementations.
- **Class and Static Methods**: Used for utility functions that do not depend on instance state.

## Diagrams

### Encapsulation Diagram
![image](https://github.com/user-attachments/assets/6de561a1-54c5-421b-ac36-47faffe3cd63)

### Abstract Class and Method Diagram
![image](https://github.com/user-attachments/assets/d3e0f10a-16b9-4db4-9c94-b85387da2673)

### Method Overriding Flow Diagram
![image](https://github.com/user-attachments/assets/4f7cb2b3-922a-40b0-88b0-189448dd295c)

## Syntax
```python
# Encapsulation
class ClassName:
    def __init__(self, parameter):
        self.__private_variable = parameter

    def get_variable(self):
        return self.__private_variable

# Abstraction
from abc import ABC, abstractmethod

class AbstractClass(ABC):
    @abstractmethod
    def abstract_method(self):
        pass

# Overriding
class ParentClass:
    def method(self):
        return "Parent"

class ChildClass(ParentClass):
    def method(self):
        return "Child"

# Class and Static Methods
class MyClass:
    @classmethod
    def class_method(cls):
        return "class method called"

    @staticmethod
    def static_method():
        return "static method called"
```

## Example Code
```python
# Encapsulation example
class Person:
    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    def get_name(self):
        return self.__name

    def set_name(self, name):
        self.__name = name

person = Person("Alice", 30)
print(person.get_name())  # Output: Alice

# Abstraction example
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Woof!"

dog = Dog()
print(dog.sound())  # Output: Woof!

# Overriding example
class Parent:
    def greet(self):
        return "Hello from Parent"

class Child(Parent):
    def greet(self):
        return "Hello from Child"

child = Child()
print(child.greet())  # Output: Hello from Child

# Class and Static Methods example
class MyClass:
    @classmethod
    def class_method(cls):
        return "Class method called"

    @staticmethod
    def static_method():
        return "Static method called"

print(MyClass.class_method())  # Output: Class method called
print(MyClass.static_method())  # Output: Static method called
```

## Explanation Code Step by Step
1. Encapsulation:

	- self.__name is a private variable.
	- get_name() is a getter method to access the private variable.
2. Abstraction:

	- class Animal(ABC) defines an abstract class with an abstract method sound().
3. Overriding:

	- def greet(self): in Child class overrides the method from Parent class.
4. Class and Static Methods:

	- @classmethod decorator defines a class method.
	- @staticmethod decorator defines a static method.

## Key Points to Remember
1. Encapsulation: Protects data within a class using private variables.
2. Abstraction: Provides a clear interface by hiding implementation details.
3. Overriding: Allows subclasses to provide specific implementations of methods.
4. Class Methods: Operate on the class itself.
5. Static Methods: Do not depend on class or instance state.

## Quick Summary
Encapsulation, abstraction, overriding, class methods, and static methods are advanced OOP concepts that promote data hiding, modularity, and flexibility. They enhance code maintainability and security.

## Quiz
1. What is encapsulation in OOP?
2. How do you define an abstract method in Python?
3. What is the difference between class methods and static methods?

## Labs
1. Lab 9.1: Create a Class BankAccount
   Objective: Create a class BankAccount with private attributes balance and methods to deposit, withdraw, and get balance using encapsulation.

   Instructions:

   Define the BankAccount class with a private attribute __balance.
   Implement methods to deposit, withdraw, and get balance.
   	```python
	class BankAccount:
	    def __init__(self):
	        self.__balance = 0
	
	    def deposit(self, amount):
	        if amount > 0:
	            self.__balance += amount
	
	    def withdraw(self, amount):
	        if 0 < amount <= self.__balance:
	            self.__balance -= amount
	
	    def get_balance(self):
	        return self.__balance
	
	# Test the BankAccount class
	account = BankAccount()
	account.deposit(100)
	account.withdraw(50)
	print(account.get_balance())  # Output: 50
	```
2. Lab 9.2: Implement an Abstract Class Shape
   Objective: Implement an abstract class Shape with a method area(). Create subclasses Circle and Rectangle and override the area() method in each.

   Instructions:

   Define the abstract class Shape with an abstract method area().
   Create the Circle subclass with a specific implementation of area().
   Create the Rectangle subclass with a specific implementation of area().
	```python
	from abc import ABC, abstractmethod
	
	class Shape(ABC):
	    @abstractmethod
	    def area(self):
	        pass
	
	class Circle(Shape):
	    def __init__(self, radius):
	        self.radius = radius
	
	    def area(self):
	        return 3.14 * (self.radius ** 2)
	
	class Rectangle(Shape):
	    def __init__(self, width, height):
	        self.width = width
	        self.height = height
	
	    def area(self):
	        return self.width * self.height
	
	# Test the Shape subclasses
	circle = Circle(5)
	rectangle = Rectangle(4, 6)
	
	print(circle.area())  # Output: 78.5
	print(rectangle.area())  # Output: 24
	```
