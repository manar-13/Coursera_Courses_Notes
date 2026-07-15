# Introduction to Data Analysis Using Python
## Module 4 — Data Structures in Python

---

## Module 4 Overview

In this module you will learn:
- **Lists** — ordered, mutable collections
- **Tuples** — ordered, immutable sequences
- **Dictionaries** — key-value pairs
- **Sets** — unordered, unique elements
- **NumPy** — arrays and vectorization
- **Pandas** — DataFrames and Series for tabular data
- **Libraries, Packages, Modules** — importing and using external tools

---

## Data Types vs Data Structures

| Concept | Definition |
|---------|-----------|
| **Data type** | An attribute that describes a piece of data based on its values (e.g. int, float, string, Boolean) |
| **Data structure** | A collection of data values or objects that can contain different data types |

Data structures enable more efficient storage, access, and modification of data.

---

## Lists

### What is a List?
- A data structure that helps **store and manipulate an ordered collection of items**
- Can contain any data type (integers, strings, floats, other lists, etc.)
- **Mutable** — elements can be modified, added, or removed
- Uses **square brackets** `[]`
- Supports indexing, slicing, and duplicates

### Create a List
```python
fruits = ['apple', 'banana', 'kiwi']
empty_list = []
empty_list2 = list()
```

### Indexing and Slicing
```python
x = ['Now', 'we', 'are', 'cooking', 'with', 'seven', 'ingredients']
print(x[3])      # 'cooking'
print(x[1:3])    # ['we', 'are']
print(x[:2])     # ['Now', 'we']
print(x[2:])     # ['are', 'cooking', 'with', 'seven', 'ingredients']
```

### Check if Element Exists
```python
'this' in x   # False
```

### List Methods

| Method | What It Does | Example |
|--------|-------------|---------|
| `append()` | Add element to the end | `fruits.append('kiwi')` |
| `insert(i, val)` | Insert at given index | `fruits.insert(1, 'orange')` |
| `remove(val)` | Remove first occurrence | `fruits.remove('banana')` |
| `pop(i)` | Remove and return element at index | `fruits.pop(2)` |
| `clear()` | Remove all items | `fruits.clear()` |
| `index(val)` | Return index of first occurrence | `fruits.index('apple')` |
| `count(val)` | Count occurrences | `fruits.count('apple')` |
| `sort()` | Sort the list | `fruits.sort()` |

### List Operations
```python
[1,2,3] + ['a','b','c']   # combines lists
['a','b'] * 2              # ['a','b','a','b']
# Cannot subtract or divide lists
```

> Lists are **mutable** — you can change individual elements directly.
> Strings are **immutable** — you cannot change a single character; you must create a new string.

---

## Tuples

### What is a Tuple?
- An **immutable sequence** that can contain elements of any data type
- More secure than lists — cannot be accidentally changed
- Uses **parentheses** `()` or the `tuple()` function
- Supports indexing and slicing

### Create a Tuple
```python
name = ('Grace', 'M', 'Hopper')
empty_tuple = ()
converted = tuple(['Grace', 'M', 'Hopper'])
```

> When creating a tuple with a single element, you must add a trailing comma: `(1,)`

### Tuples are Immutable
```python
name[2] = 'Copper'   # TypeError — cannot modify
```

### Unpacking a Tuple
```python
def to_dollar_cents(price):
    dollars = int(price)
    cents = round((price - dollars) * 100)
    return dollars, cents

dollars, cents = to_dollar_cents(6.55)
```

### Why Use Tuples?
- Store data of different types inside other structures (e.g. list of tuples)
- Return multiple values from a function
- Use as dictionary keys (because they are immutable)
- Signal to other developers that data should NOT be modified

### Example — Basketball Roster (List of Tuples)
```python
team = [
    ('Mia', 20, 'Guard'),
    ('Tasha', 22, 'Forward'),
    ('Lisa', 19, 'Center')
]

for name, age, position in team:
    print(name, position)
```

---

## Strings vs Lists vs Tuples — Comparison

| Feature | String | List | Tuple |
|---------|--------|------|-------|
| **Syntax** | `' '` or `" "` | `[ ]` | `( )` |
| **Mutable** | No | Yes | No |
| **Content** | Characters only | Any data type | Any data type |
| **Indexing/Slicing** | Yes | Yes | Yes |
| **Common use** | Text data | Ordered, modifiable collections | Immutable records, function returns |

---

## Useful Tools: zip(), enumerate(), List Comprehension

### zip()
- Combines two or more sequences element-wise into tuples

```python
cities = ['Paris', 'Lagos', 'Mumbai']
countries = ['France', 'Nigeria', 'India']
places = list(zip(cities, countries))
# [('Paris', 'France'), ('Lagos', 'Nigeria'), ('Mumbai', 'India')]
```

### enumerate()
- Iterates over a sequence while keeping track of each element's index

```python
letters = ['a', 'b', 'c']
for index, letter in enumerate(letters):
    print(index, letter)
```

### List Comprehension
- A concise way to create a new list based on an existing iterable
- Syntax: `[expression for element in iterable if condition]`

```python
numbers = [1, 2, 3, 4, 5]
new_list = [x + 10 for x in numbers]
# [11, 12, 13, 14, 15]

# With condition
words = ['Emotan', 'Amina', 'Ibeno', 'Sankwala']
new_list = [(word[0], word[-1]) for word in words if len(word) > 5]
```

---

## Dictionaries

### What is a Dictionary?
- A data structure that consists of a **collection of key-value pairs**
- **Mutable** — you can add, modify, or delete key-value pairs
- **Unordered** — cannot be accessed by positional index
- Keys must be **immutable** (strings, integers, floats, tuples)
- Instantiated with `{}` or `dict()`

### Create a Dictionary
```python
# Using braces
zoo = {1: 'lions', 2: 'zebras', 3: 'elephants'}

# Using dict()
zoo = dict(pen1='lions', pen2='zebras')
```

### Access Values
```python
zoo[2]          # 'zebras'
zoo['zebras']   # KeyError — can only search by key, not value
```

### Add a Key-Value Pair
```python
zoo[4] = 'crocodiles'
```

### Check if Key Exists
```python
2 in zoo    # True — works for keys only, not values
```

### Delete a Key-Value Pair
```python
del zoo[4]
```

### Dictionary Methods

| Method | What It Does |
|--------|-------------|
| `keys()` | Returns all keys |
| `values()` | Returns all values |
| `items()` | Returns both keys and values |

```python
zoo.keys()    # dict_keys([1, 2, 3])
zoo.values()  # dict_values(['lions', 'zebras', 'elephants'])
zoo.items()   # dict_items([(1, 'lions'), (2, 'zebras'), ...])
```

### Looping over a Dictionary
```python
for key in zoo:
    print(key)   # prints only keys

for key, value in zoo.items():
    print(key, value)
```

---

## Sets

### What is a Set?
- A data structure containing only **unordered, unique elements**
- Each element is immutable, but the set itself is mutable
- Cannot be indexed or sliced
- Use `set()` function or non-empty `{}`

> To create an **empty set**, use `set()` — NOT `{}` (which creates an empty dictionary)

### Create a Set
```python
my_set = {1, 2, 3}
my_set2 = set([1, 2, 2, 3])   # {1, 2, 3} — duplicates removed
frozenset(['a', 'b', 'c'])    # immutable set
```

### Set Operations

| Operation | Method | Operator | What It Does |
|-----------|--------|----------|-------------|
| Union | `union()` | `\|` | All elements from both sets |
| Intersection | `intersection()` | `&` | Elements in common |
| Difference | `difference()` | `-` | Elements in one but not the other |
| Symmetric difference | `symmetric_difference()` | `^` | Elements not shared by either set |

```python
set_1 = {'a', 'b', 'c'}
set_2 = {'b', 'c', 'd'}

set_1 | set_2    # {'a', 'b', 'c', 'd'}
set_1 & set_2    # {'b', 'c'}
set_1 - set_2    # {'a'}
set_1 ^ set_2    # {'a', 'd'}
```

---

## Libraries, Packages, and Modules

### Definitions
- **Library / Package** — a reusable collection of code, related modules, and documentation (terms used interchangeably)
- **Module** — a Python file containing collections of functions and global variables; a subcomponent of a library
- **Global variable** — a variable that can be accessed from anywhere in a program or script

### Key Libraries for Data Professionals

| Library | Alias | Purpose |
|---------|-------|---------|
| **NumPy** | `np` | Multidimensional arrays, scientific computation |
| **Pandas** | `pd` | Manipulate and analyze tabular data |
| **Matplotlib** | `plt` | Create static, animated, interactive visualizations |
| **Seaborn** | `sns` | Simplified visualization built on Matplotlib |
| **Scikit-learn** | — | Statistical modeling, machine learning |
| **Statsmodels** | — | Statistical model testing |

### Import Statements

```python
import numpy as np                          # import with alias
import pandas as pd
import matplotlib.pyplot as plt             # import specific module

from sklearn.metrics import precision_score  # import specific function
```

> **Aliasing** — assigning an abbreviated name to a library to make code shorter and easier to read

### Built-in Modules (no installation needed)

| Module | Purpose |
|--------|---------|
| `math` | Mathematical functions (exp, log, factorial, sqrt) |
| `random` | Generate random numbers, random choices |
| `datetime` | Date and time conversions and calculations |

---

## NumPy

### What is NumPy?
- **Numerical Python** — essential library for scientific computation
- Power comes from **vectorization** — operations performed on multiple components simultaneously
- Much faster than regular Python loops for large datasets

### Vectorization Example
```python
import numpy as np

list_a = [1, 2, 3]
list_b = [4, 5, 6]

# Without NumPy (slow)
list_c = []
for i in range(len(list_a)):
    list_c.append(list_a[i] * list_b[i])

# With NumPy (fast)
array_a = np.array(list_a)
array_b = np.array(list_b)
array_c = array_a * array_b   # [4, 10, 18]
```

### The ndarray (N-Dimensional Array)
- The core data structure of NumPy
- **Mutable** — can change values but NOT resize
- All elements must be the **same data type**
- Stores data in a **contiguous block of memory** (why it's so fast)

### Create Arrays

```python
import numpy as np

# 1D array
array_1d = np.array([1, 2, 3])

# 2D array (like a table)
array_2d = np.array([(1, 2, 3), (4, 5, 6)])

# 3D array (like two tables)
array_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

# Pre-filled arrays
np.zeros((3, 2))    # filled with 0s
np.ones((2, 2))     # filled with 1s
np.full((5, 3), 8)  # filled with 8s
```

### Array Attributes

| Attribute | What It Returns |
|-----------|----------------|
| `.shape` | Tuple of array dimensions |
| `.dtype` | Data type of array contents |
| `.ndim` | Number of dimensions |
| `.size` | Total number of elements |
| `.T` | Transposed array (rows become columns) |

```python
array_2d.shape   # (2, 3)
array_2d.dtype   # int64
array_2d.ndim    # 2
```

### Array Methods

| Method | What It Does |
|--------|-------------|
| `.reshape(rows, cols)` | Change shape without changing data |
| `.flatten()` | Collapse to 1D |
| `.tolist()` | Convert to Python list |
| `.max()` | Maximum value |
| `.min()` | Minimum value |
| `.mean()` | Mean value |
| `.std()` | Standard deviation |

```python
array_2d.reshape(3, 2)   # change from 2x3 to 3x2
array_2d.reshape(3, -1)  # -1 means "figure it out automatically"
```

---

## Pandas

### What is Pandas?
- **Python Data Analysis library** — built on top of NumPy
- Used to **manipulate and analyze tabular data** (rows and columns)
- Provides a simple interface to always see what's happening to your data

### Import Pandas
```python
import pandas as pd
import numpy as np   # typically imported together
```

### Two Core Classes

| Class | Description |
|-------|-------------|
| **DataFrame** | Two-dimensional labeled data structure (like a spreadsheet or SQL table) |
| **Series** | One-dimensional labeled array. Represents a single column or row of a DataFrame |

### Create a DataFrame

```python
# From a dictionary
d = {'col1': [1, 2], 'col2': [3, 4]}
df = pd.DataFrame(data=d)

# From a NumPy array
df2 = pd.DataFrame(np.array([[1,2,3],[4,5,6],[7,8,9]]),
                   columns=['a', 'b', 'c'])

# From a CSV file
df3 = pd.read_csv('/file_path/file_name.csv')
df3 = pd.read_csv('https://url-to-data.com/file.csv')
```

### DataFrame Attributes

| Attribute | What It Returns |
|-----------|----------------|
| `.columns` | Column labels |
| `.shape` | (rows, columns) tuple |
| `.dtypes` | Data type of each column |
| `.values` | NumPy representation |
| `.iloc[]` | Select by integer-location (index number) |
| `.loc[]` | Select by label (name) |

### DataFrame Methods

| Method | What It Does |
|--------|-------------|
| `.head(n)` | First n rows (default 5) |
| `.info()` | Summary: columns, data types, non-null counts |
| `.describe()` | Summary statistics (mean, min, max, etc.) |
| `.apply()` | Apply a function over an axis |
| `.copy()` | Make a copy of the DataFrame |
| `.drop()` | Drop rows or columns |
| `.groupby()` | Group rows by values at one or more columns |
| `.sort_values()` | Sort by values |
| `.value_counts()` | Count unique rows |
| `.isna()` | Check for null values |

### Selecting Data

```python
# Single column (returns Series)
df['column_name']
df.column_name   # dot notation (only if no spaces in name)

# Multiple columns (returns DataFrame)
df[['col1', 'col2']]

# Select by index number (iloc)
df.iloc[0]          # first row as Series
df.iloc[[0]]        # first row as DataFrame
df.iloc[0:3]        # rows 0, 1, 2
df.iloc[0:3, 3:5]   # rows 0-2, columns 3-4

# Select by name (loc)
df.loc['row_name']
df.loc[0:3, ['col_name']]
```

> **NaN** = "not a number" — how pandas represents null/missing values
> If a Series contains mixed or string data, its dtype shows as **"object"**

### Boolean Masking
- A filtering technique that overlays a Boolean grid onto a DataFrame
- Only rows where the condition is `True` are returned

```python
# Filter passengers over 60 in third class
df[(df['class'] == 3) & (df['age'] > 60)]
```

### Adding a New Column
```python
df['new_column'] = df['price'] * 1.07   # add column with calculation
```

### Concatenating DataFrames (concat)
- Combines DataFrames by adding new **rows** (axis=0) or new **columns** (axis=1)
- Use when data is identically formatted and needs to be stacked

```python
result = pd.concat([df1, df2], axis=0)   # vertical (new rows)
result = result.reset_index(drop=True)   # reset index after concat
```

### Merging DataFrames (merge)
- Joins two DataFrames **horizontally** based on a shared key column
- Similar to SQL joins

```python
merged = pd.merge(df_left, df_right, on='planet', how='inner')
```

### Types of Joins

| Join Type | What It Keeps |
|-----------|--------------|
| **inner** | Only keys in BOTH DataFrames |
| **outer** | All keys from BOTH DataFrames (NaN for missing) |
| **left** | All keys from LEFT DataFrame |
| **right** | All keys from RIGHT DataFrame |

---

## Module 4 Glossary

| Term | Definition |
|------|-----------|
| **agg()** | Pandas groupby method to apply multiple calculations to groups |
| **Aliasing** | Assigning an alternate name to something (e.g. `import numpy as np`) |
| **append()** | Adds an element to the end of a list |
| **Boolean masking** | Filtering technique using a Boolean grid on a DataFrame |
| **concat()** | Pandas function that combines DataFrames vertically or horizontally |
| **CSV file** | Comma-separated values — plaintext file using commas to separate values |
| **Data structure** | A collection of data values or objects containing different data types |
| **DataFrame** | Two-dimensional labeled data structure with rows and columns |
| **dict()** | Function to create a dictionary |
| **Dictionary** | Data structure consisting of key-value pairs |
| **difference()** | Finds elements in one set but not the other |
| **dtype** | NumPy attribute to check data type of array contents |
| **Global variable** | A variable accessible from anywhere in a program or script |
| **groupby()** | Groups DataFrame rows by values at one or more columns |
| **iloc[]** | Selects by integer-location-based position |
| **Immutability** | Values can never be altered or updated |
| **Import statement** | Uses the `import` keyword to load an external library/module |
| **Inner join** | Only keys in both DataFrames get included |
| **insert()** | Inserts an element at a given index in a list |
| **intersection()** | Finds elements two sets have in common |
| **items()** | Retrieves both keys and values from a dictionary |
| **Keys** | Shared points of reference between DataFrames for joining |
| **keys()** | Retrieves only the dictionary's keys |
| **Left join** | All keys from the left DataFrame are included |
| **Library** | A reusable collection of code; also called a package |
| **List** | Ordered, mutable collection of items |
| **List comprehension** | Formulaic creation of a new list from an existing list |
| **loc[]** | Selects pandas rows and columns by name |
| **matplotlib** | Library for creating visualizations in Python |
| **merge()** | Joins two DataFrames together horizontally |
| **Module** | Python file containing functions and global variables |
| **Mutability** | Ability to change the internal state of a data structure |
| **N-dimensional array (ndarray)** | Core data object of NumPy |
| **NaN** | "Not a number" — how null values are represented in pandas |
| **ndim** | NumPy attribute to check number of dimensions |
| **Nested loop** | A loop inside another loop |
| **NumPy** | Library with multidimensional array structures and functions |
| **Outer join** | All keys from both DataFrames get included |
| **pandas** | Library built on NumPy for manipulating and analyzing tabular data |
| **pop()** | Removes and returns element at a given index from a list |
| **remove()** | Removes an element from a list |
| **reshape()** | Changes shape of a NumPy array without changing data |
| **Right join** | All keys from the right DataFrame are included |
| **Seaborn** | Visualization library based on matplotlib |
| **Sequence** | A positionally ordered collection of items |
| **Series** | One-dimensional labeled array in pandas |
| **Set** | Data structure containing unordered, unique elements |
| **set()** | Takes an iterable and returns a new set object |
| **shape** | NumPy attribute to check the shape of an array |
| **symmetric_difference()** | Finds elements not shared by either set |
| **Tabular data** | Data in the form of a table with rows and columns |
| **Tuple** | Immutable sequence that can contain any data type |
| **tuple()** | Transforms input into a tuple |
| **union()** | Finds all elements from both sets |
| **values()** | Retrieves only the dictionary's values |
| **Vectorization** | Enables operations on multiple data components simultaneously |

---

## Quiz — Lists and Tuples

**Q1: Lists and their contents are immutable, so their elements cannot be modified, added, or removed.**
- True
- ✅ **False**

> Lists are **mutable** — elements can be modified, added, or removed.

**Q2: What Python method adds an element to the end of a list?**
- type()
- ✅ **append()**
- pop()
- remove()

**Q3: A data professional wants to instantiate a tuple. What Python elements can they use? (Select all that apply)**
- Square brackets
- ✅ **Parentheses**
- The insert() function
- ✅ **The tuple() function**

**Q4: What Python technique formulaically creates a new list based on the values in an existing list?**
- List conversion
- ✅ **List comprehension**
- List sequencing
- List nesting

---

## Quiz — Dictionaries and Sets

**Q1: Fill in the blank: In Python, a dictionary's _____ must be immutable.**
- order
- sets
- ✅ **keys**
- lists

**Q2: In Python, what does the items() method retrieve?**
- Only a dictionary's keys
- ✅ **Both a dictionary's keys and values**
- A dictionary's sets
- Only a dictionary's values

**Q3: A data professional is working with two Python sets. What function can they use to combine the sets (find all distinct elements in one or both)?**
- symmetric_difference()
- intersection()
- difference()
- ✅ **union()**

---

## Quiz — Libraries and NumPy

**Q1: Python libraries and packages include which of the following features? (Select all that apply)**
- ✅ **Modules**
- ✅ **Documentation**
- Cells
- ✅ **Reusable collections of code**

**Q2: What is the core data structure of NumPy?**
- List
- Dictionary
- ✅ **Array**
- Global variable

**Q3: A data professional wants to confirm the datatype of the contents of array x. How would they do this?**
- type(x)
- datatype(x)
- ✅ **x.dtype**
- x.ndim

---

## Quiz — Pandas

**Q1: Fill in the blank: In pandas, a _____ is a one-dimensional, labeled array.**
- CSV file
- dataframe
- key
- ✅ **series**

**Q2: In pandas, what is Boolean masking used for?**
- Adding data to a dataframe
- Merging data in a dataframe
- Deleting data from a dataframe
- ✅ **Filtering data in a dataframe**

**Q3: What is a pandas method that groups rows of a dataframe together based on their values at one or more columns?**
- agg()
- ✅ **groupby()**
- values()
- keys()

**Q4: A data professional wants to join two dataframes containing identically formatted data vertically. What pandas function can they use?**
- insert()
- type()
- merge()
- ✅ **concat()**

---

## Graded Quiz — Module 4

**Q1: A data professional wants to merge two pandas dataframes so all keys from BOTH DataFrames get included. What technique?**
- ✅ **Outer join**
- Inner join
- Left join
- Right join

**Q2: What function finds elements from both sets that are mutually not present in the other?**
- union()
- intersection()
- ✅ **symmetric_difference()**
- difference()

**Q3: In pandas, what is the difference between iloc[] and loc[]?**
- iloc[] selects by name; loc[] selects by index
- iloc[] merges vertically; loc[] merges horizontally
- ✅ **iloc[] selects by index; loc[] selects by name**
- iloc[] merges horizontally; loc[] merges vertically

**Q4: Fill in the blank: In Python, _____ indicate where a list starts and ends.**
- quotation marks
- parentheses
- braces
- ✅ **square brackets**

**Q5: A data professional wants the maximum value of the Price column in a DataFrame named sales. What code can they use?**
- sales['Price'].max()... ✅ **sales['Price'].max()**
- sales.max().Price
- sales = 'Price'.max()
- sales.max().[Price]

**Q6: Fill in the blank: In Python, a dictionary's keys must be _____.**
- mutable
- ✅ **immutable**
- identical
- equal

**Q7: How do global variables differ from other variables in Python? (Select all that apply)**
- Global variables cannot be accessed from a script
- ✅ **Global variables can be accessed from anywhere in a script**
- Global variables cannot be accessed from a program
- ✅ **Global variables can be accessed from anywhere in a program**

**Q8: What Python code retrieves only the values from a dictionary named employees?**
- items.employees()
- ✅ **employees.values()**
- employees.items()
- values.employees()

**Q9: Which statements accurately describe Python tuples? (Select all that apply)**
- Tuples cannot be split into separate variables
- ✅ **Tuples are sequences**
- ✅ **Tuples are immutable**
- ✅ **Tuples can be split into separate variables**

**Q10: The string 'Houston' is the third element (index 2) in a list named cities. What code removes it?**
- cities.pop(1)
- cities.pop(4)
- ✅ **cities.pop(2)**
- cities.pop(3)

**Q11: A NumPy array has 3 rows and 2 columns. How to change it to 2 rows and 3 columns?**
- agg()
- groupby()
- type()
- ✅ **reshape()**
---
