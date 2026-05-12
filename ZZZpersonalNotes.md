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

...
