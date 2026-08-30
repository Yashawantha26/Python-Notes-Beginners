# 🐍 Python Notes 2 — Control Flow

> Learn how to make Python programs take decisions and repeat tasks.

---

## 📌 Topics

1. What is Control Flow?
2. `if` Statement
3. `if-else`
4. `if-elif-else`
5. Nested `if`
6. Comparison Operators
7. Logical Operators
8. `for` Loop
9. `while` Loop
10. `range()`
11. `break`
12. `continue`
13. `pass`
14. Nested Loops
15. Practice Programs
16. Quick Revision

---

# 1. 🔄 What is Control Flow?

Control flow determines **which statements Python executes and in what order**.

Normally:

```python
print("A")
print("B")
print("C")
```

Output:

```text
A
B
C
```

But sometimes we need to make decisions or repeat code.

Python provides:

```text
if
elif
else
for
while
break
continue
pass
```

---

# 2. 🤔 `if` Statement

The `if` statement executes code only when a condition is `True`.

### Syntax

```python
if condition:
    statement
```

### Example

```python
age = 20

if age >= 18:
    print("You are eligible")
```

Output:

```text
You are eligible
```

---

# 3. ⚠️ Indentation

Python uses indentation to identify a block of code.

Correct:

```python
age = 20

if age >= 18:
    print("Adult")
```

Incorrect:

```python
age = 20

if age >= 18:
print("Adult")
```

Usually, use **4 spaces** for indentation.

---

# 4. 🔀 `if-else`

Use `else` when you want an alternative.

### Example

```python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

### Structure

```text
          Condition
              ↓
         ┌── True ──→ if block
         │
Condition
         │
         └── False ─→ else block
```

---

# 5. 🔀 `if-elif-else`

Use `elif` when there are multiple conditions.

### Example

```python
marks = 75

if marks >= 90:
    print("A+")
elif marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
elif marks >= 60:
    print("C")
else:
    print("Fail")
```

Output:

```text
B
```

Python checks conditions from **top to bottom**.

Once a condition is true, the remaining conditions are skipped.

---

# 6. 🪆 Nested `if`

An `if` statement inside another `if` statement is called a nested `if`.

### Example

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Output:

```text
Entry allowed
```

---

# 7. 🔍 Comparison Operators

Comparison operators return `True` or `False`.

| Operator | Meaning               | Example  |
| -------- | --------------------- | -------- |
| `==`     | Equal                 | `5 == 5` |
| `!=`     | Not equal             | `5 != 3` |
| `>`      | Greater than          | `5 > 3`  |
| `<`      | Less than             | `3 < 5`  |
| `>=`     | Greater than or equal | `5 >= 5` |
| `<=`     | Less than or equal    | `3 <= 5` |

### Example

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

# 8. 🧠 Logical Operators

Python has three important logical operators.

```text
and
or
not
```

---

## `and`

Both conditions must be true.

```python
age = 20

if age >= 18 and age <= 30:
    print("Eligible")
```

Output:

```text
Eligible
```

---

## `or`

At least one condition must be true.

```python
day = "Sunday"

if day == "Saturday" or day == "Sunday":
    print("Weekend")
```

Output:

```text
Weekend
```

---

## `not`

Reverses a Boolean result.

```python
is_raining = False

if not is_raining:
    print("Go outside")
```

Output:

```text
Go outside
```

---

# 9. 🎯 Membership Operators

Membership operators check whether a value exists inside a sequence.

```text
in
not in
```

### Example

```python
name = "Python"

print("P" in name)
```

Output:

```text
True
```

Another example:

```python
fruits = ["apple", "banana", "mango"]

print("apple" in fruits)
```

Output:

```text
True
```

---

# 10. 🔁 `for` Loop

A `for` loop is used to repeat code for each item in a sequence.

### Example

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

---

# 11. 📏 `range()`

`range()` generates a sequence of numbers.

### `range(stop)`

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

The ending number is **not included**.

---

## `range(start, stop)`

```python
for i in range(2, 6):
    print(i)
```

Output:

```text
2
3
4
5
```

---

## `range(start, stop, step)`

```python
for i in range(2, 10, 2):
    print(i)
```

Output:

```text
2
4
6
8
```

---

# 12. 🔢 Reverse `range()`

You can count backwards.

```python
for i in range(5, 0, -1):
    print(i)
```

Output:

```text
5
4
3
2
1
```

---

# 13. 🔤 Loop Through a String

```python
name = "Python"

for letter in name:
    print(letter)
```

Output:

```text
P
y
t
h
o
n
```

---

# 14. 📋 Loop Through a List

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

# 15. 🔄 `while` Loop

A `while` loop repeats as long as a condition is true.

### Example

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

---

# 16. ⚠️ Infinite Loop

Be careful with `while` loops.

This creates an infinite loop:

```python
count = 1

while count <= 5:
    print(count)
```

Why?

Because `count` never changes.

Correct:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

---

# 17. 🛑 `break`

`break` immediately stops a loop.

### Example

```python
for i in range(10):
    if i == 5:
        break

    print(i)
```

Output:

```text
0
1
2
3
4
```

When `i` becomes `5`, the loop stops.

---

# 18. ⏭️ `continue`

`continue` skips the current iteration and moves to the next one.

### Example

```python
for i in range(5):
    if i == 2:
        continue

    print(i)
```

Output:

```text
0
1
3
4
```

`2` was skipped.

---

# 19. 💤 `pass`

`pass` does nothing.

It is useful when you need a block of code but haven't written the code yet.

```python
if True:
    pass
```

Example:

```python
for i in range(5):
    pass
```

---

# 20. 🪆 Nested Loops

A loop inside another loop is called a nested loop.

### Example

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

---

# 21. ⭐ Print a Pattern

```python
for i in range(1, 6):
    print("*" * i)
```

Output:

```text
*
**
***
****
*****
```

---

# 22. 🔢 Print Even Numbers

```python
for i in range(1, 11):
    if i % 2 == 0:
        print(i)
```

Output:

```text
2
4
6
8
10
```

---

# 23. 🔢 Print Odd Numbers

```python
for i in range(1, 11):
    if i % 2 != 0:
        print(i)
```

Output:

```text
1
3
5
7
9
```

---

# 24. 🧮 Sum of Numbers

Find the sum from 1 to 10.

```python
total = 0

for i in range(1, 11):
    total += i

print("Sum =", total)
```

Output:

```text
Sum = 55
```

---

# 25. ✖️ Multiplication Table

```python
number = 5

for i in range(1, 11):
    print(number, "x", i, "=", number * i)
```

Output:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

# 26. 🎯 Check Positive, Negative or Zero

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

---

# 27. 🔢 Check Even or Odd

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

# 28. 🏆 Find the Largest of Two Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

if a > b:
    print("Largest =", a)
else:
    print("Largest =", b)
```

---

# 29. 🏆 Find the Largest of Three Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
c = int(input("Enter third number: "))

if a >= b and a >= c:
    print("Largest =", a)
elif b >= a and b >= c:
    print("Largest =", b)
else:
    print("Largest =", c)
```

---

# 30. 🎓 Grade Calculator

```python
marks = int(input("Enter marks: "))

if marks >= 90:
    print("Grade A+")
elif marks >= 80:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
elif marks >= 40:
    print("Grade D")
else:
    print("Fail")
```

---

# 31. 🔐 Simple Login Program

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "1234":
    print("Login successful")
else:
    print("Invalid username or password")
```

> This is only a learning example. Never store real passwords directly in source code.

---

# 32. 🔢 Factorial

Factorial of 5:

```text
5 × 4 × 3 × 2 × 1 = 120
```

Python:

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print("Factorial =", factorial)
```

Output:

```text
Factorial = 120
```

---

# 33. 🔍 Check Prime Number

A prime number has exactly two factors: `1` and itself.

Example:

```text
2, 3, 5, 7, 11, 13
```

Program:

```python
number = int(input("Enter a number: "))

if number < 2:
    print("Not Prime")
else:
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime")
    else:
        print("Not Prime")
```

---

# 34. 🔢 Reverse a Number

```python
number = int(input("Enter a number: "))
reverse = 0

while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10

print("Reverse =", reverse)
```

Example:

```text
Input:
12345

Output:
Reverse = 54321
```

---

# 35. 🔢 Count Digits

```python
number = int(input("Enter a number: "))

count = 0

while number > 0:
    number //= 10
    count += 1

print("Digits =", count)
```

---

# 36. 💡 `for` vs `while`

| `for` Loop                           | `while` Loop                                    |
| ------------------------------------ | ----------------------------------------------- |
| Used for sequences/known repetitions | Used when condition controls repetition         |
| Works well with `range()`            | Works well with conditions                      |
| Often easier for counting            | Useful when repetitions aren't known beforehand |

### Example `for`

```python
for i in range(5):
    print(i)
```

### Example `while`

```python
i = 0

while i < 5:
    print(i)
    i += 1
```

Both produce:

```text
0
1
2
3
4
```

---

# 37. 🧠 Quick Revision

### Decision Making

```text
if
elif
else
```

### Loops

```text
for
while
```

### Loop Control

```text
break
continue
pass
```

### Useful Function

```text
range()
```

---

# 38. 📚 Practice Questions

Try solving these yourself.

### Beginner

1. Check whether a number is positive or negative.
2. Check whether a number is even or odd.
3. Find the largest of two numbers.
4. Find the largest of three numbers.
5. Check whether a person is eligible to vote.
6. Print numbers from 1 to 100.
7. Print numbers from 100 to 1.
8. Print all even numbers from 1 to 100.
9. Print all odd numbers from 1 to 100.
10. Calculate the sum of numbers from 1 to 100.

### Intermediate

11. Print a multiplication table.
12. Calculate factorial.
13. Check whether a number is prime.
14. Print prime numbers between 1 and 100.
15. Reverse a number.
16. Count digits in a number.
17. Find the sum of digits.
18. Check whether a number is a palindrome.
19. Print Fibonacci numbers.
20. Create a simple calculator.

### Pattern Practice

21. Print:

```text
*
**
***
****
*****
```

22. Print:

```text
*****
****
***
**
*
```

23. Print:

```text
1
12
123
1234
12345
```

---

# 39. 🚀 Learning Path

After completing Notes 1 and Notes 2:

```text
Notes 1
Python Basics
      ↓
Notes 2
Control Flow
      ↓
Notes 3
Strings
      ↓
Notes 4
Lists
      ↓
Notes 5
Tuples, Sets & Dictionaries
      ↓
Notes 6
Functions
      ↓
Notes 7
Modules & Packages
      ↓
Notes 8
File Handling
      ↓
Notes 9
Exception Handling
      ↓
Notes 10
Object-Oriented Programming
```

---

# ⭐ Final Tip

Don't memorize every program.

Understand:

```text
Condition
    ↓
Decision
    ↓
Loop
    ↓
Repeat
    ↓
Result
```

Practice writing programs yourself. The more problems you solve, the stronger your Python logic becomes.

```python
print("Keep Coding 🚀")
print("Keep Practicing 💻")
print("Keep Learning 🐍")
```

**Happy Coding! 🐍🔥**
