# 🐍 Python Beginners – Notes 7

## 📌 Topic: Lists in Python

---

# 1. What is a List?

A **list** is a collection of multiple values stored in a single variable.

Lists are:

* Ordered
* Changeable (Mutable)
* Allow duplicate values
* Can contain different data types

### Example

```python
fruits = ["apple", "banana", "mango"]

print(fruits)
```

### Output

```text
['apple', 'banana', 'mango']
```

---

# 2. Creating a List

A list is created using square brackets `[]`.

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

### Output

```text
[10, 20, 30, 40, 50]
```

---

# 3. Empty List

We can create an empty list.

```python
my_list = []

print(my_list)
```

### Output

```text
[]
```

---

# 4. List with Different Data Types

A list can contain different types of values.

```python
student = ["Yashu", 20, 85.5, True]

print(student)
```

### Output

```text
['Yashu', 20, 85.5, True]
```

A list can contain:

```text
String
Integer
Float
Boolean
Other Lists
```

---

# 5. List Indexing

Every element in a list has an index.

The index starts from `0`.

### Example

```python
fruits = ["apple", "banana", "mango", "orange"]

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

# 6. Negative Indexing

Python also supports negative indexing.

The last element has index `-1`.

```python
fruits = ["apple", "banana", "mango", "orange"]

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

# 7. Accessing List Elements

We can access an element using its index.

```python
numbers = [10, 20, 30, 40]

print(numbers[2])
```

### Output

```text
30
```

---

# 8. Changing List Elements

Lists are mutable, which means we can change their values.

```python
fruits = ["apple", "banana", "mango"]

fruits[1] = "orange"

print(fruits)
```

### Output

```text
['apple', 'orange', 'mango']
```

---

# 9. Adding Elements to a List

## Using append()

`append()` adds an element to the end of the list.

```python
fruits = ["apple", "banana"]

fruits.append("mango")

print(fruits)
```

### Output

```text
['apple', 'banana', 'mango']
```

---

# 10. Using insert()

`insert()` adds an element at a specific position.

### Syntax

```python
list.insert(index, value)
```

### Example

```python
fruits = ["apple", "mango"]

fruits.insert(1, "banana")

print(fruits)
```

### Output

```text
['apple', 'banana', 'mango']
```

---

# 11. Adding Multiple Elements Using extend()

`extend()` adds multiple elements to a list.

```python
fruits = ["apple", "banana"]

fruits.extend(["mango", "orange"])

print(fruits)
```

### Output

```text
['apple', 'banana', 'mango', 'orange']
```

---

# 12. Difference Between append() and extend()

### append()

Adds one object as a single element.

```python
numbers = [1, 2]

numbers.append([3, 4])

print(numbers)
```

Output:

```text
[1, 2, [3, 4]]
```

### extend()

Adds each element separately.

```python
numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

### Remember

```text
append() → adds one element
extend() → adds multiple elements
```

---

# 13. Removing Elements

## Using remove()

`remove()` removes a specific value.

```python
fruits = ["apple", "banana", "mango"]

fruits.remove("banana")

print(fruits)
```

### Output

```text
['apple', 'mango']
```

---

# 14. Using pop()

`pop()` removes an element using its index.

```python
fruits = ["apple", "banana", "mango"]

fruits.pop(1)

print(fruits)
```

### Output

```text
['apple', 'mango']
```

If no index is given, `pop()` removes the last element.

```python
fruits = ["apple", "banana", "mango"]

fruits.pop()

print(fruits)
```

### Output

```text
['apple', 'banana']
```

---

# 15. Using del

The `del` keyword can delete an element.

```python
fruits = ["apple", "banana", "mango"]

del fruits[1]

print(fruits)
```

### Output

```text
['apple', 'mango']
```

---

# 16. clear()

`clear()` removes all elements from a list.

```python
fruits = ["apple", "banana", "mango"]

fruits.clear()

print(fruits)
```

### Output

```text
[]
```

---

# 17. Finding Length of a List

Use the `len()` function.

```python
fruits = ["apple", "banana", "mango"]

print(len(fruits))
```

### Output

```text
3
```

---

# 18. Checking if an Element Exists

Use the `in` operator.

```python
fruits = ["apple", "banana", "mango"]

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

# 19. Checking if an Element Does Not Exist

Use `not in`.

```python
fruits = ["apple", "banana", "mango"]

print("orange" not in fruits)
```

### Output

```text
True
```

---

# 20. Loop Through a List

We can use a `for` loop to access every element.

```python
fruits = ["apple", "banana", "mango"]

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

# 21. Loop Through Numbers

```python
numbers = [10, 20, 30, 40]

for number in numbers:
    print(number)
```

### Output

```text
10
20
30
40
```

---

# 22. List with if Condition

```python
numbers = [10, 15, 20, 25, 30]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

### Output

```text
10
20
30
```

---

# 23. List Slicing

Slicing is used to get a portion of a list.

### Syntax

```python
list[start:end]
```

The ending index is not included.

### Example

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
```

### Output

```text
[20, 30, 40]
```

---

# 24. List Slicing from Beginning

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[:3])
```

### Output

```text
[10, 20, 30]
```

---

# 25. List Slicing to End

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[2:])
```

### Output

```text
[30, 40, 50]
```

---

# 26. Negative Slicing

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[-3:])
```

### Output

```text
[30, 40, 50]
```

---

# 27. List Step

We can specify a step value.

### Syntax

```python
list[start:end:step]
```

### Example

```python
numbers = [1, 2, 3, 4, 5, 6]

print(numbers[::2])
```

### Output

```text
[1, 3, 5]
```

---

# 28. Reverse a List Using Slicing

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[::-1])
```

### Output

```text
[5, 4, 3, 2, 1]
```

---

# 29. sort()

`sort()` arranges elements in ascending order.

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
```

### Output

```text
[10, 20, 30, 40, 50]
```

---

# 30. Sorting in Descending Order

Use `reverse=True`.

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort(reverse=True)

print(numbers)
```

### Output

```text
[50, 40, 30, 20, 10]
```

---

# 31. reverse()

`reverse()` reverses the existing list.

```python
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
```

### Output

```text
[5, 4, 3, 2, 1]
```

---

# 32. count()

`count()` counts how many times a value occurs.

```python
numbers = [10, 20, 10, 30, 10]

print(numbers.count(10))
```

### Output

```text
3
```

---

# 33. index()

`index()` returns the position of the first occurrence of a value.

```python
fruits = ["apple", "banana", "mango"]

print(fruits.index("banana"))
```

### Output

```text
1
```

---

# 34. copy()

`copy()` creates a copy of a list.

```python
numbers = [10, 20, 30]

new_numbers = numbers.copy()

print(new_numbers)
```

### Output

```text
[10, 20, 30]
```

---

# 35. Copying a List

```python
numbers = [1, 2, 3]

new_numbers = numbers

print(new_numbers)
```

Both variables refer to the same list.

For an independent copy, use:

```python
new_numbers = numbers.copy()
```

---

# 36. Nested Lists

A list can contain another list.

This is called a **nested list**.

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6]
]

print(numbers)
```

### Output

```text
[[1, 2, 3], [4, 5, 6]]
```

---

# 37. Accessing Nested Lists

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6]
]

print(numbers[0][1])
```

### Output

```text
2
```

Explanation:

```text
numbers[0] → [1, 2, 3]
numbers[0][1] → 2
```

---

# 38. List Concatenation

Two lists can be joined using `+`.

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]

result = list1 + list2

print(result)
```

### Output

```text
[1, 2, 3, 4, 5, 6]
```

---

# 39. Repeating a List

We can repeat a list using `*`.

```python
numbers = [1, 2, 3]

print(numbers * 2)
```

### Output

```text
[1, 2, 3, 1, 2, 3]
```

---

# 40. Taking List Input from User

We can create a list using `input()`.

### Example

```python
numbers = input("Enter numbers: ").split()

print(numbers)
```

If the user enters:

```text
10 20 30
```

Output:

```text
['10', '20', '30']
```

Notice that the values are strings.

---

# 41. Converting Input to Integers

```python
numbers = list(map(int, input("Enter numbers: ").split()))

print(numbers)
```

If input is:

```text
10 20 30
```

Output:

```text
[10, 20, 30]
```

---

# 42. Finding Maximum Value

Use `max()`.

```python
numbers = [10, 50, 30, 20, 40]

print(max(numbers))
```

### Output

```text
50
```

---

# 43. Finding Minimum Value

Use `min()`.

```python
numbers = [10, 50, 30, 20, 40]

print(min(numbers))
```

### Output

```text
10
```

---

# 44. Finding Sum

Use `sum()`.

```python
numbers = [10, 20, 30, 40]

print(sum(numbers))
```

### Output

```text
100
```

---

# 45. List Comprehension

List comprehension provides a short way to create lists.

### Normal Method

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

### Output

```text
[1, 2, 3, 4, 5]
```

### Using List Comprehension

```python
numbers = [i for i in range(1, 6)]

print(numbers)
```

### Output

```text
[1, 2, 3, 4, 5]
```

---

# 46. List Comprehension with Condition

```python
even_numbers = [i for i in range(1, 11) if i % 2 == 0]

print(even_numbers)
```

### Output

```text
[2, 4, 6, 8, 10]
```

---

# 47. Square Using List Comprehension

```python
squares = [i * i for i in range(1, 6)]

print(squares)
```

### Output

```text
[1, 4, 9, 16, 25]
```

---

# 48. List Methods Summary

| Method      | Purpose                                |
| ----------- | -------------------------------------- |
| `append()`  | Adds an element at the end             |
| `insert()`  | Adds an element at a specific position |
| `extend()`  | Adds multiple elements                 |
| `remove()`  | Removes a specific value               |
| `pop()`     | Removes an element by index            |
| `clear()`   | Removes all elements                   |
| `sort()`    | Sorts the list                         |
| `reverse()` | Reverses the list                      |
| `count()`   | Counts occurrences                     |
| `index()`   | Finds the index                        |
| `copy()`    | Creates a copy                         |

---

# 49. Useful List Functions

| Function   | Purpose                    |
| ---------- | -------------------------- |
| `len()`    | Finds number of elements   |
| `max()`    | Finds largest value        |
| `min()`    | Finds smallest value       |
| `sum()`    | Finds total                |
| `sorted()` | Returns a sorted list      |
| `list()`   | Creates/converts to a list |

---

# 50. Common Mistakes

## Mistake 1: Wrong Index

```python
numbers = [10, 20, 30]

print(numbers[3])
```

This causes:

```text
IndexError
```

Valid indexes are:

```text
0
1
2
```

---

## Mistake 2: Forgetting That Index Starts at 0

```python
numbers = [10, 20, 30]

print(numbers[0])
```

Output:

```text
10
```

Not `20`.

---

## Mistake 3: Using remove() with an Index

Wrong:

```python
numbers = [10, 20, 30]

numbers.remove(1)
```

`remove()` searches for a value.

Correct:

```python
numbers.remove(20)
```

For an index, use:

```python
numbers.pop(1)
```

---

# 51. Practice Programs

## Program 1: Print All Elements

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

---

## Program 2: Find Sum of List

```python
numbers = [10, 20, 30, 40, 50]

print("Sum:", sum(numbers))
```

### Output

```text
Sum: 150
```

---

## Program 3: Find Largest Number

```python
numbers = [10, 50, 20, 40, 30]

print("Largest:", max(numbers))
```

### Output

```text
Largest: 50
```

---

## Program 4: Find Smallest Number

```python
numbers = [10, 50, 20, 40, 30]

print("Smallest:", min(numbers))
```

### Output

```text
Smallest: 10
```

---

## Program 5: Count Even Numbers

```python
numbers = [10, 15, 20, 25, 30, 35]

count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
```

### Output

```text
Even numbers: 3
```

---

## Program 6: Print Even Numbers

```python
numbers = [10, 15, 20, 25, 30, 35]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

### Output

```text
10
20
30
```

---

## Program 7: Print Odd Numbers

```python
numbers = [10, 15, 20, 25, 30, 35]

for number in numbers:
    if number % 2 != 0:
        print(number)
```

### Output

```text
15
25
35
```

---

## Program 8: Reverse a List

```python
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
```

### Output

```text
[5, 4, 3, 2, 1]
```

---

## Program 9: Sort a List

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
```

### Output

```text
[10, 20, 30, 40, 50]
```

---

## Program 10: Search an Element

```python
numbers = [10, 20, 30, 40, 50]

search = int(input("Enter number to search: "))

if search in numbers:
    print("Number found")
else:
    print("Number not found")
```

---

# 52. Mini Project – Student Marks

```python
marks = [85, 90, 78, 92, 88]

print("Marks:", marks)
print("Total:", sum(marks))
print("Highest:", max(marks))
print("Lowest:", min(marks))
print("Number of subjects:", len(marks))
print("Average:", sum(marks) / len(marks))
```

### Example Output

```text
Marks: [85, 90, 78, 92, 88]
Total: 433
Highest: 92
Lowest: 78
Number of subjects: 5
Average: 86.6
```

---

# 53. Mini Project – Shopping List

```python
shopping_list = []

while True:
    item = input("Enter item (or type 'done'): ")

    if item.lower() == "done":
        break

    shopping_list.append(item)

print("\nShopping List:")

for item in shopping_list:
    print("-", item)
```

### Example

```text
Enter item (or type 'done'): Rice
Enter item (or type 'done'): Milk
Enter item (or type 'done'): Apples
Enter item (or type 'done'): done

Shopping List:
- Rice
- Milk
- Apples
```

---

# 54. Quick Revision

### Create a List

```python
fruits = ["apple", "banana", "mango"]
```

### Access

```python
print(fruits[0])
```

### Change

```python
fruits[0] = "orange"
```

### Add

```python
fruits.append("grapes")
```

### Insert

```python
fruits.insert(1, "banana")
```

### Remove

```python
fruits.remove("banana")
```

### Delete by Index

```python
fruits.pop(0)
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

### Check

```python
"apple" in fruits
```

### Loop

```python
for fruit in fruits:
    print(fruit)
```

---

# 55. Key Points to Remember ⭐

* A list stores multiple values.
* Lists are created using `[]`.
* List indexing starts from `0`.
* Negative indexing starts from `-1`.
* Lists are mutable.
* Lists allow duplicate values.
* Lists can contain different data types.
* `append()` adds one element.
* `insert()` adds an element at a specific position.
* `extend()` adds multiple elements.
* `remove()` removes a value.
* `pop()` removes an element using its index.
* `clear()` removes all elements.
* `sort()` sorts the list.
* `reverse()` reverses the list.
* `len()` finds the number of elements.
* `max()` finds the largest value.
* `min()` finds the smallest value.
* `sum()` calculates the total.
* `in` checks whether an element exists.
* List comprehension provides a short way to create lists.

---

# 📝 Notes 7 Practice Questions

## Basic Questions

1. What is a list in Python?
2. How do you create a list?
3. What is the first index of a list?
4. What is negative indexing?
5. Are Python lists mutable?
6. Can a list contain different data types?
7. What is the use of `append()`?
8. What is the use of `insert()`?
9. What is the use of `extend()`?
10. What is the difference between `remove()` and `pop()`?

## Programming Questions

11. Create a list of five numbers and print it.
12. Print the first element of a list.
13. Print the last element using negative indexing.
14. Change an element in a list.
15. Add an element using `append()`.
16. Insert an element at a specific position.
17. Remove an element from a list.
18. Find the length of a list.
19. Find the largest number in a list.
20. Find the smallest number in a list.
21. Find the sum of all numbers in a list.
22. Count how many even numbers are in a list.
23. Print all odd numbers from a list.
24. Reverse a list.
25. Sort a list in ascending order.
26. Sort a list in descending order.
27. Search for an element in a list.
28. Create a nested list.
29. Create a list using list comprehension.
30. Create a student marks program using a list.

---

# 🎯 Important Interview Questions

### Q1. What is a list?

A list is an ordered and mutable collection of elements in Python.

### Q2. How are lists created?

Using square brackets:

```python
numbers = [1, 2, 3]
```

### Q3. Are lists mutable?

Yes. We can change their elements after creation.

### Q4. What is the difference between append() and extend()?

```text
append() → adds one element
extend() → adds multiple elements
```

### Q5. What is the difference between remove() and pop()?

```text
remove() → removes a value
pop()    → removes an element using its index
```

### Q6. What is list slicing?

List slicing extracts a portion of a list.

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[1:4])
```

Output:

```text
[2, 3, 4]
```
