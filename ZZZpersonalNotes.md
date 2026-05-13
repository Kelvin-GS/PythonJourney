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
