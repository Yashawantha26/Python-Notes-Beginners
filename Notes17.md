Here is your complete **`Notes17.md`**, continuing your Python Beginners Notes series.

# Python Beginners Notes – Notes 17

## 📘 Topic: Object-Oriented Programming (OOP) in Python

**Object-Oriented Programming (OOP)** is a programming approach where programs are organized around **objects and classes**.

OOP helps us build programs that are:

* Organized
* Reusable
* Maintainable
* Scalable
* Easier to understand

Python strongly supports object-oriented programming.

---

# 1. What is OOP?

OOP stands for:

```text
Object-Oriented Programming
```

Instead of writing only separate functions, we create **objects** that contain:

```text
Data + Functions
```

Example:

```text
Student
 ├── name
 ├── age
 ├── marks
 │
 ├── study()
 └── display()
```

Here:

* `name`, `age`, `marks` → Data
* `study()`, `display()` → Methods

---

# 2. What is a Class?

A **class** is a blueprint or template for creating objects.

Example:

```python
class Student:
    pass
```

Here:

```text
Student → Class
```

---

# 3. What is an Object?

An **object** is an instance of a class.

Example:

```python
class Student:
    pass


student1 = Student()
student2 = Student()
```

Here:

```text
Student → Class

student1 → Object
student2 → Object
```

---

# 4. Class and Object Example

```python
class Student:
    name = "Yashu"
    age = 20


student1 = Student()

print(student1.name)
print(student1.age)
```

Output:

```text
Yashu
20
```

---

# 5. Creating a Class

Syntax:

```python
class ClassName:
    # attributes
    # methods
```

Example:

```python
class Car:
    brand = "Toyota"
    color = "White"
```

---

# 6. Creating an Object

```python
class Car:
    brand = "Toyota"


car1 = Car()

print(car1.brand)
```

Output:

```text
Toyota
```

---

# 7. Attributes

Attributes are variables associated with an object or class.

Example:

```python
class Student:
    name = "Yashu"
    age = 20
```

Here:

```text
name → Attribute
age  → Attribute
```

---

# 8. Methods

Methods are functions defined inside a class.

Example:

```python
class Student:

    def display(self):
        print("Student details")
```

Create object:

```python
student = Student()

student.display()
```

Output:

```text
Student details
```

---

# 9. The `self` Parameter

`self` refers to the **current object**.

Example:

```python
class Student:

    def display(self):
        print("Hello")


student = Student()

student.display()
```

Python automatically passes the object as `self`.

---

# 10. `self` with Attributes

```python
class Student:

    def set_details(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)


student = Student()

student.set_details("Yashu", 20)

student.display()
```

Output:

```text
Name: Yashu
Age: 20
```

---

# 11. The `__init__()` Method

`__init__()` is a special method that is commonly used to initialize an object.

Example:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age
```

Create object:

```python
student = Student("Yashu", 20)

print(student.name)
print(student.age)
```

Output:

```text
Yashu
20
```

---

# 12. Constructor

In beginner-level Python terminology, `__init__()` is often called the **constructor**.

More precisely, `__init__()` initializes an already-created instance; object creation itself is handled by `__new__()`.

For normal Python programs, you will most commonly work with `__init__()`.

---

# 13. Multiple Objects

A class can create many objects.

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age


student1 = Student("Yashu", 20)
student2 = Student("Rahul", 21)
student3 = Student("Arun", 22)

print(student1.name)
print(student2.name)
print(student3.name)
```

Output:

```text
Yashu
Rahul
Arun
```

Each object has its own data.

---

# 14. Instance Attributes

Attributes created using `self` are usually **instance attributes**.

Example:

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
```

Here:

```text
self.name
self.marks
```

belong to each individual object.

---

# 15. Class Attributes

A class attribute belongs to the class and is shared unless an instance provides its own attribute with the same name.

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

# 16. Instance vs Class Attributes

| Instance Attribute                | Class Attribute               |
| --------------------------------- | ----------------------------- |
| Belongs to an individual instance | Belongs to the class          |
| Usually created using `self`      | Defined directly inside class |
| Can differ between objects        | Commonly shared               |
| Example: `self.name`              | Example: `college`            |

Example:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name
```

---

# 17. Changing Instance Attributes

```python
class Student:

    def __init__(self, name):
        self.name = name


student = Student("Yashu")

print(student.name)

student.name = "Rahul"

print(student.name)
```

Output:

```text
Yashu
Rahul
```

---

# 18. Adding Attributes Dynamically

Python allows attributes to be added to an instance.

```python
class Student:
    pass


student = Student()

student.name = "Yashu"
student.age = 20

print(student.name)
print(student.age)
```

For clean application design, defining expected attributes in `__init__()` is usually clearer.

---

# 19. Methods with Parameters

```python
class Calculator:

    def add(self, a, b):
        return a + b


calculator = Calculator()

print(calculator.add(10, 20))
```

Output:

```text
30
```

---

# 20. Instance Methods

An instance method works with an object.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def display(self):
        print("Name:", self.name)
```

---

# 21. Class Methods

A class method receives the class as its first argument, usually named `cls`.

Use:

```python
@classmethod
```

Example:

```python
class Student:

    college = "RIT Hassan"

    @classmethod
    def display_college(cls):
        print(cls.college)


Student.display_college()
```

Output:

```text
RIT Hassan
```

---

# 22. Static Methods

A static method does not automatically receive `self` or `cls`.

Use:

```python
@staticmethod
```

Example:

```python
class Calculator:

    @staticmethod
    def add(a, b):
        return a + b


print(Calculator.add(10, 20))
```

Output:

```text
30
```

---

# 23. Instance vs Class vs Static Method

| Method          | First automatic argument | Decorator       |
| --------------- | ------------------------ | --------------- |
| Instance method | `self`                   | None            |
| Class method    | `cls`                    | `@classmethod`  |
| Static method   | None                     | `@staticmethod` |

---

# 24. Four Main Principles of OOP

The four commonly taught pillars are:

```text
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
```

These are very important for interviews and software development.

---

# 25. Encapsulation

**Encapsulation** means combining data and methods within a class and controlling how internal state is accessed or modified.

Example:

```python
class BankAccount:

    def __init__(self, balance):
        self._balance = balance

    def get_balance(self):
        return self._balance

    def deposit(self, amount):
        if amount > 0:
            self._balance += amount


account = BankAccount(1000)

account.deposit(500)

print(account.get_balance())
```

Output:

```text
1500
```

---

# 26. Single Underscore `_`

A single underscore is commonly used as a convention indicating:

```text
"Internal use"
```

Example:

```python
self._balance
```

Python does not strictly prevent access.

---

# 27. Double Underscore `__`

Double underscore triggers **name mangling** for instance attributes.

Example:

```python
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance
```

Direct access:

```python
account.__balance
```

does not work normally because the attribute is name-mangled.

---

# 28. Getter Method

A getter retrieves data.

```python
class Student:

    def __init__(self, marks):
        self.__marks = marks

    def get_marks(self):
        return self.__marks
```

---

# 29. Setter Method

A setter changes data while allowing validation.

```python
class Student:

    def __init__(self, marks):
        self.__marks = marks

    def set_marks(self, marks):

        if 0 <= marks <= 100:
            self.__marks = marks
        else:
            print("Invalid marks")

    def get_marks(self):
        return self.__marks
```

---

# 30. Using `@property`

Python provides a cleaner property-based approach.

```python
class Student:

    def __init__(self, marks):
        self._marks = marks

    @property
    def marks(self):
        return self._marks

    @marks.setter
    def marks(self, value):

        if 0 <= value <= 100:
            self._marks = value
        else:
            raise ValueError("Marks must be between 0 and 100")
```

Usage:

```python
student = Student(80)

print(student.marks)

student.marks = 90

print(student.marks)
```

---

# 31. Inheritance

**Inheritance** allows one class to reuse and extend another class.

Example:

```python
class Animal:

    def eat(self):
        print("Animal is eating")


class Dog(Animal):
    pass


dog = Dog()

dog.eat()
```

Output:

```text
Animal is eating
```

Here:

```text
Animal → Parent class
Dog    → Child class
```

---

# 32. Parent and Child Class

Another terminology:

```text
Parent class
Base class
Super class
```

and:

```text
Child class
Derived class
Subclass
```

---

# 33. Adding Child-Specific Methods

```python
class Animal:

    def eat(self):
        print("Eating")


class Dog(Animal):

    def bark(self):
        print("Barking")


dog = Dog()

dog.eat()
dog.bark()
```

Output:

```text
Eating
Barking
```

---

# 34. Method Overriding

A child class can provide its own implementation of a parent method.

```python
class Animal:

    def sound(self):
        print("Animal makes a sound")


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

`super()` is used to access functionality from a parent class.

Example:

```python
class Animal:

    def __init__(self, name):
        self.name = name


class Dog(Animal):

    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed


dog = Dog("Bruno", "Labrador")

print(dog.name)
print(dog.breed)
```

Output:

```text
Bruno
Labrador
```

---

# 36. Multilevel Inheritance

Inheritance can occur across multiple levels.

```text
Animal
   ↓
Mammal
   ↓
Dog
```

Example:

```python
class Animal:

    def eat(self):
        print("Eating")


class Mammal(Animal):

    def walk(self):
        print("Walking")


class Dog(Mammal):

    def bark(self):
        print("Barking")


dog = Dog()

dog.eat()
dog.walk()
dog.bark()
```

---

# 37. Multiple Inheritance

A class can inherit from more than one parent.

```python
class Father:

    def skill1(self):
        print("Programming")


class Mother:

    def skill2(self):
        print("Design")


class Child(Father, Mother):
    pass


child = Child()

child.skill1()
child.skill2()
```

Output:

```text
Programming
Design
```

---

# 38. Hierarchical Inheritance

Multiple child classes inherit from one parent.

```text
        Animal
       /      \
     Dog      Cat
```

Example:

```python
class Animal:

    def eat(self):
        print("Eating")


class Dog(Animal):

    def bark(self):
        print("Barking")


class Cat(Animal):

    def meow(self):
        print("Meowing")
```

---

# 39. Hybrid Inheritance

Hybrid inheritance combines multiple inheritance patterns.

Example:

```text
       A
      / \
     B   C
      \ /
       D
```

Python supports complex inheritance structures, but they should be designed carefully.

---

# 40. Method Resolution Order (MRO)

When multiple inheritance is involved, Python uses **MRO** to determine the order in which classes are searched.

Use:

```python
print(ClassName.mro())
```

Example:

```python
class A:
    pass


class B(A):
    pass


class C(B):
    pass


print(C.mro())
```

Output will show the order:

```text
C → B → A → object
```

---

# 41. Polymorphism

Polymorphism means:

```text
"One interface, different behavior"
```

Example:

```python
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


animals = [Dog(), Cat()]

for animal in animals:
    animal.sound()
```

Output:

```text
Bark
Meow
```

The same method call:

```python
animal.sound()
```

produces different behavior.

---

# 42. Duck Typing

Python often uses **duck typing**.

The idea is:

> If an object behaves like the required type, it can often be used.

Example:

```python
class Dog:

    def speak(self):
        print("Bark")


class Person:

    def speak(self):
        print("Hello")


def make_speak(obj):
    obj.speak()


make_speak(Dog())
make_speak(Person())
```

Output:

```text
Bark
Hello
```

The function does not require a specific class.

---

# 43. Abstraction

**Abstraction** means exposing essential functionality while hiding implementation details.

Python provides the `abc` module for formal abstract base classes.

```python
from abc import ABC, abstractmethod
```

---

# 44. Abstract Class

Example:

```python
from abc import ABC, abstractmethod


class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass
```

`Animal` is an abstract class.

---

# 45. Implementing an Abstract Class

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

# 46. Abstract Methods

An abstract method specifies that subclasses must provide an implementation.

Example:

```python
@abstractmethod
def area(self):
    pass
```

---

# 47. Why Abstraction?

Abstraction helps:

* Define common interfaces
* Enforce required methods
* Hide implementation details
* Design large systems cleanly

---

# 48. Operator Overloading

Python allows classes to define how operators work with their objects.

Example:

```python
class Number:

    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return Number(self.value + other.value)
```

Usage:

```python
a = Number(10)
b = Number(20)

c = a + b

print(c.value)
```

Output:

```text
30
```

---

# 49. Common Magic Methods

Magic methods have names surrounded by double underscores.

Examples:

```text
__init__
__str__
__repr__
__len__
__add__
__eq__
__lt__
```

---

# 50. `__str__()`

Used to provide a readable string representation.

Example:

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def __str__(self):
        return f"{self.name} - {self.marks}"


student = Student("Yashu", 85)

print(student)
```

Output:

```text
Yashu - 85
```

---

# 51. `__repr__()`

`__repr__()` is intended to provide a useful representation of an object, especially for debugging.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def __repr__(self):
        return f"Student(name={self.name!r})"
```

---

# 52. `__len__()`

You can define what `len()` means for your object.

```python
class Team:

    def __init__(self, members):
        self.members = members

    def __len__(self):
        return len(self.members)


team = Team(["A", "B", "C"])

print(len(team))
```

Output:

```text
3
```

---

# 53. `__eq__()`

Defines equality behavior.

```python
class Student:

    def __init__(self, roll_no):
        self.roll_no = roll_no

    def __eq__(self, other):
        return self.roll_no == other.roll_no
```

Usage:

```python
student1 = Student(101)
student2 = Student(101)

print(student1 == student2)
```

Output:

```text
True
```

For production code, consider type-checking `other` before accessing its attributes.

---

# 54. Composition

Composition means building a class using objects of other classes.

Example:

```python
class Engine:

    def start(self):
        print("Engine started")


class Car:

    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()
        print("Car started")


car = Car()

car.start()
```

Output:

```text
Engine started
Car started
```

---

# 55. Inheritance vs Composition

### Inheritance

Represents an:

```text
"is-a"
```

relationship.

Example:

```text
Dog is an Animal
```

### Composition

Represents a:

```text
"has-a"
```

relationship.

Example:

```text
Car has an Engine
```

---

# 56. Why Composition Is Often Preferred

Composition can make systems:

* More flexible
* Easier to change
* Less tightly coupled

Use inheritance when there is a strong and meaningful parent-child relationship.

---

# 57. Dataclasses

Python provides `dataclasses` for classes mainly used to store data.

Example:

```python
from dataclasses import dataclass


@dataclass
class Student:
    name: str
    age: int
    marks: float


student = Student("Yashu", 20, 85)

print(student)
```

Output:

```text
Student(name='Yashu', age=20, marks=85)
```

---

# 58. Type Hints with Classes

You can add type hints:

```python
class Student:

    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age
```

Type hints improve readability and tooling but are not, by themselves, runtime validation.

---

# 59. Complete Student Class

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name, age, marks):
        self.name = name
        self.age = age
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)
        print("Marks:", self.marks)

    def is_passed(self):
        return self.marks >= 40


student = Student("Yashu", 20, 85)

student.display()

print("Passed:", student.is_passed())
```

Output:

```text
Name: Yashu
Age: 20
Marks: 85
Passed: True
```

---

# 60. Complete Bank Account Example

```python
class BankAccount:

    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):

        if amount <= 0:
            raise ValueError("Deposit must be positive")

        self.balance += amount

    def withdraw(self, amount):

        if amount <= 0:
            raise ValueError("Withdrawal must be positive")

        if amount > self.balance:
            raise ValueError("Insufficient balance")

        self.balance -= amount

    def display_balance(self):
        print("Owner:", self.owner)
        print("Balance:", self.balance)


account = BankAccount("Yashu", 5000)

account.deposit(1000)
account.withdraw(2000)

account.display_balance()
```

Output:

```text
Owner: Yashu
Balance: 4000
```

---

# 61. OOP Mini Project – Student Management

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
            return "Pass"

        return "Fail"


students = [
    Student("Yashu", 101, 85),
    Student("Rahul", 102, 72),
    Student("Arun", 103, 35)
]

for student in students:
    student.display()
    print("Result:", student.result())
    print()
```

---

# 62. OOP Mini Project – Library

```python
class Book:

    def __init__(self, title, author):
        self.title = title
        self.author = author
        self.available = True

    def borrow(self):

        if not self.available:
            print("Book is already borrowed")
            return

        self.available = False
        print("Book borrowed")

    def return_book(self):

        self.available = True
        print("Book returned")


book = Book("Python Basics", "John")

book.borrow()
book.borrow()
book.return_book()
```

---

# 63. OOP Mini Project – Employee

```python
class Employee:

    company = "Tech Company"

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):
        print("Name:", self.name)
        print("Salary:", self.salary)

    def yearly_salary(self):
        return self.salary * 12


employee = Employee("Yashu", 30000)

employee.display()

print("Yearly Salary:", employee.yearly_salary())
```

---

# 64. OOP Mini Project – Vehicle

```python
class Vehicle:

    def start(self):
        print("Vehicle started")


class Car(Vehicle):

    def start(self):
        print("Car started")


class Bike(Vehicle):

    def start(self):
        print("Bike started")


vehicles = [
    Car(),
    Bike()
]

for vehicle in vehicles:
    vehicle.start()
```

This demonstrates polymorphism.

---

# 65. Practice Questions

## Beginner

### Question 1

Create a `Student` class with:

```text
name
age
marks
```

and a method:

```text
display()
```

---

### Question 2

Create a `Car` class with:

```text
brand
model
price
```

and display the details.

---

### Question 3

Create a `Rectangle` class with:

```text
length
width
```

Methods:

```text
area()
perimeter()
```

---

### Question 4

Create a `BankAccount` class with:

```text
deposit()
withdraw()
balance()
```

---

### Question 5

Create an `Employee` class with:

```text
name
salary
```

and calculate yearly salary.

---

# 66. Intermediate Practice

### Question 6

Create:

```text
Animal
Dog
Cat
```

Use inheritance and method overriding.

---

### Question 7

Create:

```text
Vehicle
Car
Bike
```

and demonstrate polymorphism.

---

### Question 8

Create a `Student` class using:

```text
private-like attribute
getter
setter
```

Validate marks between 0 and 100.

---

### Question 9

Create a class:

```text
Circle
```

with:

```text
radius
area()
circumference()
```

Use `math.pi`.

---

### Question 10

Create an abstract class:

```text
Shape
```

with an abstract method:

```text
area()
```

Implement:

```text
Circle
Rectangle
```

---

# 67. Advanced Practice

### Question 11

Create a banking system using:

```text
Account
SavingsAccount
CurrentAccount
```

Use inheritance and method overriding.

---

### Question 12

Create a library management system:

```text
Book
Member
Library
```

Use composition.

---

### Question 13

Create an employee management system:

```text
Employee
Manager
Developer
Intern
```

Demonstrate polymorphism.

---

### Question 14

Create a shopping cart using:

```text
Product
Cart
Customer
```

Use composition.

---

### Question 15

Create a complete student management system using:

```text
Student
Course
Teacher
Department
```

Use classes, composition, inheritance, and appropriate methods.

---

# 68. Important Interview Questions

### Q1. What is OOP?

OOP is a programming paradigm that organizes programs around objects containing data and behavior.

---

### Q2. What is a class?

A class is a blueprint used to create objects.

---

### Q3. What is an object?

An object is an instance of a class.

---

### Q4. What is `self`?

`self` refers to the current instance inside an instance method.

---

### Q5. What is `__init__()`?

It is an initializer method commonly used to initialize an object's attributes.

---

### Q6. What are the four pillars of OOP?

```text
Encapsulation
Inheritance
Polymorphism
Abstraction
```

---

### Q7. What is inheritance?

Inheritance allows a class to reuse and extend functionality from another class.

---

### Q8. What is polymorphism?

Polymorphism allows the same interface or method call to behave differently for different objects.

---

### Q9. What is encapsulation?

Encapsulation combines data and behavior and controls how internal state is accessed or modified.

---

### Q10. What is abstraction?

Abstraction exposes essential behavior while hiding implementation details.

---

### Q11. What is method overriding?

When a child class provides its own implementation of a method inherited from a parent class.

---

### Q12. What is `super()`?

`super()` provides a way to access methods or attributes from a parent class according to Python's method resolution order.

---

### Q13. Difference between class and instance attributes?

```text
Class attribute
→ Associated with the class

Instance attribute
→ Associated with each object
```

---

### Q14. What is a static method?

A method that does not automatically receive `self` or `cls`.

---

### Q15. What is a class method?

A method that receives the class as its first argument, conventionally called `cls`.

---

### Q16. What is composition?

Composition builds objects by containing other objects.

---

### Q17. Inheritance vs composition?

```text
Inheritance → is-a
Composition  → has-a
```

---

# 69. OOP Cheat Sheet

```text
class
    ↓
Blueprint

object
    ↓
Instance of class

self
    ↓
Current instance

__init__
    ↓
Initialize instance

method
    ↓
Function inside class

attribute
    ↓
Data associated with class/object

inheritance
    ↓
Reuse/extend another class

polymorphism
    ↓
Same interface, different behavior

encapsulation
    ↓
Control and organize internal state

abstraction
    ↓
Hide implementation details

super()
    ↓
Access parent-class behavior

@classmethod
    ↓
Method receives cls

@staticmethod
    ↓
No automatic self/cls

@property
    ↓
Managed attribute access
```

---

# 70. OOP Structure

A typical class:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print(self.name)
        print(self.marks)
```

Create object:

```python
student = Student("Yashu", 85)

student.display()
```

---

# 71. Real-World OOP Examples

### Banking

```text
Bank
Account
Customer
Transaction
```

### E-commerce

```text
Product
Customer
Cart
Order
Payment
```

### College Management

```text
Student
Teacher
Course
Department
Exam
```

### Hospital

```text
Patient
Doctor
Appointment
Prescription
```

### Food Delivery

```text
Customer
Restaurant
Menu
Order
Delivery
```

---

# 72. OOP Design Tip

Don't create classes just because you can.

Use a class when it helps model:

* State
* Behavior
* A meaningful entity
* A reusable abstraction

For simple one-off operations, a normal function may be better.

---

# 73. Important OOP Example

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def is_passed(self):
        return self.marks >= 40

    def display(self):
        print(f"Name: {self.name}")
        print(f"Marks: {self.marks}")
        print(f"College: {self.college}")


students = [
    Student("Yashu", 85),
    Student("Rahul", 72),
    Student("Arun", 35)
]

for student in students:
    student.display()
    print("Result:", "Pass" if student.is_passed() else "Fail")
    print()
```

---

# 🎯 Notes 17 Summary

In this lesson, you learned:

* Object-Oriented Programming
* Classes
* Objects
* Attributes
* Methods
* `self`
* `__init__()`
* Instance attributes
* Class attributes
* Instance methods
* Class methods
* Static methods
* Encapsulation
* `_` convention
* Name mangling with `__`
* Getters
* Setters
* `@property`
* Inheritance
* Parent and child classes
* Method overriding
* `super()`
* Single inheritance
* Multilevel inheritance
* Multiple inheritance
* Hierarchical inheritance
* Hybrid inheritance
* Method Resolution Order
* Polymorphism
* Duck typing
* Abstraction
* Abstract classes
* Abstract methods
* Operator overloading
* Magic methods
* `__str__()`
* `__repr__()`
* `__len__()`
* `__eq__()`
* Composition
* Inheritance vs composition
* Dataclasses
* Type hints
* OOP mini projects
* Practice questions
* Interview questions

---

# ⭐ Most Important Concepts

Remember:

```text
Class
 ↓
Blueprint

Object
 ↓
Instance

Encapsulation
 ↓
Protect/control internal state

Inheritance
 ↓
Reuse and extend classes

Polymorphism
 ↓
Same interface, different behavior

Abstraction
 ↓
Hide implementation details

Composition
 ↓
Build objects using other objects
```

The basic pattern is:

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print(self.name)
        print(self.marks)


student = Student("Yashu", 85)

student.display()
```

---

# 🚀 Next Lesson

**Notes 18 → Python Iterators, Iterables & Generators**
