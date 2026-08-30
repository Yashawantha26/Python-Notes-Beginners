# Python Beginners Notes – Notes 21

# 🛡️ Python Exception Handling

In this lesson, we will learn:

* What is an exception?
* Errors vs exceptions
* Syntax errors
* Runtime errors
* Logical errors
* `try`
* `except`
* `else`
* `finally`
* Multiple `except` blocks
* Handling specific exceptions
* Exception hierarchy
* `raise`
* Custom exceptions
* User input validation
* File-related exceptions
* Debugging
* Best practices
* Practical programs
* Mini projects
* Interview questions

---

# 1. What is an Exception?

An **exception** is an error that occurs while a Python program is running.

Example:

```python
number = 10
result = number / 0

print(result)
```

Output:

```text
ZeroDivisionError
```

The program stops because division by zero is not allowed.

---

# 2. Why Exception Handling?

Without exception handling:

```python
number = int(input("Enter a number: "))
print(10 / number)
```

If the user enters:

```text
0
```

Python produces an error.

With exception handling, we can handle the problem gracefully.

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

---

# 3. Types of Errors

Python programs commonly have:

```text
1. Syntax errors
2. Runtime errors / exceptions
3. Logical errors
```

---

# 4. Syntax Error

A syntax error occurs when Python code does not follow Python's syntax rules.

Example:

```python
if 10 > 5
    print("Hello")
```

The colon is missing.

Python reports a syntax error before normal execution can proceed.

---

# 5. Correct Syntax

```python
if 10 > 5:
    print("Hello")
```

Output:

```text
Hello
```

---

# 6. Runtime Error

A runtime error happens while the program is executing.

Example:

```python
number = 10
print(number / 0)
```

Output:

```text
ZeroDivisionError
```

This is an exception.

---

# 7. Logical Error

A logical error means the program runs but produces the wrong result.

Example:

```python
a = 10
b = 20

average = a + b / 2

print(average)
```

The intended calculation is:

```python
(a + b) / 2
```

Correct code:

```python
average = (a + b) / 2
```

Logical errors usually do not produce exceptions automatically.

---

# 8. Common Python Exceptions

Some common built-in exceptions are:

| Exception             | Meaning                |
| --------------------- | ---------------------- |
| `ValueError`          | Invalid value          |
| `TypeError`           | Incorrect type         |
| `ZeroDivisionError`   | Division by zero       |
| `IndexError`          | Invalid list index     |
| `KeyError`            | Missing dictionary key |
| `NameError`           | Unknown variable/name  |
| `FileNotFoundError`   | File does not exist    |
| `PermissionError`     | Permission denied      |
| `AttributeError`      | Invalid attribute      |
| `ImportError`         | Import problem         |
| `ModuleNotFoundError` | Module not found       |

---

# 9. Basic `try` and `except`

Syntax:

```python
try:
    # risky code

except:
    # error handling
```

Example:

```python
try:
    number = 10 / 0

except:
    print("Something went wrong.")
```

Output:

```text
Something went wrong.
```

---

# 10. Better Exception Handling

Avoid using a bare `except` when possible.

Instead, catch the specific exception.

```python
try:
    number = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

This is clearer and safer.

---

# 11. Handling `ValueError`

Example:

```python
try:
    age = int(input("Enter your age: "))
    print("Age:", age)

except ValueError:
    print("Please enter a valid integer.")
```

If the user enters:

```text
abc
```

Output:

```text
Please enter a valid integer.
```

---

# 12. Handling `TypeError`

Example:

```python
try:
    result = "10" + 5
    print(result)

except TypeError:
    print("Cannot combine these data types.")
```

---

# 13. Handling `IndexError`

Example:

```python
numbers = [10, 20, 30]

try:
    print(numbers[5])

except IndexError:
    print("Index does not exist.")
```

---

# 14. Handling `KeyError`

Example:

```python
student = {
    "name": "Yashu",
    "marks": 85
}

try:
    print(student["age"])

except KeyError:
    print("Age key does not exist.")
```

---

# 15. Handling `NameError`

```python
try:
    print(username)

except NameError:
    print("Variable is not defined.")
```

---

# 16. Handling `FileNotFoundError`

```python
try:
    with open("unknown.txt", "r", encoding="utf-8") as file:
        print(file.read())

except FileNotFoundError:
    print("File not found.")
```

---

# 17. Handling `PermissionError`

```python
try:
    with open("data.txt", "r", encoding="utf-8") as file:
        print(file.read())

except PermissionError:
    print("You do not have permission to access this file.")
```

---

# 18. Multiple `except` Blocks

You can handle different exceptions separately.

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print(result)

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

---

# 19. `else`

The `else` block executes when no exception occurs.

Syntax:

```python
try:
    # risky code

except:
    # error

else:
    # successful execution
```

Example:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

else:
    print("You entered:", number)
```

---

# 20. `finally`

The `finally` block executes whether an exception occurs or not.

Example:

```python
try:
    number = 10 / 2
    print(number)

except ZeroDivisionError:
    print("Cannot divide by zero.")

finally:
    print("Program finished.")
```

Output:

```text
5.0
Program finished.
```

---

# 21. `finally` with an Exception

```python
try:
    number = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero.")

finally:
    print("This always executes.")
```

Output:

```text
Cannot divide by zero.
This always executes.
```

---

# 22. Complete Exception Structure

The complete structure is:

```python
try:
    # risky code

except SomeException:
    # handle error

else:
    # runs if no exception

finally:
    # runs at the end
```

Example:

```python
try:
    number = int(input("Enter number: "))
    result = 100 / number

except ValueError:
    print("Invalid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Result:", result)

finally:
    print("Execution completed.")
```

---

# 23. Exception Object

You can store the exception in a variable.

```python
try:
    number = 10 / 0

except ZeroDivisionError as error:
    print("Error:", error)
```

Output:

```text
Error: division by zero
```

---

# 24. Multiple Exceptions in One Block

You can handle multiple exception types together.

```python
try:
    number = int(input("Enter number: "))
    result = 100 / number

except (ValueError, ZeroDivisionError):
    print("Invalid input or division by zero.")
```

---

# 25. Catching General Exceptions

You can use:

```python
except Exception as error:
    print("Error:", error)
```

Example:

```python
try:
    result = 10 / 0

except Exception as error:
    print("Error:", error)
```

`Exception` is a broad catch-all for most ordinary runtime exceptions.

However, specific exceptions are usually preferable.

---

# 26. Why Specific Exceptions Are Better

Less precise:

```python
try:
    value = int(input("Enter number: "))

except Exception:
    print("Error")
```

Better:

```python
try:
    value = int(input("Enter number: "))

except ValueError:
    print("Please enter a valid integer.")
```

Specific exceptions make your program easier to understand and debug.

---

# 27. Exception Hierarchy

Python exceptions are organized in a hierarchy.

Simplified:

```text
BaseException
│
├── SystemExit
├── KeyboardInterrupt
└── Exception
    │
    ├── ArithmeticError
    │   └── ZeroDivisionError
    │
    ├── LookupError
    │   ├── IndexError
    │   └── KeyError
    │
    ├── ValueError
    ├── TypeError
    ├── OSError
    │   ├── FileNotFoundError
    │   └── PermissionError
    │
    └── RuntimeError
```

This is simplified; Python has many more built-in exception classes.

---

# 28. `Exception` vs `BaseException`

Most application errors inherit from:

```python
Exception
```

`BaseException` is higher in the hierarchy and also includes special exceptions such as:

```text
KeyboardInterrupt
SystemExit
GeneratorExit
```

Normally, application code should catch `Exception`, not `BaseException`.

---

# 29. `raise`

The `raise` statement is used to manually generate an exception.

Example:

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative.")
```

---

# 30. `raise ValueError`

```python
def set_age(age):

    if age < 0:
        raise ValueError("Age must be positive.")

    return age


print(set_age(20))
```

---

# 31. Handling a Raised Exception

```python
def check_age(age):

    if age < 18:
        raise ValueError("Age must be 18 or above.")

    return True


try:
    check_age(15)

except ValueError as error:
    print(error)
```

Output:

```text
Age must be 18 or above.
```

---

# 32. `raise` Without an Argument

Inside an `except` block, `raise` can re-raise the current exception.

```python
try:
    number = 10 / 0

except ZeroDivisionError:
    print("Logging error...")
    raise
```

This is useful when you want to record an error and then let higher-level code handle it.

---

# 33. Custom Exceptions

You can create your own exception class.

Syntax:

```python
class MyError(Exception):
    pass
```

Example:

```python
class AgeError(Exception):
    pass
```

---

# 34. Using Custom Exception

```python
class AgeError(Exception):
    pass


age = 15

if age < 18:
    raise AgeError("Age must be 18 or above.")
```

---

# 35. Handling Custom Exception

```python
class AgeError(Exception):
    pass


try:

    age = 15

    if age < 18:
        raise AgeError("You are not eligible.")

except AgeError as error:
    print(error)
```

Output:

```text
You are not eligible.
```

---

# 36. Custom Exception with a Function

```python
class InsufficientBalanceError(Exception):
    pass


def withdraw(balance, amount):

    if amount > balance:
        raise InsufficientBalanceError(
            "Insufficient balance."
        )

    return balance - amount


try:
    balance = withdraw(1000, 1500)
    print(balance)

except InsufficientBalanceError as error:
    print(error)
```

---

# 37. Input Validation

Exception handling is useful for validating user input.

Example:

```python
while True:

    try:
        age = int(input("Enter your age: "))

        if age < 0:
            raise ValueError("Age cannot be negative.")

        print("Your age is:", age)
        break

    except ValueError as error:
        print("Invalid input:", error)
```

---

# 38. Integer Validation

```python
while True:

    try:
        number = int(input("Enter an integer: "))
        break

    except ValueError:
        print("Please enter an integer.")
```

---

# 39. Float Validation

```python
while True:

    try:
        price = float(input("Enter price: "))
        break

    except ValueError:
        print("Enter a valid number.")
```

---

# 40. Multiple Validation Rules

```python
while True:

    try:

        marks = int(input("Enter marks: "))

        if marks < 0 or marks > 100:
            raise ValueError("Marks must be between 0 and 100.")

        break

    except ValueError as error:
        print("Invalid:", error)

print("Marks:", marks)
```

---

# 41. Exception Handling with Functions

```python
def divide(a, b):

    try:
        return a / b

    except ZeroDivisionError:
        return "Cannot divide by zero."


print(divide(10, 2))
print(divide(10, 0))
```

---

# 42. Exception Handling in a Calculator

```python
try:

    a = float(input("Enter first number: "))
    operator = input("Enter operator (+ - * /): ")
    b = float(input("Enter second number: "))

    if operator == "+":
        result = a + b

    elif operator == "-":
        result = a - b

    elif operator == "*":
        result = a * b

    elif operator == "/":
        result = a / b

    else:
        raise ValueError("Invalid operator.")

    print("Result:", result)

except ValueError as error:
    print("Error:", error)

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

---

# 43. File Exception Handling

```python
try:

    with open("data.txt", "r", encoding="utf-8") as file:
        data = file.read()

except FileNotFoundError:
    print("The file does not exist.")

except PermissionError:
    print("Permission denied.")

else:
    print(data)

finally:
    print("File operation completed.")
```

---

# 44. JSON Exception Handling

```python
import json

try:

    with open("data.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("JSON file not found.")

except json.JSONDecodeError:
    print("Invalid JSON data.")

else:
    print(data)
```

---

# 45. Common JSON Exceptions

When working with JSON, you may encounter:

```text
FileNotFoundError
json.JSONDecodeError
PermissionError
```

Example:

```python
import json

try:
    with open("data.json", encoding="utf-8") as file:
        data = json.load(file)

except json.JSONDecodeError:
    print("JSON format is invalid.")
```

---

# 46. CSV Exception Handling

```python
import csv

try:

    with open(
        "students.csv",
        "r",
        newline="",
        encoding="utf-8"
    ) as file:

        reader = csv.reader(file)

        for row in reader:
            print(row)

except FileNotFoundError:
    print("CSV file not found.")

except OSError as error:
    print("File error:", error)
```

---

# 47. Nested `try`

You can have a `try` block inside another `try` block.

```python
try:

    number = int(input("Enter number: "))

    try:
        result = 100 / number
        print(result)

    except ZeroDivisionError:
        print("Cannot divide by zero.")

except ValueError:
    print("Invalid input.")
```

Nested exception handling should be used only when it makes the error-handling structure clearer.

---

# 48. `else` Example

```python
try:

    number = int(input("Enter number: "))

except ValueError:

    print("Invalid input.")

else:

    print("Valid number:", number)
```

The `else` block executes only if the `try` block succeeds.

---

# 49. `finally` Example

```python
try:

    print("Starting program.")

except Exception:

    print("Error occurred.")

finally:

    print("Cleaning up.")
```

---

# 50. Complete Example

```python
try:

    number = int(input("Enter a number: "))

    if number < 0:
        raise ValueError("Number cannot be negative.")

    result = 100 / number

except ValueError as error:

    print("Value error:", error)

except ZeroDivisionError:

    print("Cannot divide by zero.")

else:

    print("Result:", result)

finally:

    print("Program completed.")
```

---

# 51. Exception Information

An exception object can provide information about the error.

```python
try:
    int("abc")

except ValueError as error:
    print(type(error))
    print(error)
```

Example output:

```text
<class 'ValueError'>
invalid literal for int() with base 10: 'abc'
```

The exact message can vary between Python versions.

---

# 52. Traceback

When an unhandled exception occurs, Python displays a **traceback**.

Example:

```python
def divide(a, b):
    return a / b


result = divide(10, 0)
```

Python displays information including:

```text
Traceback
File
Line number
Exception type
Error message
```

A traceback helps identify where the error occurred.

---

# 53. Reading a Traceback

Example:

```text
Traceback (most recent call last):
    ...
ZeroDivisionError: division by zero
```

Important parts:

```text
1. File name
2. Line number
3. Code causing the problem
4. Exception type
5. Error message
```

---

# 54. Debugging Strategy

When you see an exception:

### Step 1

Read the exception type.

Example:

```text
ValueError
```

### Step 2

Read the message.

Example:

```text
invalid literal for int()
```

### Step 3

Find the line where it occurred.

### Step 4

Check the input and variables.

### Step 5

Fix the actual cause instead of hiding the error.

---

# 55. Don't Hide Errors

Avoid:

```python
try:
    risky_operation()

except:
    pass
```

This silently ignores errors.

It can make debugging very difficult.

Better:

```python
try:
    risky_operation()

except ValueError as error:
    print("Invalid value:", error)
```

---

# 56. `assert`

Python also provides `assert` for checking assumptions.

Syntax:

```python
assert condition
```

Example:

```python
age = 20

assert age >= 18
```

If the condition is false:

```python
assert age >= 18, "Age must be 18 or above."
```

Python raises:

```text
AssertionError
```

Assertions are mainly for programmer/developer assumptions and debugging, not for validating untrusted user input in production.

---

# 57. Example with `assert`

```python
marks = 85

assert 0 <= marks <= 100

print("Valid marks")
```

---

# 58. Assertion Error

```python
marks = 150

assert 0 <= marks <= 100, "Invalid marks"
```

This raises:

```text
AssertionError
```

---

# 59. Exception Handling Best Practices

### 1. Catch specific exceptions

Good:

```python
except ValueError:
```

Avoid unnecessarily broad handlers.

---

### 2. Keep `try` blocks small

Instead of:

```python
try:
    # lots of unrelated code
```

prefer:

```python
try:
    number = int(input("Enter number: "))

except ValueError:
    print("Invalid number.")
```

---

### 3. Give useful error messages

Bad:

```python
print("Error")
```

Better:

```python
print("Please enter a valid integer.")
```

---

### 4. Do not silently ignore exceptions

Avoid:

```python
except:
    pass
```

---

### 5. Use `finally` for cleanup when appropriate

```python
try:
    resource = acquire_resource()

finally:
    release_resource(resource)
```

For files, prefer `with`.

---

# 60. Practical Program – Safe Division

```python
def safe_divide():

    try:

        a = float(input("Enter first number: "))
        b = float(input("Enter second number: "))

        result = a / b

    except ValueError:

        print("Enter valid numbers.")

    except ZeroDivisionError:

        print("Cannot divide by zero.")

    else:

        print("Result:", result)


safe_divide()
```

---

# 61. Practical Program – Age Validator

```python
def get_age():

    while True:

        try:

            age = int(input("Enter your age: "))

            if age < 0 or age > 120:
                raise ValueError("Age must be between 0 and 120.")

            return age

        except ValueError as error:

            print("Invalid:", error)


age = get_age()

print("Your age is:", age)
```

---

# 62. Practical Program – Marks Validator

```python
def get_marks():

    while True:

        try:

            marks = float(input("Enter marks: "))

            if not 0 <= marks <= 100:
                raise ValueError(
                    "Marks must be between 0 and 100."
                )

            return marks

        except ValueError as error:

            print("Invalid:", error)


marks = get_marks()

print("Marks:", marks)
```

---

# 63. Practical Program – Safe Integer Input

```python
def get_integer(message):

    while True:

        try:
            return int(input(message))

        except ValueError:
            print("Please enter a valid integer.")


number = get_integer("Enter a number: ")

print("You entered:", number)
```

---

# 64. Practical Program – Safe File Reader

```python
def read_file(filename):

    try:

        with open(filename, "r", encoding="utf-8") as file:
            return file.read()

    except FileNotFoundError:

        return "File not found."

    except PermissionError:

        return "Permission denied."

    except OSError as error:

        return f"File error: {error}"


print(read_file("data.txt"))
```

---

# 65. Practical Program – Safe JSON Reader

```python
import json


def read_json(filename):

    try:

        with open(filename, "r", encoding="utf-8") as file:
            return json.load(file)

    except FileNotFoundError:

        print("File not found.")

    except json.JSONDecodeError:

        print("Invalid JSON.")

    except OSError as error:

        print("File error:", error)

    return None


data = read_json("student.json")

if data is not None:
    print(data)
```

---

# 66. Practical Program – Login Validation

```python
correct_username = "admin"
correct_password = "1234"

try:

    username = input("Username: ")
    password = input("Password: ")

    if username != correct_username:
        raise ValueError("Invalid username.")

    if password != correct_password:
        raise ValueError("Invalid password.")

    print("Login successful.")

except ValueError as error:

    print("Login failed:", error)
```

For real applications, never store passwords in plain text like this.

---

# 67. Mini Project – Calculator with Exception Handling

```python
def calculator():

    while True:

        try:

            a = float(input("Enter first number: "))
            operator = input("Enter operator (+ - * /): ")
            b = float(input("Enter second number: "))

            if operator == "+":

                result = a + b

            elif operator == "-":

                result = a - b

            elif operator == "*":

                result = a * b

            elif operator == "/":

                result = a / b

            else:

                raise ValueError("Invalid operator.")

            print("Result:", result)

        except ValueError as error:

            print("Error:", error)

        except ZeroDivisionError:

            print("Cannot divide by zero.")

        choice = input("Continue? (y/n): ").lower()

        if choice != "y":
            break


calculator()
```

---

# 68. Mini Project – Student Marks System

```python
def get_marks():

    while True:

        try:

            marks = float(input("Enter marks: "))

            if marks < 0 or marks > 100:
                raise ValueError(
                    "Marks must be between 0 and 100."
                )

            return marks

        except ValueError as error:

            print("Invalid:", error)


name = input("Enter student name: ")

marks = get_marks()

print("\nStudent:", name)
print("Marks:", marks)
```

---

# 69. Mini Project – ATM Withdrawal

```python
class InsufficientBalanceError(Exception):
    pass


balance = 5000

try:

    amount = float(input("Enter withdrawal amount: "))

    if amount <= 0:
        raise ValueError("Amount must be greater than zero.")

    if amount > balance:
        raise InsufficientBalanceError(
            "Insufficient balance."
        )

    balance -= amount

    print("Withdrawal successful.")
    print("Remaining balance:", balance)

except ValueError as error:

    print("Invalid amount:", error)

except InsufficientBalanceError as error:

    print(error)
```

---

# 70. Mini Project – Number Guessing with Validation

```python
import random

secret = random.randint(1, 10)

while True:

    try:

        guess = int(input("Guess a number from 1 to 10: "))

        if not 1 <= guess <= 10:
            raise ValueError(
                "Number must be between 1 and 10."
            )

        if guess == secret:

            print("Correct!")
            break

        elif guess < secret:

            print("Too low.")

        else:

            print("Too high.")

    except ValueError as error:

        print("Invalid input:", error)
```

---

# 71. Mini Project – Contact Book Validation

```python
contacts = {}


def add_contact():

    name = input("Enter name: ").strip()

    if not name:
        raise ValueError("Name cannot be empty.")

    phone = input("Enter phone number: ").strip()

    if not phone.isdigit():
        raise ValueError("Phone number must contain digits only.")

    contacts[name] = phone

    print("Contact added.")


while True:

    print("\n1. Add Contact")
    print("2. View Contacts")
    print("3. Exit")

    choice = input("Choose: ")

    try:

        if choice == "1":

            add_contact()

        elif choice == "2":

            if not contacts:
                print("No contacts.")

            else:
                for name, phone in contacts.items():
                    print(name, ":", phone)

        elif choice == "3":

            print("Goodbye!")
            break

        else:

            raise ValueError("Invalid menu choice.")

    except ValueError as error:

        print("Error:", error)
```

---

# 72. Exception Handling Flow

Remember this flow:

```text
             try
              │
              ▼
       Code executes
              │
       ┌──────┴──────┐
       │             │
   Exception       No Exception
       │             │
       ▼             ▼
    except          else
       │             │
       └──────┬──────┘
              ▼
           finally
              │
              ▼
             End
```

---

# 73. Quick Syntax Revision

### Basic

```python
try:
    risky_code()

except ValueError:
    print("Invalid value.")
```

### With error object

```python
try:
    risky_code()

except ValueError as error:
    print(error)
```

### Multiple exceptions

```python
try:
    risky_code()

except ValueError:
    print("Value error.")

except TypeError:
    print("Type error.")
```

### Else

```python
try:
    risky_code()

except ValueError:
    print("Error.")

else:
    print("Success.")
```

### Finally

```python
try:
    risky_code()

except ValueError:
    print("Error.")

finally:
    print("Finished.")
```

### Raise

```python
raise ValueError("Invalid value")
```

### Custom exception

```python
class MyError(Exception):
    pass
```

---

# 74. Common Mistakes

## Mistake 1 – Using bare `except`

Avoid:

```python
try:
    code()

except:
    print("Error")
```

Prefer:

```python
try:
    code()

except ValueError:
    print("Invalid value")
```

---

## Mistake 2 – Catching `Exception` too early

Avoid:

```python
try:
    code()

except Exception:
    print("Error")

except ValueError:
    print("Value error")
```

The `ValueError` handler is unreachable because `Exception` catches it first.

Correct:

```python
try:
    code()

except ValueError:
    print("Value error")

except Exception:
    print("Other error")
```

---

## Mistake 3 – Empty `except`

Avoid:

```python
except:
    pass
```

This can hide bugs.

---

## Mistake 4 – Using exceptions for normal control flow

Do not intentionally use exceptions for ordinary conditions when a simple `if` check is clearer.

---

## Mistake 5 – Huge `try` blocks

Avoid putting the entire program inside one `try`.

Keep the protected section focused.

---

# 75. Practice Questions

### Question 1

Write a program that handles division by zero.

---

### Question 2

Ask the user for an integer and handle invalid input.

---

### Question 3

Create a program that handles:

```text
ValueError
ZeroDivisionError
```

---

### Question 4

Create a program using:

```text
try
except
else
finally
```

---

### Question 5

Write a program that safely reads a text file.

---

### Question 6

Write a program that safely reads a JSON file.

---

### Question 7

Create a custom exception:

```text
AgeError
```

---

### Question 8

Create a marks validator.

Valid range:

```text
0–100
```

---

### Question 9

Create an ATM withdrawal program with a custom insufficient-balance exception.

---

### Question 10

Create a calculator that handles invalid input and division by zero.

---

### Question 11

Write a function that accepts only positive integers.

---

### Question 12

Create a program that checks whether a file exists before opening it.

---

# 76. Interview Questions

## Q1. What is an exception?

An exception is an event that occurs during program execution that disrupts the normal flow of the program.

---

## Q2. What is exception handling?

Exception handling is a mechanism for detecting and handling runtime errors using constructs such as:

```text
try
except
else
finally
```

---

## Q3. What is `try`?

`try` contains code that may raise an exception.

---

## Q4. What is `except`?

`except` handles an exception raised by the protected code.

---

## Q5. What is `else`?

`else` executes when the `try` block completes without raising an exception.

---

## Q6. What is `finally`?

`finally` is used for code that should run when leaving the `try` statement, whether or not an exception occurred.

---

## Q7. What is `raise`?

`raise` is used to explicitly raise an exception.

Example:

```python
raise ValueError("Invalid age")
```

---

## Q8. What is a custom exception?

A custom exception is a user-defined exception class that normally inherits from `Exception`.

Example:

```python
class MyError(Exception):
    pass
```

---

## Q9. What is `ValueError`?

`ValueError` occurs when a function receives a value of the correct general type but an inappropriate value.

Example:

```python
int("hello")
```

---

## Q10. What is `TypeError`?

`TypeError` occurs when an operation or function is applied to an inappropriate type.

Example:

```python
"10" + 5
```

---

## Q11. What is `ZeroDivisionError`?

It occurs when a number is divided by zero.

Example:

```python
10 / 0
```

---

## Q12. What is `IndexError`?

It occurs when trying to access a sequence position that does not exist.

Example:

```python
numbers = [1, 2, 3]

print(numbers[5])
```

---

## Q13. What is `KeyError`?

It occurs when a dictionary key is not found.

Example:

```python
data = {"name": "Yashu"}

print(data["age"])
```

---

## Q14. What is `FileNotFoundError`?

It occurs when a requested file or directory cannot be found.

---

## Q15. What is the difference between syntax and runtime errors?

```text
Syntax Error
→ Code cannot be parsed correctly.

Runtime Exception
→ Problem occurs while code is executing.
```

---

## Q16. What is the difference between `raise` and `except`?

```text
raise
→ Generates an exception.

except
→ Handles an exception.
```

---

## Q17. Why should we avoid bare `except`?

Because it can catch unexpected exceptions and make debugging difficult. It may also catch exceptions such as `KeyboardInterrupt` if written as a bare `except`.

---

## Q18. What is the purpose of `finally`?

It is useful for cleanup operations that should happen when leaving the `try` statement.

---

## Q19. What is an exception hierarchy?

Python organizes exception classes into parent-child relationships.

For example:

```text
Exception
└── LookupError
    ├── IndexError
    └── KeyError
```

---

## Q20. What is `assert`?

`assert` checks a condition and raises `AssertionError` if the condition is false.

---

# 77. Important Cheat Sheet

```text
try
→ Code that may fail

except
→ Handle exception

else
→ Runs if no exception occurred

finally
→ Runs when leaving try statement

raise
→ Manually raise exception

Exception
→ Base class for most ordinary application exceptions

assert
→ Check a programmer assumption
```

---

# 78. Exception Handling Example to Remember

```python
try:

    number = int(input("Enter number: "))

    if number < 0:
        raise ValueError("Number cannot be negative.")

    result = 100 / number

except ValueError as error:

    print("Invalid value:", error)

except ZeroDivisionError:

    print("Cannot divide by zero.")

else:

    print("Result:", result)

finally:

    print("Program finished.")
```

Understand this example well because it combines the main concepts from this lesson.

---

# 79. Final Revision

Remember:

```text
Python Errors
      ↓
Syntax Errors
Runtime Exceptions
Logical Errors
      ↓
try
      ↓
except
      ↓
else
      ↓
finally
      ↓
raise
      ↓
Custom Exceptions
      ↓
Input Validation
      ↓
Safe File / JSON / CSV Operations
      ↓
Debugging
```

---

# 🎯 Notes 21 Summary

In this lesson, you learned:

* What exceptions are
* Syntax errors
* Runtime exceptions
* Logical errors
* `try`
* `except`
* Multiple `except` blocks
* Specific exception handling
* `else`
* `finally`
* Exception objects
* Exception hierarchy
* `Exception`
* `BaseException`
* `raise`
* Re-raising exceptions
* Custom exceptions
* Input validation
* File exception handling
* JSON exception handling
* CSV exception handling
* `assert`
* Tracebacks
* Debugging
* Exception handling best practices
* Safe calculators
* Age validation
* Marks validation
* ATM withdrawal
* Contact book
* Number guessing
* Interview questions
* Practice questions

---

# 🚀 Next Lesson

## Notes 22 → Python Object-Oriented Programming (OOP)

You will learn:

```text
What is OOP?
Classes
Objects
Attributes
Methods
__init__()
self
Instance variables
Class variables
Instance methods
Class methods
Static methods
Encapsulation
Inheritance
Polymorphism
Abstraction
Method overriding
super()
Magic methods
@property
Getters and setters
Composition
Aggregation
Practical projects
Interview questions
```
