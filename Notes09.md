````markdown
# 🐍 Python Notes 9 — Lists

> **Topic:** Python Lists  
> **Level:** Beginner → Intermediate  
> **Goal:** Understand, create, modify, and work with lists confidently.

---

# 📌 Table of Contents

1. What is a List?
2. Creating a List
3. Accessing List Elements
4. Positive Indexing
5. Negative Indexing
6. Changing List Elements
7. Adding Elements
8. `append()`
9. `insert()`
10. `extend()`
11. Removing Elements
12. `remove()`
13. `pop()`
14. `del`
15. `clear()`
16. List Slicing
17. List Length
18. Checking Membership
19. Looping Through a List
20. List Methods
21. Sorting Lists
22. Reversing Lists
23. Copying Lists
24. Joining Lists
25. Nested Lists
26. List Comprehension
27. Important Programs
28. Interview Questions
29. Practice Questions
30. Quick Revision

---

# 1. 📚 What is a List?

A **list** is a collection of multiple values stored in a single variable.

Lists are:

- Ordered
- Mutable
- Allow duplicate values
- Can contain different data types
- Written using square brackets `[]`

### Example

```python
numbers = [10, 20, 30, 40]
print(numbers)
````

Output:

```text
[10, 20, 30, 40]
```

---

# 2. 📝 Creating a List

### Empty List

```python
my_list = []
```

### List of Numbers

```python
numbers = [10, 20, 30, 40, 50]
```

### List of Strings

```python
fruits = ["Apple", "Banana", "Mango"]
```

### Mixed Data Types

```python
data = [10, "Python", 3.14, True]
```

---

# 3. 🔍 Accessing List Elements

List elements are accessed using their index.

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits[0])
print(fruits[1])
print(fruits[2])
```

Output:

```text
Apple
Banana
Mango
```

---

# 4. 🔢 Positive Indexing

Index starts from `0`.

```text
Apple   → 0
Banana  → 1
Mango   → 2
Orange  → 3
```

Example:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[0])
print(fruits[3])
```

---

# 5. 🔄 Negative Indexing

Negative indexing starts from the end.

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
print(fruits[-2])
```

Output:

```text
Orange
Mango
```

---

# 6. ✏️ Changing List Elements

Lists are **mutable**, so their values can be changed.

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

# 7. ➕ Adding Elements

Python provides several methods to add elements:

```text
append()
insert()
extend()
```

---

# 8. ➕ append()

`append()` adds one element to the end of the list.

```python
fruits = ["Apple", "Banana"]

fruits.append("Mango")

print(fruits)
```

Output:

```text
['Apple', 'Banana', 'Mango']
```

### Important

```python
list.append(value)
```

adds exactly **one object**.

Example:

```python
numbers = [1, 2, 3]

numbers.append(4)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

---

# 9. 📍 insert()

`insert()` adds an element at a specific position.

Syntax:

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

# 10. ➕ extend()

`extend()` adds multiple elements to a list.

```python
numbers = [1, 2, 3]

numbers.extend([4, 5, 6])

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

### append vs extend

```python
a = [1, 2]

a.append([3, 4])

print(a)
```

Output:

```text
[1, 2, [3, 4]]
```

Using `extend()`:

```python
a = [1, 2]

a.extend([3, 4])

print(a)
```

Output:

```text
[1, 2, 3, 4]
```

---

# 11. ❌ Removing Elements

Python provides:

```text
remove()
pop()
del
clear()
```

---

# 12. 🗑️ remove()

`remove()` removes the first matching value.

```python
fruits = ["Apple", "Banana", "Mango"]

fruits.remove("Banana")

print(fruits)
```

Output:

```text
['Apple', 'Mango']
```

---

# 13. 🔥 pop()

`pop()` removes an element using its index and returns the removed value.

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

### Remove last element

```python
fruits.pop()
```

---

# 14. 🗑️ del

`del` can remove an element using its index.

```python
numbers = [10, 20, 30, 40]

del numbers[1]

print(numbers)
```

Output:

```text
[10, 30, 40]
```

### Delete multiple elements

```python
numbers = [10, 20, 30, 40, 50]

del numbers[1:4]

print(numbers)
```

Output:

```text
[10, 50]
```

---

# 15. 🧹 clear()

`clear()` removes all elements.

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

---

# 16. ✂️ List Slicing

Slicing extracts a portion of a list.

Syntax:

```python
list[start:end]
```

Example:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

### From beginning

```python
print(numbers[:3])
```

### To the end

```python
print(numbers[2:])
```

### Copy using slicing

```python
copy = numbers[:]
```

---

# 17. 📏 Length of a List

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

# 18. 🔎 Checking Membership

Use:

```text
in
not in
```

Example:

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
print("Orange" in fruits)
```

Output:

```text
True
False
```

Example:

```python
if "Mango" in fruits:
    print("Mango is available")
```

---

# 19. 🔁 Looping Through a List

## Using for loop

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

## Using index

```python
fruits = ["Apple", "Banana", "Mango"]

for i in range(len(fruits)):
    print(fruits[i])
```

---

# 20. 🛠️ Important List Methods

| Method      | Purpose                    |
| ----------- | -------------------------- |
| `append()`  | Add one element            |
| `insert()`  | Add at a specific position |
| `extend()`  | Add multiple elements      |
| `remove()`  | Remove a value             |
| `pop()`     | Remove by index            |
| `clear()`   | Remove all elements        |
| `index()`   | Find index                 |
| `count()`   | Count occurrences          |
| `sort()`    | Sort list                  |
| `reverse()` | Reverse list               |
| `copy()`    | Copy list                  |

---

# 21. 📊 Sorting Lists

## Ascending Order

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

## Descending Order

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

# 22. 🔄 Reversing a List

```python
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
```

Output:

```text
[5, 4, 3, 2, 1]
```

### Using slicing

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[::-1])
```

---

# 23. 📋 Copying Lists

Use `copy()`:

```python
numbers = [10, 20, 30]

new_numbers = numbers.copy()

print(new_numbers)
```

You can also use:

```python
new_numbers = numbers[:]
```

---

# 24. 🔗 Joining Lists

Lists can be joined using `+`.

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

# 25. 📦 Nested Lists

A list can contain another list.

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix)
```

### Accessing nested elements

```python
print(matrix[0][1])
```

Output:

```text
2
```

---

# 26. ⚡ List Comprehension

List comprehension provides a short way to create lists.

### Normal Method

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

### List Comprehension

```python
numbers = [i for i in range(1, 6)]

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

---

## Even Numbers Using List Comprehension

```python
even = [i for i in range(1, 11) if i % 2 == 0]

print(even)
```

Output:

```text
[2, 4, 6, 8, 10]
```

---

## Squares Using List Comprehension

```python
squares = [i ** 2 for i in range(1, 6)]

print(squares)
```

Output:

```text
[1, 4, 9, 16, 25]
```

---

# 27. 💻 Important List Programs

## Program 1: Find Largest Element

```python
numbers = [10, 25, 5, 40, 15]

print(max(numbers))
```

Output:

```text
40
```

---

## Program 2: Find Smallest Element

```python
numbers = [10, 25, 5, 40, 15]

print(min(numbers))
```

Output:

```text
5
```

---

## Program 3: Find Sum

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

Output:

```text
100
```

---

## Program 4: Count Even Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

count = 0

for num in numbers:
    if num % 2 == 0:
        count += 1

print("Even count =", count)
```

Output:

```text
Even count = 3
```

---

## Program 5: Print Even Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

for num in numbers:
    if num % 2 == 0:
        print(num)
```

Output:

```text
2
4
6
```

---

## Program 6: Print Odd Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

for num in numbers:
    if num % 2 != 0:
        print(num)
```

Output:

```text
1
3
5
```

---

## Program 7: Find Average

```python
numbers = [10, 20, 30, 40, 50]

average = sum(numbers) / len(numbers)

print("Average =", average)
```

Output:

```text
Average = 30.0
```

---

## Program 8: Remove Duplicates

```python
numbers = [1, 2, 2, 3, 4, 4, 5]

unique = list(set(numbers))

print(unique)
```

> **Note:** A set does not preserve duplicates. If the original order must be preserved, use a different approach.

---

## Program 9: Find Duplicate Values

```python
numbers = [1, 2, 2, 3, 4, 4, 5]

duplicates = []

for num in numbers:
    if numbers.count(num) > 1 and num not in duplicates:
        duplicates.append(num)

print(duplicates)
```

Output:

```text
[2, 4]
```

---

## Program 10: Search an Element

```python
numbers = [10, 20, 30, 40]

search = int(input("Enter number: "))

if search in numbers:
    print("Element found")
else:
    print("Element not found")
```

---

# 28. 🎯 Important List Interview Questions

### Q1. What is a list?

**Answer:**
A list is an ordered, mutable collection of elements in Python.

---

### Q2. How do you create a list?

```python
numbers = [1, 2, 3, 4]
```

---

### Q3. Are lists mutable?

**Answer:**
Yes. List elements can be changed after creation.

```python
numbers = [1, 2, 3]

numbers[0] = 100
```

---

### Q4. Can a list contain duplicate values?

**Answer:**
Yes.

```python
numbers = [1, 2, 2, 3]
```

---

### Q5. Can a list contain different data types?

**Answer:**
Yes.

```python
data = [10, "Python", 3.14, True]
```

---

### Q6. Difference between `append()` and `extend()`?

**Answer:**

`append()` adds one object.

```python
a = [1, 2]
a.append([3, 4])

print(a)
```

```text
[1, 2, [3, 4]]
```

`extend()` adds each element from an iterable.

```python
a = [1, 2]
a.extend([3, 4])

print(a)
```

```text
[1, 2, 3, 4]
```

---

### Q7. Difference between `remove()` and `pop()`?

**Answer:**

* `remove()` removes by value.
* `pop()` removes by index and returns the removed element.

---

### Q8. How do you find the length of a list?

```python
len(numbers)
```

---

### Q9. How do you sort a list?

```python
numbers.sort()
```

---

### Q10. How do you reverse a list?

```python
numbers.reverse()
```

or:

```python
numbers[::-1]
```

---

# 29. 📝 Important Practice Questions

Try solving these without looking at the solution.

### Beginner

1. Create a list of five numbers.
2. Print the first element.
3. Print the last element.
4. Find the length of a list.
5. Add an element using `append()`.
6. Add an element using `insert()`.
7. Remove an element using `remove()`.
8. Remove an element using `pop()`.
9. Sort a list.
10. Reverse a list.

### Intermediate

11. Find the largest element without using `max()`.
12. Find the smallest element without using `min()`.
13. Find the sum without using `sum()`.
14. Count even numbers.
15. Count odd numbers.
16. Find duplicate elements.
17. Remove duplicate elements.
18. Find the second largest element.
19. Find the second smallest element.
20. Search for an element.
21. Find the frequency of an element.
22. Merge two lists.
23. Find common elements between two lists.
24. Separate even and odd numbers.
25. Create a list of squares.

### List Comprehension

26. Create numbers from 1 to 10.
27. Create even numbers from 1 to 20.
28. Create odd numbers from 1 to 20.
29. Create squares from 1 to 10.
30. Create numbers divisible by 5.

---

# 30. ⚡ Quick Revision

## List Syntax

```python
my_list = [10, 20, 30]
```

## Access

```python
my_list[0]
```

## Change

```python
my_list[0] = 100
```

## Add

```python
my_list.append(40)
```

## Insert

```python
my_list.insert(1, 50)
```

## Extend

```python
my_list.extend([60, 70])
```

## Remove

```python
my_list.remove(20)
```

## Pop

```python
my_list.pop()
```

## Length

```python
len(my_list)
```

## Sort

```python
my_list.sort()
```

## Reverse

```python
my_list.reverse()
```

## Check

```python
20 in my_list
```

## Slice

```python
my_list[1:4]
```

---

# 🧠 List Cheat Sheet

| Operation    | Syntax                |
| ------------ | --------------------- |
| Create       | `[]`                  |
| Access       | `list[index]`         |
| Change       | `list[index] = value` |
| Add          | `append()`            |
| Insert       | `insert()`            |
| Add multiple | `extend()`            |
| Remove value | `remove()`            |
| Remove index | `pop()`               |
| Delete       | `del`                 |
| Clear        | `clear()`             |
| Length       | `len()`               |
| Sort         | `sort()`              |
| Reverse      | `reverse()`           |
| Copy         | `copy()`              |
| Count        | `count()`             |
| Find index   | `index()`             |
| Membership   | `in`                  |
| Slice        | `list[start:end]`     |

---

# ⭐ Important Points

Remember:

```text
List
 ↓
Ordered
 ↓
Mutable
 ↓
Allows duplicates
 ↓
Allows different data types
 ↓
Uses []
 ↓
Index starts from 0
```

---

# 🚀 Learning Challenge

Before moving to the next topic, make sure you can independently:

* [ ] Create a list
* [ ] Access elements
* [ ] Use positive indexing
* [ ] Use negative indexing
* [ ] Change elements
* [ ] Add elements
* [ ] Remove elements
* [ ] Slice lists
* [ ] Loop through lists
* [ ] Sort lists
* [ ] Reverse lists
* [ ] Copy lists
* [ ] Work with nested lists
* [ ] Use list comprehension
* [ ] Solve basic list problems

---

# 🎯 Key Takeaway

> **Lists are one of the most important Python data structures.**

Master:

**Create → Access → Modify → Add → Remove → Iterate → Sort → Slice → Comprehension**

These concepts are essential for **Python programming, problem solving, DSA, coding tests, and technical interviews.**

---

```
```
