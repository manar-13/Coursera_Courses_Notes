# Introduction to Data Analysis Using Python
## Module 2 — Functions and Conditional Statements

---

## Module 2 Overview

In this module you will learn:
- **Functions** — reusable chunks of code to perform specific tasks
- **Clean code** — reusability and modularity
- **Commenting** — documenting your workflow
- **Operators** — comparators and logical operators
- **Conditional statements** — if, else, elif

---

## Functions

### What is a Function?
- A **function** is a body of reusable code for performing specific processes or tasks
- Functions are like the **verbs** of a programming language — they perform actions
- You can call a function at any time to perform useful actions on your data (sorting, classifying, summarizing, etc.)

### Built-in Python Functions

| Function | What It Does |
|----------|-------------|
| `print()` | Writes text on the screen |
| `type()` | Returns the data type of a variable |
| `str()` | Converts an object into a string |
| `len()` | Returns the length of an object |
| `sum()` | Returns the sum of items |

> In Python 3, `print` is a function and **requires parentheses**, even when empty.

### How to Define a Function

```python
def my_function(parameters):
    '''
    Docstring.
    Summarize the function's behavior and explain its arguments and return values.
    '''
    # code block

    return value
```

**Rules:**
- Start with the keyword `def`
- Follow with the function name (use **snake_case** — lowercase words separated by underscores)
- Put parameters inside parentheses, then add a colon `:`
- Indent the body **4 spaces**
- End with a `return` or `print` statement

### Example — Simple Function

```python
def greeting(name):
    print("Welcome", name)
    print("You are part of the team.")

greeting("Rebecca")
```

Output:
```
Welcome Rebecca
You are part of the team.
```

### The `return` Keyword

- `return` saves the result of a function for **later use**
- `print` just displays something on screen — you can't use that value later

> **Analogy:** `return` is like your brother going to the market and **bringing you back potatoes**. `print` is like your brother going to the market, coming home, and **telling you what potatoes were for sale** — but you have no potatoes.

### Example — Function with return

```python
def triangle_area(base, height):
    return base * height / 2

area1 = triangle_area(5, 3)
area2 = triangle_area(10, 4)
total_area = area1 + area2
```

### Example — get_seconds Function

```python
def get_seconds(hours, minutes, seconds):
    total_seconds = hours * 3600 + minutes * 60 + seconds
    return total_seconds

get_seconds(16, 45, 20)
```

Output: `60320`

### Functions vs Methods

| | Function | Method |
|-|----------|--------|
| **Belongs to** | No specific class — can be used on multiple types | A specific class |
| **How to call** | `function_name(argument)` | `object.method_name()` |
| **Example** | `sum([6, 3])` | `my_string.split()` |

---

## Clean Code — Reusability and Modularity

### Reusability
- **Reusability** = defining code once and using it many times without rewriting it
- When you find **duplicated code** in your scripts, convert it into a function
- Functions make code reusable — call it as many times as needed with different inputs

### Modularity
- **Modularity** = the ability to write code in separate components that work together and can be reused for other programs
- Modularity allows data professionals to **reuse code** for other programs
- Helps collaborate with data engineers on larger projects without starting from scratch

### Refactoring
- **Refactoring** = restructuring code while maintaining its original functionality
- Part of creating **self-documenting code**
- **Self-documenting code** = code written in a way that is readable and makes its purpose clear

> Benefits of clean, modular, reusable code: reduces errors, enhances teamwork, builds trust, saves time

---

## Commenting

### What is a Comment?
- A line starting with `#` — the computer **ignores** everything after `#` on that line
- Comments are for **humans reading the code**, not the computer

### Why Use Comments?
- Provide helpful explanations
- Outline the steps of a process
- Document your work for teammates
- Help you think through your logic before writing code

### Comments as Scaffolding
- Write comments **before** writing the actual code
- Break the problem into small, logical steps using comments first
- Then fill in the code step by step

### Example — Seed Calculator with Comments

```python
def seed_calculator(fountain_side, grass_width):
    '''
    Calculate the number of kilograms of grass seed needed
    for a border around a square fountain.

    Args:
        fountain_side: float, length of one side of the fountain in meters
        grass_width: float, width of the grass border in meters

    Returns:
        seed: float, amount of grass seed needed in kilograms
    '''
    # Find the area of the fountain
    fountain_area = fountain_side ** 2

    # Calculate the total area (fountain + border)
    total_area = (fountain_side + 2 * grass_width) ** 2

    # Calculate the area of just the grass border
    grass_area = total_area - fountain_area

    # Calculate the amount of seed needed (35g per square meter)
    seed_grams = grass_area * 35

    # Convert grams to kilograms
    seed = seed_grams / 1000

    return seed
```

### Docstrings
- A **docstring** is a string at the beginning of a function's body that summarizes the function's behavior
- Written between **three quotation marks** `'''` or `"""`
- Should describe: what the function does, its parameters, and its return value
- Written in the form of a **command** (e.g., "Calculate the area" not "Calculates the area")

---

## Operators

### What are Operators?
- **Operators** are characters that enact specific arithmetic, logical actions, or processes

### Comparators
- **Comparators** are operators that compare two values and produce **Boolean values** (True or False)
- **Boolean** = a data type with only two possible values: `True` or `False` (named after George Boole)

| Operation | Operator |
|-----------|---------|
| Greater than | `>` |
| Greater than or equal to | `>=` |
| Less than | `<` |
| Less than or equal to | `<=` |
| Equal to | `==` |
| Not equal to | `!=` |

> `=` (single equals) is for **assignment** only. Using it for comparison returns a SyntaxError.
> Comparing incompatible data types (e.g. string vs integer) returns a TypeError.

### Logical Operators
- **Logical operators** connect multiple statements and perform more complex comparisons

| Operator | What It Does |
|----------|-------------|
| `and` | Returns `True` only if **both** statements are true |
| `or` | Returns `True` if **either** statement is true. `False` only when both are false |
| `not` | **Inverts** the value — True becomes False, False becomes True |

### Examples

```python
print(10 > 1)           # True
print("cat" == "dog")   # False
print(1 != 2)           # True

# and — both must be true
print("yellow" > "cyan" and "brown" > "magenta")  # False

# or — either can be true
print(25 > 50 or 1 != 2)  # True

# not — inverts the result
print(not 42 == "Answer")  # True
```

### Arithmetic Operators

| Operation | Operator | Example | Output |
|-----------|---------|---------|--------|
| Addition | `+` | `5 + 2` | `7` |
| Subtraction | `-` | `5 - 2` | `3` |
| Multiplication | `*` | `5 * 2` | `10` |
| Division | `/` | `5 / 2` | `2.5` |
| Modulo (remainder) | `%` | `5 % 2` | `1` |
| Exponentiation | `**` | `5 ** 2` | `25` |
| Floor division | `//` | `5 // 2` | `2` |

### The Modulo Operator
- Returns the **remainder** when one number is divided by another
- Even numbers divided by 2 always have a remainder of **0**
- Used to check if a number is even: `x % 2 == 0`

---

## Conditional Statements (Branching)

### What is Branching?
- **Branching** = the ability of a program to alter its execution sequence
- Uses `if`, `elif`, and `else` statements based on conditions

### if Statement
- Executes code **only when the condition is True**
- If condition is False, the indented code is skipped

```python
if condition:
    # code runs only if condition is True
```

### else Statement
- Executes when the **preceding `if` condition is False**

```python
if condition:
    # runs if True
else:
    # runs if False
```

### elif Statement
- Short for **else-if**
- Checks additional conditions when previous ones are False
- You can have an **unlimited number** of `elif` statements

```python
if condition1:
    # runs if condition1 is True
elif condition2:
    # runs if condition1 is False AND condition2 is True
else:
    # runs if ALL above conditions are False
```

### Full Example — Username Validation

```python
def validate_username(username):
    if len(username) < 8:
        print("Invalid: username must be at least 8 characters.")
    elif len(username) > 15:
        print("Invalid: username must be no more than 15 characters.")
    else:
        print("Valid username!")
```

### Key Rules for Conditional Statements
- `elif` and `else` are **optional**
- You can have **multiple** `elif` statements
- You can only have **one** `else`, and only at the **end**
- Conditions must evaluate to `True` or `False`
- **Indentation matters** — 4 spaces is the convention. Indentation mistakes are one of the most common causes of unexpected behavior

### Omitting else
Sometimes `else` is not needed:

```python
# With else (works fine)
def greater_than_ten(x):
    if x > 10:
        return True
    else:
        return False

# Without else (same result, cleaner)
def greater_than_ten(x):
    if x > 10:
        return True
    return False
```

---

## Module 2 Glossary

| Term | Definition |
|------|-----------|
| **Algorithm** | A set of instructions for solving a problem or accomplishing a task |
| **Boolean** | A data type with only two possible values: True or False |
| **Branching** | The ability of a program to alter its execution sequence |
| **Comparator** | An operator that compares two values and produces Boolean values |
| **def** | A keyword that defines a function at the start of the function block |
| **Docstring** | A string at the beginning of a function's body that summarizes its behavior and explains arguments and return values |
| **elif** | A reserved keyword that executes subsequent conditions when previous conditions are not true |
| **else** | A reserved keyword that executes when preceding conditions evaluate as False |
| **Function** | A body of reusable code for performing specific processes or tasks |
| **if** | A reserved keyword that sets up a condition in Python |
| **Logical operator** | An operator that connects multiple statements and performs complex comparisons |
| **Modularity** | The ability to write code in separate components that work together and can be reused |
| **Modulo** | An operator that returns the remainder when one number is divided by another |
| **Refactoring** | The process of restructuring code while maintaining its original functionality |
| **return** | A reserved keyword that makes a function produce new results saved for later use |
| **Reusability** | The capability to define code once and use it many times without rewriting it |
| **Self-documenting code** | Code written in a way that is readable and makes its purpose clear |

---

## Quiz — Functions and Clean Code

**Q1: A data professional wants to define their own Python function. What keyword should they use at the start of the function block?**
- return
- ✅ **def**
- for
- with

**Q2: Modularity is the ability to write code in separate components that work together.**
- ✅ **True**
- False

> Modularity allows data professionals to reuse code for other programs.

**Q3: Why do data professionals use comments for their Python code? (Select all that apply)**
- ✅ **To provide helpful explanations**
- ✅ **To outline the steps of a process**
- To execute code
- ✅ **To document their work for teammates**

---

## Quiz — Operators and Conditional Statements

**Q1: Fill in the blank: Comparators are operators that compare two values and produce _____ values.**
- float
- ✅ **boolean**
- integer
- string

**Q2: When comparing two expressions, what logical operator requires both expressions to be true to return a True result?**
- ✅ **and**
- or
- not
- with

**Q3: Which of the following is a reserved keyword that sets up a condition in Python?**
- ✅ **if**
- with
- else
- as

**Q4: The elif keyword only works when there are exactly two possible conditions in the code.**
- True
- ✅ **False**

> The `elif` keyword allows for an **unlimited** number of comparison cases.

---

## Graded Quiz — Module 2

**Q1: In Python, when does an else statement execute a piece of code?**
- When the if statement contains numeric data
- When the if statement contains text data
- When the if statement contains a true condition
- ✅ **When the if statement contains a false condition**

**Q2: In Python, what is the process of restructuring code while maintaining its original functionality?**
- ✅ **Refactoring**
- Branching
- Reprogramming
- Converting

**Q3: A data professional wants to define a function to calculate the area of a rectangle. What code should they begin with?**
- return area_rectangle(length, width):
- ✅ **def area_rectangle(length, width):**
- if area_rectangle(length, width):
- else area_rectangle(length, width):

**Q4: A data professional wants to make a Python function produce new results and save the results for later use. What keyword should they use?**
- ✅ **return**
- if
- and
- else

**Q5: What are best practices for writing clean code? (Select all that apply)**
- ✅ **Modularity**
- ✅ **Clarity**
- ✅ **Reusability**
- Redundancy

**Q6: What is the Python comparator for less than or equal to?**
- ==
- >=
- !=
- ✅ **<=**

**Q7: In Python, when does an if statement execute a piece of code?**
- ✅ **When the condition evaluates to True**
- When the condition evaluates to False
- When the condition evaluates to Not Equal
- When the condition evaluates to Equal

**Q8: Which code block(s) will yield results identical to the following function? (Select all that apply)**

Original:
```python
def is_even(x):
    if x % 2 == 0:
        return True
    else:
        return False
```

- ✅
```python
def is_even(x):
    if x % 2 != 0:
       return False
    else:
       return True
```

- ✅
```python
def is_even(x):
    return x % 2 == 0
```

- ✅
```python
def is_even(x):
    if x % 2 == 0:
        return True
    return False
```

- ❌
```python
def is_even(x):
    if x % 2 != 0:
       return True
    return False
```
> This is reversed — returns True if odd, False if even

**Q9: A data professional writes `print(33 > 12 or 9 < 7)`. What result will Python display?**
- ✅ **True**
- False
- Not equal
- Equal

> 33 > 12 is True. With `or`, only one needs to be True, so the result is True.

**Q10: Fill in the blank: A data professional can add a _____ to the beginning of a function's body to summarize the function's behavior and explain its arguments and return values.**
- conditional statement
- comparator
- ✅ **docstring**
- logical operator
---
