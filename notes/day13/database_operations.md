# Day 13: Database Operations

## Title: Database Operations

### Topics Covered
- SQL Basics
- SQLite
- SQLAlchemy
- CRUD Operations

## Detailed Explanations

### Definition
- **Databases**: Store and manage data.
- **SQL (Structured Query Language)**: Used to interact with relational databases.
- **SQLite**: A lightweight database engine.
- **SQLAlchemy**: An ORM (Object Relational Mapper) for Python.

### Why it is Required
Databases are essential for storing, retrieving, and managing data in applications. SQLAlchemy provides an abstraction layer over SQL, simplifying database interactions.

### How to Implement
- Use `sqlite3` module for SQLite operations.
- Use SQLAlchemy to define models and perform CRUD operations.

### Where to Use
Database operations are used in web applications, data-driven applications, and any system requiring data persistence.

## Diagrams

### Database CRUD Operations Diagram
![Database CRUD Operations Diagram](images/database_crud_operations.png)

### SQLAlchemy ORM Diagram
![SQLAlchemy ORM Diagram](images/sqlalchemy_orm.png)

## Syntax
```python
# SQLite operations
import sqlite3

conn = sqlite3.connect('example.db')
cursor = conn.cursor()

# Create table
cursor.execute('''CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''')

# Insert data
cursor.execute('''INSERT INTO users (name, age) VALUES ('Alice', 30)''')
conn.commit()

# Query data
cursor.execute('''SELECT * FROM users''')
rows = cursor.fetchall()

# SQLAlchemy operations
from sqlalchemy import create_engine, Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

engine = create_engine('sqlite:///example.db')
Base = declarative_base()

class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    name = Column(String)
    age = Column(Integer)

Base.metadata.create_all(engine)

Session = sessionmaker(bind=engine)
session = Session()

# Insert data
new_user = User(name='Alice', age=30)
session.add(new_user)
session.commit()

# Query data
users = session.query(User).all()
```

## Example Code
```python
# SQLite example
import sqlite3

conn = sqlite3.connect('example.db')
cursor = conn.cursor()

# Create table
cursor.execute('''CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''')

# Insert data
cursor.execute('''INSERT INTO users (name, age) VALUES ('Alice', 30)''')
conn.commit()

# Query data
cursor.execute('''SELECT * FROM users''')
rows = cursor.fetchall()
for row in rows:
    print(row)  # Output: (1, 'Alice', 30)

conn.close()

# SQLAlchemy example
from sqlalchemy import create_engine, Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

engine = create_engine('sqlite:///example.db')
Base = declarative_base()

class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    name = Column(String)
    age = Column(Integer)

Base.metadata.create_all(engine)

Session = sessionmaker(bind=engine)
session = Session()

# Insert data
new_user = User(name='Alice', age=30)
session.add(new_user)
session.commit()

# Query data
users = session.query(User).all()
for user in users:
    print(user.name, user.age)  # Output: Alice 30
```

## Explanation Code Step by Step
1. SQLite Operations:

	- sqlite3.connect('example.db') connects to the SQLite database.
	- cursor.execute('''CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''') creates a table.
2. Insert Data:

	- cursor.execute('''INSERT INTO users (name, age) VALUES ('Alice', 30)''') inserts data into the table.
	- conn.commit() commits the transaction.
3. Query Data:

	- cursor.execute('''SELECT * FROM users''') queries the table.
	- rows = cursor.fetchall() fetches all rows.
4. SQLAlchemy Operations:

	- create_engine('sqlite:///example.db') creates a database engine.
	- declarative_base() defines the base class for models.
5. Define Model:

	- class User(Base): defines a User model with columns id, name, and age.
6. Create Session:

	- Session = sessionmaker(bind=engine) creates a session factory.
	- session = Session() creates a session.
7. Insert Data:

	- new_user = User(name='Alice', age=30) creates a new User object.
	- session.add(new_user) adds it to the session.
8. Query Data:

	- users = session.query(User).all() queries all users.

## Key Points to Remember
1. SQL is used for interacting with relational databases.
2. SQLite is a lightweight, file-based database.
3. SQLAlchemy is an ORM that abstracts SQL queries and provides a high-level API for database operations.
4. Use sqlite3 for direct SQLite operations and SQLAlchemy for a higher-level ORM approach.

## Quick Summary
Database operations involve using SQL to interact with databases. SQLite is a simple, lightweight database engine, while SQLAlchemy provides an ORM for more abstract and high-level database interactions. Both are essential for data-driven applications.

## Quiz
1. What is SQL?
2. How do you create a table using SQLite in Python?
3. What is SQLAlchemy?

## Labs
1. Lab 13.1: Create a SQLite Database
	Objective: Create a SQLite database with a table for storing books (title, author, year).
	
	Instructions:
	
	Import the sqlite3 library.
	Connect to a SQLite database.
	Create a table for books with columns title, author, and year.
	Insert a book into the table.
	Query and print all books.
	
	```python
	import sqlite3
	
	conn = sqlite3.connect('books.db')
	cursor = conn.cursor()
	
	cursor.execute('''CREATE TABLE books (title TEXT, author TEXT, year INTEGER)''')
	cursor.execute('''INSERT INTO books (title, author, year) VALUES ('1984', 'George Orwell', 1949)''')
	conn.commit()
	
	cursor.execute('''SELECT * FROM books''')
	rows = cursor.fetchall()
	for row in rows:
	    print(row)  # Output: ('1984', 'George Orwell', 1949)
	
	conn.close()
	```
2. Lab 13.2: Use SQLAlchemy for CRUD Operations
	Objective: Use SQLAlchemy to create a table for storing employee information (name, department, salary) and perform CRUD operations.
	
	Instructions:
	
	Import the necessary SQLAlchemy libraries.
	Create a SQLAlchemy engine and base class.
	Define an Employee model with columns name, department, and salary.
	Create a session and add an employee.
	Query and print all employees.
	```python
	from sqlalchemy import create_engine, Column, Integer, String
	from sqlalchemy.ext.declarative import declarative_base
	from sqlalchemy.orm import sessionmaker
	
	engine = create_engine('sqlite:///employees.db')
	Base = declarative_base()
	
	class Employee(Base):
	    __tablename__ = 'employees'
	    id = Column(Integer, primary_key=True)
	    name = Column(String)
	    department = Column(String)
	    salary = Column(Integer)
	
	Base.metadata.create_all(engine)
	
	Session = sessionmaker(bind=engine)
	session = Session()
	
	new_employee = Employee(name='John Doe', department='IT', salary=60000)
	session.add(new_employee)
	session.commit()
	
	employees = session.query(Employee).all()
	for employee in employees:
	    print(employee.name, employee.department, employee.salary)  # Output: John Doe IT 60000
	```
