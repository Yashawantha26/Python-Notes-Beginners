Absolutely — here is the complete **`Notes18.md`**, continuing from Notes 17.

# Python Beginners Notes – Notes 18

# 🔄 Iterators, Iterables & Generators

In this lesson, we will learn:

* Iterable
* Iterator
* `iter()`
* `next()`
* `StopIteration`
* Creating custom iterators
* Generator functions
* `yield`
* `next()` with generators
* Generator expressions
* `yield from`
* `send()`
* `close()`
* `throw()`
* Memory efficiency
* Iterator vs Iterable
* Generator vs Iterator
* Practical examples
* Interview questions
* Practice problems

---

# 1. What is an Iterable?

An **iterable** is an object that can be looped over.

Examples:

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number)
```

Output:

```text
10
20
30
```

The list is an iterable.

Common iterables include:

```text
list
tuple
string
set
dictionary
range
```

---

# 2. Examples of Iterables

## List

```python
numbers = [10, 20, 30]

for x in numbers:
    print(x)
```

## Tuple

```python
numbers = (10, 20, 30)

for x in numbers:
    print(x)
```

## String

```python
name = "Python"

for character in name:
    print(character)
```

## Set

```python
numbers = {10, 20, 30}

for x in numbers:
    print(x)
```

## Dictionary

```python
student = {
    "name": "Yashu",
    "age": 20
}

for key in student:
    print(key)
```

---

# 3. What is an Iterator?

An **iterator** is an object that produces values one at a time.

An iterator provides:

```text
__iter__()
__next__()
```

Example:

```python
numbers = [10, 20, 30]

iterator = iter(numbers)

print(next(iterator))
print(next(iterator))
print(next(iterator))
```

Output:

```text
10
20
30
```

---

# 4. `iter()`

The `iter()` function creates an iterator from an iterable.

Example:

```python
numbers = [10, 20, 30]

iterator = iter(numbers)

print(iterator)
```

The exact printed representation may vary, but it will be an iterator object.

---

# 5. `next()`

The `next()` function gets the next item from an iterator.

Example:

```python
numbers = [10, 20, 30]

iterator = iter(numbers)

print(next(iterator))
print(next(iterator))
print(next(iterator))
```

Output:

```text
10
20
30
```

---

# 6. What Happens After the End?

If there are no more values, `next()` raises:

```text
StopIteration
```

Example:

```python
numbers = [10, 20]

iterator = iter(numbers)

print(next(iterator))
print(next(iterator))
print(next(iterator))
```

Output:

```text
10
20
Traceback ...
StopIteration
```

---

# 7. Handling `StopIteration`

You can use `try` and `except`.

```python
numbers = [10, 20]

iterator = iter(numbers)

try:
    print(next(iterator))
    print(next(iterator))
    print(next(iterator))
except StopIteration:
    print("No more items")
```

Output:

```text
10
20
No more items
```

---

# 8. How a `for` Loop Works

A `for` loop internally uses the iterator protocol.

This:

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number)
```

is conceptually similar to:

```python
numbers = [10, 20, 30]

iterator = iter(numbers)

while True:
    try:
        number = next(iterator)
        print(number)
    except StopIteration:
        break
```

This is an important Python concept.

---

# 9. Iterable vs Iterator

| Iterable                      | Iterator                               |
| ----------------------------- | -------------------------------------- |
| Can be looped over            | Produces values one at a time          |
| Can create an iterator        | Implements iterator protocol           |
| Usually provides `__iter__()` | Provides `__iter__()` and `__next__()` |
| Example: list                 | Example: `iter(list)`                  |

Example:

```python
numbers = [10, 20, 30]

iterator = iter(numbers)
```

Here:

```text
numbers → Iterable
iterator → Iterator
```

---

# 10. Checking an Iterator

```python
numbers = [10, 20, 30]

iterator = iter(numbers)

print(iter(iterator) is iterator)
```

Output:

```text
True
```

An iterator returns itself from `iter()`.

---

# 11. Strings Are Iterable

A string can be iterated character by character.

```python
word = "Python"

for character in word:
    print(character)
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

# 12. Dictionary Iteration

By default, iterating over a dictionary gives its keys.

```python
student = {
    "name": "Yashu",
    "age": 20,
    "course": "CSE"
}

for key in student:
    print(key)
```

Output:

```text
name
age
course
```

---

# 13. Dictionary Values

```python
student = {
    "name": "Yashu",
    "age": 20
}

for value in student.values():
    print(value)
```

---

# 14. Dictionary Items

```python
student = {
    "name": "Yashu",
    "age": 20
}

for key, value in student.items():
    print(key, value)
```

Output:

```text
name Yashu
age 20
```

---

# 15. `range()` Is Iterable

```python
numbers = range(5)

for number in numbers:
    print(number)
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

# 16. Creating a Custom Iterator

You can create your own iterator using a class.

Example:

```python
class Count:

    def __init__(self, maximum):
        self.current = 1
        self.maximum = maximum

    def __iter__(self):
        return self

    def __next__(self):

        if self.current <= self.maximum:
            value = self.current
            self.current += 1
            return value

        raise StopIteration


counter = Count(5)

for number in counter:
    print(number)
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

# 17. Understanding the Custom Iterator

Our class contains:

```python
def __iter__(self):
    return self
```

This makes the object an iterator.

And:

```python
def __next__(self):
```

defines how the next value is generated.

When there are no more values:

```python
raise StopIteration
```

---

# 18. Another Custom Iterator

Create an iterator for even numbers.

```python
class EvenNumbers:

    def __init__(self, maximum):
        self.current = 2
        self.maximum = maximum

    def __iter__(self):
        return self

    def __next__(self):

        if self.current <= self.maximum:
            value = self.current
            self.current += 2
            return value

        raise StopIteration


numbers = EvenNumbers(10)

for number in numbers:
    print(number)
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

# 19. Problems with Custom Iterators

Custom iterator classes can become lengthy.

For example:

```python
class Count:

    def __init__(self, maximum):
        self.current = 1
        self.maximum = maximum

    def __iter__(self):
        return self

    def __next__(self):
        ...
```

Python provides a simpler solution:

```text
Generators
```

---

# 20. What is a Generator?

A **generator** is a simple way to create an iterator.

Generators use:

```python
yield
```

instead of manually implementing `__next__()`.

---

# 21. Generator Function

Example:

```python
def numbers():
    yield 1
    yield 2
    yield 3
```

Call the function:

```python
result = numbers()

print(result)
```

It returns a generator object.

---

# 22. Using a Generator

```python
def numbers():
    yield 1
    yield 2
    yield 3


for number in numbers():
    print(number)
```

Output:

```text
1
2
3
```

---

# 23. `yield`

`yield` produces a value and pauses the generator.

Example:

```python
def numbers():
    yield 10
    yield 20
    yield 30
```

The function does not produce all values at once.

It produces them one by one.

---

# 24. `yield` vs `return`

### `return`

```python
def example():
    return 10
```

The function finishes immediately.

### `yield`

```python
def example():
    yield 10
    yield 20
```

The function becomes a generator and can resume later.

---

# 25. Generator with `next()`

```python
def numbers():
    yield 10
    yield 20
    yield 30


generator = numbers()

print(next(generator))
print(next(generator))
print(next(generator))
```

Output:

```text
10
20
30
```

---

# 26. Generator After Completion

```python
def numbers():
    yield 10


generator = numbers()

print(next(generator))
print(next(generator))
```

The second `next()` raises:

```text
StopIteration
```

---

# 27. Generator Example

```python
def count_to_five():

    number = 1

    while number <= 5:
        yield number
        number += 1


for number in count_to_five():
    print(number)
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

# 28. Generator for Even Numbers

```python
def even_numbers(limit):

    number = 2

    while number <= limit:
        yield number
        number += 2


for number in even_numbers(10):
    print(number)
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

# 29. Generator for Odd Numbers

```python
def odd_numbers(limit):

    number = 1

    while number <= limit:
        yield number
        number += 2


for number in odd_numbers(10):
    print(number)
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

# 30. Generator for Squares

```python
def squares(limit):

    for number in range(1, limit + 1):
        yield number * number


for square in squares(5):
    print(square)
```

Output:

```text
1
4
9
16
25
```

---

# 31. Generator for Fibonacci Numbers

```python
def fibonacci(count):

    a = 0
    b = 1

    for _ in range(count):
        yield a
        a, b = b, a + b


for number in fibonacci(10):
    print(number)
```

Output:

```text
0
1
1
2
3
5
8
13
21
34
```

---

# 32. Infinite Generator

Generators can represent an unbounded sequence.

Example:

```python
def numbers():

    number = 1

    while True:
        yield number
        number += 1
```

Use carefully:

```python
generator = numbers()

for _ in range(5):
    print(next(generator))
```

Output:

```text
1
2
3
4
5
```

The generator itself can continue producing values indefinitely.

---

# 33. Generator Expression

A generator expression looks similar to a list comprehension.

### List comprehension

```python
numbers = [x * x for x in range(5)]

print(numbers)
```

### Generator expression

```python
numbers = (x * x for x in range(5))

print(numbers)
```

The generator expression produces values lazily.

---

# 34. List Comprehension vs Generator Expression

### List comprehension

```python
numbers = [x * x for x in range(1000000)]
```

Creates the list immediately.

### Generator expression

```python
numbers = (x * x for x in range(1000000))
```

Produces values when requested.

---

# 35. Memory Efficiency

Generators are useful when processing large sequences because they can avoid storing the entire result in memory at once.

Example:

```python
def read_numbers():
    for number in range(1000000):
        yield number
```

Only the current value needs to be produced as iteration proceeds.

---

# 36. Important: Lazy Evaluation

Generators use **lazy evaluation**.

This means:

```text
Do the work only when the next value is requested.
```

Example:

```python
def numbers():

    print("Producing 1")
    yield 1

    print("Producing 2")
    yield 2
```

Usage:

```python
generator = numbers()

print("Generator created")

print(next(generator))
print(next(generator))
```

The generator body starts executing when iteration begins, not when the generator object is created.

---

# 37. Generator State

A generator remembers where it stopped.

Example:

```python
def numbers():

    yield 10
    yield 20
    yield 30


generator = numbers()

print(next(generator))
print(next(generator))
```

Output:

```text
10
20
```

The generator remembers that `20` was the most recently produced value.

The next call gives:

```text
30
```

---

# 38. `yield from`

`yield from` delegates iteration to another iterable or iterator.

Example:

```python
def numbers():
    yield from [10, 20, 30]


for number in numbers():
    print(number)
```

Output:

```text
10
20
30
```

---

# 39. `yield from` with Another Generator

```python
def first():
    yield 1
    yield 2


def second():
    yield 3
    yield 4


def combined():
    yield from first()
    yield from second()


for number in combined():
    print(number)
```

Output:

```text
1
2
3
4
```

---

# 40. Generator `send()`

Generators can receive values using:

```python
send()
```

Example:

```python
def calculator():

    number = 0

    while True:
        value = yield number
        number += value


generator = calculator()

print(next(generator))
print(generator.send(10))
print(generator.send(5))
```

Output:

```text
0
10
15
```

The first `next()` starts the generator and advances it to the `yield`.

---

# 41. `send(None)`

A generator must be started before sending a non-`None` value.

Usually:

```python
next(generator)
```

is used first.

Equivalent:

```python
generator.send(None)
```

can also start it.

---

# 42. Generator `close()`

You can stop a generator using:

```python
close()
```

Example:

```python
def numbers():

    try:
        yield 1
        yield 2
        yield 3
    finally:
        print("Generator closed")


generator = numbers()

print(next(generator))

generator.close()
```

Output:

```text
1
Generator closed
```

---

# 43. Generator `throw()`

A generator can receive an exception using:

```python
throw()
```

Example:

```python
def example():

    try:
        yield 1
    except ValueError:
        print("ValueError received")


generator = example()

print(next(generator))

generator.throw(ValueError)
```

Output:

```text
1
ValueError received
```

---

# 44. Generator Pipeline

Generators are useful for processing data in stages.

Example:

```python
def numbers():
    for number in range(1, 6):
        yield number


def squares(numbers):
    for number in numbers:
        yield number * number


for value in squares(numbers()):
    print(value)
```

Output:

```text
1
4
9
16
25
```

---

# 45. Generator Pipeline with Filtering

```python
def numbers():
    for number in range(1, 11):
        yield number


def even_numbers(numbers):
    for number in numbers:
        if number % 2 == 0:
            yield number


def squares(numbers):
    for number in numbers:
        yield number * number


result = squares(even_numbers(numbers()))

for value in result:
    print(value)
```

Output:

```text
4
16
36
64
100
```

---

# 46. Reading Large Files

Generators are useful for processing large files line by line.

Example:

```python
def read_file(filename):

    with open(filename, "r") as file:

        for line in file:
            yield line.strip()
```

Usage:

```python
for line in read_file("data.txt"):
    print(line)
```

This avoids manually loading all lines into a list.

---

# 47. Generator for Large Data

Suppose you need numbers from 1 to 10 million.

A list:

```python
numbers = list(range(10_000_000))
```

stores all numbers.

A generator:

```python
numbers = (x for x in range(10_000_000))
```

produces them lazily.

---

# 48. Generator Function Example

```python
def student_names():

    students = [
        "Yashu",
        "Rahul",
        "Arun",
        "Kiran"
    ]

    for student in students:
        yield student


for name in student_names():
    print(name)
```

Output:

```text
Yashu
Rahul
Arun
Kiran
```

---

# 49. Generator for Multiplication Table

```python
def multiplication_table(number):

    for i in range(1, 11):
        yield number * i


for value in multiplication_table(5):
    print(value)
```

Output:

```text
5
10
15
20
25
30
35
40
45
50
```

---

# 50. Generator for Prime Numbers

```python
def is_prime(number):

    if number < 2:
        return False

    for divisor in range(2, int(number ** 0.5) + 1):
        if number % divisor == 0:
            return False

    return True


def prime_numbers(limit):

    for number in range(2, limit + 1):

        if is_prime(number):
            yield number


for prime in prime_numbers(30):
    print(prime)
```

Output:

```text
2
3
5
7
11
13
17
19
23
29
```

---

# 51. Generator vs List

| Generator                               | List                     |
| --------------------------------------- | ------------------------ |
| Lazy                                    | Eager                    |
| Produces values on demand               | Stores values            |
| Usually memory efficient                | Can use more memory      |
| Can be iterated only once in normal use | Can be reused            |
| Uses `yield` or generator expression    | Uses `[]`                |
| Good for streams/large data             | Good for repeated access |

---

# 52. Generator vs Iterator

A generator is a convenient way to create an iterator.

### Custom iterator

Usually requires:

```python
__iter__()
__next__()
```

### Generator

Usually requires:

```python
yield
```

Example:

```python
def numbers():
    yield 1
    yield 2
```

This automatically creates iterator behavior.

---

# 53. Iterable vs Iterator vs Generator

```text
Iterable
   ↓
Can be iterated over

Iterator
   ↓
Produces next values

Generator
   ↓
A convenient iterator created using yield
```

Example:

```python
numbers = [1, 2, 3]

iterator = iter(numbers)

generator = (x * 2 for x in numbers)
```

---

# 54. Checking Objects

You can use:

```python
from collections.abc import Iterable, Iterator, Generator
```

Example:

```python
from collections.abc import Iterable, Iterator, Generator

numbers = [1, 2, 3]

iterator = iter(numbers)

generator = (x * 2 for x in numbers)

print(isinstance(numbers, Iterable))
print(isinstance(iterator, Iterator))
print(isinstance(generator, Generator))
```

Output:

```text
True
True
True
```

---

# 55. Reusing an Iterable

A list can normally be iterated multiple times.

```python
numbers = [1, 2, 3]

for number in numbers:
    print(number)

for number in numbers:
    print(number)
```

Both loops work.

---

# 56. Iterator Is Usually One-Way

```python
numbers = [1, 2, 3]

iterator = iter(numbers)

print(list(iterator))
print(list(iterator))
```

Output:

```text
[1, 2, 3]
[]
```

The iterator has already been exhausted.

---

# 57. Generator Is Usually One-Way

```python
def numbers():
    yield 1
    yield 2
    yield 3


generator = numbers()

print(list(generator))
print(list(generator))
```

Output:

```text
[1, 2, 3]
[]
```

Once exhausted, the same generator object does not restart automatically.

---

# 58. Generator Expression Example

```python
squares = (x ** 2 for x in range(1, 6))

for square in squares:
    print(square)
```

Output:

```text
1
4
9
16
25
```

---

# 59. Generator with Condition

```python
even_squares = (
    x ** 2
    for x in range(1, 11)
    if x % 2 == 0
)

for value in even_squares:
    print(value)
```

Output:

```text
4
16
36
64
100
```

---

# 60. Nested Generator Expression

```python
result = (
    (x, y)
    for x in range(3)
    for y in range(2)
)

for pair in result:
    print(pair)
```

Output:

```text
(0, 0)
(0, 1)
(1, 0)
(1, 1)
(2, 0)
(2, 1)
```

---

# 61. Generator for CSV-like Data

```python
def student_data():

    data = [
        ("Yashu", 85),
        ("Rahul", 72),
        ("Arun", 65)
    ]

    for student in data:
        yield student


for name, marks in student_data():
    print(name, marks)
```

---

# 62. Generator with `enumerate()`

```python
def names():
    yield "Yashu"
    yield "Rahul"
    yield "Arun"


for index, name in enumerate(names(), start=1):
    print(index, name)
```

Output:

```text
1 Yashu
2 Rahul
3 Arun
```

---

# 63. Generator with `zip()`

```python
def names():
    yield "Yashu"
    yield "Rahul"
    yield "Arun"


marks = [85, 72, 90]

for name, mark in zip(names(), marks):
    print(name, mark)
```

Output:

```text
Yashu 85
Rahul 72
Arun 90
```

---

# 64. Generator with `sum()`

```python
numbers = (x for x in range(1, 6))

total = sum(numbers)

print(total)
```

Output:

```text
15
```

---

# 65. Generator with `any()`

```python
numbers = (x for x in range(1, 6))

print(any(x > 3 for x in numbers))
```

Output:

```text
True
```

---

# 66. Generator with `all()`

```python
numbers = (x for x in range(1, 6))

print(all(x > 0 for x in numbers))
```

Output:

```text
True
```

---

# 67. Important Difference

This:

```python
numbers = [x * 2 for x in range(5)]
```

creates a list.

This:

```python
numbers = (x * 2 for x in range(5))
```

creates a generator expression.

Remember:

```text
[] → List
() → Generator expression
```

when used in these comprehension forms.

---

# 68. Practical Project – Number Stream

```python
def number_stream(start, end):

    current = start

    while current <= end:
        yield current
        current += 1


for number in number_stream(1, 10):
    print(number)
```

---

# 69. Practical Project – Log Filter

```python
def read_logs(logs):

    for log in logs:
        if "ERROR" in log:
            yield log


logs = [
    "INFO Server started",
    "ERROR Database failed",
    "INFO User logged in",
    "ERROR Connection failed"
]

for error in read_logs(logs):
    print(error)
```

Output:

```text
ERROR Database failed
ERROR Connection failed
```

---

# 70. Practical Project – Student Result Stream

```python
def passed_students(students):

    for name, marks in students:

        if marks >= 40:
            yield name


students = [
    ("Yashu", 85),
    ("Rahul", 35),
    ("Arun", 70),
    ("Kiran", 30)
]

for name in passed_students(students):
    print(name)
```

Output:

```text
Yashu
Arun
```

---

# 71. Practical Project – Data Processing Pipeline

```python
def numbers():
    for number in range(1, 11):
        yield number


def even(numbers):
    for number in numbers:
        if number % 2 == 0:
            yield number


def square(numbers):
    for number in numbers:
        yield number ** 2


data = square(even(numbers()))

for value in data:
    print(value)
```

Output:

```text
4
16
36
64
100
```

---

# 72. When Should You Use Generators?

Use generators when:

* Data is large
* Data is processed sequentially
* You don't need all values at once
* You want lazy evaluation
* You are processing streams
* You are reading large files
* You are building data pipelines

---

# 73. When Should You Use a List?

Use a list when:

* You need random access
* You need to reuse the values
* You need indexing
* You need to know the complete collection
* The data size is manageable

Example:

```python
numbers = [10, 20, 30]

print(numbers[0])
```

Generators do not support normal indexing like lists.

---

# 74. Common Mistake

Wrong assumption:

```python
generator = (x for x in range(5))

print(generator[0])
```

This raises:

```text
TypeError
```

Instead:

```python
print(next(generator))
```

---

# 75. Common Mistake with `yield`

Incorrect:

```python
def numbers():
    yield
```

This yields `None`.

Correct:

```python
def numbers():
    yield 10
```

---

# 76. Common Mistake with `send()`

This can fail:

```python
def example():
    value = yield
    print(value)


generator = example()

generator.send(10)
```

The generator must first be suspended at a `yield`, commonly by:

```python
next(generator)
```

or:

```python
generator.send(None)
```

---

# 77. Important Generator Pattern

Remember this structure:

```python
def generator_function():

    # setup

    while condition:
        # calculate
        yield value
        # update state
```

Example:

```python
def countdown(number):

    while number > 0:
        yield number
        number -= 1
```

---

# 78. Countdown Generator

```python
def countdown(number):

    while number > 0:
        yield number
        number -= 1


for value in countdown(5):
    print(value)
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

# 79. Reverse String Generator

```python
def reverse_string(text):

    for character in reversed(text):
        yield character


for character in reverse_string("Python"):
    print(character)
```

Output:

```text
n
o
h
t
y
P
```

---

# 80. Word Generator

```python
def words(sentence):

    for word in sentence.split():
        yield word


for word in words("Python is easy to learn"):
    print(word)
```

Output:

```text
Python
is
easy
to
learn
```

---

# 81. Character Generator

```python
def characters(text):

    for character in text:
        yield character


for character in characters("HELLO"):
    print(character)
```

---

# 82. Generator for Multiples

```python
def multiples(number, count):

    for i in range(1, count + 1):
        yield number * i


for value in multiples(7, 10):
    print(value)
```

---

# 83. Generator for Perfect Squares

```python
def perfect_squares(limit):

    number = 1

    while number * number <= limit:
        yield number * number
        number += 1


for value in perfect_squares(50):
    print(value)
```

Output:

```text
1
4
9
16
25
36
49
```

---

# 84. Iterator Protocol

An object is an iterator when it implements:

```python
__iter__()
__next__()
```

Example:

```python
class Counter:

    def __init__(self):
        self.value = 0

    def __iter__(self):
        return self

    def __next__(self):
        self.value += 1

        if self.value > 3:
            raise StopIteration

        return self.value
```

---

# 85. Why `StopIteration`?

Python needs a standard way to know that an iterator is finished.

That standard signal is:

```python
StopIteration
```

A `for` loop catches this internally and stops.

---

# 86. `iter()` with Two Arguments

Python also supports:

```python
iter(callable, sentinel)
```

It repeatedly calls the callable until the returned value equals the sentinel.

Example:

```python
from io import StringIO

file = StringIO("A\nB\n")

for line in iter(file.readline, ""):
    print(line.strip())
```

Output:

```text
A
B
```

This is an advanced but useful form of `iter()`.

---

# 87. Generator Return Value

A generator can use `return`.

Example:

```python
def example():

    yield 1
    yield 2

    return "Finished"
```

The returned value becomes part of the `StopIteration` exception when the generator finishes.

---

# 88. Capturing Generator Return Value

```python
def example():

    yield 1
    yield 2

    return "Finished"


generator = example()

print(next(generator))
print(next(generator))

try:
    next(generator)
except StopIteration as error:
    print(error.value)
```

Output:

```text
1
2
Finished
```

---

# 89. Generator Best Practices

### 1. Use meaningful names

```python
def read_lines():
```

Better than:

```python
def x():
```

### 2. Keep generators focused

One generator should usually perform one logical streaming task.

### 3. Avoid unnecessary lists

Instead of:

```python
data = [process(x) for x in values]
```

consider:

```python
data = (process(x) for x in values)
```

when lazy processing is appropriate.

### 4. Remember generators are exhausted

Don't expect the same generator object to restart.

---

# 90. Interview Questions

## Q1. What is an iterable?

An iterable is an object that can return its elements one at a time during iteration.

Examples:

```text
list
tuple
string
set
dictionary
range
```

---

## Q2. What is an iterator?

An iterator is an object that implements the iterator protocol:

```python
__iter__()
__next__()
```

---

## Q3. What is `iter()`?

`iter()` obtains an iterator from an iterable.

Example:

```python
iterator = iter([1, 2, 3])
```

---

## Q4. What is `next()`?

`next()` retrieves the next item from an iterator.

---

## Q5. What is `StopIteration`?

It signals that an iterator has no more values.

---

## Q6. What is a generator?

A generator is a convenient way to create an iterator, commonly using `yield`.

---

## Q7. What is `yield`?

`yield` produces a value from a generator and suspends its execution until the generator is resumed.

---

## Q8. Difference between `yield` and `return`?

```text
return
→ Ends the function

yield
→ Produces a value and pauses generator execution
```

---

## Q9. What is lazy evaluation?

Lazy evaluation means values are calculated only when they are needed.

---

## Q10. Why are generators memory efficient?

They generally produce values one at a time instead of storing the entire sequence in memory.

---

## Q11. Can a generator be reused?

The same generator object is normally consumed once. After exhaustion, create a new generator to iterate again.

---

## Q12. What is a generator expression?

A compact way to create a generator.

Example:

```python
(x * x for x in range(10))
```

---

## Q13. What is `yield from`?

`yield from` delegates yielding to another iterable or generator.

---

## Q14. What does `send()` do?

It sends a value into a suspended generator.

---

## Q15. What does `close()` do?

It terminates a generator by raising `GeneratorExit` inside it.

---

# 91. Quick Comparison

```text
Iterable
   ↓
Can be iterated

Iterator
   ↓
Has __iter__() and __next__()

Generator
   ↓
Convenient iterator using yield
```

---

# 92. Important Syntax

## Iterator

```python
iterator = iter(iterable)

next(iterator)
```

## Generator

```python
def generator():
    yield value
```

## Generator expression

```python
generator = (expression for item in iterable)
```

## Yield from

```python
yield from iterable
```

---

# 93. Mini Challenge 1

Create a generator that produces numbers from:

```text
1 to 10
```

Expected:

```text
1
2
3
...
10
```

---

# 94. Mini Challenge 2

Create a generator that produces only even numbers from 1 to 50.

Expected:

```text
2
4
6
...
50
```

---

# 95. Mini Challenge 3

Create a generator that produces squares from 1 to 20.

Expected:

```text
1
4
9
16
...
400
```

---

# 96. Mini Challenge 4

Create a generator that produces Fibonacci numbers.

Input:

```text
10
```

Expected:

```text
0
1
1
2
3
5
8
13
21
34
```

---

# 97. Mini Challenge 5

Create a generator that reads a list of students and yields only students whose marks are greater than or equal to 75.

Example:

```python
students = [
    ("Yashu", 85),
    ("Rahul", 65),
    ("Arun", 90),
    ("Kiran", 70)
]
```

Expected:

```text
Yashu
Arun
```

---

# 98. Mini Challenge 6

Create a generator pipeline:

```text
Numbers
   ↓
Even Numbers
   ↓
Squares
```

For:

```text
1 to 20
```

Expected:

```text
4
16
36
64
100
144
196
256
324
400
```

---

# 99. Mini Challenge 7

Create a custom iterator that produces:

```text
5
10
15
20
25
```

Use:

```python
__iter__()
__next__()
```

---

# 100. Mini Challenge 8

Create a generator that reads a sentence and yields each word.

Input:

```text
Python is powerful and easy
```

Expected:

```text
Python
is
powerful
and
easy
```

---

# 🎯 Notes 18 Summary

In this lesson, you learned:

* Iterable
* Iterator
* `iter()`
* `next()`
* `StopIteration`
* Iterator protocol
* Custom iterators
* Generator functions
* `yield`
* `return` vs `yield`
* Generator state
* Lazy evaluation
* Generator expressions
* `yield from`
* `send()`
* `close()`
* `throw()`
* Generator pipelines
* Memory-efficient processing
* File processing with generators
* Iterable vs iterator
* Iterator vs generator
* Practical generator projects
* Interview questions

---

# ⭐ Final Cheat Sheet

```text
ITERABLE
   ↓
Object that can be iterated over
   ↓
list, tuple, string, set, dict, range


ITERATOR
   ↓
Produces one value at a time
   ↓
__iter__()
__next__()


iter()
   ↓
Creates/gets an iterator


next()
   ↓
Gets next value


StopIteration
   ↓
Iterator is finished


GENERATOR
   ↓
Convenient way to create an iterator
   ↓
Uses yield


yield
   ↓
Produces value
   ↓
Pauses execution
   ↓
Resumes later


GENERATOR EXPRESSION
   ↓
(expression for item in iterable)


yield from
   ↓
Delegate iteration


send()
   ↓
Send value into generator


close()
   ↓
Stop generator
```

---

# 🚀 Next Lesson

## Notes 19 → Python Modules, Packages & Imports

You will learn:

```text
Modules
Packages
import
from ... import
as
__name__
__main__
Standard Library
Creating your own modules
Creating packages
Installing packages
pip
Virtual environments
```
