# Introduction to Data Analysis Using Python
## Module 3 — Loops and Strings

---

## Module 3 Overview

In this module you will learn:
- **While loops** — repeat code based on a condition
- **For loops** — iterate over a sequence of values
- **Strings** — concatenation, indexing, slicing, formatting
- **range()** function — generate sequences of numbers

---

## Loops

### Key Terms
- **Loop** — a block of code used to carry out iterations
- **Iteration** — the repeated execution of a set of statements
- **Iterable** — an object that's looped (iterated) over

---

## While Loops

### What is a While Loop?
- A loop that instructs the computer to **continuously execute code based on the value of a condition**
- Similar to an `if` statement, but the body can execute **multiple times** instead of just once
- The condition must evaluate to **True or False**

### Basic Syntax

```python
while condition:
    # code block to execute
```

### Example

```python
x = 0
while x < 5:
    print("The value of x is", x)
    x += 1       # shortcut for x = x + 1

print("Final value:", x)
```

Output:
```
The value of x is 0
The value of x is 1
The value of x is 2
The value of x is 3
The value of x is 4
Final value: 5
```

> `x += 1` is a shortcut for `x = x + 1` — they mean the same thing

### Infinite Loops
- If you forget to increment the variable, the loop **never stops**
- To break out of an infinite loop in Jupyter: click the **Stop button**, go to **Kernel → Interrupt**, or press **i twice** in command mode

### break and continue

| Keyword | What It Does |
|---------|-------------|
| `break` | Exits the loop immediately without triggering any `else` that follows |
| `continue` | Skips the rest of the current iteration and goes back to the condition check |

### Example with break

```python
x = 1
i = 0
while x < 100:
    if i == 5:
        break
    print(i, x)
    x = x * 2
    i += 1
```

### When to Use While Loops
- When you want to **repeat an action until a Boolean condition changes**
- When you don't know in advance how many iterations are needed

---

## For Loops

### What is a For Loop?
- A loop that **iterates over a sequence of values**
- Executes the body the same number of times as there are elements in the iterable

### Basic Syntax

```python
for item in iterable_sequence:
    # code block to execute for each value
```

### Simple Example

```python
for x in range(5):
    print(x)
```

Output: `0, 1, 2, 3, 4`

### The range() Function
- Returns a sequence of numbers starting from zero, incrementing by 1, stopping before the given number
- Has three parameters: **start, stop, step**

| Usage | Result |
|-------|--------|
| `range(3)` | 0, 1, 2 |
| `range(2, 5)` | 2, 3, 4 |
| `range(2, 11, 2)` | 2, 4, 6, 8, 10 |

> The **stop value is NOT included** in the range. To include 100, use `range(0, 101)`

### Example — Factorial of 9

```python
product = 1
for n in range(1, 10):
    product = product * n
print(product)
```

Output: `362880`

### Example — Temperature Conversion Table

```python
def convert_fahrenheit(x):
    return (x - 32) * 5 / 9

for temp in range(0, 101, 10):
    print(temp, convert_fahrenheit(temp))
```

### Nested Loops
- A loop inside another loop
- Used to iterate over nested structures (e.g. list of lists)

```python
students = [['Igor', 'Sokolov'], ['Riko', 'Miyazaki'], ['Tuva', 'Johansen']]
for student in students:
    for name in student:
        print(name)
    print()
```

### When to Use For Loops
- When there's a **sequence of elements** to iterate over
- Better for looping over a variable or record in a dataset
- Improves **readability** of your code

### For vs While — Quick Guide

| Use | Loop Type |
|-----|-----------|
| Iterating over a sequence of known length | `for` loop |
| Repeating until a condition changes | `while` loop |
| Either works | Use whichever you prefer |

---

## Strings

### What is a String?
- A **sequence of characters and punctuation** that contains textual information
- An **immutable** data type — values can never be altered or updated

### String Concatenation
- **Concatenate** = to link or join strings together
- Use the `+` operator

```python
"Hello" + " " + "world"   # "Hello world"
greeting1 = "Hello"
greeting2 = "world"
print(greeting1 + " " + greeting2)
```

- Use `*` to repeat a string:

```python
"Danger! " * 3   # "Danger! Danger! Danger! "
```

- Cannot use `-` or `/` on strings — will throw an error

### Escape Characters
- **Escape character** = a character that changes the typical behavior of the characters that follow it
- Use backslash `\`

| Escape Sequence | Meaning |
|----------------|---------|
| `\"` | Include double quote inside string |
| `\'` | Include single quote inside string |
| `\n` | New line |
| `\\` | Include backslash as a character |

```python
print("She said \"hello\"")   # She said "hello"
print("Line 1\nLine 2")       # prints on two lines
```

---

## String Indexing

### What is Indexing?
- A way to refer to **individual items** within an iterable by their relative position
- Python uses **zero-based indexing** — the first character is at index 0

```python
name = "Jolene"
print(name[0])   # J
print(name[5])   # e
print(name[-1])  # e  (last character)
print(name[-2])  # n  (second to last)
```

> Trying to access an index out of range returns an **IndexError**

### The index() Method
- Returns the index number of the **first occurrence** of a character or substring

```python
pets = "cats and dogs"
pets.index("s")    # returns 3
pets.index("z")    # ValueError — not found
```

---

## String Slicing

### What is Slicing?
- Accessing a **range of elements** from a sequence
- Also called a **substring** or **string slice**
- Use square brackets with two indices separated by a colon

```python
"orange"[1:4]    # "ran" (indices 1, 2, 3 — stop index NOT included)
"pineapple"[:4]  # "pine" (from start to index 3)
"pineapple"[4:]  # "apple" (from index 4 to end)
```

> Starting index is **inclusive**, stopping index is **exclusive**

### Checking if Substring Exists

```python
"apple" in "pineapple"    # True
"banana" in "pineapple"   # False
```

---

## String Formatting

### The format() Method
- Formats and inserts specific substrings into designated places within a larger string
- Uses `{}` curly braces as placeholders

```python
name = "Manar"
number = 42
print("Hello, {}! Your number is {}.".format(name, number))
```

### Named Keywords

```python
print("{name} has number {num}.".format(name="Manar", num=42))
```

### Index-Based Insertion

```python
print("{1}, {0}".format("World", "Hello"))   # "Hello, World"
```

### F-Strings (Python 3.6+)
- **Literal string interpolation** — faster and cleaner syntax
- Start with `f` before the string

```python
var_a = 1
var_b = 2
print(f'{var_a} + {var_b} = {var_a + var_b}')
```

### Float Formatting

```python
num = 8.2925
print(f'{num:.2f}')    # 8.29 (2 decimal places)
print(f'{num:.0f}')    # 8 (no decimal places)
```

| Format Code | Meaning |
|-------------|---------|
| `.2f` | Fixed-point, 2 decimal places |
| `.3e` | Scientific notation, 3 decimal places |
| `.4%` | Percentage, 4 decimal places |

### Useful String Methods

| Method | What It Does |
|--------|-------------|
| `str.count(sub)` | Count occurrences of substring |
| `str.find(sub)` | Return lowest index of substring (-1 if not found) |
| `str.join(iterable)` | Join strings in iterable with separator |
| `str.replace(old, new)` | Replace occurrences of old with new |
| `str.split(sep)` | Split string into list using separator |
| `str.partition(sep)` | Split at first occurrence of sep, return 3-tuple |

### Regular Expressions (Regex)
- Advanced technique for searching and modifying strings using **pattern matching**
- Import the `re` module first
- Used in: web scraping, text processing, data cleaning

```python
import re
my_string = 'Three sad tigers swallowed wheat in a wheat field'
re.search('wall', my_string)   # finds 'wall' at indices 18-22
```

---

## Module 3 Glossary

| Term | Definition |
|------|-----------|
| **break** | A keyword that lets a user escape a loop without triggering any else statement |
| **Concatenate** | To link or join strings together |
| **Escape character** | A character that changes the typical behavior of the characters that follow it |
| **For loop** | A piece of code that iterates over a sequence of values |
| **format()** | A string method that formats and inserts specific substrings into designated places within a larger string |
| **index()** | A string method that outputs the index number of a character in a string |
| **Indexing** | A way to refer to individual items within an iterable by their relative position |
| **Iterable** | An object that's looped or iterated over |
| **Iteration** | The repeated execution of a set of statements |
| **Loop** | A block of code used to carry out iterations |
| **range()** | A Python function that returns a sequence of numbers starting from zero, incrementing by 1 by default, stopping before the given number |
| **String slice** | A portion of a string that can contain more than one character; also called a substring |
| **While loop** | A loop that instructs the computer to continuously execute code based on the value of a condition |

---

## Quiz — While Loops

**Q1: Fill in the blank: A while loop instructs your computer to continuously execute your code based on the value of a _____.**
- ✅ **condition**
- comparator
- data type
- function

**Q2: A data professional wants to set up a while loop that will iterate as long as x is less than 7. They assign the value 0 to x. What code should they write next?**
- ✅ **while x < 7:**
- iterate x < 7:
- repeat x < 7:
- loop x < 7:

**Q3: In Python, the keyword break lets you escape a loop without triggering any else statement that follows it in the loop.**
- ✅ **True**
- False

---

## Quiz — For Loops

**Q1: A data professional can use a for loop to perform which of the following tasks?**
- ✅ **To iterate over a series of numbers**
- To convert one data type to another
- To repeat a specific block of code until a condition is met
- To define a function

**Q2: A data professional writes `for x in range(3):`. What values will x take?**
- ✅ **0, 1, and 2**
- Only 3
- 0, 1, 2, and 3
- 1, 2, and 3

**Q3: What parameter of Python's range() function specifies the size of the increments in a sequence of numbers?**
- Stop value
- Start value
- ✅ **Step value**
- Loop value

---

## Quiz — Strings (Indexing & Slicing)

**Q1: In Python, what is the term for the portion of a string that can contain more than one character? (Select all that apply)**
- Superstring
- String segment
- ✅ **Substring**
- ✅ **String slice**

**Q2: If you're reading from left to right, what is the index of the first character in a string?**
- ✅ **0**
- 1
- 2
- 3

**Q3: A data professional wants to insert specific substrings in a larger string. What method can they use?**
- print()
- type()
- range()
- ✅ **format()**

---

## Graded Quiz — Module 3

**Q1: In Python, what method works by interpreting a string as a sequence of characters, where each character has a numbered slot?**
- range()
- type()
- format()
- ✅ **index()**

**Q2: A data professional assigns the string 'spinach and asparagus' to the variable vegetables. What code finds the index of 'c'?**
- index.vegetables('c')
- index.spinach('c')
- ✅ **vegetables.index('c')**
- spinach.index('c')

**Q3: What would the output be when you execute `namer(Anya, Jankowski, 27)` given the function `f'Name: {last}, {first} \nAge: {age}'`?**
- ✅ **Name: Jankowski, Anya / Age: 27**
- Name: Anya Jankowski / Age: 27
- Name: Jankowski, Anya \nAge: 27
- Name: {Jankowski}, {Anya}, \nAge: {27}

**Q4: Fill in the blank: The Python _____ function returns a sequence of numbers starting from zero, incrementing by one by default, stopping before the given number.**
- index()
- type()
- format()
- ✅ **range()**

**Q5: A data professional assigns the string 'football' to the variable sport. What Python code will return the slice 'ball'?**
- sport[-1]
- ✅ **sport[4: ]**
- sport[ :4]
- sport[1:4]

**Q6: Fill in the blank: A data professional can use the format() method to insert specific _____ in a larger string.**
- while loops
- for loops
- libraries
- ✅ **substrings**

**Q7: What type of loop can a data professional use to repeat a specific block of code until a condition is no longer met?**
- if loop
- for loop
- ✅ **while loop**
- else loop

**Q8: What Python code can a data professional use to concatenate the strings 'air' and 'plane'?**
- 'air' % 'plane'
- 'air' == 'plane'
- 'air' / 'plane'
- ✅ **'air' + 'plane'**

**Q9: A data professional writes `for x in range(100, 501, 20):`. What is the step value?**
- ✅ **20**
- 100
- 500
- 501

**Q10: What Python code instructs the computer to loop through values from 20 to 90 (inclusive)?**
- ✅ **for x in range(20, 91):**
- for x in range(21, 90):
- for x in range(20, 90):
- for x in range(21, 91):
---
