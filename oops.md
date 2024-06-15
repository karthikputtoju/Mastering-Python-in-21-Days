# Python Object-Oriented Programming (OOP)

| Topic                                    | Description                                                                   | Example                                               |
|------------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------|
| **Defining Classes and Creating Objects** | Creating classes and instantiating objects.                                    | ```python class Dog: pass dog1 = Dog() ```            |
| **Class Attributes and Instance Attributes** | Differentiating between class-level and instance-level attributes.             | ```python class Dog: species = 'Canis' dog1.species = 'Canis' ``` |
| **Inheritance and Method Overriding**    | Deriving new classes from existing ones and overriding methods.                | ```python class Animal: def speak(self): print("Sound") class Dog(Animal): def speak(self): print("Bark") ``` |
| **Polymorphism and Method Overloading**  | Using polymorphism to call different methods based on the object.               | ```python def make_sound(animal): animal.speak() dog = Dog() make_sound(dog) ``` |
| **Class Methods, Static Methods, and Properties** | Using class methods, static methods, and properties for different purposes.    | ```python class MyClass: @classmethod def class_method(cls): pass @staticmethod def static_method(): pass @property def prop(self): return self._prop ``` |

## Defining Classes and Creating Objects
```python
# Defining a class and creating an object
class Dog:
    def __init__(self, name):
        self.name = name

dog1 = Dog("Buddy")
print(dog1.name)  # Output: Buddy
```
## Class Attributes and Instance Attributes
```python
# Class attributes and instance attributes
class Dog:
    species = 'Canis familiaris'  # Class attribute

    def __init__(self, name):
        self.name = name  # Instance attribute

dog1 = Dog("Buddy")
dog2 = Dog("Max")

print(dog1.species)  # Output: Canis familiaris
print(dog1.name)     # Output: Buddy
print(dog2.species)  # Output: Canis familiaris
print(dog2.name)     # Output: Max
```

## Inheritance and Method Overriding
```python
# Inheritance and method overriding
class Animal:
    def speak(self):
        print("Animal sound")

class Dog(Animal):
    def speak(self):
        print("Bark")

dog = Dog()
dog.speak()  # Output: Bark
```
## Polymorphism and Method Overloading
```python
# Polymorphism
class Animal:
    def speak(self):
        print("Animal sound")

class Dog(Animal):
    def speak(self):
        print("Bark")

class Cat(Animal):
    def speak(self):
        print("Meow")

def make_sound(animal):
    animal.speak()

dog = Dog()
cat = Cat()

make_sound(dog)  # Output: Bark
make_sound(cat)  # Output: Meow
```
## Class Methods, Static Methods, and Properties
```python
# Class methods, static methods, and properties
class MyClass:
    _prop = None

    def __init__(self, prop):
        self._prop = prop

    @classmethod
    def class_method(cls):
        return "This is a class method"

    @staticmethod
    def static_method():
        return "This is a static method"

    @property
    def prop(self):
        return self._prop

    @prop.setter
    def prop(self, value):
        self._prop = value

obj = MyClass("Initial Value")
print(MyClass.class_method())    # Output: This is a class method
print(MyClass.static_method())   # Output: This is a static method
print(obj.prop)                  # Output: Initial Value
obj.prop = "New Value"
print(obj.prop)                  # Output: New Value
```
