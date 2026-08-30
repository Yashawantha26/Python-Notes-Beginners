# Python Beginners Notes – Notes 13

## 📘 Topic: Advanced OOP in Python

In Notes 12, we learned the basics of:

* Classes
* Objects
* Attributes
* Methods
* Constructors
* Inheritance
* Polymorphism
* Encapsulation
* Abstraction

In this lesson, we will learn more useful OOP concepts used in real Python programs.

---

# 1. Instance Methods

An instance method works with a specific object.

It normally uses:

```python
self
```

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def display(self):
        print("Name:", self.name)


student = Student("Yashu")

student.display()
```

Output:

```text
Name: Yashu
```

---

# 2. Class Methods

A **class method** works with the class rather than a particular object.

It uses the:

```python
@classmethod
```

decorator.

The first parameter is usually:

```python
cls
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

# 3. `self` vs `cls`

| `self`                   | `cls`                 |
| ------------------------ | --------------------- |
| Refers to object         | Refers to class       |
| Used in instance methods | Used in class methods |
| Accesses instance data   | Accesses class data   |

Example:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name

    def student_info(self):
        print(self.name)

    @classmethod
    def college_info(cls):
        print(cls.college)
```

---

# 4. Static Methods

A **static method** does not depend on an object or class.

It uses:

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

# 5. Instance vs Class vs Static Methods

| Method   | Decorator       | First Parameter | Used For            |
| -------- | --------------- | --------------- | ------------------- |
| Instance | None            | `self`          | Object data         |
| Class    | `@classmethod`  | `cls`           | Class data          |
| Static   | `@staticmethod` | None            | Independent utility |

---

# 6. Example of All Three Methods

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name

    def display_name(self):
        print("Name:", self.name)

    @classmethod
    def display_college(cls):
        print("College:", cls.college)

    @staticmethod
    def welcome():
        print("Welcome to Python")


student = Student("Yashu")

student.display_name()
Student.display_college()
Student.welcome()
```

Output:

```text
Name: Yashu
College: RIT Hassan
Welcome to Python
```

---

# 7. Encapsulation

Encapsulation means keeping data and methods together and controlling access to data.

Python commonly uses:

```text
_public
_private
__private
```

---

# 8. Public Attributes

Public attributes can normally be accessed directly.

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

# 9. Protected Convention

A single underscore is commonly used to indicate an internal/protected-style attribute.

```python
class Student:

    def __init__(self, name):
        self._name = name
```

This is mainly a convention.

Python does not strictly prevent access.

```python
student = Student("Yashu")

print(student._name)
```

---

# 10. Private Attributes

Double underscore is used for name mangling.

```python
class Student:

    def __init__(self, name):
        self.__name = name
```

Direct access like:

```python
student.__name
```

will not normally work.

---

# 11. Getter

A getter retrieves private data.

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

# 12. Setter

A setter modifies private data.

```python
class Student:

    def __init__(self, name):
        self.__name = name

    def get_name(self):
        return self.__name

    def set_name(self, name):
        self.__name = name


student = Student("Yashu")

student.set_name("Rahul")

print(student.get_name())
```

Output:

```text
Rahul
```

---

# 13. Property Decorator

Python provides `@property` to create controlled attribute access.

Example:

```python
class Student:

    def __init__(self, name):
        self.__name = name

    @property
    def name(self):
        return self.__name


student = Student("Yashu")

print(student.name)
```

Output:

```text
Yashu
```

Notice that we use:

```python
student.name
```

instead of:

```python
student.get_name()
```

---

# 14. Property Setter

We can also use `@name.setter`.

```python
class Student:

    def __init__(self, name):
        self.__name = name

    @property
    def name(self):
        return self.__name

    @name.setter
    def name(self, value):
        self.__name = value


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

# 15. Property with Validation

Properties are useful for validation.

```python
class Student:

    def __init__(self, age):
        self.age = age

    @property
    def age(self):
        return self.__age

    @age.setter
    def age(self, value):
        if value >= 0:
            self.__age = value
        else:
            print("Age cannot be negative")


student = Student(20)

print(student.age)
```

---

# 16. Inheritance

Inheritance allows a class to reuse another class.

```python
class Animal:

    def eat(self):
        print("Animal eats")


class Dog(Animal):

    def bark(self):
        print("Dog barks")


dog = Dog()

dog.eat()
dog.bark()
```

Output:

```text
Animal eats
Dog barks
```

---

# 17. Single Inheritance

One child inherits from one parent.

```text
Animal
   ↓
 Dog
```

Example:

```python
class Animal:
    pass


class Dog(Animal):
    pass
```

---

# 18. Multilevel Inheritance

Inheritance can happen across multiple levels.

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

Output:

```text
Eating
Walking
Barking
```

---

# 19. Multiple Inheritance

A class can inherit from more than one parent class.

```text
Father ──┐
         ├── Child
Mother ──┘
```

Example:

```python
class Father:

    def father_method(self):
        print("Father method")


class Mother:

    def mother_method(self):
        print("Mother method")


class Child(Father, Mother):

    def child_method(self):
        print("Child method")


child = Child()

child.father_method()
child.mother_method()
child.child_method()
```

Output:

```text
Father method
Mother method
Child method
```

---

# 20. Hierarchical Inheritance

One parent can have multiple children.

```text
       Animal
       /    \
     Dog    Cat
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

# 21. Hybrid Inheritance

Hybrid inheritance is a combination of different inheritance types.

Example structure:

```text
        A
       / \
      B   C
       \ /
        D
```

Python can support complex inheritance structures.

---

# 22. Method Overriding

A child class can redefine a parent method.

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

# 23. Using `super()`

`super()` allows the child class to call parent functionality.

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

# 24. `super()` with Constructor

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

# 25. Method Resolution Order (MRO)

MRO determines the order in which Python searches for methods in inheritance.

Use:

```python
ClassName.mro()
```

Example:

```python
class A:
    pass


class B(A):
    pass


print(B.mro())
```

Output will show the order including:

```text
B
A
object
```

---

# 26. `object` Class

In Python, classes ultimately inherit from:

```text
object
```

Example:

```python
class Student:
    pass
```

Conceptually:

```text
Student
   ↓
object
```

You can check:

```python
print(Student.mro())
```

---

# 27. Magic Methods

Magic methods are special methods with double underscores.

Examples:

```text
__init__
__str__
__len__
__add__
__eq__
```

They allow Python objects to work naturally with built-in operations.

---

# 28. `__str__()`

`__str__()` defines a user-friendly string representation of an object.

Example:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"{self.name} - {self.age}"


student = Student("Yashu", 20)

print(student)
```

Output:

```text
Yashu - 20
```

---

# 29. Without `__str__()`

If `__str__()` is not defined:

```python
class Student:

    def __init__(self, name):
        self.name = name


student = Student("Yashu")

print(student)
```

Python normally displays a default object representation.

---

# 30. `__len__()`

The `__len__()` method controls what happens when `len()` is called.

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

# 31. `__eq__()`

`__eq__()` defines how two objects are compared using `==`.

```python
class Student:

    def __init__(self, roll_no):
        self.roll_no = roll_no

    def __eq__(self, other):
        return self.roll_no == other.roll_no


student1 = Student(101)
student2 = Student(101)

print(student1 == student2)
```

Output:

```text
True
```

---

# 32. `__add__()`

`__add__()` can customize the `+` operator.

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

# 33. Operator Overloading

Operator overloading means giving operators special behavior for your objects.

Examples:

```text
+  → __add__()
-  → __sub__()
*  → __mul__()
/  → __truediv__()
== → __eq__()
<  → __lt__()
>  → __gt__()
```

---

# 34. Example of Operator Overloading

```python
class Point:

    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Point(
            self.x + other.x,
            self.y + other.y
        )


p1 = Point(2, 3)
p2 = Point(4, 5)

p3 = p1 + p2

print(p3.x)
print(p3.y)
```

Output:

```text
6
8
```

---

# 35. `__repr__()`

`__repr__()` is mainly intended to provide an unambiguous representation useful for debugging.

Example:

```python
class Student:

    def __init__(self, name):
        self.name = name

    def __repr__(self):
        return f"Student({self.name!r})"


student = Student("Yashu")

print(repr(student))
```

Possible output:

```text
Student('Yashu')
```

---

# 36. `__del__()`

`__del__()` is associated with object finalization.

Example:

```python
class Student:

    def __del__(self):
        print("Object cleanup")


student = Student()

del student
```

Output may include:

```text
Object cleanup
```

### Important

Do not rely on `__del__()` for important resource management. Prefer context managers such as `with`.

---

# 37. Abstract Classes

Abstract classes define a common structure for child classes.

Use:

```python
from abc import ABC, abstractmethod
```

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

---

# 38. Abstract Method

An abstract method is declared using:

```python
@abstractmethod
```

Example:

```python
from abc import ABC, abstractmethod


class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass
```

Child classes should implement the required method.

---

# 39. Duck Typing

Python often focuses on what an object **can do** rather than what type it is.

Example:

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

The function works because both objects have:

```text
sound()
```

---

# 40. Composition

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

Here:

```text
Car HAS-A Engine
```

---

# 41. Inheritance vs Composition

### Inheritance

Represents an:

```text
IS-A
```

relationship.

Example:

```text
Dog IS-A Animal
```

### Composition

Represents a:

```text
HAS-A
```

relationship.

Example:

```text
Car HAS-A Engine
```

---

# 42. Class Attributes

Class attributes belong to the class.

```python
class Student:

    college = "RIT Hassan"
```

Access:

```python
print(Student.college)
```

---

# 43. Changing Class Attributes

```python
class Student:

    college = "RIT Hassan"


print(Student.college)

Student.college = "VTU"

print(Student.college)
```

Output:

```text
RIT Hassan
VTU
```

---

# 44. Instance Attribute Shadowing

An instance can have an attribute with the same name as a class attribute.

```python
class Student:

    college = "RIT Hassan"


student = Student()

student.college = "Another College"

print(student.college)
print(Student.college)
```

Output:

```text
Another College
RIT Hassan
```

The instance attribute shadows the class attribute for that object.

---

# 45. `isinstance()`

`isinstance()` checks whether an object belongs to a class or compatible subclass.

```python
class Student:
    pass


student = Student()

print(isinstance(student, Student))
```

Output:

```text
True
```

---

# 46. `issubclass()`

`issubclass()` checks whether one class inherits from another.

```python
class Animal:
    pass


class Dog(Animal):
    pass


print(issubclass(Dog, Animal))
```

Output:

```text
True
```

---

# 47. Mini Project – Employee Management

```python
class Employee:

    company = "Tech Company"

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):
        print("Name:", self.name)
        print("Salary:", self.salary)
        print("Company:", self.company)

    @classmethod
    def change_company(cls, name):
        cls.company = name

    @staticmethod
    def welcome():
        print("Welcome to the employee system")


employee1 = Employee("Yashu", 30000)

employee1.display()

Employee.change_company("Python Solutions")

employee1.display()

Employee.welcome()
```

---

# 48. Mini Project – Bank Account

```python
class BankAccount:

    bank_name = "Python Bank"

    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance

    @property
    def balance(self):
        return self.__balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
        else:
            print("Invalid withdrawal")

    def display(self):
        print("Owner:", self.owner)
        print("Balance:", self.__balance)


account = BankAccount("Yashu", 5000)

account.deposit(2000)
account.withdraw(1000)

account.display()
```

Output:

```text
Owner: Yashu
Balance: 6000
```

---

# 49. Mini Project – Shape System

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass


class Rectangle(Shape):

    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width


class Circle(Shape):

    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius * self.radius


rectangle = Rectangle(10, 5)
circle = Circle(7)

print("Rectangle area:", rectangle.area())
print("Circle area:", circle.area())
```

---

# 50. Mini Project – Vehicle System

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

Output:

```text
Car started
Bike started
```

This demonstrates **polymorphism**.

---

# 51. Practice Questions

## Beginner

### Question 1

Create a class `Student` with:

```text
name
age
branch
```

Add an instance method to display the details.

---

### Question 2

Create a class method that changes a shared `college` value.

---

### Question 3

Create a static method:

```text
is_even(number)
```

that returns `True` if the number is even.

---

### Question 4

Create a class with a private attribute:

```text
__balance
```

Create getter and setter methods.

---

### Question 5

Use `@property` to control access to a student's age.

---

# 52. Intermediate Practice

### Question 6

Create:

```text
Animal
Dog
Cat
```

Use method overriding to implement different `sound()` methods.

---

### Question 7

Create:

```text
Person
Student
```

Use `super()` to initialize the parent class.

---

### Question 8

Create multiple inheritance using:

```text
Father
Mother
Child
```

---

### Question 9

Create a `Point` class and overload the `+` operator.

---

### Question 10

Create an abstract `Shape` class with:

```text
area()
```

Implement it using:

```text
Circle
Rectangle
```

---

# 53. Advanced Practice

### Question 11

Create a `BankAccount` class with:

* Private balance
* Deposit
* Withdraw
* Property for balance
* Class variable for bank name

---

### Question 12

Create a vehicle system using polymorphism.

Classes:

```text
Vehicle
Car
Bike
Bus
```

Each class should implement:

```text
start()
```

---

### Question 13

Create an `Employee` class with:

* Instance method
* Class method
* Static method
* Private salary
* Property for salary

---

### Question 14

Create a shopping cart using composition.

Structure:

```text
ShoppingCart HAS-A Product list
```

---

### Question 15

Create a complete student management system using OOP.

Features:

```text
Add student
Display student
Update student
Calculate result
```

---

# 54. Common Mistakes

## Mistake 1: Forgetting `self`

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

## Mistake 2: Calling an instance method incorrectly

Example:

```python
class Student:

    def display(self):
        print("Hello")
```

Create an object:

```python
student = Student()

student.display()
```

---

## Mistake 3: Forgetting `@classmethod`

Wrong:

```python
class Student:

    def display(cls):
        print(cls)
```

Correct:

```python
class Student:

    @classmethod
    def display(cls):
        print(cls)
```

---

## Mistake 4: Forgetting `@staticmethod`

Correct:

```python
class Calculator:

    @staticmethod
    def add(a, b):
        return a + b
```

---

## Mistake 5: Confusing `self` and `cls`

Remember:

```text
self → object
cls  → class
```

---

# 55. OOP Relationship Keywords

Remember these:

```text
IS-A   → Inheritance

HAS-A  → Composition
```

Examples:

```text
Dog IS-A Animal

Car HAS-A Engine
```

---

# 56. Quick Revision

```text
self              → Current object

cls               → Current class

@classmethod      → Class method

@staticmethod     → Static method

@property         → Controlled attribute access

__attribute       → Private-style attribute/name mangling

super()           → Parent class functionality

MRO               → Method Resolution Order

__str__()         → String representation

__repr__()        → Developer-oriented representation

__len__()         → len() behavior

__eq__()          → == behavior

__add__()         → + behavior

isinstance()      → Check object/class relationship

issubclass()      → Check inheritance relationship

ABC               → Abstract Base Class

abstractmethod    → Abstract method

Composition       → HAS-A relationship

Inheritance       → IS-A relationship
```

---

# 🎯 Notes 13 Summary

In this lesson, you learned:

* Instance methods
* Class methods
* Static methods
* `self`
* `cls`
* Encapsulation
* Public attributes
* Protected convention
* Private attributes
* Getters
* Setters
* `@property`
* Property validation
* Single inheritance
* Multilevel inheritance
* Multiple inheritance
* Hierarchical inheritance
* Hybrid inheritance
* Method overriding
* `super()`
* MRO
* Magic methods
* `__str__()`
* `__repr__()`
* `__len__()`
* `__eq__()`
* `__add__()`
* Operator overloading
* Abstract classes
* Duck typing
* Composition
* Class attributes
* Instance attributes
* `isinstance()`
* `issubclass()`
* OOP mini projects
* OOP practice problems

---

# ⭐ Most Important Concepts

Remember these five:

```text
1. self
2. cls
3. @classmethod
4. @staticmethod
5. @property
```

And these OOP relationships:

```text
Inheritance
    ↓
IS-A

Composition
    ↓
HAS-A
```

A useful advanced OOP structure is:

```python
class Student:

    college = "RIT Hassan"

    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)

    @classmethod
    def college_name(cls):
        print(cls.college)

    @staticmethod
    def welcome():
        print("Welcome to Python")
```

**Next:** Notes 14 → **Python Exception Handling & Error Handling**
