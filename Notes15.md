# Python Beginners Notes – Notes 15

## 📘 Topic: Regular Expressions (Regex) in Python

Regular Expressions, commonly called **Regex**, are patterns used to search, match, validate, and manipulate text.

Python provides the built-in:

```python
re
```

module for working with regular expressions.

Regex is useful for:

* Finding text patterns
* Validating emails
* Validating phone numbers
* Extracting numbers
* Searching words
* Replacing text
* Splitting text
* Data cleaning

---

# 1. Import the `re` Module

Before using regular expressions:

```python
import re
```

---

# 2. Simple Search

Use:

```python
re.search()
```

Example:

```python
import re

text = "Python is easy to learn"

result = re.search("Python", text)

print(result)
```

If the pattern is found, a match object is returned.

---

# 3. Check Whether a Pattern Exists

```python
import re

text = "I am learning Python"

if re.search("Python", text):
    print("Python found")
else:
    print("Python not found")
```

Output:

```text
Python found
```

---

# 4. `re.search()`

`re.search()` searches the entire string and returns the first matching location.

Example:

```python
import re

text = "Python is powerful"

match = re.search("powerful", text)

print(match.group())
```

Output:

```text
powerful
```

---

# 5. `group()`

`group()` returns the matched text.

```python
import re

text = "I love Python"

match = re.search("Python", text)

print(match.group())
```

Output:

```text
Python
```

---

# 6. `start()`

`start()` returns the starting index of the match.

```python
import re

text = "I love Python"

match = re.search("Python", text)

print(match.start())
```

Output:

```text
7
```

---

# 7. `end()`

`end()` returns the index immediately after the match.

```python
import re

text = "I love Python"

match = re.search("Python", text)

print(match.end())
```

Output:

```text
13
```

---

# 8. `span()`

`span()` returns the start and end positions.

```python
import re

text = "I love Python"

match = re.search("Python", text)

print(match.span())
```

Output:

```text
(7, 13)
```

---

# 9. `re.match()`

`re.match()` checks only at the beginning of the string.

Example:

```python
import re

text = "Python is easy"

result = re.match("Python", text)

print(result.group())
```

Output:

```text
Python
```

---

# 10. Difference Between `search()` and `match()`

### `search()`

Searches anywhere:

```python
re.search("Python", "I love Python")
```

### `match()`

Checks only from the beginning:

```python
re.match("Python", "I love Python")
```

But:

```python
re.match("Python", "I love learning Python")
```

returns:

```text
None
```

---

# 11. `re.fullmatch()`

`fullmatch()` requires the entire string to match the pattern.

Example:

```python
import re

text = "Python"

result = re.fullmatch("Python", text)

print(result.group())
```

Output:

```text
Python
```

---

# 12. Regex Metacharacters

Regex uses special characters to represent patterns.

Important metacharacters:

```text
.  ^  $  *  +  ?  { }  [ ]  \  |  ( )
```

---

# 13. Dot `.`

The dot matches almost any single character except a newline.

Example:

```python
import re

text = "cat"

result = re.search("c.t", text)

print(result.group())
```

Output:

```text
cat
```

It can also match:

```text
cot
cut
c9t
```

---

# 14. Character Set `[ ]`

Square brackets match one character from a set.

Example:

```python
import re

text = "cat"

result = re.search("[abc]", text)

print(result.group())
```

Output:

```text
c
```

---

# 15. Character Range

You can specify a range.

```text
[a-z]
```

means lowercase letters.

```text
[A-Z]
```

means uppercase letters.

```text
[0-9]
```

means digits.

Example:

```python
import re

text = "Python123"

result = re.search("[0-9]", text)

print(result.group())
```

Output:

```text
1
```

---

# 16. `[^ ]` Negation

A caret inside brackets means "not".

Example:

```python
import re

text = "abc123"

result = re.search("[^a-z]", text)

print(result.group())
```

Output:

```text
1
```

It finds a character that is not lowercase.

---

# 17. `^` Start of String

`^` matches the beginning of a string.

Example:

```python
import re

text = "Python is easy"

if re.search("^Python", text):
    print("Starts with Python")
```

Output:

```text
Starts with Python
```

---

# 18. `$` End of String

`$` matches the end of a string.

Example:

```python
import re

text = "I love Python"

if re.search("Python$", text):
    print("Ends with Python")
```

Output:

```text
Ends with Python
```

---

# 19. `*` Zero or More

`*` means the previous character can occur zero or more times.

Example:

```python
import re

text = "cooool"

result = re.search("co*l", text)

print(result.group())
```

Possible match:

```text
cooool
```

It can match:

```text
cl
col
cool
coool
```

---

# 20. `+` One or More

`+` means one or more occurrences.

Example:

```python
import re

text = "coool"

result = re.search("co+l", text)

print(result.group())
```

It requires at least one `o`.

---

# 21. `?` Zero or One

`?` means zero or one occurrence.

Example:

```python
import re

text = "color"

result = re.search("colou?r", text)

print(result.group())
```

This pattern can match:

```text
color
colour
```

---

# 22. `{n}` Exact Number

`{n}` means exactly `n` occurrences.

Example:

```python
import re

text = "12345"

result = re.search(r"\d{3}", text)

print(result.group())
```

Output:

```text
123
```

---

# 23. `{n,m}` Range

Matches between `n` and `m` occurrences.

Example:

```python
import re

text = "123456"

result = re.search(r"\d{2,4}", text)

print(result.group())
```

Possible match:

```text
1234
```

---

# 24. `{n,}` Minimum Occurrences

Example:

```python
import re

text = "123456"

result = re.search(r"\d{4,}", text)

print(result.group())
```

This means at least 4 digits.

---

# 25. Special Character Classes

Python regex provides shortcuts.

```text
\d → Digit
\D → Not a digit

\w → Word character
\W → Not a word character

\s → Whitespace
\S → Not whitespace
```

---

# 26. `\d`

Matches digits.

Example:

```python
import re

text = "Age: 20"

result = re.search(r"\d+", text)

print(result.group())
```

Output:

```text
20
```

---

# 27. `\D`

Matches non-digit characters.

```python
import re

text = "123ABC"

result = re.search(r"\D+", text)

print(result.group())
```

Output:

```text
ABC
```

---

# 28. `\w`

Matches word characters.

Usually includes:

* Letters
* Digits
* Underscore

Example:

```python
import re

text = "Python_123"

result = re.search(r"\w+", text)

print(result.group())
```

Output:

```text
Python_123
```

---

# 29. `\s`

Matches whitespace.

Example:

```python
import re

text = "Hello World"

result = re.search(r"\s", text)

print(result.group())
```

The match is the space between the words.

---

# 30. Raw Strings

Regex patterns commonly use raw strings:

```python
r"..."
```

Example:

```python
pattern = r"\d+"
```

Raw strings make backslashes easier to work with.

---

# 31. `re.findall()`

`findall()` returns all matching strings.

Example:

```python
import re

text = "I have 10 apples and 20 oranges"

numbers = re.findall(r"\d+", text)

print(numbers)
```

Output:

```text
['10', '20']
```

---

# 32. Finding All Words

```python
import re

text = "Python Java C++"

words = re.findall(r"\w+", text)

print(words)
```

Output:

```text
['Python', 'Java', 'C']
```

Note: `\w+` does not treat `+` in `C++` as a word character.

---

# 33. `re.finditer()`

`finditer()` returns match objects for all matches.

Example:

```python
import re

text = "Python 10 Java 20"

for match in re.finditer(r"\d+", text):
    print(match.group(), match.start())
```

Output:

```text
10 7
20 15
```

---

# 34. `re.split()`

`re.split()` splits a string using a regex pattern.

Example:

```python
import re

text = "apple,banana;orange"

result = re.split(r"[,;]", text)

print(result)
```

Output:

```text
['apple', 'banana', 'orange']
```

---

# 35. `re.sub()`

`re.sub()` replaces matching text.

Example:

```python
import re

text = "I like Java"

result = re.sub("Java", "Python", text)

print(result)
```

Output:

```text
I like Python
```

---

# 36. Replace All Digits

```python
import re

text = "My marks are 90"

result = re.sub(r"\d+", "XX", text)

print(result)
```

Output:

```text
My marks are XX
```

---

# 37. Limiting Replacements

`count` controls how many replacements happen.

```python
import re

text = "cat cat cat"

result = re.sub("cat", "dog", text, count=2)

print(result)
```

Output:

```text
dog dog cat
```

---

# 38. Groups `( )`

Parentheses create groups.

Example:

```python
import re

text = "Name: Yashu"

result = re.search(r"Name: (\w+)", text)

print(result.group(1))
```

Output:

```text
Yashu
```

---

# 39. Multiple Groups

```python
import re

text = "Yashu 20"

result = re.search(r"(\w+)\s+(\d+)", text)

print(result.group(1))
print(result.group(2))
```

Output:

```text
Yashu
20
```

---

# 40. Named Groups

Named groups make patterns easier to understand.

Syntax:

```python
(?P<name>pattern)
```

Example:

```python
import re

text = "Name: Yashu"

result = re.search(r"Name: (?P<name>\w+)", text)

print(result.group("name"))
```

Output:

```text
Yashu
```

---

# 41. Alternation `|`

`|` means OR.

Example:

```python
import re

text = "I use Python"

result = re.search(r"Python|Java", text)

print(result.group())
```

Output:

```text
Python
```

---

# 42. Email Validation

A simple email pattern:

```python
import re

email = "yashu@example.com"

pattern = r"^[\w.-]+@[\w.-]+\.\w+$"

if re.fullmatch(pattern, email):
    print("Valid email")
else:
    print("Invalid email")
```

Output:

```text
Valid email
```

### Note

Email syntax is more complicated than this simple pattern. For real applications, use appropriate validation rather than assuming one simple regex handles every valid email address.

---

# 43. Phone Number Validation

Example for a 10-digit number:

```python
import re

phone = "9876543210"

pattern = r"^\d{10}$"

if re.fullmatch(pattern, phone):
    print("Valid phone number")
else:
    print("Invalid phone number")
```

Output:

```text
Valid phone number
```

---

# 44. Indian Mobile Number Example

A basic pattern:

```python
import re

phone = "9876543210"

pattern = r"^[6-9]\d{9}$"

if re.fullmatch(pattern, phone):
    print("Valid mobile number")
else:
    print("Invalid mobile number")
```

This checks for:

* 10 digits
* First digit from 6 to 9

---

# 45. Password Validation

Example requirements:

* At least 8 characters
* One uppercase letter
* One lowercase letter
* One digit

```python
import re

password = "Python123"

pattern = r"^(?=.*[A-Z])(?=.*[a-z])(?=.*\d).{8,}$"

if re.fullmatch(pattern, password):
    print("Strong password")
else:
    print("Weak password")
```

---

# 46. URL Validation – Simple Example

```python
import re

url = "https://example.com"

pattern = r"^https?://[\w.-]+(?:/.*)?$"

if re.fullmatch(pattern, url):
    print("Valid URL")
else:
    print("Invalid URL")
```

---

# 47. Extracting Email Addresses

```python
import re

text = """
Contact us at support@example.com
or admin@example.org
"""

emails = re.findall(
    r"[\w.-]+@[\w.-]+\.\w+",
    text
)

print(emails)
```

Output:

```text
['support@example.com', 'admin@example.org']
```

---

# 48. Extracting Phone Numbers

```python
import re

text = """
Call 9876543210 or 8765432109
"""

numbers = re.findall(r"\b[6-9]\d{9}\b", text)

print(numbers)
```

Output:

```text
['9876543210', '8765432109']
```

---

# 49. Extracting Numbers from Text

```python
import re

text = "Python 3.12 was released in 2023"

numbers = re.findall(r"\d+", text)

print(numbers)
```

Output:

```text
['3', '12', '2023']
```

---

# 50. Extracting Decimal Numbers

```python
import re

text = "Prices are 99.50 and 120.75"

numbers = re.findall(r"\d+(?:\.\d+)?", text)

print(numbers)
```

Output:

```text
['99.50', '120.75']
```

---

# 51. Removing Extra Spaces

```python
import re

text = "Python    is     easy"

clean_text = re.sub(r"\s+", " ", text)

print(clean_text)
```

Output:

```text
Python is easy
```

---

# 52. Removing Special Characters

```python
import re

text = "Hello@Python#World!"

clean_text = re.sub(r"[^\w\s]", "", text)

print(clean_text)
```

Output:

```text
HelloPythonWorld
```

---

# 53. Extracting Hashtags

```python
import re

text = "Learning #Python #Programming #AI"

hashtags = re.findall(r"#\w+", text)

print(hashtags)
```

Output:

```text
['#Python', '#Programming', '#AI']
```

---

# 54. Extracting Mentions

```python
import re

text = "Hello @Yashu and @Rahul"

mentions = re.findall(r"@\w+", text)

print(mentions)
```

Output:

```text
['@Yashu', '@Rahul']
```

---

# 55. Compiling a Pattern

If you use the same regex repeatedly, compile it.

```python
import re

pattern = re.compile(r"\d+")

text1 = "Age 20"
text2 = "Marks 90"

print(pattern.findall(text1))
print(pattern.findall(text2))
```

Output:

```text
['20']
['90']
```

---

# 56. Regex Flags

Flags modify regex behavior.

Common flags:

```text
re.IGNORECASE
re.MULTILINE
re.DOTALL
```

---

# 57. `re.IGNORECASE`

Makes matching case-insensitive.

```python
import re

text = "Python"

result = re.search(
    "python",
    text,
    re.IGNORECASE
)

print(result.group())
```

Output:

```text
Python
```

---

# 58. `re.MULTILINE`

Allows `^` and `$` to work with individual lines.

Example:

```python
import re

text = """Python
Java
Python"""

matches = re.findall(
    r"^Python$",
    text,
    re.MULTILINE
)

print(matches)
```

Output:

```text
['Python', 'Python']
```

---

# 59. `re.DOTALL`

Normally `.` does not match a newline.

`re.DOTALL` allows it to match newlines.

```python
import re

text = """Hello
World"""

result = re.search(
    r"Hello.*World",
    text,
    re.DOTALL
)

print(result.group())
```

---

# 60. Regex Cheat Sheet

| Pattern  | Meaning                      |    |
| -------- | ---------------------------- | -- |
| `.`      | Any character except newline |    |
| `^`      | Start                        |    |
| `$`      | End                          |    |
| `*`      | 0 or more                    |    |
| `+`      | 1 or more                    |    |
| `?`      | 0 or 1                       |    |
| `{n}`    | Exactly n                    |    |
| `{n,m}`  | n to m                       |    |
| `[abc]`  | a, b, or c                   |    |
| `[a-z]`  | Lowercase letter             |    |
| `[A-Z]`  | Uppercase letter             |    |
| `[0-9]`  | Digit                        |    |
| `[^abc]` | Not a, b, or c               |    |
| `\d`     | Digit                        |    |
| `\D`     | Non-digit                    |    |
| `\w`     | Word character               |    |
| `\W`     | Non-word character           |    |
| `\s`     | Whitespace                   |    |
| `\S`     | Non-whitespace               |    |
| `        | `                            | OR |
| `( )`    | Group                        |    |

---

# 61. Regex Functions Cheat Sheet

```text
re.search()      → Search anywhere

re.match()       → Match from beginning

re.fullmatch()   → Match entire string

re.findall()     → Find all matches

re.finditer()    → Find all match objects

re.split()       → Split using regex

re.sub()         → Replace matches

re.compile()     → Compile pattern
```

---

# 62. `search()` vs `match()` vs `fullmatch()`

| Function      | Checks        |
| ------------- | ------------- |
| `search()`    | Anywhere      |
| `match()`     | Beginning     |
| `fullmatch()` | Entire string |

Example:

```python
import re

text = "Python"

print(re.search("thon", text))
print(re.match("thon", text))
print(re.fullmatch("Python", text))
```

---

# 63. Mini Project – Email Extractor

```python
import re

text = """
My emails are:
yashu@example.com
admin@example.org
support@example.net
"""

pattern = r"[\w.-]+@[\w.-]+\.\w+"

emails = re.findall(pattern, text)

for email in emails:
    print(email)
```

Output:

```text
yashu@example.com
admin@example.org
support@example.net
```

---

# 64. Mini Project – Contact Extractor

```python
import re

text = """
Yashu: 9876543210
Rahul: 8765432109
Arun: 7654321098
"""

pattern = r"\b[6-9]\d{9}\b"

numbers = re.findall(pattern, text)

for number in numbers:
    print(number)
```

---

# 65. Mini Project – Text Cleaner

```python
import re

text = """
Hello!!!     Python@@@
This   is   a   test.
"""

text = re.sub(r"[^\w\s]", "", text)
text = re.sub(r"\s+", " ", text)

print(text.strip())
```

Output:

```text
Hello Python
This is a test
```

---

# 66. Mini Project – Password Validator

```python
import re

def validate_password(password):

    if len(password) < 8:
        return False

    if not re.search(r"[A-Z]", password):
        return False

    if not re.search(r"[a-z]", password):
        return False

    if not re.search(r"\d", password):
        return False

    return True


password = input("Enter password: ")

if validate_password(password):
    print("Strong password")
else:
    print("Weak password")
```

---

# 67. Mini Project – Student Data Extractor

```python
import re

text = """
Name: Yashu
Age: 20
Marks: 85
"""

name = re.search(
    r"Name:\s*(\w+)",
    text
)

age = re.search(
    r"Age:\s*(\d+)",
    text
)

marks = re.search(
    r"Marks:\s*(\d+)",
    text
)

print("Name:", name.group(1))
print("Age:", age.group(1))
print("Marks:", marks.group(1))
```

Output:

```text
Name: Yashu
Age: 20
Marks: 85
```

---

# 68. Practice Questions

## Beginner

### Question 1

Use regex to find all numbers from:

```text
I have 10 apples, 20 oranges and 30 bananas.
```

---

### Question 2

Check whether a string contains the word:

```text
Python
```

---

### Question 3

Find all words starting with:

```text
P
```

---

### Question 4

Find all email addresses in a paragraph.

---

### Question 5

Find all 10-digit mobile numbers.

---

# 69. Intermediate Practice

### Question 6

Create an email validator.

---

### Question 7

Create a phone number validator.

---

### Question 8

Create a password validator with:

* Minimum 8 characters
* Uppercase
* Lowercase
* Number

---

### Question 9

Remove all special characters from a sentence.

---

### Question 10

Replace multiple spaces with a single space.

---

# 70. Advanced Practice

### Question 11

Extract:

* Emails
* Phone numbers
* URLs

from a large text.

---

### Question 12

Create a log analyzer that extracts:

```text
IP address
Date
Time
Error message
```

---

### Question 13

Create a text cleaner that:

* Removes special characters
* Removes extra spaces
* Converts text to lowercase

---

### Question 14

Create a hashtag extractor.

Example:

```text
I love #Python and #AI
```

Expected:

```text
['#Python', '#AI']
```

---

### Question 15

Create a username validator.

Rules:

* 5–15 characters
* Letters, numbers, underscore only
* Must start with a letter

---

# 71. Common Mistakes

## Mistake 1: Forgetting Raw Strings

Instead of:

```python
"\d+"
```

prefer:

```python
r"\d+"
```

for regex patterns containing backslashes.

---

## Mistake 2: Using `match()` when you need `search()`

Remember:

```text
match()  → Beginning
search() → Anywhere
```

---

## Mistake 3: Forgetting That `findall()` Returns a List

Example:

```python
numbers = re.findall(r"\d+", text)
```

`numbers` is a list.

---

## Mistake 4: Assuming Simple Email Regex Is Perfect

Email syntax can be complex.

A basic regex is useful for simple validation, but production applications may need more robust validation.

---

# 72. Regex Learning Strategy

Learn these first:

```text
1. re.search()
2. re.match()
3. re.fullmatch()
4. re.findall()
5. re.sub()
6. re.split()
7. \d
8. \w
9. \s
10. +
11. *
12. ?
13. []
14. {}
15. ()
16. ^
17. $
```

Then practice validation and text extraction.

---

# 🎯 Notes 15 Summary

In this lesson, you learned:

* What Regular Expressions are
* `re` module
* `re.search()`
* `re.match()`
* `re.fullmatch()`
* Match objects
* `group()`
* `start()`
* `end()`
* `span()`
* Regex metacharacters
* Character sets
* Character ranges
* `^`
* `$`
* `*`
* `+`
* `?`
* `{n}`
* `{n,m}`
* `\d`
* `\D`
* `\w`
* `\W`
* `\s`
* `\S`
* Raw strings
* `re.findall()`
* `re.finditer()`
* `re.split()`
* `re.sub()`
* Groups
* Named groups
* Alternation
* Regex flags
* Email validation
* Phone validation
* Password validation
* Text extraction
* Text cleaning
* Pattern compilation
* Regex mini projects
* Practice questions

---

# ⭐ Most Important Regex Patterns

```text
\d+        → One or more digits

\w+        → One or more word characters

\s+        → One or more spaces

[a-z]      → Lowercase letters

[A-Z]      → Uppercase letters

[0-9]      → Digits

^Python    → Starts with Python

Python$    → Ends with Python

Python|Java → Python OR Java

\d{10}     → Exactly 10 digits

\w+@\w+\.\w+ → Simple email-like pattern
```

---

# 🧠 Final Example

```python
import re

text = """
My name is Yashu.
My email is yashu@example.com.
My phone number is 9876543210.
I am learning Python and AI.
"""

emails = re.findall(
    r"[\w.-]+@[\w.-]+\.\w+",
    text
)

phones = re.findall(
    r"\b[6-9]\d{9}\b",
    text
)

words = re.findall(
    r"\bPython\b",
    text,
    re.IGNORECASE
)

print("Emails:", emails)
print("Phones:", phones)
print("Python found:", bool(words))
```

Output:

```text
Emails: ['yashu@example.com']
Phones: ['9876543210']
Python found: True
```

---

## 🚀 Next Lesson

**Notes 16 → Python Modules, Packages & `pip`**
