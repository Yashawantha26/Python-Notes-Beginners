Here is your complete **`Notes11.md`** in the same beginner-friendly format, ready to copy.

# Python Beginners Notes – Notes 11

## 📘 Topic: Modules and Packages in Python

Modules and packages help us **organize Python code**, reuse code, and build larger projects easily.

---

# 1. What is a Module?

A **module** is a Python file (`.py`) that contains:

* Variables
* Functions
* Classes
* Statements

Example:

```text
math_utils.py
```

can contain:

```python
def add(a, b):
    return a + b
```

We can use this function in another Python file.

---

# 2. Why Use Modules?

Modules help us:

* Reuse code
* Organize programs
* Reduce duplicate code
* Make programs easier to maintain
* Keep large projects clean

---

# 3. Creating Your Own Module

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

Use the `import` keyword.

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

---

# 5. `import` Statement

The `import` statement loads a module.

Syntax:

```python
import module_name
```

Example:

```python
import math
```

Now we can use functions from the `math` module.

---

# 6. Python Built-in Modules

Python provides many ready-made modules.

Some important modules:

| Module       | Purpose                     |
| ------------ | --------------------------- |
| `math`       | Mathematical operations     |
| `random`     | Random numbers              |
| `datetime`   | Date and time               |
| `os`         | Operating system operations |
| `sys`        | Python system information   |
| `statistics` | Statistical calculations    |
| `json`       | JSON data handling          |

---

# 7. Math Module

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

# 8. `math.pi`

```python
import math

print(math.pi)
```

Output:

```text
3.141592653589793
```

---

# 9. `math.pow()`

Used to calculate powers.

```python
import math

print(math.pow(2, 3))
```

Output:

```text
8.0
```

---

# 10. `math.ceil()`

Rounds a number **up**.

```python
import math

print(math.ceil(4.2))
```

Output:

```text
5
```

---

# 11. `math.floor()`

Rounds a number **down**.

```python
import math

print(math.floor(4.8))
```

Output:

```text
4
```

---

# 12. `math.factorial()`

Calculates factorial.

```python
import math

print(math.factorial(5))
```

Output:

```text
120
```

Because:

```text
5! = 5 × 4 × 3 × 2 × 1
   = 120
```

---

# 13. Random Module

The `random` module is used to generate random values.

```python
import random

number = random.randint(1, 10)

print(number)
```

Possible output:

```text
7
```

The number can be different each time.

---

# 14. `random.randint()`

Generates a random integer between two numbers.

```python
import random

print(random.randint(1, 100))
```

Possible output:

```text
64
```

---

# 15. `random.random()`

Generates a random floating-point number between `0` and `1`.

```python
import random

print(random.random())
```

Example:

```text
0.734521
```

---

# 16. Choosing a Random Item

`random.choice()` selects a random item from a sequence.

```python
import random

names = ["Yashu", "Rahul", "Anil", "Kiran"]

print(random.choice(names))
```

Possible output:

```text
Kiran
```

---

# 17. Random Password Example

```python
import random

characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"

password = ""

for i in range(6):
    password += random.choice(characters)

print(password)
```

Possible output:

```text
A7K92P
```

---

# 18. Datetime Module

The `datetime` module is used to work with:

* Date
* Time
* Date and time

Example:

```python
import datetime

print(datetime.datetime.now())
```

Possible output:

```text
2026-08-30 19:30:25
```

---

# 19. Current Date

```python
from datetime import date

today = date.today()

print(today)
```

Example:

```text
2026-08-30
```

---

# 20. Current Time

```python
from datetime import datetime

current_time = datetime.now()

print(current_time.time())
```

---

# 21. Formatting Date and Time

The `strftime()` method formats date and time.

```python
from datetime import datetime

now = datetime.now()

print(now.strftime("%d-%m-%Y"))
```

Example output:

```text
30-08-2026
```

---

# 22. Common Date Format Codes

| Code | Meaning |
| ---- | ------- |
| `%d` | Day     |
| `%m` | Month   |
| `%Y` | Year    |
| `%H` | Hour    |
| `%M` | Minute  |
| `%S` | Second  |

Example:

```python
from datetime import datetime

now = datetime.now()

print(now.strftime("%d/%m/%Y"))
print(now.strftime("%H:%M:%S"))
```

---

# 23. OS Module

The `os` module allows Python to interact with the operating system.

```python
import os

print(os.getcwd())
```

`getcwd()` returns the current working directory.

---

# 24. Creating a Folder Using `os`

```python
import os

os.mkdir("MyFolder")
```

This creates:

```text
MyFolder
```

---

# 25. Listing Files

`os.listdir()` displays files and folders.

```python
import os

print(os.listdir())
```

---

# 26. Checking if a File Exists

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

---

# 27. Removing a File

```python
import os

if os.path.exists("data.txt"):
    os.remove("data.txt")
    print("File deleted")
```

---

# 28. SYS Module

The `sys` module provides information about the Python environment.

```python
import sys

print(sys.version)
```

This displays the Python version installed on your computer.

---

# 29. Command Line Arguments

The `sys.argv` list contains command-line arguments.

Example:

```python
import sys

print(sys.argv)
```

If you run:

```text
python main.py hello
```

You may get:

```text
['main.py', 'hello']
```

---

# 30. Statistics Module

The `statistics` module provides statistical functions.

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

# 31. Median

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

# 32. Mode

The mode is the value that occurs most frequently.

```python
import statistics

numbers = [10, 20, 20, 30, 40]

print(statistics.mode(numbers))
```

Output:

```text
20
```

---

# 33. Import Specific Function

Instead of importing the entire module, we can import a specific function.

```python
from math import sqrt

print(sqrt(25))
```

Output:

```text
5.0
```

---

# 34. Import Multiple Functions

```python
from math import sqrt, factorial

print(sqrt(16))
print(factorial(5))
```

Output:

```text
4.0
120
```

---

# 35. Import Everything

You can use:

```python
from math import *
```

Then:

```python
print(sqrt(25))
print(pi)
```

### ⚠️ Recommendation

Avoid `from module import *` in larger programs because it can make code harder to understand.

Prefer:

```python
import math
```

or:

```python
from math import sqrt
```

---

# 36. Using an Alias

An alias gives a module a shorter name.

Syntax:

```python
import module as alias
```

Example:

```python
import math as m

print(m.sqrt(25))
```

Output:

```text
5.0
```

---

# 37. Alias for Random

```python
import random as r

print(r.randint(1, 10))
```

---

# 38. Importing Your Own Module

Suppose we have:

```text
project/
│
├── main.py
└── calculator.py
```

`calculator.py`:

```python
def add(a, b):
    return a + b
```

`main.py`:

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

Output:

```text
30
```

---

# 39. Module with Variables and Functions

`student.py`:

```python
name = "Yashu"
course = "Computer Science"

def display():
    print("Name:", name)
    print("Course:", course)
```

`main.py`:

```python
import student

student.display()
```

Output:

```text
Name: Yashu
Course: Computer Science
```

---

# 40. `__name__`

Python provides a special variable called:

```python
__name__
```

When a Python file is executed directly:

```python
__name__ == "__main__"
```

---

# 41. Using `if __name__ == "__main__"`

Example:

```python
def greet():
    print("Hello Python")


if __name__ == "__main__":
    greet()
```

This code runs `greet()` only when the file is executed directly.

---

# 42. Why Use `__name__`?

Suppose `calculator.py` contains:

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))
```

When running:

```text
python calculator.py
```

Output:

```text
30
```

But when another file imports it:

```python
import calculator
```

the test code inside:

```python
if __name__ == "__main__":
```

does not execute.

---

# 43. What is a Package?

A **package** is a folder containing Python modules.

Example:

```text
myproject/
│
├── main.py
│
└── tools/
    ├── __init__.py
    ├── calculator.py
    └── converter.py
```

Here:

```text
tools
```

is a package.

---

# 44. Creating a Package

Folder:

```text
tools/
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
```

---

# 45. Importing from a Package

In `main.py`:

```python
from tools.calculator import add

print(add(10, 20))
```

Output:

```text
30
```

---

# 46. Module vs Package

| Module                     | Package                     |
| -------------------------- | --------------------------- |
| A single `.py` file        | A folder containing modules |
| Contains functions/classes | Organizes multiple modules  |
| Example: `math_utils.py`   | Example: `tools/`           |
| Smaller unit               | Larger structure            |

---

# 47. Standard Library

Python comes with a large collection of modules called the **Python Standard Library**.

Examples:

```text
math
random
datetime
os
sys
json
statistics
```

You can use many of them without installing anything separately.

---

# 48. Third-Party Modules

Third-party modules are created by other developers and are installed separately.

Examples:

```text
NumPy
Pandas
Matplotlib
Requests
Flask
Django
```

These are commonly installed using `pip`.

---

# 49. What is pip?

`pip` is Python's package installer.

Example:

```text
pip install requests
```

This installs the `requests` package.

---

# 50. Checking pip

You can check whether pip is available:

```text
pip --version
```

---

# 51. Installing a Package

Example:

```text
pip install numpy
```

After installation:

```python
import numpy

print(numpy.array([1, 2, 3]))
```

---

# 52. Uninstalling a Package

```text
pip uninstall numpy
```

---

# 53. Listing Installed Packages

```text
pip list
```

This displays installed Python packages.

---

# 54. Requirements File

Python projects often use:

```text
requirements.txt
```

Example:

```text
requests
numpy
pandas
flask
```

Install everything using:

```text
pip install -r requirements.txt
```

---

# 55. Mini Project – Random Number Generator

```python
import random

start = int(input("Enter starting number: "))
end = int(input("Enter ending number: "))

number = random.randint(start, end)

print("Random number:", number)
```

---

# 56. Mini Project – Simple Calculator Module

Create:

```text
calculator.py
```

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b


def divide(a, b):
    if b == 0:
        return "Cannot divide by zero"
    return a / b
```

Create:

```text
main.py
```

```python
import calculator

a = 20
b = 5

print("Addition:", calculator.add(a, b))
print("Subtraction:", calculator.subtract(a, b))
print("Multiplication:", calculator.multiply(a, b))
print("Division:", calculator.divide(a, b))
```

Output:

```text
Addition: 25
Subtraction: 15
Multiplication: 100
Division: 4.0
```

---

# 57. Mini Project – Dice Simulator

```python
import random

dice = random.randint(1, 6)

print("You rolled:", dice)
```

Possible output:

```text
You rolled: 4
```

---

# 58. Mini Project – Random Name Picker

```python
import random

names = [
    "Yashu",
    "Rahul",
    "Kiran",
    "Anil",
    "Arjun"
]

winner = random.choice(names)

print("Selected name:", winner)
```

---

# 59. Mini Project – Current Date and Time

```python
from datetime import datetime

now = datetime.now()

print("Current date and time:")
print(now.strftime("%d-%m-%Y %H:%M:%S"))
```

---

# 60. Common Mistakes

### Mistake 1: Wrong module name

Wrong:

```python
import mathh
```

Correct:

```python
import math
```

---

### Mistake 2: Forgetting the module name

If you write:

```python
import math

print(sqrt(25))
```

You may get:

```text
NameError
```

Correct:

```python
print(math.sqrt(25))
```

---

### Mistake 3: Wrong package path

If the structure is:

```text
tools/
    calculator.py
```

Use:

```python
from tools.calculator import add
```

---

# 61. Practice Questions

## Beginner

### Question 1

Import the `math` module and find the square root of `144`.

---

### Question 2

Use the `random` module to generate a number between `1` and `100`.

---

### Question 3

Use `datetime` to display the current date.

---

### Question 4

Create your own module containing:

```text
add()
subtract()
multiply()
```

Import it into another Python file.

---

### Question 5

Use the `statistics` module to find the mean of:

```python
[10, 20, 30, 40, 50]
```

---

## Intermediate

### Question 6

Create a dice simulator using `random`.

---

### Question 7

Create a random name picker.

---

### Question 8

Create a calculator module and use it from `main.py`.

---

### Question 9

Create a package called `student` containing:

```text
student_info.py
marks.py
```

Import functions from both modules.

---

### Question 10

Create a program that displays the current date and time in this format:

```text
30-08-2026 19:30:00
```

---

# 62. Quick Revision

```text
Module          → Python file containing reusable code

import          → Import a module

from            → Import specific items

as              → Create an alias

Package         → Folder containing modules

pip             → Python package installer

__name__        → Special Python variable

__main__        → Indicates direct execution

math            → Mathematical operations

random          → Random values

datetime        → Date and time

os              → Operating system operations

sys             → Python system information

statistics      → Statistical operations
```

---

# 🎯 Notes 11 Summary

In this lesson, you learned:

* What modules are
* Why modules are useful
* Creating your own modules
* Importing modules
* `import`
* `from ... import`
* Module aliases
* Built-in modules
* `math`
* `random`
* `datetime`
* `os`
* `sys`
* `statistics`
* `__name__`
* `__main__`
* Packages
* Python Standard Library
* Third-party packages
* `pip`
* `requirements.txt`
* Creating reusable Python projects

## ⭐ Key Point

Modules help you **write code once and reuse it anywhere**.

```python
import math

print(math.sqrt(100))
```

Output:

```text
10.0
```

**Next:** Notes 12 → **Python Object-Oriented Programming (OOP) Basics**
