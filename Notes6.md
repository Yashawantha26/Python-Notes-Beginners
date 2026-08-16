🐍 Notes 6 — Python Functions
# 🐍 Python Notes 6 — Functions


> A complete beginner-friendly guide to Python Functions with syntax, parameters, arguments, return values, scope, recursion, lambda functions, `*args`, `**kwargs`, and practice programs.


---


## 📌 Table of Contents


1. What is a Function?
2. Why Use Functions?
3. Creating a Function
4. Calling a Function
5. Function Syntax
6. Parameters
7. Arguments
8. Multiple Parameters
9. Return Value
10. `print()` vs `return`
11. Default Arguments
12. Keyword Arguments
13. Positional Arguments
14. Positional vs Keyword Arguments
15. Arbitrary Arguments `*args`
16. Arbitrary Keyword Arguments `**kwargs`
17. Combining Arguments
18. Local Variables
19. Global Variables
20. `global` Keyword
21. Function Documentation
22. Passing Lists to Functions
23. Passing Dictionaries to Functions
24. Returning Multiple Values
25. Function as a Variable
26. Nested Functions
27. Recursive Functions
28. Lambda Functions

Calling the function:

greet()

Output:

Hello!
2. ⭐ Why Use Functions?

Functions make programs:

Easier to understand
Easier to maintain
Reusable
Shorter
More organized
Easier to test

Without a function:

print("Hello Yashu")
print("Hello Yashu")
print("Hello Yashu")

With a function:

def greet():
    print("Hello Yashu")


greet()
greet()
greet()
3. 🛠️ Creating a Function

Use the def keyword.

Syntax:

def function_name():
    # code

Example:

def greet():
    print("Hello, Python!")
4. 📞 Calling a Function

Creating a function does not automatically execute it.

You need to call it.

def greet():
    print("Hello!")


greet()

Output:

Hello!
5. 📝 Function Syntax

Basic structure:

def function_name(parameters):
    statements
    return value

Example:

def add(a, b):
    result = a + b
    return result

Call:

answer = add(10, 20)


print(answer)

Output:

30
6. 📦 Parameters

A parameter is a variable written inside the function definition.

Example:

def greet(name):
    print("Hello", name)

Here:

name → parameter
7. 🎯 Arguments

An argument is the actual value passed to a function.

def greet(name):
    print("Hello", name)


greet("Yashu")

Here:

name  → parameter
"Yashu" → argument

Output:

Hello Yashu
8. 👥 Multiple Parameters

A function can have multiple parameters.

def add(a, b):
    print(a + b)


add(10, 20)

Output:

30

Another example:

def student(name, age, branch):
    print("Name:", name)
    print("Age:", age)
    print("Branch:", branch)


student("Yashu", 20, "CSE")
9. 🔙 Return Value

The return statement sends a value back from a function.

Example:

def add(a, b):
    return a + b


result = add(10, 20)


print(result)

Output:

30
10. 🆚 print() vs return

This is very important.

print()

Displays something on the screen.

def add(a, b):
    print(a + b)
return

Sends the result back so it can be stored or used later.

def add(a, b):
    return a + b

Example:

result = add(10, 20)


print(result * 2)

Output:

60
11. 🔢 Function Without Return
def greet():
    print("Hello")


result = greet()


print(result)

Output:

Hello
None

If a function does not explicitly return a value, Python returns None.

12. ⚙️ Default Arguments

A parameter can have a default value.

def greet(name="Guest"):
    print("Hello", name)


greet()
greet("Yashu")

Output:

Hello Guest
Hello Yashu
13. 🔑 Keyword Arguments

You can specify arguments using parameter names.

def student(name, age):
    print(name, age)


student(age=20, name="Yashu")

Output:

Yashu 20

The order does not matter when using keyword arguments.

14. 📍 Positional Arguments

Arguments can also be passed according to their position.

def student(name, age):
    print(name)
    print(age)


student("Yashu", 20)

Here:

"Yashu" → name
20       → age
15. 🆚 Positional vs Keyword Arguments
Positional
student("Yashu", 20)
Keyword
student(name="Yashu", age=20)

Both work.

16. ⚠️ Argument Order

This is valid:

def student(name, age=20):
    print(name, age)

This is invalid:

def student(age=20, name):
    print(name, age)

A non-default parameter cannot normally come after a default parameter.

Correct:

def student(name, age=20):
    print(name, age)
17. 📦 Arbitrary Arguments — *args

*args allows a function to accept any number of positional arguments.

def add_numbers(*numbers):
    print(numbers)


add_numbers(10, 20, 30, 40)

Output:

(10, 20, 30, 40)

Inside the function, args is a tuple.

18. ➕ Sum Using *args
def add_numbers(*numbers):
    total = 0


    for number in numbers:
        total += number


    return total


print(add_numbers(10, 20))
print(add_numbers(10, 20, 30, 40))

Output:

30
100
19. 🔑 Arbitrary Keyword Arguments — **kwargs

**kwargs allows a function to accept any number of keyword arguments.

def student_info(**details):
    print(details)


student_info(
    name="Yashu",
    age=20,
    branch="CSE"
)

Output:

{'name': 'Yashu', 'age': 20, 'branch': 'CSE'}

Inside the function, kwargs is a dictionary.

20. 🔄 Loop Through **kwargs
def student_info(**details):
    for key, value in details.items():
        print(key, ":", value)


student_info(
    name="Yashu",
    age=20,
    branch="CSE"
)

Output:

name : Yashu
age : 20
branch : CSE
21. 🧩 Combining Parameters, *args, and **kwargs

Example:

def example(name, *args, **kwargs):
    print("Name:", name)
    print("Extra values:", args)
    print("Details:", kwargs)


example(
    "Yashu",
    10,
    20,
    age=20,
    branch="CSE"
)

Output:

Name: Yashu
Extra values: (10, 20)
Details: {'age': 20, 'branch': 'CSE'}
22. 🌍 Local Variables

A variable created inside a function is usually a local variable.

def test():
    x = 10
    print(x)


test()

x exists inside the function's local scope.

23. 🌎 Global Variables

A variable created outside a function is a global variable.

x = 100


def test():
    print(x)


test()

Output:

100

The function can read the global variable.

24. ⚠️ Local vs Global
x = 100


def test():
    x = 50
    print(x)


test()


print(x)

Output:

50
100

The local x does not change the global x.

25. 🌐 global Keyword

Use global when you want to modify a global variable inside a function.

x = 10


def change():
    global x
    x = 50


change()


print(x)

Output:

50

Avoid unnecessary global variables in larger programs. Returning values is usually cleaner.

26. 📚 Function Documentation

A function can have a docstring explaining what it does.

def add(a, b):
    """
    Returns the sum of two numbers.
    """
    return a + b

You can see the documentation:

print(add.__doc__)
27. 📋 Passing a List to a Function

Functions can accept lists.

def display_fruits(fruits):
    for fruit in fruits:
        print(fruit)


my_fruits = ["Apple", "Banana", "Mango"]


display_fruits(my_fruits)

Output:

Apple
Banana
Mango
28. 📊 Calculate List Sum Using Function
def calculate_sum(numbers):
    return sum(numbers)


numbers = [10, 20, 30, 40]


print(calculate_sum(numbers))

Output:

100
29. 📖 Passing a Dictionary
def display_student(student):
    print("Name:", student["name"])
    print("Age:", student["age"])


student = {
    "name": "Yashu",
    "age": 20
}


display_student(student)
30. 🔙 Returning Multiple Values

A function can return multiple values.

def calculate(a, b):
    total = a + b
    difference = a - b
    product = a * b


    return total, difference, product


result = calculate(10, 5)


print(result)

Output:

(15, 5, 50)

You can unpack them:

total, difference, product = calculate(10, 5)


print(total)
print(difference)
print(product)
31. 🧮 Calculator Function
def calculator(a, b):
    return {
        "addition": a + b,
        "subtraction": a - b,
        "multiplication": a * b,
        "division": a / b
    }


result = calculator(20, 5)


print(result)
32. 🔄 Function as a Variable

Functions are objects in Python.

You can assign a function to another variable.

def greet():
    print("Hello!")


message = greet


message()

Output:

Hello!
33. 🪆 Nested Functions

A function can be defined inside another function.

def outer():
    
    def inner():
        print("Inside inner function")


    inner()


outer()

Output:

Inside inner function
34. 🔁 Recursive Functions

A function that calls itself is called a recursive function.

Example:

def countdown(n):
    if n == 0:
        return


    print(n)


    countdown(n - 1)


countdown(5)

Output:

5
4
3
2
1

Every recursive function needs a base condition to stop.

35. 🧮 Factorial Using Recursion

Factorial:

5! = 5 × 4 × 3 × 2 × 1

Program:

def factorial(n):
    if n == 0 or n == 1:
        return 1


    return n * factorial(n - 1)


print(factorial(5))

Output:

120
36. 🐢 Fibonacci Using Recursion
def fibonacci(n):
    if n <= 1:
        return n


    return fibonacci(n - 1) + fibonacci(n - 2)


for i in range(10):
    print(fibonacci(i))

Output:

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

Recursive Fibonacci is useful for learning recursion, but an iterative approach is much more efficient for larger values.

37. ⚡ Lambda Functions

A lambda is a small anonymous function.

Normal function:

def square(x):
    return x ** 2

Lambda:

square = lambda x: x ** 2

Use:

print(square(5))

Output:

25
38. 🧮 Lambda with Two Arguments
add = lambda a, b: a + b


print(add(10, 20))

Output:

30
39. 🟢 Lambda with Condition
check = lambda n: "Even" if n % 2 == 0 else "Odd"


print(check(10))
print(check(7))

Output:

Even
Odd
40. 🗺️ map()

map() applies a function to every item in an iterable.

Example:

numbers = [1, 2, 3, 4]


squares = list(map(lambda x: x ** 2, numbers))


print(squares)

Output:

[1, 4, 9, 16]
41. 🔎 filter()

filter() keeps items that satisfy a condition.

numbers = [1, 2, 3, 4, 5, 6]


even_numbers = list(
    filter(lambda x: x % 2 == 0, numbers)
)


print(even_numbers)

Output:

[2, 4, 6]
42. ➗ reduce()

reduce() repeatedly combines values into one result.

It must be imported from functools.

from functools import reduce


numbers = [1, 2, 3, 4]


result = reduce(
    lambda a, b: a + b,
    numbers
)


print(result)

Output:

10
43. 🧠 Higher-Order Functions

A function is called a higher-order function when it:

Takes another function as an argument, or
Returns a function.

Example:

def apply_function(function, value):
    return function(value)


def square(x):
    return x ** 2


print(apply_function(square, 5))

Output:

25
44. 🏗️ Function Returning a Function
def multiplier(n):


    def multiply(x):
        return x * n


    return multiply


double = multiplier(2)


print(double(5))

Output:

10
45. 🧰 Useful Built-in Functions

Python already provides many functions.

Function	Purpose
print()	Display output
len()	Find length
type()	Find data type
int()	Convert to integer
float()	Convert to float
str()	Convert to string
sum()	Calculate sum
max()	Find maximum
min()	Find minimum
sorted()	Sort values
range()	Generate sequence
abs()	Absolute value
round()	Round number
46. 🔢 Even or Odd Function
def check_even_odd(number):


    if number % 2 == 0:
        return "Even"


    return "Odd"


print(check_even_odd(10))
print(check_even_odd(7))

Output:

Even
Odd
47. 🔢 Positive, Negative or Zero
def check_number(number):


    if number > 0:
        return "Positive"


    elif number < 0:
        return "Negative"


    else:
        return "Zero"


print(check_number(10))
print(check_number(-5))
print(check_number(0))
48. 🏆 Find Largest Number
def find_largest(numbers):
    return max(numbers)


numbers = [10, 50, 20, 80, 30]


print(find_largest(numbers))

Output:

80
49. 🏆 Find Largest Without max()
def find_largest(numbers):


    largest = numbers[0]


    for number in numbers:


        if number > largest:
            largest = number


    return largest


numbers = [10, 50, 20, 80, 30]


print(find_largest(numbers))
50. 🔢 Count Even Numbers
def count_even(numbers):


    count = 0


    for number in numbers:


        if number % 2 == 0:
            count += 1


    return count


numbers = [1, 2, 3, 4, 5, 6]


print(count_even(numbers))

Output:

3
51. 🔤 Reverse a String
def reverse_string(text):
    return text[::-1]


print(reverse_string("Python"))

Output:

nohtyP
52. 🔍 Check Palindrome

A palindrome reads the same forward and backward.

Examples:

madam
level
radar

Function:

def is_palindrome(text):


    return text == text[::-1]


print(is_palindrome("madam"))
print(is_palindrome("python"))

Output:

True
False
53. 🔢 Factorial Using Loop
def factorial(n):


    result = 1


    for i in range(1, n + 1):
        result *= i


    return result


print(factorial(5))

Output:

120
54. 🔢 Prime Number Function
def is_prime(number):


    if number < 2:
        return False


    for i in range(2, int(number ** 0.5) + 1):


        if number % i == 0:
            return False


    return True


print(is_prime(7))
print(is_prime(10))

Output:

True
False
55. 🔢 Generate Prime Numbers
def is_prime(number):


    if number < 2:
        return False


    for i in range(2, int(number ** 0.5) + 1):


        if number % i == 0:
            return False


    return True




def generate_primes(limit):


    primes = []


    for number in range(2, limit + 1):


        if is_prime(number):
            primes.append(number)


    return primes




print(generate_primes(20))

Output:

[2, 3, 5, 7, 11, 13, 17, 19]
56. 📊 Student Grade Function
def calculate_grade(marks):


    if marks >= 90:
        return "A+"


    elif marks >= 80:
        return "A"


    elif marks >= 70:
        return "B"


    elif marks >= 60:
        return "C"


    elif marks >= 50:
        return "D"


    else:
        return "F"




print(calculate_grade(92))
print(calculate_grade(75))
print(calculate_grade(45))
57. 🧮 Calculator Using Functions
def add(a, b):
    return a + b




def subtract(a, b):
    return a - b




def multiply(a, b):
    return a * b




def divide(a, b):


    if b == 0:
        return "Cannot divide by zero"


    return a / b




print(add(10, 5))
print(subtract(10, 5))
print(multiply(10, 5))
print(divide(10, 5))
58. 🏧 Simple ATM Example
balance = 10000




def check_balance():
    return balance




def deposit(amount):
    global balance
    balance += amount




def withdraw(amount):


    global balance


    if amount > balance:
        return "Insufficient balance"


    balance -= amount
    return "Withdrawal successful"




deposit(2000)


print("Balance:", check_balance())


print(withdraw(3000))


print("Balance:", check_balance())

For larger programs, using classes or returning updated values is generally cleaner than relying heavily on global state.

59. 🛒 Shopping Cart Function
def calculate_total(cart):


    total = 0


    for item, price in cart.items():
        total += price


    return total




cart = {
    "Laptop": 50000,
    "Mouse": 1000,
    "Keyboard": 1500
}


print("Total:", calculate_total(cart))

Output:

Total: 52500
60. 📚 Function Naming Best Practices

Use meaningful names.

❌ Bad:

def x(a, b):
    return a + b

✅ Better:

def calculate_total(price, tax):
    return price + tax

Recommended style:

snake_case

Examples:

calculate_average()
find_largest()
check_prime()
get_student_marks()
61. 🎯 Function Best Practices

Good functions should usually:

Do one clear task
Have meaningful names
Accept necessary inputs
Return useful results
Avoid unnecessary global variables
Be easy to test
Avoid repeating code

Example:

def calculate_average(marks):
    return sum(marks) / len(marks)

This is better than mixing input, calculations, and output into one large block.

62. 🧪 Testing a Function

You can test different inputs.

def add(a, b):
    return a + b




print(add(2, 3))
print(add(10, 20))
print(add(-5, 5))

Expected:

5
30
0
63. 🧠 Common Mistakes
Mistake 1 — Forgetting parentheses

❌

greet

✅

greet()
Mistake 2 — Forgetting return
def add(a, b):
    a + b

This returns None.

Correct:

def add(a, b):
    return a + b
Mistake 3 — Wrong indentation

❌

def greet():
print("Hello")

✅

def greet():
    print("Hello")
Mistake 4 — Too many responsibilities

Avoid functions that try to do everything.

Prefer:

get_marks()
calculate_total()
calculate_average()
calculate_grade()

instead of one huge function.

64. 📝 Practice Questions
Beginner
Create a function that prints "Hello Python".
Create a function that accepts a name.
Create a function that adds two numbers.
Create a function that subtracts two numbers.
Create a function that multiplies two numbers.
Create a function that divides two numbers.
Create a function that checks even/odd.
Create a function that checks positive/negative.
Create a function that returns the square of a number.
Create a function that returns the cube of a number.
65. 📝 Intermediate Practice
Find the largest number using a function.
Find the smallest number.
Calculate the average of a list.
Count even numbers.
Count odd numbers.
Reverse a string.
Check palindrome.
Check prime number.
Generate prime numbers.
Calculate factorial.
Generate Fibonacci numbers.
Find the sum of a list.
Find the longest word.
Find the shortest word.
Remove duplicates.
66. 📝 Advanced Practice
Use *args to calculate the sum of any number of values.
Use **kwargs to display student information.
Create a calculator using functions.
Create a contact book using functions.
Create a student marks system.
Create a shopping cart.
Create a simple ATM system.
Create a number guessing game using functions.
Create a password validation function.
Create a menu-driven program using functions.
67. 🚀 Mini Project — Student Management

Create functions:

add_student()
display_students()
search_student()
update_student()
delete_student()
calculate_average()

Example data:

students = {
    "101": {
        "name": "Yashu",
        "marks": 90
    },
    "102": {
        "name": "Rahul",
        "marks": 85
    }
}
68. 🚀 Mini Project — Calculator

Create:

add()
subtract()
multiply()
divide()

Then create a menu:

1. Add
2. Subtract
3. Multiply
4. Divide
5. Exit
69. 🚀 Mini Project — Contact Book

Functions:

add_contact()
view_contacts()
search_contact()
update_contact()
delete_contact()

Store data using a dictionary.

70. 🎯 Quick Revision
Create a function
def greet():
    print("Hello")
Call
greet()
Parameter
def greet(name):
    print(name)
Argument
greet("Yashu")
Return
def add(a, b):
    return a + b
Default argument
def greet(name="Guest"):
    print(name)
Keyword argument
greet(name="Yashu")
*args
def numbers(*args):
    print(args)
**kwargs
def student(**kwargs):
    print(kwargs)
Lambda
square = lambda x: x ** 2
Map
list(map(lambda x: x * 2, numbers))
Filter
list(filter(lambda x: x % 2 == 0, numbers))
Recursion
def countdown(n):
    if n == 0:
        return
    print(n)
    countdown(n - 1)
71. 🧠 Most Important Concepts

Before moving forward, make sure you understand:

✅ def
✅ Function call
✅ Parameters
✅ Arguments
✅ return
✅ Default arguments
✅ Keyword arguments
✅ *args
✅ **kwargs
✅ Local scope
✅ Global scope
✅ Recursion
✅ Lambda
✅ map()
✅ filter()
🚀 Python Learning Path
Notes 1  → Python Basics
     ↓
Notes 2  → Control Flow
     ↓
Notes 3  → Strings
     ↓
Notes 4  → Lists
     ↓
Notes 5  → Tuples, Sets & Dictionaries
     ↓
Notes 6  → Functions ✅
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
⭐ Final Tip

Think of a function like a machine:

       INPUT
         ↓
   ┌─────────────┐
   │   FUNCTION  │
   │             │
   │  Processing │
   └─────────────┘
         ↓
       OUTPUT

Example:

def add(a, b):
    return a + b
10 + 20
   ↓
 add()
   ↓
  30

The most important idea is:

Write code once, reuse it many times.

def learn():
    print("Practice Python every day!")


learn()
learn()
learn()

Happy Coding! 🐍💻🔥


