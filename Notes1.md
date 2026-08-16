# 🐍 Python Notes 1 — Complete Beginner Basics

> A simple and easy-to-understand Python reference for beginners.

---

## 📌 Table of Contents

1. What is Python?
2. Why Learn Python?
3. Installing Python
4. First Python Program
5. Comments
6. Variables
7. Data Types
8. Numbers
9. Strings
10. Boolean
11. Input and Output
12. Type Casting
13. Operators
14. Basic Practice Programs
15. Important Points

---

# 1. 🐍 What is Python?

**Python** is a high-level, interpreted, general-purpose programming language.

It was created by **Guido van Rossum** and first released in **1991**.

Python is popular because its syntax is simple and easy to read.

### Example

```python
print("Hello, World!")
```

Output:

```text
Hello, World!
```

---

# 2. ⭐ Why Learn Python?

Python is used in many areas:

* 🌐 Web Development
* 🤖 Artificial Intelligence
* 🧠 Machine Learning
* 📊 Data Science
* 🔐 Cybersecurity
* ⚙️ Automation
* 🖥️ Software Development
* 📱 Application Development
* 📈 Data Analysis

### Popular Python Libraries

| Library    | Use                 |
| ---------- | ------------------- |
| NumPy      | Numerical computing |
| Pandas     | Data analysis       |
| Matplotlib | Data visualization  |
| Flask      | Web development     |
| Django     | Web development     |
| TensorFlow | Machine Learning    |
| PyTorch    | Deep Learning       |

---

# 3. 💻 Installing Python

Download Python from the official Python website.

During installation on Windows, make sure to select:

```text
Add Python to PATH
```

Check installation:

```powershell
python --version
```

Example:

```text
Python 3.x.x
```

You can also check:

```powershell
py --version
```

---

# 4. 🚀 First Python Program

The simplest Python program is:

```python
print("Hello, World!")
```

### `print()`

`print()` is used to display information on the screen.

```python
print("Hello")
print("Welcome to Python")
print(100)
```

Output:

```text
Hello
Welcome to Python
100
```

---

# 5. 📝 Comments

Comments are notes written inside the program.

Python ignores comments when executing the program.

## Single-line Comment

Use `#`.

```python
# This is a comment
print("Hello")
```

## Example

```python
name = "Yashu"  # Store the user's name
print(name)
```

---

# 6. 📦 Variables

A variable is a name used to store a value.

```python
name = "Yashu"
age = 20
marks = 85.5
```

Here:

```text
name  → "Yashu"
age   → 20
marks → 85.5
```

### Example

```python
name = "Yashu"
age = 20

print(name)
print(age)
```

Output:

```text
Yashu
20
```

---

## Variable Naming Rules

### ✅ Valid

```python
name = "Yashu"
student_name = "Rahul"
age2 = 20
_marks = 90
```

### ❌ Invalid

```python
2name = "Yashu"
student-name = "Rahul"
class = 10
```

### Important Rules

* Variable names cannot start with a number.
* Variable names can contain letters, numbers and `_`.
* Python is case-sensitive.
* Do not use Python keywords as variable names.

Example:

```python
name = "Yashu"
Name = "Rahul"
```

These are two different variables.

---

# 7. 🔢 Data Types

A data type tells Python what kind of value is stored.

Common Python data types:

```text
int
float
str
bool
list
tuple
set
dict
NoneType
```

---

## 7.1 Integer — `int`

Integers are whole numbers.

```python
age = 20
marks = 95
number = -10
```

Check type:

```python
age = 20

print(type(age))
```

Output:

```text
<class 'int'>
```

---

## 7.2 Float — `float`

Float values contain decimal numbers.

```python
price = 99.50
height = 5.8
temperature = 36.5
```

Example:

```python
price = 99.50

print(type(price))
```

Output:

```text
<class 'float'>
```

---

## 7.3 String — `str`

A string is a sequence of characters.

```python
name = "Yashu"
college = "RIT Hassan"
```

Strings can use:

```python
"Hello"
'Hello'
```

Example:

```python
name = "Yashu"

print(name)
print(type(name))
```

Output:

```text
Yashu
<class 'str'>
```

---

## 7.4 Boolean — `bool`

Boolean values are:

```python
True
False
```

Example:

```python
is_student = True
is_working = False

print(is_student)
print(is_working)
```

Output:

```text
True
False
```

---

# 8. 🔢 Numbers in Python

Python supports different numerical operations.

```python
a = 10
b = 3
```

### Addition

```python
print(a + b)
```

Output:

```text
13
```

### Subtraction

```python
print(a - b)
```

Output:

```text
7
```

### Multiplication

```python
print(a * b)
```

Output:

```text
30
```

### Division

```python
print(a / b)
```

Output:

```text
3.3333333333333335
```

### Floor Division

```python
print(a // b)
```

Output:

```text
3
```

### Modulus

```python
print(a % b)
```

Output:

```text
1
```

### Power

```python
print(a ** b)
```

Output:

```text
1000
```

---

# 9. 🔤 Strings

Strings are used to store text.

```python
name = "Yashu"
```

## String Concatenation

Joining strings together:

```python
first_name = "Yashu"
last_name = "H M"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Yashu H M
```

---

## String Length

Use `len()`.

```python
name = "Python"

print(len(name))
```

Output:

```text
6
```

---

## Accessing Characters

Python uses indexing.

```python
word = "Python"
```

Indexes:

```text
P  y  t  h  o  n
0  1  2  3  4  5
```

Example:

```python
word = "Python"

print(word[0])
print(word[1])
print(word[5])
```

Output:

```text
P
y
n
```

---

## Negative Indexing

```text
P   y   t   h   o   n
-6 -5  -4  -3  -2  -1
```

Example:

```python
word = "Python"

print(word[-1])
```

Output:

```text
n
```

---

## String Slicing

```python
word = "Python"

print(word[0:3])
```

Output:

```text
Pyt
```

General syntax:

```python
string[start:end]
```

The `end` index is not included.

---

# 10. 🟢 Boolean Values

Boolean expressions return either:

```text
True
False
```

Example:

```python
age = 20

print(age > 18)
```

Output:

```text
True
```

Example:

```python
age = 15

print(age >= 18)
```

Output:

```text
False
```

---

# 11. ⌨️ Input and Output

## Output

Use:

```python
print()
```

Example:

```python
print("Welcome")
```

---

## Input

Use:

```python
input()
```

Example:

```python
name = input("Enter your name: ")

print("Hello", name)
```

If the user enters:

```text
Yashu
```

Output:

```text
Hello Yashu
```

---

# 12. 🔄 Type Casting

Type casting means converting one data type into another.

Common functions:

```python
int()
float()
str()
bool()
```

---

## String to Integer

```python
age = "20"

age = int(age)

print(age)
print(type(age))
```

---

## Integer to String

```python
age = 20

age = str(age)

print(type(age))
```

---

## String to Float

```python
price = "99.5"

price = float(price)

print(price)
```

---

# 13. 🧮 Operators

Operators are symbols used to perform operations.

---

## Arithmetic Operators

| Operator | Meaning        | Example   |
| -------- | -------------- | --------- |
| `+`      | Addition       | `10 + 5`  |
| `-`      | Subtraction    | `10 - 5`  |
| `*`      | Multiplication | `10 * 5`  |
| `/`      | Division       | `10 / 5`  |
| `//`     | Floor division | `10 // 3` |
| `%`      | Modulus        | `10 % 3`  |
| `**`     | Power          | `10 ** 2` |

---

# 14. 🔍 Comparison Operators

Comparison operators compare values.

| Operator | Meaning               |
| -------- | --------------------- |
| `==`     | Equal                 |
| `!=`     | Not equal             |
| `>`      | Greater than          |
| `<`      | Less than             |
| `>=`     | Greater than or equal |
| `<=`     | Less than or equal    |

Example:

```python
a = 10
b = 20

print(a == b)
print(a != b)
print(a < b)
print(a > b)
```

Output:

```text
False
True
True
False
```

---

# 15. 🧠 Logical Operators

Python has three main logical operators:

```text
and
or
not
```

## `and`

Both conditions must be true.

```python
age = 20

print(age > 18 and age < 30)
```

Output:

```text
True
```

---

## `or`

At least one condition must be true.

```python
age = 20

print(age < 18 or age > 18)
```

Output:

```text
True
```

---

## `not`

Reverses the result.

```python
is_student = True

print(not is_student)
```

Output:

```text
False
```

---

# 16. 📝 Assignment Operators

Assignment operators are used to assign values.

```python
x = 10
```

Other operators:

```python
x += 5
x -= 2
x *= 3
x /= 2
x //= 2
x %= 2
x **= 2
```

Example:

```python
x = 10

x += 5

print(x)
```

Output:

```text
15
```

---

# 17. 🔎 `type()` Function

`type()` tells us the data type of a value.

```python
name = "Yashu"
age = 20
marks = 85.5
student = True

print(type(name))
print(type(age))
print(type(marks))
print(type(student))
```

---

# 18. 📏 `len()` Function

`len()` returns the number of items/characters.

```python
name = "Python"

print(len(name))
```

Output:

```text
6
```

---

# 19. 🎯 Multiple Variables

Python allows multiple assignments.

```python
name, age, marks = "Yashu", 20, 90
```

Example:

```python
name, age = "Yashu", 20

print(name)
print(age)
```

---

# 20. 🔄 Swapping Variables

Python makes swapping easy.

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

---

# 21. 🧑‍💻 Basic Python Programs

## Program 1 — Add Two Numbers

```python
a = 10
b = 20

sum = a + b

print("Sum =", sum)
```

Output:

```text
Sum = 30
```

---

## Program 2 — Take Two Numbers from User

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum =", a + b)
```

---

## Program 3 — Calculate Area of Rectangle

Formula:

```text
Area = length × width
```

Python:

```python
length = 10
width = 5

area = length * width

print("Area =", area)
```

Output:

```text
Area = 50
```

---

## Program 4 — Calculate Simple Interest

Formula:

```text
SI = (P × R × T) / 100
```

```python
p = 10000
r = 5
t = 2

si = (p * r * t) / 100

print("Simple Interest =", si)
```

Output:

```text
Simple Interest = 1000.0
```

---

## Program 5 — Check Age

```python
age = int(input("Enter your age: "))

print("Age =", age)
```

---

# 22. 💡 Important Beginner Concepts

Remember these:

```text
print()  → Display output
input()  → Take input
type()   → Check data type
len()    → Find length
int()    → Convert to integer
float()  → Convert to float
str()    → Convert to string
bool()   → Convert to boolean
```

---

# 23. ⚠️ Common Beginner Mistakes

### Mistake 1 — Forgetting quotes

❌ Wrong:

```python
name = Yashu
```

✅ Correct:

```python
name = "Yashu"
```

---

### Mistake 2 — Using `=` instead of `==`

`=` means assignment.

```python
age = 20
```

`==` means comparison.

```python
age == 20
```

---

### Mistake 3 — Forgetting type conversion

`input()` normally returns a string.

```python
a = input("Enter number: ")
b = input("Enter number: ")

print(a + b)
```

If the user enters:

```text
10
20
```

The result is:

```text
1020
```

Correct:

```python
a = int(input("Enter number: "))
b = int(input("Enter number: "))

print(a + b)
```

Output:

```text
30
```

---

# 24. 🧪 Practice Questions

Try these without looking at the solution.

### Beginner

1. Print your name.
2. Print your college name.
3. Store your age in a variable and print it.
4. Add two numbers.
5. Subtract two numbers.
6. Multiply two numbers.
7. Divide two numbers.
8. Find the remainder of two numbers.
9. Calculate the area of a circle.
10. Convert Celsius to Fahrenheit.

### Slightly More Practice

11. Take the user's name and print a welcome message.
12. Take two numbers from the user and calculate their sum.
13. Take three numbers and calculate their average.
14. Swap two numbers.
15. Calculate simple interest.
16. Calculate the area of a rectangle.
17. Calculate the perimeter of a rectangle.
18. Convert kilometers to meters.
19. Convert hours to minutes.
20. Find the square and cube of a number.

---

# 25. 🎯 Quick Revision

### Python

```text
Python = Programming Language
```

### Variable

```python
name = "Yashu"
```

### Integer

```python
age = 20
```

### Float

```python
price = 99.5
```

### String

```python
name = "Python"
```

### Boolean

```python
is_student = True
```

### Output

```python
print("Hello")
```

### Input

```python
name = input("Enter name: ")
```

### Type

```python
type(value)
```

### Length

```python
len(value)
```

### Conversion

```python
int()
float()
str()
bool()
```

---

# 🚀 What to Learn Next

After completing these basics, learn:

```text
01. Variables & Data Types       ✅
02. Input & Output               ✅
03. Operators                    ✅
04. Strings                      ✅
05. if / elif / else
06. for loops
07. while loops
08. Lists
09. Tuples
10. Sets
11. Dictionaries
12. Functions
13. Modules
14. File Handling
15. Exception Handling
16. Object-Oriented Programming
17. Advanced Python
18. NumPy
19. Pandas
20. Matplotlib
```

---

## ⭐ Final Tip

Don't just read Python notes.

**Read → Write → Run → Make mistakes → Fix → Practice.**

The fastest way to learn Python is to write code every day.

```python
print("Keep Learning Python 🚀")
```

---

### 🐍 Python Learning Journey

```text
Beginner
   ↓
Python Basics
   ↓
Control Flow
   ↓
Data Structures
   ↓
Functions
   ↓
OOP
   ↓
Advanced Python
   ↓
Libraries
   ↓
Projects
   ↓
Real-World Development 🚀
```

**Happy Coding! 💻🐍**
