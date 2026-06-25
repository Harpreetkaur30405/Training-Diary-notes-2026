# Training Diary 2026
## Day 1
## Date: 22 June 2026
### Introduction to Python

On the first day of the AI/ML training program, we installed Python and learned about different platforms for writing and executing Python code. We were introduced to Google Colab, a cloud-based environment that allows users to write and run Python programs directly through a web browser without installing software locally.
### Variables in Python

A variable is a name used to store data in memory. Variables allow us to save and manipulate information within a program.

Example:

name = "Harpreet"

age = 20

Here, name and age are variables.
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

Examples:

a = 10

b = 3.14

c = 2 + 3j

#### 2. String Type

Strings are used to store text data.

##### Single-Line String

name = "Harpreet"

##### Multi-Line String

message = """
Welcome to AI/ML Training.
This is a multiline string.
"""

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

|Operator|	Description	Example
|+	             Addition	5 + 2 = 7
|-	Subtraction	5 - 2 = 3
|*	Multiplication	5 * 2 = 10
|/	Division	5 / 2 = 2.5
|%	Modulus (Remainder)	5 % 2 = 1
|//	Floor Division	5 // 2 = 2
|**	Exponentiation	5 ** 2 = 25


#### 2. Comparison Operators

Used to compare two values and return True or False.

Operator	Meaning

-	Equal to(==)
  
-	Not equal to(!=)
  
-	Greater than(>)
  
-	Less than(<)
  
-	Greater than or equal to(>=)
  
-	Less than or equal to(<=)

Example:

10 > 5

Output:

True

#### 3. Logical Operators

Used to combine conditional statements.

Operator	Description

- and	Returns True if both conditions are True
  
- or	Returns True if at least one condition is True
  
- not	Reverses the result

Example:

True and False

Output:

False

#### 4. Assignment Operators

Used to assign and update values in variables.

Operator	Example

- +=	x += 5

- -=	x -= 5

- *=	x *= 5

- /=	x /= 5

- //=	x //= 5

- **=	x **= 5

Example:

x = 10

x += 5

print(x)

Output:

15
Learning Outcomes

By the end of Day 1, I was able to:

Install Python and understand the use of Google Colab.
Understand variables and dynamic typing in Python.
Learn different Python data types.
Differentiate between mutable and immutable objects.
Use arithmetic, comparison, logical, and assignment operators.
Write basic Python statements and perform simple operations.
Conclusion

The first day of training provided a strong foundation in Python programming. I learned about variables, data types, mutable and immutable objects, and different categories of operators. These concepts are essential for further learning in Artificial Intelligence and Machine Learning.
