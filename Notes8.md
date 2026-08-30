Here is the complete **`Notes8.md`**, continuing your Python Beginners series with **Tuples in Python**.

# 🐍 Python Beginners – Notes 8

## 📌 Topic: Tuples in Python

---

# 1. What is a Tuple?

A **tuple** is a collection of multiple values stored in a single variable.

A tuple is:

* Ordered
* Immutable (Cannot be changed)
* Allows duplicate values
* Can contain different data types
* Can contain another tuple or list

### Example

```python
fruits = ("apple", "banana", "mango")

print(fruits)
```

### Output

```text
('apple', 'banana', 'mango')
```

---

# 2. Creating a Tuple

Tuples are usually created using parentheses `()`.

```python
numbers = (10, 20, 30, 40, 50)

print(numbers)
```

### Output

```text
(10, 20, 30, 40, 50)
```

---

# 3. Empty Tuple

We can create an empty tuple.

```python
my_tuple = ()

print(my_tuple)
```

### Output

```text
()
```

---

# 4. Tuple with Different Data Types

A tuple can contain different types of values.

```python
student = ("Yashu", 20, 85.5, True)

print(student)
```

### Output

```text
('Yashu', 20, 85.5, True)
```

A tuple can contain:

```text
String
Integer
Float
Boolean
List
Tuple
```

---

# 5. Single Element Tuple

There is an important rule when creating a tuple with only one element.

### Wrong

```python
number = (10)
```

This is an integer, not a tuple.

### Correct

```python
number = (10,)

print(type(number))
```

### Output

```text
<class 'tuple'>
```

The comma `,` makes it a tuple.

---

# 6. Tuple Indexing

Every element in a tuple has an index.

The index starts from `0`.

### Example

```python
fruits = ("apple", "banana", "mango", "orange")

print(fruits[0])
print(fruits[1])
print(fruits[2])
print(fruits[3])
```

### Output

```text
apple
banana
mango
orange
```

### Index Positions

```text
apple   → 0
banana  → 1
mango   → 2
orange  → 3
```

---

# 7. Negative Indexing

Tuples support negative indexing.

The last element has index `-1`.

```python
fruits = ("apple", "banana", "mango", "orange")

print(fruits[-1])
print(fruits[-2])
```

### Output

```text
orange
mango
```

### Negative Index Positions

```text
apple   → -4
banana  → -3
mango   → -2
orange  → -1
```

---

# 8. Accessing Tuple Elements

We can access elements using their index.

```python
numbers = (10, 20, 30, 40)

print(numbers[2])
```

### Output

```text
30
```

---

# 9. Tuple is Immutable

**Immutable** means the values cannot be changed after the tuple is created.

### Example

```python
numbers = (10, 20, 30)

numbers[1] = 50
```

This produces an error:

```text
TypeError
```

We cannot directly change a tuple element.

---

# 10. List vs Tuple

### List

```python
numbers = [10, 20, 30]

numbers[1] = 50
```

This is allowed.

### Tuple

```python
numbers = (10, 20, 30)

numbers[1] = 50
```

This is not allowed.

### Remember

```text
List  → Mutable
Tuple → Immutable
```

---

# 11. Tuple Slicing

We can extract a portion of a tuple using slicing.

### Syntax

```python
tuple[start:end]
```

The ending index is not included.

### Example

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
```

### Output

```text
(20, 30, 40)
```

---

# 12. Tuple Slicing from Beginning

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[:3])
```

### Output

```text
(10, 20, 30)
```

---

# 13. Tuple Slicing to End

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[2:])
```

### Output

```text
(30, 40, 50)
```

---

# 14. Negative Slicing

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[-3:])
```

### Output

```text
(30, 40, 50)
```

---

# 15. Tuple Step

We can specify a step value.

### Syntax

```python
tuple[start:end:step]
```

### Example

```python
numbers = (1, 2, 3, 4, 5, 6)

print(numbers[::2])
```

### Output

```text
(1, 3, 5)
```

---

# 16. Reverse a Tuple Using Slicing

```python
numbers = (1, 2, 3, 4, 5)

print(numbers[::-1])
```

### Output

```text
(5, 4, 3, 2, 1)
```

---

# 17. len() Function

The `len()` function returns the number of elements in a tuple.

```python
fruits = ("apple", "banana", "mango")

print(len(fruits))
```

### Output

```text
3
```

---

# 18. Checking an Element

Use the `in` operator to check whether an element exists.

```python
fruits = ("apple", "banana", "mango")

print("banana" in fruits)
```

### Output

```text
True
```

Example:

```python
print("orange" in fruits)
```

Output:

```text
False
```

---

# 19. not in Operator

Use `not in` to check whether an element does not exist.

```python
fruits = ("apple", "banana", "mango")

print("orange" not in fruits)
```

### Output

```text
True
```

---

# 20. Loop Through a Tuple

We can use a `for` loop to access every element.

```python
fruits = ("apple", "banana", "mango")

for fruit in fruits:
    print(fruit)
```

### Output

```text
apple
banana
mango
```

---

# 21. Loop Using Index

We can use `range()` and `len()` to access tuple elements.

```python
numbers = (10, 20, 30, 40)

for i in range(len(numbers)):
    print(numbers[i])
```

### Output

```text
10
20
30
40
```

---

# 22. count() Method

The `count()` method counts how many times a value appears.

```python
numbers = (10, 20, 10, 30, 10)

print(numbers.count(10))
```

### Output

```text
3
```

---

# 23. index() Method

The `index()` method returns the position of the first occurrence of a value.

```python
fruits = ("apple", "banana", "mango")

print(fruits.index("banana"))
```

### Output

```text
1
```

---

# 24. Tuple Concatenation

We can join two tuples using `+`.

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)

result = tuple1 + tuple2

print(result)
```

### Output

```text
(1, 2, 3, 4, 5, 6)
```

---

# 25. Repeating a Tuple

We can repeat a tuple using `*`.

```python
numbers = (1, 2, 3)

print(numbers * 2)
```

### Output

```text
(1, 2, 3, 1, 2, 3)
```

---

# 26. Nested Tuple

A tuple can contain another tuple.

This is called a **nested tuple**.

```python
numbers = (
    (1, 2, 3),
    (4, 5, 6)
)

print(numbers)
```

### Output

```text
((1, 2, 3), (4, 5, 6))
```

---

# 27. Accessing Nested Tuple

```python
numbers = (
    (1, 2, 3),
    (4, 5, 6)
)

print(numbers[0][1])
```

### Output

```text
2
```

Explanation:

```text
numbers[0]     → (1, 2, 3)
numbers[0][1]  → 2
```

---

# 28. Tuple Packing

Putting multiple values into a single tuple is called **tuple packing**.

```python
student = "Yashu", 20, "CSE"

print(student)
```

### Output

```text
('Yashu', 20, 'CSE')
```

Python automatically creates a tuple.

---

# 29. Tuple Unpacking

Taking values from a tuple and storing them in separate variables is called **tuple unpacking**.

```python
student = ("Yashu", 20, "CSE")

name, age, course = student

print(name)
print(age)
print(course)
```

### Output

```text
Yashu
20
CSE
```

---

# 30. Unpacking with *

The `*` operator can collect multiple values.

```python
numbers = (10, 20, 30, 40, 50)

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

### Output

```text
10
[20, 30, 40]
50
```

Notice that `middle` becomes a list.

---

# 31. Converting List to Tuple

Use the `tuple()` function.

```python
numbers = [10, 20, 30, 40]

numbers_tuple = tuple(numbers)

print(numbers_tuple)
```

### Output

```text
(10, 20, 30, 40)
```

---

# 32. Converting Tuple to List

Use the `list()` function.

```python
numbers = (10, 20, 30, 40)

numbers_list = list(numbers)

print(numbers_list)
```

### Output

```text
[10, 20, 30, 40]
```

Now we can modify the list.

```python
numbers_list[1] = 50

print(numbers_list)
```

### Output

```text
[10, 50, 30, 40]
```

---

# 33. Modifying a Tuple Indirectly

Although tuples are immutable, we can convert them to a list, modify the list, and convert it back.

```python
numbers = (10, 20, 30)

temp = list(numbers)

temp[1] = 50

numbers = tuple(temp)

print(numbers)
```

### Output

```text
(10, 50, 30)
```

---

# 34. max() Function

The `max()` function finds the largest value.

```python
numbers = (10, 50, 30, 20, 40)

print(max(numbers))
```

### Output

```text
50
```

---

# 35. min() Function

The `min()` function finds the smallest value.

```python
numbers = (10, 50, 30, 20, 40)

print(min(numbers))
```

### Output

```text
10
```

---

# 36. sum() Function

The `sum()` function calculates the total.

```python
numbers = (10, 20, 30, 40)

print(sum(numbers))
```

### Output

```text
100
```

---

# 37. sorted() Function

The `sorted()` function returns a sorted list.

```python
numbers = (50, 10, 40, 20, 30)

result = sorted(numbers)

print(result)
```

### Output

```text
[10, 20, 30, 40, 50]
```

### Important

`sorted()` returns a **list**, not a tuple.

---

# 38. Sorting in Descending Order

```python
numbers = (50, 10, 40, 20, 30)

result = sorted(numbers, reverse=True)

print(result)
```

### Output

```text
[50, 40, 30, 20, 10]
```

---

# 39. Tuple with a List

A tuple can contain a list.

```python
data = ("Yashu", [80, 90, 85])

print(data)
```

### Output

```text
('Yashu', [80, 90, 85])
```

The tuple itself cannot be changed, but the list inside it can be modified.

```python
data[1][0] = 95

print(data)
```

### Output

```text
('Yashu', [95, 90, 85])
```

---

# 40. Tuple with a Dictionary

A tuple can also contain a dictionary.

```python
student = (
    "Yashu",
    {"Python": 90, "Java": 85}
)

print(student)
```

### Output

```text
('Yashu', {'Python': 90, 'Java': 85})
```

---

# 41. Tuple Comparison

Tuples can be compared using comparison operators.

```python
tuple1 = (1, 2, 3)
tuple2 = (1, 2, 4)

print(tuple1 == tuple2)
print(tuple1 < tuple2)
```

### Output

```text
False
True
```

Python compares elements from left to right.

---

# 42. Membership Operators

The `in` and `not in` operators work with tuples.

```python
numbers = (10, 20, 30, 40)

print(20 in numbers)
print(50 not in numbers)
```

### Output

```text
True
True
```

---

# 43. Tuple Methods

Tuples have only two main built-in methods.

## count()

Counts occurrences.

```python
numbers = (1, 2, 2, 3, 2)

print(numbers.count(2))
```

Output:

```text
3
```

## index()

Finds the first index.

```python
numbers = (10, 20, 30)

print(numbers.index(20))
```

Output:

```text
1
```

---

# 44. Why Use Tuples?

Tuples are useful when:

* Data should not be changed
* We want to protect values from accidental modification
* We want to represent fixed data
* We need to return multiple values from a function
* We need an immutable collection

### Example

```python
coordinates = (12.9716, 77.5946)
```

Coordinates can be stored as a tuple because the pair of values represents fixed data.

---

# 45. List vs Tuple

| Feature              | List            | Tuple      |
| -------------------- | --------------- | ---------- |
| Syntax               | `[]`            | `()`       |
| Mutable              | Yes             | No         |
| Ordered              | Yes             | Yes        |
| Duplicates           | Allowed         | Allowed    |
| Different data types | Yes             | Yes        |
| Add elements         | Yes             | No         |
| Remove elements      | Yes             | No         |
| Change elements      | Yes             | No         |
| Methods              | Many            | Few        |
| Typical use          | Changeable data | Fixed data |

---

# 46. Tuple vs String

Both tuples and strings are sequences.

### String

```python
name = "Yashu"
```

### Tuple

```python
name = ("Y", "a", "s", "h", "u")
```

Both support:

* Indexing
* Slicing
* `len()`
* `in`
* Loops

But their elements are different types of data.

---

# 47. Tuple as Function Return Value

A function can return multiple values as a tuple.

```python
def calculate(a, b):
    return a + b, a - b

result = calculate(10, 5)

print(result)
```

### Output

```text
(15, 5)
```

We can unpack the result.

```python
def calculate(a, b):
    return a + b, a - b

addition, subtraction = calculate(10, 5)

print(addition)
print(subtraction)
```

### Output

```text
15
5
```

---

# 48. Tuple Input from User

We can take multiple values and convert them into a tuple.

```python
numbers = tuple(map(int, input("Enter numbers: ").split()))

print(numbers)
```

If the input is:

```text
10 20 30 40
```

Output:

```text
(10, 20, 30, 40)
```

---

# 49. Common Mistakes

## Mistake 1: Trying to Change a Tuple

Wrong:

```python
numbers = (10, 20, 30)

numbers[1] = 50
```

This gives:

```text
TypeError
```

Because tuples are immutable.

---

## Mistake 2: Forgetting the Comma

Wrong:

```python
number = (10)
```

This is an integer.

Correct:

```python
number = (10,)
```

---

## Mistake 3: Using List Methods on a Tuple

Wrong:

```python
numbers = (10, 20, 30)

numbers.append(40)
```

This gives:

```text
AttributeError
```

Tuples do not have `append()`.

---

# 50. Practice Programs

## Program 1: Create a Tuple

```python
fruits = ("apple", "banana", "mango")

print(fruits)
```

---

## Program 2: Print First and Last Element

```python
fruits = ("apple", "banana", "mango", "orange")

print("First:", fruits[0])
print("Last:", fruits[-1])
```

### Output

```text
First: apple
Last: orange
```

---

## Program 3: Find Length

```python
numbers = (10, 20, 30, 40, 50)

print("Length:", len(numbers))
```

---

## Program 4: Find Sum

```python
numbers = (10, 20, 30, 40, 50)

print("Sum:", sum(numbers))
```

### Output

```text
Sum: 150
```

---

## Program 5: Find Largest Number

```python
numbers = (10, 50, 20, 40, 30)

print("Largest:", max(numbers))
```

### Output

```text
Largest: 50
```

---

## Program 6: Find Smallest Number

```python
numbers = (10, 50, 20, 40, 30)

print("Smallest:", min(numbers))
```

### Output

```text
Smallest: 10
```

---

## Program 7: Count an Element

```python
numbers = (10, 20, 10, 30, 10)

print("10 occurs:", numbers.count(10), "times")
```

### Output

```text
10 occurs: 3 times
```

---

## Program 8: Search an Element

```python
fruits = ("apple", "banana", "mango")

search = input("Enter fruit: ")

if search in fruits:
    print("Fruit found")
else:
    print("Fruit not found")
```

---

## Program 9: Reverse a Tuple

```python
numbers = (1, 2, 3, 4, 5)

print(numbers[::-1])
```

### Output

```text
(5, 4, 3, 2, 1)
```

---

## Program 10: Tuple Unpacking

```python
student = ("Yashu", 20, "CSE")

name, age, course = student

print("Name:", name)
print("Age:", age)
print("Course:", course)
```

### Output

```text
Name: Yashu
Age: 20
Course: CSE
```

---

# 51. Mini Project – Student Information

```python
student = (
    "Yashu",
    20,
    "CSE",
    85
)

name, age, course, marks = student

print("Student Information")
print("-------------------")
print("Name:", name)
print("Age:", age)
print("Course:", course)
print("Marks:", marks)
```

### Output

```text
Student Information
-------------------
Name: Yashu
Age: 20
Course: CSE
Marks: 85
```

---

# 52. Mini Project – Student Marks

```python
marks = (85, 90, 78, 92, 88)

total = sum(marks)
highest = max(marks)
lowest = min(marks)
average = total / len(marks)

print("Marks:", marks)
print("Total:", total)
print("Highest:", highest)
print("Lowest:", lowest)
print("Average:", average)
```

### Output

```text
Marks: (85, 90, 78, 92, 88)
Total: 433
Highest: 92
Lowest: 78
Average: 86.6
```

---

# 53. Quick Revision

### Create a Tuple

```python
fruits = ("apple", "banana", "mango")
```

### Access

```python
print(fruits[0])
```

### Negative Index

```python
print(fruits[-1])
```

### Length

```python
print(len(fruits))
```

### Check

```python
print("apple" in fruits)
```

### Count

```python
print(fruits.count("apple"))
```

### Index

```python
print(fruits.index("banana"))
```

### Loop

```python
for fruit in fruits:
    print(fruit)
```

### Slice

```python
print(fruits[1:3])
```

### Reverse

```python
print(fruits[::-1])
```

### Convert List to Tuple

```python
numbers = tuple([1, 2, 3])
```

### Convert Tuple to List

```python
numbers = list((1, 2, 3))
```

---

# 54. Important Tuple Terms

| Term      | Meaning                               |
| --------- | ------------------------------------- |
| Tuple     | Ordered immutable collection          |
| Immutable | Cannot be changed                     |
| Index     | Position of an element                |
| Slicing   | Extracting part of a tuple            |
| Packing   | Creating a tuple from multiple values |
| Unpacking | Assigning tuple values to variables   |
| `count()` | Counts an element                     |
| `index()` | Finds the first position              |
| `tuple()` | Converts to tuple                     |
| `list()`  | Converts to list                      |

---

# 55. Key Points to Remember ⭐

* A tuple is an ordered collection.
* Tuples are created using `()`.
* Tuple indexing starts from `0`.
* Negative indexing starts from `-1`.
* Tuples are immutable.
* Tuples allow duplicate values.
* Tuples can contain different data types.
* A single-element tuple requires a comma.
* `count()` counts occurrences.
* `index()` finds the first occurrence.
* Tuples support slicing.
* Tuples support loops.
* Tuples support `in` and `not in`.
* Tuples can be nested.
* Tuples support packing and unpacking.
* `tuple()` converts data into a tuple.
* `list()` can convert a tuple into a list.
* `max()`, `min()`, `sum()`, and `len()` work with numeric tuples.
* `sorted()` returns a list.
* Tuples are useful for fixed data.

---

# 📝 Notes 8 Practice Questions

## Basic Questions

1. What is a tuple in Python?
2. How do you create a tuple?
3. What is the difference between a list and a tuple?
4. Are tuples mutable?
5. What is tuple indexing?
6. What is negative indexing?
7. What is tuple slicing?
8. What is tuple packing?
9. What is tuple unpacking?
10. Why is a comma required for a single-element tuple?

## Programming Questions

11. Create a tuple containing five numbers.
12. Print the first element of a tuple.
13. Print the last element using negative indexing.
14. Find the length of a tuple.
15. Find the largest value in a tuple.
16. Find the smallest value in a tuple.
17. Find the sum of all values in a tuple.
18. Count how many times an element occurs.
19. Find the index of an element.
20. Reverse a tuple using slicing.
21. Check whether an element exists in a tuple.
22. Convert a list into a tuple.
23. Convert a tuple into a list.
24. Create a nested tuple.
25. Perform tuple unpacking.
26. Return multiple values from a function using a tuple.
27. Take tuple values as user input.
28. Sort a tuple using `sorted()`.
29. Create a student information tuple.
30. Create a student marks program using a tuple.

---

# 🎯 Important Interview Questions

### Q1. What is a tuple?

A tuple is an ordered and immutable collection of elements in Python.

### Q2. How is a tuple created?

Using parentheses:

```python
numbers = (1, 2, 3)
```

### Q3. Are tuples mutable?

No. Tuples are immutable.

### Q4. What is the difference between a list and a tuple?

```text
List  → Mutable
Tuple → Immutable
```

### Q5. How do you create a single-element tuple?

Use a comma:

```python
number = (10,)
```

### Q6. How do you access tuple elements?

Using indexes:

```python
numbers = (10, 20, 30)

print(numbers[1])
```

Output:

```text
20
```

### Q7. What are the main tuple methods?

```text
count()
index()
```

### Q8. Can a tuple contain a list?

Yes.

```python
data = ("Yashu", [80, 90, 85])
```

### Q9. Can a tuple be converted into a list?

Yes.

```python
numbers = (1, 2, 3)

numbers = list(numbers)
```

### Q10. What is tuple unpacking?

Tuple unpacking means assigning tuple values to separate variables.

```python
student = ("Yashu", 20, "CSE")

name, age, course = student
```
