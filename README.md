# Training Diary 2026
## Day 1
## Date: 22 June 2026
## Introduction to Python  
On the first day of the AI/ML training program, we installed Python and learned about different platforms for writing and executing Python code. We were introduced to Google Colab, a cloud-based environment that allows users to write and run Python programs directly through a web browser without installing software locally.
## Learning Objectives
By the end of this session, you will understand:
1. **Variables**: What they are and how Python handles them in memory (the "reference" model).
2. **Data Types**: The built-in data types in Python (`int`, `float`, `complex`, `str`, `list`, `tuple`, `dict`, `set`, `bool`, `None`).
3. **Mutability vs. Immutability**: Why this distinction is critical for data science.
4. **Type Casting**: How to convert between different data types.
5. **Best Practices**: Variable naming conventions in Python.  
### Write a python program that takes a student's name and marks as input and prints a formatted result card showing Pass/Fail.   
<img width="443" height="315" alt="Example 1" src="https://github.com/user-attachments/assets/4e04a1e7-0d5d-41fb-9bad-f6e0f3c7efbe" />  

<img width="524" height="641" alt="Example 2" src="https://github.com/user-attachments/assets/3d76de61-1545-4afd-8ba3-c39a9f9c0d1c" />  

## 1. Variables: Pointers to Memory

In many programming languages (like C or Java), a variable is seen as a **labeled box** that holds a value. 
In Python, however, a variable is a **nametag (reference)** attached to an **object** in memory.

When you write:
```python
x = 42
```
Python does three things:
1. Creates an integer object with the value `42` in memory.
2. Creates a variable name `x`.
3. Binds (links) the name `x` to the memory address of the object `42`.

We can inspect the memory address using the `id()` function, and check the type of the object using `type()`.  
<img width="686" height="471" alt="Variable image 1" src="https://github.com/user-attachments/assets/b7897fe6-4863-40ce-afa8-38dc6f5bc4e5" />  

### 1.1 Sharing References
When you assign one variable to another, e.g., `y = x`, Python does **not** copy the value. Instead, it makes `y` point to the **same object** that `x` is pointing to.  
<img width="898" height="346" alt="Reference image" src="https://github.com/user-attachments/assets/82020531-e937-48cc-b056-72173329f6b6" />  

### 1.2 Dynamic Typing
Python is **dynamically typed**, meaning you do not need to declare the variable type beforehand. The type is associated with the *object*, not the *variable name*. A variable name can point to an integer at one point and a string at another.  
<img width="395" height="229" alt="Dynamic typing" src="https://github.com/user-attachments/assets/72cf12ed-d998-4c58-afca-1f3af40a0df4" />  

## 2. Core Built-in Data Types

Python has several standard data types built-in. Let's look at them grouped by category.

### 2.1 Numeric Types
- `int`: Integers (positive, negative, zero, of unlimited precision).
- `float`: Decimal numbers (IEEE 754 double precision floating-point).
- `complex`: Complex numbers written as `real + imag j`.  
<img width="953" height="560" alt="numeric" src="https://github.com/user-attachments/assets/972862c1-7df0-4d57-ac01-9905af0dacd6" />  

### 2.2 Text / String Type
- `str`: Strings in Python are Unicode-compliant characters enclosed in single `'`, double `"`, or triple `'''` or `"""` quotes (useful for multi-line strings).
<img width="937" height="369" alt="string" src="https://github.com/user-attachments/assets/8ec678b0-7693-4e28-b599-09ca975ae633" />

### 2.3 Boolean & None Types
- `bool`: Logical values `True` or `False`. Used extensively in conditions and loops.
- `NoneType`: Represented by the keyword `None`. Indicates the absence of a value or a null value (similar to `null` in Java/C++).
<img width="658" height="283" alt="Boolean type" src="https://github.com/user-attachments/assets/324187b6-b677-4bcc-afd3-99a73b0108a7" />

## 3. Mutability vs. Immutability

This is one of the most important concepts to master in Python. 

- **Immutable Objects**: Once created, their value **cannot** be changed in place. 
  - Examples: `int`, `float`, `str`, `tuple`, `bool`, `frozenset`.
- **Mutable Objects**: Their value **can** be changed in place without changing their identity (memory address).
  - Examples: `list`, `dict`, `set`.

 ### 3.1 Immutable Behavior (e.g., Integer)
Let's modify an integer and observe its memory address before and after.  
<img width="1152" height="284" alt="immutable" src="https://github.com/user-attachments/assets/0cb9909e-fd42-4b37-b2a8-3126f32273d9" />  

### 3.2 Mutable Behavior (e.g., List)
Let's modify a list and observe its memory address.  
<img width="499" height="137" alt="image" src="https://github.com/user-attachments/assets/1b18cc05-c2ce-4b50-aad9-d2690e989957" />  

### 3.3 The Danger of Mutable References
Because mutable objects can be modified in-place, having multiple variables reference the same mutable object can lead to unexpected bugs.  
<img width="1636" height="523" alt="Danger of mutable " src="https://github.com/user-attachments/assets/cfd72656-f71d-40c0-884d-35cb921c94f2" />  

### 3.4 How to Avoid Mutable Reference Bugs
If you want to copy a mutable object without referencing the same one, you need to create a **copy** of it.  
<img width="841" height="341" alt="Avoid bug errors" src="https://github.com/user-attachments/assets/b6136d03-5fc8-4e31-aec9-fa2d0fedfb7c" />  

## 4. Sequence & Collection Types

Let's briefly introduce Python's main collection types which are heavily used in AI/ML data preprocessing:

1. **List** (`list`): Ordered, mutable, allows duplicate elements.
2. **Tuple** (`tuple`): Ordered, **immutable**, allows duplicate elements. Think of it as a read-only list.
3. **Dictionary** (`dict`): Unordered (ordered by insertion in Python 3.7+), mutable, key-value pairs, keys must be unique and immutable.
4. **Set** (`set`): Unordered, mutable, unique elements only.
<img width="592" height="282" alt="image " src="https://github.com/user-attachments/assets/196738c4-cdaa-4fad-8c53-bdd2b87e0110" />  

<img width="1075" height="475" alt="collections" src="https://github.com/user-attachments/assets/35970ac2-5308-4be6-ad2b-9f7e56469ed2" />  

## 5. Type Casting / Conversion

Type casting is the process of converting a variable from one data type to another.

- **Implicit Type Conversion**: Done automatically by Python interpreter (e.g., adding an `int` and a `float` yields a `float`).
- **Explicit Type Conversion**: Done manually using Python constructor functions like `int()`, `float()`, `str()`, `list()`, `tuple()`, `set()`, etc.
<img width="819" height="658" alt="implicit and explicit" src="https://github.com/user-attachments/assets/57f729a3-3de7-4ace-a9fd-cc0e875df150" />

## Operators in Python  
Operators are symbols used to perform operations on values and variables.

## 1. Arithmetic Operators  
Used to perform mathematical calculations.

|Operator |	      Description     |	Example     |
|---------|-----------------------|-------------|
|   +	    |   Addition            |	5 + 2 = 7   |
|   -	    |   Subtraction         |	5 - 2 = 3   |
|   *	    |   Multiplication      |	5 * 2 = 10  |
|   /	    |   Division	          | 5 / 2 = 2.5 |
|   %	    |   Modulus (Remainder) |	5 % 2 = 1   |
|  //	    |   Floor Division	    | 5 // 2 = 2  |
|  **	    |   Exponentiation	    | 5 ** 2 = 25 |

<img width="377" height="334" alt="Arithmetic operators" src="https://github.com/user-attachments/assets/d643e16b-d97a-4dd3-a87e-8d10e17ba89d" />  

## 2. Comparison Operators  
Used to compare two values and return True or False.

|Operator|	Meaning                  |
|--------|---------------------------|
|  ==	   | Equal to                  |
|  !=	   | Not equal to              |
|   >	   | Greater than              |
|   <	   | Less than                 |
|  >=	   | Greater than or equal to  |
|  <=	   | Less than or equal to     | 

<img width="306" height="253" alt="comparison" src="https://github.com/user-attachments/assets/e0f93ba1-f875-4b3e-8600-5073f259bfec" />

## 3. Logical Operators  
Used to combine conditional statements.

|Operator|	Description                                   |
|--------|------------------------------------------------|
|   and	 |Returns True if both conditions are True        |
|   or	 |Returns True if at least one condition is True  |
|   not	 |Reverses the result                             |

<img width="414" height="297" alt="logical" src="https://github.com/user-attachments/assets/02dd9b70-2433-4f59-853d-c39d1ce0ede2" />  

## 4. Assignment Operators  
Used to assign and update values in variables.

|Operator|	Example |
|--------|----------|
|  +=    |  x += 5  |
|  -=	   |  x -= 5  |
|  *=	   |  x *= 5  |
|  /=	   |  x /= 5  |
|  //=	 |  x //= 5 |
|  **=	 |  x **= 5 |

<img width="573" height="297" alt="Assignment operators" src="https://github.com/user-attachments/assets/0fa6fee4-e8e8-4dae-91dc-b8a367efb343" />  

## Day 2  
## 23 June 2026  
## 5. Bitwise Operators  
Bitwise operators are used to compare (binary) numbers:  

|Operator|	Name |	Description|	Example|
|--------|-------|-------------|---------|
|   &    | 	AND	 |Sets each bit to 1 if both bits are 1|x & y|
|   \|   |  OR   |Sets each bit to 1 if one of two bits is 1| x \| y |
|   ^	   |  XOR  |Sets each bit to 1 if only one of two bits is 1|x ^ y|	
|   ~    |	NOT  |Inverts all the bits|	~x|	
|   <<	 |Zero fill left shift|Shift left by pushing zeros in from the right and let the leftmost bits fall off|x << 2|
|   >>	 |Signed right shift|	Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off|x >> 2|

<img width="411" height="527" alt="bitwise" src="https://github.com/user-attachments/assets/0c51fbe0-995c-4ec6-af08-b8f3a0e09f64" />  

## 6. Membership operator  
Membership operators are used to test if a sequence is presented in an object:  

|Operator|Description|Example|
|--------|-----------|--------|
|   in 	 |Returns True if a sequence with the specified value is present in the object|x in y|	
| not in |Returns True if a sequence with the specified value is not present in the object|x not in y|

<img width="422" height="230" alt="Membership" src="https://github.com/user-attachments/assets/34ae9cc2-7103-4c5b-8cea-64428a9f9375" />  

## 7. Identity operator  
Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location:  

|Operator|Description|Example|
|--------|-----------|-------|
|   is 	 |Returns True if both variables are the same object|x is y|	
| is not |Returns True if both variables are not the same object|x is not y|

<img width="290" height="440" alt="Identity" src="https://github.com/user-attachments/assets/5b767a96-fb20-4ef6-bfc6-59058a119e2c" />  

## Python Loops: `for` and `while`  
Loops allow us to repeat a block of code multiple times. In Python, there are two native loops: `for` and `while`.  

### 1 The `for` Loop and `range()`  
The `for` loop is iterator-based. It traverses a sequence (list, tuple, string, set, dictionary) or an iterator.  
We use `range(start, stop, step)` to generate a sequence of numbers:  
- `start` (optional): Defaults to 0.  
- `stop` (required): Generates numbers up to, but not including, this value.  
- `step` (optional): Step value for incrementing (or decrementing).  
<img width="402" height="434" alt="for loop 1" src="https://github.com/user-attachments/assets/2a18b1c1-27bf-4a68-87da-c84bff9d531e" />  
 
<img width="513" height="676" alt="iterating over a list" src="https://github.com/user-attachments/assets/8fd5ac95-68f8-4321-b6e0-d5d1e436a60b" />  
<img width="502" height="315" alt="password example" src="https://github.com/user-attachments/assets/6cbb1b47-51ee-4dc1-a34d-835ffe5a37f8" />  

<img width="257" height="340" alt="for loop" src="https://github.com/user-attachments/assets/80bcea96-152e-4c49-98ac-3e58ac5facbc" />  

### 2 The `while` Loop  
A `while` loop continues executing a block of code as long as a specified condition is `True`.   

**Warning**: You must ensure that the condition is updated inside the loop to eventually evaluate to `False`, otherwise you will create an **infinite loop**.  
<img width="563" height="227" alt="while loop 1" src="https://github.com/user-attachments/assets/f642fbd5-01e9-4cd0-ab12-613f8e451806" />  

### 3 How to Use Loops (Practical Iteration & Controls)  
#### A. Loop Control Statements:  
Python provides control statements to modify the execution flow of loops:  
##### 1. The `break` Statement  
The `break` statement terminates the loop immediately when triggered, jumping to the code execution directly after the loop.  
<img width="295" height="178" alt="image" src="https://github.com/user-attachments/assets/033ee08a-6e4e-4db0-b3a5-ce36100370a7" />  

##### 2. The `continue` Statement  
The `continue` statement skips the rest of the current loop iteration and moves directly to the next iteration.  
<img width="408" height="405" alt="continue" src="https://github.com/user-attachments/assets/794ee728-15eb-4f4d-a298-afaaf8380abf" />  

##### 3. The `pass` Statement  
The `pass` statement is a null operation. It does nothing and acts as a placeholder when the syntax requires a statement, but no action is needed yet.  
<img width="754" height="300" alt="pass statement" src="https://github.com/user-attachments/assets/14d85db8-f6f5-480d-b640-8bc6cfaaa45c" />  

#### B. The Unique Loop `else` Clause:
In Python, loops can have an optional `else` block. The `else` block executes **only if the loop terminates normally** (i.e., completes all iterations without hitting a `break` statement). If a `break` is triggered, the `else` block is skipped.  
<img width="870" height="410" alt="Loop else" src="https://github.com/user-attachments/assets/c9742dd6-84ce-4585-ac0e-f26e09b5ac06" />  

## Control Flow Statements in Python  
Control flow allows programs to make decisions and execute different blocks of code dynamically.  

### Syntax of Conditional Branching (`if`, `elif`, `else`)  
```python
if condition1:
    # executes if condition1 is True
elif condition2:
    # executes if condition1 is False and condition2 is True
else:
    # executes if all previous conditions are False
```
### Exercise : Control Flow Branching
Write a script that classifies a person's age into the following categories:
- `age < 13`: "Child"
- `age` between 13 and 19 (inclusive): "Teenager"
- `age` between 20 and 59 (inclusive): "Adult"
- `age >= 60`: "Senior"
<img width="313" height="313" alt="control flow branching" src="https://github.com/user-attachments/assets/1d19d634-0304-41f0-b2a3-7832b0c32f37" />

## Day 3
## 24 June 2026
## Python Foundations — Functions and Modular Programming  
**Functions**—the building blocks of reusable and modular code. In AI/ML, functions are used everywhere: from defining custom data preprocessing pipelines, wrapping evaluation metrics, designing neural network layers, to structuring experiment run loggers.  
## Learning Objectives  
1. **Built-in Functions**: Explore and apply standard Python helper functions (`len`, `sum`, `max`, `min`, `abs`, `round`).
2. **Custom Functions**: How to define and call your own functions using the `def` keyword.
3. **Parameters vs. Arguments**: Passing information into functions.
4. **The `return` Statement**: Getting results back from functions to use in other calculations.
5. **Types of Arguments**: Positional, keyword, default parameters, and variable-length arguments (`*args`, `**kwargs`).
6. **Variable Scope**: Understanding local vs. global variables and the `global` keyword.
7. **Recursive Functions**: Functions that call themselves (e.g., Factorial, Fibonacci).
## 1. Built-in (Inbuilt) Functions in Python

Python has several functions that are already created and ready to use. These are called **built-in functions**. In AI/ML, we use them constantly to get basic statistics of our dataset, inspect list lengths, or round float metrics.

Commonly used built-in functions:
- `len(sequence)`: Returns the number of items in a list, tuple, set, string, etc.
- `sum(iterable)`: Adds up all elements of a numerical collection.
- `max(iterable)` / `min(iterable)`: Returns the largest or smallest element.
- `abs(number)`: Returns the absolute (positive) value of a number (important for calculating absolute errors).
- `round(number, digits)`: Rounds a floating-point number to a specified number of decimal places.
- `print(...)`: Outputs text or values to the screen.
<img width="271" height="630" alt="bulit in functions" src="https://github.com/user-attachments/assets/fa9eb1c4-d074-4791-b4c7-8865cd54139c" />

## 2. Creating Custom Functions

While built-in functions are great, most of the time we need to write custom logic. In Python, we define a function using the **`def`** keyword, followed by the function name, parentheses `()`, and a colon `:`. The code inside the function must be indented.

### 2.1 Defining and Calling a Simple Function
A function does not run when you define it; it only runs when you explicitly **call** (execute) it by writing its name followed by parentheses.  
<img width="613" height="276" alt="custom function" src="https://github.com/user-attachments/assets/7b16bc01-9278-40b0-9ab9-c50856570bdd" />  

### 2.2 Parameters and Arguments
Functions are much more useful when we can pass data into them. We do this by defining **parameters** (variable placeholders) inside the parentheses. When calling the function, we pass the actual values (**arguments**) into it.
- **Parameter**: The variable listed in the function definition (e.g., `username`).
- **Argument**: The actual value sent to the function when it is called (e.g., `"Amit"
<img width="924" height="298" alt="function 1" src="https://github.com/user-attachments/assets/6313c482-2a61-4469-b190-11b427fa70dd" />

## 3. The `return` Statement

In the previous exercise, your function printed the sum on the screen. However, printing is only for humans to see. In a program, we usually need the function to **return** the calculated value back so we can save it in a variable and use it in other calculations.

We use the **`return`** keyword to send a value back to the caller.

> [gradient-alert]
> A function exits immediately when it hits a `return` statement. Any lines of code written after `return` inside the same function scope are **unreachable** and will not execute.
> <img width="805" height="471" alt="return statement" src="https://github.com/user-attachments/assets/cf733a64-abaa-4822-9c49-d5a6ef3ade07" />

## Day 4
## 25 June 2026
## 4. Types of Arguments

Python is highly flexible in how parameters are passed to functions. Let's look at the primary ways:

### 4.1 Positional vs. Keyword Arguments
- **Positional Arguments**: Assigned based on the order they are passed.
- **Keyword Arguments**: Passed with name-value pairs (e.g., `parameter=value`), allowing you to pass them in any order.

### 4.2 Default Arguments
You can assign a default value to a parameter in the function definition. If the caller does not pass an argument for that parameter, the default is used.  
<img width="859" height="456" alt="various using arguments" src="https://github.com/user-attachments/assets/1a9e895e-2a80-4b88-a15a-33c71a5225d6" />  

### 4.3 Variable-Length Arguments (`*args` and `**kwargs`)
Sometimes, you don't know how many arguments will be passed to your function. Python provides two special symbols:
- **`*args`**: Collects extra positional arguments into a **Tuple**.
- **`**kwargs`**: Collects extra keyword arguments into a **Dictionary**.
<img width="822" height="247" alt="args" src="https://github.com/user-attachments/assets/c430cb96-3f79-448c-92a8-b212394972d4" />

<img width="1219" height="308" alt="kwargs" src="https://github.com/user-attachments/assets/c7ece91e-1591-4b08-9340-fa731c7ea9a6" />  

## 5. Variable Scope: Local vs. Global

Variables are not accessible everywhere in a Python script. Where a variable is defined determines its **scope**:
- **Global Scope**: Variables defined outside any function. They can be read anywhere in the file.
- **Local Scope**: Variables defined inside a function. They can only be accessed *inside* that function. Once the function finishes running, local variables are destroyed.
<img width="546" height="400" alt="global and local" src="https://github.com/user-attachments/assets/6e74232f-0a7f-47b0-b92e-3e84fe744798" />

### The `global` Keyword
If you try to change a global variable inside a function, Python will normally create a new local variable with the same name. To modify the actual global variable, you must declare it using the **`global`** keyword.  
<img width="590" height="334" alt="global keyword" src="https://github.com/user-attachments/assets/8d0550d4-f094-41d6-b095-5783a9309954" />  

## 6. Recursive Functions

A **recursive function** is a function that calls itself to solve a problem. It works by breaking a complex problem down into smaller, simpler steps of the same problem.

Every recursive function must have two crucial parts:
1. **Base Case**: A simple condition that stops the recursion (prevents infinite loops!).
2. **Recursive Case**: The section where the function calls itself with a slightly simpler input.

### 6.1 Simple Example: Factorial
The factorial of a number $n$ (written as $n!$) is the product of all positive integers less than or equal to $n$.
For example: $5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$.
Formula: $n! = n \times (n-1)!$ with base case $0! = 1$ and $1! = 1$.  
<img width="702" height="297" alt="Recursive function" src="https://github.com/user-attachments/assets/3b68c097-62ab-4889-bff7-137348f59d1f" />  

# Python Foundations — Python Data Structures (Lists, Tuples, Dictionaries, and Sets)  
**Data Structures**—the backbone of data storage, manipulation, and processing in Python. In AI/ML, these collections are absolutely crucial: from organizing features and training labels, to configuring hyperparameters, creating vocabularies, and filtering unique class labels.  

## Learning Objectives
1. **Lists**: Mutable ordered sequences, common methods, indexing/slicing, and how they represent features and labels.
2. **Tuples**: Immutable ordered sequences, memory/speed efficiency, packing/unpacking, and representing fixed dimensions (like image shapes).
3. **Dictionaries**: Key-value mappings (hash maps), keys hashability rule, safe lookups (`.get()`), and storing model configurations/evaluation metrics.
4. **Sets**: Unordered unique collections, set operations (union, intersection, difference), and handling class labels/vocabulary overlap in datasets.
5. **Data Structures in Action**: Side-by-side coding questions for immediate practice.
6. **Comprehensive Practice**: Complex questions at the end to integrate everything you've learned.

## 1. Lists: Mutable Sequences

A **List** in Python is an ordered, mutable sequence of items. It allows duplicates and can contain elements of different data types (though in AI/ML, we usually keep them homogeneous for tabular data).

### 1.1 Memory Representation & Mutability
- Lists store **references (pointers)** to objects in memory rather than the actual values directly in a contiguous block.
- Because lists are **mutable**, you can change, add, or remove elements in-place without changing the identity (`id()`) of the list itself.

### 1.2 Useful List Operations for AI/ML
- **Appending & Extending**: `.append(x)` adds a single item, `.extend(iterable)` adds multiple items (e.g., merging batches).
- **Inserting & Removing**: `.insert(index, x)`, `.remove(value)` (removes first occurrence), and `.pop(index)` (removes and returns item).
- **Slicing**: Extremely important for batching and sequence slicing: `list[start:end:step]`.
- **Sorting**: `.sort()` sorts in-place, whereas `sorted(list)` returns a new sorted list.

<img width="858" height="864" alt="List types" src="https://github.com/user-attachments/assets/d9f8d926-bfca-40d8-a3af-6d132ec131ca" />

## Day 5  
## 26 June 2026
## 2. Tuples: Locked-down Sequences

A **Tuple** is an ordered, **immutable** sequence of items. Once a tuple is created, its values cannot be altered, added, or deleted.

### 2.1 Why Use Tuples in AI/ML?
- **Data Safety**: Prevents accidental modification of constant parameters (e.g., `image_shape = (224, 224, 3)`).
- **Performance**: Tuples are faster to construct and use less memory than lists because they are allocated in a single, fixed-size memory block.
- **Dictionary Keys**: Because tuples are immutable, they are hashable and can be used as dictionary keys (lists cannot).

### 2.2 Unpacking and Wildcards
- We can extract elements of a tuple into individual variables directly (unpacking).
- We can use the wildcard operator `*` to capture multiple elements into a list during unpacking.

<img width="432" height="363" alt="Tuples" src="https://github.com/user-attachments/assets/30b4f062-bad5-40c4-98c4-faecdfd88e4e" />  

## Wildcard Unpacking  
Wildcard unpacking in Python tuples means using the * operator while unpacking a tuple to collect multiple values into a list.  
### Syntax  
a, *b, c = tuple_name  
a → gets the first element.  
*b → gets all the middle elements as a list.  
c → gets the last element.  

<img width="501" height="303" alt="Wildcard unpacking" src="https://github.com/user-attachments/assets/b224ae79-1fac-4ce7-97b1-bc0b3a54e7e9" />  

### Exercise: Dataset Split Unpacker (Tuples)

When training ML models, we split our dataset into train, validation, and test splits.

1. Write a function `unpack_splits(split_tuple)` that takes a nested tuple formatted as: `( (X_train, y_train), (X_val, y_val), (X_test, y_test) )`.
2. The function should unpack these splits and print:
   - The size/length of `X_train`
   - The size/length of `X_val`
   - The size/length of `X_test`
3. Test your function with the provided `dataset_splits` variable.

<img width="695" height="537" alt="Dataset S lit Unpacker" src="https://github.com/user-attachments/assets/32ccc700-7496-41dd-9744-2d96b5df0fb2" />  

<img width="308" height="261" alt="tuple example" src="https://github.com/user-attachments/assets/89f0e1c9-e7d9-41f8-b43e-e2a720ca8498" />  

## 3. Dictionaries: Fast Key-Value Maps

A **Dictionary** in Python is an unordered (insertion-ordered since 3.7) collection of key-value pairs. Dictionaries use an underlying **Hash Table**, allowing key lookups in constant time ($O(1)$ on average), which is incredibly fast!

### 3.1 Rules of Hashability
- **Keys** MUST be **immutable** (hashable) objects (e.g., strings, numbers, tuples). You cannot use lists or dictionaries as keys.
- **Values** can be anything, including lists, other dictionaries, or custom objects.

### 3.2 Key Methods
- **Accessing Safely**: Using `dict[key]` raises a `KeyError` if the key doesn't exist. Using `dict.get(key, default)` returns the default value (or `None`) safely without crashing.
- **Iteration**: Use `.keys()`, `.values()`, or `.items()` (which returns a view of key-value tuples).
- **Updating**: `dict[key] = value` updates or inserts the key-value pair.  

<img width="828" height="671" alt="Dictionary" src="https://github.com/user-attachments/assets/e3c5db5b-8ea0-4238-9dc1-569d6d422545" />  

## Counting Occurrences of List Elements Using Dictionary:  
This program uses a dictionary to count how many times each element appears in a list. The count() method finds the number of occurrences of each element, and the dictionary stores the element as the key and its frequency as the value.  

<img width="440" height="379" alt="counting frequency using dictionary" src="https://github.com/user-attachments/assets/2ed7110d-26b9-4c3c-a6d1-8ac5e81bd814" />  

## 4. Sets: Unique Collections

A **Set** is an unordered collection of unique elements. Like dictionaries, sets use hash tables under the hood, making membership tests (`element in set`) extremely fast ($O(1)$).

### 4.1 Set Operations
Sets are ideal for mathematical operations:
- **Union** (`|` or `.union()`): Combined unique elements from both sets.
- **Intersection** (`&` or `.intersection()`): Elements present in both sets.
- **Difference** (`-` or `.difference()`): Elements in the first set but not the second.
- **Symmetric Difference** (`^` or `.symmetric_difference()`): Elements in either set, but not both.

<img width="326" height="244" alt="Sets example" src="https://github.com/user-attachments/assets/e62ebf44-958e-4401-a43b-3211a15dcadf" />  

## Example of Union, Intersection, Difference:  
<img width="758" height="548" alt="Example of Union, Intersection, Difference" src="https://github.com/user-attachments/assets/f025bfa1-1c65-4141-bc4b-b611a19f9bf0" />  

## Day 6  
## 29 June 2026
## NumPy Essentials for AI & Machine Learning  
we transition from pure Python to **NumPy** (Numerical Python), the most important library for handling numbers, matrices, and datasets in AI.  
In AI and Machine Learning, your data is always represented as grids of numbers (like rows of data, pixel values in images, or word frequencies in texts). While Python lists can store these numbers, they are very slow. NumPy introduces a special array structure that runs up to 100x faster than standard Python lists.  

## Learning Objectives  
1. **NumPy Arrays vs. Python Lists**: Why NumPy is faster (Memory Layout).
2. **Creating Arrays & Attributes**: Creating 1D and 2D arrays, and checking `.shape` and `.dtype`.
3. **Vectorization**: Performing math operations on full datasets without writing slow `for` loops.
4. **Slicing & Indexing**: Extracting features ($X$) and labels ($y$) from a dataset.
5. **Data Cleaning & Filtering**: Using Boolean masks and `np.where()` to handle outliers or invalid data.
6. **Statistical Summaries & Broadcasting**: Calculating mean/standard deviation and standardizing data.
7. **Reshaping & Flattening**: Changing array structures for model inputs.

## 1. Introduction: Why NumPy Arrays?

- **Python Lists**: Store pointers to values scattered across your computer's memory. This makes them flexible but slow for doing heavy calculations.
- **NumPy Arrays**: Store numbers directly side-by-side in a **contiguous block of memory** of a single data type. This allows your CPU to perform operations on the numbers instantly.

Let's import `numpy` (usually as `np`) and create our first arrays:  
<img width="497" height="181" alt="numpy" src="https://github.com/user-attachments/assets/edf7fff5-4659-463e-9963-b458c87f8f6d" />  

<img width="618" height="365" alt="numpy 1d array" src="https://github.com/user-attachments/assets/12f71473-6be4-4d6e-957d-21579ae28bf4" />  

<img width="543" height="370" alt="numpy 2d array" src="https://github.com/user-attachments/assets/a132ec6e-f08a-4ffa-a24b-10628d049947" />

## 2. Vectorization: Math Without Loops

If you want to perform math on every item in a Python list, you must write a `for` loop. In NumPy, you can do math operations directly on the array. NumPy applies the operation to every element automatically. This is called **vectorization**.  

<img width="632" height="484" alt="vectorized" src="https://github.com/user-attachments/assets/23050619-51c8-48c7-8ddd-024c4f09ca82" />  

### Speed Comparison: Python Loop vs. NumPy Vectorization
Let's see the speed difference by adding one million numbers together:  

<img width="633" height="655" alt="speed comparison" src="https://github.com/user-attachments/assets/851f93fe-de01-4bd8-b595-2f1c19a328a6" />  

## 3. Indexing & Slicing

In Machine Learning, datasets are 2D grids (matrices):
- **Rows** represent individual data samples (e.g., houses, patients, customers).
- **Columns** represent characteristics or features (e.g., area, number of rooms, price).

We slice arrays using: `array[row_indices, column_indices]`. The colon `:` means "select all" along that direction.  

<img width="321" height="483" alt="indexing" src="https://github.com/user-attachments/assets/68e1ba1c-0c1b-42ca-8a42-f3015d12f6cf" />  

<img width="257" height="327" alt="slicing" src="https://github.com/user-attachments/assets/e675bfb9-0c35-4cc0-aa89-c13bd47623ab" />  

## 4. Data Filtering & Cleaning (Boolean Masking & `np.where`)

Datasets often contain mistakes, missing values, or outliers (e.g., negative salaries or zero values where it's impossible). NumPy allows us to filter these out easily.  

<img width="742" height="474" alt="np where" src="https://github.com/user-attachments/assets/90277e78-4831-4355-ad8f-75e2f109f27b" />  

## 5. Statistical Summaries & Standardization (Broadcasting)

NumPy offers functions to calculate dataset metrics. 
- `axis=0`: Perform calculation column-wise (vertical down).
- `axis=1`: Perform calculation row-wise (horizontal across).

<img width="736" height="626" alt="mean and median" src="https://github.com/user-attachments/assets/c88bec69-ed6d-4e68-9238-b52e7932d2d6" />  

## 6. Reshaping & Flattening

AI models sometimes require inputs of specific shapes (e.g. flattening image pixels from a 2D matrix into a 1D vector).  

<img width="615" height="534" alt="Reshaping and flatten" src="https://github.com/user-attachments/assets/5ecd954c-3bf1-458d-ab02-03c72e0c4270" />  

## 7. Bonus: Matrix Multiplication (The Dot Product)

In neural networks, we multiply inputs by weight grids to make predictions. In NumPy, matrix multiplication is done using the `@` operator or the `np.dot()` function.  

<img width="457" height="561" alt="Dot product" src="https://github.com/user-attachments/assets/842645f5-947d-4875-96fb-8db91e7cf91b" />  

## Normalization
Standardize input values for training a model using mean and standard deviation.
1. Calculate the column-wise mean of features matrix `X` below.
2. Calculate the column-wise standard deviation of `X` using `np.std()`.
3. Standardize `X` in a single line using broadcasting.
   - Formula: $X_{normalized} = \frac{X - mean}{std}$

<img width="333" height="584" alt="normalization" src="https://github.com/user-attachments/assets/29e85986-4121-4ad9-bc42-6bc81e4ab0eb" />  

# NumPy Fundamentals

Welcome to **Day 9 of your Data Science Journey**! Today, we start learning about **NumPy (Numerical Python)**, which is the foundational library for scientific computing and data analysis in Python.

## What is NumPy?
NumPy is an open-source Python library that provides support for large, multi-dimensional arrays and matrices, along with a collection of high-level mathematical functions to operate on these arrays.

### Why do we need NumPy in Data Science?
You might wonder: *Why not just use standard Python lists?*
Standard Python lists are highly flexible because they can hold elements of different data types. However, this flexibility makes them slow and memory-intensive for large datasets. NumPy arrays resolve this limitation. Here is a comparison:

| Feature | Python Lists | NumPy Arrays (`ndarray`) |
| :--- | :--- | :--- |
| **Data Type** | Heterogeneous (can store integers, strings, floats together) | Homogeneous (all elements must be of the same type) |
| **Memory Layout** | Non-contiguous (elements are pointers scattered in memory) | Contiguous (stored next to each other in memory) |
| **Speed** | Slow (requires type checking and pointer dereferencing) | Extremely fast (processed close to CPU/hardware speed) |
| **Operations** | Elements must be modified in loops | Supports vectorized operations (no loops needed) | 

### 🧠 Memory Structure Visualization:
```text
Python List (Pointers to Objects):
[ List Object ] ──► [Pointer 0] ──► [ Integer Object: 1 ]
                    [Pointer 1] ──► [ Integer Object: 2 ]
                    [Pointer 2] ──► [ Integer Object: 3 ]

NumPy Array (Contiguous Blocks of Raw Bytes):
[ Array Metadata ] ──► [ 1 ][ 2 ][ 3 ] (Raw binary memory values in contiguous blocks)
```

## Module 1: Creating NumPy Arrays & Inspecting Attributes

The core data structure of NumPy is the **`ndarray`** (N-dimensional array). Let's explore the various ways to create arrays and check their characteristics.

### 1.1 Creating Arrays from Lists
You can convert standard Python lists or tuples into arrays using `np.array()`.  

<img width="288" height="304" alt="creating array from lists" src="https://github.com/user-attachments/assets/b08411ea-3fc6-4189-bf89-a2033941d8e1" />  

### 1.2 Defining Array Data Types (`dtype`)
NumPy allows you to explicitly specify the data type of the elements during array creation using the `dtype` parameter. Common types include: `np.int32`, `np.int64`, `np.float32`, `np.float64`, and `np.bool_`.  

<img width="622" height="210" alt="data type" src="https://github.com/user-attachments/assets/bebd9924-1c84-428f-91be-cb21967cbbec" />  

### 1.3 Built-in Functions for Array Creation
Creating empty, filled, or structured arrays is highly useful for numerical computation. NumPy provides standard helpers:
* `np.zeros(shape)`: Creates an array filled with 0s.
* `np.ones(shape)`: Creates an array filled with 1s.
* `np.arange(start, stop, step)`: Creates an array with values from start to stop (exclusive).
* `np.linspace(start, stop, num)`: Creates an array with `num` evenly-spaced values over a specified interval (inclusive).
* `np.eye(n)`: Creates an identity matrix of size $n \times n$.

<img width="469" height="190" alt="np zeros" src="https://github.com/user-attachments/assets/afd2f6ea-52df-4ebf-aa92-0709d7594bf0" />  

<img width="264" height="144" alt="np ones" src="https://github.com/user-attachments/assets/50a17753-333b-46eb-9dc6-130088a2fe8b" />  

<img width="877" height="320" alt="np arange" src="https://github.com/user-attachments/assets/d2d78b4e-5ccd-4d88-8e95-ab38a9bde279" />  

<img width="790" height="166" alt="np linspace" src="https://github.com/user-attachments/assets/6b1fcd6e-f0e6-41ef-ac69-c4893c5e15fb" />  

<img width="1002" height="233" alt="np eye" src="https://github.com/user-attachments/assets/d8f005b9-ddf1-4ba3-b915-1b2282b78cf5" />  

### 1.4 Array Attributes
Every NumPy array has specific attributes that provide structural details:
* `.ndim`: Number of dimensions (axes).
* `.shape`: Dimensions of the array (represented as a tuple: (rows, columns)).
* `.size`: Total number of elements in the array.
* `.dtype`: Data type of elements.
* `.itemsize`: Size of one array element in bytes.

<img width="667" height="469" alt="Array Attributes" src="https://github.com/user-attachments/assets/68d29887-8d4c-410d-8b59-078222c0d959" />  

## Module 2: Indexing in NumPy

Indexing allows you to select single values or complete subsets from an array.

### 2.1 1D Array Indexing
Works exactly like Python list indexing (using `0` for the first element, `-1` for the last element).  
<img width="504" height="413" alt="1d array indexing" src="https://github.com/user-attachments/assets/da691b2f-cfcd-480b-a9cd-32d5fc297fda" />  

### 2.2 2D Array Indexing (Matrices)
In standard Python, a 2D list of lists is indexed using `list_name[row][col]`. 
In NumPy, you can do this more efficiently using a single set of square brackets: **`array[row, col]`**.

<img width="319" height="363" alt="2d array indexing" src="https://github.com/user-attachments/assets/676095c5-149b-43ed-b37d-90748352336f" />  

### 2.3 Boolean Indexing (Filtering / Masking) 🌟
Boolean masking is one of the most powerful indexing techniques in NumPy. It allows you to select elements that meet specific logical conditions.

1. **Create a condition (mask):** Evaluating an operation like `arr > 5` returns a boolean array of the same shape.
2. **Apply the mask:** Passing the boolean array inside square brackets `arr[mask]` returns only elements where the condition is `True`.
<img width="585" height="741" alt="boolean indexing" src="https://github.com/user-attachments/assets/7500b7c6-01e7-4907-9182-fb74c12d90f7" />

#### Modifying elements with Boolean masks:
You can modify values that meet specific criteria in one line, without any loops.  
<img width="592" height="274" alt="Boolean masking" src="https://github.com/user-attachments/assets/3d1a3e5e-c84a-46ed-abae-6f7bc8de2cb6" />  

## Module 3: Slicing in NumPy (Views vs. Copies)

Slicing pulls out a range of elements using the `[start:stop:step]` format.

### 3.1 1D Slicing  
<img width="698" height="385" alt="1d slicing" src="https://github.com/user-attachments/assets/37850fd3-ccac-4fd7-9abb-4e2de98caf53" />  

### 3.2 2D Slicing
To slice a 2D matrix, specify row slicing and column slicing separated by a comma: **`matrix[row_start:row_stop, col_start:col_stop]`**.  
<img width="625" height="674" alt="2d slicing" src="https://github.com/user-attachments/assets/0d1e2797-b29f-4533-8e1c-c78503759714" />  

## Day 7
## 30 June 2026
## Assignment Questions  
### Question 1  
#### Without importing any external module (like "collections"), write a Python function count_frequencies(label_list) that takes a list of labels and returns a dictionary where keys are the unique labels and values are their occurrence counts. Test your function with the following list: labels = ["tumor", "healthy", "tumor", "cyst", "tumor", "healthy"] Expected output: {"tumor": 3, "healthy": 2, "cyst": 1}  
<img width="811" height="556" alt="Answer 1" src="https://github.com/user-attachments/assets/cb44506d-826d-4bd9-b4a0-cc3670ea82f9" />  

### Question 2  
### Write a Python function is_prime(n) that checks if a number is prime. Then, write another function get_primes_in_range(start, end) that returns a list of all prime numbers between start and end (inclusive) by calling your is_prime function. Test your function with: get_primes_in_range(10, 50) Expected output: [11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47]  
<img width="443" height="625" alt="Answer 2" src="https://github.com/user-attachments/assets/9b0b6278-21e1-45a9-bf82-1f89a154f6cf" />  

### Question 3 
### Write a recursive function recursive_power(base, exponent) that calculates the value of base raised to the power of exponent (where exponent >= 0). - Do not use the "**" operator or the "math" module. - Clearly identify the base case and the recursive case. - Test your function with base = 3 and exponent = 4 (Expected output: 81).  
<img width="654" height="525" alt="Answer 3" src="https://github.com/user-attachments/assets/c7fd1aac-ad16-424d-9083-6c68cc6119e8" />  

### Question 4  
### Write a Python function sum_of_digits(n) that takes a positive integer n and returns the sum of its digits without converting the number to a string. (Hint: Use modulus % 10 and floor division // 10 inside a loop). Test your function with: sum_of_digits(12345) Expected output: 15 (since 1 + 2 + 3 + 4 + 5 = 15)  
<img width="628" height="486" alt="Answer 4" src="https://github.com/user-attachments/assets/6d534a25-a656-47bf-95df-87706babe83e" />  

### Question 5  
### Write a Python function calculate_precision_recall(actual, predicted) that takes actual ground-truth labels and model prediction labels. - Calculate: * True Positives (TP): actual is 1, predicted is 1. * False Positives (FP): actual is 0, predicted is 1. * False Negatives (FN): actual is 1, predicted is 0. - Calculate Precision and Recall using the formulas: Precision = TP / (TP + FP) Recall = TP / (TP + FN)  
### - Note: Your code must handle division-by-zero checks to prevent crashes. - Test your function with:
### actual = [1,0,1,1,0,0,1,0,1,1]
### predicted = [1,0,0,1,0,1,1,0,1,0]
<img width="568" height="834" alt="Answer 5" src="https://github.com/user-attachments/assets/41260600-a34e-4d2b-a884-d4483b3d3ba5" />  

### Question 6  
### Write two functions:  
### a) format_names(learning_rate_val, batch_size_val) that prints the values formatted nicely, whereparameters comply with PEP 8 standards. b) parse_numbers_string(data_string) that takes a string of space-separated numbers (e.g., "1.52.30.94.1"),splits it, converts each element to a float, and returns the list.  
<img width="582" height="678" alt="Answer 6" src="https://github.com/user-attachments/assets/1b0600d6-b5e2-43a2-af6f-46452175692f" />  

### Question 7
### You are given a list of feature values containing noisy outliers:
### features = [1.2,105.4,0.9,-45.2,2.1,1.8,99.8,-0.5]
### Write a single-line list comprehension that:
### 1. Removes any outlier that is outside the range [-2.0, 10.0]. 2. Computes the square of the remaining valid feature values. Print both the original features list and the resulting squared valid features list.  
<img width="995" height="301" alt="Answer 7" src="https://github.com/user-attachments/assets/e7d598db-76c8-401b-9f5b-fb242ae8cce6" />  

### Question 8
### Write a Python function named log_training_run that accepts: 
### - One mandatory positional argument: model_name (str)
### - Variable number of positional arguments: *metrics (representing loss values at different checkpoints)- Variable number of keyword arguments: **hyperparameters (like learning_rate, batch_size)
### The function should:
### 1. Print the model name in uppercase. 2. Print the average metric value (rounded to 4 decimal places). If no metrics are provided, print awarningmessage. 3. Iterate and print all hyperparameters in the format: [Key] -> [Value]. Example Call:
### log_training_run("ResNet50", 0.85, 0.42, 0.15, learning_rate=0.001, optimizer="Adam")  
<img width="656" height="795" alt="Answer 8" src="https://github.com/user-attachments/assets/0710dcd5-57a6-4a2f-b09e-f2bd71fc319f" />  

### Question 9  
### Write a Python function convert_temperature(temp, to_scale) that converts a temperature: - If to_scale is "C", convert the temperature from Fahrenheit to Celsius using the formula: C=(F- 32)*5/9.- If to_scale is "F", convert the temperature from Celsius to Fahrenheit using the formula: F=(C*9/5)+32.- The function should return the converted value rounded to 2 decimal places. Test your function with Celsius to Fahrenheit (37, "F") and Fahrenheit to Celsius (98.6, "C").  
<img width="730" height="614" alt="Answer 9" src="https://github.com/user-attachments/assets/ef37673e-e6b2-4865-913e-532b380c0140" />  

### Question 10  
### In Natural Language Processing (NLP), Jaccard Similarity measures the similarity between twosetsofwords (documents) and is defined as:  
### Jaccard Similarity = Size of (Set A Intersection Set B) / Size of (Set A Union Set B)  
### Write a Python function jaccard_similarity(doc1, doc2) that:  
### 1. Takes two strings, splits them into words, and converts them to lowercase. 2. Converts the word lists into sets. 3. Calculates and returns the Jaccard Similarity score (a float between 0.0 and 1.0). Test your function with:  
### doc1 = "Python is great for machine learning" doc2 = "Machine learning in Python is awesome"  
<img width="551" height="625" alt="Answer 10" src="https://github.com/user-attachments/assets/05cabe2f-86b0-47b5-82b7-4514817807f0" />  

### Question 11  
### Write a Python program that searches a list of sensor reading floats for any anomaly (definedas anyvaluestrictly less than 0.0 or strictly greater than 100.0). - If an anomaly is found, print the index and the anomalous value, and terminate the loop immediatelyusinga break statement. - If the loop completes and no anomaly is found, print "All sensor readings are normal." usingPython'sunique else clause for loops. Test your program with these two lists:  
### readings_1 = [12.5,45.2,98.9,0.5,76.1]
### readings_2 = [12.5,45.2,-1.2,98.9,105.4]  
<img width="617" height="778" alt="Answer 11" src="https://github.com/user-attachments/assets/540f40bd-f356-48ae-a5e0-c69c8055cc95" />  

### Question 12  
### Write a recursive function decimal_to_binary(n) that takes a positive decimal integer n and returnsitsbinaryrepresentation as a string. - Hint: Think about dividing by 2 and taking the remainder. - Base Case: Identify what the function should return if n == 0. - Test it with n = 10 (Expected output: "1010") and n = 25 (Expected output: "11001").  
<img width="640" height="509" alt="Answer 12" src="https://github.com/user-attachments/assets/d56abab2-f03d-441e-8b7d-91b77adc77bb" />  

### Question 13
### Write a Python function bitwise_check(num) that uses bitwise operators (do NOT use the modulus%operator, multiplication *, or division / operators) to:
### a) Determine if num is odd or even (Hint: Use bitwise AND &). b) Multiply num by 4 (Hint: Use left shift <<). c) Perform floor division of num by 2 (Hint: Use right shift >>). Test your function with num = 12 and num = 15.  
<img width="528" height="820" alt="Answer 13" src="https://github.com/user-attachments/assets/799129b6-838f-404b-a689-4fabaf636d85" />  

### Question 14
### You have raw data records containing user info as tuples:
### raw_data = [(25, "Dev", "Delhi"), (30, "Aarav", "Mumbai"), (25, "Dev", "Delhi"), (22, "Neha", "Delhi"),(30,"Aarav", "Mumbai")]
### Write a Python program that:
### 1. Deduplicates the records using a Set and converts it back to a list of unique records. 2. Sorts the unique records by age in descending order. 3. Prints the final sorted unique list.
<img width="852" height="644" alt="Answer 14" src="https://github.com/user-attachments/assets/06009b53-b40c-43bc-b11a-a72e0c21fd61" />  

### Question 15
### Write a Python function is_palindrome(text) that checks if a given string is a palindrome (reads thesameforward and backward). The function should ignore spaces, punctuation, and capitalization. Test your function with: - "A man a plan a canal Panama" (Expected output: True)
### - "Machine Learning" (Expected output: False)  
<img width="696" height="525" alt="Answer 15" src="https://github.com/user-attachments/assets/4a302140-771f-4216-92b3-e410fd122f41" />  

### Question 16
### When feeding images to neural networks, checking dimensions is crucial. Write a Python functionvalidate_image_shape(shape_tuple) that: - Receives a tuple representing image shape: (height, width, channels). - Returns True if:
### 1. The image is square (height == width). 2. The image has either 1 channel (grayscale) or 3 channels (RGB). - Returns False otherwise. Test the function with (224, 224, 3), (128, 256, 3), and (512, 512, 4).  
<img width="715" height="525" alt="Answer 16" src="https://github.com/user-attachments/assets/a07ad3f0-68b9-4228-92ab-919315c963e0" />  

### Question 17
### Casting a list containing duplicate elements to a Set (e.g., unique_list = list(set(original_list))) removesduplicates, but it does not guarantee that the original order of elements is preserved. Write a Python function deduplicate_preserve_order(input_list) that removes duplicate elements fromalistwhile keeping the exact order of their first occurrence. Test your function with:
### sample_list = ["apple", "banana", "apple", "cherry", "banana", "date"]
### Expected output: ["apple", "banana", "cherry", "date"]  
<img width="833" height="576" alt="Answer 17" src="https://github.com/user-attachments/assets/c6724271-b1f1-47c1-9a81-2f283c999813" />  

### Question 18
### Given two lists:
### student_names = ["Aarav", "Dev", "Neha", "Priya"]
### scores = [88, 95, 78, 92]
### Write a single for loop that uses both enumerate and zip to print the rank, name, and score of eachstudentinthe following format:
### Rank 1: Aarav scored 88/100
### Rank 2: Dev scored 95/100
### Rank 3: Neha scored 78/100
### Rank 4: Priya scored 92/100  
<img width="892" height="288" alt="Answer 18" src="https://github.com/user-attachments/assets/a5ed298f-522e-48be-ab37-6156109e9981" />  

## Day 8
## 2 July 2026
## Pandas Essentials — DataFrames and Data Manipulation

we transition to **Pandas** (Python Data Analysis Library), the standard Python package used to load, clean, analyze, and transform tabular datasets.

## What is Pandas?
Pandas is an open-source Python library that provides high-performance, easy-to-use data structures and data analysis tools. It is built on top of NumPy, meaning it inherits NumPy's speed while adding indexable rows and columns.

### Why do we need Pandas in Data Science?
Standard Python lists and dictionaries are highly flexible but slow for doing heavy data calculations. NumPy arrays are extremely fast but can only hold a single data type (homogeneous) and lack labeled columns or rows. 

Pandas combines the best of both worlds: it handles tables of mixed data types (heterogeneous) and allows us to reference columns by name and rows by indices.

| Feature | Python Lists / Dicts | NumPy Arrays | Pandas DataFrames / Series |
| :--- | :--- | :--- | :--- |
| **Structure** | Unstructured or Nested | Homogeneous N-D Array | Heterogeneous Tabular 2D Grid / 1D Columns |
| **Row/Col Labels** | Index only / Dict keys | Numeric index only | Custom Index & Column Labels |
| **Data Types** | Mixed (slow) | Homogeneous (fast) | Mixed per column (fast, built on NumPy) |
| **Missing Data** | `None` (manual check) | `nan` (limited support) | `NaN` / `None` (built-in automatic alignment & handling) |

### 🧠 Data Structures Visual representation:
```text
Pandas Series (1D column with index):
       Index    Values
         0  ──►  23
         1  ──►  45
         2  ──►  31

Pandas DataFrame (2D table made of aligned Series columns):
       Index      Name      Age     Income
         0   ──►  Alice     23      50000
         1   ──►  Bob       45      85000
         2   ──►  Charlie   31      62000
```
## Module 1: Pandas Data Structures (Series & DataFrames)

The two primary structures in Pandas are the **`Series`** (1-dimensional) and the **`DataFrame`** (2-dimensional). 

- **Series**: A one-dimensional labeled array capable of holding any data type (integers, strings, floating point numbers, Python objects, etc.).
- **DataFrame**: A two-dimensional labeled data structure with columns of potentially different types, like a spreadsheet or SQL table.
<img width="436" height="499" alt="Example pandas" src="https://github.com/user-attachments/assets/f0eb847b-d622-4db5-9c03-637f4d8db55a" />
<img width="619" height="672" alt="Pandas example 2" src="https://github.com/user-attachments/assets/f2615571-2e2e-48a1-963b-a4483f097532" />

## Module 2: Reading Data & Dataset Inspection

Usually, datasets are loaded from external files (like CSV or Excel). We use **`pd.read_csv()`** to load CSV files.

<img width="673" height="514" alt="data csv" src="https://github.com/user-attachments/assets/c36def37-5ddc-454a-95f9-e773322254bc" />  
<img width="179" height="317" alt="dtypes" src="https://github.com/user-attachments/assets/018e5cd7-726f-4248-b28a-ca60d1d80ea2" />  
<img width="444" height="468" alt="df shape and info" src="https://github.com/user-attachments/assets/72e44a49-4081-417a-b1ea-75fbeb8e006d" />  
<img width="477" height="565" alt="df head and tail" src="https://github.com/user-attachments/assets/0bade206-a1bc-402f-a0f2-4ea325f61c91" />  
<img width="547" height="674" alt="df columns" src="https://github.com/user-attachments/assets/fee72fc7-3dae-4099-ab51-acd2808e4b19" />  

## Day 9
## 3 July 2026
## Module 3: Slicing & Selecting Data

Extracting subsets of columns and rows is standard practice.
- **Column Selection**: Select columns using brackets `df['col_name']` or a list of columns `df[['col1', 'col2']]`.
- **Positional Slicing (`.iloc`)**: Select rows and columns by integer index position `.iloc[row_idx, col_idx]`.
- **Label-based Indexing (`.loc`)**: Select rows and columns by labels `.loc[row_label, col_label]`.
<img width="462" height="866" alt="slicing pandas" src="https://github.com/user-attachments/assets/f5eb64d9-1068-4805-b4a4-74e8efff7b32" />

## Module 4: Boolean Indexing: Filtering Rows

In Machine Learning, we often filter records based on specific criteria (e.g. selecting rows where income is above a threshold).
- Wrap conditions in parentheses.
- Use bitwise operators: `&` for **AND**, `|` for **OR**, `~` for **NOT**.
<img width="640" height="683" alt="boolean indexing nad masking" src="https://github.com/user-attachments/assets/7b816406-5277-48bb-9b21-6f606094a28a" />

## Module 5: Cleaning Missing Data (NaNs)

Real-world datasets contain gaps (represented as `NaN` — Not a Number). Machine Learning models cannot be trained with missing inputs. We must handle them:
1. **Detecting Nulls**: Check null value counts per column using `.isnull().sum()`.
2. **Strategy A (Imputation)**: Fill NaNs using `.fillna()`.
3. **Strategy B (Deletion)**: Remove rows containing NaNs using `.dropna()`.  
<img width="516" height="726" alt="missing values" src="https://github.com/user-attachments/assets/b3683cb4-8e36-403e-9c82-47587f22873e" />

## Module 6: Groupby & Aggregations

Analyzing stats by grouping categories is essential (e.g. comparing average income of customers who purchased vs those who didn't). We use **`.groupby()`** followed by an aggregation function like `.mean()`, `.sum()`, `.count()`.  
<img width="612" height="329" alt="group by example" src="https://github.com/user-attachments/assets/a8e579f0-938e-440c-8620-553bb266b73f" />  

## Day 10
## 6 July 2026
##  Data Visualization — Matplotlib and Seaborn (For Beginners!)

Welcome to Day 8! Now that you know how to organize data with Pandas and NumPy, it's time to learn the most fun part of coding: **drawing pictures with numbers!**

### Why do we visualize data?
Imagine someone gives you a list of 1000 numbers. It is almost impossible to find the pattern by just reading them! But if you plot them as dots or lines on a screen, you might see a hidden shape, a trend going up, or a single weird point way off in the corner.

Today, we will learn:
1. **Matplotlib**: Our digital drawing board where we draw lines, bars, and dots.
2. **Seaborn**: Our magic paint box that sits on top of Matplotlib and makes our charts look beautiful and modern.

Let's import our tools first!  
<img width="1775" height="582" alt="install matplotlib" src="https://github.com/user-attachments/assets/6a809d72-61b5-4bc9-9f46-acc47f50ada9" />  
<img width="1769" height="674" alt="matplotlib" src="https://github.com/user-attachments/assets/e888c848-af77-42cc-8f71-82539b2d53d2" />  
<img width="1792" height="720" alt="seaborn and pandas" src="https://github.com/user-attachments/assets/a2ad987d-4f43-4809-a61c-d3fe79ff7111" />  
<img width="1003" height="889" alt="example of data visualization" src="https://github.com/user-attachments/assets/ab901858-f164-4e90-8343-9bd72db976ea" />  

## Module 1: Matplotlib (Our Drawing Canvas)
Matplotlib is like a piece of graph paper where we can draw whatever we want. We use `plt` to draw lines, bars, and scatter dots.

### 📈 Task 1: Line Plots (Tracking a Superhero's Speed)
A **Line Plot** connects sequential dots with lines to show how something changes over time.
* **Story**: Imagine tracking a superhero's flight speed as they train over 5 days.
* **What we learn from this plot (Plot Insight)**: **Identifying Trends!** It tells us whether their speed is going up (improving) or going down, and how fast they are progressing.
<img width="1102" height="859" alt="line plot" src="https://github.com/user-attachments/assets/4530e423-6bef-498e-9217-4310a9b8752f" />

<img width="700" height="798" alt="example of line plot" src="https://github.com/user-attachments/assets/b231fb7e-9145-4d9a-80f9-20e6943f1c54" />  

### 📊 Task 2: Bar Plots (Comparing Favorite Treats)
A **Bar Plot** uses vertical columns to compare different groups or categories of things.
* **Story**: We asked our friends how many treats they ate this week. We want to see which treat was the most popular!
* **What we learn from this plot (Plot Insight)**: **Comparing Categories!** We can instantly see which treats were eaten the most (highest bar) and which were eaten the least (lowest bar) without reading a table of numbers.
<img width="749" height="768" alt="Bar plot" src="https://github.com/user-attachments/assets/dfb48984-85e5-45ad-a159-36bd94ffc796" />

### 📍 Task 3: Scatter Plots (Treasure Map Hunt!)
A **Scatter Plot** shows individual dots at specific (X, Y) coordinates, without connecting them. It is like placing flags on a map.
* **Story**: Imagine you are looking at a treasure map grid. Each star is where a player found a hidden treasure chest.
* **What we learn from this plot (Plot Insight)**: **Spotting Relationships and Clusters!** It shows where the points group together (clusters of gold!) or if they follow a pattern (like a diagonal line showing that treasures are found further north as you go east).
<img width="876" height="802" alt="scatter plot" src="https://github.com/user-attachments/assets/266f1e0c-f451-44cd-b895-77323762b11d" />

## Module 2: Seaborn (The Magic Paintbrush)
Seaborn is built on top of Matplotlib. It handles all the complex styling details automatically, making our charts look professional and polished with very little code.

## Day 11
## 7 July 2026
### 📊 Task 4: Histograms & KDE (Candy Count Distribution)
A **Histogram** groups individual numbers into "bins" (ranges) and shows columns representing how many items fall into each range.
* **Story**: Imagine 30 kids count how many candies they collected at a party. We want to see how candy counts are distributed.
* **What we learn from this plot (Plot Insight)**: **Data Distributions!** We learn how our data is spread out. Are the candy counts mostly centered around a single number (symmetrical/normal distribution)? Or are they skewed (e.g., almost everyone got very few candies, or almost everyone got a lot)? The smooth KDE curve line shows the general shape of this distribution density.
<img width="445" height="801" alt="Histogram Plot" src="https://github.com/user-attachments/assets/9c41041a-c9f0-4a4f-b080-05b51015be57" />

### 📦 Task 5: Box Plots (Outlier Detection in Frog Jumps)
A **Box Plot** summarizes a dataset's distribution using a box and lines. It is the absolute best tool for spotting **outliers** (extreme numbers that are weirdly different from the rest).
* **Story**: We measured how far 10 frogs can jump (in feet). Most frogs jumped between 4 and 8 feet, but one "super-frog" jumped 18 feet!
* **What we learn from this plot (Plot Insight)**: **Detecting Outliers & Quartiles!**
  * The **box** in the middle shows where the middle 50% of the frogs jumped.
  * The line inside the box is the **median** (the middle score).
  * The **whiskers** (lines extending from the box) show the normal min and max ranges.
  * The single dot way outside the whiskers represents our **outlier** (the super-frog jump!).
<img width="750" height="697" alt="Box plot" src="https://github.com/user-attachments/assets/ae1a4e94-606e-40a3-b85e-c2c59fc6b8e8" />

### 🌡️ Task 6: Correlation Heatmaps (What makes a Video Game popular?)
A **Correlation Heatmap** is a grid of colored cells showing how strongly different numeric columns are related to each other.
* **Story**: We want to understand what makes a video game popular. We analyze Play Time, Popularity Score, and Game Difficulty.
* **What we learn from this plot (Plot Insight)**: **Understanding Correlation!**
  * Correlation values range from **-1.0** to **1.0**.
  * **Close to 1.0 (Positive)**: Features grow together (e.g., Play Time and Popularity have a strong positive correlation). Colored in **warm colors** (red/orange).
  * **Close to -1.0 (Negative)**: As one goes up, the other goes down (e.g., Game Difficulty and Popularity might have a negative correlation because hard games can frustrate players!). Colored in **cool colors** (blue).
  * **Close to 0.0**: The features have no relationship.
<img width="541" height="733" alt="correlation heatmaps" src="https://github.com/user-attachments/assets/45022ccf-e527-49fa-a9ad-e4285d4ba1de" />

## 💡 Let's Review: The Visual Cheat Sheet!
When should you use each chart?
1. **Line Plot**: Use this to show a **trend** over time (e.g., height growing each year).
2. **Bar Plot**: Use this to **compare categories** (e.g., number of students who like apples vs bananas).
3. **Scatter Plot**: Use this to show **individual coordinates** and find clusters (e.g., positions on a coordinate plane).
4. **Histogram**: Use this to show **distribution** (e.g., how many students got scores in the 70s, 80s, or 90s).
5. **Box Plot**: Use this to spot **outliers** (e.g., finding the single giant height in a primary school class).
6. **Heatmap**: Use this to see how multiple columns **correlate** together.

## Day 12
## 8 July 2026
Exploratory Data Analysis (EDA) — Detective Work on House Prices! 🕵️‍♂️🏠

We have a case file of over **21,000 houses** in King County, USA. Some are tiny, some are huge, some are cheap, and some cost millions of dollars! 

**Our Mission:** Find out what makes a house expensive or cheap! 
We will use our "spy gear" (Python libraries) to look for clues, draw pictures, and map out connections in the data. This is what data scientists call **Exploratory Data Analysis (EDA)**.
## 🔍 Step 1: Load Our Spy Gear (Libraries)
First, we need to gather our tools:
- **Pandas** 🐼: Our case file organizer. It helps us read and sort tables.
- **NumPy** 🔢: Our magnifying glass for fast math operations.
- **Matplotlib & Seaborn** 🎨: Our digital drawing board and magic paint box to paint pictures of numbers.
<img width="783" height="322" alt="example 3" src="https://github.com/user-attachments/assets/13b66c37-5188-43d3-8848-dacd2b972351" />

## Step 2: Load the Dataset  
Loading the dataset means importing the data file into Python so it can be analyzed, cleaned, and used for Machine Learning. After loading, the data is stored as a DataFrame, making it easy to access and work with.  
<img width="1106" height="303" alt="Load the dataset" src="https://github.com/user-attachments/assets/73d69438-6a30-46df-8acd-629325ef170b" />  

## ✂️ Step 3: Simplifying the Clues (Keeping Only What We Understand)
The raw dataset has columns like `sqft_living15` and `lat` (latitude) which can be confusing. 
Let's focus only on the **most fun and intuitive features** that we all understand! 

We will keep:
- `price`: The price of the house (Target value)
- `bedrooms`: How many bedrooms it has
- `bathrooms`: How many bathrooms it has
- `sqft_living`: The size of the house (living space in square feet)
- `floors`: How many stories/floors the house has
- `waterfront`: If it has a lake/beach view (1 = yes, 0 = no)
- `yr_built`: The year the house was built
- `condition`: How clean/well-maintained the house is (1 = poor, 5 = excellent)
<img width="894" height="476" alt="Step 3" src="https://github.com/user-attachments/assets/5e6c34f0-1c97-4a55-baa3-093ff3c5804c" />

## 📊 Step 4: The Detective Statistics
Let's get a quick summary. What is the average price? When was the oldest house built? What is the size of the biggest house? 
We can do this easily with `.describe()`!  
<img width="507" height="699" alt="step 4" src="https://github.com/user-attachments/assets/0284996a-a68c-4798-850f-dc9c15b2e8c3" />  

## 📈 Step 5: Visualizing Clue 1 — The Price Mountain (Univariate Analysis)
Let's look at the distribution of the house prices. Are most houses cheap, average, or extremely expensive? 
We will plot a **histogram** to see the "Price Mountain" shape.  
<img width="908" height="781" alt="step 5" src="https://github.com/user-attachments/assets/e4ad6b80-26f0-4e54-8d4f-d653b241250e" />  

## 🛏️ Step 6: Visualizing Clue 2 — The Bedroom Count
Let's check how many bedrooms most houses have. What is the most common number? And look out for any crazy outliers (like a house with 33 bedrooms!) using a **countplot**.  
<img width="784" height="802" alt="Step 6" src="https://github.com/user-attachments/assets/316cdd5b-1561-46dd-b2a5-e4bfba02dc9c" />  

## 📏 Step 7: Connecting the Dots — Size vs. Price (Bivariate Analysis)
Let's check if bigger houses always cost more. We will draw a **scatter plot** where every dot represents a house. If the dots trend upwards, it means: *Larger House = Higher Price!*  
<img width="763" height="755" alt="step 7" src="https://github.com/user-attachments/assets/eec245fe-3d55-4ee2-a3d1-230b8cb6b4e7" />  

## 🌊 Step 8: Waterfront Houses — Living by the Lake (Bivariate Analysis)
Does living near a beach or lake make a house more expensive? Let's check with a **box plot** which shows the median and spread of prices.  
<img width="648" height="590" alt="step 8" src="https://github.com/user-attachments/assets/7cec28b2-5e54-45c3-a1ae-5cfcb716030b" />  

## 🛠️ Step 9: House Condition — Does Neater Mean Costlier?
How does the condition of the house affect its price? Let's plot the average price for each condition rating (1 is messy, 5 is perfect!).  
<img width="645" height="578" alt="step 9" src="https://github.com/user-attachments/assets/5eb49d9d-60e7-4720-a516-fea85df33be4" />  

## 🗺️ Step 10: The Detective's Map — The Connection Matrix
Let's draw a **heatmap**! It shows correlation (from -1 to +1). 
If two features are close to +1, they move together like best friends. If they are close to 0, they don't affect each other.  
<img width="568" height="809" alt="step 10" src="https://github.com/user-attachments/assets/264b08a7-69d1-482d-83c3-63ad2b80f7b5" />  

## Day 13
## 9 July 2026
## Data Preprocessing — Washing & Sorting our Lego Blocks! 🧼🧱
we need to prepare our house data for our **Machine Learning Robot**. 

**Why do we do Preprocessing?**
Machine learning models are like smart robots, but they are also very picky. They only eat **clean, neat, and scaled numbers**. 
If we feed them messy data, they will output garbage (*Garbage in, Garbage out!*). Preprocessing is like washing and sorting Lego blocks before building a castle.  
## 🧼 Step 1: Import Preprocessing Gear & Load Data
Let's import our libraries and load the dataset we saved yesterday.  
<img width="1693" height="495" alt="install scikit learn" src="https://github.com/user-attachments/assets/7c7e6d93-970f-4e7c-b480-f584e81cd37a" />  
<img width="813" height="735" alt="example of scikit learn" src="https://github.com/user-attachments/assets/80df3b5e-be47-4a9d-80c5-4b623f2ded4f" />  

## 🧩 Step 2: The Mystery of the Missing Values (Imputation)
Real-world data often has blanks (missing values). To practice resolving this, let's randomly hide the birth year (`Year_Built`) for 100 houses and learn how to solve it!

### Analogy: Filling in the Blanks
We call this **Imputation**. If a house's build year is missing, we fill it using the **median** (the middle-of-the-road year). Why the median instead of the mean? Because the median is robust and won't get pulled away by one or two extremely old castles!  

## 🤠 Step 3: Taming the Giants (Outlier Capping)
Remember the house with 33 bedrooms? Or giant mansions? 
Extreme values are like **Giants** in our dataset. They confuse our ML robot during training. We can use a trick called **IQR (Interquartile Range) Capping** to trim their tall hats so they fit in our room, without deleting the data!  
<img width="911" height="676" alt="example of scikit" src="https://github.com/user-attachments/assets/a9496cfc-6513-477e-b3c3-28c88c1c970b" />  

<img width="616" height="741" alt="example of scikit 2" src="https://github.com/user-attachments/assets/ee38b391-be51-489e-a66a-6d3d12b36c38" />  

<img width="641" height="447" alt="example of scikit 3" src="https://github.com/user-attachments/assets/98293a15-302c-4e80-a29e-47f292e13582" />  

## ⚖️ Step 4: Balancing the Scales (Feature Scaling)
Why scale?
- Size range: 290 to 4,234 sqft.
- Bedroom range: 1 to 5 rooms.
Because house size numbers are so much bigger, the robot will think size is thousands of times more important than bedroom count! 

We have two common scaling methods:
1. **MinMaxScaler (0 to 1 scaling)**: Shrinks data so the smallest value becomes 0 and the largest becomes 1. Like shrinking a giant Lego model to fit in a pocket!
2. **StandardScaler (Average scaling)**: Centers data so the average becomes 0. If you are average height, you are 0. If you are taller, you get a positive score; if shorter, a negative score.

If you feed this data straight into an AI algorithm, the algorithm will look at the massive numbers in the "Price" column and assume it is way more important than the "Bedrooms" column, just because the numbers are bigger.  
<img width="668" height="291" alt="step 4 valued" src="https://github.com/user-attachments/assets/5e75d753-fa8d-410b-938a-40a3c32091ff" />  

## 🏷️ Step 5: Translating Words to Numbers (One-Hot Encoding)
Machine learning robots don't read words, they only read numbers! 
If we have a category like "Neighborhood" (with values like Budget, Mid-Range, Premium), how do we explain this to the robot?

### The Flag Game (One-Hot Encoding)
We create new columns representing each word flag. A house gets a `1` if it matches, and `0` if it doesn't.  
<img width="682" height="483" alt="step 5" src="https://github.com/user-attachments/assets/c4c4f90a-54ea-4c6b-b8ed-7302efddc5fc" />  

## 🎉 Step 6: Final Review & Saving the Preprocessed Lego Blocks!
Let's select our final preprocessed features and save them to a file. Our dataset is now perfectly clean and ready to train any AI model!  
<img width="707" height="758" alt="step 6" src="https://github.com/user-attachments/assets/5f6853f9-1272-4301-93f9-85cbdc61833b" />  

## Day 14
## 13 July 2026
## Linear Regression — Training our First AI Robot to Predict House Prices! 🤖📈

### What is Linear Regression?
Imagine you are looking at a scatter plot of house sizes vs. prices. You notice that as size increases, price generally goes up. If you took a pencil and drew a straight line through the center of those points to show the trend, you would be doing manual linear regression!

In machine learning, we let the computer (our robot) find the mathematically perfect straight line that fits the data. Once the robot has this line, it can use it to predict the price of any new house just by looking at its size!

## 🔌 Step 1: Import our Tools & Load the Clean Data

Let's import our favorite libraries: `pandas`, `numpy`, `matplotlib`, and `seaborn`. We will also import the `LinearRegression` model and splitting/evaluation tools from `scikit-learn` (`sklearn`).
<img width="1429" height="701" alt="Example LR" src="https://github.com/user-attachments/assets/66ed7bcb-128a-4c55-8ddb-5875522e8825" />  

## 🎓 Step 2: Splitting the Work (Train / Test Split)

Before we train our model, we must split our dataset into two sets:
1. **Training Set (80%)**: The dataset our robot will study to learn the patterns and relationships.
2. **Testing Set (20%)**: The dataset we will use to test our robot on "unseen" questions to see how smart it really is.

### The Math Exam Analogy 📝
If you study for a math test using practice questions, and the teacher gives you the exact same practice questions on the actual exam, you might get a 100% just by memorizing the answers. You wouldn't prove you actually understand math!
To test if you truly understand math, the teacher must give you *new, unseen questions* on the exam. 
Similarly, we train the model on training data, and evaluate it on test data.
<img width="1121" height="572" alt="example 2 lR" src="https://github.com/user-attachments/assets/5e2d5345-4925-451b-a786-fd2bd2587709" />  

## 🤖 Step 3: Simple Linear Regression (One Clue)

Let's start simple. We will train our robot using only **one clue**: `Scaled_size` (the size of the house) to predict the house `price`.
<img width="889" height="475" alt="example 3 LR" src="https://github.com/user-attachments/assets/a07db972-d732-471f-8096-26c9b58280f7" />  

## 🧠 Step 4: Looking Inside the Robot's Brain

Remember the equation of a line from algebra class?
$$
y = m \cdot x + c
$$
Where:
- $y$ is the predicted house Price
- $x$ is the scaled Size (`Scaled_size`)
- $m$ is the **Slope** (Coefficient) — how much the price increases per unit size
- $c$ is the **Intercept** — the baseline price of a house if its size was 0

Let's inspect the values of $m$ and $c$ that our robot learned!  
<img width="1017" height="385" alt="LR" src="https://github.com/user-attachments/assets/58b9dd7b-a5f3-46c8-a2cf-b56f688bb393" />  

## 📊 Step 5: Visualizing the Best-Fit Line

Let's plot the actual test houses (as dots) and overlay our robot's prediction line (in red)!
<img width="625" height="793" alt="example 4 lr" src="https://github.com/user-attachments/assets/f91715b9-2be3-477a-906a-1fee6a654172" />  

## 🚀 Step 6: Multiple Linear Regression (All Clues!)

Using just the house size gets us a good start, but houses are complex! They have bedrooms, bathrooms, floors, and are in different neighborhoods.

Let's train a new model using **all** our preprocessed features to see if our robot gets smarter when we give it more clues!
<img width="992" height="423" alt="example 5 lr" src="https://github.com/user-attachments/assets/1401bc8a-9a27-41e5-8b18-099dd4db0d55" />  

## 🏠 Step 7: Predicting a Custom House Price

Let's play around and ask our Multiple Regression model to predict the price of a custom house that we specify!

Here is the order of features the model expects:
- `bedrooms`
- `bathrooms`
- `Scaled_size`
- `floors`
- `waterfront`
- `sqft_living`
- `condition`
- `Loc_Budget`
- `Loc_Mid-Range`
- `Loc_Premium`
<img width="624" height="666" alt="example 6 lr" src="https://github.com/user-attachments/assets/2daf3a9f-034d-4191-a47c-20902ffe5b15" />

## 🎯 Step 8: How Do We Know If Our Model Is Accurate? (Model Evaluation)

Now that we have trained both the **Simple Linear Regression** model and the **Multiple Linear Regression** model, how can we know how accurate they are? How do we measure the intelligence of our AI models?

In machine learning, we evaluate regression models on the test set (our "exam paper") using two key metrics:

### 1. Mean Absolute Error (MAE) 💸
* **What is it?** MAE measures the average size of the mistakes our model makes. On average, how many dollars off are our predictions from the actual prices?
* **Analogy:** If a house actually sold for $300,000, and our model predicted $280,000, the error is $20,000. MAE is the average of these absolute errors for all houses in our test set.
* **How to read it:** **Lower is better!** A lower MAE means the robot's predictions are closer to the real prices on average.

### 2. $R^2$ Score (Coefficient of Determination) 📈
* **What is it?** This score (ranging from 0 to 1, or 0% to 100%) tells us how much of the variance in house prices can be explained by our clues.
* **Scale:**
  * `0.0` (0%) means the model is useless (it just guesses the average house price every time).
  * `1.0` (100%) means the model is perfect (it predicts every house price with 100% precision).
* **How to read it:** **Higher is better!** An $R^2$ score of 0.70 means our clues explain 70% of why house prices go up or down.

Let's write the code to evaluate both models and compare them side-by-side!
<img width="1169" height="519" alt="step 8 lr" src="https://github.com/user-attachments/assets/38a7491b-22e6-4987-aee1-b48845c369bf" />  

## Day 15
## 14 July 2026
## Polynomial Regression — Teaching our Robot to Curve! 🤖〰️

Welcome back, Data Builders! Yesterday, we trained our first Linear Regression model to predict house prices using straight lines.

But what if the relationship between our clues (like house size) and the price isn't a straight line? What if it's curved? Today, we are going to teach our AI robot how to **bend the line** to capture curves using **Polynomial Regression**!

---

### 🎢 The Roller Coaster Analogy: What is Polynomial Regression?

Imagine you have a robot friend.
* **Linear Regression:** The robot is only allowed to draw **straight lines** with a ruler. If our data points form a straight path, the robot does a great job. But what if the data points go up and down like a roller coaster or a smile? A straight line will miss most of the points!
* **Polynomial Regression:** We give the robot a **flexible ruler** that can bend! This allows the robot to draw **curves** to fit the dots much better.

---

### 📏 How Do We Know if Our Robot is Smart? (Our Metrics)

To see how well our robot is doing, we check two things:
1. **MAE (Mean Absolute Error) 🎯**:
   * Think of this as the **"Average Miss."**
   * If a house actually costs \$300,000, and our robot guesses \$280,000, it missed by \$20,000.
   * MAE calculates the average amount our robot misses by across all houses. **Smaller is better!**
2. **Accuracy (R² Score) 🧠**:
   * Think of this as the **"Robot's Grade."**
   * It tells us how much smarter our robot is compared to a simple guesser that just guesses the average price of all houses.
   * A score of `1.0` (or `100%`) means a perfect grade (zero mistakes!).

## 🔌 Step 1: Import our Tools & Load the Clean Data

Let's import our favorite libraries and load the same preprocessed house dataset `kc_house_preprocessed.csv`.
<img width="479" height="738" alt="step 1 pl" src="https://github.com/user-attachments/assets/dab83022-94da-4006-979c-a6252fa7e6b4" />  

## 🤖 Step 2: Train the Bendy Line Robot (Polynomial Regression)

We will train a Polynomial Regression model of Degree 2. This creates a squared feature ($Size^2$) which lets the robot bend the line to capture the curve.
<img width="564" height="188" alt="step 2 polynomial" src="https://github.com/user-attachments/assets/72d6b3a0-5b78-4248-9435-fc451a5d18e6" />  

## 📈 Step 3: Measure the Robot's Performance

Let's see how well our robot predicts house prices on the test data by calculating the MAE (Average Miss) and Accuracy ($R^2$ Score).
<img width="407" height="433" alt="step 3 pl" src="https://github.com/user-attachments/assets/8d3ff4b0-dd0a-463f-8356-dba516cb0c0c" />  

--- 
## 🎨 Step 4: Visualize the Curved Polynomial Line

Now let's draw the actual house data points and overlay the curved line our robot learned. This is much easier to explain to children!
<img width="874" height="814" alt="polynomial" src="https://github.com/user-attachments/assets/c8d13c7a-5f72-43cc-97f3-8b95d77bc50b" />  

## Day 16
## 15 July 2026
## Ridge & Lasso Regularization — Putting a Leash on our Robot! 🎗️🪓

But sometimes, if we allow our robot to bend the line too much (like using a very high degree curve), it goes completely wild! It tries too hard to touch every single dot in our training set, making the line look like a crazy zig-zag. This is called **Overfitting**.

Today, we are going to learn how to **tame our robot** using a technique called **Regularization**—which is basically putting a leash on the robot so it draws smooth, sensible curves!


### 🎓 The "Try-Hard Student" Analogy: What is Overfitting?

Imagine two students studying for a math test:
* **The Memorizer (Overfitting):** This student memorizes the exact numbers from the practice questions. When they see the exact same questions, they get 100%. But on the real test with new numbers, they get a bad grade because they didn't learn the general pattern.
* **The Smart Learner (Regularization):** This student focuses on learning the general rules and patterns. They might miss a few practice questions, but they get a great grade on the real test because they can handle new numbers!

Regularization is how we force our robot to be a **Smart Learner** rather than a **Memorizer**.

### 🎗️ The Two Types of Leashes

We have two popular leashes to control our robot:
1. **Ridge Regression (L2 Penalty) 🎗️**:
   * **The Gentle Leash:** It shrinks all the weights of the curve closer to zero, but doesn't make any of them exactly zero. It dampens the wild swings and makes the curve nice and smooth.
2. **Lasso Regression (L1 Penalty) 🪓**:
   * **The Strict Leash:** It is very strict and shrinks some weights to **exactly zero**! This means it completely throws away clues it thinks are useless, helping the robot focus only on the most important details.

## 🔌 Step 1: Import our Tools & Load the Clean Data

Let's import our favorite libraries and load the same preprocessed house dataset `kc_house_preprocessed.csv`.
<img width="735" height="813" alt="ridge " src="https://github.com/user-attachments/assets/5c0592f9-9ab3-4d3a-9c27-e743bab8b423" />  

## 🤖 Step 2: The Wild Robot (No Leash / Overfitting)

Let's see what happens when we train a Degree 6 Polynomial model without any regularization. The robot has absolute freedom to bend the line as much as it wants.
<img width="937" height="496" alt="ridge 2" src="https://github.com/user-attachments/assets/53f53d7e-5e30-4ef2-b716-6df46ff95beb" />  

## 🎗️ Step 3: The Gentle Leash (Ridge Regularization)

Now let's apply the **Ridge leash** (L2) to our Degree 6 Polynomial. This leash gently shrinks all the curve weights to make the curve smoother.
<img width="967" height="549" alt="ridge 3" src="https://github.com/user-attachments/assets/43dc9ee2-d569-4b7f-aa6e-28692abad920" />  

## 🪓 Step 4: The Strict Leash (Lasso Regularization)

Let's see the **Lasso leash** (L1) in action. Lasso will try to throw away useless polynomial terms by setting their weights to exactly zero.
<img width="892" height="556" alt="ridge 4" src="https://github.com/user-attachments/assets/e2b2943b-f092-4eb5-921a-581901947884" />  

## 🎨 Step 5: Draw the Curves!

Let's draw all the models on the same graph to see how the regularized leashes (Ridge and Lasso) keep the line from going wild compared to the unregularized model!
<img width="1070" height="832" alt="ridge 5" src="https://github.com/user-attachments/assets/c8dae26c-ab9a-4c6d-8b20-1d841ae931d4" />  

## Classification & Logistic Regression

Unlike regression (where we predict continuous numbers, like house prices), classification is all about predicting **categories or labels**.

We will use the famous **Titanic dataset** (`train.csv`) to learn about two major types of classification:
1. **Binary Classification**: Predicting between exactly two outcomes (e.g., Did a passenger survive? Yes or No / 1 or 0).
2. **Multiclass (Multilevel) Classification**: Predicting between three or more outcomes (e.g., What passenger class was someone in? Class 1, Class 2, or Class 3).


## What is Classification?
- **Binary Classification**: The target variable has only two possible values.
  - *Example*: Email is Spam (1) or Not Spam (0).
  - *Example*: Passenger Survived (1) or Did Not Survive (0).
- **Multiclass Classification**: The target variable has three or more possible values.
  - *Example*: Predict weather (Sunny, Rainy, Cloudy, Snowy).
  - *Example*: Predict Passenger Class (1st Class, 2nd Class, or 3rd Class).

## Section 0: Imports & Setup

Let's start by importing the necessary python libraries:
- `pandas` and `numpy` for data manipulation.
- `matplotlib` and `seaborn` for visualization.
- `scikit-learn` for machine learning algorithms and evaluation metrics.
<img width="1183" height="499" alt="logistic" src="https://github.com/user-attachments/assets/c19bfa65-e4fa-4f7f-9ddf-bec7a9c35218" />

## Section 1: Load Data & Exploration

We will load the Titanic dataset from `train.csv`. Let's inspect it to see what information we have about the passengers.
<img width="1761" height="538" alt="logistic 2" src="https://github.com/user-attachments/assets/c7d0570b-5d6f-42f5-b78e-f1834180641b" />  

### Preprocessing the Data

Machine Learning algorithms require numbers to work, but our dataset has:
1. **Missing values** (e.g., some ages are missing).
2. **Categorical text values** (e.g., 'Sex' is 'male' or 'female').

Let's clean this up in a very simple way:
1. Fill missing values in `Age` with the median age.
2. Fill missing values in `Embarked` with the most common value (mode).
3. Convert the `Sex` column to a binary number (`1` for female, `0` for male) so the computer can understand it.
<img width="621" height="717" alt="logistic 3" src="https://github.com/user-attachments/assets/b7526fc8-f988-4531-8230-c3efaaee9a81" />

## Section 2: Binary Classification (Predicting Survival)

In this section, we want to answer a binary question: **Did the passenger survive?**
- **Target (y)**: `Survived` (1 = Yes, 0 = No)
- **Features (X)**: `Age`, `Fare`, `SibSp` (siblings/spouses aboard), `Parch` (parents/children aboard), and `IsFemale` (gender).

### Intuition: Logistic Regression & The Sigmoid Function
How does Logistic Regression work?
1. It calculates a weighted sum of features, just like Linear Regression.
2. It passes this sum through a special function called the **Sigmoid Function**.
3. The Sigmoid function squashes any number into a value between **0 and 1**. This value can be interpreted as a **probability** (e.g., "The passenger has an 80% chance of survival").
4. If probability >= 0.5, we predict **Survived (1)**. If probability < 0.5, we predict **Not Survived (0)**.

Let's visualize the Sigmoid function:
<img width="850" height="756" alt="logistic 4" src="https://github.com/user-attachments/assets/136d5e25-b654-468f-b575-1d2c1aaedb4d" />  

### Step 1: Split the Data
We split our data into a **Training set** (to train our model) and a **Testing set** (to test how well it performs on unseen data).
<img width="520" height="315" alt="logistic 5" src="https://github.com/user-attachments/assets/981b53d3-53cd-4104-89fb-9d49394f40dc" />  

### Step 2: Train the Model
Let's fit the `LogisticRegression` model on our training data.
<img width="760" height="360" alt="split 2" src="https://github.com/user-attachments/assets/136cefdf-b1e1-4eac-8817-52834aa1bb1b" />  

### Step 3: Make Predictions and Evaluate
Now, let's predict the survival status for our testing set and evaluate how well our model did.

We will look at:
1. **Accuracy**: The percentage of passengers we correctly predicted.
2. **Confusion Matrix**: A table showing correct predictions vs. incorrect predictions:
   - **True Negatives (TN)**: Predicted Did Not Survive, actually Did Not Survive.
   - **True Positives (TP)**: Predicted Survived, actually Survived.
   - **False Positives (FP)**: Predicted Survived, actually Did Not Survive.
   - **False Negatives (FN)**: Predicted Did Not Survive, actually Survived.
3. **Classification Report**:
   - **Precision**: Out of all predicted survived, how many actually survived?
   - **Recall**: Out of all who actually survived, how many did we find?
   - **F1-Score**: The balance between Precision and Recall.
<img width="539" height="870" alt="step 3" src="https://github.com/user-attachments/assets/407018e6-5c6c-4a68-b09a-4a8baf9504e1" />  

---
## Section 3: Multiclass (Multilevel) Classification (Predicting Passenger Class)

In this section, we transition to a multiclass problem: **What Passenger Class was the passenger in?**
- **Target (y)**: `Pclass` (1 = 1st class [Upper], 2 = 2nd class [Middle], 3 = 3rd class [Lower])
- **Features (X)**: `Survived`, `Age`, `Fare`, `SibSp`, `Parch`, `IsFemale`

Since there are **three** classes here, it is a multiclass (multilevel) classification problem!

### How does Logistic Regression handle Multiclass?
By default, Logistic Regression is a binary classifier. However, it can solve multiclass problems using two common approaches:
1. **One-vs-Rest (OvR) or One-vs-All**: The model trains a separate binary classifier for *each* class (e.g., Class 1 vs. Not Class 1, Class 2 vs. Not Class 2, and Class 3 vs. Not Class 3). The class with the highest probability is selected.
2. **Multinomial (Softmax)**: The model predicts probabilities across all classes simultaneously using the Softmax function (a generalization of the Sigmoid function for multiple classes).
<img width="1290" height="767" alt="section 3" src="https://github.com/user-attachments/assets/00689025-a2ea-480c-a92b-01fd363abca4" />  

### Train the Multiclass Model
We will set the `multi_class` parameter to `'multinomial'` (which uses the Softmax function) and train the model.
<img width="843" height="314" alt="section 4" src="https://github.com/user-attachments/assets/d8bbb92b-0e41-4845-9821-5e39778f099f" />  

### Evaluate the Multiclass Model
Let's see how our model performs when classifying passengers into Class 1, 2, or 3.
<img width="482" height="772" alt="multicast model" src="https://github.com/user-attachments/assets/b1c3b53b-ac86-422c-b1bd-8c9dae0936a3" />  

## Section 4: Comparing Binary vs. Multiclass

Let's recap the differences in a simple summary table:

| Aspect | Binary Classification | Multiclass Classification |
|---|---|---|
| **Number of Classes** | Exactly 2 (e.g., 0 or 1, Yes or No) | 3 or more (e.g., 1, 2, 3) |
| **Example in Notebook** | Predicting Survival (`Survived`) | Predicting Class (`Pclass`) |
| **Underlying Function** | Sigmoid Function | Softmax Function (or One-vs-Rest) |
| **Confusion Matrix Size** | $2 \times 2$ matrix | $N \times N$ matrix (where $N = $ number of classes) |
| **Output Interpretation** | Probability of the positive class (e.g., 75% survival) | Probability distribution over all classes (e.g., 10% Class 1, 30% Class 2, 60% Class 3) |

## Day 17
## 16 July 2026
# Day 15: Decision Trees & Random Forests
## Project: Titanic Passenger Survival Prediction (continued)

### What We Will Cover Today (2-Hour Class)

| Block | Time | Topic |
|---|---|---|
| 1 | 0:00 – 0:20 | Tree-based models intuition — splitting and Gini impurity |
| 2 | 0:20 – 0:40 | Fitting Decision Trees & Visualizing Tree Splits |
| 3 | 0:40 – 1:05 | Regularizing Trees — tuning `max_depth` and leaf size |
| 4 | 1:05 – 1:30 | Ensemble learning intuition & Random Forests |
| 5 | 1:30 – 1:45 | Feature Importance — tree-based vs. logistic regression |
| 6 | 1:45 – 2:00 | Grand Classifier Comparison & Exercises |

---

### Why Tree-Based Models?

In Day 14, we used **Logistic Regression** for classification. While fast and interpretable, it assumes a **linear relationship** in the log-odds space. 

**Decision Trees** and **Random Forests** make no such assumptions. They split the data recursively based on feature thresholds: *"Is Age <= 6.5?"* → *"Is IsFemale <= 0.5?"*. 

| Property | Logistic Regression | Decision Trees / Random Forests |
|---|---|---|
| **Linearity** | Assumes linear boundary | Non-linear boundaries natively |
| **Scaling** | Sensitive to feature scaling | Scaling-invariant (splits don't care about units) |
| **Interactions** | Must engineer interaction terms | Captures feature interactions automatically |
| **Interpretability** | Coefs show log-odds impact | Highly visual (trees); feature importance (forests) |

Today, we will apply these models to classify Titanic passengers into **Survived** (1) or **Did Not Survive** (0).

## Section 0: Imports & Setup
<img width="639" height="498" alt="section 0" src="https://github.com/user-attachments/assets/e9086051-82ad-4c39-acfd-54f87111bb26" />  

## Section 1: Load Data & Preprocessing

We load the Titanic dataset from `train.csv` and apply the same simple preprocessing we learned in Day 14:
1. Fill missing `Age` values with the median age.
2. Fill missing `Embarked` values with the most common port (mode).
3. Convert the `Sex` column to a binary number `IsFemale` (1 for female, 0 for male).
<img width="727" height="516" alt="section 1" src="https://github.com/user-attachments/assets/8a06555a-41b3-40ef-8f9a-3e7a17fee0ce" />

## Section 2: How Decision Trees Split Data

A decision tree finds splits that maximize the **homogeneity** (purity) of the resulting child nodes. The default measure is **Gini Impurity**:
```
Gini = 1 − Σ (p_i)²
```
Where `p_i` is the probability of class `i` in the node. 
For binary classification (survived vs. did not survive):
- **Gini = 0** → Perfect purity (all samples belong to a single class, either everyone survived or everyone died).
- **Gini = 0.5** → Maximum impurity (exactly 50% survived and 50% died).

At each step, the tree searches over all features and split points to find the partition that yields the **largest decrease in Gini Impurity** (Information Gain).

## Section 3: Training an Unconstrained Decision Tree

Let's train a Decision Tree without limiting its growth (`max_depth=None`) and observe its performance.
<img width="757" height="516" alt="section 3" src="https://github.com/user-attachments/assets/a4b2ea1e-2536-4349-88fd-8204ab644d8a" />  

## Section 4: Visualizing Shallow Decision Trees

By limiting the tree's growth (`max_depth=3`), we can plot and inspect the splitting decisions.
<img width="902" height="875" alt="section 4" src="https://github.com/user-attachments/assets/d7d4d5db-327d-47e7-9f7b-75c047914a7a" />  

---
## Section 5: Regularization — Tuning Tree Hyperparameters

To solve the overfitting problem, we must regularize the tree by limiting its growth. The primary hyperparameters are:
- **`max_depth`**: Max length of path from root to leaf.
- **`min_samples_split`**: Minimum training samples required to split a node.
- **`min_samples_leaf`**: Minimum training samples required to be in a leaf node.

Let's sweep `max_depth` to locate the optimal bias-variance trade-off.
<img width="602" height="895" alt="section 5" src="https://github.com/user-attachments/assets/17002e3d-44ca-4aaa-8451-b282b33de2ae" />  

## Section 6: Ensemble Methods — Random Forests

A single decision tree has high variance (prone to overfitting). **Random Forests** resolve this by building an ensemble of trees and averaging their predictions (bagging).

### The Recipe of a Random Forest:
1. **Bootstrap Aggregation (Bagging)**: Each tree is trained on a random sample of the training dataset selected with replacement.
2. **Feature Subspace Sampling**: At each split, only a random subset of features is considered (e.g., `sqrt(n_features)`). This decorrelates the trees, making their collective vote more stable.
3. **Voting**: The forest outputs the class that receives the majority of votes from the individual trees.

## Section 7: Fitting a Random Forest Classifier

We train a `RandomForestClassifier` with 100 trees and limit `max_depth` to prevent overfitting.
<img width="375" height="854" alt="section 7" src="https://github.com/user-attachments/assets/fea4ec04-a92d-466f-8df4-90f301924b15" />  

---
## Section 8: Feature Importance — Trees vs. Logistic Regression

Decision Trees and Random Forests estimate feature importance based on **Gini Importance** (Mean Decrease in Impurity). It tracks how much a feature's splits reduce node impurity across the entire ensemble.

Let's plot and compare the Random Forest feature importances with Logistic Regression coefficients from Day 14.
<img width="932" height="804" alt="section 8" src="https://github.com/user-attachments/assets/7ee1c9ab-ae37-4cf1-8b2f-f721238ecb2e" />  

## Section 9: Grand Classifier Comparison

Let's put the classifiers head-to-head on the test set.
<img width="542" height="884" alt="section 9" src="https://github.com/user-attachments/assets/8bf08df0-626b-47b4-a87a-41e199722cd1" />  

## Day 18
## 17 July 2026





































































































































































