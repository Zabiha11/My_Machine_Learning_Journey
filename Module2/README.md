# 🐍 Module 2: Python Basics for Machine Learning 

---

## 2.1 Google Colaboratory for Python

**Google Colab:** A free cloud service to write and execute Python code in a Jupyter Notebook environment.

- Offers free access to GPU/TPU.
- Ideal for data science, ML, and deep learning workflows.
- Saves work to Google Drive.

2.2 Python Basics
Basic Syntax:

Case-sensitive.

Indentation is mandatory.

Comments use #.

Example:

# This is a comment
x = 5
print(x)


## 2.3 Python Basic Data Types
# Data Types:

- int: Integer numbers → x = 10

- float: Decimal numbers → y = 10.5

- str: Text → name = "Zabi"

- complex: Complex numbers → z = 3 + 4j

- bool: Boolean values → flag = True

Check Type:

print(type(10.5))  # Output: <class 'float'>


## 2.4 Python Special Data Types
- List: Ordered, mutable → [1, 2, 3]
- Tuple: Ordered, immutable → (1, 2, 3)
- Set: Unordered, unique values → {1, 2, 3}
- Dict: Key-value pairs → {'name': 'Zabi', 'age': 21}

Example:

info = {'name': 'Zabi', 'skills': ['Python', 'ML']}
print(info['skills'])  # Output: ['Python', 'ML']


## 2.5 Operators in Python
- Arithmetic: +, -, *, /, **, %
- Relational: >, <, ==, !=, >=, <=
- Logical: and, or, not
- Assignment: =, +=, -=, etc.
- Membership: in, not in
- Identity: is, is not

x = 10
print(x > 5 and x < 20)  # Output: True

## 2.6 if else Statement in Python

age = 18
if age >= 18:
    print("Adult")
else:
    print("Minor")


## 2.7 Loops in Python – For Loop & While Loop
**For Loop:** Iterates over sequences (list, tuple, dict, etc.)

for i in range(5):
    print(i)

**While Loop:** Repeats while condition is true

count = 0
while count < 5:
    print(count)
    count += 1

## 2.8 Functions in Python
**Definition:** Reusable block of code defined with def keyword.

Syntax:

def greet(name):
    return f"Hello, {name}!"

print(greet("Zabi"))


---

