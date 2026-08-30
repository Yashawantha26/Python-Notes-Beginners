Absolutely. Since your previous **Notes 6–9** are Python beginner notes, here is a complete **`Notes10.md`** you can copy directly.

# Python Beginners Notes – Notes 10

## 📘 Topic: File Handling in Python

File handling is used to **create, read, write, and modify files** using Python.

Python provides built-in functions to work with files.

---

## 1. Opening a File

The `open()` function is used to open a file.

### Syntax

```python
open("filename", "mode")
```

### Example

```python
file = open("data.txt", "r")
```

Here:

* `data.txt` → File name
* `"r"` → Read mode

---

# 2. File Modes

Python provides different modes for working with files.

| Mode | Meaning         |
| ---- | --------------- |
| `r`  | Read            |
| `w`  | Write           |
| `a`  | Append          |
| `x`  | Create          |
| `r+` | Read and Write  |
| `w+` | Write and Read  |
| `a+` | Append and Read |

---

## 3. Read Mode – `r`

The `r` mode is used to read an existing file.

```python
file = open("data.txt", "r")

content = file.read()

print(content)

file.close()
```

### Important

If the file does not exist, Python gives:

```text
FileNotFoundError
```

---

# 4. `read()`

The `read()` method reads the complete contents of a file.

### Example

Suppose `data.txt` contains:

```text
Hello Python
I am learning programming
```

Program:

```python
file = open("data.txt", "r")

data = file.read()

print(data)

file.close()
```

Output:

```text
Hello Python
I am learning programming
```

---

# 5. Reading a Specific Number of Characters

You can give a number inside `read()`.

```python
file = open("data.txt", "r")

data = file.read(5)

print(data)

file.close()
```

If the file contains:

```text
Python Programming
```

Output:

```text
Pytho
```

---

# 6. `readline()`

The `readline()` method reads **one line at a time**.

```python
file = open("data.txt", "r")

line = file.readline()

print(line)

file.close()
```

---

## 7. Reading Multiple Lines

You can call `readline()` multiple times.

```python
file = open("data.txt", "r")

print(file.readline())
print(file.readline())
print(file.readline())

file.close()
```

Each call reads the next line.

---

# 8. `readlines()`

The `readlines()` method reads all lines and returns them as a list.

```python
file = open("data.txt", "r")

lines = file.readlines()

print(lines)

file.close()
```

Example output:

```python
['Hello Python\n', 'Learning File Handling\n']
```

---

# 9. Using a `for` Loop to Read a File

You can directly loop through a file.

```python
file = open("data.txt", "r")

for line in file:
    print(line)

file.close()
```

This is useful for reading large files line by line.

---

# 10. Write Mode – `w`

The `w` mode is used to write data into a file.

```python
file = open("data.txt", "w")

file.write("Hello Python")

file.close()
```

If the file does not exist, Python creates it.

---

## ⚠️ Important: Write Mode Overwrites Data

Suppose the file contains:

```text
Hello
Welcome to Python
```

Then:

```python
file = open("data.txt", "w")

file.write("New Data")

file.close()
```

The old contents are deleted.

The file now contains:

```text
New Data
```

---

# 11. Writing Multiple Lines

You can use `write()` multiple times.

```python
file = open("data.txt", "w")

file.write("Python\n")
file.write("Java\n")
file.write("C++\n")

file.close()
```

File contents:

```text
Python
Java
C++
```

---

# 12. Append Mode – `a`

The `a` mode adds new content to the **end of the file**.

```python
file = open("data.txt", "a")

file.write("\nJavaScript")

file.close()
```

If the file contains:

```text
Python
Java
```

After running the program:

```text
Python
Java
JavaScript
```

---

# 13. Difference Between `w` and `a`

### Write Mode

```python
file = open("data.txt", "w")
```

Deletes old content and writes new content.

### Append Mode

```python
file = open("data.txt", "a")
```

Keeps old content and adds new content.

### Remember

```text
w → Replace
a → Add
```

---

# 14. Create Mode – `x`

The `x` mode is used to create a new file.

```python
file = open("newfile.txt", "x")

file.write("New file created")

file.close()
```

If the file already exists, Python gives:

```text
FileExistsError
```

---

# 15. Closing a File

After working with a file, it should be closed.

```python
file = open("data.txt", "r")

print(file.read())

file.close()
```

### Why close the file?

Closing a file:

* Releases system resources
* Prevents unnecessary file locks
* Ensures data is properly saved

---

# 16. Using `with open()`

A better way to work with files is using the `with` statement.

```python
with open("data.txt", "r") as file:
    data = file.read()
    print(data)
```

Python automatically closes the file.

### Advantage

You don't need:

```python
file.close()
```

---

# 17. Writing Using `with`

```python
with open("data.txt", "w") as file:
    file.write("Learning Python")
```

---

# 18. Appending Using `with`

```python
with open("data.txt", "a") as file:
    file.write("\nLearning File Handling")
```

---

# 19. Checking if a File Exists

Python's `os` module can be used to check whether a file exists.

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

Output:

```text
File exists
```

---

# 20. Deleting a File

The `os.remove()` function can delete a file.

```python
import os

os.remove("data.txt")
```

### Safer Version

```python
import os

if os.path.exists("data.txt"):
    os.remove("data.txt")
    print("File deleted")
else:
    print("File not found")
```

---

# 21. Creating a Folder

The `os.mkdir()` function creates a folder.

```python
import os

os.mkdir("PythonFiles")
```

---

# 22. Checking if a Folder Exists

```python
import os

if os.path.exists("PythonFiles"):
    print("Folder exists")
else:
    print("Folder does not exist")
```

---

# 23. File Paths

A file can be inside a folder.

Example:

```text
project/
│
├── main.py
└── data/
    └── students.txt
```

You can open the file using:

```python
with open("data/students.txt", "r") as file:
    print(file.read())
```

---

# 24. Absolute Path

An absolute path gives the complete location of a file.

Example:

```python
file = open("C:/Users/User/Documents/data.txt", "r")
```

On Windows, raw strings are useful:

```python
file = open(r"C:\Users\User\Documents\data.txt", "r")
```

---

# 25. File Encoding

You can specify the encoding while opening a file.

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
    print(data)
```

`UTF-8` supports many languages and special characters.

---

# 26. Reading and Writing Text

Example:

```python
with open("student.txt", "w") as file:
    file.write("Name: Yashawantha\n")
    file.write("Course: Computer Science Engineering\n")
    file.write("Language: Python")
```

Reading:

```python
with open("student.txt", "r") as file:
    print(file.read())
```

---

# 27. Simple Student File Program

```python
name = input("Enter your name: ")
course = input("Enter your course: ")

with open("student.txt", "w") as file:
    file.write("Name: " + name + "\n")
    file.write("Course: " + course)

print("Student details saved successfully")
```

---

# 28. Reading Student Details

```python
with open("student.txt", "r") as file:
    data = file.read()

print(data)
```

---

# 29. Simple Notes App

```python
note = input("Enter your note: ")

with open("notes.txt", "a") as file:
    file.write(note + "\n")

print("Note saved successfully")
```

Every new note is added to the file.

---

# 30. Counting Lines in a File

```python
with open("data.txt", "r") as file:
    lines = file.readlines()

print("Number of lines:", len(lines))
```

---

# 31. Counting Words in a File

```python
with open("data.txt", "r") as file:
    data = file.read()

words = data.split()

print("Number of words:", len(words))
```

---

# 32. Counting Characters

```python
with open("data.txt", "r") as file:
    data = file.read()

print("Number of characters:", len(data))
```

---

# 33. Searching for a Word in a File

```python
with open("data.txt", "r") as file:
    data = file.read()

if "Python" in data:
    print("Python found")
else:
    print("Python not found")
```

---

# 34. Exception Handling with Files

Sometimes a file may not exist.

We can handle this using `try-except`.

```python
try:
    with open("data.txt", "r") as file:
        print(file.read())

except FileNotFoundError:
    print("File not found")
```

---

# 35. File Handling Example

```python
try:
    name = input("Enter your name: ")

    with open("user.txt", "w") as file:
        file.write(name)

    print("Data saved successfully")

except Exception as e:
    print("Error:", e)
```

---

# 36. Important File Methods

| Method         | Purpose                   |
| -------------- | ------------------------- |
| `open()`       | Opens a file              |
| `read()`       | Reads complete file       |
| `readline()`   | Reads one line            |
| `readlines()`  | Reads all lines as a list |
| `write()`      | Writes data               |
| `writelines()` | Writes multiple lines     |
| `close()`      | Closes file               |
| `seek()`       | Changes file position     |
| `tell()`       | Returns current position  |

---

# 37. `seek()`

The `seek()` method moves the file pointer.

```python
with open("data.txt", "r") as file:
    print(file.read(5))

    file.seek(0)

    print(file.read())
```

`seek(0)` moves the pointer back to the beginning.

---

# 38. `tell()`

The `tell()` method tells the current position of the file pointer.

```python
with open("data.txt", "r") as file:
    print(file.tell())

    file.read(5)

    print(file.tell())
```

---

# 39. `writelines()`

Used to write multiple strings.

```python
lines = [
    "Python\n",
    "Java\n",
    "C++\n"
]

with open("languages.txt", "w") as file:
    file.writelines(lines)
```

---

# 40. Common Mistakes

### Mistake 1: Forgetting to close a file

```python
file = open("data.txt", "r")
```

Better:

```python
with open("data.txt", "r") as file:
    print(file.read())
```

---

### Mistake 2: Using `w` when you want to add data

Wrong:

```python
open("data.txt", "w")
```

Use:

```python
open("data.txt", "a")
```

when you want to preserve existing content.

---

### Mistake 3: Reading a file that doesn't exist

```python
open("abc.txt", "r")
```

This can cause:

```text
FileNotFoundError
```

Use exception handling when appropriate.

---

# 41. Mini Project – Student Record

```python
name = input("Enter student name: ")
age = input("Enter age: ")
branch = input("Enter branch: ")

with open("student_record.txt", "a") as file:
    file.write("Name: " + name + "\n")
    file.write("Age: " + age + "\n")
    file.write("Branch: " + branch + "\n")
    file.write("--------------------\n")

print("Student record saved!")
```

---

# 42. Practice Questions

## Beginner

### Question 1

Create a file called `hello.txt` and write:

```text
Hello Python
```

---

### Question 2

Read and display the contents of `hello.txt`.

---

### Question 3

Add the following line to the same file:

```text
I am learning Python
```

Use append mode.

---

### Question 4

Create a program that stores your:

* Name
* Age
* College
* Branch

in a file.

---

### Question 5

Write a program to count the number of words in a text file.

---

## Intermediate

### Question 6

Write a program that searches for a word inside a file.

---

### Question 7

Write a program that counts:

* Lines
* Words
* Characters

in a file.

---

### Question 8

Create a simple notes application that allows the user to add notes to a file.

---

### Question 9

Create a student record system using file handling.

---

### Question 10

Handle `FileNotFoundError` while reading a file.

---

# 43. Quick Revision

```text
open()       → Open file
r            → Read
w            → Write / overwrite
a            → Append
x            → Create
read()       → Read all content
readline()   → Read one line
readlines()  → Read all lines
write()      → Write content
writelines() → Write multiple lines
seek()       → Move file pointer
tell()       → Current file position
close()      → Close file
```

---

# ⭐ Key Point

The easiest and safest way to work with files is:

```python
with open("data.txt", "r") as file:
    data = file.read()
    print(data)
```

Python automatically closes the file after the `with` block.

---

# 🎯 Notes 10 Summary

In this lesson, you learned:

* What file handling is
* `open()`
* File modes
* Read mode
* Write mode
* Append mode
* Create mode
* `read()`
* `readline()`
* `readlines()`
* `write()`
* `writelines()`
* `with open()`
* File paths
* File encoding
* Creating folders
* Deleting files
* `seek()`
* `tell()`
* Exception handling
* File handling mini projects

**Next:** Notes 11 → **Python Modules & Packages**
