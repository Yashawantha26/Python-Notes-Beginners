# Python Beginners Notes – Notes 19

# 📦 Python Modules, Packages & Imports

In this lesson, we will learn:

* What is a module?
* Why modules are useful
* Creating a module
* `import`
* `from ... import`
* Importing multiple items
* `as` alias
* `dir()`
* `help()`
* `__name__`
* `__main__`
* Standard Library
* Common built-in modules
* Packages
* Creating packages
* `__init__.py`
* Installing packages with `pip`
* Virtual environments
* `requirements.txt`
* Module search path
* Common import errors
* Best practices
* Practical examples
* Interview questions
* Practice problems

---

# 1. What is a Module?

A **module** is a Python file containing code such as:

* Variables
* Functions
* Classes
* Statements

A Python module normally has the extension:

```text
.py
```

Example:

```text
calculator.py
```

A module helps organize code into separate files.

---

# 2. Why Use Modules?

Suppose you have a large program containing:

```text
1000+ lines of code
```

Keeping everything in one file can become difficult.

Instead, you can divide the program:

```text
main.py
calculator.py
student.py
database.py
utils.py
```

This makes the project:

* Easier to understand
* Easier to maintain
* Easier to test
* Easier to reuse

---

# 3. Creating Your First Module

Create a file called:

```text
calculator.py
```

Add:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

Now create another file:

```text
main.py
```

---

# 4. Importing a Module

Inside `main.py`:

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
```

Output:

```text
15
5
```

The syntax is:

```python
import module_name
```

---

# 5. Module Name

If the file is:

```text
calculator.py
```

the module name is:

```text
calculator
```

You normally do not write:

```python
import calculator.py
```

Instead:

```python
import calculator
```

---

# 6. Accessing Functions from a Module

Use:

```python
module_name.function_name()
```

Example:

```python
import calculator

result = calculator.add(20, 10)

print(result)
```

Output:

```text
30
```

---

# 7. Module Variables

A module can contain variables.

`student.py`:

```python
name = "Yashu"
age = 20
course = "CSE"
```

`main.py`:

```python
import student

print(student.name)
print(student.age)
print(student.course)
```

Output:

```text
Yashu
20
CSE
```

---

# 8. Module Classes

A module can also contain classes.

`student.py`:

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print(self.name, self.marks)
```

`main.py`:

```python
import student

s1 = student.Student("Yashu", 85)

s1.display()
```

Output:

```text
Yashu 85
```

---

# 9. `from ... import`

Instead of importing the complete module:

```python
import calculator

print(calculator.add(10, 20))
```

you can import a specific function:

```python
from calculator import add

print(add(10, 20))
```

Output:

```text
30
```

---

# 10. Import Multiple Functions

You can import multiple items:

```python
from calculator import add, subtract

print(add(10, 5))
print(subtract(10, 5))
```

Output:

```text
15
5
```

---

# 11. Import Everything

Python allows:

```python
from calculator import *
```

Then:

```python
print(add(10, 5))
print(subtract(10, 5))
```

However, this is generally **not recommended** in larger programs because it can make it unclear where names came from and can cause naming conflicts.

Prefer explicit imports.

---

# 12. Import Using `as`

You can give a module an alias.

Example:

```python
import calculator as calc

print(calc.add(10, 5))
```

Output:

```text
15
```

---

# 13. Aliasing Functions

You can also alias an imported function.

```python
from calculator import add as addition

print(addition(10, 20))
```

Output:

```text
30
```

---

# 14. Importing Standard Modules

Python provides many modules in its **Standard Library**.

Example:

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

---

# 15. `math` Module

The `math` module provides mathematical functions and constants.

Example:

```python
import math

print(math.sqrt(16))
print(math.pow(2, 3))
print(math.ceil(4.2))
print(math.floor(4.8))
```

Output:

```text
4.0
8.0
5
4
```

---

# 16. Useful `math` Functions

```python
import math

print(math.sqrt(25))
print(math.factorial(5))
print(math.gcd(12, 8))
```

Output:

```text
5.0
120
4
```

---

# 17. Math Constants

```python
import math

print(math.pi)
print(math.e)
```

Example output:

```text
3.141592653589793
2.718281828459045
```

---

# 18. `random` Module

The `random` module is used to generate pseudo-random values.

```python
import random

number = random.randint(1, 10)

print(number)
```

The output will be a number between:

```text
1 and 10
```

---

# 19. Random Float

```python
import random

print(random.random())
```

This produces a floating-point number from:

```text
0.0
```

up to but not including:

```text
1.0
```

---

# 20. Random Choice

```python
import random

names = ["Yashu", "Rahul", "Arun", "Kiran"]

print(random.choice(names))
```

One item is selected randomly.

---

# 21. Random Sample

```python
import random

numbers = [1, 2, 3, 4, 5]

print(random.sample(numbers, 2))
```

This selects two unique items from the population.

---

# 22. `datetime` Module

The `datetime` module works with dates and times.

```python
from datetime import datetime

now = datetime.now()

print(now)
```

---

# 23. Current Date and Time

```python
from datetime import datetime

now = datetime.now()

print("Date:", now.date())
print("Time:", now.time())
```

---

# 24. Creating a Date

```python
from datetime import date

birthday = date(2005, 10, 15)

print(birthday)
```

Output:

```text
2005-10-15
```

---

# 25. `timedelta`

`timedelta` represents a duration.

```python
from datetime import date, timedelta

today = date.today()

tomorrow = today + timedelta(days=1)

print(tomorrow)
```

---

# 26. `os` Module

The `os` module provides operating-system-related functionality.

Example:

```python
import os

print(os.getcwd())
```

This prints the current working directory.

---

# 27. List Files

```python
import os

files = os.listdir()

print(files)
```

This returns entries in the current directory.

---

# 28. Create a Directory

```python
import os

os.mkdir("test_folder")
```

This creates a directory named:

```text
test_folder
```

If it already exists, an error can occur.

---

# 29. Check if a File Exists

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

---

# 30. `sys` Module

The `sys` module provides access to Python interpreter-related functionality.

Example:

```python
import sys

print(sys.version)
```

This displays the Python version.

---

# 31. Command-Line Arguments

`sys.argv` contains command-line arguments.

Example:

```python
import sys

print(sys.argv)
```

If you run:

```text
python main.py hello
```

you may get something similar to:

```text
['main.py', 'hello']
```

---

# 32. `statistics` Module

Python also provides a statistics module.

```python
import statistics

numbers = [10, 20, 30, 40, 50]

print(statistics.mean(numbers))
```

Output:

```text
30
```

---

# 33. Median

```python
import statistics

numbers = [10, 20, 30, 40, 50]

print(statistics.median(numbers))
```

Output:

```text
30
```

---

# 34. Mode

```python
import statistics

numbers = [1, 2, 2, 3, 4]

print(statistics.mode(numbers))
```

Output:

```text
2
```

---

# 35. `collections`

The `collections` module provides specialized container types.

Example:

```python
from collections import Counter

numbers = [1, 2, 2, 3, 3, 3]

result = Counter(numbers)

print(result)
```

Output will show the frequency of each value.

---

# 36. `Counter`

```python
from collections import Counter

text = "banana"

count = Counter(text)

print(count)
```

It counts occurrences.

---

# 37. `defaultdict`

```python
from collections import defaultdict

students = defaultdict(list)

students["CSE"].append("Yashu")
students["CSE"].append("Rahul")

print(students)
```

---

# 38. `json` Module

The `json` module works with JSON data.

```python
import json

student = {
    "name": "Yashu",
    "age": 20,
    "course": "CSE"
}

data = json.dumps(student)

print(data)
```

Output:

```text
{"name": "Yashu", "age": 20, "course": "CSE"}
```

---

# 39. JSON String to Python Object

Use `json.loads()`:

```python
import json

data = '{"name": "Yashu", "age": 20}'

student = json.loads(data)

print(student["name"])
```

Output:

```text
Yashu
```

---

# 40. `pathlib`

`pathlib` provides an object-oriented way to work with filesystem paths.

```python
from pathlib import Path

path = Path("data.txt")

print(path.exists())
```

---

# 41. Creating a Path

```python
from pathlib import Path

folder = Path("data")

print(folder)
```

---

# 42. Module Documentation

You can add a module-level docstring.

```python
"""
Utility functions for student management.
"""

def calculate_grade(marks):
    ...
```

Documentation helps explain the purpose of a module.

---

# 43. `dir()`

The `dir()` function shows names available in an object or module.

Example:

```python
import math

print(dir(math))
```

It lists functions, constants, and other attributes.

---

# 44. `help()`

The `help()` function provides documentation.

Example:

```python
import math

help(math.sqrt)
```

You can also use:

```python
help(math)
```

---

# 45. The `__name__` Variable

Every Python module has a special variable:

```python
__name__
```

Its value depends on how the module is being used.

---

# 46. `__name__` in the Main File

Suppose:

```python
print(__name__)
```

inside the file being executed directly.

Output:

```text
__main__
```

---

# 47. `__name__ == "__main__"`

A common Python pattern is:

```python
if __name__ == "__main__":
    print("Program started")
```

This code runs when the file is executed directly.

---

# 48. Why Use `__main__`?

Suppose `calculator.py` contains:

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))
```

If you run:

```text
python calculator.py
```

the output is:

```text
30
```

But if another file imports:

```python
import calculator
```

the test code inside the `if` block does not execute merely because the module was imported.

---

# 49. Module Example with `__main__`

`calculator.py`:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


if __name__ == "__main__":
    print(add(10, 5))
    print(subtract(10, 5))
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

# 50. Package

A **package** is a way to organize related Python modules into directories.

Example:

```text
project/
│
├── main.py
│
└── utilities/
    ├── __init__.py
    ├── calculator.py
    └── string_utils.py
```

Here:

```text
utilities
```

is the package.

---

# 51. Why Use Packages?

Packages help:

* Organize large projects
* Group related modules
* Avoid naming conflicts
* Improve maintainability
* Make code reusable

---

# 52. Creating a Package

Create:

```text
utilities/
```

Inside it:

```text
__init__.py
calculator.py
```

`calculator.py`:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

---

# 53. Importing from a Package

In `main.py`:

```python
from utilities.calculator import add

print(add(10, 20))
```

Output:

```text
30
```

---

# 54. Import the Package Module

You can also write:

```python
from utilities import calculator

print(calculator.add(10, 20))
```

---

# 55. `__init__.py`

Historically, `__init__.py` has been used to mark a directory as a Python package.

Modern Python also supports namespace packages without `__init__.py` in appropriate situations, but `__init__.py` remains very common and useful.

It can be empty:

```python
# __init__.py
```

or contain package initialization code.

---

# 56. Package Example

Project:

```text
student_project/
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

# 57. Nested Packages

Packages can contain subpackages.

Example:

```text
project/
│
├── main.py
│
└── app/
    ├── __init__.py
    │
    ├── database/
    │   ├── __init__.py
    │   └── connection.py
    │
    └── services/
        ├── __init__.py
        └── student.py
```

---

# 58. Absolute Import

An absolute import specifies the complete package path.

Example:

```python
from student.details import get_name
```

---

# 59. Relative Import

Inside a package, relative imports can be used.

Example:

```python
from .details import get_name
```

The dot means:

```text
current package
```

Relative imports are mainly useful inside package modules.

---

# 60. Standard Library

Python includes a large collection of modules known as the **Standard Library**.

Examples:

```text
math
random
datetime
os
sys
json
statistics
collections
pathlib
re
sqlite3
itertools
functools
```

You can use many of these without separately installing them.

---

# 61. `re` Module

The `re` module provides regular expressions.

Example:

```python
import re

text = "My phone number is 9876543210"

result = re.search(r"\d+", text)

print(result.group())
```

Output:

```text
9876543210
```

---

# 62. `itertools`

`itertools` provides tools for creating efficient iterators.

Example:

```python
from itertools import count

numbers = count(10)

print(next(numbers))
print(next(numbers))
print(next(numbers))
```

Output:

```text
10
11
12
```

---

# 63. `functools`

`functools` provides higher-order function utilities.

Example:

```python
from functools import reduce

numbers = [1, 2, 3, 4]

result = reduce(lambda a, b: a + b, numbers)

print(result)
```

Output:

```text
10
```

---

# 64. Third-Party Packages

Not every Python package comes with Python.

Examples of third-party packages include:

```text
NumPy
Pandas
Matplotlib
Requests
Flask
Django
```

These normally need to be installed separately.

---

# 65. What is `pip`?

`pip` is the standard package installer for Python.

You can use it to install third-party packages.

Example:

```text
pip install requests
```

---

# 66. Installing NumPy

```text
pip install numpy
```

Then:

```python
import numpy as np

numbers = np.array([1, 2, 3])

print(numbers)
```

---

# 67. Installing Pandas

```text
pip install pandas
```

Then:

```python
import pandas as pd

data = {
    "Name": ["Yashu", "Rahul"],
    "Marks": [85, 75]
}

df = pd.DataFrame(data)

print(df)
```

---

# 68. Installing Matplotlib

```text
pip install matplotlib
```

Example:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3]
y = [2, 4, 6]

plt.plot(x, y)
plt.show()
```

---

# 69. Checking pip

You can check pip with:

```text
pip --version
```

Depending on your Python installation, this may also be useful:

```text
python -m pip --version
```

Using:

```text
python -m pip
```

helps ensure pip is associated with the Python interpreter you intend to use.

---

# 70. Upgrade a Package

```text
python -m pip install --upgrade requests
```

---

# 71. Uninstall a Package

```text
python -m pip uninstall requests
```

---

# 72. List Installed Packages

```text
python -m pip list
```

---

# 73. Show Package Information

```text
python -m pip show requests
```

---

# 74. `requirements.txt`

A `requirements.txt` file lists project dependencies.

Example:

```text
requests==2.32.4
pandas==2.3.1
numpy==2.3.2
```

The exact versions depend on your environment and project.

---

# 75. Install Requirements

Run:

```text
python -m pip install -r requirements.txt
```

This installs the packages listed in the file.

---

# 76. Generate Requirements

You can export installed packages with:

```text
python -m pip freeze > requirements.txt
```

This records the installed package versions from the current environment.

---

# 77. What is a Virtual Environment?

A **virtual environment** creates an isolated Python environment for a project.

Example:

```text
Project A
→ requests version A

Project B
→ requests version B
```

Each project can have its own dependencies.

---

# 78. Creating a Virtual Environment

Run:

```text
python -m venv .venv
```

This creates:

```text
.venv/
```

---

# 79. Activating Virtual Environment on Windows

In PowerShell:

```text
.venv\Scripts\Activate.ps1
```

In Command Prompt:

```text
.venv\Scripts\activate
```

If PowerShell execution-policy settings prevent activation, you can use another supported shell or configure your environment appropriately.

---

# 80. Activating on macOS/Linux

```text
source .venv/bin/activate
```

---

# 81. Deactivating

Use:

```text
deactivate
```

---

# 82. Checking Python Version

```text
python --version
```

or:

```text
python -V
```

---

# 83. Module Search Path

When Python imports a module, it searches locations listed in:

```python
sys.path
```

Example:

```python
import sys

for path in sys.path:
    print(path)
```

---

# 84. Current Project Directory

Python commonly searches the directory associated with the running script as part of its import process.

Therefore, a file such as:

```text
calculator.py
```

can often be imported by:

```python
import calculator
```

when it is in the appropriate import path.

---

# 85. Common Import Error

You may see:

```text
ModuleNotFoundError: No module named 'calculator'
```

Possible reasons include:

* Wrong filename
* Wrong directory
* Package not installed
* Incorrect Python environment
* Incorrect import path
* Typographical error

---

# 86. Example of a Typo

File:

```text
calculator.py
```

Wrong:

```python
import calculater
```

Correct:

```python
import calculator
```

---

# 87. Package Installation Error

Suppose you write:

```python
import requests
```

and get:

```text
ModuleNotFoundError: No module named 'requests'
```

Install it in the environment being used:

```text
python -m pip install requests
```

Then try:

```python
import requests
```

again.

---

# 88. Wrong Python Environment

Sometimes a package is installed but Python cannot find it because:

```text
Package installed in Environment A
Python running from Environment B
```

Check:

```text
python --version
```

and:

```text
python -m pip --version
```

Make sure they point to the environment you intend to use.

---

# 89. Circular Imports

A circular import occurs when modules depend on each other.

Example:

```text
A imports B
B imports A
```

This can cause confusing import errors.

Avoid unnecessary circular dependencies by restructuring the project.

---

# 90. Module Naming Conflicts

Avoid naming your own file after an important standard or third-party module.

For example, avoid:

```text
random.py
json.py
math.py
requests.py
```

If your project contains `random.py`, then:

```python
import random
```

may import your local file instead of the intended standard-library module.

Prefer names such as:

```text
random_utils.py
json_helpers.py
math_utils.py
```

---

# 91. Import Style

Recommended:

```python
import math
import random
from datetime import datetime
```

Avoid unnecessary wildcard imports:

```python
from math import *
```

Prefer explicit imports.

---

# 92. Multiple Modules Example

Project:

```text
student_app/
│
├── main.py
├── student.py
├── marks.py
└── utils.py
```

`student.py`:

```python
class Student:

    def __init__(self, name):
        self.name = name
```

`marks.py`:

```python
def calculate_average(marks):
    return sum(marks) / len(marks)
```

`utils.py`:

```python
def greet(name):
    return f"Hello, {name}!"
```

---

# 93. Main Program

`main.py`:

```python
from student import Student
from marks import calculate_average
from utils import greet


student = Student("Yashu")

marks = [80, 85, 90]

print(greet(student.name))
print(calculate_average(marks))
```

Output:

```text
Hello, Yashu!
85.0
```

---

# 94. Package-Based Project

A larger project could look like:

```text
student_app/
│
├── main.py
│
├── models/
│   ├── __init__.py
│   └── student.py
│
├── services/
│   ├── __init__.py
│   └── marks.py
│
└── utils/
    ├── __init__.py
    └── helpers.py
```

This structure separates responsibilities.

---

# 95. Practical Example – Calculator Package

Project:

```text
calculator_app/
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
from calculator.basic import add, subtract
from calculator.advanced import square, cube


print(add(10, 5))
print(subtract(10, 5))
print(square(5))
print(cube(3))
```

Output:

```text
15
5
25
27
```

---

# 96. Practical Example – Student Package

Project:

```text
student_app/
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
def get_student():
    return {
        "name": "Yashu",
        "course": "CSE"
    }
```

`result.py`:

```python
def calculate_percentage(marks):

    total = sum(marks)

    return total / len(marks)
```

`main.py`:

```python
from student.details import get_student
from student.result import calculate_percentage


student = get_student()

marks = [80, 85, 90, 95]

print(student)
print(calculate_percentage(marks))
```

Output:

```text
{'name': 'Yashu', 'course': 'CSE'}
87.5
```

---

# 97. Module vs Package

| Module                     | Package                               |
| -------------------------- | ------------------------------------- |
| Usually a `.py` file       | Usually a directory of Python modules |
| Contains Python code       | Organizes multiple modules            |
| Example: `calculator.py`   | Example: `calculator/`                |
| Used for code organization | Used for larger project organization  |

---

# 98. Standard Library vs Third-Party Package

### Standard Library

Comes with Python.

Examples:

```text
math
os
sys
json
datetime
random
```

Usually:

```python
import math
```

No separate installation is required.

### Third-Party Package

Installed separately.

Examples:

```text
numpy
pandas
flask
requests
```

Installation:

```text
python -m pip install package_name
```

---

# 99. Module vs Library vs Package

### Module

A Python file containing reusable code.

### Package

A structured collection of modules.

### Library

A broader term for reusable code distributed for developers to use.

A library can contain packages and modules.

---

# 100. Best Practices

### Use meaningful module names

Good:

```text
student_utils.py
database.py
calculator.py
```

Avoid:

```text
x.py
abc.py
test123.py
```

for production modules.

---

### Keep modules focused

A module should generally have a clear purpose.

For example:

```text
database.py
```

should primarily handle database-related functionality.

---

### Avoid wildcard imports

Prefer:

```python
from math import sqrt
```

instead of:

```python
from math import *
```

---

### Use `__main__` correctly

```python
if __name__ == "__main__":
    main()
```

---

### Use virtual environments

For projects with external dependencies:

```text
.venv
```

helps isolate packages.

---

# 101. Common Mistakes

## Mistake 1

Writing:

```python
import calculator.py
```

Correct:

```python
import calculator
```

---

## Mistake 2

Wrong module name:

```python
import calculater
```

Correct:

```python
import calculator
```

---

## Mistake 3

Installing a package globally but running another environment.

Use:

```text
python -m pip install package_name
```

with the intended Python interpreter/environment active.

---

## Mistake 4

Naming your file:

```text
math.py
```

and then writing:

```python
import math
```

This can cause an import conflict.

---

## Mistake 5

Using wildcard imports unnecessarily.

Avoid:

```python
from module import *
```

Prefer explicit imports.

---

# 102. Mini Challenge 1

Create:

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

Then import the functions into:

```text
main.py
```

---

# 103. Mini Challenge 2

Create a module:

```text
student.py
```

with:

```text
name
age
course
```

Import the variables into:

```text
main.py
```

and print them.

---

# 104. Mini Challenge 3

Create a module:

```text
number_utils.py
```

with:

```text
is_even()
is_odd()
is_prime()
```

Import and test the functions.

---

# 105. Mini Challenge 4

Create a package:

```text
geometry/
```

with:

```text
__init__.py
circle.py
rectangle.py
```

Implement:

```text
circle_area()
rectangle_area()
```

Then use them from:

```text
main.py
```

---

# 106. Mini Challenge 5

Create:

```text
date_utils.py
```

Use the `datetime` module to create functions for:

```text
today's date
tomorrow's date
yesterday's date
```

---

# 107. Mini Challenge 6

Create a package:

```text
student/
```

with:

```text
details.py
marks.py
result.py
```

Implement:

```text
get_student_details()
calculate_total()
calculate_percentage()
```

Use all functions from `main.py`.

---

# 108. Mini Challenge 7

Create:

```text
random_game.py
```

Use the `random` module to create a number guessing game.

The program should:

1. Generate a random number.
2. Ask the user for a guess.
3. Check the guess.
4. Display whether it is correct.

---

# 109. Mini Challenge 8

Create:

```text
utils.py
```

with:

```python
def greet(name):
    return f"Hello, {name}!"
```

Then import it into:

```text
main.py
```

and call:

```python
print(greet("Yashu"))
```

Expected:

```text
Hello, Yashu!
```

---

# 110. Interview Questions

## Q1. What is a module?

A module is a Python file containing reusable code such as functions, classes, and variables.

---

## Q2. How do you import a module?

```python
import module_name
```

---

## Q3. How do you import a specific function?

```python
from module_name import function_name
```

---

## Q4. What is an alias?

An alias is another name given to an imported module or object.

Example:

```python
import numpy as np
```

Here:

```text
np
```

is an alias for:

```text
numpy
```

---

## Q5. What is `__name__`?

`__name__` is a special module variable that identifies the module's execution context.

---

## Q6. What is `__main__`?

When a Python file is executed directly, its `__name__` is:

```text
__main__
```

---

## Q7. Why use:

```python
if __name__ == "__main__":
```

It allows code to run when the file is executed directly without automatically running that code when the module is imported.

---

## Q8. What is a package?

A package is a directory structure used to organize related Python modules.

---

## Q9. What is `__init__.py`?

It is a Python file commonly used in package directories for package initialization and package configuration.

---

## Q10. What is pip?

`pip` is Python's standard package installer for installing and managing Python packages.

---

## Q11. What is a virtual environment?

A virtual environment is an isolated Python environment that keeps a project's dependencies separate from other projects.

---

## Q12. What is `requirements.txt`?

It is a file that lists project dependencies, often including package versions.

---

## Q13. What is `ModuleNotFoundError`?

It occurs when Python cannot find the requested module in its import path or environment.

---

## Q14. What is the difference between a module and a package?

```text
Module
→ Usually one .py file

Package
→ Directory used to organize modules
```

---

# 111. Quick Cheat Sheet

```text
MODULE
↓
Python file
↓
calculator.py
```

Import:

```python
import calculator
```

Specific import:

```python
from calculator import add
```

Alias:

```python
import calculator as calc
```

Multiple imports:

```python
from calculator import add, subtract
```

Package:

```text
calculator/
├── __init__.py
├── basic.py
└── advanced.py
```

Package import:

```python
from calculator.basic import add
```

Standard library:

```python
import math
import random
import os
import sys
```

Third-party package:

```text
python -m pip install requests
```

Virtual environment:

```text
python -m venv .venv
```

Activate on Windows PowerShell:

```text
.venv\Scripts\Activate.ps1
```

Activate on macOS/Linux:

```text
source .venv/bin/activate
```

Deactivate:

```text
deactivate
```

Requirements:

```text
python -m pip install -r requirements.txt
```

Main check:

```python
if __name__ == "__main__":
    main()
```

---

# 🎯 Notes 19 Summary

In this lesson, you learned:

* Modules
* Creating modules
* Importing modules
* `import`
* `from ... import`
* Multiple imports
* Aliases with `as`
* `dir()`
* `help()`
* `__name__`
* `__main__`
* Standard Library
* `math`
* `random`
* `datetime`
* `os`
* `sys`
* `statistics`
* `collections`
* `json`
* `pathlib`
* `re`
* `itertools`
* `functools`
* Packages
* `__init__.py`
* Absolute imports
* Relative imports
* Third-party packages
* `pip`
* `requirements.txt`
* Virtual environments
* `sys.path`
* Import errors
* Circular imports
* Naming conflicts
* Module best practices

---

# 🚀 Next Lesson

## Notes 20 → Python File Handling

You will learn:

```text
Files
Opening files
Reading files
Writing files
Appending files
with open()
File modes
read()
readline()
readlines()
write()
writelines()
File paths
Text files
CSV files
JSON files
Exception handling with files
Working with directories
pathlib
Practical projects
```
