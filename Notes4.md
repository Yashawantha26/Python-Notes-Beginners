# 🐍 Python Notes 4 — Lists

> A complete beginner-friendly guide to Python Lists with syntax, indexing, slicing, methods, loops, copying, nested lists, and practice programs.

---

## 📌 Table of Contents

1. What is a List?
2. Creating a List
3. Different Types of Data
4. List Indexing
5. Negative Indexing
6. List Slicing
7. Changing List Items
8. Adding Items
9. Removing Items
10. List Length
11. Checking Items
12. Looping Through Lists
13. Sorting Lists
14. Reversing Lists
15. Copying Lists
16. Joining Lists
17. List Operators
18. Nested Lists
19. List Comprehension
20. Useful List Methods
21. Common Programs
22. Practice Questions
23. Quick Revision

---

# 1. 📋 What is a List?

A **list** is a collection of multiple values stored in a single variable.

Example:

```python
fruits = ["Apple", "Banana", "Mango"]
```

A list can contain multiple items.

```text
Apple
Banana
Mango
```

Lists are one of the most commonly used data structures in Python.

---

# 2. 📝 Creating a List

Lists are created using square brackets `[]`.

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

---

# 3. 🧩 Lists Can Store Different Data Types

A list can contain different types of values.

```python
data = ["Yashu", 20, 85.5, True]
```

Here:

```text
"Yashu" → String
20      → Integer
85.5    → Float
True    → Boolean
```

Python allows this.

---

# 4. 🔢 List Indexing

Every item in a list has an index.

Example:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]
```

Indexes:

```text
Apple   → 0
Banana  → 1
Mango   → 2
Orange  → 3
```

Example:

```python
print(fruits[0])
print(fruits[2])
```

Output:

```text
Apple
Mango
```

---

# 5. 🔙 Negative Indexing

Lists support negative indexes.

```text
Apple   → -4
Banana  → -3
Mango   → -2
Orange  → -1
```

Example:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[-1])
```

Output:

```text
Orange
```

---

# 6. ✂️ List Slicing

You can extract part of a list.

### Syntax

```python
list[start:end]
```

Example:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[1:3])
```

Output:

```text
['Banana', 'Mango']
```

Remember:

> The ending index is not included.

---

## More Examples

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[:3])
print(numbers[2:])
print(numbers[1:4])
```

Output:

```text
[10, 20, 30]
[30, 40, 50]
[20, 30, 40]
```

---

# 7. 🔄 Reverse a List Using Slicing

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[::-1])
```

Output:

```text
[5, 4, 3, 2, 1]
```

---

# 8. ✏️ Changing List Items

Lists are **mutable**.

This means you can change their values.

```python
fruits = ["Apple", "Banana", "Mango"]

fruits[1] = "Orange"

print(fruits)
```

Output:

```text
['Apple', 'Orange', 'Mango']
```

---

# 9. ➕ Adding Items

There are several ways to add items.

## `append()`

Adds an item to the end.

```python
fruits = ["Apple", "Banana"]

fruits.append("Mango")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

---

# 10. 📍 `insert()`

Adds an item at a specific position.

### Syntax

```python
list.insert(index, value)
```

Example:

```python
fruits = ["Apple", "Mango"]

fruits.insert(1, "Banana")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

---

# 11. 🔗 `extend()`

Adds multiple items from another collection.

```python
fruits = ["Apple", "Banana"]

more_fruits = ["Mango", "Orange"]

fruits.extend(more_fruits)

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

---

# 12. 🗑️ Removing Items

## `remove()`

Removes a specific value.

```python
fruits = ["Apple", "Banana", "Mango"]

fruits.remove("Banana")

print(fruits)
```

Output:

```text
['Apple', 'Mango']
```

> If the value doesn't exist, `remove()` raises an error.

---

# 13. 🗑️ `pop()`

`pop()` removes an item using its index and returns that item.

```python
fruits = ["Apple", "Banana", "Mango"]

item = fruits.pop(1)

print(item)
print(fruits)
```

Output:

```text
Banana
['Apple', 'Mango']
```

If no index is given, it removes the last item.

```python
fruits.pop()
```

---

# 14. 🧹 `clear()`

Removes all items.

```python
fruits = ["Apple", "Banana", "Mango"]

fruits.clear()

print(fruits)
```

Output:

```text
[]
```

---

# 15. 📏 List Length

Use `len()`.

```python
fruits = ["Apple", "Banana", "Mango"]

print(len(fruits))
```

Output:

```text
3
```

---

# 16. 🔍 Check Whether an Item Exists

Use `in`.

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
```

Output:

```text
True
```

Example:

```python
print("Orange" in fruits)
```

Output:

```text
False
```

---

# 17. ❌ `not in`

```python
fruits = ["Apple", "Banana", "Mango"]

print("Orange" not in fruits)
```

Output:

```text
True
```

---

# 18. 🔄 Loop Through a List

Use a `for` loop.

```python
fruits = ["Apple", "Banana", "Mango"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Banana
Mango
```

---

# 19. 🔢 Loop Using Index

Use `range()` and `len()`.

```python
fruits = ["Apple", "Banana", "Mango"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

Output:

```text
0 Apple
1 Banana
2 Mango
```

---

# 20. 🔢 List of Numbers

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

---

# 21. ➕ Sum of List

Python provides `sum()`.

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

Output:

```text
100
```

---

# 22. 🔼 Find Maximum

Use `max()`.

```python
numbers = [10, 50, 20, 80, 30]

print(max(numbers))
```

Output:

```text
80
```

---

# 23. 🔽 Find Minimum

Use `min()`.

```python
numbers = [10, 50, 20, 80, 30]

print(min(numbers))
```

Output:

```text
10
```

---

# 24. 🔢 Count an Item

Use `count()`.

```python
numbers = [1, 2, 2, 3, 2, 4]

print(numbers.count(2))
```

Output:

```text
3
```

---

# 25. 🔎 Find Position

Use `index()`.

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits.index("Banana"))
```

Output:

```text
1
```

---

# 26. 🔤 Sorting a List

## `sort()`

Sorts the list in ascending order.

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

---

# 27. 🔽 Descending Sort

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[50, 40, 30, 20, 10]
```

---

# 28. 🔤 Sorting Strings

```python
fruits = ["Mango", "Apple", "Orange", "Banana"]

fruits.sort()

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango', 'Orange']
```

---

# 29. 🔄 `reverse()`

Reverses the list in place.

```python
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
```

Output:

```text
[5, 4, 3, 2, 1]
```

---

# 30. 📋 Copying a List

Be careful when copying lists.

## Using `copy()`

```python
original = [1, 2, 3]

copy_list = original.copy()

print(copy_list)
```

Output:

```text
[1, 2, 3]
```

Now they are separate list objects.

---

# 31. ⚠️ Reference vs Copy

This:

```python
a = [1, 2, 3]
b = a
```

does not create an independent list.

Both names refer to the same list.

Use:

```python
b = a.copy()
```

when you want a separate copy.

---

# 32. ➕ Joining Lists

Lists can be combined using `+`.

```python
a = [1, 2, 3]
b = [4, 5, 6]

c = a + b

print(c)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

---

# 33. ✖️ Repeating Lists

Use `*`.

```python
numbers = [1, 2]

print(numbers * 3)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

---

# 34. 🪆 Nested Lists

A list can contain another list.

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

This is called a **nested list**.

---

# 35. 🎯 Access Nested Lists

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(numbers[0])
```

Output:

```text
[1, 2, 3]
```

To access `5`:

```python
print(numbers[1][1])
```

Output:

```text
5
```

---

# 36. 🔄 Loop Through Nested Lists

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in numbers:
    for number in row:
        print(number)
```

Output:

```text
1
2
3
4
5
6
7
8
9
```

---

# 37. 🧠 List Comprehension

List comprehension provides a short way to create lists.

### Normal method

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

### List comprehension

```python
numbers = [i for i in range(1, 6)]

print(numbers)
```

Same output:

```text
[1, 2, 3, 4, 5]
```

---

# 38. 🔢 Squares Using List Comprehension

```python
squares = [i ** 2 for i in range(1, 6)]

print(squares)
```

Output:

```text
[1, 4, 9, 16, 25]
```

---

# 39. 🟢 Even Numbers Using List Comprehension

```python
even_numbers = [i for i in range(1, 11) if i % 2 == 0]

print(even_numbers)
```

Output:

```text
[2, 4, 6, 8, 10]
```

---

# 40. 🔤 Convert Words to Uppercase

```python
names = ["yashu", "rahul", "arun"]

upper_names = [name.upper() for name in names]

print(upper_names)
```

Output:

```text
['YASHU', 'RAHUL', 'ARUN']
```

---

# 41. 📚 Useful List Methods

| Method      | Purpose               |
| ----------- | --------------------- |
| `append()`  | Add item at end       |
| `insert()`  | Add item at position  |
| `extend()`  | Add multiple items    |
| `remove()`  | Remove specific value |
| `pop()`     | Remove by index       |
| `clear()`   | Remove everything     |
| `index()`   | Find position         |
| `count()`   | Count occurrences     |
| `sort()`    | Sort list             |
| `reverse()` | Reverse list          |
| `copy()`    | Copy list             |

---

# 42. 🧰 Useful Built-in Functions

| Function   | Purpose             |
| ---------- | ------------------- |
| `len()`    | Number of items     |
| `sum()`    | Sum of numbers      |
| `max()`    | Largest value       |
| `min()`    | Smallest value      |
| `sorted()` | Returns sorted list |
| `list()`   | Creates a list      |

---

# 43. `sort()` vs `sorted()`

### `sort()`

Changes the original list.

```python
numbers = [3, 1, 2]

numbers.sort()

print(numbers)
```

### `sorted()`

Creates and returns a new sorted list.

```python
numbers = [3, 1, 2]

new_numbers = sorted(numbers)

print(new_numbers)
print(numbers)
```

Output:

```text
[1, 2, 3]
[3, 1, 2]
```

---

# 44. 🧮 Find Sum Using Loop

```python
numbers = [10, 20, 30, 40]

total = 0

for number in numbers:
    total += number

print("Sum =", total)
```

Output:

```text
Sum = 100
```

---

# 45. 🔢 Find Even Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

Output:

```text
2
4
6
```

---

# 46. 🔢 Find Odd Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

for number in numbers:
    if number % 2 != 0:
        print(number)
```

Output:

```text
1
3
5
```

---

# 47. 🏆 Find Largest Without `max()`

```python
numbers = [10, 50, 20, 80, 30]

largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number

print("Largest =", largest)
```

Output:

```text
Largest = 80
```

---

# 48. 🔽 Find Smallest Without `min()`

```python
numbers = [10, 50, 20, 80, 30]

smallest = numbers[0]

for number in numbers:
    if number < smallest:
        smallest = number

print("Smallest =", smallest)
```

Output:

```text
Smallest = 10
```

---

# 49. 🔢 Remove Duplicates

One simple method:

```python
numbers = [1, 2, 2, 3, 3, 4]

unique = list(set(numbers))

print(unique)
```

Output may be:

```text
[1, 2, 3, 4]
```

> Note: converting to a set does not guarantee preserving the original order in general. If order matters, use another approach.

---

# 50. 🔄 Copy a List Using Slicing

```python
numbers = [1, 2, 3, 4]

copy_list = numbers[:]

print(copy_list)
```

---

# 51. 🧑‍🎓 Student Marks Example

```python
marks = [85, 90, 78, 92, 88]

print("Total =", sum(marks))
print("Highest =", max(marks))
print("Lowest =", min(marks))
print("Number of subjects =", len(marks))
```

Output:

```text
Total = 433
Highest = 92
Lowest = 78
Number of subjects = 5
```

---

# 52. 📊 Calculate Average

```python
marks = [85, 90, 78, 92, 88]

average = sum(marks) / len(marks)

print("Average =", average)
```

Output:

```text
Average = 86.6
```

---

# 53. 🔤 Find Longest Word

```python
words = ["Python", "Java", "Programming", "AI"]

longest = words[0]

for word in words:
    if len(word) > len(longest):
        longest = word

print("Longest word =", longest)
```

Output:

```text
Longest word = Programming
```

---

# 54. 🔎 Search an Item

```python
fruits = ["Apple", "Banana", "Mango"]

search = input("Enter fruit: ")

if search in fruits:
    print("Fruit found")
else:
    print("Fruit not found")
```

---

# 55. 🛒 Simple Shopping List

```python
shopping = []

shopping.append("Milk")
shopping.append("Bread")
shopping.append("Eggs")

print("Shopping List:")

for item in shopping:
    print("-", item)
```

Output:

```text
Shopping List:
- Milk
- Bread
- Eggs
```

---

# 56. 🧮 Separate Positive and Negative Numbers

```python
numbers = [10, -5, 8, -2, 0, 7]

positive = []
negative = []

for number in numbers:
    if number > 0:
        positive.append(number)
    elif number < 0:
        negative.append(number)

print("Positive:", positive)
print("Negative:", negative)
```

Output:

```text
Positive: [10, 8, 7]
Negative: [-5, -2]
```

---

# 57. 📌 Important Property: Lists are Mutable

A list can be changed after creation.

```python
numbers = [1, 2, 3]

numbers[0] = 100

print(numbers)
```

Output:

```text
[100, 2, 3]
```

This is called **mutability**.

---

# 58. 🆚 List vs String

| Feature  | List            | String |
| -------- | --------------- | ------ |
| Stores   | Multiple values | Text   |
| Brackets | `[]`            | Quotes |
| Mutable  | ✅ Yes           | ❌ No   |
| Indexing | ✅               | ✅      |
| Slicing  | ✅               | ✅      |
| `len()`  | ✅               | ✅      |

Example:

```python
name = "Python"
numbers = [1, 2, 3]
```

---

# 59. 🧠 List vs Tuple Preview

Lists:

```python
numbers = [1, 2, 3]
```

Tuples:

```python
numbers = (1, 2, 3)
```

Main difference:

```text
List  → Mutable
Tuple → Immutable
```

Tuples will be covered in the next notes.

---

# 60. 📚 Practice Questions

Try these without looking at the answers.

### Beginner

1. Create a list of five fruits.
2. Print the first item.
3. Print the last item.
4. Find the length of a list.
5. Add an item using `append()`.
6. Insert an item using `insert()`.
7. Remove an item using `remove()`.
8. Remove the last item using `pop()`.
9. Check whether an item exists.
10. Reverse a list.

### Intermediate

11. Find the largest number.
12. Find the smallest number.
13. Find the sum of all numbers.
14. Calculate the average.
15. Count occurrences of an item.
16. Sort numbers in ascending order.
17. Sort numbers in descending order.
18. Create a copy of a list.
19. Remove duplicate values.
20. Find all even numbers.

### Advanced Practice

21. Find the second-largest number.
22. Find the second-smallest number.
23. Find the longest word.
24. Find the shortest word.
25. Separate positive and negative numbers.
26. Separate even and odd numbers.
27. Reverse a list without using `reverse()`.
28. Find common elements between two lists.
29. Merge two lists.
30. Create a list of squares using list comprehension.

---

# 61. 🎯 Quick Revision

### Create

```python
fruits = ["Apple", "Banana", "Mango"]
```

### Access

```python
fruits[0]
```

### Last item

```python
fruits[-1]
```

### Slice

```python
fruits[1:3]
```

### Add

```python
fruits.append("Orange")
```

### Insert

```python
fruits.insert(1, "Orange")
```

### Extend

```python
fruits.extend(["Grapes", "Papaya"])
```

### Remove

```python
fruits.remove("Apple")
```

### Pop

```python
fruits.pop()
```

### Length

```python
len(fruits)
```

### Sort

```python
fruits.sort()
```

### Reverse

```python
fruits.reverse()
```

### Copy

```python
new_list = fruits.copy()
```

### Check

```python
"Apple" in fruits
```

### Count

```python
fruits.count("Apple")
```

### Position

```python
fruits.index("Apple")
```

### Sum

```python
sum(numbers)
```

### Largest

```python
max(numbers)
```

### Smallest

```python
min(numbers)
```

---

# 🚀 Learning Path

```text
Notes 1 → Python Basics
      ↓
Notes 2 → Control Flow
      ↓
Notes 3 → Strings
      ↓
Notes 4 → Lists ✅
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
Notes 10 → Object-Oriented Programming
```

---

# ⭐ Final Tip

Lists are extremely important in Python.

You will use them for:

```text
Student marks
User data
Products
Shopping carts
Database results
API responses
Files
Data analysis
Machine Learning
Projects
```

Master these:

```text
Indexing
Slicing
append()
insert()
extend()
remove()
pop()
sort()
reverse()
copy()
Loops
List Comprehension
```

Then move on to **Tuples, Sets and Dictionaries**.

```python
print("Learn Lists 🐍")
print("Practice Every Day 💻")
print("Build Real Projects 🚀")
```

**Happy Coding! 🔥**
