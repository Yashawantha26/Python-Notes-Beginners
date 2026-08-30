
🐍 Python Beginners – Notes 7
📌 Topic: Lists in Python
1. What is a List?

A list is a collection of multiple values stored in a single variable.

Lists are:

Ordered
Changeable (Mutable)
Allow duplicate values
Can contain different data types
Example
fruits = ["apple", "banana", "mango"]

print(fruits)
Output
['apple', 'banana', 'mango']
2. Creating a List

A list is created using square brackets [].

numbers = [10, 20, 30, 40, 50]

print(numbers)
Output
[10, 20, 30, 40, 50]
3. Empty List

We can create an empty list.

my_list = []

print(my_list)
Output
[]
4. List with Different Data Types

A list can contain different types of values.

student = ["Yashu", 20, 85.5, True]

print(student)
Output
['Yashu', 20, 85.5, True]

A list can contain:

String
Integer
Float
Boolean
Other Lists
5. List Indexing

Every element in a list has an index.

The index starts from 0.

Example
fruits = ["apple", "banana", "mango", "orange"]

print(fruits[0])
print(fruits[1])
print(fruits[2])
print(fruits[3])
Output
apple
banana
mango
orange
Index Positions
apple   → 0
banana  → 1
mango   → 2
orange  → 3
6. Negative Indexing

Python also supports negative indexing.

The last element has index -1.

fruits = ["apple", "banana", "mango", "orange"]

print(fruits[-1])
print(fruits[-2])
Output
orange
mango
Negative Index Positions
apple   → -4
banana  → -3
mango   → -2
orange  → -1
7. Accessing List Elements

We can access an element using its index.

numbers = [10, 20, 30, 40]

print(numbers[2])
Output
30
8. Changing List Elements

Lists are mutable, which means we can change their values.

fruits = ["apple", "banana", "mango"]

fruits[1] = "orange"

print(fruits)
Output
['apple', 'orange', 'mango']
9. Adding Elements to a List
Using append()

append() adds an element to the end of the list.

fruits = ["apple", "banana"]

fruits.append("mango")

print(fruits)
Output
['apple', 'banana', 'mango']
10. Using insert()

insert() adds an element at a specific position.

Syntax
list.insert(index, value)
Example
fruits = ["apple", "mango"]

fruits.insert(1, "banana")

print(fruits)
Output
['apple', 'banana', 'mango']
11. Adding Multiple Elements Using extend()

extend() adds multiple elements to a list.

fruits = ["apple", "banana"]

fruits.extend(["mango", "orange"])

print(fruits)
Output
['apple', 'banana', 'mango', 'orange']
12. Difference Between append() and extend()
append()

Adds one object as a single element.

numbers = [1, 2]

numbers.append([3, 4])

print(numbers)

Output:

[1, 2, [3, 4]]
extend()

Adds each element separately.

numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)

Output:

[1, 2, 3, 4]
Remember
append() → adds one element
extend() → adds multiple elements
13. Removing Elements
Using remove()

remove() removes a specific value.

fruits = ["apple", "banana", "mango"]

fruits.remove("banana")

print(fruits)
Output
['apple', 'mango']
14. Using pop()

pop() removes an element using its index.

fruits = ["apple", "banana", "mango"]

fruits.pop(1)

print(fruits)
Output
['apple', 'mango']

If no index is given, pop() removes the last element.

fruits = ["apple", "banana", "mango"]

fruits.pop()

print(fruits)
Output
['apple', 'banana']
15. Using del

The del keyword can delete an element.

fruits = ["apple", "banana", "mango"]

del fruits[1]

print(fruits)
Output
['apple', 'mango']
16. clear()

clear() removes all elements from a list.

fruits = ["apple", "banana", "mango"]

fruits.clear()

print(fruits)
Output
[]
17. Finding Length of a List

Use the len() function.

fruits = ["apple", "banana", "mango"]

print(len(fruits))
Output
3
18. Checking if an Element Exists

Use the in operator.

fruits = ["apple", "banana", "mango"]

print("banana" in fruits)
Output
True

Example:

print("orange" in fruits)

Output:

False
19. Checking if an Element Does Not Exist

Use not in.

fruits = ["apple", "banana", "mango"]

print("orange" not in fruits)
Output
True
20. Loop Through a List

We can use a for loop to access every element.

fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
Output
apple
banana
mango
21. Loop Through Numbers
numbers = [10, 20, 30, 40]

for number in numbers:
    print(number)
Output
10
20
30
40
22. List with if Condition
numbers = [10, 15, 20, 25, 30]

for number in numbers:
    if number % 2 == 0:
        print(number)
Output
10
20
30
23. List Slicing

Slicing is used to get a portion of a list.

Syntax
list[start:end]

The ending index is not included.

Example
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
Output
[20, 30, 40]
24. List Slicing from Beginning
numbers = [10, 20, 30, 40, 50]

print(numbers[:3])
Output
[10, 20, 30]
25. List Slicing to End
numbers = [10, 20, 30, 40, 50]

print(numbers[2:])
Output
[30, 40, 50]
26. Negative Slicing
numbers = [10, 20, 30, 40, 50]

print(numbers[-3:])
Output
[30, 40, 50]
27. List Step

We can specify a step value.

Syntax
list[start:end:step]
Example
numbers = [1, 2, 3, 4, 5, 6]

print(numbers[::2])
Output
[1, 3, 5]
28. Reverse a List Using Slicing
numbers = [1, 2, 3, 4, 5]

print(numbers[::-1])
Output
[5, 4, 3, 2, 1]
29. sort()

sort() arranges elements in ascending order.

numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
Output
[10, 20, 30, 40, 50]
30. Sorting in Descending Order

Use reverse=True.

numbers = [50, 10, 40, 20, 30]

numbers.sort(reverse=True)

print(numbers)
Output
[50, 40, 30, 20, 10]
31. reverse()

reverse() reverses the existing list.

numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
Output
[5, 4, 3, 2, 1]
32. count()

count() counts how many times a value occurs.

numbers = [10, 20, 10, 30, 10]

print(numbers.count(10))
Output
3
33. index()

index() returns the position of the first occurrence of a value.

fruits = ["apple", "banana", "mango"]

print(fruits.index("banana"))
Output
1
34. copy()

copy() creates a copy of a list.

numbers = [10, 20, 30]

new_numbers = numbers.copy()

print(new_numbers)
Output
[10, 20, 30]
35. Copying a List
numbers = [1, 2, 3]

new_numbers = numbers

print(new_numbers)

Both variables refer to the same list.

For an independent copy, use:

new_numbers = numbers.copy()
36. Nested Lists

A list can contain another list.

This is called a nested list.

numbers = [
    [1, 2, 3],
    [4, 5, 6]
]

print(numbers)
Output
[[1, 2, 3], [4, 5, 6]]
37. Accessing Nested Lists
numbers = [
    [1, 2, 3],
    [4, 5, 6]
]

print(numbers[0][1])
Output
2

Explanation:

numbers[0] → [1, 2, 3]
numbers[0][1] → 2
38. List Concatenation

Two lists can be joined using +.

list1 = [1, 2, 3]
list2 = [4, 5, 6]

result = list1 + list2

print(result)
Output
[1, 2, 3, 4, 5, 6]
39. Repeating a List

We can repeat a list using *.

numbers = [1, 2, 3]

print(numbers * 2)
Output
[1, 2, 3, 1, 2, 3]
40. Taking List Input from User

We can create a list using input().

Example
numbers = input("Enter numbers: ").split()

print(numbers)

If the user enters:

10 20 30

Output:

['10', '20', '30']

Notice that the values are strings.

41. Converting Input to Integers
numbers = list(map(int, input("Enter numbers: ").split()))

print(numbers)

If input is:

10 20 30

Output:

[10, 20, 30]
42. Finding Maximum Value

Use max().

numbers = [10, 50, 30, 20, 40]

print(max(numbers))
Output
50
43. Finding Minimum Value

Use min().

numbers = [10, 50, 30, 20, 40]

print(min(numbers))
Output
10
44. Finding Sum

Use sum().

numbers = [10, 20, 30, 40]

print(sum(numbers))
Output
100
45. List Comprehension

List comprehension provides a short way to create lists.

Normal Method
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
Output
[1, 2, 3, 4, 5]
Using List Comprehension
numbers = [i for i in range(1, 6)]

print(numbers)
Output
[1, 2, 3, 4, 5]
46. List Comprehension with Condition
even_numbers = [i for i in range(1, 11) if i % 2 == 0]

print(even_numbers)
Output
[2, 4, 6, 8, 10]
47. Square Using List Comprehension
squares = [i * i for i in range(1, 6)]

print(squares)
Output
[1, 4, 9, 16, 25]
48. List Methods Summary
Method	Purpose
append()	Adds an element at the end
insert()	Adds an element at a specific position
extend()	Adds multiple elements
remove()	Removes a specific value
pop()	Removes an element by index
clear()	Removes all elements
sort()	Sorts the list
reverse()	Reverses the list
count()	Counts occurrences
index()	Finds the index
copy()	Creates a copy
49. Useful List Functions
Function	Purpose
len()	Finds number of elements
max()	Finds largest value
min()	Finds smallest value
sum()	Finds total
sorted()	Returns a sorted list
list()	Creates/converts to a list
50. Common Mistakes
Mistake 1: Wrong Index
numbers = [10, 20, 30]

print(numbers[3])

This causes:

IndexError

Valid indexes are:

0
1
2
Mistake 2: Forgetting That Index Starts at 0
numbers = [10, 20, 30]

print(numbers[0])

Output:

10

Not 20.

Mistake 3: Using remove() with an Index

Wrong:

numbers = [10, 20, 30]

numbers.remove(1)

remove() searches for a value.

Correct:

numbers.remove(20)

For an index, use:

numbers.pop(1)
51. Practice Programs
Program 1: Print All Elements
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
Program 2: Find Sum of List
numbers = [10, 20, 30, 40, 50]

print("Sum:", sum(numbers))
Output
Sum: 150
Program 3: Find Largest Number
numbers = [10, 50, 20, 40, 30]

print("Largest:", max(numbers))
Output
Largest: 50
Program 4: Find Smallest Number
numbers = [10, 50, 20, 40, 30]

print("Smallest:", min(numbers))
Output
Smallest: 10
Program 5: Count Even Numbers
numbers = [10, 15, 20, 25, 30, 35]

count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
Output
Even numbers: 3
Program 6: Print Even Numbers
numbers = [10, 15, 20, 25, 30, 35]

for number in numbers:
    if number % 2 == 0:
        print(number)
Output
10
20
30
Program 7: Print Odd Numbers
numbers = [10, 15, 20, 25, 30, 35]

for number in numbers:
    if number % 2 != 0:
        print(number)
Output
15
25
35
Program 8: Reverse a List
numbers = [1, 2, 3, 4, 5]

numbers.reverse()

print(numbers)
Output
[5, 4, 3, 2, 1]
Program 9: Sort a List
numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
Output
[10, 20, 30, 40, 50]
Program 10: Search an Element
numbers = [10, 20, 30, 40, 50]

search = int(input("Enter number to search: "))

if search in numbers:
    print("Number found")
else:
    print("Number not found")
52. Mini Project – Student Marks
marks = [85, 90, 78, 92, 88]

print("Marks:", marks)
print("Total:", sum(marks))
print("Highest:", max(marks))
print("Lowest:", min(marks))
print("Number of subjects:", len(marks))
print("Average:", sum(marks) / len(marks))
Example Output
Marks: [85, 90, 78, 92, 88]
Total: 433
Highest: 92
Lowest: 78
Number of subjects: 5
Average: 86.6
53. Mini Project – Shopping List
shopping_list = []

while True:
    item = input("Enter item (or type 'done'): ")

    if item.lower() == "done":
        break

    shopping_list.append(item)

print("\nShopping List:")

for item in shopping_list:
    print("-", item)
Example
Enter item (or type 'done'): Rice
Enter item (or type 'done'): Milk
Enter item (or type 'done'): Apples
Enter item (or type 'done'): done

Shopping List:
- Rice
- Milk
- Apples
54. Quick Revision
Create a List
fruits = ["apple", "banana", "mango"]
Access
print(fruits[0])
Change
fruits[0] = "orange"
Add
fruits.append("grapes")
Insert
fruits.insert(1, "banana")
Remove
fruits.remove("banana")
Delete by Index
fruits.pop(0)
Length
len(fruits)
Sort
fruits.sort()
Reverse
fruits.reverse()
Check
"apple" in fruits
Loop
for fruit in fruits:
    print(fruit)
55. Key Points to Remember ⭐
A list stores multiple values.
Lists are created using [].
List indexing starts from 0.
Negative indexing starts from -1.
Lists are mutable.
Lists allow duplicate values.
Lists can contain different data types.
append() adds one element.
insert() adds an element at a specific position.
extend() adds multiple elements.
remove() removes a value.
pop() removes an element using its index.
clear() removes all elements.
sort() sorts the list.
reverse() reverses the list.
len() finds the number of elements.
max() finds the largest value.
min() finds the smallest value.
sum() calculates the total.
in checks whether an element exists.
List comprehension provides a short way to create lists.
📝 Notes 7 Practice Questions
Basic Questions
What is a list in Python?
How do you create a list?
What is the first index of a list?
What is negative indexing?
Are Python lists mutable?
Can a list contain different data types?
What is the use of append()?
What is the use of insert()?
What is the use of extend()?
What is the difference between remove() and pop()?
Programming Questions
Create a list of five numbers and print it.
Print the first element of a list.
Print the last element using negative indexing.
Change an element in a list.
Add an element using append().
Insert an element at a specific position.
Remove an element from a list.
Find the length of a list.
Find the largest number in a list.
Find the smallest number in a list.
Find the sum of all numbers in a list.
Count how many even numbers are in a list.
Print all odd numbers from a list.
Reverse a list.
Sort a list in ascending order.
Sort a list in descending order.
Search for an element in a list.
Create a nested list.
Create a list using list comprehension.
Create a student marks program using a list.
🎯 Important Interview Questions
Q1. What is a list?

A list is an ordered and mutable collection of elements in Python.

Q2. How are lists created?

Using square brackets:

numbers = [1, 2, 3]
Q3. Are lists mutable?

Yes. We can change their elements after creation.

Q4. What is the difference between append() and extend()?
append() → adds one element
extend() → adds multiple elements
Q5. What is the difference between remove() and pop()?
remove() → removes a value
pop()    → removes an element using its index
Q6. What is list slicing?

List slicing extracts a portion of a list.

numbers = [1, 2, 3, 4, 5]

print(numbers[1:4])

Output:

[2, 3, 4]
🚀 End of Notes 7
Next Topic: Tuples in Python
give Notes8.md

Here is the complete Notes8.md, continuing your Python Beginners series with Tuples in Python.

🐍 Python Beginners – Notes 8
📌 Topic: Tuples in Python
1. What is a Tuple?

A tuple is a collection of multiple values stored in a single variable.

A tuple is:

Ordered
Immutable (Cannot be changed)
Allows duplicate values
Can contain different data types
Can contain another tuple or list
Example
fruits = ("apple", "banana", "mango")

print(fruits)
Output
('apple', 'banana', 'mango')
2. Creating a Tuple

Tuples are usually created using parentheses ().

numbers = (10, 20, 30, 40, 50)

print(numbers)
Output
(10, 20, 30, 40, 50)
3. Empty Tuple

We can create an empty tuple.

my_tuple = ()

print(my_tuple)
Output
()
4. Tuple with Different Data Types

A tuple can contain different types of values.

student = ("Yashu", 20, 85.5, True)

print(student)
Output
('Yashu', 20, 85.5, True)

A tuple can contain:

String
Integer
Float
Boolean
List
Tuple
5. Single Element Tuple

There is an important rule when creating a tuple with only one element.

Wrong
number = (10)

This is an integer, not a tuple.

Correct
number = (10,)

print(type(number))
Output
<class 'tuple'>

The comma , makes it a tuple.

6. Tuple Indexing

Every element in a tuple has an index.

The index starts from 0.

Example
fruits = ("apple", "banana", "mango", "orange")

print(fruits[0])
print(fruits[1])
print(fruits[2])
print(fruits[3])
Output
apple
banana
mango
orange
Index Positions
apple   → 0
banana  → 1
mango   → 2
orange  → 3
7. Negative Indexing

Tuples support negative indexing.

The last element has index -1.

fruits = ("apple", "banana", "mango", "orange")

print(fruits[-1])
print(fruits[-2])
Output
orange
mango
Negative Index Positions
apple   → -4
banana  → -3
mango   → -2
orange  → -1
8. Accessing Tuple Elements

We can access elements using their index.

numbers = (10, 20, 30, 40)

print(numbers[2])
Output
30
9. Tuple is Immutable

Immutable means the values cannot be changed after the tuple is created.

Example
numbers = (10, 20, 30)

numbers[1] = 50

This produces an error:

TypeError

We cannot directly change a tuple element.

10. List vs Tuple
List
numbers = [10, 20, 30]

numbers[1] = 50

This is allowed.

Tuple
numbers = (10, 20, 30)

numbers[1] = 50

This is not allowed.

Remember
List  → Mutable
Tuple → Immutable
11. Tuple Slicing

We can extract a portion of a tuple using slicing.

Syntax
tuple[start:end]

The ending index is not included.

Example
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
Output
(20, 30, 40)
12. Tuple Slicing from Beginning
numbers = (10, 20, 30, 40, 50)

print(numbers[:3])
Output
(10, 20, 30)
13. Tuple Slicing to End
numbers = (10, 20, 30, 40, 50)

print(numbers[2:])
Output
(30, 40, 50)
14. Negative Slicing
numbers = (10, 20, 30, 40, 50)

print(numbers[-3:])
Output
(30, 40, 50)
15. Tuple Step

We can specify a step value.

Syntax
tuple[start:end:step]
Example
numbers = (1, 2, 3, 4, 5, 6)

print(numbers[::2])
Output
(1, 3, 5)
16. Reverse a Tuple Using Slicing
numbers = (1, 2, 3, 4, 5)

print(numbers[::-1])
Output
(5, 4, 3, 2, 1)
17. len() Function

The len() function returns the number of elements in a tuple.

fruits = ("apple", "banana", "mango")

print(len(fruits))
Output
3
18. Checking an Element

Use the in operator to check whether an element exists.

fruits = ("apple", "banana", "mango")

print("banana" in fruits)
Output
True

Example:

print("orange" in fruits)

Output:

False
19. not in Operator

Use not in to check whether an element does not exist.

fruits = ("apple", "banana", "mango")

print("orange" not in fruits)
Output
True
20. Loop Through a Tuple

We can use a for loop to access every element.

fruits = ("apple", "banana", "mango")

for fruit in fruits:
    print(fruit)
Output
apple
banana
mango
21. Loop Using Index

We can use range() and len() to access tuple elements.

numbers = (10, 20, 30, 40)

for i in range(len(numbers)):
    print(numbers[i])
Output
10
20
30
40
22. count() Method

The count() method counts how many times a value appears.

numbers = (10, 20, 10, 30, 10)

print(numbers.count(10))
Output
3
23. index() Method

The index() method returns the position of the first occurrence of a value.

fruits = ("apple", "banana", "mango")

print(fruits.index("banana"))
Output
1
24. Tuple Concatenation

We can join two tuples using +.

tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)

result = tuple1 + tuple2

print(result)
Output
(1, 2, 3, 4, 5, 6)
25. Repeating a Tuple

We can repeat a tuple using *.

numbers = (1, 2, 3)

print(numbers * 2)
Output
(1, 2, 3, 1, 2, 3)
26. Nested Tuple

A tuple can contain another tuple.

This is called a nested tuple.

numbers = (
    (1, 2, 3),
    (4, 5, 6)
)

print(numbers)
Output
((1, 2, 3), (4, 5, 6))
27. Accessing Nested Tuple
numbers = (
    (1, 2, 3),
    (4, 5, 6)
)

print(numbers[0][1])
Output
2

Explanation:

numbers[0]     → (1, 2, 3)
numbers[0][1]  → 2
28. Tuple Packing

Putting multiple values into a single tuple is called tuple packing.

student = "Yashu", 20, "CSE"

print(student)
Output
('Yashu', 20, 'CSE')

Python automatically creates a tuple.

29. Tuple Unpacking

Taking values from a tuple and storing them in separate variables is called tuple unpacking.

student = ("Yashu", 20, "CSE")

name, age, course = student

print(name)
print(age)
print(course)
Output
Yashu
20
CSE
30. Unpacking with *

The * operator can collect multiple values.

numbers = (10, 20, 30, 40, 50)

first, *middle, last = numbers

print(first)
print(middle)
print(last)
Output
10
[20, 30, 40]
50

Notice that middle becomes a list.

31. Converting List to Tuple

Use the tuple() function.

numbers = [10, 20, 30, 40]

numbers_tuple = tuple(numbers)

print(numbers_tuple)
Output
(10, 20, 30, 40)
32. Converting Tuple to List

Use the list() function.

numbers = (10, 20, 30, 40)

numbers_list = list(numbers)

print(numbers_list)
Output
[10, 20, 30, 40]

Now we can modify the list.

numbers_list[1] = 50

print(numbers_list)
Output
[10, 50, 30, 40]
33. Modifying a Tuple Indirectly

Although tuples are immutable, we can convert them to a list, modify the list, and convert it back.

numbers = (10, 20, 30)

temp = list(numbers)

temp[1] = 50

numbers = tuple(temp)

print(numbers)
Output
(10, 50, 30)
34. max() Function

The max() function finds the largest value.

numbers = (10, 50, 30, 20, 40)

print(max(numbers))
Output
50
35. min() Function

The min() function finds the smallest value.

numbers = (10, 50, 30, 20, 40)

print(min(numbers))
Output
10
36. sum() Function

The sum() function calculates the total.

numbers = (10, 20, 30, 40)

print(sum(numbers))
Output
100
37. sorted() Function

The sorted() function returns a sorted list.

numbers = (50, 10, 40, 20, 30)

result = sorted(numbers)

print(result)
Output
[10, 20, 30, 40, 50]
Important

sorted() returns a list, not a tuple.

38. Sorting in Descending Order
numbers = (50, 10, 40, 20, 30)

result = sorted(numbers, reverse=True)

print(result)
Output
[50, 40, 30, 20, 10]
39. Tuple with a List

A tuple can contain a list.

data = ("Yashu", [80, 90, 85])

print(data)
Output
('Yashu', [80, 90, 85])

The tuple itself cannot be changed, but the list inside it can be modified.

data[1][0] = 95

print(data)
Output
('Yashu', [95, 90, 85])
40. Tuple with a Dictionary

A tuple can also contain a dictionary.

student = (
    "Yashu",
    {"Python": 90, "Java": 85}
)

print(student)
Output
('Yashu', {'Python': 90, 'Java': 85})
41. Tuple Comparison

Tuples can be compared using comparison operators.

tuple1 = (1, 2, 3)
tuple2 = (1, 2, 4)

print(tuple1 == tuple2)
print(tuple1 < tuple2)
Output
False
True

Python compares elements from left to right.

42. Membership Operators

The in and not in operators work with tuples.

numbers = (10, 20, 30, 40)

print(20 in numbers)
print(50 not in numbers)
Output
True
True
43. Tuple Methods

Tuples have only two main built-in methods.

count()

Counts occurrences.

numbers = (1, 2, 2, 3, 2)

print(numbers.count(2))

Output:

3
index()

Finds the first index.

numbers = (10, 20, 30)

print(numbers.index(20))

Output:

1
44. Why Use Tuples?

Tuples are useful when:

Data should not be changed
We want to protect values from accidental modification
We want to represent fixed data
We need to return multiple values from a function
We need an immutable collection
Example
coordinates = (12.9716, 77.5946)

Coordinates can be stored as a tuple because the pair of values represents fixed data.

45. List vs Tuple
Feature	List	Tuple
Syntax	[]	()
Mutable	Yes	No
Ordered	Yes	Yes
Duplicates	Allowed	Allowed
Different data types	Yes	Yes
Add elements	Yes	No
Remove elements	Yes	No
Change elements	Yes	No
Methods	Many	Few
Typical use	Changeable data	Fixed data
46. Tuple vs String

Both tuples and strings are sequences.

String
name = "Yashu"
Tuple
name = ("Y", "a", "s", "h", "u")

Both support:

Indexing
Slicing
len()
in
Loops

But their elements are different types of data.

47. Tuple as Function Return Value

A function can return multiple values as a tuple.

def calculate(a, b):
    return a + b, a - b

result = calculate(10, 5)

print(result)
Output
(15, 5)

We can unpack the result.

def calculate(a, b):
    return a + b, a - b

addition, subtraction = calculate(10, 5)

print(addition)
print(subtraction)
Output
15
5
48. Tuple Input from User

We can take multiple values and convert them into a tuple.

numbers = tuple(map(int, input("Enter numbers: ").split()))

print(numbers)

If the input is:

10 20 30 40

Output:

(10, 20, 30, 40)
49. Common Mistakes
Mistake 1: Trying to Change a Tuple

Wrong:

numbers = (10, 20, 30)

numbers[1] = 50

This gives:

TypeError

Because tuples are immutable.

Mistake 2: Forgetting the Comma

Wrong:

number = (10)

This is an integer.

Correct:

number = (10,)
Mistake 3: Using List Methods on a Tuple

Wrong:

numbers = (10, 20, 30)

numbers.append(40)

This gives:

AttributeError

Tuples do not have append().

50. Practice Programs
Program 1: Create a Tuple
fruits = ("apple", "banana", "mango")

print(fruits)
Program 2: Print First and Last Element
fruits = ("apple", "banana", "mango", "orange")

print("First:", fruits[0])
print("Last:", fruits[-1])
Output
First: apple
Last: orange
Program 3: Find Length
numbers = (10, 20, 30, 40, 50)

print("Length:", len(numbers))
Program 4: Find Sum
numbers = (10, 20, 30, 40, 50)

print("Sum:", sum(numbers))
Output
Sum: 150
Program 5: Find Largest Number
numbers = (10, 50, 20, 40, 30)

print("Largest:", max(numbers))
Output
Largest: 50
Program 6: Find Smallest Number
numbers = (10, 50, 20, 40, 30)

print("Smallest:", min(numbers))
Output
Smallest: 10
Program 7: Count an Element
numbers = (10, 20, 10, 30, 10)

print("10 occurs:", numbers.count(10), "times")
Output
10 occurs: 3 times
Program 8: Search an Element
fruits = ("apple", "banana", "mango")

search = input("Enter fruit: ")

if search in fruits:
    print("Fruit found")
else:
    print("Fruit not found")
Program 9: Reverse a Tuple
numbers = (1, 2, 3, 4, 5)

print(numbers[::-1])
Output
(5, 4, 3, 2, 1)
Program 10: Tuple Unpacking
student = ("Yashu", 20, "CSE")

name, age, course = student

print("Name:", name)
print("Age:", age)
print("Course:", course)
Output
Name: Yashu
Age: 20
Course: CSE
51. Mini Project – Student Information
student = (
    "Yashu",
    20,
    "CSE",
    85
)

name, age, course, marks = student

print("Student Information")
print("-------------------")
print("Name:", name)
print("Age:", age)
print("Course:", course)
print("Marks:", marks)
Output
Student Information
-------------------
Name: Yashu
Age: 20
Course: CSE
Marks: 85
52. Mini Project – Student Marks
marks = (85, 90, 78, 92, 88)

total = sum(marks)
highest = max(marks)
lowest = min(marks)
average = total / len(marks)

print("Marks:", marks)
print("Total:", total)
print("Highest:", highest)
print("Lowest:", lowest)
print("Average:", average)
Output
Marks: (85, 90, 78, 92, 88)
Total: 433
Highest: 92
Lowest: 78
Average: 86.6
53. Quick Revision
Create a Tuple
fruits = ("apple", "banana", "mango")
Access
print(fruits[0])
Negative Index
print(fruits[-1])
Length
print(len(fruits))
Check
print("apple" in fruits)
Count
print(fruits.count("apple"))
Index
print(fruits.index("banana"))
Loop
for fruit in fruits:
    print(fruit)
Slice
print(fruits[1:3])
Reverse
print(fruits[::-1])
Convert List to Tuple
numbers = tuple([1, 2, 3])
Convert Tuple to List
numbers = list((1, 2, 3))
54. Important Tuple Terms
Term	Meaning
Tuple	Ordered immutable collection
Immutable	Cannot be changed
Index	Position of an element
Slicing	Extracting part of a tuple
Packing	Creating a tuple from multiple values
Unpacking	Assigning tuple values to variables
count()	Counts an element
index()	Finds the first position
tuple()	Converts to tuple
list()	Converts to list
55. Key Points to Remember ⭐
A tuple is an ordered collection.
Tuples are created using ().
Tuple indexing starts from 0.
Negative indexing starts from -1.
Tuples are immutable.
Tuples allow duplicate values.
Tuples can contain different data types.
A single-element tuple requires a comma.
count() counts occurrences.
index() finds the first occurrence.
Tuples support slicing.
Tuples support loops.
Tuples support in and not in.
Tuples can be nested.
Tuples support packing and unpacking.
tuple() converts data into a tuple.
list() can convert a tuple into a list.
max(), min(), sum(), and len() work with numeric tuples.
sorted() returns a list.
Tuples are useful for fixed data.
📝 Notes 8 Practice Questions
Basic Questions
What is a tuple in Python?
How do you create a tuple?
What is the difference between a list and a tuple?
Are tuples mutable?
What is tuple indexing?
What is negative indexing?
What is tuple slicing?
What is tuple packing?
What is tuple unpacking?
Why is a comma required for a single-element tuple?
Programming Questions
Create a tuple containing five numbers.
Print the first element of a tuple.
Print the last element using negative indexing.
Find the length of a tuple.
Find the largest value in a tuple.
Find the smallest value in a tuple.
Find the sum of all values in a tuple.
Count how many times an element occurs.
Find the index of an element.
Reverse a tuple using slicing.
Check whether an element exists in a tuple.
Convert a list into a tuple.
Convert a tuple into a list.
Create a nested tuple.
Perform tuple unpacking.
Return multiple values from a function using a tuple.
Take tuple values as user input.
Sort a tuple using sorted().
Create a student information tuple.
Create a student marks program using a tuple.
🎯 Important Interview Questions
Q1. What is a tuple?

A tuple is an ordered and immutable collection of elements in Python.

Q2. How is a tuple created?

Using parentheses:

numbers = (1, 2, 3)
Q3. Are tuples mutable?

No. Tuples are immutable.

Q4. What is the difference between a list and a tuple?
List  → Mutable
Tuple → Immutable
Q5. How do you create a single-element tuple?

Use a comma:

number = (10,)
Q6. How do you access tuple elements?

Using indexes:

numbers = (10, 20, 30)

print(numbers[1])

Output:

20
Q7. What are the main tuple methods?
count()
index()
Q8. Can a tuple contain a list?

Yes.

data = ("Yashu", [80, 90, 85])
Q9. Can a tuple be converted into a list?

Yes.

numbers = (1, 2, 3)

numbers = list(numbers)
Q10. What is tuple unpacking?

Tuple unpacking means assigning tuple values to separate variables.

student = ("Yashu", 20, "CSE")

name, age, course = student
🚀 End of Notes 8
Next Topic: Sets in Python
give Notes9.md

Here is the complete Notes9.md — continuing with Sets in Python, ready to copy.

🐍 Python Beginners – Notes 9
📌 Topic: Sets in Python
1. What is a Set?

A set is a collection of unique elements in Python.

Sets are:

Unordered
Mutable
Unindexed
Do not allow duplicate values
Can contain different data types
Written using curly brackets {}
Example
fruits = {"apple", "banana", "mango"}

print(fruits)
Output
{'apple', 'banana', 'mango'}

Note: The order of elements in a set is not guaranteed.

2. Creating a Set

A set is usually created using curly brackets {}.

numbers = {10, 20, 30, 40, 50}

print(numbers)
Output
{10, 20, 30, 40, 50}
3. Set with Duplicate Values

Sets automatically remove duplicate values.

numbers = {10, 20, 10, 30, 20, 40}

print(numbers)
Output
{10, 20, 30, 40}

Duplicates are removed automatically.

4. Empty Set

Be careful when creating an empty set.

Wrong
my_set = {}

This creates an empty dictionary, not a set.

Correct
my_set = set()

print(my_set)
Output
set()
5. Set with Different Data Types

A set can contain different data types.

data = {"Yashu", 20, 85.5, True}

print(data)

The order may vary because sets are unordered.

6. Important Properties of Sets
Unordered

Sets do not maintain a fixed element position.

No Duplicates

Duplicate values are automatically removed.

Mutable

We can add and remove elements.

Unindexed

We cannot access elements using indexes.

7. Set Indexing

Sets do not support indexing.

Example
numbers = {10, 20, 30}

print(numbers[0])

This causes an error:

TypeError

Instead, use a loop.

for number in numbers:
    print(number)
8. Adding Elements Using add()

The add() method adds one element to a set.

fruits = {"apple", "banana"}

fruits.add("mango")

print(fruits)
Output
{'apple', 'banana', 'mango'}
9. Adding Duplicate Elements

Adding an existing element does nothing.

fruits = {"apple", "banana"}

fruits.add("apple")

print(fruits)

The set still contains only one "apple".

10. Adding Multiple Elements Using update()

The update() method adds multiple elements.

fruits = {"apple", "banana"}

fruits.update(["mango", "orange"])

print(fruits)
Result
{'apple', 'banana', 'mango', 'orange'}
11. Difference Between add() and update()
add()

Adds one element.

numbers = {1, 2, 3}

numbers.add(4)
update()

Adds multiple elements.

numbers = {1, 2, 3}

numbers.update([4, 5, 6])
Remember
add()    → one element
update() → multiple elements
12. Removing Elements Using remove()

remove() removes a specific element.

fruits = {"apple", "banana", "mango"}

fruits.remove("banana")

print(fruits)
Output
{'apple', 'mango'}

If the element does not exist, remove() raises a KeyError.

13. Removing Elements Using discard()

discard() also removes an element.

The difference is that it does not raise an error if the element is missing.

fruits = {"apple", "banana", "mango"}

fruits.discard("orange")

print(fruits)

No error occurs.

Remember
remove()  → error if element does not exist
discard() → no error if element does not exist
14. pop()

pop() removes and returns an arbitrary element from a set.

numbers = {10, 20, 30, 40}

removed = numbers.pop()

print("Removed:", removed)
print("Remaining:", numbers)

Because sets are unordered, you should not assume which element will be removed.

15. clear()

clear() removes all elements from a set.

numbers = {10, 20, 30}

numbers.clear()

print(numbers)
Output
set()
16. del Keyword

The del keyword can delete the entire set variable.

numbers = {10, 20, 30}

del numbers

After this, the variable numbers no longer exists.

17. Checking an Element

Use the in operator.

fruits = {"apple", "banana", "mango"}

print("banana" in fruits)
Output
True
18. not in Operator

Use not in to check whether an element does not exist.

fruits = {"apple", "banana", "mango"}

print("orange" not in fruits)
Output
True
19. Loop Through a Set

We can use a for loop.

fruits = {"apple", "banana", "mango"}

for fruit in fruits:
    print(fruit)

The output order may be different.

20. Finding Length of a Set

Use len().

numbers = {10, 20, 30, 40}

print(len(numbers))
Output
4
21. Set Union

Union combines all unique elements from two sets.

Use:

|

or:

union()
Example
set1 = {1, 2, 3}
set2 = {3, 4, 5}

result = set1 | set2

print(result)
Output
{1, 2, 3, 4, 5}
22. union() Method
set1 = {1, 2, 3}
set2 = {3, 4, 5}

result = set1.union(set2)

print(result)
Output
{1, 2, 3, 4, 5}
23. Set Intersection

Intersection returns elements that are common to both sets.

Use:

&
Example
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1 & set2

print(result)
Output
{2, 3}
24. intersection() Method
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1.intersection(set2)

print(result)
Output
{2, 3}
25. Set Difference

Difference returns elements that exist in the first set but not in the second.

Use:

-
Example
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1 - set2

print(result)
Output
{1}
26. difference() Method
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1.difference(set2)

print(result)
Output
{1}
27. Difference in Reverse Direction
set1 = {1, 2, 3}
set2 = {2, 3, 4}

print(set2 - set1)
Output
{4}

The order of the sets matters.

28. Symmetric Difference

Symmetric difference returns elements that are in either set, but not in both.

Use:

^
Example
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1 ^ set2

print(result)
Output
{1, 4}
29. symmetric_difference() Method
set1 = {1, 2, 3}
set2 = {2, 3, 4}

result = set1.symmetric_difference(set2)

print(result)
Output
{1, 4}
30. Set Operators Summary
Operator	Meaning
`	`	Union
&	Intersection
-	Difference
^	Symmetric Difference
31. Union Example
students_python = {"Yashu", "Rahul", "Anil"}
students_java = {"Rahul", "Anil", "Kiran"}

all_students = students_python | students_java

print(all_students)

The result contains every unique student.

32. Intersection Example
students_python = {"Yashu", "Rahul", "Anil"}
students_java = {"Rahul", "Anil", "Kiran"}

common = students_python & students_java

print(common)
Result
{'Rahul', 'Anil'}

These students are in both sets.

33. Difference Example
students_python = {"Yashu", "Rahul", "Anil"}
students_java = {"Rahul", "Anil", "Kiran"}

only_python = students_python - students_java

print(only_python)
Result
{'Yashu'}
34. Symmetric Difference Example
students_python = {"Yashu", "Rahul", "Anil"}
students_java = {"Rahul", "Anil", "Kiran"}

different = students_python ^ students_java

print(different)
Result
{'Yashu', 'Kiran'}
35. Subset

A set is a subset if every element of one set is also present in another set.

Use:

<=

or:

issubset()
Example
small = {1, 2}
large = {1, 2, 3, 4}

print(small.issubset(large))
Output
True
36. issubset()
set1 = {1, 2}
set2 = {1, 2, 3}

print(set1.issubset(set2))
Output
True
37. Superset

A set is a superset if it contains all elements of another set.

Use:

>=

or:

issuperset()
Example
set1 = {1, 2, 3}
set2 = {1, 2}

print(set1.issuperset(set2))
Output
True
38. Disjoint Sets

Two sets are disjoint if they have no common elements.

Use:

isdisjoint()
Example
set1 = {1, 2, 3}
set2 = {4, 5, 6}

print(set1.isdisjoint(set2))
Output
True
39. copy()

The copy() method creates a copy of a set.

numbers = {1, 2, 3}

new_numbers = numbers.copy()

print(new_numbers)
Output
{1, 2, 3}
40. Set Comprehension

Set comprehension provides a short way to create sets.

Normal Method
numbers = set()

for i in range(1, 6):
    numbers.add(i)

print(numbers)
Using Set Comprehension
numbers = {i for i in range(1, 6)}

print(numbers)
Result
{1, 2, 3, 4, 5}
41. Set Comprehension with Condition
even_numbers = {i for i in range(1, 11) if i % 2 == 0}

print(even_numbers)
Output
{2, 4, 6, 8, 10}
42. Converting List to Set

Use set().

numbers = [10, 20, 10, 30, 20]

numbers_set = set(numbers)

print(numbers_set)
Output
{10, 20, 30}

This is useful for removing duplicate values.

43. Removing Duplicates from a List
numbers = [1, 2, 2, 3, 3, 4, 4]

unique_numbers = list(set(numbers))

print(unique_numbers)

The result contains unique values.

The order is not guaranteed because sets are unordered.

44. Converting Set to List
numbers = {10, 20, 30}

numbers_list = list(numbers)

print(numbers_list)
Output
[10, 20, 30]
45. Converting Set to Tuple
numbers = {10, 20, 30}

numbers_tuple = tuple(numbers)

print(numbers_tuple)

The order may vary.

46. frozenset

A frozenset is an immutable version of a set.

It cannot be changed after creation.

Example
numbers = frozenset([1, 2, 3, 4])

print(numbers)
Output
frozenset({1, 2, 3, 4})
47. Set vs Frozenset
Feature	Set	Frozenset
Mutable	Yes	No
Add elements	Yes	No
Remove elements	Yes	No
Duplicates	No	No
Unordered	Yes	Yes
48. Why Use Sets?

Sets are useful when:

We need unique values
We need to remove duplicates
We need to find common elements
We need to compare groups
We need union, intersection, or difference operations
We need fast membership checking
49. Set vs List vs Tuple
Feature	List	Tuple	Set
Syntax	[]	()	{}
Ordered	Yes	Yes	No
Mutable	Yes	No	Yes
Duplicates	Allowed	Allowed	Not allowed
Indexing	Yes	Yes	No
Slicing	Yes	Yes	No
Main use	Changeable collection	Fixed collection	Unique collection
50. Set Methods Summary
Method	Purpose
add()	Adds one element
update()	Adds multiple elements
remove()	Removes an element
discard()	Removes an element without error if missing
pop()	Removes an arbitrary element
clear()	Removes all elements
copy()	Creates a copy
union()	Combines sets
intersection()	Finds common elements
difference()	Finds elements only in first set
symmetric_difference()	Finds elements in either set but not both
issubset()	Checks subset
issuperset()	Checks superset
isdisjoint()	Checks for no common elements
51. Set Operators Summary
|   → Union
&   → Intersection
-   → Difference
^   → Symmetric Difference
Example
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)
print(A & B)
print(A - B)
print(A ^ B)
52. Common Mistakes
Mistake 1: Trying to Use Indexing

Wrong:

numbers = {10, 20, 30}

print(numbers[0])

Sets do not support indexing.

Mistake 2: Creating an Empty Set Incorrectly

Wrong:

numbers = {}

This creates a dictionary.

Correct:

numbers = set()
Mistake 3: Assuming Set Order

Do not assume that:

numbers = {10, 20, 30}

will always print in the same order.

Sets are unordered.

Mistake 4: Using remove() for a Missing Element
numbers = {1, 2, 3}

numbers.remove(10)

This causes a KeyError.

If you are not sure whether the element exists, use:

numbers.discard(10)
53. Practice Programs
Program 1: Create a Set
numbers = {10, 20, 30, 40, 50}

print(numbers)
Program 2: Remove Duplicates
numbers = [10, 20, 10, 30, 20, 40]

unique = set(numbers)

print(unique)
Program 3: Add an Element
numbers = {10, 20, 30}

numbers.add(40)

print(numbers)
Program 4: Remove an Element
numbers = {10, 20, 30}

numbers.remove(20)

print(numbers)
Program 5: Check an Element
numbers = {10, 20, 30}

search = int(input("Enter number: "))

if search in numbers:
    print("Number found")
else:
    print("Number not found")
Program 6: Union
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)
Program 7: Intersection
A = {1, 2, 3}
B = {2, 3, 4}

print(A & B)
Program 8: Difference
A = {1, 2, 3}
B = {2, 3, 4}

print(A - B)
Program 9: Symmetric Difference
A = {1, 2, 3}
B = {2, 3, 4}

print(A ^ B)
Program 10: Find Unique Numbers
numbers = [1, 2, 2, 3, 4, 4, 5, 5]

unique_numbers = set(numbers)

print(unique_numbers)
54. Mini Project – Common Students

Suppose two groups of students participate in different courses.

python_students = {"Yashu", "Rahul", "Anil", "Kiran"}

java_students = {"Rahul", "Anil", "Manoj", "Kiran"}

common_students = python_students & java_students

print("Students in both courses:")
print(common_students)
Result
Students in both courses:
{'Rahul', 'Anil', 'Kiran'}
55. Mini Project – Unique Names
names = [
    "Yashu",
    "Rahul",
    "Anil",
    "Yashu",
    "Kiran",
    "Rahul"
]

unique_names = set(names)

print("Unique Names:")

for name in unique_names:
    print(name)

The duplicate names are removed.

56. Mini Project – Common Subjects
student1 = {"Python", "Java", "DBMS", "OS"}

student2 = {"Python", "DBMS", "AI", "Web"}

common = student1 & student2

print("Common Subjects:", common)
Result
Common Subjects: {'Python', 'DBMS'}
57. Quick Revision
Create a Set
numbers = {1, 2, 3}
Empty Set
numbers = set()
Add
numbers.add(4)
Add Multiple
numbers.update([5, 6])
Remove
numbers.remove(2)
Safe Remove
numbers.discard(2)
Clear
numbers.clear()
Length
len(numbers)
Check
2 in numbers
Union
A | B
Intersection
A & B
Difference
A - B
Symmetric Difference
A ^ B
Subset
A.issubset(B)
Superset
A.issuperset(B)
Disjoint
A.isdisjoint(B)
58. Important Set Terms
Term	Meaning
Set	Collection of unique elements
Unordered	No guaranteed position/order
Mutable	Can be changed
Duplicate	Repeated value
Union	All unique elements
Intersection	Common elements
Difference	Elements only in one set
Symmetric Difference	Elements not common
Subset	Set contained inside another set
Superset	Set containing another set
Disjoint	Sets with no common elements
frozenset	Immutable set
59. Key Points to Remember ⭐
A set stores unique elements.
Sets are created using {}.
An empty set is created using set().
Sets do not allow duplicate values.
Sets are unordered.
Sets do not support indexing.
Sets are mutable.
add() adds one element.
update() adds multiple elements.
remove() removes an element and raises an error if it is missing.
discard() removes an element without raising an error if it is missing.
pop() removes an arbitrary element.
clear() removes all elements.
in checks membership.
| performs union.
& performs intersection.
- performs difference.
^ performs symmetric difference.
issubset() checks whether a set is a subset.
issuperset() checks whether a set is a superset.
isdisjoint() checks whether two sets have no common elements.
frozenset is an immutable set.
Sets are very useful for removing duplicates.
📝 Notes 9 Practice Questions
Basic Questions
What is a set in Python?
How do you create a set?
What are the main properties of a set?
Does a set allow duplicate values?
Are sets ordered?
Can we use indexing with sets?
How do you create an empty set?
What is the use of add()?
What is the use of update()?
What is the difference between remove() and discard()?
Programming Questions
Create a set containing five numbers.
Create an empty set.
Add an element to a set.
Add multiple elements to a set.
Remove an element from a set.
Check whether an element exists.
Find the length of a set.
Remove duplicate values from a list using a set.
Find the union of two sets.
Find the intersection of two sets.
Find the difference between two sets.
Find the symmetric difference of two sets.
Check whether one set is a subset of another.
Check whether one set is a superset of another.
Check whether two sets are disjoint.
Loop through a set.
Convert a list to a set.
Convert a set to a list.
Create a set using set comprehension.
Create a program to find common students between two courses.
🎯 Important Interview Questions
Q1. What is a set?

A set is an unordered, mutable collection of unique elements in Python.

Q2. Do sets allow duplicates?

No. Duplicate values are automatically removed.

numbers = {1, 2, 2, 3}

print(numbers)

Result:

{1, 2, 3}
Q3. Can sets be indexed?

No. Sets do not support indexing.

Q4. How do you create an empty set?
my_set = set()
Q5. What is the difference between remove() and discard()?
remove()  → raises KeyError if element is missing
discard() → does not raise an error
Q6. What is union?

Union combines all unique elements from two sets.

A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)

Result:

{1, 2, 3, 4, 5}
Q7. What is intersection?

Intersection returns common elements.

A = {1, 2, 3}
B = {2, 3, 4}

print(A & B)

Result:

{2, 3}
Q8. What is difference?

Difference returns elements present in the first set but not the second.

A = {1, 2, 3}
B = {2, 3, 4}

print(A - B)

Result:

{1}
Q9. What is a frozenset?

A frozenset is an immutable version of a set.

numbers = frozenset([1, 2, 3])
Q10. How can you remove duplicates from a list?

Convert the list into a set:

numbers = [1, 2, 2, 3, 3]

unique = set(numbers)

print(unique)
🚀 End of Notes 9
Next Topic: Dictionaries in Python
