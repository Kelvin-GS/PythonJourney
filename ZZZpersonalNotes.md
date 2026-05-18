#### Built in Python functions

The Python Standard Library has some built in functions. Some of these useful functions are:

| Function              | Meaning                                               |
| :-------------------- | :---------------------------------------------------- |
| `len(x)`            | **length** of x                                 |
| `pow(x, n)`         | x to the**power** n (x\*\*n)                    |
| `abs(x)`            | **absolute value** of x                         |
| `round(x, n)`       | **round** x to n digits after the decimal point |
| `min(x, y, z, ...)` | the**minimum** value of x, y, z, ...            |
| `max(x, y, z, ...)` | the**maximum** value of x, y, z, ...            |

Some common type conversion functions are:

|  Function  |          Description          |
| :---------: | :----------------------------: |
|  `int()`  | converts a value to an integer |
| `float()` |  converts a value to a float  |
|  `str()`  |  converts a value to a string  |

**Note:** not all strings can be converted to an `int` or a `float`. With the `isnumeric()` method we can check whether all characters of a string are numeric (ie. `0`, `1`, ..., `9`):

#### Modules

print(math.pi) # 𝜋 (3.3.1415...)
print(math.e) # Euler constant (2.7182...)

#### String Concatenation

We observe that:

- the `print()` adds one space in between strings. This can be changed with the `sep` argument of the `print()` function.
- At the end of the line, `print()` adds a newline character. This can be changed with the `end` argument of the `print()` function.
- with the `+` operator strings are concatenated without extra spaces in between
- string duplication with the `*` operator saves typing time

  ```
  print(word1, word2, word3, sep = "***", end = ";)-")    # Instead of white space, adds what ever is in "sep"
  ```

#### String manipulation

Often we need to manipulate strings:

- search for a character or a substring,
- count the numberof occurances,
- replace one or more characters by others,
- split the string,
- etc.

Python has an extensive list of string methods. Some useful methods are:

|    Method    | Description                                                                                             |
| :-----------: | ------------------------------------------------------------------------------------------------------- |
|  `find()`  | Searches the string for a specified value and returns the**first** position of where it was found |
|  `count()`  | Returns the number of times a specified value occurs in a string                                        |
| `replace()` | Returns a string where a specified value is replaced with a specified value                             |
|  `split()`  | Splits the string at the specified separator, and returns a list                                        |
|  `lower()`  | Converts a string into**lower** case                                                              |
|  `upper()`  | Converts a string into**upper** case                                                              |

#### Slicing

Slicing is the selection of multiple characters. Again, the index operator `[]` is used:

```Python
    s[i:j] # with i < j
```

means: select the characters with indices `i`, `i+1`, up to `j-1`. The character with index `j` is **not included** in the selection.

The **general** syntax is:

```python
    s[start:stop:step]
```

where

- `start` is the index of the first element (default is 0),
- `stop` is the index of the last element (**not included**, default is len(list_name)) and
- `step` is the number of elements to skip (default is 1).

**Example:**

`print(s[0:4])   # select characters with indices 0 up to 3`

|    Slice    | Meaning                                                                      |
| :----------: | ---------------------------------------------------------------------------- |
|   `s[i]`   | character at index `i` (counting starts at 0)                              |
|  `s[i:j]`  | characters `i` up to `j-1` (character `j` **not** included)      |
|  `s[i:]`  | characters from `i` up to end of string                                    |
|  `s[:j]`  | characters from start up to `j-1` (character `j` **not** included) |
| `s[i:j:k]` | characters from `i` up to `j-1` in steps of `k`                        |
|   `s[:]`   | all characters                                                               |
| `s[::-1]` | all characters in**reversed** order                                    |

#### Basic formatting

To use `f` strings:

- place an `f` or an `F` before the string to be formatted
- type accolades `{}` (_place holders_) around the variable to be formatted
- let the variable be followed by a colon `:`
- specify the datatype of the variable:

| Character | Datatype |
| :-------: | -------- |
|   `s`   | string   |
|   `d`   | integer  |
|   `f`   | float    |

- print the `f` string with the `print()` function

The syntax to format a variable is

```Python
    {variable:xtype}
```

with:

- `variable`: the name of the variable to be formatted
- `x`: the number of characters (places) to be used
- `type`: the datatype of the variable to be formatted (`s`, `d` or `f`)

```python
char = "a"
n = 23
print(f"The character {char:5s} occurs {n:10d} times")  # THis leaves 5 spaces for the variable "char" and 10 spaces for "n"

# Output is : The character a     occurs         23 times
```

```python
bmi = 21.718
name = "John"
print(f"{name:10s} has a BMI of {bmi:7.1f}.")   # Specifies to leave 1 decimal place

# Output: John       has a BMI of    21.7.
```

The formatting `{name:10s}` means: use 10 characters to represent the value of `name`. Since 10 places were provided and strings are aligned to the left, and `John` takes 4 places, 6 additional spaces were added to the **right** of `John`. The `s` stands for string.

The formatting `{bmi:7.1f}` means: use 7 characters to represent the value of `bmi` and round to 1 decimal place. The `f` stands for float.

Since 7 places were provided, and numbers are aligned to the right, and `21.7` takes 4 places (the dot takes one too), 3 additional spaces were added to the **left** of `21.7`.

**Alignment**

The alignment can be specified by adding `<`, `>` or `^` just after the colon:

| Character | Alignment |
| :-------: | --------- |
|   `<`   | left      |
|   `>`   | right     |
|   `^`   | centered  |

```
bmi = 21.718
name = "John"
print(f"{name:>10s} has a BMI of {bmi:<7.1f}.")   # Specifies to leave 1 decimal place: And "<", means to left align: ">" means to right align
```

#### Logical expressions

**Logical** expressions are a combination of values, variables, **logical** and **comparison** operators. Upon evaluation the result will always be either `True` (1) or `False` (0).

The **comparison** operators are:

| Operator | Description              |
| :------: | ------------------------ |
|  `==`  | equal                    |
|  `!=`  | not equal                |
|  `<`  | lower than               |
|  `<=`  | lower than or equal to   |
|  `>`  | greater than             |
|  `>=`  | greater than or equal to |

The **logical** operators are:

| Operator | Description                                                     |
| :------: | --------------------------------------------------------------- |
| `and` | conjunction: returns `True` if both expressions are true      |
|  `or`  | disjunction: returns `True` if one of the expressions is true |
| `not` | negation: reverses the result                                   |

The **order of operation** becomes:

| Priority |                 Operator(s)                 | Meaning                                               |
| :------: | :------------------------------------------: | ----------------------------------------------------- |
|    1    |                    `()`                    | parenthesis                                           |
|    2    |                    `**`                    | exponent                                              |
|    3    |                `+`x, `-`x                | unary +, unary -                                      |
|    4    |         `*`, `/`, `%`, `//`         | multiplication, division, remainder, integer division |
|    5    |                 `+`, `-`                 | addition, substraction                                |
|    6    | `==`, `!=`, `<`, `<=`, `>`, `>=` | comparison                                            |
|    7    |                  `not` x                  | negation                                              |
|    8    |                   `and`                   | conjunction                                           |
|    9    |                    `or`                    | disjunction                                           |

**Note:** be careful when `and` and `or` both appear in an expression. Use parenthesis to emphasize (or change) the priority of operators.

Some examples will illustrate the use of these operators:

#### The `if-else`-statement

An `if-else`-statement has the following syntax:

```Python
    if condition1:
        # instruction(s) to be executed if condition1 is True
    elif condition2:
        # instruction(s) to be executed if condition1 is False and condition2 is True
    else:
        # instruction(s) to be executed if conditions above are False
```

**Important notes**

- the `condition` can be a **composite** expression.
- the colon `:` is **mandatory**
- the instruction(s) to be executed are **indented**

#### The `while` loop

A `while` loop executes the instructions within the `while`-suite a **variable** number of times. How many times times depends on the condition.

The syntax is:

```Python
    while condition:
        # instruction(s) to be executed if condition is True
```

The `condition` is an (composite) expression containing a loop control variable whose value changes in the `while` loop.

**Example**

Given a positive number $n$, print all powers of 2 smaller than $n$. This can be realized by the following `while` loop:

```
n = 25
p = 0 # first power of 2 (ie. 2**0)
while 2**p < n:
    print(2**p)
    p = p + 1
```

#### The `for` loop

A `for` loop is a control structure that allows to repeat code a **fixed number of times**.

**Syntax**

The syntax is:

```Python
    for variable in sequence:
        # instruction(s) to be executed for each value of variable
```

where:

- `variable`: a loop variable (placeholder) that takes the value of each element in the sequence, one at a time
- `sequence`: a collection of elements
  - characters (as in a string)
  - range of numbers
  - ...

#### The `range()` function

The `range()` function creates a sequence of **whole** numbers.

The syntax is:

```Python
    range(start, stop, step)
```

where

- `start`: start value (optional, default 0)
- `stop`: stop value (obligatory, **not included in result**)
- `step`: step size (optional, can be negative, default 1)

```
for i in range(3, 11):     # first = 3, last = 10
    print(i)
```

```
for i in range(0, 10, 2):  # first = 0, last = 8
    print(i)

# This gives numbers in steps of 2, from 0 to less than 10
```

#### Nested for loops

It is possible to nest `for` loops. This means that a `for` loop is placed inside another `for` loop. The inner `for` loop is executed for each iteration of the outer `for` loop.

The syntax is:

```Python
    for variable1 in sequence1:
        for variable2 in sequence2:
            # instruction(s) to be executed for each value of variable1 and variable2
```

Suppose you want to print all possible combinations of two dice. This can be achieved by:

```Python
    for i in range(1, 7):     # first dice
        for j in range(1, 7): # second dice
            print(i, j)       # combinations
```

Try to understand the code above. What is the value of `i` and `j` for each iteration of the inner `for` loop?

#### The `break` statement

The `break` statement is used to exit a loop prematurely. The `break` statement is placed inside the loop and stops the execution of the loop. The program continues with the first instruction after the loop.

Suppose you want to check whether a number is prime. The code checks whether `n` is divisible by any number between 2 and $\sqrt{n}$. If a divisor is found, the value of `prime` is set to `False`. If no divisor is found, the value of `prime` stays `True` and the number is prime. **As soon as a divisor is found, the loop is exited.** The value of `prime` is set to `False` and the program continues with the first instruction after the loop.

```
n = input("Enter a whole number (> 2): ")
n = int(n)
prime = True
for i in range(2, int(n**0.5)+1):
    if n % i == 0:
        prime = False
        break
if prime:
    print(n, "is a prime number")
else:
    print(n, "is not a prime number")
```

#### Syntax of a Function

The syntax of a function in Python is as follows:

```python
    def function_name(parameters):
        statement(s)
        return variable
```

In this syntax:

- `def`: a keyword that marks the beginning of the function header.
- `function_name`: the name of the function
- `parameters`: the values passed to the function (optional)
- `statement(s)`: the (**indented**) block of statements that perform the operations of the function.
- `return variable`: is used to return a value from the function (optional)

Note that the statements in the function are indented. This is how Python knows that these statements are part of the function.

A first example of a function is the function `mean()` that calculates the mean of a list of numbers. The function is defined as follows:

```python
    def mean(numbers):
        total = sum(numbers)
        length = len(numbers)
        average = total / length
        return average
```

The name of the function is `mean`, and it takes one parameter, `numbers`. The function calculates the sum of the numbers in the list, and divides this sum by the length of the list. The result (average) is returned by the function.

**Functions can have multiple return values**. For example, the following function `circle()` computes the area and circumference of a circle with radius `r`. The function takes 1 argument, `r`, and returns the area and circumference of the circle.

```python
    import math
    def circle(r):
        area = math.pi*r**2
        circumference = 2*math.pi*r
        return area, circumference
```

```python
# import math module
import math
# function definition
def circle(r):
    area = math.pi*r**2
    circumference = 2*math.pi*r
    return area, circumference

# test instructions
r = 5
area, circumference = circle(r) # Assigns the returns to separate variables
print("Area:", round(area, 2))
print("Circumference", round(circumference, 2))
```

#### Variable scope

The scope of a variable is the part of the program where the variable is accessible. In Python, variables defined inside a function are not accessible outside the function. These variables have local scope. Variables defined outside a function are accessible inside the function. These variables have global scope. When you call a function, Python first looks for the variable in the local namespace. If the variable is not found, Python looks for the variable in the global namespace. If the variable is not found in the global namespace, Python looks for the variable in the built-in namespace.

#### Default arguments

You can specify default values for the arguments of a function. If you call the function without specifying the value of an argument, the default value is used. An example of a built-in function with default arguments is the function `round()`. The function `round()` takes 2 arguments: `number` and `ndigits`. The default value of `ndigits` is 0. If you call the function `round()` with only 1 argument, the default value 0 is used and the number is rounded to the nearest integer.

An example with a user-defined function is the function `kin_energy()` where we make `g` a default argument. If you call the function `kin_energy()` without specifying the value of `g`, the default value 9.81 is used:

```
# function definition
def kin_energy(m, v0, h, g = 9.81):	# This step specifies a default value for g
    KE = 1/2*m*v0**2 - m*g*h
    return KE

# test instructions
m = 1.25
v0 = 10
h = 5
KE = kin_energy(m, v0, h) # g is not provided
print("On Earth", round(KE, 2), "J")
```

#### Lambda functions

A lambda function is a small anonymous function. A lambda function can take any number of arguments, but can only have one expression. The syntax of a lambda function is as follows:

```python
lambda argument(s): expression
```

In this syntax:

* `lambda`: a keyword that marks the beginning of the lambda function.
* `argument(s)`: the argument(s) of the lambda function.
* `expression`: the expression that is evaluated and returned by the lambda function.

For example, the following lambda function calculates the square of a number:

```python
square = lambda x: x**2
```

You can call the lambda function with an argument.

```python
# lambda function definition
square = lambda x: x**2
# test instructions
square(3)
```

Lambda functions can include multiple arguments. For example, the following lambda function calculates the sum of two numbers:

```python
add = lambda x, y: x + y
```

Lambda functions can include if-else-statements. For example, the following lambda function returns the string 'positive' if the number is positive, and 'negative' if the number is negative:

```python
# Lambda function definition
sign = lambda x: "positive" if x > 0 else "negative"

# Test instructions
print(sign(3))
print(sign(-3))
```

#### Creating a List

You can create a list by **enclosing the values in square brackets and separating them with commas**.

Check the following examples:

```python
# Creating an empty list
L = []
print(L)

# List of numbers
decimal = [8, -1, 4.2, 75, -0.93, 3]
print(decimal)

# List of strings
words = ["hello", "world", "python", "is", "cool", "yeah"]
print(words)

# List of mixed data types
data = ["John", 1.75, 70]
print(data)
```

#### Other ways to create a list

There are some other ways to create a list:

* Using the `list()` constructor to convert a string to a list.
* Using the `split()` method to split a string into a list.

```python
# Using the list() constructor to convert a string to a List
list2 = list("Hello")
print(list2)

# Using list() and range() to create a list of numbers
numbers = list(range(10))
print(numbers)
```

#### Accessing elements by slicing

You can access a range of elements in a list using slicing. The syntax for slicing is similar to the syntax for slicing a string. The syntax is:

```python
    list_name[start:stop:step]
```

where

* `start` is the index of the first element (default is 0),
* `stop` is the index of the last element (**not included**, default is len(list_name)) and
* `step` is the number of elements to skip (default is 1).

The following table summarizes some indexing and slicing possibilities (the variable `L` represents a string):

|    Slice    | Meaning                                                                   |
| :----------: | ------------------------------------------------------------------------- |
|   `L[i]`   | element at index `i` (counting starts at 0)                             |
|  `L[i:j]`  | elements `i` up to `j-1` (element `j` **not** included)       |
|  `L[i:]`  | elements from `i` up to end of list                                     |
|  `L[:i]`  | elements from start up to `i-1` (element  `i` **not** included) |
| `L[i:j:k]` | elements from `i` up to `j-1` in steps of `k`                       |
|   `L[:]`   | all elements                                                              |
| `L[::-1]` | all elements in**reversed** order                                   |

#### Iterating over a List

Just as with strings, you can iterate over the elements in a list using a `for` loop. Iterating can be index based or element based. The following examples show both methods.

```python
# Index based iteration
words = ["hello", "world", "python", "is", "cool", "yeah"]
for i in range(len(words)):
    print(i, words[i])
```

```python
# Element based iteration
i = 0
for word in words:
    print(i, word)
    i = i + 1
```

#### Adding elements to a list

You can add elements to a list using the `append()` method. The `append()` method adds the element to the end of the list.

```python
    list_name.append(element)
```

Note that we don't write `L = L.append(element)` because the `append()` method **does not return a new list**. It modifies the original list.

#### Extending a list

You can add multiple elements to a list using the `extend()` method. The `extend()` method adds the elements of the list to the end of the list. Its basically the same as using the "+" operator to concatenate.

```python
    list_name.extend(list2)
```

Example:

```python
L = ["First element", "Second element"]
L2 = ["Third element", "Fourth element", "Fifth element"]
L.extend(L2)
print(L)

# Output: ['First element', 'Second element', 'Third element', 'Fourth element', 'Fifth element']
```

#### The `in` and `not in` operators

You can check if an element is in a list using the `in` operator. You can also check if an element is not in a list using the `not in` operator.

Example:

```python
L = ["apple", "banana", "cherry", "date"]
"pear" in L		# Returns a boolean
```

#### List methods

There are several methods that you can use with lists. We already encountered `append()` and `extend()`. Some of the other methods are:

| Method                       | Meaning                                                   |
| ---------------------------- | --------------------------------------------------------- |
| `L.insert(index, element)` | adds `element` at a specific `index`                  |
| `L.remove(element)`        | removes the first occurrence of `element` from the list |
| `L.index(element)`         | returns the index of the first occurrence of `element`  |
| `L.count(element)`         | returns the number of occurrences of `element`          |
| `L.sort()`                 | sorts the elements in the list                            |

You can get a complete list of methods by typing

* `dir(list)` or
* the name of a list followed by a dot

Note that the `sort()` method **modifies the original list**, such as the `append()`, `extend()`, `insert()` and `remove()` methods.

#### Creating nested lists

A list can contain other lists. This is called a **nested list**. You can access the elements in the nested list using multiple indices.

Suppose we want to represent the following matrix $A$ (a two-dimensional array) in Python:

$$
A = \left [
\begin{matrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9 \\
10 & 11 & 12
\end{matrix}
\right ]
$$

We can use a nested list:

```python
    A = [ [1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12] ]
```

Note that each row of the matrix is a list: the matrix is a list of lists.

The elements don't have to be of the same type. For example, the following list contains strings, floats and integers:

```python
    bmi_data = [["John", 1.75, 70], ["Mary", 1.65, 58], ["Tom", 1.80, 83], ["Alice", 1.70, 61]]
```

The sublists don't have to be of the same length. For example, the following list contains sublists of different lengths:

```python
    data = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
```

#### Accessing elements by a single index

Accessing elements in a nested list is similar to accessing elements in a simple list. By using a single index, you can access the entire row. For example, to access the **second row** in the matrix $A$, you use the index `1`:

```python
A = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
A[-1]

# Output: [10, 11, 12]
```

#### Accessing elements by multiple indices

You can access the elements of a nested list using **multiple indices**. For example, to access the element 1.70 (height of Alice) in `bmi_data`, you use the indices `3` and `1`:

```python
bmi_data = [["John", 1.75, 70], ["Mary", 1.65, 58], ["Tom", 1.80, 83], ["Alice", 1.70, 61]]
bmi_data[3][1] # height of Alice

# Output is: 1.7
```

To compute the BMI of all persons in `bmi_data`, you can use a loop:

```python
bmi_data = [["John", 1.75, 70], ["Mary", 1.65, 58], ["Tom", 1.80, 83], ["Alice", 1.70, 61]]

# element based indexing*
for person in bmi_data:
    bmi = person[2] / person[1]**2
    print(person[0], "has a BMI of", round(bmi, 2))

# index based indexing
for i in range(len(bmi_data)):
    bmi = bmi_data[i][2] / bmi_data[i][1]**2
    print(bmi_data[i][0], "has a BMI of", round(bmi, 2))

# Output:
# John has a BMI of 22.86
# Mary has a BMI of 21.3
# Tom has a BMI of 25.62
# Alice has a BMI of 21.11
```

#### Iterating over a nested list

You can iterate over a nested list using nested loops. The outer loop iterates over the rows and the inner loop iterates over the elements in the row.

This is how you can iterate element by element over the matrix $A$:

```python
A = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
for row in A:
    for element in row:
        print(element, end = " ")
    print()
```

```python
A = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
for i in range(len(A)):
    for j in range(len(A[i])):
        print(A[i][j], end = " ")
    print()
```

#### List comprehension

List comprehension is a concise way to create lists. It is a compact way to apply an operation to each element in a list. The syntax is:

```python
    [expression for item in list]
```

Some examples will explain the usage of list comprehension.

Consider the following sequence of numbers:

$$
1^2,\quad 2^2,\quad 3^2,\quad ...,\quad 99^2,\quad 100^2
$$

Without list comprehension, we would write:

```python
    squares = []
    for x in range(1, 101):
        squares.append(x**2)
```

We can use list comprehension to create a list of the squares of the numbers from 1 to 100:

```python
    squares = [x**2 for x in range(1, 101)]
```

We can include an `if`-statement in the list comprehension. For example, to create a list of the squares of the even numbers from 1 to 100:

```python
    squares_even = [x**2 for x in range(1, 101) if x % 2 == 0]
```

The result is the following sequence:

$$
2^2,\quad 4^2,\quad 6^2,\quad ...,\quad 98^2,\quad 100^2
$$

#### Immutable objects

Strings, ints and floats are immutable.  When you change a copy, the variable name refers to a new memory register.

```python
my_int = 27
your_int = my_int
print('my_int:', my_int)
print('your_int:', your_int)

# Output:
# my_int: 27
# your_int: 27

your_int = your_int + 1
print('my_int:', my_int)
print('your_int:', your_int)

# Output:
# my_int: 27
# your_int: 28
```

For strings, immutability also means that you cannot change individual characters or slices.

```python
a_string = "abc"
print(a_string)
a_string[1] = 'B'
# This cell should give an error.
```

#### Mutable objects

**Lists are mutable:** the individual elements of a list can be changed.

Elements of a list do not contain values; they contain references to memory addresses.  If you change an element of a *shallow* copy, the original list also changes.

```python
a_list = [1,2,3]
b_list = a_list
print('a_list:', a_list)
print('b_list:', b_list)
print()

# Output:
# a_list: [1, 2, 3]
# b_list: [1, 2, 3]
```

```python
b_list[1] = 20
print('a_list:', a_list)
print('b_list:', b_list)

# Output:
# a_list: [1, 20, 3]
# b_list: [1, 20, 3]
```

As you can see in the previous cell, we only changed the value of one element in ``b_list``, yet ``a_list`` changed as well. If this is not the behaviour you like for your program, you can make a *deep* copy.  A deep copy of a list is filled with new memory addresses, and these are filled with copies of the values.  One of the ways to do this is to use the `.copy()` method.

```python
a_list = [1,2,3]
b_list = a_list.copy()	# This is a deep copy, creating immutability!!!
print('a_list:', a_list)
print('b_list:', b_list)
print()

b_list[1] = 20
print('a_list:', a_list)
print('b_list:', b_list)

```

```
a_list: [1, 2, 3]
b_list: [1, 2, 3]

a_list: [1, 2, 3]
b_list: [1, 20, 3]
```

#### Creating tuples

Tuples are a lot like lists. They are defined by **parentheses** `()`:

```python
    coord = (3, -2, 4)
```

#### Accessing tuple elements

You can access the values in a tuple just like you can in a list:

```python
    print(coord[2]) # prints 4
```

#### Iterating over tuples

You can iterate over tuples just like you can with lists: index based or element based.

```python
# index based iteration
coord = (3, -2, 4)
for i in range(len(coord)):
    print(coord[i])

# element based iteration
for x in coord:
    print(x)
```

#### Tuple concatenation and duplication

You can **concatenate** tuples by using the `+` operator, just as with lists:

```python
    coord1 = (3, -2, 4)
    coord2 = (1, 2, 3)
    print(coord1 + coord2) # prints (3, -2, 4, 1, 2, 3)
```

You can also **duplicate** tuples by using the `*` operator, just as with lists:

```python
    coord = (3, -2, 4)
    print(coord * 3) # prints (3, -2, 4, 3, -2, 4, 3, -2, 4)
```

#### Tuple manipulation

With concatenation and duplication a new tuple is created. You can't change the values of a tuple once it's created: tuples are **immutable**. This is a key difference between tuples and lists.

#### Dictionaries

A dictionary in Python is a built-in data structure that allows you to store and retrieve data in the form of key-value pairs. Each unique key is associated with a specific value, enabling efficient data lookup and manipulation.

A key in a dictionary must be unique and immutable, such as strings, numbers, or tuples. The values can be of any data type, including strings, numbers, lists and tuples.

A value can be a single value or a list of values.

Dictionaries are commonly used when you need to quickly access data based on unique identifiers, such as usernames, product IDs, or settings.

#### Creating dictionaries

Dictionaries are defined by **curly braces** `{}`. An **empty dictionary** is created by `{}`:

```python
    D = {}
```

The syntax for a non-empty dictionary is `key: value` pairs separated by commas:

```python
    D = {key1: value1, key2: value2, key3: value3, ...}
```

Suppose you want to store the atomic weights of some elements. Then you can create a dictionary as follows:

```python
    atoms = {'H': 1.01, 'He': 4.00, 'Li': 6.94, 'Na': 22.99, 'O': 16.00}
```

Some other examples are given below:

```python
# A dictorionary with list of values
models = {'Audi': ['A4', 'A5', 'A6', 'A7', 'A8'], 'BMW': ['X1', 'X3', 'X5'], 'Mercedes': ['C-Class', 'E-Class']}
print(models['BMW'][1])
```

#### Accessing dictionary elements

To access the value associated with a key, you can use square brackets `[]`:

```python
    print(atoms['Li'])
```

#### Adding and modifying dictionary elements

You can add a new key-value pair to a dictionary by assigning a value to a new key. For example, to add the atomic weight of carbon to the `atoms` dictionary:

```python
    atoms['C'] = 12.01
```

To modify an existing value, you can simply assign a new value to the key. Suppose you made a mistake in the atomic weight of sodium and want to correct it. Then you can do this by:

```python
    atoms['Na'] = 23.00
```

It is also possible to add values to an existing list of values. Suppose you want to add `A9` to the values list of the key `Audi`. You can do this by using the append method:

```python
# Add a new element to an existing list
models = {'Audi': ['A4', 'A5', 'A6', 'A7', 'A8'], 'BMW': ['X1', 'X3', 'X5'], 'Mercedes': ['C-Class', 'E-Class']}
models['Audi'].append('A9')
print(models['Audi'])
```

#### Removing dictionary elements

You can remove a key-value pair from a dictionary using the `del` keyword:

```python
    del atoms['He']
```

#### Searching for a key in a dictionary

You can check if a key is present in a dictionary using the `in` operator or the `keys()` method. The `in` operator returns `True` if the key is present in the dictionary, and `False` otherwise. The `keys()` method returns a view object that displays a list of all the keys in the dictionary:

```python
    print('H' in atoms)         # True
    print('H' in atoms.keys())  # True
    print('Ne' in atoms)        # False
```

#### Searching for a value in a dictionary

To check whether a value is present in a dictionary, you can use the `values()` method.

```python
values_list = atoms.values()
print(values_list)
list(values_list)  # convert the view to a list

# Output:
# dict_values([1.01, 4.0, 6.94, 22.99, 16.0])
# [1.01, 4.0, 6.94, 22.99, 16.0]
```

If the values consist of list of values than you have to use the `in` operator for every list.

```python
models = {'Audi': ['A4', 'A5', 'A6', 'A7', 'A8'], 'BMW': ['X1', 'X3', 'X5'], 'Mercedes': ['C-Class', 'E-Class']}
found = False
for models_list in models.values():
    if 'X1' in models_list:
        found = True
        break
print(found)	# True
```

Note that, in this case, if we use the `in` operator just once in `models.values()` it will return `False` because `X1` is not a value of the dictionary `models`. If we would look for `['X1', 'X3', 'X5']` then it would return `True`:

```python
models = {'Audi': ['A4', 'A5', 'A6', 'A7', 'A8'], 'BMW': ['X1', 'X3', 'X5'], 'Mercedes': ['C-Class', 'E-Class']}
print('X1' in models.values())			# False
print(['X1', 'X3', 'X5'] in models.values())	# True
```

#### File I/O - Introduction

In the previous chapters, we either defined our data directly in the code, asked the user for data input, or generated it using functions. However, in many cases, we need to read data from external sources, such as files.

A file is a collection of data stored on a disk. Files can be text files, which contain human-readable text (coded as ASCII or Unicode), or binary files, which contain data in a format that is not human-readable.

#### File location

When you want to open a file, you need to specify the file location. The file location can be either an absolute path or a relative path:

* An **absolute path** specifies the location of a file from the root directory.
* A **relative path** specifies the location of a file relative to the current working directory.

For example, if you have a file called `example.txt` in the current working directory, you can open it using the relative path `'example.txt'`. If you have a file called `example.txt` in a directory called `files` in the current working directory, you can open it using the relative path `'files/example.txt'`.

#### The `os` module

The `os` module provides a way of using operating system dependent functionality. The `os` module provides a way to interact with the file system.

The `os` module provides several functions to work with files and directories. Here are some of the most commonly used functions:

* `os.getcwd()`: returns the current working directory.
* `os.chdir(path)`: changes the current working directory to `path`.
* `os.listdir(path)`: returns a list of all files and directories in the directory specified by `path`.
* `os.mkdir(path)`: creates a new directory with the name `path`.

```python
import os

# Get the current working directory
print(os.getcwd())
```

`/home/kelvin/Documents/GitHub/PythonJourney`

```python
# Change the current working directory
os.chdir('files')

# Get the current working directory
print(os.getcwd())
```

`/home/kelvin/Documents/GitHub/PythonJourney/files`

```python
os.chdir("..")

# Get the current working directory
print(os.getcwd())
```

`/home/kelvin/Documents/GitHub/PythonJourney`

The `..` between the parentheses is a special path that refers to the parent directory of the current working directory. This is useful when you want **to move up one directory level**.

#### Reading text files

Reading data from a text files goes as follows:

* open the file with the `open()` function
* read the data using a a `for` loop, or the `read()`, `readline()`, or `readlines()` functions
* close the file with the `close()` function

#### Opening files

You can open a file using the `open()` function. The `open()` function takes two arguments:

* the name of the file you want to open and
* the mode in which you want to open the file. The mode can be
  * `"r"` for reading (default),
  * `"w"` for writing, or
  * `"a"` for appending.

The `open()` function returns a file object, which you can use to read from or write data to the file. Using a `for` loop, you can iterate over the lines of the file.

The file `data.txt` in the `files` directory. The file contains 5 lines of data. The following code reads the entire content of the file and prints it to the screen:

```python
f = open("files/data.txt", "r")
for line in f:
    print(line)
f.close()
```

`8.1

9

4.6

5.2

7`

The empty line between each line of output is due to the newline character `\n` at the end of each line in the file. The `print()` function adds another newline character by default. To avoid this, you can use the `end` parameter of the `print()` function and set it to an empty string. Another way is to get rid of the newline character using the `strip()` function. The `strip()` function removes leading and trailing whitespaces (including the newline character) from a string.

```python
f = open("files/data.txt", "r")
for line in f:
    print(line.strip())
f.close()
```

`8.1 9 4.6 5.2 7`

#### Built-in functions to read data from a file

Python has several functions to read data from a file:

* `read()`: read the entire content of the file as a **single string**
* `readline()`: read **one line** of the file
* `readlines()`: read **all lines** of the file and store them **in a list**

To close the file, you can use the function `close()`.

Consider the file `data.txt` in the `files` directory. The file contains 5 lines of data. The following code reads the entire content of the file into a list:

```python
    f = open("files/data.txt", "r") # "r" is optional
    data = f.readlines()
    f.close()
    print(data)
```

`['8.1\n', '9\n', '4.6\n', '5.2\n', '7']`

**Important notes**

* Each element of the list corresponds to a line of the file.
* The newline character `\n` is included in each element of the list. To get rid of the newline character, you can use the `strip()` function. The `strip()` function removes leading and trailing whitespaces (including the newline character) from a string.
* The values in the file are read (interpreted) as strings. If you want to convert the values to numbers (to perform calculations), you need to use the `int()` or `float()` functions.

The following code reads the entire content of the file into a list and converts the values to floating-point numbers:

```python
    f = open("files/data.txt", "r")
    data = f.readlines()
    f.close()
    for i in range(len(data)):
        data[i] = float(data[i].strip())
    print(data)
```

`[8.1, 9.0, 4.6, 5.2, 7.0]`

#### Processing file content

In many cases, you need to process the content of a file:

* You may need to remove the newline character.
* You may need to split the content of a file into words or numbers, or a combination of both.
* You may need to convert (part of) the content of a file to a different format.

The file `atoms.txt` contains a list of 50 atoms and their properties. For each atom the following data are given: the name of the atom, the symbol of the atom, and the atomic weight. The data are separated by comma and a space character.

The following code reads the content of the file and stores the data in a nested list. Each element of the nested list corresponds to a line of the file, and each element of the nested list is a list of strings. The atomic weight is converted to a floating-point number:

```python
    f = open("files/atoms.txt", "r")
    data = f.readlines()
    f.close()
    for i in range(len(data)):
        data[i] = data[i].strip().split(", ")	# Removes new line character, white space and splits by ", "
        data[i][-1] = float(data[i][-1])		# Of the new list, converts the last value into a float
    print(data)
```

`[['H', 'Hydrogen', 1.008], ['He', 'Helium', 4.0026], ['Li', 'Lithium', 6.9 . . .`

Note that the stripping and the splitting of the data are done in one line of code: first the newline character is removed, and then the string is split into a list of strings.

#### Writing to files

Writing data to a file goes as follows:

* open the file
* write the data
* close the file

You can use the `print()` function to write data to a file. The `print()` function takes an additional argument, `file`, which specifies the file object to which you want to write the data.

The following code reads user input and writes these and the number of words to a file called `words.txt`:

```python
    n = 0
    f = open("files/words.txt", "w")
    while True:
        word = input("Enter a word (or 'q' to quit): ")
        if word == "q":
            break
        n = n + 1
        print(word, file = f)
    print("Number of words:", n, file = f)
    f.close()
```

**Note**: if you forget to specify the file object `file = f`, the data will be written to the standard output (the screen).

#### Reading from a directory

Sometimes the data you need to process are stored in multiple files in a directory. You can read all files in a directory using the `os` module. The `os` module provides a function called `listdir()`, which returns a list of all files in a directory.

The following code lists all files in the `files` directory:

```python
    import os
    files = os.listdir("files")
    print(files)
```

`['codontable.csv', 'photo.txt', 'data.txt', 'template.txt', 'mendelejev.txt', 'numbers.txt', 'new_directory', 'words.txt', 'surrounded.txt', 'passwords.txt', 'atoms.txt', 'weakpasswords.txt', 'random2.txt', 'pH_data', 'names.txt', 'random.txt', 'matrix.txt', 'matrix2.txt', 'species.txt']`

**Example**

The directory `pH_data` contains several files, each of which contains one pH measurement. The following code reads all files in the directory and stores the pH measurements as floating-point numbers in a list:

```python
    import os
    pH = []
    files = os.listdir("files/pH_data")
    for file in files:
        file = open("files/pH_data/" + file, "r")
        pH.append(float(file.readline().strip()))
        file.close()
    print(pH)
```

`[6.931036696461067, 6.948686218625284, 7.049832715085693, 7.103096969166499, 6.561500654988191, . . .`

Note that the command `pH.append(float(file.readline().strip()))`

* reads the first (and only) line of the file,
* removes the newline character,
* converts the value to a floating-point number, and
* appends the value to the list `pH`.

The code will be more readible if we split this command into several lines:

```python
    import os
    pH = []
    files = os.listdir("files/pH_data")
    for file in files:
        f = open("files/pH_data/" + file, "r")
        line = f.readline()
        line = line.strip()
        pH.append(float(line))
        f.close()
    print(pH)
```

#### The infoFunWP module

The module `infoFunWP` is part of a package with the same name but is not part of the standard Python library.

The module contains the following functions to **read** files:

* `listRead()`: read the complete file and return a list of strings (one string per line)
* `listReadValues()`: read the complete file and return a list of floats (one float per line)
* `stringRead()`: read the complete file and return a **single string**

The module contains the following functions to **write** files:

* `listWrite()`: write a list of strings to a text file (one line per string)
* `stringWrite()`: write a string to a text file

In order to use the module, you need to install the package `infoFunWP` first. You can install the package using the following command in a terminal:

```python
    pip install infoFunWP
```

Next, you can import the module using the following command:

```python
    import infoFunWP as infoFun
```

A few examples of how to use the module are given below.

The function `listReadValues()` is very useful if the file contains a single column with numerical data. The function reads the data and returns a list of floating-point numbers:

```python
# read the content of the file data.txt in the files directory
import infoFunWP as infoFun
data = infoFun.listReadValues("files/data.txt")
print(data)

# The code is more concise and easier to read.
```

If the file contains text data, you can use the function `listRead()` to read the data and return a list of strings:

```python
# read the content of the file names.txt in the files directory
import infoFunWP as infoFun
names = infoFun.listRead("files/names.txt")
print(names)
```

When the file contains multiple columns of data such as in the file `atoms.txt`, you can use the function `listRead()` to read the data and to get a list of strings. You can then proceed to process the data:

* remove the newline character
* split each string into a list of strings
* convert to float
* ...

```python
# read the content of the file atoms.txt in the files directory
import infoFunWP as infoFun
data = infoFun.listRead("files/atoms.txt")
for i in range(len(data)):
    data[i] = data[i].strip().split(", ")
    data[i][-1] = float(data[i][-1])
print(data)
```

#### NumPy

NumPy (stands for Numerical Python) is a Python library that provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays. It is the fundamental package for scientific computing with Python.

#### Importing the NumPy module

To use NumPy, we need to import the `numpy` module. The standard way to import NumPy is by using the alias `np`.

```python
import numpy as np
```

#### Creating NumPy arrays

There are several ways to create NumPy arrays. Some of the common methods are:

* the `array()` function
* the `arange()` function
* the `linspace()` function
* the `zeros()` and `ones()` functions

#### The `array()` function

The `array()` function is used to create a NumPy array from a list or a tuple. The syntax for creating an array using the `array()` function is as follows:

```python
    np.array(object, dtype = None)
```

With:

* `object`: the input data,
* `dtype`: the data type of the resulting array (optional, default is `None`). Typical values are `int`, `float`, `str`. If `dtype` is not specified, the data type is inferred from the other input arguments.

```python
import numpy as np

# Create an array from a LIST
x = np.array([1, 2, 3, 4, 5])
print(x)
```

`[1 2 3 4 5]`

```python
# Create an array from a LIST of LISTS
M = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(M)
```

```
[[1 2 3]
 [4 5 6]
 [7 8 9]]
```

```python
# Array of bools
b = np.array([True, False, True, False, True])
print(b)
```

`[ True False  True False  True]`

In stead of typing `True` or `False`, we can use `1` or `0` to represent `True` or `False`, respectively:

```python
    np.array([1, 0, 1, 0], dtype = bool)
```

This will create the same array as in the previous example.

#### The `arange()` function

The `arange()` function is used to create **a 1D array with a range of values** between a start and end value. The syntax for creating an array using the `arange()` function is as follows:

```python
    np.arange(start, stop, step, dtype = None)
```

With:

* `start`: the starting value of the range (optional, default is 0),
* `stop`: the end value of the range (**not included** in the array),
* `step`: the step size between the values in the range (optional, default is 1),
* `dtype`: the data type of the resulting array (optional, default is `None`). Possible values are `int`, `float`, `str`. If `dtype` is not specified, the data type is inferred from the other input arguments.

```python
# decreasing array from 10 to 1
y = np.arange(10, 0, -1)
print(y)
```

`[10  9  8  7  6  5  4  3  2  1]`

#### The `linspace()` function

The `linspace()` function is used **to create a 1D array with a specified number of evenly spaced values between a start and end value**. The syntax for creating an array using the `linspace()` function is as follows:

```python
    np.linspace(start, stop, num = 50)
```

With:

* `start`: the starting value of the range,
* `stop`: the end value of the range (**included** in the array),
* `num`: the number of values to generate (optional, default is 50),

```python
import numpy as np
# divide the interval from 0 to 1 into 5 equal parts
x = np.linspace(0, 1, 5)
print(x)
```

`[0.   0.25 0.5  0.75 1.  ]`

There is a nice relationship between the step size `step` on one hand and `start`, `stop` and `num` on the other hand:

$$
step = \dfrac{stop - start}{num - 1}
$$

#### The `zeros()` and `ones()` functions

The `zeros()` and `ones()` functions are used to create arrays filled with zeros and ones, respectively. The syntax for creating an array using the `zeros()` and `ones()` functions is as follows:

```python
    np.zeros(shape, dtype = None)
    np.ones(shape, dtype = None)
```

With:

* `shape`: the shape of the array (a tuple of integers),
* `dtype`: the data type of the resulting array (optional, default is `None`). Possible values are `int`, `float` and `bool`. If `dtype` is not specified, the data type is `float`.

```python
import numpy as np

# create a 3x5 array of zeros
x = np.zeros((3, 5)) # default dtype is float64
print(x)
```

`[[1. 1. 1. 1. 1.]  [1. 1. 1. 1. 1.]  [1. 1. 1. 1. 1.]]`

#### Array attributes

NumPy arrays have several attributes that provide information about the array. Some of the common attributes are:

* `shape`: the shape of the array (a tuple of integers),
* `size`: the total number of elements in the array,
* `dtype`: the data type of the elements in the array,
* `ndim`: the number of dimensions of the array.

```python
# create a 1D array with values from 0 to 10
x = np.arange(1, 11)

# get the shape
print(x.shape)	# (10, )

# get the number of elements in x
print(x.size)	# 10

# get the number of dimensions of x
print(x.ndim)	# 1
```

Note that `x` is a 1D array.

#### Numpy Indexing and slicing arrays

1D NumPy arrays can be indexed and sliced in the same way as lists. The syntax for indexing and slicing **1D arrays** is as follows:

```python
    array[index]            # access an element at a specific index
    array[start:stop:step]  # slice the array from start to stop with a step size
```

With:

* `index`: the index of the element to access,
* `start`: the starting index of the slice,
* `stop`: the ending index of the slice (**not included** in the slice),
* `step`: the step size between the elements in the slice.

The following table summarizes some indexing and slicing possibilities (the variable `x` represents a 1D array):

|    Slice    | Meaning                                                                  |
| :----------: | ------------------------------------------------------------------------ |
|   `x[i]`   | element at index `i` (counting starts at 0)                            |
|  `x[i:j]`  | element `i` up to `j-1` (character `j` **not** included)     |
|  `x[i:]`  | element from `i` up to end of `x`                                    |
|  `x[:j]`  | element from start up to `j-1` (element  `j` **not** included) |
| `x[i:j:k]` | elements from `i` up to `j-1` in steps of `k`                      |
|   `x[:]`   | all elements                                                             |
| `x[::-1]` | all elements in**reversed** order                                  |

Negative indices can be used to access elements from the end of the array. The syntax for using negative indices is as follows:

```python
    array[-index]  # where index is a positive integer ranging from 1 to `len(array)`
```

The syntax for indexing and slicing **2D arrays** is as follows:

```python
    array[row, column]              # access an element at a specific row and column
    array[start:stop:step, :]       # slice the array along the rows
    array[:, start:stop:step]       # slice the array along the columns
    array[start_row:stop_row:step, start_column:stop_column:step]  # slice the array along the rows and columns
```

With:

* `row`: the index of the row to access,
* `column`: the index of the column to access,
* `start_row`: the starting index of the slice along the rows,
* `stop_row`: the ending index of the slice along the rows (**not included** in the slice),
* `start_column`: the starting index of the slice along the columns,
* `stop_column`: the ending index of the slice along the columns (**not included** in the slice),
* `step`: the step size between the elements in the slice.

```python
import numpy as np

# create a 2D array with 3 rows and 5 columns with the numbers from 1 to 15
M = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10], [11, 12, 13, 14, 15]])
print(M)

# get the element in the second row and the fourth column
print(M[1, 3])

# get the first row of M
print(M[0])

# get the third column of M
print(M[:, 2])

# get the subarray of M consisting of the first two rows and the last three columns
print(M[:2, 2:])
```

`[[ 1  2  3  4  5]  [ 6  7  8  9 10]  [11 12 13 14 15]] 9 [1 2 3 4 5] [ 3  8 13] [[ 3  4  5]  [ 8  9 10]]`

#### Numpy Element based iteration

1D NumPy arrays can be iterated over using a `for` loop. The syntax for iterating over the elements of an array is as follows:

```python
    for element in array:
        # do something with element
```

2D NumPy arrays can be iterated over using nested `for` loops. The syntax for iterating over the elements of a 2D array is as follows:

```python
    for row in array:
        for element in row:
            # do something with element
```

Note that

* the parameter `sep` in the first `print` statement is used to separate the elements of the array with a space,
* the `print` statement after the `for` loop is used to print a newline character after each row.

#### Index based iteration

1D NumPy arrays can be iterated over using the `range()` function. The syntax for iterating over the elements of an array using the `range()` function is as follows:

```python
    for i in range(len(array)):
        # do something with array[i]
```

2D NumPy arrays can be iterated over using nested `for` loops and the `range()` function. The syntax for iterating over the elements of a 2D array using the `range()` function is as follows:

```python
    r, k = array.shape
    for i in range(r):
        for j in range(k):
            # do something with array[i, j]
```

Selecting subarrays is a very powerful technique. It is used in many applications, such as image processing, signal processing, and machine learning.

In image processing, for example, we can use subarrays to search for objects in an image. To find an object in an image, we can use a template image that contains the object we are looking for. We can then slide the template image over the original image and compare the template image with the subarrays of the original image. If the template image matches a subarray of the original image, we have found the object.

#### Numpy Mathematical functions

NumPy provides a collection of mathematical functions that operate on arrays. Some of the common mathematical functions are:

* trigoniometric functions: `np.sin()`, `np.cos()`, `np.tan()`, ...
* exponential and logarithmic functions: `np.exp()`, `np.log()`, `np.log10()`, ...
* rounding functions: `np.fix()`, `np.round()`, ...
* aggregation functions: `np.min()`, `np.max()`, `np.sum()`, `np.median()`, ...
* searching functions: `np.argmax()`, `np.argmin()`, `np.nonzero()`, `np.unique()`, ...
* logical functions: `np.all()`, `np.any()`, ...
* mathematical constants: `np.pi`, `np.e`, ...

#### **Aggregation functions**

The aggregation functions operate on the entire array and **return a single value**. Some examples of using these functions are:

```python
import numpy as np
# create a 2D array with 3 rows and 5 columns with random numbers in the interval $[-10, 10]$
M = np.random.randint(-10, 11, (3, 5))
print(M)

# calculate the sum of all elements of M
s = np.sum(M)
print(s)

# calculate the maximum of all elements of M
m = np.max(M)
print(m)

# calculate the mean of all elements of M
avg = np.mean(M)
print(avg)
```

If we want to compute the sum (or maximum value or average) of each row or column of a 2D array, we can use the `axis` parameter. The `axis` parameter specifies the axis along which the aggregation function is applied. The syntax for using the `axis` parameter is as follows:

```python
    np.sum(array, axis = 0)  # compute the sum value along the columns
    np.max(array, axis = 1)  # compute the maximum value along the rows
    np.mean(array, axis = 1)  # compute the average along the rows
```

Some examples of using the `axis` parameter are:

```python
import numpy as np
# create a 2D array with 3 rows and 5 columns with random numbers in the interval $[-10, 10]$
M = np.random.randint(-10, 11, (3, 5))
print(M)

# calculate the sum along the columns
s = np.sum(M, axis = 0)
print(s)

# calculate the maximum along the rows
m = np.max(M, axis = 1)
print(m)

# calculate the mean along the rows
avg = np.mean(M, axis = 1)
print(avg)
```

#### **Searching functions**

The searching functions `np.argmax()` and `np.argmin()` operate on the entire array and **return a single value**:

* `np.argmax()`: returns the index of the maximum value in the array,
* `np.argmin()`: returns the index of the minimum value in the array,

Note that the `argmax()` and `argmin()` functions return the index of the **first occurrence** of the maximum and minimum values, respectively.

#### **The `np.nonzero()` function**

The `np.nonzero()` function returns the indices of the non-zero elements in the array:

* 1D array: returns a tuple with the indices of the non-zero elements,
* 2D array: returns a tuple with two arrays: the first array contains the row indices and the second array contains the column indices of the non-zero elements.

#### **The `np.unique()` function**

The `np.unique()` function returns the unique elements in the array:

* array of numbers: returns the unique numbers in the array, sorted in ascending order,
* array of strings: returns the unique strings in the array, sorted in lexicographical order.

#### **The `np.all()` and `np.any()` functions**

The `np.all()` and `np.any()` functions operate on the entire array and **return a single value**:

* `np.all()`: returns `True` if all elements in the array are `True`, otherwise `False`,
* `np.any()`: returns `True` if any element in the array is `True`, otherwise `False`.

#### Numpy Logical indexing

Logical indexing is a powerful feature of NumPy that allows you to access elements in an array based on a condition. We will illustrate the power of logical indexing with an example.

Consider the following 2D array `M`:

$$
M = \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9 \\
\end{bmatrix}
$$

Suppose we want to select all elements in `M` that are even. We can do this using `for` loops as follows:

```python
import numpy as np
# 3 times 5 matrix with random numbers between 0 and 25:
M = np.random.randint(0, 26, (3, 5))

print(M)

even_elements = []
for row in M:
    for element in row:
        if element % 2 == 0:
            even_elements.append(element)
print(even_elements)
```

However, this can be done more efficiently using logical indexing.
Let us start by creating a boolean array `even` that is `True` for all even elements in `M` and `False` otherwise:

```python
even = M % 2 == 0
print(even)
```

The expression `even = M % 2 == 0` returns a boolean array `even` with the same shape as `M`. The value of `even[i, j]` is `True` if `M[i, j]` is even and `False` otherwise.

We can now use the boolean array `even` to select the even elements in `M`:

The expression `M[even]` returns a 1D array with all elements in `M` that are even:

```python
even_elements = M[even]
print(even_elements)
```

Note that the even elements are **selected row by row**.

We can combine the previous two steps into a single line of code:

```python
    M[M % 2 == 0]
```

The expression `M[M % 2 == 0]` returns a 1D array with all elements in `M` that are even.

#### Form operations

Some form operations are available in NumPy. The most common form operations are:

* `reshape()`: to change the shape of an array
* `T`: to transpose an array
* `ravel()`: to flatten an array
* `concatenate()`: to concatenate arrays along a specified axis

#### The `reshape()` function

The `reshape()` function is used to change the shape of an array. The syntax for reshaping an array is as follows:

```python
    reshape(array, newshape, order = "C")
```

With:

* `array`: the array to reshape,
* `newshape`: the new shape of the array (a tuple of integers)
* `order`: the order in which the elements of the array are read. Possible values are `'C'` (row-major order) and `'F'` (column-major order). The default value is `'C'`.

If one of the dimensions in the new shape is `-1`, the value for that dimension is inferred from the length of the array and the remaining dimensions. For example, if the array has 12 elements and the new shape is `(2, -1)`, the resulting array will have 2 rows and 6 columns.

#### The `T` attribute

The `T` attribute is used to transpose an array. The syntax for transposing an array is as follows:

```python
    array.T
```

Note that there are no empty parentheses after `T`. This is because `T` is an **attribute of the array**, not a function.

#### The `ravel()` function

The `ravel()` function is used to flatten an array. The syntax for flattening an array is as follows:

```python
    ravel(array, order = "C")
```

With:

* `array`: the array to flatten,
* `order`: the order in which the elements of the array are read. Possible values are `"C"` (row-major order) and `"F"` (column-major order). The default value is `"C"`.

#### The `concatenate()` function

The `concatenate()` function is used to concatenate arrays along a specified axis. The syntax for concatenating arrays is as follows:

```python
    concatenate((array1, array2, ...), axis = 0)
```

With:

* `array1`, `array2`, ...: a tuple with the arrays to concatenate,
* `axis`: the axis along which to concatenate the arrays. Possible values are `0` (concatenate along the rows) and `1` (concatenate along the columns). The default value is `0`.

Note that 1D arrays are always concatenated along the rows. To concatenate 1D arrays along the columns, we **need to reshape the arrays to 2D arrays first**.

#### Broadcasting

Broadcasting is a powerful feature of NumPy that allows you to perform mathematical operations on arrays with different shapes. The smaller array is **broadcasted** to the shape of the larger array so that the shapes of the two arrays are compatible.

The rules of broadcasting are as follows:

1. If the arrays have a different number of dimensions, the shape of the smaller array is **padded** with ones on its left side until the number of dimensions of the two arrays is the same.
2. If the shape of the two arrays does not match in any dimension, the array with shape equal to 1 in that dimension is **stretched** to match the shape of the other array.
3. If the shape of the two arrays does not match in any dimension and neither array has shape equal to 1 in that dimension, a `ValueError` is raised.

#### File I/O with `loadtxt()` and `savetxt()`

NumPy provides functions to read and write arrays from and to text files. The `loadtxt()` function is used to read arrays from text files, and the `savetxt()` function is used to write arrays to text files.

#### The `loadtxt()` function

The `loadtxt()` function is used to read arrays from text files. The syntax for reading arrays from text files is as follows:

```python
    loadtxt(fname, dtype = float, delimiter = None)
```

With:

* `fname`: the name of the file to read,
* `dtype`: the data type of the elements in the array (optional, default is `float`),
* `delimiter`: the delimiter used to separate the values in the file (optional, default is white space).
