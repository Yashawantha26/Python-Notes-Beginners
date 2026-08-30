````markdown
# 🐍 Python Beginners – Notes 6

## 📌 Topic: Functions in Python

---

## 1. What is a Function?

A **function** is a reusable block of code that performs a specific task.

Instead of writing the same code multiple times, we can create a function and call it whenever we need it.

### Syntax

```python
def function_name():
    # code
````

### Example

```python
def greet():
    print("Hello, World!")

greet()
```

### Output

```text
Hello, World!
```

---

# 2. Why Use Functions?

Functions help us to:

* Reuse code
* Reduce code repetition
* Make programs easier to understand
* Make programs easier to maintain
* Divide a large program into smaller parts

### Example Without Function

```python
print("Hello Yashu")
print("Hello Yashu")
print("Hello Yashu")
```

### Example With Function

```python
def greet():
    print("Hello Yashu")

greet()
greet()
greet()
```

---

# 3. Creating a Function

We use the `def` keyword to create a function.

```python
def greet():
    print("Welcome to Python")
```

The function will not execute until we call it.

### Calling the Function

```python
greet()
```

### Complete Example

```python
def greet():
    print("Welcome to Python")

greet()
```

### Output

```text
Welcome to Python
```

---

# 4. Function with Parameters

A **parameter** is a value received by a function.

### Example

```python
def greet(name):
    print("Hello", name)

greet("Yashu")
```

### Output

```text
Hello Yashu
```

Here:

* `name` → parameter
* `"Yashu"` → argument

---

# 5. Parameter vs Argument

### Parameter

A parameter is written when defining a function.

```python
def greet(name):
    print(name)
```

Here `name` is a parameter.

### Argument

An argument is the actual value passed when calling the function.

```python
greet("Yashu")
```

Here `"Yashu"` is an argument.

---

# 6. Function with Multiple Parameters

A function can have multiple parameters.

### Example

```python
def add(a, b):
    print(a + b)

add(10, 20)
```

### Output

```text
30
```

Another example:

```python
def student(name, age):
    print("Name:", name)
    print("Age:", age)

student("Yashu", 20)
```

### Output

```text
Name: Yashu
Age: 20
```

---

# 7. Return Statement

The `return` statement sends a value back from a function.

### Example

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

### Output

```text
30
```

The returned value can be stored in a variable.

---

# 8. print() vs return

## print()

`print()` displays the result on the screen.

```python
def add(a, b):
    print(a + b)

add(10, 20)
```

Output:

```text
30
```

## return

`return` sends the result back to the calling code.

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

### Important Difference

```text
print() → displays the value
return  → returns the value
```

---

# 9. Function Without Return

A function does not always need a `return` statement.

```python
def greet():
    print("Hello")

greet()
```

Output:

```text
Hello
```

---

# 10. Function with Return

```python
def square(number):
    return number * number

result = square(5)

print(result)
```

Output:

```text
25
```

---

# 11. Default Parameters

A parameter can have a default value.

### Example

```python
def greet(name="Student"):
    print("Hello", name)

greet()
```

### Output

```text
Hello Student
```

If we provide a value, it replaces the default value.

```python
def greet(name="Student"):
    print("Hello", name)

greet("Yashu")
```

### Output

```text
Hello Yashu
```

---

# 12. Keyword Arguments

We can pass arguments using parameter names.

### Example

```python
def student(name, age):
    print("Name:", name)
    print("Age:", age)

student(age=20, name="Yashu")
```

### Output

```text
Name: Yashu
Age: 20
```

The order does not matter when using keyword arguments.

---

# 13. Positional Arguments

Arguments passed according to their position are called positional arguments.

```python
def student(name, age):
    print(name)
    print(age)

student("Yashu", 20)
```

Here:

```text
"Yashu" → name
20       → age
```

---

# 14. Mixing Positional and Keyword Arguments

We can also use both.

```python
def student(name, age, course):
    print(name)
    print(age)
    print(course)

student("Yashu", age=20, course="CSE")
```

### Output

```text
Yashu
20
CSE
```

---

# 15. Local Variables

A variable created inside a function is called a **local variable**.

### Example

```python
def test():
    x = 10
    print(x)

test()
```

Output:

```text
10
```

The variable `x` belongs to the function.

---

# 16. Global Variables

A variable created outside a function is called a **global variable**.

### Example

```python
x = 100

def test():
    print(x)

test()
```

### Output

```text
100
```

The function can access the global variable.

---

# 17. Local vs Global Variable

### Local Variable

Created inside a function.

```python
def test():
    x = 10
```

### Global Variable

Created outside a function.

```python
x = 10

def test():
    print(x)
```

### Remember

```text
Local  → inside function
Global → outside function
```

---

# 18. Using global Keyword

The `global` keyword can be used to modify a global variable inside a function.

### Example

```python
x = 10

def change():
    global x
    x = 20

change()

print(x)
```

### Output

```text
20
```

---

# 19. Function Returning Multiple Values

Python allows a function to return multiple values.

```python
def calculate(a, b):
    return a + b, a - b, a * b

result = calculate(10, 5)

print(result)
```

### Output

```text
(15, 5, 50)
```

We can also store them separately.

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

# 20. Function for Addition

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

### Output

```text
30
```

---

# 21. Function for Subtraction

```python
def subtract(a, b):
    return a - b

print(subtract(20, 10))
```

### Output

```text
10
```

---

# 22. Function for Multiplication

```python
def multiply(a, b):
    return a * b

print(multiply(5, 4))
```

### Output

```text
20
```

---

# 23. Function for Division

```python
def divide(a, b):
    return a / b

print(divide(10, 2))
```

### Output

```text
5.0
```

---

# 24. Function to Find Square

```python
def square(number):
    return number * number

print(square(5))
```

### Output

```text
25
```

---

# 25. Function to Find Cube

```python
def cube(number):
    return number * number * number

print(cube(3))
```

### Output

```text
27
```

---

# 26. Function to Check Even or Odd

```python
def check_even_odd(number):
    if number % 2 == 0:
        return "Even"
    else:
        return "Odd"

print(check_even_odd(10))
```

### Output

```text
Even
```

---

# 27. Function to Find Largest Number

```python
def largest(a, b):
    if a > b:
        return a
    else:
        return b

print(largest(10, 20))
```

### Output

```text
20
```

---

# 28. Function to Find Positive or Negative

```python
def check_number(number):
    if number > 0:
        return "Positive"
    elif number < 0:
        return "Negative"
    else:
        return "Zero"

print(check_number(-5))
```

### Output

```text
Negative
```

---

# 29. Function to Calculate Area of Circle

Formula:

```text
Area = π × r × r
```

### Example

```python
def circle_area(radius):
    return 3.14 * radius * radius

print(circle_area(5))
```

### Output

```text
78.5
```

---

# 30. Function to Calculate Simple Interest

Formula:

```text
SI = (P × R × T) / 100
```

### Example

```python
def simple_interest(p, r, t):
    return (p * r * t) / 100

print(simple_interest(10000, 5, 2))
```

### Output

```text
1000.0
```

---

# 31. Function with User Input

We can take input from the user and pass it to a function.

```python
def greet(name):
    print("Hello", name)

name = input("Enter your name: ")

greet(name)
```

### Example Output

```text
Enter your name: Yashu
Hello Yashu
```

---

# 32. Function with Integer Input

```python
def square(number):
    return number * number

number = int(input("Enter a number: "))

print("Square:", square(number))
```

### Example Output

```text
Enter a number: 6
Square: 36
```

---

# 33. Function Calling Another Function

One function can call another function.

```python
def add(a, b):
    return a + b

def display():
    result = add(10, 20)
    print("Result:", result)

display()
```

### Output

```text
Result: 30
```

---

# 34. Nested Function

A function defined inside another function is called a nested function.

```python
def outer():
    
    def inner():
        print("Inside inner function")
    
    inner()

outer()
```

### Output

```text
Inside inner function
```

---

# 35. Function Documentation

We can use a **docstring** to describe a function.

```python
def add(a, b):
    """This function returns the sum of two numbers."""
    return a + b

print(add(10, 20))
```

The text inside `""" """` is called a docstring.

---

# 36. Pass Statement

The `pass` statement is used when we want to create an empty function.

```python
def test():
    pass
```

The function does nothing.

Later, we can add code to it.

---

# 37. Function with No Parameters

```python
def welcome():
    print("Welcome to Python")

welcome()
```

---

# 38. Function with One Parameter

```python
def welcome(name):
    print("Welcome", name)

welcome("Yashu")
```

---

# 39. Function with Two Parameters

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

---

# 40. Function with Default Parameter

```python
def welcome(name="Student"):
    print("Welcome", name)

welcome()
```

---

# 41. Important Function Terms

| Term            | Meaning                         |
| --------------- | ------------------------------- |
| `def`           | Used to define a function       |
| Function        | Reusable block of code          |
| Parameter       | Variable in function definition |
| Argument        | Value passed to a function      |
| `return`        | Sends a value back              |
| `print()`       | Displays output                 |
| Local variable  | Variable inside a function      |
| Global variable | Variable outside a function     |
| `pass`          | Empty statement                 |
| Docstring       | Description of a function       |

---

# 42. Basic Function Structure

```python
def function_name(parameters):
    # statements
    return result
```

### Example

```python
def add(a, b):
    result = a + b
    return result

answer = add(10, 20)

print(answer)
```

---

# 43. Important Rules for Functions

### Rule 1

Use `def` to define a function.

```python
def greet():
    print("Hello")
```

### Rule 2

Use parentheses `()` after the function name.

```python
def greet():
```

### Rule 3

Use indentation for the function body.

```python
def greet():
    print("Hello")
```

### Rule 4

Call the function using its name.

```python
greet()
```

### Rule 5

Parameters are optional.

```python
def greet():
    print("Hello")
```

or

```python
def greet(name):
    print("Hello", name)
```

---

# 44. Common Mistakes

## Mistake 1: Forgetting `def`

Wrong:

```python
greet():
    print("Hello")
```

Correct:

```python
def greet():
    print("Hello")
```

---

## Mistake 2: Forgetting Parentheses

Wrong:

```python
def greet:
    print("Hello")
```

Correct:

```python
def greet():
    print("Hello")
```

---

## Mistake 3: Incorrect Indentation

Wrong:

```python
def greet():
print("Hello")
```

Correct:

```python
def greet():
    print("Hello")
```

---

## Mistake 4: Forgetting to Call the Function

```python
def greet():
    print("Hello")
```

The function is defined but not executed.

Correct:

```python
def greet():
    print("Hello")

greet()
```

---

# 45. Practice Programs

## Program 1: Greeting

Write a function to print:

```text
Welcome to Python
```

### Answer

```python
def welcome():
    print("Welcome to Python")

welcome()
```

---

## Program 2: Add Two Numbers

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

---

## Program 3: Find Square

```python
def square(number):
    return number * number

print(square(7))
```

---

## Program 4: Find Cube

```python
def cube(number):
    return number * number * number

print(cube(4))
```

---

## Program 5: Check Even or Odd

```python
def check(number):
    if number % 2 == 0:
        return "Even"
    else:
        return "Odd"

print(check(15))
```

---

## Program 6: Find Largest of Two Numbers

```python
def largest(a, b):
    if a > b:
        return a
    else:
        return b

print(largest(50, 30))
```

---

## Program 7: Find Positive, Negative or Zero

```python
def check(number):
    if number > 0:
        return "Positive"
    elif number < 0:
        return "Negative"
    else:
        return "Zero"

print(check(0))
```

---

## Program 8: Calculate Simple Interest

```python
def simple_interest(p, r, t):
    return (p * r * t) / 100

p = float(input("Enter principal: "))
r = float(input("Enter rate: "))
t = float(input("Enter time: "))

print("Simple Interest:", simple_interest(p, r, t))
```

---

# 46. Mini Project – Calculator Using Functions

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b


def divide(a, b):
    return a / b


a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

print("Addition:", add(a, b))
print("Subtraction:", subtract(a, b))
print("Multiplication:", multiply(a, b))

if b != 0:
    print("Division:", divide(a, b))
else:
    print("Cannot divide by zero")
```

---

# 47. Quick Revision

```text
Function
   ↓
Reusable block of code
```

```python
def greet():
    print("Hello")

greet()
```

### Parameters

```python
def greet(name):
    print("Hello", name)

greet("Yashu")
```

### Return

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

### Default Parameter

```python
def greet(name="Student"):
    print("Hello", name)

greet()
```

### Keyword Argument

```python
def student(name, age):
    print(name, age)

student(age=20, name="Yashu")
```

---

# 48. Key Points to Remember ⭐

* A function is a reusable block of code.
* Use `def` to create a function.
* Use `()` after the function name.
* Function parameters receive values.
* Arguments are values passed to functions.
* `return` sends a value back.
* `print()` displays a value.
* Functions can have zero, one, or many parameters.
* Functions can have default parameters.
* Python supports positional and keyword arguments.
* Variables inside functions are usually local variables.
* Variables outside functions are global variables.
* `pass` is used for an empty function.
* Functions make programs cleaner and easier to reuse.

---

# 📝 Notes 6 Summary

## Functions in Python

```text
def
 ↓
Define Function
 ↓
Parameters
 ↓
Function Body
 ↓
return
 ↓
Function Call
```

### Example

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

### Output

```text
30
```

---

# 🎯 Notes 6 Practice Questions

1. What is a function in Python?
2. Why are functions used?
3. What is the purpose of the `def` keyword?
4. What is a parameter?
5. What is an argument?
6. What is the difference between `print()` and `return`?
7. What is a default parameter?
8. What are keyword arguments?
9. What is a local variable?
10. What is a global variable?
11. Write a function to add two numbers.
12. Write a function to find the square of a number.
13. Write a function to find the cube of a number.
14. Write a function to check whether a number is even or odd.
15. Write a function to find the largest of two numbers.
16. Write a function to calculate simple interest.
17. Write a function to calculate the area of a circle.
18. Write a function to check whether a number is positive, negative, or zero.
19. Create a calculator using functions.
20. Create a function that returns multiple values.

