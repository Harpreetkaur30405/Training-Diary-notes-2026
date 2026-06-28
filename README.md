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






 











### Operators in Python

Operators are symbols used to perform operations on values and variables.

#### 1. Arithmetic Operators

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


#### 2. Comparison Operators

Used to compare two values and return True or False.

|Operator|	Meaning                  |
|--------|---------------------------|
|  ==	   | Equal to                  |
|  !=	   | Not equal to              |
|   >	   | Greater than              |
|   <	   | Less than                 |
|  >=	   | Greater than or equal to  |
|  <=	   | Less than or equal to     | 

Example:

10 > 5

Output:

True

#### 3. Logical Operators

Used to combine conditional statements.

|Operator|	Description                                   |
|--------|------------------------------------------------|
|   and	 |Returns True if both conditions are True        |
|   or	 |Returns True if at least one condition is True  |
|   not	 |Reverses the result                             |

Example:

True and False

Output:

False

#### 4. Assignment Operators

Used to assign and update values in variables.

|Operator|	Example |
|--------|----------|
|  +=    |  x += 5  |
|  -=	   |  x -= 5  |
|  *=	   |  x *= 5  |
|  /=	   |  x /= 5  |
|  //=	 |  x //= 5 |
|  **=	 |  x **= 5 |

Example:

x = 10

x += 5

print(x)

Output:

15
