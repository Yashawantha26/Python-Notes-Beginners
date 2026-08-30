# 🐍 Python Notes 5 — Tuples, Sets & Dictionaries

> A complete beginner-friendly guide to **Tuples, Sets, and Dictionaries** with syntax, examples, methods, differences, and practice programs.

---

## 📌 Table of Contents

1. Python Data Structures
2. Tuples
3. Creating Tuples
4. Tuple Indexing
5. Tuple Slicing
6. Tuple Methods
7. Tuple Unpacking
8. Tuple Operations
9. Lists vs Tuples
10. Sets
11. Creating Sets
12. Adding Set Items
13. Removing Set Items
14. Set Operations
15. Set Methods
16. Dictionaries
17. Creating Dictionaries
18. Accessing Dictionary Values
19. Adding and Updating Values
20. Removing Dictionary Items
21. Dictionary Methods
22. Looping Through Dictionaries
23. Nested Dictionaries
24. Dictionary Comprehension
25. Tuples vs Sets vs Dictionaries
26. Practice Programs
27. Practice Questions
28. Quick Revision

---

# 1. 🧠 Python Data Structures

A **data structure** is a way to organize and store data.

Important Python data structures:

```text
List
Tuple
Set
Dictionary
```

We already learned:

```text
List → []
```

Now we will learn:

```text
Tuple      → ()
Set        → {}
Dictionary → {key: value}
```

---

# 2. 📦 Tuples

A **tuple** is an ordered collection of items.

Tuples are:

* Ordered
* Indexed
* Allow duplicate values
* Immutable

Example:

```python id="d8b2bc"
numbers = (10, 20, 30, 40)

print(numbers)
```

Output:

```text id="q9wyq2"
(10, 20, 30, 40)
```

---

# 3. 📝 Creating a Tuple

Use parentheses `()`.

```python id="y2izid"
fruits = ("Apple", "Banana", "Mango")

print(fruits)
```

You can also create a tuple without parentheses:

```python id="4trfzt"
fruits = "Apple", "Banana", "Mango"

print(fruits)
```

---

# 4. ⚠️ Single-Item Tuple

A single-item tuple needs a comma.

Correct:

```python id="0t4b8v"
number = (10,)
```

Without the comma:

```python id="36j8c9"
number = (10)
```

This is just an integer, not a tuple.

Check:

```python id="7s7k6w"
print(type(number))
```

---

# 5. 🔢 Tuple Indexing

Tuples support indexing just like lists.

```python id="v3wq1p"
fruits = ("Apple", "Banana", "Mango")

print(fruits[0])
print(fruits[1])
```

Output:

```text id="j11v9f"
Apple
Banana
```

---

# 6. 🔙 Negative Indexing

```python id="8v5cgo"
fruits = ("Apple", "Banana", "Mango")

print(fruits[-1])
```

Output:

```text id="n6f9wa"
Mango
```

---

# 7. ✂️ Tuple Slicing

```python id="o1zjym"
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
```

Output:

```text id="yxh2k9"
(20, 30, 40)
```

---

# 8. 🔒 Tuples are Immutable

Immutable means a tuple cannot be changed after creation.

This is invalid:

```python id="f5zuwu"
numbers = (10, 20, 30)

numbers[0] = 100
```

It produces an error because tuples cannot be modified directly.

If you need a collection that can change, use a list.

---

# 9. 📏 Tuple Length

Use `len()`.

```python id="2gn7f4"
numbers = (10, 20, 30, 40)

print(len(numbers))
```

Output:

```text id="z1l5am"
4
```

---

# 10. 🔍 Check Tuple Item

```python id="0h6qf7"
fruits = ("Apple", "Banana", "Mango")

print("Apple" in fruits)
```

Output:

```text id="c2f6e6"
True
```

---

# 11. 🔢 Tuple `count()`

Counts how many times a value appears.

```python id="zzx1p8"
numbers = (1, 2, 2, 3, 2)

print(numbers.count(2))
```

Output:

```text id="b1ftw8"
3
```

---

# 12. 🔎 Tuple `index()`

Finds the first position of a value.

```python id="v6z1sn"
fruits = ("Apple", "Banana", "Mango")

print(fruits.index("Banana"))
```

Output:

```text id="r7z8zv"
1
```

---

# 13. 🔄 Loop Through Tuple

```python id="djh6qp"
fruits = ("Apple", "Banana", "Mango")

for fruit in fruits:
    print(fruit)
```

Output:

```text id="jv8y3m"
Apple
Banana
Mango
```

---

# 14. 📦 Tuple Unpacking

Tuple unpacking allows us to assign tuple values to variables.

```python id="x5x2pg"
person = ("Yashu", 20, "CSE")

name, age, branch = person

print(name)
print(age)
print(branch)
```

Output:

```text id="f4f1vv"
Yashu
20
CSE
```

---

# 15. 🔄 Swapping Variables Using Tuples

Python makes swapping easy.

```python id="17bqye"
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text id="6sl8fy"
20
10
```

---

# 16. ➕ Joining Tuples

Use `+`.

```python id="0q4l7e"
a = (1, 2, 3)
b = (4, 5, 6)

c = a + b

print(c)
```

Output:

```text id="w2hj2m"
(1, 2, 3, 4, 5, 6)
```

---

# 17. ✖️ Repeating Tuples

Use `*`.

```python id="9z5w8m"
numbers = (1, 2)

print(numbers * 3)
```

Output:

```text id="b4yx9x"
(1, 2, 1, 2, 1, 2)
```

---

# 18. 🆚 List vs Tuple

| Feature    | List | Tuple |
| ---------- | ---- | ----- |
| Syntax     | `[]` | `()`  |
| Ordered    | ✅    | ✅     |
| Indexed    | ✅    | ✅     |
| Duplicates | ✅    | ✅     |
| Mutable    | ✅    | ❌     |
| Immutable  | ❌    | ✅     |

Use a **list** when data needs to change.

Use a **tuple** when data should remain unchanged.

---

# 19. 🔵 Sets

A **set** is an unordered collection of unique values.

Example:

```python id="3e4kfz"
numbers = {1, 2, 3, 4}

print(numbers)
```

A set does not allow duplicate values.

```python id="2b0kku"
numbers = {1, 2, 2, 3, 3, 4}

print(numbers)
```

Output will contain each value only once.

---

# 20. ⚠️ Sets Are Unordered

Do not depend on a set having a particular display order.

For example:

```python id="m9w1nq"
fruits = {"Apple", "Banana", "Mango"}

print(fruits)
```

The displayed order is not something you should rely on.

Sets are mainly useful for:

```text
Unique values
Membership testing
Set mathematics
Removing duplicates
```

---

# 21. 📝 Creating an Empty Set

This is important.

❌ This creates an empty dictionary:

```python id="g8byo0"
data = {}
```

✅ This creates an empty set:

```python id="a8d3cf"
data = set()
```

---

# 22. ➕ Add to a Set

Use `add()`.

```python id="k5k4wl"
fruits = {"Apple", "Banana"}

fruits.add("Mango")

print(fruits)
```

---

# 23. ➕ Add Multiple Items

Use `update()`.

```python id="t4cc5g"
fruits = {"Apple", "Banana"}

fruits.update(["Mango", "Orange"])

print(fruits)
```

---

# 24. 🗑️ Remove from Set

## `remove()`

```python id="q9i8cf"
fruits = {"Apple", "Banana", "Mango"}

fruits.remove("Banana")

print(fruits)
```

If the item does not exist, `remove()` raises an error.

---

# 25. 🗑️ `discard()`

`discard()` also removes an item.

But if the item does not exist, it does **not** raise an error.

```python id="d0aklq"
fruits = {"Apple", "Banana"}

fruits.discard("Mango")

print(fruits)
```

No error occurs.

---

# 26. 🗑️ `pop()`

`pop()` removes and returns an arbitrary set item.

```python id="i0od8p"
numbers = {10, 20, 30}

item = numbers.pop()

print(item)
print(numbers)
```

Because sets are unordered, do not assume which item will be removed.

---

# 27. 🧹 Clear a Set

```python id="aq6w8h"
numbers = {1, 2, 3}

numbers.clear()

print(numbers)
```

Output:

```text id="p1l7p6"
set()
```

---

# 28. 🔍 Membership in Sets

Sets are very useful for checking membership.

```python id="e5yqby"
languages = {"Python", "Java", "C++"}

print("Python" in languages)
```

Output:

```text id="u0wq1e"
True
```

---

# 29. 🔗 Set Union

Union combines values from two sets.

```python id="j0p0h8"
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)
```

Output:

```text id="8jwmgu"
{1, 2, 3, 4, 5}
```

You can also use:

```python id="2q8y0j"
print(a.union(b))
```

---

# 30. 🔵 Set Intersection

Intersection returns values common to both sets.

```python id="8s7f4d"
a = {1, 2, 3}
b = {3, 4, 5}

print(a & b)
```

Output:

```text id="y4i1ah"
{3}
```

Or:

```python id="x0e5px"
print(a.intersection(b))
```

---

# 31. ➖ Set Difference

Difference returns values that exist in the first set but not the second.

```python id="i1ry7f"
a = {1, 2, 3}
b = {3, 4, 5}

print(a - b)
```

Output:

```text id="6uwxft"
{1, 2}
```

---

# 32. 🔄 Symmetric Difference

Returns values that are in either set but not both.

```python id="d8em0q"
a = {1, 2, 3}
b = {3, 4, 5}

print(a ^ b)
```

Output:

```text id="c0u3s8"
{1, 2, 4, 5}
```

---

# 33. 📊 Set Operations Summary

| Operation            | Symbol | Method                   |
| -------------------- | ------ | ------------------------ |
| Union                | `\|`   | `union()`                |
| Intersection         | `&`    | `intersection()`         |
| Difference           | `-`    | `difference()`           |
| Symmetric Difference | `^`    | `symmetric_difference()` |

---

# 34. 🗂️ Dictionaries

A **dictionary** stores data as **key-value pairs**.

Example:

```python id="r0f8od"
student = {
    "name": "Yashu",
    "age": 20,
    "branch": "CSE"
}
```

Structure:

```text id="p2y8pl"
key       → value

"name"    → "Yashu"
"age"     → 20
"branch"  → "CSE"
```

---

# 35. 🔑 Dictionary Keys

Keys are used to identify values.

Example:

```python id="w2r6dd"
student = {
    "name": "Yashu",
    "age": 20
}
```

Here:

```text id="6z4y9t"
"name" → key
"Yashu" → value

"age" → key
20 → value
```

Keys must be unique within a dictionary.

---

# 36. 🎯 Access Dictionary Values

Use the key.

```python id="r0x1y7"
student = {
    "name": "Yashu",
    "age": 20
}

print(student["name"])
print(student["age"])
```

Output:

```text id="rx0m7f"
Yashu
20
```

---

# 37. 🛡️ Using `get()`

`get()` safely retrieves a value.

```python id="sm2l1c"
student = {
    "name": "Yashu",
    "age": 20
}

print(student.get("name"))
```

Output:

```text id="y1g9oc"
Yashu
```

If the key does not exist:

```python id="k1z5m3"
print(student.get("city"))
```

Output:

```text id="y5z5jk"
None
```

You can provide a default:

```python id="qk7m8u"
print(student.get("city", "Not Available"))
```

Output:

```text id="0h54pv"
Not Available
```

---

# 38. ➕ Add a Dictionary Item

```python id="c9v4oe"
student = {
    "name": "Yashu",
    "age": 20
}

student["city"] = "Hassan"

print(student)
```

---

# 39. ✏️ Update Dictionary Value

```python id="n1v5zi"
student = {
    "name": "Yashu",
    "age": 20
}

student["age"] = 21

print(student)
```

---

# 40. 🔄 `update()`

You can update multiple values.

```python id="e4v3u6"
student = {
    "name": "Yashu",
    "age": 20
}

student.update({
    "age": 21,
    "city": "Hassan"
})

print(student)
```

---

# 41. 🗑️ Remove Dictionary Item

## `pop()`

```python id="x1k9h7"
student = {
    "name": "Yashu",
    "age": 20,
    "city": "Hassan"
}

student.pop("city")

print(student)
```

---

# 42. 🗑️ `popitem()`

Removes and returns the last inserted key-value pair.

```python id="c2g6cx"
student = {
    "name": "Yashu",
    "age": 20,
    "city": "Hassan"
}

item = student.popitem()

print(item)
print(student)
```

---

# 43. 🧹 `clear()`

Removes everything.

```python id="k6w7qq"
student = {
    "name": "Yashu",
    "age": 20
}

student.clear()

print(student)
```

Output:

```text id="d6q8pk"
{}
```

---

# 44. 🔑 `keys()`

Returns dictionary keys.

```python id="x3m6fw"
student = {
    "name": "Yashu",
    "age": 20,
    "city": "Hassan"
}

print(student.keys())
```

---

# 45. 💎 `values()`

Returns dictionary values.

```python id="g6d9kl"
print(student.values())
```

---

# 46. 🔗 `items()`

Returns key-value pairs.

```python id="f8n7i4"
print(student.items())
```

---

# 47. 🔄 Loop Through Dictionary Keys

```python id="q4x6yr"
student = {
    "name": "Yashu",
    "age": 20,
    "city": "Hassan"
}

for key in student:
    print(key)
```

Output:

```text id="4p7w0x"
name
age
city
```

---

# 48. 🔄 Loop Through Values

```python id="w9t8s4"
for value in student.values():
    print(value)
```

---

# 49. 🔄 Loop Through Keys and Values

Use `items()`.

```python id="5i2h5g"
for key, value in student.items():
    print(key, ":", value)
```

Output:

```text id="0z6n8f"
name : Yashu
age : 20
city : Hassan
```

---

# 50. 🔍 Check Dictionary Key

Use `in`.

```python id="5w4p8x"
student = {
    "name": "Yashu",
    "age": 20
}

if "name" in student:
    print("Name exists")
```

---

# 51. 📏 Dictionary Length

```python id="q2d4v5"
student = {
    "name": "Yashu",
    "age": 20,
    "city": "Hassan"
}

print(len(student))
```

Output:

```text id="q89t7e"
3
```

---

# 52. 🪆 Nested Dictionary

A dictionary can contain another dictionary.

```python id="h7k3q5"
students = {
    "student1": {
        "name": "Yashu",
        "age": 20
    },
    "student2": {
        "name": "Rahul",
        "age": 21
    }
}
```

Access:

```python id="e6n1b4"
print(students["student1"]["name"])
```

Output:

```text id="q5f7m8"
Yashu
```

---

# 53. 📚 Dictionary of Student Marks

```python id="x4m7p2"
marks = {
    "Python": 90,
    "Java": 85,
    "DBMS": 88
}

print(marks["Python"])
```

Output:

```text id="1s7w3c"
90
```

---

# 54. 🧮 Calculate Total Marks

```python id="r5n8c1"
marks = {
    "Python": 90,
    "Java": 85,
    "DBMS": 88
}

total = sum(marks.values())

print("Total =", total)
```

Output:

```text id="0q7y2k"
Total = 263
```

---

# 55. 📊 Calculate Average

```python id="f2m4r7"
marks = {
    "Python": 90,
    "Java": 85,
    "DBMS": 88
}

average = sum(marks.values()) / len(marks)

print("Average =", average)
```

---

# 56. 🧠 Dictionary Comprehension

Dictionary comprehension provides a short way to create dictionaries.

### Normal method

```python id="n7r4w2"
squares = {}

for i in range(1, 6):
    squares[i] = i ** 2

print(squares)
```

### Dictionary comprehension

```python id="e9p1u3"
squares = {i: i ** 2 for i in range(1, 6)}

print(squares)
```

Output:

```text id="y4w2f8"
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

# 57. 🔢 Dictionary Comprehension with Condition

```python id="v8m3k2"
even_squares = {
    i: i ** 2
    for i in range(1, 11)
    if i % 2 == 0
}

print(even_squares)
```

Output:

```text id="q6c1y7"
{2: 4, 4: 16, 6: 36, 8: 64, 10: 100}
```

---

# 58. 🆚 Tuple vs Set vs Dictionary

| Feature    | Tuple  | Set                 | Dictionary      |
| ---------- | ------ | ------------------- | --------------- |
| Syntax     | `()`   | `{}`                | `{key: value}`  |
| Ordered    | ✅      | No guaranteed order | ✅               |
| Indexed    | ✅      | ❌                   | By key          |
| Duplicates | ✅      | ❌                   | Keys ❌          |
| Mutable    | ❌      | ✅                   | ✅               |
| Stores     | Values | Unique values       | Key-value pairs |

---

# 59. 🧠 When to Use What?

### Use a List when:

```text id="o8h5q2"
You need an ordered collection
AND
you need to change it.
```

Example:

```python id="z8c3m5"
shopping = ["Milk", "Bread", "Eggs"]
```

### Use a Tuple when:

```text id="q7f3b1"
Data should not change.
```

Example:

```python id="0d5g8k"
coordinates = (12.5, 77.5)
```

### Use a Set when:

```text id="k9s1d4"
You need unique values.
```

Example:

```python id="c3r6v8"
unique_numbers = {1, 2, 3}
```

### Use a Dictionary when:

```text id="b6m2q7"
You need key-value relationships.
```

Example:

```python id="e5t8n2"
student = {
    "name": "Yashu",
    "age": 20
}
```

---

# 60. 🔥 Remove Duplicates Using Set

```python id="a1z5m9"
numbers = [1, 2, 2, 3, 3, 4, 4]

unique_numbers = set(numbers)

print(unique_numbers)
```

The set keeps only unique values.

If you need a list again:

```python id="r4p7k2"
unique_numbers = list(set(numbers))
```

> If preserving the original order matters, don't rely on this approach; use an order-preserving technique instead.

---

# 61. 🔄 Convert List to Tuple

```python id="v2k5m8"
numbers = [1, 2, 3]

numbers_tuple = tuple(numbers)

print(numbers_tuple)
```

Output:

```text id="f8r3y1"
(1, 2, 3)
```

---

# 62. 🔄 Convert Tuple to List

```python id="p5d8w2"
numbers = (1, 2, 3)

numbers_list = list(numbers)

print(numbers_list)
```

---

# 63. 🔄 Convert List to Set

```python id="m1c7v4"
numbers = [1, 2, 2, 3]

numbers_set = set(numbers)

print(numbers_set)
```

---

# 64. 🧑‍🎓 Student Information Program

```python id="q3x7n9"
student = {
    "name": "Yashu",
    "age": 20,
    "branch": "CSE",
    "college": "RIT Hassan"
}

print("Name:", student["name"])
print("Age:", student["age"])
print("Branch:", student["branch"])
print("College:", student["college"])
```

---

# 65. 🛒 Shopping Cart Dictionary

```python id="m6v2r8"
cart = {
    "Laptop": 50000,
    "Mouse": 1000,
    "Keyboard": 1500
}

total = sum(cart.values())

print("Total =", total)
```

Output:

```text id="f4w8s1"
Total = 52500
```

---

# 66. 🔢 Find Common Values

```python id="h2k6p9"
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

common = a.intersection(b)

print(common)
```

Output:

```text id="s8d1v5"
{3, 4}
```

---

# 67. 🧠 Practice Questions — Tuples

1. Create a tuple containing five numbers.
2. Print the first item.
3. Print the last item.
4. Find its length.
5. Count a specific value.
6. Find the index of a value.
7. Slice a tuple.
8. Reverse a tuple.
9. Unpack a tuple.
10. Convert a tuple to a list.

---

# 68. 🧠 Practice Questions — Sets

1. Create a set of numbers.
2. Add an item.
3. Remove an item.
4. Check whether an item exists.
5. Find the union of two sets.
6. Find the intersection.
7. Find the difference.
8. Find the symmetric difference.
9. Remove duplicates from a list.
10. Find common elements between two lists.

---

# 69. 🧠 Practice Questions — Dictionaries

1. Create a student dictionary.
2. Access a value using its key.
3. Add a new key.
4. Update a value.
5. Remove a key.
6. Print all keys.
7. Print all values.
8. Print all key-value pairs.
9. Loop through a dictionary.
10. Create a nested dictionary.

---

# 70. 🚀 Mini Projects

Try building these using today's concepts:

### Project 1 — Student Marks

Store:

```text id="w4j7m1"
Name
Roll Number
Python Marks
Java Marks
DBMS Marks
```

Calculate:

```text id="n8q3v6"
Total
Average
Highest Mark
Lowest Mark
```

---

### Project 2 — Contact Book

Use a dictionary:

```python id="t5v9k2"
contacts = {
    "Rahul": "9876543210",
    "Arun": "9876543211"
}
```

Features:

```text id="c8m2r5"
Add contact
Search contact
Update contact
Delete contact
Display contacts
```

---

### Project 3 — Duplicate Remover

Input:

```text id="s7n4q1"
[1, 2, 2, 3, 3, 4, 5, 5]
```

Output unique values.

---

# 71. 🎯 Quick Revision

## Tuple

```python id="2z8x4p"
numbers = (1, 2, 3)
```

Access:

```python id="7n5m1c"
numbers[0]
```

Count:

```python id="k3q9v6"
numbers.count(2)
```

Index:

```python id="m8r2t4"
numbers.index(2)
```

---

## Set

```python id="q6w1p8"
numbers = {1, 2, 3}
```

Add:

```python id="v9c4m2"
numbers.add(4)
```

Remove:

```python id="s5x8k3"
numbers.remove(4)
```

Union:

```python id="d2r7n9"
a | b
```

Intersection:

```python id="p4m6w1"
a & b
```

Difference:

```python id="h8q2v5"
a - b
```

---

## Dictionary

```python id="x7c3n6"
student = {
    "name": "Yashu",
    "age": 20
}
```

Access:

```python id="r5m8k2"
student["name"]
```

Safe access:

```python id="z1q6v9"
student.get("name")
```

Add/update:

```python id="w3n7p4"
student["city"] = "Hassan"
```

Remove:

```python id="c9x2m5"
student.pop("city")
```

Keys:

```python id="f6r1k8"
student.keys()
```

Values:

```python id="n4v7q2"
student.values()
```

Items:

```python id="y8m3c5"
student.items()
```

---

# 🚀 Python Learning Path

```text
Notes 1  → Python Basics
     ↓
Notes 2  → Control Flow
     ↓
Notes 3  → Strings
     ↓
Notes 4  → Lists
     ↓
Notes 5  → Tuples, Sets & Dictionaries ✅
     ↓
Notes 6  → Functions
     ↓
Notes 7  → Modules & Packages
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
```

---

# ⭐ Final Tip

Remember the easiest way:

```text
LIST
↓
Ordered + Changeable
[1, 2, 3]


TUPLE
↓
Ordered + Not Changeable
(1, 2, 3)


SET
↓
Unique Values
{1, 2, 3}


DICTIONARY
↓
Key → Value
{"name": "Yashu"}
```

These four structures form a major part of Python programming.

```python id="c4n8m2"
print("Learn Data Structures 🐍")
print("Practice Every Day 💻")
print("Build Real Projects 🚀")
```

**Happy Coding! 🔥**
