# Python Beginners Notes – Notes 14

## 📘 Topic: Exception Handling & Error Handling in Python

Programs can sometimes encounter unexpected situations.

For example:

* A user enters invalid input
* A file does not exist
* A number is divided by zero
* A dictionary key is missing
* A list index is invalid

Python provides **exception handling** to handle these situations without crashing the entire program.

---

# 1. What is an Error?

An error is a problem in a program that prevents the program from working correctly.

Example:

```python
print("Hello"
```

This produces a syntax error because the closing `)` is missing.

---

# 2. Types of Errors

Common Python errors include:

```text
Syntax Error
Runtime Error
Logical Error
```

---

# 3. Syntax Error

A syntax error occurs when Python code does not follow the correct syntax.

Example:

```python
if 10 > 5
    print("Yes")
```

Output:

```text
SyntaxError
```

Correct:

```python
if 10 > 5:
    print("Yes")
```

---

# 4. Runtime Error

A runtime error happens while the program is running.

Example:

```python
a = 10
b = 0

print(a / b)
```

Output:

```text
ZeroDivisionError
```

The syntax is correct, but the operation cannot be performed.

---

# 5. Logical Error

A logical error occurs when the program runs but produces the wrong result.

Example:

```python
a = 10
b = 20

average = a + b / 2

print(average)
```

The intended formula is:

```text
(a + b) / 2
```

Correct code:

```python
average = (a + b) / 2

print(average)
```

Logical errors do not necessarily produce an error message.

---

# 6. What is an Exception?

An **exception** is an event that occurs during program execution and interrupts the normal flow of the program.

Example:

```python
number = int("abc")
```

Python raises:

```text
ValueError
```

---

# 7. Common Python Exceptions

| Exception             | Meaning                |
| --------------------- | ---------------------- |
| `ValueError`          | Invalid value          |
| `TypeError`           | Invalid operation/type |
| `ZeroDivisionError`   | Division by zero       |
| `IndexError`          | Invalid list index     |
| `KeyError`            | Missing dictionary key |
| `NameError`           | Variable not defined   |
| `FileNotFoundError`   | File does not exist    |
| `AttributeError`      | Invalid attribute      |
| `ImportError`         | Import problem         |
| `ModuleNotFoundError` | Module not found       |

---

# 8. `try` and `except`

Python uses `try` and `except` to handle exceptions.

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
    print("An error occurred")
```

Output:

```text
An error occurred
```

---

# 9. Handling `ZeroDivisionError`

```python
try:
    a = 10
    b = 0

    result = a / b

    print(result)

except ZeroDivisionError:
    print("Cannot divide by zero")
```

Output:

```text
Cannot divide by zero
```

---

# 10. Handling `ValueError`

```python
try:
    age = int(input("Enter your age: "))
    print("Age:", age)

except ValueError:
    print("Please enter a valid number")
```

If the user enters:

```text
abc
```

Output:

```text
Please enter a valid number
```

---

# 11. Handling `TypeError`

Example:

```python
try:
    result = "10" + 5
    print(result)

except TypeError:
    print("Invalid data types")
```

Output:

```text
Invalid data types
```

---

# 12. Handling `IndexError`

```python
numbers = [10, 20, 30]

try:
    print(numbers[5])

except IndexError:
    print("Index does not exist")
```

Output:

```text
Index does not exist
```

---

# 13. Handling `KeyError`

```python
student = {
    "name": "Yashu",
    "age": 20
}

try:
    print(student["branch"])

except KeyError:
    print("Key not found")
```

Output:

```text
Key not found
```

---

# 14. Handling `NameError`

```python
try:
    print(name)

except NameError:
    print("Variable is not defined")
```

Output:

```text
Variable is not defined
```

---

# 15. Handling `FileNotFoundError`

```python
try:
    with open("data.txt", "r") as file:
        print(file.read())

except FileNotFoundError:
    print("File not found")
```

---

# 16. Multiple `except` Blocks

You can handle different exceptions separately.

```python
try:
    number = int(input("Enter number: "))
    result = 10 / number

    print(result)

except ValueError:
    print("Please enter a number")

except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

# 17. Generic `except`

You can use:

```python
except Exception:
```

Example:

```python
try:
    result = 10 / 0

except Exception:
    print("Something went wrong")
```

### Recommendation

Prefer handling specific exceptions when possible.

Better:

```python
except ZeroDivisionError:
```

instead of:

```python
except:
```

---

# 18. Getting the Error Message

You can store the exception in a variable.

```python
try:
    result = 10 / 0

except Exception as e:
    print("Error:", e)
```

Output:

```text
Error: division by zero
```

---

# 19. `else` Block

The `else` block executes when no exception occurs.

Syntax:

```python
try:
    # code
except:
    # error
else:
    # success
```

Example:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid number")

else:
    print("You entered:", number)
```

---

# 20. `finally` Block

The `finally` block always executes whether an exception occurs or not.

Example:

```python
try:
    number = 10 / 2

except ZeroDivisionError:
    print("Cannot divide by zero")

finally:
    print("Program finished")
```

Output:

```text
Program finished
```

---

# 21. `try-except-else-finally`

All four can be used together.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input")

else:
    print("Valid input:", number)

finally:
    print("Execution completed")
```

---

# 22. Flow of Exception Handling

Remember:

```text
try
 ↓
Exception occurs?
 ↓
Yes → except
 ↓
No → else
 ↓
finally
```

The `finally` block runs in both cases.

---

# 23. Raising an Exception

Python allows us to manually generate an exception using:

```python
raise
```

Example:

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative")
```

Output:

```text
ValueError: Age cannot be negative
```

---

# 24. Using `raise` with Input Validation

```python
age = int(input("Enter age: "))

if age < 0:
    raise ValueError("Age must be positive")

print("Age:", age)
```

---

# 25. Custom Exceptions

We can create our own exception classes.

Example:

```python
class InvalidAgeError(Exception):
    pass
```

Use it:

```python
age = -5

if age < 0:
    raise InvalidAgeError("Invalid age")
```

---

# 26. Handling Custom Exceptions

```python
class InvalidAgeError(Exception):
    pass


try:
    age = -5

    if age < 0:
        raise InvalidAgeError("Age cannot be negative")

except InvalidAgeError as e:
    print(e)
```

Output:

```text
Age cannot be negative
```

---

# 27. Why Use Custom Exceptions?

Custom exceptions make programs easier to understand.

Instead of:

```text
ValueError
```

you can have:

```text
InvalidAgeError
```

This clearly describes the problem.

---

# 28. Exception Hierarchy

Python exceptions are organized in a hierarchy.

Simplified structure:

```text
BaseException
    |
    └── Exception
          |
          ├── ValueError
          ├── TypeError
          ├── IndexError
          ├── KeyError
          ├── OSError
          └── ...
```

Most application errors should inherit from:

```python
Exception
```

---

# 29. Catching Multiple Exceptions

You can catch multiple exceptions using a tuple.

```python
try:
    number = int(input("Enter number: "))
    result = 10 / number

except (ValueError, ZeroDivisionError):
    print("Invalid input")
```

---

# 30. Nested `try`

A `try` block can exist inside another `try` block.

```python
try:

    try:
        number = 10 / 0

    except ZeroDivisionError:
        print("Inner error handled")

except Exception:
    print("Outer error")
```

Output:

```text
Inner error handled
```

---

# 31. Exception Handling with Functions

```python
def divide(a, b):

    try:
        return a / b

    except ZeroDivisionError:
        return "Cannot divide by zero"


print(divide(10, 2))
print(divide(10, 0))
```

Output:

```text
5.0
Cannot divide by zero
```

---

# 32. Exception Handling with File Handling

```python
try:

    with open("data.txt", "r") as file:
        data = file.read()

    print(data)

except FileNotFoundError:
    print("The file does not exist")

except PermissionError:
    print("Permission denied")
```

---

# 33. Exception Handling with Lists

```python
numbers = [10, 20, 30]

try:
    index = int(input("Enter index: "))
    print(numbers[index])

except ValueError:
    print("Enter a valid integer")

except IndexError:
    print("Index is out of range")
```

---

# 34. Exception Handling with Dictionaries

```python
student = {
    "name": "Yashu",
    "age": 20
}

try:
    key = input("Enter key: ")
    print(student[key])

except KeyError:
    print("Key does not exist")
```

---

# 35. Exception Handling with User Input

A common pattern:

```python
while True:

    try:
        number = int(input("Enter a number: "))
        break

    except ValueError:
        print("Invalid input. Try again.")

print("Number:", number)
```

This keeps asking until the user enters a valid integer.

---

# 36. Input Validation Example

```python
while True:

    try:
        age = int(input("Enter your age: "))

        if age < 0:
            raise ValueError("Age cannot be negative")

        break

    except ValueError as e:
        print("Invalid:", e)

print("Valid age:", age)
```

---

# 37. Bank Account Example

```python
class BankAccount:

    def __init__(self, balance):
        self.balance = balance

    def withdraw(self, amount):

        if amount <= 0:
            raise ValueError("Amount must be positive")

        if amount > self.balance:
            raise ValueError("Insufficient balance")

        self.balance -= amount


account = BankAccount(5000)

try:
    amount = float(input("Enter withdrawal amount: "))
    account.withdraw(amount)

    print("Withdrawal successful")
    print("Balance:", account.balance)

except ValueError as e:
    print("Error:", e)
```

---

# 38. Custom Bank Exception

```python
class InsufficientBalanceError(Exception):
    pass


class BankAccount:

    def __init__(self, balance):
        self.balance = balance

    def withdraw(self, amount):

        if amount > self.balance:
            raise InsufficientBalanceError(
                "Insufficient balance"
            )

        self.balance -= amount


account = BankAccount(5000)

try:
    account.withdraw(7000)

except InsufficientBalanceError as e:
    print(e)
```

Output:

```text
Insufficient balance
```

---

# 39. Avoiding Bare `except`

This works:

```python
try:
    print(10 / 0)

except:
    print("Error")
```

But it is usually better to write:

```python
try:
    print(10 / 0)

except ZeroDivisionError:
    print("Cannot divide by zero")
```

Why?

Because specific exception handling makes the code:

* Easier to understand
* Easier to debug
* Safer
* More precise

---

# 40. Do Not Hide Errors Unnecessarily

Avoid:

```python
try:
    important_function()

except Exception:
    pass
```

This silently ignores the problem.

Better:

```python
try:
    important_function()

except Exception as e:
    print("Error:", e)
```

Or handle the specific exception you expect.

---

# 41. Exception Handling Best Practices

### 1. Catch specific exceptions

Prefer:

```python
except ValueError:
```

instead of:

```python
except:
```

### 2. Keep `try` blocks small

Avoid putting the entire program inside one `try`.

### 3. Give useful error messages

Example:

```python
print("Please enter a valid age")
```

### 4. Don't silently ignore exceptions

Avoid:

```python
except:
    pass
```

### 5. Use `finally` for cleanup

Useful when something must happen regardless of success or failure.

---

# 42. Debugging vs Exception Handling

### Debugging

Finding and fixing problems in code.

### Exception Handling

Managing expected runtime problems gracefully.

Example:

```text
Debugging:
Why is my calculation wrong?

Exception Handling:
What should happen if the user enters 0?
```

---

# 43. Error vs Exception

| Error                                                    | Exception                               |
| -------------------------------------------------------- | --------------------------------------- |
| General problem in a program                             | Runtime event that can often be handled |
| Syntax errors cannot normally be handled by `try-except` | Many exceptions can be handled          |
| Example: missing `:`                                     | Example: `ValueError`                   |
| Usually fixed in code                                    | Can often be handled during execution   |

---

# 44. Common Exceptions Examples

## ValueError

```python
int("hello")
```

---

## TypeError

```python
"10" + 5
```

---

## ZeroDivisionError

```python
10 / 0
```

---

## IndexError

```python
[1, 2, 3][10]
```

---

## KeyError

```python
{"name": "Yashu"}["age"]
```

---

## NameError

```python
print(x)
```

when `x` has not been defined.

---

## FileNotFoundError

```python
open("missing.txt")
```

when the file does not exist.

---

# 45. Mini Project – Safe Calculator

```python
def calculator():

    try:
        a = float(input("Enter first number: "))
        operator = input("Enter operator (+, -, *, /): ")
        b = float(input("Enter second number: "))

        if operator == "+":
            result = a + b

        elif operator == "-":
            result = a - b

        elif operator == "*":
            result = a * b

        elif operator == "/":
            if b == 0:
                raise ZeroDivisionError(
                    "Cannot divide by zero"
                )

            result = a / b

        else:
            raise ValueError("Invalid operator")

        print("Result:", result)

    except ValueError as e:
        print("Input error:", e)

    except ZeroDivisionError as e:
        print("Calculation error:", e)


calculator()
```

---

# 46. Mini Project – Student Marks

```python
def get_marks():

    try:
        marks = float(input("Enter marks: "))

        if marks < 0 or marks > 100:
            raise ValueError("Marks must be between 0 and 100")

        return marks

    except ValueError as e:
        print("Invalid marks:", e)
        return None


marks = get_marks()

if marks is not None:

    if marks >= 40:
        print("Result: Pass")
    else:
        print("Result: Fail")
```

---

# 47. Mini Project – File Reader

```python
def read_file(filename):

    try:
        with open(filename, "r", encoding="utf-8") as file:
            return file.read()

    except FileNotFoundError:
        return "File not found"

    except PermissionError:
        return "Permission denied"


filename = input("Enter filename: ")

content = read_file(filename)

print(content)
```

---

# 48. Mini Project – Login System

```python
correct_username = "admin"
correct_password = "1234"

try:

    username = input("Enter username: ")
    password = input("Enter password: ")

    if username != correct_username:
        raise ValueError("Invalid username")

    if password != correct_password:
        raise ValueError("Invalid password")

    print("Login successful")

except ValueError as e:
    print("Login failed:", e)
```

---

# 49. Practice Questions

## Beginner

### Question 1

Write a program that divides two numbers and handles:

```text
ZeroDivisionError
```

---

### Question 2

Ask the user for an integer and handle:

```text
ValueError
```

---

### Question 3

Create a program that accesses an invalid list index and handles:

```text
IndexError
```

---

### Question 4

Create a dictionary and safely access a missing key using:

```text
KeyError
```

---

### Question 5

Write a program that opens a file and handles:

```text
FileNotFoundError
```

---

# 50. Intermediate Practice

### Question 6

Create a calculator that handles:

* Invalid numbers
* Invalid operators
* Division by zero

---

### Question 7

Create a program that repeatedly asks for a valid age.

Conditions:

```text
Age must be an integer
Age cannot be negative
```

---

### Question 8

Create a bank account with custom exception:

```text
InsufficientBalanceError
```

---

### Question 9

Create a student marks program.

Conditions:

```text
0 <= marks <= 100
```

Raise an exception if the value is outside this range.

---

### Question 10

Create a file reader that handles:

* File not found
* Permission errors
* Other unexpected errors

---

# 51. Advanced Practice

### Question 11

Create your own custom exception:

```python
InvalidEmailError
```

Use it to validate an email address.

---

### Question 12

Create:

```text
InvalidPasswordError
```

and use it in a password validation system.

---

### Question 13

Create a banking application with:

```text
Deposit
Withdraw
Balance
Custom exceptions
```

---

### Question 14

Create a menu-driven calculator using exception handling.

---

### Question 15

Create a student management program that handles invalid:

```text
Name
Age
Marks
Roll number
```

---

# 52. Quick Revision

```text
Error             → Problem in a program

Exception         → Runtime problem that can often be handled

try               → Code that may cause an exception

except            → Handles an exception

else              → Runs when no exception occurs

finally           → Runs whether exception occurs or not

raise             → Manually raise an exception

Exception         → Base class for most application exceptions

ValueError        → Invalid value

TypeError         → Invalid type/operation

ZeroDivisionError → Division by zero

IndexError        → Invalid list/sequence index

KeyError          → Missing dictionary key

NameError         → Undefined variable/name

FileNotFoundError → File does not exist

Custom Exception  → User-defined exception class
```

---

# 53. Important Syntax

## Basic

```python
try:
    risky_code()

except ValueError:
    print("Invalid value")
```

## With multiple exceptions

```python
try:
    risky_code()

except ValueError:
    print("Invalid value")

except TypeError:
    print("Invalid type")
```

## With `else`

```python
try:
    risky_code()

except ValueError:
    print("Error")

else:
    print("Success")
```

## With `finally`

```python
try:
    risky_code()

except ValueError:
    print("Error")

finally:
    print("Finished")
```

## Raise

```python
if value < 0:
    raise ValueError("Value cannot be negative")
```

---

# 🎯 Notes 14 Summary

In this lesson, you learned:

* What errors are
* Syntax errors
* Runtime errors
* Logical errors
* What exceptions are
* Common Python exceptions
* `try`
* `except`
* Multiple `except` blocks
* `else`
* `finally`
* `raise`
* Custom exceptions
* Exception hierarchy
* Exception handling with functions
* Exception handling with files
* Exception handling with lists
* Exception handling with dictionaries
* Input validation
* Debugging vs exception handling
* Exception handling best practices
* Safe programming techniques
* Calculator mini project
* Student marks mini project
* File reader mini project
* Login mini project
* Practice questions

---

# ⭐ Most Important Concept

Remember this structure:

```python
try:
    # Code that may cause an exception

except SpecificException:
    # Handle the error

else:
    # Runs if there is no error

finally:
    # Always runs
```

And remember:

```text
try      → Try the operation
except   → Handle the problem
else     → Continue after success
finally  → Always perform cleanup
raise    → Create an exception manually
```

**Next:** Notes 15 → **Python Regular Expressions (Regex)**
