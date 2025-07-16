
# 🔹 Functions in Python

## 1. Definition and Syntax of Functions

A function is a block of reusable code that performs a specific task.

**Syntax:**
```python
def function_name(parameters):
    # code block
    return result
```

**Example:**
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Nilesh"))  # Output: Hello, Nilesh!
```

---

## 2. Types of Functions

- **Built-in Functions**: Provided by Python (e.g., `len()`, `sum()`, `type()`)
- **User-defined Functions**: Functions created by the user

---

## 3. Function Arguments

### a. Positional Arguments
Passed in order:
```python
def add(a, b):
    return a + b

print(add(3, 5))  # Output: 8
```

### b. Keyword Arguments
Passed using parameter names:
```python
print(add(b=5, a=3))  # Output: 8
```

### c. Default Arguments
```python
def greet(name="User"):
    return f"Hello, {name}!"

print(greet())          # Output: Hello, User!
print(greet("Nilesh"))  # Output: Hello, Nilesh!
```

### d. Variable-length Arguments

- **`*args`** (Non-keyworded):
```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4))  # Output: 10
```

- **`**kwargs`** (Keyworded):
```python
def user_info(**kwargs):
    return kwargs

print(user_info(name="Nilesh", age=25))
# Output: {'name': 'Nilesh', 'age': 25}
```

---

## 4. Return Statement
```python
def multiply(a, b):
    return a * b

result = multiply(4, 5)
print(result)  # Output: 20
```

---

## 5. Scope and Lifetime of Variables

### a. Local vs Global Variables
```python
x = 10  # Global

def example():
    x = 5  # Local
    print("Inside:", x)

example()            # Output: Inside: 5
print("Outside:", x) # Output: Outside: 10
```

### b. `global` Keyword
```python
x = 10

def modify():
    global x
    x = 20

modify()
print(x)  # Output: 20
```

---

## 6. Lambda (Anonymous) Functions
```python
square = lambda x: x * x
print(square(5))  # Output: 25
```

---

## 7. Recursive Functions
```python
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

---

## 8. Docstrings and Function Documentation
```python
def greet(name):
    """This function greets the user by name."""
    return f"Hello, {name}!"

print(greet.__doc__)
# Output: This function greets the user by name.
```

---

## 9. Function Best Practices

- Keep functions short and focused (single responsibility).
- Use meaningful names.
- Write docstrings for clarity.
- Avoid global variables when possible.

---

# 🔹 Modules in Python

## 1. What is a Module?

A module is a file containing Python definitions and statements. They help organize code, promote reusability, and separate concerns.

---

## 2. Creating and Using Modules

**`mymodule.py`**
```python
def say_hello(name):
    return f"Hello, {name}!"
```

**`main.py`**
```python
import mymodule

print(mymodule.say_hello("Nilesh"))
# Output: Hello, Nilesh!
```

---

## 3. Importing Modules

### a. Basic Import
```python
import math
print(math.sqrt(16))  # Output: 4.0
```

### b. From Import
```python
from math import sqrt
print(sqrt(25))  # Output: 5.0
```

### c. Aliasing
```python
import math as m
print(m.pi)  # Output: 3.141592653589793
```

---

## 4. Standard Library Modules
```python
import datetime
print(datetime.datetime.now())
# Output: 2025-07-15 21:24:25.123456 (or current time)
```

---

## 5. Third-party Modules and pip Installation

**Install:**
```bash
pip install requests
```

**Usage:**
```python
import requests

response = requests.get("https://api.github.com")
print(response.status_code)  # Output: 200 (if successful)
```

---

## 6. `if __name__ == '__main__'`

Used to ensure code runs only when the script is executed directly.

```python
def main():
    print("Executed directly")

if __name__ == "__main__":
    main()
```

---

## 7. Module Search Path
```python
import sys
print(sys.path)
# Output: List of directories where Python looks for modules
```

---

## 8. Packages and Sub-packages

A package organizes related modules using a directory and an `__init__.py` file.

**Structure:**
```
myapp/
├── __init__.py
├── module1.py
└── subpackage/
    ├── __init__.py
    └── module2.py
```

**Usage:**
```python
from myapp.subpackage import module2
```

---

## 9. Relative vs Absolute Imports

- **Absolute Import**:
```python
from myapp.module1 import func
```

- **Relative Import**:
```python
from .module1 import func          # From same package
from ..another_package import mod  # From parent package
```

---

## 10. Organizing Code with Modules and Packages

- Use **modules** to group related logic.
- Use **packages** for project-level organization.
- Improves maintainability, reusability, and scalability.

---
