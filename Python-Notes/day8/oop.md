# Day 8: Object-Oriented Programming

## Title: Object-Oriented Programming

### Topics Covered
- Classes and Objects
- Methods
- Inheritance
- Polymorphism

## Detailed Explanations

### Definition
Object-oriented programming (OOP) is a programming paradigm that uses objects and classes to structure software in a way that models real-world entities. OOP encapsulates data and behavior within objects, making it easier to manage and extend complex systems.

### Why it is Required
OOP promotes:
- **Code Reuse**: By defining common behaviors in base classes and reusing them in derived classes.
- **Modularity**: By organizing code into distinct classes with specific responsibilities.
- **Encapsulation**: By hiding the internal state and requiring all interactions to be performed through an object's methods.
- **Maintenance and Scalability**: By making it easier to manage and extend code as requirements change.

### How to Implement
- **Classes**: Defined using the `class` keyword, representing a blueprint for objects.
- **Objects**: Instances of classes created to represent real-world entities.
- **Inheritance**: Allows a class to inherit properties and methods from another class using the `class SubClassName(ParentClassName):` syntax.
- **Polymorphism**: Enables a single interface to represent different underlying forms (data types).

### Where to Use
OOP is widely used in:
- **Large-scale Applications**: To manage complexity and ensure code reuse.
- **GUI Applications**: Where each GUI element can be modeled as an object.
- **Systems**: Where modularity and code reuse are critical for maintainability.

## Diagrams

### Class and Object Diagram
![image](https://github.com/user-attachments/assets/756c6c74-711d-4eec-9396-7ea2dc14c7de)

### Inheritance Hierarchy Diagram
![image](https://github.com/user-attachments/assets/834baa18-295e-416d-9853-f7ad0933c321)

## Syntax
```python
# Class definition
class ClassName:
    # Constructor
    def __init__(self, parameters):
        # Instance variables
        self.variable = value

    # Method
    def method_name(self):
        # Code block

# Inheritance
class SubClassName(ParentClassName):
    # Code block

# Polymorphism
def function_name(parameter):
    # Code block
```

## Example Code
```python
# Class and object example
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return f"{self.name} says woof!"

dog1 = Dog("Buddy", 3)
print(dog1.bark())  # Output: Buddy says woof!

# Inheritance example
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        raise NotImplementedError("Subclasses must implement this method")

class Cat(Animal):
    def speak(self):
        return f"{self.name} says meow!"

cat1 = Cat("Whiskers")
print(cat1.speak())  # Output: Whiskers says meow!

# Polymorphism example
def make_sound(animal):
    print(animal.speak())

make_sound(dog1)  # Output: Buddy says woof!
make_sound(cat1)  # Output: Whiskers says meow!
```

## Explanation Code Step by Step
1. Class Definition:

	- class Dog: defines a class named Dog with an __init__ method (constructor) and a bark method.
	- The __init__ method initializes the object's attributes.
2. Creating Objects:

	- dog1 = Dog("Buddy", 3) creates an instance of the Dog class with the name "Buddy" and age 3.
3. Inheritance:

	- class Cat(Animal): defines a subclass Cat that inherits from the Animal class.
	- The speak method in the Animal class is overridden in the Cat class.
4. Polymorphism:

	- def make_sound(animal): defines a function that accepts any object with a speak method and calls it.
	- This function demonstrates polymorphism by calling the speak method on different types of objects (Dog and Cat).

## Key Points to Remember
1. Classes: Defined using the class keyword; they encapsulate data and behavior.
2. Objects: Instances of classes; created using the class constructor.
3. Methods: Functions defined within a class; they define the behavior of objects.
4. Inheritance: Mechanism to create a new class from an existing class.
5. Polymorphism: Ability of different classes to be treated as instances of the same class through a common interface.

## Quick Summary
Object-oriented programming (OOP) uses classes and objects to structure software. It promotes modularity and code reuse through inheritance and polymorphism. Methods define object behavior, and classes model entities.

## Quiz
1. What is a class in Python?
2. How do you create an object of a class?
3. What is inheritance in OOP?

## Labs
1. Lab 8.1: Create a Class Person
	Objective: Create a class Person with attributes name and age and a method to display the details.
	
	Instructions:
	
	Define the Person class with __init__, name, and age attributes.
	Implement a method to display the person's details.
	```python
	class Person:
	    def __init__(self, name, age):
	        self.name = name
	        self.age = age
	
	    def display_details(self):
	        print(f"Name: {self.name}, Age: {self.age}")

	# Test the Person class
	person1 = Person("Alice", 30)
	person1.display_details()  # Output: Name: Alice, Age: 30
	```
2. Lab 8.2: Create a Class Vehicle with Subclass Car
	Objective: Create a class Vehicle with a subclass Car. Implement methods in both classes and demonstrate polymorphism.
	
	Instructions:
	
	Define the Vehicle class with a __init__ method and a display_info method.
	Define the Car subclass inheriting from Vehicle with an overridden display_info method.
	Demonstrate polymorphism by using a function that accepts a Vehicle object and calls its display_info method.
	```python
	class Vehicle:
	    def __init__(self, make, model):
	        self.make = make
	        self.model = model
	
	    def display_info(self):
	        print(f"Vehicle Make: {self.make}, Model: {self.model}")
	
	class Car(Vehicle):
	    def __init__(self, make, model, doors):
	        super().__init__(make, model)
	        self.doors = doors
	
	    def display_info(self):
	        print(f"Car Make: {self.make}, Model: {self.model}, Doors: {self.doors}")
	
	# Function to demonstrate polymorphism
	def show_vehicle_info(vehicle):
	    vehicle.display_info()
	
	# Test the Vehicle and Car classes
	vehicle1 = Vehicle("Toyota", "Camry")
	car1 = Car("Honda", "Civic", 4)
	
	show_vehicle_info(vehicle1)  # Output: Vehicle Make: Toyota, Model: Camry
	show_vehicle_info(car1)      # Output: Car Make: Honda, Model: Civic, Doors: 4
	```
