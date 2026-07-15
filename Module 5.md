# Data Science Fundamentals with Python and SQL Specialization
## Module 5 — R, RStudio, and GitHub

---

## Introduction to R and RStudio

### What is R?
- A **statistical programming language**
- Powerful for: data processing, manipulation, statistical inference, data analysis, and machine learning
- Most used by: academics, healthcare, and government
- Supports importing data from: flat files, databases, web, and statistical software (SPSS, STATA)
- Functions are easy to use and produce great visualizations
- Contains packages to handle data analysis **without installing additional libraries**

### RStudio Interface
RStudio is the most popular IDE for R. It includes:

| Panel | Purpose |
|-------|---------|
| **Code Editor** | Write R code with syntax highlighting and direct execution |
| **Console** | Type and run R commands directly |
| **Workspace / History tab** | Shows R objects created and history of all previous commands |
| **Files tab** | Shows files in your working directory |
| **Plots tab** | Displays history of plots. Can export to PDF or image |
| **Packages tab** | Shows external R packages available on your computer |
| **Help tab** | Provides help on R resources, packages, and RStudio support |

### Popular R Libraries for Data Science

| Library | Purpose |
|---------|---------|
| **dplyr** | Manipulating data |
| **stringr** | Manipulating strings |
| **ggplot2** | Visualizing data (histograms, bar charts, scatterplots) |
| **caret** | Machine learning |
| **Lattice** | Complex multi-variable data visualization |
| **Plotly** | Web-based interactive visualizations (saved as HTML) |
| **Leaflet** | Creating interactive maps/plots |
| **GGally** | Extension of ggplot2 — reduces complexity of combining geometric objects |

---

## Plotting in RStudio

### R Visualization Packages
- Install packages with: `install.packages("package_name")`

### Inbuilt R Plot Function
```r
# Basic scatterplot
plot(x, y)

# Add a line
plot(x, y, type="l")

# Add a title
title("My Plot Title")
```

### Plotting with ggplot2

```r
# Load library
library(ggplot2)

# Basic scatterplot using mtcars dataset
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point()

# Add a title
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point() +
  ggtitle("displacement vs miles per gallon")

# Change axis names
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point() +
  ggtitle("displacement vs miles per gallon") +
  labs(x = "Displacement", y = "Miles per Gallon")
```

> **ggtitle()** — adds a title to the plot
> **labs()** / **xlab() and ylab()** — adds names to the axes
> **geom_point()** — specifies a scatterplot (without it, the plot is empty)

---

## Lab: R Basics using RStudio

### Write Hello World in Console
```r
print("Hello World!")
```
Expected output: `Hello World!`

### Create Variables
```r
x <- 1
y <- 2
z <- x + y
```
Variables `x`, `y`, `z` appear in the **Environment panel**

> To clear the console: **Ctrl + L**
> To clean the workspace: click the **Broom icon**

### Create and Run an R Script File
1. File → New File → R Script
2. File → Save → name it `first_script.R`
3. Add code:
```r
x <- 3
y <- 4
z <- x + y
print(z)
```
4. Run using **Run icon** (selected lines) or **Source icon** (all lines)

Expected output: `[1] 7`

### Practice Tasks

**Task 1 & 2: Subtract x from y**
```r
x <- 10
y <- 20
result <- y - x
print(result)
```
Expected output: `[1] 10`

---

## Lab: Getting Started with RStudio and Installing Packages

### Load the Iris Dataset
```r
library(datasets)
data(iris)
View(iris)
```
- 150 entries, 5 columns (4 floating point + 1 string label)

### Find Unique Species
```r
unique(iris$Species)
```
Expected output: 3 different species

---

## Lab: Creating Data Visualizations using ggplot

### Load mtcars and View Data
```r
library(datasets)
data(mtcars)
head(mtcars, 5)
```

### Get Dataset Info
```r
?mtcars
```

### Scatterplot
```r
library(ggplot2)
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point()
```

### Add Title
```r
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point() +
  ggtitle("displacement vs miles per gallon")
```

### Change Axis Names
```r
ggplot(aes(x=disp, y=mpg), data=mtcars) + geom_point() +
  ggtitle("displacement vs miles per gallon") +
  labs(x = "Displacement", y = "Miles per Gallon")
```

### Boxplot (Engine Type vs MPG)
```r
mtcars$vs <- as.factor(mtcars$vs)
ggplot(aes(x=vs, y=mpg), data=mtcars) + geom_boxplot()
```

### Boxplot with Color
```r
ggplot(aes(x=vs, y=mpg, fill=vs), data=mtcars) +
  geom_boxplot(alpha=0.3) +
  theme(legend.position="none")
```

### Histogram of Weight
```r
ggplot(aes(x=wt), data=mtcars) + geom_histogram(binwidth=0.5)
```

---

## Lab: Plotting with RStudio (GGally)

### Install Dependencies (run in Console)
```r
install.packages("https://cran.r-project.org/src/contrib/Archive/patchwork/patchwork_1.1.0.tar.gz",
  repos=NULL, type="source", dependencies=TRUE)

install.packages("https://cran.r-project.org/src/contrib/Archive/broom.helpers/broom.helpers_1.4.0.tar.gz",
  repos=NULL, type="source", dependencies=TRUE)

install.packages("https://cran.r-project.org/src/contrib/Archive/ggstats/ggstats_0.5.0.tar.gz",
  repos=NULL, type="source", dependencies=TRUE)
```

### Create GGally Plot with Iris Dataset
```r
library(datasets)
data(iris)
library(GGally)
ggpairs(iris, mapping=ggplot2::aes(colour = Species))
```

What the output shows:
- **Diagonal** — data distributions per column and species
- **Left of diagonal** — pairwise scatterplots by color
- **Right of diagonal** — correlation values between columns
- **Bottom** — histograms
- Correlation close to **1** = high similarity, close to **0** = less similarity

---

## Introduction to GitHub and Version Control

### What is Version Control?
- A system that **tracks changes** to documents over time
- Lets you **recover older versions** if you make a mistake
- Makes **collaboration** with others much easier

### What is Git?
- **Free and open-source** distributed version control system
- Created in **2005** by **Linus Torvalds** (originally for Linux kernel development)
- Every developer has a **full local copy** of the project history
- Users can sync changes to a remote server

### Key Git Terms

| Term | Meaning |
|------|---------|
| **Repository (Repo)** | Folders set up for version control — stores code and tracks changes |
| **Fork** | A copy of a repository |
| **Branch** | An isolated environment within a repo to make changes |
| **Pull Request** | A request for someone to review and approve your changes before merging |
| **Working Directory** | Files and folders on your computer associated with a Git repo |
| **SSH Protocol** | Method for secure remote login between computers |
| **Commit** | Save a snapshot of your changes to the repo |
| **Organization** | A collection of user accounts that owns repositories |

### Basic Git Commands

| Command | What It Does |
|---------|-------------|
| `git clone` | Clone/copy an existing repository |
| `git add` | Move changes from working directory to staging area |
| `git status` | See the state of your working directory and staged changes |
| `git commit` | Save staged changes to the project |
| `git reset` | Undo changes made to files in your working directory |
| `git log` | Browse previous changes to a project |
| `git branch` | Create an isolated environment / list branches |
| `git checkout` | See and change existing branches |
| `git merge` | Merge branches back together |
| `git revert` | Revert a previous commit |

### GitHub vs GitLab vs Bitbucket
All are **web-hosted services** for Git repositories.

| Platform | Notes |
|----------|-------|
| **GitHub** | Most popular. Hosted by Microsoft. Free, professional, enterprise accounts |
| **GitLab** | Complete DevOps platform. Built-in CI/CD. Fully open source |
| **Bitbucket** | Popular with Atlassian tools (Jira, etc.) |

---

## GitHub Repository Tabs

| Tab | Purpose |
|-----|---------|
| **Code** | Where all source files live |
| **Issues** | Track and plan open items against the project |
| **Pull Requests** | Review changes before merging into the main branch |
| **Projects** | Tools for managing and planning work |
| **Settings** | Personalization, access control, rename repo |

---

## Working with Branches in GitHub

### What is a Branch?
- A **snapshot of your repository** where you can make changes safely
- A copy of the **main branch** — used to develop and test changes
- Changes stay in the branch **until you merge them** back to main

### Workflow
1. Create a **child branch** from main
2. Make changes, add files, test
3. Open a **Pull Request (PR)** to notify team members
4. Team reviews and approves
5. **Merge** the PR into main
6. Delete the branch if no longer needed

### Why Use Branches?
- Changes done by one member **do not affect** other members' workflow
- Multiple branches can be created and merged when ready

---

## Lab: Getting Started with GitHub

### Exercise 1 — Create a GitHub Account
1. Go to: https://github.com/join
2. Enter username, email, password → Click **Sign up**
3. Solve the visual puzzle → verify email

### Exercise 2 — Create a Repository
1. Click **+** → **New repository**
2. Give it a name
3. Initialize with **README.md**
4. Choose **public or private**
5. Click **Create repository**

### Exercise 3a — Edit a File
1. Click the **pencil icon** on README.md
2. Add text
3. Scroll down → Click **Commit Changes**

### Exercise 3b — Create a New File
1. Click **Add file** → **Create new file**
2. Give a name + extension (e.g. `firstpython.py`)
3. Add code
4. Click **Commit changes**

### Exercise 4 — Upload a File
1. Click **Add file** → **Upload files**
2. Click **Choose your files** → select from your computer
3. Click **Commit changes**

---

## Lab: Working with Branches in GitHub

### Step 1 — Create a Branch
1. Go to repository main page
2. Click the **Branch drop-down** (shows "main")
3. Type the new branch name (e.g. `Child_Branch`)
4. Press **Enter** or click **Create branch from main**

### Step 2 — Add a File to the Branch
1. Make sure **Child_Branch** is selected in the drop-down
2. Click **Add file** → **Create new file**
3. Name the file (e.g. `testchild.py`) and add code
4. Scroll down → add a commit description → Click **Commit**

> The file is added to Child_Branch only — NOT to main

### Step 3 — Open a Pull Request
1. In Child_Branch, click **Compare & pull request**
2. Review the changes highlighted in green
3. Optionally add a comment
4. Click **Create pull request**

### Step 4 — Merge a Pull Request
1. Click the **Pull requests** tab
2. Click the pull request you want to merge
3. Click **Merge pull request** → **Confirm merge**
4. The branch can now be deleted

> After merging, check the main branch to confirm the new file is there

---

## Lab: Getting Started with Branches using Git Commands

### Key Commands Used

```bash
# Create a new local repository
git init

# Add a file to staging
git add filename

# Commit changes
git commit -m "your message"

# Create a new branch
git branch branch_name

# Switch to a branch
git checkout branch_name

# Check status of files
git status

# View recent commits
git log

# Revert a commit
git revert commit_id

# List all branches (active branch marked with *)
git branch

# Merge a branch into the current branch
git merge branch_name
```

---

## Practice Quiz — RStudio

**Q1: Where can you type R commands in RStudio?**
- Files
- History
- ✅ **Console**
- Code editor

**Q2: Which R library will you use for data visualizations such as histograms, bar charts, and scatterplots? (Select all that apply)**
- ✅ **ggplot**
- Lattic
- Leaflet
- ✅ **Plotly**

**Q3: Which is the command used to install packages in R?**
- library(packages)
- installpackages()
- ✅ **install.packages()**

---

## Practice Quiz — GitHub

**Q1: Which term describes the folders set up for version control?**
- Pull request
- SSH protocol
- ✅ **Repository**
- Fork

**Q2: Which tab in your Repository enables a review of changes made before being merged into the main branch?**
- ✅ **Pull requests**
- Projects
- Issues
- Code

**Q3: Which command is used to clone an existing repository?**
- ✅ **git clone**
- git reset
- git status
- git add

---

## Graded Quiz — RStudio & GitHub

**Q1: Which of the following is True about R language?**
- ✅ **R supports importing of data from different sources like flat files, databases**
- R functions require lots of coding compared to other Data Science tools
- R requires installation of additional libraries to handle data analysis
- R is used for statistical inference and does not support visualization

**Q2: Which R library is used for machine learning?**
- dplyr
- ggplot
- stringr
- ✅ **caret**

**Q3: Which function in ggplot adds a title to the plot?**
- ✅ **ggtitle**
- library
- geom_point
- ggplot

**Q4: Which function is used to specify appropriate names for both axes in a plot?**
- ggplot
- geom_point
- ✅ **xlab and ylab**
- library

**Q5: What is a copy of a repository?**
- Working directory
- SSH protocol
- ✅ **Fork**
- Pull request

**Q6: How does GitLab provide streamline testing and delivery?**
- ✅ **With Built-in Continuous Integration (CI) and Continuous Delivery (CD)**
- With merging
- With branching
- With reviewing and including comments

**Q7: In GitHub, what is an organization?**
- ✅ **A collection of user accounts that owns repositories**
- A name you must specify for your repository
- The top level of a repository tree
- A path to the code files in a project

**Q8: On which tab in the Repository can you see all the source files?**
- Projects
- Pull requests
- ✅ **Code**
- Issues

**Q9: How do you save changes in the Repository?**
- Create new file
- Save changes
- ✅ **Commit changes**
- Add file

**Q10: Which option enables you to add a file to the Repository from your local machine?**
- New Repository
- Create new file
- Commit changes
- ✅ **Upload files**

---
