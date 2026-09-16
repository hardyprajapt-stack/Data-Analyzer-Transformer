# project04
This is a menu-driven Python program that analyzes and transforms 1D or 2D data using various functions. It performs operations like summary calculation, sorting, filtering, recursion (factorial), and demonstrates *args and **kwargs usage


# 📊 Data Analyzer & Transformer

A beginner-friendly **Python Data Analyzer & Transformer** project designed to demonstrate fundamental Python programming concepts through a menu-driven data analysis application.

The project supports both **1D and 2D numerical lists** and demonstrates practical concepts such as **global variables, functions, recursion, lambda functions, filtering, sorting, `*args`, `**kwargs`, returning multiple values, list comprehensions, built-in functions, and data transformation**.

---

## 📌 Project Overview

The **Data Analyzer & Transformer** is a console-based Python application where users can enter numerical data in either:

* 1D List
* 2D List

After storing the data, the application provides several operations for analyzing and transforming it.

The main operations include:

* 📥 Input Data
* 📊 Generate Data Summary
* 🔢 Calculate Factorial using Recursion
* 🔎 Filter Data using Lambda
* 🔃 Sort Data
* 📈 Calculate Minimum, Maximum and Average
* 📦 Demonstrate `*args` and `**kwargs`
* 🚪 Exit the Program

---

# 🎯 Project Objectives

The main objectives of this project are:

* Understand Python functions
* Work with 1D and 2D lists
* Learn data transformation using list comprehension
* Use global variables
* Calculate basic statistical summaries
* Understand recursion
* Use lambda functions
* Learn `filter()`
* Understand `sort()` and `sorted()`
* Learn `*args` and `**kwargs`
* Return multiple values from a function
* Build a menu-driven Python application
* Practice Python built-in functions

---

# 🛠️ Technologies Used

* **Python 3**
* Lists
* Functions
* Global Variables
* Recursion
* Lambda Functions
* `filter()`
* `sort()`
* `sorted()`
* List Comprehension
* `*args`
* `**kwargs`
* Built-in Functions
* Conditional Statements
* `while` Loop

---

# 📂 Project Structure

```text
Data-Analyzer-and-Transformer/
│
├── data_analyzer.py
└── README.md
```

---

# 🧠 Python Concepts Demonstrated

## 1. Global Variables

The program starts with two global variables:

```python
data = []
summary = {}
```

### `data`

Stores the user's dataset.

### `summary`

Stores calculated summary information.

The `global` keyword is used inside functions to modify these variables.

Example:

```python
global data
```

and:

```python
global summary
```

---

# 📥 2. Input Data

The `input_data()` function allows the user to enter either a **1D list or a 2D list**.

The user chooses:

```text
Enter 1 for 1D list, 2 for 2D list:
```

---

## 1D List

If the user selects `1`:

```python
data = list(map(int, input().split()))
```

Example input:

```text
10 20 30 40 50
```

Stored data:

```python
[10, 20, 30, 40, 50]
```

---

## 2D List

If the user selects `2`, the program asks for the number of rows.

Example:

```text
Enter number of rows: 3

Row 1: 10 20 30
Row 2: 40 50 60
Row 3: 70 80 90
```

Stored data:

```python
[
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]
```

---

# 🔄 3. Flattening Data

The `flatten_data()` function converts a 2D list into a 1D list.

```python
def flatten_data(d):
    if isinstance(d[0], list):
        return [item for row in d for item in row]
    return d
```

### Example

Input:

```python
[
    [10, 20],
    [30, 40],
    [50, 60]
]
```

After flattening:

```python
[10, 20, 30, 40, 50, 60]
```

This makes it easier to perform calculations on both 1D and 2D data using the same functions.

---

# 📊 4. Data Summary

The `data_summary()` function calculates basic statistics from the dataset.

The summary contains:

* Count
* Sum
* Minimum
* Maximum
* Average

The code uses Python built-in functions:

```python
len()
sum()
min()
max()
```

Average is calculated using:

```python
sum(flat) / len(flat)
```

---

## Example

For:

```python
[10, 20, 30, 40, 50]
```

The summary will be:

```text
Count : 5
Sum : 150
Min : 10
Max : 50
Average : 30.0
```

The results are stored inside the `summary` dictionary:

```python
summary = {
    "Count": len(flat),
    "Sum": sum(flat),
    "Min": min(flat),
    "Max": max(flat),
    "Average": sum(flat) / len(flat)
}
```

---

# 🔢 5. Factorial Using Recursion

The project demonstrates **recursion** through the `factorial()` function.

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)
```

A recursive function calls itself until it reaches a base condition.

### Example

For:

```text
5
```

The calculation follows:

```text
5 × 4 × 3 × 2 × 1
```

Result:

```text
Factorial = 120
```

The `calculate_factorial()` function takes input from the user and displays the result.

---

# 🔎 6. Lambda Filter

The `lambda_filter()` function filters values based on a user-defined threshold.

The code uses:

```python
filter(lambda x: x > threshold, flat)
```

The lambda condition is:

```python
x > threshold
```

### Example

Data:

```python
[10, 20, 30, 40, 50]
```

Threshold:

```text
25
```

Result:

```text
Filtered values: [30, 40, 50]
```

This demonstrates:

* Lambda functions
* `filter()`
* List conversion

---

# 🔃 7. Sorting Demo

The `sorting_demo()` function demonstrates two different Python sorting approaches.

### `sort()`

```python
flat.sort()
```

This sorts the list in ascending order.

### `sorted()`

```python
sorted(flat, reverse=True)
```

This creates a sorted result in descending order.

Example:

```text
Original: [40, 10, 30, 20]

Sorted using sort(): [10, 20, 30, 40]

Sorted using sorted(): [40, 30, 20, 10]
```

---

# 📦 8. `*args`

The project includes:

```python
def show_args(*args):
```

`*args` allows a function to receive multiple positional arguments.

Example:

```python
show_args(10, 20, 30)
```

Output:

```text
Values using *args: (10, 20, 30)
```

Inside the function, `args` is represented as a tuple.

---

# 🗂️ 9. `**kwargs`

The project also demonstrates keyword arguments using:

```python
def show_kwargs(**kwargs):
```

The function receives keyword arguments and loops through them:

```python
for k, v in kwargs.items():
    print(k, ":", v)
```

The program calls:

```python
show_kwargs(**summary)
```

This passes the summary dictionary as keyword arguments.

Example:

```text
Count : 5
Sum : 150
Min : 10
Max : 50
Average : 30.0
```

---

# 🔢 10. Returning Multiple Values

The `return_multiple()` function returns three values:

```python
return min(flat), max(flat), sum(flat) / len(flat)
```

The returned values are:

1. Minimum
2. Maximum
3. Average

They are received using:

```python
mn, mx, avg = return_multiple()
```

Example output:

```text
Min: 10 Max: 50 Average: 30.0
```

This demonstrates **multiple-value return and tuple unpacking**.

---

# 🧮 Built-in Functions Used

The project uses several Python built-in functions.

| Function       | Purpose                            |
| -------------- | ---------------------------------- |
| `len()`        | Counts elements                    |
| `sum()`        | Calculates total                   |
| `min()`        | Finds minimum                      |
| `max()`        | Finds maximum                      |
| `map()`        | Applies conversion to input values |
| `list()`       | Creates a list                     |
| `filter()`     | Filters values                     |
| `isinstance()` | Checks data type                   |
| `input()`      | Takes user input                   |
| `print()`      | Displays output                    |
| `int()`        | Converts input to integer          |
| `sorted()`     | Returns sorted data                |

---

# 🔁 Main Menu

The program uses a `while True` loop to continuously display the main menu.

```text
====== MAIN MENU ======

1. Input Data
2. Display Data Summary
3. Calculate Factorial (Recursion)
4. Lambda Filter
5. Sorting Demo
6. Return Multiple Values
7. Show *args & **kwargs
8. Exit
```

The user's choice determines which function is executed.

---

# 🔄 Program Flow

```text
                START
                  │
                  ▼
          Display Main Menu
                  │
       ┌──────────┼───────────┐
       │          │           │
       ▼          ▼           ▼
 Input Data    Summary     Factorial
       │          │           │
       ├──────────┼───────────┤
       │          │           │
       ▼          ▼           ▼
   Lambda      Sorting    Multiple Values
       │          │           │
       └──────────┼───────────┘
                  │
                  ▼
            *args / **kwargs
                  │
                  ▼
              Exit?
             /     \
           No       Yes
           │         │
           └──► Menu ▼
                  END
```

---

# 📋 Features

| Feature                | Description                                 |
| ---------------------- | ------------------------------------------- |
| 📥 Data Input          | Supports 1D and 2D numerical lists          |
| 🔄 Data Transformation | Converts 2D lists into 1D                   |
| 📊 Summary             | Calculates count, sum, min, max and average |
| 🔢 Recursion           | Calculates factorial                        |
| 🔎 Lambda Filter       | Filters values above a threshold            |
| 🔃 Sorting             | Demonstrates `sort()` and `sorted()`        |
| 📦 `*args`             | Demonstrates multiple positional arguments  |
| 🗂️ `**kwargs`         | Demonstrates keyword arguments              |
| 🔢 Multiple Return     | Returns min, max and average                |
| 🔄 Menu System         | Provides continuous interaction             |

---

# 🧪 Example Run

### Step 1 — Input Data

```text
====== MAIN MENU ======

1. Input Data
2. Display Data Summary
3. Calculate Factorial (Recursion)
4. Lambda Filter
5. Sorting Demo
6. Return Multiple Values
7. Show *args & **kwargs
8. Exit

Enter your choice: 1

Enter 1 for 1D list, 2 for 2D list: 1
Enter numbers separated by space: 10 20 30 40 50

Data stored successfully!
```

### Step 2 — Display Summary

```text
Enter your choice: 2

--- Data Summary ---
Count : 5
Sum : 150
Min : 10
Max : 50
Average : 30.0
```

### Step 3 — Lambda Filter

```text
Enter your choice: 4

Enter threshold: 25

Filtered values: [30, 40, 50]
```

### Step 4 — Sorting

```text
Enter your choice: 5

Original: [10, 20, 30, 40, 50]
Sorted using sort(): [10, 20, 30, 40, 50]
Sorted using sorted(): [50, 40, 30, 20, 10]
```

### Step 5 — Factorial

```text
Enter your choice: 3

Enter number: 5
Factorial = 120
```

---

# 🧩 Function Overview

| Function                | Purpose                         |
| ----------------------- | ------------------------------- |
| `input_data()`          | Takes 1D or 2D data             |
| `data_summary()`        | Generates data summary          |
| `flatten_data()`        | Converts 2D data into 1D        |
| `factorial()`           | Recursive factorial calculation |
| `calculate_factorial()` | Takes factorial input           |
| `lambda_filter()`       | Filters values                  |
| `show_args()`           | Demonstrates `*args`            |
| `show_kwargs()`         | Demonstrates `**kwargs`         |
| `sorting_demo()`        | Demonstrates sorting            |
| `return_multiple()`     | Returns min, max and average    |

---

# 📚 What I Learned From This Project

This project provides practical experience with:

* Python Functions
* Global Variables
* 1D Lists
* 2D Lists
* List Comprehension
* Data Flattening
* Built-in Functions
* Recursion
* Lambda Functions
* `filter()`
* `sort()`
* `sorted()`
* `*args`
* `**kwargs`
* Multiple Return Values
* Tuple Unpacking
* Dictionaries
* `while` Loops
* `if-elif-else`
* User Input
* Menu-Driven Applications

---

# 💼 Data Analytics Connection

This project introduces several concepts that are useful in Data Analytics.

The basic workflow is:

```text
Input Data
    ↓
Store Data
    ↓
Transform Data
    ↓
Calculate Summary
    ↓
Filter Data
    ↓
Sort Data
    ↓
Generate Insights
```

The project therefore provides a small-scale example of how raw numerical data can be **stored, transformed, filtered, sorted, and summarized**.

---

# 🚀 How to Run

## Step 1 — Install Python

Make sure Python 3 is installed.

Check the installation:

```bash
python --version
```

---

## Step 2 — Save the Python File

Save the program as:

```text
data_analyzer.py
```

---

## Step 3 — Open Terminal

Navigate to the folder containing the Python file:

```bash
cd path\to\Data-Analyzer-and-Transformer
```

---

## Step 4 — Run the Program

```bash
python data_analyzer.py
```

The main menu will appear.

---

# ⚠️ Important Notes

* The program expects numerical input.
* 1D and 2D data are both supported.
* The summary is calculated from flattened data.
* Lambda filtering returns values greater than the entered threshold.
* The sorting demo uses both `sort()` and `sorted()`.
* `show_kwargs(**summary)` depends on the summary dictionary containing data.
* The factorial function uses recursion.
* The program uses global variables for `data` and `summary`.

---

# 🔮 Future Improvements

Possible improvements for a future version include:

* Add `try-except` validation for invalid input
* Add CSV file import/export
* Add Pandas integration
* Add NumPy integration
* Add more statistical calculations
* Add median and standard deviation
* Add graphical data visualization
* Add data saving functionality
* Add search functionality
* Add data cleaning operations
* Add Excel integration
* Add Power BI integration

---

# 📌 Project Highlights

* 🐍 Python Data Analysis Project
* 📊 1D & 2D Data Handling
* 🔄 Data Transformation
* 📈 Statistical Summary
* 🔢 Recursive Factorial
* 🔎 Lambda Filtering
* 🔃 Sorting Operations
* 📦 `*args` & `**kwargs`
* 🔢 Multiple Return Values
* 🧠 Core Python Programming Concepts
* 💻 Interactive Console Application

---

# 👨‍💻 Author

**Hardik Kumawat**

Data Analytics Learner | Python | SQL | Excel | Power BI

---

## ⭐ Project Purpose

This project was created as a practical Python learning project to strengthen **core Python programming, data transformation, basic data analysis, functional programming concepts, and problem-solving skills**.

