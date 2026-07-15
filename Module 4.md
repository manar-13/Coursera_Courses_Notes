# Data Science Fundamentals with Python and SQL Specialization
## Module 4 — Jupyter Notebooks and JupyterLab

---

## Introduction to Jupyter Notebooks

### What is Jupyter Notebook?
- Originally called **iPython** — developed for Python programming
- Renamed **Jupyter** = **Ju**lia + **Py**thon + **R** (now supports many more languages)
- A **browser-based application** that lets you create and share documents containing:
  - Code
  - Equations
  - Visualizations
  - Narrative text and links
- Works like a **scientist's lab notebook** — record experiments and results others can reproduce
- Combines descriptive text, code blocks, and code output in a **single file**
- Can export to **PDF or HTML** to share with anyone

### What is JupyterLab?
- A browser-based application that gives access to **multiple** Jupyter Notebook files, code, and data files
- Extends Jupyter Notebooks with:
  - Multiple notebooks open at once
  - Text editors, terminals, and custom components
  - Flexible and integrated layout
- Compatible with: CSV, JSON, PDF, Vega, and more
- **Open source**

### How to Install/Access Jupyter
| Method | How |
|--------|-----|
| **Cloud (IBM/Google Colab)** | No installation needed. Import/export notebooks using .ipynb format |
| **Command line** | `pip install jupyter` |
| **Anaconda** | Download from anaconda.com — includes Jupyter and JupyterLab |
| **Skills Network Labs** | Hosted version — no installation needed for this course |

---

## Getting Started with Jupyter — Key Actions

### Cell Basics
- A **cell** is an input field that allows multiple lines of text
- Two types of cells:
  - **Code cell** — write and execute code. Default cell type
  - **Markdown cell** — write formatted text (headings, links, tables, bold, lists, etc.)

### Running Code
| Action | How |
|--------|-----|
| Run selected cell | **Shift + Enter** |
| Run from menu | Run → Run Selected Cells |
| Run all cells | Run → Run All Cells |

### Managing Cells
| Action | How |
|--------|-----|
| Insert new cell | Click **+** in toolbar |
| Delete cell | Edit → Delete Cells (or press **D** twice) |
| Move cell up/down | Edit → Move Cells Up / Move Cells Down |
| Split cell | Edit → Split Cell (or **Ctrl + Shift + -**) |
| Convert to Markdown | Click dropdown → select **Markdown** |

### Working with Multiple Notebooks
- Click **+** in toolbar → select file to open another notebook
- Or: File → Open a new launcher / Open a new notebook
- Notebooks can be placed **side by side**

### Presenting a Notebook
- Add **Markdown cells** for titles and text descriptions
- Create line plots and convert cells into **slides or sub-slides**
- Deliver code, visualizations, text, and outputs as a presentation

### Shutting Down
- Click the **stop icon** on the sidebar (second icon from top)
- Shut down all sessions at once or individually
- "No kernel" at top right confirms it is no longer active

---

## Jupyter Kernels

### What is a Kernel?
- A **computational engine** that executes the code in a Notebook file
- When a notebook opens, the related kernel **launches automatically**
- The kernel performs computation and produces results
- The kernel name shows in the **top right corner** of the notebook

### Available Kernels in Skills Network Environment
- Python, Apache, Julia, R, Swift

### Switching Kernels
- Select kernel on the **launch page**, or
- Click the **top right kernel icon** and select from the dropdown menu

> If running locally, you must manually install languages through the command line (CLI)

---

## Jupyter Architecture

### Two-Process Model
| Component | Role |
|-----------|------|
| **Client** | The browser — user interface to send code to the kernel |
| **Kernel** | Executes the code and returns results to the client |
| **Notebook Server** | Responsible for saving and loading notebooks |

### How Notebooks Are Saved
- When you save, the notebook is sent from browser → Notebook server
- Saved as a **JSON file** with `.ipynb` extension

### Converting Files (NB Convert Tool)
To convert a notebook to another format (e.g. HTML):
1. **Preprocessor** modifies the notebook
2. **Exporter** converts it to the new format
3. **Postprocessor** works on the exported file to give final output

---

## Lab: Getting Started with Jupyter Notebooks

### Overview of Code and Markdown Cells
- **Markdown cell** — for text, headings, links, tables, bold, lists. Not executed as code
- **Code cell** — write and execute code. Default cell type in Jupyter

### Exercise 1 — Say "Hello" to the world in Python
Click the cell containing `'Hello, Python!'` and press **Shift + Enter**

Expected output:
```
Hello, Python!
```

### Display an Integer
Run the cell containing `2`

Expected output:
```
2
```

### Mathematical Operations
Run the following cells:

```python
# Addition operation
2+2
```
Expected output: `4`

```python
# Multiplication operation
2.5*3.5
```
Expected output: `8.75`

---

### Exercise 2 — Create a new cell and execute it
1. Click the **+** button in the toolbar
2. Type `4.5` in the new cell
3. Press **Shift + Enter**

Expected output: `4.5`

---

### Exercise 3 — Delete a cell
1. Click on the cell to select it
2. Go to **Edit** → **Delete Cells**
3. Or shortcut: press **D** twice

---

### Exercise 4 — Writing comments in Python
- Use `#` before a comment — Python ignores everything after `#`

```python
# Execute this cell by clicking Shift + Enter
2+3
```
Expected output: `5`

```python
# Execute this cell by clicking Shift + Enter
# 2+3
```
Expected output: **nothing** — because `2+3` is commented out

---

### Exercise 5 — Using Markdown cells
1. Click the cell
2. Change the dropdown from **Code** to **Markdown**
3. Type `My First Markdown`
4. Press **Shift + Enter** to render it

> To edit a Markdown cell, double-click anywhere within it

---

### Practice Exercises

**Task 1:** Insert a new Markdown cell with text: `Evaluating Basic Arithmetic Expression`
- Click **+** → change dropdown to **Markdown** → type text → **Shift + Enter**

**Task 2:** Insert a new code cell and run `(20+5)*4`
Expected output: `100`

**Task 3:** Add a comment and a string in the cell:
```python
# Displaying a string message
"Let us explore python without coding."
```

**Task 4 (Bonus):** Split the cell after `1+1`
- Click cursor after `1+1` → Edit → Split Cell (or **Ctrl + Shift + -**)

---

## Lab: Using Markdowns in Jupyter Notebooks

### Markdown Formatting Rules

#### Headings
```markdown
# Heading 1
## Heading 2
### Heading 3
```

#### Bold and Italics
```markdown
**Bold text**
*Italic text*
```

#### Links
```markdown
[Link text](URL)
```

#### Images
```markdown
![Alt text](image URL)
```

#### Tables
```markdown
| Fruits  | Quantity(Kg) | Price(In Rupee) |
| ------- | ------------ | --------------- |
| Apple   | 2            | 500             |
| Orange  | 1            | 200             |
| Mango   | 3            | 1000            |
| Grapes  | 2            | 400             |
```

#### Ordered List
```markdown
1. Python
2. Java
3. C++
4. C
```

#### Unordered List
```markdown
- Item 1
- Item 2
- Item 3
```

> Full Markdown reference: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

---

## Lab: Working with Files in Jupyter Notebooks

### Exercise 5 — Upload a Downloaded Notebook
**Option 1 — Upload files:**
1. Click **Upload Files**
2. Browse for the notebook on your local machine
3. Select it — it will appear in the left navigation pane
4. Double-click to open it

**Option 2 — Drag and Drop:**
1. Open your local file manager
2. Select the notebook file
3. Drag it into the Skills Network Labs file explorer
4. It appears in the left panel — double-click to open

---

### Exercise 6 — Work with Multiple Notebooks
1. Click **File** menu
2. Select **New view for notebook**
3. View notebooks **side by side** and update them simultaneously

---

## Anaconda and Additional Jupyter Environments

### What is Anaconda?
- Free and open-source distributor for **Python and R**
- Has **1,500+ libraries**
- Includes **Anaconda Navigator** — a GUI that launches applications without using the command line
- Download from: anaconda.com

### Jupyter Environments in Anaconda Navigator
| Environment | Description |
|-------------|-------------|
| **JupyterLab** | Open-source, web-based. Includes NumPy, Pandas, Matplotlib pre-installed |
| **VS Code** | Free, open-source code editor. Works on Linux, Windows, macOS. Supports syntax highlighting, auto-indentation, multiple languages |

### How to Launch JupyterLab from Anaconda
1. Open Anaconda Navigator
2. Click **Launch** in the JupyterLab box
3. Dashboard opens in browser on localhost

### How to Execute Python in VS Code
1. Open VS Code from Anaconda Navigator
2. Install **Python extensions** (Ctrl + Shift + X)
3. File → New File → Jupyter Notebook
4. Write code and run using the **RUN icon**

> If you install VS Code separately (not via Anaconda), it will NOT be configured for Python or Jupyter automatically

---

## Cloud-Based Jupyter Environments

### JupyterLite
- Lightweight tool built from JupyterLab components
- Executes **entirely in the browser** — no dedicated server needed
- Deployed as a **static website**
- Supports visualization libraries: Altair, Plotly, ipywidgets
- Default kernel: **Pyolite** (based on Pyodide)
- Launch at: `jupyter.org/try-jupyter/lab`

### Google Colaboratory (GoogleColab)
- Free Jupyter notebook environment that runs **entirely in the cloud**
- Notebooks execute in a browser
- Projects stored on **Google Drive** and **GitHub**
- No setup or installation needed
- Can clone GitHub projects and execute them
- Pre-installed libraries: scikit-learn, matplotlib, and more
- To open: Google Drive → New → More → Google Colaboratory

### Summary of All Jupyter Environments

| Environment | Type | Notes |
|-------------|------|-------|
| Jupyter Notebook | Local/Cloud | Original tool |
| JupyterLab | Local/Cloud | Next version of Jupyter, more features |
| JupyterLite | Browser (cloud) | No server needed, static website |
| Google Colab | Cloud | Stores on Google Drive/GitHub |
| VS Code | Local | Needs Python extension installed |
| Anaconda Navigator | Local | GUI launcher for all the above |

---

## Lab: Anaconda Installation Steps (Windows)

### Exercise 1 — Download & Install Anaconda
1. Go to: https://www.anaconda.com/products/distribution
2. Download the installer for your OS
3. Right-click the downloaded file → Run as Administrator
4. Click **Next** → Agree to license → Select **Just me** → Choose install folder
5. Select **Register Anaconda3 as default Python** → Click Install
6. Click **Finish**

### Exercise 2 — Create Anaconda Environment
1. Open Anaconda Navigator from Start menu
2. Go to **Environments** tab → Click **Create**
3. Give a name, select language version → Click **Create**
4. Go back to Home → Launch Jupyter → Create a Python Notebook

### Exercise 3 — Create and Execute Python Jupyter Notebook

**Step 1: Create Markdown cell**
```markdown
# My First Program
```
Press **Shift + Enter** to render

**Step 2: Create new cells**
- Insert → Insert Cell Above / Insert Cell Below
- Shortcuts: `a` = insert above, `b` = insert below

**Step 3: Write and execute code**
```python
1+1
```
Expected output: `2`

**Step 4: Rename, Shutdown, Save**
- Rename: File → Rename → type `My_Notebook.ipynb`
- Shutdown kernel: Kernel → Shutdown
- Save: File → Save Notebook

### Exercise 3 — Practice Problems (Python)

**Problem 1: Min and Max**
```python
x = min(5, 10, 25)
y = max(5, 10, 25)
print(x)
print(y)
```
Expected output:
```
5
25
```

**Problem 2: Power**
```python
x = pow(4, 3)
print(x)
```
Expected output: `64`

### Exercise 4 — R Jupyter Notebook Problems

**Problem 1: Multiplication**
```r
2 * 3 # Multiplication
```
Expected output: `6`

**Problem 2: Subtraction**
```r
4 - 1 # Subtraction
```
Expected output: `3`

**Problem 3: Add 2 to a variable**
```r
a <- 1 # Assigning 1 to variable "a"
a + 2  # Adding 2
```
Expected output: `3`

**Problem 4: Create a data frame**
```r
df = data.frame(Emp_Name = c("Jai", "David", "Michael"),
                Job_role = c("Manager", "Team Lead", "Developer"))
print(df)
```
Expected output:
```
  Emp_Name   Job_role
1      Jai    Manager
2    David  Team Lead
3  Michael  Developer
```

---

## Quiz 1 — Jupyter Notebooks

**Q1: What functionality is provided by the Jupyter Notebook file to Data Scientists?**
- Does not allow to share the file in any format
- ✅ **Allows to combine descriptive text, code blocks, and code output in a single file**
- Runs the code and generates the output in a separate file
- Allows to code in only one language

**Q2: What is the purpose of the kernel in the Jupyter Notebook?**
- ✅ **Executes the code**
- Exports the code to a different file
- Translates the code to a different language
- Writes the code

**Q3: What are the elements of Jupyter's architecture?**
- Server and client
- Two kernels and a server
- ✅ **Kernel and client**
- Two clients and a server

**Q4: What is the default kernel of JupyterLite?**
- ✅ **Pyolite**
- SQLite
- Julia
- No kernel

**Q5: What is the purpose of Anaconda Navigator?**
- ✅ **Allows to install new packages without using a command line interface**
- Allows creating interactive visualizations
- Allows execution of code written in any language
- Allows to install packages using a command line interface only

---

## Quiz 2 — Jupyter Environments

**Q1: In which formats can you share a notebook with other users?**
- ✅ **PDF**
- ppt
- xls
- doc

**Q2: What is a feature of JupyterLab?**
- Allows support of a single HTML file format
- ✅ **Interactive control of the notebook cells and output**
- Allows access to a single Notebook
- Is not an open source

**Q3: Which option gives the output of the current highlighted code cell in Jupyter Notebook?**
- ✅ **Run → Run Selected Cells**
- Edit → Run
- Run → Render All Markdown Cells
- Run → Run All Cells

**Q4: How can you switch the kernel in the Jupyter Notebook?**
- By clicking on the Code option
- By clicking the top left of the notebook
- ✅ **By clicking the top right of the notebook**
- From the Edit menu on top of the notebook

**Q5: Which of the following can be used to work with Jupyter Notebook?**
- Notepad
- ✅ **Browser**
- Explorer
- Notepad++

**Q6: What do you use to convert the ipynb file to other formats?**
- Postprocessor
- Client Browser
- Preprocessor
- ✅ **Exporter**

**Q7: What is one of the features of JupyterLite?**
- Requires a dedicated server
- ✅ **Can create interactive graphics and visualizations**
- It is not a static website
- Default kernel is SQLite

**Q8: What is one of the features of GoogleColab?**
- GoogleColab Jupyter notebooks execute on a server
- GoogleColab projects are stored on the local machine
- You need to set up and install GoogleColab Jupyter notebooks
- ✅ **You can clone GitHub projects and execute them in GoogleColab**

**Q9: Which environment is used for creating and modifying Jupyter Notebooks on a local device?**
- GoogleColab
- ✅ **Visual Studio Code**
- SQLite
- Python

**Q10: How can you execute Python code in Visual Studio Code?**
- ✅ **By installing Python extensions**
- By clicking on Download as
- By selecting Markdown from the drop-down menu
- By selecting Code from the drop-down menu

---