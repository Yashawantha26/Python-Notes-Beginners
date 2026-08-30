Here is your complete **`Notes12.md`**, continuing your Python Beginners Notes series. You can copy it directly into your file.

# Python Beginners Notes – Notes 12

## 📘 Topic: Object-Oriented Programming (OOP) Basics

Object-Oriented Programming, or **OOP**, is a programming approach where we organize programs using **objects and classes**.

OOP is very important for:

* Large Python projects
* Software development
* Web development
* Data science
* AI/ML projects
* Real-world applications

---

# 1. What is OOP?

**OOP = Object-Oriented Programming**

Instead of writing only functions and variables, OOP allows us to combine:

* Data
* Functions

inside **objects**.

Example:

```python
class Student:
    name = "Yashu"
    age = 20
```

Here:

```text
Student → Class
name    → Attribute
age     → Attribute
```

---

# 2. What is a Class?

A **class** is a blueprint or template for creating objects.

Example:

```python
class Student:
    name = "Yashu"
    age = 20
```

The class describes what a student object can contain.

Think of it like:

```text
Class → Blueprint
Object → Actual thing created from blueprint
```

---

# 3. What is an Object?

An **object** is an instance of a class.

Example:

```python
class Student:
    name = "Yashu"


student1 = Student()

print(student1.name)
```

Output:

```text
Yashu
```

Here:

```text
Student  → Class
student1 → Object
```

---

# 4. Simple Real-World Example

Imagine a car.

### Class

```text
Car
```

The class describes:

* Brand
* Model
* Color
* Speed

### Objects

```text
BMW
Toyota
Honda
```

Each object can have different values.

---

# 5. Creating a Simple Class

```python
class Car:
    brand = "Toyota"
    color = "White"


car1 = Car()

print(car1.brand)
print(car1.color)
```

Output:

```text
Toyota
White
```

---

# 6. Creating Multiple Objects

```python
class Student:
    name = "Yashu"


student1 = Student()
student2 = Student()

print(student1.name)
print(student2.name)
```

Output:

```text
Yashu
Yashu
```

Both objects are created from the same class.

---

# 7. Attributes

Attributes are variables that belong to an object or class.

Example:

```python
class Student:
    name = "Yashu"
    age = 20
    branch = "CSE"
```

Here:

```text
name
age
branch
```

are attributes.

---

# 8. Methods

A **method** is a function defined inside a class.

Example:

```python
class Student:

    def greet(self):
        print("Hello Python")


student1 = Student()

student1.greet()
```

Output:

```text
Hello Python
```

---

# 9. Understanding `self`

`self` refers to the **current object**.

Example:

```python
class Student:

    def display(self):
        print("Student details")


student1 = Student()

student1.display()
```

Python internally passes the object to `self`.

---

# 10. Constructor

A constructor is a special method that runs automatically when an object is created.

Python uses:

```python
__init__()
```

Example:

```python
class Student:

    def __init__(self):
        print("Student object created")


student1 = Student()
```

Output:

```text
Student object created
```

---

# 11. `__init__()` Method

The `__init__()` method is commonly used to initialize object data.

Example:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age


student1 = Student("Yashu", 20)

print(student1.name)
print(student1.age)
```

Output:

```text
Yashu
20
```

---

# 12. Why Use `self.name`?

Consider:

```python
self.name = name
```

Here:

```text
name       → parameter
self.name  → object attribute
```

The value passed to `name` is stored inside the object.

---

# 13. Multiple Objects with Different Data

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age


student1 = Student("Yashu", 20)
student2 = Student("Rahul", 21)

print(student1.name)
print(student2.name)
```

Output:

```text
Yashu
Rahul
```

Each object has its own data.

---

# 14. Adding Methods to a Class

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)


student1 = Student("Yashu", 20)

student1.display()
```

Output:

```text
Name: Yashu
Age: 20
```

---

# 15. Class Variables

A class variable is shared by all objects.

Example:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name


student1 = Student("Yashu")
student2 = Student("Rahul")

print(student1.college)
print(student2.college)
```

Output:

```text
RIT Hassan
RIT Hassan
```

---

# 16. Instance Variables

Instance variables belong to individual objects.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name


student1 = Student("Yashu")
student2 = Student("Rahul")

print(student1.name)
print(student2.name)
```

Here:

```text
student1.name → Yashu
student2.name → Rahul
```

---

# 17. Class Variable vs Instance Variable

| Class Variable       | Instance Variable            |
| -------------------- | ---------------------------- |
| Shared by objects    | Different for each object    |
| Defined inside class | Usually defined using `self` |
| Common data          | Object-specific data         |
| Example: college     | Example: name                |

Example:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name
```

Here:

```text
college → Class variable
name    → Instance variable
```

---

# 18. Modifying Object Attributes

```python
class Student:

    def __init__(self, name):
        self.name = name


student1 = Student("Yashu")

student1.name = "Arjun"

print(student1.name)
```

Output:

```text
Arjun
```

---

# 19. Adding Attributes After Object Creation

Python allows you to add attributes.

```python
class Student:
    pass


student1 = Student()

student1.name = "Yashu"
student1.age = 20

print(student1.name)
print(student1.age)
```

---

# 20. `pass` Statement

`pass` is used when a class or function has no implementation yet.

```python
class Student:
    pass
```

This is valid Python code.

---

# 21. Methods with Parameters

```python
class Calculator:

    def add(self, a, b):
        return a + b


calc = Calculator()

print(calc.add(10, 20))
```

Output:

```text
30
```

---

# 22. Methods with Return Values

```python
class Calculator:

    def multiply(self, a, b):
        return a * b


calc = Calculator()

result = calc.multiply(5, 4)

print(result)
```

Output:

```text
20
```

---

# 23. Simple Bank Account Class

```python
class BankAccount:

    def __init__(self, name, balance):
        self.name = name
        self.balance = balance

    def display(self):
        print("Account holder:", self.name)
        print("Balance:", self.balance)


account = BankAccount("Yashu", 5000)

account.display()
```

Output:

```text
Account holder: Yashu
Balance: 5000
```

---

# 24. Adding Deposit Method

```python
class BankAccount:

    def __init__(self, name, balance):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def display(self):
        print("Name:", self.name)
        print("Balance:", self.balance)


account = BankAccount("Yashu", 5000)

account.deposit(2000)

account.display()
```

Output:

```text
Name: Yashu
Balance: 7000
```

---

# 25. Adding Withdraw Method

```python
class BankAccount:

    def __init__(self, name, balance):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
        else:
            print("Insufficient balance")

    def display(self):
        print("Balance:", self.balance)


account = BankAccount("Yashu", 5000)

account.deposit(1000)
account.withdraw(2000)

account.display()
```

Output:

```text
Balance: 4000
```

---

# 26. Encapsulation

**Encapsulation** means combining data and methods inside a class and controlling access to the data.

Example:

```python
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance
```

The double underscore:

```text
__
```

indicates a private-style attribute.

---

# 27. Private Attributes

Example:

```python
class Student:

    def __init__(self, name):
        self.__name = name


student = Student("Yashu")
```

The attribute:

```python
__name
```

is intended to be accessed internally through the class.

---

# 28. Getter Method

A getter can be used to access private data.

```python
class Student:

    def __init__(self, name):
        self.__name = name

    def get_name(self):
        return self.__name


student = Student("Yashu")

print(student.get_name())
```

Output:

```text
Yashu
```

---

# 29. Setter Method

A setter can be used to modify private data.

```python
class Student:

    def __init__(self, name):
        self.__name = name

    def set_name(self, name):
        self.__name = name

    def get_name(self):
        return self.__name


student = Student("Yashu")

student.set_name("Rahul")

print(student.get_name())
```

Output:

```text
Rahul
```

---

# 30. Inheritance

**Inheritance** allows one class to inherit properties and methods from another class.

Example:

```python
class Animal:

    def speak(self):
        print("Animal makes a sound")


class Dog(Animal):
    pass


dog = Dog()

dog.speak()
```

Output:

```text
Animal makes a sound
```

Here:

```text
Animal → Parent class
Dog    → Child class
```

---

# 31. Parent Class

The class being inherited from is called the:

* Parent class
* Base class
* Superclass

Example:

```python
class Animal:
    pass
```

---

# 32. Child Class

The class that inherits another class is called the:

* Child class
* Derived class
* Subclass

Example:

```python
class Dog(Animal):
    pass
```

---

# 33. Inheritance Example

```python
class Vehicle:

    def start(self):
        print("Vehicle started")


class Car(Vehicle):

    def drive(self):
        print("Car is driving")


car = Car()

car.start()
car.drive()
```

Output:

```text
Vehicle started
Car is driving
```

---

# 34. Method Overriding

A child class can provide its own version of a parent method.

```python
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def sound(self):
        print("Dog barks")


dog = Dog()

dog.sound()
```

Output:

```text
Dog barks
```

---

# 35. `super()`

`super()` is used to call methods from the parent class.

Example:

```python
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def sound(self):
        super().sound()
        print("Dog barks")


dog = Dog()

dog.sound()
```

Output:

```text
Animal sound
Dog barks
```

---

# 36. Constructor Inheritance

```python
class Person:

    def __init__(self, name):
        self.name = name


class Student(Person):

    def __init__(self, name, branch):
        super().__init__(name)
        self.branch = branch


student = Student("Yashu", "CSE")

print(student.name)
print(student.branch)
```

Output:

```text
Yashu
CSE
```

---

# 37. Polymorphism

**Polymorphism** means "many forms."

Different classes can have methods with the same name but different behavior.

Example:

```python
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


dog = Dog()
cat = Cat()

dog.sound()
cat.sound()
```

Output:

```text
Bark
Meow
```

---

# 38. Polymorphism with a Function

```python
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


def make_sound(animal):
    animal.sound()


make_sound(Dog())
make_sound(Cat())
```

Output:

```text
Bark
Meow
```

---

# 39. Abstraction

**Abstraction** means hiding unnecessary implementation details and showing only the important functionality.

Python provides the `abc` module for abstract classes.

Example:

```python
from abc import ABC, abstractmethod


class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass
```

---

# 40. Abstract Class

An abstract class cannot normally be used to create a complete object directly when it contains abstract methods.

Example:

```python
from abc import ABC, abstractmethod


class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass


class Dog(Animal):

    def sound(self):
        print("Bark")


dog = Dog()

dog.sound()
```

Output:

```text
Bark
```

---

# 41. Four Main Principles of OOP

The four major principles are:

```text
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
```

---

# 42. OOP Summary

### Encapsulation

Combines data and methods and controls access.

### Inheritance

Allows a child class to reuse parent functionality.

### Polymorphism

Allows the same method name to behave differently.

### Abstraction

Hides unnecessary implementation details.

---

# 43. Real-World OOP Example

Consider a student management system.

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name, age, branch):
        self.name = name
        self.age = age
        self.branch = branch

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)
        print("Branch:", self.branch)
        print("College:", self.college)


student1 = Student("Yashu", 20, "CSE")

student1.display()
```

Output:

```text
Name: Yashu
Age: 20
Branch: CSE
College: RIT Hassan
```

---

# 44. Mini Project – Student Management

```python
class Student:

    def __init__(self, name, roll_no, marks):
        self.name = name
        self.roll_no = roll_no
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Roll No:", self.roll_no)
        print("Marks:", self.marks)

    def result(self):
        if self.marks >= 40:
            print("Result: Pass")
        else:
            print("Result: Fail")


student = Student("Yashu", 101, 85)

student.display()
student.result()
```

Output:

```text
Name: Yashu
Roll No: 101
Marks: 85
Result: Pass
```

---

# 45. Mini Project – Calculator Using OOP

```python
class Calculator:

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
        if b == 0:
            return "Cannot divide by zero"
        return a / b


calc = Calculator()

print("Addition:", calc.add(10, 5))
print("Subtraction:", calc.subtract(10, 5))
print("Multiplication:", calc.multiply(10, 5))
print("Division:", calc.divide(10, 5))
```

Output:

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

---

# 46. Mini Project – Car Class

```python
class Car:

    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def display(self):
        print("Brand:", self.brand)
        print("Model:", self.model)
        print("Year:", self.year)

    def start(self):
        print(self.brand, "car started")


car = Car("Toyota", "Fortuner", 2026)

car.display()
car.start()
```

---

# 47. Practice Questions

## Beginner

### Question 1

Create a `Student` class with:

```text
name
age
branch
```

Create an object and display the values.

---

### Question 2

Create a `Car` class with:

```text
brand
model
price
```

Display the details.

---

### Question 3

Create a `Calculator` class with:

```text
add()
subtract()
multiply()
divide()
```

---

### Question 4

Create a `BankAccount` class with:

```text
deposit()
withdraw()
display_balance()
```

---

### Question 5

Create a `Rectangle` class with:

```text
length
width
```

Add methods to calculate:

```text
Area
Perimeter
```

---

# 48. Intermediate Practice

### Question 6

Create a parent class:

```text
Animal
```

and child classes:

```text
Dog
Cat
```

Override the `sound()` method.

---

### Question 7

Create a `Person` class and inherit it into a `Student` class.

---

### Question 8

Create a class with a private attribute and implement:

```text
getter
setter
```

---

### Question 9

Create a `BankAccount` class with:

* Account holder
* Balance
* Deposit
* Withdrawal
* Balance checking

---

### Question 10

Create a student management system using OOP.

The system should support:

* Add student
* Display student
* Calculate result

---

# 49. Common Mistakes

### Mistake 1: Forgetting `self`

Wrong:

```python
class Student:

    def display():
        print("Hello")
```

Correct:

```python
class Student:

    def display(self):
        print("Hello")
```

---

### Mistake 2: Incorrect constructor

Wrong:

```python
def init(self):
    pass
```

Correct:

```python
def __init__(self):
    pass
```

---

### Mistake 3: Forgetting `self` for attributes

Wrong:

```python
class Student:

    def __init__(self, name):
        name = name
```

Correct:

```python
class Student:

    def __init__(self, name):
        self.name = name
```

---

### Mistake 4: Forgetting to create an object

Class:

```python
class Student:
    pass
```

Create object:

```python
student = Student()
```

---

# 50. Quick Revision

```text
OOP              → Object-Oriented Programming

Class            → Blueprint

Object            → Instance of a class

Attribute         → Data belonging to an object/class

Method            → Function inside a class

self              → Current object

__init__()        → Constructor

Class variable    → Shared by objects

Instance variable → Object-specific data

Encapsulation     → Data + methods / controlled access

Inheritance       → Reuse parent class functionality

Polymorphism      → Same interface, different behavior

Abstraction       → Hide implementation details

super()           → Access parent class functionality

ABC               → Abstract Base Class
```

---

# 🎯 Notes 12 Summary

In this lesson, you learned:

* What OOP is
* Classes
* Objects
* Attributes
* Methods
* `self`
* Constructors
* `__init__()`
* Class variables
* Instance variables
* Encapsulation
* Private attributes
* Getters and setters
* Inheritance
* Parent and child classes
* Method overriding
* `super()`
* Polymorphism
* Abstraction
* Abstract classes
* Four principles of OOP
* Real-world OOP examples
* OOP mini projects
* OOP practice questions

---

# ⭐ Key Point

Remember the basic OOP structure:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name)
        print(self.age)


student = Student("Yashu", 20)

student.display()
```

Think:

```text
Class
  ↓
Object
  ↓
Attributes + Methods
```

And remember the four pillars:

```text
Encapsulation
Inheritance
Polymorphism
Abstraction
```

**Next:** Notes 13 → **Advanced OOP: Class Methods, Static Methods, Properties, Magic Methods & Multiple Inheritance**
