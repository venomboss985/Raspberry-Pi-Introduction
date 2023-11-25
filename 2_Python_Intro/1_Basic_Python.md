---
marp: true
theme: gaia
class: invert
paginate: true
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
header: "*Python Introduction Pt. 1* :snake:"
---
<!-- _header: "" -->

# Introduction to Python :snake:

* Variables and data types
* Basic math operations
* Control flow
* Functions
* And more...

By: Hedron Hackerspace

![bg right w:600](https://quantumobile.com/static/0cddd58936ed9792f56f0da4b5c99b2d/5d2c5/1.png)
<!-- _footer: "Rev 1.0; Python ver. >=3.9.x" -->
---

# Common Misconceptions Pt. 1

* "You need to be **smart**"
  * No you don't, just look at the instructor
* "You need to know **a lot of difficult maths**"
  * Nope, Python and libraries will do most of it for you
* "Programming is **boring**"
  * Only if you let it, there are plenty of ways to make it interesting
* "Python is **slow** compared to other languages"
  * Yes, but it depends on your implementation (ie. Numpy)

---

# Common Misconceptions Pt. 2

* "Python is for **children**"
  * A lot of data science and cybersecurity fields use </br> nothing *but* Python
* "Programming **isn't creative**"
  * If anything, you have to* be creative to program
* "You have to know **a lot of computer science**"
  * Really only the basics are needed
<!-- _footer: "* - At least somewhat" -->
---

# IDEs and editors

* **IDE**: *integrated development environment*
  * It's the thing you code in
  * IDEs usually have
    * Syntax highlighting
    * Integrated terminal
    * Project tree and file tabs

* **Text Editor**: *just a text editor, lol*
  * Just meant to edit text in files, but certainly usable for coding
  * Most of the time, doesn't have any quality of life features

---

# Desktop GUI: VS Code

Pi OS already has Python installed, so all we need is an **IDE**. We're going to use **VS Code**, but use whichever IDE you want.

* Open a terminal window and enter `sudo apt install code-oss`
* Type in your password and accept the "Are you sure?" prompt
* Once installation is complete, enter `code` in the terminal and VS Code should automatically open
  * Or you can go into the applications menu to open it
* Go into extensions and install the official Python extension
* Sign into GitHub if you have an account (not required)

---

# Headless: Nano

Pi OS already has Python and Nano installed, so all we need to do is open it. We're going to use **Nano**, but use whichever editor you want.

* Open a terminal window and enter `nano`
* That's it...

---

# Creating a Python File

* Open the folder you want to keep your programs in
  * VS Code: File>Open Folder
  * nano: `cd <folder>`
* Create a Python file with the name `hello_world.py`
  * VS Code: New File>"hello_world.py"
  * nano: `nano hello_world.py` or use `touch` first
  * Python files NEED the `.py` extension for the interpreter to run
* Write the line `print("Hello world!")` and save the file
  * VS Code and nano: Ctrl+S

---

# Running a Python File

* VS Code: Right click>Run Python>Run Python File in Terminal
* nano: Ctrl+X to exit (after you save)>`python hello_world.py`

![w:1000](image.png)

Congratulations, you just created and ran your first (allegedly) Python program!

---

# 3 Key Programming Concepts

## (if you don't take anything else from this)

* Cooking == Programming
  * Conceptually the same thing, just one is significantly tastier
  * If you can cook or follow instructions, you can program
* EVERYTHING IS BINARY
  * This is a slightly more intermediate and won't be useful until a bit later
* The further you break something down, the easier it will be to implement

---

# Syntax

* "Sentence structure rules" for Python
* Rules such as:
  * Python uses whitespace and indents for scope
  * Don't start names with a number, special character, etc.
  * Don't use reserved names for variables, functions, etc.
* Would not recommend learning all the rules at once
  * Better learned slowly over time
  * We will touch on things as they become relevant

---

# Formatting

* [PEP-8](https://peps.python.org/pep-0008/) is the official Python Style Guide
  * Follow this if other people will see your code (industry standard)
* You can also develop your own style (like myself)
* If you want to follow a common casing, choose one of these:
  * **snake_case**: all lowercase, spaces are replaced with an underscore (PEP-8 uses this for *nearly everything*)
  * **camelCase**: no spaces, first letter of every word except the start is captialized (never used in Python)
  * **PascalCase**: camel case, but every word is capitalized (Objects)

---

# Formatting continued

Some languages use multiple cases. My personal style:

* snake_case: Variables
* camelCase: Functions
* PascalCase: Objects

![bg right w:800](https://cdn.ttgtmedia.com/rms/onlineimages/naming_conventions_in_java-f_mobile.png)

I don't use Java... don't be getting any ideas.

---

# Variables

```py
age = 20    # Sets the variable named `age` equal to 20
print(age)  # Prints the value of `age` to the terminal
>>> 20
```

* Something that stores data
* You can think of a variable like a food container
  * Name of the variable = Container label
  * Value in variable = Food itself
  * Data type = Type of food that can be stored in the container
  * Ex. `msg = "Hi"` stores the value "Hi" in a variable named `msg`

---

# Data Types

* Type of data that can be stored (type of food for a container)
* Lots of data types in Python:
  * `int` - Any whole number (including negatives)
  * `float` - Any decimal number (including negatives)
  * `bool` - Binary value (`True` or `False`)
  * `list` - Array of values
  * `str` - List of characters
  * `dict` - List of key-value pairs
  * Others include: `range`, `bytes`, `tuple`, `set`

---

## Examples of data types

* `int` - `10`, `23`, `-40`, `-96`, `1502089109740`, `-129379379`
* `float` - `10.0`, `-1532.32523409`, `-302.`, `3.141592`
* `bool` - `True`, `False`, `1`, `0`
* `list` - `[1, 5, False, True, -23940.212, -129423, 364, -0.15246]`
* `str` - `"Hello"`, `'a'`, `"Python loves memory"`, `"42.7837"`
* `dict` - `{"apples": 10, "oranges": 7, "bananas": 4, "grapes": 26}`

---

## Why data types are important

* Python is a loosely typed language
  * Data types are implicitly set and sometimes implicitly casted
  * Ex. `age = 20` automatically assigns `age` the data type of `int`
* If data is used with the wrong data type, errors can be thrown
  * Ex. `10 == "10"` will return `False` because integers are different from strings
* Type casting changes the data type of a value
  * Type cast by returning a value with a constructor
  * Ex. `10 == int("10")` will return `True` because they have the same value

---

# Basic Math Operations

```py
age = 20        # Sets the variable `age` to equal 20
age = age + 5   # Sets `age` to the current value of `age` and 5
print(age)      # Prints the value of `age` to the terminal
print(age % 5)  # Prints the remainder of `age` / 5
>>> 25
>>> 0
```

* Some basic operators include:
  * Addition, subtraction, multiplication, division, remainder (+-*/%)
  * Exponents, integer (floor) division (**, //)
* More operations can be done with the `math` module

---

## Using Multiple Operations

```py
apples = 10
oranges = 7
bananas = 4
fruit = apples + oranges + bananas
print(fruit)
>>> 21
```

```py
num_fruits = 3
avg_fruits = (apples + oranges + bananas) / num_fruits
print(avg_fruits) 
>>> 7.0
```

<!-- ```py
x = 6
y = 2*x-3
print(y)
>>> 9
``` -->

* PEMDAS rules apply

---

## Compound Operators

```py
count = 20
count += 5
count /= 5
print(count)
>>> 5.0
```

* Fast way to modify stored values
* Uses the operator appended with `=`
  * Ex. `count *= 7` multiplies 7 to the variable `count`
  * Ex. `clients -= 10` subtracts 10 from the variable `clients`

---

# Control Flow

* Doing different things under certain conditions
  * Compare values to determine a condition
  * Do something based on that condition
  * Ex. If there are 6 fruit, print the number of apples
* Doing something repeatedly
  * Set the conditions of the repetition
  * Do something based on that condition
  * Ex. Send a "hello" message to every client connected to a server

---

## Comparison Operators

```py
print(42 > 2**8)
>>> False
```

* Returns if a statement is `True` or `False`
* Operators:
  * `==`, `!=` - Equal to, Not equal to
  * `<`, `>` - Less than, Greater than
  * `<=` - Less than or equal to
  * `>=` - Greater than or equal to

---

## Logical Operators

```py
print(42 > 2**8 or 42 < 700)
print(not 42 >= 2**5)
>>> True
>>> False
```

* Returns if all statements are `True` and/or `False`
* Operators:
  * `and` - If at least one value is `False`, returns `False`
  * `or` - If at least one value is `True`, returns `True`
  * `not` - If value is `True`, return `False` (and vice versa)

---

## `if` Statement

```py
connected_clients = 3
if connected_clients > 1:
  print("Chatroom initializing")
elif connected_clients == 10:
  print("Chatroom limit reached")
else:
  print("Waiting for more clients")
```

* `if` - Runs the first codeblock if the condition is `True`
* `elif` - Runs the second codeblock if the first condition is `False` and second condition is `True`
* `else` - Runs the last codeblock if neither conditions are `True`

---

## `for` Loop

```py
result = 0
numbers = [67, -236, -112, 445, 14]
for num in numbers:
  result += num
  print(result)
>>> 67
>>> -169
>>> -281
>>> 164
>>> 178
```

<!-- ```py
total = 0
for i in range(10):
  total += i
print(total)
>>> 45
``` -->

* `num` is the value of the object at an internally tracked index
* `numbers` can be any iterable object (ie. `range`, `list`, etc.)

---

## `while` Loop

```py
num = 0
run = True
while run == True:
  num += 1
  if num > 100:
    run = False
  print(num)
>>> 1
>>> 2
>>> ...
>>> 101
```

* Checks if the condition is `True` before running the code block
* Once the condition returns `False`, the block will be skipped

---

## Going further with loops

```py
for num in range(10000):
  if num % 2 == 0: continue
  if num == 1000: break
  print(num)
>>> 1
>>> 3
>>> ...
>>> 9997
>>> 9999
```

* Both keywords can be used with either `for` or `while` loops
* `break` - Exits the loop at the executed line
* `continue` - Stops the code and starts again at the next iteration

---
