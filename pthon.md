# 🐍 Complete Python Tutorial — Beginner to Expert
### With Full Descriptions, Explanations & Examples

> [!NOTE]
> This tutorial covers **5 progressive levels** — from absolute beginner to expert. Every topic includes a detailed description, real-world analogies, common pitfalls, and runnable code examples. Work through each level in order and practice every example.

---

## 📋 Table of Contents

- [Level 1 — Beginner (Foundations)](#level-1--beginner-foundations)
  - [1.1 What is Python?](#11-what-is-python)
  - [1.2 Installing Python](#12-installing-python)
  - [1.3 Your First Program](#13-your-first-program)
  - [1.4 Comments](#14-comments)
  - [1.5 Variables and Data Types](#15-variables-and-data-types)
  - [1.6 Basic Input and Output](#16-basic-input-and-output)
  - [1.7 Basic Operators](#17-basic-operators)
  - [1.8 Strings in Detail](#18-strings-in-detail)
  - [1.9 Type Conversion (Casting)](#19-type-conversion-casting)
- [Level 2 — Elementary (Building Blocks)](#level-2--elementary-building-blocks)
  - [2.1 Conditional Statements](#21-conditional-statements-if--elif--else)
  - [2.2 Loops](#22-loops)
  - [2.3 Lists](#23-lists)
  - [2.4 Tuples](#24-tuples)
  - [2.5 Dictionaries](#25-dictionaries)
  - [2.6 Sets](#26-sets)
  - [2.7 Functions](#27-functions)
- [Level 3 — Intermediate (Core Python)](#level-3--intermediate-core-python)
- [Level 4 — Advanced Python](#level-4--advanced-python)
- [Level 5 — Expert (Mastery)](#level-5--expert-mastery)

---

# Level 1 — Beginner (Foundations)

## 1.1 What is Python?

**Python** is a high-level, interpreted, dynamically-typed, general-purpose programming language created by **Guido van Rossum** and first released in **1991**. The name "Python" was inspired by the British comedy series *Monty Python's Flying Circus* — not the snake!

Python follows the philosophy of **"There should be one obvious way to do it"**, making it extremely readable and beginner-friendly. Its design prioritizes **code clarity** over clever tricks.

### How Python Works

When you write Python code, the interpreter reads it line-by-line (that's what "interpreted" means). Unlike compiled languages (C, C++), there's no separate compilation step — you just write and run. Python converts your code to **bytecode** (.pyc files) internally, which runs on the Python Virtual Machine (PVM).

```
Your Code (.py) → Python Interpreter → Bytecode → PVM → Output
```

### Why Learn Python?

| Reason | Details |
|--------|---------|
| 🟢 **Beginner Friendly** | Syntax reads almost like English — very low learning curve |
| 🚀 **Versatile** | Web development, data science, AI/ML, automation, scripting, games |
| 📦 **Rich Ecosystem** | 400,000+ packages on PyPI (Python Package Index) |
| 💼 **High Demand** | Consistently top 3 most demanded programming language globally |
| 🌍 **Huge Community** | Millions of developers, Stack Overflow, tutorials, forums |
| 🔬 **Scientific Computing** | NumPy, Pandas, TensorFlow, PyTorch — the language of data science |
| 🆓 **Free & Open Source** | No licensing cost — free forever |

### Python vs Other Languages

```
Python:   print("Hello World")           → 1 line
Java:     System.out.println("Hello");   → needs class + main method
C++:      #include<iostream>
          int main() { std::cout << "Hello"; return 0; }
```

Python 3 is the current version (Python 2 reached end-of-life in 2020). Always use **Python 3.10+**.

---

## 1.2 Installing Python

Python needs to be installed before you can run programs. Here's how:

### Step-by-Step Installation

**Windows:**
1. Visit [python.org/downloads](https://www.python.org/downloads/)
2. Click the big yellow "Download Python 3.x.x" button
3. Run the installer
4. ✅ **CRITICAL**: Check **"Add Python to PATH"** before clicking Install
5. Click "Install Now"

**macOS:**
```bash
# Using Homebrew (recommended)
brew install python3
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install python3 python3-pip
```

### Verify Installation

After installing, open a terminal/command prompt and run:

```bash
python --version
# or on some systems:
python3 --version

# Expected output:
# Python 3.12.3
```

### Choosing an Editor / IDE

| Editor | Best For | Cost |
|--------|----------|------|
| **VS Code** | All-purpose, lightweight | Free |
| **PyCharm** | Professional Python dev | Free (Community) / Paid (Pro) |
| **Jupyter Notebook** | Data science, experiments | Free |
| **IDLE** | Beginners, bundled with Python | Free |
| **Thonny** | Absolute beginners (school use) | Free |

> [!TIP]
> **VS Code** with the Python extension is the most popular choice. Install it from [code.visualstudio.com](https://code.visualstudio.com) then add the **"Python"** extension by Microsoft.

### Setting Up VS Code for Python

1. Install VS Code
2. Install the **Python** extension (Ctrl+Shift+X → search "Python")
3. Open a folder → Create a new file `hello.py`
4. Write your code and press **F5** to run

---

## 1.3 Your First Program

Every programmer's journey begins with **"Hello, World!"** — a simple program that prints text to the screen. In Python, this takes exactly one line.

### The `print()` Function

`print()` is Python's built-in function that outputs text (or any value) to the screen. It's your primary tool for showing results to the user.

```python
# Your very first Python program!
print("Hello, World!")

# Output:
# Hello, World!
```

### More print() Examples

```python
# Print a simple message
print("Hello, World!")

# Print numbers
print(42)
print(3.14)

# Print multiple values (separated by space by default)
print("Name:", "Alice", "Age:", 25)
# Output: Name: Alice Age: 25

# Change the separator
print("apple", "banana", "cherry", sep=", ")
# Output: apple, banana, cherry

# Change the ending (default is newline \n)
print("Hello", end=" ")
print("World!")
# Output: Hello World!   (on same line)

# Print nothing (just a blank line)
print()

# Print multiple lines
print("Line 1\nLine 2\nLine 3")
# Output:
# Line 1
# Line 2
# Line 3
```

> [!TIP]
> **How to run a Python file:**
> 1. Save your file as `hello.py`
> 2. Open terminal in the same folder
> 3. Type: `python hello.py` and press Enter

---

## 1.4 Comments

Comments are lines in your code that **Python completely ignores**. They exist solely for humans — to explain what the code does, why it was written a certain way, or to leave reminders.

### Why Comments Matter

- **Readability**: Code is read far more often than it is written
- **Collaboration**: Other developers (or future-you) need to understand your code
- **Documentation**: Explains complex logic that isn't immediately obvious
- **Debugging**: Temporarily "remove" code without deleting it

### Types of Comments

```python
# ──────────────────────────────────────────────
# 1. SINGLE-LINE COMMENT
#    Starts with a # symbol. Python ignores everything after #
# ──────────────────────────────────────────────

x = 10  # This is an inline comment — code runs, then comment is ignored

# This whole line is a comment — nothing executes

# ──────────────────────────────────────────────
# 2. MULTI-LINE COMMENT (using triple quotes)
#    Technically these are string literals (docstrings), but when placed
#    alone they act as multi-line comments.
# ──────────────────────────────────────────────

"""
This is a multi-line comment.
You can write as many lines as you want.
Python ignores this block entirely when it's not assigned to a variable.
"""

'''
You can also use single triple quotes.
Both work the same way.
'''

# ──────────────────────────────────────────────
# 3. DOCSTRINGS — special comments for functions, classes, modules
# ──────────────────────────────────────────────

def calculate_area(radius):
    """
    Calculate the area of a circle.

    Args:
        radius (float): The radius of the circle.

    Returns:
        float: The area of the circle.

    Example:
        >>> calculate_area(5)
        78.53981633974483
    """
    import math
    return math.pi * radius ** 2

# You can access a function's docstring like this:
print(calculate_area.__doc__)
```

### Comment Best Practices

```python
# ✅ GOOD — explains WHY, not just WHAT
# Using index -1 because we always want the last uploaded file
latest_file = uploaded_files[-1]

# ❌ BAD — just restates what the code does (obvious)
# Get the last element
latest_file = uploaded_files[-1]

# ✅ GOOD — explains a non-obvious algorithm
# Fisher-Yates shuffle: ensures uniform probability distribution
# Time complexity: O(n), Space: O(1)
for i in range(len(arr) - 1, 0, -1):
    j = random.randint(0, i)
    arr[i], arr[j] = arr[j], arr[i]
```

---

## 1.5 Variables and Data Types

### What is a Variable?

A **variable** is like a labelled box that stores a value. You give it a name, and Python remembers the value for you. Unlike some languages, Python is **dynamically typed** — you don't need to declare what type of data a variable will hold. Python figures it out automatically.

```
Think of variables like labelled jars:
    name = "Alice"   →  [  "Alice"  ] ← jar labelled "name"
    age  = 25        →  [    25    ] ← jar labelled "age"
```

### Core Data Types

Python has several built-in data types. These are the foundational ones:

```python
# ── INTEGER (int) ──────────────────────────────────────────────────────────
# Whole numbers, positive or negative, no decimal point
# No size limit in Python (unlike C/Java which have int32, int64)
age = 25
year = 2024
negative = -100
big_number = 1_000_000   # Underscores allowed for readability (= 1000000)
binary = 0b1010          # Binary literal (= 10)
hexadecimal = 0xFF       # Hex literal (= 255)
octal = 0o17             # Octal literal (= 15)

print(type(age))         # <class 'int'>


# ── FLOAT (float) ──────────────────────────────────────────────────────────
# Numbers with a decimal point (floating-point)
# Stored as 64-bit IEEE 754 double precision
price = 19.99
pi = 3.14159265358979
negative_float = -0.5
scientific = 1.5e10     # Scientific notation = 15,000,000,000
tiny = 2.5e-4           # = 0.00025

print(type(price))      # <class 'float'>

# ⚠️ Floating-point precision warning:
print(0.1 + 0.2)        # 0.30000000000000004  (not exactly 0.3!)
# This is a known issue with binary floating-point math
# Use the decimal module when precision matters (e.g., money)
from decimal import Decimal
print(Decimal('0.1') + Decimal('0.2'))  # 0.3 (exact!)


# ── STRING (str) ──────────────────────────────────────────────────────────
# Sequences of characters (text). Immutable.
name = "Alice"
city = 'Mumbai'
multiline = """This
spans multiple
lines"""

print(type(name))       # <class 'str'>


# ── BOOLEAN (bool) ────────────────────────────────────────────────────────
# Only two possible values: True or False
# Note: True and False must be capitalized!
is_student = True
has_passed = False
is_adult = (18 >= 18)   # Evaluates to True

print(type(is_student)) # <class 'bool'>

# Booleans are subclass of int: True == 1, False == 0
print(True + True)      # 2
print(True * 5)         # 5


# ── NONE (NoneType) ───────────────────────────────────────────────────────
# Represents the absence of a value — like "null" in other languages
# Used as a default/placeholder or to indicate "nothing"
result = None
user_email = None        # Email not yet provided

print(type(result))     # <class 'NoneType'>
print(result is None)   # True  (use 'is' to check for None, not ==)
```

### Variable Naming Rules

Python has strict rules for naming variables. Break them and you'll get a `SyntaxError`.

```python
# ✅ VALID variable names
my_name = "Alice"         # snake_case (preferred in Python)
_private_var = 10         # Leading underscore = "internal use"
__very_private = 99       # Double underscore = name mangling (advanced)
camelCase = "valid"       # Works but not Pythonic
CONSTANT_VALUE = 3.14     # ALL_CAPS = convention for constants
user2 = "Bob"             # Numbers allowed (not at start)

# ❌ INVALID variable names (will cause SyntaxError)
# 2user = "error"         # Cannot start with a digit
# my-name = "error"       # Hyphens not allowed (it's subtraction!)
# my name = "error"       # No spaces in names
# for = "error"           # 'for' is a reserved keyword

# Python reserved keywords (cannot be used as variable names):
# False, None, True, and, as, assert, async, await, break, class,
# continue, def, del, elif, else, except, finally, for, from,
# global, if, import, in, is, lambda, nonlocal, not, or, pass,
# raise, return, try, while, with, yield
```

### Multiple Assignment

```python
# Assign same value to multiple variables at once
x = y = z = 0
print(x, y, z)  # 0 0 0

# Assign multiple values at once (tuple unpacking)
a, b, c = 1, 2, 3
print(a, b, c)  # 1 2 3

# Swap values — Python's elegant way
a, b = 10, 20
a, b = b, a      # Swap!
print(a, b)      # 20 10

# Augmented assignment operators
count = 0
count += 1   # Same as: count = count + 1  →  1
count *= 3   # Same as: count = count * 3  →  3
count -= 1   # Same as: count = count - 1  →  2
count //= 2  # Same as: count = count // 2 →  1
```

### Checking Types

```python
age = 25
name = "Alice"
values = [1, 2, 3]

# Check exact type
print(type(age))           # <class 'int'>
print(type(name))          # <class 'str'>
print(type(values))        # <class 'list'>

# Check if a variable is a certain type
print(isinstance(age, int))        # True
print(isinstance(age, (int, float)))  # True — checks against multiple types
print(isinstance(name, str))       # True
print(isinstance(age, str))        # False
```

---

## 1.6 Basic Input and Output

### The `print()` Function (Output)

`print()` displays values to the standard output (usually your terminal). It's the most fundamental way to communicate results from your program to the user.

```python
# ── Basic printing ──────────────────────────────────────────────────────
print("Hello!")                    # Hello!
print(42)                          # 42
print(3.14)                        # 3.14
print(True)                        # True
print(None)                        # None

# ── Multiple arguments ──────────────────────────────────────────────────
# print() can take multiple comma-separated values
# By default it adds a space between them
print("Name:", "Alice", "Age:", 25)
# Output: Name: Alice Age: 25

# ── Custom separator (sep) ──────────────────────────────────────────────
print("2024", "06", "15", sep="-")     # 2024-06-15
print("a", "b", "c", sep=" | ")       # a | b | c
print("one", "two", "three", sep="")  # onetwothree

# ── Custom ending (end) ─────────────────────────────────────────────────
# Default end is '\n' (newline). You can change it.
print("Loading", end="")
print("...", end="")
print(" Done!")
# Output: Loading... Done!   (all on one line)

# ── f-strings: The Modern Way to Format Output ──────────────────────────
name = "Alice"
age = 30
score = 95.678

# Embed variables directly in strings with {}
print(f"My name is {name} and I am {age} years old.")
# Output: My name is Alice and I am 30 years old.

# Expressions inside {} are evaluated
print(f"5 + 3 = {5 + 3}")
# Output: 5 + 3 = 8

# Format numbers
print(f"Score: {score:.2f}")        # 2 decimal places → Score: 95.68
print(f"Big: {1000000:,}")          # Thousands separator → 1,000,000
print(f"Percent: {0.856:.1%}")      # Percentage → 85.6%
print(f"Hex: {255:#x}")             # Hexadecimal → 0xff

# ── Printing special characters ─────────────────────────────────────────
print("Tab:\there")          # Tab space
print("Newline:\nhere")      # New line
print("Quote: \"hello\"")    # Escaped double quote
print("Backslash: \\")       # Literal backslash
print(r"Raw: \n not newline") # Raw string — backslashes are literal
```

### The `input()` Function (User Input)

`input()` pauses the program and waits for the user to type something and press Enter. It **always returns a string**, so you must convert it if you need a number.

```python
# ── Basic input ─────────────────────────────────────────────────────────
name = input("What is your name? ")   # User types: Alice
print(f"Hello, {name}!")              # Hello, Alice!

# ── Input is ALWAYS a string — convert when needed ──────────────────────
age_str = input("How old are you? ")  # User types: 25
print(type(age_str))                   # <class 'str'>  ← still a string!

age = int(age_str)                     # Convert to integer
print(f"Next year you'll be {age + 1}")  # Works now!

# ── One-liner conversion ─────────────────────────────────────────────────
age = int(input("Enter your age: "))
price = float(input("Enter price: "))

# ── Safe input with error handling ──────────────────────────────────────
try:
    number = int(input("Enter a number: "))
    print(f"You entered: {number}")
except ValueError:
    print("That's not a valid number!")

# ── Reading multiple values on one line ─────────────────────────────────
# User types: 10 20 30
values = input("Enter three numbers: ").split()
a, b, c = int(values[0]), int(values[1]), int(values[2])
print(f"Sum = {a + b + c}")

# Or more elegantly:
a, b, c = map(int, input("Enter three numbers: ").split())
print(f"Sum = {a + b + c}")
```

---

## 1.7 Basic Operators

Operators are special symbols that perform operations on values (called **operands**). Python has several categories of operators.

### Arithmetic Operators

Used for mathematical calculations:

```python
a = 17
b = 5

# Addition (+): adds two numbers
print(a + b)    # 22

# Subtraction (-): subtracts right from left
print(a - b)    # 12

# Multiplication (*): multiplies two numbers
print(a * b)    # 85

# Division (/): always returns a FLOAT
print(a / b)    # 3.4   ← notice: float, not int!
print(10 / 2)   # 5.0   ← even if divisible evenly, still float

# Floor Division (//): integer division, rounds DOWN
print(a // b)   # 3     ← drops the decimal (floors toward negative infinity)
print(-7 // 2)  # -4    ← floors down, not toward zero!

# Modulus (%): remainder after division
print(a % b)    # 2     ← 17 = 3×5 + 2, remainder is 2
print(10 % 3)   # 1
# Great for: checking if a number is even/odd: n % 2 == 0 means even

# Exponentiation (**): power/raised-to
print(a ** 2)   # 289   ← 17²
print(2 ** 10)  # 1024
print(27 ** (1/3))  # 3.0  ← cube root

# Practical example: Calculate BMI
weight_kg = 70
height_m = 1.75
bmi = weight_kg / (height_m ** 2)
print(f"BMI: {bmi:.1f}")  # BMI: 22.9
```

### Comparison (Relational) Operators

Compare two values and **always return True or False**:

```python
x = 10
y = 20

print(x == y)   # False — Equal to? No, 10 ≠ 20
print(x != y)   # True  — Not equal to? Yes, they differ
print(x > y)    # False — Greater than? No, 10 < 20
print(x < y)    # True  — Less than? Yes, 10 < 20
print(x >= 10)  # True  — Greater than or equal to? Yes, 10 == 10
print(x <= 5)   # False — Less than or equal to? No, 10 > 5

# ⚠️ Common mistake: = vs ==
# x = 5   means ASSIGN value 5 to x
# x == 5  means CHECK if x is equal to 5

# Chained comparisons (Python-specific, very readable!)
age = 25
print(18 <= age <= 65)    # True — between 18 and 65
print(0 < x < y < 100)   # True — chain of comparisons

# Comparing strings (lexicographic/alphabetical order)
print("apple" < "banana")  # True  — 'a' comes before 'b'
print("abc" == "abc")      # True
print("A" < "a")           # True  — uppercase letters have lower Unicode values
```

### Logical Operators

Combine multiple Boolean expressions:

```python
# AND: both conditions must be True
print(True and True)   # True
print(True and False)  # False
print(False and True)  # False
print(False and False) # False

# OR: at least one condition must be True
print(True or True)    # True
print(True or False)   # True
print(False or True)   # True
print(False or False)  # False

# NOT: inverts the Boolean value
print(not True)        # False
print(not False)       # True

# ── Practical examples ───────────────────────────────────────────────────
age = 20
has_ticket = True
is_vip = False

# Can enter the event?
can_enter = age >= 18 and has_ticket
print(f"Can enter: {can_enter}")      # True

# Gets free drink?
free_drink = is_vip or age >= 21
print(f"Free drink: {free_drink}")    # False

# Is a minor?
is_minor = not (age >= 18)
print(f"Is minor: {is_minor}")        # False

# ── Short-circuit evaluation ─────────────────────────────────────────────
# Python stops evaluating as soon as the result is certain
# With 'and': if first is False, second is never checked
# With 'or': if first is True, second is never checked
x = 0
result = x != 0 and (10 / x > 1)  # Safe! Division never runs
print(result)   # False (x != 0 is False, so stops there)
```

### Assignment Operators

```python
x = 10          # Basic assignment

x += 5          # x = x + 5  → 15
x -= 3          # x = x - 3  → 12
x *= 2          # x = x * 2  → 24
x /= 4          # x = x / 4  → 6.0  (becomes float)
x //= 2         # x = x // 2 → 3.0  (floor division)
x **= 3         # x = x ** 3 → 27.0 (exponentiation)
x %= 5          # x = x % 5  → 2.0  (modulus)

# Walrus operator := (Python 3.8+) — assign AND use in one expression
# Very useful in while loops and comprehensions
import random
while (n := random.randint(1, 10)) != 7:
    print(f"Got {n}, not 7 yet...")
print(f"Finally got 7!")
```

### Bitwise Operators (Brief Overview)

```python
# Work on individual bits of integers
a = 0b1010  # 10 in binary
b = 0b1100  # 12 in binary

print(a & b)   # 8  — AND: 0b1000
print(a | b)   # 14 — OR:  0b1110
print(a ^ b)   # 6  — XOR: 0b0110
print(~a)      # -11 — NOT (inverts all bits)
print(a << 1)  # 20 — Left shift by 1 (multiply by 2)
print(a >> 1)  # 5  — Right shift by 1 (divide by 2)
```

---

## 1.8 Strings in Detail

Strings are one of the most important data types in Python. A **string** is an ordered, immutable sequence of Unicode characters. You can store any text — letters, numbers, symbols, emojis — in a string.

### Creating Strings

```python
# Single quotes
s1 = 'Hello, World!'

# Double quotes (no difference — use whichever is convenient)
s2 = "Hello, World!"

# Triple quotes — allows multi-line strings and embedded quotes
s3 = """This is a
multi-line string.
It can span as many lines as you want."""

s4 = '''Another
multi-line option'''

# Embedding quotes inside strings
s5 = "He said, \"Hello!\""   # Escape with backslash
s6 = 'She said, "Hello!"'    # Use opposite quote type (easier)
s7 = "It's a beautiful day"  # Single quote inside double quotes — fine

# Raw strings — backslashes are treated as literals
path = r"C:\Users\Alice\Documents"   # Without r, \U and \A are escape sequences!
regex = r"\d+\.\d+"                  # Common in regex patterns

# Unicode strings
greeting = "नमस्ते"   # Hindi — Python natively supports Unicode
emoji_str = "I ❤️ Python 🐍"
```

### String Indexing and Slicing

Strings are **sequences** — each character has an index. Python uses **zero-based indexing** (first character is at index 0).

```python
word = "Python"
#       P y t h o n
# Index: 0 1 2 3 4 5
# Neg:  -6-5-4-3-2-1

# Indexing — access a single character
print(word[0])     # 'P'  (first character)
print(word[3])     # 'h'  (4th character)
print(word[-1])    # 'n'  (last character — negative indexing counts from end)
print(word[-2])    # 'o'  (second-to-last)

# Slicing — extract a substring: string[start:stop:step]
# start is inclusive, stop is exclusive
print(word[0:3])   # 'Pyt'  — chars at index 0, 1, 2
print(word[2:5])   # 'tho'  — chars at index 2, 3, 4
print(word[:3])    # 'Pyt'  — from start to index 3 (exclusive)
print(word[3:])    # 'hon'  — from index 3 to end
print(word[:])     # 'Python' — full copy
print(word[::2])   # 'Pto'  — every 2nd character
print(word[::-1])  # 'nohtyP' — reversed! (step=-1 goes backward)

# ⚠️ Strings are IMMUTABLE — you cannot change individual characters!
# word[0] = 'p'   # ❌ TypeError: 'str' object does not support item assignment
# Instead, create a new string:
new_word = 'p' + word[1:]   # 'python'
```

### Essential String Methods

Python strings have dozens of built-in methods. Here are the most important ones:

```python
text = "  Hello, World! Python is amazing.  "

# ── Case methods ─────────────────────────────────────────────────────────
print(text.upper())          # "  HELLO, WORLD! PYTHON IS AMAZING.  "
print(text.lower())          # "  hello, world! python is amazing.  "
print(text.title())          # "  Hello, World! Python Is Amazing.  "
print(text.capitalize())     # "  hello..." (only first char of whole string)
print(text.swapcase())       # "  hELLO, wORLD! pYTHON IS AMAZING.  "

# ── Whitespace methods ───────────────────────────────────────────────────
print(text.strip())          # "Hello, World! Python is amazing."  (both sides)
print(text.lstrip())         # "Hello, World! Python is amazing.  " (left only)
print(text.rstrip())         # "  Hello, World! Python is amazing." (right only)

# ── Search methods ───────────────────────────────────────────────────────
clean = text.strip()
print(clean.find("Python"))      # 14 (index of first match, -1 if not found)
print(clean.rfind("o"))          # 26 (last occurrence)
print(clean.index("World"))      # 7  (like find but raises ValueError if not found)
print(clean.count("is"))         # 1  (how many times it appears)
print(clean.startswith("Hello")) # True
print(clean.endswith("ing."))    # True
print("Python" in clean)         # True  (membership test)

# ── Modification methods ─────────────────────────────────────────────────
print(clean.replace("Python", "Java"))        # Replaces all occurrences
print(clean.replace("is", "IS", 1))           # Replace only first occurrence
print("  spaces  ".strip().replace(" ", "_")) # "spaces"

# ── Split and Join ───────────────────────────────────────────────────────
sentence = "apple,banana,cherry,date"
fruits = sentence.split(",")
print(fruits)    # ['apple', 'banana', 'cherry', 'date']

words = "the cat sat on the mat".split()  # Splits on whitespace by default
print(words)     # ['the', 'cat', 'sat', 'on', 'the', 'mat']

# Split with max splits
parts = "one:two:three:four".split(":", 2)
print(parts)     # ['one', 'two', 'three:four']

# Join — inverse of split: takes a list and joins into a string
fruits_str = ", ".join(fruits)
print(fruits_str)  # "apple, banana, cherry, date"

path_parts = ["Users", "Alice", "Documents", "file.txt"]
path = "/".join(path_parts)
print(path)      # "Users/Alice/Documents/file.txt"

# ── Validation methods ───────────────────────────────────────────────────
print("12345".isdigit())      # True — all characters are digits
print("abc".isalpha())        # True — all characters are letters
print("abc123".isalnum())     # True — all characters are letters or digits
print("   ".isspace())        # True — all whitespace
print("Hello World".istitle())# True — title case
print("HELLO".isupper())      # True
print("hello".islower())      # True

# ── Padding and alignment ────────────────────────────────────────────────
print("hello".center(11))          # "   hello   "
print("hello".ljust(10, '-'))      # "hello-----"
print("hello".rjust(10, '0'))      # "00000hello"
print("42".zfill(5))               # "00042"  (zero-pad numbers)
```

### String Formatting (3 Methods)

```python
name = "Alice"
age = 30
score = 98.765

# ── Method 1: f-strings (Python 3.6+) — RECOMMENDED ─────────────────────
# Embed expressions directly in string with {expression}
print(f"Name: {name}, Age: {age}, Score: {score:.1f}")
# Output: Name: Alice, Age: 30, Score: 98.8

# Advanced formatting specifiers
pi = 3.14159265
print(f"PI = {pi:.4f}")           # 4 decimal places: 3.1416
print(f"PI = {pi:10.4f}")         # Right-aligned in 10 chars: "    3.1416"
print(f"PI = {pi:<10.4f}")        # Left-aligned: "3.1416    "
print(f"PI = {pi:^10.4f}")        # Centered: "  3.1416  "
print(f"{1000000:,}")              # Thousands commas: 1,000,000
print(f"{0.85:.1%}")              # Percentage: 85.0%
print(f"{255:#010x}")             # Hex with prefix: 0x000000ff
print(f"{'hello':!^15}")          # Centered with ! fill: "!!!!!hello!!!!!"

# Expressions in f-strings
print(f"2 to the power 10 = {2**10}")   # 1024
print(f"Name reversed: {name[::-1]}")   # ecilA
print(f"Uppercase: {name.upper()}")      # ALICE

# ── Method 2: .format() method ───────────────────────────────────────────
print("Name: {}, Age: {}".format(name, age))
print("Name: {0}, repeated {0}".format(name))    # reuse by index
print("Name: {n}, Age: {a}".format(n=name, a=age))  # by keyword

# ── Method 3: % operator (old-style) ─────────────────────────────────────
print("Name: %s, Age: %d, Score: %.1f" % (name, age, score))
# %s = string, %d = integer, %f = float, %r = repr()
# Note: this style is discouraged in modern Python
```

---

## 1.9 Type Conversion (Casting)

Python is **strongly typed** — you can't accidentally mix types like adding a number to a string. When you need to convert between types, you do it **explicitly** using built-in conversion functions.

Think of casting like currency conversion: the value changes form but represents the same concept.

```python
# ── str() — Convert anything to a string ───────────────────────────────
age = 25
age_str = str(age)              # "25"
pi_str = str(3.14159)           # "3.14159"
bool_str = str(True)            # "True"
none_str = str(None)            # "None"

# Why useful? You can't concatenate a string with a number directly:
# "Age: " + 25   ← ❌ TypeError
# "Age: " + str(25)   ← ✅ Works!
print("Age: " + str(25))        # "Age: 25"


# ── int() — Convert to integer ───────────────────────────────────────────
print(int("42"))         # 42    — string of digits to integer
print(int("0"))          # 0
print(int(3.9))          # 3     ← TRUNCATES (not rounds!) toward zero
print(int(-3.9))         # -3    ← also truncates toward zero (not -4)
print(int(True))         # 1
print(int(False))        # 0
print(int("101", 2))     # 5     — convert binary "101" to decimal
print(int("FF", 16))     # 255   — convert hex to decimal
print(int("17", 8))      # 15    — convert octal to decimal

# ⚠️ int() fails if the string isn't a clean integer:
# int("3.14")   ← ❌ ValueError — has a decimal point
# int("hello")  ← ❌ ValueError — not a number
# int("")       ← ❌ ValueError — empty string


# ── float() — Convert to floating-point ─────────────────────────────────
print(float("3.14"))     # 3.14   — string to float
print(float("3"))        # 3.0    — int-like string to float
print(float(5))          # 5.0    — integer to float
print(float(True))       # 1.0
print(float("inf"))      # inf    — positive infinity!
print(float("-inf"))     # -inf   — negative infinity
print(float("nan"))      # nan    — Not a Number


# ── bool() — Convert to boolean ─────────────────────────────────────────
# Everything in Python has a "truthiness". These are FALSY (evaluate to False):
print(bool(0))           # False — zero integer
print(bool(0.0))         # False — zero float
print(bool(""))          # False — empty string
print(bool([]))          # False — empty list
print(bool({}))          # False — empty dict
print(bool(()))          # False — empty tuple
print(bool(set()))       # False — empty set
print(bool(None))        # False — None

# Everything else is TRUTHY (evaluates to True):
print(bool(1))           # True — any non-zero number
print(bool(-5))          # True — negative numbers too!
print(bool("hello"))     # True — any non-empty string
print(bool([0]))         # True — list with one element (even if element is 0)
print(bool(0.001))       # True — any non-zero float


# ── list(), tuple(), set() — Collection conversions ──────────────────────
# Convert between collection types
string = "hello"
print(list(string))       # ['h', 'e', 'l', 'l', 'o']

lst = [1, 2, 2, 3, 3, 4]
print(set(lst))           # {1, 2, 3, 4}  — removes duplicates!
print(tuple(lst))         # (1, 2, 2, 3, 3, 4)

my_set = {3, 1, 4, 1, 5}
print(sorted(my_set))     # [1, 3, 4, 5]  — sorted list from set


# ── Safe conversion with error handling ─────────────────────────────────
def safe_int(value):
    """Try to convert to int, return None if it fails."""
    try:
        return int(value)
    except (ValueError, TypeError):
        return None

print(safe_int("42"))      # 42
print(safe_int("hello"))   # None  (no crash!)
print(safe_int(None))      # None
print(safe_int(3.7))       # 3
```

---

# Level 2 — Elementary (Building Blocks)

## 2.1 Conditional Statements (if / elif / else)

**Conditional statements** allow your program to make decisions — to execute different blocks of code based on whether certain conditions are true or false. This is what makes programs "smart" — they can respond differently to different inputs.

Think of it like real-life decisions:
```
IF it's raining → take an umbrella
ELSE IF it's sunny → wear sunglasses
ELSE → just go as-is
```

### Basic if / elif / else

```python
# Syntax:
# if condition:
#     code runs if condition is True
# elif another_condition:
#     code runs if previous conditions were False and this is True
# else:
#     code runs if ALL above conditions were False

age = 18

if age < 13:
    print("Child")
elif age < 18:
    print("Teenager")
elif age == 18:
    print("Just became an adult!")
else:
    print("Adult")
# Output: Just became an adult!

# ── IMPORTANT: Indentation is mandatory! ───────────────────────────────
# Python uses indentation (4 spaces or 1 tab) to define code blocks.
# Without proper indentation, you get an IndentationError.

# ✅ Correct:
if True:
    print("This is inside the if block")
    print("So is this")
print("This is OUTSIDE the if block")

# ── Real-world example: Grade Calculator ───────────────────────────────
score = int(input("Enter your test score (0-100): "))

if score >= 90:
    grade = "A"
    feedback = "Excellent!"
elif score >= 80:
    grade = "B"
    feedback = "Good job!"
elif score >= 70:
    grade = "C"
    feedback = "Average. Keep studying."
elif score >= 60:
    grade = "D"
    feedback = "Below average. Need improvement."
else:
    grade = "F"
    feedback = "Failed. Please retake."

print(f"Score: {score} → Grade: {grade} — {feedback}")
```

### Ternary Expression (Conditional Expression)

A compact one-liner for simple if-else assignments:

```python
# Syntax: value_if_true if condition else value_if_false

age = 20
status = "Adult" if age >= 18 else "Minor"
print(status)   # "Adult"

# Equivalent to:
# if age >= 18:
#     status = "Adult"
# else:
#     status = "Minor"

# More examples
x = 5
print("Positive" if x > 0 else "Non-positive")

num = 7
parity = "even" if num % 2 == 0 else "odd"
print(f"{num} is {parity}")   # "7 is odd"

# Nested ternary (use sparingly — reduces readability)
score = 75
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"
print(grade)  # "C"
```

### Nested Conditions

```python
# Conditions can be nested inside other conditions
username = "admin"
password = "secret123"
is_active = True

if username == "admin":
    if password == "secret123":
        if is_active:
            print("Login successful! Welcome, admin.")
        else:
            print("Account is deactivated.")
    else:
        print("Wrong password.")
else:
    print("Username not found.")

# Tip: Deep nesting (>3 levels) hurts readability.
# Consider using 'and' to flatten:
if username == "admin" and password == "secret123" and is_active:
    print("Login successful!")
```

### Match Statement (Python 3.10+ — Pattern Matching)

Python 3.10 introduced `match` — similar to switch/case in other languages but much more powerful:

```python
# Basic match
command = "start"

match command:
    case "start":
        print("Starting the engine...")
    case "stop":
        print("Stopping the engine...")
    case "pause":
        print("Pausing...")
    case _:           # Default case (like 'else')
        print("Unknown command")

# Match with multiple patterns
status_code = 404

match status_code:
    case 200:
        print("OK — Success!")
    case 301 | 302:   # OR patterns
        print("Redirect")
    case 400:
        print("Bad Request")
    case 404:
        print("Not Found")
    case 500:
        print("Internal Server Error")
    case _:
        print(f"Unknown status: {status_code}")

# Match with conditions (guards)
point = (3, 4)

match point:
    case (0, 0):
        print("Origin")
    case (x, 0):
        print(f"On X-axis at {x}")
    case (0, y):
        print(f"On Y-axis at {y}")
    case (x, y) if x == y:
        print(f"On diagonal at {x}")
    case (x, y):
        print(f"Point at ({x}, {y})")
# Output: Point at (3, 4)
```

---

## 2.2 Loops

**Loops** allow you to execute a block of code repeatedly — either a fixed number of times, or until a condition changes. They're fundamental to automation: imagine copying a task 1000 times manually vs. letting a loop do it!

### The `for` Loop

A `for` loop iterates over a **sequence** (list, string, range, etc.) and executes the body once for each item:

```python
# ── Loop over a range ──────────────────────────────────────────────────
# range(stop)         → 0, 1, 2, ..., stop-1
# range(start, stop)  → start, start+1, ..., stop-1
# range(start, stop, step) → with custom step

for i in range(5):
    print(i)   # 0, 1, 2, 3, 4

for i in range(1, 6):
    print(i)   # 1, 2, 3, 4, 5

for i in range(0, 20, 4):
    print(i)   # 0, 4, 8, 12, 16

for i in range(10, 0, -1):
    print(i)   # 10, 9, 8, ..., 1   (countdown!)

# ── Loop over a list ───────────────────────────────────────────────────
fruits = ["apple", "banana", "cherry", "mango"]
for fruit in fruits:
    print(f"I like {fruit}")

# ── Loop with index using enumerate() ─────────────────────────────────
# enumerate() gives you both the index and the value
for index, fruit in enumerate(fruits):
    print(f"{index + 1}. {fruit}")
# 1. apple
# 2. banana
# 3. cherry
# 4. mango

# Start enumerate from a different number
for num, fruit in enumerate(fruits, start=10):
    print(f"{num}: {fruit}")
# 10: apple, 11: banana, etc.

# ── Loop over a string ─────────────────────────────────────────────────
# Strings are sequences of characters
for char in "Python":
    print(char, end=" ")   # P y t h o n

# ── Loop over a dictionary ────────────────────────────────────────────
person = {"name": "Alice", "age": 30, "city": "Mumbai"}

for key in person:                    # Iterates over keys by default
    print(key)

for value in person.values():         # Iterate over values
    print(value)

for key, value in person.items():     # Iterate over key-value pairs
    print(f"{key}: {value}")

# ── zip() — Loop over multiple sequences simultaneously ──────────────
names = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]
grades = ["B", "A", "C"]

for name, score, grade in zip(names, scores, grades):
    print(f"{name}: {score} ({grade})")
# Alice: 85 (B)
# Bob: 92 (A)
# Charlie: 78 (C)
```

### The `while` Loop

A `while` loop keeps executing as long as its condition remains True. Use it when you don't know ahead of time how many iterations are needed:

```python
# ── Basic while ────────────────────────────────────────────────────────
count = 1
while count <= 5:
    print(f"Count: {count}")
    count += 1   # ⚠️ ALWAYS update the condition variable — or you get infinite loop!
# Count: 1, Count: 2, Count: 3, Count: 4, Count: 5

# ── do-while equivalent (Python doesn't have do-while) ───────────────
# Use while True + break to simulate
while True:
    answer = input("Continue? (yes/no): ")
    if answer.lower() == "no":
        break
    print("Continuing...")

# ── Real example: Number guessing game ────────────────────────────────
import random
secret = random.randint(1, 100)
attempts = 0
MAX_ATTEMPTS = 7

while attempts < MAX_ATTEMPTS:
    guess = int(input(f"Guess (attempt {attempts + 1}/{MAX_ATTEMPTS}): "))
    attempts += 1

    if guess == secret:
        print(f"🎉 Correct! You got it in {attempts} attempts!")
        break
    elif guess < secret:
        print("Too low!")
    else:
        print("Too high!")
else:
    # 'else' on while runs if loop ended without 'break'
    print(f"Out of attempts! The number was {secret}")
```

### `break`, `continue`, and `pass`

```python
# ── break — exit the loop immediately ──────────────────────────────────
print("Finding first multiple of 7 over 20:")
for n in range(21, 100):
    if n % 7 == 0:
        print(f"Found: {n}")
        break   # Stop as soon as we find it

# ── continue — skip rest of current iteration, go to next ──────────────
print("\nOdd numbers between 1 and 10:")
for i in range(1, 11):
    if i % 2 == 0:
        continue   # Skip even numbers
    print(i, end=" ")   # 1 3 5 7 9

# ── pass — do nothing (placeholder) ────────────────────────────────────
# Useful when you need a code block syntactically but don't want any action
for i in range(5):
    if i == 3:
        pass   # TODO: handle this case later
    else:
        print(i)

# Also useful for empty functions/classes during development:
def future_function():
    pass   # Will implement later

class EmptyClass:
    pass

# ── for...else / while...else ─────────────────────────────────────────
# The else clause on a loop runs only if the loop completed WITHOUT a break
# This is unique to Python — very useful for search patterns!

# Example: Check if a number is prime
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            print(f"{n} is divisible by {i}")
            break     # Found a factor — not prime
    else:
        return True   # No factor found — is prime
    return False

print(is_prime(17))   # True
print(is_prime(15))   # False (15 is divisible by 3)
```

### Nested Loops

```python
# A loop inside a loop — the inner loop completes fully for each outer iteration

# ── Multiplication table ───────────────────────────────────────────────
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i*j:4}", end="")   # :4 means width of 4 chars (right-aligned)
    print()  # New line after each row

# Output:
#    1   2   3   4   5
#    2   4   6   8  10
#    3   6   9  12  15
#    4   8  12  16  20
#    5  10  15  20  25

# ── Pattern printing ───────────────────────────────────────────────────
# Right triangle
for row in range(1, 6):
    for col in range(row):
        print("*", end="")
    print()
# *
# **
# ***
# ****
# *****

# Pyramid
n = 5
for row in range(1, n + 1):
    print(" " * (n - row) + "* " * row)
#     *
#    * *
#   * * *
#  * * * *
# * * * * *
```

---

## 2.3 Lists

A **list** is Python's most versatile and commonly used data structure. It is an **ordered, mutable** (changeable) collection of items. Lists can contain items of any type — including other lists — and items can be repeated.

Think of a list like a numbered shopping list where you can add, remove, and change items.

```python
# ── Creating lists ──────────────────────────────────────────────────────
empty_list = []                        # Empty list
numbers = [1, 2, 3, 4, 5]            # List of integers
fruits = ["apple", "banana", "cherry"] # List of strings
mixed = [1, "hello", 3.14, True, None, [1, 2]]  # Mixed types, even nested list!
from_range = list(range(1, 11))        # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
from_string = list("Python")           # ['P', 'y', 't', 'h', 'o', 'n']

# ── Accessing elements ──────────────────────────────────────────────────
fruits = ["apple", "banana", "cherry", "date", "elderberry"]
# Index:    0         1          2        3          4
# Neg idx: -5        -4         -3       -2         -1

print(fruits[0])     # "apple"    — first element
print(fruits[-1])    # "elderberry" — last element
print(fruits[2])     # "cherry"
print(fruits[-2])    # "date"

# Slicing: list[start:stop:step]
print(fruits[1:3])   # ['banana', 'cherry']
print(fruits[:3])    # ['apple', 'banana', 'cherry'] — first 3
print(fruits[2:])    # ['cherry', 'date', 'elderberry'] — from index 2 onward
print(fruits[::2])   # ['apple', 'cherry', 'elderberry'] — every 2nd item
print(fruits[::-1])  # Reversed list

# ── Modifying lists ─────────────────────────────────────────────────────
# Lists are MUTABLE — unlike strings or tuples
colors = ["red", "green", "blue"]

colors[1] = "yellow"         # Change element at index 1
print(colors)                # ['red', 'yellow', 'blue']

colors[1:3] = ["purple", "orange", "pink"]  # Replace a slice
print(colors)                # ['red', 'purple', 'orange', 'pink']

# ── Adding elements ─────────────────────────────────────────────────────
nums = [1, 2, 3]
nums.append(4)               # Add single item to END: [1, 2, 3, 4]
nums.insert(1, 99)           # Insert 99 at index 1: [1, 99, 2, 3, 4]
nums.extend([5, 6, 7])       # Add multiple items to END: [1, 99, 2, 3, 4, 5, 6, 7]
nums += [8, 9]               # Same as extend: [1, 99, 2, 3, 4, 5, 6, 7, 8, 9]

# ── Removing elements ───────────────────────────────────────────────────
nums = [1, 2, 3, 2, 4, 2]
nums.remove(2)               # Remove FIRST occurrence of value 2: [1, 3, 2, 4, 2]
last = nums.pop()            # Remove and RETURN last element: last=2, nums=[1,3,2,4]
second = nums.pop(1)         # Remove and RETURN element at index 1: second=3
del nums[0]                  # Delete element at index 0 (no return)
del nums[1:3]                # Delete a slice
nums.clear()                 # Remove ALL elements → []

# ── Searching ───────────────────────────────────────────────────────────
fruits = ["apple", "banana", "apple", "cherry"]
print("apple" in fruits)       # True  — membership test
print("mango" not in fruits)   # True
print(fruits.count("apple"))   # 2     — how many times
print(fruits.index("banana"))  # 1     — index of FIRST occurrence
# print(fruits.index("mango")) # ❌ ValueError if not found

# Safe search:
try:
    idx = fruits.index("mango")
except ValueError:
    idx = -1
print(idx)  # -1

# ── Sorting ─────────────────────────────────────────────────────────────
nums = [3, 1, 4, 1, 5, 9, 2, 6, 5]
nums.sort()                   # In-place sort (modifies original): ascending
print(nums)                   # [1, 1, 2, 3, 4, 5, 5, 6, 9]

nums.sort(reverse=True)       # In-place sort: descending
print(nums)                   # [9, 6, 5, 5, 4, 3, 2, 1, 1]

words = ["banana", "apple", "Cherry", "date"]
words.sort()                  # ['Cherry', 'apple', 'banana', 'date'] — case-sensitive!
words.sort(key=str.lower)     # ['apple', 'banana', 'Cherry', 'date'] — case-insensitive

# sorted() returns a NEW sorted list (original unchanged)
original = [3, 1, 4, 1, 5]
new_sorted = sorted(original)
print(original)    # [3, 1, 4, 1, 5]   ← unchanged!
print(new_sorted)  # [1, 1, 3, 4, 5]   ← new list

# Sort by custom key
students = [("Alice", 85), ("Bob", 92), ("Charlie", 78)]
students.sort(key=lambda s: s[1])  # Sort by score
print(students)  # [('Charlie', 78), ('Alice', 85), ('Bob', 92)]

# ── Copying lists ───────────────────────────────────────────────────────
# ⚠️ Be careful! Assignment doesn't copy:
a = [1, 2, 3]
b = a           # b points to SAME list!
b.append(4)
print(a)        # [1, 2, 3, 4]  ← a changed too!

# Make a real copy:
c = a.copy()     # Method 1: .copy()
d = a[:]         # Method 2: slice
e = list(a)      # Method 3: list() constructor
import copy
f = copy.deepcopy(a)  # For nested lists: deep copy

# ── Other useful operations ─────────────────────────────────────────────
nums = [1, 2, 3, 4, 5]
print(len(nums))     # 5      — length
print(sum(nums))     # 15     — sum
print(min(nums))     # 1      — minimum
print(max(nums))     # 5      — maximum
nums.reverse()       # Reverse in-place: [5, 4, 3, 2, 1]

# Concatenation and repetition
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined = list1 + list2   # [1, 2, 3, 4, 5, 6]
repeated = list1 * 3       # [1, 2, 3, 1, 2, 3, 1, 2, 3]

# Unpacking
first, *middle, last = [1, 2, 3, 4, 5]
print(first, middle, last)  # 1 [2, 3, 4] 5
```

### List Comprehensions

List comprehensions are a concise, Pythonic way to create lists. They're faster than equivalent for loops and considered more readable by experienced Python developers.

```python
# Syntax: [expression for item in iterable if condition]

# ── Basic: build a list of squares ─────────────────────────────────────
# Traditional way:
squares = []
for x in range(10):
    squares.append(x**2)

# List comprehension way (same result, one line):
squares = [x**2 for x in range(10)]
print(squares)  # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# ── With condition (filter) ─────────────────────────────────────────────
evens = [x for x in range(20) if x % 2 == 0]
print(evens)    # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

# Squares of even numbers only
even_squares = [x**2 for x in range(15) if x % 2 == 0]
print(even_squares)  # [0, 4, 16, 36, 64, 100, 144, 196]

# ── With if-else (transform) ────────────────────────────────────────────
labels = ["even" if x % 2 == 0 else "odd" for x in range(6)]
print(labels)   # ['even', 'odd', 'even', 'odd', 'even', 'odd']

# Replace negatives with 0 (ReLU activation in ML)
data = [-3, -1, 0, 2, 5, -4, 8]
relu = [x if x > 0 else 0 for x in data]
print(relu)     # [0, 0, 0, 2, 5, 0, 8]

# ── Nested list comprehension ───────────────────────────────────────────
# Flatten a 2D matrix to 1D
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat = [num for row in matrix for num in row]
print(flat)     # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Transpose a matrix
transposed = [[row[i] for row in matrix] for i in range(3)]
print(transposed)   # [[1, 4, 7], [2, 5, 8], [3, 6, 9]]

# ── Real-world examples ─────────────────────────────────────────────────
# Get all .py files from a directory listing
files = ["main.py", "utils.py", "README.md", "data.csv", "app.py"]
python_files = [f for f in files if f.endswith(".py")]
print(python_files)   # ['main.py', 'utils.py', 'app.py']

# Extract words with more than 4 characters
sentence = "the quick brown fox jumps over the lazy dog"
long_words = [w for w in sentence.split() if len(w) > 4]
print(long_words)     # ['quick', 'brown', 'jumps']

# Parse CSV line into list of values
csv_line = "Alice,30,Mumbai,Engineer"
parsed = [field.strip() for field in csv_line.split(",")]
print(parsed)         # ['Alice', '30', 'Mumbai', 'Engineer']
```

---

## 2.4 Tuples

A **tuple** is an ordered, **immutable** (unchangeable) collection. Once created, you cannot modify it — no adding, removing, or changing elements. This immutability makes tuples:

- **Faster** than lists (less overhead)
- **Safer** — data won't be accidentally modified
- **Hashable** — can be used as dictionary keys or set elements
- The right choice for data that shouldn't change (coordinates, RGB colors, database records)

```python
# ── Creating tuples ─────────────────────────────────────────────────────
empty = ()
single = (42,)            # ⚠️ Note the trailing comma! (42) is just int 42
point = (10, 20)
rgb = (255, 128, 0)
person = ("Alice", 30, "Mumbai")
mixed = (1, "hello", 3.14, [1, 2])  # Can contain any type
no_parens = 1, 2, 3                  # Parentheses optional (tuple packing)

# ⚠️ Common mistake:
wrong = (42)       # This is just int 42, NOT a tuple!
right = (42,)      # This is a tuple with one element
print(type(wrong))  # <class 'int'>
print(type(right))  # <class 'tuple'>

# ── Accessing (same as lists) ────────────────────────────────────────────
colors = ("red", "green", "blue", "yellow")
print(colors[0])     # "red"
print(colors[-1])    # "yellow"
print(colors[1:3])   # ('green', 'blue')

# ── Immutability ────────────────────────────────────────────────────────
point = (10, 20)
# point[0] = 99    # ❌ TypeError: 'tuple' object does not support item assignment

# But if a tuple contains a mutable item (like a list), that item can change:
data = (1, 2, [3, 4, 5])
data[2].append(6)    # ✅ Modifying the list INSIDE the tuple
print(data)          # (1, 2, [3, 4, 5, 6]) — tuple unchanged, but list modified

# ── Tuple unpacking ─────────────────────────────────────────────────────
# Assign tuple elements to multiple variables at once
x, y = (10, 20)
print(x, y)           # 10 20

name, age, city = ("Alice", 30, "Mumbai")
print(name, age, city)  # Alice 30 Mumbai

# Extended unpacking
first, *rest = (1, 2, 3, 4, 5)
print(first)   # 1
print(rest)    # [2, 3, 4, 5]

*start, last = (1, 2, 3, 4, 5)
print(start)   # [1, 2, 3, 4]
print(last)    # 5

first, *middle, last = (1, 2, 3, 4, 5)
print(first, middle, last)  # 1 [2, 3, 4] 5

# Swap variables (Python's elegant trick — uses tuple packing/unpacking)
a, b = 10, 20
a, b = b, a      # Behind the scenes: (a, b) = (b, a)
print(a, b)       # 20 10

# ── Tuple methods ────────────────────────────────────────────────────────
nums = (1, 2, 3, 2, 4, 2)
print(nums.count(2))    # 3  — how many times 2 appears
print(nums.index(4))    # 4  — index of first occurrence of 4

# ── Converting between tuple and list ────────────────────────────────────
my_list = [1, 2, 3]
my_tuple = tuple(my_list)    # List → Tuple (now immutable)

my_tuple2 = (4, 5, 6)
my_list2 = list(my_tuple2)   # Tuple → List (now mutable)
my_list2.append(7)            # Can now modify!

# ── Named Tuples ────────────────────────────────────────────────────────
# Regular tuples require remembering what each index means
point = (10, 20)
print(point[0])  # Is this x or y? Not obvious from context!

# Named tuples give names to positions
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
p = Point(10, 20)
print(p.x)      # 10 — much clearer!
print(p.y)      # 20
print(p)        # Point(x=10, y=20)

# Named tuples are still tuples
print(p[0])     # 10 — index access still works
print(p._asdict())  # {'x': 10, 'y': 20}

# Real-world: representing a person record
Person = namedtuple("Person", ["name", "age", "email"])
alice = Person("Alice", 30, "alice@email.com")
print(alice.name)   # Alice
print(alice.age)    # 30
```

---

## 2.5 Dictionaries

A **dictionary** (dict) stores data as **key-value pairs** — like a real dictionary where each word (key) maps to a definition (value). Dictionaries are:

- **Ordered** (Python 3.7+ maintains insertion order)
- **Mutable** — you can add, change, and remove key-value pairs
- **Keyed** — access values by key (O(1) lookup — very fast!)
- Keys must be **immutable** (strings, numbers, tuples)

Think of a dictionary like a contact list: each name (key) maps to a phone number (value).

```python
# ── Creating dictionaries ───────────────────────────────────────────────
empty = {}
person = {
    "name": "Alice",
    "age": 30,
    "city": "Mumbai",
    "is_active": True
}

# From keyword arguments
d = dict(name="Bob", age=25, city="Delhi")

# From list of tuples
pairs = [("a", 1), ("b", 2), ("c", 3)]
d2 = dict(pairs)

# ── Accessing values ────────────────────────────────────────────────────
print(person["name"])               # "Alice"  — direct access
# print(person["phone"])            # ❌ KeyError if key doesn't exist!

# .get() is safer — returns None (or a default) if key not found
print(person.get("name"))           # "Alice"
print(person.get("phone"))          # None  (no error!)
print(person.get("phone", "N/A"))   # "N/A"  (custom default)

# Check if key exists before accessing
if "email" in person:
    print(person["email"])
else:
    print("No email on file")

# ── Adding and modifying ────────────────────────────────────────────────
person["email"] = "alice@email.com"   # Add new key
person["age"] = 31                    # Modify existing key's value

# setdefault() — add only if key doesn't exist
person.setdefault("phone", "Unknown") # Adds "phone": "Unknown"
person.setdefault("name", "Newname")  # Does NOT change existing "name"

# update() — merge another dict in
extra_info = {"job": "Developer", "age": 32}   # age will overwrite
person.update(extra_info)
print(person["job"])   # "Developer"
print(person["age"])   # 32  (overwritten)

# ── Removing items ──────────────────────────────────────────────────────
del person["phone"]                   # Delete key (KeyError if not found)
age = person.pop("age")              # Remove and RETURN value
info = person.pop("missing", None)   # Safe pop with default
last = person.popitem()              # Remove and return LAST inserted (key, value) pair
person.clear()                       # Remove ALL items

# ── Iterating over dictionaries ─────────────────────────────────────────
inventory = {"apple": 50, "banana": 30, "cherry": 20}

# Iterate over keys (default)
for key in inventory:
    print(key)

# Iterate over values
for qty in inventory.values():
    print(qty)

# Iterate over key-value pairs (most common)
for fruit, qty in inventory.items():
    print(f"{fruit}: {qty} units")

# ── Useful methods ──────────────────────────────────────────────────────
print(inventory.keys())    # dict_keys(['apple', 'banana', 'cherry'])
print(inventory.values())  # dict_values([50, 30, 20])
print(inventory.items())   # dict_items([('apple', 50), ('banana', 30), ...])
print(len(inventory))      # 3

# Merge dictionaries (Python 3.9+)
base = {"color": "red", "size": "M"}
custom = {"size": "L", "weight": 1.5}
merged = base | custom      # {'color': 'red', 'size': 'L', 'weight': 1.5}
base |= custom              # In-place merge (base is updated)

# ── Dictionary comprehension ────────────────────────────────────────────
# Syntax: {key_expr: value_expr for item in iterable if condition}

# Squares dictionary
squares = {x: x**2 for x in range(8)}
# {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49}

# Invert a dictionary (swap keys and values)
grades = {"Alice": "A", "Bob": "B", "Charlie": "A"}
inverted = {v: k for k, v in grades.items()}
# {'A': 'Charlie', 'B': 'Bob'}  — Note: only last duplicate key survives

# Filter: keep only items where value > some threshold
prices = {"apple": 1.5, "truffle": 200, "banana": 0.75, "saffron": 150}
expensive = {item: price for item, price in prices.items() if price > 10}
print(expensive)  # {'truffle': 200, 'saffron': 150}

# Normalize: convert all string values to uppercase
data = {"name": "alice", "city": "mumbai"}
normalized = {k: v.upper() for k, v in data.items()}
# {'name': 'ALICE', 'city': 'MUMBAI'}

# ── Nested dictionaries ─────────────────────────────────────────────────
students = {
    "alice": {
        "age": 20,
        "grades": {"math": 95, "english": 88, "science": 92},
        "active": True
    },
    "bob": {
        "age": 22,
        "grades": {"math": 78, "english": 85, "science": 80},
        "active": False
    }
}

# Access nested values
print(students["alice"]["grades"]["math"])   # 95

# Iterate over nested structure
for name, info in students.items():
    avg = sum(info["grades"].values()) / len(info["grades"])
    print(f"{name.capitalize()}: average grade = {avg:.1f}")
# Alice: average grade = 91.7
# Bob: average grade = 81.0
```

---

## 2.6 Sets

A **set** is an **unordered** collection of **unique** elements. Sets are perfect when:
- You need to eliminate duplicates
- You need fast membership testing (is X in the collection?)
- You need mathematical set operations (union, intersection, difference)

```python
# ── Creating sets ───────────────────────────────────────────────────────
empty = set()             # ⚠️ {} creates an empty DICT, not a set!
fruits = {"apple", "banana", "cherry"}
from_list = set([1, 2, 2, 3, 3, 3, 4])  # {1, 2, 3, 4} — duplicates removed!
from_string = set("hello")               # {'h', 'e', 'l', 'o'} — unique chars

# ── Membership test — O(1) hash-based lookup ────────────────────────────
# Sets are MUCH faster than lists for this:
big_list = list(range(1000000))
big_set = set(range(1000000))

# Both check if 999999 exists, but set is ~100x faster!
print(999999 in big_list)   # True — O(n) time
print(999999 in big_set)    # True — O(1) time

# ── Adding and removing ─────────────────────────────────────────────────
fruits = {"apple", "banana"}
fruits.add("cherry")           # Add single element
fruits.add("apple")            # No effect — already exists (no duplicates!)
fruits.update(["mango", "kiwi", "apple"])  # Add multiple

fruits.remove("banana")        # Remove (raises KeyError if not found)
fruits.discard("grape")        # Remove (NO error if not found — safer!)
popped = fruits.pop()          # Remove and return a RANDOM element
fruits.clear()                  # Remove all elements

# ── Set operations ──────────────────────────────────────────────────────
a = {1, 2, 3, 4, 5}
b = {4, 5, 6, 7, 8}

# Union — all elements from both sets (no duplicates)
print(a | b)            # {1, 2, 3, 4, 5, 6, 7, 8}
print(a.union(b))       # Same result

# Intersection — elements that exist in BOTH sets
print(a & b)            # {4, 5}
print(a.intersection(b))

# Difference — elements in a but NOT in b
print(a - b)            # {1, 2, 3}
print(a.difference(b))

# Symmetric difference — elements in EITHER set but NOT in BOTH
print(a ^ b)            # {1, 2, 3, 6, 7, 8}
print(a.symmetric_difference(b))

# Subset and superset checks
x = {1, 2}
y = {1, 2, 3, 4}
print(x.issubset(y))    # True  — all elements of x are in y
print(y.issuperset(x))  # True  — y contains all elements of x
print(x.isdisjoint({5, 6, 7}))  # True — no elements in common

# ── Set comprehension ────────────────────────────────────────────────────
even_squares = {x**2 for x in range(10) if x % 2 == 0}
print(even_squares)  # {0, 4, 16, 36, 64} — unordered!

# ── Practical use-cases ─────────────────────────────────────────────────
# 1. Remove duplicates from a list (while preserving some order via sorted)
names = ["Alice", "Bob", "Alice", "Charlie", "Bob", "David"]
unique_names = list(set(names))   # Order not guaranteed
unique_sorted = sorted(set(names))  # Sorted for consistency

# 2. Find common elements between two lists
list1 = [1, 2, 3, 4, 5, 6]
list2 = [4, 5, 6, 7, 8, 9]
common = set(list1) & set(list2)
print(common)   # {4, 5, 6}

# 3. Find elements in one list but not another
only_in_list1 = set(list1) - set(list2)
print(only_in_list1)  # {1, 2, 3}

# ── Frozenset — immutable set ────────────────────────────────────────────
# A frozenset is like a set but immutable — it can be used as a dict key
fs = frozenset([1, 2, 3])
# fs.add(4)  # ❌ AttributeError — can't modify

# Use as dictionary key (regular set can't be a key since it's mutable)
graph = {
    frozenset({"A", "B"}): 5,   # Edge from A to B with weight 5
    frozenset({"B", "C"}): 3,
}
```

---

## 2.7 Functions

A **function** is a reusable, named block of code that performs a specific task. Functions are the building blocks of well-organized programs. The core principles are:

- **DRY** (Don't Repeat Yourself) — write logic once, call it many times
- **Single Responsibility** — each function should do one thing well
- **Abstraction** — hide complex details behind a simple name

```python
# ── Basic function anatomy ────────────────────────────────────────────
# def keyword → function name → parameters → colon
# def function_name(param1, param2):
#     """Docstring describing the function."""
#     # body
#     return value

def greet(name):
    """Return a greeting for the given name."""
    return f"Hello, {name}!"

# Calling a function
result = greet("Alice")
print(result)   # "Hello, Alice!"
print(greet("Bob"))   # "Hello, Bob!"  — reusable!

# ── Parameters and Arguments ─────────────────────────────────────────
# Parameters: variables listed in the function definition
# Arguments: actual values passed when calling the function

# Positional arguments (order matters)
def describe(name, age, city):
    return f"{name}, {age}, from {city}"

print(describe("Alice", 30, "Mumbai"))  # positional
print(describe(age=25, city="Delhi", name="Bob"))  # keyword (order doesn't matter)
print(describe("Charlie", city="Pune", age=28))    # mixed (positional first!)

# Default parameter values (make arguments optional)
def power(base, exponent=2):
    """Raise base to the power of exponent. Default: squared."""
    return base ** exponent

print(power(5))      # 25  — uses default exponent=2
print(power(5, 3))   # 125 — overrides default with 3
print(power(exponent=4, base=2))  # 16 — keyword arguments

# ⚠️ GOTCHA: Never use mutable defaults!
def bad_append(item, lst=[]):    # ❌ The default list is shared across calls!
    lst.append(item)
    return lst

print(bad_append(1))  # [1]
print(bad_append(2))  # [1, 2]  — not [2]! (bug!)

def good_append(item, lst=None):  # ✅ Use None as default
    if lst is None:
        lst = []
    lst.append(item)
    return lst

# ── *args — Variable positional arguments ────────────────────────────
# Collects any number of positional arguments into a TUPLE
def add_all(*args):
    print(f"args = {args}, type = {type(args)}")  # args is a tuple
    return sum(args)

print(add_all(1, 2, 3))           # 6
print(add_all(10, 20, 30, 40))    # 100
print(add_all())                   # 0

# ── **kwargs — Variable keyword arguments ─────────────────────────────
# Collects any number of keyword arguments into a DICT
def show_info(**kwargs):
    print(f"kwargs = {kwargs}, type = {type(kwargs)}")  # kwargs is a dict
    for key, value in kwargs.items():
        print(f"  {key}: {value}")

show_info(name="Alice", age=30, city="Mumbai")

# ── Combined parameter types ─────────────────────────────────────────
# Order: regular args → *args → keyword-only args → **kwargs
def complex_func(a, b, *args, separator=", ", **kwargs):
    parts = [str(a), str(b)] + [str(x) for x in args]
    print(separator.join(parts))
    print("Extra:", kwargs)

complex_func(1, 2, 3, 4, separator=" | ", x=10, y=20)
# 1 | 2 | 3 | 4
# Extra: {'x': 10, 'y': 20}

# Unpacking when calling
def add(a, b, c):
    return a + b + c

values = [1, 2, 3]
print(add(*values))     # Unpack list as positional arguments → 6

info = {"a": 1, "b": 2, "c": 3}
print(add(**info))      # Unpack dict as keyword arguments → 6

# ── Return values ─────────────────────────────────────────────────────
def get_min_max(numbers):
    """Return both the minimum and maximum value."""
    return min(numbers), max(numbers)  # Returns a TUPLE

lo, hi = get_min_max([3, 1, 4, 1, 5, 9, 2, 6])
print(f"Min: {lo}, Max: {hi}")   # Min: 1, Max: 9

# Return None implicitly (function with no return statement)
def print_greeting(name):
    print(f"Hello, {name}!")
    # No return → returns None implicitly

result = print_greeting("Alice")
print(result)   # None

# Early return (guard clauses)
def divide(a, b):
    if b == 0:
        return None   # Early exit for invalid input
    return a / b

# ── Scope: LEGB Rule ─────────────────────────────────────────────────
# Python looks up variables in this order:
# L — Local scope (inside the current function)
# E — Enclosing scope (outer function, for nested functions)
# G — Global scope (module level)
# B — Built-in scope (Python's built-ins like len, print, range)

x = "global"   # Global scope

def outer():
    x = "enclosing"   # Enclosing scope
    def inner():
        x = "local"   # Local scope
        print(x)      # "local" — L comes first in LEGB
    inner()
    print(x)          # "enclosing" — inside outer(), x is enclosing

outer()
print(x)              # "global" — at module level

# global keyword — modify a global variable from inside a function
count = 0
def increment():
    global count      # Tell Python we want the global 'count'
    count += 1

increment()
increment()
print(count)   # 2
```

### Lambda Functions

```python
# A lambda is a small anonymous (unnamed) function defined in one line
# Syntax: lambda parameters: expression

# Regular function:
def square(x):
    return x ** 2

# Equivalent lambda:
square = lambda x: x ** 2
print(square(5))   # 25

# Multi-parameter lambda
add = lambda a, b: a + b
print(add(3, 4))   # 7

# Lambda with condition
is_even = lambda n: n % 2 == 0
print(is_even(4))   # True
print(is_even(7))   # False

# ── When to use lambdas ───────────────────────────────────────────────
# Best used as short, one-off functions passed to other functions:

numbers = [3, -1, 4, -1, 5, -9, 2, -6]

# sorted() with custom key
sorted_abs = sorted(numbers, key=lambda x: abs(x))
print(sorted_abs)   # [-1, -1, 2, 3, 4, -6, 5, -9]

# max/min with key
students = [("Alice", 85), ("Bob", 92), ("Charlie", 78)]
top = max(students, key=lambda s: s[1])
print(f"Top student: {top[0]} with {top[1]}")  # Bob with 92

# map() — apply function to every element
doubled = list(map(lambda x: x * 2, [1, 2, 3, 4, 5]))
print(doubled)   # [2, 4, 6, 8, 10]

# filter() — keep only elements where function returns True
positives = list(filter(lambda x: x > 0, numbers))
print(positives)   # [3, 4, 5, 2]

# reduce() — cumulatively apply function
from functools import reduce
product = reduce(lambda a, b: a * b, [1, 2, 3, 4, 5])
print(product)   # 120  (1×2×3×4×5)

# ⚠️ Don't overuse lambdas — if the logic is complex, use a named function
# for better readability and reusability
```

---

---

# Level 3 — Intermediate (Core Python)

## 3.1 Object-Oriented Programming (OOP)

**Object-Oriented Programming (OOP)** is a programming paradigm that organizes code around **objects** — entities that bundle together data (attributes) and behavior (methods). OOP makes complex programs easier to design, understand, maintain, and reuse.

The 4 pillars of OOP are:
1. **Encapsulation** — bundling data and methods; hiding internal details
2. **Inheritance** — a class can acquire properties of another class
3. **Polymorphism** — objects of different types can be treated uniformly
4. **Abstraction** — expose only what's necessary; hide complexity

### Classes and Objects

A **class** is a blueprint/template. An **object** (instance) is a concrete thing created from that blueprint.

```python
# CLASS = blueprint (like an architect's plan)
# OBJECT = instance (like the actual house built from that plan)

class Dog:
    # Class variable — shared by ALL instances of Dog
    species = "Canis familiaris"

    # __init__ is the constructor — runs automatically when an object is created
    # 'self' refers to the instance being created (like 'this' in Java/C++)
    def __init__(self, name, age, breed):
        # Instance variables — unique to EACH object
        self.name = name
        self.age = age
        self.breed = breed
        self._tricks = []        # Protected: internal use
        self.__id = id(self)     # Private: name-mangled to _Dog__id

    # Instance method — can access/modify instance data via self
    def bark(self):
        return f"{self.name} says: Woof! Woof!"

    def learn_trick(self, trick):
        self._tricks.append(trick)
        return f"{self.name} learned '{trick}'!"

    def show_tricks(self):
        if not self._tricks:
            return f"{self.name} knows no tricks yet."
        return f"{self.name} knows: {', '.join(self._tricks)}"

    # Class method — works on the class, not instances
    @classmethod
    def from_string(cls, dog_str):
        """Alternative constructor: 'Buddy-3-Labrador' → Dog object"""
        name, age, breed = dog_str.split("-")
        return cls(name, int(age), breed)

    # Static method — utility function, no access to class or instance
    @staticmethod
    def dog_years(human_years):
        """Convert human years to approximate dog years."""
        return human_years * 7

    def __str__(self):
        """Human-readable string (used by print())"""
        return f"{self.name} the {self.breed}, age {self.age}"

    def __repr__(self):
        """Developer-friendly string (used in REPL/debugging)"""
        return f"Dog(name='{self.name}', age={self.age}, breed='{self.breed}')"

    def __eq__(self, other):
        return isinstance(other, Dog) and self.name == other.name and self.age == other.age

    def __lt__(self, other):
        return self.age < other.age   # Compare by age

# Creating objects
dog1 = Dog("Buddy", 3, "Labrador")
dog2 = Dog("Max", 5, "German Shepherd")
dog3 = Dog.from_string("Luna-2-Poodle")  # Using classmethod

print(dog1)                     # Buddy the Labrador, age 3
print(repr(dog2))               # Dog(name='Max', age=5, breed='German Shepherd')
print(dog1.bark())              # Buddy says: Woof! Woof!
print(dog1.learn_trick("sit")) # Buddy learned 'sit'!
print(dog1.learn_trick("paw")) # Buddy learned 'paw'!
print(dog1.show_tricks())      # Buddy knows: sit, paw

print(Dog.dog_years(7))        # 49 (static method via class)
print(dog1.dog_years(3))       # 21 (static method via instance also works)
print(Dog.species)             # Canis familiaris (class variable)

print(dog1 == dog2)            # False
print(sorted([dog2, dog1, dog3], key=lambda d: d.age))  # sorted by age
```

### Inheritance

Inheritance lets a **child class** reuse and extend the functionality of a **parent class**. This models the real-world "is-a" relationship (a Dog IS-A Animal).

```python
class Animal:
    """Base class for all animals."""
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.energy = 100

    def eat(self, food):
        self.energy += 10
        return f"{self.name} eats {food}. Energy: {self.energy}"

    def sleep(self, hours):
        self.energy += hours * 5
        return f"{self.name} sleeps {hours}h. Energy: {self.energy}"

    def speak(self):
        raise NotImplementedError("Subclasses must implement speak()")

    def __str__(self):
        return f"{self.__class__.__name__}({self.name}, age={self.age})"


class Dog(Animal):
    def __init__(self, name, age, breed):
        super().__init__(name, age)   # Call parent __init__
        self.breed = breed
        self.trained = False

    def speak(self):
        return f"{self.name}: Woof!"

    def fetch(self, item="ball"):
        self.energy -= 10
        return f"{self.name} fetches the {item}!"

    def train(self):
        self.trained = True
        return f"{self.name} is now trained!"


class Cat(Animal):
    def __init__(self, name, age, indoor=True):
        super().__init__(name, age)
        self.indoor = indoor

    def speak(self):
        return f"{self.name}: Meow!"

    def purr(self):
        return f"{self.name} purrs contentedly..."

    def scratch(self, target="furniture"):
        return f"{self.name} scratches the {target}!"


class GuideDog(Dog):
    """Multi-level inheritance: GuideDog → Dog → Animal"""
    def __init__(self, name, age, breed, owner):
        super().__init__(name, age, breed)
        self.owner = owner

    def guide(self):
        return f"{self.name} safely guides {self.owner}."


# Testing inheritance
dog = Dog("Buddy", 3, "Labrador")
cat = Cat("Whiskers", 5)
guide = GuideDog("Rex", 4, "Golden Retriever", "Alice")

print(dog.eat("bone"))    # Inherited from Animal
print(dog.speak())        # Overridden in Dog
print(dog.fetch("stick")) # Dog-specific

print(cat.sleep(8))       # Inherited
print(cat.speak())        # Overridden in Cat
print(cat.purr())         # Cat-specific

print(guide.guide())      # GuideDog-specific
print(guide.fetch())      # Inherited from Dog
print(guide.eat("kibble"))  # Inherited from Animal

# Type checking
print(isinstance(guide, GuideDog))  # True
print(isinstance(guide, Dog))       # True (is a Dog)
print(isinstance(guide, Animal))    # True (is an Animal)
print(isinstance(guide, Cat))       # False

# Method Resolution Order (MRO) — which class's method gets called
print(GuideDog.__mro__)
# (<class 'GuideDog'>, <class 'Dog'>, <class 'Animal'>, <class 'object'>)
```

### Encapsulation

Encapsulation means **bundling data and methods together** and **restricting direct access** to internal data. Python uses naming conventions:

```python
class BankAccount:
    """
    Demonstrates encapsulation with public, protected, and private attributes.
    Public: name — accessible everywhere
    Protected: _type — convention for "internal use", still accessible
    Private: __balance — name-mangled to _BankAccount__balance
    """

    interest_rate = 0.05   # Class variable (public)

    def __init__(self, owner, initial_balance=0):
        self.owner = owner              # Public attribute
        self._account_type = "Savings"  # Protected (by convention)
        self.__balance = initial_balance # Private (name-mangled)
        self.__transaction_log = []      # Private

    def deposit(self, amount):
        """Public method to add money."""
        if not isinstance(amount, (int, float)) or amount <= 0:
            raise ValueError(f"Invalid deposit amount: {amount}")
        self.__balance += amount
        self.__log(f"DEPOSIT +{amount}")
        return f"Deposited {amount}. New balance: {self.__balance}"

    def withdraw(self, amount):
        """Public method to remove money."""
        if amount <= 0:
            raise ValueError("Withdrawal amount must be positive")
        if amount > self.__balance:
            raise ValueError(f"Insufficient funds. Balance: {self.__balance}")
        self.__balance -= amount
        self.__log(f"WITHDRAW -{amount}")
        return f"Withdrew {amount}. New balance: {self.__balance}"

    def __log(self, message):
        """Private helper — only callable from inside this class."""
        import datetime
        self.__transaction_log.append(
            f"[{datetime.datetime.now():%H:%M:%S}] {message}"
        )

    @property
    def balance(self):
        """Read-only property — exposes balance without direct access."""
        return self.__balance

    @property
    def history(self):
        return list(self.__transaction_log)  # Return a copy

    def __str__(self):
        return f"Account({self.owner}, balance={self.__balance})"


acc = BankAccount("Alice", 1000)
print(acc.deposit(500))     # Deposited 500. New balance: 1500
print(acc.withdraw(200))    # Withdrew 200. New balance: 1300
print(acc.balance)          # 1300 — via property
print(acc.history)          # Transaction log
# acc.__balance             # ❌ AttributeError — private!
# acc._BankAccount__balance # Works but bad practice (accessing private)
```

### Properties (Getters and Setters)

Properties let you define controlled access to attributes — you can validate data on the way in and compute values on the way out:

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius   # Uses the setter below

    @property
    def radius(self):
        """Getter: called when you READ circle.radius"""
        return self._radius

    @radius.setter
    def radius(self, value):
        """Setter: called when you WRITE circle.radius = x"""
        if not isinstance(value, (int, float)):
            raise TypeError("Radius must be a number")
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value

    @radius.deleter
    def radius(self):
        """Deleter: called when you do del circle.radius"""
        raise AttributeError("Cannot delete radius")

    @property
    def diameter(self):
        """Computed property — no setter needed (read-only)"""
        return self._radius * 2

    @property
    def area(self):
        import math
        return math.pi * self._radius ** 2

    @property
    def circumference(self):
        import math
        return 2 * math.pi * self._radius


c = Circle(5)
print(c.radius)        # 5
print(c.diameter)      # 10
print(f"Area: {c.area:.2f}")    # Area: 78.54
c.radius = 10          # Calls the setter
print(c.diameter)      # 20
# c.radius = -3        # ❌ ValueError
# c.radius = "big"     # ❌ TypeError
```

### Polymorphism and Magic (Dunder) Methods

Polymorphism means "many forms" — the same operation works differently for different types. Python achieves this through **duck typing** and **dunder methods** (double underscore methods like `__add__`, `__len__`):

```python
import math

class Vector2D:
    """2D vector with rich operator support."""

    def __init__(self, x, y):
        self.x = x
        self.y = y

    # Arithmetic operators
    def __add__(self, other):      # v1 + v2
        return Vector2D(self.x + other.x, self.y + other.y)

    def __sub__(self, other):      # v1 - v2
        return Vector2D(self.x - other.x, self.y - other.y)

    def __mul__(self, scalar):     # v1 * 3
        return Vector2D(self.x * scalar, self.y * scalar)

    def __rmul__(self, scalar):    # 3 * v1 (reversed)
        return self.__mul__(scalar)

    def __truediv__(self, scalar): # v1 / 2
        return Vector2D(self.x / scalar, self.y / scalar)

    def __neg__(self):             # -v1
        return Vector2D(-self.x, -self.y)

    # Comparison operators
    def __eq__(self, other):       # v1 == v2
        return self.x == other.x and self.y == other.y

    def __abs__(self):             # abs(v1) → magnitude
        return math.sqrt(self.x**2 + self.y**2)

    # Container-like behavior
    def __len__(self):             # len(v1)
        return 2

    def __getitem__(self, index):  # v1[0], v1[1]
        return (self.x, self.y)[index]

    def __iter__(self):            # for coord in v1
        yield self.x
        yield self.y

    def __contains__(self, value): # 3 in v1
        return value in (self.x, self.y)

    # String representations
    def __str__(self):
        return f"({self.x}, {self.y})"

    def __repr__(self):
        return f"Vector2D({self.x}, {self.y})"

    def __format__(self, spec):    # f"{v1:.2f}"
        return f"({self.x:{spec}}, {self.y:{spec}})"

    def dot(self, other):
        return self.x * other.x + self.y * other.y


v1 = Vector2D(3, 4)
v2 = Vector2D(1, 2)

print(v1 + v2)       # (4, 6)
print(v1 - v2)       # (2, 2)
print(v1 * 3)        # (9, 12)
print(3 * v1)        # (9, 12)  — uses __rmul__
print(abs(v1))       # 5.0     — magnitude
print(len(v1))       # 2
print(v1[0])         # 3
print(list(v1))      # [3, 4]
print(3 in v1)       # True
print(f"{v1:.1f}")   # (3.0, 4.0)
print(v1.dot(v2))    # 11  (3×1 + 4×2)
```

---

## 3.2 Error and Exception Handling

Programs fail — users enter bad data, files go missing, networks drop. **Exception handling** lets you gracefully manage errors instead of crashing. Python uses a structured `try/except/else/finally` mechanism.

### The Exception Hierarchy

```
BaseException
├── SystemExit          ← sys.exit()
├── KeyboardInterrupt   ← Ctrl+C
└── Exception           ← All normal exceptions
    ├── ValueError      ← Wrong value (e.g., int("hello"))
    ├── TypeError       ← Wrong type (e.g., "a" + 1)
    ├── KeyError        ← Dict key not found
    ├── IndexError      ← List index out of range
    ├── AttributeError  ← Object has no such attribute
    ├── NameError       ← Variable not defined
    ├── ZeroDivisionError ← Division by zero
    ├── FileNotFoundError ← File doesn't exist
    ├── ImportError     ← Module not found
    ├── StopIteration   ← Iterator exhausted
    └── ... many more
```

```python
# ── Basic try-except ────────────────────────────────────────────────────
try:
    result = 10 / 0         # This raises ZeroDivisionError
    print("Never reaches here")
except ZeroDivisionError:
    print("Cannot divide by zero!")   # This runs instead
print("Program continues...")

# ── Catching specific exceptions ────────────────────────────────────────
def parse_number(text):
    try:
        return int(text)
    except ValueError:
        print(f"'{text}' is not a valid integer")
        return None
    except TypeError:
        print(f"Expected a string, got {type(text).__name__}")
        return None

parse_number("42")     # Returns 42
parse_number("hello")  # ValueError caught
parse_number(None)     # TypeError caught

# ── Catching multiple exceptions in one line ────────────────────────────
try:
    data = {}
    value = data["key"]      # KeyError
    result = value / 0       # ZeroDivisionError (unreachable here)
except (KeyError, ZeroDivisionError) as e:
    print(f"Caught: {type(e).__name__}: {e}")

# ── try-except-else-finally ─────────────────────────────────────────────
# else:    runs ONLY if no exception occurred
# finally: ALWAYS runs (cleanup code — close files, connections, etc.)

def read_file(filename):
    file = None
    try:
        file = open(filename, "r")
        content = file.read()
    except FileNotFoundError:
        print(f"Error: '{filename}' not found")
        return None
    except PermissionError:
        print(f"Error: No permission to read '{filename}'")
        return None
    else:
        # Only runs if no exception occurred
        print(f"Successfully read {len(content)} characters")
        return content
    finally:
        # ALWAYS runs — perfect for cleanup
        if file:
            file.close()
            print("File closed.")

# ── Using 'with' (context manager) — safer file handling ────────────────
# The 'with' statement handles cleanup automatically
with open("example.txt", "w") as f:
    f.write("Hello!\n")
# File is automatically closed here, even if an exception occurs

# ── Raising exceptions ───────────────────────────────────────────────────
def set_age(age):
    """Validate and set age."""
    if not isinstance(age, int):
        raise TypeError(f"Age must be int, got {type(age).__name__}")
    if age < 0 or age > 150:
        raise ValueError(f"Age must be between 0 and 150, got {age}")
    return age

# Re-raising exceptions (add context and re-raise)
def process_data(data):
    try:
        result = risky_operation(data)
    except ValueError as e:
        raise RuntimeError(f"Failed to process data: {data}") from e

# ── Exception chaining ───────────────────────────────────────────────────
try:
    try:
        int("bad")
    except ValueError as original:
        raise RuntimeError("Data processing failed") from original
except RuntimeError as e:
    print(f"Error: {e}")
    print(f"Caused by: {e.__cause__}")

# ── Custom exceptions ────────────────────────────────────────────────────
class AppError(Exception):
    """Base exception for this application."""
    pass

class ValidationError(AppError):
    """Raised when input validation fails."""
    def __init__(self, field, message):
        self.field = field
        self.message = message
        super().__init__(f"Validation failed on '{field}': {message}")

class AuthenticationError(AppError):
    """Raised when authentication fails."""
    def __init__(self, username):
        self.username = username
        super().__init__(f"Authentication failed for user: {username}")

class InsufficientFundsError(AppError):
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount
        self.shortfall = amount - balance
        super().__init__(
            f"Cannot withdraw {amount}. Balance: {balance}. "
            f"Short by: {self.shortfall}"
        )

# Using custom exceptions
def validate_email(email):
    if "@" not in email:
        raise ValidationError("email", f"'{email}' is not a valid email address")
    return email.lower()

try:
    validate_email("notanemail")
except ValidationError as e:
    print(f"Field '{e.field}': {e.message}")
    # Field 'email': 'notanemail' is not a valid email address
```

---

## 3.3 File Handling

File I/O (Input/Output) allows your program to **persist data** beyond the program's lifetime — reading configuration, saving results, processing log files, etc.

```python
import os
import csv
import json
from pathlib import Path

# ── The 'with' statement — always use it for files! ──────────────────────
# It guarantees the file is closed even if an error occurs
# Open modes:
# 'r'  — read (default) — file must exist
# 'w'  — write — creates or OVERWRITES file
# 'a'  — append — creates or adds to end of file
# 'x'  — exclusive create — fails if file exists
# 'b'  — binary mode (combine: 'rb', 'wb')
# '+'  — read+write (combine: 'r+', 'w+')

# ── Writing text files ───────────────────────────────────────────────────
with open("students.txt", "w", encoding="utf-8") as f:
    f.write("Alice, 20, A\n")
    f.write("Bob, 22, B\n")
    f.writelines(["Charlie, 21, A\n", "Diana, 23, C\n"])

# ── Reading text files ───────────────────────────────────────────────────
# Method 1: Read entire file as a string
with open("students.txt", "r", encoding="utf-8") as f:
    content = f.read()
    print(content)

# Method 2: Read line by line (memory efficient for large files)
with open("students.txt", "r", encoding="utf-8") as f:
    for line in f:
        name, age, grade = line.strip().split(", ")
        print(f"{name} (age {age}): Grade {grade}")

# Method 3: Read all lines into a list
with open("students.txt", "r") as f:
    lines = f.readlines()   # Each line includes the \n character

# Method 4: Read single line
with open("students.txt", "r") as f:
    first_line = f.readline()

# ── Appending to files ───────────────────────────────────────────────────
with open("students.txt", "a", encoding="utf-8") as f:
    f.write("Eve, 24, B\n")   # Added to end without overwriting

# ── pathlib — modern path handling (Python 3.4+) ────────────────────────
# Recommended over os.path for file paths
path = Path("data") / "students" / "class_a.txt"  # Cross-platform paths!
path.parent.mkdir(parents=True, exist_ok=True)     # Create dirs
path.write_text("Hello!\n", encoding="utf-8")      # Write
content = path.read_text(encoding="utf-8")          # Read
print(path.exists())    # True
print(path.suffix)      # '.txt'
print(path.stem)        # 'class_a'
print(path.parent)      # data/students
for p in Path(".").glob("*.txt"):  # Find all .txt files
    print(p)

# ── CSV files ────────────────────────────────────────────────────────────
# CSV (Comma-Separated Values) is the most common data exchange format

# Writing CSV
students = [
    {"name": "Alice", "age": 20, "grade": "A"},
    {"name": "Bob", "age": 22, "grade": "B"},
    {"name": "Charlie", "age": 21, "grade": "A"},
]

with open("students.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "age", "grade"])
    writer.writeheader()
    writer.writerows(students)

# Reading CSV
with open("students.csv", "r", encoding="utf-8") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(f"{row['name']} — Grade: {row['grade']}")

# ── JSON files ───────────────────────────────────────────────────────────
# JSON is the standard format for APIs and configuration files

config = {
    "app_name": "MyApp",
    "version": "1.0.0",
    "debug": False,
    "database": {
        "host": "localhost",
        "port": 5432,
        "name": "mydb"
    },
    "allowed_hosts": ["localhost", "127.0.0.1"]
}

# Write JSON (serialize Python → JSON string)
with open("config.json", "w", encoding="utf-8") as f:
    json.dump(config, f, indent=4, ensure_ascii=False)

# Read JSON (deserialize JSON string → Python)
with open("config.json", "r", encoding="utf-8") as f:
    loaded_config = json.load(f)

print(loaded_config["database"]["host"])   # localhost

# Convert between JSON string and Python dict
json_string = json.dumps(config, indent=2)   # dict → string
data = json.loads(json_string)               # string → dict

# ── os module for file system operations ─────────────────────────────────
import os

print(os.getcwd())                    # Current working directory
os.makedirs("temp/subdir", exist_ok=True)  # Create nested directories
print(os.listdir("."))               # List files in current directory

# Check existence
print(os.path.exists("students.txt"))  # True
print(os.path.isfile("students.txt"))  # True
print(os.path.isdir("temp"))           # True

# File info
stat = os.stat("students.txt")
print(f"Size: {stat.st_size} bytes")

# Rename and delete
os.rename("students.txt", "class_list.txt")
os.remove("class_list.txt")        # Delete a file
os.rmdir("temp/subdir")            # Delete empty directory
```

---

## 3.4 Modules and Packages

**Modules** are Python files (.py) you can import into other files. **Packages** are directories of modules. They're the foundation of Python's ecosystem and help organize large codebases.

```python
# ── Importing modules ────────────────────────────────────────────────────
# Method 1: Import entire module (access via module.name)
import math
print(math.pi)          # 3.14159...
print(math.sqrt(16))    # 4.0
print(math.factorial(5))# 120

# Method 2: Import specific items (no prefix needed)
from math import pi, sqrt, ceil, floor, log2
print(pi)               # 3.14159...
print(sqrt(25))         # 5.0

# Method 3: Import with alias (shorter name)
import numpy as np          # Common convention
import pandas as pd         # Common convention
import matplotlib.pyplot as plt  # Common convention

# Method 4: Import everything (use sparingly — pollutes namespace)
from math import *          # Now all math functions available directly

# ── Standard Library highlights ──────────────────────────────────────────
import os, sys, math, random, datetime, re, json
import collections, itertools, functools
from pathlib import Path
from typing import List, Dict, Optional

# math — mathematical operations
print(math.gcd(48, 18))         # 6  — greatest common divisor
print(math.lcm(4, 6))           # 12 — least common multiple (3.9+)
print(math.log(100, 10))        # 2.0 — log base 10
print(math.degrees(math.pi))    # 180.0 — radians to degrees
print(math.sin(math.pi/2))      # 1.0
print(math.isclose(0.1+0.2, 0.3))  # True — float comparison!

# random — randomness
random.seed(42)                  # Seed for reproducibility
print(random.randint(1, 10))     # Random int 1-10
print(random.random())           # Random float 0.0-1.0
print(random.uniform(1.5, 10.5))# Random float in range
items = ["a", "b", "c", "d"]
print(random.choice(items))      # Random element
print(random.sample(items, 2))   # 2 unique random elements (no replacement)
random.shuffle(items)            # Shuffle in-place

# datetime — dates and times
from datetime import datetime, date, timedelta, timezone
now = datetime.now()
print(now)                       # 2024-06-15 13:45:00.123456
print(now.strftime("%d %B %Y")) # 15 June 2024
born = date(1995, 6, 15)
age = (date.today() - born).days // 365
print(f"Age: {age} years")
deadline = now + timedelta(days=30, hours=5)  # 30 days 5 hours from now
print(datetime.strptime("15/06/2024", "%d/%m/%Y"))  # Parse from string

# collections — specialized data structures
from collections import Counter, defaultdict, OrderedDict, deque, namedtuple

# Counter — count occurrences
words = "the quick brown fox jumps over the lazy dog the".split()
freq = Counter(words)
print(freq.most_common(3))    # [('the', 3), ('quick', 1), ('brown', 1)]
print(freq["the"])             # 3
freq.update(["fox", "dog"])   # Add more counts

# defaultdict — dict with automatic default value for missing keys
grouped = defaultdict(list)
data = [("fruit", "apple"), ("veggie", "carrot"), ("fruit", "banana")]
for category, item in data:
    grouped[category].append(item)
print(dict(grouped))
# {'fruit': ['apple', 'banana'], 'veggie': ['carrot']}

# deque — double-ended queue, O(1) at both ends
dq = deque(range(5))          # deque([0, 1, 2, 3, 4])
dq.appendleft(-1)             # deque([-1, 0, 1, 2, 3, 4])
dq.append(5)                  # deque([-1, 0, 1, 2, 3, 4, 5])
dq.popleft()                  # -1 removed
dq.rotate(2)                  # Rotate right by 2
dq_limited = deque(range(10), maxlen=5)  # Only keeps last 5

# itertools — efficient iterators
import itertools
print(list(itertools.islice(itertools.count(0, 2), 5)))  # [0, 2, 4, 6, 8]
print(list(itertools.combinations([1,2,3,4], 2)))
# [(1,2),(1,3),(1,4),(2,3),(2,4),(3,4)]
print(list(itertools.permutations("ABC", 2)))
# [('A','B'),('A','C'),('B','A'),('B','C'),('C','A'),('C','B')]
print(list(itertools.product([0,1], repeat=3)))  # Binary: 000 to 111

# ── Creating your own module ─────────────────────────────────────────────
# File: calculator.py
# def add(a, b): return a + b
# def subtract(a, b): return a - b
# PI = 3.14159
# if __name__ == "__main__":      ← Only runs when file is executed directly
#     print("Running as script")  ← Does NOT run when imported

# File: main.py
# import calculator
# print(calculator.add(2, 3))   # 5
# print(calculator.PI)          # 3.14159

# ── Package structure ────────────────────────────────────────────────────
# my_package/
# ├── __init__.py          ← Required; can be empty or set up public API
# ├── models.py
# ├── utils.py
# └── services/
#     ├── __init__.py
#     ├── email_service.py
#     └── payment_service.py

# my_package/__init__.py
# from .models import User, Product       ← re-export
# from .utils import format_date, slugify
# __version__ = "1.0.0"
# __all__ = ["User", "Product", "format_date"]  ← controls 'from pkg import *'

# Usage after installing or adding to PYTHONPATH:
# from my_package import User
# from my_package.services.email_service import send_email
```

---

## 3.5 Regular Expressions

**Regular expressions** (regex) are patterns that describe a set of strings. They're incredibly powerful for searching, validating, and transforming text. The `re` module provides regex functionality in Python.

```python
import re

# ── Regex special characters ─────────────────────────────────────────────
# .  — any character except newline
# *  — 0 or more of the previous
# +  — 1 or more of the previous
# ?  — 0 or 1 of the previous (optional)
# ^  — start of string
# $  — end of string
# [] — character class: [aeiou] matches any vowel
# [^]— negated class: [^0-9] matches any non-digit
# \d — digit [0-9]
# \D — non-digit
# \w — word character [a-zA-Z0-9_]
# \W — non-word character
# \s — whitespace [ \t\n\r\f\v]
# \S — non-whitespace
# \b — word boundary
# () — capturing group
# | — alternation (OR)
# {} — repetition: \d{3} means exactly 3 digits, \d{2,4} means 2 to 4

# ── Core functions ───────────────────────────────────────────────────────
text = "Alice's phone: +91-9876543210, email: alice@example.com"

# re.search() — find FIRST match anywhere in string
match = re.search(r'\d+', text)
if match:
    print(match.group())    # "91" (first sequence of digits)
    print(match.start())    # position where match starts
    print(match.end())      # position where match ends
    print(match.span())     # (start, end)

# re.findall() — find ALL matches, return as list
all_numbers = re.findall(r'\d+', text)
print(all_numbers)   # ['91', '9876543210']

# re.match() — match only at the START of string
m = re.match(r'\w+', "Hello World")
print(m.group() if m else "No match")  # "Hello"
m = re.match(r'\d+', "Hello World")
print(m)  # None — no digits at start

# re.fullmatch() — must match ENTIRE string
print(re.fullmatch(r'\d{10}', '9876543210'))  # Match
print(re.fullmatch(r'\d{10}', 'abc'))          # None

# re.sub() — replace matches
cleaned = re.sub(r'\d', '#', text)         # Replace every digit
print(cleaned)   # Alice's phone: +##-##########, email: alice@example.com

# Replace with function
def mask_digit(m):
    return '*' * len(m.group())

masked = re.sub(r'\d+', mask_digit, text)
print(masked)    # Alice's phone: +**-**********, email: alice@example.com

# re.split() — split on a pattern
parts = re.split(r'[,\s]+', "one, two,  three    four")
print(parts)   # ['one', 'two', 'three', 'four']

# ── Compiled patterns — faster for repeated use ──────────────────────────
email_re = re.compile(
    r'^[a-zA-Z0-9._%+-]+'   # username
    r'@'                      # @ symbol
    r'[a-zA-Z0-9.-]+'        # domain
    r'\.'                     # dot
    r'[a-zA-Z]{2,}$',        # TLD (2+ letters)
    re.IGNORECASE             # case-insensitive
)

emails = ["alice@example.com", "bob@GMAIL.COM", "bad@email", "no-at-sign"]
for e in emails:
    print(f"{e}: {'Valid' if email_re.match(e) else 'Invalid'}")

# ── Capturing groups ─────────────────────────────────────────────────────
# Use () to capture parts of the pattern
log_line = "2024-06-15 13:45:22 ERROR Failed to connect to database"
pattern = r'(\d{4}-\d{2}-\d{2}) (\d{2}:\d{2}:\d{2}) (\w+) (.*)'

m = re.match(pattern, log_line)
if m:
    date, time, level, message = m.groups()
    print(f"Date: {date}")      # 2024-06-15
    print(f"Time: {time}")      # 13:45:22
    print(f"Level: {level}")    # ERROR
    print(f"Message: {message}")

# Named groups — much more readable
pattern = r'(?P<date>\d{4}-\d{2}-\d{2}) (?P<time>\d{2}:\d{2}:\d{2}) (?P<level>\w+) (?P<msg>.*)'
m = re.match(pattern, log_line)
if m:
    print(m.group('date'))    # 2024-06-15
    print(m.group('level'))   # ERROR
    print(m.groupdict())      # {'date': ..., 'time': ..., ...}

# ── Practical regex patterns ──────────────────────────────────────────────
PATTERNS = {
    "email":       r'^[\w.+-]+@[\w-]+\.[\w.]+$',
    "phone_india": r'^\+?91?[-.\s]?[6-9]\d{9}$',
    "url":         r'https?://[\w./-]+(?:\?[\w=&]+)?',
    "ipv4":        r'\b(?:\d{1,3}\.){3}\d{1,3}\b',
    "date_dmy":    r'\b\d{1,2}/\d{1,2}/\d{4}\b',
    "credit_card": r'\b\d{4}[-\s]?\d{4}[-\s]?\d{4}[-\s]?\d{4}\b',
    "password":    r'^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$',  # 8+ chars, upper, lower, digit
}
```

---

## 3.6 Iterators and Generators

**Iterators** provide a standard way to traverse a sequence of values one at a time, without loading everything into memory. **Generators** are a simpler way to create iterators using `yield`.

### Iterators

```python
# Everything you can loop over is ITERABLE
# An ITERATOR is an object that produces values one at a time

# Python's for loop internally:
#   1. Calls iter(iterable) to get an iterator
#   2. Repeatedly calls next(iterator) until StopIteration

# Manual iteration
nums = [10, 20, 30]
iterator = iter(nums)        # Get iterator object
print(next(iterator))        # 10
print(next(iterator))        # 20
print(next(iterator))        # 30
# print(next(iterator))      # ❌ StopIteration — exhausted!

# Custom iterator — implement __iter__ and __next__
class NumberRange:
    """An iterator that generates numbers from start to stop with a step."""
    def __init__(self, start, stop, step=1):
        self.current = start
        self.stop = stop
        self.step = step

    def __iter__(self):
        return self   # The object itself is the iterator

    def __next__(self):
        if self.current >= self.stop:
            raise StopIteration
        value = self.current
        self.current += self.step
        return value

# Works in for loops
for n in NumberRange(0, 20, 3):
    print(n, end=" ")   # 0 3 6 9 12 15 18

# Can use list(), sum(), etc.
print(list(NumberRange(1, 6)))    # [1, 2, 3, 4, 5]
print(sum(NumberRange(1, 101)))   # 5050
```

### Generators

```python
# Generators use 'yield' instead of 'return'
# They produce values ON DEMAND — never build the entire sequence in memory
# Great for: large datasets, infinite sequences, pipelines

# Generator function
def count_up(start, stop, step=1):
    """Generate numbers from start to stop."""
    current = start
    while current < stop:
        yield current          # Pause here, return value, resume on next()
        current += step

# Exact same behavior as NumberRange, but simpler!
for n in count_up(0, 20, 3):
    print(n, end=" ")   # 0 3 6 9 12 15 18

# ── Generator expressions — inline generators ───────────────────────────
# Like list comprehensions but with () — lazy evaluation
squares_list = [x**2 for x in range(1000000)]    # Allocates 1M items in memory!
squares_gen  = (x**2 for x in range(1000000))    # Allocates almost nothing!

# Only compute what you need
first_5 = [next(squares_gen) for _ in range(5)]  # [0, 1, 4, 9, 16]

# ── Infinite generators ─────────────────────────────────────────────────
def fibonacci():
    """Infinite Fibonacci sequence generator."""
    a, b = 0, 1
    while True:          # Infinite loop — OK in a generator!
        yield a
        a, b = b, a + b

def primes():
    """Infinite prime number generator (Sieve of Eratosthenes style)."""
    sieve = set()
    n = 2
    while True:
        if n not in sieve:
            yield n
            sieve.update(range(n*n, n*n + n*1000, n))  # Mark multiples
        n += 1

# Consume only what you need
import itertools
fib = fibonacci()
first_10_fib = list(itertools.islice(fib, 10))
print(first_10_fib)   # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]

first_10_primes = list(itertools.islice(primes(), 10))
print(first_10_primes)  # [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]

# ── Generator pipelines ──────────────────────────────────────────────────
# Chain generators together for efficient data processing
def read_lines(filename):
    """Lazily read a file line by line."""
    with open(filename) as f:
        for line in f:
            yield line.strip()

def filter_non_empty(lines):
    for line in lines:
        if line and not line.startswith('#'):
            yield line

def parse_csv_row(lines):
    for line in lines:
        yield line.split(',')

# Pipeline: file → filter → parse (processes one line at a time)
# pipeline = parse_csv_row(filter_non_empty(read_lines("data.csv")))
# for row in pipeline:
#     process(row)

# ── yield from — delegate to sub-generator ──────────────────────────────
def flatten(nested):
    """Recursively flatten nested iterables."""
    for item in nested:
        if hasattr(item, '__iter__') and not isinstance(item, (str, bytes)):
            yield from flatten(item)   # Delegate to recursive call
        else:
            yield item

nested = [1, [2, 3], [4, [5, 6]], 7]
print(list(flatten(nested)))   # [1, 2, 3, 4, 5, 6, 7]
```

---

# Level 4 — Advanced Python

## 4.1 Decorators

A **decorator** is a function that takes another function and extends/modifies its behavior without changing the original function's code. Decorators use the `@` syntax sugar.

**Real-world analogy**: Think of a decorator like gift wrapping — you take a gift (function), wrap it in paper (decorator), and the gift still works the same inside but now has extra packaging around it.

```python
import time
import functools

# ── How decorators work ──────────────────────────────────────────────────
# A decorator is simply a function that:
# 1. Takes a function as its argument
# 2. Returns a new (wrapped) function

def bold(func):
    """Wrap the return value in <b> tags."""
    @functools.wraps(func)   # Preserves __name__, __doc__, etc.
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return f"<b>{result}</b>"
    return wrapper

# These two are equivalent:
@bold
def greet(name):
    return f"Hello, {name}!"

# greet = bold(greet)  # Same as @bold

print(greet("Alice"))   # <b>Hello, Alice!</b>

# ── Practical: timer decorator ───────────────────────────────────────────
def timer(func):
    """Measure and print how long a function takes."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        result = func(*args, **kwargs)
        elapsed = time.perf_counter() - start
        print(f"[TIMER] {func.__name__}() took {elapsed:.4f}s")
        return result
    return wrapper

@timer
def slow_sum(n):
    return sum(range(n))

result = slow_sum(10_000_000)   # [TIMER] slow_sum() took 0.2345s

# ── Practical: memoize/cache decorator ──────────────────────────────────
def memoize(func):
    """Cache results so repeated calls with same args are instant."""
    cache = {}
    @functools.wraps(func)
    def wrapper(*args):
        if args not in cache:
            cache[args] = func(*args)
        return cache[args]
    return wrapper

@memoize
def fib(n):
    if n < 2: return n
    return fib(n-1) + fib(n-2)   # Without memoize, exponential time!

print(fib(50))   # Instant with memoize!

# Python has this built-in:
from functools import lru_cache
@lru_cache(maxsize=128)
def fib_builtin(n):
    if n < 2: return n
    return fib_builtin(n-1) + fib_builtin(n-2)

# ── Decorator with arguments ──────────────────────────────────────────────
# Need THREE levels of nesting
def retry(max_attempts=3, exceptions=(Exception,), delay=0):
    """Retry a function up to max_attempts times if it raises an exception."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for attempt in range(1, max_attempts + 1):
                try:
                    return func(*args, **kwargs)
                except exceptions as e:
                    print(f"Attempt {attempt}/{max_attempts} failed: {e}")
                    if attempt < max_attempts and delay:
                        time.sleep(delay)
            raise RuntimeError(f"All {max_attempts} attempts failed")
        return wrapper
    return decorator

@retry(max_attempts=3, exceptions=(ConnectionError,), delay=1)
def connect_to_server():
    import random
    if random.random() < 0.7:   # 70% chance of failure
        raise ConnectionError("Connection refused")
    return "Connected!"

# ── Stacking multiple decorators ─────────────────────────────────────────
# Applied bottom-up: first @memoize wraps fib, then @timer wraps that
@timer
@memoize
def expensive_fib(n):
    if n < 2: return n
    return expensive_fib(n-1) + expensive_fib(n-2)

# ── Class-based decorators ────────────────────────────────────────────────
class CountCalls:
    """Decorator that counts how many times a function is called."""
    def __init__(self, func):
        functools.update_wrapper(self, func)
        self.func = func
        self.call_count = 0

    def __call__(self, *args, **kwargs):
        self.call_count += 1
        print(f"[{self.call_count}] Calling {self.func.__name__}")
        return self.func(*args, **kwargs)

    def reset(self):
        self.call_count = 0

@CountCalls
def add(a, b):
    return a + b

add(1, 2)   # [1] Calling add
add(3, 4)   # [2] Calling add
print(add.call_count)   # 2
add.reset()
```

---

## 4.2 Context Managers

A **context manager** handles setup and teardown around a block of code — guaranteeing cleanup happens even if an exception occurs. The `with` statement uses context managers.

```python
from contextlib import contextmanager, asynccontextmanager
import time

# ── Why context managers? ────────────────────────────────────────────────
# Without context manager (fragile):
f = open("data.txt", "w")
try:
    f.write("hello")
finally:
    f.close()   # Must remember to close, even on exception

# With context manager (safe and clean):
with open("data.txt", "w") as f:
    f.write("hello")
# File automatically closed — even if an exception occurred!

# ── Class-based context manager ──────────────────────────────────────────
class Timer:
    """Time a block of code."""
    def __enter__(self):
        self.start = time.perf_counter()
        return self          # Value assigned to 'as' variable

    def __exit__(self, exc_type, exc_val, exc_tb):
        self.elapsed = time.perf_counter() - self.start
        print(f"Elapsed: {self.elapsed:.4f}s")
        return False   # Don't suppress exceptions (return True to suppress)

with Timer() as t:
    total = sum(range(1_000_000))
print(f"Sum: {total}")
# Access t.elapsed after the block if needed

# ── Generator-based context manager (simpler) ────────────────────────────
@contextmanager
def database_transaction(db_name):
    """Simulate a database transaction with commit/rollback."""
    print(f"BEGIN TRANSACTION on {db_name}")
    connection = {"db": db_name, "committed": False}
    try:
        yield connection          # Code inside 'with' block runs here
        connection["committed"] = True
        print("COMMIT")
    except Exception as e:
        print(f"ROLLBACK due to: {e}")
        raise
    finally:
        print(f"Connection to {db_name} closed")

with database_transaction("users_db") as conn:
    print(f"Inserting data into {conn['db']}")
    # If exception here → ROLLBACK, then re-raise

# ── Multiple context managers ─────────────────────────────────────────────
with open("input.txt", "r") as fin, open("output.txt", "w") as fout:
    for line in fin:
        fout.write(line.upper())

# ── Practical context managers ────────────────────────────────────────────
@contextmanager
def temp_directory():
    """Create a temporary directory and clean it up afterward."""
    import tempfile, shutil
    tmpdir = tempfile.mkdtemp()
    print(f"Created temp dir: {tmpdir}")
    try:
        yield tmpdir
    finally:
        shutil.rmtree(tmpdir)
        print(f"Deleted temp dir: {tmpdir}")

@contextmanager
def suppress_exceptions(*exception_types):
    """Suppress specified exceptions (similar to contextlib.suppress)."""
    try:
        yield
    except exception_types:
        pass   # Silently ignore

with suppress_exceptions(FileNotFoundError):
    open("nonexistent.txt")   # Would normally crash — now silently ignored
```

---

## 4.3 Dataclasses (Python 3.7+)

**Dataclasses** automatically generate boilerplate code (`__init__`, `__repr__`, `__eq__`, etc.) for classes that primarily store data. They're cleaner and less error-prone than writing these manually.

```python
from dataclasses import dataclass, field, asdict, astuple
from typing import List, Optional
import math

# ── Basic dataclass ──────────────────────────────────────────────────────
@dataclass
class Point:
    x: float
    y: float

    def distance_to(self, other: 'Point') -> float:
        return math.sqrt((self.x - other.x)**2 + (self.y - other.y)**2)

p1 = Point(1.0, 2.0)
p2 = Point(4.0, 6.0)
print(p1)                    # Point(x=1.0, y=2.0) — __repr__ auto-generated!
print(p1 == Point(1.0, 2.0)) # True — __eq__ auto-generated!
print(p1.distance_to(p2))    # 5.0

# ── Dataclass with defaults ───────────────────────────────────────────────
@dataclass
class Student:
    name: str
    age: int
    grade: float = 0.0
    # field() for mutable defaults (can't use [] directly)
    courses: List[str] = field(default_factory=list)
    is_active: bool = field(default=True)
    # Fields excluded from __repr__ or __init__
    _id: int = field(default=0, repr=False, init=False)

    def __post_init__(self):
        """Called automatically after __init__ — for validation/computed fields."""
        if self.age < 0:
            raise ValueError(f"Age cannot be negative: {self.age}")
        if not (0 <= self.grade <= 100):
            raise ValueError(f"Grade must be 0-100, got {self.grade}")
        import random
        self._id = random.randint(1000, 9999)

    def add_course(self, course: str):
        self.courses.append(course)

    @property
    def letter_grade(self) -> str:
        if self.grade >= 90: return "A"
        if self.grade >= 80: return "B"
        if self.grade >= 70: return "C"
        return "F"

s = Student("Alice", 20, 85.5)
s.add_course("Python")
s.add_course("Machine Learning")
print(s)
# Student(name='Alice', age=20, grade=85.5, courses=['Python', 'Machine Learning'], is_active=True)
print(s.letter_grade)   # B

# Convert to dict or tuple
print(asdict(s))        # {'name': 'Alice', 'age': 20, ...}
print(astuple(s))       # ('Alice', 20, 85.5, ['Python', 'Machine Learning'], True, ...)

# ── Frozen dataclass (immutable) ─────────────────────────────────────────
@dataclass(frozen=True)
class Color:
    r: int   # 0-255
    g: int
    b: int
    a: float = 1.0   # Alpha (opacity)

    def to_hex(self) -> str:
        return f"#{self.r:02x}{self.g:02x}{self.b:02x}"

    def blend(self, other: 'Color', ratio: float = 0.5) -> 'Color':
        return Color(
            int(self.r * ratio + other.r * (1-ratio)),
            int(self.g * ratio + other.g * (1-ratio)),
            int(self.b * ratio + other.b * (1-ratio)),
        )

red = Color(255, 0, 0)
blue = Color(0, 0, 255)
# red.r = 128  # ❌ FrozenInstanceError — truly immutable!
print(red.to_hex())         # #ff0000
print(red.blend(blue))      # Color(r=127, g=0, b=127) — purple!

# Frozen dataclass is hashable — can be used in sets/as dict keys
palette = {red, blue, red.blend(blue)}
```

---

## 4.4 Type Hints and Annotations

**Type hints** (Python 3.5+) are annotations that indicate the expected types of variables, parameters, and return values. They don't affect runtime but enable:
- Better IDE autocompletion and error detection
- Static analysis with tools like **mypy**, **pyright**
- Self-documenting code

```python
from typing import (
    List, Dict, Tuple, Set, Optional, Union,
    Callable, Any, Iterator, Generator, TypeVar,
    Protocol, Final, Literal, TypedDict
)

# ── Basic annotations ─────────────────────────────────────────────────────
name: str = "Alice"
age: int = 30
pi: float = 3.14
is_active: bool = True

def greet(name: str) -> str:
    return f"Hello, {name}!"

def add(a: int, b: int) -> int:
    return a + b

# ── Collection types ──────────────────────────────────────────────────────
def process(items: List[int]) -> Dict[str, int]:
    return {"sum": sum(items), "count": len(items)}

def get_coords() -> Tuple[float, float, float]:
    return (1.0, 2.0, 3.0)

# Python 3.9+: use built-in types directly (no import needed)
def greet_all(names: list[str]) -> dict[str, str]:
    return {name: f"Hello, {name}!" for name in names}

# ── Optional — can be None ─────────────────────────────────────────────
def find_user(user_id: int) -> Optional[str]:   # str or None
    users = {1: "Alice", 2: "Bob"}
    return users.get(user_id)

# Python 3.10+: use X | None
def find_user_modern(user_id: int) -> str | None:
    return None

# ── Union — multiple possible types ──────────────────────────────────────
def stringify(value: Union[int, float, str]) -> str:
    return str(value)

# Python 3.10+
def stringify_modern(value: int | float | str) -> str:
    return str(value)

# ── Callable ──────────────────────────────────────────────────────────────
def apply(func: Callable[[int, int], int], a: int, b: int) -> int:
    return func(a, b)

result = apply(lambda x, y: x + y, 3, 4)   # 7

# ── TypeVar — generic functions ───────────────────────────────────────────
T = TypeVar('T')
K = TypeVar('K')
V = TypeVar('V')

def first(lst: List[T]) -> T:
    return lst[0]

def last(lst: list[T]) -> T:
    return lst[-1]

print(first([1, 2, 3]))       # 1 — T inferred as int
print(first(["a", "b"]))     # "a" — T inferred as str

# ── Protocol — structural subtyping (duck typing) ─────────────────────────
class Drawable(Protocol):
    def draw(self) -> None: ...

class Circle:
    def draw(self) -> None:
        print("Drawing circle")

class Square:
    def draw(self) -> None:
        print("Drawing square")

def render(shape: Drawable) -> None:
    shape.draw()

# Works for any class with a draw() method — no inheritance needed!
render(Circle())   # Drawing circle
render(Square())   # Drawing square

# ── Literal — specific values only ───────────────────────────────────────
from typing import Literal
Direction = Literal["north", "south", "east", "west"]

def move(direction: Direction, steps: int) -> None:
    print(f"Moving {direction} by {steps} steps")

# ── TypedDict — typed dictionaries ───────────────────────────────────────
class UserInfo(TypedDict):
    name: str
    age: int
    email: str
    is_admin: bool

def create_user(info: UserInfo) -> str:
    return f"Created user: {info['name']}"

# ── Final — constants ──────────────────────────────────────────────────
MAX_SIZE: Final = 100
PI: Final[float] = 3.14159

# Run type checking:
# $ pip install mypy
# $ mypy your_script.py
```

---

## 4.5 Concurrency — Threading, Async, Multiprocessing

Python offers three approaches to concurrency, each for different use cases:

| Approach | Best For | Limitation |
|----------|----------|------------|
| **Threading** | I/O-bound tasks (network, file I/O) | GIL limits true parallelism |
| **AsyncIO** | I/O-bound tasks (modern, efficient) | Requires async-compatible code |
| **Multiprocessing** | CPU-bound tasks (math, image processing) | Higher overhead, IPC needed |

```python
import threading
import asyncio
import multiprocessing
import time
from concurrent.futures import ThreadPoolExecutor, ProcessPoolExecutor

# ── Threading ────────────────────────────────────────────────────────────
def download_file(filename, delay=2):
    print(f"  Starting: {filename}")
    time.sleep(delay)   # Simulate I/O wait
    print(f"  Done: {filename}")
    return f"{filename}_content"

# Sequential: 6 seconds total
# for f in ["file1.txt", "file2.txt", "file3.txt"]:
#     download_file(f)

# Threaded: ~2 seconds total
threads = []
for f in ["file1.txt", "file2.txt", "file3.txt"]:
    t = threading.Thread(target=download_file, args=(f,), name=f"Thread-{f}")
    threads.append(t)
    t.start()

for t in threads:
    t.join()   # Wait for all to finish

# Thread with return value (use list to collect results)
results = []
lock = threading.Lock()

def fetch_and_store(url, results_list):
    data = f"data from {url}"   # Simulate fetch
    with lock:                   # Thread-safe access to shared resource
        results_list.append(data)

# ThreadPoolExecutor — easier thread management
with ThreadPoolExecutor(max_workers=5) as executor:
    futures = [executor.submit(download_file, f) for f in ["a", "b", "c", "d", "e"]]
    results = [f.result() for f in futures]

# ── AsyncIO — modern concurrency ─────────────────────────────────────────
async def fetch_url(url: str, session_id: int) -> str:
    """Simulate an async HTTP request."""
    print(f"  [{session_id}] Fetching {url}")
    await asyncio.sleep(1)   # Non-blocking sleep (other tasks run during this!)
    return f"Response from {url}"

async def main_async():
    urls = [f"https://api.example.com/{i}" for i in range(5)]

    # Run all concurrently
    results = await asyncio.gather(*[fetch_url(url, i) for i, url in enumerate(urls)])
    print(f"Got {len(results)} responses in ~1 second!")
    return results

# Run the async main function
asyncio.run(main_async())   # All 5 URLs fetched concurrently in ~1s (not 5s)

# Async with context manager and semaphore (rate limiting)
async def limited_fetch():
    semaphore = asyncio.Semaphore(3)   # Max 3 concurrent requests

    async def fetch_with_limit(url):
        async with semaphore:
            await asyncio.sleep(0.5)   # Simulate request
            return f"data:{url}"

    urls = [f"/api/{i}" for i in range(10)]
    return await asyncio.gather(*[fetch_with_limit(url) for url in urls])

# ── Multiprocessing — true parallelism ──────────────────────────────────
def cpu_intensive(n):
    """CPU-bound work: compute sum of squares."""
    return sum(i * i for i in range(n))

if __name__ == "__main__":   # REQUIRED on Windows for multiprocessing!
    numbers = [10**7] * 4    # 4 large computations

    # Sequential
    start = time.time()
    results = [cpu_intensive(n) for n in numbers]
    print(f"Sequential: {time.time()-start:.2f}s")

    # Parallel (uses all CPU cores)
    start = time.time()
    with ProcessPoolExecutor(max_workers=4) as executor:
        results = list(executor.map(cpu_intensive, numbers))
    print(f"Parallel: {time.time()-start:.2f}s")   # ~4x faster!
```

---

# Level 5 — Expert (Mastery)

## 5.1 Metaclasses

A **metaclass** is "the class of a class". Just as objects are instances of classes, classes are instances of metaclasses. The default metaclass is `type`. Metaclasses let you customize class creation.

```python
# type() can create classes dynamically:
Dog = type("Dog", (object,), {"species": "Canis familiaris", "bark": lambda self: "Woof!"})
d = Dog()
print(d.bark())   # Woof!

# ── Custom metaclass ──────────────────────────────────────────────────────
class SingletonMeta(type):
    """Metaclass that makes any class a Singleton."""
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Database(metaclass=SingletonMeta):
    def __init__(self, host="localhost"):
        self.host = host
        print(f"Connecting to {host}")

db1 = Database("production-db")   # "Connecting to production-db"
db2 = Database("another-host")    # No output — same instance returned!
print(db1 is db2)   # True

# ── Auto-registration metaclass ───────────────────────────────────────────
class PluginMeta(type):
    """Automatically register all subclasses."""
    registry = {}

    def __init__(cls, name, bases, namespace):
        super().__init__(name, bases, namespace)
        if bases:   # Skip the base class itself
            PluginMeta.registry[name] = cls

class Plugin(metaclass=PluginMeta):
    """Base class for all plugins."""
    def run(self): raise NotImplementedError

class EmailPlugin(Plugin):
    def run(self): print("Sending email...")

class SMSPlugin(Plugin):
    def run(self): print("Sending SMS...")

class PushNotificationPlugin(Plugin):
    def run(self): print("Sending push notification...")

# All subclasses automatically registered!
print(PluginMeta.registry)
# {'EmailPlugin': <class>, 'SMSPlugin': <class>, 'PushNotificationPlugin': <class>}

# Use them
for name, plugin_cls in PluginMeta.registry.items():
    plugin_cls().run()
```

---

## 5.2 Design Patterns

Design patterns are proven, reusable solutions to common programming problems:

```python
from abc import ABC, abstractmethod
from typing import List, Callable

# ── Singleton ─────────────────────────────────────────────────────────────
class Config:
    _instance = None
    _settings = {}

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

    def set(self, key, value):
        self._settings[key] = value

    def get(self, key, default=None):
        return self._settings.get(key, default)

cfg1 = Config()
cfg2 = Config()
cfg1.set("debug", True)
print(cfg2.get("debug"))    # True — same object!
print(cfg1 is cfg2)         # True

# ── Factory ───────────────────────────────────────────────────────────────
class Animal(ABC):
    @abstractmethod
    def speak(self) -> str: ...

class Dog(Animal):
    def speak(self): return "Woof!"

class Cat(Animal):
    def speak(self): return "Meow!"

class Bird(Animal):
    def speak(self): return "Tweet!"

class AnimalFactory:
    _creators = {"dog": Dog, "cat": Cat, "bird": Bird}

    @classmethod
    def register(cls, animal_type: str, animal_class):
        cls._creators[animal_type] = animal_class

    @classmethod
    def create(cls, animal_type: str) -> Animal:
        creator = cls._creators.get(animal_type.lower())
        if not creator:
            raise ValueError(f"Unknown animal: {animal_type}")
        return creator()

dog = AnimalFactory.create("dog")
print(dog.speak())   # Woof!

# ── Observer (Event System) ───────────────────────────────────────────────
class EventEmitter:
    def __init__(self):
        self._listeners: dict[str, List[Callable]] = {}

    def on(self, event: str, callback: Callable):
        self._listeners.setdefault(event, []).append(callback)
        return self   # Allow chaining

    def off(self, event: str, callback: Callable):
        if event in self._listeners:
            self._listeners[event].remove(callback)

    def emit(self, event: str, *args, **kwargs):
        for cb in self._listeners.get(event, []):
            cb(*args, **kwargs)

# Usage
app = EventEmitter()

def on_login(user): print(f"Welcome, {user}!")
def log_login(user): print(f"[LOG] {user} logged in at {__import__('datetime').datetime.now():%H:%M}")

app.on("login", on_login).on("login", log_login)
app.emit("login", "Alice")
# Welcome, Alice!
# [LOG] Alice logged in at 13:45

# ── Strategy ──────────────────────────────────────────────────────────────
class Sorter:
    def __init__(self, strategy: Callable):
        self._strategy = strategy

    def sort(self, data: list) -> list:
        return self._strategy(data)

    def set_strategy(self, strategy: Callable):
        self._strategy = strategy

# Different sorting strategies
def bubble_sort(data):
    arr = data.copy()
    n = len(arr)
    for i in range(n):
        for j in range(n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

def merge_sort(data):
    if len(data) <= 1: return data
    mid = len(data) // 2
    left = merge_sort(data[:mid])
    right = merge_sort(data[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i]); i += 1
        else:
            result.append(right[j]); j += 1
    return result + left[i:] + right[j:]

sorter = Sorter(merge_sort)
print(sorter.sort([5, 2, 8, 1, 9]))   # [1, 2, 5, 8, 9]
sorter.set_strategy(sorted)            # Switch strategy at runtime
print(sorter.sort([5, 2, 8, 1, 9]))   # [1, 2, 5, 8, 9]
```

---

## 5.3 Testing with pytest

**Testing** is the practice of verifying your code works as expected. Good tests give you confidence to refactor and extend code without breaking things.

```python
# ── File: calculator.py ──────────────────────────────────────────────────
def add(a, b): return a + b
def subtract(a, b): return a - b
def multiply(a, b): return a * b

def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero")
    return a / b

def factorial(n):
    if not isinstance(n, int) or n < 0:
        raise ValueError(f"n must be a non-negative integer, got {n}")
    if n == 0: return 1
    return n * factorial(n - 1)


# ── File: test_calculator.py ─────────────────────────────────────────────
import pytest

class TestAdd:
    def test_positive_numbers(self):
        assert add(2, 3) == 5

    def test_negative_numbers(self):
        assert add(-1, -2) == -3

    def test_mixed(self):
        assert add(-5, 3) == -2

    def test_floats(self):
        assert abs(add(0.1, 0.2) - 0.3) < 1e-10   # float comparison!

class TestDivide:
    def test_normal(self):
        assert divide(10, 2) == 5.0

    def test_fractional(self):
        assert divide(7, 2) == 3.5

    def test_zero_divisor(self):
        with pytest.raises(ZeroDivisionError, match="Cannot divide by zero"):
            divide(10, 0)

# Parametrized tests — same test, multiple inputs
@pytest.mark.parametrize("a, b, expected", [
    (0, 0, 0),
    (1, 1, 2),
    (-1, 1, 0),
    (100, 200, 300),
    (1.5, 2.5, 4.0),
])
def test_add_parametrized(a, b, expected):
    assert add(a, b) == expected

# Fixtures — reusable test setup
@pytest.fixture
def sample_numbers():
    return [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

def test_sum_of_numbers(sample_numbers):
    assert sum(sample_numbers) == 55

def test_max_of_numbers(sample_numbers):
    assert max(sample_numbers) == 10

# Mocking — replace external dependencies with fake objects
from unittest.mock import Mock, patch, MagicMock

def get_user_from_api(user_id):
    import requests
    response = requests.get(f"https://api.example.com/users/{user_id}")
    return response.json()

@patch("requests.get")
def test_get_user(mock_get):
    # Set up the mock
    mock_get.return_value.json.return_value = {"id": 1, "name": "Alice"}
    mock_get.return_value.status_code = 200

    result = get_user_from_api(1)

    assert result["name"] == "Alice"
    mock_get.assert_called_once_with("https://api.example.com/users/1")

# Run tests:
# pip install pytest
# pytest test_calculator.py -v
# pytest test_calculator.py -v --tb=short   # Shorter tracebacks
# pytest test_calculator.py -k "test_add"   # Run only matching tests
# pytest --cov=calculator test_calculator.py  # Coverage report
```

---

## 🏆 Practice Projects by Level

| Level | Project | Key Concepts |
|-------|---------|-------------|
| **Beginner** | Calculator (CLI) | Variables, input/output, operators, if-else |
| **Beginner** | Number Guessing Game | while loops, random, conditionals |
| **Beginner** | Temperature Converter | Functions, arithmetic, f-strings |
| **Elementary** | Contact Book | Dicts, lists, file I/O, CRUD operations |
| **Elementary** | To-Do List (with file save) | File handling, lists, functions |
| **Elementary** | Simple Quiz App | Loops, dicts, scoring logic |
| **Intermediate** | Student Grade Manager | OOP, file I/O, error handling, CSV |
| **Intermediate** | Web Scraper | `requests`, `BeautifulSoup`, regex |
| **Intermediate** | CLI Budget Tracker | OOP, JSON persistence, date handling |
| **Advanced** | REST API Client (async) | `asyncio`, `aiohttp`, type hints, decorators |
| **Advanced** | Mini ORM (Object-Relational Mapper) | Metaclasses, descriptors, `sqlite3` |
| **Expert** | Plugin Framework | Metaclasses, ABCs, dynamic loading |
| **Expert** | Async Web Crawler | Async generators, semaphores, recursion |
| **Expert** | Testing Framework | Metaclasses, decorators, introspection |

---

## 📚 Recommended Learning Path

```
Week 1-2:   Level 1 — Variables, types, operators, strings, I/O
Week 3-4:   Level 2 — Conditionals, loops, lists, dicts, functions
Week 5-7:   Level 3 — OOP, error handling, files, modules, regex
Week 8-10:  Level 4 — Decorators, type hints, async, dataclasses
Week 11-14: Level 5 — Metaclasses, design patterns, testing, performance
```

| Resource | Type | Best For |
|----------|------|----------|
| [Python Docs](https://docs.python.org/3/) | Official Docs | Reference |
| [Real Python](https://realpython.com/) | Tutorials | All levels |
| [Fluent Python — Luciano Ramalho](https://www.oreilly.com/library/view/fluent-python/) | Book | Advanced |
| [Python Cookbook — Beazley](https://www.oreilly.com/library/view/python-cookbook/) | Book | Intermediate |
| [LeetCode](https://leetcode.com/) | Practice | Algorithms |
| [HackerRank Python](https://www.hackerrank.com/domains/python) | Practice | All levels |

> [!TIP]
> **The Learning Loop**: Read a concept → Type it out by hand → Modify the example → Break it on purpose → Fix it → Build a mini project using it. This cycle is how real developers learn.

> [!IMPORTANT]
> **Practice over Passivity**: You cannot learn programming by just reading. For every hour you read, spend 3 hours coding. Start small projects from day one — even imperfect ones teach you more than perfect tutorials.

---

*🐍 Happy Coding! The journey from beginner to expert is measured in lines of code written, not hours of tutorials watched.*

