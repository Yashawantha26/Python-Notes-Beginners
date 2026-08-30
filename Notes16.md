Here is your complete **`Notes16.md`**, continuing the Python Beginners Notes series.

# Python Beginners Notes – Notes 16

## 📘 Topic: Modules, Packages & pip in Python

As Python programs become larger, putting everything in one file becomes difficult.

Python provides:

* **Modules** → Organize code into files
* **Packages** → Organize modules into folders
* **Libraries** → Collections of reusable code
* **pip** → Install external Python packages

These concepts are very important for real-world Python development.

---

# 1. What is a Module?

A **module** is simply a Python file containing code.

A Python file has the extension:

```text
.py
```

Example:

```text
math_operations.py
```

It can contain:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

This file is a module.

---

# 2. Why Use Modules?

Modules help you:

* Organize code
* Reuse code
* Avoid repeating code
* Make programs easier to maintain
* Separate different functionalities
* Work with large projects

Instead of writing everything in:

```text
main.py
```

you can create:

```text
main.py
math_operations.py
student.py
calculator.py
```

---

# 3. Creating Your Own Module

Create a file:

```text
calculator.py
```

Add:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b


def divide(a, b):
    return a / b
```

Now create:

```text
main.py
```

---

# 4. Importing a Module

In `main.py`:

```python
import calculator

print(calculator.add(10, 20))
print(calculator.subtract(20, 5))
```

Output:

```text
30
15
```

The syntax is:

```python
module_name.function_name()
```

---

# 5. Import Specific Functions

Instead of importing the entire module:

```python
from calculator import add
```

Now:

```python
print(add(10, 20))
```

Output:

```text
30
```

---

# 6. Import Multiple Functions

```python
from calculator import add, subtract
```

Then:

```python
print(add(10, 20))
print(subtract(20, 5))
```

---

# 7. Import Everything

You can write:

```python
from calculator import *
```

Then:

```python
print(add(10, 20))
print(subtract(20, 5))
```

However, this style is generally **not recommended** in larger programs because it can make it unclear where names came from.

Prefer:

```python
from calculator import add
```

or:

```python
import calculator
```

---

# 8. Using an Alias

You can give a module a shorter name.

```python
import calculator as calc
```

Now:

```python
print(calc.add(10, 20))
```

---

# 9. Alias for a Function

```python
from calculator import add as addition
```

Now:

```python
print(addition(10, 20))
```

---

# 10. Built-in Modules

Python includes many modules in its standard library.

Examples:

```text
math
random
datetime
os
sys
json
re
statistics
collections
```

You do not normally need to install these separately.

---

# 11. The `math` Module

The `math` module provides mathematical functions.

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

---

# 12. `math.pi`

```python
import math

print(math.pi)
```

Output:

```text
3.141592653589793
```

---

# 13. `math.ceil()`

Rounds a number upward.

```python
import math

print(math.ceil(4.2))
```

Output:

```text
5
```

---

# 14. `math.floor()`

Rounds downward.

```python
import math

print(math.floor(4.9))
```

Output:

```text
4
```

---

# 15. `math.pow()`

```python
import math

print(math.pow(2, 3))
```

Output:

```text
8.0
```

---

# 16. `math.factorial()`

```python
import math

print(math.factorial(5))
```

Output:

```text
120
```

---

# 17. The `random` Module

The `random` module generates pseudo-random values.

```python
import random

number = random.randint(1, 10)

print(number)
```

Example output:

```text
7
```

The result can be different each time.

---

# 18. `random.randint()`

Generates an integer between the specified boundaries.

```python
import random

print(random.randint(1, 100))
```

---

# 19. `random.choice()`

Selects a random item.

```python
import random

names = ["Yashu", "Rahul", "Arun"]

print(random.choice(names))
```

---

# 20. `random.shuffle()`

Shuffles a list.

```python
import random

numbers = [1, 2, 3, 4, 5]

random.shuffle(numbers)

print(numbers)
```

Possible output:

```text
[3, 1, 5, 2, 4]
```

---

# 21. The `datetime` Module

Used for dates and times.

```python
from datetime import datetime

now = datetime.now()

print(now)
```

---

# 22. Current Date

```python
from datetime import date

today = date.today()

print(today)
```

---

# 23. Current Year

```python
from datetime import date

today = date.today()

print(today.year)
```

---

# 24. Current Month

```python
from datetime import date

today = date.today()

print(today.month)
```

---

# 25. Current Day

```python
from datetime import date

today = date.today()

print(today.day)
```

---

# 26. The `os` Module

The `os` module provides operating-system-related functionality.

```python
import os

print(os.getcwd())
```

`getcwd()` returns the current working directory.

---

# 27. List Files

```python
import os

files = os.listdir()

print(files)
```

---

# 28. Create a Directory

```python
import os

os.mkdir("test_folder")
```

This creates:

```text
test_folder
```

---

# 29. Check Whether a File Exists

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

---

# 30. The `sys` Module

The `sys` module provides access to Python interpreter-related functionality.

Example:

```python
import sys

print(sys.version)
```

This displays the Python version.

---

# 31. Command-Line Arguments

The `sys.argv` list contains command-line arguments.

Example:

```python
import sys

print(sys.argv)
```

If you run:

```text
python main.py Yashu
```

you may get something like:

```text
['main.py', 'Yashu']
```

---

# 32. The `json` Module

JSON is commonly used for storing and exchanging structured data.

Example:

```python
import json

student = {
    "name": "Yashu",
    "age": 20
}

json_data = json.dumps(student)

print(json_data)
```

Output:

```text
{"name": "Yashu", "age": 20}
```

---

# 33. `json.dumps()`

Converts a Python object into a JSON string.

```python
import json

data = {
    "name": "Yashu",
    "skills": ["Python", "Java"]
}

result = json.dumps(data)

print(result)
```

---

# 34. `json.loads()`

Converts a JSON string into a Python object.

```python
import json

data = '{"name": "Yashu", "age": 20}'

result = json.loads(data)

print(result)
print(result["name"])
```

Output:

```text
{'name': 'Yashu', 'age': 20}
Yashu
```

---

# 35. What is a Package?

A **package** is a directory that organizes related Python modules.

Example:

```text
project/
│
├── main.py
│
└── calculator/
    ├── __init__.py
    ├── basic.py
    └── advanced.py
```

The `calculator` directory is a package.

---

# 36. Package Structure

Example:

```text
myproject/
│
├── main.py
│
└── utilities/
    ├── __init__.py
    ├── math_utils.py
    └── string_utils.py
```

---

# 37. `__init__.py`

Traditionally, a package contains:

```text
__init__.py
```

It tells Python that the directory is intended to be a package.

Modern Python can also use namespace packages without `__init__.py`, but beginners will commonly encounter `__init__.py` in regular packages.

---

# 38. Importing from a Package

Suppose:

```text
utilities/
    __init__.py
    math_utils.py
```

`math_utils.py`:

```python
def add(a, b):
    return a + b
```

In `main.py`:

```python
from utilities.math_utils import add

print(add(10, 20))
```

Output:

```text
30
```

---

# 39. Import a Package Module

You can also write:

```python
import utilities.math_utils

print(utilities.math_utils.add(10, 20))
```

---

# 40. Package with Multiple Modules

Structure:

```text
project/
│
├── main.py
│
└── student/
    ├── __init__.py
    ├── details.py
    └── marks.py
```

`details.py`:

```python
def get_name():
    return "Yashu"
```

`marks.py`:

```python
def get_marks():
    return 85
```

`main.py`:

```python
from student.details import get_name
from student.marks import get_marks

print(get_name())
print(get_marks())
```

Output:

```text
Yashu
85
```

---

# 41. What is a Library?

A library is reusable code that provides functionality you can use in your programs.

Examples:

```text
NumPy
Pandas
Matplotlib
Requests
Flask
Django
```

Many popular libraries are installed separately using package-management tools such as `pip`.

---

# 42. Standard Library vs External Packages

### Python Standard Library

Comes with Python.

Examples:

```text
math
random
os
sys
json
datetime
re
```

### External Packages

Usually installed separately.

Examples:

```text
numpy
pandas
requests
flask
```

---

# 43. What is `pip`?

`pip` is Python's package installer.

It is commonly used to install packages from the Python Package Index (PyPI).

Basic command:

```bash
python -m pip install package_name
```

Example:

```bash
python -m pip install requests
```

---

# 44. Installing NumPy

```bash
python -m pip install numpy
```

Then:

```python
import numpy as np

numbers = np.array([1, 2, 3])

print(numbers)
```

---

# 45. Installing Pandas

```bash
python -m pip install pandas
```

Then:

```python
import pandas as pd

data = {
    "Name": ["Yashu", "Rahul"],
    "Marks": [85, 90]
}

df = pd.DataFrame(data)

print(df)
```

---

# 46. Installing Matplotlib

```bash
python -m pip install matplotlib
```

Then:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3]
y = [10, 20, 30]

plt.plot(x, y)
plt.show()
```

---

# 47. Installing Requests

```bash
python -m pip install requests
```

Then:

```python
import requests

response = requests.get("https://example.com")

print(response.status_code)
```

For production applications, handle network failures and timeouts appropriately.

---

# 48. Checking Installed Packages

Use:

```bash
python -m pip list
```

This displays installed packages.

---

# 49. Show Package Information

```bash
python -m pip show requests
```

This displays information such as:

* Package name
* Version
* Location
* Dependencies

---

# 50. Upgrade a Package

```bash
python -m pip install --upgrade requests
```

---

# 51. Uninstall a Package

```bash
python -m pip uninstall requests
```

You will normally be asked to confirm.

---

# 52. Check pip Version

```bash
python -m pip --version
```

Using:

```bash
python -m pip
```

is often preferable because it makes clear which Python interpreter is running pip.

---

# 53. `requirements.txt`

A `requirements.txt` file records project dependencies.

Example:

```text
requests
numpy
pandas
```

You can install them with:

```bash
python -m pip install -r requirements.txt
```

---

# 54. Version Pinning

You can specify versions:

```text
requests==2.32.4
numpy==2.3.2
```

This helps reproduce an environment.

For a real project, dependency versions should be chosen based on the project's supported Python version and compatibility requirements.

---

# 55. Create `requirements.txt`

One common command is:

```bash
python -m pip freeze > requirements.txt
```

This writes installed package versions into the file.

Example:

```text
requests==2.32.4
numpy==2.3.2
```

Be careful: `pip freeze` records the packages installed in the current environment, which may include packages unrelated to your project.

---

# 56. Virtual Environment

A **virtual environment** creates an isolated Python environment for a project.

This is very important in real-world Python development.

Why?

Different projects may require different package versions.

Example:

```text
Project A → requests version X
Project B → requests version Y
```

A virtual environment keeps their dependencies separate.

---

# 57. Create a Virtual Environment

Windows:

```bash
python -m venv .venv
```

macOS/Linux:

```bash
python3 -m venv .venv
```

This creates:

```text
.venv/
```

---

# 58. Activate Virtual Environment – Windows PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

After activation, you may see:

```text
(.venv)
```

in your terminal prompt.

---

# 59. Activate Virtual Environment – Windows CMD

```cmd
.venv\Scripts\activate.bat
```

---

# 60. Activate Virtual Environment – macOS/Linux

```bash
source .venv/bin/activate
```

---

# 61. Deactivate Virtual Environment

```bash
deactivate
```

---

# 62. Install Packages Inside a Virtual Environment

After activation:

```bash
python -m pip install requests
```

The package is installed into that environment.

---

# 63. Recommended Project Structure

A simple Python project can look like:

```text
my_project/
│
├── .venv/
│
├── src/
│   ├── __init__.py
│   ├── calculator.py
│   └── utils.py
│
├── tests/
│   └── test_calculator.py
│
├── main.py
├── requirements.txt
└── README.md
```

---

# 64. `__name__ == "__main__"`

A very important Python concept:

```python
if __name__ == "__main__":
```

It checks whether the current file is being run directly.

Example:

```python
def hello():
    print("Hello Python")


if __name__ == "__main__":
    hello()
```

If you run the file directly:

```text
Hello Python
```

---

# 65. Why Use `__name__ == "__main__"`?

Suppose:

```text
calculator.py
main.py
```

`calculator.py`:

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))
```

When imported:

```python
import calculator
```

the test code under:

```python
if __name__ == "__main__":
```

does not run automatically.

This keeps modules reusable.

---

# 66. Module Example with Main Guard

`calculator.py`:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


if __name__ == "__main__":
    print(add(10, 20))
    print(subtract(20, 5))
```

`main.py`:

```python
import calculator

print(calculator.add(100, 50))
```

Output:

```text
150
```

---

# 67. Relative Imports

Inside a package, you may see relative imports.

Example:

```python
from .math_utils import add
```

The dot means:

```text
Current package
```

Relative imports are useful when organizing larger packages.

---

# 68. Absolute Imports

Example:

```python
from utilities.math_utils import add
```

This uses the package path explicitly.

---

# 69. Import Errors

If Python cannot find a module:

```python
import something
```

you may get:

```text
ModuleNotFoundError
```

Example:

```text
ModuleNotFoundError: No module named 'something'
```

---

# 70. Fixing `ModuleNotFoundError`

Check:

1. Is the package installed?
2. Is the module name correct?
3. Are you using the correct Python environment?
4. Is your virtual environment activated?
5. Is the file in the correct location?

For an external package:

```bash
python -m pip install package_name
```

---

# 71. `pip` vs `python -m pip`

You may see:

```bash
pip install requests
```

or:

```bash
python -m pip install requests
```

The second form is often safer because it explicitly uses the pip associated with the selected Python interpreter.

Recommended:

```bash
python -m pip install requests
```

---

# 72. Package Naming

Avoid naming your own files after popular standard-library modules.

For example, avoid:

```text
random.py
math.py
json.py
re.py
```

If you create:

```text
random.py
```

and then write:

```python
import random
```

Python may import your local file instead of the standard-library module, causing confusing errors.

---

# 73. Import Order

A common style is:

```python
# Standard library
import os
import re
import json

# Third-party
import requests
import pandas as pd

# Local modules
from utilities.math_utils import add
```

This makes imports easier to read.

---

# 74. Module Example – Student

Create:

```text
student.py
```

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Marks:", self.marks)
```

Then:

```text
main.py
```

```python
from student import Student

student = Student("Yashu", 85)

student.display()
```

Output:

```text
Name: Yashu
Marks: 85
```

---

# 75. Mini Project – Calculator Package

Structure:

```text
calculator_project/
│
├── main.py
│
└── calculator/
    ├── __init__.py
    ├── basic.py
    └── advanced.py
```

`basic.py`:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b


def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")

    return a / b
```

`advanced.py`:

```python
def square(number):
    return number ** 2


def cube(number):
    return number ** 3
```

`main.py`:

```python
from calculator.basic import add, divide
from calculator.advanced import square

print("Addition:", add(10, 20))
print("Division:", divide(20, 5))
print("Square:", square(5))
```

Output:

```text
Addition: 30
Division: 4.0
Square: 25
```

---

# 76. Mini Project – Student Package

Structure:

```text
student_project/
│
├── main.py
│
└── student/
    ├── __init__.py
    ├── details.py
    └── result.py
```

`details.py`:

```python
def get_student_name():
    return "Yashu"
```

`result.py`:

```python
def get_result(marks):

    if marks >= 40:
        return "Pass"

    return "Fail"
```

`main.py`:

```python
from student.details import get_student_name
from student.result import get_result

name = get_student_name()
result = get_result(85)

print("Name:", name)
print("Result:", result)
```

Output:

```text
Name: Yashu
Result: Pass
```

---

# 77. Mini Project – Random Password Generator

```python
import random
import string

characters = (
    string.ascii_letters
    + string.digits
    + string.punctuation
)

password = ""

for _ in range(12):
    password += random.choice(characters)

print("Password:", password)
```

This is useful for learning modules, although security-sensitive password generation should use the `secrets` module rather than `random`.

---

# 78. `secrets` Module

For security-sensitive random values, use:

```python
import secrets
```

Example:

```python
import secrets
import string

characters = string.ascii_letters + string.digits

password = "".join(
    secrets.choice(characters)
    for _ in range(12)
)

print(password)
```

---

# 79. Mini Project – Date Calculator

```python
from datetime import date, timedelta

today = date.today()

future_date = today + timedelta(days=30)

print("Today:", today)
print("After 30 days:", future_date)
```

---

# 80. Mini Project – JSON File

```python
import json

student = {
    "name": "Yashu",
    "age": 20,
    "skills": [
        "Python",
        "Java",
        "AI"
    ]
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file, indent=4)

print("Data saved")
```

---

# 81. Reading JSON File

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    student = json.load(file)

print(student)
print(student["name"])
```

---

# 82. Useful `pip` Commands

```bash
python -m pip install package
```

Install package.

```bash
python -m pip uninstall package
```

Uninstall package.

```bash
python -m pip list
```

List installed packages.

```bash
python -m pip show package
```

Show package information.

```bash
python -m pip install --upgrade package
```

Upgrade package.

```bash
python -m pip freeze
```

Show installed packages and versions.

```bash
python -m pip freeze > requirements.txt
```

Save dependencies.

```bash
python -m pip install -r requirements.txt
```

Install dependencies from a file.

---

# 83. Important Commands for Beginners

Create environment:

```bash
python -m venv .venv
```

Activate on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Install package:

```bash
python -m pip install package_name
```

Run Python file:

```bash
python main.py
```

Deactivate:

```bash
deactivate
```

---

# 84. Standard Library Cheat Sheet

| Module        | Purpose                   |
| ------------- | ------------------------- |
| `math`        | Mathematics               |
| `random`      | Random values             |
| `datetime`    | Date and time             |
| `os`          | Operating system          |
| `sys`         | Python/system information |
| `json`        | JSON data                 |
| `re`          | Regular expressions       |
| `statistics`  | Statistics                |
| `collections` | Specialized containers    |
| `pathlib`     | File-system paths         |
| `secrets`     | Secure random values      |

---

# 85. Import Cheat Sheet

### Import module

```python
import math
```

### Import function

```python
from math import sqrt
```

### Multiple functions

```python
from math import sqrt, factorial
```

### Alias

```python
import pandas as pd
```

### Function alias

```python
from math import sqrt as square_root
```

---

# 86. Module vs Package vs Library

| Concept | Meaning                             |
| ------- | ----------------------------------- |
| Module  | A Python file                       |
| Package | Collection of related modules       |
| Library | Reusable functionality/code         |
| `pip`   | Tool for installing Python packages |

Simple idea:

```text
Module
   ↓
Package
   ↓
Library / ecosystem
   ↓
Application
```

---

# 87. Best Practices

### 1. Keep modules focused

A module should generally have a clear purpose.

### 2. Use meaningful names

Good:

```text
math_utils.py
student.py
database.py
```

Avoid:

```text
abc.py
test123.py
file2.py
```

### 3. Use virtual environments

For projects with external dependencies:

```bash
python -m venv .venv
```

### 4. Avoid `import *`

Prefer explicit imports.

### 5. Use `requirements.txt`

Record project dependencies.

### 6. Keep secrets out of source code

Do not hard-code:

```text
API keys
passwords
tokens
```

### 7. Use `__name__ == "__main__"`

This keeps modules reusable.

---

# 88. Practice Questions

## Beginner

### Question 1

Create a module named:

```text
calculator.py
```

with:

```text
add()
subtract()
multiply()
divide()
```

Import it into `main.py`.

---

### Question 2

Create a module:

```text
student.py
```

with a function:

```text
display_student()
```

Import and use it from another file.

---

### Question 3

Use the `math` module to calculate:

* Square root
* Factorial
* Power
* Ceiling
* Floor

---

### Question 4

Use the `random` module to:

* Generate a random number
* Select a random name
* Shuffle a list

---

### Question 5

Use the `datetime` module to display:

* Current date
* Current year
* Current month
* Current day

---

# 89. Intermediate Practice

### Question 6

Create a package:

```text
calculator/
    __init__.py
    basic.py
    advanced.py
```

Add calculator functions.

---

### Question 7

Create a package:

```text
student/
    __init__.py
    details.py
    result.py
```

Use it from `main.py`.

---

### Question 8

Create a JSON file containing:

```text
Name
Age
Branch
Skills
```

Read it using Python.

---

### Question 9

Create a `requirements.txt` file and add three external packages.

---

### Question 10

Create a virtual environment and install a package inside it.

---

# 90. Advanced Practice

### Question 11

Create a modular banking application:

```text
banking/
├── account.py
├── transactions.py
└── validation.py
```

---

### Question 12

Create a student management package:

```text
student/
├── details.py
├── marks.py
├── attendance.py
└── result.py
```

---

### Question 13

Create a utility package containing:

```text
math_utils.py
string_utils.py
date_utils.py
```

---

### Question 14

Build a command-line application using:

```python
sys.argv
```

---

### Question 15

Build a Python project with:

```text
.venv
src
tests
requirements.txt
README.md
```

and separate your application logic into modules.

---

# 91. Important Interview Questions

### Q1. What is a module?

A module is a Python file containing reusable code such as functions, classes, and variables.

### Q2. What is a package?

A package organizes related Python modules into a directory structure.

### Q3. What is pip?

`pip` is Python's package installer used to install and manage Python packages.

### Q4. What is a virtual environment?

A virtual environment is an isolated Python environment used to manage project-specific dependencies.

### Q5. Difference between module and package?

```text
Module  → Python file
Package → Directory containing related modules
```

### Q6. What is `__init__.py`?

It is commonly used as the initialization module for a regular Python package.

### Q7. What is `__name__ == "__main__"`?

It allows code to run only when the file is executed directly rather than imported.

### Q8. Why use virtual environments?

To keep dependencies isolated between projects.

### Q9. Difference between standard library and external package?

```text
Standard library → Included with Python
External package → Usually installed separately
```

---

# 92. Quick Revision

```text
Module
   ↓
Python file containing reusable code

Package
   ↓
Directory organizing related modules

Library
   ↓
Reusable collection of functionality

pip
   ↓
Python package installer

venv
   ↓
Isolated project environment

requirements.txt
   ↓
Project dependency list
```

---

# 🎯 Notes 16 Summary

In this lesson, you learned:

* Modules
* Creating modules
* Importing modules
* `from ... import ...`
* Aliases
* Built-in modules
* `math`
* `random`
* `datetime`
* `os`
* `sys`
* `json`
* Packages
* `__init__.py`
* Package imports
* Libraries
* External packages
* `pip`
* Installing packages
* Updating packages
* Uninstalling packages
* `requirements.txt`
* Version pinning
* Virtual environments
* Activating environments
* Deactivating environments
* `__name__ == "__main__"`
* Relative imports
* Absolute imports
* `ModuleNotFoundError`
* Import best practices
* Project structure
* Mini projects
* Practice questions
* Interview questions

---

# ⭐ Most Important Concepts

Remember:

```python
import math
```

```python
from math import sqrt
```

```python
import pandas as pd
```

```bash
python -m pip install requests
```

```bash
python -m venv .venv
```

```bash
python -m pip install -r requirements.txt
```

And:

```python
if __name__ == "__main__":
    main()
```

These concepts are essential for moving from **beginner Python programs to real-world Python projects**.

---

# 🚀 Next Lesson

**Notes 17 → Object-Oriented Programming (OOP) in Python**
