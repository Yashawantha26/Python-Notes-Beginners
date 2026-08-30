# 🚀 Python OOP Interview Questions & Answers

## Company-Wise + Year-Wise Interview Preparation

---

# 📌 Important Note

This file is designed for **Python fresher/software developer interviews**.

It contains:

* Python OOP fundamentals
* Interview-ready answers
* Coding questions
* Output-based questions
* Company-wise preparation
* Year-wise preparation
* Frequently repeated concepts
* Tricky questions
* HR + technical follow-ups
* Solutions
* Mini interview tests

Company/year questions are organized as **preparation patterns**, because actual interview questions vary by role, location, interviewer, and candidate.

---

# 1. What is OOP?

### Interview Answer

OOP stands for **Object-Oriented Programming**.

It is a programming paradigm where programs are organized around **objects and classes**.

The main principles are:

```text
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
```

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def study(self):
        print(self.name, "is studying")


student = Student("Yashu")

student.study()
```

Output:

```text
Yashu is studying
```

---

# 2. What is a Class?

### Answer

A class is a **blueprint/template** used to create objects.

Example:

```python
class Student:

    def study(self):
        print("Student is studying")
```

Here:

```text
Student → class
study() → method
```

---

# 3. What is an Object?

### Answer

An object is an **instance of a class**.

Example:

```python
class Student:
    pass


student1 = Student()
student2 = Student()
```

Here:

```text
Student → class
student1 → object
student2 → object
```

---

# 4. Class vs Object

| Class                                    | Object                           |
| ---------------------------------------- | -------------------------------- |
| Blueprint                                | Instance                         |
| Defines structure                        | Represents actual entity         |
| Does not represent one specific instance | Represents one specific instance |
| `Student`                                | `student1`                       |

Example:

```python
class Student:
    pass


student = Student()
```

---

# 5. What is `__init__()`?

`__init__()` is a special method that is automatically called when an object is initialized.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name


student = Student("Yashu")

print(student.name)
```

Output:

```text
Yashu
```

---

# 6. What is `self`?

`self` refers to the **current object/instance**.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def show(self):
        print(self.name)
```

When:

```python
student = Student("Yashu")
student.show()
```

`self` refers to `student`.

---

# 7. Is `self` a keyword?

No.

`self` is a conventional parameter name used for the current instance.

Technically, another valid name can be used, but `self` is the standard and recommended convention.

---

# 8. What is an Instance Variable?

An instance variable belongs to a particular object.

Example:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age
```

Here:

```text
self.name
self.age
```

are instance variables.

Each object can have different values.

---

# 9. What is a Class Variable?

A class variable is shared by instances of the class unless an instance shadows it.

Example:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name
```

`college` is a class variable.

---

# 10. Class Variable vs Instance Variable

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name
```

Here:

```text
college → class variable
name → instance variable
```

---

# 11. What is a Method?

A method is a function defined inside a class.

Example:

```python
class Student:

    def study(self):
        print("Studying")
```

`study()` is a method.

---

# 12. Types of Methods

Python commonly uses:

```text
1. Instance method
2. Class method
3. Static method
```

---

# 13. Instance Method

An instance method receives the object as its first parameter.

```python
class Student:

    def show(self):
        print("Student")


student = Student()

student.show()
```

---

# 14. Class Method

A class method receives the class as its first parameter, conventionally named `cls`.

Use:

```python
@classmethod
```

Example:

```python
class Student:

    college = "RIT Hassan"

    @classmethod
    def show_college(cls):
        print(cls.college)


Student.show_college()
```

---

# 15. Static Method

A static method does not automatically receive `self` or `cls`.

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

# 16. Instance vs Class vs Static Method

| Method   | First parameter    | Decorator       |
| -------- | ------------------ | --------------- |
| Instance | `self`             | None            |
| Class    | `cls`              | `@classmethod`  |
| Static   | None automatically | `@staticmethod` |

---

# 17. What is Encapsulation?

Encapsulation means combining data and methods into a class and controlling access to internal implementation details.

Example:

```python
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance

    def get_balance(self):
        return self.__balance
```

---

# 18. Public Variable

```python
class Student:

    def __init__(self):
        self.name = "Yashu"
```

`name` is public.

It can normally be accessed directly:

```python
student.name
```

---

# 19. Protected Convention

Python uses a single underscore as a convention indicating an internal/protected-style attribute:

```python
class Student:

    def __init__(self):
        self._marks = 90
```

Python does not enforce Java-style protected access restrictions.

---

# 20. Private Variable

Python supports name mangling for names beginning with two underscores.

```python
class Student:

    def __init__(self):
        self.__marks = 90
```

Direct access:

```python
student.__marks
```

will normally fail because the name is mangled.

---

# 21. What is Name Mangling?

Python transforms a double-underscore attribute name internally.

Example:

```python
class Student:

    def __init__(self):
        self.__marks = 90
```

It is approximately stored as:

```text
_student__marks
```

This is intended to reduce accidental name collisions, not to provide absolute security.

---

# 22. What is Inheritance?

Inheritance allows a child class to reuse or extend behavior from a parent class.

Example:

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

# 23. Types of Inheritance

Python supports:

```text
1. Single inheritance
2. Multiple inheritance
3. Multilevel inheritance
4. Hierarchical inheritance
5. Hybrid inheritance
```

---

# 24. Single Inheritance

```python
class Animal:
    pass


class Dog(Animal):
    pass
```

One child inherits from one parent.

---

# 25. Multilevel Inheritance

```python
class Grandparent:
    pass


class Parent(Grandparent):
    pass


class Child(Parent):
    pass
```

Hierarchy:

```text
Grandparent
     ↓
   Parent
     ↓
   Child
```

---

# 26. Multiple Inheritance

One class inherits from multiple parent classes.

```python
class Father:

    def skills(self):
        print("Programming")


class Mother:

    def hobbies(self):
        print("Music")


class Child(Father, Mother):
    pass


child = Child()

child.skills()
child.hobbies()
```

---

# 27. Hierarchical Inheritance

Multiple child classes inherit from one parent.

```python
class Animal:
    pass


class Dog(Animal):
    pass


class Cat(Animal):
    pass
```

---

# 28. What is Polymorphism?

Polymorphism means **one interface/name can have different behavior depending on the object**.

Example:

```python
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


for animal in [Dog(), Cat()]:
    animal.sound()
```

Output:

```text
Bark
Meow
```

---

# 29. What is Method Overriding?

A child class provides its own implementation of a method inherited from the parent.

```python
class Animal:

    def sound(self):
        print("Animal sound")


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

# 30. What is `super()`?

`super()` is used to access functionality from a parent class according to Python's method resolution order.

Example:

```python
class Animal:

    def __init__(self, name):
        self.name = name


class Dog(Animal):

    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed
```

---

# 31. What is Abstraction?

Abstraction means exposing essential behavior while hiding implementation details.

Python commonly implements formal abstraction using the `abc` module.

Example:

```python
from abc import ABC, abstractmethod


class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass
```

---

# 32. Abstract Class

An abstract class is a class intended to provide a common interface and may contain abstract methods that subclasses must implement.

Example:

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass
```

---

# 33. Implementing an Abstract Class

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass


class Circle(Shape):

    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2


circle = Circle(5)

print(circle.area())
```

---

# 34. Encapsulation vs Abstraction

| Encapsulation                     | Abstraction                     |
| --------------------------------- | ------------------------------- |
| Bundles data and behavior         | Hides implementation complexity |
| Controls access                   | Exposes essential interface     |
| Focuses on data protection/design | Focuses on what the object does |
| Example: private attribute        | Example: abstract method        |

---

# 35. Inheritance vs Composition

Inheritance represents an **is-a** relationship.

```text
Dog is an Animal
```

Composition represents a **has-a** relationship.

```text
Car has an Engine
```

Composition is often preferred when inheritance does not represent a natural subtype relationship.

---

# 36. Composition Example

```python
class Engine:

    def start(self):
        print("Engine started")


class Car:

    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()


car = Car()

car.start()
```

---

# 37. What is Duck Typing?

Python often focuses on what an object can do rather than its exact class.

Example:

```python
class Dog:

    def speak(self):
        print("Bark")


class Cat:

    def speak(self):
        print("Meow")


def make_sound(animal):
    animal.speak()


make_sound(Dog())
make_sound(Cat())
```

The function only requires that the object provide `speak()`.

---

# 38. What is MRO?

MRO means **Method Resolution Order**.

It determines the order in which Python searches classes for attributes and methods.

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

Conceptually:

```text
C → B → A → object
```

---

# 39. `__mro__`

You can also inspect:

```python
print(C.__mro__)
```

---

# 40. MRO with Multiple Inheritance

```python
class A:

    def show(self):
        print("A")


class B(A):

    def show(self):
        print("B")


class C(A):

    def show(self):
        print("C")


class D(B, C):
    pass


d = D()

d.show()
```

Output:

```text
B
```

Python follows the MRO.

---

# 41. What is C3 Linearization?

Python uses **C3 linearization** to determine MRO in multiple inheritance.

It provides a consistent ordering while respecting inheritance relationships.

Interviewers may ask this for advanced Python roles.

---

# 42. What are Magic/Dunder Methods?

Special methods with names surrounded by double underscores are commonly called dunder methods.

Examples:

```text
__init__
__str__
__repr__
__len__
__eq__
__add__
__getitem__
```

---

# 43. `__str__`

`__str__` provides a user-friendly string representation.

```python
class Student:

    def __init__(self, name):
        self.name = name

    def __str__(self):
        return self.name


student = Student("Yashu")

print(student)
```

Output:

```text
Yashu
```

---

# 44. `__repr__`

`__repr__` is intended to provide a useful developer-oriented representation.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def __repr__(self):
        return f"Student({self.name!r})"
```

---

# 45. `__len__`

You can define how `len()` behaves for your object.

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

# 46. Operator Overloading

Python lets classes define behavior for operators through special methods.

Example:

```python
class Number:

    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return Number(self.value + other.value)


a = Number(10)
b = Number(20)

result = a + b

print(result.value)
```

Output:

```text
30
```

---

# 47. What is `__eq__`?

`__eq__` controls equality comparison.

```python
class Student:

    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name
```

---

# 48. `__new__()` vs `__init__()`

### `__new__()`

Responsible for creating/returning a new instance.

### `__init__()`

Initializes an already-created instance.

For beginner interviews, remember:

```text
__new__ → creates/returns instance
__init__ → initializes instance
```

---

# 49. What is `@property`?

`@property` allows a method to be accessed like an attribute.

Example:

```python
class Student:

    def __init__(self, marks):
        self._marks = marks

    @property
    def marks(self):
        return self._marks


student = Student(90)

print(student.marks)
```

---

# 50. Property Setter

```python
class Student:

    def __init__(self, marks):
        self._marks = marks

    @property
    def marks(self):
        return self._marks

    @marks.setter
    def marks(self, value):

        if not 0 <= value <= 100:
            raise ValueError("Marks must be 0 to 100.")

        self._marks = value
```

---

# 🏢 COMPANY-WISE INTERVIEW PREPARATION

The following sections are **company-targeted preparation sets**, not claims that every listed question was asked exactly in that company's interview.

---

# 51. TCS Python/OOP Interview Questions

## TCS – Fresher Level

### Q1. What is OOP?

**Answer:**

OOP is a programming paradigm based on classes and objects. Its main principles are encapsulation, inheritance, polymorphism, and abstraction.

---

### Q2. Difference between class and object?

**Answer:**

A class is a blueprint, while an object is an instance of that class.

---

### Q3. What is inheritance?

**Answer:**

Inheritance allows a child class to reuse and extend functionality from a parent class.

---

### Q4. What is polymorphism?

**Answer:**

Polymorphism allows the same interface or method name to behave differently for different objects.

---

### Q5. What is encapsulation?

**Answer:**

Encapsulation bundles data and behavior together and helps control access to internal implementation.

---

### Q6. What is `self`?

**Answer:**

`self` refers to the current instance.

---

### Q7. What is `__init__()`?

**Answer:**

It initializes an object after it has been created.

---

### Q8. What is the difference between list and tuple?

**Answer:**

```text
List
→ Mutable

Tuple
→ Immutable
```

Example:

```python
numbers = [1, 2, 3]

values = (1, 2, 3)
```

---

### Q9. What is a dictionary?

A dictionary stores key-value pairs.

```python
student = {
    "name": "Yashu",
    "marks": 90
}
```

---

### Q10. Reverse a string.

```python
text = "Python"

print(text[::-1])
```

Output:

```text
nohtyP
```

---

# 52. Infosys Python/OOP Interview Questions

## Fresher Preparation

### Q1. What is inheritance?

```python
class Animal:
    pass


class Dog(Animal):
    pass
```

`Dog` inherits from `Animal`.

---

### Q2. What is method overriding?

A child class provides a different implementation of a parent method.

```python
class A:

    def show(self):
        print("A")


class B(A):

    def show(self):
        print("B")
```

---

### Q3. What is multiple inheritance?

```python
class A:
    pass


class B:
    pass


class C(A, B):
    pass
```

---

### Q4. What is abstraction?

Abstraction hides unnecessary implementation details and exposes an essential interface.

---

### Q5. What is the difference between `@staticmethod` and `@classmethod`?

```text
staticmethod
→ no automatic self/cls

classmethod
→ receives cls
```

---

### Q6. Find duplicate elements.

```python
numbers = [1, 2, 2, 3, 4, 4]

duplicates = []

for number in numbers:

    if numbers.count(number) > 1 and number not in duplicates:
        duplicates.append(number)

print(duplicates)
```

Output:

```text
[2, 4]
```

---

# 53. Wipro Python/OOP Interview Questions

### Q1. Explain the four pillars.

```text
Encapsulation
Inheritance
Polymorphism
Abstraction
```

---

### Q2. What is method overloading?

Method overloading means using the same method name for different parameter combinations.

Python does not provide traditional compile-time method overloading like Java.

A common Python approach is default arguments or `*args`.

Example:

```python
class Calculator:

    def add(self, a, b=0, c=0):
        return a + b + c


calculator = Calculator()

print(calculator.add(10))
print(calculator.add(10, 20))
print(calculator.add(10, 20, 30))
```

---

### Q3. What is method overriding?

```python
class Parent:

    def show(self):
        print("Parent")


class Child(Parent):

    def show(self):
        print("Child")
```

---

### Q4. What is constructor?

In Python, `__init__()` is commonly called the initializer and is used to initialize instance state.

---

### Q5. Write factorial.

```python
def factorial(n):

    result = 1

    for i in range(1, n + 1):
        result *= i

    return result


print(factorial(5))
```

Output:

```text
120
```

---

# 54. Accenture Python Interview Preparation

### Q1. Explain class and object.

```python
class Car:

    def drive(self):
        print("Driving")


car = Car()

car.drive()
```

---

### Q2. What is constructor?

```python
class Student:

    def __init__(self, name):
        self.name = name
```

---

### Q3. What is inheritance?

```python
class Vehicle:
    pass


class Car(Vehicle):
    pass
```

---

### Q4. What is polymorphism?

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

---

### Q5. What is exception handling?

It is the process of handling runtime exceptions using:

```text
try
except
else
finally
```

---

### Q6. Find the largest number.

```python
numbers = [10, 50, 20, 40]

largest = numbers[0]

for number in numbers:

    if number > largest:
        largest = number

print(largest)
```

Output:

```text
50
```

---

# 55. Cognizant Python Interview Preparation

### Q1. What is `self`?

`self` refers to the current instance.

---

### Q2. What is `super()`?

It provides access to methods/attributes through the parent-class hierarchy according to MRO.

---

### Q3. What is MRO?

MRO is the order Python uses to search classes for attributes and methods.

---

### Q4. What is duck typing?

Python often determines whether an object can be used based on the operations/methods it supports rather than requiring a specific class.

---

### Q5. What is the difference between `is` and `==`?

```text
== 
→ compares values/equality

is
→ checks object identity
```

Example:

```python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

---

# 56. Capgemini Python Interview Preparation

### Q1. What is abstraction?

Abstraction hides implementation details and exposes essential functionality.

---

### Q2. What is encapsulation?

Encapsulation bundles data and related methods together and helps manage access to internal state.

---

### Q3. What is inheritance?

Inheritance enables reuse and extension of parent-class behavior.

---

### Q4. What is polymorphism?

Different object types can respond to the same operation in their own way.

---

### Q5. What is a static method?

A method that does not receive an instance or class automatically.

```python
class Math:

    @staticmethod
    def square(n):
        return n * n
```

---

### Q6. Check palindrome.

```python
text = input("Enter text: ")

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not palindrome")
```

---

# 57. HCLTech Python Interview Preparation

### Q1. What is a class variable?

A variable defined on the class and shared through the class/instances unless shadowed.

---

### Q2. What is an instance variable?

A variable associated with a particular object.

---

### Q3. Explain `__str__`.

It provides a user-friendly string representation.

---

### Q4. Explain `__repr__`.

It provides a representation intended to be useful for developers/debugging.

---

### Q5. What is exception handling?

Handling runtime exceptions without unnecessarily terminating the application.

---

# 58. IBM Python Interview Preparation

### Q1. What is OOP?

Object-oriented programming organizes data and behavior using objects/classes.

---

### Q2. What are the four pillars?

```text
Encapsulation
Abstraction
Inheritance
Polymorphism
```

---

### Q3. What is composition?

Composition is building an object using other objects.

Example:

```python
class Engine:
    pass


class Car:

    def __init__(self):
        self.engine = Engine()
```

---

### Q4. What is aggregation?

Aggregation is a weaker whole-part relationship where the contained object can exist independently of the container.

---

### Q5. What is operator overloading?

Defining special methods so operators work with custom objects.

---

# 59. Deloitte Python Interview Preparation

### Q1. What is the difference between `__new__` and `__init__`?

```text
__new__
→ creates/returns an instance

__init__
→ initializes the instance
```

---

### Q2. What is MRO?

MRO determines the order Python uses to resolve attributes/methods in inheritance.

---

### Q3. What is multiple inheritance?

```python
class A:
    pass


class B:
    pass


class C(A, B):
    pass
```

---

### Q4. What is `super()`?

It delegates to the next implementation in the MRO.

---

### Q5. What is a property?

A property provides attribute-style access backed by methods.

---

# 60. EY Python Interview Preparation

### Q1. What is abstraction?

Hiding unnecessary implementation complexity.

---

### Q2. What is encapsulation?

Bundling state and behavior while controlling access to implementation details.

---

### Q3. What is dependency injection?

Dependency injection means providing an object with the dependencies it needs instead of having it create them internally.

Example:

```python
class Service:

    def __init__(self, database):
        self.database = database
```

---

### Q4. Why is composition useful?

It reduces tight inheritance coupling and allows behavior to be assembled from smaller components.

---

# 61. KPMG Python Interview Preparation

### Q1. Difference between class and object?

```text
Class → blueprint
Object → instance
```

---

### Q2. Difference between `is` and `==`?

```text
is → identity
== → equality
```

---

### Q3. What is encapsulation?

Bundling state and behavior and controlling access to implementation details.

---

### Q4. What is polymorphism?

Same operation/interface can produce different behavior for different objects.

---

# 62. Amazon Python/OOP Preparation

Amazon interviews may go beyond definitions and ask you to reason about design, complexity, data structures, and working code.

### Q1. Explain composition vs inheritance.

Prefer inheritance when there is a genuine subtype relationship.

Use composition when an object is built from other components.

---

### Q2. Explain polymorphism with a practical example.

```python
class Payment:

    def pay(self):
        raise NotImplementedError


class UPI(Payment):

    def pay(self):
        print("Paid using UPI")


class Card(Payment):

    def pay(self):
        print("Paid using card")


payments = [UPI(), Card()]

for payment in payments:
    payment.pay()
```

---

### Q3. Design a simple shopping cart.

```python
class Product:

    def __init__(self, name, price):
        self.name = name
        self.price = price


class Cart:

    def __init__(self):
        self.products = []

    def add(self, product):
        self.products.append(product)

    def total(self):
        return sum(product.price for product in self.products)


cart = Cart()

cart.add(Product("Laptop", 50000))
cart.add(Product("Mouse", 1000))

print(cart.total())
```

Output:

```text
51000
```

---

# 63. Microsoft Python/OOP Preparation

### Q1. Explain abstraction vs encapsulation.

```text
Abstraction
→ hides implementation complexity

Encapsulation
→ bundles and controls access to state/behavior
```

---

### Q2. Explain MRO.

Python uses MRO to determine which class implementation is selected in inheritance.

---

### Q3. What is duck typing?

An object's supported behavior matters more than its declared class for many Python operations.

---

### Q4. What is `__slots__`?

`__slots__` can restrict which instance attributes are stored and may reduce per-instance memory overhead in suitable cases.

Example:

```python
class Student:

    __slots__ = ("name", "marks")

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
```

---

# 64. Google Python Preparation

For higher-level interviews, focus less on memorizing definitions and more on:

```text
Problem solving
Data structures
Algorithms
Complexity
Python internals
Clean code
System design
OOP design
Testing
```

### Example Design Question

Design a notification system.

```python
class Notification:

    def send(self, message):
        raise NotImplementedError


class EmailNotification(Notification):

    def send(self, message):
        print("Email:", message)


class SMSNotification(Notification):

    def send(self, message):
        print("SMS:", message)


def notify(service, message):
    service.send(message)


notify(EmailNotification(), "Hello")
notify(SMSNotification(), "Hello")
```

---

# 📅 YEAR-WISE PREPARATION

---

# 65. 2023 Interview Pattern

Focus on fundamentals:

```text
Class
Object
Inheritance
Polymorphism
Encapsulation
Abstraction
Constructor
self
Exception handling
Basic Python programs
```

### Must Practice

```python
class Student:

    def __init__(self, name):
        self.name = name

    def show(self):
        print(self.name)


student = Student("Yashu")

student.show()
```

---

# 66. 2024 Interview Pattern

More practical questions commonly included:

```text
Class vs object
self
__init__
Inheritance
Method overriding
Exception handling
List/dictionary questions
String programs
Basic OOP coding
```

### Coding

Find frequency of characters:

```python
text = "python"

frequency = {}

for char in text:

    frequency[char] = frequency.get(char, 0) + 1

print(frequency)
```

---

# 67. 2025 Interview Pattern

Prepare beyond basic definitions:

```text
Class vs instance attributes
classmethod
staticmethod
property
Inheritance
super()
Method overriding
Exception handling
Magic methods
Composition
```

### Example

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name

    @classmethod
    def show_college(cls):
        print(cls.college)

    @staticmethod
    def greet():
        print("Hello")
```

---

# 68. 2026 Interview Pattern

Current preparation should include:

```text
OOP fundamentals
Python object model
self
Class vs instance attributes
MRO
super()
Multiple inheritance
Dunder methods
Properties
Duck typing
Composition
Abstraction
Exception handling
Clean code
Problem solving
```

Recent 2026 interview-preparation material specifically highlights `self`, class vs instance attributes, MRO, `super()`, dunder methods, and multiple inheritance as recurring Python OOP topics. ([PapersAdda][1])

---

# 69. Most Repeated Python OOP Questions

Memorize these first:

```text
1. What is OOP?
2. What is a class?
3. What is an object?
4. Class vs object?
5. What is self?
6. What is __init__?
7. What are instance variables?
8. What are class variables?
9. What is inheritance?
10. Types of inheritance?
11. What is polymorphism?
12. What is encapsulation?
13. What is abstraction?
14. What is method overriding?
15. Does Python support method overloading?
16. What is super()?
17. What is MRO?
18. What is multiple inheritance?
19. What is a static method?
20. What is a class method?
21. What is @property?
22. What are dunder methods?
23. __str__ vs __repr__?
24. __new__ vs __init__?
25. What is duck typing?
26. What is composition?
27. Composition vs inheritance?
28. What is operator overloading?
29. What are custom exceptions?
30. What is exception handling?
```

---

# 70. TOP 20 Coding Questions

## Q1. Reverse a string

```python
text = "Python"

print(text[::-1])
```

---

## Q2. Check palindrome

```python
text = input("Enter text: ")

print("Palindrome" if text == text[::-1] else "Not palindrome")
```

---

## Q3. Factorial

```python
def factorial(n):

    result = 1

    for i in range(1, n + 1):
        result *= i

    return result


print(factorial(5))
```

---

## Q4. Fibonacci

```python
n = 7

a = 0
b = 1

for _ in range(n):

    print(a, end=" ")

    a, b = b, a + b
```

Output:

```text
0 1 1 2 3 5 8
```

---

## Q5. Prime number

```python
n = 17

if n < 2:

    print("Not prime")

else:

    is_prime = True

    for i in range(2, int(n ** 0.5) + 1):

        if n % i == 0:
            is_prime = False
            break

    print("Prime" if is_prime else "Not prime")
```

---

## Q6. Find largest number

```python
numbers = [10, 50, 20, 40]

print(max(numbers))
```

---

## Q7. Remove duplicates

```python
numbers = [1, 2, 2, 3, 3, 4]

unique = list(dict.fromkeys(numbers))

print(unique)
```

Output:

```text
[1, 2, 3, 4]
```

---

## Q8. Count vowels

```python
text = "python programming"

count = 0

for char in text.lower():

    if char in "aeiou":
        count += 1

print(count)
```

---

## Q9. Character frequency

```python
text = "hello"

frequency = {}

for char in text:

    frequency[char] = frequency.get(char, 0) + 1

print(frequency)
```

---

## Q10. Sum of list

```python
numbers = [10, 20, 30]

print(sum(numbers))
```

---

## Q11. Second largest

```python
numbers = [10, 20, 50, 30, 40]

unique = sorted(set(numbers))

print(unique[-2])
```

---

## Q12. Swap variables

```python
a = 10
b = 20

a, b = b, a

print(a, b)
```

---

## Q13. Even or odd

```python
number = 10

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

## Q14. Sum digits

```python
number = 12345

total = 0

for digit in str(number):
    total += int(digit)

print(total)
```

Output:

```text
15
```

---

## Q15. Count words

```python
sentence = "Python is easy to learn"

words = sentence.split()

print(len(words))
```

---

## Q16. Anagram

```python
a = "listen"
b = "silent"

if sorted(a) == sorted(b):
    print("Anagram")
else:
    print("Not anagram")
```

---

## Q17. Armstrong number

```python
number = 153

digits = str(number)

total = sum(int(digit) ** len(digits) for digit in digits)

if total == number:
    print("Armstrong")
else:
    print("Not Armstrong")
```

---

## Q18. Find missing number

```python
numbers = [1, 2, 3, 5]

n = 5

missing = n * (n + 1) // 2 - sum(numbers)

print(missing)
```

Output:

```text
4
```

---

## Q19. Find duplicates

```python
numbers = [1, 2, 3, 2, 4, 3]

seen = set()
duplicates = set()

for number in numbers:

    if number in seen:
        duplicates.add(number)

    seen.add(number)

print(duplicates)
```

---

## Q20. Sort without `sort()`

```python
numbers = [5, 2, 8, 1, 3]

for i in range(len(numbers)):

    for j in range(i + 1, len(numbers)):

        if numbers[i] > numbers[j]:
            numbers[i], numbers[j] = numbers[j], numbers[i]

print(numbers)
```

---

# 🧠 OUTPUT-BASED QUESTIONS

---

# 71. Output Question 1

```python
class A:

    def show(self):
        print("A")


class B(A):

    def show(self):
        print("B")


obj = B()

obj.show()
```

### Answer

```text
B
```

Reason:

The child method overrides the parent method.

---

# 72. Output Question 2

```python
class Student:

    college = "RIT"

student1 = Student()
student2 = Student()

print(student1.college)
print(student2.college)
```

### Output

```text
RIT
RIT
```

---

# 73. Output Question 3

```python
class Student:

    def __init__(self, name):
        self.name = name


a = Student("A")
b = Student("B")

print(a.name)
print(b.name)
```

### Output

```text
A
B
```

---

# 74. Output Question 4

```python
class A:

    x = 10


a = A()

a.x = 20

print(A.x)
print(a.x)
```

### Output

```text
10
20
```

Why?

`a.x = 20` creates/updates an instance attribute and does not change the class attribute.

---

# 75. Output Question 5

```python
class A:

    def show(self):
        print("A")


class B(A):

    pass


B().show()
```

### Output

```text
A
```

Because `B` inherits `show()` from `A`.

---

# 76. Output Question 6

```python
class A:

    def __init__(self):
        print("A")


class B(A):

    def __init__(self):
        print("B")


B()
```

### Output

```text
B
```

The child initializer overrides the parent's initializer.

---

# 77. Output Question 7

```python
class A:

    def show(self):
        print("A")


class B(A):

    def show(self):
        super().show()
        print("B")


B().show()
```

### Output

```text
A
B
```

---

# 78. OUTPUT QUESTION 8

```python
class A:

    def show(self):
        print("A")


class B(A):

    def show(self):
        print("B")


class C(B):

    pass


C().show()
```

### Answer

```text
B
```

Because Python finds `show()` in `B` first.

---

# 79. OUTPUT QUESTION 9

```python
class Counter:

    count = 0

    def __init__(self):
        Counter.count += 1


Counter()
Counter()
Counter()

print(Counter.count)
```

### Output

```text
3
```

---

# 80. OUTPUT QUESTION 10

```python
class A:

    def __init__(self):
        self.x = 10


a = A()

print(a.x)
```

### Output

```text
10
```

---

# 🎯 TRICKY INTERVIEW QUESTIONS

---

# 81. Is Python Purely Object-Oriented?

### Answer

Python is strongly object-oriented and treats many things, including functions, classes, and numbers, as objects. However, it is multi-paradigm rather than requiring every program to be written purely in OOP style.

---

# 82. Can a class inherit from multiple classes?

Yes.

```python
class A:
    pass


class B:
    pass


class C(A, B):
    pass
```

---

# 83. Does Python support method overloading?

Python does not support traditional compile-time method overloading based solely on parameter signatures.

You can achieve similar behavior using:

```text
Default arguments
*args
**kwargs
```

Example:

```python
class Calculator:

    def add(self, *numbers):
        return sum(numbers)
```

---

# 84. Does Python support method overriding?

Yes.

```python
class Parent:

    def show(self):
        print("Parent")


class Child(Parent):

    def show(self):
        print("Child")
```

---

# 85. Can Python have private variables?

Python uses name mangling for double-underscore attributes.

```python
self.__balance
```

This is not the same as strict private access enforcement in some other languages.

---

# 86. Can an object change its class?

Python permits advanced runtime manipulation of `__class__` in certain compatible cases, but this is not normal beginner-level practice and should not be used casually.

---

# 87. What is the difference between `type()` and `isinstance()`?

```python
class Animal:
    pass


class Dog(Animal):
    pass


dog = Dog()

print(type(dog) is Dog)
print(isinstance(dog, Dog))
print(isinstance(dog, Animal))
```

Output:

```text
True
True
True
```

`isinstance()` also considers inheritance.

---

# 88. What is `object`?

`object` is the root/base class for Python's ordinary class hierarchy.

Example:

```python
class Student:
    pass
```

A normal new-style Python class ultimately derives from `object`.

---

# 89. What is a metaclass?

A metaclass is the class of a class.

The default metaclass for most classes is:

```python
type
```

Example:

```python
class Student:
    pass


print(type(Student))
```

Output:

```text
<class 'type'>
```

---

# 90. What is `__call__`?

`__call__` allows an instance to be called like a function.

```python
class Greeter:

    def __call__(self, name):
        print("Hello", name)


greet = Greeter()

greet("Yashu")
```

Output:

```text
Hello Yashu
```

---

# 91. What is `__getitem__`?

It controls subscription/indexing behavior.

```python
class Numbers:

    def __init__(self):
        self.values = [10, 20, 30]

    def __getitem__(self, index):
        return self.values[index]


numbers = Numbers()

print(numbers[1])
```

Output:

```text
20
```

---

# 92. What is `__iter__`?

It allows an object to provide an iterator.

Example:

```python
class Numbers:

    def __init__(self, values):
        self.values = values

    def __iter__(self):
        return iter(self.values)


numbers = Numbers([1, 2, 3])

for number in numbers:
    print(number)
```

---

# 93. What is SOLID?

SOLID is a set of object-oriented design principles:

```text
S → Single Responsibility Principle
O → Open/Closed Principle
L → Liskov Substitution Principle
I → Interface Segregation Principle
D → Dependency Inversion Principle
```

These are especially relevant in larger software systems and advanced interviews.

---

# 94. Single Responsibility Principle

A class should have one primary responsibility/reason to change.

Bad design:

```python
class Employee:

    def calculate_salary(self):
        pass

    def save_to_database(self):
        pass

    def generate_report(self):
        pass
```

These responsibilities may be better separated.

---

# 95. Open/Closed Principle

Software entities should generally be open for extension but closed for modification.

Use polymorphism and composition to extend behavior without repeatedly changing stable code.

---

# 96. Liskov Substitution Principle

A subclass should be usable wherever its base class is expected without breaking correctness.

---

# 97. Interface Segregation Principle

Clients should not be forced to depend on methods they do not use.

---

# 98. Dependency Inversion Principle

High-level code should depend on abstractions rather than tightly coupling itself to low-level implementations.

---

# 99. Real Interview Design Question

### Design a Bank Account

```python
class BankAccount:

    def __init__(self, owner, balance=0):
        self.owner = owner
        self._balance = balance

    def deposit(self, amount):

        if amount <= 0:
            raise ValueError("Amount must be positive.")

        self._balance += amount

    def withdraw(self, amount):

        if amount <= 0:
            raise ValueError("Amount must be positive.")

        if amount > self._balance:
            raise ValueError("Insufficient balance.")

        self._balance -= amount

    @property
    def balance(self):
        return self._balance


account = BankAccount("Yashu", 5000)

account.deposit(1000)
account.withdraw(2000)

print(account.balance)
```

Output:

```text
4000
```

Concepts tested:

```text
Class
Object
Constructor
Encapsulation
Property
Validation
Exception
Methods
```

---

# 100. Real Interview Design Question

## Design a Library System

```python
class Book:

    def __init__(self, title, author):
        self.title = title
        self.author = author
        self.is_available = True


class Library:

    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)

    def borrow_book(self, title):

        for book in self.books:

            if book.title == title:

                if not book.is_available:
                    raise ValueError("Book already borrowed.")

                book.is_available = False
                return

        raise ValueError("Book not found.")

    def return_book(self, title):

        for book in self.books:

            if book.title == title:
                book.is_available = True
                return

        raise ValueError("Book not found.")


library = Library()

library.add_book(
    Book("Python Basics", "Author")
)

library.borrow_book("Python Basics")

print("Book borrowed successfully.")
```

---

# 101. Real Interview Design Question

## Design a Simple Employee System

```python
class Employee:

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):
        print(self.name, self.salary)


class Developer(Employee):

    def work(self):
        print(self.name, "writes code")


class Manager(Employee):

    def work(self):
        print(self.name, "manages the team")


employees = [
    Developer("A", 50000),
    Manager("B", 70000)
]

for employee in employees:

    employee.display()
    employee.work()
```

This demonstrates:

```text
Inheritance
Polymorphism
Encapsulation
Objects
Methods
```

---

# 102. Interview Answer Formula

When interviewer asks a technical question, use:

```text
1. Definition
2. Why it is used
3. Small example
4. Real-world example
```

Example:

### Interviewer:

What is inheritance?

### Good Answer:

Inheritance is a mechanism where a child class reuses and extends behavior from a parent class.

It improves code reuse.

For example, `Car` can inherit from `Vehicle`.

```python
class Vehicle:
    def start(self):
        print("Starting")


class Car(Vehicle):
    pass
```

A car can now use `start()`.

---

# 103. 30-Second OOP Answer

If interviewer says:

### "Explain OOP."

Answer:

> OOP stands for Object-Oriented Programming. It organizes software around classes and objects that combine data and behavior. The four major principles are encapsulation, inheritance, polymorphism, and abstraction. OOP helps make software modular, reusable, maintainable, and easier to extend.

---

# 104. 60-Second Python OOP Answer

> Python supports object-oriented programming through classes and objects. A class defines attributes and methods, while an object is an instance of that class. Python supports inheritance, polymorphism, encapsulation, and abstraction. It also provides features such as class methods, static methods, properties, special methods, multiple inheritance, and MRO.

---

# 105. Fresher Rapid-Fire Round

### Q1. Python OOP?

Classes + objects + OOP principles.

### Q2. Class?

Blueprint.

### Q3. Object?

Instance of a class.

### Q4. `self`?

Current instance reference.

### Q5. `__init__`?

Initializes an instance.

### Q6. Inheritance?

Reuse/extend parent behavior.

### Q7. Polymorphism?

Same interface, different behavior.

### Q8. Encapsulation?

Bundle/control state and behavior.

### Q9. Abstraction?

Hide implementation complexity.

### Q10. `super()`?

Delegate to next class in MRO.

### Q11. MRO?

Method Resolution Order.

### Q12. `classmethod`?

Method receiving `cls`.

### Q13. `staticmethod`?

No automatic `self` or `cls`.

### Q14. `__str__`?

User-friendly string representation.

### Q15. `__repr__`?

Developer-oriented representation.

### Q16. `@property`?

Attribute-style access through methods.

### Q17. Multiple inheritance?

One class inherits from multiple classes.

### Q18. Duck typing?

Behavior/capability matters more than exact type.

### Q19. Composition?

Building an object using other objects.

### Q20. Custom exception?

User-defined exception class.

---

# 106. Final Company Preparation Priority

For fresher Python interviews, prepare in this order:

## Level 1 – Must Know

```text
Python basics
Variables
Data types
if/else
loops
functions
strings
lists
tuples
sets
dictionaries
```

## Level 2 – Must Know

```text
OOP
Class
Object
self
__init__
Instance variables
Class variables
Methods
Inheritance
Polymorphism
Encapsulation
Abstraction
```

## Level 3 – Important

```text
classmethod
staticmethod
super()
Method overriding
Properties
Exception handling
File handling
Modules
Packages
```

## Level 4 – Advanced

```text
MRO
Multiple inheritance
Dunder methods
Duck typing
Composition
Descriptors
__new__
Metaclasses
__slots__
SOLID
Design patterns
```

---

# 107. Most Important Questions to Memorize

If you have limited time, prepare these **25 first**:

```text
1. What is OOP?
2. What is class?
3. What is object?
4. Class vs object?
5. What is self?
6. What is __init__?
7. Class variable vs instance variable?
8. What is inheritance?
9. Types of inheritance?
10. What is polymorphism?
11. What is method overriding?
12. Does Python support method overloading?
13. What is encapsulation?
14. What is abstraction?
15. What is super()?
16. What is MRO?
17. What is multiple inheritance?
18. staticmethod vs classmethod?
19. What is @property?
20. __str__ vs __repr__?
21. What are dunder methods?
22. __new__ vs __init__?
23. What is duck typing?
24. Composition vs inheritance?
25. How do you handle exceptions?
```

---

# 108. Final Interview Checklist

Before attending a Python interview, make sure you can explain without notes:

```text
☐ Class
☐ Object
☐ self
☐ __init__
☐ Instance variable
☐ Class variable
☐ Instance method
☐ Class method
☐ Static method
☐ Encapsulation
☐ Inheritance
☐ Polymorphism
☐ Abstraction
☐ Method overriding
☐ Method overloading limitations
☐ super()
☐ Multiple inheritance
☐ MRO
☐ Duck typing
☐ Composition
☐ @property
☐ __str__
☐ __repr__
☐ __new__
☐ __eq__
☐ __len__
☐ __getitem__
☐ Exception handling
☐ Custom exceptions
☐ Basic coding problems
☐ OOP design problems
```

---

# 🎯 Notes 22 Final Summary

## Core OOP

```text
Class
↓
Object
↓
Attributes
↓
Methods
↓
Encapsulation
↓
Inheritance
↓
Polymorphism
↓
Abstraction
```

## Python-Specific OOP

```text
self
__init__
classmethod
staticmethod
super
MRO
property
dunder methods
duck typing
__new__
```

## Interview Coding

```text
Reverse string
Palindrome
Factorial
Fibonacci
Prime
Largest
Second largest
Duplicates
Frequency
Anagram
Armstrong
Missing number
Sorting
```

## Company Preparation

```text
TCS
Infosys
Wipro
Accenture
Cognizant
Capgemini
HCLTech
IBM
Deloitte
EY
KPMG
Amazon
Microsoft
Google
```

## Year Preparation

```text
2023 → OOP fundamentals

2024 → OOP + Python coding

2025 → Python OOP + practical concepts

2026 → OOP + Python internals + MRO +
       dunder methods + design + coding
```

---

# 🚀 Next Notes

## Notes 23 → Python Advanced Interview Questions

Topics:

```text
Python memory management
Garbage collection
Shallow copy
Deep copy
Mutable vs immutable
Iterators
Iterables
Generators
Decorators
Context managers
Closures
Lambda
map()
filter()
reduce()
List comprehension
Dictionary comprehension
Set comprehension
*args
**kwargs
LEGB
Scopes
Namespaces
GIL
Multithreading
Multiprocessing
Async programming
Caching
Python internals
Advanced interview coding
Company-wise questions
Year-wise questions
```

---

# ⭐ Interview Rule

Don't only memorize the definition.

For every concept, prepare:

```text
WHAT is it?
↓
WHY is it used?
↓
HOW does it work?
↓
CODE example
↓
REAL-WORLD example
↓
INTERVIEW follow-up
```

That approach is much stronger than memorizing one-line answers.

[1]: https://papersadda.com/article/python-oops-interview-questions-2026/?utm_source=chatgpt.com "Python OOPs Interview Questions 2026: 30 Q&A With Code | PA"
