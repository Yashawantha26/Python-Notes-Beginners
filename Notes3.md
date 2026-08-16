# 🐍 Python Notes 3 — Strings

> A complete beginner-friendly guide to Python strings with examples, methods, slicing, formatting, and practice.

---

## 📌 Table of Contents

1. What is a String?
2. Creating Strings
3. Single and Double Quotes
4. Multiline Strings
5. String Indexing
6. Negative Indexing
7. String Slicing
8. String Length
9. String Concatenation
10. String Repetition
11. Membership Operators
12. String Comparison
13. Changing Case
14. Removing Spaces
15. Searching in Strings
16. Replacing Text
17. Splitting Strings
18. Joining Strings
19. Checking String Content
20. Escape Characters
21. String Formatting
22. f-Strings
23. Useful String Methods
24. Common String Programs
25. Practice Questions
26. Quick Revision

---

# 1. 🔤 What is a String?

A **string** is a sequence of characters used to store text.

Examples:

```python
name = "Yashu"
city = "Hassan"
message = "Welcome to Python"
```

Strings can contain:

* Letters
* Numbers
* Spaces
* Symbols
* Special characters

Example:

```python
text = "Python 3.12!"
```

---

# 2. 📝 Creating Strings

Strings can be created using quotes.

### Double Quotes

```python
name = "Yashu"
```

### Single Quotes

```python
name = 'Yashu'
```

Both are valid.

```python
a = "Hello"
b = 'Hello'

print(a)
print(b)
```

Output:

```text
Hello
Hello
```

---

# 3. 📚 Multiline Strings

Triple quotes can be used for multiple lines.

```python
message = """Hello
Welcome to Python
Keep Learning!"""

print(message)
```

Output:

```text
Hello
Welcome to Python
Keep Learning!
```

You can also use:

```python
message = '''Hello
Python
World'''
```

---

# 4. 🔢 String Indexing

Each character has a position called an **index**.

Example:

```python
word = "Python"
```

Index positions:

```text
 P   y   t   h   o   n
 0   1   2   3   4   5
```

Access characters:

```python
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

# 5. 🔙 Negative Indexing

Python also supports negative indexes.

```text
 P   y   t   h   o   n
-6  -5  -4  -3  -2  -1
```

Example:

```python
word = "Python"

print(word[-1])
print(word[-2])
```

Output:

```text
n
o
```

---

# 6. ✂️ String Slicing

Slicing is used to get a part of a string.

### Syntax

```python
string[start:end]
```

Example:

```python
word = "Python"

print(word[0:3])
```

Output:

```text
Pyt
```

Remember:

> The ending index is not included.

---

## More Examples

```python
word = "Python"

print(word[1:4])
print(word[2:6])
print(word[:3])
print(word[3:])
```

Output:

```text
yth
thon
Pyt
hon
```

---

# 7. 🔄 Slicing with Step

Syntax:

```python
string[start:end:step]
```

Example:

```python
word = "Python"

print(word[0:6:2])
```

Output:

```text
Pto
```

Because it takes every second character.

---

# 8. 🔙 Reverse a String

The easiest way:

```python
word = "Python"

print(word[::-1])
```

Output:

```text
nohtyP
```

Explanation:

```text
start = omitted
end   = omitted
step  = -1
```

So Python moves backwards.

---

# 9. 📏 String Length

Use `len()`.

```python
word = "Python"

print(len(word))
```

Output:

```text
6
```

Spaces are also counted.

```python
text = "Hello World"

print(len(text))
```

Output:

```text
11
```

---

# 10. ➕ String Concatenation

Concatenation means joining strings.

Use `+`.

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

# 11. ✖️ String Repetition

Use `*` to repeat a string.

```python
print("Hi " * 3)
```

Output:

```text
Hi Hi Hi
```

Another example:

```python
print("*" * 10)
```

Output:

```text
**********
```

---

# 12. 🔍 Membership Operators

Use:

```text
in
not in
```

### `in`

```python
text = "Python Programming"

print("Python" in text)
```

Output:

```text
True
```

### `not in`

```python
text = "Python Programming"

print("Java" not in text)
```

Output:

```text
True
```

---

# 13. ⚖️ Comparing Strings

Strings can be compared.

```python
a = "apple"
b = "apple"

print(a == b)
```

Output:

```text
True
```

Example:

```python
a = "Python"
b = "Java"

print(a == b)
print(a != b)
```

Output:

```text
False
True
```

---

# 14. 🔠 Change Case

Python provides several methods for changing letter case.

---

## `upper()`

Converts to uppercase.

```python
name = "yashu"

print(name.upper())
```

Output:

```text
YASHU
```

---

## `lower()`

Converts to lowercase.

```python
name = "YASHU"

print(name.lower())
```

Output:

```text
yashu
```

---

## `capitalize()`

Makes the first character uppercase.

```python
text = "python programming"

print(text.capitalize())
```

Output:

```text
Python programming
```

---

## `title()`

Makes the first character of each word uppercase.

```python
text = "python programming language"

print(text.title())
```

Output:

```text
Python Programming Language
```

---

## `swapcase()`

Changes uppercase to lowercase and lowercase to uppercase.

```python
text = "PyThOn"

print(text.swapcase())
```

Output:

```text
pYtHoN
```

---

# 15. 🧹 Removing Spaces

## `strip()`

Removes spaces from both sides.

```python
text = "   Python   "

print(text.strip())
```

Output:

```text
Python
```

---

## `lstrip()`

Removes spaces from the left.

```python
text = "   Python"

print(text.lstrip())
```

---

## `rstrip()`

Removes spaces from the right.

```python
text = "Python   "

print(text.rstrip())
```

---

# 16. 🔎 Searching in Strings

## `find()`

Returns the position of the first occurrence.

```python
text = "Python Programming"

print(text.find("Programming"))
```

Output:

```text
7
```

If the text isn't found:

```python
print(text.find("Java"))
```

Output:

```text
-1
```

---

## `index()`

Similar to `find()`.

```python
text = "Python"

print(text.index("t"))
```

Output:

```text
2
```

Important difference:

* `find()` returns `-1` if not found.
* `index()` raises an error if not found.

---

# 17. 🔄 Replacing Text

Use `replace()`.

### Syntax

```python
string.replace(old, new)
```

Example:

```python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

Output:

```text
I like Python
```

---

# 18. ✂️ Splitting a String

`split()` converts a string into a list.

```python
text = "Python Java C++"

languages = text.split()

print(languages)
```

Output:

```text
['Python', 'Java', 'C++']
```

---

## Split Using Comma

```python
text = "Apple,Banana,Mango"

fruits = text.split(",")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

---

# 19. 🔗 Joining Strings

`join()` combines items into a string.

```python
words = ["Python", "is", "easy"]

sentence = " ".join(words)

print(sentence)
```

Output:

```text
Python is easy
```

Another example:

```python
words = ["2026", "08", "16"]

date = "-".join(words)

print(date)
```

Output:

```text
2026-08-16
```

---

# 20. ✅ Checking String Content

Python provides methods to check the contents of a string.

---

## `isalpha()`

Checks whether all characters are letters.

```python
text = "Python"

print(text.isalpha())
```

Output:

```text
True
```

---

## `isdigit()`

Checks whether all characters are digits.

```python
text = "12345"

print(text.isdigit())
```

Output:

```text
True
```

---

## `isalnum()`

Checks whether characters contain only letters and numbers.

```python
text = "Python123"

print(text.isalnum())
```

Output:

```text
True
```

---

## `isspace()`

Checks whether the string contains only spaces.

```python
text = "   "

print(text.isspace())
```

Output:

```text
True
```

---

## `islower()`

```python
text = "python"

print(text.islower())
```

Output:

```text
True
```

---

## `isupper()`

```python
text = "PYTHON"

print(text.isupper())
```

Output:

```text
True
```

---

# 21. 🚨 Escape Characters

Escape characters allow special characters inside strings.

---

## New Line — `\n`

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

---

## Tab — `\t`

```python
print("Hello\tWorld")
```

Output:

```text
Hello   World
```

---

## Double Quote — `\"`

```python
print("He said \"Hello\"")
```

Output:

```text
He said "Hello"
```

---

## Single Quote — `\'`

```python
print('It\'s Python')
```

Output:

```text
It's Python
```

---

## Backslash — `\\`

```python
print("C:\\Users\\Yashu")
```

---

# 22. 🎨 Raw Strings

A raw string treats backslashes mostly as normal characters.

Use `r` before the string.

```python
path = r"C:\Users\Yashu\Documents"

print(path)
```

This is especially useful for Windows paths and regular expressions.

---

# 23. 🧩 String Formatting

Suppose:

```python
name = "Yashu"
age = 20
```

We want:

```text
My name is Yashu and I am 20 years old.
```

There are several ways.

---

## Method 1 — Concatenation

```python
name = "Yashu"
age = 20

print("My name is " + name + " and I am " + str(age) + " years old.")
```

---

## Method 2 — `format()`

```python
name = "Yashu"
age = 20

print("My name is {} and I am {} years old.".format(name, age))
```

Output:

```text
My name is Yashu and I am 20 years old.
```

---

# 24. ⭐ f-Strings

f-strings are one of the easiest and most useful ways to format strings.

Put `f` before the string.

```python
name = "Yashu"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Yashu and I am 20 years old.
```

You can also put expressions inside `{}`.

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Output:

```text
Sum = 30
```

---

# 25. 💰 Formatting Numbers

f-strings can format numbers.

```python
price = 99.5678

print(f"Price: {price:.2f}")
```

Output:

```text
Price: 99.57
```

`.2f` means **2 digits after the decimal point**.

---

# 26. 📊 Useful String Methods

| Method         | Purpose                              |
| -------------- | ------------------------------------ |
| `upper()`      | Uppercase                            |
| `lower()`      | Lowercase                            |
| `capitalize()` | First letter uppercase               |
| `title()`      | First letter of every word uppercase |
| `swapcase()`   | Reverse case                         |
| `strip()`      | Remove outer spaces                  |
| `lstrip()`     | Remove left spaces                   |
| `rstrip()`     | Remove right spaces                  |
| `find()`       | Find position                        |
| `replace()`    | Replace text                         |
| `split()`      | Convert string to list               |
| `join()`       | Join strings                         |
| `startswith()` | Check beginning                      |
| `endswith()`   | Check ending                         |
| `isalpha()`    | Check letters                        |
| `isdigit()`    | Check digits                         |
| `isalnum()`    | Check letters/numbers                |
| `isspace()`    | Check spaces                         |

---

# 27. 🔍 `startswith()`

Checks whether a string starts with specific text.

```python
text = "Python Programming"

print(text.startswith("Python"))
```

Output:

```text
True
```

---

# 28. 🔚 `endswith()`

Checks whether a string ends with specific text.

```python
text = "Python Programming"

print(text.endswith("Programming"))
```

Output:

```text
True
```

---

# 29. 🔢 Count Characters

Use `count()`.

```python
text = "banana"

print(text.count("a"))
```

Output:

```text
3
```

Another example:

```python
text = "Python Python Python"

print(text.count("Python"))
```

Output:

```text
3
```

---

# 30. 🔒 Strings are Immutable

Strings cannot be changed directly after they are created.

Example:

```python
word = "Python"
```

You cannot directly do:

```python
word[0] = "J"
```

This causes an error.

Instead, create a new string:

```python
word = "Python"

word = "J" + word[1:]

print(word)
```

Output:

```text
Jython
```

---

# 31. 🧮 Count Vowels

Program to count vowels:

```python
text = input("Enter a string: ")

count = 0

for char in text:
    if char.lower() in "aeiou":
        count += 1

print("Vowels =", count)
```

Example:

```text
Input:
Python Programming

Output:
Vowels = 4
```

---

# 32. 🔄 Reverse a String

```python
text = input("Enter a string: ")

reverse = text[::-1]

print("Reverse =", reverse)
```

Example:

```text
Input:
Python

Output:
Reverse = nohtyP
```

---

# 33. 🪞 Check Palindrome

A palindrome reads the same forwards and backwards.

Examples:

```text
madam
level
racecar
```

Program:

```python
text = input("Enter a string: ")

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

---

# 34. 🔤 Count Words

```python
sentence = input("Enter a sentence: ")

words = sentence.split()

print("Number of words =", len(words))
```

Example:

```text
Input:
Python is easy to learn

Output:
Number of words = 5
```

---

# 35. 🔠 Convert First Letter to Uppercase

```python
name = input("Enter your name: ")

print(name.capitalize())
```

Example:

```text
Input:
yashu

Output:
Yashu
```

---

# 36. 🧹 Remove Extra Spaces

```python
text = input("Enter text: ")

text = text.strip()

print(text)
```

---

# 37. 🔍 Find Character Frequency

```python
text = input("Enter a string: ")
character = input("Enter a character: ")

count = text.count(character)

print("Frequency =", count)
```

Example:

```text
Input:
banana
a

Output:
Frequency = 3
```

---

# 38. 🔐 Simple Username Check

```python
username = input("Enter username: ")

if username == "yashu":
    print("Welcome Yashu")
else:
    print("Unknown user")
```

---

# 39. 📧 Basic Email Check

A simple beginner check:

```python
email = input("Enter email: ")

if "@" in email and "." in email:
    print("Looks like an email")
else:
    print("Invalid email")
```

> This is only a basic learning example, not complete email validation.

---

# 40. 🧠 Important Difference

### `find()`

```python
text.find("x")
```

Returns:

```text
-1
```

if not found.

### `index()`

```python
text.index("x")
```

Raises an error if not found.

---

# 41. 📚 Practice Questions

Try these yourself.

### Beginner

1. Create a string containing your name.
2. Print the length of your name.
3. Print the first character.
4. Print the last character.
5. Reverse a string.
6. Convert a string to uppercase.
7. Convert a string to lowercase.
8. Count the number of `a` characters.
9. Replace one word with another.
10. Check whether a word exists in a sentence.

### Intermediate

11. Count vowels in a string.
12. Count consonants.
13. Count words in a sentence.
14. Check whether a string is a palindrome.
15. Remove spaces from both sides.
16. Find the first occurrence of a character.
17. Find the frequency of every character.
18. Reverse every word in a sentence.
19. Find the longest word in a sentence.
20. Remove duplicate characters from a string.

### Challenge

21. Check whether two strings are anagrams.

Example:

```text
listen
silent
```

Result:

```text
Anagrams
```

22. Find the most frequent character.

23. Count uppercase and lowercase letters.

24. Count letters, digits and special characters.

25. Create a simple password strength checker.

---

# 42. 🎯 Quick Revision

### Create a string

```python
name = "Yashu"
```

### Length

```python
len(name)
```

### Index

```python
name[0]
```

### Last character

```python
name[-1]
```

### Slice

```python
name[0:3]
```

### Reverse

```python
name[::-1]
```

### Uppercase

```python
name.upper()
```

### Lowercase

```python
name.lower()
```

### Remove spaces

```python
name.strip()
```

### Replace

```python
name.replace("old", "new")
```

### Split

```python
text.split()
```

### Join

```python
" ".join(words)
```

### Search

```python
text.find("Python")
```

### Count

```python
text.count("a")
```

### f-string

```python
f"Hello {name}"
```

---

# 🚀 Learning Path

You have now covered:

```text
Notes 1 → Python Basics
           ↓
Notes 2 → Control Flow
           ↓
Notes 3 → Strings ✅
           ↓
Notes 4 → Lists
           ↓
Notes 5 → Tuples, Sets & Dictionaries
           ↓
Notes 6 → Functions
           ↓
Notes 7 → Modules & Packages
           ↓
Notes 8 → File Handling
           ↓
Notes 9 → Exception Handling
           ↓
Notes 10 → OOP
```

---

# ⭐ Final Tip

Strings are used everywhere in real-world Python:

```text
Usernames
Passwords
Emails
Messages
File paths
JSON data
Web data
Database data
AI prompts
Search queries
```

Master these concepts:

```text
Indexing
Slicing
Methods
Searching
Replacing
Splitting
Joining
Formatting
```

and you'll have a strong foundation for the next Python topics.

```python
print("Keep Learning 🐍")
print("Keep Practicing 💻")
print("Build Projects 🚀")
```

**Happy Coding! 🐍🔥**
