# Training Diary 2026
## Day 1
## Date: 22 June 2026
### Introduction to Python

On the first day of the AI/ML training program, we installed Python and learned about different platforms for writing and executing Python code. We were introduced to Google Colab, a cloud-based environment that allows users to write and run Python programs directly through a web browser without installing software locally.
### Variables in Python
A variable is a name used to store data in memory.Variables allow us to save and manipulate information within a program.  
#### Example:  
name = "Harpreet"  
age = 20  
Here, name and age are variables.

### The type() Function  
The type() function is used to determine the data type of a variable.  
#### Example:  
x = 42  
print(type(x))  
#### Output:  
<class 'int'>  
This shows that x is an integer (int) data type.  

### The id() Function  
The id() function returns the unique memory address (identity) of an object.  
#### Example:  
x = 42  
print(id(x))  
#### Output:  
140721234567890  
(The actual number may vary on different systems.)  
This value represents the memory location where the object is stored.

### Formatted Strings (f-Strings)  
Python provides f-strings (formatted strings) to insert variables directly into text.  
The letter f before a string tells Python to evaluate expressions written inside curly braces {}.  
#### Example:  
name = "Harpreet"  
print(f"My name is {name}")  
#### Output:  
My name is Harpreet

### Difference Between f-String and Normal String  
#### Using f-string:  
print(f"Data Type of x: {type(x)}")  
#### Output:  
Data Type of x: <class 'int'>  
Python evaluates the expression inside {}.

#### Using normal string:  
print("Data Type of x: {type(x)}")  
#### Output:  
Data Type of x: {type(x)}  
Since there is no f before the string, Python treats everything as plain text and does not evaluate the expression.  
Example :  <img src="https://github.com/username/repo/blob/main/day1.jpg?raw=true" width="500">

### Dynamic Typing

Python is a dynamically typed language, which means we do not need to declare the data type of a variable explicitly. Python automatically determines the type based on the assigned value.

Example:

x = 10

x = "Hello"

The same variable can store different types of data at different times.

### Data Types in Python

Data types define the type of value stored in a variable.

#### 1. Numeric Types

Numeric data types are used to store numbers.

Integer (int) – Whole numbers

Float (float) – Decimal numbers

Complex (complex) – Numbers with real and imaginary parts

#### Examples:

my_int = -10

my_float = 3.14159

my_complex = 2 + 3j

print(type(my_int))

print(type(my_float))

print(type(my_complex))

print(my_complex.real, my_complex.imag)

#### Output:

<class 'int'>

<class 'float'>

<class 'complex'>

2.0 3.0

#### 2. String Type

Strings are used to store text data.

##### Single-Line String

name = "Harpreet"

##### Multi-Line String

message = """
Welcome to AI/ML Training.
This is a multiline string.
"""

#### Example:

single_line = "Hello AIML Freshers!"

multi_line = """This is a multi-line string.

It is very useful for documentation strings (docstrings) or block comment."""

print(single_line)

print(multi_line)

print(type(single_line))

print(type(multi_line))

#### Output: 

Hello AIML Freshers!

This is a multi-line string.

It is very useful for documentation strings (docstrings) or block comment.

<class 'str'>

<class 'str'>

Strings are enclosed within single quotes (' '), double quotes (" "), or triple quotes (''' ''' or """ """).

#### 3. Boolean Type

Boolean values represent logical conditions.

True

False

Example:

is_student = True

#### 4. None Type

The None value represents the absence of a value or a null value.

Example:

result = None

### Mutable and Immutable Objects

#### Immutable Objects

Objects whose values cannot be changed after creation are called immutable objects.

Examples:

int

float

string

tuple

name = "Python"

A new object is created if the value is modified.

#### Mutable Objects

Objects whose values can be modified after creation are called mutable objects.

Examples:

list

dictionary

set

numbers = [1, 2, 3]

numbers.append(4)

The original object is modified directly.

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
