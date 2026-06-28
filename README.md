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



























