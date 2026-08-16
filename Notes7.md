🐍 Notes 7 — Python Modules & Packages

# 🐍 Python Notes 7 — Modules & Packages

> A beginner-friendly guide to Python Modules, Packages, Imports, Standard Library, `pip`, external packages, `__name__`, and how to organize Python projects.

---

## 📌 Table of Contents

1. What is a Module?
2. Why Use Modules?
3. Creating a Module
4. Importing a Module
5. `import`
6. `from ... import`
7. Import Multiple Items
8. Import with Alias
9. Your Own Module
10. Module Variables
11. Module Functions
12. Module Classes
13. `dir()`
14. `__name__`
15. `if __name__ == "__main__"`
16. What is a Package?
17. Package Structure
18. Importing from Packages
19. Subpackages
20. Standard Library
21. `math`
22. `random`
23. `datetime`
24. `os`
25. `sys`
26. `json`
27. `statistics`
28. `collections`
29. `re`
30. `pathlib`
31. What is pip?
32. Installing Packages
33. Requirements File
34. Virtual Environments
35. `venv`
36. Third-Party Packages
37. Common Python Packages
38. Module vs Package
39. Common Errors
40. Practice Programs
41. Practice Questions
42. Mini Projects
43. Quick Revision
44. Learning Path

---

# 1. 🧠 What is a Module?

A **module** is a Python file containing code that can be reused in another Python program.

A Python file ending with:

```text
.py

can be used as a module.

Example:

calculator.py

The file can contain:

def add(a, b):
    return a + b


def subtract(a, b):
    return a - b

Another Python file can import these functions.


---

2. ⭐ Why Use Modules?

Modules help us:

Reuse code

Organize large programs

Avoid repeating code

Make projects easier to maintain

Separate different parts of an application


Instead of having:

app.py

with 1,000 lines of code, we can organize it:

project/
│
├── app.py
├── calculator.py
├── users.py
├── database.py
└── utilities.py

This makes the project easier to understand.


---

3. 🛠️ Creating a Module

Create:

calculator.py

Add:

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

Now calculator.py is a module.


---

4. 📥 Importing a Module

Create another file:

main.py

Import the module:

import calculator

Use its functions:

print(calculator.add(10, 20))
print(calculator.subtract(20, 5))

Output:

30
15


---

5. 📦 The import Statement

Syntax:

import module_name

Example:

import math

Then use:

print(math.sqrt(25))

Output:

5.0


---

6. 🎯 from ... import

Instead of importing the entire module, you can import a specific function.

from math import sqrt

print(sqrt(25))

You don't need:

math.sqrt()

You can directly use:

sqrt()


---

7. 📚 Import Multiple Items

from math import sqrt, factorial

print(sqrt(25))
print(factorial(5))

Output:

5.0
120


---

8. 🏷️ Import with Alias

An alias gives a module another name.

Example:

import math as m

print(m.sqrt(25))

Output:

5.0

Another common example:

import numpy as np

Then:

np.array([1, 2, 3])


---

9. 🧑‍💻 Import Your Own Module

Suppose the project contains:

project/
│
├── main.py
└── calculator.py

calculator.py:

def add(a, b):
    return a + b

main.py:

import calculator

result = calculator.add(10, 20)

print(result)

Output:

30


---

10. 📊 Module Variables

A module can contain variables.

student.py:

name = "Yashu"
age = 20
branch = "CSE"

main.py:

import student

print(student.name)
print(student.age)
print(student.branch)


---

11. 🔧 Module Functions

A module can contain multiple functions.

calculator.py:

def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b

main.py:

import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
print(calculator.multiply(10, 5))


---

12. 🏗️ Modules Can Contain Classes

student.py:

class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name)
        print(self.age)

main.py:

from student import Student

student = Student("Yashu", 20)

student.display()


---

13. 🔍 The dir() Function

dir() shows names available inside an object or module.

Example:

import math

print(dir(math))

It displays functions, variables, and other names available in the math module.

You can also use:

import calculator

print(dir(calculator))


---

14. 🧠 What is __name__?

Every Python module has a special variable called:

__name__

When a file is executed directly:

__name__

usually contains:

__main__

When the file is imported:

__name__

contains the module's name.


---

15. 🚀 if __name__ == "__main__"

This is one of the most important Python patterns.

Example:

def greet():
    print("Hello Python")


if __name__ == "__main__":
    greet()

If you run this file directly, greet() runs.

If you import the file into another program, the code inside:

if __name__ == "__main__":

does not run automatically.


---

16. 💡 Why Use __main__?

Suppose:

calculator.py
main.py

calculator.py:

def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))

If you run:

python calculator.py

Output:

30

But if main.py does:

import calculator

the test code does not execute automatically.

This keeps modules clean and reusable.


---

17. 📦 What is a Package?

A package is a collection of related Python modules organized inside a directory.

Example:

myproject/
│
├── main.py
│
└── utilities/
    ├── __init__.py
    ├── calculator.py
    └── text.py

Here:

utilities

is the package.

calculator.py
text.py

are modules.


---

18. 📁 Package Structure

Example:

student_project/
│
├── main.py
│
└── student/
    ├── __init__.py
    ├── details.py
    └── marks.py

details.py:

def get_name():
    return "Yashu"

marks.py:

def get_marks():
    return 90


---

19. 📥 Importing from a Package

In main.py:

from student.details import get_name
from student.marks import get_marks

print(get_name())
print(get_marks())

Output:

Yashu
90


---

20. 📦 What is __init__.py?

__init__.py is commonly used to mark and initialize a Python package.

Example:

student/
│
├── __init__.py
├── details.py
└── marks.py

The file can be empty:

# Package initialization

Modern Python also supports namespace packages without requiring __init__.py in every case, but beginners will commonly see it in regular packages.


---

21. 🪆 Subpackages

A package can contain another package.

Example:

project/
│
├── main.py
│
└── school/
    ├── __init__.py
    │
    ├── students/
    │   ├── __init__.py
    │   └── student.py
    │
    └── teachers/
        ├── __init__.py
        └── teacher.py

This is useful for large applications.


---

22. 📚 Python Standard Library

Python comes with many built-in modules.

These are called the Python Standard Library.

Examples:

math
random
datetime
os
sys
json
statistics
collections
re
pathlib

You usually don't need to install these separately.


---

23. 🧮 math Module

The math module provides mathematical functions.

import math

Square root:

print(math.sqrt(25))

Output:

5.0

Power:

print(math.pow(2, 3))

Output:

8.0

Ceiling:

print(math.ceil(4.2))

Output:

5

Floor:

print(math.floor(4.8))

Output:

4


---

24. 🥧 Math Constants

import math

print(math.pi)
print(math.e)

math.pi gives the value of π.


---

25. 🎲 random Module

The random module generates pseudo-random values.

import random

Random integer:

number = random.randint(1, 10)

print(number)

This generates an integer from 1 through 10.


---

26. 🎯 Random Choice

import random

fruits = ["Apple", "Banana", "Mango"]

print(random.choice(fruits))

One item is selected randomly.


---

27. 🔀 Shuffle a List

import random

numbers = [1, 2, 3, 4, 5]

random.shuffle(numbers)

print(numbers)

The list is shuffled in place.


---

28. 📅 datetime Module

Used for dates and times.

from datetime import datetime

now = datetime.now()

print(now)


---

29. 📅 Current Date

from datetime import date

today = date.today()

print(today)


---

30. 🕐 Format Date and Time

from datetime import datetime

now = datetime.now()

formatted = now.strftime("%d-%m-%Y %H:%M:%S")

print(formatted)

Common formatting:

%d → Day
%m → Month
%Y → Year
%H → Hour
%M → Minute
%S → Second


---

31. 💻 os Module

The os module allows Python to interact with the operating system.

import os

Current directory:

print(os.getcwd())

List files:

print(os.listdir())


---

32. 📁 Create Directory with os

import os

os.mkdir("data")

> This raises an error if the directory already exists. For more flexible directory creation, pathlib.Path(...).mkdir(exist_ok=True) is often convenient.




---

33. 🗑️ Remove Directory

import os

os.rmdir("data")

The directory generally needs to be empty.


---

34. 🖥️ sys Module

The sys module provides access to Python's runtime environment.

import sys

print(sys.version)

This displays the Python version.


---

35. 📌 Command-Line Arguments

sys.argv contains command-line arguments.

Example:

import sys

print(sys.argv)

If you run:

python app.py Yashu

you can access:

print(sys.argv[1])

Output:

Yashu


---

36. 📄 json Module

JSON is commonly used for storing and transferring structured data.

Example Python dictionary:

student = {
    "name": "Yashu",
    "age": 20
}

Convert dictionary to JSON:

import json

data = json.dumps(student)

print(data)


---

37. 🔄 JSON to Python

Use json.loads().

import json

data = '{"name": "Yashu", "age": 20}'

student = json.loads(data)

print(student["name"])


---

38. 💾 Save JSON to a File

import json

student = {
    "name": "Yashu",
    "age": 20,
    "branch": "CSE"
}

with open("student.json", "w") as file:
    json.dump(student, file, indent=4)


---

39. 📖 Read JSON from a File

import json

with open("student.json", "r") as file:
    student = json.load(file)

print(student)


---

40. 📊 statistics Module

Used for basic statistical calculations.

import statistics

numbers = [10, 20, 30, 40, 50]

print(statistics.mean(numbers))
print(statistics.median(numbers))

Output:

30
30


---

41. 📦 collections Module

The collections module provides specialized containers.

Example:

from collections import Counter

Count values:

numbers = [1, 2, 2, 3, 3, 3]

counter = Counter(numbers)

print(counter)

Output:

Counter({3: 3, 2: 2, 1: 1})


---

42. 🔤 Counter with Strings

from collections import Counter

text = "banana"

count = Counter(text)

print(count)

It counts how many times each character occurs.


---

43. 🔎 re Module

The re module provides regular expressions.

Example:

import re

text = "My phone number is 9876543210"

result = re.search(r"\d+", text)

print(result.group())

Output:

9876543210

Regular expressions are useful for:

Email validation
Phone number patterns
Searching text
Replacing text
Extracting information


---

44. 📂 pathlib

pathlib provides an object-oriented way to work with file paths.

from pathlib import Path

path = Path("data")

print(path.exists())

Create a directory:

path.mkdir(exist_ok=True)


---

45. 📄 Create a File with pathlib

from pathlib import Path

file = Path("notes.txt")

file.write_text("Python is easy to learn!")

print(file.read_text())


---

46. 🆚 os vs pathlib

Both can work with files and directories.

For new code, pathlib is often easier to read:

from pathlib import Path

path = Path("data")
path.mkdir(exist_ok=True)


---

47. 📦 What is pip?

pip is Python's package installer.

It is used to install third-party packages.

Example:

pip install requests


---

48. 🔍 Check pip

Run in the terminal:

python -m pip --version

Using:

python -m pip

is often more reliable because it ensures pip is associated with the Python interpreter you're using.


---

49. 📥 Install a Package

Example:

python -m pip install requests

After installation:

import requests


---

50. 🔄 Upgrade a Package

python -m pip install --upgrade requests


---

51. 🗑️ Uninstall a Package

python -m pip uninstall requests


---

52. 📋 List Installed Packages

python -m pip list


---

53. 🔎 Show Package Information

python -m pip show requests


---

54. 📄 requirements.txt

A requirements.txt file lists project dependencies.

Example:

requests
flask
python-dotenv

Install all:

python -m pip install -r requirements.txt


---

55. 📌 Why Use requirements.txt?

Suppose your project needs:

Flask
requests
python-dotenv

Another developer can install everything with:

python -m pip install -r requirements.txt

This makes projects easier to share.


---

56. 📦 Freeze Dependencies

You can generate a requirements file:

python -m pip freeze > requirements.txt

This records installed package versions.

Example:

Flask==3.x.x
requests==2.x.x

The exact versions depend on your environment.


---

57. 🌐 Third-Party Packages

Third-party packages are created by the Python community and are installed separately.

Popular examples:

requests
Flask
Django
NumPy
Pandas
Matplotlib
scikit-learn

These are not all part of Python's standard library.


---

58. 🌐 requests

Used for making HTTP requests.

Install:

python -m pip install requests

Example:

import requests

response = requests.get("https://example.com")

print(response.status_code)


---

59. 🌐 Flask

Flask is a lightweight Python web framework.

Install:

python -m pip install flask

Basic example:

from flask import Flask

app = Flask(__name__)


@app.route("/")
def home():
    return "Hello Python!"


if __name__ == "__main__":
    app.run()


---

60. 📊 NumPy

NumPy is widely used for numerical computing.

Install:

python -m pip install numpy

Example:

import numpy as np

numbers = np.array([1, 2, 3, 4])

print(numbers)


---

61. 📊 Pandas

Pandas is widely used for data analysis.

Install:

python -m pip install pandas

Example:

import pandas as pd

data = {
    "Name": ["Yashu", "Rahul"],
    "Marks": [90, 85]
}

df = pd.DataFrame(data)

print(df)


---

62. 📈 Matplotlib

Matplotlib is commonly used for visualization.

Install:

python -m pip install matplotlib

Example:

import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [10, 20, 15, 25]

plt.plot(x, y)

plt.show()


---

63. 🧪 Virtual Environment

A virtual environment creates an isolated Python environment for a project.

Example:

project/
│
├── .venv/
├── app.py
└── requirements.txt

This prevents project dependencies from interfering with each other.


---

64. 🏗️ Create Virtual Environment

Windows:

python -m venv .venv

macOS/Linux:

python3 -m venv .venv


---

65. ▶️ Activate Virtual Environment

Windows PowerShell

.\.venv\Scripts\Activate.ps1

Windows Command Prompt

.venv\Scripts\activate

macOS/Linux

source .venv/bin/activate

After activation, your terminal normally shows something like:

(.venv)


---

66. ⏹️ Deactivate Virtual Environment

deactivate


---

67. 📦 Install Packages in Virtual Environment

After activation:

python -m pip install flask

Then create:

python -m pip freeze > requirements.txt


---

68. 🏗️ Recommended Project Structure

A small Python project:

my-project/
│
├── .venv/
│
├── app.py
├── calculator.py
├── requirements.txt
└── README.md

A larger project:

my-project/
│
├── .venv/
│
├── app/
│   ├── __init__.py
│   ├── routes.py
│   ├── models.py
│   └── utils.py
│
├── tests/
│   └── test_app.py
│
├── requirements.txt
└── README.md


---

69. 🧩 Module vs Package

Feature	Module	Package

Meaning	Python file	Collection of modules
Extension	.py	Directory
Example	calculator.py	utilities/
Contains	Functions/classes/variables	Modules/subpackages
Purpose	Organize reusable code	Organize larger codebases



---

70. 🧠 Standard Library vs Third-Party

Standard Library

Usually available with Python:

import math
import random
import os
import json

No separate installation is normally required.

Third-Party

Usually installed with pip:

python -m pip install requests

Then:

import requests


---

71. ⚠️ Common Import Error

Error:

ModuleNotFoundError: No module named 'requests'

Possible solution:

python -m pip install requests

If using a virtual environment, make sure it is activated first.


---

72. ⚠️ Wrong File Name

Avoid naming your own files after standard libraries.

For example, don't create:

random.py
math.py
json.py

If you do, Python may import your file instead of the standard library module.

Better:

random_demo.py
math_examples.py
json_handler.py


---

73. ⚠️ Circular Imports

Avoid situations like:

A imports B
B imports A

This can create circular import problems.

Better project design usually separates shared functionality into another module.

Example:

utils.py

Then:

A → utils
B → utils

instead of:

A ↔ B


---

74. 🔥 Practical Example — Calculator Package

Project:

calculator_project/
│
├── main.py
│
└── calculator/
    ├── __init__.py
    ├── basic.py
    └── advanced.py

basic.py:

def add(a, b):
    return a + b


def subtract(a, b):
    return a - b

advanced.py:

def square(a):
    return a ** 2


def cube(a):
    return a ** 3

main.py:

from calculator.basic import add
from calculator.advanced import square

print(add(10, 20))
print(square(5))

Output:

30
25


---

75. 🔥 Practical Example — Utility Module

Create:

utils.py

def is_even(number):
    return number % 2 == 0


def is_prime(number):

    if number < 2:
        return False

    for i in range(2, int(number ** 0.5) + 1):

        if number % i == 0:
            return False

    return True

Use it:

from utils import is_even, is_prime

print(is_even(10))
print(is_prime(7))

Output:

True
True


---

76. 🧪 Testing Modules

Suppose:

# calculator.py

def add(a, b):
    return a + b

Test:

# test_calculator.py

from calculator import add

assert add(2, 3) == 5
assert add(10, 20) == 30

print("All tests passed!")


---

77. 📌 Important Import Styles

Import module

import math

Use:

math.sqrt(25)

Import specific function

from math import sqrt

Use:

sqrt(25)

Import with alias

import math as m

Use:

m.sqrt(25)

Import multiple functions

from math import sqrt, ceil, floor


---

78. 🧠 Best Practices

1. Use meaningful module names

Good:

calculator.py
database.py
student.py
utils.py

Avoid:

x.py
abc.py
test123.py

for production code.


---

2. Keep modules focused

A module should generally have a clear purpose.

Example:

database.py

for database-related functionality.

auth.py

for authentication-related functionality.


---

3. Avoid unnecessary wildcard imports

Avoid:

from math import *

Prefer:

from math import sqrt

This makes it clear where names come from and reduces naming conflicts.


---

79. 📝 Practice Questions

Beginner

1. What is a module?


2. Create your own module.


3. Import your module into another file.


4. Create a module containing calculator functions.


5. Import only one function from a module.


6. Import a module using an alias.


7. Use the math module.


8. Use the random module.


9. Use the datetime module.


10. Use the os module.




---

80. 📝 Intermediate Practice

11. Create a utility module.


12. Create a package containing two modules.


13. Import a function from a package.


14. Create a student package.


15. Create a calculator package.


16. Use json to save student data.


17. Read JSON data from a file.


18. Use Counter to count characters.


19. Use pathlib to create a folder.


20. Create a requirements.txt.




---

81. 📝 Advanced Practice

21. Create a complete calculator package.


22. Create a student management package.


23. Create separate modules for database, utilities, and application logic.


24. Create a virtual environment.


25. Install Flask in the environment.


26. Generate requirements.txt.


27. Create a project with tests.


28. Use __name__ == "__main__".


29. Build a reusable utility library.


30. Organize a Python project into packages.
82. 🚀 Mini Project — Utility Toolkit
Create:
python-toolkit/
│
├── main.py
│
└── toolkit/
    ├── __init__.py
    ├── numbers.py
    ├── strings.py
    └── dates.py
numbers.py:
def is_even(number):
    return number % 2 == 0


def square(number):
    return number ** 2
strings.py:
def reverse(text):
    return text[::-1]


def count_characters(text):
    return len(text)
main.py:
from toolkit.numbers import is_even, square
from toolkit.strings import reverse

print(is_even(10))
print(square(5))
print(reverse("Python"))



---



    83. 🚀 Mini Project — Student Package
Structure:
student-app/
│
├── main.py
│
└── student/
    ├── __init__.py
    ├── details.py
    └── marks.py
details.py:
def student_details(name, age, branch):
    return {
        "name": name,
        "age": age,
        "branch": branch
    }
marks.py:
def calculate_average(marks):
    return sum(marks) / len(marks)
main.py:
from student.details import student_details
from student.marks import calculate_average

student = student_details(
    "Yashu",
    20,
    "CSE"
)

marks = [90, 85, 88]

print(student)
print("Average:", calculate_average(marks))
84. 🚀 Mini Project — Random Password Generator
import random
import string


def generate_password(length):

    characters = string.ascii_letters + string.digits

    password = ""

    for _ in range(length):
        password += random.choice(characters)

    return password


print(generate_password(10))
This demonstrates:
Modules
Functions
Loops
Strings
Random selection
85. 🚀 Mini Project — JSON Student Database
import json


student = {
    "name": "Yashu",
    "age": 20,
    "branch": "CSE",
    "marks": [90, 85, 88]
}


with open("student.json", "w") as file:
    json.dump(student, file, indent=4)


with open("student.json", "r") as file:
    data = json.load(file)


print(data)
86. 🎯 Quick Revision
Module
import math
Specific Import
from math import sqrt
Alias
import numpy as np
Package
package/
├── __init__.py
├── module1.py
└── module2.py
Package Import
from package.module1 import function
Main Check
if __name__ == "__main__":
    main()
Install Package
python -m pip install package_name
Requirements
python -m pip install -r requirements.txt
Virtual Environment
python -m venv .venv
87. 🧠 Most Important Concepts
Before moving to Notes 8, understand:
✅ Module
✅ import
✅ from ... import
✅ Aliases
✅ Your own modules
✅ Packages
✅ __init__.py
✅ __name__
✅ __main__
✅ Standard Library
✅ pip
✅ requirements.txt
✅ Virtual environments
✅ Third-party packages
🚀 Python Learning Path
Notes 1  → Python Basics
     ↓
Notes 2  → Control Flow
     ↓
Notes 3  → Strings
     ↓
Notes 4  → Lists
     ↓
Notes 5  → Tuples, Sets & Dictionaries
     ↓
Notes 6  → Functions
     ↓
Notes 7  → Modules & Packages ✅
     ↓
Notes 8  → File Handling
     ↓
Notes 9  → Exception Handling
     ↓
Notes 10 → Object-Oriented Programming
     ↓
Notes 11 → Advanced Python
     ↓
Notes 12 → NumPy
     ↓
Notes 13 → Pandas
     ↓
Notes 14 → Matplotlib
     ↓
Projects 🚀
⭐ Final Concept
Think of Python code like a toolbox:
                    🧰 PYTHON PROJECT
                           │
          ┌────────────────┼────────────────┐
          ↓                ↓                ↓
       MODULE           MODULE           MODULE
          │                │                │
     calculator.py     users.py        database.py
          │                │                │
       functions         classes        functions
          │                │                │
          └────────────────┼────────────────┘
                           ↓
                       main.py
A module helps organize reusable code.
A package helps organize multiple related modules.
A library/package from pip gives you functionality created by others.
import math

def calculate_area(radius):
    return math.pi * radius ** 2


if __name__ == "__main__":
    print(calculate_area(5))
Remember:
Module = reusable Python file 📄
Package = collection of related modules 📦
pip = package installer 📥
Virtual environment = isolated project environment 🛡️
Good structure = easier projects 🚀
Happy Coding! 🐍💻🔥