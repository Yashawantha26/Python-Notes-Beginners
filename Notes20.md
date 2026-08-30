Here is your complete **`Notes20.md`**, continuing the Python Beginners Notes series.

# Python Beginners Notes – Notes 20

# 📁 Python File Handling

In this lesson, we will learn:

* What is file handling?
* Opening files
* File modes
* Reading files
* Writing files
* Appending files
* `with open()`
* `read()`
* `readline()`
* `readlines()`
* `write()`
* `writelines()`
* File positions
* `seek()`
* `tell()`
* Closing files
* Working with directories
* `os`
* `pathlib`
* Text files
* CSV files
* JSON files
* Exception handling with files
* Practical examples
* Mini projects
* Interview questions

---

# 1. What is File Handling?

**File handling** means creating, reading, writing, updating, and deleting files using a program.

Python can work with files such as:

```text
.txt
.csv
.json
```

Example:

```text
student.txt
marks.csv
data.json
```

---

# 2. Why File Handling?

Variables store data temporarily.

Example:

```python
name = "Yashu"
```

When the program stops, the variable is normally lost.

Files allow us to store data permanently.

Example:

```text
student.txt
```

Data can remain in the file after the program ends.

---

# 3. Basic File Handling Steps

Usually, file handling involves:

```text
1. Open the file
2. Read/write the file
3. Close the file
```

Example:

```python
file = open("data.txt", "r")

content = file.read()

print(content)

file.close()
```

---

# 4. `open()`

Python provides the `open()` function.

Syntax:

```python
open(filename, mode)
```

Example:

```python
file = open("data.txt", "r")
```

---

# 5. File Modes

Common file modes are:

| Mode | Meaning        |
| ---- | -------------- |
| `r`  | Read           |
| `w`  | Write          |
| `a`  | Append         |
| `x`  | Create         |
| `b`  | Binary         |
| `t`  | Text           |
| `+`  | Read and write |

---

# 6. Read Mode – `r`

Use `r` to read an existing file.

```python
file = open("data.txt", "r")

content = file.read()

print(content)

file.close()
```

If the file does not exist, Python raises:

```text
FileNotFoundError
```

---

# 7. Write Mode – `w`

Use `w` to write data.

```python
file = open("data.txt", "w")

file.write("Hello Python")

file.close()
```

If the file does not exist, Python normally creates it.

If the file already exists, its previous contents are replaced.

---

# 8. Append Mode – `a`

Use `a` to add data at the end of a file.

```python
file = open("data.txt", "a")

file.write("\nWelcome to Python")

file.close()
```

Existing content is preserved.

---

# 9. Create Mode – `x`

Use `x` to create a new file.

```python
file = open("newfile.txt", "x")

file.write("New file created")

file.close()
```

If the file already exists, Python raises:

```text
FileExistsError
```

---

# 10. Text Mode – `t`

Text mode is the default.

```python
file = open("data.txt", "rt")
```

This is equivalent to:

```python
file = open("data.txt", "r")
```

---

# 11. Binary Mode – `b`

Binary mode is used for binary data such as:

```text
Images
Audio
Videos
PDF files
Other binary files
```

Example:

```python
file = open("image.jpg", "rb")

data = file.read()

file.close()
```

---

# 12. Read and Write – `+`

You can combine reading and writing.

Example:

```python
file = open("data.txt", "r+")

content = file.read()

file.write("New data")

file.close()
```

Be careful with the current file position when using `+`.

---

# 13. Common File Modes

```text
r
→ Read

w
→ Write and overwrite

a
→ Append

x
→ Create new file

r+
→ Read and write

w+
→ Write and read, truncating existing content

a+
→ Append and read
```

Binary versions can be created by adding `b`:

```text
rb
wb
ab
```

---

# 14. Reading a Complete File

Suppose `data.txt` contains:

```text
Python
Java
C++
JavaScript
```

Python:

```python
file = open("data.txt", "r")

content = file.read()

print(content)

file.close()
```

Output:

```text
Python
Java
C++
JavaScript
```

---

# 15. `read()`

`read()` reads the contents of a file.

```python
file = open("data.txt", "r")

content = file.read()

print(content)

file.close()
```

---

# 16. Reading a Specific Number of Characters

You can provide a size.

```python
file = open("data.txt", "r")

content = file.read(5)

print(content)

file.close()
```

If the file begins with:

```text
Python
```

output:

```text
Pytho
```

---

# 17. `readline()`

`readline()` reads one line at a time.

```python
file = open("data.txt", "r")

line = file.readline()

print(line)

file.close()
```

---

# 18. Reading Multiple Lines

```python
file = open("data.txt", "r")

print(file.readline())
print(file.readline())
print(file.readline())

file.close()
```

Each call advances the file position.

---

# 19. `readlines()`

`readlines()` reads all lines and returns them as a list.

```python
file = open("data.txt", "r")

lines = file.readlines()

print(lines)

file.close()
```

Example result:

```python
['Python\n', 'Java\n', 'C++\n']
```

---

# 20. Reading Using a Loop

A very common approach is:

```python
file = open("data.txt", "r")

for line in file:
    print(line.strip())

file.close()
```

This processes the file line by line.

---

# 21. `strip()`

When reading text files, lines often contain a newline character:

```text
\n
```

You can remove surrounding whitespace with:

```python
line.strip()
```

Example:

```python
line = "Python\n"

print(line.strip())
```

Output:

```text
Python
```

---

# 22. Writing to a File

Example:

```python
file = open("student.txt", "w")

file.write("Name: Yashu\n")
file.write("Course: CSE\n")
file.write("Marks: 85\n")

file.close()
```

File contents:

```text
Name: Yashu
Course: CSE
Marks: 85
```

---

# 23. `write()`

The `write()` method writes a string to a file.

```python
file.write("Hello")
```

It returns the number of characters written.

Example:

```python
file = open("data.txt", "w")

count = file.write("Hello")

print(count)

file.close()
```

Output:

```text
5
```

---

# 24. Writing Multiple Lines

```python
file = open("data.txt", "w")

file.write("Python\n")
file.write("Java\n")
file.write("C++\n")

file.close()
```

---

# 25. `writelines()`

`writelines()` writes multiple strings.

```python
lines = [
    "Python\n",
    "Java\n",
    "C++\n"
]

file = open("data.txt", "w")

file.writelines(lines)

file.close()
```

Important:

`writelines()` does **not** automatically add newline characters.

You must include `\n` when needed.

---

# 26. Appending Data

Use `a` mode.

```python
file = open("data.txt", "a")

file.write("\nJavaScript")

file.close()
```

The new data is added at the end.

---

# 27. Difference Between `w` and `a`

### `w`

```python
open("data.txt", "w")
```

Existing content is replaced.

### `a`

```python
open("data.txt", "a")
```

Existing content is preserved and new content is added at the end.

---

# 28. Why Close a File?

After working with a file, close it:

```python
file.close()
```

Closing a file:

* Releases system resources
* Flushes buffered data
* Prevents accidental further operations

---

# 29. Checking if a File is Closed

```python
file = open("data.txt", "r")

print(file.closed)

file.close()

print(file.closed)
```

Output:

```text
False
True
```

---

# 30. `with open()`

The recommended approach is:

```python
with open("data.txt", "r") as file:
    content = file.read()
    print(content)
```

Python automatically closes the file when the `with` block ends.

---

# 31. Why Use `with`?

Instead of:

```python
file = open("data.txt", "r")

content = file.read()

file.close()
```

prefer:

```python
with open("data.txt", "r") as file:
    content = file.read()
```

Advantages:

* Cleaner code
* Automatic cleanup
* Safer resource management
* File closes even when leaving the block normally

---

# 32. Reading with `with`

```python
with open("data.txt", "r") as file:
    print(file.read())
```

---

# 33. Writing with `with`

```python
with open("data.txt", "w") as file:
    file.write("Hello Python")
```

---

# 34. Appending with `with`

```python
with open("data.txt", "a") as file:
    file.write("\nNew line")
```

---

# 35. File Encoding

You can specify the encoding.

Example:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

For writing:

```python
with open("data.txt", "w", encoding="utf-8") as file:
    file.write("Hello")
```

Using an explicit encoding such as UTF-8 is often a good practice when portability matters.

---

# 36. Writing Unicode Text

```python
with open("data.txt", "w", encoding="utf-8") as file:
    file.write("Hello नमस्ते ಕನ್ನಡ")
```

UTF-8 can store a wide range of Unicode characters.

---

# 37. File Pointer

When a file is opened, Python maintains a current position called the **file pointer**.

Example:

```python
with open("data.txt", "r") as file:
    print(file.read(5))
    print(file.read(5))
```

The second `read()` continues from where the first one stopped.

---

# 38. `tell()`

`tell()` returns the current file position.

```python
with open("data.txt", "r") as file:
    print(file.tell())

    file.read(5)

    print(file.tell())
```

---

# 39. `seek()`

`seek()` moves the file pointer.

```python
with open("data.txt", "r") as file:

    print(file.read(5))

    file.seek(0)

    print(file.read(5))
```

The second read starts from the beginning.

---

# 40. Example of `seek()`

Suppose:

```text
Python Programming
```

Code:

```python
with open("data.txt", "r") as file:

    print(file.read(6))

    file.seek(0)

    print(file.read(6))
```

Output:

```text
Python
Python
```

---

# 41. File Paths

A file can be located using:

```text
Relative path
Absolute path
```

---

# 42. Relative Path

Example:

```python
open("data.txt")
```

This refers to a path relative to the program's current working directory.

Another example:

```python
open("data/data.txt")
```

---

# 43. Absolute Path

An absolute path specifies the complete location.

Windows example:

```python
open(r"C:\Users\User\Documents\data.txt")
```

Using a raw string:

```python
r"C:\Users\User\Documents\data.txt"
```

helps avoid backslash escape issues.

---

# 44. Pathlib

Python provides the `pathlib` module for working with paths.

```python
from pathlib import Path

path = Path("data.txt")

print(path.exists())
```

---

# 45. Check File Exists

Using `pathlib`:

```python
from pathlib import Path

path = Path("data.txt")

if path.exists():
    print("File exists")
else:
    print("File not found")
```

---

# 46. Create a File with `Path`

```python
from pathlib import Path

path = Path("data.txt")

path.write_text("Hello Python", encoding="utf-8")
```

---

# 47. Read a File with `Path`

```python
from pathlib import Path

path = Path("data.txt")

content = path.read_text(encoding="utf-8")

print(content)
```

---

# 48. Get File Name

```python
from pathlib import Path

path = Path("folder/data.txt")

print(path.name)
```

Output:

```text
data.txt
```

---

# 49. Get File Extension

```python
from pathlib import Path

path = Path("data.txt")

print(path.suffix)
```

Output:

```text
.txt
```

---

# 50. Get File Stem

```python
from pathlib import Path

path = Path("data.txt")

print(path.stem)
```

Output:

```text
data
```

---

# 51. Create Directory Using `pathlib`

```python
from pathlib import Path

folder = Path("students")

folder.mkdir(exist_ok=True)
```

`exist_ok=True` prevents an error if the directory already exists.

---

# 52. Create Nested Directories

```python
from pathlib import Path

folder = Path("project/data/students")

folder.mkdir(parents=True, exist_ok=True)
```

---

# 53. List Files Using `pathlib`

```python
from pathlib import Path

folder = Path(".")

for item in folder.iterdir():
    print(item)
```

---

# 54. Find Python Files

```python
from pathlib import Path

folder = Path(".")

for file in folder.glob("*.py"):
    print(file)
```

---

# 55. Find Text Files

```python
from pathlib import Path

for file in Path(".").glob("*.txt"):
    print(file)
```

---

# 56. Recursive Search

Use `rglob()`:

```python
from pathlib import Path

for file in Path(".").rglob("*.py"):
    print(file)
```

This searches through subdirectories too.

---

# 57. Delete a File

Using `Path.unlink()`:

```python
from pathlib import Path

path = Path("data.txt")

if path.exists():
    path.unlink()
```

Be careful: deleting a file is destructive.

---

# 58. Working with `os`

The `os` module can also work with files and directories.

```python
import os

print(os.getcwd())
```

This displays the current working directory.

---

# 59. List Directory Contents

```python
import os

print(os.listdir())
```

---

# 60. Create Directory

```python
import os

os.mkdir("students")
```

---

# 61. Check if Path Exists

```python
import os

if os.path.exists("data.txt"):
    print("Exists")
```

---

# 62. Check File or Directory

```python
import os

if os.path.isfile("data.txt"):
    print("It is a file")

if os.path.isdir("students"):
    print("It is a directory")
```

---

# 63. Rename a File

Using `os`:

```python
import os

os.rename("old.txt", "new.txt")
```

Using `pathlib`:

```python
from pathlib import Path

Path("old.txt").rename("new.txt")
```

---

# 64. Delete a File with `os`

```python
import os

if os.path.exists("data.txt"):
    os.remove("data.txt")
```

---

# 65. Text Files

Text files store human-readable characters.

Examples:

```text
.txt
.csv
.json
.html
.py
```

Example:

```python
with open("message.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python")
```

---

# 66. CSV Files

CSV means:

**Comma-Separated Values**

Example:

```text
Name,Course,Marks
Yashu,CSE,85
Rahul,CSE,78
Arun,CSE,90
```

CSV is commonly used for tabular data.

---

# 67. Writing CSV Using `csv`

Python provides the `csv` module.

```python
import csv

with open("students.csv", "w", newline="", encoding="utf-8") as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Course", "Marks"])
    writer.writerow(["Yashu", "CSE", 85])
    writer.writerow(["Rahul", "CSE", 78])
```

---

# 68. Reading CSV

```python
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:

    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output:

```text
['Name', 'Course', 'Marks']
['Yashu', 'CSE', '85']
['Rahul', 'CSE', '78']
```

---

# 69. CSV with Dictionary

```python
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:

    reader = csv.DictReader(file)

    for row in reader:
        print(row["Name"], row["Marks"])
```

---

# 70. Writing CSV with Dictionary

```python
import csv

students = [
    {"Name": "Yashu", "Course": "CSE", "Marks": 85},
    {"Name": "Rahul", "Course": "CSE", "Marks": 78}
]

with open("students.csv", "w", newline="", encoding="utf-8") as file:

    fieldnames = ["Name", "Course", "Marks"]

    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerows(students)
```

---

# 71. JSON Files

JSON means:

**JavaScript Object Notation**

JSON is commonly used for structured data and APIs.

Example:

```json
{
    "name": "Yashu",
    "course": "CSE",
    "marks": 85
}
```

---

# 72. Writing JSON

```python
import json

student = {
    "name": "Yashu",
    "course": "CSE",
    "marks": 85
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file, indent=4)
```

---

# 73. Reading JSON

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    student = json.load(file)

print(student)
```

Output:

```text
{'name': 'Yashu', 'course': 'CSE', 'marks': 85}
```

---

# 74. Access JSON Values

```python
print(student["name"])
print(student["course"])
print(student["marks"])
```

Output:

```text
Yashu
CSE
85
```

---

# 75. JSON List

JSON can contain arrays.

Example:

```json
{
    "students": [
        {
            "name": "Yashu",
            "marks": 85
        },
        {
            "name": "Rahul",
            "marks": 78
        }
    ]
}
```

Python:

```python
import json

data = {
    "students": [
        {"name": "Yashu", "marks": 85},
        {"name": "Rahul", "marks": 78}
    ]
}

with open("students.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

---

# 76. Exception Handling with Files

File operations can produce errors.

Example:

```python
try:

    with open("data.txt", "r", encoding="utf-8") as file:
        content = file.read()

    print(content)

except FileNotFoundError:
    print("File not found")
```

---

# 77. Handling Permission Error

```python
try:

    with open("data.txt", "r", encoding="utf-8") as file:
        print(file.read())

except FileNotFoundError:
    print("File does not exist")

except PermissionError:
    print("Permission denied")
```

---

# 78. Generic File Error

You can handle:

```python
except OSError as error:
    print("File operation failed:", error)
```

`OSError` covers many operating-system-related file errors.

---

# 79. Example – Student Records

Create:

```text
students.txt
```

Python:

```python
students = [
    "Yashu - CSE - 85\n",
    "Rahul - CSE - 78\n",
    "Arun - CSE - 90\n"
]

with open("students.txt", "w", encoding="utf-8") as file:
    file.writelines(students)
```

---

# 80. Reading Student Records

```python
with open("students.txt", "r", encoding="utf-8") as file:

    for line in file:
        print(line.strip())
```

Output:

```text
Yashu - CSE - 85
Rahul - CSE - 78
Arun - CSE - 90
```

---

# 81. Count Lines in a File

```python
count = 0

with open("data.txt", "r", encoding="utf-8") as file:

    for line in file:
        count += 1

print("Lines:", count)
```

---

# 82. Count Words in a File

```python
count = 0

with open("data.txt", "r", encoding="utf-8") as file:

    for line in file:
        count += len(line.split())

print("Words:", count)
```

---

# 83. Count Characters

```python
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()

print("Characters:", len(content))
```

---

# 84. Search for a Word

```python
word = "Python"

with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()

if word in content:
    print("Word found")
else:
    print("Word not found")
```

---

# 85. Count Occurrences of a Word

```python
word = "Python"

with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()

count = content.count(word)

print("Occurrences:", count)
```

---

# 86. Copy File Contents

```python
with open("source.txt", "r", encoding="utf-8") as source:
    content = source.read()

with open("destination.txt", "w", encoding="utf-8") as destination:
    destination.write(content)
```

---

# 87. Copy a File Using `shutil`

Python also provides `shutil`.

```python
import shutil

shutil.copyfile("source.txt", "destination.txt")
```

---

# 88. File Extension Checker

```python
from pathlib import Path

filename = Path("document.pdf")

print(filename.suffix)
```

Output:

```text
.pdf
```

---

# 89. Practical Program – Notes Saver

```python
note = input("Enter your note: ")

with open("notes.txt", "a", encoding="utf-8") as file:
    file.write(note + "\n")

print("Note saved successfully!")
```

---

# 90. Practical Program – Read Notes

```python
from pathlib import Path

path = Path("notes.txt")

if path.exists():

    content = path.read_text(encoding="utf-8")

    print("\nYour Notes:")
    print(content)

else:
    print("No notes found.")
```

---

# 91. Practical Program – Student File

```python
name = input("Enter name: ")
course = input("Enter course: ")
marks = input("Enter marks: ")

with open("student.txt", "w", encoding="utf-8") as file:

    file.write(f"Name: {name}\n")
    file.write(f"Course: {course}\n")
    file.write(f"Marks: {marks}\n")

print("Student details saved.")
```

---

# 92. Practical Program – Student CSV

```python
import csv

name = input("Enter name: ")
course = input("Enter course: ")
marks = input("Enter marks: ")

with open("students.csv", "a", newline="", encoding="utf-8") as file:

    writer = csv.writer(file)

    writer.writerow([name, course, marks])

print("Student added successfully.")
```

---

# 93. Practical Program – JSON Student

```python
import json

student = {
    "name": input("Enter name: "),
    "course": input("Enter course: "),
    "marks": int(input("Enter marks: "))
}

with open("student.json", "w", encoding="utf-8") as file:

    json.dump(student, file, indent=4)

print("Student saved successfully.")
```

---

# 94. Practical Program – Simple Log File

```python
from datetime import datetime

message = input("Enter log message: ")

with open("app.log", "a", encoding="utf-8") as file:

    timestamp = datetime.now()

    file.write(f"{timestamp} - {message}\n")
```

---

# 95. Mini Project – To-Do List

Create a file:

```text
todo.txt
```

Program:

```python
while True:

    print("\n1. Add Task")
    print("2. View Tasks")
    print("3. Exit")

    choice = input("Choose: ")

    if choice == "1":

        task = input("Enter task: ")

        with open("todo.txt", "a", encoding="utf-8") as file:
            file.write(task + "\n")

        print("Task added.")

    elif choice == "2":

        try:
            with open("todo.txt", "r", encoding="utf-8") as file:

                tasks = file.readlines()

                if not tasks:
                    print("No tasks.")

                for index, task in enumerate(tasks, start=1):
                    print(index, task.strip())

        except FileNotFoundError:
            print("No tasks found.")

    elif choice == "3":

        print("Goodbye!")
        break

    else:
        print("Invalid choice.")
```

---

# 96. Mini Project – Student Record System

Requirements:

```text
1. Add student
2. View students
3. Search student
4. Exit
```

Store data in:

```text
students.csv
```

Example implementation:

```python
import csv
from pathlib import Path

FILE = Path("students.csv")


def add_student():

    name = input("Name: ")
    course = input("Course: ")
    marks = input("Marks: ")

    file_exists = FILE.exists()

    with FILE.open("a", newline="", encoding="utf-8") as file:

        writer = csv.writer(file)

        if not file_exists:
            writer.writerow(["Name", "Course", "Marks"])

        writer.writerow([name, course, marks])

    print("Student added.")


def view_students():

    if not FILE.exists():
        print("No records found.")
        return

    with FILE.open("r", newline="", encoding="utf-8") as file:

        reader = csv.DictReader(file)

        for student in reader:
            print(
                student["Name"],
                student["Course"],
                student["Marks"]
            )


def search_student():

    search_name = input("Enter name: ").lower()

    if not FILE.exists():
        print("No records found.")
        return

    found = False

    with FILE.open("r", newline="", encoding="utf-8") as file:

        reader = csv.DictReader(file)

        for student in reader:

            if student["Name"].lower() == search_name:

                print(student)
                found = True

    if not found:
        print("Student not found.")


while True:

    print("\n1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Exit")

    choice = input("Choose: ")

    if choice == "1":
        add_student()

    elif choice == "2":
        view_students()

    elif choice == "3":
        search_student()

    elif choice == "4":
        break

    else:
        print("Invalid choice.")
```

---

# 97. File Handling Best Practices

### 1. Prefer `with open()`

Good:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

---

### 2. Specify encoding for text files

```python
encoding="utf-8"
```

This makes the intended text encoding explicit.

---

### 3. Use the correct mode

Read:

```text
r
```

Write:

```text
w
```

Append:

```text
a
```

---

### 4. Be careful with `w`

This:

```python
open("data.txt", "w")
```

can replace existing contents.

---

### 5. Validate file existence

Using `pathlib`:

```python
from pathlib import Path

path = Path("data.txt")

if path.exists():
    print("File exists")
```

---

### 6. Handle expected errors

```python
try:
    with open("data.txt", encoding="utf-8") as file:
        print(file.read())

except FileNotFoundError:
    print("File not found.")
```

---

# 98. Common Mistakes

## Mistake 1 – Forgetting to close

Less ideal:

```python
file = open("data.txt")
data = file.read()
```

Better:

```python
with open("data.txt", encoding="utf-8") as file:
    data = file.read()
```

---

## Mistake 2 – Using `w` accidentally

```python
open("data.txt", "w")
```

may erase previous content.

If you want to add data:

```python
open("data.txt", "a")
```

---

## Mistake 3 – Reading a missing file

```python
with open("unknown.txt", "r") as file:
    print(file.read())
```

can raise:

```text
FileNotFoundError
```

---

## Mistake 4 – Incorrect Windows path

Potentially problematic:

```python
"C:\new\data.txt"
```

because backslashes can introduce escape sequences.

Better:

```python
r"C:\new\data.txt"
```

or:

```python
"C:\\new\\data.txt"
```

or use:

```python
from pathlib import Path

path = Path("C:/new/data.txt")
```

---

## Mistake 5 – Forgetting newline

This:

```python
file.write("Python")
file.write("Java")
```

may produce:

```text
PythonJava
```

Instead:

```python
file.write("Python\n")
file.write("Java\n")
```

---

# 99. Important Methods Cheat Sheet

```text
open()
→ Open a file

read()
→ Read content

readline()
→ Read one line

readlines()
→ Read all lines as a list

write()
→ Write a string

writelines()
→ Write multiple strings

close()
→ Close file

tell()
→ Get current position

seek()
→ Change current position
```

---

# 100. File Modes Cheat Sheet

```text
r
→ Read

w
→ Write / overwrite

a
→ Append

x
→ Create new file

r+
→ Read + write

w+
→ Write + read / truncate

a+
→ Append + read

rb
→ Read binary

wb
→ Write binary

ab
→ Append binary
```

---

# 101. `os` Cheat Sheet

```python
import os
```

Current directory:

```python
os.getcwd()
```

List directory:

```python
os.listdir()
```

Create directory:

```python
os.mkdir("folder")
```

Check existence:

```python
os.path.exists("file.txt")
```

Check file:

```python
os.path.isfile("file.txt")
```

Check directory:

```python
os.path.isdir("folder")
```

Rename:

```python
os.rename("old.txt", "new.txt")
```

Delete:

```python
os.remove("file.txt")
```

---

# 102. `pathlib` Cheat Sheet

```python
from pathlib import Path
```

Create path:

```python
Path("data.txt")
```

Check existence:

```python
path.exists()
```

Read:

```python
path.read_text(encoding="utf-8")
```

Write:

```python
path.write_text("Hello", encoding="utf-8")
```

File name:

```python
path.name
```

Extension:

```python
path.suffix
```

Stem:

```python
path.stem
```

Create directory:

```python
path.mkdir()
```

Delete file:

```python
path.unlink()
```

---

# 103. Important Differences

## `read()` vs `readline()`

```text
read()
→ Reads content

readline()
→ Reads one line
```

---

## `readline()` vs `readlines()`

```text
readline()
→ One line

readlines()
→ List of lines
```

---

## `write()` vs `writelines()`

```text
write()
→ Writes one string

writelines()
→ Writes multiple strings
```

---

## `w` vs `a`

```text
w
→ Replace existing content

a
→ Add to existing content
```

---

## `os` vs `pathlib`

Both can work with files and directories.

For new code, `pathlib` is often easier to read because it provides an object-oriented path API.

---

# 104. Interview Questions

## Q1. What is file handling?

File handling is the process of reading, writing, creating, updating, and managing files using a program.

---

## Q2. How do you open a file?

```python
file = open("data.txt", "r")
```

---

## Q3. What is the default mode of `open()`?

The default mode is:

```text
r
```

which means read text.

---

## Q4. What does `w` mode do?

It opens a file for writing and truncates existing contents.

---

## Q5. What does `a` mode do?

It opens a file for appending data at the end.

---

## Q6. What does `x` mode do?

It creates a new file and raises an error if the file already exists.

---

## Q7. What is `with open()`?

It is a context-manager pattern that automatically handles closing the file when the block is exited.

---

## Q8. What is `read()`?

It reads file content and returns it as a string in text mode.

---

## Q9. What is `readline()`?

It reads the next line from a file.

---

## Q10. What is `readlines()`?

It reads lines and returns them as a list.

---

## Q11. What is `write()`?

It writes a string to a file.

---

## Q12. What is `writelines()`?

It writes multiple strings to a file.

It does not automatically insert separators such as newlines.

---

## Q13. What is `seek()`?

It changes the current file position.

---

## Q14. What is `tell()`?

It returns the current file position.

---

## Q15. What is `FileNotFoundError`?

It is raised when a requested file cannot be found.

---

## Q16. What is `pathlib`?

`pathlib` is a standard-library module that provides an object-oriented interface for filesystem paths.

---

## Q17. What is CSV?

CSV stands for:

```text
Comma-Separated Values
```

It is commonly used to represent tabular data.

---

## Q18. What is JSON?

JSON stands for:

```text
JavaScript Object Notation
```

It is a text format commonly used for structured data exchange.

---

# 105. Practice Questions

### Question 1

Create a file called:

```text
hello.txt
```

and write:

```text
Hello Python
```

---

### Question 2

Read the contents of:

```text
hello.txt
```

and print them.

---

### Question 3

Append:

```text
Python is easy to learn.
```

to the same file.

---

### Question 4

Count the number of lines in a text file.

---

### Question 5

Count the number of words in a text file.

---

### Question 6

Count the number of characters in a text file.

---

### Question 7

Search for a particular word in a file.

---

### Question 8

Create a CSV file containing:

```text
Name
Course
Marks
```

for five students.

---

### Question 9

Read the CSV file and print every student.

---

### Question 10

Create a JSON file containing:

```text
Name
Age
Course
Skills
```

---

### Question 11

Read the JSON file and print the student's name and skills.

---

### Question 12

Create a program that copies one text file into another.

---

### Question 13

Create a program that finds all `.py` files in the current directory.

---

### Question 14

Create a program that checks whether a given file exists.

---

### Question 15

Create a simple To-Do List using a text file.

---

# 106. Mini Project Ideas

Practice these projects:

```text
1. To-Do List
2. Student Record System
3. Contact Book
4. Notes Manager
5. Expense Tracker
6. Simple Log System
7. Password Manager
8. Quiz Score Saver
9. Attendance Tracker
10. Book Record System
```

For beginner projects, start with `.txt`, `.csv`, and `.json` files before moving to databases.

---

# 107. Final Revision

Remember:

```text
File Handling
      ↓
open()
      ↓
Read / Write / Append
      ↓
read()
readline()
readlines()
write()
writelines()
      ↓
with open()
      ↓
pathlib / os
      ↓
CSV / JSON
      ↓
Exception Handling
```

---

# 🎯 Notes 20 Summary

In this lesson, you learned:

* File handling
* `open()`
* File modes
* `r`
* `w`
* `a`
* `x`
* `b`
* `t`
* `+`
* `read()`
* `readline()`
* `readlines()`
* `write()`
* `writelines()`
* `close()`
* `with open()`
* Encoding
* File pointer
* `tell()`
* `seek()`
* Relative paths
* Absolute paths
* `pathlib`
* `os`
* Creating directories
* Deleting files
* CSV files
* JSON files
* Exception handling
* `FileNotFoundError`
* `PermissionError`
* `OSError`
* Practical file programs
* Student record system
* To-Do List
* File-handling best practices

---

# 🚀 Next Lesson

## Notes 21 → Python Exception Handling

You will learn:

```text
What is an exception?
Syntax errors
Runtime errors
Exceptions
try
except
else
finally
raise
Custom exceptions
Exception hierarchy
Multiple exceptions
Exception messages
User input validation
File-related exceptions
Debugging
Best practices
Practical programs
Mini projects
Interview questions
```
